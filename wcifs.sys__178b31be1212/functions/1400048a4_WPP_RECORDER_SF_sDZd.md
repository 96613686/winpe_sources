# WPP_RECORDER_SF_sDZd

- ea: `0x1400048a4`
- end: `0x140004b03`
- name: `WPP_RECORDER_SF_sDZd`
- size: `607`
- prototype: `__int64(__int64, unsigned __int8, unsigned int, unsigned __int16, __int64, const char *, ...)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140017f64`
- `0x140018b9c`
- `0x140018e28`
- `0x14001d5b0`
- `0x14001d8dc`
- `0x14001ecb8`
- `0x14001fc48`
- `0x140020434`
- `0x140025270`
- `0x140026cec`
- `0x140026e30`
- `0x140029658`
- `0x14002a664`
- `0x14002ad54`
- `0x14002cb38`
- `0x14002d648`
- `0x14002daa4`
- `0x140030da4`

## callees

- `0x1400048a4`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004ae2`
- `WppRecorder!WppAutoLogTrace` at `0x140004ae2`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDZd(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        ...)
{
  const char *v6; // rdi
  __int64 v7; // rbp
  unsigned __int64 v10; // rsi
  unsigned int v11; // edx
  const wchar_t *v12; // rbx
  int v13; // eax
  __int64 v14; // r15
  __int64 v15; // rdx
  const wchar_t *v16; // r11
  const wchar_t *v17; // r9
  __int64 v18; // rax
  __int64 v19; // r8
  const char *v20; // rcx
  bool v21; // zf
  bool v22; // zf
  int v24; // [rsp+20h] [rbp-A8h]
  __int64 v25; // [rsp+D0h] [rbp+8h]
  unsigned __int16 v28; // [rsp+E8h] [rbp+20h]
  __int64 v29; // [rsp+100h] [rbp+38h] BYREF
  va_list va; // [rsp+100h] [rbp+38h]
  unsigned __int16 *v31; // [rsp+108h] [rbp+40h]
  va_list va1; // [rsp+110h] [rbp+48h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v29 = va_arg(va1, _QWORD);
  v31 = va_arg(va1, unsigned __int16 *);
  v28 = a4;
  v25 = a1;
  v6 = a6;
  v7 = -1;
  v10 = (unsigned __int64)a3 >> 16;
  v11 = ((_BYTE)a3 - 1) & 0x1F;
  v12 = v31;
  v13 = *((_DWORD *)&wil_details_featureDescriptors_a->Timer + 20 * v10 + ((unsigned __int16)(a3 - 1) >> 5) + 1);
  v14 = 5;
  if ( !_bittest(&v13, v11) || *((_BYTE *)&wil_details_featureDescriptors_a->Timer + 80 * v10 + 1) < a2 )
    goto LABEL_18;
  if ( !v31 )
  {
    v15 = 8;
    goto LABEL_7;
  }
  v15 = *v31;
  if ( !*v31 )
  {
LABEL_7:
    v16 = L"NULL";
    goto LABEL_8;
  }
  v16 = (const wchar_t *)*((_QWORD *)v31 + 1);
LABEL_8:
  v17 = v31;
  if ( !v31 )
    v17 = L"\b";
  if ( a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a6[v18] );
    v19 = v18 + 1;
  }
  else
  {
    v19 = 5;
  }
  v20 = a6;
  if ( !a6 )
    v20 = "NULL";
  ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, const char *, __int64, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
    *((_QWORD *)&wil_details_featureDescriptors_a->AttachedDevice + 10 * v10),
    43,
    a5,
    v28,
    v20,
    v19,
    (__int64 *)va,
    4,
    v17,
    2,
    v16,
    v15,
    va1,
    4,
    0);
  a4 = v28;
  a1 = v25;
LABEL_18:
  v21 = v12 == 0;
  if ( v12 )
    v21 = 0;
  if ( v21 )
    v12 = L"\b";
  v22 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v14 = v7 + 1;
    v22 = a6 == 0;
  }
  if ( v22 )
    v6 = "NULL";
  LOWORD(v24) = a4;
  return WppAutoLogTrace(a1, a2, a3, a5, v24, v6, v14, (__int64 *)va, 4, v12);
}

```

