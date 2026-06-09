# CProfileNotificationHandler::OnDelete(ushort const *,ushort const *,ulong)

- ea: `0x180006890`
- end: `0x180006aed`
- name: `?OnDelete@CProfileNotificationHandler@@UEAAJPEBG0K@Z`
- size: `605`
- prototype: `__int64 __fastcall(CProfileNotificationHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006180`
- `0x180006890`
- `0x180006f54`
- `0x18000855c`
- `0x18000868c`
- `0x180008828`
- `0x180008f80`
- `0x1800092e8`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006999`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006999`
- `SHELL32!SHGetKnownFolderPath` at `0x180006921`
- `SHELL32!SHGetKnownFolderPath` at `0x18000695c`
- `SHELL32!SHGetKnownFolderPath` at `0x180006921`
- `SHELL32!SHGetKnownFolderPath` at `0x18000695c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ab2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000697d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000697d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180006a4b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180006a4b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800068ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800068ac`

## pseudocode

```c
__int64 __fastcall CProfileNotificationHandler::OnDelete(
        CProfileNotificationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  CProfileNotificationHandler *v4; // rcx
  unsigned int v5; // edi
  PWSTR ppszPath; // [rsp+40h] [rbp-38h] BYREF
  PSID Sid; // [rsp+48h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-20h] BYREF
  LPVOID v11; // [rsp+60h] [rbp-18h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    pv = 0;
    if ( (int)SHTranslateSIDToName(Sid, &pv) >= 0 )
    {
      SHDeleteDataFileForUser(pv);
      CoTaskMemFree(pv);
    }
    if ( a2 && *a2 )
      CProfileNotificationHandler::_DeleteUserTiles(v4, a2);
    LODWORD(ppszPath) = 0;
    CSIsUserInAdministratorGroup(Sid);
    DeleteSystemDataFolderForUser(Sid);
    DeleteSystemDataRegistryKeyForUser(Sid);
    LocalFree(Sid);
  }
  else
  {
    GetLastError();
  }
  ppv = 0;
  if ( CoCreateInstance(&CLSID_HomeGroupCollection, 0, 1u, &GUID_c042fb2f_bc74_4636_95b1_2bbe308f7391, &ppv) >= 0 )
  {
    LODWORD(ppszPath) = 0;
    if ( (*(int (__fastcall **)(LPVOID, PWSTR *))(*(_QWORD *)ppv + 24LL))(ppv, &ppszPath) >= 0 && (_DWORD)ppszPath )
    {
      v5 = 0;
      do
      {
        pv = 0;
        if ( (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, LPVOID *))(*(_QWORD *)ppv + 32LL))(
               ppv,
               v5,
               &GUID_9642ab2b_2198_4234_8f68_c3f55e5e9247,
               &pv) >= 0 )
        {
          if ( CoSetProxyBlanket((IUnknown *)pv, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) >= 0 )
            (*(void (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *))(*(_QWORD *)pv + 40LL))(pv, 0, a2);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        }
        ++v5;
      }
      while ( v5 < (unsigned int)ppszPath );
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  v11 = 0;
  if ( CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v11) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v11 + 176LL))(v11, a2);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180006890  push    rbp
0x180006892  push    rbx
0x180006893  push    rsi
0x180006894  push    rdi
0x180006895  mov     rbp, rsp
0x180006898  sub     rsp, 78h
0x18000689c  mov     rbx, rdx
0x18000689f  xor     esi, esi
0x1800068a1  mov     rcx, rbx; StringSid
0x1800068a4  mov     [rbp+Sid], rsi
0x1800068a8  lea     rdx, [rbp+Sid]; Sid
0x1800068ac  call    cs:__imp_ConvertStringSidToSidW
0x1800068b2  test    eax, eax
0x1800068b4  jz      loc_1800069A1
0x1800068ba  mov     rcx, [rbp+Sid]
0x1800068be  lea     rdx, [rbp+pv]
0x1800068c2  mov     [rbp+pv], rsi
0x1800068c6  call    SHTranslateSIDToName
0x1800068cb  test    eax, eax
0x1800068cd  js      short loc_1800068E2
0x1800068cf  mov     rcx, [rbp+pv]
0x1800068d3  call    SHDeleteDataFileForUser
0x1800068d8  mov     rcx, [rbp+pv]; pv
0x1800068dc  call    cs:__imp_CoTaskMemFree
0x1800068e2  test    rbx, rbx
0x1800068e5  jz      short loc_1800068F4
0x1800068e7  cmp     [rbx], si
0x1800068ea  jz      short loc_1800068F4
0x1800068ec  mov     rdx, rbx; unsigned __int16 *
0x1800068ef  call    ?_DeleteUserTiles@CProfileNotificationHandler@@AEAAJPEBG@Z; CProfileNotificationHandler::_DeleteUserTiles(ushort const *)
0x1800068f4  mov     rcx, [rbp+Sid]; pSid2
0x1800068f8  lea     rdx, [rbp+ppszPath]
0x1800068fc  mov     dword ptr [rbp+ppszPath], esi
0x1800068ff  call    CSIsUserInAdministratorGroup
0x180006904  test    eax, eax
0x180006906  js      short loc_180006983
0x180006908  cmp     dword ptr [rbp+ppszPath], esi
0x18000690b  jz      short loc_180006983
0x18000690d  lea     r9, [rbp+pv]; ppszPath
0x180006911  mov     [rbp+pv], rsi
0x180006915  xor     r8d, r8d; hToken
0x180006918  lea     rcx, FOLDERID_PublicDesktop; rfid
0x18000691f  xor     edx, edx; dwFlags
0x180006921  call    cs:__imp_SHGetKnownFolderPath
0x180006927  test    eax, eax
0x180006929  js      short loc_180006948
0x18000692b  mov     rdx, [rbp+Sid]; void *
0x18000692f  mov     r8d, 1; int
0x180006935  mov     rcx, [rbp+pv]; pObjectName
0x180006939  call    ?AddRemoveDeleteAceOnFolder@@YAJPEBGPEAXH@Z; AddRemoveDeleteAceOnFolder(ushort const *,void *,int)
0x18000693e  mov     rcx, [rbp+pv]; pv
0x180006942  call    cs:__imp_CoTaskMemFree
0x180006948  lea     r9, [rbp+ppszPath]; ppszPath
0x18000694c  mov     [rbp+ppszPath], rsi
0x180006950  xor     r8d, r8d; hToken
0x180006953  lea     rcx, FOLDERID_CommonStartMenu; rfid
0x18000695a  xor     edx, edx; dwFlags
0x18000695c  call    cs:__imp_SHGetKnownFolderPath
0x180006962  test    eax, eax
0x180006964  js      short loc_180006983
0x180006966  mov     rdx, [rbp+Sid]; void *
0x18000696a  mov     r8d, 1; int
0x180006970  mov     rcx, [rbp+ppszPath]; pObjectName
0x180006974  call    ?AddRemoveDeleteAceOnFolder@@YAJPEBGPEAXH@Z; AddRemoveDeleteAceOnFolder(ushort const *,void *,int)
0x180006979  mov     rcx, [rbp+ppszPath]; pv
0x18000697d  call    cs:__imp_CoTaskMemFree
0x180006983  mov     rcx, [rbp+Sid]
0x180006987  call    ?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z; DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)
0x18000698c  mov     rcx, [rbp+Sid]; void *
0x180006990  call    ?DeleteSystemDataRegistryKeyForUser@@YAJPEAX@Z; DeleteSystemDataRegistryKeyForUser(void *)
0x180006995  mov     rcx, [rbp+Sid]; hMem
0x180006999  call    cs:__imp_LocalFree
0x18000699f  jmp     short loc_1800069A7
0x1800069a1  call    cs:__imp_GetLastError
0x1800069a7  xor     edx, edx; pUnkOuter
0x1800069a9  mov     [rbp+var_20], rsi
0x1800069ad  lea     rax, [rbp+var_20]
0x1800069b1  lea     r9, _GUID_c042fb2f_bc74_4636_95b1_2bbe308f7391; riid
0x1800069b8  mov     [rsp+78h+ppv], rax; ppv
0x1800069bd  lea     rcx, CLSID_HomeGroupCollection; rclsid
0x1800069c4  lea     r8d, [rdx+1]; dwClsContext
0x1800069c8  call    cs:__imp_CoCreateInstance
0x1800069ce  test    eax, eax
0x1800069d0  js      loc_180006A91
0x1800069d6  mov     rcx, [rbp+var_20]
0x1800069da  lea     rdx, [rbp+ppszPath]
0x1800069de  mov     dword ptr [rbp+ppszPath], esi
0x1800069e1  mov     rax, [rcx]
0x1800069e4  mov     rax, [rax+18h]
0x1800069e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ed  test    eax, eax
0x1800069ef  js      loc_180006A81
0x1800069f5  mov     eax, dword ptr [rbp+ppszPath]
0x1800069f8  test    eax, eax
0x1800069fa  jz      loc_180006A81
0x180006a00  mov     edi, esi
0x180006a02  mov     rcx, [rbp+var_20]
0x180006a06  lea     r9, [rbp+pv]
0x180006a0a  mov     [rbp+pv], rsi
0x180006a0e  lea     r8, _GUID_9642ab2b_2198_4234_8f68_c3f55e5e9247
0x180006a15  mov     edx, edi
0x180006a17  mov     rax, [rcx]
0x180006a1a  mov     rax, [rax+20h]
0x180006a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a23  test    eax, eax
0x180006a25  js      short loc_180006A7A
0x180006a27  mov     rcx, [rbp+pv]; pProxy
0x180006a2b  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180006a2f  mov     [rsp+78h+dwCapabilities], esi; dwCapabilities
0x180006a33  or      edx, r8d; dwAuthnSvc
0x180006a36  mov     [rsp+78h+pAuthInfo], rsi; pAuthInfo
0x180006a3b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180006a3f  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x180006a47  mov     dword ptr [rsp+78h+ppv], esi; dwAuthnLevel
0x180006a4b  call    cs:__imp_CoSetProxyBlanket
0x180006a51  test    eax, eax
0x180006a53  js      short loc_180006A6A
0x180006a55  mov     rcx, [rbp+pv]
0x180006a59  mov     r8, rbx
0x180006a5c  xor     edx, edx
0x180006a5e  mov     rax, [rcx]
0x180006a61  mov     rax, [rax+28h]
0x180006a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6a  mov     rcx, [rbp+pv]
0x180006a6e  mov     rax, [rcx]
0x180006a71  mov     rax, [rax+10h]
0x180006a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7a  inc     edi
0x180006a7c  cmp     edi, dword ptr [rbp+ppszPath]
0x180006a7f  jb      short loc_180006A02
0x180006a81  mov     rcx, [rbp+var_20]
0x180006a85  mov     rax, [rcx]
0x180006a88  mov     rax, [rax+10h]
0x180006a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a91  xor     edx, edx; pUnkOuter
0x180006a93  mov     [rbp+var_18], rsi
0x180006a97  lea     rax, [rbp+var_18]
0x180006a9b  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180006aa2  mov     [rsp+78h+ppv], rax; ppv
0x180006aa7  lea     rcx, CLSID_SyncRootManager; rclsid
0x180006aae  lea     r8d, [rdx+1]; dwClsContext
0x180006ab2  call    cs:__imp_CoCreateInstance
0x180006ab8  test    eax, eax
0x180006aba  js      short loc_180006AE2
0x180006abc  mov     rcx, [rbp+var_18]
0x180006ac0  mov     rdx, rbx
0x180006ac3  mov     rax, [rcx]
0x180006ac6  mov     rax, [rax+0B0h]
0x180006acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad2  mov     rcx, [rbp+var_18]
0x180006ad6  mov     rax, [rcx]
0x180006ad9  mov     rax, [rax+10h]
0x180006add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae2  xor     eax, eax
0x180006ae4  add     rsp, 78h
0x180006ae8  pop     rdi
0x180006ae9  pop     rsi
0x180006aea  pop     rbx
0x180006aeb  pop     rbp
0x180006aec  retn
```
