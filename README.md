# Dash Google Auth
Basic example of using Google OAuth to authenticate and view a [Dash](https://dash.plot.ly/) app. Uses [flask dance](https://github.com/singingwolfboy/flask-dance) and a modified version of Plotly's own [dash auth](https://github.com/plotly/dash-auth) for authentication.

Steps to try this out yourself:
1. Set up a virtual environment and install the requirements (tested only with Python 2.7)
2. Follow the [Flask Dance Guide](http://flask-dance.readthedocs.io/en/latest/quickstarts/google.html) to create an app on the google admin console
3. Replace the variables for *server.config["GOOGLE_OAUTH_CLIENT_ID"]* and *server.config["GOOGLE_OAUTH_CLIENT_SECRET"]* in [init.py](./app/__init__.py) with values from the Google OAuth 2 client you should have set up in step 1. If you've set these up properly, you can find them at [https://console.developers.google.com/apis/credentials](https://console.developers.google.com/apis/credentials) under the section **OAuth 2.0 client IDs**
4. Replace authorized_emails from [init.py](./app/__init__.py) with whatever google emails you want to grant access to your app. In production, I'd recommend getting these from a database instead.
5. Run `python app.py` and open [localhost](http://localhost:8050/) in a browser window to try it out! If the app loads automatically without prompting a google login, that means you're already authenticated -- try using an incogntio window in this case if you want to see the login experience for a new user.
