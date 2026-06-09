# WinNatLibDeleteStaticBindingEntry

- ea: `0x14001bcbc`
- end: `0x14001bce2`
- name: `WinNatLibDeleteStaticBindingEntry`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400319dc`
- `0x1400326d0`

## callees

- `0x14001ae34`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteStaticBindingEntry(__int64 a1, __int64 a2, _WORD *a3, int a4, char a5, int a6)
{
  return WinNatRemoveBindingReservation(a1 + 768, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x14001bcbc  sub     rsp, 38h
0x14001bcc0  mov     eax, [rsp+38h+arg_28]
0x14001bcc4  add     rcx, 300h
0x14001bccb  mov     [rsp+38h+var_10], eax
0x14001bccf  mov     al, [rsp+38h+arg_20]
0x14001bcd3  mov     [rsp+38h+var_18], al
0x14001bcd7  call    WinNatRemoveBindingReservation
0x14001bcdc  add     rsp, 38h
0x14001bce0  retn
```
