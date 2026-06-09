# PermissionsUI::AddPermissionsProvider(PermissionsProvider *)

- ea: `0x18038a874`
- end: `0x18038ab97`
- name: `?AddPermissionsProvider@PermissionsUI@@QEAAJPEAVPermissionsProvider@@@Z`
- size: `803`
- prototype: `__int64 __fastcall(PermissionsUI *__hidden this, struct PermissionsProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18038b7b8`

## callees

- `0x180008a74`
- `0x18000b7e8`
- `0x1801078a8`
- `0x18035a340`
- `0x18038a740`
- `0x18038a874`
- `0x18038aba0`
- `0x18038b290`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18038a982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18038a9c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18038a982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18038a9c8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18038ab65`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18038ab65`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18038a8cd`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18038a964`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18038a8cd`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18038a964`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18038ab77`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18038ab77`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18038ab2a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18038ab2a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038a8b6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038a954`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038aa2c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038a8b6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038a954`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18038aa2c`
- `DUI70!StrToID` at `0x18038a8aa`
- `DUI70!StrToID` at `0x18038a947`
- `DUI70!StrToID` at `0x18038aa1f`
- `DUI70!StrToID` at `0x18038a8aa`
- `DUI70!StrToID` at `0x18038a947`
- `DUI70!StrToID` at `0x18038aa1f`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18038a901`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18038a901`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18038ab4d`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18038ab4d`

## pseudocode

```c
__int64 __fastcall PermissionsUI::AddPermissionsProvider(PermissionsUI *this, struct PermissionsProvider *a2)
{
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  struct DirectUI::Element *v7; // r15
  DirectUI::DUIXmlParser *ParserForThread; // rax
  int v9; // ebx
  HINSTANCE v10; // r9
  HINSTANCE v11; // r9
  const unsigned __int16 *v12; // r8
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *v16; // rcx
  int v17; // eax
  DWORD v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int16 v21; // ax
  struct DirectUI::Element *v22; // r12
  unsigned int v23; // r14d
  void *v24; // rdi
  __int64 (__fastcall *v25)(void *, _QWORD, _QWORD *); // rbx
  __int64 v26; // rdi
  struct ISettingsProvider *v27; // r13
  int (__fastcall *v28)(__int64, GUID *, struct ISetting **); // rbx
  PermissionsUI *v29; // rcx
  int v30; // eax
  struct DirectUI::Element *v31; // [rsp+30h] [rbp-28h] BYREF
  void *v32; // [rsp+38h] [rbp-20h] BYREF
  struct ISettingsProvider *v33; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v34[2]; // [rsp+48h] [rbp-10h] BYREF
  LPOLESTR lpsz; // [rsp+A8h] [rbp+50h] BYREF
  struct ISetting *v37; // [rsp+B0h] [rbp+58h] BYREF
  int v38; // [rsp+B8h] [rbp+60h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = StrToID(L"ePermissionsSection");
  Descendent = DirectUI::Element::FindDescendent(this, v5);
  v7 = Descendent;
  if ( Descendent )
  {
    DirectUI::Element::SetVisible(Descendent, 1);
    v31 = 0;
    ParserForThread = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_PermissionsDUIResourceManager);
    v9 = DirectUI::DUIXmlParser::CreateElement(ParserForThread, L"permission", 0, v7, 0, &v31);
    if ( v9 >= 0 )
    {
      DUI_SetDescendentElementTextAndAccName(v31, L"ePermissionTitle", *((const unsigned __int16 **)a2 + 5), v10);
      v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
      if ( v12 )
      {
        DUI_SetDescendentElementTextAndAccName(v31, L"ePermissionDescription", v12, v11);
      }
      else
      {
        v13 = StrToID(L"ePermissionDescription");
        v14 = DirectUI::Element::FindDescendent(v31, v13);
        if ( v14 )
          DirectUI::Element::SetVisible(v14, 0);
      }
      v33 = 0;
      v32 = 0;
      LODWORD(lpsz) = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      v33 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *(const unsigned __int16 **)a2;
      if ( *((_DWORD *)a2 + 4) == CurrentThreadId )
        v17 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct ISettingsProvider **))v16 + 1))(
                *((_QWORD *)v16 + 1),
                &GUID_5fc0f146_1b06_44ca_a568_283acd690e00,
                &v33);
      else
        v17 = AgileGitPtr::CopyLocal(
                (AgileGitPtr *)(v16 + 8),
                &GUID_5fc0f146_1b06_44ca_a568_283acd690e00,
                (void **)&v33);
      v9 = v17;
      if ( v17 >= 0 )
      {
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v32 = 0;
        v18 = GetCurrentThreadId();
        v19 = *((_QWORD *)a2 + 1);
        v20 = *((_DWORD *)a2 + 4) == v18
            ? (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(v19 + 8))(
                *(_QWORD *)(v19 + 8),
                &GUID_62948522_8857_4c63_9b85_8fff20128f6a,
                &v32)
            : AgileGitPtr::CopyLocal((AgileGitPtr *)(v19 + 16), &GUID_62948522_8857_4c63_9b85_8fff20128f6a, &v32);
        v9 = v20;
        if ( v20 >= 0 )
          v9 = (*(__int64 (__fastcall **)(void *, LPOLESTR *))(*(_QWORD *)v32 + 32LL))(v32, &lpsz);
      }
      v21 = StrToID(L"ePermissionSettingsSection");
      v22 = DirectUI::Element::FindDescendent(v31, v21);
      v23 = 0;
      while ( v9 >= 0 )
      {
        if ( v23 >= (unsigned int)lpsz )
          goto LABEL_31;
        v34[0] = 0;
        v24 = v32;
        v25 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD *))(*(_QWORD *)v32 + 40LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v34);
        v9 = v25(v24, v23, v34);
        if ( v9 >= 0 )
        {
          v26 = v34[0];
          v27 = v33;
          v37 = 0;
          v28 = **(int (__fastcall ***)(__int64, GUID *, struct ISetting **))v34[0];
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
          v30 = v28(v26, &GUID_18d72473_cd4a_411d_a73e_6b212cec6ca8, &v37) < 0
              ? PermissionsUI::AddLabelSettingToPermissions(v29, v37, v22)
              : PermissionsUI::AddToggleSettingToPermissions(v29, v37, v27, v22);
          v9 = v30;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
          if ( v9 >= 0 )
          {
            v38 = 0;
            LODWORD(v37) = 0;
            if ( (*(int (__fastcall **)(_QWORD, int *, struct ISetting **))(*(_QWORD *)v34[0] + 56LL))(
                   v34[0],
                   &v38,
                   &v37) >= 0 )
            {
              if ( (_DWORD)v37 )
                PermissionsUI::ShowGroupPolicyMessage(this);
            }
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v34);
        ++v23;
      }
      DirectUI::Element::Destroy(v31, 0);
