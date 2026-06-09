# GamingAudio::SessionInfoItem::Init(GamingAudio::AppList *,Microsoft::WRL::ComPtr<IAudioSessionControl2> const &)

- ea: `0x1803e4fa8`
- end: `0x1803e5635`
- name: `?Init@SessionInfoItem@GamingAudio@@QEAAJPEAVAppList@2@AEBV?$ComPtr@UIAudioSessionControl2@@@WRL@Microsoft@@@Z`
- size: `1677`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1803e4bcc`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x18004baf0`
- `0x180051b40`
- `0x18007b3e0`
- `0x1800f1d34`
- `0x1800f1d74`
- `0x18015d020`
- `0x1801b6bc8`
- `0x180356360`
- `0x1803e3648`
- `0x1803e3724`
- `0x1803e375c`
- `0x1803e4fa8`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803e5399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803e5399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803e5113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803e546e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803e5113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803e546e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803e5271`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803e5271`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1803e53f3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1803e53f3`
- `USER32!IsImmersiveProcess` at `0x1803e528f`
- `USER32!IsImmersiveProcess` at `0x1803e528f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1803e5434`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1803e5434`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x1803e54a4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x1803e54a4`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1803e52b7`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1803e52b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GamingAudio::SessionInfoItem::Init(__int64 a1, __int64 a2, LPARAM a3)
{
  __int64 (__fastcall ****v3)(__int64, GUID *, __int64 *); // r12
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  DWORD *v9; // r13
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 (__fastcall ***v13)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v14)(__int64, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  BOOL v18; // eax
  _QWORD *v19; // rsi
  __int64 (__fastcall ***v20)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v21)(__int64, GUID *, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  char *v24; // rdi
  BOOL v25; // eax
  __int64 v26; // rsi
  int (__fastcall *v27)(__int64, _QWORD, _QWORD, int (__fastcall ****)(_QWORD, GUID *, int *)); // rbx
  __int64 v28; // rax
  int (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v30)(_QWORD, GUID *, int *); // rsi
  HSTRING v31; // r8
  HSTRING *v32; // r12
  __int64 v33; // rsi
  void (__fastcall *v34)(__int64, __int64); // rbx
  _WORD *v35; // rsi
  HSTRING v36; // r8
  Microsoft::WRL::Wrappers::Details **v37; // rbx
  HSTRING v38; // r8
  int v39; // eax
  HSTRING v40; // r8
  unsigned __int64 v41; // rcx
  int v42; // eax
  __int64 (__fastcall ***v43)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v44)(__int64, GUID *, __int64 *); // rbx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rbx
  int v49; // [rsp+20h] [rbp-E0h]
  char *v50; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  LPARAM lParam[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v55[2]; // [rsp+70h] [rbp-90h] BYREF
  UINT32 packageFullNameLength; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  int (__fastcall ***v59)(_QWORD, GUID *, int *); // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwSize; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v62[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v3 = (__int64 (__fastcall ****)(__int64, GUID *, __int64 *))a3;
  lParam[0] = a3;
  v58 = a1 + 760;
  v6 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v58);
  v7 = Microsoft::WRL::AsWeak<Windows::Internal::GamingOverlay::IGamingOverlayExperienceManager>(a2, v6);
  if ( v7 >= 0 )
  {
    *(_QWORD *)(a1 + 768) = a2;
    v9 = (DWORD *)(a1 + 48);
    v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64))(**v3)[14])(
           *v3,
           a1 + 48);
    if ( v7 < 0 )
    {
      v8 = 287;
      goto LABEL_3;
    }
    v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64))(**v3)[3])(
            *v3,
            a1 + 84);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v10,
        v49);
    *(_DWORD *)(a1 + 72) = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(**v3)[15])(*v3) == 0;
    pv = 0;
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), LPVOID *))(**v3)[4])(*v3, &pv);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v11,
        v49);
    if ( pv )
    {
      v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(a1 + 56, &pv);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x129,
          (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
          (const char *)(unsigned int)v12,
          v49);
      CoTaskMemFree(pv);
    }
    v60 = 0;
    v13 = *v3;
    v14 = ***v3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v15 = v14((__int64)v13, &GUID_1167b081_0746_45f0_9ecd_97cc50de3a1f, &v60);
    v7 = v15;
    if ( v15 < 0 )
    {
      v16 = 303;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v15,
        v49);
