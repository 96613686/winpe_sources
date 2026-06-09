# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18002e174`
- end: `0x18002e61b`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `1191`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e07c`

## callees

- `0x18002e174`
- `0x18002e624`
- `0x18002e7dc`
- `0x18002ee64`
- `0x180039740`
- `0x18003d958`
- `0x1800485a4`
- `0x180076722`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002e35b`
- `msvcrt!memmove_s` at `0x18002e35b`
- `msvcrt!memcpy_s` at `0x18002e3c6`
- `msvcrt!memcpy_s` at `0x18002e497`
- `msvcrt!memcpy_s` at `0x18002e53c`
- `msvcrt!memcpy_s` at `0x18002e3c6`
- `msvcrt!memcpy_s` at `0x18002e497`
- `msvcrt!memcpy_s` at `0x18002e53c`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  __int64 v6; // rsi
  unsigned __int16 v8; // r12
  unsigned __int8 *v9; // rsi
  char v10; // r14
  unsigned __int8 *v11; // rcx
  unsigned __int64 v12; // rdx
  size_t v13; // r13
  unsigned __int8 *v14; // rbx
  unsigned __int16 v15; // ax
  unsigned __int8 *v16; // r15
  int v17; // ecx
  unsigned __int64 v18; // rdx
  void *v19; // r12
  unsigned __int8 *v20; // rbx
  unsigned __int8 *v21; // rax
  char v22; // r14
  __int64 v23; // rcx
  unsigned int v24; // r8d
  char v25; // dl
  __int64 v26; // rax
  unsigned __int64 v27; // rdx
  __int64 v28; // rbx
  unsigned __int64 v29; // r9
  unsigned __int8 *v31; // r8
  int v32; // ebx
  char *v33; // rdi
  char v34; // al
  unsigned __int8 *v35; // rax
  unsigned int v36; // r14d
  unsigned __int8 *v37; // r8
  unsigned __int16 Destination; // [rsp+38h] [rbp-79h] BYREF
  unsigned __int16 v39; // [rsp+40h] [rbp-71h] BYREF
  char v40; // [rsp+42h] [rbp-6Fh]
  unsigned int v41; // [rsp+44h] [rbp-6Dh] BYREF
  unsigned __int16 v42; // [rsp+48h] [rbp-69h] BYREF
  __int128 v43; // [rsp+50h] [rbp-61h]
  unsigned __int8 *v44; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 v45; // [rsp+68h] [rbp-49h]
  __int16 v46; // [rsp+70h] [rbp-41h] BYREF
  char v47; // [rsp+72h] [rbp-3Fh]
  int v48; // [rsp+74h] [rbp-3Dh]
  unsigned __int16 v49; // [rsp+78h] [rbp-39h]
  void *Buf2[2]; // [rsp+80h] [rbp-31h]
  unsigned __int8 *v51; // [rsp+90h] [rbp-21h]
  __int16 v52; // [rsp+98h] [rbp-19h] BYREF
  char v53; // [rsp+9Ah] [rbp-17h]
  unsigned int v54; // [rsp+9Ch] [rbp-15h]
  __int16 v55; // [rsp+A0h] [rbp-11h]
  __int64 v56; // [rsp+A8h] [rbp-9h]
  void *v57; // [rsp+B0h] [rbp-1h]
  unsigned __int8 *v58; // [rsp+108h] [rbp+57h] BYREF
  void *Buf1; // [rsp+110h] [rbp+5Fh]
  size_t Size; // [rsp+118h] [rbp+67h]
  void *v61; // [rsp+120h] [rbp+6Fh]

  v61 = a4;
  Size = a3;
  Buf1 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v8 = *((_WORD *)this + 1);
  v9 = (unsigned __int8 *)(v6 + 10);
  v10 = *((_BYTE *)this + 4);
  v39 = v8;
  v11 = v9;
  v40 = v10;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  LOBYTE(v58) = 0;
  while ( 1 )
  {
    v12 = *((_QWORD *)this + 4);
    v13 = a5;
    v45 = v12;
    v51 = v9;
    v44 = v9;
    if ( v10 == 1 )
    {
      v14 = v11 + 2;
      if ( (unsigned __int64)(v11 + 2) > v12 )
        break;
      Destination = 0;
      *(_QWORD *)&v43 = v11;
      memcpy_s(&Destination, 2u, v11, 2u);
      v41 = Destination;
      goto LABEL_32;
    }
    if ( v10 != 2 )
    {
      v14 = v11;
      goto LABEL_6;
    }
    v14 = v11 + 4;
    if ( (unsigned __int64)(v11 + 4) > v12 )
      break;
    *(_QWORD *)&v43 = v11;
    memcpy_s(&v41, 4u, v11, 4u);
LABEL_32:
    v10 = v40;
    v8 = v39;
    v12 = v45;
LABEL_6:
    v15 = v8;
    v42 = v8;
    if ( !v8 )
    {
      if ( (unsigned __int64)(v14 + 2) > v12 )
        break;
      memcpy_s(&v42, 2u, v14, 2u);
      v15 = v42;
      v10 = v40;
      v14 += 2;
      v8 = v39;
    }
    v16 = &v14[v15];
    if ( (unsigned __int64)v16 > v45 )
      break;
    *((_QWORD *)&v43 + 1) = v14;
    if ( Size == v15 )
      v17 = memcmp_0(Buf1, v14, Size);
    else
      v17 = Size - v15;
    if ( v17 < 0 )
    {
      v9 = v51;
      v44 = v51;
      goto LABEL_36;
    }
    if ( !v17 )
    {
      v46 = *((_WORD *)this + 3);
      v47 = *((_BYTE *)this + 8);
      v48 = 0;
      v49 = 0;
      *(_OWORD *)Buf2 = 0;
      if ( *((_QWORD *)this + 2) )
      {
        v18 = (*((_QWORD *)this + 4) - (_QWORD)v16) / *((_QWORD *)this + 2);
        if ( v41 > v18 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v18);
        v19 = v61;
        v20 = &v16[*((_QWORD *)this + 2) * v41];
        v21 = wil::details_abi::RawUsageIndex::LowerBound(this, v16, v41, v61, v13);
        v9 = v21;
        if ( v21 >= v20 )
        {
LABEL_16:
          v44 = v9;
          if ( v9 )
          {
            v22 = 1;
            v23 = 0;
            goto LABEL_18;
          }
          return 1;
        }
        v31 = (unsigned __int8 *)*((_QWORD *)this + 4);
        v58 = v21;
        wil::details_abi::UsageIndexProperty::Read((wil::details_abi::UsageIndexProperty *)&v46, &v58, v31);
        if ( v13 == v49 )
          v32 = memcmp_0(v19, Buf2[1], v13);
        else
          v32 = v13 - v49;
      }
      else
      {
        v19 = v61;
        v32 = -1;
        v36 = 0;
        v9 = v16;
        while ( v36 < v41 )
        {
          v37 = (unsigned __int8 *)*((_QWORD *)this + 4);
          v58 = v9;
          if ( !wil::details_abi::UsageIndexProperty::Read((wil::details_abi::UsageIndexProperty *)&v46, &v58, v37) )
          {
            wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v36);
            break;
          }
          v32 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v46, v19, v13);
          if ( v32 <= 0 )
            break;
          v9 = v58;
          ++v36;
        }
      }
      if ( v32 )
        goto LABEL_16;
      if ( v47 )
      {
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v46, a6 + v48);
        v33 = (char *)this + 56;
      }
      else
      {
        v33 = (char *)this + 56;
        v34 = 0;
        if ( !*v33 )
        {
LABEL_53:
          *v33 = v34;
          return 1;
        }
      }
      v34 = 1;
      goto LABEL_53;
    }
    v35 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v39, v16);
    v10 = v40;
    v9 = v35;
    v8 = v39;
    v11 = v35;
  }
  v23 = 0;
  *((_QWORD *)this + 4) = v9;
  if ( !(_BYTE)v58 )
  {
LABEL_36:
    v42 = Size;
    *((_QWORD *)&v43 + 1) = Buf1;
    v41 = 1;
    *(_QWORD *)&v43 = 0;
    if ( v8 )
      v23 = v8;
    else
      v23 = (unsigned __int16)Size + 2LL;
    if ( v10 == 1 )
    {
      v23 += 2;
    }
    else if ( v10 == 2 )
    {
      v23 += 4;
    }
  }
  v22 = (char)v58;
  v19 = v61;