LABEL_31:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      if ( v9 >= 0 )
      {
        v9 = DirectUI::Element::Add(v7, v31);
        if ( v9 >= 0 )
        {
          lpsz = 0;
          if ( StringFromCLSID((const IID *const)((char *)a2 + 20), &lpsz) >= 0 )
            DirectUI::Element::SetID(v31, lpsz);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18038a874  mov     [rsp-40h+arg_0], rcx
0x18038a879  push    rbp
0x18038a87a  push    rbx
0x18038a87b  push    rsi
0x18038a87c  push    rdi
0x18038a87d  push    r12
0x18038a87f  push    r13
0x18038a881  push    r14
0x18038a883  push    r15
0x18038a885  mov     rbp, rsp
0x18038a888  sub     rsp, 58h
0x18038a88c  xor     edi, edi
0x18038a88e  mov     rsi, rdx
0x18038a891  mov     rbx, rcx
0x18038a894  test    rdx, rdx
0x18038a897  jnz     short loc_18038A8A3
0x18038a899  mov     eax, 80070057h
0x18038a89e  jmp     loc_18038AB86
0x18038a8a3  lea     rcx, aEpermissionsse; "ePermissionsSection"
0x18038a8aa  call    cs:__imp_StrToID
0x18038a8b0  movzx   edx, ax
0x18038a8b3  mov     rcx, rbx
0x18038a8b6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18038a8bc  mov     r15, rax
0x18038a8bf  test    rax, rax
0x18038a8c2  jz      loc_18038AB7F
0x18038a8c8  mov     dl, 1
0x18038a8ca  mov     rcx, rax
0x18038a8cd  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18038a8d3  lea     rcx, ?g_PermissionsDUIResourceManager@@3VCDUIResourceManager@@A; this
0x18038a8da  mov     [rbp+var_28], rdi
0x18038a8de  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x18038a8e3  lea     rcx, [rbp+var_28]
0x18038a8e7  mov     r9, r15
0x18038a8ea  mov     [rsp+58h+var_30], rcx
0x18038a8ef  lea     rdx, aPermission; "permission"
0x18038a8f6  mov     rcx, rax
0x18038a8f9  mov     [rsp+58h+var_38], rdi
0x18038a8fe  xor     r8d, r8d
0x18038a901  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18038a907  mov     ebx, eax
0x18038a909  test    eax, eax
0x18038a90b  js      loc_18038AB84
0x18038a911  mov     r8, [rsi+28h]; unsigned __int16 *
0x18038a915  lea     rdx, aEpermissiontit; "ePermissionTitle"
0x18038a91c  mov     rcx, [rbp+var_28]; struct DirectUI::Element *
0x18038a920  call    ?DUI_SetDescendentElementTextAndAccName@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementTextAndAccName(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x18038a925  mov     r8, [rsi+30h]; unsigned __int16 *
0x18038a929  test    r8, r8
0x18038a92c  jz      short loc_18038A940
0x18038a92e  mov     rcx, [rbp+var_28]; struct DirectUI::Element *
0x18038a932  lea     rdx, aEpermissiondes; "ePermissionDescription"
0x18038a939  call    ?DUI_SetDescendentElementTextAndAccName@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementTextAndAccName(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x18038a93e  jmp     short loc_18038A96A
0x18038a940  lea     rcx, aEpermissiondes; "ePermissionDescription"
0x18038a947  call    cs:__imp_StrToID
0x18038a94d  mov     rcx, [rbp+var_28]
0x18038a951  movzx   edx, ax
0x18038a954  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18038a95a  test    rax, rax
0x18038a95d  jz      short loc_18038A96A
0x18038a95f  xor     edx, edx
0x18038a961  mov     rcx, rax
0x18038a964  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18038a96a  lea     rcx, [rbp+var_18]
0x18038a96e  mov     [rbp+var_18], rdi
0x18038a972  mov     [rbp+var_20], rdi
0x18038a976  mov     dword ptr [rbp+lpsz], edi
0x18038a979  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038a97e  mov     [rbp+var_18], rdi
0x18038a982  call    cs:__imp_GetCurrentThreadId
0x18038a988  mov     rcx, [rsi]
0x18038a98b  lea     r8, [rbp+var_18]; void **
0x18038a98f  lea     rdx, _GUID_5fc0f146_1b06_44ca_a568_283acd690e00; struct _GUID *
0x18038a996  cmp     [rsi+10h], eax
0x18038a999  jnz     short loc_18038A9AC
0x18038a99b  mov     rcx, [rcx+8]
0x18038a99f  mov     rax, [rcx]
0x18038a9a2  mov     rax, [rax]
0x18038a9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038a9aa  jmp     short loc_18038A9B5
0x18038a9ac  add     rcx, 10h; this
0x18038a9b0  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18038a9b5  mov     ebx, eax
0x18038a9b7  test    eax, eax
0x18038a9b9  js      short loc_18038AA18
0x18038a9bb  lea     rcx, [rbp+var_20]
0x18038a9bf  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038a9c4  mov     [rbp+var_20], rdi
0x18038a9c8  call    cs:__imp_GetCurrentThreadId
0x18038a9ce  mov     rcx, [rsi+8]
0x18038a9d2  lea     r8, [rbp+var_20]; void **
0x18038a9d6  lea     rdx, _GUID_62948522_8857_4c63_9b85_8fff20128f6a; struct _GUID *
0x18038a9dd  cmp     [rsi+10h], eax
0x18038a9e0  jnz     short loc_18038A9F3
0x18038a9e2  mov     rcx, [rcx+8]
0x18038a9e6  mov     rax, [rcx]
0x18038a9e9  mov     rax, [rax]
0x18038a9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038a9f1  jmp     short loc_18038A9FC
0x18038a9f3  add     rcx, 10h; this
0x18038a9f7  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18038a9fc  mov     ebx, eax
0x18038a9fe  test    eax, eax
0x18038aa00  js      short loc_18038AA18
0x18038aa02  mov     rcx, [rbp+var_20]
0x18038aa06  lea     rdx, [rbp+lpsz]
0x18038aa0a  mov     rax, [rcx]
0x18038aa0d  mov     rax, [rax+20h]
0x18038aa11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038aa16  mov     ebx, eax
0x18038aa18  lea     rcx, aEpermissionset; "ePermissionSettingsSection"
0x18038aa1f  call    cs:__imp_StrToID
0x18038aa25  mov     rcx, [rbp+var_28]
0x18038aa29  movzx   edx, ax
0x18038aa2c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18038aa32  mov     r12, rax
0x18038aa35  mov     r14d, edi
0x18038aa38  jmp     loc_18038AB1C
0x18038aa3d  cmp     r14d, dword ptr [rbp+lpsz]
0x18038aa41  jnb     loc_18038AB30
0x18038aa47  mov     [rbp+var_10], rdi
0x18038aa4b  lea     rcx, [rbp+var_10]
0x18038aa4f  mov     rdi, [rbp+var_20]
0x18038aa53  mov     rdx, [rdi]
0x18038aa56  mov     rbx, [rdx+28h]
0x18038aa5a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038aa5f  lea     r8, [rbp+var_10]
0x18038aa63  mov     edx, r14d
0x18038aa66  mov     rcx, rdi
0x18038aa69  mov     rax, rbx
0x18038aa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038aa71  xor     edi, edi
0x18038aa73  mov     ebx, eax
0x18038aa75  test    eax, eax
0x18038aa77  js      loc_18038AB10
0x18038aa7d  mov     rdi, [rbp+var_10]
0x18038aa81  lea     rcx, [rbp+arg_10]
0x18038aa85  mov     r13, [rbp+var_18]
0x18038aa89  mov     [rbp+arg_10], 0
0x18038aa91  mov     rax, [rdi]
0x18038aa94  mov     rbx, [rax]
0x18038aa97  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038aa9c  lea     r8, [rbp+arg_10]
0x18038aaa0  mov     rcx, rdi
0x18038aaa3  lea     rdx, _GUID_18d72473_cd4a_411d_a73e_6b212cec6ca8
0x18038aaaa  mov     rax, rbx
0x18038aaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038aab2  mov     rdx, [rbp+arg_10]; struct ISetting *
0x18038aab6  xor     edi, edi
0x18038aab8  test    eax, eax
0x18038aaba  js      short loc_18038AAC9
0x18038aabc  mov     r9, r12; struct DirectUI::Element *
0x18038aabf  mov     r8, r13; struct ISettingsProvider *
0x18038aac2  call    ?AddToggleSettingToPermissions@PermissionsUI@@AEAAJPEAUIBooleanSetting@@PEAUISettingsProvider@@PEAVElement@DirectUI@@@Z; PermissionsUI::AddToggleSettingToPermissions(IBooleanSetting *,ISettingsProvider *,DirectUI::Element *)
0x18038aac7  jmp     short loc_18038AAD1
0x18038aac9  mov     r8, r12; struct DirectUI::Element *
0x18038aacc  call    ?AddLabelSettingToPermissions@PermissionsUI@@AEAAJPEAUISetting@@PEAVElement@DirectUI@@@Z; PermissionsUI::AddLabelSettingToPermissions(ISetting *,DirectUI::Element *)
0x18038aad1  lea     rcx, [rbp+arg_10]
0x18038aad5  mov     ebx, eax
0x18038aad7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038aadc  test    ebx, ebx
0x18038aade  js      short loc_18038AB10
0x18038aae0  mov     rcx, [rbp+var_10]
0x18038aae4  lea     r8, [rbp+arg_10]
0x18038aae8  mov     [rbp+arg_18], edi
0x18038aaeb  lea     rdx, [rbp+arg_18]
0x18038aaef  mov     dword ptr [rbp+arg_10], edi
0x18038aaf2  mov     rax, [rcx]
0x18038aaf5  mov     rax, [rax+38h]
0x18038aaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038aafe  test    eax, eax
0x18038ab00  js      short loc_18038AB10
0x18038ab02  cmp     dword ptr [rbp+arg_10], edi
0x18038ab05  jz      short loc_18038AB10
0x18038ab07  mov     rcx, [rbp+arg_0]; this
0x18038ab0b  call    ?ShowGroupPolicyMessage@PermissionsUI@@QEAAJXZ; PermissionsUI::ShowGroupPolicyMessage(void)
0x18038ab10  lea     rcx, [rbp+var_10]
0x18038ab14  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038ab19  inc     r14d
0x18038ab1c  test    ebx, ebx
0x18038ab1e  jns     loc_18038AA3D
0x18038ab24  mov     rcx, [rbp+var_28]
0x18038ab28  xor     edx, edx
0x18038ab2a  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18038ab30  lea     rcx, [rbp+var_20]
0x18038ab34  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038ab39  lea     rcx, [rbp+var_18]
0x18038ab3d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18038ab42  test    ebx, ebx
0x18038ab44  js      short loc_18038AB84
0x18038ab46  mov     rdx, [rbp+var_28]
0x18038ab4a  mov     rcx, r15
0x18038ab4d  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18038ab53  mov     ebx, eax
0x18038ab55  test    eax, eax
0x18038ab57  js      short loc_18038AB84
0x18038ab59  lea     rcx, [rsi+14h]; rclsid
0x18038ab5d  mov     [rbp+lpsz], rdi
0x18038ab61  lea     rdx, [rbp+lpsz]; lplpsz
0x18038ab65  call    cs:__imp_StringFromCLSID
0x18038ab6b  test    eax, eax
0x18038ab6d  js      short loc_18038AB84
0x18038ab6f  mov     rdx, [rbp+lpsz]
0x18038ab73  mov     rcx, [rbp+var_28]
0x18038ab77  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18038ab7d  jmp     short loc_18038AB84
0x18038ab7f  mov     ebx, 80004005h
0x18038ab84  mov     eax, ebx
0x18038ab86  add     rsp, 58h
0x18038ab8a  pop     r15
0x18038ab8c  pop     r14
0x18038ab8e  pop     r13
0x18038ab90  pop     r12
0x18038ab92  pop     rdi
0x18038ab93  pop     rsi
0x18038ab94  pop     rbx
0x18038ab95  pop     rbp
0x18038ab96  retn
```
