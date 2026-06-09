# CSQLSatelliteConnection::AuthorizeSSLConnection(SNI_Conn *,CertificateHashList *,bool *)

- ea: `0x1004740e0`
- end: `0x100474659`
- name: `?AuthorizeSSLConnection@CSQLSatelliteConnection@@QEAAKPEAVSNI_Conn@@PEAVCertificateHashList@@PEA_N@Z`
- size: `1401`
- prototype: `unsigned int __fastcall(CSQLSatelliteConnection *__hidden this, struct SNI_Conn *, struct CertificateHashList *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x100473a60`

## callees

- `0x100403270`
- `0x100403420`
- `0x100403520`
- `0x100403760`
- `0x10041c040`
- `0x1004269b0`
- `0x1004740e0`
- `0x1004773d0`
- `0x1004775a0`
- `0x100486af0`
- `0x100488249`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100474329`
- `KERNEL32!QueryPerformanceCounter` at `0x10047437b`
- `KERNEL32!QueryPerformanceCounter` at `0x100474329`
- `KERNEL32!QueryPerformanceCounter` at `0x10047437b`
- `KERNEL32!GetLastError` at `0x100474235`
- `KERNEL32!GetLastError` at `0x100474235`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004743ea`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047431a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047436b`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10047433d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047446d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004744f8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100474556`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100474597`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047446d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004744f8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100474556`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100474597`
- `sqldk!SystemThread_TlsIndex` at `0x1004742ec`
- `sqldk!SystemThread_TlsOffset` at `0x1004742f5`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004742cf`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004743f6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004743f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004744d5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004744d5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004744c9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004744c9`
- `CRYPT32!CryptHashCertificate` at `0x10047422b`
- `CRYPT32!CryptHashCertificate` at `0x10047422b`
- `Secur32!QueryContextAttributesW` at `0x10047415a`
- `Secur32!QueryContextAttributesW` at `0x10047415a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall CSQLSatelliteConnection::AuthorizeSSLConnection(
        CSQLSatelliteConnection *this,
        struct SNI_Conn *a2,
        struct CertificateHashList *a3,
        const wchar_t *a4)
{
  unsigned int result; // eax
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 Head; // rdi
  __int64 v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rdi
  LARGE_INTEGER v12; // rbx
  signed __int64 UniqueThread_low; // rsi
  __int64 v14; // r8
  char *v15; // rcx
  LARGE_INTEGER v16; // rax
  LONGLONG v17; // rcx
  signed __int32 v18; // ecx
  int v19; // eax
  void *v20; // rcx
  CSQLSatelliteConnection *v21; // rbx
  char *v22; // rcx
  void *v23; // rbx
  void *v24; // rbx
  DWORD pcbComputedHash[4]; // [rsp+40h] [rbp-C0h] BYREF
  PCtxtHandle phContext; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h]
  struct CertificateHashList *v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+78h] [rbp-88h]
  unsigned int v31; // [rsp+80h] [rbp-80h]
  __int64 pBuffer; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v34; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v35; // [rsp+A0h] [rbp-60h]
  CSQLSatelliteConnection *v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[8]; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+D0h] [rbp-30h]
  _QWORD *v41; // [rsp+D8h] [rbp-28h]
  char *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  _QWORD v44[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v45; // [rsp+100h] [rbp+0h] BYREF
  __int64 v46; // [rsp+310h] [rbp+210h]
  __int64 v47; // [rsp+318h] [rbp+218h]
  PCtxtHandle *v48; // [rsp+320h] [rbp+220h] BYREF
  unsigned int v49; // [rsp+328h] [rbp+228h]
  char v50[8]; // [rsp+330h] [rbp+230h] BYREF
  int v51; // [rsp+338h] [rbp+238h]
  int v52; // [rsp+340h] [rbp+240h]
  _QWORD *v53; // [rsp+348h] [rbp+248h]
  char *v54; // [rsp+350h] [rbp+250h]
  __int64 v55; // [rsp+358h] [rbp+258h]
  _QWORD v56[2]; // [rsp+360h] [rbp+260h] BYREF
  char v57; // [rsp+370h] [rbp+270h] BYREF
  __int64 v58; // [rsp+580h] [rbp+480h]
  __int64 v59; // [rsp+588h] [rbp+488h]
  PCtxtHandle *p_phContext; // [rsp+590h] [rbp+490h] BYREF
  unsigned int v61; // [rsp+598h] [rbp+498h]
  BYTE Buf1[16]; // [rsp+5A0h] [rbp+4A0h] BYREF
  int v63; // [rsp+5B0h] [rbp+4B0h]

  v37 = -2;
  v35 = (wchar_t *)a4;
  v36 = this;
  *(_BYTE *)a4 = 0;
  pBuffer = 0;
  phContext = 0;
  result = SNIGetInfo((__int64)a2, 42, (__int64)&phContext, a4);
  v6 = result;
  if ( result )
  {
    if ( (dword_1005113AC & 0x10000) != 0 )
    {
      v51 = 0x10000;
      v52 = 0;
      v53 = v56;
      v54 = &v57;
      v58 = 0;
      v55 = 0;
      v59 = 0;
      v56[0] = &p_phContext;
      v56[1] = 12;
      p_phContext = &phContext;
      v61 = result;
      XeSQLSatellitePkg::get_SSL_certificate_fail::Publish((XeSQLSatellitePkg::get_SSL_certificate_fail *)v50);
      return v6;
    }
    return result;
  }
  result = QueryContextAttributesW(phContext, 0x53u, &pBuffer);
  v7 = result;
  v31 = result;
  if ( result )
  {
    if ( (dword_1005113AC & 0x10000) != 0 )
    {
      v39 = 0x10000;
      v40 = 0;
      v41 = v44;
      v42 = &v45;
      v46 = 0;
      v43 = 0;
      v47 = 0;
      v44[0] = &v48;
      v44[1] = 12;
      v48 = &phContext;
      v49 = result;
      XeSQLSatellitePkg::get_SSL_certificate_fail::Publish((XeSQLSatellitePkg::get_SSL_certificate_fail *)v38);
      return v7;
    }
    return result;
  }
  if ( !pBuffer )
    return result;
  *(_OWORD *)Buf1 = 0;
  v63 = 0;
  pcbComputedHash[0] = 20;
  if ( !CryptHashCertificate(0, 0, 0, *(const BYTE **)(pBuffer + 8), *(_DWORD *)(pBuffer + 16), Buf1, pcbComputedHash) )
    GetLastError();
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v28 = a3;
  Head = TList<CertificateHashList,CertificateHash,0,TListSLock>::GetHead(a3);
  *(_QWORD *)&v27 = Head;
  *((_QWORD *)&v27 + 1) = TList<CertificateHashList,CertificateHash,0,TListSLock>::GetTail(a3);
  v9 = 0;
  do
  {
    v10 = 0;
    if ( !v9 )
    {
      v10 = Head;
      goto LABEL_55;
    }
    if ( Head )
    {
      if ( Head == *((_QWORD *)&v27 + 1) )
      {
        *(_QWORD *)&v27 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Head + 24), 0xFFFFFFFF) != 1 )
        {
LABEL_54:
          Head = v27;
          goto LABEL_55;
        }
        if ( *(_QWORD *)(Head + 8) )
        {
          TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(Head + 16), (__int64 *)Head);
          operator delete((void *)Head, 0x38u);
          Head = v27;
          goto LABEL_62;
        }
        v20 = (void *)Head;
      }
      else
      {
        v11 = 0;
        v12.QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *((_DWORD *)a3 + 4)
          || _InterlockedCompareExchange64((volatile signed __int64 *)a3 + 2, UniqueThread_low, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v14 && *(_QWORD *)(v14 + 272) == v14 )
              v11 = *(_QWORD *)(v14 + 256);
            if ( v11 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v12 = PerformanceCount;
              }
              else
              {
                v12.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          v15 = (char *)a3 + 16;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v15, UniqueThread_low);
          else
            Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v15, v11, UniqueThread_low);
          if ( v11 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v34);
              v16 = v34;
            }
            else
            {
              v16.QuadPart = MEMORY[0x7FFE0008];
            }
            v17 = v16.QuadPart - v12.QuadPart;
            if ( v16.QuadPart < (unsigned __int64)v12.QuadPart )
              v17 = 0;
            *(_QWORD *)(v11 + 3192) += v17;
          }
        }
        v10 = *(_QWORD *)(v9 + 8);
