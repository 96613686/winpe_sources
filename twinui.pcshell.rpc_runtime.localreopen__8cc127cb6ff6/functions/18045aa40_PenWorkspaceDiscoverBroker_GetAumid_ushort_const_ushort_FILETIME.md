# PenWorkspaceDiscoverBroker::GetAumid(ushort const *,ushort * *,_FILETIME *)

- ea: `0x18045aa40`
- end: `0x18045b0ba`
- name: `?GetAumid@PenWorkspaceDiscoverBroker@@UEAAJPEBGPEAPEAGPEAU_FILETIME@@@Z`
- size: `1658`
- prototype: `int(PenWorkspaceDiscoverBroker *__hidden this, const unsigned __int16 *, unsigned __int16 **, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x18005a710`
- `0x18007b3e0`
- `0x180086ac0`
- `0x18008a6f0`
- `0x180356360`
- `0x180459ae8`
- `0x180459f08`
- `0x18045a020`
- `0x18045aa40`
- `0x18045b0d8`
- `0x18066a0f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ad6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ae22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ae8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045aec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045af41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045af63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045affb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ad6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ae22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045ae8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045aec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045af41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045af63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18045affb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18045ad8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18045aee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18045ad8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18045aee1`

## string_xrefs

- `0x18045aa8e`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045aadf`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045ab2a`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045ab90`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045abd9`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045ac64`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045acb0`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045ae5c`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045aead`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045af04`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045afc1`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045afe5`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045b00e`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`
- `0x18045b032`: `pcshell\twinui\penworkspace\broker\lib\discoverbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall PenWorkspaceDiscoverBroker::GetAumid(
        PenWorkspaceDiscoverBroker *this,
        char *a2,
        unsigned __int16 **a3,
        struct _FILETIME *a4)
{
  int IsShellExperience; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64, __int64, __int64 *); // rbx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  unsigned int i; // esi
  __int64 v59; // rdi
  __int64 (__fastcall *v60)(__int64, _QWORD, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **); // rbx
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v65; // rdi
  __int64 (__fastcall *v66)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, __int64 *); // rbx
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rbx
  __int64 (__fastcall *v72)(__int64, HSTRING *); // rdi
  int v73; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v75; // r9
  char *v76; // r8
  __int64 v77; // rdx
  int v78; // ecx
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v79; // rdi
  __int64 (__fastcall *v80)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  int (__fastcall ***v85)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v86)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  int InstallTime; // eax
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 v103; // rdi
  __int64 (__fastcall *v104)(__int64, HSTRING *); // rbx
  int v105; // eax
  PCWSTR v106; // rax
  int v107; // eax
  unsigned __int16 *Reserved1; // rax
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  __int64 v124; // rdx
  __int64 v125; // r8
  __int64 v126; // r9
  __int64 v127; // rdx
  __int64 v128; // r8
  __int64 v129; // r9
  __int64 v130; // rdx
  __int64 v131; // r8
  __int64 v132; // r9
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // r9
  __int64 v136; // rdx
  __int64 v137; // r8
  __int64 v138; // r9
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // r9
  __int64 v142; // rdx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v149; // [rsp+20h] [rbp-69h] BYREF
  __int64 v150; // [rsp+28h] [rbp-61h] BYREF
  __int64 v151; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  __int64 v153; // [rsp+40h] [rbp-49h] BYREF
  __int64 v154; // [rsp+48h] [rbp-41h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v155; // [rsp+50h] [rbp-39h] BYREF
  __int64 v156; // [rsp+58h] [rbp-31h] BYREF
  HSTRING v157; // [rsp+60h] [rbp-29h] BYREF
  int (__fastcall ***v158)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-21h] BYREF
  __int64 v159; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v160; // [rsp+78h] [rbp-11h] BYREF
  __int64 v161; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v163; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *a3 = 0;
  *a4 = 0;
  IsShellExperience = CallerIdentity::EnsureCallingProcessIsShellExperience(this);
  v8 = IsShellExperience;
  if ( IsShellExperience >= 0 )
  {
    v161 = 0;
    v163 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsInternal.Shell.UnifiedTile.UnifiedTileManager",
      0x35u,
      0x34u);
    v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(
           v163,
           &v161);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
        (const char *)(unsigned int)v9,
        v149);
LABEL_62:
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v161, v13, v14, v15);
      return v8;
    }
    v149 = 0;
    v16 = v161;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v161 + 48LL);
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v149, v10, v11, v12);
    v18 = v17(v16, 33, 3, &v149);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 68;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
        (const char *)(unsigned int)v18,
        v149);
