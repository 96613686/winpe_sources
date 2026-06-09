# GetPackageProperties(ushort const *,bool &,bool &,bool &,bool &,bool &)

- ea: `0x180087818`
- end: `0x180087ca3`
- name: `?GetPackageProperties@@YAJPEBGAEA_N1111@Z`
- size: `1163`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, bool *@<rdx>, bool *@<r8>, bool *@<r9>, bool *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e578`

## callees

- `0x18000e074`
- `0x18000e0a0`
- `0x18000eccc`
- `0x18000edf0`
- `0x18000f0b4`
- `0x18000f14c`
- `0x18000f7f4`
- `0x1800210f8`
- `0x180087818`
- `0x180093f20`
- `0x1800a0a8c`
- `0x1800a3d1c`
- `0x1800a7b84`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800ba888`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180087be0`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180087be0`
- `ntdll!RtlInitUnicodeString` at `0x180087ba7`
- `ntdll!RtlInitUnicodeString` at `0x180087ba7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180087c2a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180087c2a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800878ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800878ca`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180087b47`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180087b47`

## string_xrefs

- `0x1800878f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180087950`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180087989`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180087a6e`: `onecore\com\combase\catalog\services.cxx`
- `0x180087b72`: `onecore\com\combase\catalog\services.cxx`
- `0x180087bf7`: `onecore\com\combase\catalog\services.cxx`
- `0x180087b98`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall GetPackageProperties(const unsigned __int16 *a1, bool *a2, bool *a3, bool *a4, bool *a5, bool *a6)
{
  bool v6; // si
  bool *v7; // rdi
  bool *v10; // r14
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r14
  int v15; // eax
  __int64 v16; // rdx
  bool v17; // cl
  unsigned __int64 v18; // r9
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int i; // ebx
  int v24; // [rsp+20h] [rbp-E0h]
  bool *v25; // [rsp+20h] [rbp-E0h]
  bool v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  bool *v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  char v33; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  bool *v35; // [rsp+A0h] [rbp-60h]
  __int128 v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int128 v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  __int64 v46; // [rsp+110h] [rbp+10h]
  _BYTE pSid2[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[80]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = 0;
  *a2 = 0;
  v7 = a2;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v35 = a5;
  v10 = a3;
  v28 = a2;
  v31 = (__int64)&v30;
  *(_QWORD *)&DestinationString.Length = a3;
  *a6 = 0;
  v30 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v32 = 0;
  v33 = 1;
  v11 = SRCacheManager_Open(0, &v32);
  if ( v33 )
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(v31, v32);
  if ( v11 >= 0 )
  {
    v26 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl) )
    {
      v25 = &v26;
      v19 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v30, a1, 568, &v36);
      v11 = v19;
      if ( v19 < 0 )
      {
        v18 = (unsigned int)v19;
        v12 = 1983;
        goto LABEL_27;
      }
      v6 = v26;
LABEL_16:
      if ( v6 )
      {
        v17 = (v38 & 0x40000000000000LL) != 0;
        *v7 = (v38 & 0x80000000000LL) != 0;
        *v10 = v17;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl)
          || HIDWORD(v39) != 2 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
            *a6 = (v39 & 0x200000) != 0;
        }
        else
        {
          *a6 = 0;
        }
        if ( *v7 || (v38 & 0x400000000000000LL) != 0 || (_QWORD)v43 )
        {
          *a4 = 1;
        }
        else if ( (unsigned __int8)IsQueryApplicationCapabilitiesPresent() )
        {
          v28 = 0;
          v31 = (__int64)&v28;
          v29 = 0;
          LODWORD(v32) = 0;
          BYTE4(v32) = 1;
          wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v28);
          v20 = QueryApplicationCapabilities(a1, &v28, &v32, 0);
          v11 = v20;
          if ( BYTE4(v32) )
            *(_QWORD *)(v31 + 8) = (unsigned int)v32;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7F1,
              (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
              (const char *)(unsigned int)v20,
              0);
