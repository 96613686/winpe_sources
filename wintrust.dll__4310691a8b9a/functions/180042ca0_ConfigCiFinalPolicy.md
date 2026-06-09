# ConfigCiFinalPolicy

- ea: `0x180042ca0`
- end: `0x180043669`
- name: `ConfigCiFinalPolicy`
- size: `2505`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180025340`
- `0x180026494`
- `0x180027030`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c34c`
- `0x18002c728`
- `0x18002cc80`
- `0x18002d8ac`
- `0x18002da8c`
- `0x18002e5d0`
- `0x180030224`
- `0x180040d58`
- `0x180041d7c`
- `0x180041e8c`
- `0x180042bcc`
- `0x180042c08`
- `0x180042ca0`
- `0x180043a30`
- `0x18004de6a`
- `0x18004de76`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043278`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800432c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004361f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043278`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800432c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004361f`
- `ntdll!NtQuerySystemInformation` at `0x180042e17`
- `ntdll!NtQuerySystemInformation` at `0x180042ea4`
- `ntdll!NtQuerySystemInformation` at `0x180042e17`
- `ntdll!NtQuerySystemInformation` at `0x180042ea4`
- `CRYPT32!CryptMsgGetParam` at `0x1800430ab`
- `CRYPT32!CryptMsgGetParam` at `0x1800430ab`

## string_xrefs

- `0x1800431ef`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall ConfigCiFinalPolicy(_QWORD *a1)
{
  PVOID v1; // rbx
  void *v3; // r13
  __int64 v4; // rsi
  __int64 v5; // r14
  char *v6; // rdi
  __int64 v7; // rdx
  _OWORD *v8; // r12
  int v9; // ecx
  __int64 v10; // rax
  void *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  char *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r15
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rdi
  NTSTATUS v22; // edi
  _OWORD **v23; // rbx
  void *v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  _OWORD **v28; // rdi
  _QWORD *v29; // r15
  unsigned int v30; // ecx
  __int64 v31; // rax
  __int64 v32; // rax
  void *v33; // rcx
  DWORD v34; // eax
  __int64 v35; // rdi
  __int64 v36; // rdi
  const char *v37; // rdx
  _OWORD *v38; // rax
  int AuthenticodeSha256Hash; // eax
  _OWORD **v40; // r14
  void *v41; // rcx
  __int64 unique_hlocal; // rax
  HLOCAL v43; // rcx
  int v44; // eax
  __int64 v45; // rax
  _OWORD **v46; // r14
  _OWORD **v47; // r14
  _OWORD **v48; // r14
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rcx
  bool v52; // cc
  _DWORD *v53; // rax
  _DWORD *v54; // rcx
  __int64 v55; // r15
  __int64 v56; // rcx
  _DWORD *v57; // rcx
  _OWORD **v58; // r14
  DWORD pcbData; // [rsp+20h] [rbp-E0h]
  char v60[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v61; // [rsp+34h] [rbp-CCh]
  DWORD v62; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ReturnLength; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v64; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v65; // [rsp+48h] [rbp-B8h] BYREF
  PVOID SystemInformation; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A0h]
  char v69; // [rsp+68h] [rbp-98h] BYREF
  _OWORD *v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h]
  __int128 v72; // [rsp+90h] [rbp-70h] BYREF
  __int128 v73; // [rsp+A0h] [rbp-60h]
  __m256i v74; // [rsp+B0h] [rbp-50h]
  __int128 v75; // [rsp+D0h] [rbp-30h]
  __int128 v76; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v77; // [rsp+F0h] [rbp-10h]
  __int128 v78; // [rsp+100h] [rbp+0h]
  __int128 v79; // [rsp+110h] [rbp+10h]
  __int128 v80; // [rsp+120h] [rbp+20h]
  __m256i v81; // [rsp+130h] [rbp+30h]
  __int128 v82; // [rsp+150h] [rbp+50h]
  __int128 v83; // [rsp+160h] [rbp+60h]
  __int64 v84; // [rsp+170h] [rbp+70h]
  _OWORD v85[2]; // [rsp+178h] [rbp+78h] BYREF
  __m256i v86; // [rsp+198h] [rbp+98h]
  __int128 v87; // [rsp+1B8h] [rbp+B8h]
  __int128 v88; // [rsp+1C8h] [rbp+C8h]
  __int128 v89; // [rsp+1D8h] [rbp+D8h]
  __int128 v90; // [rsp+1E8h] [rbp+E8h]
  __int128 v91; // [rsp+1F8h] [rbp+F8h]
  __int128 v92; // [rsp+208h] [rbp+108h]
  __m256i v93; // [rsp+218h] [rbp+118h]
  __int128 v94; // [rsp+238h] [rbp+138h]
  __int128 v95; // [rsp+248h] [rbp+148h]
  __int64 v96; // [rsp+258h] [rbp+158h]
  _OWORD pvData[4]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v1 = 0;
  hMem = a1;
  SystemInformation = 0;
  v3 = 0;
  memset_0(pvData, 0, sizeof(pvData));
  v4 = 2;
  v5 = 2;
  v6 = &v69;
  do
  {
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v6);
    v6 += 8;
    --v5;
  }
  while ( v5 );
  v7 = a1[1];
  v8 = 0;
  v70 = 0;
  v65 = 0;
  v64 = 0;
  v9 = *(_DWORD *)(v7 + 32);
  if ( (unsigned int)(v9 - 1) <= 1 )
  {
    v10 = *(_QWORD *)(a1[20] + 40LL);
    if ( !v10 || (v11 = *(void **)(v10 + 16), v11 == (void *)-1LL) || (v3 = v11) == 0 )
    {
      if ( v9 == 1 )
      {
        v12 = *(_QWORD *)(v7 + 40);
        if ( *(_QWORD *)(v12 + 16) != -1 )
          v3 = *(void **)(v12 + 16);
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl) )
  {
    if ( !v3 )
    {
      v13 = a1[1];
      if ( *(_DWORD *)(v13 + 32) == 6 )
      {
        v14 = *(_QWORD *)(v13 + 8);
        if ( v14 )
        {
          if ( *(_DWORD *)v14 > 0x28u )
          {
            v15 = *(_QWORD *)(v14 + 40);
            if ( v15 )
            {
              if ( *(_DWORD *)v15 > 0xE0u )
              {
                v16 = *(char **)(v15 + 224);
                if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  v3 = v16;
              }
            }
          }
        }
      }
    }
  }
  v17 = a1[1];
  v18 = *(_QWORD *)(v17 + 8);
  if ( v18 && *(_DWORD *)v18 > 0x10u )
  {
    v19 = *(unsigned int *)(v18 + 4);
    if ( (_DWORD)v19 )
    {
      v20 = InitializeSiPoliciesFromBlobs(v19, *(_QWORD *)(v18 + 8), &v65);
      v68 = v65;
      LODWORD(v21) = v20 | 0x10000000;
      v5 = v18;
      if ( v20 >= 0 )
        LODWORD(v21) = 0;
      goto LABEL_41;
    }
    v5 = *(_QWORD *)(v17 + 8);
  }
  ReturnLength = 0;
  v22 = NtQuerySystemInformation(SystemProcessorPowerInformation|0x80, 0, 0, &ReturnLength);
  if ( v22 >= 0 )
  {
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
    v23 = &v70;
    do
    {
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v23);
      --v4;
    }
    while ( v4 );
    operator delete(0);
    return 0;
  }
  v68 = 0;
  if ( v22 != -1073741820 )
    goto LABEL_33;
  v25 = operator new[](ReturnLength, (const struct std::nothrow_t *)std::nothrow);
  std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(&SystemInformation, v25);
  v1 = SystemInformation;
  if ( !SystemInformation )
  {
    LODWORD(v21) = -2147024882;
    goto LABEL_129;
  }
  v22 = NtQuerySystemInformation(SystemProcessorPowerInformation|0x80, SystemInformation, ReturnLength, &ReturnLength);
  if ( v22 >= 0 )
  {
    LODWORD(v21) = 0;
    v27 = InitializeSiPolicy(v26, v1, ReturnLength, &v64);
    if ( v27 < 0 )
    {
      if ( v27 == -1073741637 )
      {
        wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
        wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
        v28 = &v70;
        do
        {
          wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v28);
          --v4;
        }
        while ( v4 );
        LODWORD(v21) = 0;
        goto LABEL_133;
      }
      LODWORD(v21) = v27 | 0x10000000;
    }
    v68 = v64;
  }
  else
  {
LABEL_33:
    LODWORD(v21) = v22 | 0x10000000;
  }
LABEL_41:
  if ( (v21 & 0x80000000) != 0LL )
  {
LABEL_129:
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
    if ( v8 )
      LocalFree(v8);
    v58 = &v70;
    do
    {
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v58);
      --v4;
    }
    while ( v4 );
    goto LABEL_133;
  }
  SystemInformation = 0;
  v61 = 0;
  LODWORD(v72) = 0;
  v62 = 0;
  memset_0((char *)&v72 + 4, 0, 0x1CCu);
  v29 = hMem;
  v30 = 0;
  while ( 1 )
  {
    v31 = v29[1];
    if ( *(_DWORD *)(v31 + 32) != 2 )
      break;
    v32 = *(_QWORD *)(v31 + 40);
    if ( *(_QWORD *)(v32 + 40) )
    {
      v33 = *(void **)(v32 + 40);
      v34 = *(_DWORD *)(v32 + 48);
      SystemInformation = v33;
LABEL_46:
      v62 = v34;
      goto LABEL_78;
    }
LABEL_64:
    if ( v3 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl)
        || *(_DWORD *)(v29[1] + 32LL) != 6
        || v61
        || (v41 = (void *)v29[14]) == 0
        || (v62 = 64, !CryptMsgGetParam(v41, 0x16u, 0, pvData, &v62)) )
      {
        LODWORD(v21) = WintrustGetHash(v3, L"SHA256", 32, pvData);
        if ( (v21 & 0x80000000) != 0LL )
        {
          WTConfigCiFreePrivateData(&v72);
          WTConfigCiFreePrivateData(v85);
          wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
          wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
          if ( v8 )
            LocalFree(v8);
          v47 = &v70;
          do
          {
            wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v47);
            --v4;
          }
          while ( v4 );
          goto LABEL_133;
        }
        unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, 32);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
          &v70,
          unique_hlocal);
        v43 = hMem;
        hMem = 0;
        if ( v43 )
          LocalFree(v43);
        v8 = v70;
        if ( !v70 )
        {
          LODWORD(v21) = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDCD,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
            (const char *)0x8007000ELL,
            pcbData);
          WTConfigCiFreePrivateData(&v72);
          WTConfigCiFreePrivateData(v85);
          wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
          wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
          v46 = &v70;
          do
          {
            wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v46);
            --v4;
          }
          while ( v4 );
          goto LABEL_133;
        }
        *v70 = pvData[0];
        v62 = 32;
        v8[1] = pvData[1];
        goto LABEL_76;
      }
      SystemInformation = pvData;
      v34 = v62;
      goto LABEL_46;
    }
LABEL_79:
    v71 = 232LL * v30;
    pcbData = v62;
    v44 = FinalPolicyInternal_(v68, v29, v3, SystemInformation);
    LODWORD(v21) = v44;
    if ( v44 < 0 && (v44 & 0x1FFF0000) != 0x10E90000 )
    {
      WTConfigCiFreePrivateData(&v72);
      WTConfigCiFreePrivateData(v85);
      wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
      wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
      if ( v8 )
        LocalFree(v8);
      v48 = &v70;
      do
      {
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v48);
        --v4;
      }
      while ( v4 );
      goto LABEL_133;
    }
    if ( *(_DWORD *)((char *)&v72 + v71 + 8) == 2 && *((_BYTE *)&v73 + v71) )
    {
      v30 = v61;
LABEL_100:
      if ( v30 == 2 )
      {
        v60[0] = 0;
        if ( (int)WTIsFirstConfigCiResultPreferred(&v72, v85, v60) >= 0 && !v60[0] )
        {
          WTConfigCiFreePrivateData(&v72);
          v72 = v85[0];
          v84 = v96;
          v73 = v85[1];
          v74 = v86;
          v75 = v87;
          v76 = v88;
          v77 = v89;
          v78 = v90;
          v79 = v91;
          v80 = v92;
          v81 = v93;
          v82 = v94;
          v83 = v95;
          memset_0(v85, 0, 0xE8u);
        }
      }
      v21 = DWORD1(v72);
      if ( !v81.m256i_i64[0] && v8 )
      {
        DWORD2(v80) = 32;
        v81.m256i_i64[0] = (__int64)v8;
        v8 = 0;
      }
      if ( SDWORD1(v72) < 0 )
      {
        if ( DWORD2(v72) == 2 && (_BYTE)v73 )
          *(_DWORD *)(v29[10] + 144LL) = -2146762484;
        else
          *(_DWORD *)(v29[10] + 144LL) = DWORD1(v72);
      }
      else
      {
        *(_DWORD *)(v29[10] + 144LL) = 0;
      }
      if ( v5 )
      {
        v49 = *((_QWORD *)&v72 + 1);
        *(_DWORD *)(v5 + 20) = DWORD2(v72);
        *(_BYTE *)(v5 + 28) = v73;
        v50 = DWORD1(v72);
        v51 = HIDWORD(v49);
        v52 = *(_DWORD *)v5 <= 0x28u;
        *(_DWORD *)(v5 + 24) = v51;
        *(_DWORD *)(v5 + 16) = v50;
        if ( !v52 )
        {
          v53 = *(_DWORD **)(v5 + 40);
          if ( v53 )
          {
            if ( *v53 > 0x10u )
            {
              v53[3] = v51;
              *(_DWORD *)(*(_QWORD *)(v5 + 40) + 8LL) = DWORD2(v72);
              *(_BYTE *)(*(_QWORD *)(v5 + 40) + 16LL) = v73;
              *(_DWORD *)(*(_QWORD *)(v5 + 40) + 4LL) = DWORD1(v72);
            }
            v54 = *(_DWORD **)(v5 + 40);
            if ( *v54 > 0x18u )
            {
              v54[5] = DWORD1(v73);
              *(_QWORD *)(*(_QWORD *)(v5 + 40) + 24LL) = *((_QWORD *)&v73 + 1);
              *((_QWORD *)&v73 + 1) = 0;
            }
            v55 = *(_QWORD *)(v5 + 40);
            if ( *(_DWORD *)v55 > 0x50u )
            {
              *(_DWORD *)(v55 + 32) = v74.m256i_i32[0];
              *(_OWORD *)(v55 + 80) = v76;
              *(_OWORD *)(v55 + 96) = v77;
              *(_OWORD *)(v55 + 112) = v78;
              *(_OWORD *)(v55 + 128) = v79;
              *(_OWORD *)(v55 + 144) = v80;
              *(_QWORD *)(v55 + 160) = v81.m256i_i64[0];
              memset_0(&v76, 0, 0x58u);
              *(_OWORD *)(v55 + 36) = *(_OWORD *)((char *)v74.m256i_i64 + 4);
              *(_DWORD *)(v55 + 52) = v74.m256i_i32[5];
              *(_WORD *)(v55 + 56) = v74.m256i_i16[12];
              *(_DWORD *)(v55 + 60) = v74.m256i_i32[7];
              *(_OWORD *)(v55 + 64) = v75;
              *((_QWORD *)&v75 + 1) = 0;
            }
            v56 = *(_QWORD *)(v5 + 40);
            if ( *(_DWORD *)v56 > 0xC8u )
            {
              *(_OWORD *)(v56 + 168) = *(_OWORD *)&v81.m256i_u64[1];
              *(_QWORD *)(v56 + 184) = v81.m256i_i64[3];
              *(_OWORD *)(v56 + 192) = v82;
              v82 = 0u;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAC_LocalLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SAC_LocalLogging>::GetImpl'::`2'::impl) )
            {
              v57 = *(_DWORD **)(v5 + 40);
              if ( *v57 > 0xD0u )
                v57[52] = v83;
            }
          }
        }
      }
      WTConfigCiFreePrivateData(&v72);
      WTConfigCiFreePrivateData(v85);
      goto LABEL_129;
    }
    v45 = v29[1];
    v30 = ++v61;
    if ( *(_DWORD *)(v45 + 32) != 1 || v30 >= 2 )
      goto LABEL_100;
  }
  if ( *(_DWORD *)(v31 + 32) != 1 || v30 )
    goto LABEL_64;
  v35 = v29[20];
  if ( v35 )
  {
    v36 = *(_QWORD *)(v35 + 56);
    if ( v36 )
    {
      if ( *(_DWORD *)(v36 + 48) == 32 )
      {
        v37 = *(const char **)(v36 + 24);
        if ( v37 )
        {
          if ( !strcmp_0("2.16.840.1.101.3.4.2.1", v37) )
          {
            v38 = *(_OWORD **)(v36 + 56);
            v62 = 32;
            goto LABEL_77;
          }
          v31 = v29[1];
        }
      }
    }
  }
  AuthenticodeSha256Hash = GetAuthenticodeSha256Hash(*(LPCWSTR *)(*(_QWORD *)(v31 + 40) + 8LL), v3);
  LODWORD(v21) = AuthenticodeSha256Hash;
  if ( AuthenticodeSha256Hash >= 0 )
  {
    v62 = 32;
LABEL_76:
    v38 = pvData;
LABEL_77:
    SystemInformation = v38;
LABEL_78:
    v30 = v61;
    goto LABEL_79;
  }
  if ( AuthenticodeSha256Hash == -2146762749 )
    goto LABEL_78;
  WTConfigCiFreePrivateData(&v72);
  WTConfigCiFreePrivateData(v85);
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v64);
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___(&v65);
  if ( v8 )
    LocalFree(v8);
  v40 = &v70;
  do
  {
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(--v40);
    --v4;
  }
  while ( v4 );
