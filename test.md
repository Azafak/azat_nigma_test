const { chromium } = require('playwright');

(async () => {
    const browser = await chromium.launch({ headless: false });
    const page = await browser.newPage();
    await page.goto('https://gymlog.ru/');
    await page.click('.registration-button.scroll'); 
    await page.fill('input[name="email"]', 'testnigma@gmail.com');
    await page.click('button'); 
    await page.waitForTimeout(5000);
    await page.goto('https://gymlog.ru/profile/login/');
    await page.fill('input[name="email"]', 'testnigma@gmail.com''); 
    await page.fill('input[name="password"]', 'password987');
    await page.click('button[type="submit"]');
    await page.waitForTimeout(5000);
    await browser.close();
})();
