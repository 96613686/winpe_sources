# ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)

- ea: `0x18000a2e8`
- end: `0x18000a523`
- name: `?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z`
- size: `571`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a200`

## callees

- `0x18000778c`
- `0x18000a2e8`
- `0x18001b3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4f9`

## string_xrefs

- `0x18000a4e2`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall ExpandPaths(
        const unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  const unsigned __int16 *v6; // r11
  const unsigned __int16 *v7; // r8
  __int64 v8; // rsi
  const unsigned __int16 *v9; // rax
  __int64 v10; // r15
  unsigned int v11; // edi
  __int64 v12; // r15
  unsigned __int16 v13; // ax
  char v14; // r12
  unsigned int v15; // r13d
  unsigned int i; // ebp
  const unsigned __int16 *v17; // r10
  __int64 v18; // r14
  __int64 v19; // r11
  unsigned __int16 *v20; // rcx
  int v22; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v23; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v24; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned __int16 v27; // [rsp+98h] [rbp+10h]
  unsigned int v29; // [rsp+A8h] [rbp+20h]

  v29 = a4;
  v6 = a3;
  v7 = a1;
  v8 = 0;
  if ( !a1 || (unsigned int)a2 > 0x7FFFFFFF )
  {
    v11 = -2147024809;
LABEL_32:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA8F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)v11,
      v22);
    SetLastError((unsigned __int16)v11);
    goto LABEL_33;
  }
  a2 = (unsigned int)a2;
  v9 = a1;
  v10 = (unsigned int)a2;
  if ( (_DWORD)a2 )
  {
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --a2;
    }
    while ( a2 );
  }
  v11 = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
    v12 = v10 - a2;
  else
    v12 = 0;
  if ( !a2 )
    goto LABEL_32;
  v13 = a1[v12 - 1];
  v14 = 1;
  v27 = v13;
  v15 = 0;
  for ( i = 0; i < a4; ++i )
  {
    v17 = &v6[i];
    v24 = v17;
    if ( *v17 )
    {
      if ( *v17 != 32 )
      {
        if ( *v17 == 59 )
          goto LABEL_14;
LABEL_28:
        v14 = 0;
        ++v15;
        continue;
      }
      if ( !v14 )
        goto LABEL_28;
    }
    else
    {
      if ( !v14 )
      {
LABEL_14:
        v14 = 1;
        if ( v15 )
        {
          v18 = v12 + v15 + (v13 != 92) + 1LL;
          if ( a5 && v18 + v8 + 1 <= (unsigned __int64)*a6 )
          {
            v23 = (unsigned __int16 *)&v6[i - (unsigned __int64)v15];
            StringCchCopyW(&a5[v8], (unsigned int)(v12 + 1), v7);
            v20 = &a5[v8 + v19];
            if ( v27 != 92 )
              *v20++ = 92;
            StringCchCopyW(v20, v15 + 1, v23);
            a4 = v29;
            v7 = a1;
            v6 = a3;
          }
          v8 += v18;
          v15 = 0;
          v13 = v27;
          if ( !*v24 )
            i = a4;
        }
        continue;
      }
      i = a4;
    }
  }
  if ( a5 && *a6 >= (unsigned __int64)(v8 + 1) )
    a5[v8] = 0;
  LODWORD(v8) = v8 + 1;
LABEL_33:
  *a6 = v8;
  return v11;
}

```

## disassembly

