# CSsl3TlsClientContext::GenerateCertVerify(uchar *,ulong *)

- ea: `0x180079120`
- end: `0x180079691`
- name: `?GenerateCertVerify@CSsl3TlsClientContext@@AEAAKPEAEPEAK@Z`
- size: `1393`
- prototype: `unsigned int __fastcall(CSsl3TlsClientContext *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x18000d820`
- `0x1800214f0`
- `0x1800319c0`
- `0x180039a50`
- `0x18003d7b0`
- `0x180047dc8`
- `0x180057c8c`
- `0x180057cb4`
- `0x1800597b0`
- `0x180059d68`
- `0x18005b3fc`
- `0x180078244`
- `0x180079120`
- `0x180079b58`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180079493`
- `ntdll!RtlReleaseResource` at `0x180079493`
- `ntdll!RtlAcquireResourceShared` at `0x18007942f`
- `ntdll!RtlAcquireResourceShared` at `0x18007942f`
- `ncrypt!SslComputeClientAuthHash` at `0x18007947c`
- `ncrypt!SslComputeClientAuthHash` at `0x18007947c`

## pseudocode

```c
__int64 __fastcall CSsl3TlsClientContext::GenerateCertVerify(
        CSsl3TlsClientContext *this,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  __int64 v3; // rax
  unsigned int *v4; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // r13
  __int64 v11; // rcx
  int v12; // edx
  unsigned int v13; // ecx
  __int64 v14; // rax
  unsigned int v15; // r14d
  int v17; // r15d
  unsigned int v18; // ecx
  int v19; // edx
  wchar_t *v20; // rax
  char *v21; // rax
  CTlsSignatureSuiteList *v22; // rdi
  CTlsSignatureSuiteList *v23; // rcx
  __int64 v24; // r9
  unsigned __int16 v25; // r15
  CSsl3TlsClientContext *v26; // rcx
  unsigned __int64 TlsClientAuthHandshakeHash; // rdi
  unsigned int v28; // edi
  __int64 v29; // rdx
  __int64 *v30; // rax
  __int64 v31; // rcx
  unsigned int v32; // r14d
  unsigned int v33; // r14d
  unsigned int v34; // eax
  unsigned int v35; // eax
  size_t Size; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v38; // [rsp+7Ch] [rbp-5Dh] BYREF
  enum _eTlsHashAlgorithm v39; // [rsp+80h] [rbp-59h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-51h]
  _eTlsSignatureAlgorithm v41; // [rsp+90h] [rbp-49h]
  LPCWSTR lpString; // [rsp+98h] [rbp-41h] BYREF
  unsigned int *v43; // [rsp+A0h] [rbp-39h]
  void *v44; // [rsp+A8h] [rbp-31h]
  BYTE Src[64]; // [rsp+B0h] [rbp-29h] BYREF

  v3 = *((_QWORD *)this + 13);
  v4 = a3;
  Size = 0;
  v43 = a3;
  v44 = *(void **)(v3 + 816);
  v7 = *(_QWORD *)this;
  v38 = 32772;
  lpString = 0;
  v8 = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *))(v7 + 264))(this);
  v10 = v8;
  v37 = 0;
  v11 = *(_QWORD *)(v8 + 432);
  if ( v11 )
  {
    v12 = 118;
    v13 = *(_DWORD *)(v11 + 8) + 2;
    if ( v13 > 0x76 )
      v12 = v13;
  }
  else
  {
    v14 = *(_QWORD *)(v8 + 32);
    if ( v14 )
      v12 = *(_DWORD *)(*(_QWORD *)(v14 + 24) + 120LL) + 52;
    else
      v12 = 68;
  }
  v15 = v12 + 2;
  if ( (*((_DWORD *)this + 22) & 0x80800) == 0 )
    v15 = v12;
  if ( !a2 )
  {
    *v4 = v15;
    return 0;
  }
  v17 = 0;
  if ( *((_QWORD *)this + 332) && !*((_BYTE *)this + 2752) )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
    v18 = *((_DWORD *)this + 666);
    HIDWORD(Size) = v15 - 2;
    if ( v18 <= v15 - 2 )
    {
      memcpy_0(a2 + 2, *((const void **)this + 332), v18);
      v19 = *((_DWORD *)this + 666);
LABEL_71:
      a2[v17] = BYTE1(v19);
      a2[v17 + 1] = v19;
      *v4 = v17 + v19 + 2;
      return 0;
    }
    goto LABEL_58;
  }
  v41 = *(_DWORD *)(v10 + 132);
  if ( v41 == TlsSignatureAlgorithm_Rsa )
  {
    v20 = (wchar_t *)L"RSA";
    v38 = 32776;
    LODWORD(Size) = 36;
    v37 = 2;
  }
  else
  {
    if ( v41 == TlsSignatureAlgorithm_Dsa )
    {
      v20 = (wchar_t *)L"DSA";
    }
    else
    {
      if ( v41 != TlsSignatureAlgorithm_Ecdsa )
        return 2148074289LL;
      v20 = (wchar_t *)L"ECDSA";
    }
    LODWORD(Size) = 20;
  }
  String1 = v20;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids, v20);
  if ( (*((_DWORD *)this + 22) & 0x80800) != 0 )
  {
    v39 = TlsHashAlgorithm_None;
    if ( *(_QWORD *)(v10 + 112) )
    {
      v21 = (char *)operator new(0x24u);
      v22 = (CTlsSignatureSuiteList *)v21;
      if ( v21 )
      {
        *(_OWORD *)(v21 + 2) = 0;
        *(_OWORD *)(v21 + 18) = 0;
        *(_WORD *)v21 = 0;
        *((_WORD *)v21 + 17) = 0;
      }
      else
      {
        v22 = 0;
      }
      CTlsSignatureSuiteList::SetDefaultClientHello(v22);
      CTlsSignatureSuiteList::Restrict(v23, (CSsl3TlsClientContext *)((char *)this + 2230), *((_DWORD *)this + 22));
    }
    else
    {
      v22 = (CSsl3TlsClientContext *)((char *)this + 2230);
    }
    v25 = __ROR2__(
            CTlsSignatureSuiteList::GetMinimumCodePointToSign(
              v22,
              v41,
              *(_DWORD *)(v10 + 428),
              *((_DWORD *)this + 22),
              0),
            8);
    if ( *(_QWORD *)(v10 + 112) && v22 )
      operator delete(v22);
    if ( !v25 )
    {
      LOBYTE(v24) = 40;
      CSslContext::SetErrorAndFatalAlert(this, 304, 2148074289LL, v24);
      return 2148074289LL;
    }
    GetSignatureSuiteInfoByCodePoint(v25, 0, &v39, &v38, &lpString, (unsigned int *)&Size, &v37);
    TlsClientAuthHandshakeHash = CSsl3TlsContext::FindTlsClientAuthHandshakeHash(this, v39);
    if ( !TlsClientAuthHandshakeHash || v15 < 2 )
    {
      v28 = 1359;
      v29 = 304;
LABEL_47:
      LOBYTE(v9) = 80;
      CSslContext::SetErrorAndFatalAlert(v26, v29, v28, v9);
      return v28;
    }
    *(_WORD *)a2 = v25;
    v17 = 2;
  }
  else
  {
    TlsClientAuthHandshakeHash = *((_QWORD *)this + 289);
  }
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL), 1u);
  v30 = (__int64 *)*((_QWORD *)this + 1);
  if ( v30 )
    v31 = *v30;
  else
    v31 = 0;
  v28 = SslComputeClientAuthHash(
          v31,
          *(_QWORD *)(*((_QWORD *)this + 380) + 32LL),
          TlsClientAuthHandshakeHash,
          String1,
          Src,
          Size,
          &Size,
          0);
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL));
  if ( v28 )
  {
    v29 = 300;
LABEL_55:
    v26 = this;
    goto LABEL_47;
  }
  v32 = v15 - v17 - 2;
  HIDWORD(Size) = v32;
  if ( *((_BYTE *)this + 2752) )
  {
    if ( *((_DWORD *)this + 666) > v32 )
    {
LABEL_58:
      v28 = -2146893018;
      v29 = 302;
      goto LABEL_55;
    }
    memcpy_0(&a2[v17 + 2], *((const void **)this + 332), *((unsigned int *)this + 666));
  }
  v33 = v38;
  v34 = SignHashUsingCred(
          this,
          (struct CSslCredential *)v10,
          v44,
          v38,
          v37,
          String1,
          lpString,
          Src,
          Size,
          &a2[v17 + 2],
          (DWORD *)&Size + 1,
          *((_BYTE *)this + 2752),
          *((_DWORD *)this + 666));
  v28 = v34;
  if ( v34 != -1073741168 && v34 != -2146893790 )
  {
    if ( v34 == 590610 )
    {
      if ( *((_BYTE *)this + 1986) )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
        *((_DWORD *)this + 23) = 77;
        return 590610;
      }
    }
    else if ( !v34 )
    {
      v19 = HIDWORD(Size);
      v4 = v43;
      goto LABEL_71;
    }
    v29 = 301;
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
  if ( (*((_DWORD *)this + 22) & 0x80800) != 0 )
  {
    v28 = -2146893043;
    CSslContext::SetError(this, 303, 2148074253LL);
    return v28;
  }
  v35 = Size;
  *((_DWORD *)a2 + 1) = v33;
  *(_DWORD *)a2 = 68;
  *((_DWORD *)a2 + 2) = v35;
  memcpy_0(a2 + 12, Src, v35);
  *((_OWORD *)a2 + 3) = *(_OWORD *)(v10 + 40);
  *((_DWORD *)a2 + 16) = *(_DWORD *)(v10 + 56);
  *v43 = 68;
  return 590684;
}