LABEL_41:
            wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v28);
            goto LABEL_53;
          }
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
          memset_0(pSid2, 0, 0x44u);
          memset_0(v48, 0, 0x44u);
          v21 = RtlDeriveCapabilitySidsFromName(&DestinationString, v48, pSid2);
          if ( v21 < 0 )
          {
            v11 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x7FD,
                    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                    (const char *)(unsigned int)v21,
                    0);
            goto LABEL_41;
          }
          for ( i = 0; i < v29; ++i )
          {
            if ( EqualSid(*(PSID *)&v28[8 * i], pSid2) )
            {
              *a4 = 1;
              break;
            }
          }
          wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v28);
        }
        *v35 = (v39 & 0x8000) != 0;
      }
      v11 = 0;
      goto LABEL_53;
    }
    v31 = 0;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v30,
            a1,
            &v31);
    if ( v11 < 0 )
    {
      v13 = 1165;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v11,
        v24);
      v12 = 1974;
      goto LABEL_26;
    }
    v14 = v31;
    if ( !v31 )
    {
LABEL_15:
      v10 = *(bool **)&DestinationString.Length;
      goto LABEL_16;
    }
    v27 = 0;
    v15 = StateRepository::Cache::Entity::Package_NoThrow::Open(
            (struct StateRepository::Cache::Manager_NoThrow *)&v30,
            v31,
            (struct StateRepository::Cache::Context_NoThrow *)&v27,
            &v26);
    v6 = v26;
    v11 = v15;
    if ( v15 >= 0 )
    {
      if ( !v26 )
      {
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v27, 0);
LABEL_14:
        v7 = v28;
        goto LABEL_15;
      }
      v15 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v27, &v36, 536, v14);
      v11 = v15;
      if ( v15 >= 0 )
      {
        v11 = 0;
LABEL_23:
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v27, 0);
        if ( v11 < 0 )
        {
          v13 = 1168;
          goto LABEL_25;
        }
        goto LABEL_14;
      }
      v16 = 1115;
    }
    else
    {
      v16 = 1110;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v15,
      v24);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)(unsigned int)v11,
    v24);
  v12 = 1963;
LABEL_26:
  v18 = (unsigned int)v11;
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
    (const char *)v18,
    (int)v25);
LABEL_53:
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v36);
  wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v30, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180087818  push    rbp
