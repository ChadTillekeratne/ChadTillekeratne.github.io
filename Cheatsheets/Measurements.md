- SLI - Service Level Indicator
- SLO - Service Level Objective
- SLA - Service Level Agreement

# Incident Management
||Metric|Calculation|Good|Poor|Percentile
|--|--|--|--|--|--|
|TTD|time to detect
|TTE|time to engage
|TTA|time to acknowledge|when work begins
|TTF|time to fix
|TTM|time to mitigation
|TTR|time to recovery

- [[Seeking SRE] Chapter 4. Using Incident Metrics to Improve SRE at Scale
](https://www.oreilly.com/library/view/seeking-sre/9781491978856/ch04.html)
- https://www.atlassian.com/incident-management/kpis/common-metrics

||Metric|Calculation|Good|Poor|Percentile
|--|--|--|--|--|--|
|MTBF|Mean time between failures
|MTTF|Mean time to failure



# Performance

||Metric|Calculation|Good|Poor|Percentile
|--|--|--|--|--|--|
|TTFB|time to First Byte|
- [[web.dev] lighthouse - Chrome DevTools](https://github.com/GoogleChrome/lighthouse)


# Client - Loading and Rendering
## Web Vitals
- Largest Contentful Paint (LCP)
- First Input Delay (FID)
- Cumulative Layout Shift (CLS)

||Metric|Calculation|Good|Poor|Percentile
|--|--|--|--|--|--|
|LCP|Largest Contentful Paint||≤2500ms|>4000ms|75
|FID|First Input Delay||≤100ms|>300ms|75
|CLS|Cumulative Layout Shift||≤0.1|>0.25|75
- [[web.dev] Web Vitals Overview](https://web.dev/learn-web-vitals/)
- [[web.dev] Defining Core Web Vitals](https://web.dev/defining-core-web-vitals-thresholds/)
- [[Cloudflare] Introducing Automatic Platform Optimization, starting with WordPress
](https://blog.cloudflare.com/automatic-platform-optimizations-starting-with-wordpress/)

||Metric|Calculation|Good|Poor|Percentile
|--|--|--|--|--|--|
|FPC|[First Contentful Paint](https://web.dev/first-contentful-paint/)|time for first text or image is painted
|TBT|[Total Blocking Time](https://web.dev/lighthouse-total-blocking-time/)|
