# WPP_RECORDER_SF_sDdd

- ea: `0x140004d7c`
- end: `0x140004f3a`
- name: `WPP_RECORDER_SF_sDdd`
- size: `446`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140014c90`
- `0x1400154ac`
- `0x14001a364`
- `0x140020e60`
- `0x140026210`
- `0x14002b788`
- `0x14002b9f0`

## callees

- `0x140004d7c`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004f1c`
- `WppRecorder!WppAutoLogTrace` at `0x140004f1c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDdd(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        ...)
{
  __int64 v6; // rdi
  unsigned __int64 v8; // rsi
  unsigned int v9; // r15d
  __int64 v10; // rbp
  const char *v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  const char *v16; // rcx
  bool v17; // zf
  int v19; // [rsp+20h] [rbp-98h]
  __int64 v20; // [rsp+70h] [rbp-48h]
  __int64 v21; // [rsp+78h] [rbp-40h]
  __int64 v22; // [rsp+80h] [rbp-38h]
  __int64 v23; // [rsp+88h] [rbp-30h]
  __int64 v24; // [rsp+90h] [rbp-28h]
  __int64 v25; // [rsp+98h] [rbp-20h]
  __int64 v26; // [rsp+A0h] [rbp-18h]
  __int64 v27; // [rsp+C0h] [rbp+8h]
  __int64 v28; // [rsp+F0h] [rbp+38h] BYREF
  va_list va; // [rsp+F0h] [rbp+38h]
  __int64 v30; // [rsp+F8h] [rbp+40h] BYREF
  va_list va1; // [rsp+F8h] [rbp+40h]
  va_list va2; // [rsp+100h] [rbp+48h] BYREF

  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v28 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v30 = va_arg(va2, _QWORD);
  v27 = a1;
  v6 = -1;
  v8 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = 5;
  v12 = a6;
  v13 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v8 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v13, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v8 + 1) >= a2 )
  {
    if ( a6 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a6[v14] );
      v15 = v14 + 1;
    }
    else
    {
      v15 = 5;
    }
    v16 = a6;
    if ( !a6 )
      v16 = "NULL";
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, const char *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      v16,
      v15,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
    a1 = v27;
  }
  v17 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v10 = v6 + 1;
    v17 = a6 == 0;
  }
  if ( v17 )
    v12 = "NULL";
  LOWORD(v19) = a4;
  return WppAutoLogTrace(
           a1,
           v9,
           a3,
           a5,
           v19,
           v12,
           v10,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           va2,
           4,
           0,
           v20,
           v21,
           v22,
           v23,
           v24,
           v25,
           v26);
}

```

## disassembly

