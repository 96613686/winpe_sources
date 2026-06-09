# WinNatLibDereferenceAddressEntry

- ea: `0x14000c9d8`
- end: `0x14000ca04`
- name: `WinNatLibDereferenceAddressEntry`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400085d0`
- `0x14001915c`
- `0x140019320`
- `0x140019428`
- `0x1400196a4`
- `0x140019adc`
- `0x140019c78`
- `0x140019edc`
- `0x14001a878`

## callees

- `0x14000c9d8`
- `0x14000d410`

## pseudocode

```c
__int64 __fastcall WinNatLibDereferenceAddressEntry(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return WinNatLibCleanupAddressEntry((PVOID)a1);
  }
  return result;
}

```

## disassembly

```asm
0x14000c9d8  sub     rsp, 28h
0x14000c9dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c9e0  lock xadd [rcx], rax
0x14000c9e5  sub     rax, 1
0x14000c9e9  jg      short loc_14000C9FE
0x14000c9eb  test    rax, rax
0x14000c9ee  jz      short loc_14000C9F9
0x14000c9f0  mov     ecx, 0Eh; P
0x14000c9f5  int     29h; Win8: RtlFailFast(ecx)
0x14000c9f7  jmp     short loc_14000C9FE
0x14000c9f9  call    WinNatLibCleanupAddressEntry
0x14000c9fe  add     rsp, 28h
0x14000ca02  retn
```
