# Observability Overview

Observability in Choreo provides the capability to visualize and monitor the performance of services deployed on Choreo. Choreo has in-built support for viewing the overall status, latencies, throughput data,  diagnostic data, and logs. Hence, you can use Choreo Observability to detect and troubleshoot anomalies in your services efficiently. 

## Dashboard
Choreo Observability dashboard gives you more than one way to monitor your services. This section introduces the dashboards.

### Dashboard overview

The following diagram shows the Observability dashboard:

![Dashboard overview](../../assets/img/observability/overview-overall.png){.cInlineImage-full}

!!! note
    The observability dashboard for non-Ballerina components doed not display the low-code diagram. Therefore, the functionality within the low-code diagram is available only to Ballerina components. 

The Observability dashboard allows you to:

- Observe the throughput and latencies of requests served over a given period.
- View the logs generated over a given period.
- Compare metrics side-by-side for better diagnosis.
- Observe the flame graph (Diagnostics view) generated over a given period (not available for non-Ballerina components).
- View the low-code diagram (not available for non-Ballerina components).
- Trace requests (not available for non-Ballerina components).

!!! info
    By default, automatic refreshing is turned off for the Observability view. You can configure the Observability view to be automatically refreshed at a specified time interval via this field.
    ![../../assets/img/observability/options-bar.png]

!!! note
    The Observability view is private and is only visible to the service owner.


### Throughput and latency graphs

The throughput graph shows the throughput of requests per hour for a selected timestamp.   

![Throughput and latency graph](../../assets/img/observability/throughput-and-latency.png){.cInlineImage-full}

!!! note
    The low-code diagram is not available for non-ballerina components. 
    
By default, Choreo renders this graph for the data generated within the past 24 hours. You can change the default time window by selecting the time range and zone from the options bar. To expand the graph, click and drag the cursor over the period you want to drill down. 

You can view the Choreo service logs in the **Logs** view below the graph. Clicking on either graph updates the **Logs** view to contain the corresponding log entries generated at that time. You can use these logs to identify the reasons for any latency and throughput anomalies you detect using the graph.

The following figure shows an example of this:

![Logs view](../../assets/img/observability/logs.png){.cInlineImage-full}

### Diagnostics view

The **Diagnostics view** provides the capability to view errors, throughput, latencies, CPU usage, memory usage, and logs simultaneously for a particular event. You can detect and analyze errors and anomalies in detail via the **Diagnostics view**.

By default, the time range selected for the **Throughput & Latency** graphs is the same time range used for the **Diagnostics view**.

![Diagnostic view](../../assets/img/observability/diagnostic-view.png){.cInlineImage-full}


A **bin** is a horizontal section of the graph for a particular period. A bin consists of the following items:

- **Date/Time:** The timestamp for the log entries as they started to appear.
- **Logs:**  List of log entries and their respective log count that occurred within the bins time frame. These log entries appear according to precedence. The error logs are listed first, followed by the info logs. Each bin shows a maximum of five log entries sorted by the log count.
- **Error:** The number of HTTP errors that occurred at the selected time.
- **TP:** Throughput of the requests at the selected time (req/s).
- **Latency:** Latency of the request at the selected time (ms).
- **CPU:** CPU usage at the selected time (millicores).
- **Memory:** Memory usage at the selected time (MiB).


## View and filter all logs

The **Logs** panel includes all logs generated by the service. You can filter it based on time or based on text. The following figure shows how this might look:

![Logs panel](../../assets/img/observability/logs-panel.png){.cInlineImage-full}

To download the log entries, click **Download**. As a result, the log entries are saved as a .zip file in the location you specify.


### Trace requests

You can trace requests received by your service at a given timestamp by clicking a point in the time axis of either the throughput or the latency graphs.  The low-code view shows the received requests.
For each request in the low-code view, it displays the request time, the latency, and the status. Furthermore, when you click on a specific request, you can view the status code, request latency, the path (control flow) followed to execute the request, and the execution time per `if`, `while`, and `foreach` body.
The low-code diagram also displays the average request latency and the success rate for each client request that corresponds to the selected time interval.