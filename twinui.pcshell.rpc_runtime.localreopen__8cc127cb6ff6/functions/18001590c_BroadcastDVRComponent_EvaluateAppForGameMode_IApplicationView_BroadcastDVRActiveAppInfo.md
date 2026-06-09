# BroadcastDVRComponent::EvaluateAppForGameMode(IApplicationView *,BroadcastDVRActiveAppInfo *)

- ea: `0x18001590c`
- end: `0x180015dd3`
- name: `?EvaluateAppForGameMode@BroadcastDVRComponent@@AEAAXPEAUIApplicationView@@PEAUBroadcastDVRActiveAppInfo@@@Z`
- size: `1223`
- prototype: `void(BroadcastDVRComponent *__hidden this, struct IApplicationView *, struct BroadcastDVRActiveAppInfo *)`
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001500c`
- `0x180162338`
- `0x1802ef394`

## callees

- `0x18001590c`
- `0x180015ddc`
- `0x180015fc8`
- `0x180016018`
- `0x180016058`
- `0x1800163ec`
- `0x180016504`
- `0x180016c28`
- `0x180016e14`
- `0x180016e68`
- `0x180017174`
- `0x1800172c8`
- `0x18001f6e0`
- `0x18002e580`
- `0x180031200`
- `0x180031c70`
- `0x180051b40`
- `0x180056880`
- `0x180140f90`
- `0x180154fc0`
- `0x1801766f0`
- `0x180199354`
- `0x18019f498`
- `0x180204440`
- `0x1802ef604`
- `0x180356360`
- `0x180397ecc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015c38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015c38`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015983`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015983`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015b92`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015b92`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180015c08`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180015c08`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180015c1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180015c1a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180015a62`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180015a62`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeInitializeResourceRequest` at `0x180015c6c`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeInitializeResourceRequest` at `0x180015c6c`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeRegisterProcess` at `0x180015cd4`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeRegisterProcess` at `0x180015cd4`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeGetLargestValidResourceRequest` at `0x180015c7a`
- `ext-ms-win-resourcemanager-gamemode-l1-2-0!RmGameModeGetLargestValidResourceRequest` at `0x180015c7a`

## string_xrefs

