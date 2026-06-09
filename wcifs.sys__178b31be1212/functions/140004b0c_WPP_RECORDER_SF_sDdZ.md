# WPP_RECORDER_SF_sDdZ

- ea: `0x140004b0c`
- end: `0x140004d75`
- name: `WPP_RECORDER_SF_sDdZ`
- size: `617`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, unsigned int, unsigned __int16, __int64, const char *, char, char, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140018e28`
- `0x14001c688`
- `0x140020988`
- `0x140025270`
- `0x140026260`
- `0x140026cec`
- `0x1400278a4`
- `0x140027f74`
- `0x14002ef90`
- `0x1400338b0`

## callees

- `0x140004b0c`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004d54`
- `WppRecorder!WppAutoLogTrace` at `0x140004d54`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDdZ(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        char a7,
        char a8,
        unsigned __int16 *a9)
{
  const char *v9; // rdi
  __int16 v10; // ax
  __int64 v11; // rbp
  unsigned __int64 v12; // rsi
  unsigned __int64 v14; // rsi
  __int64 v15; // r15
  unsigned int v16; // edx
  int v17; // eax
  __int64 v18; // rdx
  const wchar_t *v19; // r11
  const wchar_t *v20; // r9
  __int64 v21; // rax
  __int64 v22; // r8
  const char *v23; // rcx
  bool v24; // zf
  int v26; // [rsp+20h] [rbp-A8h]
  __int64 v27; // [rsp+D0h] [rbp+8h]
  unsigned __int16 v30; // [rsp+E8h] [rbp+20h]

  v30 = a4;
  v27 = a1;
  v9 = a6;
  v10 = a3;
  v11 = -1;
  v12 = a3;
  v14 = v12 >> 16;
  v15 = 5;
  v16 = ((_BYTE)v10 - 1) & 0x1F;
  v17 = *((_DWORD *)&wil_details_featureDescriptors_a->Timer + 20 * v14 + ((unsigned __int16)(v10 - 1) >> 5) + 1);
  if ( !_bittest(&v17, v16) || *((_BYTE *)&wil_details_featureDescriptors_a->Timer + 80 * v14 + 1) < a2 )
    goto LABEL_18;
  if ( !a9 )
  {
    v18 = 8;
    goto LABEL_7;
  }
  v18 = *a9;
  if ( !*a9 )
  {
LABEL_7:
    v19 = L"NULL";
    goto LABEL_8;
  }
  v19 = (const wchar_t *)*((_QWORD *)a9 + 1);
LABEL_8:
  v20 = a9;
  if ( !a9 )
    v20 = L"\b";
  if ( a6 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a6[v21] );
    v22 = v21 + 1;
  }
  else
  {
    v22 = 5;
  }
  v23 = a6;
  if ( !a6 )
    v23 = "NULL";
  ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, const char *, __int64, char *, __int64, char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
    *((_QWORD *)&wil_details_featureDescriptors_a->AttachedDevice + 10 * v14),
    43,
    a5,
    v30,
    v23,
    v22,
    &a7,
    4,
    &a8,
    4,
    v20,
    2,
    v19,
    v18,
    0);
  a4 = v30;
  a1 = v27;
LABEL_18:
  v24 = a6 == 0;
  if ( a6 )
  {
    do
      ++v11;
    while ( a6[v11] );
    v15 = v11 + 1;
    v24 = a6 == 0;
  }
  if ( v24 )
    v9 = "NULL";
  LOWORD(v26) = a4;
  return WppAutoLogTrace(a1, a2, a3, a5, v26, v9, v15, &a7, 4, &a8);
}

