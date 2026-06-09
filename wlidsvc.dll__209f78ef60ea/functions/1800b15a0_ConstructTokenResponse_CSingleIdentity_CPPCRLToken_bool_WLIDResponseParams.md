# ConstructTokenResponse(CSingleIdentity *,CPPCRLToken &,bool,_WLIDResponseParams &)

- ea: `0x1800b15a0`
- end: `0x1800b1a7b`
- name: `?ConstructTokenResponse@@YAJPEAVCSingleIdentity@@AEAVCPPCRLToken@@_NAEAU_WLIDResponseParams@@@Z`
- size: `1243`
- prototype: `__int64 __fastcall(struct CSingleIdentity *, struct CPPCRLToken *, bool, struct _WLIDResponseParams *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009fdd0`

## callees

- `0x18000c050`
- `0x18000cf88`
- `0x18000ed04`
- `0x1800151c4`
- `0x180018f80`
- `0x1800191c0`
- `0x1800277c0`
- `0x180029d54`
- `0x180030120`
- `0x180037288`
- `0x180037e48`
- `0x18004d6e4`
- `0x18004edf4`
- `0x180051784`
- `0x180079554`
- `0x180082230`
- `0x1800b15a0`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b167a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b1773`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b17e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b1832`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b188d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b194b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b19a4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b167a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b1773`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b17e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b1832`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b188d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b194b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b19a4`

## string_xrefs

- `0x1800b1659`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800b1717`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800b1652`: `ConstructTokenResponse`
- `0x1800b1710`: `ConstructTokenResponse`
- `0x1800b16ac`: `hr = StringCchCopyW(response.wszAuthChallenge, wszFlowUrl.GetLength() + 1, wszFlowUrl)`
- `0x1800b16fb`: `hr = CAuthInfo::EncryptStringInSystemContext(&executionContext, token.GetToken(), tokenBlob)`
- `0x1800b179f`: `hr = StringCchCopyW(response.wszToken, tokenBlob.GetLength() + 1, tokenBlob)`
- `0x1800b180d`: `hr = SafeCopyMemory(response.pbSessionKey, bpSessionKey.GetLength(), bpSessionKey.GetBuffer(), bpSessionKey.GetLength())`
- `0x1800b1860`: `hr = StringCchCopyW(response.wszCID, wstrCID.GetLength() + 1, wstrCID)`
- `0x1800b18fc`: `hr = StringCchCopyW(response.wstrKeyPair, token.GetKeyPair().GetLength() + 1, token.GetKeyPair())`
- `0x1800b1923`: `hr = token.GetAuthzToken(pszAuthzToken)`
- `0x1800b1977`: `hr = StringCchCopyW(response.wszAuthorizationToken, pszAuthzToken.GetLength() + 1, pszAuthzToken)`
- `0x1800b1a13`: `hr = StringCchCopyW(response.wstrTokenURI, token.GetTokenURI().GetLength() + 1, token.GetTokenURI())`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ConstructTokenResponse(
        struct CSingleIdentity *a1,
        struct CPPCRLToken *a2,
        char a3,
        struct _WLIDResponseParams *a4)
{
  int AuthzToken; // ebx
  const char *v9; // rax
  unsigned int v10; // r8d
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v12; // rcx
  _QWORD *Token; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // rbx
  unsigned __int16 *v16; // rcx
  int v17; // r14d
  unsigned int v18; // ebx
  void *v19; // rax
  unsigned __int16 *v20; // rcx
  _QWORD *KeyPair; // rax
  const unsigned __int16 *v22; // rbx
  _QWORD *v23; // rax
  unsigned __int16 *v24; // rbx
  int v25; // eax
  unsigned __int16 *v26; // rcx
  _QWORD *TokenURI; // rax
  const unsigned __int16 *v28; // rbx
  _QWORD *v29; // rax
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v33; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  int v36; // [rsp+58h] [rbp-A8h]
  _BYTE v37[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v38; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 *v39; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 *v40; // [rsp+188h] [rbp+88h] BYREF

  v35 = 0;
  LODWORD(Size) = 0;
  v36 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  *(_DWORD *)a4 = *((_DWORD *)a2 + 24);
  *((_DWORD *)a4 + 1) = *((_DWORD *)a2 + 25);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v33, (char *)a2 + 104);
  AuthzToken = (*(__int64 (__fastcall **)(struct CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)a1 + 64LL))(
                 a1,
                 L"CID",
                 &v39);
  if ( AuthzToken >= 0 )
  {
    v11 = v33;
    v12 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v33 - 4) + 1));
    *((_QWORD *)a4 + 7) = v12;
    if ( v12 )
    {
      AuthzToken = StringCchCopyW(v12, *((_DWORD *)v11 - 4) + 1, v11);
      if ( AuthzToken < 0 )
      {
        v9 = "hr = StringCchCopyW(response.wszAuthChallenge, wszFlowUrl.GetLength() + 1, wszFlowUrl)";
        v10 = 8121;
        goto LABEL_3;
      }
      if ( a3 == 1 )
      {
        ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v37);
        Token = (_QWORD *)CPPCRLToken::GetToken(a2, &v31);
        AuthzToken = CAuthInfo::EncryptStringInSystemContext(v37, *Token, &v38);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
        if ( AuthzToken < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "ConstructTokenResponse",
            0x1FBEu,
            AuthzToken,
            "hr = CAuthInfo::EncryptStringInSystemContext(&executionContext, token.GetToken(), tokenBlob)");
          ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v37);
          goto LABEL_35;
        }
        ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v37);
      }
      else
      {
        v14 = CPPCRLToken::GetToken(a2, &v31);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&v38, v14);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
      }
      v15 = v38;
      v16 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v38 - 4) + 1));
      *((_QWORD *)a4 + 5) = v16;
      if ( v16 )
      {
        AuthzToken = StringCchCopyW(v16, *((_DWORD *)v15 - 4) + 1, v15);
        if ( AuthzToken < 0 )
        {
          v9 = "hr = StringCchCopyW(response.wszToken, tokenBlob.GetLength() + 1, tokenBlob)";
          v10 = 8135;
          goto LABEL_3;
        }
        *((_DWORD *)a4 + 8) = GetTokenType(*((unsigned int *)a2 + 6));
        CBytePtr::Attach((CBytePtr *)&Size, *((unsigned __int8 **)a2 + 18), *((_DWORD *)a2 + 34), 0);
        v17 = Size;
        v18 = Size;
        v19 = malloc((unsigned int)Size);
        *((_QWORD *)a4 + 2) = v19;
        if ( v19 )
        {
          AuthzToken = SafeCopyMemory(v19, v18, v35, v18);
          if ( AuthzToken < 0 )
          {
            v9 = "hr = SafeCopyMemory(response.pbSessionKey, bpSessionKey.GetLength(), bpSessionKey.GetBuffer(), bpSessio"
                 "nKey.GetLength())";
            v10 = 8142;
            goto LABEL_3;
          }
          *((_DWORD *)a4 + 2) = v17;
          v20 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v39 - 4) + 1));
          *((_QWORD *)a4 + 3) = v20;
          if ( v20 )
          {
            AuthzToken = StringCchCopyW(v20, *((_DWORD *)v39 - 4) + 1, v39);
            if ( AuthzToken < 0 )
            {
              v9 = "hr = StringCchCopyW(response.wszCID, wstrCID.GetLength() + 1, wstrCID)";
              v10 = 8147;
              goto LABEL_3;
            }
            KeyPair = (_QWORD *)CPPCRLToken::GetKeyPair(a2, &v31);
            *((_QWORD *)a4 + 11) = malloc(2LL * (*(_DWORD *)(*KeyPair - 16LL) + 1));
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
            if ( *((_QWORD *)a4 + 11) )
            {
              v22 = *(const unsigned __int16 **)CPPCRLToken::GetKeyPair(a2, &v32);
              v23 = (_QWORD *)CPPCRLToken::GetKeyPair(a2, &v31);
              AuthzToken = StringCchCopyW(*((unsigned __int16 **)a4 + 11), *(_DWORD *)(*v23 - 16LL) + 1, v22);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
              if ( AuthzToken < 0 )
              {
                v9 = "hr = StringCchCopyW(response.wstrKeyPair, token.GetKeyPair().GetLength() + 1, token.GetKeyPair())";
                v10 = 8151;
                goto LABEL_3;
              }
              AuthzToken = CPPCRLToken::GetAuthzToken(a2, &v40);
              if ( AuthzToken < 0 )
              {
                v9 = "hr = token.GetAuthzToken(pszAuthzToken)";
                v10 = 8153;
                goto LABEL_3;
              }
              v24 = v40;
              v25 = *((_DWORD *)v40 - 4);
              if ( v25 )
              {
                v26 = (unsigned __int16 *)malloc(2LL * (v25 + 1));
                *((_QWORD *)a4 + 6) = v26;
                if ( !v26 )
                  goto LABEL_5;
                AuthzToken = StringCchCopyW(v26, *((_DWORD *)v24 - 4) + 1, v24);
                if ( AuthzToken < 0 )
                {
                  v9 = "hr = StringCchCopyW(response.wszAuthorizationToken, pszAuthzToken.GetLength() + 1, pszAuthzToken)";
                  v10 = 8159;
                  goto LABEL_3;
                }
              }
              TokenURI = (_QWORD *)CPPCRLToken::GetTokenURI(a2, &v32);
              *((_QWORD *)a4 + 10) = malloc(2LL * (*(_DWORD *)(*TokenURI - 16LL) + 1));
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
              if ( *((_QWORD *)a4 + 10) )
              {
                v28 = *(const unsigned __int16 **)CPPCRLToken::GetTokenURI(a2, &v31);
                v29 = (_QWORD *)CPPCRLToken::GetTokenURI(a2, &v32);
                AuthzToken = StringCchCopyW(*((unsigned __int16 **)a4 + 10), *(_DWORD *)(*v29 - 16LL) + 1, v28);
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
                if ( AuthzToken >= 0 )
                {
                  *((_QWORD *)a4 + 12) = *((_QWORD *)a2 + 4);
                  *((_QWORD *)a4 + 13) = *((_QWORD *)a2 + 7);
                  goto LABEL_35;
                }
                v9 = "hr = StringCchCopyW(response.wstrTokenURI, token.GetTokenURI().GetLength() + 1, token.GetTokenURI())";
                v10 = 8164;
                goto LABEL_3;
              }
            }
          }
        }
      }
    }
LABEL_5:
    AuthzToken = -2147024882;
    goto LABEL_35;
  }
  v9 = "hr = pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_CID, wstrCID)";
  v10 = 8117;
LABEL_3:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "ConstructTokenResponse",
    v10,
    AuthzToken,
    v9);
LABEL_35:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  CBytePtr::Empty((CBytePtr *)&Size);
  return (unsigned int)AuthzToken;
}

```

