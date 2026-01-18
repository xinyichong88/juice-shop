# Dry Principle
It means don't repeat yourself. In coding, there is no duplicate rules and logic can be exist only in one place.
DRY helps to reduce bugs, maintain code and improve security.

However, in this juice-shop challenge "Repeat Registration", I tried to register as a new customer.
I typed the 1st password and repeat it correctly, then will change the original password to a new password.
And I tried to register and it succeed. This shows validation logic is duplicated.

# Empty User Registration
I used burp suite and register a new account by turning on the proxy. Then after entering the email and password those, I found the post and send to repeater and click send. Then turn off proxy and delete the email and password into "". Then, click send again and empty registration challenge is done.

# Missing Encoding
I click phtowall and there is a textbox about cat emoji. I insipect this page and find the code and link related to it. Then, I used burp suite to encode the # sign for URL and it shows %23. So, I change each # to %23 and the image comes out.
*This # sign in URL allows server to ignore items after # and handles by browser. URL for each character need to be encoded.
| Character | Meaning             |
| #         | Fragment            |
| ?         | Start of query      |
| &         | Parameter separator |
| /         | Path separator      |
| =         | Key/value           |
| %         | Encoding indicator  |

# Mass Dispel (Closing all notifications at one go)
At first, I tried to inspect and find any clues but I can't find it. So, I searched online tutorials and it showed click shift with the cross sign of notifications. I tried it and successfully did complete that challenge. However, I'm curious on how to know is using shift and I asked Chtgpt. It says can inspect and find the js. script and find some keywords and succeed finding below code that required us to use shift.
*return s.Njj(c.closeNotification(r, i.shiftKey))

# Outdated Allowlist
I inspect a page and go to sources and click main.js. Then, I find the keyword of blockchain as it needs crypto currency address and consists of redirect keyword. Then, I copied the link and paste it in a new tab after the URL 3000/. Then, it brought me to that website.

# Extra coding challenge
## Scoreboard
{
    path: 'score-board', [REMAIN]
    component: ScoreBoardComponent [DELETE]
}
## Confidential Document
*Remove all these codes*
/* /ftp directory browsing and file download */
  app.use('/ftp', serveIndexMiddleware, serveIndex('ftp', { icons: true }))
  app.use('/ftp(?!/quarantine)/:file', servePublicFiles())
  app.use('/ftp/quarantine/:file', serveQuarantineFiles())
## Exposed Metrics
x app.get('/metrics', metrics.serveMetrics())
app.get('/metrics', security.isAdmin(), metrics.serveMetrics()) [make admin access only]

x export async function start (readyCallback?: () => void) {
export async function start (readyCallback: any) {


