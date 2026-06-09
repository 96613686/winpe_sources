# WsCompareStringU

- ea: `0x18003190c`
- end: `0x18003195f`
- name: `WsCompareStringU`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003db0`
- `0x18000a3a0`
- `0x18002c5a8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18003194d`
- `ntdll!RtlCompareUnicodeString` at `0x18003194d`

## pseudocode

```c
LONG __fastcall WsCompareStringU(WCHAR *a1, __int16 a2, WCHAR *a3, __int16 a4)
{
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING v6; // [rsp+30h] [rbp-18h] BYREF

  *(&v6.MaximumLength + 2) = 0;
  *(_DWORD *)&v6.MaximumLength = (unsigned __int16)(2 * a2);
  *(&v5.MaximumLength + 2) = 0;
  v6.Length = 2 * a2;
  v6.Buffer = a1;
  v5.Buffer = a3;
  *(_DWORD *)&v5.MaximumLength = (unsigned __int16)(2 * a4);
  v5.Length = 2 * a4;
  return RtlCompareUnicodeString(&v6, &v5, 1u);
}

```

## disassembly

```asm
0x18003190c  mov     rax, rsp
0x18003190f  sub     rsp, 48h
0x180031913  add     dx, dx
0x180031916  add     r9w, r9w
0x18003191a  xorps   xmm0, xmm0
0x18003191d  xorps   xmm1, xmm1
0x180031920  movups  xmmword ptr [rax-18h], xmm0
0x180031924  mov     [rax-16h], dx
0x180031928  movups  xmmword ptr [rax-28h], xmm1
0x18003192c  mov     [rax-18h], dx
0x180031930  lea     rdx, [rax-28h]; String2
0x180031934  mov     [rax-10h], rcx
0x180031938  lea     rcx, [rax-18h]; String1
0x18003193c  mov     [rax-20h], r8
0x180031940  mov     r8b, 1; CaseInsensitive
0x180031943  mov     [rax-26h], r9w
0x180031948  mov     [rax-28h], r9w
0x18003194d  call    cs:__imp_RtlCompareUnicodeString
0x180031954  nop     dword ptr [rax+rax+00h]
0x180031959  add     rsp, 48h
0x18003195d  retn
```
