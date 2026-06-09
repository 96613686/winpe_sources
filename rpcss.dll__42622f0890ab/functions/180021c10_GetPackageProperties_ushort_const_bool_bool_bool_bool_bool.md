# GetPackageProperties(ushort const *,bool &,bool &,bool &,bool &,bool &)

- ea: `0x180021c10`
- end: `0x1800220ec`
- name: `?GetPackageProperties@@YAJPEBGAEA_N1111@Z`
- size: `1244`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, bool *@<rdx>, bool *@<r8>, bool *@<r9>, bool *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004cd64`

## callees

- `0x180020598`
- `0x180020b3c`
- `0x180020e38`
- `0x180020ed0`
- `0x180021454`
- `0x180021c10`
- `0x18002ba28`
- `0x18008cd90`
- `0x18009b364`
- `0x18009eb2c`
- `0x1800a25dc`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800b5588`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180022032`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180022032`
- `ntdll!RtlInitUnicodeString` at `0x180021ffe`
- `ntdll!RtlInitUnicodeString` at `0x180021ffe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022073`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022073`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021de4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021e87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021de4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021e87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180021cbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180021cbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021ce5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021d3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800220c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021ce5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021d3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800220c1`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180021fa3`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180021fa3`

## string_xrefs

- `0x180021d16`: `onecore\com\combase\catalog\services.cxx`
- `0x180021eab`: `onecore\com\combase\catalog\services.cxx`
- `0x180021fc7`: `onecore\com\combase\catalog\services.cxx`
- `0x180022043`: `onecore\com\combase\catalog\services.cxx`
- `0x180021d85`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021e62`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021cf6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180021fed`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall GetPackageProperties(const unsigned __int16 *a1, bool *a2, bool *a3, bool *a4, bool *a5, bool *a6)
{
  bool v6; // di
  bool *v10; // rsi
  int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rsi
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  bool v22; // cl
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  unsigned int i; // ebx
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-E0h]
  bool *v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  char v37; // [rsp+80h] [rbp-80h]
  __int64 *v38; // [rsp+88h] [rbp-78h]
  unsigned int v39; // [rsp+90h] [rbp-70h] BYREF
  char v40; // [rsp+94h] [rbp-6Ch]
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  __int64 v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int128 v48; // [rsp+E0h] [rbp-20h]
  int v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  bool *v52; // [rsp+110h] [rbp+10h]
  _BYTE pSid2[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v54[80]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v52 = a5;
  v38 = (__int64 *)a3;
  v35 = (__int64)&v33;
  v10 = a3;
  *a6 = 0;
  v33 = 0;
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
  v51 = 0;
  v36 = 0;
  v37 = 1;
  v11 = SRCacheManager_Open(0, &v36);
  if ( v37 )
  {
    v12 = *(_QWORD *)v35;
    *(_QWORD *)v35 = v36;
    if ( v12 )
      SRCacheManager_Close(v12);
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v11,
      v29);
    v13 = 1963;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)v11,
      (int)v30);
LABEL_7:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
    v14 = v33;
    v33 = 0;
LABEL_8:
    if ( v14 )
      SRCacheManager_Close(v14);
    return (unsigned int)v11;
  }
  v32 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl) )
  {
    v35 = 0;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v33,
            a1,
            &v35);
    if ( v11 < 0 )
    {
      v16 = 1165;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v11,
        v29);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B6,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v11,
        v31);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
      v14 = v33;
      v33 = 0;
      goto LABEL_8;
    }
    v17 = v35;
    if ( v35 )
    {
      *(_QWORD *)&DestinationString.Length = 0;
      v18 = StateRepository::Cache::Entity::Package_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v33,
              v35,
              (struct StateRepository::Cache::Context_NoThrow *)&DestinationString,
              &v32);
      v11 = v18;
      if ( v18 < 0 )
      {
        v20 = 1110;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)(unsigned int)v18,
          v29);
        v24 = *(_QWORD *)&DestinationString.Length;
        *(_QWORD *)&DestinationString.Length = 0;
        if ( v24 )
          SRCacheContext_Close(v24, v23);
        v16 = 1168;
        goto LABEL_30;
      }
      v6 = v32;
      if ( v32 )
      {
        v18 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&DestinationString, &v41, 536, v17);
        v11 = v18;
        if ( v18 < 0 )
        {
          v20 = 1115;
          goto LABEL_27;
        }
      }
      v21 = *(_QWORD *)&DestinationString.Length;
      *(_QWORD *)&DestinationString.Length = 0;
      if ( v21 )
        SRCacheContext_Close(v21, v19);
    }
    v10 = (bool *)v38;
  }
  else
  {
    v30 = &v32;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v33, a1, 568, &v41);
    if ( v11 < 0 )
    {
      v13 = 1983;
      goto LABEL_6;
    }
    v6 = v32;
  }
  if ( v6 )
  {
    v22 = (v43 & 0x40000000000000LL) != 0;
    *a2 = (v43 & 0x80000000000LL) != 0;
    *v10 = v22;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl)
      || HIDWORD(v44) != 2 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
        *a6 = (v44 & 0x200000) != 0;
    }
    else
    {
      *a6 = 0;
    }
    if ( *a2 || (v43 & 0x400000000000000LL) != 0 || (_QWORD)v48 )
    {
      *a4 = 1;
    }
    else if ( (unsigned __int8)IsQueryApplicationCapabilitiesPresent() )
    {
      v35 = 0;
      v38 = &v35;
      v36 = 0;
      v39 = 0;
      v40 = 1;
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v35);
      v25 = QueryApplicationCapabilities(a1, &v35, &v39, 0);
      v11 = v25;
      if ( v40 )
        v38[1] = v39;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F1,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)(unsigned int)v25,
          0);