LABEL_72:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      return (unsigned int)v7;
    }
    v57 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 152LL))(v60, &v57);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v17,
        v49);
    v18 = *(_DWORD *)(a1 + 84) != 2 && (v57 & 0x200000) == 0;
    *(_DWORD *)(a1 + 80) = v18;
    v19 = (_QWORD *)(a1 + 744);
    v20 = *v3;
    v21 = ***v3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 744);
    v15 = v21((__int64)v20, &GUID_87ce5498_68d6_44e5_9215_6da47ef883d8, (__int64 *)(a1 + 744));
    v7 = v15;
    if ( v15 < 0 )
    {
      v16 = 311;
      goto LABEL_24;
    }
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v19 + 32LL))(*v19, a1 + 64);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v22,
        v49);
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v19 + 48LL))(*v19, a1 + 68);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
        (const char *)(unsigned int)v23,
        v49);
    if ( *v9 )
    {
      v24 = (char *)OpenProcess(0x1000u, 0, *v9);
      v50 = v24;
      if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v25 = IsImmersiveProcess(v24);
        *(_DWORD *)(a1 + 76) = v25;
        if ( v25 )
        {
          packageFullNameLength = 65;
          if ( !GetPackageFullName(v24, &packageFullNameLength, (PWSTR)(a1 + 88)) )
          {
            v58 = 0;
            v59 = 0;
            *(_QWORD *)v55 = 0;
            v52 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Management.Deployment.PackageManager",
              0x2Du,
              0x2Cu);
            if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
                        v52,
                        &v58) >= 0 )
            {
              v26 = v58;
              v27 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, int (__fastcall ****)(_QWORD, GUID *, int *)))(*(_QWORD *)v58 + 168LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
              v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (PCWSTR)(a1 + 88));
              if ( v27(v26, 0, *(_QWORD *)(v28 + 24), &v59) >= 0 )
              {
                v29 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
                v30 = **v59;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
                if ( v30(v29, &GUID_a6612fb6_7688_4ace_95fb_359538e7aa01, v55) >= 0 )
                {
                  v32 = (HSTRING *)(a1 + 56);
                  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                        *(Microsoft::WRL::Wrappers::Details **)(a1 + 56),
                                        0,
                                        v31) )
                  {
                    v33 = *(_QWORD *)v55;
                    v34 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)v55 + 48LL);
                    WindowsDeleteString(*v32);
                    *v32 = 0;
                    v34(v33, a1 + 56);
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
          }
          v3 = (__int64 (__fastcall ****)(__int64, GUID *, __int64 *))lParam[0];
        }
        dwSize = 261;
        v35 = (_WORD *)(a1 + 218);
        if ( !QueryFullProcessImageNameW(v24, 0, (LPWSTR)(a1 + 218), &dwSize) )
        {
          *v35 = 0;
          *(_DWORD *)(a1 + 80) = 0;
        }
        v37 = (Microsoft::WRL::Wrappers::Details **)(a1 + 56);
        if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                              *(Microsoft::WRL::Wrappers::Details **)(a1 + 56),
                              0,
                              v36) )
        {
          *(_OWORD *)lParam = 0;
          LODWORD(lParam[0]) = *v9;
          EnumWindows(GamingAudio::EnumWindowsProc, (LPARAM)lParam);
          if ( lParam[1] )
          {
            v39 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(a1 + 56, &lParam[1]);
            if ( v39 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x178,
                (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
                (const char *)(unsigned int)v39,
                v49);
            CoTaskMemFree((LPVOID)lParam[1]);
          }
        }
        if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(*v37, 0, v38) )
        {
          v62[0] = 0;
          v55[0] = 261;
          if ( (unsigned int)SHGetFileDescriptionW(a1 + 218, 0, 0, v62, v55) )
          {
            packageFullNameLength = 0;
            v41 = -1;
            do
              ++v41;
            while ( v62[v41] );
            v42 = ULongLongToULong(v41, &packageFullNameLength);
            if ( v42 >= 0 )
              v42 = Microsoft::WRL::Wrappers::HString::Set(
                      (Microsoft::WRL::Wrappers::HString *)(a1 + 56),
                      v62,
                      packageFullNameLength);
            if ( v42 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x185,
                (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
                (const char *)(unsigned int)v42,
                v49);
          }
        }
        if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(*v37, 0, v40)
          && !*v35
          && !*(_DWORD *)(a1 + 72) )
        {
          *(_DWORD *)(a1 + 80) = 0;
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
    }
    if ( *(_DWORD *)(a1 + 80) )
    {
      *(_QWORD *)v55 = 0;
      v43 = *v3;
      v44 = ***v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
      v45 = v44((__int64)v43, &GUID_f4b1a599_7266_4319_a8ca_e70acb11e8cd, (__int64 *)v55);
      v7 = v45;
      if ( v45 < 0 )
      {
        v46 = 407;
LABEL_63:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
          (const char *)(unsigned int)v45,
          v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
        goto LABEL_72;
      }
      v47 = *(_QWORD *)v55;
      if ( *(_QWORD *)(a1 + 752) != *(_QWORD *)v55 )
      {
        if ( *(_QWORD *)v55 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 8LL))(*(_QWORD *)v55);
        v50 = *(char **)(a1 + 752);
        *(_QWORD *)(a1 + 752) = v47;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      }
      v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 752) + 80LL))(*(_QWORD *)(a1 + 752), a1);
      v7 = v45;
      if ( v45 < 0 )
      {
        v46 = 412;
        goto LABEL_63;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
    }
    v7 = 0;
    goto LABEL_72;
  }
  v8 = 283;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\Audio.cpp",
    (const char *)(unsigned int)v7,
    v49);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1803e4fa8  mov     [rsp-8+arg_18], rbx
