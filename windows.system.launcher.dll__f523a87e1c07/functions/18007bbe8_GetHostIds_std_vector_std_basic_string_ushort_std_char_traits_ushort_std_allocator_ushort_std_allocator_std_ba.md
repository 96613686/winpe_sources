# GetHostIds(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18007bbe8`
- end: `0x18007bf2f`
- name: `?GetHostIds@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `839`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070600`

## callees

- `0x18000f194`
- `0x180010c04`
- `0x180034d10`
- `0x18003a700`
- `0x18003d318`
- `0x18003d454`
- `0x18004a844`
- `0x18004acdc`
- `0x18007bbe8`
- `0x18007bf38`
- `0x18007c000`
- `0x18007c0c8`
- `0x18007c6a4`
- `0x1800856c8`
- `0x1800867cc`
- `0x18008a030`
- `0x1800d5074`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007bc64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007bc64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007be82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007be82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007bed8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007bed8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007be98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007bec2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007be98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007bec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bee7`

## string_xrefs

- `0x18007bc32`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bca1`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bd4e`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bdcf`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bf08`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bf1d`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007bc81`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18007bd8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18007bcf9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
void __fastcall GetHostIds(__int64 a1)
{
  unsigned __int16 **v2; // rdx
  int CallingProcessPackageFullName; // eax
  int v4; // ebx
  void *v5; // rbx
  const unsigned __int16 *v6; // r9
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int128 v36; // [rsp+B0h] [rbp-50h]
  __int128 v37; // [rsp+C0h] [rbp-40h]
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  CallingProcessPackageFullName = UserAwareCallerIdentity::GetCallingProcessPackageFullName(
                                    (UserAwareCallerIdentity *)&pv,
                                    v2);
  if ( CallingProcessPackageFullName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      v21);
  v22 = 0;
  *(_QWORD *)&v24 = &v22;
  *((_QWORD *)&v24 + 1) = 0;
  LOBYTE(v25) = 1;
  v4 = SRCacheManager_Open(0, (char *)&v24 + 8);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v24);
  if ( v4 >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v4,
      v21);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v4,
      v21);
  v32 = 0;
  v5 = pv;
  StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
    (struct StateRepository::Cache::Manager_NoThrow *)&v22,
    (const unsigned __int16 *)pv,
    &v32);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v7 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(
         (StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *)&v29,
         (struct StateRepository::Cache::Manager_NoThrow *)&v22,
         v32,
         v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x391,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v7,
      v21);
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  BYTE1(v21) = 0;
  v9 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(&v29, v8, v33, (char *)&v21 + 1);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v9,
      v21);
  while ( BYTE1(v21) )
  {
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v10 = StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::OpenByPackageExtension(
            (StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow *)&v26,
            (struct StateRepository::Cache::Manager_NoThrow *)&v22,
            v33[0]);
    if ( v10 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27E,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
        (const char *)(unsigned int)v10,
        v21);
    v24 = 0;
    v25 = 0;
    LOBYTE(v21) = 0;
    v12 = StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::Get(&v26, v11, &v24, &v21);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v12,
        v21);
    while ( (_BYTE)v21 )
    {
      std::wstring::wstring(v38);
      if ( *(_QWORD *)(a1 + 8) == *(_QWORD *)(a1 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, *(_QWORD *)(a1 + 8), v38);
      }
      else
      {
        std::wstring::wstring(*(_QWORD *)(a1 + 8), v38);
        *(_QWORD *)(a1 + 8) += 32LL;
      }
      ++v27;
      v15 = StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::Get(&v26, v14, &v24, &v21);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v15,
          v21);
      std::wstring::_Tidy_deallocate(v38);
    }
    ++v30;
    v16 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(&v29, v13, v33, (char *)&v21 + 1);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v16,
        v21);
    v17 = v25;
    v25 = 0;
    if ( v17 )
      SRCache_Free();
    v18 = v26;
    v26 = 0;
    if ( v18 )
      SRCacheContext_Close();
  }
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v33);
  v19 = v29;
  v29 = 0;
  if ( v19 )
    SRCacheContext_Close();
  v20 = v22;
  v22 = 0;
  if ( v20 )
    SRCacheManager_Close();
  if ( v5 )
    CoTaskMemFree(v5);
}

```