```

## disassembly

```asm
0x180079120  mov     [rsp-8+arg_18], rbx
0x180079125  push    rbp
0x180079126  push    rsi
0x180079127  push    rdi
0x180079128  push    r12
0x18007912a  push    r13
0x18007912c  push    r14
0x18007912e  push    r15
0x180079130  lea     rbp, [rsp-27h]
0x180079135  sub     rsp, 100h
0x18007913c  mov     rax, cs:__security_cookie
0x180079143  xor     rax, rsp
0x180079146  mov     [rbp+57h+var_40], rax
0x18007914a  mov     rax, [rcx+68h]
0x18007914e  xor     r12d, r12d
0x180079151  mov     dword ptr [rbp+57h+Size+4], r12d
0x180079155  mov     rdi, r8
0x180079158  mov     dword ptr [rbp+57h+Size], r12d
0x18007915c  mov     rsi, rdx
0x18007915f  mov     [rbp+57h+var_90], r8
0x180079163  mov     rbx, rcx
0x180079166  mov     rax, [rax+330h]
0x18007916d  mov     [rbp+57h+var_88], rax
0x180079171  mov     rax, [rcx]
0x180079174  mov     [rbp+57h+var_B4], 8004h
0x18007917b  mov     [rbp+57h+var_98], r12
0x18007917f  mov     rax, [rax+108h]
0x180079186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007918b  mov     r13, rax
0x18007918e  mov     [rbp+57h+var_B8], r12d
0x180079192  mov     rcx, [rax+1B0h]
0x180079199  test    rcx, rcx
0x18007919c  jz      short loc_1800791B0
0x18007919e  mov     ecx, [rcx+8]
0x1800791a1  lea     edx, [r12+76h]
0x1800791a6  add     ecx, 2
0x1800791a9  cmp     ecx, edx
0x1800791ab  cmova   edx, ecx
0x1800791ae  jmp     short loc_1800791CA
0x1800791b0  mov     rax, [rax+20h]
0x1800791b4  test    rax, rax
0x1800791b7  jz      short loc_1800791C5
0x1800791b9  mov     rax, [rax+18h]
0x1800791bd  mov     edx, [rax+78h]
0x1800791c0  add     edx, 34h ; '4'
0x1800791c3  jmp     short loc_1800791CA
0x1800791c5  mov     edx, 44h ; 'D'
0x1800791ca  test    dword ptr [rbx+58h], 80800h
0x1800791d1  lea     r14d, [rdx+2]
0x1800791d5  cmovz   r14d, edx
0x1800791d9  test    rsi, rsi
0x1800791dc  jnz     short loc_1800791E8
0x1800791de  mov     [rdi], r14d
0x1800791e1  xor     eax, eax
0x1800791e3  jmp     loc_18007966A
0x1800791e8  mov     r15d, r12d
0x1800791eb  cmp     [rbx+0A60h], r12
0x1800791f2  jz      short loc_18007925E
0x1800791f4  cmp     [rbx+0AC0h], r12b
0x1800791fb  jnz     short loc_18007925E
0x1800791fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180079204  lea     r12, WPP_GLOBAL_Control
0x18007920b  cmp     rcx, r12
0x18007920e  jz      short loc_18007922B
0x180079210  test    byte ptr [rcx+1Ch], 4
0x180079214  jz      short loc_18007922B
0x180079216  mov     rcx, [rcx+10h]
0x18007921a  lea     r8, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids
0x180079221  mov     edx, 2Fh ; '/'
0x180079226  call    WPP_SF_
0x18007922b  mov     ecx, [rbx+0A68h]
0x180079231  lea     eax, [r14-2]
0x180079235  mov     dword ptr [rbp+57h+Size+4], eax
0x180079238  cmp     ecx, eax
0x18007923a  ja      loc_1800794D3
0x180079240  mov     rdx, [rbx+0A60h]; Src
0x180079247  mov     r8d, ecx; Size
0x18007924a  lea     rcx, [rsi+2]; void *
0x18007924e  call    memcpy_0
0x180079253  mov     edx, [rbx+0A68h]
0x180079259  jmp     loc_1800795C5
0x18007925e  mov     ecx, [r13+84h]
0x180079265  mov     edi, 24h ; '$'
0x18007926a  mov     [rbp+57h+var_A0], ecx
0x18007926d  sub     ecx, 1
0x180079270  jz      short loc_18007929F
0x180079272  sub     ecx, 1
0x180079275  jz      short loc_180079296
0x180079277  cmp     ecx, 1
0x18007927a  jz      short loc_180079286
0x18007927c  mov     eax, 80090331h
0x180079281  jmp     loc_18007966A
0x180079286  lea     rax, aEcdsa; "ECDSA"
0x18007928d  mov     dword ptr [rbp+57h+Size], 14h
0x180079294  jmp     short loc_1800792B7
0x180079296  lea     rax, aDsa; "DSA"
0x18007929d  jmp     short loc_18007928D
0x18007929f  lea     rax, aRsa; "RSA"
0x1800792a6  mov     [rbp+57h+var_B4], 8008h
0x1800792ad  mov     dword ptr [rbp+57h+Size], edi
0x1800792b0  mov     [rbp+57h+var_B8], 2
0x1800792b7  mov     [rbp+57h+var_A8], rax
0x1800792bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800792c2  lea     r12, WPP_GLOBAL_Control
0x1800792c9  cmp     rcx, r12
0x1800792cc  jz      short loc_1800792EC
0x1800792ce  test    byte ptr [rcx+1Ch], 4
0x1800792d2  jz      short loc_1800792EC
0x1800792d4  mov     rcx, [rcx+10h]
0x1800792d8  lea     r8, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids
0x1800792df  mov     edx, 30h ; '0'
0x1800792e4  mov     r9, rax
0x1800792e7  call    WPP_SF_S
0x1800792ec  test    dword ptr [rbx+58h], 80800h
0x1800792f3  jz      loc_180079417
0x1800792f9  xor     eax, eax
0x1800792fb  lea     r15, [rbx+8B6h]
0x180079302  mov     [rbp+57h+var_B0], eax
0x180079305  cmp     [r13+70h], rax
0x180079309  jz      short loc_18007934C
0x18007930b  mov     rcx, rdi; Size
0x18007930e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079313  xor     ecx, ecx
0x180079315  mov     rdi, rax
0x180079318  test    rax, rax
0x18007931b  jz      short loc_180079331
0x18007931d  xorps   xmm0, xmm0
0x180079320  movups  xmmword ptr [rax+2], xmm0
0x180079324  movups  xmmword ptr [rax+12h], xmm0
0x180079328  mov     [rax], cx
0x18007932b  mov     [rax+22h], cx
0x18007932f  jmp     short loc_180079334
0x180079331  mov     rdi, rcx
0x180079334  mov     rcx, rdi; this
0x180079337  call    ?SetDefaultClientHello@CTlsSignatureSuiteList@@QEAAXXZ; CTlsSignatureSuiteList::SetDefaultClientHello(void)
0x18007933c  mov     r8d, [rbx+58h]; unsigned int
0x180079340  mov     rdx, r15; struct CTlsSignatureSuiteList *
0x180079343  call    ?Restrict@CTlsSignatureSuiteList@@QEAAEPEBV1@K@Z; CTlsSignatureSuiteList::Restrict(CTlsSignatureSuiteList const *,ulong)
0x180079348  xor     eax, eax
0x18007934a  jmp     short loc_18007934F
0x18007934c  mov     rdi, r15
0x18007934f  mov     r8d, [r13+1ACh]; unsigned int
0x180079356  mov     rcx, rdi; this
0x180079359  mov     edx, [rbp+57h+var_A0]; enum _eTlsSignatureAlgorithm
0x18007935c  mov     r9d, [rbx+58h]; unsigned int
0x180079360  mov     dword ptr [rsp+130h+var_110], eax; unsigned int
0x180079364  call    ?GetMinimumCodePointToSign@CTlsSignatureSuiteList@@QEBAGW4_eTlsSignatureAlgorithm@@KKK@Z; CTlsSignatureSuiteList::GetMinimumCodePointToSign(_eTlsSignatureAlgorithm,ulong,ulong,ulong)
0x180079369  movzx   r15d, ax
0x18007936d  xor     eax, eax
0x18007936f  ror     r15w, 8
0x180079374  cmp     [r13+70h], rax
0x180079378  jz      short loc_180079387
0x18007937a  test    rdi, rdi
0x18007937d  jz      short loc_180079387
0x18007937f  mov     rcx, rdi; Block
0x180079382  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180079387  test    r15w, r15w
0x18007938b  jnz     short loc_1800793A8
0x18007938d  mov     r9b, 28h ; '('
0x180079390  mov     edx, 130h
0x180079395  mov     r8d, 80090331h
0x18007939b  mov     rcx, rbx
0x18007939e  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x1800793a3  jmp     loc_18007927C
0x1800793a8  lea     rax, [rbp+57h+var_B8]
0x1800793ac  xor     edx, edx; enum _eTlsSignatureAlgorithm *
0x1800793ae  mov     [rsp+130h+lpString], rax; unsigned int *
0x1800793b3  lea     r9, [rbp+57h+var_B4]; unsigned int *
0x1800793b7  lea     rax, [rbp+57h+Size]
0x1800793bb  movzx   ecx, r15w; unsigned __int16
0x1800793bf  mov     [rsp+130h+String1], rax; unsigned int *
0x1800793c4  lea     r8, [rbp+57h+var_B0]; enum _eTlsHashAlgorithm *
0x1800793c8  lea     rax, [rbp+57h+var_98]
0x1800793cc  mov     [rsp+130h+var_110], rax; unsigned __int16 **
0x1800793d1  call    ?GetSignatureSuiteInfoByCodePoint@@YAXGPEAW4_eTlsSignatureAlgorithm@@PEAW4_eTlsHashAlgorithm@@PEAIPEAPEBGPEAK4@Z; GetSignatureSuiteInfoByCodePoint(ushort,_eTlsSignatureAlgorithm *,_eTlsHashAlgorithm *,uint *,ushort const * *,ulong *,ulong *)
0x1800793d6  mov     edx, [rbp+57h+var_B0]; enum _eTlsHashAlgorithm
0x1800793d9  mov     rcx, rbx; this
0x1800793dc  call    ?FindTlsClientAuthHandshakeHash@CSsl3TlsContext@@IEAA_KW4_eTlsHashAlgorithm@@@Z; CSsl3TlsContext::FindTlsClientAuthHandshakeHash(_eTlsHashAlgorithm)
0x1800793e1  mov     rdi, rax
0x1800793e4  test    rax, rax
0x1800793e7  jz      short loc_1800793FB
0x1800793e9  cmp     r14d, 2
0x1800793ed  jb      short loc_1800793FB
0x1800793ef  mov     [rsi], r15w
0x1800793f3  mov     r15d, 2
0x1800793f9  jmp     short loc_18007941E
0x1800793fb  mov     edi, 54Fh
0x180079400  mov     edx, 130h
0x180079405  mov     r8d, edi
0x180079408  mov     r9b, 50h ; 'P'
0x18007940b  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180079410  mov     eax, edi
0x180079412  jmp     loc_18007966A
0x180079417  mov     rdi, [rbx+908h]
0x18007941e  mov     rax, [rbx+0BE0h]
0x180079425  mov     dl, 1; Wait
0x180079427  mov     rcx, [rax+28h]
0x18007942b  add     rcx, 50h ; 'P'; Resource
0x18007942f  call    cs:__imp_RtlAcquireResourceShared
0x180079435  mov     rax, [rbx+0BE0h]
0x18007943c  xor     r8d, r8d
0x18007943f  mov     edx, dword ptr [rbp+57h+Size]
0x180079442  mov     r10, [rax+20h]
0x180079446  mov     rax, [rbx+8]
0x18007944a  test    rax, rax
0x18007944d  jz      short loc_180079454
0x18007944f  mov     rcx, [rax]
0x180079452  jmp     short loc_180079457
0x180079454  mov     rcx, r8
0x180079457  mov     r9, [rbp+57h+var_A8]
0x18007945b  lea     rax, [rbp+57h+Size]
0x18007945f  mov     dword ptr [rsp+130h+pbHashValue], r8d
0x180079464  mov     r8, rdi
0x180079467  mov     [rsp+130h+lpString], rax
0x18007946c  lea     rax, [rbp+57h+Src]
0x180079470  mov     dword ptr [rsp+130h+String1], edx
0x180079474  mov     rdx, r10
0x180079477  mov     [rsp+130h+var_110], rax
0x18007947c  call    cs:__imp_SslComputeClientAuthHash
0x180079482  mov     rcx, [rbx+0BE0h]
0x180079489  mov     edi, eax
0x18007948b  mov     rcx, [rcx+28h]
0x18007948f  add     rcx, 50h ; 'P'; Resource
0x180079493  call    cs:__imp_RtlReleaseResource
0x180079499  test    edi, edi
0x18007949b  jz      short loc_1800794AA
0x18007949d  mov     edx, 12Ch
0x1800794a2  mov     rcx, rbx
0x1800794a5  jmp     loc_180079405
0x1800794aa  sub     r14d, r15d
0x1800794ad  mov     edi, r15d
0x1800794b0  add     rdi, 2
0x1800794b4  sub     r14d, 2
0x1800794b8  add     rdi, rsi
0x1800794bb  mov     dword ptr [rbp+57h+Size+4], r14d
0x1800794bf  cmp     byte ptr [rbx+0AC0h], 0
0x1800794c6  jz      short loc_1800794F1
0x1800794c8  mov     eax, [rbx+0A68h]
0x1800794ce  cmp     eax, r14d
0x1800794d1  jbe     short loc_1800794DF
0x1800794d3  mov     edi, 80090326h
0x1800794d8  mov     edx, 12Eh
0x1800794dd  jmp     short loc_1800794A2
0x1800794df  mov     rdx, [rbx+0A60h]; Src
0x1800794e6  mov     r8, rax; Size
0x1800794e9  mov     rcx, rdi; void *
0x1800794ec  call    memcpy_0
0x1800794f1  mov     eax, [rbx+0A68h]
0x1800794f7  mov     rdx, r13; struct CSslCredential *
0x1800794fa  mov     ecx, dword ptr [rbp+57h+Size]
0x1800794fd  mov     r14d, [rbp+57h+var_B4]
0x180079501  mov     r9d, r14d; unsigned int
0x180079504  mov     r8, [rbp+57h+var_88]; void *
0x180079508  mov     [rsp+130h+var_D0], eax; unsigned int
0x18007950c  mov     al, [rbx+0AC0h]
0x180079512  mov     [rsp+130h+var_D8], al; char
0x180079516  lea     rax, [rbp+57h+Size+4]
0x18007951a  mov     [rsp+130h+pcbEncoded], rax; pcbEncoded
0x18007951f  lea     rax, [rbp+57h+Src]
0x180079523  mov     [rsp+130h+pbEncoded], rdi; pbEncoded
0x180079528  mov     [rsp+130h+cbHashValue], ecx; cbHashValue
0x18007952c  mov     rcx, rbx; struct CSslContext *
0x18007952f  mov     [rsp+130h+pbHashValue], rax; pbHashValue
0x180079534  mov     rax, [rbp+57h+var_98]
0x180079538  mov     [rsp+130h+lpString], rax; lpString
0x18007953d  mov     rax, [rbp+57h+var_A8]
0x180079541  mov     [rsp+130h+String1], rax; String1
0x180079546  mov     eax, [rbp+57h+var_B8]
0x180079549  mov     dword ptr [rsp+130h+var_110], eax; unsigned int
0x18007954d  call    ?SignHashUsingCred@@YAKPEAVCSslContext@@PEAVCSslCredential@@PEAXIKPEBG3PEAEK4PEAKEK@Z; SignHashUsingCred(CSslContext *,CSslCredential *,void *,uint,ulong,ushort const *,ushort const *,uchar *,ulong,uchar *,ulong *,uchar,ulong)
0x180079552  mov     edi, eax
0x180079554  cmp     eax, 0C0000290h
0x180079559  jz      loc_1800795E4
0x18007955f  cmp     eax, 80090022h
0x180079564  jz      short loc_1800795E4
0x180079566  mov     r14d, 90312h
0x18007956c  cmp     eax, r14d
0x18007956f  jnz     short loc_1800795B0
0x180079571  cmp     byte ptr [rbx+7C2h], 0
0x180079578  jz      short loc_1800795B4
0x18007957a  mov     rcx, cs:WPP_GLOBAL_Control
0x180079581  cmp     rcx, r12
0x180079584  jz      short loc_1800795A1
0x180079586  test    byte ptr [rcx+1Ch], 4
0x18007958a  jz      short loc_1800795A1
0x18007958c  mov     rcx, [rcx+10h]
0x180079590  lea     r8, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids
0x180079597  mov     edx, 32h ; '2'
0x18007959c  call    WPP_SF_
0x1800795a1  mov     dword ptr [rbx+5Ch], 4Dh ; 'M'
0x1800795a8  mov     eax, r14d
0x1800795ab  jmp     loc_18007966A
0x1800795b0  test    edi, edi
0x1800795b2  jz      short loc_1800795BE
0x1800795b4  mov     edx, 12Dh
0x1800795b9  jmp     loc_1800794A2
0x1800795be  mov     edx, dword ptr [rbp+57h+Size+4]
0x1800795c1  mov     rdi, [rbp+57h+var_90]
0x1800795c5  mov     eax, r15d
0x1800795c8  mov     ecx, edx
  ... truncated ...
```
