# WPP_SF_Sdd

- ea: `0x14000da74`
- end: `0x14000db0b`
- name: `WPP_SF_Sdd`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004d70`
- `0x140009e70`

## callees

- `0x14000da74`
- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_Sdd(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, ...)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v8 = va_arg(va1, _QWORD);
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
           a2,
           a4,
           v6,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x14000da74  sub     rsp, 68h
0x14000da78  xor     r8d, r8d
0x14000da7b  mov     r10, rcx
0x14000da7e  test    r9, r9
0x14000da81  jz      short loc_14000DA9B
0x14000da83  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000da87  inc     rax
0x14000da8a  cmp     [r9+rax*2], r8w
0x14000da8f  jnz     short loc_14000DA87
0x14000da91  lea     rcx, ds:2[rax*2]
0x14000da99  jmp     short loc_14000DAA0
0x14000da9b  mov     ecx, 0Ah
0x14000daa0  mov     [rsp+68h+var_18], r8
0x14000daa5  lea     rax, aNull_0; "NULL"
0x14000daac  mov     r11d, 4
0x14000dab2  lea     r8, [rsp+68h+arg_28]
0x14000daba  mov     [rsp+68h+var_20], r11
0x14000dabf  test    r9, r9
0x14000dac2  mov     [rsp+68h+var_28], r8
0x14000dac7  lea     r8, [rsp+68h+arg_20]
0x14000dacf  mov     [rsp+68h+var_30], r11
0x14000dad4  cmovz   r9, rax
0x14000dad8  mov     rax, cs:pfnWppTraceMessage
0x14000dadf  mov     [rsp+68h+var_38], r8
0x14000dae4  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000daeb  mov     [rsp+68h+var_40], rcx
0x14000daf0  mov     rcx, r10
0x14000daf3  mov     [rsp+68h+var_48], r9
0x14000daf8  movzx   r9d, dx
0x14000dafc  lea     edx, [r11+27h]
0x14000db00  call    _guard_dispatch_icall
0x14000db05  add     rsp, 68h
0x14000db09  retn
```
