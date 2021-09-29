# 在 trigger 觸發時存放資料
```js
preRun: (data, matches) => {
  // matches.target => 取得被點的目標
}

    {
      id: 'TEA Decree Nisi Gain',
      type: 'GainsEffect',
      netRegex: NetRegexes.gainsEffect({ effectId: kDecreeNisi }),
      run: (data, matches) => {
        const num = kDecreeNisi.indexOf(matches.effectId.toUpperCase());
        data.nisiMap ??= {};
        data.nisiMap[matches.target] = num;
      },
    },
```

# Debuff ID

* 水點名: 85E
* 雷點名: 85F
* 水耐性下降: 860
* 雷耐性下降: 861


```js
    {
      id: 'TEA Water Down',
      type: 'GainsEffect',
      netRegex: NetRegexes.gainsEffect({ effectId: '860' }),
      run: (data, matches) => {
        data.waterDown = matches.target;
      }
    },
    {
      id: 'TEA Lighting Down',
      type: 'GainsEffect',
      netRegex: NetRegexes.gainsEffect({ effectId: '861' }),
      run: (data, matches) => {
        data.lightningDown = matches.target;
      }
    },
```
