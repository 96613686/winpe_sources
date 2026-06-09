# WsCompareStringU

- ea: `0x18002ed4c`
- end: `0x18002ed98`
- name: `WsCompareStringU`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b70`
- `0x180009b80`
- `0x18002a06c`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002ed8d`
- `ntdll!RtlCompareUnicodeString` at `0x18002ed8d`

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
0x18002ed4c  mov     rax, rsp
0x18002ed4f  sub     rsp, 48h
0x18002ed53  add     dx, dx
0x18002ed56  add     r9w, r9w
0x18002ed5a  xorps   xmm0, xmm0
0x18002ed5d  xorps   xmm1, xmm1
0x18002ed60  movups  xmmword ptr [rax-18h], xmm0
0x18002ed64  mov     [rax-16h], dx
0x18002ed68  movups  xmmword ptr [rax-28h], xmm1
0x18002ed6c  mov     [rax-18h], dx
0x18002ed70  lea     rdx, [rax-28h]; String2
0x18002ed74  mov     [rax-10h], rcx
0x18002ed78  lea     rcx, [rax-18h]; String1
0x18002ed7c  mov     [rax-20h], r8
0x18002ed80  mov     r8b, 1; CaseInsensitive
0x18002ed83  mov     [rax-26h], r9w
0x18002ed88  mov     [rax-28h], r9w
0x18002ed8d  call    cs:__imp_RtlCompareUnicodeString
0x18002ed93  add     rsp, 48h
0x18002ed97  retn
```