## disassembly

```asm
0x1800b15a0  push    rbp
0x1800b15a2  push    rbx
0x1800b15a3  push    rsi
0x1800b15a4  push    rdi
0x1800b15a5  push    r14
0x1800b15a7  lea     rbp, [rsp-40h]
0x1800b15ac  sub     rsp, 140h
0x1800b15b3  mov     rdi, r9
0x1800b15b6  mov     r14b, r8b
0x1800b15b9  mov     rsi, rdx
0x1800b15bc  mov     rbx, rcx
0x1800b15bf  mov     [rsp+160h+var_110], 0
0x1800b15c8  mov     dword ptr [rsp+160h+Size], 0
0x1800b15d0  mov     [rsp+160h+var_108], 0
0x1800b15d8  lea     rcx, [rsp+160h+var_120]
0x1800b15dd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b15e2  nop
0x1800b15e3  lea     rcx, [rbp+60h+arg_8]
0x1800b15e7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b15ec  nop
0x1800b15ed  lea     rcx, [rbp+60h+arg_0]
0x1800b15f1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b15f6  nop
0x1800b15f7  lea     rcx, [rbp+60h+arg_18]
0x1800b15fe  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b1603  nop
0x1800b1604  mov     eax, [rsi+60h]
0x1800b1607  mov     [rdi], eax
0x1800b1609  mov     eax, [rsi+64h]
0x1800b160c  mov     [rdi+4], eax
0x1800b160f  lea     rdx, [rsi+68h]
0x1800b1613  lea     rcx, [rsp+160h+var_120]
0x1800b1618  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800b161d  mov     rax, [rbx]
0x1800b1620  lea     r8, [rbp+60h+arg_8]
0x1800b1624  lea     rdx, aCid; "CID"
0x1800b162b  mov     rcx, rbx
0x1800b162e  mov     rax, [rax+40h]
0x1800b1632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1637  mov     ebx, eax
0x1800b1639  test    eax, eax
0x1800b163b  jns     short loc_1800B166A
0x1800b163d  lea     rax, aHrPidentityGet_11; "hr = pIdentity->GetCredProperty(PPCRL_C"...
0x1800b1644  mov     r8d, 1FB5h; unsigned int
0x1800b164a  mov     [rsp+160h+var_140], rax; char *
0x1800b164f  mov     r9d, ebx; int
0x1800b1652  lea     rdx, aConstructtoken; "ConstructTokenResponse"
0x1800b1659  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800b1660  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b1665  jmp     loc_1800B1A35
0x1800b166a  mov     rbx, [rsp+160h+var_120]
0x1800b166f  mov     eax, [rbx-10h]
0x1800b1672  inc     eax
0x1800b1674  movsxd  rcx, eax
0x1800b1677  add     rcx, rcx; Size
0x1800b167a  call    cs:__imp_malloc
0x1800b1680  mov     rcx, rax; unsigned __int16 *
0x1800b1683  mov     [rdi+38h], rax
0x1800b1687  test    rax, rax
0x1800b168a  jnz     short loc_1800B1696
0x1800b168c  mov     ebx, 8007000Eh
0x1800b1691  jmp     loc_1800B1A35
0x1800b1696  mov     eax, [rbx-10h]
0x1800b1699  inc     eax
0x1800b169b  movsxd  rdx, eax; unsigned __int64
0x1800b169e  mov     r8, rbx; unsigned __int16 *
0x1800b16a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b16a6  mov     ebx, eax
0x1800b16a8  test    eax, eax
0x1800b16aa  jns     short loc_1800B16BB
0x1800b16ac  lea     rax, aHrStringcchcop_1; "hr = StringCchCopyW(response.wszAuthCha"...
0x1800b16b3  mov     r8d, 1FB9h
0x1800b16b9  jmp     short loc_1800B164A
0x1800b16bb  cmp     r14b, 1
0x1800b16bf  jnz     short loc_1800B173F
0x1800b16c1  lea     rcx, [rsp+160h+var_100]; this
0x1800b16c6  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800b16cb  nop
0x1800b16cc  lea     rdx, [rsp+160h+var_130]
0x1800b16d1  mov     rcx, rsi
0x1800b16d4  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800b16d9  nop
0x1800b16da  lea     r8, [rbp+60h+arg_0]
0x1800b16de  mov     rdx, [rax]
0x1800b16e1  lea     rcx, [rsp+160h+var_100]
0x1800b16e6  call    ?EncryptStringInSystemContext@CAuthInfo@@SAJPEAVIServiceExecutionContext@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAuthInfo::EncryptStringInSystemContext(IServiceExecutionContext *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800b16eb  mov     ebx, eax
0x1800b16ed  lea     rcx, [rsp+160h+var_130]
0x1800b16f2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b16f7  test    ebx, ebx
0x1800b16f9  jns     short loc_1800B1733
0x1800b16fb  lea     rax, aHrCauthinfoEnc_0; "hr = CAuthInfo::EncryptStringInSystemCo"...
0x1800b1702  mov     [rsp+160h+var_140], rax; char *
0x1800b1707  mov     r9d, ebx; int
0x1800b170a  mov     r8d, 1FBEh; unsigned int
0x1800b1710  lea     rdx, aConstructtoken; "ConstructTokenResponse"
0x1800b1717  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800b171e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b1723  nop
0x1800b1724  lea     rcx, [rsp+160h+var_100]; this
0x1800b1729  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800b172e  jmp     loc_1800B1A35
0x1800b1733  lea     rcx, [rsp+160h+var_100]; this
0x1800b1738  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800b173d  jmp     short loc_1800B1764
0x1800b173f  lea     rdx, [rsp+160h+var_130]
0x1800b1744  mov     rcx, rsi
0x1800b1747  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800b174c  nop
0x1800b174d  mov     rdx, rax
0x1800b1750  lea     rcx, [rbp+60h+arg_0]
0x1800b1754  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800b1759  nop
0x1800b175a  lea     rcx, [rsp+160h+var_130]
0x1800b175f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b1764  mov     rbx, [rbp+60h+arg_0]
0x1800b1768  mov     eax, [rbx-10h]
0x1800b176b  inc     eax
0x1800b176d  movsxd  rcx, eax
0x1800b1770  add     rcx, rcx; Size
0x1800b1773  call    cs:__imp_malloc
0x1800b1779  mov     rcx, rax; unsigned __int16 *
0x1800b177c  mov     [rdi+28h], rax
0x1800b1780  test    rax, rax
0x1800b1783  jz      loc_1800B168C
0x1800b1789  mov     eax, [rbx-10h]
0x1800b178c  inc     eax
0x1800b178e  movsxd  rdx, eax; unsigned __int64
0x1800b1791  mov     r8, rbx; unsigned __int16 *
0x1800b1794  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b1799  mov     ebx, eax
0x1800b179b  test    eax, eax
0x1800b179d  jns     short loc_1800B17B1
0x1800b179f  lea     rax, aHrStringcchcop_25; "hr = StringCchCopyW(response.wszToken, "...
0x1800b17a6  mov     r8d, 1FC7h
0x1800b17ac  jmp     loc_1800B164A
0x1800b17b1  mov     ecx, [rsi+18h]
0x1800b17b4  call    ?GetTokenType@@YAKW4TokenFormat@@@Z; GetTokenType(TokenFormat)
0x1800b17b9  mov     [rdi+20h], eax
0x1800b17bc  xor     r9d, r9d; bool
0x1800b17bf  mov     r8d, [rsi+88h]; unsigned int
0x1800b17c6  mov     rdx, [rsi+90h]; unsigned __int8 *
0x1800b17cd  lea     rcx, [rsp+160h+Size]; this
0x1800b17d2  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800b17d7  mov     r14d, dword ptr [rsp+160h+Size]
0x1800b17dc  mov     ebx, r14d
0x1800b17df  mov     ecx, r14d; Size
0x1800b17e2  call    cs:__imp_malloc
0x1800b17e8  mov     [rdi+10h], rax
0x1800b17ec  test    rax, rax
0x1800b17ef  jz      loc_1800B168C
0x1800b17f5  mov     r9d, ebx
0x1800b17f8  mov     r8, [rsp+160h+var_110]
0x1800b17fd  mov     edx, ebx
0x1800b17ff  mov     rcx, rax
0x1800b1802  call    SafeCopyMemory
0x1800b1807  mov     ebx, eax
0x1800b1809  test    eax, eax
0x1800b180b  jns     short loc_1800B181F
0x1800b180d  lea     rax, aHrSafecopymemo_16; "hr = SafeCopyMemory(response.pbSessionK"...
0x1800b1814  mov     r8d, 1FCEh
0x1800b181a  jmp     loc_1800B164A
0x1800b181f  mov     [rdi+8], r14d
0x1800b1823  mov     rax, [rbp+60h+arg_8]
0x1800b1827  mov     ecx, [rax-10h]
0x1800b182a  inc     ecx
0x1800b182c  movsxd  rcx, ecx
0x1800b182f  add     rcx, rcx; Size
0x1800b1832  call    cs:__imp_malloc
0x1800b1838  mov     rcx, rax; unsigned __int16 *
0x1800b183b  mov     [rdi+18h], rax
0x1800b183f  test    rax, rax
0x1800b1842  jz      loc_1800B168C
0x1800b1848  mov     r8, [rbp+60h+arg_8]; unsigned __int16 *
0x1800b184c  mov     eax, [r8-10h]
0x1800b1850  inc     eax
0x1800b1852  movsxd  rdx, eax; unsigned __int64
0x1800b1855  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b185a  mov     ebx, eax
0x1800b185c  test    eax, eax
0x1800b185e  jns     short loc_1800B1872
0x1800b1860  lea     rax, aHrStringcchcop_14; "hr = StringCchCopyW(response.wszCID, ws"...
0x1800b1867  mov     r8d, 1FD3h
0x1800b186d  jmp     loc_1800B164A
0x1800b1872  lea     rdx, [rsp+160h+var_130]
0x1800b1877  mov     rcx, rsi
0x1800b187a  call    ?GetKeyPair@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetKeyPair(void)
0x1800b187f  mov     rax, [rax]
0x1800b1882  mov     ecx, [rax-10h]
0x1800b1885  inc     ecx
0x1800b1887  movsxd  rcx, ecx
0x1800b188a  add     rcx, rcx; Size
0x1800b188d  call    cs:__imp_malloc
0x1800b1893  mov     [rdi+58h], rax
0x1800b1897  lea     rcx, [rsp+160h+var_130]
0x1800b189c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b18a1  cmp     qword ptr [rdi+58h], 0
0x1800b18a6  jz      loc_1800B168C
0x1800b18ac  lea     rdx, [rsp+160h+var_128]
0x1800b18b1  mov     rcx, rsi
0x1800b18b4  call    ?GetKeyPair@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetKeyPair(void)
0x1800b18b9  nop
0x1800b18ba  mov     rbx, [rax]
0x1800b18bd  lea     rdx, [rsp+160h+var_130]
0x1800b18c2  mov     rcx, rsi
0x1800b18c5  call    ?GetKeyPair@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetKeyPair(void)
0x1800b18ca  mov     rcx, [rax]
0x1800b18cd  mov     eax, [rcx-10h]
0x1800b18d0  inc     eax
0x1800b18d2  movsxd  rdx, eax; unsigned __int64
0x1800b18d5  mov     r8, rbx; unsigned __int16 *
0x1800b18d8  mov     rcx, [rdi+58h]; unsigned __int16 *
0x1800b18dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b18e1  mov     ebx, eax
0x1800b18e3  lea     rcx, [rsp+160h+var_130]
0x1800b18e8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b18ed  nop
0x1800b18ee  lea     rcx, [rsp+160h+var_128]
0x1800b18f3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b18f8  test    ebx, ebx
0x1800b18fa  jns     short loc_1800B190E
0x1800b18fc  lea     rax, aHrStringcchcop_46; "hr = StringCchCopyW(response.wstrKeyPai"...
0x1800b1903  mov     r8d, 1FD7h
0x1800b1909  jmp     loc_1800B164A
0x1800b190e  lea     rdx, [rbp+60h+arg_18]
0x1800b1915  mov     rcx, rsi
0x1800b1918  call    ?GetAuthzToken@CPPCRLToken@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLToken::GetAuthzToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800b191d  mov     ebx, eax
0x1800b191f  test    eax, eax
0x1800b1921  jns     short loc_1800B1935
0x1800b1923  lea     rax, aHrTokenGetauth; "hr = token.GetAuthzToken(pszAuthzToken)"
0x1800b192a  mov     r8d, 1FD9h
0x1800b1930  jmp     loc_1800B164A
0x1800b1935  mov     rbx, [rbp+60h+arg_18]
0x1800b193c  mov     eax, [rbx-10h]
0x1800b193f  test    eax, eax
0x1800b1941  jz      short loc_1800B1989
0x1800b1943  inc     eax
0x1800b1945  movsxd  rcx, eax
0x1800b1948  add     rcx, rcx; Size
0x1800b194b  call    cs:__imp_malloc
0x1800b1951  mov     rcx, rax; unsigned __int16 *
0x1800b1954  mov     [rdi+30h], rax
0x1800b1958  test    rax, rax
0x1800b195b  jz      loc_1800B168C
0x1800b1961  mov     eax, [rbx-10h]
0x1800b1964  inc     eax
0x1800b1966  movsxd  rdx, eax; unsigned __int64
0x1800b1969  mov     r8, rbx; unsigned __int16 *
0x1800b196c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b1971  mov     ebx, eax
0x1800b1973  test    eax, eax
0x1800b1975  jns     short loc_1800B1989
0x1800b1977  lea     rax, aHrStringcchcop_27; "hr = StringCchCopyW(response.wszAuthori"...
0x1800b197e  mov     r8d, 1FDFh
0x1800b1984  jmp     loc_1800B164A
0x1800b1989  lea     rdx, [rsp+160h+var_128]
0x1800b198e  mov     rcx, rsi
0x1800b1991  call    ?GetTokenURI@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetTokenURI(void)
0x1800b1996  mov     rax, [rax]
0x1800b1999  mov     ecx, [rax-10h]
0x1800b199c  inc     ecx
0x1800b199e  movsxd  rcx, ecx
0x1800b19a1  add     rcx, rcx; Size
0x1800b19a4  call    cs:__imp_malloc
0x1800b19aa  mov     [rdi+50h], rax
0x1800b19ae  lea     rcx, [rsp+160h+var_128]
0x1800b19b3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b19b8  cmp     qword ptr [rdi+50h], 0
0x1800b19bd  jz      loc_1800B168C
0x1800b19c3  lea     rdx, [rsp+160h+var_130]
0x1800b19c8  mov     rcx, rsi
0x1800b19cb  call    ?GetTokenURI@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetTokenURI(void)
0x1800b19d0  nop
0x1800b19d1  mov     rbx, [rax]
0x1800b19d4  lea     rdx, [rsp+160h+var_128]
0x1800b19d9  mov     rcx, rsi
0x1800b19dc  call    ?GetTokenURI@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetTokenURI(void)
0x1800b19e1  mov     rcx, [rax]
0x1800b19e4  mov     eax, [rcx-10h]
0x1800b19e7  inc     eax
0x1800b19e9  movsxd  rdx, eax; unsigned __int64
0x1800b19ec  mov     r8, rbx; unsigned __int16 *
0x1800b19ef  mov     rcx, [rdi+50h]; unsigned __int16 *
0x1800b19f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b19f8  mov     ebx, eax
0x1800b19fa  lea     rcx, [rsp+160h+var_128]
0x1800b19ff  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b1a04  nop
0x1800b1a05  lea     rcx, [rsp+160h+var_130]
0x1800b1a0a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b1a0f  test    ebx, ebx
0x1800b1a11  jns     short loc_1800B1A25
0x1800b1a13  lea     rax, aHrStringcchcop_47; "hr = StringCchCopyW(response.wstrTokenU"...
0x1800b1a1a  mov     r8d, 1FE4h
0x1800b1a20  jmp     loc_1800B164A
0x1800b1a25  mov     rax, [rsi+20h]
0x1800b1a29  mov     [rdi+60h], rax
0x1800b1a2d  mov     rax, [rsi+38h]
0x1800b1a31  mov     [rdi+68h], rax
  ... truncated ...
```
