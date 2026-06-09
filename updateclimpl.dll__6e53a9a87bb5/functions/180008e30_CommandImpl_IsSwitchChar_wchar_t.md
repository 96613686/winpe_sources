# CommandImpl::IsSwitchChar(wchar_t)

- ea: `0x180008e30`
- end: `0x180008e38`
- name: `?IsSwitchChar@CommandImpl@@EEAA_N_W@Z`
- size: `8`
- prototype: `bool __fastcall(CommandImpl *this, __int16)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall CommandImpl::IsSwitchChar(CommandImpl *this, __int16 a2)
{
  return a2 == 45;
}

```

## disassembly

```asm
0x180008e30  cmp     dx, 2Dh ; '-'
0x180008e34  setz    al
0x180008e37  retn
```
