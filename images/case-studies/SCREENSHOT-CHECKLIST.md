# Case Study Screenshot Checklist

Use this checklist to collect sanitized screenshots and visuals for each case study. Keep private tokens, customer data, internal URLs, account IDs, phone numbers, and exact revenue figures hidden or blurred.

## AI Facebook Comment Automation

- [x] n8n workflow overview, zoomed out enough to show the full flow (`ai-facebook-comment-automation/n8n-workflow-overview.png`)
- [x] Sanitized Facebook comment example: incoming question and automated reply (`ai-facebook-comment-automation/facebook-comment-reply-example.png`)
- [x] FAQ/data source screenshot showing how answers are grounded (`ai-facebook-comment-automation/faq-data-source.png`)
- [x] Safety/escalation logic screenshot: spam, complaint, bad comment, or human review branch (`ai-facebook-comment-automation/safety-escalation-logic.png`)
- [x] Before/after process diagram: manual comment monitoring vs filtered AI-assisted response workflow (`ai-facebook-comment-automation/before-after-process-diagram.png`)

## Facebook Auto Post for High-Viewed Products

- [x] n8n workflow overview showing schedule, product selection, image generation, QA, and Facebook posting (`facebook-auto-post-high-viewed-products/n8n-workflow-overview.png`)
- [x] Product analytics/source signal screenshot: top viewed products or selected product, sanitized (`facebook-auto-post-high-viewed-products/product-analytics-source-signal.png`)
- [x] Generated promo image example (`facebook-auto-post-high-viewed-products/generated-promo-image.png`)
- [x] AI QA gate screenshot showing pass/fail or validation result (`facebook-auto-post-high-viewed-products/ai-qa-gate-result.png`)
- [x] Published Facebook post example with private data hidden (`facebook-auto-post-high-viewed-products/published-facebook-post.png`)

## PC Build Gallery AI Data Entry

- [x] n8n workflow overview showing gallery intake, metadata improvement, image validation, upload, and publishing (`pc-build-gallery-ai-data-entry/n8n-workflow-overview.png`)
- [x] Before/after gallery entry: raw/rough build data vs cleaned title, tags, description (`pc-build-gallery-ai-data-entry/before-after-gallery-entry.png`)
- [x] Image validation screenshot: valid PC image vs rejected/invalid image branch (`pc-build-gallery-ai-data-entry/image-validation-branch.png`)
- [x] AI-generated setup image example with watermark (`pc-build-gallery-ai-data-entry/ai-generated-setup-image.png`)

## Auto Website Blogs

- [ ] n8n workflow overview showing RSS read, topic filter, metadata creation, HTML content, CMS write, and publish (`auto-website-blogs/n8n-workflow-overview.png`)
- [ ] RSS/topic queue screenshot, sanitized (`auto-website-blogs/rss-topic-queue.png`)
- [ ] AI relevance filter output: valid hardware topic vs rejected promo/deal topic (`auto-website-blogs/ai-relevance-filter-output.png`)
- [ ] Generated article HTML or CMS editor preview (`auto-website-blogs/generated-article-cms-preview.png`)
- [ ] Published blog post screenshot (`auto-website-blogs/published-blog-post.png`)

## Automated SMS Sales Report

- [x] AWS Lambda function page screenshot, showing function name only and sensitive config hidden (`auto-sms-sales-report/aws-lambda-function.png`)
- [x] AWS Scheduler/EventBridge rule screenshot showing the scheduled trigger (`auto-sms-sales-report/aws-scheduler-trigger.png`)
- [x] Sanitized SMS message example showing timestamp, sales, gross, and margin format with dummy numbers (`auto-sms-sales-report/sanitized-sms-example.png`)
- [x] AWS Lambda flowchart showing authentication, sales retrieval, formatting, and SMS delivery (`auto-sms-sales-report/aws-lambda-flowchart.png`)
- [ ] Before/after process diagram: manual login/report/message vs scheduled Lambda SMS (`auto-sms-sales-report/before-after-process-diagram.png`)
- [ ] Optional CloudWatch log screenshot showing successful run, with tokens/data removed (`auto-sms-sales-report/cloudwatch-success-log.png`)

## Looker Studio Sales ETL Automation

- [ ] AWS Glue job visual/DAG screenshot showing source tables, SQL transform, quality check, and output (`looker-studio-sales-etl/aws-glue-job-dag.png`)
- [ ] Sanitized SQL transform screenshot showing joins, with private table/database names hidden if needed (`looker-studio-sales-etl/sanitized-sql-transform.png`)
- [ ] S3/output dataset screenshot showing generated reporting file/folder, no bucket/account details (`looker-studio-sales-etl/s3-output-dataset.png`)
- [ ] Looker Studio dashboard screenshot with real layout but blurred/sanitized numbers (`looker-studio-sales-etl/looker-studio-dashboard.png`)
- [ ] Before/after process diagram: manual export/table joins/dashboard refresh vs Glue ETL to dashboard (`looker-studio-sales-etl/before-after-process-diagram.png`)