## disassembly

```asm
0x1400048a4  mov     rax, rsp
0x1400048a7  mov     [rax+20h], r9w
0x1400048ac  mov     [rax+18h], r8d
0x1400048b0  mov     [rax+10h], dl
0x1400048b3  mov     [rax+8], rcx
0x1400048b7  push    rbx
0x1400048b8  push    rbp
0x1400048b9  push    rsi
0x1400048ba  push    rdi
0x1400048bb  push    r12
0x1400048bd  push    r13
0x1400048bf  push    r14
0x1400048c1  push    r15
0x1400048c3  sub     rsp, 88h
0x1400048ca  mov     r12, cs:wil_details_featureDescriptors_a
0x1400048d1  lea     r13, aNull_0; "NULL"
0x1400048d8  mov     rdi, [rsp+0C8h+arg_28]
0x1400048e0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400048e4  mov     eax, r8d
0x1400048e7  mov     r8b, dl
0x1400048ea  mov     esi, eax
0x1400048ec  shr     rsi, 10h
0x1400048f0  lea     ebx, [rax-1]
0x1400048f3  mov     r10d, ebx
0x1400048f6  and     ebx, 1Fh
0x1400048f9  shr     r10, 5
0x1400048fd  lea     rax, [rsi+rsi*4]
0x140004901  and     r10d, 7FFh
0x140004908  mov     edx, ebx
0x14000490a  mov     rbx, [rsp+0C8h+arg_38]
0x140004912  lea     r11, [r10+rax*4]
0x140004916  mov     eax, [r12+r11*4+2Ch]
0x14000491b  lea     r10, asc_14000A7D0; "\b"
0x140004922  xor     r11d, r11d
0x140004925  bt      eax, edx
0x140004928  lea     r14d, [r11+8]
0x14000492c  lea     r15d, [r11+5]
0x140004930  jnb     loc_140004A37
0x140004936  lea     r10, [rsi+rsi*4]
0x14000493a  add     r10, r10
0x14000493d  cmp     [r12+r10*8+29h], r8b
0x140004942  jb      loc_140004A30
0x140004948  test    rbx, rbx
0x14000494b  jz      short loc_14000495C
0x14000494d  movzx   edx, word ptr [rbx]
0x140004950  cmp     [rbx], r11w
0x140004954  jz      short loc_14000495F
0x140004956  mov     r11, [rbx+8]
0x14000495a  jmp     short loc_140004962
0x14000495c  mov     rdx, r14
0x14000495f  mov     r11, r13
0x140004962  test    rbx, rbx
0x140004965  lea     rax, asc_14000A7D0; "\b"
0x14000496c  mov     r9, rbx
0x14000496f  cmovz   r9, rax
0x140004973  test    rdi, rdi
0x140004976  jz      short loc_14000498A
0x140004978  mov     rax, rbp
0x14000497b  inc     rax
0x14000497e  cmp     byte ptr [rdi+rax], 0
0x140004982  jnz     short loc_14000497B
0x140004984  lea     r8, [rax+1]
0x140004988  jmp     short loc_14000498D
0x14000498a  mov     r8, r15
0x14000498d  mov     [rsp+0C8h+var_58], 0
0x140004996  lea     rax, aNull; "NULL"
0x14000499d  mov     [rsp+0C8h+var_60], 4
0x1400049a6  lea     rsi, [rsp+0C8h+arg_40]
0x1400049ae  mov     [rsp+0C8h+var_68], rsi
0x1400049b3  test    rdi, rdi
0x1400049b6  mov     [rsp+0C8h+var_70], rdx
0x1400049bb  mov     rcx, rdi
0x1400049be  mov     [rsp+0C8h+var_78], r11
0x1400049c3  lea     rdx, [rsp+0C8h+arg_30]
0x1400049cb  mov     [rsp+0C8h+var_80], 2
0x1400049d4  cmovz   rcx, rax
0x1400049d8  mov     rax, cs:pfnWppTraceMessage
0x1400049df  mov     [rsp+0C8h+var_88], r9
0x1400049e4  movzx   r9d, [rsp+0C8h+arg_18]
0x1400049ed  mov     [rsp+0C8h+var_90], 4
0x1400049f6  mov     [rsp+0C8h+var_98], rdx
0x1400049fb  mov     edx, 2Bh ; '+'
0x140004a00  mov     [rsp+0C8h+var_A0], r8
0x140004a05  mov     r8, [rsp+0C8h+arg_20]
0x140004a0d  mov     [rsp+0C8h+var_A8], rcx
0x140004a12  mov     rcx, [r12+r10*8+18h]
0x140004a17  call    _guard_dispatch_icall
0x140004a1c  movzx   r9d, [rsp+0C8h+arg_18]
0x140004a25  xor     r11d, r11d
0x140004a28  mov     rcx, [rsp+0C8h+arg_0]
0x140004a30  lea     r10, asc_14000A7D0; "\b"
0x140004a37  test    rbx, rbx
0x140004a3a  jz      short loc_140004A4D
0x140004a3c  movzx   r14d, word ptr [rbx]
0x140004a40  cmp     [rbx], r11w
0x140004a44  jz      short loc_140004A4A
0x140004a46  mov     r13, [rbx+8]
0x140004a4a  test    rbx, rbx
0x140004a4d  cmovz   rbx, r10
0x140004a51  test    rdi, rdi
0x140004a54  jz      short loc_140004A66
0x140004a56  inc     rbp
0x140004a59  cmp     [rdi+rbp], r11b
0x140004a5d  jnz     short loc_140004A56
0x140004a5f  lea     r15, [rbp+1]
0x140004a63  test    rdi, rdi
0x140004a66  mov     r8d, [rsp+0C8h+arg_10]
0x140004a6e  lea     rax, aNull; "NULL"
0x140004a75  movzx   edx, [rsp+0C8h+arg_8]
0x140004a7d  cmovz   rdi, rax
0x140004a81  mov     [rsp+0C8h+var_50], r11
0x140004a86  lea     rax, [rsp+0C8h+arg_40]
0x140004a8e  mov     [rsp+0C8h+var_58], 4
0x140004a97  mov     [rsp+0C8h+var_60], rax
0x140004a9c  lea     rax, [rsp+0C8h+arg_30]
0x140004aa4  mov     [rsp+0C8h+var_68], r14
0x140004aa9  mov     [rsp+0C8h+var_70], r13
0x140004aae  mov     [rsp+0C8h+var_78], 2
0x140004ab7  mov     [rsp+0C8h+var_80], rbx
0x140004abc  mov     [rsp+0C8h+var_88], 4
0x140004ac5  mov     [rsp+0C8h+var_90], rax
0x140004aca  mov     [rsp+0C8h+var_98], r15
0x140004acf  mov     [rsp+0C8h+var_A0], rdi
0x140004ad4  mov     word ptr [rsp+0C8h+var_A8], r9w
0x140004ada  mov     r9, [rsp+0C8h+arg_20]
0x140004ae2  call    cs:__imp_WppAutoLogTrace
0x140004ae9  nop     dword ptr [rax+rax+00h]
0x140004aee  add     rsp, 88h
0x140004af5  pop     r15
0x140004af7  pop     r14
0x140004af9  pop     r13
0x140004afb  pop     r12
0x140004afd  pop     rdi
0x140004afe  pop     rsi
0x140004aff  pop     rbp
0x140004b00  pop     rbx
0x140004b01  retn
```
