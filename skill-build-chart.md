# Skill: Build a Chart
**File:** `skills/skill-build-chart.md`  
**Use when:** Adding a new chart or visualization to the dashboard.

---

## Chart Library
This project uses **Recharts**. Always use Recharts — do not introduce a second chart library.

---

## Steps

### 1. Decide the chart type
| Data type | Chart to use |
|---|---|
| Trend over time | `LineChart` or `AreaChart` |
| Comparison between categories | `BarChart` |
| Part-of-whole | `PieChart` with `innerRadius` (donut) |
| Funnel / drop-off | Custom `BarChart` horizontal |
| Distribution | `BarChart` |

### 2. Create the component file
- Location: `src/components/charts/`
- File name: `[ChartName]Chart.jsx` e.g. `RevenueLineChart.jsx`
- Always accept `data` as a prop — never hardcode data inside a chart component

```jsx
// Template
import { LineChart, Line, XAxis, YAxis, Tooltip, ResponsiveContainer } from 'recharts';

export default function MyChart({ data }) {
  return (
    <ResponsiveContainer width="100%" height={300}>
      <LineChart data={data}>
        <XAxis dataKey="name" />
        <YAxis />
        <Tooltip />
        <Line type="monotone" dataKey="value" stroke="var(--accent)" strokeWidth={2} />
      </LineChart>
    </ResponsiveContainer>
  );
}
```

### 3. Use CSS variables for colors
Always use the project's CSS variables, never hardcode hex values:
- `var(--accent)` — primary highlight color
- `var(--accent2)` — secondary color
- `var(--text)` — axis labels
- `var(--surface)` — tooltip background

### 4. Wrap in a Card
Every chart goes inside a `<Card>` component:
```jsx
<Card title="Monthly Revenue">
  <RevenueLineChart data={revenueData} />
</Card>
```

### 5. Add to the dashboard
Import and place in `src/pages/Dashboard.jsx` in the appropriate grid section.

### 6. Test responsiveness
Resize the browser window. `ResponsiveContainer` should handle this automatically.

---

## Notes
- Keep chart components pure — no API calls, no state inside chart files
- Custom tooltips go in `src/components/charts/tooltips/`
