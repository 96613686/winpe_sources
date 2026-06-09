# SystemStoreLite::GetStoredIdentityProperty(IExecutionContextLite *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180005a60`
- end: `0x1800061a0`
- name: `?GetStoredIdentityProperty@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAG2@Z`
- size: `1856`
- prototype: `__int64 __usercall@<rax>(struct IExecutionContextLite *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180005a20`
- `0x1800153c0`
- `0x18004cca8`

## callees

- `0x180004910`
- `0x180004a7c`
- `0x180004b2c`
- `0x18000535c`
- `0x180005a60`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a300`
- `0x18000a400`
- `0x180011010`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180034ea0`
- `0x18004cd80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800060f7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006140`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800060f7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006140`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005efe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005efe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f61`

## string_xrefs

- `0x180005bcf`: `hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)`
- `0x180006051`: `pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr`
- `0x180005c19`: `hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L"%s\\%s", static_cast<LPWSTR>(pSystemSidString), WLID_REG_STORED_IDENTITY )`
- `0x180006007`: `hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L"%s\\%s", currentSubKey, static_cast<LPCWSTR>(pCurrentUserSidString))`
- `0x180005e2e`: `SID missing from LiveID key. (win32 = 0x%0x)`
- `0x180005ddb`: `StringCchPrintf failed for full user SID path. (localHr = 0x%0x)`
- `0x180005f29`: `hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)`
- `0x180005f43`: `hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemStoreLite::GetStoredIdentityProperty(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  __int64 v9; // rbx
  unsigned __int16 *v10; // r14
  int SystemSidString; // eax
  PPTraceStatus *v12; // rcx
  int v13; // eax
  signed int v14; // eax
  unsigned int i; // edi
  signed int v16; // eax
  int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  const unsigned __int16 *v20; // r9
  unsigned int v21; // r8d
  unsigned __int8 v22; // cl
  __int64 v23; // rcx
  unsigned __int16 *v24; // rax
  int v25; // r9d
  __int64 v26; // rdi
  unsigned __int16 *v27; // rax
  int v28; // eax
  const char *v29; // rax
  unsigned int v30; // r8d
  unsigned __int16 *v31; // rdi
  signed int v32; // eax
  unsigned int v33; // r15d
  unsigned int v34; // ebx
  __int64 v35; // rsi
  unsigned __int64 v36; // rdi
  __int64 v37; // r14
  __int64 v38; // rcx
  unsigned __int64 v39; // rax
  __int64 v40; // rax
  PPTraceStatus *v41; // rcx
  char *v43; // [rsp+20h] [rbp-E0h]
  char *v44; // [rsp+20h] [rbp-E0h]
  char *v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int uBytes; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD uBytes_4[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h]
  __int64 v51; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v55[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v56[3]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v58; // [rsp+D8h] [rbp-28h]
  unsigned int *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  _QWORD v61[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v62[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v63[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v64[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v65[264]; // [rsp+740h] [rbp+640h] BYREF

  v9 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 8LL))(a1);
  v10 = 0;
  memset(v55, 0, sizeof(v55));
  memset_0(v64, 0, 0x208u);
  memset_0(v62, 0, 0x208u);
  memset_0(v63, 0, 0x208u);
  uBytes_4[0] = 0;
  uBytes_4[2] = v9;
  uBytes_4[1] = 0;
  v52 = 0;
  v54 = 0;
  v53 = 0;
  v49 = 0;
  v51 = 0;
  v50 = 0;
  uBytes = 0;
  v46 = 0;
  v61[0] = "SystemStoreLite::GetStoredIdentityProperty";
  v61[1] = &v46;
  v61[2] = 1;
  v61[3] = &qword_1800726F0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetStoredIdentityProperty",
    (const char *)0x8F,
    0,
    (const unsigned __int16 *)v43);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)&v57,
    "SystemStoreLite::GetStoredIdentityProperty",
    &v46,
    0xBu,
    &qword_1800726F8);
  if ( !a2 || !a3 || !a4 )
  {
    v25 = -2147024809;
    v46 = -2147024809;
    v29 = "pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr";
    v30 = 153;
LABEL_58:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      v30,
      v25,
      v29);
    goto LABEL_59;
  }
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  SystemSidString = SystemStoreLite::GetSystemSidString(a1, v55);
  v46 = SystemSidString;
  if ( SystemSidString < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xA3u,
      SystemSidString,
      "hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)");
    goto LABEL_59;
  }
  v13 = StringCchPrintfW(v64, 0x104u, L"%s\\%s", v55[0], L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
  v46 = v13;
  if ( v13 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xACu,
      v13,
      "hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L\"%s\\\\%s\", static_cast<LPWSTR>(pSystemSidString"
      "), WLID_REG_STORED_IDENTITY )");
    goto LABEL_59;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
          v9,
          -2147483645,
          v64,
          0,
          131097,
          uBytes_4);
  if ( v14 == 2 )
  {
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      0xBCu,
      L"System store not found.");
    v46 = -2147023728;
    goto LABEL_59;
  }
  if ( v14 )
  {
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v46 = v14;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xC1u,
      v14,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_59;
  }
  for ( i = 0; ; ++i )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *, int))(*(_QWORD *)v9 + 40LL))(
            v9,
            uBytes_4[0],
            i,
            v62,
            260);
    if ( v16 == 259 )
    {
      v46 = -2147023728;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        0xD5u,
        L"SystemStore property not found.");
      goto LABEL_59;
    }
    if ( v16 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v46 = v16;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xD9u,
        v16,
        "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
      goto LABEL_59;
    }
    v17 = StringCchPrintfW(v63, 0x104u, L"%s\\%s", v62, a2);
    v46 = v17;
    if ( v17 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xE1u,
        v17,
        "hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L\"%s\\\\%s\", currentSubKey, static_cast<LPCWSTR>(pC"
        "urrentUserSidString))");
      goto LABEL_59;
    }
    LODWORD(v44) = 2;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, char *, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v9 + 56LL))(
            v9,
            uBytes_4[0],
            v63,
            a3,
            v44,
            0,
            0,
            &uBytes);
    if ( v18 != 2 )
      break;
    memset_0(v65, 0, 0x208u);
    v56[0] = 0;
    v56[2] = v9;
    v56[1] = 0;
    v19 = StringCchPrintfW(v65, 0x104u, L"%s\\%s", v64, v63);
    if ( v19 >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
              v9,
              -2147483645,
              v65,
              0,
              131097,
              v56);
      if ( !v19 )
        goto LABEL_31;
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v20 = L"SID missing from LiveID key. (win32 = 0x%0x)";
      v21 = 277;
      v22 = 3;
    }
    else
    {
      v20 = L"StringCchPrintf failed for full user SID path. (localHr = 0x%0x)";
      v21 = 262;
      v22 = 2;
    }
    LODWORD(v45) = v19;
    TracePrintW(v22, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v21, v20, v45);
LABEL_31:
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v56);
  }
  if ( v18 )
  {
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v46 = v18;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x11Bu,
      v18,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_59;
  }
  if ( a5 )
  {
    v23 = 130;
    v24 = v62;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v23;
    }
    while ( v23 );
    v25 = -2147024809;
    if ( v23 )
      v25 = 0;
    v46 = v25;
    if ( !v23 )
    {
      v29 = "hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)";
      v30 = 290;
      goto LABEL_58;
    }
    v26 = 2 * (130 - v23);
    v27 = (unsigned __int16 *)LocalAlloc(0x40u, v26 + 2);
    v10 = v27;
    v49 = v27;
    if ( v27 )
    {
      v28 = StringCbCopyW(v27, v26 + 2, v62);
      v46 = v28;
      if ( v28 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
          "SystemStoreLite::GetStoredIdentityProperty",
          0x128u,
          v28,
          "hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)");
        goto LABEL_59;
      }
      goto LABEL_47;
    }
LABEL_48:
    v46 = -2147024882;
    goto LABEL_59;
  }
LABEL_47:
  v31 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
  v52 = v31;
  if ( !v31 )
    goto LABEL_48;
  v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, int, _QWORD, unsigned __int16 *, unsigned int *))(*(_QWORD *)v9 + 56LL))(
          v9,
          uBytes_4[0],
          v63,
          a3,
          2,
          0,
          v31,
          &uBytes);
  if ( v32 )
  {
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    v46 = v32;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x13Bu,
      v32,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
  }
  else
  {
    v52 = 0;
    v53 = 0;
    *a4 = v31;
    if ( a5 )
    {
      v49 = 0;
      v50 = 0;
      *a5 = v10;
    }
  }
LABEL_59:
  v33 = v46;
  v34 = *v59;
  if ( *v59 )
  {
    v35 = v57;
    if ( v57 )
    {
      v36 = v58;
      if ( v58 )
      {
        v37 = v60;
        if ( PPTraceStatus::GetAssertFlag(v12) == 2 )
        {
          if ( (v39 = v34 + 2147023179, (unsigned int)v39 <= 0x24) && (v38 = 0x1000000261LL, _bittest64(&v38, v39))
            || v34 == -2147024890
            || v34 == -2147023834 )
          {
            if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
              McTemplateU0sd_EventWriteTransfer(v38, Telemetry_ErrorVerifier, v37, v34);
            DebugBreak();
          }
        }
        v40 = 0;
        if ( v36 )
        {
          while ( v34 != *(_DWORD *)(v35 + 4 * v40) )
          {
            if ( ++v40 >= v36 )
              goto LABEL_73;
          }
        }
        else
        {
LABEL_73:
          if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
            McTemplateU0sd_EventWriteTransfer(v38, Telemetry_ErrorVerifier, v37, v34);
          if ( PPTraceStatus::GetAssertFlag((PPTraceStatus *)v38) == 1 || PPTraceStatus::GetAssertFlag(v41) == 2 )
            DebugBreak();
        }
      }
    }
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v61);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(&v49);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(&v52);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(uBytes_4);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v55);
  return v33;
}

```