LABEL_44:
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v35);
        goto LABEL_7;
      }
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
      memset_0(pSid2, 0, 0x44u);
      memset_0(v54, 0, 0x44u);
      v26 = RtlDeriveCapabilitySidsFromName(&DestinationString, v54, pSid2);
      if ( v26 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x7FD,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)(unsigned int)v26,
                0);
        goto LABEL_44;
      }
      for ( i = 0; i < v36; ++i )
      {
        if ( EqualSid(*(PSID *)(v35 + 8LL * i), pSid2) )
        {
          *a4 = 1;
          break;
        }
      }
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v35);
    }
    *v52 = (v44 & 0x8000) != 0;
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
  v28 = v33;
  v33 = 0;
  if ( v28 )
    SRCacheManager_Close(v28);
  return 0;
}

```

## disassembly

```asm
0x180021c10  push    rbp
0x180021c12  push    rbx
0x180021c13  push    rsi
0x180021c14  push    rdi
0x180021c15  push    r12
0x180021c17  push    r13
0x180021c19  push    r14
0x180021c1b  push    r15
0x180021c1d  lea     rbp, [rsp-0D8h]
0x180021c25  sub     rsp, 1D8h
0x180021c2c  mov     rax, cs:__security_cookie
0x180021c33  xor     rax, rsp
0x180021c36  mov     [rbp+110h+var_50], rax
0x180021c3d  mov     rax, [rbp+110h+arg_20]
0x180021c44  xor     edi, edi
0x180021c46  mov     r14, [rbp+110h+arg_28]
0x180021c4d  xorps   xmm0, xmm0
0x180021c50  mov     [rdx], dil
0x180021c53  mov     r13, rdx
0x180021c56  mov     [r8], dil
0x180021c59  lea     rdx, [rsp+210h+var_198]
0x180021c5e  mov     [r9], dil
0x180021c61  mov     r15, rcx
0x180021c64  mov     [rax], dil
0x180021c67  xor     ecx, ecx
0x180021c69  mov     [rbp+110h+var_100], rax
0x180021c6d  mov     r12, r9
0x180021c70  lea     rax, [rsp+210h+var_1B8]
0x180021c75  mov     [rbp+110h+var_188], r8
0x180021c79  mov     [rsp+210h+var_1A0], rax
0x180021c7e  mov     rsi, r8
0x180021c81  mov     [r14], dil
0x180021c84  mov     [rsp+210h+var_1B8], rdi
0x180021c89  movdqa  [rbp+110h+var_170], xmm0
0x180021c8e  mov     [rbp+110h+var_160], rdi
0x180021c92  mov     [rbp+110h+var_158], rdi
0x180021c96  mov     [rbp+110h+var_150], rdi
0x180021c9a  mov     [rbp+110h+var_148], rdi
0x180021c9e  mov     [rbp+110h+var_140], rdi
0x180021ca2  mov     [rbp+110h+var_138], rdi
0x180021ca6  movdqa  [rbp+110h+var_130], xmm0
0x180021cab  mov     [rbp+110h+var_120], edi
0x180021cae  mov     [rbp+110h+var_118], rdi
0x180021cb2  mov     [rbp+110h+var_110], rdi
0x180021cb6  mov     [rsp+210h+var_198], rdi
0x180021cbb  mov     [rbp+110h+var_190], 1
0x180021cbf  call    cs:__imp_SRCacheManager_Open
0x180021cc5  mov     ebx, eax
0x180021cc7  cmp     [rbp+110h+var_190], dil
0x180021ccb  jz      short loc_180021CEB
0x180021ccd  mov     rdx, [rsp+210h+var_1A0]
0x180021cd2  mov     rcx, [rsp+210h+var_198]
0x180021cd7  mov     rax, [rdx]
0x180021cda  mov     [rdx], rcx
0x180021cdd  test    rax, rax
0x180021ce0  jz      short loc_180021CEB
0x180021ce2  mov     rcx, rax
0x180021ce5  call    cs:__imp_SRCacheManager_Close
0x180021ceb  test    ebx, ebx
0x180021ced  jns     short loc_180021D4A
0x180021cef  mov     rcx, [rbp+118h]; this
0x180021cf6  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021cfd  mov     r9d, ebx; char *
0x180021d00  mov     edx, 0A5h; void *
0x180021d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d0a  mov     edx, 7ABh; void *
0x180021d0f  mov     rcx, [rbp+118h]; this
0x180021d16  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180021d1d  mov     r9d, ebx; char *
0x180021d20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d25  lea     rcx, [rbp+110h+var_170]; this
0x180021d29  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180021d2e  mov     rcx, [rsp+210h+var_1B8]
0x180021d33  mov     [rsp+210h+var_1B8], rdi
0x180021d38  test    rcx, rcx
0x180021d3b  jz      short loc_180021D43
0x180021d3d  call    cs:__imp_SRCacheManager_Close
0x180021d43  mov     eax, ebx
0x180021d45  jmp     loc_1800220C9
0x180021d4a  mov     [rsp+210h+var_1C0], dil
0x180021d4f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180021d56  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x180021d5b  lea     rcx, [rsp+210h+var_1B8]; struct StateRepository::Cache::Manager_NoThrow *
0x180021d60  mov     rdx, r15; unsigned __int16 *
0x180021d63  test    al, al
0x180021d65  jz      loc_180021EDB
0x180021d6b  lea     r8, [rsp+210h+var_1A0]; __int64 *
0x180021d70  mov     [rsp+210h+var_1A0], rdi
0x180021d75  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180021d7a  mov     ebx, eax
0x180021d7c  test    eax, eax
0x180021d7e  jns     short loc_180021D91
0x180021d80  mov     edx, 48Dh
0x180021d85  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021d8c  jmp     loc_180021E92
0x180021d91  mov     rsi, [rsp+210h+var_1A0]
0x180021d96  test    rsi, rsi
0x180021d99  jz      short loc_180021DEA
0x180021d9b  lea     r9, [rsp+210h+var_1C0]; bool *
0x180021da0  mov     qword ptr [rsp+210h+DestinationString.Length], rdi
0x180021da5  lea     r8, [rsp+210h+DestinationString]; struct StateRepository::Cache::Context_NoThrow *
0x180021daa  mov     rdx, rsi; __int64
0x180021dad  lea     rcx, [rsp+210h+var_1B8]; struct StateRepository::Cache::Manager_NoThrow *
0x180021db2  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180021db7  mov     ebx, eax
0x180021db9  test    eax, eax
0x180021dbb  jns     short loc_180021DC7
0x180021dbd  mov     edx, 456h
0x180021dc2  jmp     loc_180021E5B
0x180021dc7  mov     dil, [rsp+210h+var_1C0]
0x180021dcc  test    dil, dil
0x180021dcf  jnz     short loc_180021E35
0x180021dd1  mov     rcx, qword ptr [rsp+210h+DestinationString.Length]
0x180021dd6  mov     qword ptr [rsp+210h+DestinationString.Length], 0
0x180021ddf  test    rcx, rcx
0x180021de2  jz      short loc_180021DEA
0x180021de4  call    cs:__imp_SRCacheContext_Close
0x180021dea  mov     rsi, [rbp+110h+var_188]
0x180021dee  test    dil, dil
0x180021df1  jz      loc_1800220A7
0x180021df7  mov     ecx, dword ptr [rbp+110h+var_158+4]
0x180021dfa  mov     eax, ecx
0x180021dfc  shr     eax, 0Bh
0x180021dff  and     al, 1
0x180021e01  shr     ecx, 16h
0x180021e04  and     cl, 1
0x180021e07  mov     [r13+0], al
0x180021e0b  mov     [rsi], cl
0x180021e0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180021e14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x180021e19  xor     edi, edi
0x180021e1b  test    al, al
0x180021e1d  jnz     loc_180021F0E
0x180021e23  cmp     dword ptr [rbp+110h+var_150+4], 2
0x180021e27  jnz     loc_180021F0E
0x180021e2d  mov     [r14], dil
0x180021e30  jmp     loc_180021F29
0x180021e35  mov     r9, rsi
0x180021e38  lea     rdx, [rbp+110h+var_170]
0x180021e3c  mov     r8d, 218h
0x180021e42  lea     rcx, [rsp+210h+DestinationString]
0x180021e47  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180021e4c  mov     ebx, eax
0x180021e4e  test    eax, eax
0x180021e50  jns     loc_180021DD1
0x180021e56  mov     edx, 45Bh; void *
0x180021e5b  mov     rcx, [rbp+118h]; this
0x180021e62  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021e69  mov     r8, rdi; unsigned int
0x180021e6c  mov     r9d, eax; char *
0x180021e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e74  mov     rcx, qword ptr [rsp+210h+DestinationString.Length]
0x180021e79  mov     qword ptr [rsp+210h+DestinationString.Length], 0
0x180021e82  test    rcx, rcx
0x180021e85  jz      short loc_180021E8D
0x180021e87  call    cs:__imp_SRCacheContext_Close
0x180021e8d  mov     edx, 490h; void *
0x180021e92  mov     rcx, [rbp+118h]; this
0x180021e99  mov     r9d, ebx; char *
0x180021e9c  mov     r8, rdi; unsigned int
0x180021e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ea4  mov     rcx, [rbp+118h]; this
0x180021eab  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180021eb2  mov     r9d, ebx; char *
0x180021eb5  mov     edx, 7B6h; void *
0x180021eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ebf  lea     rcx, [rbp+110h+var_170]; this
0x180021ec3  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180021ec8  mov     rcx, [rsp+210h+var_1B8]
0x180021ecd  mov     [rsp+210h+var_1B8], 0
0x180021ed6  jmp     loc_180021D38
0x180021edb  lea     rax, [rsp+210h+var_1C0]
0x180021ee0  mov     r8d, 238h
0x180021ee6  lea     r9, [rbp+110h+var_170]
0x180021eea  mov     qword ptr [rsp+210h+var_1F0], rax
0x180021eef  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180021ef4  mov     ebx, eax
0x180021ef6  test    eax, eax
0x180021ef8  jns     short loc_180021F04
0x180021efa  mov     edx, 7BFh
0x180021eff  jmp     loc_180021D0F
0x180021f04  mov     dil, [rsp+210h+var_1C0]
0x180021f09  jmp     loc_180021DEE
0x180021f0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180021f15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180021f1a  test    al, al
0x180021f1c  jz      short loc_180021F29
0x180021f1e  mov     eax, dword ptr [rbp+110h+var_150]
0x180021f21  shr     eax, 15h
0x180021f24  and     al, 1
0x180021f26  mov     [r14], al
0x180021f29  cmp     [r13+0], dil
0x180021f2d  jnz     loc_180022092
0x180021f33  test    dword ptr [rbp+110h+var_158+4], 4000000h
0x180021f3a  jnz     loc_180022092
0x180021f40  cmp     qword ptr [rbp+110h+var_130], rdi
0x180021f44  jnz     loc_180022092
0x180021f4a  call    IsQueryApplicationCapabilitiesPresent
0x180021f4f  test    al, al
0x180021f51  jz      loc_180022097
0x180021f57  lea     rax, [rsp+210h+var_1A0]
0x180021f5c  mov     [rsp+210h+var_1A0], rdi
0x180021f61  lea     rcx, [rsp+210h+var_1A0]
0x180021f66  mov     [rbp+110h+var_188], rax
0x180021f6a  mov     [rsp+210h+var_198], rdi
0x180021f6f  mov     [rbp+110h+var_180], edi
0x180021f72  mov     [rbp+110h+var_17C], 1
0x180021f76  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180021f7b  mov     [rsp+210h+var_1D0], rdi
0x180021f80  lea     r8, [rbp+110h+var_180]
0x180021f84  mov     [rsp+210h+var_1D8], rdi
0x180021f89  lea     rdx, [rsp+210h+var_1A0]
0x180021f8e  mov     [rsp+210h+var_1E0], rdi
0x180021f93  xor     r9d, r9d
0x180021f96  mov     [rsp+210h+var_1E8], rdi
0x180021f9b  mov     rcx, r15
0x180021f9e  mov     qword ptr [rsp+210h+var_1F0], rdi; int
0x180021fa3  call    cs:__imp_QueryApplicationCapabilities
0x180021fa9  mov     ebx, eax
0x180021fab  cmp     [rbp+110h+var_17C], dil
0x180021faf  jz      short loc_180021FBC
0x180021fb1  mov     rcx, [rbp+110h+var_188]
0x180021fb5  mov     edx, [rbp+110h+var_180]
0x180021fb8  mov     [rcx+8], rdx
0x180021fbc  test    ebx, ebx
0x180021fbe  jns     short loc_180021FEA
0x180021fc0  mov     rcx, [rbp+118h]; this
0x180021fc7  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180021fce  mov     r9d, ebx; char *
0x180021fd1  mov     edx, 7F1h; void *
0x180021fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fdb  lea     rcx, [rsp+210h+var_1A0]
0x180021fe0  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180021fe5  jmp     loc_180021D25
0x180021fea  xorps   xmm0, xmm0
0x180021fed  lea     rdx, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x180021ff4  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x180021ff9  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x180021ffe  call    cs:__imp_RtlInitUnicodeString
0x180022004  mov     ebx, 44h ; 'D'
0x180022009  lea     rcx, [rbp+110h+pSid2]; void *
0x18002200d  mov     r8d, ebx; Size
0x180022010  xor     edx, edx; Val
0x180022012  call    memset_0
0x180022017  mov     r8d, ebx; Size
0x18002201a  lea     rcx, [rbp+110h+var_A0]; void *
0x18002201e  xor     edx, edx; Val
0x180022020  call    memset_0
0x180022025  lea     r8, [rbp+110h+pSid2]
0x180022029  lea     rdx, [rbp+110h+var_A0]
0x18002202d  lea     rcx, [rsp+210h+DestinationString]
0x180022032  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180022038  test    eax, eax
0x18002203a  jns     short loc_18002205B
0x18002203c  mov     rcx, [rbp+118h]; this
0x180022043  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18002204a  mov     r9d, eax; char *
0x18002204d  mov     edx, 7FDh; void *
0x180022052  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022057  mov     ebx, eax
0x180022059  jmp     short loc_180021FDB
0x18002205b  mov     ebx, edi
0x18002205d  mov     eax, ebx
0x18002205f  cmp     rax, [rsp+210h+var_198]
0x180022064  jnb     short loc_180022086
0x180022066  mov     rcx, [rsp+210h+var_1A0]
0x18002206b  lea     rdx, [rbp+110h+pSid2]; pSid2
0x18002206f  mov     rcx, [rcx+rax*8]; pSid1
0x180022073  call    cs:__imp_EqualSid
0x180022079  test    eax, eax
0x18002207b  jnz     short loc_180022081
0x18002207d  inc     ebx
0x18002207f  jmp     short loc_18002205D
0x180022081  mov     byte ptr [r12], 1
0x180022086  lea     rcx, [rsp+210h+var_1A0]
0x18002208b  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180022090  jmp     short loc_180022097
0x180022092  mov     byte ptr [r12], 1
0x180022097  mov     eax, dword ptr [rbp+110h+var_150]
0x18002209a  mov     rcx, [rbp+110h+var_100]
0x18002209e  shr     eax, 0Fh
0x1800220a1  and     al, 1
0x1800220a3  mov     [rcx], al
0x1800220a5  jmp     short loc_1800220A9
0x1800220a7  xor     edi, edi
0x1800220a9  lea     rcx, [rbp+110h+var_170]; this
0x1800220ad  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800220b2  mov     rcx, [rsp+210h+var_1B8]
0x1800220b7  mov     [rsp+210h+var_1B8], rdi
0x1800220bc  test    rcx, rcx
0x1800220bf  jz      short loc_1800220C7
0x1800220c1  call    cs:__imp_SRCacheManager_Close
0x1800220c7  xor     eax, eax
0x1800220c9  mov     rcx, [rbp+110h+var_50]
0x1800220d0  xor     rcx, rsp; StackCookie
0x1800220d3  call    __security_check_cookie
0x1800220d8  add     rsp, 1D8h
0x1800220df  pop     r15
0x1800220e1  pop     r14
0x1800220e3  pop     r13
  ... truncated ...
```