```asm
0x18000a2e8  mov     [rsp+arg_18], r9d
0x18000a2ed  mov     [rsp+arg_10], r8
0x18000a2f2  mov     [rsp+arg_0], rcx
0x18000a2f7  push    rbx
0x18000a2f8  push    rbp
0x18000a2f9  push    rsi
0x18000a2fa  push    rdi
0x18000a2fb  push    r12
0x18000a2fd  push    r13
0x18000a2ff  push    r14
0x18000a301  push    r15
0x18000a303  sub     rsp, 48h
0x18000a307  xor     ebx, ebx
0x18000a309  mov     r11, r8
0x18000a30c  mov     r8, rcx; unsigned __int16 *
0x18000a30f  mov     esi, ebx
0x18000a311  test    rcx, rcx
0x18000a314  jz      loc_18000A4D5
0x18000a31a  cmp     edx, 7FFFFFFFh
0x18000a320  ja      loc_18000A4D5
0x18000a326  mov     edx, edx
0x18000a328  mov     rax, rcx
0x18000a32b  mov     r15d, edx
0x18000a32e  test    rdx, rdx
0x18000a331  jz      short loc_18000A342
0x18000a333  cmp     [rax], bx
0x18000a336  jz      short loc_18000A342
0x18000a338  add     rax, 2
0x18000a33c  sub     rdx, 1
0x18000a340  jnz     short loc_18000A333
0x18000a342  mov     rax, rdx
0x18000a345  neg     rax
0x18000a348  sbb     edi, edi
0x18000a34a  not     edi
0x18000a34c  and     edi, 80070057h
0x18000a352  test    rdx, rdx
0x18000a355  jz      short loc_18000A35C
0x18000a357  sub     r15, rdx
0x18000a35a  jmp     short loc_18000A35F
0x18000a35c  mov     r15, rbx
0x18000a35f  test    rdx, rdx
0x18000a362  jz      loc_18000A4DA
0x18000a368  movzx   eax, word ptr [rcx+r15*2-2]
0x18000a36e  mov     r12b, 1
0x18000a371  mov     [rsp+88h+arg_8], ax
0x18000a379  mov     r13d, ebx
0x18000a37c  mov     ebp, ebx
0x18000a37e  test    r9d, r9d
0x18000a381  jz      loc_18000A491
0x18000a387  mov     [rsp+88h+var_68], edi
0x18000a38b  mov     ecx, 5Ch ; '\'
0x18000a390  mov     rdi, [rsp+88h+arg_20]
0x18000a398  mov     edx, ebp
0x18000a39a  lea     r10, [r11+rdx*2]
0x18000a39e  mov     [rsp+88h+var_58], r10
0x18000a3a3  cmp     [r10], bx
0x18000a3a7  jz      loc_18000A4C7
0x18000a3ad  cmp     word ptr [r10], 20h ; ' '
0x18000a3b2  jz      loc_18000A4BA
0x18000a3b8  cmp     word ptr [r10], 3Bh ; ';'
0x18000a3bd  jnz     loc_18000A4BF
0x18000a3c3  mov     r12b, 1
0x18000a3c6  test    r13d, r13d
0x18000a3c9  jz      loc_18000A482
0x18000a3cf  cmp     cx, ax
0x18000a3d2  mov     r10d, r13d
0x18000a3d5  mov     r14, rbx
0x18000a3d8  setnz   r14b
0x18000a3dc  inc     r14
0x18000a3df  add     r14, r10
0x18000a3e2  add     r14, r15
0x18000a3e5  test    rdi, rdi
0x18000a3e8  jz      short loc_18000A461
0x18000a3ea  mov     rax, [rsp+88h+arg_28]
0x18000a3f2  lea     rcx, [rsi+1]
0x18000a3f6  add     rcx, r14
0x18000a3f9  mov     eax, [rax]
0x18000a3fb  cmp     rcx, rax
0x18000a3fe  ja      short loc_18000A461
0x18000a400  sub     rdx, r10
0x18000a403  lea     rbx, [rdi+rsi*2]
0x18000a407  mov     rcx, rbx; unsigned __int16 *
0x18000a40a  lea     rax, [r11+rdx*2]
0x18000a40e  mov     r11d, r15d
0x18000a411  mov     [rsp+88h+var_60], rax
0x18000a416  lea     edx, [r11+1]; unsigned __int64
0x18000a41a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a41f  mov     eax, 5Ch ; '\'
0x18000a424  lea     rcx, [rbx+r11*2]
0x18000a428  cmp     ax, [rsp+88h+arg_8]
0x18000a430  jz      short loc_18000A439
0x18000a432  mov     [rcx], ax
0x18000a435  add     rcx, 2; unsigned __int16 *
0x18000a439  mov     r8, [rsp+88h+var_60]; unsigned __int16 *
0x18000a43e  lea     edx, [r13+1]; unsigned __int64
0x18000a442  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a447  mov     r9d, [rsp+88h+arg_18]
0x18000a44f  xor     ebx, ebx
0x18000a451  mov     r8, [rsp+88h+arg_0]
0x18000a459  mov     r11, [rsp+88h+arg_10]
0x18000a461  mov     rax, [rsp+88h+var_58]
0x18000a466  xor     ecx, ecx
0x18000a468  add     rsi, r14
0x18000a46b  mov     r13d, ebx
0x18000a46e  cmp     cx, [rax]
0x18000a471  mov     ecx, 5Ch ; '\'
0x18000a476  movzx   eax, [rsp+88h+arg_8]
0x18000a47e  cmovz   ebp, r9d
0x18000a482  inc     ebp
0x18000a484  cmp     ebp, r9d
0x18000a487  jb      loc_18000A398
0x18000a48d  mov     edi, [rsp+88h+var_68]
0x18000a491  mov     rdx, [rsp+88h+arg_20]
0x18000a499  test    rdx, rdx
0x18000a49c  jz      short loc_18000A4B5
0x18000a49e  mov     rax, [rsp+88h+arg_28]
0x18000a4a6  lea     rcx, [rsi+1]
0x18000a4aa  mov     eax, [rax]
0x18000a4ac  cmp     rax, rcx
0x18000a4af  jb      short loc_18000A4B5
0x18000a4b1  mov     [rdx+rsi*2], bx
0x18000a4b5  inc     rsi
0x18000a4b8  jmp     short loc_18000A505
0x18000a4ba  test    r12b, r12b
0x18000a4bd  jnz     short loc_18000A482
0x18000a4bf  mov     r12b, bl
0x18000a4c2  inc     r13d
0x18000a4c5  jmp     short loc_18000A482
0x18000a4c7  test    r12b, r12b
0x18000a4ca  jz      loc_18000A3C3
0x18000a4d0  mov     ebp, r9d
0x18000a4d3  jmp     short loc_18000A482
0x18000a4d5  mov     edi, 80070057h
0x18000a4da  mov     rcx, [rsp+88h]; this
0x18000a4e2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a4e9  mov     r9d, edi; char *
0x18000a4ec  mov     edx, 0A8Fh; void *
0x18000a4f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a4f6  movzx   ecx, di; dwErrCode
0x18000a4f9  call    cs:__imp_SetLastError
0x18000a500  nop     dword ptr [rax+rax+00h]
0x18000a505  mov     rax, [rsp+88h+arg_28]
0x18000a50d  mov     [rax], esi
0x18000a50f  mov     eax, edi
0x18000a511  add     rsp, 48h
0x18000a515  pop     r15
0x18000a517  pop     r14
0x18000a519  pop     r13
0x18000a51b  pop     r12
0x18000a51d  pop     rdi
0x18000a51e  pop     rsi
0x18000a51f  pop     rbp
0x18000a520  pop     rbx
0x18000a521  retn
```