```asm
0x140004d7c  mov     [rsp+arg_0], rcx
0x140004d81  push    rbx
0x140004d82  push    rbp
0x140004d83  push    rsi
0x140004d84  push    rdi
0x140004d85  push    r12
0x140004d87  push    r13
0x140004d89  push    r14
0x140004d8b  push    r15
0x140004d8d  sub     rsp, 78h
0x140004d91  mov     r14, cs:WPP_GLOBAL_Control
0x140004d98  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140004d9c  mov     r13d, r8d
0x140004d9f  mov     esi, r8d
0x140004da2  lea     r8, aNull; "NULL"
0x140004da9  shr     rsi, 10h
0x140004dad  movzx   r15d, dl
0x140004db1  lea     ebp, [rdi+6]
0x140004db4  lea     ebx, [r13-1]
0x140004db8  movzx   r12d, r9w
0x140004dbc  mov     r10d, ebx
0x140004dbf  lea     r9d, [rdi+5]
0x140004dc3  shr     r10, 5
0x140004dc7  lea     rax, [rsi+rsi*4]
0x140004dcb  and     ebx, 1Fh
0x140004dce  and     r10d, 7FFh
0x140004dd5  mov     edx, ebx
0x140004dd7  mov     rbx, [rsp+0B8h+arg_28]
0x140004ddf  lea     r11, [r10+rax*4]
0x140004de3  mov     eax, [r14+r11*4+2Ch]
0x140004de8  bt      eax, edx
0x140004deb  jnb     loc_140004EA6
0x140004df1  lea     r10, [rsi+rsi*4]
0x140004df5  add     r10, r10
0x140004df8  cmp     [r14+r10*8+29h], r15b
0x140004dfd  jb      loc_140004EA6
0x140004e03  test    rbx, rbx
0x140004e06  jz      short loc_140004E1A
0x140004e08  mov     rax, rdi
0x140004e0b  inc     rax
0x140004e0e  cmp     byte ptr [rbx+rax], 0
0x140004e12  jnz     short loc_140004E0B
0x140004e14  lea     rdx, [rax+1]
0x140004e18  jmp     short loc_140004E1D
0x140004e1a  mov     rdx, rbp
0x140004e1d  mov     rax, cs:pfnWppTraceMessage
0x140004e24  test    rbx, rbx
0x140004e27  mov     [rsp+0B8h+var_58], 0
0x140004e30  mov     rcx, rbx
0x140004e33  mov     [rsp+0B8h+var_60], r9
0x140004e38  cmovz   rcx, r8
0x140004e3c  lea     r8, [rsp+0B8h+arg_40]
0x140004e44  mov     [rsp+0B8h+var_68], r8
0x140004e49  lea     r8, [rsp+0B8h+arg_38]
0x140004e51  mov     [rsp+0B8h+var_70], r9
0x140004e56  mov     [rsp+0B8h+var_78], r8
0x140004e5b  lea     r8, [rsp+0B8h+arg_30]
0x140004e63  mov     [rsp+0B8h+var_80], r9
0x140004e68  mov     r9d, r12d
0x140004e6b  mov     [rsp+0B8h+var_88], r8
0x140004e70  mov     r8, [rsp+0B8h+arg_20]
0x140004e78  mov     [rsp+0B8h+var_90], rdx
0x140004e7d  mov     edx, 2Bh ; '+'
0x140004e82  mov     [rsp+0B8h+var_98], rcx
0x140004e87  mov     rcx, [r14+r10*8+18h]
0x140004e8c  call    _guard_dispatch_icall
0x140004e91  mov     rcx, [rsp+0B8h+arg_0]
0x140004e99  lea     r8, aNull; "NULL"
0x140004ea0  mov     r9d, 4
0x140004ea6  test    rbx, rbx
0x140004ea9  jz      short loc_140004EBB
0x140004eab  inc     rdi
0x140004eae  cmp     byte ptr [rbx+rdi], 0
0x140004eb2  jnz     short loc_140004EAB
0x140004eb4  lea     rbp, [rdi+1]
0x140004eb8  test    rbx, rbx
0x140004ebb  mov     [rsp+0B8h+var_50], 0
0x140004ec4  lea     rax, [rsp+0B8h+arg_40]
0x140004ecc  mov     [rsp+0B8h+var_58], r9
0x140004ed1  cmovz   rbx, r8
0x140004ed5  mov     [rsp+0B8h+var_60], rax
0x140004eda  mov     r8d, r13d
0x140004edd  mov     [rsp+0B8h+var_68], r9
0x140004ee2  lea     rax, [rsp+0B8h+arg_38]
0x140004eea  mov     [rsp+0B8h+var_70], rax
0x140004eef  mov     edx, r15d
0x140004ef2  mov     [rsp+0B8h+var_78], r9
0x140004ef7  lea     rax, [rsp+0B8h+arg_30]
0x140004eff  mov     r9, [rsp+0B8h+arg_20]
0x140004f07  mov     [rsp+0B8h+var_80], rax
0x140004f0c  mov     [rsp+0B8h+var_88], rbp
0x140004f11  mov     [rsp+0B8h+var_90], rbx
0x140004f16  mov     word ptr [rsp+0B8h+var_98], r12w
0x140004f1c  call    cs:__imp_WppAutoLogTrace
0x140004f23  nop     dword ptr [rax+rax+00h]
0x140004f28  add     rsp, 78h
0x140004f2c  pop     r15
0x140004f2e  pop     r14
0x140004f30  pop     r13
0x140004f32  pop     r12
0x140004f34  pop     rdi
0x140004f35  pop     rsi
0x140004f36  pop     rbp
0x140004f37  pop     rbx
0x140004f38  retn
```
