
## 定点数

<table>
 <tr>
    <td>16位机器数</td>
    <td>无符号数</td>
    <td colspan="3">整数</td>
    <td colspan="3">小数</td>
   </tr>
   <tr>
    <td></td>
    <td></td>
    <td>原码</td>
    <td>补码</td>
    <td>反码</td>
    <td>原码</td>
    <td>补码</td>
    <td>反码</td>
   </tr>
   <tr>
    <td>0 00..0</td>
    <td>0</td>
    <td>+0</td>
    <td>+-0</td>
    <td>+0</td>
    <td>+0.0</td>
    <td>+0.0</td>
    <td>+0.0</td>
   </tr>
   <tr>
    <td>0 11..1</td>
    <td>2^15-1</td>
    <td>+(2^15-1)</td>
    <td>+(2^15-1)</td>
    <td>+(2^15-1)</td>
    <td>+(1-2^-15)</td>
    <td>+(1-2^-15)</td>
    <td>+(1-2^-15)</td>
   </tr>
   <tr>
    <td>1 00..0</td>
    <td>2^15</td>
    <td>-0</td>
    <td>-2^15</td>
    <td>-0</td>
    <td>-0.0</td>
    <td>-1</td>
    <td>-0.0</td>
   </tr>
   <tr>
    <td>1 11..1</td>
    <td>2^16-1</td>
    <td>-(2^15-1)</td>
    <td>-(2^15-1)</td>
    <td>-(2^15-1)</td>
    <td>-(1-2^-15)</td>
    <td>-(1-2^-15)</td>
    <td>-(1-2^-15)</td>
   </tr>
   <tr>
    <td>范围</td>
    <td>0==>2^16-1</td>
    <td>-(2^15-1)==>(2^15-1)</td>
    <td>-2^15==>(2^15-1)</td>
    <td>-(2^15-1)==>(2^15-1)</td>
    <td>-(1-2^-15)==>(1-2^-15)</td>
    <td>-1==>(1-2^-15)</td>
    <td>-(1-2^-15)==>(1-2^-15)</td>
   </tr>
</table>

## 浮点数（1+4+1+10）=16位

注意对原码表示的尾数，最大正数为1-2^-10，最小正数为2^-10`0.00...01`，比此值还小的称为下溢

<table>
  <tr>
    <td></td>
    <td>A / a</td>
    <td>b</td>
    <td></td>
    <td>c</td>
    <td>B / d</td>
  </tr>
  <tr>
    <td>阶码-原码</td>
    <td>-(2^4-1)</td>
    <td></td>
    <td>==></td>
    <td></td>
    <td>(2^4-1)</td>
  </tr>
  <tr>
    <td>尾数-原码</td>
    <td>-(1-2^-10)</td>
    <td>-2^-10</td>
    <td>==></td>
    <td>2^-10</td>
    <td>(1-2^-10)</td>
  </tr>
  <tr>
    <td>范围</td>
    <td>2^B * a</td>
    <td>2^A * b</td>
    <td></td>
    <td>2^A * c</td>
    <td>2^B * d</td>
  </tr>
  <tr>
    <td></td>
    <td>===|----</td>
    <td>----|==</td>
    <td>0</td>
    <td>==|----</td>
    <td>----|===></td>
  </tr>
  <tr>
    <td>阶码-补码</td>
    <td>-2^4</td>
    <td></td>
    <td>==></td>
    <td></td>
    <td>(2^4-1)</td>
  </tr>
  <tr>
    <td>尾数-补码</td>
    <td>-1</td>
    <td>-2^-1</td>
    <td>==></td>
    <td>2^-1</td>
    <td>(1-2^-10)</td>
  </tr>
  <tr>
    <td>范围</td>
    <td>2^B * a</td>
    <td>2^A * b</td>
    <td></td>
    <td>2^A * c</td>
    <td>2^B * d</td>
  </tr>
  <tr>
    <td></td>
    <td>===|----</td>
    <td>----|==</td>
    <td>0</td>
    <td>==|----</td>
    <td>----|===></td>
  </tr>
</table>