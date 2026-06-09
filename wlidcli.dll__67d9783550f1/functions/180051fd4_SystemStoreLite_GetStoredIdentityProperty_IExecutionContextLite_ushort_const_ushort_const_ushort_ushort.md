# SystemStoreLite::GetStoredIdentityProperty(IExecutionContextLite *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180051fd4`
- end: `0x18005267d`
- name: `?GetStoredIdentityProperty@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAG2@Z`
- size: `1705`
- prototype: `__int64 __usercall@<rax>(struct IExecutionContextLite *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180051a60`
- `0x180051efc`
- `0x180052a18`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180008bb4`
- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180021a90`
- `0x180029118`
- `0x180051250`
- `0x1800512f8`
- `0x180051af8`
- `0x180051fd4`
- `0x180052684`
- `0x1800530e4`
- `0x180053890`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052475`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800524df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052475`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800524df`

## string_xrefs

- `0x1800525de`: `pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr`
- `0x18005213e`: `hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)`
- `0x180052188`: `hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L"%s\\%s", static_cast<LPWSTR>(pSystemSidString), WLID_REG_STORED_IDENTITY )`
- `0x180052597`: `hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L"%s\\%s", currentSubKey, static_cast<LPCWSTR>(pCurrentUserSidString))`
- `0x180052348`: `StringCchPrintf failed for full user SID path. (localHr = 0x%0x)`
- `0x18005239b`: `SID missing from LiveID key. (win32 = 0x%0x)`
- `0x1800524c4`: `hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)`
- `0x1800524aa`: `hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)`

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
  __int64 v9; // rdi
  unsigned __int16 *v10; // r14
  int SystemSidString; // eax
  int v12; // eax
  signed int v13; // eax
  unsigned int i; // ebx
  signed int v15; // eax
  int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  const unsigned __int16 *v19; // r9
  unsigned int v20; // r8d
  unsigned __int8 v21; // cl
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  int v24; // r9d
  __int64 v25; // rbx
  int v26; // eax
  const char *v27; // rax
  unsigned int v28; // r8d
  unsigned __int16 *v29; // rbx
  signed int v30; // eax
  unsigned int v31; // ebx
  char *v33; // [rsp+20h] [rbp-E0h]
  char *v34; // [rsp+20h] [rbp-E0h]
  char *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD uBytes[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  _QWORD v43[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v45[3]; // [rsp+B8h] [rbp-48h] BYREF
  int *v46[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v47[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v48[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v49[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v50[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v51[264]; // [rsp+740h] [rbp+640h] BYREF

  v9 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 8LL))(a1);
  v10 = 0;
  memset(v44, 0, sizeof(v44));
  memset_0(v50, 0, 0x208u);
  memset_0(v48, 0, 0x208u);
  memset_0(v49, 0, 0x208u);
  v43[0] = 0;
  v43[2] = v9;
  v43[1] = 0;
  v40 = 0;
  v42 = 0;
  v41 = 0;
  v39 = 0;
  v38 = 0;
  memset(uBytes, 0, sizeof(uBytes));
  v36 = 0;
  v47[0] = "SystemStoreLite::GetStoredIdentityProperty";
  v47[1] = &v36;
  v47[2] = 1;
  v47[3] = &dword_1800819EC;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetStoredIdentityProperty",
    (const char *)0x8F,
    0,
    (const unsigned __int16 *)v33);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v46,
    "SystemStoreLite::GetStoredIdentityProperty",
    &v36,
    0xBu,
    &qword_1800819C0);
  if ( !a2 || !a3 || !a4 )
  {
    v36 = -2147024809;
    v27 = "pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr";
    v24 = -2147024809;
    v28 = 153;
LABEL_60:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      v28,
      v24,
      v27);
    goto LABEL_61;
  }
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  SystemSidString = SystemStoreLite::GetSystemSidString(a1, v44);
  v36 = SystemSidString;
  if ( SystemSidString < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xA3u,
      SystemSidString,
      "hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)");
    goto LABEL_61;
  }
  v12 = StringCchPrintfW(v50, 0x104u, L"%s\\%s", v44[0], L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
  v36 = v12;
  if ( v12 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xACu,
      v12,
      "hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L\"%s\\\\%s\", static_cast<LPWSTR>(pSystemSidString"
      "), WLID_REG_STORED_IDENTITY )");
    goto LABEL_61;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
          v9,
          -2147483645,
          v50,
          0,
          131097,
          v43);
  if ( v13 == 2 )
  {
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      0xBCu,
      L"System store not found.");
    v36 = -2147023728;
    goto LABEL_61;
  }
  if ( v13 )
  {
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v36 = v13;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xC1u,
      v13,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_61;
  }
  for ( i = 0; ; ++i )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *, int))(*(_QWORD *)v9 + 40LL))(
            v9,
            v43[0],
            i,
            v48,
            260);
    if ( v15 == 259 )
    {
      v36 = -2147023728;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        0xD5u,
        L"SystemStore property not found.");
      goto LABEL_61;
    }
    if ( v15 )
    {
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v36 = v15;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xD9u,
        v15,
        "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
      goto LABEL_61;
    }
    v16 = StringCchPrintfW(v49, 0x104u, L"%s\\%s", v48, a2);
    v36 = v16;
    if ( v16 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xE1u,
        v16,
        "hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L\"%s\\\\%s\", currentSubKey, static_cast<LPCWSTR>(pC"
        "urrentUserSidString))");
      goto LABEL_61;
    }
    LODWORD(v34) = 2;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, char *, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)v9 + 56LL))(
            v9,
            v43[0],
            v49,
            a3,
            v34,
            0,
            0,
            uBytes);
    if ( v17 != 2 )
      break;
    memset_0(v51, 0, 0x208u);
    v45[0] = 0;
    v45[2] = v9;
    v45[1] = 0;
    v18 = StringCchPrintfW(v51, 0x104u, L"%s\\%s", v50, v49);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
              v9,
              -2147483645,
              v51,
              0,
              131097,
              v45);
      if ( !v18 )
        goto LABEL_32;
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v19 = L"SID missing from LiveID key. (win32 = 0x%0x)";
      v20 = 277;
      v21 = 3;
    }
    else
    {
      v19 = L"StringCchPrintf failed for full user SID path. (localHr = 0x%0x)";
      v20 = 262;
      v21 = 2;
    }
    LODWORD(v35) = v18;
    TracePrintW(v21, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v20, v19, v35);
LABEL_32:
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v45);
  }
  if ( v17 )
  {
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v36 = v17;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x11Bu,
      v17,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_61;
  }
  if ( a5 )
  {
    v22 = 130;
    v23 = v48;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    v24 = v22 == 0 ? 0x80070057 : 0;
    v36 = v24;
    if ( !v22 )
    {
      v27 = "hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)";
      v28 = 290;
      goto LABEL_60;
    }
    v25 = -(__int64)(v22 != 0) & (2 * (130 - v22));
    v10 = (unsigned __int16 *)LocalAlloc(0x40u, v25 + 2);
    Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&uBytes[1]);
    *(_QWORD *)&uBytes[1] = v10;
    if ( v10 )
    {
      v26 = StringCbCopyW(v10, v25 + 2, v48);
      v36 = v26;
      if ( v26 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
          "SystemStoreLite::GetStoredIdentityProperty",
          0x128u,
          v26,
          "hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)");
        goto LABEL_61;
      }
      goto LABEL_48;
    }
LABEL_49:
    v36 = -2147024882;
    goto LABEL_61;
  }
LABEL_48:
  v29 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes[0]);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v40);
  v40 = v29;
  if ( !v29 )
    goto LABEL_49;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, int, _QWORD, unsigned __int16 *, _DWORD *))(*(_QWORD *)v9 + 56LL))(
          v9,
          v43[0],
          v49,
          a3,
          2,
          0,
          v29,
          uBytes);
  if ( v30 )
  {
    if ( v30 > 0 )
      v30 = (unsigned __int16)v30 | 0x80070000;
    v36 = v30;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x13Bu,
      v30,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
  }
  else
  {
    v40 = 0;
    v41 = 0;
    *a4 = v29;
    if ( a5 )
    {
      *(_QWORD *)&uBytes[1] = 0;
      v38 = 0;
      *a5 = v10;
    }
  }
LABEL_61:
  v31 = v36;
  ErrorVerifier::CheckAgainstList((const char *)v46[3], *v46[2], (unsigned __int64)v46[1], v46[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v47);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v43);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  return v31;
}

```

