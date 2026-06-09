# WPP_RECORDER_SF_sD

- ea: `0x140004198`
- end: `0x140004308`
- name: `WPP_RECORDER_SF_sD`
- size: `368`
- prototype: `__int64(__int64, unsigned __int8, unsigned int, unsigned __int16, __int64, const char *, ...)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x140002520`
- `0x1400033a0`
- `0x140003930`
- `0x1400063dc`
- `0x14000696c`
- `0x1400142d0`
- `0x140014570`
- `0x1400148bc`
- `0x1400149c0`
- `0x140014c90`
- `0x1400154ac`
- `0x140018970`
- `0x140018e28`
- `0x1400198a0`
- `0x140019c40`
- `0x140019da0`
- `0x14001a364`
- `0x14001e374`
- `0x14001e4f8`
- `0x14001f1c8`
- `0x14001f488`
- `0x14001fe40`
- `0x140020e60`
- `0x140024fb0`
- `0x140026260`
- `0x140026e30`
- `0x1400278a4`
- `0x14002a11c`
- `0x14002daa4`
- `0x140032d80`
- `0x140034c00`
- `0x140035804`

## callees

- `0x140004198`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400042ea`
- `WppRecorder!WppAutoLogTrace` at `0x1400042ea`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sD(
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
  int v19; // [rsp+20h] [rbp-78h]
  __int64 v20; // [rsp+A0h] [rbp+8h]
  va_list va; // [rsp+D0h] [rbp+38h] BYREF

  va_start(va, a6);
  v20 = a1;
  v6 = -1;
  v8 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = 5;
  v12 = a6;
  v13 = *((_DWORD *)&wil_details_featureDescriptors_a->Timer + 20 * v8 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v13, ((_BYTE)a3 - 1) & 0x1F)
    && *((_BYTE *)&wil_details_featureDescriptors_a->Timer + 80 * v8 + 1) >= a2 )
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
    pfnWppTraceMessage(
      *((_QWORD *)&wil_details_featureDescriptors_a->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      v16,
      v15,
      va,
      4,
      0);
    a1 = v20;
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
  return WppAutoLogTrace(a1, v9, a3, a5, v19, v12, v10, va, 4, 0);
}

```

## disassembly

```asm
0x140004198  mov     [rsp+arg_0], rcx
0x14000419d  push    rbx
0x14000419e  push    rbp
0x14000419f  push    rsi
0x1400041a0  push    rdi
0x1400041a1  push    r12
0x1400041a3  push    r13
0x1400041a5  push    r14
0x1400041a7  push    r15
0x1400041a9  sub     rsp, 58h
0x1400041ad  mov     r14, cs:wil_details_featureDescriptors_a
0x1400041b4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400041b8  mov     r13d, r8d
0x1400041bb  mov     esi, r8d
0x1400041be  lea     r8, aNull; "NULL"
0x1400041c5  shr     rsi, 10h
0x1400041c9  movzx   r15d, dl
0x1400041cd  lea     ebp, [rdi+6]
0x1400041d0  lea     ebx, [r13-1]
0x1400041d4  movzx   r12d, r9w
0x1400041d8  mov     r10d, ebx
0x1400041db  and     ebx, 1Fh
0x1400041de  shr     r10, 5
0x1400041e2  lea     rax, [rsi+rsi*4]
0x1400041e6  and     r10d, 7FFh
0x1400041ed  mov     edx, ebx
0x1400041ef  mov     rbx, [rsp+98h+arg_28]
0x1400041f7  lea     r11, [r10+rax*4]
0x1400041fb  mov     eax, [r14+r11*4+2Ch]
0x140004200  bt      eax, edx
0x140004203  jnb     loc_140004294
0x140004209  lea     r10, [rsi+rsi*4]
0x14000420d  add     r10, r10
0x140004210  cmp     [r14+r10*8+29h], r15b
0x140004215  jb      short loc_140004294
0x140004217  test    rbx, rbx
0x14000421a  jz      short loc_14000422E
0x14000421c  mov     rax, rdi
0x14000421f  inc     rax
0x140004222  cmp     byte ptr [rbx+rax], 0
0x140004226  jnz     short loc_14000421F
0x140004228  lea     rdx, [rax+1]
0x14000422c  jmp     short loc_140004231
0x14000422e  mov     rdx, rbp
0x140004231  mov     rax, cs:pfnWppTraceMessage
0x140004238  test    rbx, rbx
0x14000423b  mov     [rsp+98h+var_58], 0
0x140004244  mov     rcx, rbx
0x140004247  cmovz   rcx, r8
0x14000424b  mov     [rsp+98h+var_60], 4
0x140004254  lea     r8, [rsp+98h+arg_30]
0x14000425c  mov     r9d, r12d
0x14000425f  mov     [rsp+98h+var_68], r8
0x140004264  mov     r8, [rsp+98h+arg_20]
0x14000426c  mov     [rsp+98h+var_70], rdx
0x140004271  mov     edx, 2Bh ; '+'
0x140004276  mov     [rsp+98h+var_78], rcx
0x14000427b  mov     rcx, [r14+r10*8+18h]
0x140004280  call    _guard_dispatch_icall
0x140004285  mov     rcx, [rsp+98h+arg_0]
0x14000428d  lea     r8, aNull; "NULL"
0x140004294  test    rbx, rbx
0x140004297  jz      short loc_1400042A9
0x140004299  inc     rdi
0x14000429c  cmp     byte ptr [rbx+rdi], 0
0x1400042a0  jnz     short loc_140004299
0x1400042a2  lea     rbp, [rdi+1]
0x1400042a6  test    rbx, rbx
0x1400042a9  mov     r9, [rsp+98h+arg_20]
0x1400042b1  lea     rax, [rsp+98h+arg_30]
0x1400042b9  mov     [rsp+98h+var_50], 0
0x1400042c2  cmovz   rbx, r8
0x1400042c6  mov     [rsp+98h+var_58], 4
0x1400042cf  mov     r8d, r13d
0x1400042d2  mov     [rsp+98h+var_60], rax
0x1400042d7  mov     edx, r15d
0x1400042da  mov     [rsp+98h+var_68], rbp
0x1400042df  mov     [rsp+98h+var_70], rbx
0x1400042e4  mov     word ptr [rsp+98h+var_78], r12w
0x1400042ea  call    cs:__imp_WppAutoLogTrace
0x1400042f1  nop     dword ptr [rax+rax+00h]
0x1400042f6  add     rsp, 58h
0x1400042fa  pop     r15
0x1400042fc  pop     r14
0x1400042fe  pop     r13
0x140004300  pop     r12
0x140004302  pop     rdi
0x140004303  pop     rsi
0x140004304  pop     rbp
0x140004305  pop     rbx
0x140004306  retn
```
