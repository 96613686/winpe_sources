# CTaskbandPin::RemoveFromList(IShellItem *)

- ea: `0x180677dd0`
- end: `0x180678099`
- name: `?RemoveFromList@CTaskbandPin@@UEAAJPEAUIShellItem@@@Z`
- size: `713`
- prototype: `int(CTaskbandPin *__hidden this, struct IShellItem *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180285b6c`
- `0x1802b26e4`
- `0x180356360`
- `0x180677dd0`
- `0x180680180`
- `0x1806846a0`
- `0x1806857b8`
- `0x1806858e0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677e30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677e8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677ed5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677e30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677e8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180677ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180677f18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180677f18`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180677f56`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180677f56`
- `SHELL32!SHChangeNotify` at `0x18067806a`
- `SHELL32!SHChangeNotify` at `0x18067806a`
- `SHELL32!__imp_ILFree` at `0x180677f86`
- `SHELL32!__imp_ILFree` at `0x180677f86`

## string_xrefs

- `0x18067801d`: `FavoritesRemovedChanges`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTaskbandPin::RemoveFromList(CTaskbandPin *this, IUnknown *a2)
{
  HRESULT v4; // ebx
  CPinnedList *v5; // rcx
  unsigned int v6; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  struct IShellLinkW *v11; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID dwItem1; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h]
  LPVOID v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v15[264]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 1u, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv) >= 0 )
  {
    pv = 0;
    if ( (*(int (__fastcall **)(LPVOID, IUnknown *, LPVOID *))(*(_QWORD *)ppv + 24LL))(ppv, a2, &pv) >= 0 )
    {
      dwItem1 = 0;
      if ( CoCreateInstance(&CLSID_DestinationListBoth, 0, 1u, &GUID_6332debf_87b5_4670_90c0_5e57b408a49e, &dwItem1) >= 0 )
        (*(void (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)dwItem1 + 80LL))(dwItem1, pv);
      v14[0] = 0;
      if ( CoCreateInstance(&CLSID_AutomaticDestinationListBoth, 0, 1u, &GUID_e9c5ef8d_fd41_4f72_ba87_eb03bad5817c, v14) >= 0
        && (*(int (__fastcall **)(LPVOID, LPVOID, _QWORD, _QWORD))(*(_QWORD *)v14[0] + 24LL))(v14[0], pv, 0, 0) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v14[0] + 104LL))(v14[0], 1);
      }
      CoTaskMemFree(pv);
      wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(v14);
      wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(&dwItem1);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  ppidl = 0;
  v4 = SHGetIDListFromObject(a2, &ppidl);
  if ( v4 >= 0 )
  {
    v4 = CPinnedList::MarkAsTombstone((char *)this - 80, ppidl, 25);
    if ( v4 == -2147023728 )
      v4 = 1;
    ILFree(ppidl);
  }
  v11 = 0;
  if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, struct IShellLinkW **))a2->lpVtbl[1].QueryInterface)(
         a2,
         0,
         &BHID_SFUIObject,
         &GUID_000214f9_0000_0000_c000_000000000046,
         &v11) >= 0 )
  {
    if ( CPinnedList::s_GetDarwinLinkInfo(v11, 0, v15, 0x104u) )
    {
      v4 = CPinnedList::s_RemoveDarwinShortcut(
             ((unsigned __int64)this - 88) & -(__int64)(this != (CTaskbandPin *)112),
             v15);
      if ( v4 == -2147023728 )
        v4 = 1;
    }
    ((void (__fastcall *)(struct IShellLinkW *))v11->lpVtbl->Release)(v11);
  }
  v6 = CPinnedList::_GetRemovedGlobalChangeCount(v5);
  if ( (int)SHRegSetDWORD(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartPage",
              L"FavoritesRemovedChanges",
              v6 + 1) >= 0 )
  {
    HIWORD(dwItem1) = 0;
    v13 = 0;
    LOWORD(dwItem1) = 10;
    *(_DWORD *)((char *)&dwItem1 + 2) = 14;
    SHChangeNotify(0x4000000, 0x3000u, &dwItem1, 0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180677dd0  mov     [rsp-8+arg_10], rbx
0x180677dd5  mov     [rsp-8+arg_18], rsi
0x180677dda  push    rbp
0x180677ddb  push    rdi
0x180677ddc  push    r15
0x180677dde  lea     rbp, [rsp-190h]
0x180677de6  sub     rsp, 290h
0x180677ded  mov     rax, cs:__security_cookie
0x180677df4  xor     rax, rsp
0x180677df7  mov     [rbp+1A0h+var_20], rax
0x180677dfe  mov     rdi, rdx
0x180677e01  mov     rsi, rcx
0x180677e04  mov     [rsp+2A0h+var_268], 0
0x180677e0d  lea     rax, [rsp+2A0h+var_268]
0x180677e12  mov     [rsp+2A0h+ppv], rax; ppv
0x180677e17  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180677e1e  mov     r15d, 1
0x180677e24  mov     r8d, r15d; dwClsContext
0x180677e27  xor     edx, edx; pUnkOuter
0x180677e29  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180677e30  call    cs:__imp_CoCreateInstance
0x180677e36  test    eax, eax
0x180677e38  js      loc_180677F45
0x180677e3e  mov     [rsp+2A0h+pv], 0
0x180677e47  mov     rcx, [rsp+2A0h+var_268]
0x180677e4c  mov     rax, [rcx]
0x180677e4f  lea     r8, [rsp+2A0h+pv]
0x180677e54  mov     rdx, rdi
0x180677e57  mov     rax, [rax+18h]
0x180677e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677e60  test    eax, eax
0x180677e62  js      loc_180677F34
0x180677e68  mov     [rsp+2A0h+dwItem1], 0
0x180677e71  lea     rax, [rsp+2A0h+dwItem1]
0x180677e76  mov     [rsp+2A0h+ppv], rax; ppv
0x180677e7b  lea     r9, _GUID_6332debf_87b5_4670_90c0_5e57b408a49e; riid
0x180677e82  mov     r8d, r15d; dwClsContext
0x180677e85  xor     edx, edx; pUnkOuter
0x180677e87  lea     rcx, CLSID_DestinationListBoth; rclsid
0x180677e8e  call    cs:__imp_CoCreateInstance
0x180677e94  test    eax, eax
0x180677e96  js      short loc_180677EAF
0x180677e98  mov     rcx, [rsp+2A0h+dwItem1]
0x180677e9d  mov     rax, [rcx]
0x180677ea0  mov     rdx, [rsp+2A0h+pv]
0x180677ea5  mov     rax, [rax+50h]
0x180677ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677eae  nop
0x180677eaf  mov     [rsp+2A0h+var_240], 0
0x180677eb8  lea     rax, [rsp+2A0h+var_240]
0x180677ebd  mov     [rsp+2A0h+ppv], rax; ppv
0x180677ec2  lea     r9, _GUID_e9c5ef8d_fd41_4f72_ba87_eb03bad5817c; riid
0x180677ec9  mov     r8d, r15d; dwClsContext
0x180677ecc  xor     edx, edx; pUnkOuter
0x180677ece  lea     rcx, CLSID_AutomaticDestinationListBoth; rclsid
0x180677ed5  call    cs:__imp_CoCreateInstance
0x180677edb  test    eax, eax
0x180677edd  js      short loc_180677F13
0x180677edf  mov     rcx, [rsp+2A0h+var_240]
0x180677ee4  mov     rax, [rcx]
0x180677ee7  xor     r9d, r9d
0x180677eea  xor     r8d, r8d
0x180677eed  mov     rdx, [rsp+2A0h+pv]
0x180677ef2  mov     rax, [rax+18h]
0x180677ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677efb  test    eax, eax
0x180677efd  js      short loc_180677F13
0x180677eff  mov     rcx, [rsp+2A0h+var_240]
0x180677f04  mov     rax, [rcx]
0x180677f07  mov     edx, r15d
0x180677f0a  mov     rax, [rax+68h]
0x180677f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677f13  mov     rcx, [rsp+2A0h+pv]; pv
0x180677f18  call    cs:__imp_CoTaskMemFree
0x180677f1e  nop
0x180677f1f  lea     rcx, [rsp+2A0h+var_240]
0x180677f24  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x180677f29  nop
0x180677f2a  lea     rcx, [rsp+2A0h+dwItem1]
0x180677f2f  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x180677f34  mov     rcx, [rsp+2A0h+var_268]
0x180677f39  mov     rax, [rcx]
0x180677f3c  mov     rax, [rax+10h]
0x180677f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677f45  mov     [rsp+2A0h+ppidl], 0
0x180677f4e  lea     rdx, [rsp+2A0h+ppidl]; ppidl
0x180677f53  mov     rcx, rdi; punk
0x180677f56  call    cs:__imp_SHGetIDListFromObject
0x180677f5c  mov     ebx, eax
0x180677f5e  test    eax, eax
0x180677f60  js      short loc_180677F8C
0x180677f62  lea     rcx, [rsi-50h]
0x180677f66  mov     r8d, 19h
0x180677f6c  mov     rdx, [rsp+2A0h+ppidl]
0x180677f71  call    ?MarkAsTombstone@CPinnedList@@UEAAJPEFBU_ITEMIDLIST@@W4PINNEDLISTMODIFYCALLER@@@Z; CPinnedList::MarkAsTombstone(_ITEMIDLIST const *,PINNEDLISTMODIFYCALLER)
0x180677f76  mov     ebx, eax
0x180677f78  cmp     eax, 80070490h
0x180677f7d  cmovz   ebx, r15d
0x180677f81  mov     rcx, [rsp+2A0h+ppidl]; pidl
0x180677f86  call    cs:__imp_ILFree
0x180677f8c  mov     [rsp+2A0h+var_258], 0
0x180677f95  mov     rax, [rdi]
0x180677f98  lea     rcx, [rsp+2A0h+var_258]
0x180677f9d  mov     [rsp+2A0h+ppv], rcx
0x180677fa2  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180677fa9  lea     r8, BHID_SFUIObject
0x180677fb0  xor     edx, edx
0x180677fb2  mov     rcx, rdi
0x180677fb5  mov     rax, [rax+18h]
0x180677fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180677fbe  test    eax, eax
0x180677fc0  js      short loc_180678014
0x180677fc2  mov     r9d, 104h; unsigned int
0x180677fc8  lea     r8, [rsp+2A0h+var_230]; unsigned __int16 *
0x180677fcd  xor     edx, edx; int *
0x180677fcf  mov     rcx, [rsp+2A0h+var_258]; struct IShellLinkW *
0x180677fd4  call    ?s_GetDarwinLinkInfo@CPinnedList@@KAHPEAUIShellLinkW@@PEAHPEAGI@Z; CPinnedList::s_GetDarwinLinkInfo(IShellLinkW *,int *,ushort *,uint)
0x180677fd9  test    eax, eax
0x180677fdb  jz      short loc_180678003
0x180677fdd  lea     rax, [rsi-70h]
0x180677fe1  lea     rdx, [rsi-58h]
0x180677fe5  neg     rax
0x180677fe8  sbb     rcx, rcx
0x180677feb  and     rcx, rdx
0x180677fee  lea     rdx, [rsp+2A0h+var_230]
0x180677ff3  call    ?s_RemoveDarwinShortcut@CPinnedList@@KAJPEAUIPinnedList3@@PEBGW4PINNEDLISTMODIFYCALLER@@@Z; CPinnedList::s_RemoveDarwinShortcut(IPinnedList3 *,ushort const *,PINNEDLISTMODIFYCALLER)
0x180677ff8  mov     ebx, eax
0x180677ffa  cmp     eax, 80070490h
0x180677fff  cmovz   ebx, r15d
0x180678003  mov     rcx, [rsp+2A0h+var_258]
0x180678008  mov     rax, [rcx]
0x18067800b  mov     rax, [rax+10h]
0x18067800f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678014  call    ?_GetRemovedGlobalChangeCount@CPinnedList@@IEAAKXZ; CPinnedList::_GetRemovedGlobalChangeCount(void)
0x180678019  lea     r9d, [r15+rax]; unsigned int
0x18067801d  lea     r8, aFavoritesremov; "FavoritesRemovedChanges"
0x180678024  lea     rdx, aSoftwareMicros_69; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18067802b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180678032  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180678037  test    eax, eax
0x180678039  js      short loc_180678070
0x18067803b  xor     eax, eax
0x18067803d  mov     [rsp+2A0h+dwItem1], rax
0x180678042  mov     [rsp+2A0h+var_248], eax
0x180678046  mov     eax, 0Ah
0x18067804b  mov     word ptr [rsp+2A0h+dwItem1], ax
0x180678050  mov     dword ptr [rsp+2A0h+dwItem1+2], 0Eh
0x180678058  xor     r9d, r9d; dwItem2
0x18067805b  lea     r8, [rsp+2A0h+dwItem1]; dwItem1
0x180678060  mov     edx, 3000h; uFlags
0x180678065  mov     ecx, 4000000h; wEventId
0x18067806a  call    cs:__imp_SHChangeNotify
0x180678070  mov     eax, ebx
0x180678072  mov     rcx, [rbp+1A0h+var_20]
0x180678079  xor     rcx, rsp; StackCookie
0x18067807c  call    __security_check_cookie
0x180678081  lea     r11, [rsp+2A0h+var_10]
0x180678089  mov     rbx, [r11+30h]
0x18067808d  mov     rsi, [r11+38h]
0x180678091  mov     rsp, r11
0x180678094  pop     r15
0x180678096  pop     rdi
0x180678097  pop     rbp
0x180678098  retn
```