```

## disassembly

```asm
0x140004b0c  mov     rax, rsp
0x140004b0f  mov     [rax+20h], r9w
0x140004b14  mov     [rax+18h], r8d
0x140004b18  mov     [rax+10h], dl
0x140004b1b  mov     [rax+8], rcx
0x140004b1f  push    rbx
0x140004b20  push    rbp
0x140004b21  push    rsi
0x140004b22  push    rdi
0x140004b23  push    r12
0x140004b25  push    r13
0x140004b27  push    r14
0x140004b29  push    r15
0x140004b2b  sub     rsp, 88h
0x140004b32  mov     r12, cs:wil_details_featureDescriptors_a
0x140004b39  lea     r13, aNull_0; "NULL"
0x140004b40  mov     rdi, [rsp+0C8h+arg_28]
0x140004b48  mov     r14d, 8
0x140004b4e  mov     eax, r8d
0x140004b51  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140004b55  mov     esi, eax
0x140004b57  mov     r8b, dl
0x140004b5a  shr     rsi, 10h
0x140004b5e  lea     r15d, [r14-3]
0x140004b62  lea     ebx, [rax-1]
0x140004b65  mov     r10d, ebx
0x140004b68  and     ebx, 1Fh
0x140004b6b  shr     r10, 5
0x140004b6f  lea     rax, [rsi+rsi*4]
0x140004b73  and     r10d, 7FFh
0x140004b7a  mov     edx, ebx
0x140004b7c  mov     rbx, [rsp+0C8h+arg_40]
0x140004b84  lea     r11, [r10+rax*4]
0x140004b88  mov     eax, [r12+r11*4+2Ch]
0x140004b8d  lea     r10, asc_14000A7D0; "\b"
0x140004b94  bt      eax, edx
0x140004b97  lea     r11, aNull; "NULL"
0x140004b9e  jnb     loc_140004CAF
0x140004ba4  lea     r10, [rsi+rsi*4]
0x140004ba8  xor     esi, esi
0x140004baa  add     r10, r10
0x140004bad  cmp     [r12+r10*8+29h], r8b
0x140004bb2  jb      loc_140004CA6
0x140004bb8  test    rbx, rbx
0x140004bbb  jz      short loc_140004BCB
0x140004bbd  movzx   edx, word ptr [rbx]
0x140004bc0  cmp     [rbx], si
0x140004bc3  jz      short loc_140004BCE
0x140004bc5  mov     r11, [rbx+8]
0x140004bc9  jmp     short loc_140004BD1
0x140004bcb  mov     rdx, r14
0x140004bce  mov     r11, r13
0x140004bd1  test    rbx, rbx
0x140004bd4  lea     rax, asc_14000A7D0; "\b"
0x140004bdb  mov     r9, rbx
0x140004bde  cmovz   r9, rax
0x140004be2  test    rdi, rdi
0x140004be5  jz      short loc_140004BF9
0x140004be7  mov     rax, rbp
0x140004bea  inc     rax
0x140004bed  cmp     [rdi+rax], sil
0x140004bf1  jnz     short loc_140004BEA
0x140004bf3  lea     r8, [rax+1]
0x140004bf7  jmp     short loc_140004BFC
0x140004bf9  mov     r8, r15
0x140004bfc  mov     [rsp+0C8h+var_58], rsi
0x140004c01  lea     rax, aNull; "NULL"
0x140004c08  mov     [rsp+0C8h+var_60], rdx
0x140004c0d  test    rdi, rdi
0x140004c10  mov     [rsp+0C8h+var_68], r11
0x140004c15  lea     rdx, [rsp+0C8h+arg_38]
0x140004c1d  mov     [rsp+0C8h+var_70], 2
0x140004c26  mov     rcx, rdi
0x140004c29  mov     [rsp+0C8h+var_78], r9
0x140004c2e  cmovz   rcx, rax
0x140004c32  mov     rax, cs:pfnWppTraceMessage
0x140004c39  mov     r9d, 4
0x140004c3f  mov     [rsp+0C8h+var_80], r9
0x140004c44  mov     [rsp+0C8h+var_88], rdx
0x140004c49  lea     rdx, [rsp+0C8h+arg_30]
0x140004c51  mov     [rsp+0C8h+var_90], r9
0x140004c56  movzx   r9d, [rsp+0C8h+arg_18]
0x140004c5f  mov     [rsp+0C8h+var_98], rdx
0x140004c64  mov     edx, 2Bh ; '+'
0x140004c69  mov     [rsp+0C8h+var_A0], r8
0x140004c6e  mov     r8, [rsp+0C8h+arg_20]
0x140004c76  mov     [rsp+0C8h+var_A8], rcx
0x140004c7b  mov     rcx, [r12+r10*8+18h]
0x140004c80  call    _guard_dispatch_icall
0x140004c85  movzx   r9d, [rsp+0C8h+arg_18]
0x140004c8e  lea     r10, asc_14000A7D0; "\b"
0x140004c95  mov     rcx, [rsp+0C8h+arg_0]
0x140004c9d  lea     r11, aNull; "NULL"
0x140004ca4  jmp     short loc_140004CB1
0x140004ca6  lea     r10, asc_14000A7D0; "\b"
0x140004cad  jmp     short loc_140004CB1
0x140004caf  xor     esi, esi
0x140004cb1  test    rbx, rbx
0x140004cb4  jz      short loc_140004CC6
0x140004cb6  movzx   r14d, word ptr [rbx]
0x140004cba  cmp     [rbx], si
0x140004cbd  jz      short loc_140004CC3
0x140004cbf  mov     r13, [rbx+8]
0x140004cc3  test    rbx, rbx
0x140004cc6  cmovz   rbx, r10
0x140004cca  test    rdi, rdi
0x140004ccd  jz      short loc_140004CDF
0x140004ccf  inc     rbp
0x140004cd2  cmp     [rdi+rbp], sil
0x140004cd6  jnz     short loc_140004CCF
0x140004cd8  lea     r15, [rbp+1]
0x140004cdc  test    rdi, rdi
0x140004cdf  mov     r8d, [rsp+0C8h+arg_10]
0x140004ce7  lea     rax, [rsp+0C8h+arg_38]
0x140004cef  movzx   edx, [rsp+0C8h+arg_8]
0x140004cf7  cmovz   rdi, r11
0x140004cfb  mov     [rsp+0C8h+var_50], rsi
0x140004d00  mov     [rsp+0C8h+var_58], r14
0x140004d05  mov     [rsp+0C8h+var_60], r13
0x140004d0a  mov     [rsp+0C8h+var_68], 2
0x140004d13  mov     [rsp+0C8h+var_70], rbx
0x140004d18  mov     [rsp+0C8h+var_78], 4
0x140004d21  mov     [rsp+0C8h+var_80], rax
0x140004d26  lea     rax, [rsp+0C8h+arg_30]
0x140004d2e  mov     [rsp+0C8h+var_88], 4
0x140004d37  mov     [rsp+0C8h+var_90], rax
0x140004d3c  mov     [rsp+0C8h+var_98], r15
0x140004d41  mov     [rsp+0C8h+var_A0], rdi
0x140004d46  mov     word ptr [rsp+0C8h+var_A8], r9w
0x140004d4c  mov     r9, [rsp+0C8h+arg_20]
0x140004d54  call    cs:__imp_WppAutoLogTrace
0x140004d5b  nop     dword ptr [rax+rax+00h]
0x140004d60  add     rsp, 88h
0x140004d67  pop     r15
0x140004d69  pop     r14
0x140004d6b  pop     r13
0x140004d6d  pop     r12
0x140004d6f  pop     rdi
0x140004d70  pop     rsi
0x140004d71  pop     rbp
0x140004d72  pop     rbx
0x140004d73  retn
```
