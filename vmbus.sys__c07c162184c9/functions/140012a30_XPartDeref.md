# XPartDeref

- ea: `0x140012a30`
- end: `0x140012a60`
- name: `XPartDeref`
- size: `48`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ff34`
- `0x140010344`
- `0x140010ddc`
- `0x140010e8c`
- `0x140010efc`
- `0x140011b28`
- `0x140012794`
- `0x1400134c4`
- `0x140013770`
- `0x140014680`
- `0x14002d178`

## callees

- `0x140012a30`
- `0x140012b28`

## pseudocode

```c
__int64 __fastcall XPartDeref(__int64 a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 160), 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return XPartDestroyp();
  }
  return result;
}

```

## disassembly

```asm
0x140012a30  sub     rsp, 28h
0x140012a34  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012a38  lock xadd [rcx+0A0h], rax
0x140012a41  sub     rax, 1
0x140012a45  jg      short loc_140012A5A
0x140012a47  test    rax, rax
0x140012a4a  jz      short loc_140012A55
0x140012a4c  mov     ecx, 0Eh
0x140012a51  int     29h; Win8: RtlFailFast(ecx)
0x140012a53  jmp     short loc_140012A5A
0x140012a55  call    XPartDestroyp
0x140012a5a  add     rsp, 28h
0x140012a5e  retn
```
