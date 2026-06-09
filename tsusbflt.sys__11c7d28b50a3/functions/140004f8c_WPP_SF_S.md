# WPP_SF_S

- ea: `0x140004f8c`
- end: `0x140004ff7`
- name: `WPP_SF_S`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e80`
- `0x140004724`

## callees

- `0x140004f8c`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
           a2,
           a4,
           v5,
           0);
}

```

## disassembly

```asm
0x140004f8c  sub     rsp, 48h
0x140004f90  mov     r10, cs:pfnWppTraceMessage
0x140004f97  xor     r11d, r11d
0x140004f9a  test    r9, r9
0x140004f9d  jz      short loc_140004FB7
0x140004f9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004fa3  inc     rax
0x140004fa6  cmp     [r9+rax*2], r11w
0x140004fab  jnz     short loc_140004FA3
0x140004fad  lea     rax, ds:2[rax*2]
0x140004fb5  jmp     short loc_140004FBC
0x140004fb7  mov     eax, 0Ah
0x140004fbc  test    r9, r9
0x140004fbf  mov     [rsp+48h+var_18], r11
0x140004fc4  mov     [rsp+48h+var_20], rax
0x140004fc9  lea     r8, aNull_1; "NULL"
0x140004fd0  cmovz   r9, r8
0x140004fd4  mov     rax, r10
0x140004fd7  mov     [rsp+48h+var_28], r9
0x140004fdc  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004fe3  movzx   r9d, dx
0x140004fe7  mov     edx, 2Bh ; '+'
0x140004fec  call    _guard_dispatch_icall
0x140004ff1  add     rsp, 48h
0x140004ff5  retn
```
