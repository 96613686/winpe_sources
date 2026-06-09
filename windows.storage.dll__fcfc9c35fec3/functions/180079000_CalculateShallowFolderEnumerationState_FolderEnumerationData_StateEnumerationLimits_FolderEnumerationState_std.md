# CalculateShallowFolderEnumerationState(FolderEnumerationData &,StateEnumerationLimits *,FolderEnumerationState &,std::list<FolderEnumerationData,std::allocator<FolderEnumerationData>> &)

- ea: `0x180079000`
- end: `0x180079973`
- name: `?CalculateShallowFolderEnumerationState@@YA_NAEAUFolderEnumerationData@@PEAVStateEnumerationLimits@@AEAUFolderEnumerationState@@AEAV?$list@UFolderEnumerationData@@V?$allocator@UFolderEnumerationData@@@std@@@std@@@Z`
- size: `2419`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800781c0`

## callees

- `0x180033c60`
- `0x180077b50`
- `0x180079000`
- `0x18007997c`
- `0x180079ccc`
- `0x180079cec`
- `0x1800bf1c8`
- `0x1800bf2a4`
- `0x1800bf2e0`
- `0x1800ee270`
- `0x1800f1280`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18059af94`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079272`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079253`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x18007904b`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x18007904b`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18007905d`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800795d0`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800796f2`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18007905d`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800795d0`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800796f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800793f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079868`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800798e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800793f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079868`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800798e1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079650`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079650`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180079675`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180079675`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180079966`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180079966`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800792a2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180079570`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800792a2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180079570`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180079121`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180079121`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CalculateShallowFolderEnumerationState(_QWORD *a1, _DWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rdi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rdx
  unsigned int *v10; // r8
  __int64 v11; // r9
  unsigned __int8 v12; // cl
  char v13; // r13
  int v14; // r15d
  __int64 v15; // rdx
  char PlaceholderStateFromAttributeTag; // al
  LONGLONG v17; // rdx
  char v18; // r12
  int v19; // ecx
  int v20; // edi
  char v21; // r8
  int v22; // r14d
  char v23; // cl
  LONGLONG v24; // rcx
  unsigned int v25; // r15d
  int v26; // eax
  int v27; // eax
  int v28; // esi
  char v29; // bl
  signed int *v30; // r13
  signed int v31; // r15d
  HLOCAL v32; // r14
  DWORD LastError; // ebx
  HRESULT v34; // eax
  int v35; // r12d
  char v36; // al
  int v37; // ebx
  int v38; // esi
  int v39; // esi
  int v40; // esi
  int v41; // eax
  char v42; // al
  _DWORD *v43; // rsi
  HLOCAL v44; // rdi
  _QWORD *v45; // rsi
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 *v48; // rcx
  HRESULT v49; // eax
  __int64 v51; // rcx
  bool v52; // zf
  int v53; // ebx
  __int64 v54; // rcx
  __int64 v55; // rcx
  int v56; // [rsp+20h] [rbp-E0h]
  char v57; // [rsp+30h] [rbp-D0h]
  char v58; // [rsp+31h] [rbp-CFh]
  char v59; // [rsp+34h] [rbp-CCh]
  unsigned __int8 v60; // [rsp+35h] [rbp-CBh]
  char v61; // [rsp+38h] [rbp-C8h]
  unsigned int v62; // [rsp+3Ch] [rbp-C4h]
  int v63; // [rsp+40h] [rbp-C0h]
  unsigned int v64; // [rsp+44h] [rbp-BCh]
  int v66; // [rsp+50h] [rbp-B0h] BYREF
  int v67; // [rsp+54h] [rbp-ACh]
  char v68; // [rsp+58h] [rbp-A8h]
  _QWORD *v69; // [rsp+60h] [rbp-A0h]
  HLOCAL v70; // [rsp+68h] [rbp-98h]
  char v71; // [rsp+70h] [rbp-90h]
  int v72; // [rsp+71h] [rbp-8Fh]
  __int16 v73; // [rsp+75h] [rbp-8Bh]
  char v74; // [rsp+77h] [rbp-89h]
  _DWORD *v75; // [rsp+78h] [rbp-88h]
  _QWORD *v76; // [rsp+80h] [rbp-80h]
  _QWORD *v77; // [rsp+88h] [rbp-78h]
  __int64 v78; // [rsp+90h] [rbp-70h]
  _DWORD v79[11]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszMore; // [rsp+CCh] [rbp-34h] BYREF
  __int16 v81; // [rsp+CEh] [rbp-32h]
  __int16 v82; // [rsp+D0h] [rbp-30h]
  __int64 v83[4]; // [rsp+2F0h] [rbp+1F0h] BYREF
  HLOCAL hMem; // [rsp+310h] [rbp+210h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+318h] [rbp+218h] BYREF
  __int64 v86; // [rsp+320h] [rbp+220h] BYREF
  LARGE_INTEGER Frequency; // [rsp+328h] [rbp+228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v76 = a4;
  v4 = a3;
  v75 = a2;
  v69 = a1;
  v59 = 0;
  if ( (unsigned __int8)RtlQueryThreadPlaceholderCompatibilityMode() != 2 )
  {
    LOBYTE(v6) = 2;
    v60 = RtlSetThreadPlaceholderCompatibilityMode(v6);
    v59 = 1;
  }
  memset_0(v79, 0, 0x268u);
  v86 = 0;
  v7 = CEnumFiles_CreateInstance(0, &GUID_4e31e71d_945b_471d_88a9_061b207facaa, &v86);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\syncstate.cpp",
      (const char *)(unsigned int)v7,
      v56);
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v86 + 32LL))(v86, *a1, v79);
  v12 = (unsigned __int8)retaddr;
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x214,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\syncstate.cpp",
      (const char *)(unsigned int)v8,
      v56);
  v61 = 1;
  while ( !v8 )
  {
    if ( pszMore == 46 && (!v81 || !v82 && v81 == 46) )
      goto LABEL_72;
    hMem = 0;
    v13 = 0;
    v57 = 0;
    v14 = v79[0];
    v15 = 0;
    if ( (v79[0] & 0x400) != 0 )
      v15 = v79[9];
    PlaceholderStateFromAttributeTag = CfGetPlaceholderStateFromAttributeTag(v79[0], v15);
    v18 = PlaceholderStateFromAttributeTag;
    v19 = v14 & 0x180000;
    if ( (v14 & 0x180000) == 0 )
    {
      v20 = 0;
      v21 = PlaceholderStateFromAttributeTag & 1;
LABEL_12:
      v22 = PlaceholderStateFromAttributeTag & 0x10;
      v23 = PlaceholderStateFromAttributeTag;
      v63 = v22;
      goto LABEL_13;
    }
    if ( v19 == 0x80000 )
    {
      v20 = 1;
      v21 = PlaceholderStateFromAttributeTag & 1;
      goto LABEL_12;
    }
    v21 = PlaceholderStateFromAttributeTag & 1;
    v22 = PlaceholderStateFromAttributeTag & 0x10;
    v63 = v22;
    v52 = v19 == 0x100000;
    v23 = PlaceholderStateFromAttributeTag;
    if ( !v52 )
    {
      v64 = 0;
      v20 = 3;
      v24 = PlaceholderStateFromAttributeTag & 8;
      v25 = v14 & 0x10;
      v62 = v25;
      v11 = 0;
      v26 = 0;
LABEL_14:
      v27 = v26 | 2;
      goto LABEL_15;
    }
    v20 = 2;
LABEL_13:
    v24 = v23 & 8;
    v25 = v14 & 0x10;
    v17 = v25;
    v26 = 1;
    v11 = 1;
    v64 = 1;
    v62 = v25;
    if ( v20 != 1 )
      goto LABEL_14;
    v64 = 3;
    v27 = 3;
    v63 = v22;
    v62 = v25;
LABEL_15:
    if ( v20 != 1 )
      v27 = v11;
    if ( v22 || v25 )
    {
      if ( v20 == 3 && !v22 )
      {
LABEL_90:
        v28 = 6;
        goto LABEL_30;
      }
    }
    else if ( v20 != 2 )
    {
      if ( v20 == 3 )
        goto LABEL_90;
      v64 = v27 | 4;
    }
    if ( (_DWORD)v24 )
    {
      if ( ((v20 - 1) & 0xFFFFFFFD) == 0 && v22 )
      {
        v28 = 4;
      }
      else
      {
        if ( v20 == 2 )
        {
          if ( !v22 )
          {
            if ( !v25 )
            {
              v28 = 3;
              goto LABEL_33;
            }
            goto LABEL_29;
          }
        }
        else if ( !v22 )
        {
          if ( v20 == 1 )
          {
            v28 = 15;
LABEL_33:
            v29 = 0;
            goto LABEL_34;
          }
LABEL_29:
          v28 = 14;
          goto LABEL_30;
        }
        v28 = 7;
      }
    }
    else
    {
      v28 = 3;
      if ( !v21 )
        v28 = 5;
    }
LABEL_30:
    if ( v20 != 3 )
      goto LABEL_33;
    v29 = 1;
LABEL_34:
    v58 = v29;
    if ( *(_BYTE *)(a3 + 1) && !v29 && (v79[0] & 0x100) == 0 )
    {
      *(_BYTE *)a3 = 0;
      v30 = (signed int *)(a3 + 4);
      v31 = *(_DWORD *)(a3 + 4);
      PerformanceCount.LowPart = v31;
      v66 = 0;
      v67 = 16;
      v68 = 0;
      v32 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v32);
        SetLastError(LastError);
      }
      hMem = 0;
      v34 = PathAllocCombine((PCWSTR)*v69, &pszMore, 1u, (PWSTR *)&hMem);
      v24 = (LONGLONG)retaddr;
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x228,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\syncstate.cpp",
          (const char *)(unsigned int)v34,
          v56);
      v61 = 0;
      v35 = v18 & 4;
      if ( v35 )
      {
        EssentialProps::ReadPropertiesIfNeeded((EssentialProps *)&v66, (const unsigned __int16 *)hMem);
        if ( v67 != 16 )
        {
          if ( v67 == 1 )
          {
            v31 = *(_DWORD *)(a3 + 4);
            if ( v31 > 10 )
              *v30 = 10;
          }
          else
          {
            if ( v67 != 2 )
            {
LABEL_114:
              if ( v31 != *v30 )
                CloudSyncStateTelemetry::LogUpgradedFolderEnumerationState<unsigned short (&)[260],__int64 &,enum PrimarySyncState &,enum PrimarySyncState &>(
                  &pszMore,
                  v83,
                  &PerformanceCount,
                  v30);
              goto LABEL_41;
            }
            v31 = *v30;
            if ( *v30 > 11 )
              *v30 = 11;
          }
          PerformanceCount.LowPart = v31;
          goto LABEL_114;
        }
      }
LABEL_41:
      v22 = v63;
      if ( !v63 || !v62 )
      {
        if ( v20 == 2 )
        {
          v36 = 1;
        }
        else
        {
          if ( v20 )
            goto LABEL_102;
          if ( v35 )
            EssentialProps::ReadPropertiesIfNeeded((EssentialProps *)&v66, (const unsigned __int16 *)hMem);
          if ( (v66 & 3) != 0 )
LABEL_102:
            v36 = 0;
          else
            v36 = 1;
        }
        v57 = v36;
      }
      v37 = *v30;
      if ( v28 == 14 )
      {
        if ( v37 <= 14 )
          goto LABEL_57;
        *v30 = 14;
        v41 = 14;
        goto LABEL_58;
      }
      v38 = v28 - 3;
      if ( v38 && (v39 = v38 - 1) != 0 && (v40 = v39 - 1) != 0 )
      {
        if ( v40 == 2 )
        {
          if ( v37 > 13 )
          {
            *v30 = 13;
            v41 = 13;
            goto LABEL_58;
          }
LABEL_57:
          v41 = *v30;
          goto LABEL_58;
        }
      }
      else
      {
        if ( v37 <= 12 )
          goto LABEL_57;
        *v30 = 12;
        v41 = 12;
LABEL_58:
        if ( v37 != v41 && CloudSyncStateTelemetry::IsEnabled(v24, v17) )
        {
          wil::details::static_lazy<CloudSyncStateTelemetry>::get(
            v24,
            _lambda_1305fb88a4554f9da3f78f3fa403ef92_::_lambda_invoker_cdecl_);
          CloudSyncStateTelemetry::LogUpgradedFolderEnumerationState_(v51, &pszMore, v83[0], (unsigned int)v37, *v30);
        }
      }
      v29 = v58;
      v25 = v62;
      v13 = v57;
    }
    v4 = a3;
    v10 = (unsigned int *)(a3 + 8);
    if ( *(_BYTE *)(a3 + 2) )
    {
      ModifySyncAvailabilityFlags(a3 + 8, v64);
      v24 = *(unsigned __int8 *)(a3 + 2);
    }
    else
    {
      LOBYTE(v24) = 0;
    }
    v42 = 0;
    if ( *(_BYTE *)(a3 + 1) )
      v42 = *(_DWORD *)(a3 + 4) > 10;
    if ( (_BYTE)v24 )
    {
      v24 = *v10;
      LOBYTE(v24) = (v24 & 2) != 0 && (v24 & 4) == 0;
      v42 |= v24;
    }
    if ( !v42 )
    {
      if ( hMem )
        LocalFree(hMem);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v86);
      if ( v59 )
LABEL_109:
        RtlSetThreadPlaceholderCompatibilityMode(v60);
      return 0;
    }
    v43 = v75;
    if ( v75 )
    {
      ++*v75;
      if ( *v43 >= v43[4] )
      {
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        PerformanceCount.QuadPart -= *((_QWORD *)v43 + 1);
        Frequency.QuadPart = 0;
        QueryPerformanceFrequency(&Frequency);
        v24 = Frequency.QuadPart / 1000;
        v17 = PerformanceCount.QuadPart % (Frequency.QuadPart / 1000);
        if ( PerformanceCount.QuadPart / (Frequency.QuadPart / 1000) <= *((_QWORD *)v43 + 3) )
        {
          *(_BYTE *)(a3 + 3) = 0;
          if ( hMem )
            LocalFree(hMem);
          if ( v86 )
            (*(void (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v86 + 16LL))(v86, v17);
          if ( v59 )
            goto LABEL_109;
          return 0;
        }
      }
    }
    if ( !v29 && (v79[0] & 0x10) != 0 )
    {
      if ( v22 && v25 )
      {
        *(_BYTE *)(a3 + 3) = 0;
      }
      else
      {
        v44 = hMem;
        if ( !hMem )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &hMem,
            0);
          v49 = PathAllocCombine((PCWSTR)*v69, &pszMore, 1u, (PWSTR *)&hMem);
          v24 = (LONGLONG)retaddr;
          if ( v49 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x279,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\syncstate.cpp",
              (const char *)(unsigned int)v49,
              v56);
          v44 = hMem;
        }
        v70 = v44;
        hMem = 0;
        v71 = v13;
        v72 = 0;
        v73 = 0;
        v74 = 0;
        v45 = v76;
        if ( v76[1] == 0x7FFFFFFFFFFFFFFLL )
          std::_Xlength_error("list too long");
        v46 = *v76;
        v77 = v76;
        v78 = 0;
        v47 = std::allocator<std::_List_node<FolderEnumerationData,void *>>::allocate(v24, v17, v10, v11);
        *(_QWORD *)(v47 + 16) = v44;
        v70 = 0;
        *(_BYTE *)(v47 + 24) = v13;
        ++v45[1];
        v48 = *(__int64 **)(v46 + 8);
        *(_QWORD *)v47 = v46;
        *(_QWORD *)(v47 + 8) = v48;
        v78 = 0;
        *(_QWORD *)(v46 + 8) = v47;
        *v48 = v47;
        v4 = a3;
      }
    }
    if ( hMem )
      LocalFree(hMem);
LABEL_72:
    v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *, unsigned int *, __int64))(*(_QWORD *)v86 + 56LL))(
           v86,
           v79,
           v10,
           v11);
  }
  if ( v61 )
  {
    if ( *((_BYTE *)v69 + 8) )
    {
      v53 = *(_DWORD *)(v4 + 4);
      if ( v53 > 13 )
      {
        *(_DWORD *)(v4 + 4) = 13;
        if ( CloudSyncStateTelemetry::IsEnabled(v12, v9) )
        {
          wil::details::static_lazy<CloudSyncStateTelemetry>::get(
            v54,
            _lambda_1305fb88a4554f9da3f78f3fa403ef92_::_lambda_invoker_cdecl_);
          CloudSyncStateTelemetry::LogUpgradedFolderEnumerationState_(
            v55,
            &pszMore,
            v83[0],
            (unsigned int)v53,
            *(_DWORD *)(v4 + 4));
        }
      }
    }
  }
  if ( v86 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
  if ( v59 )
    RtlSetThreadPlaceholderCompatibilityMode(v60);
  return 1;
}

```

