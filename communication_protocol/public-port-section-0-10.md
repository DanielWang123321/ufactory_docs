# Public Port Section（0-10）

## exGet version information

**Register：1(0x01)**

```
// Request
00 01 00 02 00 01 01 
```

<details>

<summary> Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//01       U8, Register
```

</details>

{% code overflow="wrap" %}
```
// Response
00 01 00 02 00 2A 01 00 36 2C 36 2C 58 49 31 32 30 32 2C 41 43 31 33 30 32 2C 76 31 2E 31 32 2E 31 30 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```
{% endcode %}

<details>

<summary> Response Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 2A    U16, Length 
//01       U8, Register
//00       U8, State
//36 2C 36 2C   U8, Type, Axes, 6,6,
//58 49 31 32 30 32 2C    U8, xArm Version XI1202,
//41 43 31 33 30 32 2C    U8, Control Box Version AC1302,
//76 31 2E 31 32 2E 31 30    U8, Firmware Version v1.12.10
//00 00 00 00 00 00 00 00 00 00 00 00 00 00   U8, null  
```

</details>





## Get SN information

**Register：2(0x02)**

```
// Request
 00 01 00 02 00 01 02
```

<details>

<summary>Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//02       U8, Register
```

</details>

{% code overflow="wrap" %}
```
// Response
00 01 00 02 00 2A 02 00 58 49 31 32 30 32 30 34 32 30 31 42 30 32 00 41 43 31 33 30 32 30 32 42 30 32 4C 30 32 0A 00 00 00 00 00 00 00 00 00 00
```
{% endcode %}

<details>

<summary>Response Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 2A    U16, Length 
//02       U8, Register
//00       U8, State
//58 49 31 32 30 32 30 34 32 30 31 42 30 32 00      U8, XI120204201B02
//41 43 31 33 30 32 30 32 42 30 32 4C 30 32 0A      U8, AC130202B02L02
//00 00 00 00 00 00 00 00 00 00     U8, null
```

</details>





## Reload friction parameters

**Register：4(0x04)**

```
// Request
00 01 00 02 00 01 04 
```

<details>

<summary>Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//04       U8, Register
```

</details>

<pre><code>// Response
00 01 00 02 00 02 04 <a data-footnote-ref href="#user-content-fn-1">10 </a>
</code></pre>

<details>

<summary>Response Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//04       U8, Register
//10       U8, State
```

</details>





## Get the value of Joint torque or actual current

**Register: 5(0x05)**

```
// Request
00 01 00 02 00 01 05
```

<details>

<summary>Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//05       U8, Register
```

</details>

<pre><code>// Response
<strong>00 01 00 02 00 03 05 <a data-footnote-ref href="#user-content-fn-2">00 00</a>
</strong></code></pre>

<details>

<summary>Response Description</summary>

{% code overflow="wrap" %}
```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 03    U16, Length 
//05       U8, Register
//00       U8, State
//00       U8, 0: Theoretical joint torque 1: Actual current of servo
```
{% endcode %}

</details>



## Get the radius of rotation of the target joint relative to the TCP

**Register：6(0x06)x**

```
// Request
00 01 00 02 00 02 06 06 
```

<details>

<summary>Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 01    U16, Length 
//06       U8, Register
//06       U8, Parameter 1(target joint:6)
```

</details>

```
// Response
00 01 00 02 00 06 06 10 00 00 00 00
```

<details>

<summary>Response Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 06    U16, Length 
//05       U8, Register
//10       U8, State
//00 00 00 00    U8, Parameter 1(Radius of rotation)
```

</details>



## Remote shut down the operating system

**Register10（0x0A）**

<pre><code>// Request
00 01 00 02 00 02 0A <a data-footnote-ref href="#user-content-fn-3">01 </a>
</code></pre>

<details>

<summary>Request Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 02    U16, Length 
//0A       U8,  Register
//01       U8,  1:remote shut down the operating system temporarily 2:reboot
```

</details>

```
// Response
00 01 00 02 00 02 0A 10
```



<details>

<summary>Response Description</summary>

```
//00 01    U16, Transaction ID
//00 02    U16, Protocol Identifier
//00 04    U16, Length 
//0A       U8, Register
//10       U8, State
```

</details>

























[^1]: 

[^2]: 

[^3]: 