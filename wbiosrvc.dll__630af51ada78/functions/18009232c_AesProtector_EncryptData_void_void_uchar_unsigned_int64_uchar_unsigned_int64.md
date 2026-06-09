# AesProtector::EncryptData(void *,void *,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x18009232c`
- end: `0x18009268d`
- name: `?EncryptData@AesProtector@@AEAAJPEAX0PEAE_KPEAPEAEPEA_K@Z`
- size: `865`
- prototype: `int(AesProtector *__hidden this, void *, void *, unsigned __int8 *, unsigned __int64, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800926a0`

## callees

- `0x18002c420`
- `0x18002dd70`
- `0x18002ddb0`
- `0x180038e30`
- `0x180069cc8`
- `0x18006b0b5`
- `0x18009232c`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800923dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800923dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800923a4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800923a4`
- `bcrypt!BCryptEncrypt` at `0x180092515`
- `bcrypt!BCryptEncrypt` at `0x1800925c2`
- `bcrypt!BCryptEncrypt` at `0x180092515`
- `bcrypt!BCryptEncrypt` at `0x1800925c2`
- `bcrypt!BCryptGenRandom` at `0x180092474`
- `bcrypt!BCryptGenRandom` at `0x180092474`

## pseudocode

```c
__int64 __fastcall AesProtector::EncryptData(
        AesProtector *this,
        void *a2,
        void *a3,
        unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 **a6,
        unsigned __int64 *a7)
{
  unsigned int v7; // r15d
  UCHAR *v10; // rax
  unsigned __int64 v11; // r12
  UCHAR *v12; // r13
  int v14; // ebx
  AesProtector *v15; // rcx
  void *v16; // rsi
  signed int LastError; // eax
  unsigned int *v18; // rdi
  AesProtector *v19; // rcx
  NTSTATUS v20; // eax
  size_t v21; // rcx
  void *v22; // rsi
  NTSTATUS v23; // eax
  void *v24; // rdx
  unsigned int v25; // eax
  char *v26; // rax
  __int64 v27; // r14
  UCHAR *v28; // r14
  NTSTATUS v29; // eax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  ULONG cbOutput; // [rsp+40h] [rbp-99h]
  PUCHAR pcbResult; // [rsp+58h] [rbp-81h] BYREF
  void *Src; // [rsp+60h] [rbp-79h]
  ULONG cbInput; // [rsp+68h] [rbp-71h]
  PUCHAR pbOutput; // [rsp+70h] [rbp-69h]
  UCHAR *v37; // [rsp+78h] [rbp-61h]
  unsigned __int64 v38; // [rsp+80h] [rbp-59h]
  _DWORD pPaddingInfo[2]; // [rsp+88h] [rbp-51h] BYREF
  PUCHAR v40; // [rsp+90h] [rbp-49h] BYREF
  unsigned int v41; // [rsp+98h] [rbp-41h]
  unsigned int *v42; // [rsp+A0h] [rbp-39h]
  unsigned int v43; // [rsp+A8h] [rbp-31h]
  void *v44; // [rsp+B0h] [rbp-29h]
  unsigned int v45; // [rsp+B8h] [rbp-21h]
  int v46; // [rsp+D8h] [rbp-1h]
  unsigned int Sizea; // [rsp+148h] [rbp+6Fh]

  v7 = -1;
  if ( Size > 0xFFFFFFFF )
    return 2147943683LL;
  cbInput = Size + 72;
  if ( (unsigned int)Size >= 0xFFFFFFB8 )
    return 2147943683LL;
  v38 = (unsigned int)(Size + 72);
  v10 = (UCHAR *)AesProtector::MemAllocate(this, v38);
  v11 = 0;
  v12 = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( CopySid(0x44u, v10, a3) )
  {
    *((_DWORD *)v12 + 17) = Size;
    v14 = 0;
    memcpy_0(v12 + 72, a4, Size);
    pcbResult = 0;
    v16 = 0;
    Src = 0;
    Sizea = 0;
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    pcbResult = 0;
    v16 = 0;
    Src = 0;
    Sizea = 0;
    if ( v14 < 0 )
    {
      v18 = 0;
      goto LABEL_16;
    }
  }
  v11 = 32;
  v18 = (unsigned int *)AesProtector::MemAllocate(v15, 0x20u);
  if ( !v18 )
    goto LABEL_14;
  *v18 = (*(__int64 (__fastcall **)(AesProtector *))(*(_QWORD *)this + 24LL))(this);
  v18[1] = 32;
  v18[2] = 12;
  v19 = (AesProtector *)*((unsigned int *)this + 7);
  Sizea = *((_DWORD *)this + 7);
  v18[4] = (unsigned int)v19;
  pcbResult = (PUCHAR)(v18 + 5);
  Src = AesProtector::MemAllocate(v19, (unsigned int)v19);
  v16 = Src;
  if ( Src )
  {
    v20 = BCryptGenRandom(0, pcbResult, v18[2], 2u);
    if ( v20 < 0 )
      v14 = v20 | 0x10000000;
  }
  else
  {
LABEL_14:
    v14 = -2147024882;
  }
LABEL_16:
  memset_0(&v40, 0, 0x50u);
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  if ( v14 >= 0 )
  {
    v22 = 0;
    v42 = v18;
    v43 = v18[1];
    v40 = pcbResult;
    v41 = v18[2];
    v44 = Src;
    v45 = v18[4];
    pbOutput = 0;
    v37 = 0;
    v46 = 0;
    v23 = BCryptEncrypt(a2, v12, cbInput, pPaddingInfo, 0, 0, 0, 0, v18 + 3, 0);
    if ( v23 < 0 )
    {
      v7 = 0;
      v14 = v23 | 0x10000000;
    }
    else
    {
      v24 = (void *)(v18[1] + v18[3]);
      if ( (unsigned int)v24 < v18[1] || (v25 = v18[4], v21 = (unsigned int)v24 + v25, (unsigned int)v21 < v25) )
      {
        v14 = -2147023613;
      }
      else
      {
        v7 = (_DWORD)v24 + v25;
        v26 = (char *)MIDL_user_allocate(v21);
        v22 = v26;
        if ( v26 )
        {
          v27 = v18[3];
          pbOutput = (PUCHAR)&v26[v18[1]];
          v28 = &pbOutput[v27];
          goto LABEL_27;
        }
        v14 = -2147024882;
      }
    }
    if ( v14 < 0 )
      goto LABEL_32;
    v28 = v37;
LABEL_27:
    cbOutput = v18[3];
    LODWORD(pcbResult) = 0;
    v29 = BCryptEncrypt(a2, v12, cbInput, pPaddingInfo, 0, 0, pbOutput, cbOutput, (ULONG *)&pcbResult, 0);
    if ( v29 < 0 )
    {
      v14 = v29 | 0x10000000;
    }
    else
    {
      if ( (_DWORD)pcbResult == v18[3] )
      {
        memcpy_0(v22, v18, v18[1]);
        memcpy_0(v28, Src, v18[4]);
        v21 = v7;
        *a6 = (unsigned __int8 *)v22;
        *a7 = v7;
LABEL_36:
        v16 = Src;
        goto LABEL_37;
      }
      v14 = -2147024883;
    }
LABEL_32:
    if ( v22 )
    {
      v30 = v7;
      v31 = v22;
      if ( v7 )
      {
        do
        {
          *v31++ = 0;
          --v30;
        }
        while ( v30 );
      }
      wil::details::FreeProcessHeap((wil::details *)v22, v24);
    }
    goto LABEL_36;
  }
LABEL_37:
  if ( v16 )
    AesProtector::MemZeroAndRelease((AesProtector *)v21, v16, Sizea);
  if ( v18 )
    AesProtector::MemZeroAndRelease((AesProtector *)v21, v18, v11);
  AesProtector::MemZeroAndRelease((AesProtector *)v21, v12, v38);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009232c  mov     rax, rsp
0x18009232f  mov     [rax+18h], rbx
0x180092333  mov     [rax+10h], rdx
0x180092337  mov     [rax+8], rcx
0x18009233b  push    rbp
0x18009233c  push    rsi
0x18009233d  push    rdi
0x18009233e  push    r12
0x180092340  push    r13
0x180092342  push    r14
0x180092344  push    r15
0x180092346  lea     rbp, [rax-47h]
0x18009234a  sub     rsp, 0E0h
0x180092351  mov     rdi, [rbp+3Fh+Size]
0x180092355  mov     r15d, 0FFFFFFFFh
0x18009235b  mov     rsi, r9
0x18009235e  mov     rbx, r8
0x180092361  cmp     rdi, r15
0x180092364  ja      loc_18009266D
0x18009236a  lea     eax, [rdi+48h]
0x18009236d  mov     [rbp+3Fh+cbInput], eax
0x180092370  cmp     eax, 48h ; 'H'
0x180092373  jb      loc_18009266D
0x180092379  mov     edx, eax; unsigned __int64
0x18009237b  mov     [rbp+3Fh+var_98], rax
0x18009237f  call    ?MemAllocate@AesProtector@@AEAAPEAX_K@Z; AesProtector::MemAllocate(unsigned __int64)
0x180092384  xor     r12d, r12d
0x180092387  mov     r13, rax
0x18009238a  test    rax, rax
0x18009238d  jnz     short loc_180092399
0x18009238f  mov     eax, 8007000Eh
0x180092394  jmp     loc_180092672
0x180092399  mov     r8, rbx; pSourceSid
0x18009239c  mov     rdx, r13; pDestinationSid
0x18009239f  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800923a4  call    cs:__imp_CopySid
0x1800923aa  mov     r14d, 8007000Eh
0x1800923b0  test    eax, eax
0x1800923b2  jz      short loc_1800923DC
0x1800923b4  lea     rcx, [r13+48h]; void *
0x1800923b8  mov     [r13+44h], edi
0x1800923bc  mov     r8, rdi; Size
0x1800923bf  mov     rdx, rsi; Src
0x1800923c2  mov     ebx, r12d
0x1800923c5  call    memcpy_0
0x1800923ca  mov     [rsp+110h+var_C0], r12
0x1800923cf  mov     rsi, r12
0x1800923d2  mov     [rbp+3Fh+Src], r12
0x1800923d6  mov     dword ptr [rbp+3Fh+Size], r12d
0x1800923da  jmp     short loc_180092409
0x1800923dc  call    cs:__imp_GetLastError
0x1800923e2  mov     ebx, eax
0x1800923e4  test    eax, eax
0x1800923e6  jle     short loc_1800923F1
0x1800923e8  movzx   ebx, ax
0x1800923eb  or      ebx, 80070000h
0x1800923f1  mov     [rsp+110h+var_C0], r12
0x1800923f6  mov     rsi, r12
0x1800923f9  mov     [rbp+3Fh+Src], r12
0x1800923fd  mov     dword ptr [rbp+3Fh+Size], r12d
0x180092401  test    ebx, ebx
0x180092403  js      loc_18009248B
0x180092409  mov     r12d, 20h ; ' '
0x18009240f  mov     edx, r12d; unsigned __int64
0x180092412  call    ?MemAllocate@AesProtector@@AEAAPEAX_K@Z; AesProtector::MemAllocate(unsigned __int64)
0x180092417  mov     rdi, rax
0x18009241a  test    rax, rax
0x18009241d  jz      short loc_180092486
0x18009241f  mov     rsi, [rbp+3Fh+arg_0]
0x180092423  mov     rcx, rsi
0x180092426  mov     rax, [rsi]
0x180092429  mov     rax, [rax+18h]
0x18009242d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092432  mov     [rdi], eax
0x180092434  lea     rax, [rdi+14h]
0x180092438  mov     [rdi+4], r12d
0x18009243c  mov     dword ptr [rdi+8], 0Ch
0x180092443  mov     ecx, [rsi+1Ch]; this
0x180092446  mov     edx, ecx; unsigned __int64
0x180092448  mov     dword ptr [rbp+3Fh+Size], ecx
0x18009244b  mov     [rdi+10h], ecx
0x18009244e  mov     [rsp+110h+var_C0], rax
0x180092453  call    ?MemAllocate@AesProtector@@AEAAPEAX_K@Z; AesProtector::MemAllocate(unsigned __int64)
0x180092458  mov     [rbp+3Fh+Src], rax
0x18009245c  mov     rsi, rax
0x18009245f  test    rax, rax
0x180092462  jz      short loc_180092486
0x180092464  mov     r8d, [rdi+8]; cbBuffer
0x180092468  lea     r9d, [r12-1Eh]; dwFlags
0x18009246d  mov     rdx, [rsp+110h+var_C0]; pbBuffer
0x180092472  xor     ecx, ecx; hAlgorithm
0x180092474  call    cs:__imp_BCryptGenRandom
0x18009247a  test    eax, eax
0x18009247c  jns     short loc_18009248E
0x18009247e  mov     ebx, eax
0x180092480  bts     ebx, 1Ch
0x180092484  jmp     short loc_18009248E
0x180092486  mov     ebx, r14d
0x180092489  jmp     short loc_18009248E
0x18009248b  mov     rdi, r12
0x18009248e  xor     edx, edx; Val
0x180092490  lea     rcx, [rbp+3Fh+var_88]; void *
0x180092494  lea     r8d, [rdx+50h]; Size
0x180092498  call    memset_0
0x18009249d  mov     [rbp+3Fh+pPaddingInfo], 58h ; 'X'
0x1800924a4  mov     [rbp+3Fh+var_8C], 1
0x1800924ab  test    ebx, ebx
0x1800924ad  js      loc_18009263C
0x1800924b3  mov     r8d, [rbp+3Fh+cbInput]; cbInput
0x1800924b7  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x1800924bb  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800924bf  xor     esi, esi
0x1800924c1  mov     [rsp+110h+dwFlags], esi; dwFlags
0x1800924c5  mov     rdx, r13; pbInput
0x1800924c8  mov     [rbp+3Fh+var_78], rdi
0x1800924cc  mov     eax, [rdi+4]
0x1800924cf  mov     [rbp+3Fh+var_70], eax
0x1800924d2  mov     rax, [rsp+110h+var_C0]
0x1800924d7  mov     [rbp+3Fh+var_88], rax
0x1800924db  mov     eax, [rdi+8]
0x1800924de  mov     [rbp+3Fh+var_80], eax
0x1800924e1  mov     rax, [rbp+3Fh+Src]
0x1800924e5  mov     [rbp+3Fh+var_68], rax
0x1800924e9  mov     eax, [rdi+10h]
0x1800924ec  mov     [rbp+3Fh+var_60], eax
0x1800924ef  lea     rax, [rdi+0Ch]
0x1800924f3  mov     [rsp+110h+pcbResult], rax; pcbResult
0x1800924f8  mov     [rsp+110h+cbOutput], esi; cbOutput
0x1800924fc  mov     [rsp+110h+pbOutput], rsi; pbOutput
0x180092501  mov     [rsp+110h+cbIV], esi; cbIV
0x180092505  mov     [rsp+110h+pbIV], rsi; pbIV
0x18009250a  mov     [rbp+3Fh+var_A8], rsi
0x18009250e  mov     [rbp+3Fh+var_A0], rsi
0x180092512  mov     [rbp+3Fh+var_40], esi
0x180092515  call    cs:__imp_BCryptEncrypt
0x18009251b  test    eax, eax
0x18009251d  js      short loc_180092563
0x18009251f  mov     edx, [rdi+0Ch]
0x180092522  add     edx, [rdi+4]
0x180092525  cmp     edx, [rdi+4]
0x180092528  jb      short loc_18009255C
0x18009252a  mov     eax, [rdi+10h]
0x18009252d  lea     ecx, [rdx+rax]; size
0x180092530  cmp     ecx, eax
0x180092532  jb      short loc_18009255C
0x180092534  mov     r15d, ecx
0x180092537  call    MIDL_user_allocate
0x18009253c  mov     rsi, rax
0x18009253f  test    rax, rax
0x180092542  jz      short loc_180092557
0x180092544  mov     eax, [rdi+4]
0x180092547  mov     r14d, [rdi+0Ch]
0x18009254b  add     rax, rsi
0x18009254e  mov     [rbp+3Fh+var_A8], rax
0x180092552  add     r14, rax
0x180092555  jmp     short loc_180092578
0x180092557  mov     ebx, r14d
0x18009255a  jmp     short loc_18009256C
0x18009255c  mov     ebx, 80070503h
0x180092561  jmp     short loc_18009256C
0x180092563  xor     r15d, r15d
0x180092566  mov     ebx, eax
0x180092568  bts     ebx, 1Ch
0x18009256c  test    ebx, ebx
0x18009256e  js      loc_180092614
0x180092574  mov     r14, [rbp+3Fh+var_A0]
0x180092578  mov     r8d, [rbp+3Fh+cbInput]; cbInput
0x18009257c  lea     rax, [rsp+110h+var_C0]
0x180092581  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180092585  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x180092589  mov     [rsp+110h+dwFlags], 0; dwFlags
0x180092591  mov     rdx, r13; pbInput
0x180092594  mov     [rsp+110h+pcbResult], rax; pcbResult
0x180092599  mov     eax, [rdi+0Ch]
0x18009259c  mov     [rsp+110h+cbOutput], eax; cbOutput
0x1800925a0  mov     rax, [rbp+3Fh+var_A8]
0x1800925a4  mov     [rsp+110h+pbOutput], rax; pbOutput
0x1800925a9  mov     [rsp+110h+cbIV], 0; cbIV
0x1800925b1  mov     [rsp+110h+pbIV], 0; pbIV
0x1800925ba  mov     dword ptr [rsp+110h+var_C0], 0
0x1800925c2  call    cs:__imp_BCryptEncrypt
0x1800925c8  test    eax, eax
0x1800925ca  js      short loc_18009260E
0x1800925cc  mov     eax, [rdi+0Ch]
0x1800925cf  cmp     dword ptr [rsp+110h+var_C0], eax
0x1800925d3  jnz     short loc_180092607
0x1800925d5  mov     r8d, [rdi+4]; Size
0x1800925d9  mov     rdx, rdi; Src
0x1800925dc  mov     rcx, rsi; void *
0x1800925df  call    memcpy_0
0x1800925e4  mov     r8d, [rdi+10h]; Size
0x1800925e8  mov     rcx, r14; void *
0x1800925eb  mov     rdx, [rbp+3Fh+Src]; Src
0x1800925ef  call    memcpy_0
0x1800925f4  mov     rax, [rbp+3Fh+arg_28]
0x1800925f8  mov     ecx, r15d
0x1800925fb  mov     [rax], rsi
0x1800925fe  mov     rax, [rbp+3Fh+arg_30]
0x180092602  mov     [rax], rcx
0x180092605  jmp     short loc_180092638
0x180092607  mov     ebx, 8007000Dh
0x18009260c  jmp     short loc_180092614
0x18009260e  mov     ebx, eax
0x180092610  bts     ebx, 1Ch
0x180092614  test    rsi, rsi
0x180092617  jz      short loc_180092638
0x180092619  mov     ecx, r15d
0x18009261c  mov     rax, rsi
0x18009261f  test    r15d, r15d
0x180092622  jz      short loc_180092630
0x180092624  mov     byte ptr [rax], 0
0x180092627  inc     rax
0x18009262a  sub     rcx, 1
0x18009262e  jnz     short loc_180092624
0x180092630  mov     rcx, rsi; this
0x180092633  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180092638  mov     rsi, [rbp+3Fh+Src]
0x18009263c  test    rsi, rsi
0x18009263f  jz      short loc_18009264D
0x180092641  mov     r8d, dword ptr [rbp+3Fh+Size]; unsigned __int64
0x180092645  mov     rdx, rsi; void *
0x180092648  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x18009264d  test    rdi, rdi
0x180092650  jz      short loc_18009265D
0x180092652  mov     r8, r12; unsigned __int64
0x180092655  mov     rdx, rdi; void *
0x180092658  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x18009265d  mov     r8, [rbp+3Fh+var_98]; unsigned __int64
0x180092661  mov     rdx, r13; void *
0x180092664  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x180092669  mov     eax, ebx
0x18009266b  jmp     short loc_180092672
0x18009266d  mov     eax, 80070503h
0x180092672  mov     rbx, [rsp+110h+arg_10]
0x18009267a  add     rsp, 0E0h
0x180092681  pop     r15
0x180092683  pop     r14
0x180092685  pop     r13
0x180092687  pop     r12
0x180092689  pop     rdi
0x18009268a  pop     rsi
0x18009268b  pop     rbp
0x18009268c  retn
```