LABEL_8:
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v149, v20, v21, v22);
      goto LABEL_62;
    }
    v18 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(v149);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 70;
      goto LABEL_7;
    }
    v150 = 0;
    v26 = v149;
    v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v149 + 64LL);
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v150, v23, v24, v25);
    v28 = v27(v26, &v150);
    v8 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
        (const char *)(unsigned int)v28,
        v149);
LABEL_13:
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v150, v29, v30, v31);
      goto LABEL_8;
    }
    v151 = 0;
    v32 = v150;
    v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v150 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v151);
    v34 = v33(v32, &v151);
    v8 = v34;
    if ( v34 >= 0 )
    {
      v34 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v151);
      v8 = v34;
      if ( v34 >= 0 )
      {
        v154 = 0;
        v39 = v150;
        v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v150 + 56LL);
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v154, v36, v37, v38);
        v163 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AllApps", 8u, 7u);
        v41 = v40(v39, 1, v163, &v154);
        v8 = v41;
        if ( v41 >= 0 )
        {
          v153 = 0;
          v48 = v154;
          v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v154 + 56LL);
          Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v153, v42, v43, v44);
          v50 = v49(v48, &v153);
          v8 = v50;
          if ( v50 >= 0 )
          {
            v160 = 0;
            v50 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v153 + 56LL))(v153, &v160);
            v8 = v50;
            if ( v50 >= 0 )
            {
              for ( i = 0; i < v160; ++i )
              {
                v155 = 0;
                v59 = v153;
                v60 = *(__int64 (__fastcall **)(__int64, _QWORD, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **))(*(_QWORD *)v153 + 48LL);
                Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v155, v55, v56, v57);
                v61 = v60(v59, i, &v155);
                v8 = v61;
                if ( v61 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x5B,
                    (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                    (const char *)(unsigned int)v61,
                    v149);
                  goto LABEL_60;
                }
                v156 = 0;
                v65 = v155;
                v66 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, __int64 *))(*(_QWORD *)v155 + 104LL);
                Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v156, v62, v63, v64);
                v67 = v66(v65, &v156);
                v8 = v67;
                if ( v67 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x5E,
                    (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                    (const char *)(unsigned int)v67,
                    v149);
                  goto LABEL_58;
                }
                v71 = v156;
                if ( v156 )
                {
                  string = 0;
                  v72 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v156 + 48LL);
                  WindowsDeleteString(0);
                  string = 0;
                  v73 = v72(v71, &string);
                  v8 = v73;
                  if ( v73 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x63,
                      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                      (const char *)(unsigned int)v73,
                      v149);
                    goto LABEL_56;
                  }
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  v76 = (char *)(a2 - (char *)StringRawBuffer);
                  do
                  {
                    v77 = *(unsigned __int16 *)&v76[(_QWORD)StringRawBuffer];
                    v78 = *StringRawBuffer - (_DWORD)v77;
                    if ( v78 )
                      break;
                    ++StringRawBuffer;
                  }
                  while ( (_DWORD)v77 );
                  if ( !v78 )
                  {
                    v158 = 0;
                    v79 = v155;
                    v80 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v155 + 48LL);
                    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v158, v77, v76, v75);
                    v81 = v80(v79, &v158);
                    v8 = v81;
                    if ( v81 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x68,
                        (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                        (const char *)(unsigned int)v81,
                        v149);
                      goto LABEL_54;
                    }
                    v159 = 0;
                    v85 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v158;
                    v86 = **v158;
                    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v159, v82, v83, v84);
                    if ( v86(v85, &GUID_a7668288_cc23_4b67_be8b_6c10455986b8, &v159) >= 0 )
                    {
                      InstallTime = PenWorkspaceDiscoverBroker::GetInstallTime(v155, a4);
                      v8 = InstallTime;
                      if ( InstallTime >= 0 )
                      {
                        v157 = 0;
                        v103 = v159;
                        v104 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v159 + 48LL);
                        WindowsDeleteString(0);
                        v157 = 0;
                        v105 = v104(v103, &v157);
                        v8 = v105;
                        if ( v105 >= 0 )
                        {
                          memset(&hstringHeader, 0, sizeof(hstringHeader));
                          v106 = WindowsGetStringRawBuffer(v157, 0);
                          v107 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                                   &hstringHeader,
                                   v106,
                                   -1);
                          v8 = v107;
                          if ( v107 >= 0 )
                          {
                            Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
                            memset(&hstringHeader, 0, sizeof(hstringHeader));
                            *a3 = Reserved1;
                            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                            WindowsDeleteString(v157);
                            v157 = 0;
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v159, v109, v110, v111);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v158, v112, v113, v114);
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v156, v115, v116, v117);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v155, v118, v119, v120);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v153, v121, v122, v123);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v154, v124, v125, v126);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v151);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v150, v127, v128, v129);
                            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v149, v130, v131, v132);
                            v8 = 0;
                            goto LABEL_62;
                          }
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x73,
                            (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                            (const char *)(unsigned int)v107,
                            v149);
                          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x70,
                            (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                            (const char *)(unsigned int)v105,
                            v149);
                        }
                        WindowsDeleteString(v157);
                        v157 = 0;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x6D,
                          (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
                          (const char *)(unsigned int)InstallTime,
                          v149);
                      }
                      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v159, v97, v98, v99);
