# Microsoft.Internal.PInvoke.Extensions::RequiresSessionChange

- ea: `0xa80`
- end: `0xaba`
- name: `Microsoft.Internal.PInvoke.Extensions::RequiresSessionChange`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xac0`

## callees

- `0xa80`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldarg.0
0xa81  box      FEATURE_CHANGE_TIME
0xa86  ldc.i4.3
0xa87  box      FEATURE_CHANGE_TIME
0xa8c  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xa91  brtrue.s loc_AB8
0xa93  ldarg.0
0xa94  box      FEATURE_CHANGE_TIME
0xa99  ldc.i4.2
0xa9a  box      FEATURE_CHANGE_TIME
0xa9f  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xaa4  brtrue.s loc_AB8
0xaa6  ldarg.0
0xaa7  box      FEATURE_CHANGE_TIME
0xaac  ldc.i4.1
0xaad  box      FEATURE_CHANGE_TIME
0xab2  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xab7  ret
0xab8  ldc.i4.1
0xab9  ret
```
