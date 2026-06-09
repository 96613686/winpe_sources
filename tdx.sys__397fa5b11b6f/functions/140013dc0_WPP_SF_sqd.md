# WPP_SF_sqd

- ea: `0x140013dc0`
- end: `0x140013e57`
- name: `WPP_SF_sqd`
- size: `151`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, char, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023b0`
- `0x1400039c0`
- `0x14000a1b0`
- `0x14000a5f0`

## callees

- `0x140013dc0`
- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_sqd(__int64 a1, unsigned __int16 a2, _DWORD a3, const char *a4, ...)
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
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, const char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
           a2,
           a4,
           v6,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x140013dc0  sub     rsp, 68h
0x140013dc4  mov     r10, rcx
0x140013dc7  test    r9, r9
0x140013dca  jz      short loc_140013DE0
0x140013dcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013dd0  inc     rax
0x140013dd3  cmp     byte ptr [r9+rax], 0
0x140013dd8  jnz     short loc_140013DD0
0x140013dda  lea     rcx, [rax+1]
0x140013dde  jmp     short loc_140013DE5
0x140013de0  mov     ecx, 5
0x140013de5  mov     [rsp+68h+var_18], 0
0x140013dee  lea     r8, [rsp+68h+arg_28]
0x140013df6  mov     [rsp+68h+var_20], 4
0x140013dff  lea     rax, aNull; "NULL"
0x140013e06  mov     [rsp+68h+var_28], r8
0x140013e0b  test    r9, r9
0x140013e0e  mov     [rsp+68h+var_30], 8
0x140013e17  lea     r8, [rsp+68h+arg_20]
0x140013e1f  mov     [rsp+68h+var_38], r8
0x140013e24  cmovz   r9, rax
0x140013e28  mov     rax, cs:pfnWppTraceMessage
0x140013e2f  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140013e36  mov     [rsp+68h+var_40], rcx
0x140013e3b  mov     rcx, r10
0x140013e3e  mov     [rsp+68h+var_48], r9
0x140013e43  movzx   r9d, dx
0x140013e47  mov     edx, 2Bh ; '+'
0x140013e4c  call    _guard_dispatch_icall
0x140013e51  add     rsp, 68h
0x140013e55  retn
```