0x1803e4fad  push    rbp
0x1803e4fae  push    rsi
0x1803e4faf  push    rdi
0x1803e4fb0  push    r12
0x1803e4fb2  push    r13
0x1803e4fb4  push    r14
0x1803e4fb6  push    r15
0x1803e4fb8  lea     rbp, [rsp-1C0h]
0x1803e4fc0  sub     rsp, 2C0h
0x1803e4fc7  mov     rax, cs:__security_cookie
0x1803e4fce  xor     rax, rsp
0x1803e4fd1  mov     [rbp+1F0h+var_40], rax
0x1803e4fd8  mov     r12, r8
0x1803e4fdb  mov     [rsp+2F0h+lParam], r8
0x1803e4fe0  mov     rdi, rdx
0x1803e4fe3  mov     r14, rcx
0x1803e4fe6  lea     rax, [rcx+2F8h]
0x1803e4fed  mov     [rbp+1F0h+var_270], rax
0x1803e4ff1  lea     rcx, [rbp+1F0h+var_270]
0x1803e4ff5  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1803e4ffa  mov     rdx, rax
0x1803e4ffd  mov     rcx, rdi
0x1803e5000  call    ??$AsWeak@UIGamingOverlayExperienceManager@GamingOverlay@Internal@Windows@@@WRL@Microsoft@@YAJPEAUIGamingOverlayExperienceManager@GamingOverlay@Internal@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Internal::GamingOverlay::IGamingOverlayExperienceManager>(Windows::Internal::GamingOverlay::IGamingOverlayExperienceManager *,Microsoft::WRL::WeakRef *)
0x1803e5005  mov     ebx, eax
0x1803e5007  test    eax, eax
0x1803e5009  jns     short loc_1803E502B
0x1803e500b  mov     edx, 11Bh; void *
0x1803e5010  lea     r8, aPcshellTwinuiG_7; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803e5017  mov     r9d, ebx; char *
0x1803e501a  mov     rcx, [rbp+1F8h]; this
0x1803e5021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803e5026  jmp     loc_1803E5609
0x1803e502b  mov     [r14+300h], rdi
0x1803e5032  mov     rcx, [r12]
0x1803e5036  lea     r13, [r14+30h]
0x1803e503a  mov     rax, [rcx]
0x1803e503d  mov     rdx, r13
0x1803e5040  mov     rax, [rax+70h]
0x1803e5044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5049  mov     ebx, eax
0x1803e504b  xor     edi, edi
0x1803e504d  test    eax, eax
0x1803e504f  jns     short loc_1803E5058
0x1803e5051  mov     edx, 11Fh
0x1803e5056  jmp     short loc_1803E5010
0x1803e5058  mov     rcx, [r12]
0x1803e505c  mov     rax, [rcx]
0x1803e505f  lea     rdx, [r14+54h]
0x1803e5063  mov     rax, [rax+18h]
0x1803e5067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e506c  mov     rcx, [rbp+1F8h]; this
0x1803e5073  lea     r15, aPcshellTwinuiG_7; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803e507a  test    eax, eax
0x1803e507c  jns     short loc_1803E508E
0x1803e507e  mov     r9d, eax; char *
0x1803e5081  mov     r8, r15; unsigned int
0x1803e5084  mov     edx, 120h; void *
0x1803e5089  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e508e  mov     rcx, [r12]
0x1803e5092  mov     rax, [rcx]
0x1803e5095  mov     rax, [rax+78h]
0x1803e5099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e509e  mov     ecx, edi
0x1803e50a0  test    eax, eax
0x1803e50a2  setz    cl
0x1803e50a5  mov     [r14+48h], ecx
0x1803e50a9  mov     [rsp+2F0h+pv], rdi
0x1803e50ae  mov     rcx, [r12]
0x1803e50b2  mov     rax, [rcx]
0x1803e50b5  lea     rdx, [rsp+2F0h+pv]
0x1803e50ba  mov     rax, [rax+20h]
0x1803e50be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e50c3  mov     rcx, [rbp+1F8h]; this
0x1803e50ca  test    eax, eax
0x1803e50cc  jns     short loc_1803E50DE
0x1803e50ce  mov     r9d, eax; char *
0x1803e50d1  mov     r8, r15; unsigned int
0x1803e50d4  mov     edx, 125h; void *
0x1803e50d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e50de  cmp     [rsp+2F0h+pv], rdi
0x1803e50e3  jz      short loc_1803E5119
0x1803e50e5  lea     rcx, [r14+38h]
0x1803e50e9  lea     rdx, [rsp+2F0h+pv]
0x1803e50ee  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1803e50f3  mov     rcx, [rbp+1F8h]; this
0x1803e50fa  test    eax, eax
0x1803e50fc  jns     short loc_1803E510E
0x1803e50fe  mov     r9d, eax; char *
0x1803e5101  mov     r8, r15; unsigned int
0x1803e5104  mov     edx, 129h; void *
0x1803e5109  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e510e  mov     rcx, [rsp+2F0h+pv]; pv
0x1803e5113  call    cs:__imp_CoTaskMemFree
0x1803e5119  mov     [rbp+1F0h+var_260], rdi
0x1803e511d  mov     rdi, [r12]
0x1803e5121  mov     rax, [rdi]
0x1803e5124  mov     rbx, [rax]
0x1803e5127  lea     rcx, [rbp+1F0h+var_260]
0x1803e512b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e5130  lea     r8, [rbp+1F0h+var_260]
0x1803e5134  lea     rdx, _GUID_1167b081_0746_45f0_9ecd_97cc50de3a1f
0x1803e513b  mov     rcx, rdi
0x1803e513e  mov     rax, rbx
0x1803e5141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5146  mov     ebx, eax
0x1803e5148  test    eax, eax
0x1803e514a  jns     short loc_1803E5156
0x1803e514c  mov     edx, 12Fh
0x1803e5151  jmp     loc_1803E51EA
0x1803e5156  mov     [rsp+2F0h+var_274], 0
0x1803e515e  mov     rcx, [rbp+1F0h+var_260]
0x1803e5162  mov     rax, [rcx]
0x1803e5165  lea     rdx, [rsp+2F0h+var_274]
0x1803e516a  mov     rax, [rax+98h]
0x1803e5171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5176  mov     rcx, [rbp+1F8h]; this
0x1803e517d  test    eax, eax
0x1803e517f  jns     short loc_1803E5191
0x1803e5181  mov     r9d, eax; char *
0x1803e5184  mov     r8, r15; unsigned int
0x1803e5187  mov     edx, 132h; void *
0x1803e518c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e5191  cmp     dword ptr [r14+54h], 2
0x1803e5196  jz      short loc_1803E51A9
0x1803e5198  test    [rsp+2F0h+var_274], 200000h
0x1803e51a0  jnz     short loc_1803E51A9
0x1803e51a2  mov     eax, 1
0x1803e51a7  jmp     short loc_1803E51AB
0x1803e51a9  xor     eax, eax
0x1803e51ab  mov     [r14+50h], eax
0x1803e51af  lea     rsi, [r14+2E8h]
0x1803e51b6  mov     rdi, [r12]
0x1803e51ba  mov     rax, [rdi]
0x1803e51bd  mov     rbx, [rax]
0x1803e51c0  mov     rcx, rsi
0x1803e51c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e51c8  mov     r8, rsi
0x1803e51cb  lea     rdx, _GUID_87ce5498_68d6_44e5_9215_6da47ef883d8
0x1803e51d2  mov     rcx, rdi
0x1803e51d5  mov     rax, rbx
0x1803e51d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e51dd  mov     ebx, eax
0x1803e51df  xor     edi, edi
0x1803e51e1  test    eax, eax
0x1803e51e3  jns     short loc_1803E5201
0x1803e51e5  mov     edx, 137h; void *
0x1803e51ea  mov     r8, r15; unsigned int
0x1803e51ed  mov     r9d, eax; char *
0x1803e51f0  mov     rcx, [rbp+1F8h]; this
0x1803e51f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803e51fc  jmp     loc_1803E5600
0x1803e5201  mov     rcx, [rsi]
0x1803e5204  mov     rax, [rcx]
0x1803e5207  lea     rdx, [r14+40h]
0x1803e520b  mov     rax, [rax+20h]
0x1803e520f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5214  mov     rcx, [rbp+1F8h]; this
0x1803e521b  test    eax, eax
0x1803e521d  jns     short loc_1803E522F
0x1803e521f  mov     r9d, eax; char *
0x1803e5222  mov     r8, r15; unsigned int
0x1803e5225  mov     edx, 138h; void *
0x1803e522a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e522f  mov     rcx, [rsi]
0x1803e5232  mov     rax, [rcx]
0x1803e5235  lea     rdx, [r14+44h]
0x1803e5239  mov     rax, [rax+30h]
0x1803e523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5242  mov     rcx, [rbp+1F8h]; this
0x1803e5249  test    eax, eax
0x1803e524b  jns     short loc_1803E525D
0x1803e524d  mov     r9d, eax; char *
0x1803e5250  mov     r8, r15; unsigned int
0x1803e5253  mov     edx, 139h; void *
0x1803e5258  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803e525d  mov     r8d, [r13+0]; dwProcessId
0x1803e5261  test    r8d, r8d
0x1803e5264  jz      loc_1803E5528
0x1803e526a  xor     edx, edx; bInheritHandle
0x1803e526c  mov     ecx, 1000h; dwDesiredAccess
0x1803e5271  call    cs:__imp_OpenProcess
0x1803e5277  mov     rdi, rax
0x1803e527a  mov     [rsp+2F0h+var_2C0], rax
0x1803e527f  dec     rax
0x1803e5282  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1803e5286  ja      loc_1803E551C
0x1803e528c  mov     rcx, rdi; hProcess
0x1803e528f  call    cs:__imp_IsImmersiveProcess
0x1803e5295  mov     [r14+4Ch], eax
0x1803e5299  xor     ebx, ebx
0x1803e529b  test    eax, eax
0x1803e529d  jz      loc_1803E53D9
0x1803e52a3  mov     [rsp+2F0h+packageFullNameLength], 41h ; 'A'
0x1803e52ab  lea     r8, [r14+58h]; packageFullName
0x1803e52af  lea     rdx, [rsp+2F0h+packageFullNameLength]; packageFullNameLength
0x1803e52b4  mov     rcx, rdi; hProcess
0x1803e52b7  call    cs:__imp_GetPackageFullName
0x1803e52bd  test    eax, eax
0x1803e52bf  jnz     loc_1803E53D4
0x1803e52c5  mov     [rbp+1F0h+var_270], rbx
0x1803e52c9  mov     [rbp+1F0h+var_268], rbx
0x1803e52cd  mov     qword ptr [rsp+2F0h+var_280], rbx
0x1803e52d2  mov     [rsp+2F0h+var_2A0], rbx
0x1803e52d7  lea     r9d, [rbx+2Ch]; unsigned int
0x1803e52db  lea     r8d, [rbx+2Dh]; unsigned int
0x1803e52df  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1803e52e6  lea     rcx, [rsp+2F0h+hstringHeader]; hstringHeader
0x1803e52eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803e52f0  lea     rdx, [rbp+1F0h+var_270]
0x1803e52f4  mov     rcx, [rsp+2F0h+var_2A0]
0x1803e52f9  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1803e52fe  test    eax, eax
0x1803e5300  js      loc_1803E53B6
0x1803e5306  mov     rsi, [rbp+1F0h+var_270]
0x1803e530a  mov     rax, [rsi]
0x1803e530d  mov     rbx, [rax+0A8h]
0x1803e5314  lea     rcx, [rbp+1F0h+var_268]
0x1803e5318  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e531d  lea     rdx, [r14+58h]; sourceString
0x1803e5321  lea     rcx, [rsp+2F0h+hstringHeader]; hstringHeader
0x1803e5326  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x1803e532b  nop
0x1803e532c  lea     r9, [rbp+1F0h+var_268]
0x1803e5330  mov     r8, [rax+18h]
0x1803e5334  xor     edx, edx
0x1803e5336  mov     rcx, rsi
0x1803e5339  mov     rax, rbx
0x1803e533c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5341  nop
0x1803e5342  test    eax, eax
0x1803e5344  js      short loc_1803E53B6
0x1803e5346  mov     rbx, [rbp+1F0h+var_268]
0x1803e534a  mov     rax, [rbx]
0x1803e534d  mov     rsi, [rax]
0x1803e5350  lea     rcx, [rsp+2F0h+var_280]
0x1803e5355  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e535a  lea     r8, [rsp+2F0h+var_280]
0x1803e535f  lea     rdx, _GUID_a6612fb6_7688_4ace_95fb_359538e7aa01
0x1803e5366  mov     rcx, rbx
0x1803e5369  mov     rax, rsi
0x1803e536c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5371  nop
0x1803e5372  test    eax, eax
0x1803e5374  js      short loc_1803E53B6
0x1803e5376  lea     r12, [r14+38h]
0x1803e537a  xor     edx, edx; HSTRING
0x1803e537c  mov     rcx, [r12]; this
0x1803e5380  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1803e5385  test    eax, eax
0x1803e5387  jnz     short loc_1803E53B6
0x1803e5389  mov     rsi, qword ptr [rsp+2F0h+var_280]
0x1803e538e  mov     rax, [rsi]
0x1803e5391  mov     rbx, [rax+30h]
0x1803e5395  mov     rcx, [r12]; string
0x1803e5399  call    cs:__imp_WindowsDeleteString
0x1803e539f  mov     qword ptr [r12], 0
0x1803e53a7  mov     rdx, r12
0x1803e53aa  mov     rcx, rsi
0x1803e53ad  mov     rax, rbx
0x1803e53b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e53b5  nop
0x1803e53b6  lea     rcx, [rsp+2F0h+var_280]
0x1803e53bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e53c0  nop
0x1803e53c1  lea     rcx, [rbp+1F0h+var_268]
0x1803e53c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e53ca  nop
0x1803e53cb  lea     rcx, [rbp+1F0h+var_270]
0x1803e53cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e53d4  mov     r12, [rsp+2F0h+lParam]
0x1803e53d9  mov     [rbp+1F0h+dwSize], 105h
0x1803e53e0  lea     rsi, [r14+0DAh]
0x1803e53e7  lea     r9, [rbp+1F0h+dwSize]; lpdwSize
0x1803e53eb  mov     r8, rsi; lpExeName
0x1803e53ee  xor     edx, edx; dwFlags
0x1803e53f0  mov     rcx, rdi; hProcess
0x1803e53f3  call    cs:__imp_QueryFullProcessImageNameW
0x1803e53f9  xor     edi, edi
0x1803e53fb  test    eax, eax
0x1803e53fd  jnz     short loc_1803E5406
0x1803e53ff  mov     [rsi], di
0x1803e5402  mov     [r14+50h], edi
0x1803e5406  lea     rbx, [r14+38h]
0x1803e540a  xor     edx, edx; HSTRING
0x1803e540c  mov     rcx, [rbx]; this
0x1803e540f  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1803e5414  test    eax, eax
0x1803e5416  jnz     short loc_1803E5474
0x1803e5418  xorps   xmm0, xmm0
0x1803e541b  movups  xmmword ptr [rsp+2F0h+lParam], xmm0
0x1803e5420  mov     eax, [r13+0]
0x1803e5424  mov     dword ptr [rsp+2F0h+lParam], eax
0x1803e5428  lea     rdx, [rsp+2F0h+lParam]; lParam
0x1803e542d  lea     rcx, ?EnumWindowsProc@GamingAudio@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x1803e5434  call    cs:__imp_EnumWindows
0x1803e543a  cmp     [rsp+2F0h+lParam+8], rdi
0x1803e543f  jz      short loc_1803E5474
0x1803e5441  lea     rdx, [rsp+2F0h+lParam+8]
0x1803e5446  mov     rcx, rbx
  ... truncated ...
```