## disassembly

```asm
0x180079000  push    rbp
0x180079002  push    rbx
0x180079003  push    rsi
0x180079004  push    rdi
0x180079005  push    r12
0x180079007  push    r13
0x180079009  push    r14
0x18007900b  push    r15
0x18007900d  lea     rbp, [rsp-248h]
0x180079015  sub     rsp, 348h
0x18007901c  mov     rax, cs:__security_cookie
0x180079023  xor     rax, rsp
0x180079026  mov     [rbp+280h+var_50], rax
0x18007902d  mov     [rbp+280h+var_300], r9
0x180079031  mov     rdi, r8
0x180079034  mov     [rsp+380h+var_338], r8
0x180079039  mov     [rsp+380h+var_308], rdx
0x18007903e  mov     rbx, rcx
0x180079041  mov     [rsp+380h+var_320], rcx
0x180079046  mov     [rsp+380h+var_34C], 0
0x18007904b  call    cs:__imp_RtlQueryThreadPlaceholderCompatibilityMode
0x180079052  nop     dword ptr [rax+rax+00h]
0x180079057  cmp     al, 2
0x180079059  jz      short loc_180079072
0x18007905b  mov     cl, 2
0x18007905d  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x180079064  nop     dword ptr [rax+rax+00h]
0x180079069  mov     [rsp+380h+var_34B], al
0x18007906d  mov     [rsp+380h+var_34C], 1
0x180079072  xor     edx, edx; Val
0x180079074  mov     r8d, 268h; Size
0x18007907a  lea     rcx, [rbp+280h+var_2E0]; void *
0x18007907e  call    memset_0
0x180079083  nop
0x180079084  mov     [rbp+280h+var_60], 0
0x18007908f  lea     r8, [rbp+280h+var_60]
0x180079096  lea     rdx, _GUID_4e31e71d_945b_471d_88a9_061b207facaa
0x18007909d  xor     ecx, ecx
0x18007909f  call    CEnumFiles_CreateInstance
0x1800790a4  mov     rcx, [rbp+288h]; this
0x1800790ab  test    eax, eax
0x1800790ad  js      loc_180079770
0x1800790b3  mov     rcx, [rbp+280h+var_60]
0x1800790ba  mov     rax, [rcx]
0x1800790bd  lea     r8, [rbp+280h+var_2E0]
0x1800790c1  mov     rdx, [rbx]
0x1800790c4  mov     rax, [rax+20h]
0x1800790c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790cd  mov     rcx, [rbp+288h]; unsigned __int8
0x1800790d4  test    eax, eax
0x1800790d6  js      loc_180079785
0x1800790dc  mov     [rsp+380h+var_348], 1
0x1800790e1  mov     ebx, 5
0x1800790e6  test    eax, eax
0x1800790e8  jnz     loc_1800795A0
0x1800790ee  cmp     [rbp+280h+pszMore], 2Eh ; '.'
0x1800790f3  jz      loc_1800794E6
0x1800790f9  mov     [rbp+280h+hMem], 0
0x180079104  xor     r13b, r13b
0x180079107  mov     [rsp+380h+var_350], r13b
0x18007910c  mov     r15d, [rbp+280h+var_2E0]
0x180079110  bt      r15d, 0Ah
0x180079115  mov     edx, 0
0x18007911a  cmovb   edx, [rbp+280h+var_2BC]
0x18007911e  mov     ecx, r15d
0x180079121  call    cs:__imp_CfGetPlaceholderStateFromAttributeTag
0x180079128  nop     dword ptr [rax+rax+00h]
0x18007912d  mov     r12d, eax
0x180079130  mov     ecx, r15d
0x180079133  and     ecx, 180000h
0x180079139  mov     r8d, eax
0x18007913c  jnz     loc_18007951D
0x180079142  xor     edi, edi
0x180079144  and     r8d, 1
0x180079148  mov     r14d, r12d
0x18007914b  and     r14d, 10h
0x18007914f  mov     ecx, r12d
0x180079152  mov     [rsp+380h+var_340], r14d
0x180079157  and     ecx, 8
0x18007915a  and     r15d, 10h
0x18007915e  mov     edx, r15d
0x180079161  mov     eax, 1
0x180079166  mov     r9d, eax
0x180079169  mov     [rsp+380h+var_33C], eax
0x18007916d  mov     [rsp+380h+var_344], edx
0x180079171  cmp     edi, eax
0x180079173  jz      loc_180079401
0x180079179  or      eax, 2
0x18007917c  cmp     edi, 1
0x18007917f  cmovnz  eax, r9d
0x180079183  test    r14d, r14d
0x180079186  jnz     short loc_1800791A9
0x180079188  test    r15d, r15d
0x18007918b  jnz     short loc_1800791A9
0x18007918d  cmp     edi, 2
0x180079190  jz      short loc_1800791B2
0x180079192  cmp     edi, 3
0x180079195  jz      loc_18007953F
0x18007919b  mov     r10d, eax
0x18007919e  or      r10d, 4
0x1800791a2  mov     [rsp+380h+var_33C], r10d
0x1800791a7  jmp     short loc_1800791B2
0x1800791a9  cmp     edi, 3
0x1800791ac  jz      loc_180079536
0x1800791b2  test    ecx, ecx
0x1800791b4  jz      loc_18007983D
0x1800791ba  lea     eax, [rdi-1]
0x1800791bd  test    eax, 0FFFFFFFDh
0x1800791c2  jnz     short loc_1800791CD
0x1800791c4  test    r14d, r14d
0x1800791c7  jnz     loc_180079833
0x1800791cd  cmp     edi, 2
0x1800791d0  jz      loc_180079431
0x1800791d6  test    r14d, r14d
0x1800791d9  jnz     loc_18007943A
0x1800791df  cmp     edi, 1
0x1800791e2  jz      short loc_1800791F2
0x1800791e4  mov     esi, 0Eh
0x1800791e9  cmp     edi, 3
0x1800791ec  jnz     short loc_1800791F7
0x1800791ee  mov     bl, 1
0x1800791f0  jmp     short loc_1800791F9
0x1800791f2  mov     esi, 0Fh
0x1800791f7  xor     bl, bl
0x1800791f9  mov     [rsp+380h+var_34F], bl
0x1800791fd  mov     rax, [rsp+380h+var_338]
0x180079202  cmp     [rax+1], r13b
0x180079206  jz      loc_180079372
0x18007920c  test    bl, bl
0x18007920e  jnz     loc_180079372
0x180079214  test    [rbp+280h+var_2E0], 100h
0x18007921b  jnz     loc_180079372
0x180079221  mov     [rax], r13b
0x180079224  lea     r13, [rax+4]
0x180079228  mov     r15d, [r13+0]
0x18007922c  mov     dword ptr [rbp+280h+PerformanceCount], r15d
0x180079233  mov     [rsp+380h+var_330], 0
0x18007923b  mov     [rsp+380h+var_32C], 10h
0x180079243  mov     [rsp+380h+var_328], bl
0x180079247  mov     r14, [rbp+280h+hMem]
0x18007924e  test    r14, r14
0x180079251  jz      short loc_18007927E
0x180079253  call    cs:__imp_GetLastError
0x18007925a  nop     dword ptr [rax+rax+00h]
0x18007925f  mov     ebx, eax
0x180079261  mov     rcx, r14; hMem
0x180079264  call    cs:__imp_LocalFree
0x18007926b  nop     dword ptr [rax+rax+00h]
0x180079270  mov     ecx, ebx; dwErrCode
0x180079272  call    cs:__imp_SetLastError
0x180079279  nop     dword ptr [rax+rax+00h]
0x18007927e  mov     [rbp+280h+hMem], 0
0x180079289  lea     r9, [rbp+280h+hMem]; ppszPathOut
0x180079290  mov     r8d, 1; dwFlags
0x180079296  lea     rdx, [rbp+280h+pszMore]; pszMore
0x18007929a  mov     rax, [rsp+380h+var_320]
0x18007929f  mov     rcx, [rax]; pszPathIn
0x1800792a2  call    cs:__imp_PathAllocCombine
0x1800792a9  nop     dword ptr [rax+rax+00h]
0x1800792ae  mov     rcx, [rbp+288h]; this
0x1800792b5  test    eax, eax
0x1800792b7  js      loc_18007941C
0x1800792bd  mov     [rsp+380h+var_348], 0
0x1800792c2  and     r12d, 4
0x1800792c6  jnz     loc_180079705
0x1800792cc  mov     r14d, [rsp+380h+var_340]
0x1800792d1  test    r14d, r14d
0x1800792d4  jnz     loc_18007950D
0x1800792da  cmp     edi, 2
0x1800792dd  jz      loc_18007988B
0x1800792e3  test    edi, edi
0x1800792e5  jnz     loc_180079638
0x1800792eb  test    r12d, r12d
0x1800792ee  jz      short loc_180079301
0x1800792f0  mov     rdx, [rbp+280h+hMem]; unsigned __int16 *
0x1800792f7  lea     rcx, [rsp+380h+var_330]; this
0x1800792fc  call    ?ReadPropertiesIfNeeded@EssentialProps@@QEAAXPEBG@Z; EssentialProps::ReadPropertiesIfNeeded(ushort const *)
0x180079301  test    byte ptr [rsp+380h+var_330], 3
0x180079306  jnz     loc_180079638
0x18007930c  mov     al, 1
0x18007930e  mov     [rsp+380h+var_350], al
0x180079312  mov     ebx, [r13+0]
0x180079316  cmp     esi, 0Eh
0x180079319  jz      short loc_18007934F
0x18007931b  sub     esi, 3
0x18007931e  jz      loc_18007984D
0x180079324  sub     esi, 1
0x180079327  jz      loc_18007984D
0x18007932d  sub     esi, 1
0x180079330  jz      loc_18007984D
0x180079336  cmp     esi, 2
0x180079339  jnz     short loc_180079362
0x18007933b  cmp     ebx, 0Dh
0x18007933e  jle     short loc_180079358
0x180079340  mov     dword ptr [r13+0], 0Dh
0x180079348  mov     eax, 0Dh
0x18007934d  jmp     short loc_18007935A
0x18007934f  cmp     ebx, 0Eh
0x180079352  jg      loc_180079879
0x180079358  mov     eax, ebx
0x18007935a  cmp     ebx, eax
0x18007935c  jnz     loc_180079602
0x180079362  movzx   ebx, [rsp+380h+var_34F]
0x180079367  mov     r15d, [rsp+380h+var_344]
0x18007936c  movzx   r13d, [rsp+380h+var_350]
0x180079372  mov     rdi, [rsp+380h+var_338]
0x180079377  lea     r8, [rdi+8]
0x18007937b  cmp     byte ptr [rdi+2], 0
0x18007937f  jnz     loc_18007992E
0x180079385  xor     cl, cl
0x180079387  xor     al, al
0x180079389  cmp     [rdi+1], al
0x18007938c  jz      short loc_180079395
0x18007938e  cmp     dword ptr [rdi+4], 0Ah
0x180079392  setnle  al
0x180079395  test    cl, cl
0x180079397  jnz     loc_180079943
0x18007939d  test    al, al
0x18007939f  jz      loc_1800798D5
0x1800793a5  mov     rsi, [rsp+380h+var_308]
0x1800793aa  test    rsi, rsi
0x1800793ad  jz      short loc_1800793BC
0x1800793af  inc     dword ptr [rsi]
0x1800793b1  mov     eax, [rsi]
0x1800793b3  cmp     eax, [rsi+10h]
0x1800793b6  jnb     loc_18007963F
0x1800793bc  test    bl, bl
0x1800793be  jnz     short loc_1800793C6
0x1800793c0  test    byte ptr [rbp+280h+var_2E0], 10h
0x1800793c4  jnz     short loc_180079444
0x1800793c6  mov     rcx, [rbp+280h+hMem]; hMem
0x1800793cd  test    rcx, rcx
0x1800793d0  jnz     short loc_1800793F3
0x1800793d2  mov     ebx, 5
0x1800793d7  mov     rcx, [rbp+280h+var_60]
0x1800793de  mov     rax, [rcx]
0x1800793e1  lea     rdx, [rbp+280h+var_2E0]
0x1800793e5  mov     rax, [rax+38h]
0x1800793e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793ee  jmp     loc_1800790E6
0x1800793f3  call    cs:__imp_LocalFree
0x1800793fa  nop     dword ptr [rax+rax+00h]
0x1800793ff  jmp     short loc_1800793D2
0x180079401  mov     [rsp+380h+var_33C], 3
0x180079409  mov     eax, 3
0x18007940e  mov     [rsp+380h+var_340], r14d
0x180079413  mov     [rsp+380h+var_344], edx
0x180079417  jmp     loc_18007917C
0x18007941c  mov     r9d, eax; char *
0x18007941f  lea     r8, aOnecoreuapShel_182; "onecoreuap\\shell\\windows.storage\\syn"...
0x180079426  mov     edx, 228h; void *
0x18007942b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079431  test    r14d, r14d
0x180079434  jz      loc_1800797C3
0x18007943a  mov     esi, 7
0x18007943f  jmp     loc_1800791E9
0x180079444  test    r14d, r14d
0x180079447  jnz     loc_18007975E
0x18007944d  mov     rdi, [rbp+280h+hMem]
0x180079454  test    rdi, rdi
0x180079457  jz      loc_180079549
0x18007945d  mov     [rsp+380h+var_318], rdi
0x180079462  mov     [rbp+280h+hMem], 0
0x18007946d  mov     [rsp+380h+var_310], r13b
0x180079472  xor     eax, eax
0x180079474  mov     [rsp+380h+var_30F], eax
0x180079478  mov     [rsp+380h+var_30B], ax
0x18007947d  mov     [rsp+380h+var_309], al
0x180079481  mov     rsi, [rbp+280h+var_300]
0x180079485  mov     rax, 7FFFFFFFFFFFFFFh
0x18007948f  cmp     [rsi+8], rax
0x180079493  jz      loc_18007995F
0x180079499  mov     rbx, [rsi]
0x18007949c  mov     [rbp+280h+var_2F8], rsi
0x1800794a0  mov     [rbp+280h+var_2F0], 0
0x1800794a8  call    ?allocate@?$allocator@U?$_List_node@UFolderEnumerationData@@PEAX@std@@@std@@QEAAPEAU?$_List_node@UFolderEnumerationData@@PEAX@2@_K@Z; std::allocator<std::_List_node<FolderEnumerationData,void *>>::allocate(unsigned __int64)
0x1800794ad  mov     [rax+10h], rdi
0x1800794b1  mov     [rsp+380h+var_318], 0
0x1800794ba  mov     [rax+18h], r13b
0x1800794be  inc     qword ptr [rsi+8]
0x1800794c2  mov     rcx, [rbx+8]
0x1800794c6  mov     [rax], rbx
0x1800794c9  mov     [rax+8], rcx
0x1800794cd  mov     [rbp+280h+var_2F0], 0
0x1800794d5  mov     [rbx+8], rax
0x1800794d9  mov     [rcx], rax
0x1800794dc  mov     rdi, [rsp+380h+var_338]
0x1800794e1  jmp     loc_1800793C6
0x1800794e6  movzx   eax, [rbp+280h+var_2B2]
0x1800794ea  test    ax, ax
0x1800794ed  jz      loc_1800793D7
0x1800794f3  cmp     [rbp+280h+var_2B0], 0
0x1800794f8  jnz     loc_1800790F9
0x1800794fe  cmp     ax, 2Eh ; '.'
0x180079502  jnz     loc_1800790F9
0x180079508  jmp     loc_1800793D7
0x18007950d  cmp     [rsp+380h+var_344], 0
0x180079512  jz      loc_1800792DA
0x180079518  jmp     loc_180079312
0x18007951d  cmp     ecx, 80000h
  ... truncated ...
```