LABEL_54:
                      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v158, v100, v101, v102);
LABEL_56:
                      WindowsDeleteString(string);
                      string = 0;
LABEL_58:
                      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v156, v133, v134, v135);
LABEL_60:
                      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v155, v136, v137, v138);
                      goto LABEL_26;
                    }
                    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v159, v87, v88, v89);
                    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v158, v90, v91, v92);
                  }
                  WindowsDeleteString(string);
                }
                Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v156, v68, v69, v70);
                Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v155, v93, v94, v95);
              }
              Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v153, v55, v56, v57);
              Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v154, v139, v140, v141);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v151);
              Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v150, v142, v143, v144);
              Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v149, v145, v146, v147);
              v8 = -2147023728;
              goto LABEL_62;
            }
            v51 = 86;
          }
          else
          {
            v51 = 83;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v51,
            (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
            (const char *)(unsigned int)v50,
            v149);
LABEL_26:
          Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v153, v52, v53, v54);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x50,
            (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
            (const char *)(unsigned int)v41,
            v149);
        }
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v154, v45, v46, v47);
        goto LABEL_17;
      }
      v35 = 77;
    }
    else
    {
      v35 = 76;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
      (const char *)(unsigned int)v34,
      v149);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v151);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\discoverbroker.cpp",
    (const char *)(unsigned int)IsShellExperience,
    v149);
  return v8;
}

