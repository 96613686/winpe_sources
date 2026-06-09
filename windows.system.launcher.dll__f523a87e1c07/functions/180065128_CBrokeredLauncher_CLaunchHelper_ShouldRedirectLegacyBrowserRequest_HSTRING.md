# CBrokeredLauncher::CLaunchHelper::ShouldRedirectLegacyBrowserRequest(HSTRING__ *)

- ea: `0x180065128`
- end: `0x18006528e`
- name: `?ShouldRedirectLegacyBrowserRequest@CLaunchHelper@CBrokeredLauncher@@AEAA_NPEAUHSTRING__@@@Z`
- size: `358`
- prototype: `bool(CBrokeredLauncher::CLaunchHelper *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005886c`

## callees

- `0x18000f194`
- `0x180010c04`
- `0x180034d10`
- `0x180058dc4`
- `0x180065128`
- `0x180066864`
- `0x180066b4c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006515b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006515b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006519d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006519d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180065279`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180065279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006513c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006513c`

## string_xrefs

- `0x1800651d9`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180065212`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180065249`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800651b9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CBrokeredLauncher::CLaunchHelper::ShouldRedirectLegacyBrowserRequest(
        CBrokeredLauncher::CLaunchHelper *this,
        HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  char v3; // di
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  __int64 *v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  CBrokeredLauncher::CLaunchHelper *v14; // [rsp+70h] [rbp+20h] BYREF
  __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  __int64 v16; // [rsp+88h] [rbp+38h] BYREF

  v14 = this;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v3 = 1;
  if ( CompareStringOrdinal(L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe", -1, StringRawBuffer, -1, 1) != 2 )
    return 0;
  if ( !IsBrowserReplacementFeaturePresent() )
  {
    v15 = 0;
    v10 = &v15;
    v11 = 0;
    v12 = 1;
    v5 = SRCacheManager_Open(0, &v11);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v10);
    if ( v5 >= 0 )
      v5 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA32,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
    v16 = 0;
    v6 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
           (struct StateRepository::Cache::Manager_NoThrow *)&v15,
           L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe",
           &v16);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA36,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
    LOBYTE(v14) = 0;
    if ( v16 )
    {
      v7 = StateRepository::Cache::Entity::Package_NoThrow::ExistsByPackageFamily(
             (struct StateRepository::Cache::Manager_NoThrow *)&v15,
             v16,
             (bool *)&v14);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA3B,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
      if ( (_BYTE)v14 )
        v3 = 0;
    }
    v8 = v15;
    v15 = 0;
    if ( v8 )
      SRCacheManager_Close(v8);
  }
  return v3;
}

```

## disassembly

```asm
0x180065128  mov     [rsp-18h+arg_0], rcx
0x18006512d  push    rbp
0x18006512e  push    rbx
0x18006512f  push    rdi
0x180065130  mov     rbp, rsp
0x180065133  sub     rsp, 50h
0x180065137  mov     rcx, rdx; string
0x18006513a  xor     edx, edx; length
0x18006513c  call    cs:__imp_WindowsGetStringRawBuffer
0x180065142  mov     r8, rax; lpString2
0x180065145  mov     edi, 1
0x18006514a  mov     [rsp+50h+bIgnoreCase], edi; int
0x18006514e  or      edx, 0FFFFFFFFh; cchCount1
0x180065151  mov     r9d, edx; cchCount2
0x180065154  lea     rcx, aMicrosoftMicro; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x18006515b  call    cs:__imp_CompareStringOrdinal
0x180065161  cmp     eax, 2
0x180065164  jnz     loc_180065284
0x18006516a  call    ?IsBrowserReplacementFeaturePresent@@YA_NXZ; IsBrowserReplacementFeaturePresent(void)
0x18006516f  test    al, al
0x180065171  jz      short loc_18006517B
0x180065173  mov     al, dil
0x180065176  jmp     loc_180065286
0x18006517b  mov     [rbp+arg_10], 0
0x180065183  lea     rax, [rbp+arg_10]
0x180065187  mov     [rbp+var_20], rax
0x18006518b  mov     [rbp+var_18], 0
0x180065193  mov     [rbp+var_10], dil
0x180065197  lea     rdx, [rbp+var_18]
0x18006519b  xor     ecx, ecx
0x18006519d  call    cs:__imp_SRCacheManager_Open
0x1800651a3  mov     ebx, eax
0x1800651a5  lea     rcx, [rbp+var_20]
0x1800651a9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800651ae  test    ebx, ebx
0x1800651b0  jns     short loc_1800651CC
0x1800651b2  mov     rcx, [rbp+18h]; this
0x1800651b6  mov     r9d, ebx; char *
0x1800651b9  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800651c0  mov     edx, 0A5h; void *
0x1800651c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800651ca  jmp     short loc_1800651CE
0x1800651cc  xor     ebx, ebx
0x1800651ce  mov     rcx, [rbp+18h]; this
0x1800651d2  test    ebx, ebx
0x1800651d4  jns     short loc_1800651EB
0x1800651d6  mov     r9d, ebx; char *
0x1800651d9  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800651e0  mov     edx, 0A32h; void *
0x1800651e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651eb  mov     [rbp+arg_18], 0
0x1800651f3  lea     r8, [rbp+arg_18]; __int64 *
0x1800651f7  lea     rdx, aMicrosoftMicro; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x1800651fe  lea     rcx, [rbp+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180065202  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180065207  mov     rcx, [rbp+18h]; this
0x18006520b  test    eax, eax
0x18006520d  jns     short loc_180065224
0x18006520f  mov     r9d, eax; char *
0x180065212  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180065219  mov     edx, 0A36h; void *
0x18006521e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065224  mov     byte ptr [rbp+arg_0], 0
0x180065228  mov     rdx, [rbp+arg_18]; __int64
0x18006522c  test    rdx, rdx
0x18006522f  jz      short loc_180065264
0x180065231  lea     r8, [rbp+arg_0]; bool *
0x180065235  lea     rcx, [rbp+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180065239  call    ?ExistsByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::ExistsByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,bool &)
0x18006523e  mov     rcx, [rbp+18h]; this
0x180065242  test    eax, eax
0x180065244  jns     short loc_18006525B
0x180065246  mov     r9d, eax; char *
0x180065249  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180065250  mov     edx, 0A3Bh; void *
0x180065255  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006525b  cmp     byte ptr [rbp+arg_0], 0
0x18006525f  jz      short loc_180065264
0x180065261  xor     dil, dil
0x180065264  mov     rcx, [rbp+arg_10]
0x180065268  mov     [rbp+arg_10], 0
0x180065270  test    rcx, rcx
0x180065273  jz      loc_180065173
0x180065279  call    cs:__imp_SRCacheManager_Close
0x18006527f  jmp     loc_180065173
0x180065284  xor     al, al
0x180065286  add     rsp, 50h
0x18006528a  pop     rdi
0x18006528b  pop     rbx
0x18006528c  pop     rbp
0x18006528d  retn
```
