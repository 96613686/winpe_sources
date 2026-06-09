# WPP_RECORDER_SF_sDqd

- ea: `0x1400053f8`
- end: `0x1400055be`
- name: `WPP_RECORDER_SF_sDqd`
- size: `454`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140014008`
- `0x140017b48`
- `0x14001b0bc`
- `0x14001b524`
- `0x14001c688`
- `0x140025220`
- `0x140026de0`
- `0x140029608`
- `0x140029d34`
- `0x14002f9f8`

## callees

- `0x1400053f8`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400055a0`
- `WppRecorder!WppAutoLogTrace` at `0x1400055a0`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDqd(
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
      8,
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
           8,
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
0x1400053f8  mov     [rsp+arg_0], rcx
0x1400053fd  push    rbx
0x1400053fe  push    rbp
0x1400053ff  push    rsi
0x140005400  push    rdi
0x140005401  push    r12
0x140005403  push    r13
0x140005405  push    r14
0x140005407  push    r15
0x140005409  sub     rsp, 78h
0x14000540d  mov     r14, cs:WPP_GLOBAL_Control
0x140005414  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005418  mov     r13d, r8d
0x14000541b  mov     esi, r8d
0x14000541e  lea     r8, aNull; "NULL"
0x140005425  shr     rsi, 10h
0x140005429  movzx   r15d, dl
0x14000542d  lea     ebp, [rdi+6]
0x140005430  lea     ebx, [r13-1]
0x140005434  movzx   r12d, r9w
0x140005438  mov     r10d, ebx
0x14000543b  lea     r9d, [rdi+5]
0x14000543f  shr     r10, 5
0x140005443  lea     rax, [rsi+rsi*4]
0x140005447  and     ebx, 1Fh
0x14000544a  and     r10d, 7FFh
0x140005451  mov     edx, ebx
0x140005453  mov     rbx, [rsp+0B8h+arg_28]
0x14000545b  lea     r11, [r10+rax*4]
0x14000545f  mov     eax, [r14+r11*4+2Ch]
0x140005464  bt      eax, edx
0x140005467  jnb     loc_140005526
0x14000546d  lea     r10, [rsi+rsi*4]
0x140005471  add     r10, r10
0x140005474  cmp     [r14+r10*8+29h], r15b
0x140005479  jb      loc_140005526
0x14000547f  test    rbx, rbx
0x140005482  jz      short loc_140005496
0x140005484  mov     rax, rdi
0x140005487  inc     rax
0x14000548a  cmp     byte ptr [rbx+rax], 0
0x14000548e  jnz     short loc_140005487
0x140005490  lea     rdx, [rax+1]
0x140005494  jmp     short loc_140005499
0x140005496  mov     rdx, rbp
0x140005499  mov     rax, cs:pfnWppTraceMessage
0x1400054a0  test    rbx, rbx
0x1400054a3  mov     [rsp+0B8h+var_58], 0
0x1400054ac  mov     rcx, rbx
0x1400054af  mov     [rsp+0B8h+var_60], r9
0x1400054b4  cmovz   rcx, r8
0x1400054b8  lea     r8, [rsp+0B8h+arg_40]
0x1400054c0  mov     [rsp+0B8h+var_68], r8
0x1400054c5  lea     r8, [rsp+0B8h+arg_38]
0x1400054cd  mov     [rsp+0B8h+var_70], 8
0x1400054d6  mov     [rsp+0B8h+var_78], r8
0x1400054db  lea     r8, [rsp+0B8h+arg_30]
0x1400054e3  mov     [rsp+0B8h+var_80], r9
0x1400054e8  mov     r9d, r12d
0x1400054eb  mov     [rsp+0B8h+var_88], r8
0x1400054f0  mov     r8, [rsp+0B8h+arg_20]
0x1400054f8  mov     [rsp+0B8h+var_90], rdx
0x1400054fd  mov     edx, 2Bh ; '+'
0x140005502  mov     [rsp+0B8h+var_98], rcx
0x140005507  mov     rcx, [r14+r10*8+18h]
0x14000550c  call    _guard_dispatch_icall
0x140005511  mov     rcx, [rsp+0B8h+arg_0]
0x140005519  lea     r8, aNull; "NULL"
0x140005520  mov     r9d, 4
0x140005526  test    rbx, rbx
0x140005529  jz      short loc_14000553B
0x14000552b  inc     rdi
0x14000552e  cmp     byte ptr [rbx+rdi], 0
0x140005532  jnz     short loc_14000552B
0x140005534  lea     rbp, [rdi+1]
0x140005538  test    rbx, rbx
0x14000553b  mov     [rsp+0B8h+var_50], 0
0x140005544  lea     rax, [rsp+0B8h+arg_40]
0x14000554c  mov     [rsp+0B8h+var_58], r9
0x140005551  cmovz   rbx, r8
0x140005555  mov     [rsp+0B8h+var_60], rax
0x14000555a  mov     r8d, r13d
0x14000555d  mov     [rsp+0B8h+var_68], 8
0x140005566  lea     rax, [rsp+0B8h+arg_38]
0x14000556e  mov     [rsp+0B8h+var_70], rax
0x140005573  mov     edx, r15d
0x140005576  mov     [rsp+0B8h+var_78], r9
0x14000557b  lea     rax, [rsp+0B8h+arg_30]
0x140005583  mov     r9, [rsp+0B8h+arg_20]
0x14000558b  mov     [rsp+0B8h+var_80], rax
0x140005590  mov     [rsp+0B8h+var_88], rbp
0x140005595  mov     [rsp+0B8h+var_90], rbx
0x14000559a  mov     word ptr [rsp+0B8h+var_98], r12w
0x1400055a0  call    cs:__imp_WppAutoLogTrace
0x1400055a7  nop     dword ptr [rax+rax+00h]
0x1400055ac  add     rsp, 78h
0x1400055b0  pop     r15
0x1400055b2  pop     r14
0x1400055b4  pop     r13
0x1400055b6  pop     r12
0x1400055b8  pop     rdi
0x1400055b9  pop     rsi
0x1400055ba  pop     rbp
0x1400055bb  pop     rbx
0x1400055bc  retn
```
