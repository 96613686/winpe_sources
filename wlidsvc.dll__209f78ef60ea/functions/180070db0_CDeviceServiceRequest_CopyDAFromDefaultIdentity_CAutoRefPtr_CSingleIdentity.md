# CDeviceServiceRequest::CopyDAFromDefaultIdentity(CAutoRefPtr<CSingleIdentity> &)

- ea: `0x180070db0`
- end: `0x1800711b2`
- name: `?CopyDAFromDefaultIdentity@CDeviceServiceRequest@@UEAAJAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z`
- size: `1026`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c050`
- `0x18000cf88`
- `0x180011f38`
- `0x1800151c4`
- `0x1800179c0`
- `0x1800191c0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x1800277c0`
- `0x180028cd4`
- `0x180037288`
- `0x180051784`
- `0x180052ca8`
- `0x18006d7c0`
- `0x180070db0`
- `0x180084374`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180070e77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180070e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071111`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071146`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071111`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071146`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070ec5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070ec5`

## string_xrefs

- `0x180070e0a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rstdevice.cpp`
- `0x1800710eb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rstdevice.cpp`
- `0x180071137`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rstdevice.cpp`
- `0x180070de0`: `CDeviceServiceRequest::CopyDAFromDefaultIdentity`
- `0x1800710e4`: `CDeviceServiceRequest::CopyDAFromDefaultIdentity`
- `0x180071130`: `CDeviceServiceRequest::CopyDAFromDefaultIdentity`
- `0x180070efb`: `pDeviceIdentity->HasAuthToken()`
- `0x180070ea2`: `m_pIdentity->GetIdentityName().CompareNoCase(pDeviceIdentity->GetIdentityName()) == 0`
- `0x18007115f`: `m_pIdentity->HasAuthToken()`
- `0x1800710cf`: `hr = m_pIdentity->GetTokenBag()->StoreToken(SERVICE_TARGET_PASSPORT, ppcrlAuthToken.GetToken(), ppcrlAuthToken.GetKeyPair(), L"", ppcrlAuthToken.GetTokenURI(), CTime(ppcrlAuthToken.GetCreatedTimeOnServer()), CTime(ppcrlAuthToken.GetExpiredTimeOnServer()), bpSessionKey, ppcrlAuthToken.GetType(), S_OK, S_OK, L"", L"", L"", L"", ppcrlAuthToken.GetSessionKeyType())`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDeviceServiceRequest::CopyDAFromDefaultIdentity(__int64 a1, CSingleIdentity **a2)
{
  __int64 v3; // rsi
  int v4; // r9d
  const char *v5; // rax
  unsigned int v6; // r8d
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  RTL_SRWLOCK *v9; // rbx
  __int64 *v10; // r13
  __int64 *v11; // r15
  int v12; // r12d
  __int64 TokenURI; // r14
  __int64 *v14; // rsi
  int KeyPair; // edi
  int Token; // ebx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  char *v21; // [rsp+20h] [rbp-F0h]
  int v22; // [rsp+90h] [rbp-80h] BYREF
  __int64 v23; // [rsp+98h] [rbp-78h]
  int v24; // [rsp+A0h] [rbp-70h]
  __int64 v25; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-58h] BYREF
  _BYTE v28[8]; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-48h] BYREF
  _BYTE v30[8]; // [rsp+D0h] [rbp-40h] BYREF
  _BYTE v31[8]; // [rsp+D8h] [rbp-38h] BYREF
  _BYTE v32[8]; // [rsp+E0h] [rbp-30h] BYREF
  __int64 *v33; // [rsp+E8h] [rbp-28h]
  __int64 *v34; // [rsp+F0h] [rbp-20h]
  __int64 v35; // [rsp+F8h] [rbp-18h] BYREF
  __int64 v36; // [rsp+100h] [rbp-10h] BYREF
  __int64 v37; // [rsp+108h] [rbp-8h]
  _QWORD v38[14]; // [rsp+110h] [rbp+0h] BYREF
  _DWORD v39[12]; // [rsp+180h] [rbp+70h] BYREF
  __int64 v40; // [rsp+1B0h] [rbp+A0h]
  __int64 v41; // [rsp+1B8h] [rbp+A8h]
  unsigned int v42; // [rsp+208h] [rbp+F8h]
  unsigned __int8 *v43; // [rsp+210h] [rbp+100h]
  int v45; // [rsp+288h] [rbp+178h] BYREF
  RTL_SRWLOCK *v46; // [rsp+290h] [rbp+180h] BYREF
  __int64 v47; // [rsp+298h] [rbp+188h] BYREF

  v3 = a1;
  v45 = 0;
  v38[0] = "CDeviceServiceRequest::CopyDAFromDefaultIdentity";
  v38[1] = &v45;
  v38[2] = 0;
  v38[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rstdevice.cpp",
    "CDeviceServiceRequest::CopyDAFromDefaultIdentity",
    (const char *)0x142,
    0,
    (const unsigned __int16 *)v21);
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v39);
  if ( !*a2 )
  {
    v4 = -2147024809;
    v5 = "pDeviceIdentity != nullptr";
    v6 = 325;
LABEL_17:
    v45 = v4;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rstdevice.cpp",
      "CDeviceServiceRequest::CopyDAFromDefaultIdentity",
      v6,
      v4,
      v5);
    goto LABEL_18;
  }
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v3 + 24) + 32LL))(
                   *(_QWORD *)(v3 + 24),
                   &v47);
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(CSingleIdentity *, RTL_SRWLOCK **))(*(_QWORD *)*a2 + 32LL))(*a2, &v46);
  LODWORD(v7) = _o__wcsicmp(*v7, *v8);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  if ( (_DWORD)v7 )
  {
    v4 = -2147187451;
    v5 = "m_pIdentity->GetIdentityName().CompareNoCase(pDeviceIdentity->GetIdentityName()) == 0";
    v6 = 328;
    goto LABEL_17;
  }
  v9 = (RTL_SRWLOCK *)((char *)*a2 + 56);
  v46 = v9;
  AcquireSRWLockShared(v9);
  v38[4] = v9;
  CSingleIdentity::GetServiceToken(*a2, L"http://Passport.NET/tb", (struct CPPCRLToken *)v39);
  if ( !CSingleIdentity::HasAuthToken(*a2) )
  {
    v45 = -2147186591;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rstdevice.cpp",
      "CDeviceServiceRequest::CopyDAFromDefaultIdentity",
      0x14Fu,
      -2147186591,
      "pDeviceIdentity->HasAuthToken()");
    goto LABEL_10;
  }
  if ( *(_QWORD *)(*(_QWORD *)(v3 + 24) + 88LL) )
  {
    v23 = 0;
    v22 = 0;
    v24 = 0;
    CBytePtr::Attach((CBytePtr *)&v22, v43, v42, 0);
    v37 = *(_QWORD *)(*(_QWORD *)(v3 + 24) + 88LL);
    v38[5] = &v47;
    v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v47,
            &qword_18013DE20);
    v38[6] = &v25;
    v34 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v25,
            &qword_18013DE20);
    v38[7] = &v26;
    v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v26,
            &qword_18013DE20);
    v38[8] = &v27;
    v11 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v27,
            &qword_18013DE20);
    v12 = v39[6];
    v35 = v41;
    v36 = v40;
    v38[9] = v28;
    TokenURI = CPPCRLToken::GetTokenURI(v39, v28);
    v38[10] = &v29;
    v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v29,
            &qword_18013DE20);
    v38[11] = v30;
    KeyPair = CPPCRLToken::GetKeyPair(v39, v30);
    v38[12] = v31;
    Token = CPPCRLToken::GetToken(v39, v31);
    v17 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            v32,
            L"http://Passport.NET/tb");
    v18 = CIdentityTokenBag::StoreToken(
            v37,
            v17,
            Token,
            KeyPair,
            (__int64)v14,
            TokenURI,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v22,
            v12,
            0,
            0,
            (__int64)v11,
            (__int64)v10,
            (__int64)v34,
            (__int64)v33,
            v39[0]);
    v45 = v18;
    if ( v18 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rstdevice.cpp",
        "CDeviceServiceRequest::CopyDAFromDefaultIdentity",
        0x164u,
        v18,
        "hr = m_pIdentity->GetTokenBag()->StoreToken(SERVICE_TARGET_PASSPORT, ppcrlAuthToken.GetToken(), ppcrlAuthToken.G"
        "etKeyPair(), L\"\", ppcrlAuthToken.GetTokenURI(), CTime(ppcrlAuthToken.GetCreatedTimeOnServer()), CTime(ppcrlAut"
        "hToken.GetExpiredTimeOnServer()), bpSessionKey, ppcrlAuthToken.GetType(), S_OK, S_OK, L\"\", L\"\", L\"\", L\"\""
        ", ppcrlAuthToken.GetSessionKeyType())");
      CBytePtr::Empty((CBytePtr *)&v22);
      v9 = v46;
LABEL_10:
      if ( v9 )
        ReleaseSRWLockShared(v9);
      goto LABEL_18;
    }
    CBytePtr::Empty((CBytePtr *)&v22);
    v9 = v46;
    v3 = a1;
  }
  if ( v9 )
    ReleaseSRWLockShared(v9);
  if ( !CSingleIdentity::HasAuthToken(*(CSingleIdentity **)(v3 + 24)) )
  {
    v4 = -2147186591;
    v5 = "m_pIdentity->HasAuthToken()";
    v6 = 360;
    goto LABEL_17;
  }
LABEL_18:
  v19 = v45;
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v39);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
  return v19;
}

```

