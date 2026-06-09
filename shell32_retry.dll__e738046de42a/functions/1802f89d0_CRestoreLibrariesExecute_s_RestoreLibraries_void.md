# CRestoreLibrariesExecute::s_RestoreLibraries(void *)

- ea: `0x1802f89d0`
- end: `0x1802f8da1`
- name: `?s_RestoreLibraries@CRestoreLibrariesExecute@@CAKPEAX@Z`
- size: `977`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800bb328`
- `0x180233280`
- `0x1802342fc`
- `0x1802f86b4`
- `0x1802f88d8`
- `0x1802f89d0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802f8c3b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802f8c3b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1802f8b93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1802f8b93`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802f8ba6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802f8ba6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802f8b7a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802f8b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f8cae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f8a3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f8a3f`
- `api-ms-win-storage-exports-internal-l1-1-0!CopyDefaultLibrariesFromGroupPolicy` at `0x1802f8cb6`
- `api-ms-win-storage-exports-internal-l1-1-0!CopyDefaultLibrariesFromGroupPolicy` at `0x1802f8cb6`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1802f8bda`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1802f8bda`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1802f8d19`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1802f8d19`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1802f8ccb`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1802f8ccb`
- `Windows.Storage!IsUnderKnownFolder` at `0x1802f8b17`
- `Windows.Storage!IsUnderKnownFolder` at `0x1802f8b17`
- `Windows.Storage!ShellExecuteExW` at `0x1802f8d51`
- `Windows.Storage!ShellExecuteExW` at `0x1802f8d51`
- `Windows.Storage!ILFree` at `0x1802f8cd6`
- `Windows.Storage!ILFree` at `0x1802f8d5c`
- `Windows.Storage!ILFree` at `0x1802f8cd6`
- `Windows.Storage!ILFree` at `0x1802f8d5c`

## pseudocode

