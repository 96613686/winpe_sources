# ProcessGroupPolicyWorker(void *)

- ea: `0x1800134b0`
- end: `0x180013b57`
- name: `?ProcessGroupPolicyWorker@@YAKPEAX@Z`
- size: `1703`
- prototype: `__int64 __fastcall(_QWORD *Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800044e0`
- `0x1800057a0`
- `0x180005cc0`
- `0x1800122d4`
- `0x1800134b0`
- `0x1800140c0`
- `0x180014190`
- `0x18001a7fc`
- `0x18001ac7c`
- `0x18001fc94`
- `0x1800204fc`
- `0x18002055c`
- `0x180020704`
- `0x1800209a0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001353e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001353e`
- `USERENV!ProcessGroupPolicyCompleted` at `0x180013b22`
- `USERENV!ProcessGroupPolicyCompleted` at `0x180013b22`

## string_xrefs

- `0x18001389c`: `DataDirectory`
- `0x18001391e`: `TextExtensions`
- `0x18001365f`: `PreventIndexingUncachedExchangeFolders`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProcessGroupPolicyWorker(_QWORD *Parameter)
{
  int IsRunning; // ebx
  LSTATUS v3; // eax
  struct IGatherManagerAdmin3 *v4; // rdx
  struct IUnknown *v5; // rdx
  HKEY v6; // rax
  HKEY v7; // rax
  HKEY v8; // rax
  HKEY v9; // rax
  HKEY v10; // rax
  HKEY v11; // rax
  HKEY v12; // rax
  HKEY v13; // rax
  HKEY v14; // rax
  HKEY v15; // rax
  CExcludedExtsPolicy *v16; // rax
  CExcludedExtsPolicy *v17; // rax
  HKEY v18; // rax
  HKEY v19; // rax
  HKEY v20; // rax
  int v21; // r14d
  int v22; // edi
  unsigned int i; // esi
  __int64 v24; // r15
  unsigned int j; // esi
  void (__fastcall ***v26)(_QWORD, __int64); // rcx
  __int64 v27; // rcx
  struct IGatherManagerAdmin3 *v28; // rdx
  struct IUnknown *v29; // rdx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v34[14]; // [rsp+80h] [rbp-80h]
  GUID extensionId; // [rsp+F0h] [rbp-10h] BYREF

  v32 = 0;
  IsRunning = SearchServiceIsRunning(&v32);
  if ( IsRunning >= 0 )
  {
    if ( v32 )
    {
      phkResult = 0;
      v3 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies",
             0,
             0,
             0,
             0x2000000u,
             0,
             &phkResult,
             0);
      IsRunning = v3;
      if ( v3 > 0 )
        IsRunning = (unsigned __int16)v3 | 0x80070000;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      memset(v33, 0, sizeof(v33));
      if ( IsRunning >= 0 )
      {
        IsRunning = CMSSAdmin::InitGatherAdmin((CMSSAdmin *)v33, v4);
        if ( IsRunning >= 0 )
        {
          IsRunning = CMSSAdmin::InitIndexerPlugin((struct IUnknown **)v33, v5);
          if ( IsRunning >= 0 )
          {
            v6 = (HKEY)operator new(0x50u);
            phkResult = v6;
            if ( v6 )
            {
              *((_QWORD *)v6 + 1) = L"AllowIndexingEncryptedStoresOrItems";
              *((_DWORD *)v6 + 4) = 0;
              *((_QWORD *)v6 + 3) = L"AllowIndexingEncryptedStoresOrItems";
              *((_QWORD *)v6 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v6 + 5) = 1;
              *((_DWORD *)v6 + 12) = 0;
              *((_QWORD *)v6 + 7) = L"AllowIndexingEncryptedStoresOrItems";
              *((_QWORD *)v6 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v6 + 9) = 1;
              *(_QWORD *)v6 = &CDisableRemovableDriveIndexingPolicy::`vftable';
            }
            else
            {
              v6 = 0;
            }
            v34[0] = v6;
            v7 = (HKEY)operator new(0x50u);
            phkResult = v7;
            if ( v7 )
            {
              *((_QWORD *)v7 + 1) = L"PreventIndexingOfflineFiles";
              *((_DWORD *)v7 + 4) = 0;
              *((_QWORD *)v7 + 3) = L"PreventIndexingOfflineFiles";
              *((_QWORD *)v7 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v7 + 5) = 1;
              *((_DWORD *)v7 + 12) = 0;
              *((_QWORD *)v7 + 7) = L"PreventIndexingOfflineFiles";
              *((_QWORD *)v7 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v7 + 9) = 1;
              *(_QWORD *)v7 = &COn1Off0Policy::`vftable';
            }
            else
            {
              v7 = 0;
            }
            v34[1] = v7;
            v8 = (HKEY)operator new(0x50u);
            phkResult = v8;
            if ( v8 )
            {
              *((_QWORD *)v8 + 1) = L"PreventIndexingUncachedExchangeFolders";
              *((_DWORD *)v8 + 4) = 0;
              *((_QWORD *)v8 + 3) = L"PreventIndexingUncachedExchangeFolders";
              *((_QWORD *)v8 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v8 + 5) = 1;
              *((_DWORD *)v8 + 12) = 0;
              *((_QWORD *)v8 + 7) = L"PreventIndexingUncachedExchangeFolders";
              *((_QWORD *)v8 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v8 + 9) = 1;
              *(_QWORD *)v8 = &COn1Off0Policy::`vftable';
            }
            else
            {
              v8 = 0;
            }
            v34[2] = v8;
            v9 = (HKEY)operator new(0x50u);
            phkResult = v9;
            if ( v9 )
            {
              *((_QWORD *)v9 + 1) = L"PreventIndexingOutlook";
              *((_DWORD *)v9 + 4) = 0;
              *((_QWORD *)v9 + 3) = L"PreventIndexingOutlook";
              *((_QWORD *)v9 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v9 + 5) = 1;
              *((_DWORD *)v9 + 12) = 0;
              *((_QWORD *)v9 + 7) = L"PreventIndexingOutlook";
              *((_QWORD *)v9 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v9 + 9) = 1;
              *(_QWORD *)v9 = &COn1Off0Policy::`vftable';
            }
            else
            {
              v9 = 0;
            }
            v34[3] = v9;
            v10 = (HKEY)operator new(0x50u);
            phkResult = v10;
            if ( v10 )
            {
              *((_QWORD *)v10 + 1) = L"PreventIndexingEmailAttachments";
              *((_DWORD *)v10 + 4) = 0;
              *((_QWORD *)v10 + 3) = L"PreventIndexingEmailAttachments";
              *((_QWORD *)v10 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v10 + 5) = 1;
              *((_DWORD *)v10 + 12) = 0;
              *((_QWORD *)v10 + 7) = L"PreventIndexingEmailAttachments";
              *((_QWORD *)v10 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v10 + 9) = 1;
              *(_QWORD *)v10 = &COn1Off0Policy::`vftable';
            }
            else
            {
              v10 = 0;
            }
            v34[4] = v10;
            v11 = (HKEY)operator new(0x50u);
            phkResult = v11;
            if ( v11 )
            {
              *((_QWORD *)v11 + 1) = L"PreventIndexingPublicFolders";
              *((_DWORD *)v11 + 4) = 0;
              *((_QWORD *)v11 + 3) = L"PreventIndexingPublicFolders";
              *((_QWORD *)v11 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v11 + 5) = 1;
              *((_DWORD *)v11 + 12) = 0;
              *((_QWORD *)v11 + 7) = L"PreventIndexingPublicFolders";
              *((_QWORD *)v11 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v11 + 9) = 1;
              *(_QWORD *)v11 = &COn1Off0Policy::`vftable';
            }
            else
            {
              v11 = 0;
            }
            v34[5] = v11;
            v12 = (HKEY)operator new(0x58u);
            phkResult = v12;
            if ( v12 )
            {
              *((_QWORD *)v12 + 1) = L"AllowUsingDiacritics";
              *((_DWORD *)v12 + 4) = 0;
              *((_QWORD *)v12 + 3) = L"AllowUsingDiacritics";
              *((_QWORD *)v12 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v12 + 5) = 1;
              *((_DWORD *)v12 + 12) = 0;
              *((_QWORD *)v12 + 7) = L"AllowUsingDiacritics";
              *((_QWORD *)v12 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v12 + 9) = 1;
              *(_QWORD *)v12 = &CDiacriticsPolicy::`vftable';
              *((_QWORD *)v12 + 10) = v33;
            }
            else
            {
              v12 = 0;
            }
            v34[6] = v12;
            v13 = (HKEY)operator new(0x50u);
            phkResult = v13;
            if ( v13 )
            {
              *((_QWORD *)v13 + 1) = L"AlwaysUseAutoLangDetection";
              *((_DWORD *)v13 + 4) = 0;
              *((_QWORD *)v13 + 3) = L"AlwaysUseAutoLangDetection";
              *((_QWORD *)v13 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v13 + 5) = 1;
              *((_DWORD *)v13 + 12) = 0;
              *((_QWORD *)v13 + 7) = L"AlwaysUseAutoLangDetection";
              *((_QWORD *)v13 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v13 + 9) = 1;
              *(_QWORD *)v13 = &CAlwaysUseAutoLangDetectionPolicy::`vftable';
            }
            else
            {
              v13 = 0;
            }
            v34[7] = v13;
            v14 = (HKEY)operator new(0x50u);
            phkResult = v14;
            if ( v14 )
            {
              *((_QWORD *)v14 + 1) = L"DisableRemovableDriveIndexing";
              *((_DWORD *)v14 + 4) = 0;
              *((_QWORD *)v14 + 3) = L"DisableRemovableDriveIndexing";
              *((_QWORD *)v14 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v14 + 5) = 1;
              *((_DWORD *)v14 + 12) = 0;
              *((_QWORD *)v14 + 7) = L"DisableRemovableDriveIndexing";
              *((_QWORD *)v14 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v14 + 9) = 1;
              *(_QWORD *)v14 = &CDisableRemovableDriveIndexingPolicy::`vftable';
            }
            else
            {
              v14 = 0;
            }
            v34[8] = v14;
            v15 = (HKEY)operator new(0x60u);
            phkResult = v15;
            if ( v15 )
            {
              *((_QWORD *)v15 + 1) = L"DataDirectory";
              *((_DWORD *)v15 + 4) = 0;
              *((_QWORD *)v15 + 3) = L"DataDirectory";
              *((_QWORD *)v15 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_DWORD *)v15 + 10) = 2;
              *((_QWORD *)v15 + 6) = 0;
              *((_DWORD *)v15 + 14) = 0;
              *((_QWORD *)v15 + 8) = L"DataDirectory";
              *((_QWORD *)v15 + 9) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_DWORD *)v15 + 20) = 2;
              *((_QWORD *)v15 + 11) = 0;
              *(_QWORD *)v15 = &CDataDirectoryPolicy::`vftable';
            }
            else
            {
              v15 = 0;
            }
            v34[9] = v15;
            v16 = (CExcludedExtsPolicy *)operator new(0x58u);
            phkResult = (HKEY)v16;
            if ( v16 )
              v17 = CExcludedExtsPolicy::CExcludedExtsPolicy(v16);
            else
              v17 = 0;
            v34[10] = v17;
            v18 = (HKEY)operator new(0x60u);
            phkResult = v18;
            if ( v18 )
            {
              *((_QWORD *)v18 + 1) = L"TextExtensions";
              *((_DWORD *)v18 + 4) = 0;
              *((_QWORD *)v18 + 3) = L"TextExtensions";
              *((_QWORD *)v18 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_DWORD *)v18 + 10) = 1;
              *((_QWORD *)v18 + 6) = 0;
              *((_DWORD *)v18 + 14) = 0;
              *((_QWORD *)v18 + 8) = L"TextExtensions";
              *((_QWORD *)v18 + 9) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_DWORD *)v18 + 20) = 1;
              *((_QWORD *)v18 + 11) = 0;
              *(_QWORD *)v18 = &CAsTextExtsPolicy::`vftable';
            }
            else
            {
              v18 = 0;
            }
            v34[11] = v18;
            v19 = (HKEY)operator new(0x50u);
            phkResult = v19;
            if ( v19 )
            {
              *((_QWORD *)v19 + 1) = L"PreventIndexingLowDiskSpaceMB";
              *((_DWORD *)v19 + 4) = 0;
              *((_QWORD *)v19 + 3) = L"PreventIndexingLowDiskSpaceMB";
              *((_QWORD *)v19 + 4) = L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
              *((_QWORD *)v19 + 5) = 1;
              *((_DWORD *)v19 + 12) = 0;
              *((_QWORD *)v19 + 7) = L"PreventIndexingLowDiskSpaceMB";
              *((_QWORD *)v19 + 8) = L"SOFTWARE\\Microsoft\\Windows Search\\CurrentPolicies";
              *((_QWORD *)v19 + 9) = 1;
              *(_QWORD *)v19 = &CFreeDiskSpaceThresholdPolicy::`vftable';
            }
            else
            {
              v19 = 0;
            }
            v34[12] = v19;
            v20 = (HKEY)operator new(0x18u);
            phkResult = v20;
            if ( v20 )
            {
              *((_QWORD *)v20 + 1) = &strIn;
              *(_QWORD *)v20 = &CCSMClusionPolicy::`vftable';
              *((_QWORD *)v20 + 2) = v33;
            }
            else
            {
              v20 = 0;
            }
            v34[13] = v20;
            v21 = 0;
            v22 = 0;
            for ( i = 0; i < 0xE; ++i )
            {
              v24 = v34[i];
              if ( v24 )
              {
                if ( (*(int (__fastcall **)(_QWORD))(*(_QWORD *)v24 + 8LL))(v34[i]) >= 0 )
                {
                  v32 = 0;
                  LODWORD(phkResult) = 0;
                  if ( (*(int (__fastcall **)(__int64, int *, HKEY *))(*(_QWORD *)v24 + 16LL))(v24, &v32, &phkResult) >= 0 )
                  {
                    if ( v21 || (v21 = 0, v32) )
                      v21 = 1;
                    if ( v22 || (v22 = 0, (_DWORD)phkResult) )
                      v22 = 1;
                  }
                }
              }
            }
            for ( j = 0; j < 0xE; ++j )
            {
              v26 = (void (__fastcall ***)(_QWORD, __int64))v34[j];
              if ( v26 )
                (**v26)(v26, 1);
            }
            if ( v21 || v22 )
            {
              CMSSAdmin::UnInit((CMSSAdmin *)v33);
              if ( !v22 || (IsRunning = CMSSAdmin::DropCatalog(v27, 4), IsRunning >= 0) )
              {
                IsRunning = SearchServiceRestart();
                if ( IsRunning >= 0 )
                {
                  IsRunning = CMSSAdmin::InitGatherAdmin((CMSSAdmin *)v33, v28);
                  if ( IsRunning >= 0 )
                  {
                    IsRunning = CMSSAdmin::InitIndexerPlugin((struct IUnknown **)v33, v29);
                    if ( IsRunning >= 0 )
                      IsRunning = CMSSAdmin::StartCrawlingAllLocalSystemStartAddresses((CMSSAdmin *)v33);
                  }
                }
              }
            }
          }
        }
      }
      CMSSAdmin::~CMSSAdmin((CMSSAdmin *)v33);
    }
    else
    {
      IsRunning = -2147467259;
    }
  }
  extensionId = (GUID)xmmword_180036F10;
  ProcessGroupPolicyCompleted(&extensionId, Parameter[5], (IsRunning >> 31) & 0x4E4);
  operator delete(Parameter, 0x40u);
  return 0;
}

```

## disassembly

```asm
0x1800134b0  push    rbp
0x1800134b2  push    rbx
0x1800134b3  push    rsi
0x1800134b4  push    rdi
0x1800134b5  push    r12
0x1800134b7  push    r13
0x1800134b9  push    r14
0x1800134bb  push    r15
0x1800134bd  lea     rbp, [rsp-18h]
0x1800134c2  sub     rsp, 118h
0x1800134c9  mov     rax, cs:__security_cookie
0x1800134d0  xor     rax, rsp
0x1800134d3  mov     [rbp+50h+var_50], rax
0x1800134d7  mov     r13, rcx
0x1800134da  xor     r12d, r12d
0x1800134dd  mov     [rsp+150h+var_F8], r12d
0x1800134e2  lea     rcx, [rsp+150h+var_F8]; int *
0x1800134e7  call    ?SearchServiceIsRunning@@YAJPEAH@Z; SearchServiceIsRunning(int *)
0x1800134ec  mov     ebx, eax
0x1800134ee  test    eax, eax
0x1800134f0  js      loc_180013B02
0x1800134f6  cmp     [rsp+150h+var_F8], r12d
0x1800134fb  jz      loc_180013AFD
0x180013501  mov     [rsp+150h+var_100], r12
0x180013506  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x18001350b  lea     rax, [rsp+150h+var_100]
0x180013510  mov     [rsp+150h+phkResult], rax; phkResult
0x180013515  mov     [rsp+150h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001351a  mov     [rsp+150h+samDesired], 2000000h; samDesired
0x180013522  mov     [rsp+150h+dwOptions], r12d; dwOptions
0x180013527  xor     r9d, r9d; lpClass
0x18001352a  xor     r8d, r8d; Reserved
0x18001352d  lea     r14, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows Search\\Cu"...
0x180013534  mov     rdx, r14; lpSubKey
0x180013537  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001353e  call    cs:__imp_RegCreateKeyExW
0x180013544  mov     ebx, eax
0x180013546  test    eax, eax
0x180013548  jle     short loc_180013553
0x18001354a  movzx   ebx, ax
0x18001354d  or      ebx, 80070000h
0x180013553  lea     rcx, [rsp+150h+var_100]
0x180013558  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001355d  xorps   xmm0, xmm0
0x180013560  movdqu  [rsp+150h+var_F0], xmm0
0x180013566  xorps   xmm1, xmm1
0x180013569  movdqu  [rsp+150h+var_E0], xmm1
0x18001356f  test    ebx, ebx
0x180013571  js      loc_180013AF1
0x180013577  lea     rcx, [rsp+150h+var_F0]; this
0x18001357c  call    ?InitGatherAdmin@CMSSAdmin@@QEAAJPEAUIGatherManagerAdmin3@@@Z; CMSSAdmin::InitGatherAdmin(IGatherManagerAdmin3 *)
0x180013581  mov     ebx, eax
0x180013583  test    eax, eax
0x180013585  js      loc_180013AF1
0x18001358b  lea     rcx, [rsp+150h+var_F0]; this
0x180013590  call    ?InitIndexerPlugin@CMSSAdmin@@QEAAJXZ; CMSSAdmin::InitIndexerPlugin(void)
0x180013595  mov     ebx, eax
0x180013597  test    eax, eax
0x180013599  js      loc_180013AF1
0x18001359f  mov     esi, 50h ; 'P'
0x1800135a4  mov     ecx, esi; unsigned __int64
0x1800135a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800135ab  mov     [rsp+150h+var_100], rax
0x1800135b0  lea     r15, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800135b7  lea     edi, [rsi-4Fh]
0x1800135ba  test    rax, rax
0x1800135bd  jz      short loc_1800135F6
0x1800135bf  lea     rcx, aAllowindexinge; "AllowIndexingEncryptedStoresOrItems"
0x1800135c6  mov     [rax+8], rcx
0x1800135ca  mov     [rax+10h], r12d
0x1800135ce  mov     [rax+18h], rcx
0x1800135d2  mov     [rax+20h], r15
0x1800135d6  mov     [rax+28h], rdi
0x1800135da  mov     [rax+30h], r12d
0x1800135de  mov     [rax+38h], rcx
0x1800135e2  mov     [rax+40h], r14
0x1800135e6  mov     [rax+48h], rdi
0x1800135ea  lea     rcx, ??_7CDisableRemovableDriveIndexingPolicy@@6B@; const CDisableRemovableDriveIndexingPolicy::`vftable'
0x1800135f1  mov     [rax], rcx
0x1800135f4  jmp     short loc_1800135F9
0x1800135f6  mov     rax, r12
0x1800135f9  mov     [rbp+50h+var_D0], rax
0x1800135fd  mov     rcx, rsi; unsigned __int64
0x180013600  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013605  mov     [rsp+150h+var_100], rax
0x18001360a  lea     rdx, ??_7COn1Off0Policy@@6B@; const COn1Off0Policy::`vftable'
0x180013611  test    rax, rax
0x180013614  jz      short loc_180013646
0x180013616  lea     rcx, aPreventindexin_1; "PreventIndexingOfflineFiles"
0x18001361d  mov     [rax+8], rcx
0x180013621  mov     [rax+10h], r12d
0x180013625  mov     [rax+18h], rcx
0x180013629  mov     [rax+20h], r15
0x18001362d  mov     [rax+28h], rdi
0x180013631  mov     [rax+30h], r12d
0x180013635  mov     [rax+38h], rcx
0x180013639  mov     [rax+40h], r14
0x18001363d  mov     [rax+48h], rdi
0x180013641  mov     [rax], rdx
0x180013644  jmp     short loc_180013649
0x180013646  mov     rax, r12
0x180013649  mov     [rbp+50h+var_C8], rax
0x18001364d  mov     rcx, rsi; unsigned __int64
0x180013650  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013655  mov     [rsp+150h+var_100], rax
0x18001365a  test    rax, rax
0x18001365d  jz      short loc_180013696
0x18001365f  lea     rcx, aPreventindexin; "PreventIndexingUncachedExchangeFolders"
0x180013666  mov     [rax+8], rcx
0x18001366a  mov     [rax+10h], r12d
0x18001366e  mov     [rax+18h], rcx
0x180013672  mov     [rax+20h], r15
0x180013676  mov     [rax+28h], rdi
0x18001367a  mov     [rax+30h], r12d
0x18001367e  mov     [rax+38h], rcx
0x180013682  mov     [rax+40h], r14
0x180013686  mov     [rax+48h], rdi
0x18001368a  lea     rcx, ??_7COn1Off0Policy@@6B@; const COn1Off0Policy::`vftable'
0x180013691  mov     [rax], rcx
0x180013694  jmp     short loc_180013699
0x180013696  mov     rax, r12
0x180013699  mov     [rbp+50h+var_C0], rax
0x18001369d  mov     rcx, rsi; unsigned __int64
0x1800136a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800136a5  mov     [rsp+150h+var_100], rax
0x1800136aa  test    rax, rax
0x1800136ad  jz      short loc_1800136E6
0x1800136af  lea     rcx, aPreventindexin_4; "PreventIndexingOutlook"
0x1800136b6  mov     [rax+8], rcx
0x1800136ba  mov     [rax+10h], r12d
0x1800136be  mov     [rax+18h], rcx
0x1800136c2  mov     [rax+20h], r15
0x1800136c6  mov     [rax+28h], rdi
0x1800136ca  mov     [rax+30h], r12d
0x1800136ce  mov     [rax+38h], rcx
0x1800136d2  mov     [rax+40h], r14
0x1800136d6  mov     [rax+48h], rdi
0x1800136da  lea     rcx, ??_7COn1Off0Policy@@6B@; const COn1Off0Policy::`vftable'
0x1800136e1  mov     [rax], rcx
0x1800136e4  jmp     short loc_1800136E9
0x1800136e6  mov     rax, r12
0x1800136e9  mov     [rbp+50h+var_B8], rax
0x1800136ed  mov     rcx, rsi; unsigned __int64
0x1800136f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800136f5  mov     [rsp+150h+var_100], rax
0x1800136fa  test    rax, rax
0x1800136fd  jz      short loc_180013736
0x1800136ff  lea     rcx, aPreventindexin_2; "PreventIndexingEmailAttachments"
0x180013706  mov     [rax+8], rcx
0x18001370a  mov     [rax+10h], r12d
0x18001370e  mov     [rax+18h], rcx
0x180013712  mov     [rax+20h], r15
0x180013716  mov     [rax+28h], rdi
0x18001371a  mov     [rax+30h], r12d
0x18001371e  mov     [rax+38h], rcx
0x180013722  mov     [rax+40h], r14
0x180013726  mov     [rax+48h], rdi
0x18001372a  lea     rcx, ??_7COn1Off0Policy@@6B@; const COn1Off0Policy::`vftable'
0x180013731  mov     [rax], rcx
0x180013734  jmp     short loc_180013739
0x180013736  mov     rax, r12
0x180013739  mov     [rbp+50h+var_B0], rax
0x18001373d  mov     rcx, rsi; unsigned __int64
0x180013740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013745  mov     [rsp+150h+var_100], rax
0x18001374a  test    rax, rax
0x18001374d  jz      short loc_180013786
0x18001374f  lea     rcx, aPreventindexin_3; "PreventIndexingPublicFolders"
0x180013756  mov     [rax+8], rcx
0x18001375a  mov     [rax+10h], r12d
0x18001375e  mov     [rax+18h], rcx
0x180013762  mov     [rax+20h], r15
0x180013766  mov     [rax+28h], rdi
0x18001376a  mov     [rax+30h], r12d
0x18001376e  mov     [rax+38h], rcx
0x180013772  mov     [rax+40h], r14
0x180013776  mov     [rax+48h], rdi
0x18001377a  lea     rcx, ??_7COn1Off0Policy@@6B@; const COn1Off0Policy::`vftable'
0x180013781  mov     [rax], rcx
0x180013784  jmp     short loc_180013789
0x180013786  mov     rax, r12
0x180013789  mov     [rbp+50h+var_A8], rax
0x18001378d  mov     ecx, 58h ; 'X'; unsigned __int64
0x180013792  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013797  mov     [rsp+150h+var_100], rax
0x18001379c  test    rax, rax
0x18001379f  jz      short loc_1800137E1
0x1800137a1  lea     rcx, aAllowusingdiac; "AllowUsingDiacritics"
0x1800137a8  mov     [rax+8], rcx
0x1800137ac  mov     [rax+10h], r12d
0x1800137b0  mov     [rax+18h], rcx
0x1800137b4  mov     [rax+20h], r15
0x1800137b8  mov     [rax+28h], rdi
0x1800137bc  mov     [rax+30h], r12d
0x1800137c0  mov     [rax+38h], rcx
0x1800137c4  mov     [rax+40h], r14
0x1800137c8  mov     [rax+48h], rdi
0x1800137cc  lea     rcx, ??_7CDiacriticsPolicy@@6B@; const CDiacriticsPolicy::`vftable'
0x1800137d3  mov     [rax], rcx
0x1800137d6  lea     rcx, [rsp+150h+var_F0]
0x1800137db  mov     [rax+50h], rcx
0x1800137df  jmp     short loc_1800137E4
0x1800137e1  mov     rax, r12
0x1800137e4  mov     [rbp+50h+var_A0], rax
0x1800137e8  mov     rcx, rsi; unsigned __int64
0x1800137eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800137f0  mov     [rsp+150h+var_100], rax
0x1800137f5  test    rax, rax
0x1800137f8  jz      short loc_180013831
0x1800137fa  lea     rcx, aAlwaysuseautol; "AlwaysUseAutoLangDetection"
0x180013801  mov     [rax+8], rcx
0x180013805  mov     [rax+10h], r12d
0x180013809  mov     [rax+18h], rcx
0x18001380d  mov     [rax+20h], r15
0x180013811  mov     [rax+28h], rdi
0x180013815  mov     [rax+30h], r12d
0x180013819  mov     [rax+38h], rcx
0x18001381d  mov     [rax+40h], r14
0x180013821  mov     [rax+48h], rdi
0x180013825  lea     rcx, ??_7CAlwaysUseAutoLangDetectionPolicy@@6B@; const CAlwaysUseAutoLangDetectionPolicy::`vftable'
0x18001382c  mov     [rax], rcx
0x18001382f  jmp     short loc_180013834
0x180013831  mov     rax, r12
0x180013834  mov     [rbp+50h+var_98], rax
0x180013838  mov     rcx, rsi; unsigned __int64
0x18001383b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013840  mov     [rsp+150h+var_100], rax
0x180013845  test    rax, rax
0x180013848  jz      short loc_180013881
0x18001384a  lea     rcx, aDisableremovab; "DisableRemovableDriveIndexing"
0x180013851  mov     [rax+8], rcx
0x180013855  mov     [rax+10h], r12d
0x180013859  mov     [rax+18h], rcx
0x18001385d  mov     [rax+20h], r15
0x180013861  mov     [rax+28h], rdi
0x180013865  mov     [rax+30h], r12d
0x180013869  mov     [rax+38h], rcx
0x18001386d  mov     [rax+40h], r14
0x180013871  mov     [rax+48h], rdi
0x180013875  lea     rcx, ??_7CDisableRemovableDriveIndexingPolicy@@6B@; const CDisableRemovableDriveIndexingPolicy::`vftable'
0x18001387c  mov     [rax], rcx
0x18001387f  jmp     short loc_180013884
0x180013881  mov     rax, r12
0x180013884  mov     [rbp+50h+var_90], rax
0x180013888  mov     ecx, 60h ; '`'; unsigned __int64
0x18001388d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013892  mov     [rsp+150h+var_100], rax
0x180013897  test    rax, rax
0x18001389a  jz      short loc_1800138DE
0x18001389c  lea     rdx, aDatadirectory; "DataDirectory"
0x1800138a3  mov     [rax+8], rdx
0x1800138a7  mov     [rax+10h], r12d
0x1800138ab  mov     [rax+18h], rdx
0x1800138af  mov     [rax+20h], r15
0x1800138b3  mov     ecx, 2
0x1800138b8  mov     [rax+28h], ecx
0x1800138bb  mov     [rax+30h], r12
0x1800138bf  mov     [rax+38h], r12d
0x1800138c3  mov     [rax+40h], rdx
0x1800138c7  mov     [rax+48h], r14
0x1800138cb  mov     [rax+50h], ecx
0x1800138ce  mov     [rax+58h], r12
0x1800138d2  lea     rcx, ??_7CDataDirectoryPolicy@@6B@; const CDataDirectoryPolicy::`vftable'
0x1800138d9  mov     [rax], rcx
0x1800138dc  jmp     short loc_1800138E1
0x1800138de  mov     rax, r12
0x1800138e1  mov     [rbp+50h+var_88], rax
0x1800138e5  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800138ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800138ef  mov     [rsp+150h+var_100], rax
0x1800138f4  test    rax, rax
0x1800138f7  jz      short loc_180013903
0x1800138f9  mov     rcx, rax; this
0x1800138fc  call    ??0CExcludedExtsPolicy@@QEAA@XZ; CExcludedExtsPolicy::CExcludedExtsPolicy(void)
0x180013901  jmp     short loc_180013906
0x180013903  mov     rax, r12
0x180013906  mov     [rbp+50h+var_80], rax
0x18001390a  mov     ecx, 60h ; '`'; unsigned __int64
0x18001390f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013914  mov     [rsp+150h+var_100], rax
0x180013919  test    rax, rax
0x18001391c  jz      short loc_18001395B
0x18001391e  lea     rcx, aTextextensions; "TextExtensions"
0x180013925  mov     [rax+8], rcx
0x180013929  mov     [rax+10h], r12d
0x18001392d  mov     [rax+18h], rcx
0x180013931  mov     [rax+20h], r15
0x180013935  mov     [rax+28h], edi
0x180013938  mov     [rax+30h], r12
0x18001393c  mov     [rax+38h], r12d
0x180013940  mov     [rax+40h], rcx
0x180013944  mov     [rax+48h], r14
0x180013948  mov     [rax+50h], edi
0x18001394b  mov     [rax+58h], r12
0x18001394f  lea     rcx, ??_7CAsTextExtsPolicy@@6B@; const CAsTextExtsPolicy::`vftable'
0x180013956  mov     [rax], rcx
0x180013959  jmp     short loc_18001395E
0x18001395b  mov     rax, r12
0x18001395e  mov     [rbp+50h+var_78], rax
0x180013962  mov     rcx, rsi; unsigned __int64
  ... truncated ...
```