LABEL_133:
  operator delete(v1);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180042ca0  push    rbp
0x180042ca2  push    rbx
0x180042ca3  push    rsi
0x180042ca4  push    rdi
0x180042ca5  push    r12
0x180042ca7  push    r13
0x180042ca9  push    r14
0x180042cab  push    r15
0x180042cad  lea     rbp, [rsp-1B8h]
0x180042cb5  sub     rsp, 2B8h
0x180042cbc  mov     rax, cs:__security_cookie
0x180042cc3  xor     rax, rsp
0x180042cc6  mov     [rbp+1F0h+var_50], rax
0x180042ccd  xor     ebx, ebx
0x180042ccf  mov     [rsp+2F0h+hMem], rcx
0x180042cd4  mov     r15, rcx
0x180042cd7  mov     [rsp+2F0h+SystemInformation], rbx
0x180042cdc  xor     r13d, r13d
0x180042cdf  lea     rcx, [rbp+1F0h+pvData]; void *
0x180042ce6  xor     edx, edx; Val
0x180042ce8  lea     r8d, [rbx+40h]; Size
0x180042cec  call    memset_0
0x180042cf1  lea     esi, [rbx+2]
0x180042cf4  mov     r14d, esi
0x180042cf7  lea     rdi, [rsp+2F0h+var_288]
0x180042cfc  mov     rcx, rdi
0x180042cff  call    ??$?0$00X@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180042d04  add     rdi, 8
0x180042d08  sub     r14, 1
0x180042d0c  jnz     short loc_180042CFC
0x180042d0e  mov     rdx, [r15+8]
0x180042d12  xor     r12d, r12d
0x180042d15  mov     [rsp+2F0h+var_278], r12
0x180042d1a  mov     [rsp+2F0h+var_2A8], rbx
0x180042d1f  mov     [rsp+2F0h+var_2B0], rbx
0x180042d24  mov     ecx, [rdx+20h]
0x180042d27  lea     eax, [rcx-1]
0x180042d2a  cmp     eax, 1
0x180042d2d  ja      short loc_180042D64
0x180042d2f  mov     rax, [r15+0A0h]
0x180042d36  mov     rax, [rax+28h]
0x180042d3a  test    rax, rax
0x180042d3d  jz      short loc_180042D51
0x180042d3f  mov     rax, [rax+10h]
0x180042d43  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042d47  jz      short loc_180042D51
0x180042d49  mov     r13, rax
0x180042d4c  test    rax, rax
0x180042d4f  jnz     short loc_180042D64
0x180042d51  cmp     ecx, 1
0x180042d54  jnz     short loc_180042D64
0x180042d56  mov     rax, [rdx+28h]
0x180042d5a  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x180042d5f  cmovnz  r13, [rax+10h]
0x180042d64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x180042d6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x180042d70  test    al, al
0x180042d72  jz      short loc_180042DB5
0x180042d74  test    r13, r13
0x180042d77  jnz     short loc_180042DB5
0x180042d79  mov     rax, [r15+8]
0x180042d7d  cmp     dword ptr [rax+20h], 6
0x180042d81  jnz     short loc_180042DB5
0x180042d83  mov     rax, [rax+8]
0x180042d87  test    rax, rax
0x180042d8a  jz      short loc_180042DB5
0x180042d8c  cmp     dword ptr [rax], 28h ; '('
0x180042d8f  jbe     short loc_180042DB5
0x180042d91  mov     rcx, [rax+28h]
0x180042d95  test    rcx, rcx
0x180042d98  jz      short loc_180042DB5
0x180042d9a  cmp     dword ptr [rcx], 0E0h
0x180042da0  jbe     short loc_180042DB5
0x180042da2  mov     rcx, [rcx+0E0h]
0x180042da9  lea     rax, [rcx-1]
0x180042dad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042db1  cmovbe  r13, rcx
0x180042db5  mov     rax, [r15+8]
0x180042db9  mov     r15, [rax+8]
0x180042dbd  test    r15, r15
0x180042dc0  jz      short loc_180042E00
0x180042dc2  cmp     dword ptr [r15], 10h
0x180042dc6  jbe     short loc_180042E00
0x180042dc8  mov     ecx, [r15+4]
0x180042dcc  test    ecx, ecx
0x180042dce  jz      short loc_180042DFD
0x180042dd0  mov     rdx, [r15+8]
0x180042dd4  lea     r8, [rsp+2F0h+var_2A8]
0x180042dd9  call    InitializeSiPoliciesFromBlobs
0x180042dde  mov     rdx, [rsp+2F0h+var_2A8]
0x180042de3  xor     ecx, ecx
0x180042de5  mov     edi, eax
0x180042de7  mov     [rsp+2F0h+var_290], rdx
0x180042dec  bts     edi, 1Ch
0x180042df0  mov     r14, r15
0x180042df3  test    eax, eax
0x180042df5  cmovns  edi, ecx
0x180042df8  jmp     loc_180042F17
0x180042dfd  mov     r14, r15
0x180042e00  mov     r15d, 0BDh
0x180042e06  mov     [rsp+2F0h+ReturnLength], ebx
0x180042e0a  mov     ecx, r15d; SystemInformationClass
0x180042e0d  lea     r9, [rsp+2F0h+ReturnLength]; ReturnLength
0x180042e12  xor     r8d, r8d; SystemInformationLength
0x180042e15  xor     edx, edx; SystemInformation
0x180042e17  call    cs:__imp_NtQuerySystemInformation
0x180042e1d  mov     edi, eax
0x180042e1f  test    eax, eax
0x180042e21  js      short loc_180042E5C
0x180042e23  lea     rcx, [rsp+2F0h+var_2B0]
0x180042e28  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180042e2d  lea     rcx, [rsp+2F0h+var_2A8]
0x180042e32  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180042e37  lea     rbx, [rsp+2F0h+var_278]
0x180042e3c  sub     rbx, 8
0x180042e40  mov     rcx, rbx
0x180042e43  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180042e48  sub     rsi, 1
0x180042e4c  jnz     short loc_180042E3C
0x180042e4e  xor     ecx, ecx; Block
0x180042e50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042e55  xor     eax, eax
0x180042e57  jmp     loc_180043646
0x180042e5c  mov     [rsp+2F0h+var_290], rbx
0x180042e61  cmp     edi, 0C0000004h
0x180042e67  jnz     short loc_180042EB0
0x180042e69  mov     ecx, [rsp+2F0h+ReturnLength]; unsigned __int64
0x180042e6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042e74  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042e79  mov     rdx, rax
0x180042e7c  lea     rcx, [rsp+2F0h+SystemInformation]
0x180042e81  call    ?reset@?$unique_ptr@$$BY0A@U_SIPOLICY_EXEC_STATUS@@U?$default_delete@$$BY0A@U_SIPOLICY_EXEC_STATUS@@@std@@@std@@QEAAXPEAU_SIPOLICY_EXEC_STATUS@@@Z; std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(_SIPOLICY_EXEC_STATUS *)
0x180042e86  mov     rbx, [rsp+2F0h+SystemInformation]
0x180042e8b  test    rbx, rbx
0x180042e8e  jz      loc_1800435FE
0x180042e94  mov     r8d, [rsp+2F0h+ReturnLength]; SystemInformationLength
0x180042e99  lea     r9, [rsp+2F0h+ReturnLength]; ReturnLength
0x180042e9e  mov     rdx, rbx; SystemInformation
0x180042ea1  mov     ecx, r15d; SystemInformationClass
0x180042ea4  call    cs:__imp_NtQuerySystemInformation
0x180042eaa  mov     edi, eax
0x180042eac  test    eax, eax
0x180042eae  jns     short loc_180042EB6
0x180042eb0  bts     edi, 1Ch
0x180042eb4  jmp     short loc_180042F17
0x180042eb6  mov     r8d, [rsp+2F0h+ReturnLength]
0x180042ebb  lea     r9, [rsp+2F0h+var_2B0]
0x180042ec0  mov     rdx, rbx
0x180042ec3  xor     edi, edi
0x180042ec5  call    InitializeSiPolicy
0x180042eca  test    eax, eax
0x180042ecc  jns     short loc_180042F0D
0x180042ece  cmp     eax, 0C00000BBh
0x180042ed3  jnz     short loc_180042F07
0x180042ed5  lea     rcx, [rsp+2F0h+var_2B0]
0x180042eda  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180042edf  lea     rcx, [rsp+2F0h+var_2A8]
0x180042ee4  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180042ee9  lea     rdi, [rsp+2F0h+var_278]
0x180042eee  sub     rdi, 8
0x180042ef2  mov     rcx, rdi
0x180042ef5  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180042efa  sub     rsi, 1
0x180042efe  jnz     short loc_180042EEE
0x180042f00  xor     edi, edi
0x180042f02  jmp     loc_18004363C
0x180042f07  mov     edi, eax
0x180042f09  bts     edi, 1Ch
0x180042f0d  mov     rax, [rsp+2F0h+var_2B0]
0x180042f12  mov     [rsp+2F0h+var_290], rax
0x180042f17  test    edi, edi
0x180042f19  js      loc_180043603
0x180042f1f  xor     eax, eax
0x180042f21  mov     [rsp+2F0h+SystemInformation], r12
0x180042f26  xor     edx, edx; Val
0x180042f28  mov     [rsp+2F0h+var_2BC], eax
0x180042f2c  mov     r8d, 1CCh; Size
0x180042f32  mov     dword ptr [rbp+1F0h+var_260], eax
0x180042f35  lea     rcx, [rbp+1F0h+var_260+4]; void *
0x180042f39  mov     [rsp+2F0h+var_2B8], r12d
0x180042f3e  call    memset_0
0x180042f43  mov     r15, [rsp+2F0h+hMem]
0x180042f48  mov     ecx, r12d
0x180042f4b  mov     rax, [r15+8]
0x180042f4f  cmp     [rax+20h], esi
0x180042f52  jnz     short loc_180042F78
0x180042f54  mov     rax, [rax+28h]
0x180042f58  cmp     qword ptr [rax+28h], 0
0x180042f5d  jz      loc_180043058
0x180042f63  mov     rcx, [rax+28h]
0x180042f67  mov     eax, [rax+30h]
0x180042f6a  mov     [rsp+2F0h+SystemInformation], rcx
0x180042f6f  mov     [rsp+2F0h+var_2B8], eax
0x180042f73  jmp     loc_18004315E
0x180042f78  cmp     dword ptr [rax+20h], 1
0x180042f7c  jnz     loc_180043058
0x180042f82  test    ecx, ecx
0x180042f84  jnz     loc_180043058
0x180042f8a  mov     rdi, [r15+0A0h]
0x180042f91  test    rdi, rdi
0x180042f94  jz      short loc_180042FD3
0x180042f96  mov     rdi, [rdi+38h]
0x180042f9a  test    rdi, rdi
0x180042f9d  jz      short loc_180042FD3
0x180042f9f  cmp     dword ptr [rdi+30h], 20h ; ' '
0x180042fa3  jnz     short loc_180042FD3
0x180042fa5  mov     rdx, [rdi+18h]; Str2
0x180042fa9  test    rdx, rdx
0x180042fac  jz      short loc_180042FD3
0x180042fae  lea     rcx, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x180042fb5  call    strcmp_0
0x180042fba  test    eax, eax
0x180042fbc  jnz     short loc_180042FCF
0x180042fbe  mov     rax, [rdi+38h]
0x180042fc2  mov     [rsp+2F0h+var_2B8], 20h ; ' '
0x180042fca  jmp     loc_180043159
0x180042fcf  mov     rax, [r15+8]
0x180042fd3  mov     rcx, [rax+28h]
0x180042fd7  lea     r8, [rbp+1F0h+pvData]
0x180042fde  mov     rdx, r13; hSourceHandle
0x180042fe1  mov     rcx, [rcx+8]; FileName
0x180042fe5  call    GetAuthenticodeSha256Hash
0x180042fea  mov     edi, eax
0x180042fec  test    eax, eax
0x180042fee  js      short loc_180042FFD
0x180042ff0  mov     [rsp+2F0h+var_2B8], 20h ; ' '
0x180042ff8  jmp     loc_180043152
0x180042ffd  cmp     eax, 800B0003h
0x180043002  jz      loc_18004315E
0x180043008  lea     rcx, [rbp+1F0h+var_260]
0x18004300c  call    WTConfigCiFreePrivateData
0x180043011  lea     rcx, [rbp+1F0h+var_178]
0x180043015  call    WTConfigCiFreePrivateData
0x18004301a  lea     rcx, [rsp+2F0h+var_2B0]
0x18004301f  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x180043024  lea     rcx, [rsp+2F0h+var_2A8]
0x180043029  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void____cdecl___SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t___
0x18004302e  test    r12, r12
0x180043031  jz      short loc_18004303C
0x180043033  mov     rcx, r12; hMem
0x180043036  call    cs:__imp_LocalFree
0x18004303c  lea     r14, [rsp+2F0h+var_278]
0x180043041  sub     r14, 8
0x180043045  mov     rcx, r14
0x180043048  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x18004304d  sub     rsi, 1
0x180043051  jnz     short loc_180043041
0x180043053  jmp     loc_18004363C
0x180043058  test    r13, r13
0x18004305b  jz      loc_180043162
0x180043061  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x180043068  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x18004306d  test    al, al
0x18004306f  jz      short loc_1800430CA
0x180043071  mov     rax, [r15+8]
0x180043075  cmp     dword ptr [rax+20h], 6
0x180043079  jnz     short loc_1800430CA
0x18004307b  cmp     [rsp+2F0h+var_2BC], 0
0x180043080  jnz     short loc_1800430CA
0x180043082  mov     rcx, [r15+70h]; hCryptMsg
0x180043086  test    rcx, rcx
0x180043089  jz      short loc_1800430CA
0x18004308b  xor     r8d, r8d; dwIndex
0x18004308e  mov     [rsp+2F0h+var_2B8], 40h ; '@'
0x180043096  lea     rax, [rsp+2F0h+var_2B8]
0x18004309b  lea     r9, [rbp+1F0h+pvData]; pvData
0x1800430a2  mov     [rsp+2F0h+pcbData], rax; pcbData
0x1800430a7  lea     edx, [r8+16h]; dwParamType
0x1800430ab  call    cs:__imp_CryptMsgGetParam
0x1800430b1  test    eax, eax
0x1800430b3  jz      short loc_1800430CA
0x1800430b5  lea     rax, [rbp+1F0h+pvData]
0x1800430bc  mov     [rsp+2F0h+SystemInformation], rax
0x1800430c1  mov     eax, [rsp+2F0h+var_2B8]
0x1800430c5  jmp     loc_180042F6F
0x1800430ca  lea     r9, [rbp+1F0h+pvData]
0x1800430d1  mov     r8d, 20h ; ' '
0x1800430d7  lea     rdx, aSha256; "SHA256"
0x1800430de  mov     rcx, r13
0x1800430e1  call    WintrustGetHash
0x1800430e6  mov     edi, eax
0x1800430e8  test    eax, eax
0x1800430ea  js      loc_18004324A
0x1800430f0  mov     edi, 20h ; ' '
0x1800430f5  lea     rcx, [rsp+2F0h+hMem]
0x1800430fa  mov     edx, edi
0x1800430fc  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180043101  mov     rdx, rax
0x180043104  lea     rcx, [rsp+2F0h+var_278]
0x180043109  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18004310e  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180043113  mov     [rsp+2F0h+hMem], 0
0x18004311c  test    rcx, rcx
0x18004311f  jz      short loc_180043127
0x180043121  call    cs:__imp_LocalFree
0x180043127  mov     r12, [rsp+2F0h+var_278]
0x18004312c  test    r12, r12
0x18004312f  jz      loc_1800431E8
0x180043135  movaps  xmm0, [rbp+1F0h+pvData]
0x18004313c  movups  xmmword ptr [r12], xmm0
  ... truncated ...
```
