# UpdateSamProperties(RenameAccountData &)

- ea: `0x18008fe20`
- end: `0x180090363`
- name: `?UpdateSamProperties@@YAJAEAURenameAccountData@@@Z`
- size: `1347`
- prototype: `__int64 __fastcall(struct RenameAccountData *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180092c78`

## callees

- `0x1800076b4`
- `0x180009e98`
- `0x18000a36c`
- `0x18000c050`
- `0x18000ed04`
- `0x180013510`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002f510`
- `0x180037e48`
- `0x18004af44`
- `0x18004afcc`
- `0x18008fe20`
- `0x18009036c`
- `0x1800903ac`
- `0x1800a3b60`
- `0x1800f0840`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009016a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009016a`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800900f9`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800900f9`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18009013b`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18009013b`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18009020b`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18009020b`

## string_xrefs

- `0x180090264`: `hr = ULongAdd(encodedBufferLength, sizeof(CLOUD_AP_RENAME_ACCOUNT_INPUT) - ANYSIZE_ARRAY, &protocolBufferLength)`
- `0x18008ff0e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x18008ffa2`: `hr = renameAccountData.pNewIdentity->GetCredProperty(PPCRL_CREDPROPERTY_LASTNAME, lastName)`
- `0x18008ff64`: `hr = renameAccountData.pNewIdentity->GetCredProperty(PPCRL_CREDPROPERTY_FIRSTNAME, firstName)`
- `0x18008fee6`: `UpdateSamProperties`
- `0x18008ffd7`: `hr = ExtensionAPI::FormatUserDisplayName(firstName, lastName, &pDisplayName, nullptr)`
- `0x1800901c6`: `hr = SafeCopyMemory(apCloudProtocolBuffer->abSerializedProperties, (protocolBufferLength - sizeof(CLOUD_AP_RENAME_ACCOUNT_INPUT) + ANYSIZE_ARRAY), apEncodedBuffer, encodedBufferLength)`
- `0x180090247`: `LsaCallAuthenticationPackage protocolStatus = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall UpdateSamProperties(struct RenameAccountData *a1)
{
  int v2; // eax
  int v3; // eax
  unsigned __int16 **v4; // r9
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  NTSTATUS v8; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rsi
  char *v14; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  PVOID *ProtocolReturnBuffer; // [rsp+20h] [rbp-E0h]
  int *ProtocolReturnBuffera; // [rsp+20h] [rbp-E0h]
  PVOID *ProtocolReturnBufferb; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-BCh] BYREF
  ULONG AuthenticationPackage; // [rsp+48h] [rbp-B8h] BYREF
  int ProtocolStatus; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-B0h] BYREF
  MsaUserExtImpl *v26; // [rsp+58h] [rbp-A8h] BYREF
  ULONG SecurityMode; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ReturnBufferLength; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  char *v30; // [rsp+70h] [rbp-90h] BYREF
  _LSA_STRING LogonProcessName; // [rsp+78h] [rbp-88h] BYREF
  struct _LSA_STRING PackageName; // [rsp+88h] [rbp-78h] BYREF
  void *LsaHandle[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v34; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v35; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v36[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v37[3]; // [rsp+D0h] [rbp-30h] BYREF
  int *v38[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v39[5]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v40[8]; // [rsp+130h] [rbp+30h] BYREF
  int v41; // [rsp+170h] [rbp+70h] BYREF
  __int64 Buffer; // [rsp+178h] [rbp+78h]
  int v43; // [rsp+180h] [rbp+80h]
  __int64 v44; // [rsp+188h] [rbp+88h]
  int v45; // [rsp+190h] [rbp+90h]
  __int64 v46; // [rsp+198h] [rbp+98h]
  int v47; // [rsp+1A0h] [rbp+A0h]
  __int64 v48; // [rsp+1A8h] [rbp+A8h]
  int v49; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 *v50; // [rsp+1B8h] [rbp+B8h]

  v21 = 0;
  *(_QWORD *)&LogonProcessName.Length = 524295;
  LogonProcessName.Buffer = "wlidsvc";
  *(_QWORD *)&PackageName.Length = 524295;
  PackageName.Buffer = "CloudAP";
  memset(LsaHandle, 0, sizeof(LsaHandle));
  SecurityMode = 0;
  AuthenticationPackage = 0;
  v35 = 0;
  ReturnBufferLength = 0;
  ProtocolStatus = 0;
  v30 = 0;
  ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v40);
  v34 = v40;
  v29 = 0;
  v22 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25);
  memset(v37, 0, sizeof(v37));
  v39[0] = "UpdateSamProperties";
  v39[1] = &v21;
  v39[2] = 0;
  v39[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "UpdateSamProperties",
    (const char *)0xA1,
    0,
    (const unsigned __int16 *)ProtocolReturnBuffer);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v38, "UpdateSamProperties", &v21, 3u, &qword_18017E1F0);
  v2 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, MsaUserExtImpl **))(**((_QWORD **)a1 + 3) + 64LL))(
         *((_QWORD *)a1 + 3),
         L"FirstName",
         &v26);
  v21 = v2;
  if ( v2 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xA8u,
      v2,
      "hr = renameAccountData.pNewIdentity->GetCredProperty(PPCRL_CREDPROPERTY_FIRSTNAME, firstName)");
    goto LABEL_28;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **))(**((_QWORD **)a1 + 3) + 64LL))(
         *((_QWORD *)a1 + 3),
         L"LastName",
         &v25);
  v21 = v3;
  if ( v3 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xA9u,
      v3,
      "hr = renameAccountData.pNewIdentity->GetCredProperty(PPCRL_CREDPROPERTY_LASTNAME, lastName)");
    goto LABEL_28;
  }
  v5 = MsaUserExtImpl::FormatUserDisplayName(v26, v25, v37, v4, ProtocolReturnBuffera);
  v21 = v5;
  if ( v5 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xAAu,
      v5,
      "hr = ExtensionAPI::FormatUserDisplayName(firstName, lastName, &pDisplayName, nullptr)");
    goto LABEL_28;
  }
  v41 = 2 * *(_DWORD *)(*(_QWORD *)a1 - 16LL) + 2;
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(a1);
  v43 = 2 * *(_DWORD *)(*((_QWORD *)a1 + 1) - 16LL) + 2;
  v44 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)a1 + 8);
  v45 = 2 * *((_DWORD *)v26 - 4) + 2;
  v46 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v26);
  v47 = 2 * *((_DWORD *)v25 - 4) + 2;
  v48 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v25);
  v6 = -1;
  do
    ++v6;
  while ( v37[0][v6] );
  v49 = 2 * v6 + 2;
  v50 = v37[0];
  v36[0] = 5;
  v36[1] = &v41;
  v7 = SerializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>((WlidPropertyBagSerializer *)&v34, v36, &v29, &v22);
  v21 = v7;
  if ( v7 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xBBu,
      v7,
      "hr = SerializeObject(serializer, propertyBag, &apEncodedBuffer, &encodedBufferLength)");
    goto LABEL_28;
  }
  v8 = LsaRegisterLogonProcess(&LogonProcessName, LsaHandle, &SecurityMode);
  if ( v8 < 0 )
  {
    v9 = L"Failure - LsaRegisterLogonProcess, HRESULT: 0x%08X\n";
    v10 = 193;
LABEL_13:
    v11 = v8 | 0x10000000;
    v21 = v11;
LABEL_14:
    LODWORD(ProtocolReturnBufferb) = v11;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      v10,
      v9,
      ProtocolReturnBufferb);
    goto LABEL_28;
  }
  v8 = LsaLookupAuthenticationPackage(LsaHandle[0], &PackageName, &AuthenticationPackage);
  if ( v8 < 0 )
  {
    v9 = L"Failure - LsaLookupAuthenticationPackage, HRESULT: 0x%08X\n";
    v10 = 200;
    goto LABEL_13;
  }
  v12 = v22;
  v13 = v22 + 27;
  if ( (unsigned int)v13 < v22 )
  {
    v21 = -2147024362;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xCBu,
      -2147024362,
      "hr = ULongAdd(encodedBufferLength, sizeof(CLOUD_AP_RENAME_ACCOUNT_INPUT) - ANYSIZE_ARRAY, &protocolBufferLength)");
    goto LABEL_28;
  }
  v21 = 0;
  v14 = (char *)malloc((unsigned int)v13);
  CMIDLPtr<unsigned short *>::Clear(&v30);
  v30 = v14;
  if ( !v14 )
  {
    v21 = -2147024882;
    goto LABEL_28;
  }
  *(_DWORD *)v14 = 5;
  *(_OWORD *)(v14 + 4) = xmmword_18017E200;
  *((_DWORD *)v14 + 5) = v12;
  v15 = SafeCopyMemory(v14 + 24, v13 - 27, v29, v12);
  v21 = v15;
  if ( v15 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "UpdateSamProperties",
      0xD2u,
      v15,
      "hr = SafeCopyMemory(apCloudProtocolBuffer->abSerializedProperties, (protocolBufferLength - sizeof(CLOUD_AP_RENAME_"
      "ACCOUNT_INPUT) + ANYSIZE_ARRAY), apEncodedBuffer, encodedBufferLength)");
    goto LABEL_28;
  }
  v11 = LsaCallAuthenticationPackage(
          LsaHandle[0],
          AuthenticationPackage,
          v14,
          v13,
          &v35,
          &ReturnBufferLength,
          &ProtocolStatus);
  if ( v11 < 0 )
  {
    v21 = v11 | 0x10000000;
    v9 = L"LsaCallAuthenticationPackage status = 0x%x.";
    v10 = 216;
    goto LABEL_14;
  }
  if ( ProtocolStatus < 0 )
  {
    v21 = ProtocolStatus | 0x10000000;
    LODWORD(ProtocolReturnBufferb) = ProtocolStatus;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      0xDEu,
      L"LsaCallAuthenticationPackage protocolStatus = 0x%x.",
      ProtocolReturnBufferb);
  }
LABEL_28:
  v16 = v21;
  ErrorVerifier::CheckAgainstList((const char *)v38[3], *v38[2], (unsigned __int64)v38[1], v38[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v39);
  Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>((__int64)v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v26);
  CMIDLPtr<unsigned char *>::Clear(&v29);
  v40[7] = &ISystemStoreLiteFunctions::`vftable';
  v40[6] = &IComFunctions::`vftable';
  v40[5] = &IComFunctions::`vftable';
  v40[4] = &IWinApiLite::`vftable';
  v40[3] = &IRPCFunctions::`vftable';
  v40[2] = &IRegistryFunctions::`vftable';
  v40[1] = &IPPCRLRequest::`vftable';
  v40[0] = &IExecutionContextLite::`vftable';
  CMIDLPtr<unsigned short *>::Clear(&v30);
  Auto<void *,LsaHandleFunctor,DummyContext>::~Auto<void *,LsaHandleFunctor,DummyContext>(LsaHandle);
  return v16;
}

```