- `0x180015a14`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180015c98`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180015cf9`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180015d8f`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall BroadcastDVRComponent::EvaluateAppForGameMode(
        BroadcastDVRComponent *this,
        struct IApplicationView *a2,
        HWND *a3)
{
  LSTATUS ValueW; // eax
  bool v7; // sf
  BroadcastDVRComponent *v8; // rcx
  struct GameConfigInfo *v9; // r12
  HWND v10; // r15
  HWND v11; // rbx
  int IsExpandedResources; // eax
  BroadcastDVRComponent *v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r15
  __int64 v22; // r9
  __int128 i; // rdi
  const char *v24; // r9
  HANDLE v25; // rbx
  const WCHAR *FileNameW; // rax
  int LargestValidResourceRequest; // esi
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  int pdwType; // [rsp+20h] [rbp-2D8h]
  int pdwTypea; // [rsp+20h] [rbp-2D8h]
  bool v36; // [rsp+40h] [rbp-2B8h] BYREF
  DWORD v37; // [rsp+44h] [rbp-2B4h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-2B0h] BYREF
  unsigned int pvData; // [rsp+50h] [rbp-2A8h] BYREF
  HANDLE v40; // [rsp+58h] [rbp-2A0h] BYREF
  HANDLE hProcess; // [rsp+60h] [rbp-298h] BYREF
  _BYTE v42[24]; // [rsp+68h] [rbp-290h] BYREF
  _OWORD v43[2]; // [rsp+80h] [rbp-278h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-258h]
  WCHAR Filename[264]; // [rsp+B0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  pvData = 0;
  pcbData[0] = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\GameDVR",
             L"AllowAutoGameMode",
             0x10u,
             0,
             &pvData,
             pcbData);
  v7 = ValueW < 0;
  if ( ValueW > 0 )
    v7 = 1;
  if ( (v7 || pvData)
    && (SHRegGetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\GameBar", L"AutoGameModeEnabled", &pvData) < 0 || pvData) )
  {
    v37 = 0;
    v36 = 0;
    v9 = (struct GameConfigInfo *)(a3 + 2);
    v10 = *a3;
    v11 = a3[1];
    IsExpandedResources = BroadcastDVRComponent::IsExpandedResources(v8, a2, &v36);
    if ( IsExpandedResources != -2147023728 && IsExpandedResources != -2147024444 )
    {
      v13 = retaddr;
      if ( IsExpandedResources < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7DD,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
          (const char *)(unsigned int)IsExpandedResources,
          pdwTypea);
    }
    LOBYTE(v13) = v36;
    v14 = v36 ? 5 : 0;
    pcbData[0] = v14;
    if ( !v36 )
    {
      if ( !BroadcastDVRComponent::IsGameModeGame(v13, v9, (enum GameModeReason *)pcbData) )
        return;
      v14 = pcbData[0];
    }
    if ( v10 )
      v11 = v10;
    GetWindowThreadProcessId(v11, &v37);
    if ( v37 )
    {
      if ( v37 == *((_DWORD *)this + 114) )
      {
        try
        {
          std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(
            v42,
            v15,
            v37);
          BroadcastDVRComponent::GetNonServiceProcessListAndIds(this, v42);
          BroadcastDVRComponent::ApplyGameRelatedForGameModeProcess(this, v37, v42);
          std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(
            v43,
            v16,
            v17);
          BroadcastDVRComponent::GetSortedUniqueProcessList(v18, v42, v43);
          BroadcastDVRComponent::RemoveKnownProcessesFromProcessList(v19, (char *)this + 352, v43);
          BroadcastDVRComponent::TelemetryLogProcessesLaunchedAfterGame(v20, v43);
          v21 = *(_QWORD *)&v43[0];
          for ( i = v43[0]; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 8 )
            std::vector<Windows::Internal::String>::push_back((char *)this + 352, i);
          if ( v21 != *((_QWORD *)&i + 1) )
          {
            *(_QWORD *)&i = std::_Move_unchecked<Windows::Internal::String *,Windows::Internal::String *>(
                              *((_QWORD *)&i + 1),
                              *((_QWORD *)&i + 1),
                              v21);
            std::_Destroy_range<std::allocator<Windows::Internal::String>>(i, *((_QWORD *)&i + 1));
            *((_QWORD *)&v43[0] + 1) = i;
          }
          LOBYTE(v22) = 0;
          std::_Sort_unchecked<Windows::Internal::String *,std::less<void>>(
            *((_QWORD *)this + 44),
            *((_QWORD *)this + 45),
            (__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 3,
            v22);
          std::vector<Windows::Internal::String>::_Tidy(v43);
          std::vector<std::pair<unsigned long,Windows::Internal::String>>::_Tidy(v42);
        }
        catch ( std::bad_alloc )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x804,
            (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
            (const char *)0x8007000ELL,
            pdwType);
        }
      }
      else
      {
        hProcess = 0;
        v40 = OpenProcess(0x1000u, 0, v37);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          &hProcess,
          &v40);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        v25 = hProcess;
        if ( hProcess )
        {
          v40 = 0;
          *(_QWORD *)pcbData = a2;
          Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(pcbData);
          if ( !a2
            || (int)Microsoft::WRL::ComPtr<IApplicationView>::As<IWinRTApplicationView>(pcbData, &v40) < 0
            || !K32GetModuleFileNameExW(v25, 0, Filename, 0x104u)
            || (FileNameW = PathFindFileNameW(Filename),
                CompareStringOrdinal(FileNameW, -1, L"applicationframehost.exe", -1, 1) != 2) )
          {
            memset(v43, 0, sizeof(v43));
            v44 = 0;
            RmGameModeInitializeResourceRequest(v43);
            LargestValidResourceRequest = RmGameModeGetLargestValidResourceRequest(v43);
            if ( LargestValidResourceRequest >= 0 )
            {
              BroadcastDVRComponent::GetGameModeRequest(this, v14, v9, v43);
              v28 = RmGameModeRegisterProcess(v25, v43, 0);
              if ( v28 >= 0 )
              {
                *((_DWORD *)this + 114) = v37;
                std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(
                  v42,
                  v29,
                  v30);
                BroadcastDVRComponent::GetNonServiceProcessListAndIds(this, v42);
                BroadcastDVRComponent::ApplyGameRelatedForGameModeProcess(this, v37, v42);
                std::vector<Windows::Internal::String>::clear((char *)this + 352);
                BroadcastDVRComponent::GetSortedUniqueProcessList(v32, v42, (char *)this + 352);
                BroadcastDVRComponent::TelemetryLogProcessesLaunchedWithGame(v33, (char *)this + 352);
                std::vector<std::pair<unsigned long,Windows::Internal::String>>::_Tidy(v42);
              }
              else if ( v28 != -1073740008 )
              {
                v31 = v28 | 0x10000000;
                if ( v31 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x833,
                    (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
                    (const char *)(unsigned int)v31,
                    pdwTypea);
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x825,
                (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
                (const char *)(LargestValidResourceRequest | 0x10000000u),
                pdwTypea);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pcbData);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        }
        else
        {
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x845,
            (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
            v24);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      }
    }
  }
}

```

