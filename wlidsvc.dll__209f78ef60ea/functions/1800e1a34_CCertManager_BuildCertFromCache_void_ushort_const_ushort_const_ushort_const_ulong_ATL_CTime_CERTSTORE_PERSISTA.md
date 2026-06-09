# CCertManager::BuildCertFromCache(void *,ushort const *,ushort const *,ushort const *,ulong,ATL::CTime,_CERTSTORE_PERSISTANT_LOCATION,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800e1a34`
- end: `0x1800e1d14`
- name: `?BuildCertFromCache@CCertManager@@QEAAJPEAXPEBG11KVCTime@ATL@@W4_CERTSTORE_PERSISTANT_LOCATION@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `736`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, unsigned int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800db798`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180046c18`
- `0x180089f80`
- `0x1800a716c`
- `0x1800af71c`
- `0x1800e1638`
- `0x1800e1a34`
- `0x1800e1d1c`
- `0x1800e314c`
- `0x1800e3780`
- `0x1800e3aac`
- `0x1800e3b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e1c43`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e1c43`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e1bc0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e1bca`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e1bc0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e1bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1c4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1c4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e1be1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e1be1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1bb6`

## string_xrefs

- `0x1800e1a90`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e1cd5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e1a69`: `CCertManager::BuildCertFromCache`
- `0x1800e1ba2`: `CCertManager::BuildCertFromCache`
- `0x1800e1b0e`: `hr = GenerateMapIndex(pIdentity, wszServiceName, wstrMapIndex)`
- `0x1800e1c98`: `wszServiceName != nullptr && *wszServiceName != L'\0'`
- `0x1800e1c80`: `hr = PutCert(pIdentity, wszServiceName, wszCert, ctExpireTime, wstrKeyPair)`
- `0x1800e1b8d`: `hr = pCert->BuildPKCS10Base64FromCache(wszKeypair, dwKeyGenFlags, (eCertStoreLocation == LOCATION_WINDOWS_CREDENTIAL_MANAGER) ? false : true)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCertManager::BuildCertFromCache(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        _WORD *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rbx
  int v15; // r9d
  const char *v16; // rax
  unsigned int v17; // r8d
  int v18; // eax
  CCertObject *v19; // rax
  CCertObject *v20; // rsi
  int v21; // eax
  int v22; // eax
  const char *v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rbx
  unsigned int v26; // edx
  unsigned int v27; // ebx
  char *v29; // [rsp+20h] [rbp-58h]
  char *v30; // [rsp+20h] [rbp-58h]
  __int64 v31; // [rsp+30h] [rbp-48h] BYREF
  CCertObject *v32; // [rsp+38h] [rbp-40h] BYREF
  CCertObject *v33[2]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v34[5]; // [rsp+50h] [rbp-28h] BYREF
  int v35; // [rsp+D8h] [rbp+60h] BYREF

  v35 = 0;
  v32 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  v34[0] = "CCertManager::BuildCertFromCache";
  v34[1] = &v35;
  v34[2] = 0;
  v34[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
    "CCertManager::BuildCertFromCache",
    (const char *)0x22F,
    0,
    (const unsigned __int16 *)v29);
  if ( !a4 || !*a4 )
  {
    v16 = "wszCert != nullptr && *wszCert != L'\\0'";
    v17 = 561;
    goto LABEL_29;
  }
  v14 = a5;
  if ( !a5 || !*a5 )
  {
    v16 = "wszKeypair != nullptr && *wszKeypair != L'\\0'";
    v17 = 562;
LABEL_29:
    v15 = -2147186544;
    goto LABEL_30;
  }
  if ( !a3 || !*a3 )
  {
    v15 = -2147188686;
    v16 = "wszServiceName != nullptr && *wszServiceName != L'\\0'";
    v17 = 563;
    goto LABEL_30;
  }
  if ( !a2 )
  {
    v15 = -2147188704;
    v16 = "pIdentity != nullptr";
    v17 = 564;
LABEL_30:
    v30 = (char *)v16;
    v35 = v15;
    goto LABEL_31;
  }
  v18 = CCertManager::GenerateMapIndex(v13, a2, a3, &v31);
  v35 = v18;
  if ( v18 < 0 )
  {
    v30 = "hr = GenerateMapIndex(pIdentity, wszServiceName, wstrMapIndex)";
    v15 = v18;
    v17 = 566;
LABEL_31:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
      "CCertManager::BuildCertFromCache",
      v17,
      v15,
      v30);
    goto LABEL_32;
  }
  v19 = (CCertObject *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v33[0] = v19;
  if ( v19 )
    v20 = CCertObject::CCertObject(v19);
  else
    v20 = 0;
  v32 = v20;
  if ( !v20 )
  {
    v35 = -2147024882;
    goto LABEL_32;
  }
  v21 = a8;
  *((_DWORD *)v20 + 15) = a8;
  v22 = CCertObject::BuildPKCS10Base64FromCache(v20, v14, a6, v21 != 1);
  v35 = v22;
  if ( v22 < 0 )
  {
    v23 = "hr = pCert->BuildPKCS10Base64FromCache(wszKeypair, dwKeyGenFlags, (eCertStoreLocation == LOCATION_WINDOWS_CRED"
          "ENTIAL_MANAGER) ? false : true)";
    v24 = 575;
LABEL_18:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
      "CCertManager::BuildCertFromCache",
      v24,
      v22,
      v23);
    goto LABEL_32;
  }
  v33[1] = (CCertObject *)a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  ResetEvent(*(HANDLE *)(a1 + 24));
  ResetEvent(*(HANDLE *)(a1 + 16));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  if ( *(int *)(a1 + 12) > 0 )
    WaitForSingleObject(*(HANDLE *)(a1 + 16), 0xFFFFFFFF);
  v33[0] = 0;
  v25 = v31;
  if ( (unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CCertObject *>>::Lookup(
                          a1 + 72,
                          v31,
                          v33) )
  {
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CCertObject *>>::RemoveKey(
      a1 + 72,
      v25);
    if ( v33[0] )
      CCertObject::`scalar deleting destructor'(v33[0], v26);
  }
  v33[0] = v20;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CCertObject *>>::SetAt(
    a1 + 72,
    v25,
    v33);
  v32 = 0;
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 8));
  SetEvent(*(HANDLE *)(a1 + 24));
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v22 = CCertManager::PutCert(a1, a2, (_DWORD)a3, (_DWORD)a4, a7, a9);
  v35 = v22;
  if ( v22 < 0 )
  {
    v23 = "hr = PutCert(pIdentity, wszServiceName, wszCert, ctExpireTime, wstrKeyPair)";
    v24 = 592;
    goto LABEL_18;
  }
LABEL_32:
  v27 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CAutoPtr<CCertObject>::Free(&v32);
  return v27;
}

```

## disassembly

```asm
0x1800e1a34  push    rbp
0x1800e1a36  push    rbx
0x1800e1a37  push    rsi
0x1800e1a38  push    rdi
0x1800e1a39  push    r12
0x1800e1a3b  push    r13
0x1800e1a3d  push    r14
0x1800e1a3f  push    r15
0x1800e1a41  mov     rbp, rsp
0x1800e1a44  sub     rsp, 78h
0x1800e1a48  mov     r13, r9
0x1800e1a4b  mov     r14, r8
0x1800e1a4e  mov     r12, rdx
0x1800e1a51  mov     rdi, rcx
0x1800e1a54  xor     r15d, r15d
0x1800e1a57  mov     [rbp+arg_18], r15d
0x1800e1a5b  mov     [rbp+var_40], r15
0x1800e1a5f  lea     rcx, [rbp+var_48]
0x1800e1a63  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e1a68  nop
0x1800e1a69  lea     rsi, aCcertmanagerBu; "CCertManager::BuildCertFromCache"
0x1800e1a70  mov     [rbp+var_28], rsi
0x1800e1a74  lea     rax, [rbp+arg_18]
0x1800e1a78  mov     [rbp+var_20], rax
0x1800e1a7c  mov     [rbp+var_18], r15
0x1800e1a80  mov     [rbp+var_10], r15
0x1800e1a84  xor     r9d, r9d; unsigned int
0x1800e1a87  mov     r8d, 22Fh; char *
0x1800e1a8d  mov     rdx, rsi; char *
0x1800e1a90  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e1a97  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800e1a9c  nop
0x1800e1a9d  test    r13, r13
0x1800e1aa0  jz      loc_1800E1CB6
0x1800e1aa6  cmp     [r13+0], r15w
0x1800e1aab  jz      loc_1800E1CB6
0x1800e1ab1  mov     rbx, [rbp+arg_20]
0x1800e1ab5  test    rbx, rbx
0x1800e1ab8  jz      loc_1800E1CA7
0x1800e1abe  cmp     [rbx], r15w
0x1800e1ac2  jz      loc_1800E1CA7
0x1800e1ac8  test    r14, r14
0x1800e1acb  jz      loc_1800E1C92
0x1800e1ad1  cmp     [r14], r15w
0x1800e1ad5  jz      loc_1800E1C92
0x1800e1adb  test    r12, r12
0x1800e1ade  jnz     short loc_1800E1AF8
0x1800e1ae0  mov     r9d, 80048020h
0x1800e1ae6  lea     rax, aPidentityNullp; "pIdentity != nullptr"
0x1800e1aed  mov     r8d, 234h
0x1800e1af3  jmp     loc_1800E1CC9
0x1800e1af8  lea     r9, [rbp+var_48]
0x1800e1afc  mov     r8, r14
0x1800e1aff  mov     rdx, r12
0x1800e1b02  call    ?GenerateMapIndex@CCertManager@@AEAAJPEAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CCertManager::GenerateMapIndex(void *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800e1b07  mov     [rbp+arg_18], eax
0x1800e1b0a  test    eax, eax
0x1800e1b0c  jns     short loc_1800E1B28
0x1800e1b0e  lea     rcx, aHrGeneratemapi_0; "hr = GenerateMapIndex(pIdentity, wszSer"...
0x1800e1b15  mov     [rsp+78h+var_58], rcx
0x1800e1b1a  mov     r9d, eax
0x1800e1b1d  mov     r8d, 236h
0x1800e1b23  jmp     loc_1800E1CD2
0x1800e1b28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e1b2f  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800e1b34  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e1b39  mov     [rbp+var_38], rax
0x1800e1b3d  test    rax, rax
0x1800e1b40  jz      short loc_1800E1B4F
0x1800e1b42  mov     rcx, rax; this
0x1800e1b45  call    ??0CCertObject@@IEAA@XZ; CCertObject::CCertObject(void)
0x1800e1b4a  mov     rsi, rax
0x1800e1b4d  jmp     short loc_1800E1B52
0x1800e1b4f  mov     rsi, r15
0x1800e1b52  mov     [rbp+var_40], rsi
0x1800e1b56  test    rsi, rsi
0x1800e1b59  jnz     short loc_1800E1B67
0x1800e1b5b  mov     [rbp+arg_18], 8007000Eh
0x1800e1b62  jmp     loc_1800E1CE1
0x1800e1b67  mov     eax, [rbp+arg_38]
0x1800e1b6d  mov     [rsi+3Ch], eax
0x1800e1b70  cmp     eax, 1
0x1800e1b73  setnz   r9b; bool
0x1800e1b77  mov     r8d, [rbp+arg_28]; unsigned int
0x1800e1b7b  mov     rdx, rbx; unsigned __int16 *
0x1800e1b7e  mov     rcx, rsi; this
0x1800e1b81  call    ?BuildPKCS10Base64FromCache@CCertObject@@QEAAJPEBGK_N@Z; CCertObject::BuildPKCS10Base64FromCache(ushort const *,ulong,bool)
0x1800e1b86  mov     [rbp+arg_18], eax
0x1800e1b89  test    eax, eax
0x1800e1b8b  jns     short loc_1800E1BAE
0x1800e1b8d  lea     rcx, aHrPcertBuildpk; "hr = pCert->BuildPKCS10Base64FromCache("...
0x1800e1b94  mov     r8d, 23Fh
0x1800e1b9a  mov     r9d, eax
0x1800e1b9d  mov     [rsp+78h+var_58], rcx
0x1800e1ba2  lea     rdx, aCcertmanagerBu; "CCertManager::BuildCertFromCache"
0x1800e1ba9  jmp     loc_1800E1CD5
0x1800e1bae  mov     [rbp+var_30], rdi
0x1800e1bb2  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800e1bb6  call    cs:__imp_EnterCriticalSection
0x1800e1bbc  mov     rcx, [rdi+18h]; hEvent
0x1800e1bc0  call    cs:__imp_ResetEvent
0x1800e1bc6  mov     rcx, [rdi+10h]; hEvent
0x1800e1bca  call    cs:__imp_ResetEvent
0x1800e1bd0  lock inc dword ptr [rdi+8]
0x1800e1bd4  cmp     [rdi+0Ch], r15d
0x1800e1bd8  jle     short loc_1800E1BE8
0x1800e1bda  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800e1bdd  mov     rcx, [rdi+10h]; hHandle
0x1800e1be1  call    cs:__imp_WaitForSingleObject
0x1800e1be7  nop
0x1800e1be8  mov     [rbp+var_38], r15
0x1800e1bec  lea     r15, [rdi+48h]
0x1800e1bf0  lea     r8, [rbp+var_38]
0x1800e1bf4  mov     rbx, [rbp+var_48]
0x1800e1bf8  mov     rdx, rbx
0x1800e1bfb  mov     rcx, r15
0x1800e1bfe  call    ?Lookup@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCCertObject@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCCertObject@@@2@@ATL@@QEBA_NPEBGAEAPEAVCCertObject@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CCertObject *>>::Lookup(ushort const *,CCertObject * &)
0x1800e1c03  test    al, al
0x1800e1c05  jz      short loc_1800E1C20
0x1800e1c07  mov     rdx, rbx
0x1800e1c0a  mov     rcx, r15
0x1800e1c0d  call    ?RemoveKey@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCCertObject@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCCertObject@@@2@@ATL@@QEAA_NPEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CCertObject *>>::RemoveKey(ushort const *)
0x1800e1c12  mov     rcx, [rbp+var_38]; this
0x1800e1c16  test    rcx, rcx
0x1800e1c19  jz      short loc_1800E1C20
0x1800e1c1b  call    ??_GCCertObject@@QEAAPEAXI@Z; CCertObject::`scalar deleting destructor'(uint)
0x1800e1c20  mov     [rbp+var_38], rsi
0x1800e1c24  lea     r8, [rbp+var_38]
0x1800e1c28  mov     rdx, rbx
0x1800e1c2b  mov     rcx, r15
0x1800e1c2e  call    ?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCCertObject@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCCertObject@@@2@@ATL@@QEAAPEAU__POSITION@@PEBGAEBQEAVCCertObject@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CCertObject *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CCertObject *>>::SetAt(ushort const *,CCertObject * const &)
0x1800e1c33  mov     [rbp+var_40], 0
0x1800e1c3b  lock dec dword ptr [rdi+8]
0x1800e1c3f  mov     rcx, [rdi+18h]; hEvent
0x1800e1c43  call    cs:__imp_SetEvent
0x1800e1c49  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800e1c4d  call    cs:__imp_LeaveCriticalSection
0x1800e1c53  mov     rax, [rbp+arg_40]
0x1800e1c5a  mov     [rsp+78h+var_50], rax
0x1800e1c5f  mov     rax, [rbp+arg_30]
0x1800e1c63  mov     [rsp+78h+var_58], rax
0x1800e1c68  mov     r9, r13
0x1800e1c6b  mov     r8, r14
0x1800e1c6e  mov     rdx, r12
0x1800e1c71  mov     rcx, rdi
0x1800e1c74  call    ?PutCert@CCertManager@@QEAAJPEAXPEBG1VCTime@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; CCertManager::PutCert(void *,ushort const *,ushort const *,ATL::CTime,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800e1c79  mov     [rbp+arg_18], eax
0x1800e1c7c  test    eax, eax
0x1800e1c7e  jns     short loc_1800E1CE1
0x1800e1c80  lea     rcx, aHrPutcertPiden; "hr = PutCert(pIdentity, wszServiceName,"...
0x1800e1c87  mov     r8d, 250h
0x1800e1c8d  jmp     loc_1800E1B9A
0x1800e1c92  mov     r9d, 80048032h
0x1800e1c98  lea     rax, aWszservicename; "wszServiceName != nullptr && *wszServic"...
0x1800e1c9f  mov     r8d, 233h
0x1800e1ca5  jmp     short loc_1800E1CC9
0x1800e1ca7  lea     rax, aWszkeypairNull; "wszKeypair != nullptr && *wszKeypair !="...
0x1800e1cae  mov     r8d, 232h
0x1800e1cb4  jmp     short loc_1800E1CC3
0x1800e1cb6  lea     rax, aWszcertNullptr; "wszCert != nullptr && *wszCert != L'\\0"...
0x1800e1cbd  mov     r8d, 231h; unsigned int
0x1800e1cc3  mov     r9d, 80048890h; int
0x1800e1cc9  mov     [rsp+78h+var_58], rax; char *
0x1800e1cce  mov     [rbp+arg_18], r9d
0x1800e1cd2  mov     rdx, rsi; char *
0x1800e1cd5  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e1cdc  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e1ce1  mov     ebx, [rbp+arg_18]
0x1800e1ce4  lea     rcx, [rbp+var_28]
0x1800e1ce8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800e1ced  nop
0x1800e1cee  lea     rcx, [rbp+var_48]
0x1800e1cf2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e1cf7  nop
0x1800e1cf8  lea     rcx, [rbp+var_40]
0x1800e1cfc  call    ?Free@?$CAutoPtr@VCCertObject@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CCertObject>::Free(void)
0x1800e1d01  mov     eax, ebx
0x1800e1d03  add     rsp, 78h
0x1800e1d07  pop     r15
0x1800e1d09  pop     r14
0x1800e1d0b  pop     r13
0x1800e1d0d  pop     r12
0x1800e1d0f  pop     rdi
0x1800e1d10  pop     rsi
0x1800e1d11  pop     rbx
0x1800e1d12  pop     rbp
0x1800e1d13  retn
```
