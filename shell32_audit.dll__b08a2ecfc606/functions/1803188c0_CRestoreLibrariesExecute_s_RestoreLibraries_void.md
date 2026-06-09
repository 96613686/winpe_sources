# CRestoreLibrariesExecute::s_RestoreLibraries(void *)

- ea: `0x1803188c0`
- end: `0x180318cf2`
- name: `?s_RestoreLibraries@CRestoreLibrariesExecute@@CAKPEAX@Z`
- size: `1074`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180055afc`
- `0x180249490`
- `0x18024a53c`
- `0x180318538`
- `0x180318798`
- `0x1803188c0`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180318b4f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180318b4f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180318a95`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180318a95`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180318aae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180318aae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180318a76`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180318a76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318bd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180318bd4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031892f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031892f`
- `api-ms-win-storage-exports-internal-l1-1-0!CopyDefaultLibrariesFromGroupPolicy` at `0x180318be2`
- `api-ms-win-storage-exports-internal-l1-1-0!CopyDefaultLibrariesFromGroupPolicy` at `0x180318be2`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x180318ae8`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x180318ae8`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180318c57`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180318c57`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180318bfd`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180318bfd`
- `Windows.Storage!IsUnderKnownFolder` at `0x180318a0d`
- `Windows.Storage!IsUnderKnownFolder` at `0x180318a0d`
- `Windows.Storage!ShellExecuteExW` at `0x180318c95`
- `Windows.Storage!ShellExecuteExW` at `0x180318c95`
- `Windows.Storage!ILFree` at `0x180318c0e`
- `Windows.Storage!ILFree` at `0x180318ca6`
- `Windows.Storage!ILFree` at `0x180318c0e`
- `Windows.Storage!ILFree` at `0x180318ca6`

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
0x1803188c0  push    rbp
0x1803188c2  push    rbx
0x1803188c3  push    rsi
0x1803188c4  push    rdi
0x1803188c5  push    r14
0x1803188c7  push    r15
0x1803188c9  lea     rbp, [rsp-18h]
0x1803188ce  sub     rsp, 118h
0x1803188d5  mov     rax, cs:__security_cookie
0x1803188dc  xor     rax, rsp
0x1803188df  mov     [rbp+40h+var_38], rax
0x1803188e3  mov     r15d, 1
0x1803188e9  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1803188f0  jz      short loc_18031890A
0x1803188f2  lea     rax, [rbp+40h+var_48]
0x1803188f6  mov     r9d, r15d
0x1803188f9  lea     rdx, ShellTask_UserLibrary_RestoreLibrariesThread_Start
0x180318900  mov     [rsp+140h+ppv], rax
0x180318905  call    McGenEventWrite_EtwEventWriteTransfer
0x18031890a  lea     rax, [rsp+140h+var_F8]
0x18031890f  xor     r14d, r14d
0x180318912  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180318919  mov     [rsp+140h+var_F8], r14
0x18031891e  mov     r8d, r15d; dwClsContext
0x180318921  mov     [rsp+140h+ppv], rax; ppv
0x180318926  xor     edx, edx; pUnkOuter
0x180318928  lea     rcx, CLSID_KnownFolderManager; rclsid
0x18031892f  call    cs:__imp_CoCreateInstance
0x180318936  nop     dword ptr [rax+rax+00h]
0x18031893b  test    eax, eax
0x18031893d  js      loc_180318C3C
0x180318943  mov     rcx, [rsp+140h+var_F8]
0x180318948  lea     r8, [rsp+140h+var_D8]
0x18031894d  mov     [rsp+140h+var_D8], r14
0x180318952  lea     rdx, FOLDERID_Libraries
0x180318959  mov     rax, [rcx]
0x18031895c  mov     rax, [rax+30h]
0x180318960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318965  test    eax, eax
0x180318967  js      loc_180318C2B
0x18031896d  mov     rcx, [rsp+140h+var_D8]
0x180318972  lea     r8, [rsp+140h+dwItem1]
0x180318977  mov     [rsp+140h+dwItem1], r14
0x18031897c  mov     edx, 8000h
0x180318981  mov     rax, [rcx]
0x180318984  mov     rax, [rax+40h]
0x180318988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031898d  test    eax, eax
0x18031898f  js      loc_180318C1A
0x180318995  mov     rcx, [rsp+140h+var_F8]
0x18031899a  lea     r8, [rbp+40h+var_50]
0x18031899e  mov     [rbp+40h+var_50], r14d
0x1803189a2  lea     rdx, [rsp+140h+pv]
0x1803189a7  mov     [rsp+140h+pv], r14
0x1803189ac  mov     rax, [rcx]
0x1803189af  mov     rax, [rax+28h]
0x1803189b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803189b8  test    eax, eax
0x1803189ba  js      loc_180318BE0
0x1803189c0  mov     ebx, r14d
0x1803189c3  cmp     [rbp+40h+var_50], r14d
0x1803189c7  jbe     loc_180318BCF
0x1803189cd  mov     rcx, [rsp+140h+var_F8]
0x1803189d2  mov     rdx, [rsp+140h+pv]
0x1803189d7  mov     [rsp+140h+var_110], r14
0x1803189dc  mov     esi, ebx
0x1803189de  mov     r8, [rcx]
0x1803189e1  shl     rsi, 4
0x1803189e5  add     rdx, rsi
0x1803189e8  mov     rax, [r8+30h]
0x1803189ec  lea     r8, [rsp+140h+var_110]
0x1803189f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803189f6  test    eax, eax
0x1803189f8  js      loc_180318BC3
0x1803189fe  mov     r8, [rsp+140h+var_110]
0x180318a03  lea     rdx, FOLDERID_Libraries
0x180318a0a  mov     ecx, r15d
0x180318a0d  call    cs:__imp_?IsUnderKnownFolder@@YAHHAEBU_GUID@@PEAUIKnownFolder@@@Z; IsUnderKnownFolder(int,_GUID const &,IKnownFolder *)
0x180318a14  nop     dword ptr [rax+rax+00h]
0x180318a19  test    eax, eax
0x180318a1b  jz      loc_180318BB2
0x180318a21  mov     rcx, [rsp+140h+var_110]
0x180318a26  lea     r8, [rsp+140h+lpFileName]
0x180318a2b  mov     [rsp+140h+lpFileName], r14
0x180318a30  mov     edx, 4000h
0x180318a35  mov     rax, [rcx]
0x180318a38  mov     rax, [rax+30h]
0x180318a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318a41  test    eax, eax
0x180318a43  js      loc_180318BB2
0x180318a49  mov     rcx, [rsp+140h+var_110]
0x180318a4e  lea     r8, [rsp+140h+pszPath]
0x180318a53  mov     [rsp+140h+pszPath], r14
0x180318a58  mov     edx, 4400h
0x180318a5d  mov     rax, [rcx]
0x180318a60  mov     rax, [rax+30h]
0x180318a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318a69  test    eax, eax
0x180318a6b  js      loc_180318BA1
0x180318a71  mov     rcx, [rsp+140h+pszPath]; pszPath
0x180318a76  call    cs:__imp_PathFindExtensionW
0x180318a7d  nop     dword ptr [rax+rax+00h]
0x180318a82  test    rax, rax
0x180318a85  jz      loc_180318B90
0x180318a8b  lea     rdx, aLibraryMs; ".library-ms"
0x180318a92  mov     rcx, rax; pszStr1
0x180318a95  call    cs:__imp_StrCmpICW
0x180318a9c  nop     dword ptr [rax+rax+00h]
0x180318aa1  test    eax, eax
0x180318aa3  jnz     loc_180318B90
0x180318aa9  mov     rcx, [rsp+140h+lpFileName]; pszPath
0x180318aae  call    cs:__imp_PathFileExistsW
0x180318ab5  nop     dword ptr [rax+rax+00h]
0x180318aba  test    eax, eax
0x180318abc  jz      loc_180318B74
0x180318ac2  mov     rcx, [rsp+140h+pv]
0x180318ac7  lea     rax, [rsp+140h+var_E8]
0x180318acc  add     rcx, rsi; rfid
0x180318acf  mov     [rsp+140h+var_E8], r14
0x180318ad4  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180318adb  mov     [rsp+140h+ppv], rax; ppv
0x180318ae0  xor     r8d, r8d; hToken
0x180318ae3  mov     edx, 4000h; flags
0x180318ae8  call    cs:__imp_SHGetKnownFolderItem
0x180318aef  nop     dword ptr [rax+rax+00h]
0x180318af4  test    eax, eax
0x180318af6  js      loc_180318B90
0x180318afc  mov     rcx, [rsp+140h+var_E8]
0x180318b01  lea     rdx, [rbp+40h+var_48]
0x180318b05  mov     [rbp+40h+var_48], r14
0x180318b09  lea     r9, _GUID_86187c37_e662_4d1e_a122_7478676d7e6e
0x180318b10  mov     [rsp+140h+ppv], rdx
0x180318b15  lea     r8, BHID_SFObject
0x180318b1c  xor     edx, edx
0x180318b1e  mov     dil, r14b
0x180318b21  mov     rax, [rcx]
0x180318b24  mov     rax, [rax+18h]
0x180318b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318b2d  test    eax, eax
0x180318b2f  js      short loc_180318B43
0x180318b31  mov     rcx, [rbp+40h+var_48]
0x180318b35  mov     rax, [rcx]
0x180318b38  mov     rax, [rax+10h]
0x180318b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318b41  jmp     short loc_180318B5E
0x180318b43  cmp     eax, 8007000Bh
0x180318b48  jnz     short loc_180318B5E
0x180318b4a  mov     rcx, [rsp+140h+lpFileName]; lpFileName
0x180318b4f  call    cs:__imp_DeleteFileW
0x180318b56  nop     dword ptr [rax+rax+00h]
0x180318b5b  mov     dil, r15b
0x180318b5e  mov     rcx, [rsp+140h+var_E8]
0x180318b63  mov     rax, [rcx]
0x180318b66  mov     rax, [rax+10h]
0x180318b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318b6f  test    dil, dil
0x180318b72  jz      short loc_180318B90
0x180318b74  mov     rcx, [rsp+140h+pv]
0x180318b79  mov     r9, [rsp+140h+pszPath]; unsigned __int16 *
0x180318b7e  add     rcx, rsi; rfid
0x180318b81  mov     r8, [rsp+140h+lpFileName]; unsigned __int16 *
0x180318b86  mov     rdx, [rsp+140h+var_110]; struct IKnownFolder *
0x180318b8b  call    ?s_RestoreKnownLibrary@CRestoreLibrariesExecute@@CAXAEBU_GUID@@PEAUIKnownFolder@@PEBG2@Z; CRestoreLibrariesExecute::s_RestoreKnownLibrary(_GUID const &,IKnownFolder *,ushort const *,ushort const *)
0x180318b90  mov     rcx, [rsp+140h+pszPath]; pv
0x180318b95  call    cs:__imp_CoTaskMemFree
0x180318b9c  nop     dword ptr [rax+rax+00h]
0x180318ba1  mov     rcx, [rsp+140h+lpFileName]; pv
0x180318ba6  call    cs:__imp_CoTaskMemFree
0x180318bad  nop     dword ptr [rax+rax+00h]
0x180318bb2  mov     rcx, [rsp+140h+var_110]
0x180318bb7  mov     rax, [rcx]
0x180318bba  mov     rax, [rax+10h]
0x180318bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318bc3  add     ebx, r15d
0x180318bc6  cmp     ebx, [rbp+40h+var_50]
0x180318bc9  jb      loc_1803189CD
0x180318bcf  mov     rcx, [rsp+140h+pv]; pv
0x180318bd4  call    cs:__imp_CoTaskMemFree
0x180318bdb  nop     dword ptr [rax+rax+00h]
0x180318be0  xor     ecx, ecx
0x180318be2  call    cs:__imp_CopyDefaultLibrariesFromGroupPolicy
0x180318be9  nop     dword ptr [rax+rax+00h]
0x180318bee  mov     r8, [rsp+140h+dwItem1]; dwItem1
0x180318bf3  xor     r9d, r9d; dwItem2
0x180318bf6  xor     edx, edx; uFlags
0x180318bf8  mov     ecx, 1000h; wEventId
0x180318bfd  call    cs:__imp_SHChangeNotify
0x180318c04  nop     dword ptr [rax+rax+00h]
0x180318c09  mov     rcx, [rsp+140h+dwItem1]; pidl
0x180318c0e  call    cs:__imp_ILFree
0x180318c15  nop     dword ptr [rax+rax+00h]
0x180318c1a  mov     rcx, [rsp+140h+var_D8]
0x180318c1f  mov     rax, [rcx]
0x180318c22  mov     rax, [rax+10h]
0x180318c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318c2b  mov     rcx, [rsp+140h+var_F8]
0x180318c30  mov     rax, [rcx]
0x180318c33  mov     rax, [rax+10h]
0x180318c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180318c3c  call    ?_OnUserProfileReset@@YAXXZ; _OnUserProfileReset(void)
0x180318c41  lea     r9, [rsp+140h+ppidl]; ppidl
0x180318c46  mov     [rsp+140h+ppidl], r14
0x180318c4b  xor     r8d, r8d; hToken
0x180318c4e  lea     rcx, FOLDERID_UsersLibraries; rfid
0x180318c55  xor     edx, edx; dwFlags
0x180318c57  call    cs:__imp_SHGetKnownFolderIDList
0x180318c5e  nop     dword ptr [rax+rax+00h]
0x180318c63  test    eax, eax
0x180318c65  js      short loc_180318CB2
0x180318c67  xor     edx, edx; Val
0x180318c69  mov     [rbp+40h+pExecInfo.cbSize], 70h ; 'p'
0x180318c70  lea     rcx, [rbp+40h+pExecInfo.fMask]; void *
0x180318c74  lea     r8d, [rdx+6Ch]; Size
0x180318c78  call    memset_0
0x180318c7d  mov     rax, [rsp+140h+ppidl]
0x180318c82  lea     rcx, [rbp+40h+pExecInfo]; pExecInfo
0x180318c86  mov     [rbp+40h+pExecInfo.lpIDList], rax
0x180318c8a  mov     [rbp+40h+pExecInfo.fMask], 0Ch
0x180318c91  mov     [rbp+40h+pExecInfo.nShow], r15d
0x180318c95  call    cs:__imp_ShellExecuteExW
0x180318c9c  nop     dword ptr [rax+rax+00h]
0x180318ca1  mov     rcx, [rsp+140h+ppidl]; pidl
0x180318ca6  call    cs:__imp_ILFree
0x180318cad  nop     dword ptr [rax+rax+00h]
0x180318cb2  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x180318cb9  jz      short loc_180318CD3
0x180318cbb  lea     rax, [rbp+40h+var_48]
0x180318cbf  mov     r9d, r15d
0x180318cc2  lea     rdx, ShellTask_UserLibrary_RestoreLibrariesThread_Stop
0x180318cc9  mov     [rsp+140h+ppv], rax
0x180318cce  call    McGenEventWrite_EtwEventWriteTransfer
0x180318cd3  xor     eax, eax
0x180318cd5  mov     rcx, [rbp+40h+var_38]
0x180318cd9  xor     rcx, rsp; StackCookie
0x180318cdc  call    __security_check_cookie
0x180318ce1  add     rsp, 118h
0x180318ce8  pop     r15
0x180318cea  pop     r14
0x180318cec  pop     rdi
0x180318ced  pop     rsi
0x180318cee  pop     rbx
0x180318cef  pop     rbp
0x180318cf0  retn
```