## disassembly

```asm
0x18007bbe8  push    rbp
0x18007bbea  push    rbx
0x18007bbeb  push    rsi
0x18007bbec  push    rdi
0x18007bbed  lea     rbp, [rsp-8]
0x18007bbf2  sub     rsp, 108h
0x18007bbf9  mov     rax, cs:__security_cookie
0x18007bc00  xor     rax, rsp
0x18007bc03  mov     [rbp+20h+var_30], rax
0x18007bc07  mov     rdi, rcx
0x18007bc0a  xor     esi, esi
0x18007bc0c  mov     [rsp+120h+pv], rsi
0x18007bc11  xor     edx, edx
0x18007bc13  lea     rcx, [rsp+120h+pv]
0x18007bc18  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007bc1d  lea     rcx, [rsp+120h+pv]; this
0x18007bc22  call    ?GetCallingProcessPackageFullName@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18007bc27  mov     rcx, [rbp+28h]; this
0x18007bc2b  test    eax, eax
0x18007bc2d  jns     short loc_18007BC44
0x18007bc2f  mov     r9d, eax; char *
0x18007bc32  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bc39  mov     edx, 164h; void *
0x18007bc3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007bc44  mov     [rsp+120h+var_F8], rsi
0x18007bc49  lea     rax, [rsp+120h+var_F8]
0x18007bc4e  mov     qword ptr [rsp+120h+var_E8], rax
0x18007bc53  mov     qword ptr [rsp+120h+var_E8+8], rsi
0x18007bc58  mov     byte ptr [rsp+120h+var_D8], 1
0x18007bc5d  lea     rdx, [rsp+120h+var_E8+8]
0x18007bc62  xor     ecx, ecx
0x18007bc64  call    cs:__imp_SRCacheManager_Open
0x18007bc6a  mov     ebx, eax
0x18007bc6c  lea     rcx, [rsp+120h+var_E8]
0x18007bc71  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18007bc76  test    ebx, ebx
0x18007bc78  jns     short loc_18007BC94
0x18007bc7a  mov     rcx, [rbp+28h]; this
0x18007bc7e  mov     r9d, ebx; char *
0x18007bc81  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007bc88  mov     edx, 0A5h; void *
0x18007bc8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bc92  jmp     short loc_18007BC96
0x18007bc94  mov     ebx, esi
0x18007bc96  mov     rcx, [rbp+28h]; this
0x18007bc9a  test    ebx, ebx
0x18007bc9c  jns     short loc_18007BCB3
0x18007bc9e  mov     r9d, ebx; char *
0x18007bca1  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bca8  mov     edx, 167h; void *
0x18007bcad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007bcb3  mov     [rbp+20h+var_A0], rsi
0x18007bcb7  lea     r8, [rbp+20h+var_A0]; __int64 *
0x18007bcbb  mov     rbx, [rsp+120h+pv]
0x18007bcc0  mov     rdx, rbx; unsigned __int16 *
0x18007bcc3  lea     rcx, [rsp+120h+var_F8]; struct StateRepository::Cache::Manager_NoThrow *
0x18007bcc8  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18007bccd  mov     [rsp+120h+var_B8], rsi
0x18007bcd2  mov     [rsp+120h+var_B0], esi
0x18007bcd6  mov     [rsp+120h+var_A8], rsi
0x18007bcdb  mov     r8, [rbp+20h+var_A0]; __int64
0x18007bcdf  lea     rdx, [rsp+120h+var_F8]; struct StateRepository::Cache::Manager_NoThrow *
0x18007bce4  lea     rcx, [rsp+120h+var_B8]; this
0x18007bce9  call    ?OpenByPackageAndCategory@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18007bcee  test    eax, eax
0x18007bcf0  jns     short loc_18007BD0A
0x18007bcf2  mov     rcx, [rbp+28h]; this
0x18007bcf6  mov     r9d, eax; char *
0x18007bcf9  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007bd00  mov     edx, 391h; void *
0x18007bd05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bd0a  xorps   xmm0, xmm0
0x18007bd0d  movdqa  xmmword ptr [rbp+20h+var_90], xmm0
0x18007bd12  mov     [rbp+20h+var_80], rsi
0x18007bd16  mov     [rbp+20h+var_78], rsi
0x18007bd1a  movdqa  [rbp+20h+var_70], xmm0
0x18007bd1f  xorps   xmm1, xmm1
0x18007bd22  movdqa  [rbp+20h+var_60], xmm1
0x18007bd27  mov     byte ptr [rsp+120h+var_100+1], sil
0x18007bd2c  lea     r9, [rsp+120h+var_100+1]
0x18007bd31  lea     r8, [rbp+20h+var_90]
0x18007bd35  lea     rcx, [rsp+120h+var_B8]
0x18007bd3a  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18007bd3f  mov     rcx, [rbp+28h]; this
0x18007bd43  test    eax, eax
0x18007bd45  jns     loc_18007BE9E
0x18007bd4b  mov     r9d, eax; char *
0x18007bd4e  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bd55  mov     edx, 172h; void *
0x18007bd5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007bd60  mov     [rsp+120h+var_D0], rsi
0x18007bd65  mov     [rsp+120h+var_C8], esi
0x18007bd69  mov     [rsp+120h+var_C0], rsi
0x18007bd6e  mov     r8, [rbp+20h+var_90]; __int64
0x18007bd72  lea     rdx, [rsp+120h+var_F8]; struct StateRepository::Cache::Manager_NoThrow *
0x18007bd77  lea     rcx, [rsp+120h+var_D0]; this
0x18007bd7c  call    ?OpenByPackageExtension@HostRuntimeIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::OpenByPackageExtension(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18007bd81  test    eax, eax
0x18007bd83  jns     short loc_18007BD9D
0x18007bd85  mov     rcx, [rbp+28h]; this
0x18007bd89  mov     r9d, eax; char *
0x18007bd8c  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007bd93  mov     edx, 27Eh; void *
0x18007bd98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bd9d  xorps   xmm0, xmm0
0x18007bda0  movdqu  [rsp+120h+var_E8], xmm0
0x18007bda6  mov     [rsp+120h+var_D8], rsi
0x18007bdab  mov     byte ptr [rsp+120h+var_100], sil; int
0x18007bdb0  lea     r9, [rsp+120h+var_100]
0x18007bdb5  lea     r8, [rsp+120h+var_E8]
0x18007bdba  lea     rcx, [rsp+120h+var_D0]
0x18007bdbf  call    ?Get@HostRuntimeIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@HostRuntime_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::HostRuntime_NoThrow::CacheFlags,StateRepository::Cache::Entity::HostRuntime_NoThrow &,bool &)
0x18007bdc4  mov     rcx, [rbp+28h]; this
0x18007bdc8  test    eax, eax
0x18007bdca  jns     short loc_18007BE49
0x18007bdcc  mov     r9d, eax; char *
0x18007bdcf  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bdd6  mov     edx, 17Bh; void *
0x18007bddb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007bde1  mov     rdx, [rsp+120h+var_D8]
0x18007bde6  lea     rcx, [rbp+20h+var_50]
0x18007bdea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007bdef  nop
0x18007bdf0  mov     rax, [rdi+8]
0x18007bdf4  cmp     rax, [rdi+10h]
0x18007bdf8  jz      short loc_18007BE0D
0x18007bdfa  lea     rdx, [rbp+20h+var_50]
0x18007bdfe  mov     rcx, rax
0x18007be01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007be06  add     qword ptr [rdi+8], 20h ; ' '
0x18007be0b  jmp     short loc_18007BE1C
0x18007be0d  lea     r8, [rbp+20h+var_50]
0x18007be11  mov     rdx, rax
0x18007be14  mov     rcx, rdi
0x18007be17  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18007be1c  inc     [rsp+120h+var_C8]
0x18007be20  lea     r9, [rsp+120h+var_100]
0x18007be25  lea     r8, [rsp+120h+var_E8]
0x18007be2a  lea     rcx, [rsp+120h+var_D0]
0x18007be2f  call    ?Get@HostRuntimeIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@HostRuntime_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::HostRuntime_NoThrow::CacheFlags,StateRepository::Cache::Entity::HostRuntime_NoThrow &,bool &)
0x18007be34  mov     rcx, [rbp+28h]; this
0x18007be38  test    eax, eax
0x18007be3a  js      loc_18007BF05
0x18007be40  lea     rcx, [rbp+20h+var_50]
0x18007be44  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007be49  cmp     byte ptr [rsp+120h+var_100], sil
0x18007be4e  jnz     short loc_18007BDE1
0x18007be50  inc     [rsp+120h+var_B0]
0x18007be54  lea     r9, [rsp+120h+var_100+1]
0x18007be59  lea     r8, [rbp+20h+var_90]
0x18007be5d  lea     rcx, [rsp+120h+var_B8]
0x18007be62  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18007be67  mov     rcx, [rbp+28h]; this
0x18007be6b  test    eax, eax
0x18007be6d  js      loc_18007BF1A
0x18007be73  mov     rcx, [rsp+120h+var_D8]
0x18007be78  mov     [rsp+120h+var_D8], rsi
0x18007be7d  test    rcx, rcx
0x18007be80  jz      short loc_18007BE89
0x18007be82  call    cs:__imp_SRCache_Free
0x18007be88  nop
0x18007be89  mov     rcx, [rsp+120h+var_D0]
0x18007be8e  mov     [rsp+120h+var_D0], rsi
0x18007be93  test    rcx, rcx
0x18007be96  jz      short loc_18007BE9E
0x18007be98  call    cs:__imp_SRCacheContext_Close
0x18007be9e  cmp     byte ptr [rsp+120h+var_100+1], sil
0x18007bea3  jnz     loc_18007BD60
0x18007bea9  lea     rcx, [rbp+20h+var_90]; this
0x18007bead  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18007beb2  nop
0x18007beb3  mov     rcx, [rsp+120h+var_B8]
0x18007beb8  mov     [rsp+120h+var_B8], rsi
0x18007bebd  test    rcx, rcx
0x18007bec0  jz      short loc_18007BEC9
0x18007bec2  call    cs:__imp_SRCacheContext_Close
0x18007bec8  nop
0x18007bec9  mov     rcx, [rsp+120h+var_F8]
0x18007bece  mov     [rsp+120h+var_F8], rsi
0x18007bed3  test    rcx, rcx
0x18007bed6  jz      short loc_18007BEDF
0x18007bed8  call    cs:__imp_SRCacheManager_Close
0x18007bede  nop
0x18007bedf  test    rbx, rbx
0x18007bee2  jz      short loc_18007BEED
0x18007bee4  mov     rcx, rbx; pv
0x18007bee7  call    cs:__imp_CoTaskMemFree
0x18007beed  mov     rcx, [rbp+20h+var_30]
0x18007bef1  xor     rcx, rsp; StackCookie
0x18007bef4  call    __security_check_cookie
0x18007bef9  add     rsp, 108h
0x18007bf00  pop     rdi
0x18007bf01  pop     rsi
0x18007bf02  pop     rbx
0x18007bf03  pop     rbp
0x18007bf04  retn
0x18007bf05  mov     r9d, eax; char *
0x18007bf08  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bf0f  mov     edx, 181h; void *
0x18007bf14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007bf1a  mov     r9d, eax; char *
0x18007bf1d  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007bf24  mov     edx, 184h; void *
0x18007bf29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