## disassembly

```asm
0x18001590c  mov     [rsp+arg_18], rbx
0x180015911  push    rsi
0x180015912  push    rdi
0x180015913  push    r12
0x180015915  push    r14
0x180015917  push    r15
0x180015919  sub     rsp, 2D0h
0x180015920  mov     rax, cs:__security_cookie
0x180015927  xor     rax, rsp
0x18001592a  mov     [rsp+2F8h+var_38], rax
0x180015932  mov     rbx, r8
0x180015935  mov     rsi, rdx
0x180015938  mov     r14, rcx
0x18001593b  mov     [rsp+2F8h+var_2A8], 0
0x180015943  mov     [rsp+2F8h+var_2B0], 4
0x18001594b  lea     rax, [rsp+2F8h+var_2B0]
0x180015950  mov     [rsp+2F8h+pcbData], rax; pcbData
0x180015955  lea     rax, [rsp+2F8h+var_2A8]
0x18001595a  mov     [rsp+2F8h+pvData], rax; pvData
0x18001595f  mov     [rsp+2F8h+pdwType], 0; int
0x180015968  mov     r9d, 10h; dwFlags
0x18001596e  lea     r8, aAllowautogamem; "AllowAutoGameMode"
0x180015975  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18001597c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015983  call    cs:__imp_RegGetValueW
0x180015989  test    eax, eax
0x18001598b  jle     short loc_180015997
0x18001598d  movzx   eax, ax
0x180015990  or      eax, 80070000h
0x180015995  test    eax, eax
0x180015997  js      short loc_1800159A4
0x180015999  cmp     [rsp+2F8h+var_2A8], 0
0x18001599e  jz      loc_180015DAB
0x1800159a4  lea     r9, [rsp+2F8h+var_2A8]; unsigned int *
0x1800159a9  lea     r8, aAutogamemodeen; "AutoGameModeEnabled"
0x1800159b0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\GameBar"
0x1800159b7  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800159be  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800159c3  test    eax, eax
0x1800159c5  js      short loc_1800159D2
0x1800159c7  cmp     [rsp+2F8h+var_2A8], 0
0x1800159cc  jz      loc_180015DAB
0x1800159d2  mov     dword ptr [rsp+2F8h+var_2B8+4], 0
0x1800159da  mov     byte ptr [rsp+2F8h+var_2B8], 0
0x1800159df  lea     r12, [rbx+10h]
0x1800159e3  mov     r15, [rbx]
0x1800159e6  mov     rbx, [rbx+8]
0x1800159ea  lea     r8, [rsp+2F8h+var_2B8]; bool *
0x1800159ef  mov     rdx, rsi; struct IApplicationView *
0x1800159f2  call    ?IsExpandedResources@BroadcastDVRComponent@@AEAAJPEAUIApplicationView@@PEA_N@Z; BroadcastDVRComponent::IsExpandedResources(IApplicationView *,bool *)
0x1800159f7  cmp     eax, 80070490h
0x1800159fc  jz      short loc_180015A25
0x1800159fe  cmp     eax, 800701C4h
0x180015a03  jz      short loc_180015A25
0x180015a05  mov     rcx, [rsp+2F8h]; this
0x180015a0d  test    eax, eax
0x180015a0f  jns     short loc_180015A25
0x180015a11  mov     r9d, eax; char *
0x180015a14  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180015a1b  mov     edx, 7DDh; void *
0x180015a20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015a25  mov     cl, byte ptr [rsp+2F8h+var_2B8]; this
0x180015a29  mov     al, cl
0x180015a2b  neg     al
0x180015a2d  sbb     edi, edi
0x180015a2f  and     edi, 5
0x180015a32  mov     [rsp+2F8h+var_2B0], edi
0x180015a36  test    cl, cl
0x180015a38  jnz     short loc_180015A53
0x180015a3a  lea     r8, [rsp+2F8h+var_2B0]; enum GameModeReason *
0x180015a3f  mov     rdx, r12; struct GameConfigInfo *
0x180015a42  call    ?IsGameModeGame@BroadcastDVRComponent@@AEAA_NPEAUGameConfigInfo@@PEAW4GameModeReason@@@Z; BroadcastDVRComponent::IsGameModeGame(GameConfigInfo *,GameModeReason *)
0x180015a47  test    al, al
0x180015a49  jz      loc_180015DAB
0x180015a4f  mov     edi, [rsp+2F8h+var_2B0]
0x180015a53  test    r15, r15
0x180015a56  cmovnz  rbx, r15
0x180015a5a  lea     rdx, [rsp+2F8h+var_2B8+4]; lpdwProcessId
0x180015a5f  mov     rcx, rbx; hWnd
0x180015a62  call    cs:__imp_GetWindowThreadProcessId
0x180015a68  mov     r8d, dword ptr [rsp+2F8h+var_2B8+4]; dwProcessId
0x180015a6d  test    r8d, r8d
0x180015a70  jz      loc_180015DAB
0x180015a76  cmp     r8d, [r14+1C8h]
0x180015a7d  jnz     loc_180015B82
0x180015a83  lea     rcx, [rsp+2F8h+var_290]
0x180015a88  call    ??0?$vector@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@V?$allocator@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(void)
0x180015a8d  nop
0x180015a8e  lea     rdx, [rsp+2F8h+var_290]
0x180015a93  mov     rcx, r14
0x180015a96  call    ?GetNonServiceProcessListAndIds@BroadcastDVRComponent@@AEAAXAEAV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@@Z; BroadcastDVRComponent::GetNonServiceProcessListAndIds(std::vector<std::pair<ulong,Windows::Internal::String>> &)
0x180015a9b  lea     r8, [rsp+2F8h+var_290]
0x180015aa0  mov     edx, dword ptr [rsp+2F8h+var_2B8+4]
0x180015aa4  mov     rcx, r14
0x180015aa7  call    ?ApplyGameRelatedForGameModeProcess@BroadcastDVRComponent@@AEAAXKAEBV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@@Z; BroadcastDVRComponent::ApplyGameRelatedForGameModeProcess(ulong,std::vector<std::pair<ulong,Windows::Internal::String>> const &)
0x180015aac  lea     rcx, [rsp+2F8h+var_278]
0x180015ab4  call    ??0?$vector@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@V?$allocator@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(void)
0x180015ab9  nop
0x180015aba  lea     r8, [rsp+2F8h+var_278]
0x180015ac2  lea     rdx, [rsp+2F8h+var_290]
0x180015ac7  call    ?GetSortedUniqueProcessList@BroadcastDVRComponent@@AEAAXAEBV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@AEAV?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@3@@Z; BroadcastDVRComponent::GetSortedUniqueProcessList(std::vector<std::pair<ulong,Windows::Internal::String>> const &,std::vector<Windows::Internal::String> &)
0x180015acc  lea     rbx, [r14+160h]
0x180015ad3  lea     r8, [rsp+2F8h+var_278]
0x180015adb  mov     rdx, rbx
0x180015ade  call    ?RemoveKnownProcessesFromProcessList@BroadcastDVRComponent@@AEAAXAEBV?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@AEAV23@@Z; BroadcastDVRComponent::RemoveKnownProcessesFromProcessList(std::vector<Windows::Internal::String> const &,std::vector<Windows::Internal::String> &)
0x180015ae3  lea     rdx, [rsp+2F8h+var_278]
0x180015aeb  call    ?TelemetryLogProcessesLaunchedAfterGame@BroadcastDVRComponent@@AEAAXAEBV?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@@Z; BroadcastDVRComponent::TelemetryLogProcessesLaunchedAfterGame(std::vector<Windows::Internal::String> const &)
0x180015af0  mov     rsi, qword ptr [rsp+2F8h+var_278+8]
0x180015af8  mov     r15, qword ptr [rsp+2F8h+var_278]
0x180015b00  mov     rdi, r15
0x180015b03  cmp     rdi, rsi
0x180015b06  jz      short loc_180015B19
0x180015b08  mov     rdx, rdi
0x180015b0b  mov     rcx, rbx
0x180015b0e  call    ?push_back@?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@QEAAX$$QEAVString@Internal@Windows@@@Z; std::vector<Windows::Internal::String>::push_back(Windows::Internal::String &&)
0x180015b13  add     rdi, 8
0x180015b17  jmp     short loc_180015B03
0x180015b19  cmp     r15, rsi
0x180015b1c  jz      short loc_180015B42
0x180015b1e  mov     r8, r15
0x180015b21  mov     rdx, rsi
0x180015b24  mov     rcx, rsi
0x180015b27  call    ??$_Move_unchecked@PEAVString@Internal@Windows@@PEAV123@@std@@YAPEAVString@Internal@Windows@@PEAV123@00@Z; std::_Move_unchecked<Windows::Internal::String *,Windows::Internal::String *>(Windows::Internal::String *,Windows::Internal::String *,Windows::Internal::String *)
0x180015b2c  mov     rdi, rax
0x180015b2f  mov     rdx, rsi
0x180015b32  mov     rcx, rax
0x180015b35  call    ??$_Destroy_range@V?$allocator@VString@Internal@Windows@@@std@@@std@@YAXPEAVString@Internal@Windows@@QEAV123@AEAV?$allocator@VString@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::String>>(Windows::Internal::String *,Windows::Internal::String * const,std::allocator<Windows::Internal::String> &)
0x180015b3a  mov     qword ptr [rsp+2F8h+var_278+8], rdi
0x180015b42  mov     rdx, [r14+168h]
0x180015b49  xor     r9b, r9b
0x180015b4c  mov     r8, rdx
0x180015b4f  sub     r8, [rbx]
0x180015b52  sar     r8, 3
0x180015b56  mov     rcx, [rbx]
0x180015b59  call    ??$_Sort_unchecked@PEAVString@Internal@Windows@@U?$less@X@std@@@std@@YAXPEAVString@Internal@Windows@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<Windows::Internal::String *,std::less<void>>(Windows::Internal::String *,Windows::Internal::String *,__int64,std::less<void>)
0x180015b5e  nop
0x180015b5f  lea     rcx, [rsp+2F8h+var_278]
0x180015b67  call    ?_Tidy@?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Internal::String>::_Tidy(void)
0x180015b6c  nop
0x180015b6d  lea     rcx, [rsp+2F8h+var_290]
0x180015b72  call    ?_Tidy@?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<ulong,Windows::Internal::String>>::_Tidy(void)
0x180015b77  nop
0x180015b78  jmp     loc_180015DAB
0x180015b7d  jmp     loc_180015DAB
0x180015b82  mov     [rsp+2F8h+hProcess], 0
0x180015b8b  xor     edx, edx; bInheritHandle
0x180015b8d  mov     ecx, 1000h; dwDesiredAccess
0x180015b92  call    cs:__imp_OpenProcess
0x180015b98  mov     [rsp+2F8h+var_2A0], rax
0x180015b9d  lea     rdx, [rsp+2F8h+var_2A0]
0x180015ba2  lea     rcx, [rsp+2F8h+hProcess]
0x180015ba7  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180015bac  lea     rcx, [rsp+2F8h+var_2A0]
0x180015bb1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015bb6  mov     rbx, [rsp+2F8h+hProcess]
0x180015bbb  test    rbx, rbx
0x180015bbe  jz      loc_180015D87
0x180015bc4  mov     [rsp+2F8h+var_2A0], 0
0x180015bcd  mov     qword ptr [rsp+2F8h+var_2B0], rsi
0x180015bd2  lea     rcx, [rsp+2F8h+var_2B0]
0x180015bd7  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x180015bdc  nop
0x180015bdd  test    rsi, rsi
0x180015be0  jz      short loc_180015C47
0x180015be2  lea     rdx, [rsp+2F8h+var_2A0]
0x180015be7  lea     rcx, [rsp+2F8h+var_2B0]
0x180015bec  call    ??$As@UIWinRTApplicationView@@@?$ComPtr@UIApplicationView@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWinRTApplicationView@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IApplicationView>::As<IWinRTApplicationView>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWinRTApplicationView>>)
0x180015bf1  test    eax, eax
0x180015bf3  js      short loc_180015C47
0x180015bf5  mov     r9d, 104h; nSize
0x180015bfb  lea     r8, [rsp+2F8h+Filename]; lpFilename
0x180015c03  xor     edx, edx; hModule
0x180015c05  mov     rcx, rbx; hProcess
0x180015c08  call    cs:__imp_K32GetModuleFileNameExW
0x180015c0e  test    eax, eax
0x180015c10  jz      short loc_180015C47
0x180015c12  lea     rcx, [rsp+2F8h+Filename]; pszPath
0x180015c1a  call    cs:__imp_PathFindFileNameW
0x180015c20  mov     dword ptr [rsp+2F8h+pdwType], 1; int
0x180015c28  or      edx, 0FFFFFFFFh; cchCount1
0x180015c2b  mov     r9d, edx; cchCount2
0x180015c2e  lea     r8, String2; "applicationframehost.exe"
0x180015c35  mov     rcx, rax; lpString1
0x180015c38  call    cs:__imp_CompareStringOrdinal
0x180015c3e  cmp     eax, 2
0x180015c41  jz      loc_180015D70
0x180015c47  xorps   xmm0, xmm0
0x180015c4a  xor     eax, eax
0x180015c4c  movups  [rsp+2F8h+var_278], xmm0
0x180015c54  movups  [rsp+2F8h+var_268], xmm0
0x180015c5c  mov     [rsp+2F8h+var_258], rax
0x180015c64  lea     rcx, [rsp+2F8h+var_278]
0x180015c6c  call    cs:__imp_RmGameModeInitializeResourceRequest
0x180015c72  lea     rcx, [rsp+2F8h+var_278]
0x180015c7a  call    cs:__imp_RmGameModeGetLargestValidResourceRequest
0x180015c80  mov     esi, eax
0x180015c82  mov     r9d, eax
0x180015c85  mov     r15d, 10000000h
0x180015c8b  or      r9d, r15d; char *
0x180015c8e  mov     rcx, [rsp+2F8h]; this
0x180015c96  jge     short loc_180015CA9
0x180015c98  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180015c9f  mov     edx, 825h; void *
0x180015ca4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015ca9  test    esi, esi
0x180015cab  js      loc_180015D70
0x180015cb1  lea     r9, [rsp+2F8h+var_278]
0x180015cb9  mov     r8, r12
0x180015cbc  mov     edx, edi
0x180015cbe  mov     rcx, r14
0x180015cc1  call    ?GetGameModeRequest@BroadcastDVRComponent@@AEAAXW4GameModeReason@@PEAUGameConfigInfo@@PEAU_RM_GAME_MODE_RESOURCE_REQUEST@@@Z; BroadcastDVRComponent::GetGameModeRequest(GameModeReason,GameConfigInfo *,_RM_GAME_MODE_RESOURCE_REQUEST *)
0x180015cc6  xor     r8d, r8d
0x180015cc9  lea     rdx, [rsp+2F8h+var_278]
0x180015cd1  mov     rcx, rbx
0x180015cd4  call    cs:__imp_RmGameModeRegisterProcess
0x180015cda  test    eax, eax
0x180015cdc  jns     short loc_180015D0C
0x180015cde  cmp     eax, 0C0000718h
0x180015ce3  jz      loc_180015D70
0x180015ce9  or      eax, r15d
0x180015cec  mov     rcx, [rsp+2F8h]; this
0x180015cf4  jge     short loc_180015D70
0x180015cf6  mov     r9d, eax; char *
0x180015cf9  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180015d00  mov     edx, 833h; void *
0x180015d05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015d0a  jmp     short loc_180015D70
0x180015d0c  mov     eax, dword ptr [rsp+2F8h+var_2B8+4]
0x180015d10  mov     [r14+1C8h], eax
0x180015d17  lea     rcx, [rsp+2F8h+var_290]
0x180015d1c  call    ??0?$vector@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@V?$allocator@U?$event_revoker@UITransitionScreen@TransitionScreen@CloudDesktop@Shell@Internal@Windows@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(void)
0x180015d21  nop
0x180015d22  lea     rdx, [rsp+2F8h+var_290]
0x180015d27  mov     rcx, r14
0x180015d2a  call    ?GetNonServiceProcessListAndIds@BroadcastDVRComponent@@AEAAXAEAV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@@Z; BroadcastDVRComponent::GetNonServiceProcessListAndIds(std::vector<std::pair<ulong,Windows::Internal::String>> &)
0x180015d2f  lea     r8, [rsp+2F8h+var_290]
0x180015d34  mov     edx, dword ptr [rsp+2F8h+var_2B8+4]
0x180015d38  mov     rcx, r14
0x180015d3b  call    ?ApplyGameRelatedForGameModeProcess@BroadcastDVRComponent@@AEAAXKAEBV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@@Z; BroadcastDVRComponent::ApplyGameRelatedForGameModeProcess(ulong,std::vector<std::pair<ulong,Windows::Internal::String>> const &)
0x180015d40  lea     rbx, [r14+160h]
0x180015d47  mov     rcx, rbx
0x180015d4a  call    ?clear@?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@QEAAXXZ; std::vector<Windows::Internal::String>::clear(void)
0x180015d4f  mov     r8, rbx
0x180015d52  lea     rdx, [rsp+2F8h+var_290]
0x180015d57  call    ?GetSortedUniqueProcessList@BroadcastDVRComponent@@AEAAXAEBV?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@AEAV?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@3@@Z; BroadcastDVRComponent::GetSortedUniqueProcessList(std::vector<std::pair<ulong,Windows::Internal::String>> const &,std::vector<Windows::Internal::String> &)
0x180015d5c  mov     rdx, rbx
0x180015d5f  call    ?TelemetryLogProcessesLaunchedWithGame@BroadcastDVRComponent@@AEAAXAEBV?$vector@VString@Internal@Windows@@V?$allocator@VString@Internal@Windows@@@std@@@std@@@Z; BroadcastDVRComponent::TelemetryLogProcessesLaunchedWithGame(std::vector<Windows::Internal::String> const &)
0x180015d64  nop
0x180015d65  lea     rcx, [rsp+2F8h+var_290]
0x180015d6a  call    ?_Tidy@?$vector@U?$pair@KVString@Internal@Windows@@@std@@V?$allocator@U?$pair@KVString@Internal@Windows@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<ulong,Windows::Internal::String>>::_Tidy(void)
0x180015d6f  nop
0x180015d70  lea     rcx, [rsp+2F8h+var_2B0]
0x180015d75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015d7a  nop
0x180015d7b  lea     rcx, [rsp+2F8h+var_2A0]
0x180015d80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015d85  jmp     short loc_180015DA1
0x180015d87  mov     rcx, [rsp+2F8h]; this
0x180015d8f  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180015d96  mov     edx, 845h; void *
0x180015d9b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180015da0  nop
0x180015da1  lea     rcx, [rsp+2F8h+hProcess]
0x180015da6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015dab  mov     rcx, [rsp+2F8h+var_38]
0x180015db3  xor     rcx, rsp; StackCookie
0x180015db6  call    __security_check_cookie
0x180015dbb  mov     rbx, [rsp+2F8h+arg_18]
0x180015dc3  add     rsp, 2D0h
0x180015dca  pop     r15
0x180015dcc  pop     r14
0x180015dce  pop     r12
0x180015dd0  pop     rdi
0x180015dd1  pop     rsi
0x180015dd2  retn
```