LABEL_34:
        while ( (struct CertificateHashList *)v10 != a3 )
        {
          if ( !v10 )
            goto LABEL_43;
          v18 = *(_DWORD *)(v10 + 24);
          if ( v18 )
          {
            while ( v18 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 24), v18 + 1, v18) )
            {
              _mm_pause();
              v18 = *(_DWORD *)(v10 + 24);
              if ( !v18 )
              {
                v10 = *(_QWORD *)(v10 + 8);
                goto LABEL_34;
              }
            }
            if ( v18 != -1 )
              goto LABEL_43;
          }
          v10 = *(_QWORD *)(v10 + 8);
        }
        v10 = 0;
LABEL_43:
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v19 = rand();
          if ( v19 == 5 * (v19 / 5) )
            Spinlock<19,1,268435714>::UpdateStatSnapshot();
        }
        *((_QWORD *)a3 + 2) = 0;
        *(_QWORD *)&v27 = v10;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) != 1 )
          goto LABEL_54;
        if ( *(_QWORD *)(v9 + 8) )
          TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v9 + 16), (__int64 *)v9);
        v20 = (void *)v9;
      }
      operator delete(v20, 0x38u);
      goto LABEL_54;
    }
LABEL_55:
    v9 = v10;
    if ( !v10 )
      goto LABEL_62;
  }
  while ( pcbComputedHash[0] != *(_DWORD *)(v10 + 52) || memcmp_0(Buf1, (const void *)(v10 + 32), pcbComputedHash[0]) );
  *(_BYTE *)v35 = 1;
  v21 = v36;
  v22 = (char *)v36 + 912;
  if ( v36 == (CSQLSatelliteConnection *)-912LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    MEMORY[0x38] = 1;
  }
  else
  {
    *(_OWORD *)v22 = *(_OWORD *)Buf1;
    *((_DWORD *)v22 + 4) = v63;
    *((_BYTE *)v21 + 968) = 1;
  }