## disassembly

```asm
0x18008fe20  push    rbp
0x18008fe22  push    rbx
0x18008fe23  push    rsi
0x18008fe24  push    rdi
0x18008fe25  push    r12
0x18008fe27  push    r13
0x18008fe29  push    r14
0x18008fe2b  push    r15
0x18008fe2d  lea     rbp, [rsp-0D8h]
0x18008fe35  sub     rsp, 1D8h
0x18008fe3c  mov     rax, cs:__security_cookie
0x18008fe43  xor     rax, rsp
0x18008fe46  mov     [rbp+110h+var_50], rax
0x18008fe4d  mov     rbx, rcx
0x18008fe50  xor     r15d, r15d
0x18008fe53  mov     [rsp+210h+var_1D0], r15d
0x18008fe58  mov     qword ptr [rsp+210h+LogonProcessName.Length], 80007h
0x18008fe61  lea     rax, aWlidsvc; "wlidsvc"
0x18008fe68  mov     [rbp+110h+LogonProcessName.Buffer], rax
0x18008fe6c  mov     qword ptr [rbp+110h+PackageName.Length], 80007h
0x18008fe74  lea     rax, aCloudap; "CloudAP"
0x18008fe7b  mov     [rbp+110h+PackageName.Buffer], rax
0x18008fe7f  mov     [rbp+110h+LsaHandle], r15
0x18008fe83  mov     [rbp+110h+var_168], r15
0x18008fe87  mov     [rbp+110h+var_170], r15
0x18008fe8b  mov     [rsp+210h+SecurityMode], r15d
0x18008fe90  mov     [rsp+210h+AuthenticationPackage], r15d
0x18008fe95  mov     [rbp+110h+var_158], r15
0x18008fe99  mov     [rsp+210h+var_1AC], r15d
0x18008fe9e  mov     [rsp+210h+var_1C4], r15d
0x18008fea3  mov     [rsp+210h+var_1A0], r15
0x18008fea8  lea     rcx, [rbp+110h+var_E0]; this
0x18008feac  call    ??0ExecutionContextLite@@QEAA@XZ; ExecutionContextLite::ExecutionContextLite(void)
0x18008feb1  nop
0x18008feb2  lea     rax, [rbp+110h+var_E0]
0x18008feb6  mov     [rbp+110h+var_160], rax
0x18008feba  mov     [rsp+210h+var_1A8], r15
0x18008febf  mov     [rsp+210h+var_1CC], r15d
0x18008fec4  lea     rcx, [rsp+210h+var_1B8]
0x18008fec9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008fece  nop
0x18008fecf  lea     rcx, [rsp+210h+var_1C0]
0x18008fed4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008fed9  nop
0x18008feda  mov     [rbp+110h+var_140], r15
0x18008fede  mov     [rbp+110h+var_130], r15
0x18008fee2  mov     [rbp+110h+var_138], r15
0x18008fee6  lea     r13, aUpdatesamprope; "UpdateSamProperties"
0x18008feed  mov     [rbp+110h+var_108], r13
0x18008fef1  lea     rax, [rsp+210h+var_1D0]
0x18008fef6  mov     [rbp+110h+var_100], rax
0x18008fefa  mov     [rbp+110h+var_F8], r15
0x18008fefe  mov     [rbp+110h+var_F0], r15
0x18008ff02  xor     r9d, r9d; unsigned int
0x18008ff05  mov     r8d, 0A1h; char *
0x18008ff0b  mov     rdx, r13; char *
0x18008ff0e  lea     r12, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008ff15  mov     rcx, r12; this
0x18008ff18  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008ff1d  nop
0x18008ff1e  lea     rax, qword_18017E1F0
0x18008ff25  mov     [rsp+210h+ProtocolReturnBuffer], rax; int *
0x18008ff2a  lea     r9d, [r15+3]; unsigned __int64
0x18008ff2e  lea     r8, [rsp+210h+var_1D0]; int *
0x18008ff33  mov     rdx, r13; char *
0x18008ff36  lea     rcx, [rbp+110h+var_128]; this
0x18008ff3a  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18008ff3f  nop
0x18008ff40  mov     rcx, [rbx+18h]
0x18008ff44  mov     rax, [rcx]
0x18008ff47  lea     r8, [rsp+210h+var_1B8]
0x18008ff4c  lea     rdx, aFirstname; "FirstName"
0x18008ff53  mov     rax, [rax+40h]
0x18008ff57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff5c  mov     [rsp+210h+var_1D0], eax
0x18008ff60  test    eax, eax
0x18008ff62  jns     short loc_18008FF7E
0x18008ff64  lea     r8, aHrRenameaccoun_1; "hr = renameAccountData.pNewIdentity->Ge"...
0x18008ff6b  mov     [rsp+210h+ProtocolReturnBuffer], r8
0x18008ff70  mov     r9d, eax
0x18008ff73  mov     r8d, 0A8h
0x18008ff79  jmp     loc_180090276
0x18008ff7e  mov     rcx, [rbx+18h]
0x18008ff82  mov     rax, [rcx]
0x18008ff85  lea     r8, [rsp+210h+var_1C0]
0x18008ff8a  lea     rdx, aLastname; "LastName"
0x18008ff91  mov     rax, [rax+40h]
0x18008ff95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff9a  mov     [rsp+210h+var_1D0], eax
0x18008ff9e  test    eax, eax
0x18008ffa0  jns     short loc_18008FFBC
0x18008ffa2  lea     rcx, aHrRenameaccoun; "hr = renameAccountData.pNewIdentity->Ge"...
0x18008ffa9  mov     [rsp+210h+ProtocolReturnBuffer], rcx
0x18008ffae  mov     r9d, eax
0x18008ffb1  mov     r8d, 0A9h
0x18008ffb7  jmp     loc_180090276
0x18008ffbc  lea     r8, [rbp+110h+var_140]; unsigned __int16 **
0x18008ffc0  mov     rdx, [rsp+210h+var_1C0]; unsigned __int16 *
0x18008ffc5  mov     rcx, [rsp+210h+var_1B8]; this
0x18008ffca  call    ?FormatUserDisplayName@MsaUserExtImpl@@YAJPEBG0PEAPEAGPEAH@Z; MsaUserExtImpl::FormatUserDisplayName(ushort const *,ushort const *,ushort * *,int *)
0x18008ffcf  mov     [rsp+210h+var_1D0], eax
0x18008ffd3  test    eax, eax
0x18008ffd5  jns     short loc_18008FFF1
0x18008ffd7  lea     rcx, aHrExtensionapi_0; "hr = ExtensionAPI::FormatUserDisplayNam"...
0x18008ffde  mov     [rsp+210h+ProtocolReturnBuffer], rcx
0x18008ffe3  mov     r9d, eax
0x18008ffe6  mov     r8d, 0AAh
0x18008ffec  jmp     loc_180090276
0x18008fff1  mov     rax, [rbx]
0x18008fff4  mov     ecx, [rax-10h]
0x18008fff7  lea     ecx, ds:2[rcx*2]
0x18008fffe  mov     [rbp+110h+var_A0], ecx
0x180090001  mov     rcx, rbx
0x180090004  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180090009  mov     [rbp+110h+var_98], rax
0x18009000d  lea     rcx, [rbx+8]
0x180090011  mov     rax, [rcx]
0x180090014  mov     edx, [rax-10h]
0x180090017  lea     edx, ds:2[rdx*2]
0x18009001e  mov     [rbp+110h+var_90], edx
0x180090024  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180090029  mov     [rbp+110h+var_88], rax
0x180090030  mov     rax, [rsp+210h+var_1B8]
0x180090035  mov     ecx, [rax-10h]
0x180090038  lea     ecx, ds:2[rcx*2]
0x18009003f  mov     [rbp+110h+var_80], ecx
0x180090045  lea     rcx, [rsp+210h+var_1B8]
0x18009004a  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18009004f  mov     [rbp+110h+var_78], rax
0x180090056  mov     rax, [rsp+210h+var_1C0]
0x18009005b  mov     ecx, [rax-10h]
0x18009005e  lea     ecx, ds:2[rcx*2]
0x180090065  mov     [rbp+110h+var_70], ecx
0x18009006b  lea     rcx, [rsp+210h+var_1C0]
0x180090070  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180090075  mov     [rbp+110h+var_68], rax
0x18009007c  mov     rcx, [rbp+110h+var_140]
0x180090080  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090084  inc     rax
0x180090087  cmp     [rcx+rax*2], r15w
0x18009008c  jnz     short loc_180090084
0x18009008e  lea     eax, ds:2[rax*2]
0x180090095  mov     [rbp+110h+var_60], eax
0x18009009b  mov     [rbp+110h+var_58], rcx
0x1800900a2  mov     [rbp+110h+var_150], 5
0x1800900aa  lea     rax, [rbp+110h+var_A0]
0x1800900ae  mov     [rbp+110h+var_148], rax
0x1800900b2  lea     r9, [rsp+210h+var_1CC]
0x1800900b7  lea     r8, [rsp+210h+var_1A8]
0x1800900bc  lea     rdx, [rbp+110h+var_150]
0x1800900c0  lea     rcx, [rbp+110h+var_160]
0x1800900c4  call    ??$SerializeObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@YAJAEAVWlidPropertyBagSerializer@@AEAU_WlidPropertyBag@@PEAPEAEPEAK@Z; SerializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(WlidPropertyBagSerializer &,_WlidPropertyBag &,uchar * *,ulong *)
0x1800900c9  mov     [rsp+210h+var_1D0], eax
0x1800900cd  test    eax, eax
0x1800900cf  jns     short loc_1800900EB
0x1800900d1  lea     rcx, aHrSerializeobj; "hr = SerializeObject(serializer, proper"...
0x1800900d8  mov     [rsp+210h+ProtocolReturnBuffer], rcx
0x1800900dd  mov     r9d, eax
0x1800900e0  mov     r8d, 0BBh
0x1800900e6  jmp     loc_180090276
0x1800900eb  lea     r8, [rsp+210h+SecurityMode]; SecurityMode
0x1800900f0  lea     rdx, [rbp+110h+LsaHandle]; LsaHandle
0x1800900f4  lea     rcx, [rsp+210h+LogonProcessName]; LogonProcessName
0x1800900f9  call    cs:__imp_LsaRegisterLogonProcess
0x1800900ff  test    eax, eax
0x180090101  jns     short loc_18009012E
0x180090103  lea     r9, aFailureLsaregi; "Failure - LsaRegisterLogonProcess, HRES"...
0x18009010a  mov     r8d, 0C1h; unsigned int
0x180090110  bts     eax, 1Ch
0x180090114  mov     [rsp+210h+var_1D0], eax
0x180090118  mov     dword ptr [rsp+210h+ProtocolReturnBuffer], eax
0x18009011c  mov     rdx, r12; char *
0x18009011f  mov     ecx, 2; unsigned __int8
0x180090124  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180090129  jmp     loc_180090281
0x18009012e  lea     r8, [rsp+210h+AuthenticationPackage]; AuthenticationPackage
0x180090133  lea     rdx, [rbp+110h+PackageName]; PackageName
0x180090137  mov     rcx, [rbp+110h+LsaHandle]; LsaHandle
0x18009013b  call    cs:__imp_LsaLookupAuthenticationPackage
0x180090141  test    eax, eax
0x180090143  jns     short loc_180090154
0x180090145  lea     r9, aFailureLsalook; "Failure - LsaLookupAuthenticationPackag"...
0x18009014c  mov     r8d, 0C8h
0x180090152  jmp     short loc_180090110
0x180090154  mov     edi, [rsp+210h+var_1CC]
0x180090158  lea     esi, [rdi+1Bh]
0x18009015b  cmp     esi, edi
0x18009015d  jb      loc_180090259
0x180090163  mov     [rsp+210h+var_1D0], r15d
0x180090168  mov     ecx, esi; Size
0x18009016a  call    cs:__imp_malloc
0x180090170  mov     rbx, rax
0x180090173  lea     rcx, [rsp+210h+var_1A0]
0x180090178  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18009017d  mov     [rsp+210h+var_1A0], rbx
0x180090182  test    rbx, rbx
0x180090185  jnz     short loc_180090194
0x180090187  mov     [rsp+210h+var_1D0], 8007000Eh
0x18009018f  jmp     loc_180090281
0x180090194  mov     dword ptr [rbx], 5
0x18009019a  movups  xmm0, cs:xmmword_18017E200
0x1800901a1  movdqu  xmmword ptr [rbx+4], xmm0
0x1800901a6  mov     [rbx+14h], edi
0x1800901a9  mov     r9, rdi
0x1800901ac  lea     rdx, [rsi-1Bh]
0x1800901b0  lea     rcx, [rbx+18h]
0x1800901b4  mov     r8, [rsp+210h+var_1A8]
0x1800901b9  call    SafeCopyMemory
0x1800901be  mov     [rsp+210h+var_1D0], eax
0x1800901c2  test    eax, eax
0x1800901c4  jns     short loc_1800901E0
0x1800901c6  lea     rcx, aHrSafecopymemo_14; "hr = SafeCopyMemory(apCloudProtocolBuff"...
0x1800901cd  mov     [rsp+210h+ProtocolReturnBuffer], rcx
0x1800901d2  mov     r9d, eax
0x1800901d5  mov     r8d, 0D2h
0x1800901db  jmp     loc_180090276
0x1800901e0  lea     rax, [rsp+210h+var_1C4]
0x1800901e5  mov     [rsp+210h+ProtocolStatus], rax; ProtocolStatus
0x1800901ea  lea     rax, [rsp+210h+var_1AC]
0x1800901ef  mov     [rsp+210h+ReturnBufferLength], rax; ReturnBufferLength
0x1800901f4  lea     rax, [rbp+110h+var_158]
0x1800901f8  mov     [rsp+210h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x1800901fd  mov     r9d, esi; SubmitBufferLength
0x180090200  mov     r8, rbx; ProtocolSubmitBuffer
0x180090203  mov     edx, [rsp+210h+AuthenticationPackage]; AuthenticationPackage
0x180090207  mov     rcx, [rbp+110h+LsaHandle]; LsaHandle
0x18009020b  call    cs:__imp_LsaCallAuthenticationPackage
0x180090211  test    eax, eax
0x180090213  jns     short loc_180090231
0x180090215  mov     ecx, eax
0x180090217  bts     ecx, 1Ch
0x18009021b  mov     [rsp+210h+var_1D0], ecx
0x18009021f  lea     r9, aLsacallauthent_0; "LsaCallAuthenticationPackage status = 0"...
0x180090226  mov     r8d, 0D8h
0x18009022c  jmp     loc_180090118
0x180090231  mov     ecx, [rsp+210h+var_1C4]
0x180090235  test    ecx, ecx
0x180090237  jns     short loc_180090281
0x180090239  mov     eax, ecx
0x18009023b  bts     eax, 1Ch
0x18009023f  mov     [rsp+210h+var_1D0], eax
0x180090243  mov     dword ptr [rsp+210h+ProtocolReturnBuffer], ecx
0x180090247  lea     r9, aLsacallauthent_1; "LsaCallAuthenticationPackage protocolSt"...
0x18009024e  mov     r8d, 0DEh
0x180090254  jmp     loc_18009011C
0x180090259  mov     r9d, 80070216h; int
0x18009025f  mov     [rsp+210h+var_1D0], r9d
0x180090264  lea     rax, aHrUlongaddEnco; "hr = ULongAdd(encodedBufferLength, size"...
0x18009026b  mov     [rsp+210h+ProtocolReturnBuffer], rax; char *
0x180090270  mov     r8d, 0CBh; unsigned int
0x180090276  mov     rdx, r13; char *
0x180090279  mov     rcx, r12; char *
0x18009027c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180090281  mov     ebx, [rsp+210h+var_1D0]
0x180090285  mov     r9, [rbp+110h+var_128]; int *
0x180090289  mov     r8, [rbp+110h+var_120]; unsigned __int64
0x18009028d  mov     rdx, [rbp+110h+var_118]
0x180090291  mov     edx, [rdx]; int
0x180090293  mov     rcx, [rbp+110h+var_110]; char *
0x180090297  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18009029c  nop
0x18009029d  lea     rcx, [rbp+110h+var_108]
0x1800902a1  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800902a6  nop
0x1800902a7  lea     rcx, [rbp+110h+var_140]
0x1800902ab  call    ??1?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>::~Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>(void)
0x1800902b0  nop
0x1800902b1  lea     rcx, [rsp+210h+var_1C0]
0x1800902b6  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800902bb  nop
0x1800902bc  lea     rcx, [rsp+210h+var_1B8]
0x1800902c1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800902c6  nop
0x1800902c7  lea     rcx, [rsp+210h+var_1A8]
0x1800902cc  call    ?Clear@?$CMIDLPtr@PEAE@@QEAAXXZ; CMIDLPtr<uchar *>::Clear(void)
0x1800902d1  nop
0x1800902d2  lea     rax, ??_7ISystemStoreLiteFunctions@@6B@; const ISystemStoreLiteFunctions::`vftable'
0x1800902d9  mov     [rbp+110h+var_A8], rax
0x1800902dd  lea     rax, ??_7IComFunctions@@6B@; const IComFunctions::`vftable'
0x1800902e4  mov     [rbp+110h+var_B0], rax
0x1800902e8  lea     rax, ??_7IComFunctions@@6B@; const IComFunctions::`vftable'
0x1800902ef  mov     [rbp+110h+var_B8], rax
0x1800902f3  lea     rax, ??_7IWinApiLite@@6B@; const IWinApiLite::`vftable'
0x1800902fa  mov     [rbp+110h+var_C0], rax
0x1800902fe  lea     rax, ??_7IRPCFunctions@@6B@; const IRPCFunctions::`vftable'
0x180090305  mov     [rbp+110h+var_C8], rax
0x180090309  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x180090310  mov     [rbp+110h+var_D0], rax
0x180090314  lea     rax, ??_7IPPCRLRequest@@6B@; const IPPCRLRequest::`vftable'
0x18009031b  mov     [rbp+110h+var_D8], rax
0x18009031f  lea     rax, ??_7IExecutionContextLite@@6B@; const IExecutionContextLite::`vftable'
0x180090326  mov     [rbp+110h+var_E0], rax
0x18009032a  lea     rcx, [rsp+210h+var_1A0]
0x18009032f  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180090334  nop
0x180090335  lea     rcx, [rbp+110h+LsaHandle]
0x180090339  call    ??1?$Auto@PEAXVLsaHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,LsaHandleFunctor,DummyContext>::~Auto<void *,LsaHandleFunctor,DummyContext>(void)
0x18009033e  mov     eax, ebx
0x180090340  mov     rcx, [rbp+110h+var_50]
0x180090347  xor     rcx, rsp; StackCookie
  ... truncated ...
```
