# Sample Code

This page provides some sample code which may be used in your example component.

This code uses TypeScript, and the Markdown code fence to wrap the code.

```typescript
const serviceEntityPage = (
  <EntityLayout>
    <EntityLayout.Route path="/" title="Overview">
      <Grid container spacing={3} alignItems="stretch">
        <Grid item md={6}>
          <EntityAboutCard variant="gridItem" />
        </Grid>
      </Grid>
    </EntityLayout.Route>
    <EntityLayout.Route path="/docs" title="Docs">
      <EntityTechdocsContent />
    </EntityLayout.Route>
  </EntityLayout>
);
```

Here is an example of Python code:

```python
def getUsersInGroup(targetGroup, secure=False):

    if __debug__:
        print('targetGroup=[' + targetGroup + ']')
```

YAML example:

```yaml
parentKey:
  level1Key1: level1Value1
  level1Key2: level1Value2
  level1Key3:
    level2Key1: level2Value1
    level2_items:
      - item1Key1: item1Value1
        item1Key2: item1Value2
      - item2Key1: item2Value1
        item2Key2: item2Value2
  level1Key4: level1Value4
```