## disassembly

```asm
0x180005a60  push    rbp
0x180005a62  push    rbx
0x180005a63  push    rsi
0x180005a64  push    rdi
0x180005a65  push    r12
0x180005a67  push    r13
0x180005a69  push    r14
0x180005a6b  push    r15
0x180005a6d  lea     rbp, [rsp-868h]
0x180005a75  sub     rsp, 968h
0x180005a7c  mov     rax, cs:__security_cookie
0x180005a83  xor     rax, rsp
0x180005a86  mov     [rbp+8A0h+var_50], rax
0x180005a8d  mov     r13, r9
0x180005a90  mov     r15, r8
0x180005a93  mov     r12, rdx
0x180005a96  mov     rdi, rcx
0x180005a99  mov     rsi, [rbp+8A0h+arg_20]
0x180005aa0  mov     rax, [rcx]
0x180005aa3  mov     rax, [rax+8]
0x180005aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aac  mov     rbx, rax
0x180005aaf  xor     r14d, r14d
0x180005ab2  mov     [rbp+8A0h+var_900], r14
0x180005ab6  mov     [rbp+8A0h+var_8F0], r14
0x180005aba  mov     [rbp+8A0h+var_8F8], r14
0x180005abe  xor     edx, edx; Val
0x180005ac0  mov     r8d, 208h; Size
0x180005ac6  lea     rcx, [rbp+8A0h+var_470]; void *
0x180005acd  call    memset_0
0x180005ad2  xor     edx, edx; Val
0x180005ad4  mov     r8d, 208h; Size
0x180005ada  lea     rcx, [rbp+8A0h+var_890]; void *
0x180005ade  call    memset_0
0x180005ae3  xor     edx, edx; Val
0x180005ae5  mov     r8d, 208h; Size
0x180005aeb  lea     rcx, [rbp+8A0h+var_680]; void *
0x180005af2  call    memset_0
0x180005af7  mov     [rsp+9A0h+uBytes+4], r14
0x180005afc  mov     [rsp+9A0h+var_938], rbx
0x180005b01  mov     [rsp+9A0h+var_940], r14
0x180005b06  mov     [rbp+8A0h+var_918], r14
0x180005b0a  mov     [rbp+8A0h+var_908], r14
0x180005b0e  mov     [rbp+8A0h+var_910], r14
0x180005b12  mov     [rsp+9A0h+var_930], r14
0x180005b17  xor     eax, eax
0x180005b19  mov     [rbp+8A0h+var_920], rax
0x180005b1d  mov     [rsp+9A0h+var_928], rax
0x180005b22  mov     dword ptr [rsp+9A0h+uBytes], eax
0x180005b26  mov     [rsp+9A0h+var_950], eax
0x180005b2a  lea     rcx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x180005b31  mov     [rbp+8A0h+var_8B0], rcx
0x180005b35  lea     rax, [rsp+9A0h+var_950]
0x180005b3a  mov     [rbp+8A0h+var_8A8], rax
0x180005b3e  mov     [rbp+8A0h+var_8A0], 1
0x180005b46  lea     rax, qword_1800726F0
0x180005b4d  mov     [rbp+8A0h+var_898], rax
0x180005b51  xor     r9d, r9d; unsigned int
0x180005b54  mov     r8d, 8Fh; char *
0x180005b5a  mov     rdx, rcx; char *
0x180005b5d  lea     rcx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180005b64  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180005b69  nop
0x180005b6a  lea     rax, qword_1800726F8
0x180005b71  mov     [rsp+9A0h+var_980], rax; int *
0x180005b76  mov     r9d, 0Bh; unsigned __int64
0x180005b7c  lea     r8, [rsp+9A0h+var_950]; int *
0x180005b81  lea     rdx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x180005b88  lea     rcx, [rbp+8A0h+var_8D0]; this
0x180005b8c  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180005b91  nop
0x180005b92  test    r12, r12
0x180005b95  jz      loc_180006046
0x180005b9b  test    r15, r15
0x180005b9e  jz      loc_180006046
0x180005ba4  test    r13, r13
0x180005ba7  jz      loc_180006046
0x180005bad  xor     eax, eax
0x180005baf  mov     [r13+0], rax
0x180005bb3  test    rsi, rsi
0x180005bb6  jz      short loc_180005BBB
0x180005bb8  mov     [rsi], rax
0x180005bbb  lea     rdx, [rbp+8A0h+var_900]; unsigned __int16 **
0x180005bbf  mov     rcx, rdi; struct IExecutionContextLite *
0x180005bc2  call    ?GetSystemSidString@SystemStoreLite@@CAJPEAVIExecutionContextLite@@PEAPEAG@Z; SystemStoreLite::GetSystemSidString(IExecutionContextLite *,ushort * *)
0x180005bc7  mov     [rsp+9A0h+var_950], eax
0x180005bcb  test    eax, eax
0x180005bcd  jns     short loc_180005BE9
0x180005bcf  lea     r8, aHrSystemstorel_1; "hr = SystemStoreLite::GetSystemSidStrin"...
0x180005bd6  mov     [rsp+9A0h+var_980], r8
0x180005bdb  mov     r9d, eax
0x180005bde  mov     r8d, 0A3h
0x180005be4  jmp     loc_180006063
0x180005be9  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\IdentityCRL\\Store"...
0x180005bf0  mov     [rsp+9A0h+var_980], rax
0x180005bf5  mov     r9, [rbp+8A0h+var_900]
0x180005bf9  lea     r8, aSS; "%s\\%s"
0x180005c00  mov     edx, 104h; unsigned __int64
0x180005c05  lea     rcx, [rbp+8A0h+var_470]; unsigned __int16 *
0x180005c0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c11  mov     [rsp+9A0h+var_950], eax
0x180005c15  test    eax, eax
0x180005c17  jns     short loc_180005C33
0x180005c19  lea     rcx, aHrStringcchpri; "hr = StringCchPrintfW( storedIdentities"...
0x180005c20  mov     [rsp+9A0h+var_980], rcx
0x180005c25  mov     r9d, eax
0x180005c28  mov     r8d, 0ACh
0x180005c2e  jmp     loc_180006063
0x180005c33  mov     rax, [rbx]
0x180005c36  lea     rcx, [rsp+9A0h+uBytes+4]
0x180005c3b  mov     [rsp+9A0h+var_978], rcx
0x180005c40  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x180005c48  xor     r9d, r9d
0x180005c4b  lea     r8, [rbp+8A0h+var_470]
0x180005c52  mov     rdx, 0FFFFFFFF80000003h
0x180005c59  mov     rcx, rbx
0x180005c5c  mov     rax, [rax+50h]
0x180005c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c65  cmp     eax, 2
0x180005c68  jnz     short loc_180005C95
0x180005c6a  lea     r9, aSystemStoreNot; "System store not found."
0x180005c71  mov     r8d, 0BCh; unsigned int
0x180005c77  lea     rdx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180005c7e  mov     ecx, 3; unsigned __int8
0x180005c83  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180005c88  mov     [rsp+9A0h+var_950], 80070490h
0x180005c90  jmp     loc_180006076
0x180005c95  test    eax, eax
0x180005c97  jz      short loc_180005CC5
0x180005c99  jle     short loc_180005CA3
0x180005c9b  movzx   eax, ax
0x180005c9e  or      eax, 80070000h
0x180005ca3  mov     [rsp+9A0h+var_950], eax
0x180005ca7  test    eax, eax
0x180005ca9  jns     short loc_180005CC5
0x180005cab  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x180005cb2  mov     [rsp+9A0h+var_980], rcx
0x180005cb7  mov     r9d, eax
0x180005cba  mov     r8d, 0C1h
0x180005cc0  jmp     loc_180006063
0x180005cc5  xor     edi, edi
0x180005cc7  nop     word ptr [rax+rax+00000000h]
0x180005cd0  mov     rax, [rbx]
0x180005cd3  mov     dword ptr [rsp+9A0h+var_980], 104h
0x180005cdb  lea     r9, [rbp+8A0h+var_890]
0x180005cdf  mov     r8d, edi
0x180005ce2  mov     rdx, [rsp+9A0h+uBytes+4]
0x180005ce7  mov     rcx, rbx
0x180005cea  mov     rax, [rax+28h]
0x180005cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf3  cmp     eax, 103h
0x180005cf8  jz      loc_18000601E
0x180005cfe  test    eax, eax
0x180005d00  jz      short loc_180005D18
0x180005d02  jle     short loc_180005D0C
0x180005d04  movzx   eax, ax
0x180005d07  or      eax, 80070000h
0x180005d0c  mov     [rsp+9A0h+var_950], eax
0x180005d10  test    eax, eax
0x180005d12  js      loc_180005E61
0x180005d18  mov     [rsp+9A0h+var_980], r12
0x180005d1d  lea     r9, [rbp+8A0h+var_890]
0x180005d21  lea     r8, aSS; "%s\\%s"
0x180005d28  mov     edx, 104h; unsigned __int64
0x180005d2d  lea     rcx, [rbp+8A0h+var_680]; unsigned __int16 *
0x180005d34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d39  mov     [rsp+9A0h+var_950], eax
0x180005d3d  test    eax, eax
0x180005d3f  js      loc_180006007
0x180005d45  mov     rax, [rbx]
0x180005d48  lea     rcx, [rsp+9A0h+uBytes]
0x180005d4d  mov     [rsp+9A0h+var_968], rcx
0x180005d52  xor     ecx, ecx
0x180005d54  mov     [rsp+9A0h+var_970], rcx
0x180005d59  mov     [rsp+9A0h+var_978], rcx
0x180005d5e  mov     dword ptr [rsp+9A0h+var_980], 2
0x180005d66  mov     r9, r15
0x180005d69  lea     r8, [rbp+8A0h+var_680]
0x180005d70  mov     rdx, [rsp+9A0h+uBytes+4]
0x180005d75  mov     rcx, rbx
0x180005d78  mov     rax, [rax+38h]
0x180005d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d81  cmp     eax, 2
0x180005d84  jnz     loc_180005E7B
0x180005d8a  xor     edx, edx; Val
0x180005d8c  mov     r8d, 208h; Size
0x180005d92  lea     rcx, [rbp+8A0h+var_260]; void *
0x180005d99  call    memset_0
0x180005d9e  xor     eax, eax
0x180005da0  mov     [rbp+8A0h+var_8E8], rax
0x180005da4  mov     [rbp+8A0h+var_8D8], rbx
0x180005da8  mov     [rbp+8A0h+var_8E0], rax
0x180005dac  lea     rax, [rbp+8A0h+var_680]
0x180005db3  mov     [rsp+9A0h+var_980], rax
0x180005db8  lea     r9, [rbp+8A0h+var_470]
0x180005dbf  lea     r8, aSS; "%s\\%s"
0x180005dc6  mov     edx, 104h; unsigned __int64
0x180005dcb  lea     rcx, [rbp+8A0h+var_260]; unsigned __int16 *
0x180005dd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005dd7  test    eax, eax
0x180005dd9  jns     short loc_180005DEF
0x180005ddb  lea     r9, aStringcchprint; "StringCchPrintf failed for full user SI"...
0x180005de2  mov     r8d, 106h
0x180005de8  mov     ecx, 2
0x180005ded  jmp     short loc_180005E40
0x180005def  mov     rax, [rbx]
0x180005df2  lea     rcx, [rbp+8A0h+var_8E8]
0x180005df6  mov     [rsp+9A0h+var_978], rcx
0x180005dfb  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x180005e03  xor     r9d, r9d
0x180005e06  lea     r8, [rbp+8A0h+var_260]
0x180005e0d  mov     rdx, 0FFFFFFFF80000003h
0x180005e14  mov     rcx, rbx
0x180005e17  mov     rax, [rax+50h]
0x180005e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e20  test    eax, eax
0x180005e22  jz      short loc_180005E51
0x180005e24  jle     short loc_180005E2E
0x180005e26  movzx   eax, ax
0x180005e29  or      eax, 80070000h
0x180005e2e  lea     r9, aSidMissingFrom; "SID missing from LiveID key. (win32 = 0"...
0x180005e35  mov     r8d, 115h; unsigned int
0x180005e3b  mov     ecx, 3; unsigned __int8
0x180005e40  mov     dword ptr [rsp+9A0h+var_980], eax
0x180005e44  lea     rdx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180005e4b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180005e50  nop
0x180005e51  lea     rcx, [rbp+8A0h+var_8E8]
0x180005e55  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x180005e5a  inc     edi
0x180005e5c  jmp     loc_180005CD0
0x180005e61  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x180005e68  mov     [rsp+9A0h+var_980], rcx
0x180005e6d  mov     r9d, eax
0x180005e70  mov     r8d, 0D9h
0x180005e76  jmp     loc_180006063
0x180005e7b  test    eax, eax
0x180005e7d  jz      short loc_180005EAB
0x180005e7f  jle     short loc_180005E89
0x180005e81  movzx   eax, ax
0x180005e84  or      eax, 80070000h
0x180005e89  mov     [rsp+9A0h+var_950], eax
0x180005e8d  test    eax, eax
0x180005e8f  jns     short loc_180005EAB
0x180005e91  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x180005e98  mov     [rsp+9A0h+var_980], rcx
0x180005e9d  mov     r9d, eax
0x180005ea0  mov     r8d, 11Bh
0x180005ea6  jmp     loc_180006063
0x180005eab  test    rsi, rsi
0x180005eae  jz      loc_180005F55
0x180005eb4  mov     edx, 82h
0x180005eb9  mov     ecx, edx
0x180005ebb  lea     rax, [rbp+8A0h+var_890]
0x180005ebf  nop
0x180005ec0  cmp     word ptr [rax], 0
0x180005ec4  jz      short loc_180005ED0
0x180005ec6  add     rax, 2
0x180005eca  sub     rcx, 1
0x180005ece  jnz     short loc_180005EC0
0x180005ed0  mov     r9d, 80070057h
0x180005ed6  xor     r12d, r12d
0x180005ed9  test    rcx, rcx
0x180005edc  cmovnz  r9d, r12d
0x180005ee0  mov     [rsp+9A0h+var_950], r9d
0x180005ee5  jz      short loc_180005F43
0x180005ee7  sub     rdx, rcx
0x180005eea  lea     rdi, [rdx+rdx]
0x180005eee  test    rcx, rcx
0x180005ef1  cmovz   rdi, r12
0x180005ef5  lea     rdx, [rdi+2]; uBytes
0x180005ef9  mov     ecx, 40h ; '@'; uFlags
0x180005efe  call    cs:__imp_LocalAlloc
0x180005f04  mov     r14, rax
0x180005f07  mov     [rsp+9A0h+var_930], rax
0x180005f0c  test    rax, rax
0x180005f0f  jz      short loc_180005F73
0x180005f11  lea     r8, [rbp+8A0h+var_890]; unsigned __int16 *
0x180005f15  lea     rdx, [rdi+2]; unsigned __int64
0x180005f19  mov     rcx, rax; unsigned __int16 *
0x180005f1c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180005f21  mov     [rsp+9A0h+var_950], eax
0x180005f25  test    eax, eax
0x180005f27  jns     short loc_180005F58
0x180005f29  lea     rcx, aHrStringcbcopy; "hr = StringCbCopyW(pLiveUserName, liveU"...
0x180005f30  mov     [rsp+9A0h+var_980], rcx
0x180005f35  mov     r9d, eax
0x180005f38  mov     r8d, 128h
0x180005f3e  jmp     loc_180006063
0x180005f43  lea     rax, aHrStringcbleng_1; "hr = StringCbLengthW(currentSubKey, MAX"...
0x180005f4a  mov     r8d, 122h
0x180005f50  jmp     loc_18000605E
0x180005f55  xor     r12d, r12d
0x180005f58  mov     edx, dword ptr [rsp+9A0h+uBytes]; uBytes
0x180005f5c  mov     ecx, 40h ; '@'; uFlags
0x180005f61  call    cs:__imp_LocalAlloc
0x180005f67  mov     rdi, rax
0x180005f6a  mov     [rbp+8A0h+var_918], rax
0x180005f6e  test    rax, rax
0x180005f71  jnz     short loc_180005F80
  ... truncated ...
```
