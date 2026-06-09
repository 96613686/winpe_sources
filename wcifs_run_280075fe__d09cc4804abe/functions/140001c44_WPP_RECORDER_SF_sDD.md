# WPP_RECORDER_SF_sDD

- ea: `0x140001c44`
- end: `0x140001de5`
- name: `WPP_RECORDER_SF_sDD`
- size: `417`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a20c`
- `0x14001e700`
- `0x140023644`
- `0x1400241c4`
- `0x140035804`

## callees

- `0x140001c44`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001dbf`
- `WppRecorder!WppAutoLogTrace` at `0x140001dbf`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDD(
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
  int v19; // [rsp+20h] [rbp-88h]
  __int64 v20; // [rsp+60h] [rbp-48h]
  __int64 v21; // [rsp+68h] [rbp-40h]
  __int64 v22; // [rsp+70h] [rbp-38h]
  __int64 v23; // [rsp+78h] [rbp-30h]
  __int64 v24; // [rsp+80h] [rbp-28h]
  __int64 v25; // [rsp+88h] [rbp-20h]
  __int64 v26; // [rsp+90h] [rbp-18h]
  __int64 v27; // [rsp+98h] [rbp-10h]
  __int64 v28; // [rsp+A0h] [rbp-8h]
  __int64 v29; // [rsp+B0h] [rbp+8h]
  __int64 v30; // [rsp+E0h] [rbp+38h] BYREF
  va_list va; // [rsp+E0h] [rbp+38h]
  va_list va1; // [rsp+E8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v30 = va_arg(va1, _QWORD);
  v29 = a1;
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
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, const char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      v16,
      v15,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
    a1 = v29;
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
           va1,
           4,
           0,
           v20,
           v21,
           v22,
           v23,
           v24,
           v25,
           v26,
           v27,
           v28);
}

```

## disassembly

```asm
0x140001c44  mov     [rsp+arg_0], rcx
0x140001c49  push    rbx
0x140001c4a  push    rbp
0x140001c4b  push    rsi
0x140001c4c  push    rdi
0x140001c4d  push    r12
0x140001c4f  push    r13
0x140001c51  push    r14
0x140001c53  push    r15
0x140001c55  sub     rsp, 68h
0x140001c59  mov     r14, cs:WPP_GLOBAL_Control
0x140001c60  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140001c64  mov     r13d, r8d
0x140001c67  mov     esi, r8d
0x140001c6a  lea     r8, aNull; "NULL"
0x140001c71  shr     rsi, 10h
0x140001c75  movzx   r15d, dl
0x140001c79  lea     ebp, [rdi+6]
0x140001c7c  lea     ebx, [r13-1]
0x140001c80  movzx   r12d, r9w
0x140001c84  mov     r10d, ebx
0x140001c87  lea     r9d, [rdi+5]
0x140001c8b  shr     r10, 5
0x140001c8f  lea     rax, [rsi+rsi*4]
0x140001c93  and     ebx, 1Fh
0x140001c96  and     r10d, 7FFh
0x140001c9d  mov     edx, ebx
0x140001c9f  mov     rbx, [rsp+0A8h+arg_28]
0x140001ca7  lea     r11, [r10+rax*4]
0x140001cab  mov     eax, [r14+r11*4+2Ch]
0x140001cb0  bt      eax, edx
0x140001cb3  jnb     loc_140001D5B
0x140001cb9  lea     r10, [rsi+rsi*4]
0x140001cbd  add     r10, r10
0x140001cc0  cmp     [r14+r10*8+29h], r15b
0x140001cc5  jb      loc_140001D5B
0x140001ccb  test    rbx, rbx
0x140001cce  jz      loc_140001DDD
0x140001cd4  mov     rax, rdi
0x140001cd7  inc     rax
0x140001cda  cmp     byte ptr [rbx+rax], 0
0x140001cde  jnz     short loc_140001CD7
0x140001ce0  lea     rdx, [rax+1]
0x140001ce4  mov     rax, cs:pfnWppTraceMessage
0x140001ceb  test    rbx, rbx
0x140001cee  mov     [rsp+0A8h+var_58], 0
0x140001cf7  mov     rcx, rbx
0x140001cfa  mov     [rsp+0A8h+var_60], r9
0x140001cff  cmovz   rcx, r8
0x140001d03  lea     r8, [rsp+0A8h+arg_38]
0x140001d0b  mov     [rsp+0A8h+var_68], r8
0x140001d10  lea     r8, [rsp+0A8h+arg_30]
0x140001d18  mov     [rsp+0A8h+var_70], r9
0x140001d1d  mov     r9d, r12d
0x140001d20  mov     [rsp+0A8h+var_78], r8
0x140001d25  mov     r8, [rsp+0A8h+arg_20]
0x140001d2d  mov     [rsp+0A8h+var_80], rdx
0x140001d32  mov     edx, 2Bh ; '+'
0x140001d37  mov     [rsp+0A8h+var_88], rcx
0x140001d3c  mov     rcx, [r14+r10*8+18h]
0x140001d41  call    _guard_dispatch_icall
0x140001d46  mov     rcx, [rsp+0A8h+arg_0]
0x140001d4e  lea     r8, aNull; "NULL"
0x140001d55  mov     r9d, 4
0x140001d5b  test    rbx, rbx
0x140001d5e  jz      short loc_140001D70
0x140001d60  inc     rdi
0x140001d63  cmp     byte ptr [rbx+rdi], 0
0x140001d67  jnz     short loc_140001D60
0x140001d69  lea     rbp, [rdi+1]
0x140001d6d  test    rbx, rbx
0x140001d70  mov     [rsp+0A8h+var_50], 0
0x140001d79  lea     rax, [rsp+0A8h+arg_38]
0x140001d81  mov     [rsp+0A8h+var_58], r9
0x140001d86  cmovz   rbx, r8
0x140001d8a  mov     [rsp+0A8h+var_60], rax
0x140001d8f  mov     r8d, r13d
0x140001d92  mov     [rsp+0A8h+var_68], r9
0x140001d97  lea     rax, [rsp+0A8h+arg_30]
0x140001d9f  mov     r9, [rsp+0A8h+arg_20]
0x140001da7  mov     edx, r15d
0x140001daa  mov     [rsp+0A8h+var_70], rax
0x140001daf  mov     [rsp+0A8h+var_78], rbp
0x140001db4  mov     [rsp+0A8h+var_80], rbx
0x140001db9  mov     word ptr [rsp+0A8h+var_88], r12w
0x140001dbf  call    cs:__imp_WppAutoLogTrace
0x140001dc6  nop     dword ptr [rax+rax+00h]
0x140001dcb  add     rsp, 68h
0x140001dcf  pop     r15
0x140001dd1  pop     r14
0x140001dd3  pop     r13
0x140001dd5  pop     r12
0x140001dd7  pop     rdi
0x140001dd8  pop     rsi
0x140001dd9  pop     rbp
0x140001dda  pop     rbx
0x140001ddb  retn
0x140001ddd  mov     rdx, rbp
0x140001de0  jmp     loc_140001CE4
```
