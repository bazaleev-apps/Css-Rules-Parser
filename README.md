# Css-Rules-Parser
Get all used css rules of HTML elements

```javascript
function onlyUnique(value, index, self) {
    return self.indexOf(value) === index;
}

function getUsedCssDeclarations(elements) {

	let rules = getMatchedCSSRules(elements);
  let strings = rules.map(rule=> rule.parentRule.parentRule? rule.parentRule.parentRule.cssText: rule.parentRule.cssText);

  strings = strings.filter(onlyUnique);

	console.log(strings.join("\n\n"));
}

getUsedCssDeclarations(document.body);
```
