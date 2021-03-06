# svs-app
Services common library

### Boilerplate

HTML boilderplate
```html
<!--
    Include the services common styles.
-->
<link rel="stylesheet" type="text/css" href="https://encompasstechnologies.github.io/svs-app/css/svs-app.css">

<div id="svs-app-main">

    <!--
        You HTML code goes here. The default app style is
        a flex box orientated by column.
    -->

</div>

<!--
    Include the services common scripts
-->
<script async type="text/javascript" src="https://encompasstechnologies.github.io/svs-app/js/svs-app.js"></script>
```

JavaScript bolierplate
```javascript
/*
 * Debug mode is used to log app activity. By default only
 * critical errors are logged.
 */
window.debug = true;

class Main {
    constructor(selector) {
        this.app = $(dashboardItem).find(selector);
        this.args = Services.getArgs();

        this.app.css({ display: "flex" });

        svs.layoutDashboard(this.app);

        /*
         * Use this.args to store and load variables from the URL.
         *
         * For Example;
         * this.args.action = "Foo";
         * Services.setArgs(this.args);
         *
         * Then pass this.args around into your functions and execute the code based on the args.
         * This will allow you to keep the browser's history and refresh working.
         */
    }

    /*
     * You application code goes here. Use ES6 class style.
     *
     * For example;
     *
     * myFunction(arg) {
     *     [code];
     * }
     *
     * myVariable = "foo"
     *
     * Note: In ES6 classes you ommit the semicolan for methods and properties. You sill
     * use semicolans in the functions.
     */
    view(message) {
        this.app.html(`<h2>${message}</h2>`);
    }
}

$(document).on("appload", () => {
    svs.init(() => {
        const app = new Main("#svs-app-main");

        /*
         * Application entry code. Use this area to call your default view
         * or any other initial code that is not called in the Main constructor.
         */
        app.view("Hello World!");
    });
});

```

Gmail API
```html
<!--
    Include the services common styles.
-->
<link rel="stylesheet" type="text/css" href="https://encompasstechnologies.github.io/svs-app/css/svs-app.css">

<div id="svs-app-main">

    <!--
        You HTML code goes here. The default app style is
        a flex box orientated by column.
    -->

</div>

<!--
    Include the Gmail API first
-->
<script async src="https://apis.google.com/js/api.js" onload="this.onload = function(){}; gmailInit();" onreadystatechange="if (this.readyState === 'complete') this.onload()"></script>

<!--
    Include the services common scripts
-->
<script async type="text/javascript" src="https://encompasstechnologies.github.io/svs-app/js/svs-app.js"></script>

<!--
    Include these files to enable Gmail access
-->
<script async type="text/javascript" src="https://encompasstechnologies.github.io/svs-app/js/gmail.js"></script>
```