```

## disassembly

```asm
0x18045aa40  mov     [rsp-8+arg_0], rbx
0x18045aa45  push    rbp
0x18045aa46  push    rsi
0x18045aa47  push    rdi
0x18045aa48  push    r12
0x18045aa4a  push    r13
0x18045aa4c  push    r14
0x18045aa4e  push    r15
0x18045aa50  lea     rbp, [rsp-27h]
0x18045aa55  sub     rsp, 0B0h
0x18045aa5c  mov     rax, cs:__security_cookie
0x18045aa63  xor     rax, rsp
0x18045aa66  mov     [rbp+57h+var_38], rax
0x18045aa6a  mov     r14, r9
0x18045aa6d  mov     r15, r8
0x18045aa70  mov     r12, rdx
0x18045aa73  xor     r13d, r13d
0x18045aa76  mov     [r8], r13
0x18045aa79  mov     [r9], r13
0x18045aa7c  call    ?EnsureCallingProcessIsShellExperience@CallerIdentity@@YAJXZ; CallerIdentity::EnsureCallingProcessIsShellExperience(void)
0x18045aa81  mov     ebx, eax
0x18045aa83  test    eax, eax
0x18045aa85  jns     short loc_18045AAA3
0x18045aa87  mov     rcx, [rbp+5Fh]; this
0x18045aa8b  mov     r9d, eax; char *
0x18045aa8e  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045aa95  lea     edx, [r13+3Bh]; void *
0x18045aa99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045aa9e  jmp     loc_18045B091
0x18045aaa3  mov     [rbp+57h+var_60], r13
0x18045aaa7  mov     [rbp+57h+var_40], r13
0x18045aaab  mov     r9d, 34h ; '4'; unsigned int
0x18045aab1  lea     r8d, [r9+1]; unsigned int
0x18045aab5  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x18045aabc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18045aac0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18045aac5  lea     rdx, [rbp+57h+var_60]
0x18045aac9  mov     rcx, [rbp+57h+var_40]
0x18045aacd  call    ??$GetActivationFactory@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>)
0x18045aad2  mov     ebx, eax
0x18045aad4  test    eax, eax
0x18045aad6  jns     short loc_18045AAF5
0x18045aad8  mov     rcx, [rbp+5Fh]; this
0x18045aadc  mov     r9d, eax; char *
0x18045aadf  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045aae6  mov     edx, 41h ; 'A'; void *
0x18045aaeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045aaf0  jmp     loc_18045B088
0x18045aaf5  mov     [rbp+57h+var_C0], r13
0x18045aaf9  mov     rdi, [rbp+57h+var_60]
0x18045aafd  mov     rax, [rdi]
0x18045ab00  mov     rbx, [rax+30h]
0x18045ab04  lea     rcx, [rbp+57h+var_C0]
0x18045ab08  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ab0d  lea     r9, [rbp+57h+var_C0]
0x18045ab11  mov     edx, 21h ; '!'
0x18045ab16  lea     r8d, [rdx-1Eh]
0x18045ab1a  mov     rcx, rdi
0x18045ab1d  call    rbx
0x18045ab1f  mov     ebx, eax
0x18045ab21  test    eax, eax
0x18045ab23  jns     short loc_18045AB4C
0x18045ab25  mov     edx, 44h ; 'D'; void *
0x18045ab2a  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045ab31  mov     r9d, eax; char *
0x18045ab34  mov     rcx, [rbp+5Fh]; this
0x18045ab38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045ab3d  nop
0x18045ab3e  lea     rcx, [rbp+57h+var_C0]
0x18045ab42  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ab47  jmp     loc_18045B088
0x18045ab4c  mov     rcx, [rbp+57h+var_C0]
0x18045ab50  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *> *,tagCOWAIT_FLAGS,void *)
0x18045ab55  mov     ebx, eax
0x18045ab57  test    eax, eax
0x18045ab59  jns     short loc_18045AB62
0x18045ab5b  mov     edx, 46h ; 'F'
0x18045ab60  jmp     short loc_18045AB2A
0x18045ab62  mov     [rbp+57h+var_B8], r13
0x18045ab66  mov     rdi, [rbp+57h+var_C0]
0x18045ab6a  mov     rax, [rdi]
0x18045ab6d  mov     rbx, [rax+40h]
0x18045ab71  lea     rcx, [rbp+57h+var_B8]
0x18045ab75  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ab7a  lea     rdx, [rbp+57h+var_B8]
0x18045ab7e  mov     rcx, rdi
0x18045ab81  call    rbx
0x18045ab83  mov     ebx, eax
0x18045ab85  test    eax, eax
0x18045ab87  jns     short loc_18045ABAD
0x18045ab89  mov     rcx, [rbp+5Fh]; this
0x18045ab8d  mov     r9d, eax; char *
0x18045ab90  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045ab97  mov     edx, 49h ; 'I'; void *
0x18045ab9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045aba1  nop
0x18045aba2  lea     rcx, [rbp+57h+var_B8]
0x18045aba6  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045abab  jmp     short loc_18045AB3E
0x18045abad  mov     [rbp+57h+var_B0], r13
0x18045abb1  mov     rdi, [rbp+57h+var_B8]
0x18045abb5  mov     rax, [rdi]
0x18045abb8  mov     rbx, [rax+50h]
0x18045abbc  lea     rcx, [rbp+57h+var_B0]
0x18045abc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18045abc5  lea     rdx, [rbp+57h+var_B0]
0x18045abc9  mov     rcx, rdi
0x18045abcc  call    rbx
0x18045abce  mov     ebx, eax
0x18045abd0  test    eax, eax
0x18045abd2  jns     short loc_18045ABF8
0x18045abd4  mov     edx, 4Ch ; 'L'; void *
0x18045abd9  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045abe0  mov     r9d, eax; char *
0x18045abe3  mov     rcx, [rbp+5Fh]; this
0x18045abe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045abec  nop
0x18045abed  lea     rcx, [rbp+57h+var_B0]
0x18045abf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18045abf6  jmp     short loc_18045ABA2
0x18045abf8  mov     rcx, [rbp+57h+var_B0]
0x18045abfc  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18045ac01  mov     ebx, eax
0x18045ac03  test    eax, eax
0x18045ac05  jns     short loc_18045AC0E
0x18045ac07  mov     edx, 4Dh ; 'M'
0x18045ac0c  jmp     short loc_18045ABD9
0x18045ac0e  mov     [rbp+57h+var_98], r13
0x18045ac12  mov     rdi, [rbp+57h+var_B8]
0x18045ac16  mov     rax, [rdi]
0x18045ac19  mov     rbx, [rax+38h]
0x18045ac1d  lea     rcx, [rbp+57h+var_98]
0x18045ac21  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ac26  mov     [rbp+57h+var_40], r13
0x18045ac2a  mov     r9d, 7; unsigned int
0x18045ac30  lea     r8d, [r9+1]; unsigned int
0x18045ac34  lea     rdx, ?c_allAppsCollectionId@CollectionConstants@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@3QBGB; "AllApps"
0x18045ac3b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18045ac3f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18045ac44  nop
0x18045ac45  lea     r9, [rbp+57h+var_98]
0x18045ac49  mov     r8, [rbp+57h+var_40]
0x18045ac4d  mov     edx, 1
0x18045ac52  mov     rcx, rdi
0x18045ac55  call    rbx
0x18045ac57  mov     ebx, eax
0x18045ac59  test    eax, eax
0x18045ac5b  jns     short loc_18045AC84
0x18045ac5d  mov     rcx, [rbp+5Fh]; this
0x18045ac61  mov     r9d, eax; char *
0x18045ac64  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045ac6b  mov     edx, 50h ; 'P'; void *
0x18045ac70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045ac75  nop
0x18045ac76  lea     rcx, [rbp+57h+var_98]
0x18045ac7a  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ac7f  jmp     loc_18045ABED
0x18045ac84  mov     [rbp+57h+var_A0], r13
0x18045ac88  mov     rdi, [rbp+57h+var_98]
0x18045ac8c  mov     rax, [rdi]
0x18045ac8f  mov     rbx, [rax+38h]
0x18045ac93  lea     rcx, [rbp+57h+var_A0]
0x18045ac97  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ac9c  lea     rdx, [rbp+57h+var_A0]
0x18045aca0  mov     rcx, rdi
0x18045aca3  call    rbx
0x18045aca5  mov     ebx, eax
0x18045aca7  test    eax, eax
0x18045aca9  jns     short loc_18045ACCF
0x18045acab  mov     edx, 53h ; 'S'; void *
0x18045acb0  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045acb7  mov     r9d, eax; char *
0x18045acba  mov     rcx, [rbp+5Fh]; this
0x18045acbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045acc3  nop
0x18045acc4  lea     rcx, [rbp+57h+var_A0]
0x18045acc8  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045accd  jmp     short loc_18045AC76
0x18045accf  mov     [rbp+57h+var_68], r13d
0x18045acd3  mov     rcx, [rbp+57h+var_A0]
0x18045acd7  mov     rax, [rcx]
0x18045acda  lea     rdx, [rbp+57h+var_68]
0x18045acde  call    qword ptr [rax+38h]
0x18045ace1  mov     ebx, eax
0x18045ace3  test    eax, eax
0x18045ace5  jns     short loc_18045ACEE
0x18045ace7  mov     edx, 56h ; 'V'
0x18045acec  jmp     short loc_18045ACB0
0x18045acee  mov     esi, r13d
0x18045acf1  cmp     esi, [rbp+57h+var_68]
0x18045acf4  jnb     loc_18045B052
0x18045acfa  mov     [rbp+57h+var_90], r13
0x18045acfe  mov     rdi, [rbp+57h+var_A0]
0x18045ad02  mov     rax, [rdi]
0x18045ad05  mov     rbx, [rax+30h]
0x18045ad09  lea     rcx, [rbp+57h+var_90]
0x18045ad0d  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ad12  lea     r8, [rbp+57h+var_90]
0x18045ad16  mov     edx, esi
0x18045ad18  mov     rcx, rdi
0x18045ad1b  call    rbx
0x18045ad1d  mov     ebx, eax
0x18045ad1f  test    eax, eax
0x18045ad21  js      loc_18045B02B
0x18045ad27  mov     [rbp+57h+var_88], r13
0x18045ad2b  mov     rdi, [rbp+57h+var_90]
0x18045ad2f  mov     rax, [rdi]
0x18045ad32  mov     rbx, [rax+68h]
0x18045ad36  lea     rcx, [rbp+57h+var_88]
0x18045ad3a  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ad3f  lea     rdx, [rbp+57h+var_88]
0x18045ad43  mov     rcx, rdi
0x18045ad46  call    rbx
0x18045ad48  mov     ebx, eax
0x18045ad4a  test    eax, eax
0x18045ad4c  js      loc_18045B007
0x18045ad52  mov     rbx, [rbp+57h+var_88]
0x18045ad56  test    rbx, rbx
0x18045ad59  jz      loc_18045AE29
0x18045ad5f  mov     [rbp+57h+string], r13
0x18045ad63  mov     rax, [rbx]
0x18045ad66  mov     rdi, [rax+30h]
0x18045ad6a  xor     ecx, ecx; string
0x18045ad6c  call    cs:__imp_WindowsDeleteString
0x18045ad72  mov     [rbp+57h+string], r13
0x18045ad76  lea     rdx, [rbp+57h+string]
0x18045ad7a  mov     rcx, rbx
0x18045ad7d  call    rdi
0x18045ad7f  mov     ebx, eax
0x18045ad81  test    eax, eax
0x18045ad83  js      loc_18045AFDE
0x18045ad89  xor     edx, edx; length
0x18045ad8b  mov     rcx, [rbp+57h+string]; string
0x18045ad8f  call    cs:__imp_WindowsGetStringRawBuffer
0x18045ad95  mov     r8, r12
0x18045ad98  sub     r8, rax
0x18045ad9b  movzx   ecx, word ptr [rax]
0x18045ad9e  movzx   edx, word ptr [rax+r8]
0x18045ada3  sub     ecx, edx
0x18045ada5  jnz     short loc_18045ADAF
0x18045ada7  add     rax, 2
0x18045adab  test    edx, edx
0x18045adad  jnz     short loc_18045AD9B
0x18045adaf  test    ecx, ecx
0x18045adb1  jnz     short loc_18045AE1E
0x18045adb3  mov     [rbp+57h+var_78], r13
0x18045adb7  mov     rdi, [rbp+57h+var_90]
0x18045adbb  mov     rax, [rdi]
0x18045adbe  mov     rbx, [rax+30h]
0x18045adc2  lea     rcx, [rbp+57h+var_78]
0x18045adc6  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045adcb  lea     rdx, [rbp+57h+var_78]
0x18045adcf  mov     rcx, rdi
0x18045add2  call    rbx
0x18045add4  mov     ebx, eax
0x18045add6  test    eax, eax
0x18045add8  js      loc_18045AFBA
0x18045adde  mov     [rbp+57h+var_70], r13
0x18045ade2  mov     rbx, [rbp+57h+var_78]
0x18045ade6  mov     rax, [rbx]
0x18045ade9  mov     rdi, [rax]
0x18045adec  lea     rcx, [rbp+57h+var_70]
0x18045adf0  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045adf5  lea     r8, [rbp+57h+var_70]
0x18045adf9  lea     rdx, _GUID_a7668288_cc23_4b67_be8b_6c10455986b8
0x18045ae00  mov     rcx, rbx
0x18045ae03  call    rdi
0x18045ae05  nop
0x18045ae06  test    eax, eax
0x18045ae08  jns     short loc_18045AE43
0x18045ae0a  lea     rcx, [rbp+57h+var_70]
0x18045ae0e  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ae13  nop
0x18045ae14  lea     rcx, [rbp+57h+var_78]
0x18045ae18  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ae1d  nop
0x18045ae1e  mov     rcx, [rbp+57h+string]; string
0x18045ae22  call    cs:__imp_WindowsDeleteString
0x18045ae28  nop
0x18045ae29  lea     rcx, [rbp+57h+var_88]
0x18045ae2d  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ae32  nop
0x18045ae33  lea     rcx, [rbp+57h+var_90]
0x18045ae37  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18045ae3c  inc     esi
0x18045ae3e  jmp     loc_18045ACF1
0x18045ae43  mov     rdx, r14; struct _FILETIME *
0x18045ae46  mov     rcx, [rbp+57h+var_90]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *
0x18045ae4a  call    ?GetInstallTime@PenWorkspaceDiscoverBroker@@CAJPEAUIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@PEAU_FILETIME@@@Z; PenWorkspaceDiscoverBroker::GetInstallTime(WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,_FILETIME *)
0x18045ae4f  mov     ebx, eax
0x18045ae51  test    eax, eax
0x18045ae53  jns     short loc_18045AE7C
0x18045ae55  mov     rcx, [rbp+5Fh]; this
0x18045ae59  mov     r9d, eax; char *
0x18045ae5c  lea     r8, aPcshellTwinuiP_16; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18045ae63  mov     edx, 6Dh ; 'm'; void *
0x18045ae68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045ae6d  nop
0x18045ae6e  lea     rcx, [rbp+57h+var_70]
0x18045ae72  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
  ... truncated ...
```