0x18008781a  push    rbx
0x18008781b  push    rsi
0x18008781c  push    rdi
0x18008781d  push    r12
0x18008781f  push    r13
0x180087821  push    r14
0x180087823  push    r15
0x180087825  lea     rbp, [rsp-0D8h]
0x18008782d  sub     rsp, 1D8h
0x180087834  mov     rax, cs:__security_cookie
0x18008783b  xor     rax, rsp
0x18008783e  mov     [rbp+110h+var_50], rax
0x180087845  mov     rax, [rbp+110h+arg_20]
0x18008784c  xor     esi, esi
0x18008784e  mov     r15, [rbp+110h+arg_28]
0x180087855  xorps   xmm0, xmm0
0x180087858  mov     [rdx], sil
0x18008785b  mov     rdi, rdx
0x18008785e  mov     [r8], sil
0x180087861  mov     r12, rcx
0x180087864  mov     [r9], sil
0x180087867  xor     ecx, ecx
0x180087869  mov     [rax], sil
0x18008786c  mov     r13, r9
0x18008786f  mov     [rbp+110h+var_170], rax
0x180087873  mov     r14, r8
0x180087876  lea     rax, [rsp+210h+var_1A0]
0x18008787b  mov     [rsp+210h+var_1B0], rdx
0x180087880  lea     rdx, [rbp+110h+var_190]
0x180087884  mov     [rsp+210h+var_198], rax
0x180087889  mov     qword ptr [rbp+110h+DestinationString.Length], r8
0x18008788d  mov     [r15], sil
0x180087890  mov     [rsp+210h+var_1A0], rsi
0x180087895  movdqa  [rbp+110h+var_160], xmm0
0x18008789a  mov     [rbp+110h+var_150], rsi
0x18008789e  mov     [rbp+110h+var_148], rsi
0x1800878a2  mov     [rbp+110h+var_140], rsi
0x1800878a6  mov     [rbp+110h+var_138], rsi
0x1800878aa  mov     [rbp+110h+var_130], rsi
0x1800878ae  mov     [rbp+110h+var_128], rsi
0x1800878b2  movdqa  [rbp+110h+var_120], xmm0
0x1800878b7  mov     [rbp+110h+var_110], esi
0x1800878ba  mov     [rbp+110h+var_108], rsi
0x1800878be  mov     [rbp+110h+var_100], rsi
0x1800878c2  mov     [rbp+110h+var_190], rsi
0x1800878c6  mov     [rbp+110h+var_188], 1
0x1800878ca  call    cs:__imp_SRCacheManager_Open
0x1800878d1  nop     dword ptr [rax+rax+00h]
0x1800878d6  mov     ebx, eax
0x1800878d8  cmp     [rbp+110h+var_188], sil
0x1800878dc  jz      short loc_1800878EC
0x1800878de  mov     rdx, [rbp+110h+var_190]
0x1800878e2  mov     rcx, [rsp+210h+var_198]
0x1800878e7  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x1800878ec  test    ebx, ebx
0x1800878ee  jns     short loc_180087915
0x1800878f0  mov     rcx, [rbp+118h]; this
0x1800878f7  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800878fe  mov     r9d, ebx; char *
0x180087901  mov     edx, 0A5h; void *
0x180087906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008790b  mov     edx, 7ABh
0x180087910  jmp     loc_180087A64
0x180087915  mov     [rsp+210h+var_1C0], sil
0x18008791a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180087921  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x180087926  lea     rcx, [rsp+210h+var_1A0]; struct StateRepository::Cache::Manager_NoThrow *
0x18008792b  mov     rdx, r12; unsigned __int16 *
0x18008792e  test    al, al
0x180087930  jz      loc_180087A7F
0x180087936  lea     r8, [rsp+210h+var_198]; __int64 *
0x18008793b  mov     [rsp+210h+var_198], rsi
0x180087940  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180087945  mov     ebx, eax
0x180087947  test    eax, eax
0x180087949  jns     short loc_18008795C
0x18008794b  mov     edx, 48Dh
0x180087950  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087957  jmp     loc_180087A4D
0x18008795c  mov     r14, [rsp+210h+var_198]
0x180087961  test    r14, r14
0x180087964  jz      short loc_1800879C6
0x180087966  lea     r9, [rsp+210h+var_1C0]; bool *
0x18008796b  mov     [rsp+210h+var_1B8], rsi
0x180087970  lea     r8, [rsp+210h+var_1B8]; struct StateRepository::Cache::Context_NoThrow *
0x180087975  mov     rdx, r14; __int64
0x180087978  lea     rcx, [rsp+210h+var_1A0]; struct StateRepository::Cache::Manager_NoThrow *
0x18008797d  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180087982  mov     sil, [rsp+210h+var_1C0]
0x180087987  mov     ebx, eax
0x180087989  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087990  test    eax, eax
0x180087992  jns     short loc_1800879B0
0x180087994  mov     edx, 456h; void *
0x180087999  mov     rcx, [rbp+118h]; this
0x1800879a0  mov     r8, rdi; unsigned int
0x1800879a3  mov     r9d, eax; char *
0x1800879a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800879ab  jmp     loc_180087A34
0x1800879b0  lea     rcx, [rsp+210h+var_1B8]
0x1800879b5  test    sil, sil
0x1800879b8  jnz     short loc_180087A10
0x1800879ba  xor     edx, edx
0x1800879bc  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1800879c1  mov     rdi, [rsp+210h+var_1B0]
0x1800879c6  mov     r14, qword ptr [rbp+110h+DestinationString.Length]
0x1800879ca  test    sil, sil
0x1800879cd  jz      loc_180087C64
0x1800879d3  mov     ecx, dword ptr [rbp+110h+var_148+4]
0x1800879d6  mov     eax, ecx
0x1800879d8  shr     eax, 0Bh
0x1800879db  and     al, 1
0x1800879dd  shr     ecx, 16h
0x1800879e0  and     cl, 1
0x1800879e3  mov     [rdi], al
0x1800879e5  mov     [r14], cl
0x1800879e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x1800879ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x1800879f4  xor     esi, esi
0x1800879f6  test    al, al
0x1800879f8  jnz     loc_180087AB2
0x1800879fe  cmp     dword ptr [rbp+110h+var_140+4], 2
0x180087a02  jnz     loc_180087AB2
0x180087a08  mov     [r15], sil
0x180087a0b  jmp     loc_180087ACD
0x180087a10  mov     r9, r14
0x180087a13  lea     rdx, [rbp+110h+var_160]
0x180087a17  mov     r8d, 218h
0x180087a1d  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180087a22  mov     ebx, eax
0x180087a24  test    eax, eax
0x180087a26  jns     short loc_180087A32
0x180087a28  mov     edx, 45Bh
0x180087a2d  jmp     loc_180087999
0x180087a32  xor     ebx, ebx
0x180087a34  lea     rcx, [rsp+210h+var_1B8]
0x180087a39  xor     edx, edx
0x180087a3b  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x180087a40  test    ebx, ebx
0x180087a42  jns     loc_1800879C1
0x180087a48  mov     edx, 490h; void *
0x180087a4d  mov     rcx, [rbp+118h]; this
0x180087a54  mov     r9d, ebx; char *
0x180087a57  mov     r8, rdi; unsigned int
0x180087a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087a5f  mov     edx, 7B6h; void *
0x180087a64  mov     r9d, ebx; char *
0x180087a67  mov     rcx, [rbp+118h]; this
0x180087a6e  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180087a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087a7a  jmp     loc_180087C68
0x180087a7f  lea     rax, [rsp+210h+var_1C0]
0x180087a84  mov     r8d, 238h
0x180087a8a  lea     r9, [rbp+110h+var_160]
0x180087a8e  mov     qword ptr [rsp+210h+var_1F0], rax
0x180087a93  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180087a98  mov     ebx, eax
0x180087a9a  test    eax, eax
0x180087a9c  jns     short loc_180087AA8
0x180087a9e  mov     r9d, eax
0x180087aa1  mov     edx, 7BFh
0x180087aa6  jmp     short loc_180087A67
0x180087aa8  mov     sil, [rsp+210h+var_1C0]
0x180087aad  jmp     loc_1800879CA
0x180087ab2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180087ab9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180087abe  test    al, al
0x180087ac0  jz      short loc_180087ACD
0x180087ac2  mov     eax, dword ptr [rbp+110h+var_140]
0x180087ac5  shr     eax, 15h
0x180087ac8  and     al, 1
0x180087aca  mov     [r15], al
0x180087acd  cmp     [rdi], sil
0x180087ad0  jnz     loc_180087C4F
0x180087ad6  test    dword ptr [rbp+110h+var_148+4], 4000000h
0x180087add  jnz     loc_180087C4F
0x180087ae3  cmp     qword ptr [rbp+110h+var_120], rsi
0x180087ae7  jnz     loc_180087C4F
0x180087aed  call    IsQueryApplicationCapabilitiesPresent
0x180087af2  test    al, al
0x180087af4  jz      loc_180087C54
0x180087afa  lea     rax, [rsp+210h+var_1B0]
0x180087aff  mov     [rsp+210h+var_1B0], rsi
0x180087b04  lea     rcx, [rsp+210h+var_1B0]
0x180087b09  mov     [rsp+210h+var_198], rax
0x180087b0e  mov     [rsp+210h+var_1A8], rsi
0x180087b13  mov     dword ptr [rbp+110h+var_190], esi
0x180087b16  mov     byte ptr [rbp+110h+var_190+4], 1
0x180087b1a  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180087b1f  mov     [rsp+210h+var_1D0], rsi
0x180087b24  lea     r8, [rbp+110h+var_190]
0x180087b28  mov     [rsp+210h+var_1D8], rsi
0x180087b2d  lea     rdx, [rsp+210h+var_1B0]
0x180087b32  mov     [rsp+210h+var_1E0], rsi
0x180087b37  xor     r9d, r9d
0x180087b3a  mov     [rsp+210h+var_1E8], rsi
0x180087b3f  mov     rcx, r12
0x180087b42  mov     qword ptr [rsp+210h+var_1F0], rsi; int
0x180087b47  call    cs:__imp_QueryApplicationCapabilities
0x180087b4e  nop     dword ptr [rax+rax+00h]
0x180087b53  mov     ebx, eax
0x180087b55  cmp     byte ptr [rbp+110h+var_190+4], sil
0x180087b59  jz      short loc_180087B67
0x180087b5b  mov     rcx, [rsp+210h+var_198]
0x180087b60  mov     edx, dword ptr [rbp+110h+var_190]
0x180087b63  mov     [rcx+8], rdx
0x180087b67  test    eax, eax
0x180087b69  jns     short loc_180087B95
0x180087b6b  mov     rcx, [rbp+118h]; this
0x180087b72  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180087b79  mov     r9d, eax; char *
0x180087b7c  mov     edx, 7F1h; void *
0x180087b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087b86  lea     rcx, [rsp+210h+var_1B0]
0x180087b8b  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180087b90  jmp     loc_180087C68
0x180087b95  xorps   xmm0, xmm0
0x180087b98  lea     rdx, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x180087b9f  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x180087ba3  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x180087ba7  call    cs:__imp_RtlInitUnicodeString
0x180087bae  nop     dword ptr [rax+rax+00h]
0x180087bb3  mov     ebx, 44h ; 'D'
0x180087bb8  lea     rcx, [rbp+110h+pSid2]; void *
0x180087bbc  mov     r8d, ebx; Size
0x180087bbf  xor     edx, edx; Val
0x180087bc1  call    memset_0
0x180087bc6  mov     r8d, ebx; Size
0x180087bc9  lea     rcx, [rbp+110h+var_A0]; void *
0x180087bcd  xor     edx, edx; Val
0x180087bcf  call    memset_0
0x180087bd4  lea     r8, [rbp+110h+pSid2]
0x180087bd8  lea     rdx, [rbp+110h+var_A0]
0x180087bdc  lea     rcx, [rbp+110h+DestinationString]
0x180087be0  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180087be7  nop     dword ptr [rax+rax+00h]
0x180087bec  test    eax, eax
0x180087bee  jns     short loc_180087C12
0x180087bf0  mov     rcx, [rbp+118h]; this
0x180087bf7  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180087bfe  mov     r9d, eax; char *
0x180087c01  mov     edx, 7FDh; void *
0x180087c06  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180087c0b  mov     ebx, eax
0x180087c0d  jmp     loc_180087B86
0x180087c12  mov     ebx, esi
0x180087c14  mov     eax, ebx
0x180087c16  cmp     rax, [rsp+210h+var_1A8]
0x180087c1b  jnb     short loc_180087C43
0x180087c1d  mov     rcx, [rsp+210h+var_1B0]
0x180087c22  lea     rdx, [rbp+110h+pSid2]; pSid2
0x180087c26  mov     rcx, [rcx+rax*8]; pSid1
0x180087c2a  call    cs:__imp_EqualSid
0x180087c31  nop     dword ptr [rax+rax+00h]
0x180087c36  test    eax, eax
0x180087c38  jnz     short loc_180087C3E
0x180087c3a  inc     ebx
0x180087c3c  jmp     short loc_180087C14
0x180087c3e  mov     byte ptr [r13+0], 1
0x180087c43  lea     rcx, [rsp+210h+var_1B0]
0x180087c48  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180087c4d  jmp     short loc_180087C54
0x180087c4f  mov     byte ptr [r13+0], 1
0x180087c54  mov     eax, dword ptr [rbp+110h+var_140]
0x180087c57  mov     rcx, [rbp+110h+var_170]
0x180087c5b  shr     eax, 0Fh
0x180087c5e  and     al, 1
0x180087c60  mov     [rcx], al
0x180087c62  jmp     short loc_180087C66
0x180087c64  xor     esi, esi
0x180087c66  mov     ebx, esi
0x180087c68  lea     rcx, [rbp+110h+var_160]; this
0x180087c6c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180087c71  xor     edx, edx
0x180087c73  lea     rcx, [rsp+210h+var_1A0]
0x180087c78  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x180087c7d  mov     eax, ebx
0x180087c7f  mov     rcx, [rbp+110h+var_50]
0x180087c86  xor     rcx, rsp; StackCookie
0x180087c89  call    __security_check_cookie
0x180087c8e  add     rsp, 1D8h
0x180087c95  pop     r15
0x180087c97  pop     r14
0x180087c99  pop     r13
0x180087c9b  pop     r12
0x180087c9d  pop     rdi
0x180087c9e  pop     rsi
0x180087c9f  pop     rbx
0x180087ca0  pop     rbp
0x180087ca1  retn
```
