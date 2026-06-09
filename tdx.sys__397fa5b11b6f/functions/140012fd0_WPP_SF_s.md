# WPP_SF_s

- ea: `0x140012fd0`
- end: `0x140013034`
- name: `WPP_SF_s`
- size: `100`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140004df4`
- `0x140006608`
- `0x14000f364`
- `0x14001154c`
- `0x140011820`
- `0x140011cb4`
- `0x140012400`

## callees

- `0x140012fd0`
- `0x140018590`

## pseudocode

```c
__int64 __fastcall WPP_SF_s(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v5; // rax
  __int64 v6; // rcx

  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           v6,
           0);
}

```

## disassembly

```asm
0x140012fd0  sub     rsp, 48h
0x140012fd4  mov     r10, rcx
0x140012fd7  test    r9, r9
0x140012fda  jz      short loc_140012FF0
0x140012fdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012fe0  inc     rax
0x140012fe3  cmp     byte ptr [r9+rax], 0
0x140012fe8  jnz     short loc_140012FE0
0x140012fea  lea     rcx, [rax+1]
0x140012fee  jmp     short loc_140012FF5
0x140012ff0  mov     ecx, 5
0x140012ff5  test    r9, r9
0x140012ff8  mov     [rsp+48h+var_18], 0
0x140013001  mov     [rsp+48h+var_20], rcx
0x140013006  lea     rax, aNull; "NULL"
0x14001300d  cmovz   r9, rax
0x140013011  mov     rcx, r10
0x140013014  mov     rax, cs:pfnWppTraceMessage
0x14001301b  mov     [rsp+48h+var_28], r9
0x140013020  movzx   r9d, dx
0x140013024  mov     edx, 2Bh ; '+'
0x140013029  call    _guard_dispatch_icall
0x14001302e  add     rsp, 48h
0x140013032  retn
```
