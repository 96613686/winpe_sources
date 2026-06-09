# CBrokeredLauncher::CLaunchHelper::IsVirtualizedLaunch(ushort const *)

- ea: `0x18007b600`
- end: `0x18007b73d`
- name: `?IsVirtualizedLaunch@CLaunchHelper@CBrokeredLauncher@@AEAA_NPEBG@Z`
- size: `317`
- prototype: `bool(CBrokeredLauncher::CLaunchHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180056460`
- `0x1800ec7c0`

## callees

- `0x18000f194`
- `0x180010c04`
- `0x180034d10`
- `0x18007b600`
- `0x18007b744`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007b62c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007b64e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007b62c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007b64e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007b67f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007b67f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007b717`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007b726`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007b717`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007b726`

## string_xrefs

- `0x18007b6be`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007b6ef`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007b69d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall CBrokeredLauncher::CLaunchHelper::IsVirtualizedLaunch(
        CBrokeredLauncher::CLaunchHelper *this,
        const unsigned __int16 *a2)
{
  int v3; // ebx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  __int64 v6; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  __int64 *v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h] BYREF
  char v11; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CBrokeredLauncher::CLaunchHelper *v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v13 = this;
  if ( CompareStringOrdinal(a2, -1, L".exe", -1, 1) != 2 && CompareStringOrdinal(a2, -1, L".msi", -1, 1) != 2 )
    return 0;
  v14 = 0;
  v9 = &v14;
  v10 = 0;
  v11 = 1;
  v3 = SRCacheManager_Open(0, &v10);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v9);
  if ( v3 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x884,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  LOBYTE(v13) = 0;
  v5 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ExistsByPackageFamilyName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v14,
         v4,
         (bool *)&v13);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x888,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  v6 = v14;
  v14 = 0;
  if ( !(_BYTE)v13 )
  {
    if ( v6 )
      SRCacheManager_Close(v6);
    return 0;
  }
  if ( v6 )
    SRCacheManager_Close(v6);
  return 1;
}

```

## disassembly

```asm
0x18007b600  mov     [rsp+arg_8], rbx
0x18007b605  mov     [rsp+arg_0], rcx
0x18007b60a  push    rdi
0x18007b60b  sub     rsp, 50h
0x18007b60f  mov     rbx, rdx
0x18007b612  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18007b61a  or      edi, 0FFFFFFFFh
0x18007b61d  mov     r9d, edi; cchCount2
0x18007b620  lea     r8, aExe; ".exe"
0x18007b627  mov     edx, edi; cchCount1
0x18007b629  mov     rcx, rbx; lpString1
0x18007b62c  call    cs:__imp_CompareStringOrdinal
0x18007b632  cmp     eax, 2
0x18007b635  jz      short loc_18007B65D
0x18007b637  mov     [rsp+58h+bIgnoreCase], 1; int
0x18007b63f  mov     r9d, edi; cchCount2
0x18007b642  lea     r8, aMsi; ".msi"
0x18007b649  mov     edx, edi; cchCount1
0x18007b64b  mov     rcx, rbx; lpString1
0x18007b64e  call    cs:__imp_CompareStringOrdinal
0x18007b654  cmp     eax, 2
0x18007b657  jnz     loc_18007B72D
0x18007b65d  xor     edi, edi
0x18007b65f  mov     [rsp+58h+arg_10], rdi
0x18007b664  lea     rax, [rsp+58h+arg_10]
0x18007b669  mov     [rsp+58h+var_28], rax
0x18007b66e  mov     [rsp+58h+var_20], rdi
0x18007b673  mov     [rsp+58h+var_18], 1
0x18007b678  lea     rdx, [rsp+58h+var_20]
0x18007b67d  xor     ecx, ecx
0x18007b67f  call    cs:__imp_SRCacheManager_Open
0x18007b685  mov     ebx, eax
0x18007b687  lea     rcx, [rsp+58h+var_28]
0x18007b68c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18007b691  test    ebx, ebx
0x18007b693  jns     short loc_18007B6B0
0x18007b695  mov     rcx, [rsp+58h]; this
0x18007b69a  mov     r9d, ebx; char *
0x18007b69d  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b6a4  mov     edx, 0A5h; void *
0x18007b6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b6ae  jmp     short loc_18007B6B2
0x18007b6b0  mov     ebx, edi
0x18007b6b2  mov     rcx, [rsp+58h]; this
0x18007b6b7  test    ebx, ebx
0x18007b6b9  jns     short loc_18007B6CF
0x18007b6bb  mov     r9d, ebx; char *
0x18007b6be  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007b6c5  mov     edx, 884h; void *
0x18007b6ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b6cf  mov     byte ptr [rsp+58h+arg_0], dil
0x18007b6d4  lea     r8, [rsp+58h+arg_0]; bool *
0x18007b6d9  lea     rcx, [rsp+58h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x18007b6de  call    ?ExistsByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ExistsByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18007b6e3  mov     rcx, [rsp+58h]; this
0x18007b6e8  test    eax, eax
0x18007b6ea  jns     short loc_18007B701
0x18007b6ec  mov     r9d, eax; char *
0x18007b6ef  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007b6f6  mov     edx, 888h; void *
0x18007b6fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b701  mov     rcx, [rsp+58h+arg_10]
0x18007b706  mov     [rsp+58h+arg_10], rdi
0x18007b70b  cmp     byte ptr [rsp+58h+arg_0], dil
0x18007b710  jz      short loc_18007B721
0x18007b712  test    rcx, rcx
0x18007b715  jz      short loc_18007B71D
0x18007b717  call    cs:__imp_SRCacheManager_Close
0x18007b71d  mov     al, 1
0x18007b71f  jmp     short loc_18007B731
0x18007b721  test    rcx, rcx
0x18007b724  jz      short loc_18007B72D
0x18007b726  call    cs:__imp_SRCacheManager_Close
0x18007b72c  nop
0x18007b72d  jmp     short $+2
0x18007b72f  xor     al, al
0x18007b731  mov     rbx, [rsp+58h+arg_8]
0x18007b736  add     rsp, 50h
0x18007b73a  pop     rdi
0x18007b73b  retn
```