LABEL_18:
  v24 = *((unsigned __int16 *)this + 3);
  v25 = *((_BYTE *)this + 8);
  v52 = v24;
  v53 = v25;
  v54 = a6;
  v55 = v13;
  v56 = 0;
  v57 = v19;
  if ( (_WORD)v24 )
    v26 = v24;
  else
    v26 = (unsigned __int16)v13 + 2LL;
  if ( v25 == 1 )
  {
    v26 += 2;
  }
  else if ( v25 == 2 )
  {
    v26 += 4;
  }
  v27 = *((_QWORD *)this + 5);
  v28 = v26 + v23;
  v29 = *((_QWORD *)this + 4);
  if ( ((v27 - v29) & -(__int64)(v29 < v27)) >= v26 + v23 )
  {
    memmove_s(&v9[v28], v27 - v28 - (_QWORD)v9, v9, v29 - (_QWORD)v9);
    *((_QWORD *)this + 4) += v28;
    if ( v22 )
    {
      if ( v40 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v41 + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v39,
        &v44,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v52,
      &v44,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e174  mov     rax, rsp
0x18002e177  mov     [rax+20h], r9
0x18002e17b  mov     [rax+18h], r8
0x18002e17f  mov     [rax+10h], rdx
0x18002e183  push    rbp
0x18002e184  push    rbx
0x18002e185  push    rsi
0x18002e186  push    rdi
0x18002e187  push    r12
0x18002e189  push    r13
0x18002e18b  push    r14
0x18002e18d  push    r15
0x18002e18f  lea     rbp, [rax-4Fh]
0x18002e193  sub     rsp, 0B8h
0x18002e19a  mov     rsi, [rcx+18h]
0x18002e19e  xor     r9d, r9d
0x18002e1a1  mov     rdi, rcx
0x18002e1a4  test    rsi, rsi
0x18002e1a7  jz      loc_18002E3A0
0x18002e1ad  movzx   r12d, word ptr [rcx+2]
0x18002e1b2  add     rsi, 0Ah
0x18002e1b6  mov     r14b, [rcx+4]
0x18002e1ba  xorps   xmm0, xmm0
0x18002e1bd  mov     [rbp+47h+var_B8], r12w
0x18002e1c2  mov     rcx, rsi
0x18002e1c5  mov     [rbp+47h+var_B6], r14b
0x18002e1c9  movdqu  [rbp+47h+var_A8], xmm0
0x18002e1ce  mov     dword ptr [rbp+47h+var_B4], r9d
0x18002e1d2  mov     word ptr [rbp+47h+var_B4+4], r9w
0x18002e1d7  mov     byte ptr [rbp+47h+arg_0], r9b
0x18002e1db  mov     rdx, [rdi+20h]
0x18002e1df  mov     r13, [rbp+47h+arg_20]
0x18002e1e3  mov     [rbp+47h+var_90], rdx
0x18002e1e7  mov     [rbp+47h+var_68], rsi
0x18002e1eb  mov     [rbp+47h+var_98], rsi
0x18002e1ef  cmp     r14b, 1
0x18002e1f3  jz      loc_18002E3A4
0x18002e1f9  cmp     r14b, 2
0x18002e1fd  jz      loc_18002E51B
0x18002e203  mov     rbx, rcx
0x18002e206  movzx   eax, r12w
0x18002e20a  mov     word ptr [rbp+47h+var_B4+4], ax
0x18002e20e  test    r12w, r12w
0x18002e212  jz      loc_18002E47E
0x18002e218  movzx   edx, ax
0x18002e21b  lea     r15, [rdx+rbx]
0x18002e21f  cmp     r15, [rbp+47h+var_90]
0x18002e223  ja      loc_18002E407
0x18002e229  mov     rcx, [rbp+47h+Size]
0x18002e22d  mov     qword ptr [rbp+47h+var_A8+8], rbx
0x18002e231  cmp     rcx, rdx
0x18002e234  jnz     loc_18002E474
0x18002e23a  mov     r8, rcx; Size
0x18002e23d  mov     rdx, rbx; Buf2
0x18002e240  mov     rcx, [rbp+47h+Buf1]; Buf1
0x18002e244  call    memcmp_0
0x18002e249  mov     ecx, eax
0x18002e24b  xor     r9d, r9d
0x18002e24e  test    ecx, ecx
0x18002e250  js      loc_18002E5FB
0x18002e256  jnz     loc_18002E547
0x18002e25c  xorps   xmm0, xmm0
0x18002e25f  movzx   eax, word ptr [rdi+6]
0x18002e263  mov     [rbp+47h+var_88], ax
0x18002e267  mov     al, [rdi+8]
0x18002e26a  mov     [rbp+47h+var_86], al
0x18002e26d  mov     [rbp+47h+var_84], r9d
0x18002e271  mov     [rbp+47h+var_80], r9w
0x18002e276  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18002e27b  cmp     [rdi+10h], r9
0x18002e27f  jbe     loc_18002E57B
0x18002e285  mov     rax, [rdi+20h]
0x18002e289  xor     edx, edx
0x18002e28b  sub     rax, r15
0x18002e28e  div     qword ptr [rdi+10h]
0x18002e292  mov     rdx, rax; unsigned int
0x18002e295  mov     eax, dword ptr [rbp+47h+var_B4]
0x18002e298  cmp     rax, rdx
0x18002e29b  ja      loc_18002E56D
0x18002e2a1  mov     r8d, dword ptr [rbp+47h+var_B4]; unsigned __int64
0x18002e2a5  mov     rdx, r15; unsigned __int8 *
0x18002e2a8  mov     r12, [rbp+47h+arg_18]
0x18002e2ac  mov     ebx, r8d
0x18002e2af  imul    rbx, [rdi+10h]
0x18002e2b4  mov     r9, r12; void *
0x18002e2b7  mov     [rsp+20h], r13; Size
0x18002e2bc  mov     rcx, rdi; this
0x18002e2bf  add     rbx, r15
0x18002e2c2  call    ?LowerBound@RawUsageIndex@details_abi@wil@@AEAAPEAEPEAE_KPEAX1@Z; wil::details_abi::RawUsageIndex::LowerBound(uchar *,unsigned __int64,void *,unsigned __int64)
0x18002e2c7  mov     rsi, rax
0x18002e2ca  cmp     rax, rbx
0x18002e2cd  jb      loc_18002E4B5
0x18002e2d3  xor     r9d, r9d
0x18002e2d6  mov     [rbp+47h+var_98], rsi
0x18002e2da  test    rsi, rsi
0x18002e2dd  jz      loc_18002E38A
0x18002e2e3  mov     r14b, 1
0x18002e2e6  mov     rcx, r9
0x18002e2e9  movzx   r8d, word ptr [rdi+6]
0x18002e2ee  mov     dl, [rdi+8]
0x18002e2f1  mov     eax, [rbp+47h+arg_28]
0x18002e2f4  mov     [rbp+47h+var_60], r8w
0x18002e2f9  mov     [rbp+47h+var_5E], dl
0x18002e2fc  mov     [rbp+47h+var_5C], eax
0x18002e2ff  mov     [rbp+47h+var_58], r13w
0x18002e304  mov     [rbp+47h+var_50], r9
0x18002e308  mov     [rbp+47h+var_48], r12
0x18002e30c  test    r8w, r8w
0x18002e310  jz      loc_18002E45D
0x18002e316  mov     eax, r8d
0x18002e319  cmp     dl, 1
0x18002e31c  jz      loc_18002E3FE
0x18002e322  cmp     dl, 2
0x18002e325  jnz     short loc_18002E32B
0x18002e327  add     rax, 4
0x18002e32b  mov     rdx, [rdi+28h]
0x18002e32f  lea     rbx, [rax+rcx]
0x18002e333  mov     r9, [rdi+20h]
0x18002e337  mov     rcx, rdx
0x18002e33a  sub     rcx, r9
0x18002e33d  cmp     r9, rdx
0x18002e340  sbb     rax, rax
0x18002e343  and     rax, rcx
0x18002e346  cmp     rax, rbx
0x18002e349  jb      short loc_18002E3A0
0x18002e34b  sub     rdx, rbx
0x18002e34e  lea     rcx, [rbx+rsi]; Destination
0x18002e352  sub     rdx, rsi; DestinationSize
0x18002e355  sub     r9, rsi; SourceSize
0x18002e358  mov     r8, rsi; Source
0x18002e35b  call    cs:__imp_memmove_s
0x18002e361  add     [rdi+20h], rbx
0x18002e365  xor     ecx, ecx
0x18002e367  test    r14b, r14b
0x18002e36a  jz      short loc_18002E3E8
0x18002e36c  cmp     [rbp+47h+var_B6], cl
0x18002e36f  jnz     loc_18002E608
0x18002e375  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002e379  lea     rdx, [rbp+47h+var_98]; unsigned __int8 **
0x18002e37d  lea     rcx, [rbp+47h+var_60]; this
0x18002e381  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002e386  mov     byte ptr [rdi+38h], 1
0x18002e38a  mov     al, 1
0x18002e38c  add     rsp, 0B8h
0x18002e393  pop     r15
0x18002e395  pop     r14
0x18002e397  pop     r13
0x18002e399  pop     r12
0x18002e39b  pop     rdi
0x18002e39c  pop     rsi
0x18002e39d  pop     rbx
0x18002e39e  pop     rbp
0x18002e39f  retn
0x18002e3a0  xor     al, al
0x18002e3a2  jmp     short loc_18002E38C
0x18002e3a4  lea     rbx, [rcx+2]
0x18002e3a8  cmp     rbx, rdx
0x18002e3ab  ja      short loc_18002E407
0x18002e3ad  mov     [rbp+47h+Destination], r9w
0x18002e3b2  mov     r8, rcx; Source
0x18002e3b5  mov     r9d, 2; SourceSize
0x18002e3bb  mov     qword ptr [rbp+47h+var_A8], rcx
0x18002e3bf  mov     edx, r9d; DestinationSize
0x18002e3c2  lea     rcx, [rbp+47h+Destination]; Destination
0x18002e3c6  call    cs:__imp_memcpy_s
0x18002e3cc  movzx   eax, [rbp+47h+Destination]
0x18002e3d0  mov     dword ptr [rbp+47h+var_B4], eax
0x18002e3d3  mov     r14b, [rbp+47h+var_B6]
0x18002e3d7  xor     r9d, r9d
0x18002e3da  movzx   r12d, [rbp+47h+var_B8]
0x18002e3df  mov     rdx, [rbp+47h+var_90]
0x18002e3e3  jmp     loc_18002E206
0x18002e3e8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002e3ec  lea     rdx, [rbp+47h+var_98]; unsigned __int8 **
0x18002e3f0  lea     rcx, [rbp+47h+var_B8]; this
0x18002e3f4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002e3f9  jmp     loc_18002E375
0x18002e3fe  add     rax, 2
0x18002e402  jmp     loc_18002E32B
0x18002e407  mov     rcx, r9
0x18002e40a  mov     [rdi+20h], rsi
0x18002e40e  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18002e412  jnz     short loc_18002E44A
0x18002e414  mov     r8, [rbp+47h+Size]
0x18002e418  mov     rax, [rbp+47h+Buf1]
0x18002e41c  mov     word ptr [rbp+47h+var_B4+4], r8w
0x18002e421  mov     qword ptr [rbp+47h+var_A8+8], rax
0x18002e425  mov     dword ptr [rbp+47h+var_B4], 1
0x18002e42c  mov     qword ptr [rbp+47h+var_A8], r9
0x18002e430  test    r12w, r12w
0x18002e434  jz      short loc_18002E46A
0x18002e436  movzx   ecx, r12w
0x18002e43a  cmp     r14b, 1
0x18002e43e  jz      short loc_18002E457
0x18002e440  cmp     r14b, 2
0x18002e444  jnz     short loc_18002E44A
0x18002e446  add     rcx, 4
0x18002e44a  mov     r14b, byte ptr [rbp+47h+arg_0]
0x18002e44e  mov     r12, [rbp+47h+arg_18]
0x18002e452  jmp     loc_18002E2E9
0x18002e457  add     rcx, 2
0x18002e45b  jmp     short loc_18002E44A
0x18002e45d  movzx   eax, r13w
0x18002e461  add     rax, 2
0x18002e465  jmp     loc_18002E319
0x18002e46a  movzx   ecx, r8w
0x18002e46e  add     rcx, 2
0x18002e472  jmp     short loc_18002E43A
0x18002e474  movzx   eax, ax
0x18002e477  sub     ecx, eax
0x18002e479  jmp     loc_18002E24E
0x18002e47e  lea     r15, [rbx+2]
0x18002e482  cmp     r15, rdx
0x18002e485  ja      short loc_18002E407
0x18002e487  mov     r9d, 2; SourceSize
0x18002e48d  lea     rcx, [rbp+47h+var_B4+4]; Destination
0x18002e491  mov     edx, r9d; DestinationSize
0x18002e494  mov     r8, rbx; Source
0x18002e497  call    cs:__imp_memcpy_s
0x18002e49d  movzx   eax, word ptr [rbp+47h+var_B4+4]
0x18002e4a1  xor     r9d, r9d
0x18002e4a4  mov     r14b, [rbp+47h+var_B6]
0x18002e4a8  mov     rbx, r15
0x18002e4ab  movzx   r12d, [rbp+47h+var_B8]
0x18002e4b0  jmp     loc_18002E218
0x18002e4b5  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002e4b9  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 **
0x18002e4bd  lea     rcx, [rbp+47h+var_88]; this
0x18002e4c1  mov     [rbp+47h+arg_0], rax
0x18002e4c5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002e4ca  movzx   eax, [rbp+47h+var_80]
0x18002e4ce  cmp     r13, rax
0x18002e4d1  jnz     short loc_18002E510
0x18002e4d3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18002e4d7  mov     r8, r13; Size
0x18002e4da  mov     rcx, r12; Buf1
0x18002e4dd  call    memcmp_0
0x18002e4e2  mov     ebx, eax
0x18002e4e4  xor     r9d, r9d
0x18002e4e7  test    ebx, ebx
0x18002e4e9  jnz     loc_18002E2D6
0x18002e4ef  cmp     [rbp+47h+var_86], r9b
0x18002e4f3  jnz     loc_18002E5E1
0x18002e4f9  add     rdi, 38h ; '8'
0x18002e4fd  mov     al, r9b
0x18002e500  cmp     [rdi], r9b
0x18002e503  jnz     loc_18002E5F4
0x18002e509  mov     [rdi], al
0x18002e50b  jmp     loc_18002E38A
0x18002e510  movzx   eax, [rbp+47h+var_80]
0x18002e514  mov     ebx, r13d
0x18002e517  sub     ebx, eax
0x18002e519  jmp     short loc_18002E4E4
0x18002e51b  lea     rbx, [rcx+4]
0x18002e51f  cmp     rbx, rdx
0x18002e522  ja      loc_18002E407
0x18002e528  mov     r9d, 4; SourceSize
0x18002e52e  mov     qword ptr [rbp+47h+var_A8], rcx
0x18002e532  mov     r8, rcx; Source
0x18002e535  mov     edx, r9d; DestinationSize
0x18002e538  lea     rcx, [rbp+47h+var_B4]; Destination
0x18002e53c  call    cs:__imp_memcpy_s
0x18002e542  jmp     loc_18002E3D3
0x18002e547  mov     r8, r15; unsigned __int8 *
0x18002e54a  lea     rdx, [rbp+47h+var_B8]; struct wil::details_abi::UsageIndexProperty *
0x18002e54e  mov     rcx, rdi; this
0x18002e551  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18002e556  mov     r14b, [rbp+47h+var_B6]
0x18002e55a  mov     rsi, rax
0x18002e55d  movzx   r12d, [rbp+47h+var_B8]
0x18002e562  mov     rcx, rax
0x18002e565  xor     r9d, r9d
0x18002e568  jmp     loc_18002E1DB
0x18002e56d  lea     rcx, [rbp+47h+var_B8]; this
0x18002e571  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18002e576  jmp     loc_18002E2A1
0x18002e57b  mov     r12, [rbp+47h+arg_18]
0x18002e57f  or      ebx, 0FFFFFFFFh
0x18002e582  mov     r14d, r9d
0x18002e585  mov     rsi, r15
0x18002e588  cmp     r14d, dword ptr [rbp+47h+var_B4]
0x18002e58c  jnb     loc_18002E4E7
0x18002e592  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002e596  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 **
0x18002e59a  lea     rcx, [rbp+47h+var_88]; this
0x18002e59e  mov     [rbp+47h+arg_0], rsi
0x18002e5a2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002e5a7  test    al, al
0x18002e5a9  jz      short loc_18002E5D0
0x18002e5ab  mov     r8, r13; unsigned __int64
0x18002e5ae  lea     rcx, [rbp+47h+var_88]; this
0x18002e5b2  mov     rdx, r12; void *
0x18002e5b5  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18002e5ba  xor     r9d, r9d
0x18002e5bd  mov     ebx, eax
0x18002e5bf  test    eax, eax
0x18002e5c1  jle     loc_18002E4E7
0x18002e5c7  mov     rsi, [rbp+47h+arg_0]
0x18002e5cb  inc     r14d
0x18002e5ce  jmp     short loc_18002E588
  ... truncated ...
```
