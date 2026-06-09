# IsPackageHostedByCaller(Windows::System::IUser *,HSTRING__ *)

- ea: `0x180066144`
- end: `0x180066557`
- name: `?IsPackageHostedByCaller@@YA_NPEAUIUser@System@Windows@@PEAUHSTRING__@@@Z`
- size: `1043`
- prototype: `char __fastcall(struct Windows::System::IUser *, HSTRING)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180076130`
- `0x180076520`

## callees

- `0x18000b1fc`
- `0x18000f194`
- `0x180010c04`
- `0x180034d10`
- `0x18003a700`
- `0x18003d318`
- `0x180066144`
- `0x180066560`
- `0x180066628`
- `0x1800666cc`
- `0x180066864`
- `0x180066b04`
- `0x18007c6a4`
- `0x18007e23c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180066187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180066187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800664c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180066537`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800664c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180066537`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800664a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066512`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800664a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066512`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006626d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006626d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800664af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800664af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066521`

## string_xrefs

- `0x1800661c5`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18006620d`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066251`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066290`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800662bb`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800662f6`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18006635c`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066421`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800664d2`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800664e7`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800661a4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1800663a8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall IsPackageHostedByCaller(struct Windows::System::IUser *a1, HSTRING a2)
{
  int v4; // ebx
  __int64 StateRepoUserFromSystemUser; // rdi
  unsigned __int16 **v6; // rdx
  int CallingProcessPackageFullName; // eax
  void *v8; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 *v19; // rcx
  __int64 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int128 v40; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  __int128 v47; // [rsp+F0h] [rbp-10h]
  int v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  __int64 v50; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  char v52; // [rsp+150h] [rbp+50h] BYREF
  char v53; // [rsp+158h] [rbp+58h] BYREF

  v27 = 0;
  v28 = &v27;
  v29 = 0;
  LOBYTE(v30) = 1;
  v4 = SRCacheManager_Open(0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v28);
  if ( v4 >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v4,
      v26);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v4,
      v26);
  StateRepoUserFromSystemUser = GetStateRepoUserFromSystemUser(
                                  (struct StateRepository::Cache::Manager_NoThrow *)&v27,
                                  a1);
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  CallingProcessPackageFullName = UserAwareCallerIdentity::GetCallingProcessPackageFullName(
                                    (UserAwareCallerIdentity *)&pv,
                                    v6);
  if ( CallingProcessPackageFullName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      v26);
  v32 = 0;
  v8 = pv;
  StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
    (struct StateRepository::Cache::Manager_NoThrow *)&v27,
    (const unsigned __int16 *)pv,
    &v32);
  if ( !v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      v26);
  v36 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v10 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v27,
          StringRawBuffer,
          &v36);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v10,
      v26);
  if ( !v36 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      v26);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v11 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
          (struct StateRepository::Cache::Manager_NoThrow *)&v27,
          v36,
          (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v33);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v11,
      v26);
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v53 = 0;
  v12 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v33, 0, &v40, &v53);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v12,
      v26);
  while ( v53 )
  {
    v28 = 0;
    LODWORD(v29) = 0;
    v30 = 0;
    v13 = StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(
            &v28,
            &v27,
            StateRepoUserFromSystemUser,
            v40);
    if ( v13 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
        (const char *)(unsigned int)v13,
        v26);
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v52 = 0;
    v15 = StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::Get(&v28, v14, &v37, &v52);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v15,
        v26);
    while ( v52 )
    {
      if ( v32 == *((_QWORD *)&v38 + 1) )
      {
        v20 = v28;
        v28 = 0;
        if ( v20 )
          SRCacheContext_Close();
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v40);
        v21 = v33;
        v33 = 0;
        if ( v21 )
          SRCacheContext_Close();
        if ( v8 )
          CoTaskMemFree(v8);
        v22 = v27;
        v27 = 0;
        if ( v22 )
          SRCacheManager_Close();
        return 1;
      }
      LODWORD(v29) = v29 + 1;
      v17 = StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::Get(&v28, v16, &v37, &v52);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v17,
          v26);
    }
    ++v34;
    v18 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v33, 0, &v40, &v53);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v18,
        v26);
    v19 = v28;
    v28 = 0;
    if ( v19 )
      SRCacheContext_Close();
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v40);
  v24 = v33;
  v33 = 0;
  if ( v24 )
    SRCacheContext_Close();
  if ( v8 )
    CoTaskMemFree(v8);
  v25 = v27;
  v27 = 0;
  if ( v25 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x180066144  mov     [rsp-8+arg_0], rbx
0x180066149  mov     [rsp-8+arg_8], rsi
0x18006614e  push    rbp
0x18006614f  push    rdi
0x180066150  push    r14
0x180066152  lea     rbp, [rsp-20h]
0x180066157  sub     rsp, 120h
0x18006615e  mov     rsi, rdx
0x180066161  mov     rdi, rcx
0x180066164  xor     r14d, r14d
0x180066167  mov     [rsp+130h+var_100], r14
0x18006616c  lea     rax, [rsp+130h+var_100]
0x180066171  mov     [rsp+130h+var_F8], rax
0x180066176  mov     [rsp+130h+var_F0], r14
0x18006617b  mov     byte ptr [rsp+130h+var_E8], 1
0x180066180  lea     rdx, [rsp+130h+var_F0]
0x180066185  xor     ecx, ecx
0x180066187  call    cs:__imp_SRCacheManager_Open
0x18006618d  mov     ebx, eax
0x18006618f  lea     rcx, [rsp+130h+var_F8]
0x180066194  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180066199  test    ebx, ebx
0x18006619b  jns     short loc_1800661B7
0x18006619d  mov     rcx, [rbp+38h]; this
0x1800661a1  mov     r9d, ebx; char *
0x1800661a4  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800661ab  mov     edx, 0A5h; void *
0x1800661b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800661b5  jmp     short loc_1800661BA
0x1800661b7  mov     ebx, r14d
0x1800661ba  mov     rcx, [rbp+38h]; this
0x1800661be  test    ebx, ebx
0x1800661c0  jns     short loc_1800661D7
0x1800661c2  mov     r9d, ebx; char *
0x1800661c5  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800661cc  mov     edx, 18Bh; void *
0x1800661d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800661d7  mov     rdx, rdi; struct Windows::System::IUser *
0x1800661da  lea     rcx, [rsp+130h+var_100]; struct StateRepository::Cache::Manager_NoThrow *
0x1800661df  call    ?GetStateRepoUserFromSystemUser@@YA_JAEAVManager_NoThrow@Cache@StateRepository@@PEAUIUser@System@Windows@@@Z; GetStateRepoUserFromSystemUser(StateRepository::Cache::Manager_NoThrow &,Windows::System::IUser *)
0x1800661e4  mov     rdi, rax
0x1800661e7  mov     [rsp+130h+pv], r14
0x1800661ec  xor     edx, edx
0x1800661ee  lea     rcx, [rsp+130h+pv]
0x1800661f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800661f8  lea     rcx, [rsp+130h+pv]; this
0x1800661fd  call    ?GetCallingProcessPackageFullName@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x180066202  mov     rcx, [rbp+38h]; this
0x180066206  test    eax, eax
0x180066208  jns     short loc_18006621F
0x18006620a  mov     r9d, eax; char *
0x18006620d  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066214  mov     edx, 192h; void *
0x180066219  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006621f  mov     [rsp+130h+var_D8], r14
0x180066224  lea     r8, [rsp+130h+var_D8]; __int64 *
0x180066229  mov     rbx, [rsp+130h+pv]
0x18006622e  mov     rdx, rbx; unsigned __int16 *
0x180066231  lea     rcx, [rsp+130h+var_100]; struct StateRepository::Cache::Manager_NoThrow *
0x180066236  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18006623b  cmp     [rsp+130h+var_D8], r14
0x180066240  setz    al
0x180066243  mov     rcx, [rbp+38h]; this
0x180066247  test    al, al
0x180066249  jz      short loc_180066263
0x18006624b  mov     r9d, 8000FFFFh; char *
0x180066251  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066258  mov     edx, 196h; void *
0x18006625d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066263  mov     [rsp+130h+var_B8], r14
0x180066268  xor     edx, edx; length
0x18006626a  mov     rcx, rsi; string
0x18006626d  call    cs:__imp_WindowsGetStringRawBuffer
0x180066273  mov     rdx, rax; unsigned __int16 *
0x180066276  lea     r8, [rsp+130h+var_B8]; __int64 *
0x18006627b  lea     rcx, [rsp+130h+var_100]; struct StateRepository::Cache::Manager_NoThrow *
0x180066280  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180066285  mov     rcx, [rbp+38h]; this
0x180066289  test    eax, eax
0x18006628b  jns     short loc_1800662A2
0x18006628d  mov     r9d, eax; char *
0x180066290  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066297  mov     edx, 199h; void *
0x18006629c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800662a2  mov     rdx, [rsp+130h+var_B8]; __int64
0x1800662a7  test    rdx, rdx
0x1800662aa  setz    al
0x1800662ad  mov     rcx, [rbp+38h]; this
0x1800662b1  test    al, al
0x1800662b3  jz      short loc_1800662CD
0x1800662b5  mov     r9d, 8000FFFFh; char *
0x1800662bb  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800662c2  mov     edx, 19Ah; void *
0x1800662c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800662cd  mov     [rsp+130h+var_D0], r14
0x1800662d2  mov     [rsp+130h+var_C8], r14d
0x1800662d7  mov     [rsp+130h+var_C0], r14
0x1800662dc  lea     r8, [rsp+130h+var_D0]; this
0x1800662e1  lea     rcx, [rsp+130h+var_100]; struct StateRepository::Cache::Manager_NoThrow *
0x1800662e6  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x1800662eb  mov     rcx, [rbp+38h]; this
0x1800662ef  test    eax, eax
0x1800662f1  jns     short loc_180066308
0x1800662f3  mov     r9d, eax; char *
0x1800662f6  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800662fd  mov     edx, 19Dh; void *
0x180066302  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066308  xorps   xmm0, xmm0
0x18006630b  movdqa  [rbp+30h+var_80], xmm0
0x180066310  mov     [rbp+30h+var_70], r14
0x180066314  mov     [rbp+30h+var_68], r14
0x180066318  mov     [rbp+30h+var_60], r14
0x18006631c  mov     [rbp+30h+var_58], r14
0x180066320  mov     [rbp+30h+var_50], r14
0x180066324  mov     [rbp+30h+var_48], r14
0x180066328  movdqa  [rbp+30h+var_40], xmm0
0x18006632d  mov     [rbp+30h+var_30], r14d
0x180066331  mov     [rbp+30h+var_28], r14
0x180066335  mov     [rbp+30h+var_20], r14
0x180066339  mov     [rbp+30h+arg_18], r14b
0x18006633d  lea     r9, [rbp+30h+arg_18]
0x180066341  lea     r8, [rbp+30h+var_80]
0x180066345  xor     edx, edx
0x180066347  lea     rcx, [rsp+130h+var_D0]
0x18006634c  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180066351  mov     rcx, [rbp+38h]; this
0x180066355  test    eax, eax
0x180066357  jns     short loc_18006636E
0x180066359  mov     r9d, eax; char *
0x18006635c  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066363  mov     edx, 1A2h; void *
0x180066368  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006636e  cmp     [rbp+30h+arg_18], r14b
0x180066372  jz      loc_1800664F9
0x180066378  mov     [rsp+130h+var_F8], r14
0x18006637d  mov     dword ptr [rsp+130h+var_F0], r14d
0x180066382  mov     [rsp+130h+var_E8], r14
0x180066387  mov     r9, qword ptr [rbp+30h+var_80]
0x18006638b  mov     r8, rdi
0x18006638e  lea     rdx, [rsp+130h+var_100]
0x180066393  lea     rcx, [rsp+130h+var_F8]
0x180066398  call    ?OpenByUserAndDependentPackageAndDependencyType@DependencyGraphIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J1W4DependencyGraphType@34@@Z; StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::DependencyGraphType)
0x18006639d  test    eax, eax
0x18006639f  jns     short loc_1800663B9
0x1800663a1  mov     rcx, [rbp+38h]; this
0x1800663a5  mov     r9d, eax; char *
0x1800663a8  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800663af  mov     edx, 24Ah; void *
0x1800663b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800663b9  xorps   xmm0, xmm0
0x1800663bc  movdqu  [rbp+30h+var_B0], xmm0
0x1800663c1  xorps   xmm1, xmm1
0x1800663c4  movdqu  [rbp+30h+var_A0], xmm1
0x1800663c9  mov     [rbp+30h+var_90], r14
0x1800663cd  mov     [rbp+30h+arg_10], r14b
0x1800663d1  lea     r9, [rbp+30h+arg_10]
0x1800663d5  lea     r8, [rbp+30h+var_B0]
0x1800663d9  lea     rcx, [rsp+130h+var_F8]
0x1800663de  call    ?Get@DependencyGraphIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DependencyGraph_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::DependencyGraph_NoThrow::CacheFlags,StateRepository::Cache::Entity::DependencyGraph_NoThrow &,bool &)
0x1800663e3  mov     rcx, [rbp+38h]; this
0x1800663e7  test    eax, eax
0x1800663e9  js      loc_1800664E4
0x1800663ef  cmp     [rbp+30h+arg_10], r14b
0x1800663f3  jz      short loc_180066433
0x1800663f5  mov     rax, qword ptr [rbp+30h+var_A0+8]
0x1800663f9  cmp     [rsp+130h+var_D8], rax
0x1800663fe  jz      short loc_180066471
0x180066400  inc     dword ptr [rsp+130h+var_F0]
0x180066404  lea     r9, [rbp+30h+arg_10]
0x180066408  lea     r8, [rbp+30h+var_B0]
0x18006640c  lea     rcx, [rsp+130h+var_F8]
0x180066411  call    ?Get@DependencyGraphIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DependencyGraph_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::DependencyGraph_NoThrow::CacheFlags,StateRepository::Cache::Entity::DependencyGraph_NoThrow &,bool &)
0x180066416  mov     rcx, [rbp+38h]; this
0x18006641a  test    eax, eax
0x18006641c  jns     short loc_1800663EF
0x18006641e  mov     r9d, eax; char *
0x180066421  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066428  mov     edx, 1B6h; void *
0x18006642d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066433  inc     [rsp+130h+var_C8]
0x180066437  lea     r9, [rbp+30h+arg_18]
0x18006643b  lea     r8, [rbp+30h+var_80]
0x18006643f  xor     edx, edx
0x180066441  lea     rcx, [rsp+130h+var_D0]
0x180066446  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18006644b  mov     rcx, [rbp+38h]; this
0x18006644f  test    eax, eax
0x180066451  js      short loc_1800664CF
0x180066453  mov     rcx, [rsp+130h+var_F8]
0x180066458  mov     [rsp+130h+var_F8], r14
0x18006645d  test    rcx, rcx
0x180066460  jz      loc_18006636E
0x180066466  call    cs:__imp_SRCacheContext_Close
0x18006646c  jmp     loc_18006636E
0x180066471  mov     rcx, [rsp+130h+var_F8]
0x180066476  mov     [rsp+130h+var_F8], r14
0x18006647b  test    rcx, rcx
0x18006647e  jz      short loc_180066487
0x180066480  call    cs:__imp_SRCacheContext_Close
0x180066486  nop
0x180066487  lea     rcx, [rbp+30h+var_80]; this
0x18006648b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180066490  nop
0x180066491  mov     rcx, [rsp+130h+var_D0]
0x180066496  mov     [rsp+130h+var_D0], r14
0x18006649b  test    rcx, rcx
0x18006649e  jz      short loc_1800664A7
0x1800664a0  call    cs:__imp_SRCacheContext_Close
0x1800664a6  nop
0x1800664a7  test    rbx, rbx
0x1800664aa  jz      short loc_1800664B6
0x1800664ac  mov     rcx, rbx; pv
0x1800664af  call    cs:__imp_CoTaskMemFree
0x1800664b5  nop
0x1800664b6  mov     rcx, [rsp+130h+var_100]
0x1800664bb  mov     [rsp+130h+var_100], r14
0x1800664c0  test    rcx, rcx
0x1800664c3  jz      short loc_1800664CB
0x1800664c5  call    cs:__imp_SRCacheManager_Close
0x1800664cb  mov     al, 1
0x1800664cd  jmp     short loc_18006653F
0x1800664cf  mov     r9d, eax; char *
0x1800664d2  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800664d9  mov     edx, 1B9h; void *
0x1800664de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800664e4  mov     r9d, eax; char *
0x1800664e7  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800664ee  mov     edx, 1ABh; void *
0x1800664f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800664f9  lea     rcx, [rbp+30h+var_80]; this
0x1800664fd  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180066502  nop
0x180066503  mov     rcx, [rsp+130h+var_D0]
0x180066508  mov     [rsp+130h+var_D0], r14
0x18006650d  test    rcx, rcx
0x180066510  jz      short loc_180066519
0x180066512  call    cs:__imp_SRCacheContext_Close
0x180066518  nop
0x180066519  test    rbx, rbx
0x18006651c  jz      short loc_180066528
0x18006651e  mov     rcx, rbx; pv
0x180066521  call    cs:__imp_CoTaskMemFree
0x180066527  nop
0x180066528  mov     rcx, [rsp+130h+var_100]
0x18006652d  mov     [rsp+130h+var_100], r14
0x180066532  test    rcx, rcx
0x180066535  jz      short loc_18006653D
0x180066537  call    cs:__imp_SRCacheManager_Close
0x18006653d  xor     al, al
0x18006653f  lea     r11, [rsp+130h+var_10]
0x180066547  mov     rbx, [r11+20h]
0x18006654b  mov     rsi, [r11+28h]
0x18006654f  mov     rsp, r11
0x180066552  pop     r14
0x180066554  pop     rdi
0x180066555  pop     rbp
0x180066556  retn
```