LABEL_62:
  if ( Head )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Head + 24), 0xFFFFFFFF) == 1 )
    {
      v23 = (void *)v27;
      if ( *(_QWORD *)(v27 + 8) )
        TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(*(_QWORD *)(v27 + 16), (__int64 *)v27);
      operator delete(v23, 0x38u);
    }
    *(_QWORD *)&v27 = 0;
  }
  if ( *((_QWORD *)&v27 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 24LL), 0xFFFFFFFF) == 1 )
    {
      v24 = (void *)*((_QWORD *)&v27 + 1);
      if ( *(_QWORD *)(*((_QWORD *)&v27 + 1) + 8LL) )
        TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(
          *(_QWORD *)(*((_QWORD *)&v27 + 1) + 16LL),
          *((__int64 **)&v27 + 1));
      operator delete(v24, 0x38u);
    }
    *((_QWORD *)&v27 + 1) = 0;
  }
  v28 = 0;
  return v31;
}

```

## disassembly

```asm
0x1004740e0  push    rbp
0x1004740e2  push    rbx
0x1004740e3  push    rsi
0x1004740e4  push    rdi
0x1004740e5  push    r12
0x1004740e7  push    r13
0x1004740e9  push    r14
0x1004740eb  push    r15
0x1004740ed  lea     rbp, [rsp-4C8h]
0x1004740f5  sub     rsp, 5C8h
0x1004740fc  mov     [rbp+500h+var_550], 0FFFFFFFFFFFFFFFEh
0x100474104  mov     rax, cs:__security_cookie
0x10047410b  xor     rax, rsp
0x10047410e  mov     [rbp+500h+var_48], rax
0x100474115  mov     [rbp+500h+var_560], r9
0x100474119  mov     r13, r8
0x10047411c  mov     rax, rdx
0x10047411f  mov     [rbp+500h+var_558], rcx
0x100474123  mov     byte ptr [r9], 0
0x100474127  xor     r15d, r15d
0x10047412a  mov     [rbp+500h+pBuffer], r15
0x10047412e  mov     [rsp+600h+phContext], r15
0x100474133  lea     r8, [rsp+600h+phContext]
0x100474138  lea     edx, [r15+2Ah]
0x10047413c  mov     rcx, rax
0x10047413f  call    SNIGetInfo
0x100474144  mov     ebx, eax
0x100474146  test    eax, eax
0x100474148  jnz     loc_1004745AF
0x10047414e  lea     r8, [rbp+500h+pBuffer]; pBuffer
0x100474152  lea     edx, [rax+53h]; ulAttribute
0x100474155  mov     rcx, [rsp+600h+phContext]; phContext
0x10047415a  call    cs:__imp_QueryContextAttributesW
0x100474160  mov     esi, eax
0x100474162  mov     [rbp+500h+var_580], eax
0x100474165  test    eax, eax
0x100474167  jz      short loc_1004741DB
0x100474169  test    cs:dword_1005113AC, 10000h
0x100474173  jz      loc_100474636
0x100474179  mov     [rbp+500h+var_538], 10000h
0x100474180  mov     [rbp+500h+var_530], r15d
0x100474184  lea     rax, [rbp+500h+var_510]
0x100474188  mov     [rbp+500h+var_528], rax
0x10047418c  lea     rax, [rbp+500h+var_500]
0x100474190  mov     [rbp+500h+var_520], rax
0x100474194  mov     [rbp+500h+var_2F0], r15
0x10047419b  mov     [rbp+500h+var_518], r15
0x10047419f  mov     [rbp+500h+var_2E8], r15
0x1004741a6  lea     rax, [rbp+500h+var_2E0]
0x1004741ad  mov     [rbp+500h+var_510], rax
0x1004741b1  mov     [rbp+500h+var_508], 0Ch
0x1004741b9  lea     rax, [rsp+600h+phContext]
0x1004741be  mov     [rbp+500h+var_2E0], rax
0x1004741c5  mov     [rbp+500h+var_2D8], esi
0x1004741cb  lea     rcx, [rbp+500h+var_540]; this
0x1004741cf  call    ?Publish@get_SSL_certificate_fail@XeSQLSatellitePkg@@QEAAXXZ; XeSQLSatellitePkg::get_SSL_certificate_fail::Publish(void)
0x1004741d4  mov     eax, esi
0x1004741d6  jmp     loc_100474636
0x1004741db  mov     r9, [rbp+500h+pBuffer]
0x1004741df  test    r9, r9
0x1004741e2  jz      loc_100474636
0x1004741e8  xorps   xmm0, xmm0
0x1004741eb  xor     eax, eax
0x1004741ed  movups  xmmword ptr [rbp+500h+Buf1], xmm0
0x1004741f4  mov     [rbp+500h+var_50], eax
0x1004741fa  mov     [rsp+600h+var_5C0], 14h
0x100474202  lea     rax, [rsp+600h+var_5C0]
0x100474207  mov     [rsp+600h+pcbComputedHash], rax; pcbComputedHash
0x10047420c  lea     rax, [rbp+500h+Buf1]
0x100474213  mov     [rsp+600h+pbComputedHash], rax; pbComputedHash
0x100474218  mov     eax, [r9+10h]
0x10047421c  mov     [rsp+600h+cbEncoded], eax; cbEncoded
0x100474220  mov     r9, [r9+8]; pbEncoded
0x100474224  xor     r8d, r8d; dwFlags
0x100474227  xor     edx, edx; Algid
0x100474229  xor     ecx, ecx; hCryptProv
0x10047422b  call    cs:__imp_CryptHashCertificate
0x100474231  test    eax, eax
0x100474233  jnz     short loc_10047423B
0x100474235  call    cs:__imp_GetLastError
0x10047423b  xorps   xmm0, xmm0
0x10047423e  movdqu  [rsp+600h+var_5A8], xmm0
0x100474244  mov     [rsp+600h+var_590], r15
0x100474249  mov     [rsp+600h+var_588], r15d
0x10047424e  mov     [rsp+600h+var_598], r15
0x100474253  mov     [rsp+600h+var_598], r13
0x100474258  mov     rcx, r13
0x10047425b  call    ?GetHead@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAPEAVCertificateHash@@XZ; TList<CertificateHashList,CertificateHash,0,TListSLock>::GetHead(void)
0x100474260  mov     rdi, rax
0x100474263  mov     qword ptr [rsp+600h+var_5A8], rax
0x100474268  mov     rcx, r13
0x10047426b  call    ?GetTail@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAPEAVCertificateHash@@XZ; TList<CertificateHashList,CertificateHash,0,TListSLock>::GetTail(void)
0x100474270  mov     qword ptr [rsp+600h+var_5A8+8], rax
0x100474275  mov     r14, r15
0x100474278  mov     r12d, 0FFFFFFFFh
0x10047427e  xchg    ax, ax
0x100474280  mov     rbx, r15
0x100474283  test    r14, r14
0x100474286  jnz     short loc_100474290
0x100474288  mov     rbx, rdi
0x10047428b  jmp     loc_100474478
0x100474290  test    rdi, rdi
0x100474293  jz      loc_100474478
0x100474299  cmp     rdi, qword ptr [rsp+600h+var_5A8+8]
0x10047429e  jz      loc_10047444C
0x1004742a4  xor     edi, edi
0x1004742a6  mov     ebx, edi
0x1004742a8  mov     eax, gs:48h
0x1004742b0  mov     esi, eax
0x1004742b2  mov     eax, [r13+10h]
0x1004742b6  test    eax, eax
0x1004742b8  jnz     short loc_1004742CF
0x1004742ba  xor     eax, eax
0x1004742bc  lock cmpxchg [r13+10h], rsi
0x1004742c2  mov     eax, edi
0x1004742c4  setz    al
0x1004742c7  test    eax, eax
0x1004742c9  jnz     loc_1004743AA
0x1004742cf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004742d6  mov     ecx, [rax]
0x1004742d8  and     ecx, 84h
0x1004742de  cmp     cl, 84h
0x1004742e1  jnz     short loc_10047433D
0x1004742e3  mov     rdx, gs:58h
0x1004742ec  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004742f3  mov     ecx, [rax]
0x1004742f5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004742fc  mov     r8d, [rax]
0x1004742ff  add     r8, [rdx+rcx*8]
0x100474303  jz      short loc_100474315
0x100474305  cmp     [r8+110h], r8
0x10047430c  jnz     short loc_100474315
0x10047430e  mov     rdi, [r8+100h]
0x100474315  test    rdi, rdi
0x100474318  jz      short loc_10047433D
0x10047431a  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100474321  cmp     [rax], ebx
0x100474323  jz      short loc_100474335
0x100474325  lea     rcx, [rbp+500h+PerformanceCount]; lpPerformanceCount
0x100474329  call    cs:__imp_QueryPerformanceCounter
0x10047432f  mov     rbx, qword ptr [rbp+500h+PerformanceCount]
0x100474333  jmp     short loc_10047433D
0x100474335  mov     rbx, ds:7FFE0008h
0x10047433d  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100474344  lea     rcx, [r13+10h]
0x100474348  cmp     byte ptr [rax+0C7h], 0
0x10047434f  jge     short loc_10047435E
0x100474351  mov     r8, rsi
0x100474354  mov     rdx, rdi
0x100474357  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10047435c  jmp     short loc_100474366
0x10047435e  mov     rdx, rsi
0x100474361  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100474366  test    rdi, rdi
0x100474369  jz      short loc_1004743A8
0x10047436b  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100474372  cmp     dword ptr [rax], 0
0x100474375  jz      short loc_100474387
0x100474377  lea     rcx, [rbp+500h+var_568]; lpPerformanceCount
0x10047437b  call    cs:__imp_QueryPerformanceCounter
0x100474381  mov     rax, qword ptr [rbp+500h+var_568]
0x100474385  jmp     short loc_10047438F
0x100474387  mov     rax, ds:7FFE0008h
0x10047438f  mov     rcx, rax
0x100474392  sub     rcx, rbx
0x100474395  cmp     rax, rbx
0x100474398  mov     eax, 0
0x10047439d  cmovb   rcx, rax
0x1004743a1  add     [rdi+0C78h], rcx
0x1004743a8  xor     edi, edi
0x1004743aa  mov     rbx, [r14+8]
0x1004743ae  cmp     rbx, r13
0x1004743b1  jz      short loc_1004743E7
0x1004743b3  test    rbx, rbx
0x1004743b6  jz      short loc_1004743EA
0x1004743b8  mov     ecx, [rbx+18h]
0x1004743bb  test    ecx, ecx
0x1004743bd  jz      short loc_1004743E1
0x1004743bf  nop
0x1004743c0  lea     edx, [rcx+1]
0x1004743c3  mov     eax, ecx
0x1004743c5  lock cmpxchg [rbx+18h], edx
0x1004743ca  cmp     ecx, eax
0x1004743cc  jz      short loc_1004743DD
0x1004743ce  pause
0x1004743d0  mov     ecx, [rbx+18h]
0x1004743d3  test    ecx, ecx
0x1004743d5  jnz     short loc_1004743C0
0x1004743d7  mov     rbx, [rbx+8]
0x1004743db  jmp     short loc_1004743AE
0x1004743dd  test    edx, edx
0x1004743df  jnz     short loc_1004743EA
0x1004743e1  mov     rbx, [rbx+8]
0x1004743e5  jmp     short loc_1004743AE
0x1004743e7  mov     rbx, rdi
0x1004743ea  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004743f1  cmp     byte ptr [rax], 0
0x1004743f4  jz      short loc_10047441D
0x1004743f6  call    cs:__imp_rand
0x1004743fc  mov     r8d, eax
0x1004743ff  mov     eax, 66666667h
0x100474404  imul    r8d
0x100474407  sar     edx, 1
0x100474409  mov     ecx, edx
0x10047440b  shr     ecx, 1Fh
0x10047440e  add     edx, ecx
0x100474410  lea     ecx, [rdx+rdx*4]
0x100474413  cmp     r8d, ecx
0x100474416  jnz     short loc_10047441D
0x100474418  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10047441d  mov     [r13+10h], rdi
0x100474421  mov     qword ptr [rsp+600h+var_5A8], rbx
0x100474426  mov     eax, r12d
0x100474429  lock xadd [r14+18h], eax
0x10047442f  cmp     eax, 1
0x100474432  jnz     short loc_100474473
0x100474434  cmp     qword ptr [r14+8], 0
0x100474439  jz      short loc_100474447
0x10047443b  mov     rdx, r14
0x10047443e  mov     rcx, [r14+10h]
0x100474442  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x100474447  mov     rcx, r14
0x10047444a  jmp     short loc_100474468
0x10047444c  mov     qword ptr [rsp+600h+var_5A8], r15
0x100474451  mov     eax, r12d
0x100474454  lock xadd [rdi+18h], eax
0x100474459  cmp     eax, 1
0x10047445c  jnz     short loc_100474473
0x10047445e  cmp     qword ptr [rdi+8], 0
0x100474463  jnz     short loc_1004744E4
0x100474465  mov     rcx, rdi
0x100474468  mov     edx, 38h ; '8'
0x10047446d  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100474473  mov     rdi, qword ptr [rsp+600h+var_5A8]
0x100474478  mov     r14, rbx
0x10047447b  test    rbx, rbx
0x10047447e  jz      loc_100474521
0x100474484  mov     eax, [rsp+600h+var_5C0]
0x100474488  cmp     eax, [rbx+34h]
0x10047448b  mov     r15d, 0
0x100474491  jnz     loc_100474280
0x100474497  mov     r8d, eax; Size
0x10047449a  lea     rdx, [rbx+20h]; Buf2
0x10047449e  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1004744a5  call    memcmp_0
0x1004744aa  test    eax, eax
0x1004744ac  jnz     loc_100474280
0x1004744b2  mov     rax, [rbp+500h+var_560]
0x1004744b6  mov     byte ptr [rax], 1
0x1004744b9  mov     rbx, [rbp+500h+var_558]
0x1004744bd  lea     rcx, [rbx+390h]
0x1004744c4  test    rcx, rcx
0x1004744c7  jnz     short loc_100474505
0x1004744c9  call    cs:__imp__errno
0x1004744cf  mov     dword ptr [rax], 16h
0x1004744d5  call    cs:__imp__invalid_parameter_noinfo
0x1004744db  mov     byte ptr [rbx+3C8h], 1
0x1004744e2  jmp     short loc_100474524
0x1004744e4  mov     rdx, rdi
0x1004744e7  mov     rcx, [rdi+10h]
0x1004744eb  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x1004744f0  mov     edx, 38h ; '8'
0x1004744f5  mov     rcx, rdi
0x1004744f8  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004744fe  mov     rdi, qword ptr [rsp+600h+var_5A8]
0x100474503  jmp     short loc_100474524
0x100474505  movups  xmm0, xmmword ptr [rbp+500h+Buf1]
0x10047450c  movups  xmmword ptr [rcx], xmm0
0x10047450f  mov     eax, [rbp+500h+var_50]
0x100474515  mov     [rcx+10h], eax
0x100474518  mov     byte ptr [rbx+3C8h], 1
0x10047451f  jmp     short loc_100474524
0x100474521  xor     r15d, r15d
0x100474524  test    rdi, rdi
0x100474527  jz      short loc_100474561
0x100474529  mov     eax, r12d
0x10047452c  lock xadd [rdi+18h], eax
0x100474531  cmp     eax, 1
0x100474534  jnz     short loc_10047455C
0x100474536  mov     rbx, qword ptr [rsp+600h+var_5A8]
0x10047453b  cmp     qword ptr [rbx+8], 0
0x100474540  jz      short loc_10047454E
0x100474542  mov     rdx, rbx
0x100474545  mov     rcx, [rbx+10h]
0x100474549  call    ?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z; TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)
0x10047454e  mov     edx, 38h ; '8'
0x100474553  mov     rcx, rbx
0x100474556  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10047455c  mov     qword ptr [rsp+600h+var_5A8], r15
0x100474561  mov     rax, qword ptr [rsp+600h+var_5A8+8]
0x100474566  test    rax, rax
0x100474569  jz      short loc_1004745A2
0x10047456b  lock xadd [rax+18h], r12d
0x100474571  cmp     r12d, 1
0x100474575  jnz     short loc_10047459D
0x100474577  mov     rbx, qword ptr [rsp+600h+var_5A8+8]
0x10047457c  cmp     qword ptr [rbx+8], 0
0x100474581  jz      short loc_10047458F
0x100474583  mov     rdx, rbx
0x100474586  mov     rcx, [rbx+10h]
  ... truncated ...
```