## disassembly

```asm
0x180051fd4  push    rbp
0x180051fd6  push    rbx
0x180051fd7  push    rsi
0x180051fd8  push    rdi
0x180051fd9  push    r12
0x180051fdb  push    r13
0x180051fdd  push    r14
0x180051fdf  push    r15
0x180051fe1  lea     rbp, [rsp-868h]
0x180051fe9  sub     rsp, 968h
0x180051ff0  mov     rax, cs:__security_cookie
0x180051ff7  xor     rax, rsp
0x180051ffa  mov     [rbp+8A0h+var_50], rax
0x180052001  mov     r15, r9
0x180052004  mov     r12, r8
0x180052007  mov     r13, rdx
0x18005200a  mov     rbx, rcx
0x18005200d  mov     rsi, [rbp+8A0h+arg_20]
0x180052014  mov     rax, [rcx]
0x180052017  mov     rax, [rax+8]
0x18005201b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052020  mov     rdi, rax
0x180052023  xor     r14d, r14d
0x180052026  mov     [rbp+8A0h+var_900], r14
0x18005202a  mov     [rbp+8A0h+var_8F0], r14
0x18005202e  mov     [rbp+8A0h+var_8F8], r14
0x180052032  xor     edx, edx; Val
0x180052034  mov     r8d, 208h; Size
0x18005203a  lea     rcx, [rbp+8A0h+var_470]; void *
0x180052041  call    memset_0
0x180052046  xor     edx, edx; Val
0x180052048  mov     r8d, 208h; Size
0x18005204e  lea     rcx, [rbp+8A0h+var_890]; void *
0x180052052  call    memset_0
0x180052057  xor     edx, edx; Val
0x180052059  mov     r8d, 208h; Size
0x18005205f  lea     rcx, [rbp+8A0h+var_680]; void *
0x180052066  call    memset_0
0x18005206b  mov     [rbp+8A0h+var_918], r14
0x18005206f  mov     [rbp+8A0h+var_908], rdi
0x180052073  mov     [rbp+8A0h+var_910], r14
0x180052077  mov     [rsp+9A0h+var_930], r14
0x18005207c  mov     [rbp+8A0h+var_920], r14
0x180052080  mov     [rsp+9A0h+var_928], r14
0x180052085  mov     qword ptr [rsp+9A0h+uBytes+4], r14
0x18005208a  xor     eax, eax
0x18005208c  mov     [rsp+9A0h+var_938], rax
0x180052091  mov     [rsp+9A0h+var_940], rax
0x180052096  mov     dword ptr [rsp+9A0h+uBytes], eax
0x18005209a  mov     [rsp+9A0h+var_950], eax
0x18005209e  lea     rcx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x1800520a5  mov     [rbp+8A0h+var_8B0], rcx
0x1800520a9  lea     rax, [rsp+9A0h+var_950]
0x1800520ae  mov     [rbp+8A0h+var_8A8], rax
0x1800520b2  mov     [rbp+8A0h+var_8A0], 1
0x1800520ba  lea     rax, dword_1800819EC
0x1800520c1  mov     [rbp+8A0h+var_898], rax
0x1800520c5  xor     r9d, r9d; unsigned int
0x1800520c8  mov     r8d, 8Fh; char *
0x1800520ce  mov     rdx, rcx; char *
0x1800520d1  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800520d8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800520dd  nop
0x1800520de  lea     rax, qword_1800819C0
0x1800520e5  mov     [rsp+9A0h+var_980], rax; int *
0x1800520ea  lea     r9d, [r14+0Bh]; unsigned __int64
0x1800520ee  lea     r8, [rsp+9A0h+var_950]; int *
0x1800520f3  lea     rdx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x1800520fa  lea     rcx, [rbp+8A0h+var_8D0]; this
0x1800520fe  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180052103  nop
0x180052104  test    r13, r13
0x180052107  jz      loc_1800525D6
0x18005210d  test    r12, r12
0x180052110  jz      loc_1800525D6
0x180052116  test    r15, r15
0x180052119  jz      loc_1800525D6
0x18005211f  mov     [r15], r14
0x180052122  test    rsi, rsi
0x180052125  jz      short loc_18005212A
0x180052127  mov     [rsi], r14
0x18005212a  lea     rdx, [rbp+8A0h+var_900]; unsigned __int16 **
0x18005212e  mov     rcx, rbx; struct IExecutionContextLite *
0x180052131  call    ?GetSystemSidString@SystemStoreLite@@CAJPEAVIExecutionContextLite@@PEAPEAG@Z; SystemStoreLite::GetSystemSidString(IExecutionContextLite *,ushort * *)
0x180052136  mov     [rsp+9A0h+var_950], eax
0x18005213a  test    eax, eax
0x18005213c  jns     short loc_180052158
0x18005213e  lea     r8, aHrSystemstorel_0; "hr = SystemStoreLite::GetSystemSidStrin"...
0x180052145  mov     [rsp+9A0h+var_980], r8
0x18005214a  mov     r9d, eax
0x18005214d  mov     r8d, 0A3h
0x180052153  jmp     loc_1800525F6
0x180052158  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18005215f  mov     [rsp+9A0h+var_980], rax
0x180052164  mov     r9, [rbp+8A0h+var_900]
0x180052168  lea     r8, aSS; "%s\\%s"
0x18005216f  mov     edx, 104h; unsigned __int64
0x180052174  lea     rcx, [rbp+8A0h+var_470]; unsigned __int16 *
0x18005217b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052180  mov     [rsp+9A0h+var_950], eax
0x180052184  test    eax, eax
0x180052186  jns     short loc_1800521A2
0x180052188  lea     rcx, aHrStringcchpri; "hr = StringCchPrintfW( storedIdentities"...
0x18005218f  mov     [rsp+9A0h+var_980], rcx
0x180052194  mov     r9d, eax
0x180052197  mov     r8d, 0ACh
0x18005219d  jmp     loc_1800525F6
0x1800521a2  mov     rax, [rdi]
0x1800521a5  lea     rcx, [rbp+8A0h+var_918]
0x1800521a9  mov     [rsp+9A0h+var_978], rcx
0x1800521ae  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x1800521b6  xor     r9d, r9d
0x1800521b9  lea     r8, [rbp+8A0h+var_470]
0x1800521c0  mov     rdx, 0FFFFFFFF80000003h
0x1800521c7  mov     rcx, rdi
0x1800521ca  mov     rax, [rax+50h]
0x1800521ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521d3  cmp     eax, 2
0x1800521d6  jnz     short loc_180052201
0x1800521d8  lea     r9, aSystemStoreNot; "System store not found."
0x1800521df  mov     r8d, 0BCh; unsigned int
0x1800521e5  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800521ec  lea     ecx, [rax+1]; unsigned __int8
0x1800521ef  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800521f4  mov     [rsp+9A0h+var_950], 80070490h
0x1800521fc  jmp     loc_180052609
0x180052201  test    eax, eax
0x180052203  jz      short loc_180052231
0x180052205  jle     short loc_18005220F
0x180052207  movzx   eax, ax
0x18005220a  or      eax, 80070000h
0x18005220f  mov     [rsp+9A0h+var_950], eax
0x180052213  test    eax, eax
0x180052215  jns     short loc_180052231
0x180052217  lea     rcx, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18005221e  mov     [rsp+9A0h+var_980], rcx
0x180052223  mov     r9d, eax
0x180052226  mov     r8d, 0C1h
0x18005222c  jmp     loc_1800525F6
0x180052231  xor     ebx, ebx
0x180052233  mov     rax, [rdi]
0x180052236  mov     dword ptr [rsp+9A0h+var_980], 104h
0x18005223e  lea     r9, [rbp+8A0h+var_890]
0x180052242  mov     r8d, ebx
0x180052245  mov     rdx, [rbp+8A0h+var_918]
0x180052249  mov     rcx, rdi
0x18005224c  mov     rax, [rax+28h]
0x180052250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052255  cmp     eax, 103h
0x18005225a  jz      loc_1800525AE
0x180052260  test    eax, eax
0x180052262  jz      short loc_18005227A
0x180052264  jle     short loc_18005226E
0x180052266  movzx   eax, ax
0x180052269  or      eax, 80070000h
0x18005226e  mov     [rsp+9A0h+var_950], eax
0x180052272  test    eax, eax
0x180052274  js      loc_1800523CE
0x18005227a  mov     [rsp+9A0h+var_980], r13
0x18005227f  lea     r9, [rbp+8A0h+var_890]
0x180052283  lea     r8, aSS; "%s\\%s"
0x18005228a  mov     edx, 104h; unsigned __int64
0x18005228f  lea     rcx, [rbp+8A0h+var_680]; unsigned __int16 *
0x180052296  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005229b  mov     [rsp+9A0h+var_950], eax
0x18005229f  test    eax, eax
0x1800522a1  js      loc_180052597
0x1800522a7  mov     rax, [rdi]
0x1800522aa  lea     rcx, [rsp+9A0h+uBytes]
0x1800522af  mov     [rsp+9A0h+var_968], rcx
0x1800522b4  mov     [rsp+9A0h+var_970], 0
0x1800522bd  mov     [rsp+9A0h+var_978], 0
0x1800522c6  mov     dword ptr [rsp+9A0h+var_980], 2
0x1800522ce  mov     r9, r12
0x1800522d1  lea     r8, [rbp+8A0h+var_680]
0x1800522d8  mov     rdx, [rbp+8A0h+var_918]
0x1800522dc  mov     rcx, rdi
0x1800522df  mov     rax, [rax+38h]
0x1800522e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522e8  cmp     eax, 2
0x1800522eb  jnz     loc_1800523E8
0x1800522f1  xor     edx, edx; Val
0x1800522f3  mov     r8d, 208h; Size
0x1800522f9  lea     rcx, [rbp+8A0h+var_260]; void *
0x180052300  call    memset_0
0x180052305  mov     [rbp+8A0h+var_8E8], 0
0x18005230d  mov     [rbp+8A0h+var_8D8], rdi
0x180052311  mov     [rbp+8A0h+var_8E0], 0
0x180052319  lea     rax, [rbp+8A0h+var_680]
0x180052320  mov     [rsp+9A0h+var_980], rax
0x180052325  lea     r9, [rbp+8A0h+var_470]
0x18005232c  lea     r8, aSS; "%s\\%s"
0x180052333  mov     edx, 104h; unsigned __int64
0x180052338  lea     rcx, [rbp+8A0h+var_260]; unsigned __int16 *
0x18005233f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052344  test    eax, eax
0x180052346  jns     short loc_18005235C
0x180052348  lea     r9, aStringcchprint; "StringCchPrintf failed for full user SI"...
0x18005234f  mov     r8d, 106h
0x180052355  mov     ecx, 2
0x18005235a  jmp     short loc_1800523AD
0x18005235c  mov     rax, [rdi]
0x18005235f  lea     rcx, [rbp+8A0h+var_8E8]
0x180052363  mov     [rsp+9A0h+var_978], rcx
0x180052368  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x180052370  xor     r9d, r9d
0x180052373  lea     r8, [rbp+8A0h+var_260]
0x18005237a  mov     rdx, 0FFFFFFFF80000003h
0x180052381  mov     rcx, rdi
0x180052384  mov     rax, [rax+50h]
0x180052388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005238d  test    eax, eax
0x18005238f  jz      short loc_1800523BE
0x180052391  jle     short loc_18005239B
0x180052393  movzx   eax, ax
0x180052396  or      eax, 80070000h
0x18005239b  lea     r9, aSidMissingFrom; "SID missing from LiveID key. (win32 = 0"...
0x1800523a2  mov     r8d, 115h; unsigned int
0x1800523a8  mov     ecx, 3; unsigned __int8
0x1800523ad  mov     dword ptr [rsp+9A0h+var_980], eax
0x1800523b1  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800523b8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800523bd  nop
0x1800523be  lea     rcx, [rbp+8A0h+var_8E8]
0x1800523c2  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800523c7  inc     ebx
0x1800523c9  jmp     loc_180052233
0x1800523ce  lea     rcx, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x1800523d5  mov     [rsp+9A0h+var_980], rcx
0x1800523da  mov     r9d, eax
0x1800523dd  mov     r8d, 0D9h
0x1800523e3  jmp     loc_1800525F6
0x1800523e8  xor     r13d, r13d
0x1800523eb  test    eax, eax
0x1800523ed  jz      short loc_18005241B
0x1800523ef  jle     short loc_1800523F9
0x1800523f1  movzx   eax, ax
0x1800523f4  or      eax, 80070000h
0x1800523f9  mov     [rsp+9A0h+var_950], eax
0x1800523fd  test    eax, eax
0x1800523ff  jns     short loc_18005241B
0x180052401  lea     rcx, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x180052408  mov     [rsp+9A0h+var_980], rcx
0x18005240d  mov     r9d, eax
0x180052410  mov     r8d, 11Bh
0x180052416  jmp     loc_1800525F6
0x18005241b  test    rsi, rsi
0x18005241e  jz      loc_1800524D6
0x180052424  mov     edx, 82h
0x180052429  mov     ecx, edx
0x18005242b  lea     rax, [rbp+8A0h+var_890]
0x18005242f  cmp     [rax], r13w
0x180052433  jz      short loc_18005243F
0x180052435  add     rax, 2
0x180052439  sub     rcx, 1
0x18005243d  jnz     short loc_18005242F
0x18005243f  mov     rax, rcx
0x180052442  neg     rax
0x180052445  sbb     r9d, r9d
0x180052448  not     r9d
0x18005244b  and     r9d, 80070057h
0x180052452  mov     [rsp+9A0h+var_950], r9d
0x180052457  test    rcx, rcx
0x18005245a  jz      short loc_1800524C4
0x18005245c  sub     rdx, rcx
0x18005245f  lea     rbx, [rdx+rdx]
0x180052463  neg     rcx
0x180052466  sbb     rax, rax
0x180052469  and     rbx, rax
0x18005246c  lea     rdx, [rbx+2]; uBytes
0x180052470  mov     ecx, 40h ; '@'; uFlags
0x180052475  call    cs:__imp_LocalAlloc
0x18005247b  mov     r14, rax
0x18005247e  lea     rcx, [rsp+9A0h+uBytes+4]
0x180052483  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180052488  mov     qword ptr [rsp+9A0h+uBytes+4], r14
0x18005248d  test    r14, r14
0x180052490  jz      short loc_1800524FC
0x180052492  lea     r8, [rbp+8A0h+var_890]; unsigned __int16 *
0x180052496  lea     rdx, [rbx+2]; unsigned __int64
0x18005249a  mov     rcx, r14; unsigned __int16 *
0x18005249d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800524a2  mov     [rsp+9A0h+var_950], eax
0x1800524a6  test    eax, eax
0x1800524a8  jns     short loc_1800524D6
0x1800524aa  lea     rcx, aHrStringcbcopy; "hr = StringCbCopyW(pLiveUserName, liveU"...
0x1800524b1  mov     [rsp+9A0h+var_980], rcx
0x1800524b6  mov     r9d, eax
0x1800524b9  mov     r8d, 128h
0x1800524bf  jmp     loc_1800525F6
0x1800524c4  lea     rax, aHrStringcbleng; "hr = StringCbLengthW(currentSubKey, MAX"...
0x1800524cb  mov     r8d, 122h
0x1800524d1  jmp     loc_1800525F1
0x1800524d6  mov     edx, dword ptr [rsp+9A0h+uBytes]; uBytes
0x1800524da  mov     ecx, 40h ; '@'; uFlags
0x1800524df  call    cs:__imp_LocalAlloc
0x1800524e5  mov     rbx, rax
0x1800524e8  lea     rcx, [rsp+9A0h+var_930]
0x1800524ed  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x1800524f2  mov     [rsp+9A0h+var_930], rbx
  ... truncated ...
```