```c
__int64 __fastcall CRestoreLibrariesExecute::s_RestoreLibraries(PVOID Parameter, __int64 a2, int a3)
{
  unsigned int i; // ebx
  __int64 v4; // rsi
  const WCHAR *ExtensionW; // rax
  char v6; // di
  int v7; // eax
  int v8; // ecx
  int v9; // r8d
  struct IKnownFolder *v11; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  void *v16; // [rsp+58h] [rbp-A8h] BYREF
  LPCVOID dwItem1; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp-90h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v21; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v22[2]; // [rsp+F8h] [rbp-8h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)Parameter,
      (unsigned int)&ShellTask_UserLibrary_RestoreLibrariesThread_Start,
      a3,
      1,
      (__int64)v22);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &ppv) >= 0 )
  {
    v18 = 0;
    if ( (*(int (__fastcall **)(LPVOID, const GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(
           ppv,
           &FOLDERID_Libraries,
           &v18) >= 0 )
    {
      dwItem1 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, LPCVOID *))(*(_QWORD *)v18 + 64LL))(v18, 0x8000, &dwItem1) >= 0 )
      {
        v21 = 0;
        pv = 0;
        if ( (*(int (__fastcall **)(LPVOID, LPVOID *, unsigned int *))(*(_QWORD *)ppv + 40LL))(ppv, &pv, &v21) >= 0 )
        {
          for ( i = 0; i < v21; ++i )
          {
            v11 = 0;
            v4 = 16LL * i;
            if ( (*(int (__fastcall **)(LPVOID, char *, struct IKnownFolder **))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   (char *)pv + v4,
                   &v11) >= 0 )
            {
              if ( IsUnderKnownFolder(1, &FOLDERID_Libraries, v11) )
              {
                lpFileName = 0;
                if ( ((int (__fastcall *)(struct IKnownFolder *, __int64, LPCWSTR *))v11->lpVtbl->GetPath)(
                       v11,
                       0x4000,
                       &lpFileName) >= 0 )
                {
                  pszPath = 0;
                  if ( ((int (__fastcall *)(struct IKnownFolder *, __int64, LPCWSTR *))v11->lpVtbl->GetPath)(
                         v11,
                         17408,
                         &pszPath) >= 0 )
                  {
                    ExtensionW = PathFindExtensionW(pszPath);
                    if ( ExtensionW && !StrCmpICW(ExtensionW, L".library-ms") )
                    {
                      if ( !PathFileExistsW(lpFileName) )
                        goto LABEL_21;
                      v16 = 0;
                      if ( SHGetKnownFolderItem(
                             (const KNOWNFOLDERID *const)((char *)pv + v4),
                             KF_FLAG_DONT_VERIFY,
                             0,
                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                             &v16) >= 0 )
                      {
                        v22[0] = 0;
                        v6 = 0;
                        v7 = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, _QWORD *))(*(_QWORD *)v16 + 24LL))(
                               v16,
                               0,
                               &BHID_SFObject,
                               &GUID_86187c37_e662_4d1e_a122_7478676d7e6e,
                               v22);
                        if ( v7 < 0 )
                        {
                          if ( v7 == -2147024885 )
                          {
                            DeleteFileW(lpFileName);
                            v6 = 1;
                          }
                        }
                        else
                        {
                          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
                        }
                        (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
                        if ( v6 )
LABEL_21:
                          CRestoreLibrariesExecute::s_RestoreKnownLibrary(
                            (KNOWNFOLDERID *)((char *)pv + v4),
                            v11,
                            lpFileName,
                            pszPath);
                      }
                    }
                    CoTaskMemFree((LPVOID)pszPath);
                  }
                  CoTaskMemFree((LPVOID)lpFileName);
                }
              }
              ((void (__fastcall *)(struct IKnownFolder *))v11->lpVtbl->Release)(v11);
            }
          }
          CoTaskMemFree(pv);
        }
        CopyDefaultLibrariesFromGroupPolicy(0);
        SHChangeNotify(4096, 0, dwItem1, 0);
        ILFree((LPITEMIDLIST)dwItem1);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  _OnUserProfileReset();
  ppidl = 0;
  if ( SHGetKnownFolderIDList(&FOLDERID_UsersLibraries, 0, 0, &ppidl) >= 0 )
  {
    pExecInfo.cbSize = 112;
    memset_0(&pExecInfo.fMask, 0, 0x6Cu);
    pExecInfo.lpIDList = ppidl;
    pExecInfo.fMask = 12;
    pExecInfo.nShow = 1;
    ShellExecuteExW(&pExecInfo);
    ILFree(ppidl);
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v8,
      (unsigned int)&ShellTask_UserLibrary_RestoreLibrariesThread_Stop,
      v9,
      1,
      (__int64)v22);
  return 0;
}

```

## disassembly

