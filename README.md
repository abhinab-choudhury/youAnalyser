<img width="100" height="100" src="https://img.icons8.com/clouds/100/vont.png" alt="vont"/>

---

# YouTube Analyzer 📊

YouTube Analyzer is a web application that provides powerful tools for analyzing various YouTube channels. It allows users to visualize data, view insights, and gain a deeper understanding of channel performance through interactive graphs, tables, and charts.



## Features 🚀

- **Channel Insights**: Obtain key statistics and metrics about a YouTube channel, including subscriber count, views, and engagement.

- **Interactive Graphs**: Visualize channel growth, view trends, and compare performance over time with dynamic and customizable graphs.

- **Data Tables**: Access detailed data in tabular format, making it easy to analyze video information, likes, dislikes, and comments.

- **Engagement Metrics**: Understand audience engagement with metrics like likes, dislikes, comments, and shares.

- **User-Friendly Interface**: A simple and intuitive interface makes it easy for users to navigate and extract valuable insights.

- **Export Data**: Download analytical reports and graphs for further analysis or sharing with others.

## Installation and Usage 💻
1. Clone this repository:
    ```bash
    git clone https://github.com/yourusername/youtube-analyzer.git
    ```
2. Change Directory to youAnalyzer and install dependencies
    ```bash
     cd youtube-analyzer
     npm install
     ```
3. Install depedescies  
    ```bash
    npm install  
    ```
     
4. Start the local server
  
    ```bash
    npm run dev  
    ```
     


## Working:
   
  ### Libraries/API used:  
  - uses Youtube API to access data about specific Channel.
  - use D3.js a Javascritp Library to make interactive Graph and Chats
  - Material Icon for React
  - Boostrap v5

### Adding Python Dashboard into React App
  To integrate a Python dashboard into your React app with all its features, you'll typically use a method that allows you to embed the Python dashboard as a web component or iframe within your React application. Here's a step-by-step guide:

  1. **Choose a Python Dashboard Framework:** 
  First, ensure that your Python dashboard is built using a framework that allows it to be embedded as a web component or iframe. Some popular choices for creating web-based Python dashboards include Flask, Dash by Plotly, and Streamlit.

  2. **Expose the Dashboard as a Web Service:**
  Modify your Python dashboard application to expose its functionality via a web service or API. You can use Flask, FastAPI, or other Python web frameworks for this purpose. Create API endpoints that allow your React app to interact with the dashboard.

  3. **Run the Python Dashboard Server:**
  Ensure that your Python dashboard is running and accessible via a URL. This means that when you visit a specific URL, you can see and interact with your dashboard.

  4. **Embed the Dashboard in Your React App:**
  In your React application, you can use an iframe or a React component to embed the Python dashboard. Here are two approaches:

  a. **Using an `<iframe>`:**
  You can create an iframe element in your React component and set its `src` attribute to the URL of your Python dashboard. This approach is simple but provides limited interactivity between the React app and the dashboard.

  ```jsx
  import React from 'react';

  function Dashboard() {
      return (
              <iframe
              src="https://your-python-dashboard-url.com"
              width="100%"
              height="600"
              frameborder="0"
              scrolling="auto"
              title="Python Dashboard"
              ></iframe>
             );
  }

export default Dashboard;
```

b. **Using a React Component with Iframe:**
You can create a React component that encapsulates the iframe and provides additional interactivity by passing props and communicating with the iframe content through JavaScript's postMessage API.

```jsx
import React, { useRef } from 'react';

function Dashboard() {
    const iframeRef = useRef(null);

    const sendMessageToDashboard = (message) => {
        if (iframeRef.current) {
            iframeRef.current.contentWindow.postMessage(message, 'https://your-python-dashboard-url.com');
        }
    };

    return (
            <div>
            <button onClick={() => sendMessageToDashboard({ action: 'refresh' })}>Refresh Dashboard</button>
            <iframe
            ref={iframeRef}
            src="https://your-python-dashboard-url.com"
            width="100%"
            height="600"
            frameborder="0"
            scrolling="auto"
            title="Python Dashboard"
            ></iframe>
            </div>
           );
}

export default Dashboard;
```

5. **Handle Communication Between React and Python:**
If you need to pass data between your React app and the Python dashboard or trigger actions within the dashboard, you can use the `postMessage` API as shown in the React component above. Ensure that both sides (React and Python) have logic to handle these messages appropriately.

6. **Styling and Integration:**
Customize the styling of the embedded dashboard to match your React app's design. You may need to adjust CSS styles and layout to make it seamless.

7. **Testing and Deployment:**
Thoroughly test the integration to ensure that the Python dashboard works seamlessly within your React app. Once testing is successful, deploy the integrated React app, which includes the embedded Python dashboard, to your hosting environment.

By following these steps, you can integrate your Python dashboard into your React app and have full control over how it's presented and interacted with by your users.