## disassembly

```asm
0x180070db0  mov     [rsp-8+arg_0], rcx
0x180070db5  push    rbp
0x180070db6  push    rbx
0x180070db7  push    rsi
0x180070db8  push    rdi
0x180070db9  push    r12
0x180070dbb  push    r13
0x180070dbd  push    r14
0x180070dbf  push    r15
0x180070dc1  lea     rbp, [rsp-128h]
0x180070dc9  sub     rsp, 238h
0x180070dd0  mov     rdi, rdx
0x180070dd3  mov     rsi, rcx
0x180070dd6  xor     r15d, r15d
0x180070dd9  mov     [rbp+160h+arg_8], r15d
0x180070de0  lea     r14, aCdeviceservice_0; "CDeviceServiceRequest::CopyDAFromDefaul"...
0x180070de7  mov     [rbp+160h+var_160], r14
0x180070deb  lea     rax, [rbp+160h+arg_8]
0x180070df2  mov     [rbp+160h+var_158], rax
0x180070df6  mov     [rbp+160h+var_150], r15
0x180070dfa  mov     [rbp+160h+var_148], r15
0x180070dfe  xor     r9d, r9d; unsigned int
0x180070e01  mov     r8d, 142h; char *
0x180070e07  mov     rdx, r14; char *
0x180070e0a  lea     r12, aOnecoreuapDsEx_103; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180070e11  mov     rcx, r12; this
0x180070e14  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180070e19  nop
0x180070e1a  lea     rcx, [rbp+160h+var_F0]; this
0x180070e1e  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x180070e23  nop
0x180070e24  cmp     [rdi], r15
0x180070e27  jnz     short loc_180070E41
0x180070e29  mov     r9d, 80070057h
0x180070e2f  lea     rax, aPdeviceidentit; "pDeviceIdentity != nullptr"
0x180070e36  mov     r8d, 145h
0x180070e3c  jmp     loc_18007116C
0x180070e41  mov     rcx, [rsi+18h]
0x180070e45  mov     rax, [rcx]
0x180070e48  lea     rdx, [rbp+160h+arg_18]
0x180070e4f  mov     rax, [rax+20h]
0x180070e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e58  mov     rbx, rax
0x180070e5b  mov     rcx, [rdi]
0x180070e5e  mov     rdx, [rcx]
0x180070e61  mov     rax, [rdx+20h]
0x180070e65  lea     rdx, [rbp+160h+arg_10]
0x180070e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e71  mov     rdx, [rax]
0x180070e74  mov     rcx, [rbx]
0x180070e77  call    cs:__imp__o__wcsicmp
0x180070e7d  mov     ebx, eax
0x180070e7f  lea     rcx, [rbp+160h+arg_10]
0x180070e86  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180070e8b  nop
0x180070e8c  lea     rcx, [rbp+160h+arg_18]
0x180070e93  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180070e98  test    ebx, ebx
0x180070e9a  jz      short loc_180070EB4
0x180070e9c  mov     r9d, 80048505h
0x180070ea2  lea     rax, aMPidentityGeti; "m_pIdentity->GetIdentityName().CompareN"...
0x180070ea9  mov     r8d, 148h
0x180070eaf  jmp     loc_18007116C
0x180070eb4  mov     rbx, [rdi]
0x180070eb7  add     rbx, 38h ; '8'
0x180070ebb  mov     [rbp+160h+arg_10], rbx
0x180070ec2  mov     rcx, rbx; SRWLock
0x180070ec5  call    cs:__imp_AcquireSRWLockShared
0x180070ecb  mov     [rbp+160h+var_140], rbx
0x180070ecf  lea     r8, [rbp+160h+var_F0]; struct CPPCRLToken *
0x180070ed3  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x180070eda  mov     rcx, [rdi]; this
0x180070edd  call    ?GetServiceToken@CSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@@Z; CSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &)
0x180070ee2  mov     rcx, [rdi]; this
0x180070ee5  call    ?HasAuthToken@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::HasAuthToken(void)
0x180070eea  test    al, al
0x180070eec  jnz     short loc_180070F1E
0x180070eee  mov     r9d, 80048861h; int
0x180070ef4  mov     [rbp+160h+arg_8], r9d
0x180070efb  lea     rax, aPdeviceidentit_0; "pDeviceIdentity->HasAuthToken()"
0x180070f02  mov     [rsp+270h+var_250], rax; char *
0x180070f07  mov     r8d, 14Fh; unsigned int
0x180070f0d  mov     rdx, r14; char *
0x180070f10  mov     rcx, r12; char *
0x180070f13  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180070f18  nop
0x180070f19  jmp     loc_180071109
0x180070f1e  mov     rax, [rsi+18h]
0x180070f22  cmp     [rax+58h], r15
0x180070f26  jz      loc_18007113E
0x180070f2c  mov     [rbp+160h+var_1D8], r15
0x180070f30  mov     [rbp+160h+var_1E0], r15d
0x180070f34  mov     [rbp+160h+var_1D0], r15d
0x180070f38  xor     r9d, r9d; bool
0x180070f3b  mov     r8d, [rbp+160h+var_68]; unsigned int
0x180070f42  mov     rdx, [rbp+160h+var_60]; unsigned __int8 *
0x180070f49  lea     rcx, [rbp+160h+var_1E0]; this
0x180070f4d  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x180070f52  mov     rax, [rsi+18h]
0x180070f56  mov     rax, [rax+58h]
0x180070f5a  mov     [rbp+160h+var_168], rax
0x180070f5e  lea     rax, [rbp+160h+arg_18]
0x180070f65  mov     [rbp+160h+var_138], rax
0x180070f69  lea     rbx, qword_18013DE20
0x180070f70  mov     rdx, rbx
0x180070f73  lea     rcx, [rbp+160h+arg_18]
0x180070f7a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180070f7f  mov     [rbp+160h+var_188], rax
0x180070f83  lea     rax, [rbp+160h+var_1C8]
0x180070f87  mov     [rbp+160h+var_130], rax
0x180070f8b  mov     rdx, rbx
0x180070f8e  lea     rcx, [rbp+160h+var_1C8]
0x180070f92  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180070f97  mov     [rbp+160h+var_180], rax
0x180070f9b  lea     rax, [rbp+160h+var_1C0]
0x180070f9f  mov     [rbp+160h+var_128], rax
0x180070fa3  mov     rdx, rbx
0x180070fa6  lea     rcx, [rbp+160h+var_1C0]
0x180070faa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180070faf  mov     r13, rax
0x180070fb2  lea     rax, [rbp+160h+var_1B8]
0x180070fb6  mov     [rbp+160h+var_120], rax
0x180070fba  mov     rdx, rbx
0x180070fbd  lea     rcx, [rbp+160h+var_1B8]
0x180070fc1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180070fc6  mov     r15, rax
0x180070fc9  mov     r12d, [rbp+160h+var_D8]
0x180070fd0  mov     rcx, [rbp+160h+var_B8]
0x180070fd7  mov     [rbp+160h+var_178], rcx
0x180070fdb  mov     rcx, [rbp+160h+var_C0]
0x180070fe2  mov     [rbp+160h+var_170], rcx
0x180070fe6  lea     rax, [rbp+160h+var_1B0]
0x180070fea  mov     [rbp+160h+var_118], rax
0x180070fee  lea     rdx, [rbp+160h+var_1B0]
0x180070ff2  lea     rcx, [rbp+160h+var_F0]
0x180070ff6  call    ?GetTokenURI@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetTokenURI(void)
0x180070ffb  mov     r14, rax
0x180070ffe  lea     rax, [rbp+160h+var_1A8]
0x180071002  mov     [rbp+160h+var_110], rax
0x180071006  mov     rdx, rbx
0x180071009  lea     rcx, [rbp+160h+var_1A8]
0x18007100d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180071012  mov     rsi, rax
0x180071015  lea     rax, [rbp+160h+var_1A0]
0x180071019  mov     [rbp+160h+var_108], rax
0x18007101d  lea     rdx, [rbp+160h+var_1A0]
0x180071021  lea     rcx, [rbp+160h+var_F0]
0x180071025  call    ?GetKeyPair@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetKeyPair(void)
0x18007102a  mov     rdi, rax
0x18007102d  lea     rax, [rbp+160h+var_198]
0x180071031  mov     [rbp+160h+var_100], rax
0x180071035  lea     rdx, [rbp+160h+var_198]
0x180071039  lea     rcx, [rbp+160h+var_F0]
0x18007103d  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x180071042  mov     rbx, rax
0x180071045  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x18007104c  lea     rcx, [rbp+160h+var_190]
0x180071050  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x180071055  nop
0x180071056  mov     ecx, [rbp+160h+var_F0]
0x180071059  mov     [rsp+270h+var_1F0], ecx
0x180071060  mov     rcx, [rbp+160h+var_188]
0x180071064  mov     [rsp+270h+var_1F8], rcx
0x180071069  mov     rcx, [rbp+160h+var_180]
0x18007106d  mov     [rsp+270h+var_200], rcx
0x180071072  mov     [rsp+270h+var_208], r13
0x180071077  mov     [rsp+270h+var_210], r15
0x18007107c  xor     r15d, r15d
0x18007107f  mov     [rsp+270h+var_218], r15d
0x180071084  mov     [rsp+270h+var_220], r15d
0x180071089  mov     [rsp+270h+var_228], r12d
0x18007108e  lea     rcx, [rbp+160h+var_1E0]
0x180071092  mov     [rsp+270h+var_230], rcx
0x180071097  lea     rcx, [rbp+160h+var_178]
0x18007109b  mov     [rsp+270h+var_238], rcx
0x1800710a0  lea     rcx, [rbp+160h+var_170]
0x1800710a4  mov     [rsp+270h+var_240], rcx
0x1800710a9  mov     [rsp+270h+var_248], r14
0x1800710ae  mov     [rsp+270h+var_250], rsi
0x1800710b3  mov     r9, rdi
0x1800710b6  mov     r8, rbx
0x1800710b9  mov     rdx, rax
0x1800710bc  mov     rcx, [rbp+160h+var_168]
0x1800710c0  call    ?StoreToken@CIdentityTokenBag@@QEAAJV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@111AEAVCTime@3@2AEBVCBytePtr@@KJJ1111W4Type@SessionKeyTypes@@@Z; CIdentityTokenBag::StoreToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CTime &,ATL::CTime &,CBytePtr const &,ulong,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SessionKeyTypes::Type)
0x1800710c5  mov     [rbp+160h+arg_8], eax
0x1800710cb  test    eax, eax
0x1800710cd  jns     short loc_180071119
0x1800710cf  lea     rcx, aHrMPidentityGe_9; "hr = m_pIdentity->GetTokenBag()->StoreT"...
0x1800710d6  mov     [rsp+270h+var_250], rcx; char *
0x1800710db  mov     r9d, eax; int
0x1800710de  mov     r8d, 164h; unsigned int
0x1800710e4  lea     rdx, aCdeviceservice_0; "CDeviceServiceRequest::CopyDAFromDefaul"...
0x1800710eb  lea     rcx, aOnecoreuapDsEx_103; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800710f2  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800710f7  nop
0x1800710f8  lea     rcx, [rbp+160h+var_1E0]; this
0x1800710fc  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180071101  nop
0x180071102  mov     rbx, [rbp+160h+arg_10]
0x180071109  test    rbx, rbx
0x18007110c  jz      short loc_180071183
0x18007110e  mov     rcx, rbx; SRWLock
0x180071111  call    cs:__imp_ReleaseSRWLockShared
0x180071117  jmp     short loc_180071183
0x180071119  lea     rcx, [rbp+160h+var_1E0]; this
0x18007111d  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180071122  mov     rbx, [rbp+160h+arg_10]
0x180071129  mov     rsi, [rbp+160h+arg_0]
0x180071130  lea     r14, aCdeviceservice_0; "CDeviceServiceRequest::CopyDAFromDefaul"...
0x180071137  lea     r12, aOnecoreuapDsEx_103; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18007113e  test    rbx, rbx
0x180071141  jz      short loc_18007114C
0x180071143  mov     rcx, rbx; SRWLock
0x180071146  call    cs:__imp_ReleaseSRWLockShared
0x18007114c  mov     rcx, [rsi+18h]; this
0x180071150  call    ?HasAuthToken@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::HasAuthToken(void)
0x180071155  test    al, al
0x180071157  jnz     short loc_180071183
0x180071159  mov     r9d, 80048861h; int
0x18007115f  lea     rax, aMPidentityHasa; "m_pIdentity->HasAuthToken()"
0x180071166  mov     r8d, 168h; unsigned int
0x18007116c  mov     [rsp+270h+var_250], rax; char *
0x180071171  mov     [rbp+160h+arg_8], r9d
0x180071178  mov     rdx, r14; char *
0x18007117b  mov     rcx, r12; char *
0x18007117e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180071183  mov     ebx, [rbp+160h+arg_8]
0x180071189  lea     rcx, [rbp+160h+var_F0]; this
0x18007118d  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x180071192  nop
0x180071193  lea     rcx, [rbp+160h+var_160]
0x180071197  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18007119c  mov     eax, ebx
0x18007119e  add     rsp, 238h
0x1800711a5  pop     r15
0x1800711a7  pop     r14
0x1800711a9  pop     r13
0x1800711ab  pop     r12
0x1800711ad  pop     rdi
0x1800711ae  pop     rsi
0x1800711af  pop     rbx
0x1800711b0  pop     rbp
0x1800711b1  retn
```