```asm
0x1802f89d0  push    rbp
0x1802f89d2  push    rbx
0x1802f89d3  push    rsi
0x1802f89d4  push    rdi
0x1802f89d5  push    r14
0x1802f89d7  push    r15
0x1802f89d9  lea     rbp, [rsp-18h]
0x1802f89de  sub     rsp, 118h
0x1802f89e5  mov     rax, cs:__security_cookie
0x1802f89ec  xor     rax, rsp
0x1802f89ef  mov     [rbp+40h+var_38], rax
0x1802f89f3  mov     r15d, 1
0x1802f89f9  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802f8a00  jz      short loc_1802F8A1A
0x1802f8a02  lea     rax, [rbp+40h+var_48]
0x1802f8a06  mov     r9d, r15d
0x1802f8a09  lea     rdx, ShellTask_UserLibrary_RestoreLibrariesThread_Start
0x1802f8a10  mov     [rsp+140h+ppv], rax
0x1802f8a15  call    McGenEventWrite_EtwEventWriteTransfer
0x1802f8a1a  lea     rax, [rsp+140h+var_F8]
0x1802f8a1f  xor     r14d, r14d
0x1802f8a22  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1802f8a29  mov     [rsp+140h+var_F8], r14
0x1802f8a2e  mov     r8d, r15d; dwClsContext
0x1802f8a31  mov     [rsp+140h+ppv], rax; ppv
0x1802f8a36  xor     edx, edx; pUnkOuter
0x1802f8a38  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1802f8a3f  call    cs:__imp_CoCreateInstance
0x1802f8a45  test    eax, eax
0x1802f8a47  js      loc_1802F8CFE
0x1802f8a4d  mov     rcx, [rsp+140h+var_F8]
0x1802f8a52  lea     r8, [rsp+140h+var_D8]
0x1802f8a57  mov     [rsp+140h+var_D8], r14
0x1802f8a5c  lea     rdx, FOLDERID_Libraries
0x1802f8a63  mov     rax, [rcx]
0x1802f8a66  mov     rax, [rax+30h]
0x1802f8a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8a6f  test    eax, eax
0x1802f8a71  js      loc_1802F8CED
0x1802f8a77  mov     rcx, [rsp+140h+var_D8]
0x1802f8a7c  lea     r8, [rsp+140h+dwItem1]
0x1802f8a81  mov     [rsp+140h+dwItem1], r14
0x1802f8a86  mov     edx, 8000h
0x1802f8a8b  mov     rax, [rcx]
0x1802f8a8e  mov     rax, [rax+40h]
0x1802f8a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8a97  test    eax, eax
0x1802f8a99  js      loc_1802F8CDC
0x1802f8a9f  mov     rcx, [rsp+140h+var_F8]
0x1802f8aa4  lea     r8, [rbp+40h+var_50]
0x1802f8aa8  mov     [rbp+40h+var_50], r14d
0x1802f8aac  lea     rdx, [rsp+140h+pv]
0x1802f8ab1  mov     [rsp+140h+pv], r14
0x1802f8ab6  mov     rax, [rcx]
0x1802f8ab9  mov     rax, [rax+28h]
0x1802f8abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8ac2  test    eax, eax
0x1802f8ac4  js      loc_1802F8CB4
0x1802f8aca  mov     ebx, r14d
0x1802f8acd  cmp     [rbp+40h+var_50], r14d
0x1802f8ad1  jbe     loc_1802F8CA9
0x1802f8ad7  mov     rcx, [rsp+140h+var_F8]
0x1802f8adc  mov     rdx, [rsp+140h+pv]
0x1802f8ae1  mov     [rsp+140h+var_110], r14
0x1802f8ae6  mov     esi, ebx
0x1802f8ae8  mov     r8, [rcx]
0x1802f8aeb  shl     rsi, 4
0x1802f8aef  add     rdx, rsi
0x1802f8af2  mov     rax, [r8+30h]
0x1802f8af6  lea     r8, [rsp+140h+var_110]
0x1802f8afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8b00  test    eax, eax
0x1802f8b02  js      loc_1802F8C9D
0x1802f8b08  mov     r8, [rsp+140h+var_110]
0x1802f8b0d  lea     rdx, FOLDERID_Libraries
0x1802f8b14  mov     ecx, r15d
0x1802f8b17  call    cs:__imp_?IsUnderKnownFolder@@YAHHAEBU_GUID@@PEAUIKnownFolder@@@Z; IsUnderKnownFolder(int,_GUID const &,IKnownFolder *)
0x1802f8b1d  test    eax, eax
0x1802f8b1f  jz      loc_1802F8C8C
0x1802f8b25  mov     rcx, [rsp+140h+var_110]
0x1802f8b2a  lea     r8, [rsp+140h+lpFileName]
0x1802f8b2f  mov     [rsp+140h+lpFileName], r14
0x1802f8b34  mov     edx, 4000h
0x1802f8b39  mov     rax, [rcx]
0x1802f8b3c  mov     rax, [rax+30h]
0x1802f8b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8b45  test    eax, eax
0x1802f8b47  js      loc_1802F8C8C
0x1802f8b4d  mov     rcx, [rsp+140h+var_110]
0x1802f8b52  lea     r8, [rsp+140h+pszPath]
0x1802f8b57  mov     [rsp+140h+pszPath], r14
0x1802f8b5c  mov     edx, 4400h
0x1802f8b61  mov     rax, [rcx]
0x1802f8b64  mov     rax, [rax+30h]
0x1802f8b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8b6d  test    eax, eax
0x1802f8b6f  js      loc_1802F8C81
0x1802f8b75  mov     rcx, [rsp+140h+pszPath]; pszPath
0x1802f8b7a  call    cs:__imp_PathFindExtensionW
0x1802f8b80  test    rax, rax
0x1802f8b83  jz      loc_1802F8C76
0x1802f8b89  lea     rdx, aLibraryMs; ".library-ms"
0x1802f8b90  mov     rcx, rax; pszStr1
0x1802f8b93  call    cs:__imp_StrCmpICW
0x1802f8b99  test    eax, eax
0x1802f8b9b  jnz     loc_1802F8C76
0x1802f8ba1  mov     rcx, [rsp+140h+lpFileName]; pszPath
0x1802f8ba6  call    cs:__imp_PathFileExistsW
0x1802f8bac  test    eax, eax
0x1802f8bae  jz      loc_1802F8C5A
0x1802f8bb4  mov     rcx, [rsp+140h+pv]
0x1802f8bb9  lea     rax, [rsp+140h+var_E8]
0x1802f8bbe  add     rcx, rsi; rfid
0x1802f8bc1  mov     [rsp+140h+var_E8], r14
0x1802f8bc6  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1802f8bcd  mov     [rsp+140h+ppv], rax; ppv
0x1802f8bd2  xor     r8d, r8d; hToken
0x1802f8bd5  mov     edx, 4000h; flags
0x1802f8bda  call    cs:__imp_SHGetKnownFolderItem
0x1802f8be0  test    eax, eax
0x1802f8be2  js      loc_1802F8C76
0x1802f8be8  mov     rcx, [rsp+140h+var_E8]
0x1802f8bed  lea     rdx, [rbp+40h+var_48]
0x1802f8bf1  mov     [rbp+40h+var_48], r14
0x1802f8bf5  lea     r9, _GUID_86187c37_e662_4d1e_a122_7478676d7e6e
0x1802f8bfc  mov     [rsp+140h+ppv], rdx
0x1802f8c01  lea     r8, BHID_SFObject
0x1802f8c08  xor     edx, edx
0x1802f8c0a  mov     dil, r14b
0x1802f8c0d  mov     rax, [rcx]
0x1802f8c10  mov     rax, [rax+18h]
0x1802f8c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8c19  test    eax, eax
0x1802f8c1b  js      short loc_1802F8C2F
0x1802f8c1d  mov     rcx, [rbp+40h+var_48]
0x1802f8c21  mov     rax, [rcx]
0x1802f8c24  mov     rax, [rax+10h]
0x1802f8c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8c2d  jmp     short loc_1802F8C44
0x1802f8c2f  cmp     eax, 8007000Bh
0x1802f8c34  jnz     short loc_1802F8C44
0x1802f8c36  mov     rcx, [rsp+140h+lpFileName]; lpFileName
0x1802f8c3b  call    cs:__imp_DeleteFileW
0x1802f8c41  mov     dil, r15b
0x1802f8c44  mov     rcx, [rsp+140h+var_E8]
0x1802f8c49  mov     rax, [rcx]
0x1802f8c4c  mov     rax, [rax+10h]
0x1802f8c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8c55  test    dil, dil
0x1802f8c58  jz      short loc_1802F8C76
0x1802f8c5a  mov     rcx, [rsp+140h+pv]
0x1802f8c5f  mov     r9, [rsp+140h+pszPath]; unsigned __int16 *
0x1802f8c64  add     rcx, rsi; rfid
0x1802f8c67  mov     r8, [rsp+140h+lpFileName]; unsigned __int16 *
0x1802f8c6c  mov     rdx, [rsp+140h+var_110]; struct IKnownFolder *
0x1802f8c71  call    ?s_RestoreKnownLibrary@CRestoreLibrariesExecute@@CAXAEBU_GUID@@PEAUIKnownFolder@@PEBG2@Z; CRestoreLibrariesExecute::s_RestoreKnownLibrary(_GUID const &,IKnownFolder *,ushort const *,ushort const *)
0x1802f8c76  mov     rcx, [rsp+140h+pszPath]; pv
0x1802f8c7b  call    cs:__imp_CoTaskMemFree
0x1802f8c81  mov     rcx, [rsp+140h+lpFileName]; pv
0x1802f8c86  call    cs:__imp_CoTaskMemFree
0x1802f8c8c  mov     rcx, [rsp+140h+var_110]
0x1802f8c91  mov     rax, [rcx]
0x1802f8c94  mov     rax, [rax+10h]
0x1802f8c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8c9d  add     ebx, r15d
0x1802f8ca0  cmp     ebx, [rbp+40h+var_50]
0x1802f8ca3  jb      loc_1802F8AD7
0x1802f8ca9  mov     rcx, [rsp+140h+pv]; pv
0x1802f8cae  call    cs:__imp_CoTaskMemFree
0x1802f8cb4  xor     ecx, ecx
0x1802f8cb6  call    cs:__imp_CopyDefaultLibrariesFromGroupPolicy
0x1802f8cbc  mov     r8, [rsp+140h+dwItem1]; dwItem1
0x1802f8cc1  xor     r9d, r9d; dwItem2
0x1802f8cc4  xor     edx, edx; uFlags
0x1802f8cc6  mov     ecx, 1000h; wEventId
0x1802f8ccb  call    cs:__imp_SHChangeNotify
0x1802f8cd1  mov     rcx, [rsp+140h+dwItem1]; pidl
0x1802f8cd6  call    cs:__imp_ILFree
0x1802f8cdc  mov     rcx, [rsp+140h+var_D8]
0x1802f8ce1  mov     rax, [rcx]
0x1802f8ce4  mov     rax, [rax+10h]
0x1802f8ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8ced  mov     rcx, [rsp+140h+var_F8]
0x1802f8cf2  mov     rax, [rcx]
0x1802f8cf5  mov     rax, [rax+10h]
0x1802f8cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f8cfe  call    ?_OnUserProfileReset@@YAXXZ; _OnUserProfileReset(void)
0x1802f8d03  lea     r9, [rsp+140h+ppidl]; ppidl
0x1802f8d08  mov     [rsp+140h+ppidl], r14
0x1802f8d0d  xor     r8d, r8d; hToken
0x1802f8d10  lea     rcx, FOLDERID_UsersLibraries; rfid
0x1802f8d17  xor     edx, edx; dwFlags
0x1802f8d19  call    cs:__imp_SHGetKnownFolderIDList
0x1802f8d1f  test    eax, eax
0x1802f8d21  js      short loc_1802F8D62
0x1802f8d23  xor     edx, edx; Val
0x1802f8d25  mov     [rbp+40h+pExecInfo.cbSize], 70h ; 'p'
0x1802f8d2c  lea     rcx, [rbp+40h+pExecInfo.fMask]; void *
0x1802f8d30  lea     r8d, [rdx+6Ch]; Size
0x1802f8d34  call    memset_0
0x1802f8d39  mov     rax, [rsp+140h+ppidl]
0x1802f8d3e  lea     rcx, [rbp+40h+pExecInfo]; pExecInfo
0x1802f8d42  mov     [rbp+40h+pExecInfo.lpIDList], rax
0x1802f8d46  mov     [rbp+40h+pExecInfo.fMask], 0Ch
0x1802f8d4d  mov     [rbp+40h+pExecInfo.nShow], r15d
0x1802f8d51  call    cs:__imp_ShellExecuteExW
0x1802f8d57  mov     rcx, [rsp+140h+ppidl]; pidl
0x1802f8d5c  call    cs:__imp_ILFree
0x1802f8d62  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802f8d69  jz      short loc_1802F8D83
0x1802f8d6b  lea     rax, [rbp+40h+var_48]
0x1802f8d6f  mov     r9d, r15d
0x1802f8d72  lea     rdx, ShellTask_UserLibrary_RestoreLibrariesThread_Stop
0x1802f8d79  mov     [rsp+140h+ppv], rax
0x1802f8d7e  call    McGenEventWrite_EtwEventWriteTransfer
0x1802f8d83  xor     eax, eax
0x1802f8d85  mov     rcx, [rbp+40h+var_38]
0x1802f8d89  xor     rcx, rsp; StackCookie
0x1802f8d8c  call    __security_check_cookie
0x1802f8d91  add     rsp, 118h
0x1802f8d98  pop     r15
0x1802f8d9a  pop     r14
0x1802f8d9c  pop     rdi
0x1802f8d9d  pop     rsi
0x1802f8d9e  pop     rbx
0x1802f8d9f  pop     rbp
0x1802f8da0  retn
```
