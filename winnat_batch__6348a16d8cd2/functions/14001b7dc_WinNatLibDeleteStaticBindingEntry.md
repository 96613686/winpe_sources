# WinNatLibDeleteStaticBindingEntry

- ea: `0x14001b7dc`
- end: `0x14001b802`
- name: `WinNatLibDeleteStaticBindingEntry`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400308ac`
- `0x1400315a0`

## callees

- `0x14001a954`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteStaticBindingEntry(__int64 a1, __int64 a2, _WORD *a3, int a4, char a5, int a6)
{
  return WinNatRemoveBindingReservation(a1 + 768, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x14001b7dc  sub     rsp, 38h
0x14001b7e0  mov     eax, [rsp+38h+arg_28]
0x14001b7e4  add     rcx, 300h
0x14001b7eb  mov     [rsp+38h+var_10], eax
0x14001b7ef  mov     al, [rsp+38h+arg_20]
0x14001b7f3  mov     [rsp+38h+var_18], al
0x14001b7f7  call    WinNatRemoveBindingReservation
0x14001b7fc  add     rsp, 38h
0x14001b800  retn
```
