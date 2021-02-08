# powerbi-react-native
Power BI for React-Native which provides components and services to enabling developers to easily embed Power BI reports into their applications.

## Quick Start

### Import

```jsx
import { PowerBIEmbed } from 'powerbi-client-react';
```

### Embed a Power BI report
```jsx
<PowerBIEmbed
	embedConfig = {{
		type: 'report',   // Supported types: report, dashboard, tile, visual and qna
		id: '<Report Id>',
		embedUrl: '<Embed Url>',
		accessToken: '<Access Token>',
		tokenType: models.TokenType.Embed,
		settings: {
			panes: {
				filters: {
					expanded: false,
					visible: false
				}
			},
			background: models.BackgroundType.Transparent,
		}
	}}

	eventHandlers = {
		new Map([
			['loaded', function () {console.log('Report loaded');}],
			['rendered', function () {console.log('Report rendered');}],
			['error', function (event) {console.log(event.detail);}]
		])
	}

	cssClassName = { "report-style-class" }

	getEmbeddedComponent = { (embeddedReport) => {
		this.report = embeddedReport as Report;
	}}
/>
```
