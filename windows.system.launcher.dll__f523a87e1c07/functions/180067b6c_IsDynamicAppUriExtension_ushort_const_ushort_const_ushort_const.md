# IsDynamicAppUriExtension(ushort const *,ushort const *,ushort const *)

- ea: `0x180067b6c`
- end: `0x180067e62`
- name: `?IsDynamicAppUriExtension@@YA_NPEBG00@Z`
- size: `758`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b2ccc`

## callees

- `0x180009a7c`
- `0x18000a790`
- `0x18000b074`
- `0x18000f194`
- `0x180010c04`
- `0x180034d10`
- `0x180066864`
- `0x1800674cc`
- `0x180067b6c`
- `0x180067e68`
- `0x180083578`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067ce9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067ce9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180067ba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180067ba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180067e22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180067e22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180067e4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180067e4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180067e0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180067e36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180067e0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180067e36`

## string_xrefs

- `0x180067c4d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x180067be4`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067c15`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067c6e`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067cb0`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067d19`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067d53`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067d97`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067de3`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180067bc3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall IsDynamicAppUriExtension(const unsigned __int16 *a1, const unsigned __int16 *a2, LPCWCH lpString2)
{
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // ebx
  int v11; // eax
  char v12; // bl
  LPCWCH v13; // rdi
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 *v19; // rcx
  LPCWCH v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-79h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-79h]
  __int64 v26; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v27; // [rsp+38h] [rbp-61h] BYREF
  __int64 v28; // [rsp+40h] [rbp-59h] BYREF
  __int64 v29; // [rsp+48h] [rbp-51h]
  __int64 v30; // [rsp+50h] [rbp-49h] BYREF
  int v31; // [rsp+58h] [rbp-41h]
  __int64 v32; // [rsp+60h] [rbp-39h]
  __int64 v33; // [rsp+68h] [rbp-31h] BYREF
  __int64 v34[2]; // [rsp+70h] [rbp-29h] BYREF
  LPCWCH lpString1[2]; // [rsp+80h] [rbp-19h]
  _OWORD v36[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  char v39; // [rsp+118h] [rbp+7Fh] BYREF

  v26 = 0;
  v27 = &v26;
  v28 = 0;
  LOBYTE(v29) = 1;
  v6 = SRCacheManager_Open(0, &v28);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v27);
  if ( v6 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x309,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  v33 = 0;
  v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v26,
         a2,
         &v33);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v8 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Open(
         (StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow *)&v30,
         (struct StateRepository::Cache::Manager_NoThrow *)&v26);
  v10 = v8;
  if ( v8 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
  v39 = 0;
  *(_OWORD *)v34 = 0;
  *(_OWORD *)lpString1 = 0;
  v11 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(&v30, v9, v34, &v39);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
  v12 = 0;
  while ( v39 )
  {
    v13 = lpString1[0];
    if ( CompareStringOrdinal(lpString1[1], -1, lpString2, -1, 1) == 2 && v13 == (LPCWCH)v33 )
    {
      v27 = 0;
      LODWORD(v28) = 0;
      v29 = 0;
      v16 = StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::FindByDynamicAppUriHandlerGroup(
              (struct StateRepository::Cache::Manager_NoThrow *)&v26,
              v34[0],
              (struct StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *)&v27);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32C,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v16,
          bIgnoreCasea);
      memset(v36, 0, sizeof(v36));
      v37 = 0;
      v17 = StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(&v27, 0, v36, &v39);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCasea);
      v12 = 0;
      while ( v39 )
      {
        if ( StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::IsHostNameMatch(
               (StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v36,
               a1) )
        {
          v12 = 1;
          break;
        }
        LODWORD(v28) = v28 + 1;
        v18 = StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(&v27, 0, v36, &v39);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x337,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
            (const char *)(unsigned int)v18,
            bIgnoreCasea);
      }
      StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v36);
      v19 = v27;
      v27 = 0;
      if ( v19 )
        SRCacheContext_Close(v19);
      break;
    }
    ++v31;
    v15 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(&v30, v14, v34, &v39);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCasea);
  }
  v20 = lpString1[1];
  lpString1[1] = 0;
  if ( v20 )
    SRCache_Free(v20);
  v21 = v30;
  v30 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SRCacheManager_Close(v22);
  return v12;
}

```

## disassembly

```asm
0x180067b6c  push    rbp
0x180067b6e  push    rbx
0x180067b6f  push    rsi
0x180067b70  push    rdi
0x180067b71  push    r14
0x180067b73  push    r15
0x180067b75  lea     rbp, [rsp-2Fh]
0x180067b7a  sub     rsp, 0C8h
0x180067b81  mov     rsi, r8
0x180067b84  mov     rdi, rdx
0x180067b87  mov     r14, rcx
0x180067b8a  xor     r15d, r15d
0x180067b8d  mov     [rbp+57h+var_C0], r15
0x180067b91  lea     rax, [rbp+57h+var_C0]
0x180067b95  mov     [rbp+57h+var_B8], rax
0x180067b99  mov     [rbp+57h+var_B0], r15
0x180067b9d  mov     byte ptr [rbp+57h+var_A8], 1
0x180067ba1  lea     rdx, [rbp+57h+var_B0]
0x180067ba5  xor     ecx, ecx
0x180067ba7  call    cs:__imp_SRCacheManager_Open
0x180067bad  mov     ebx, eax
0x180067baf  lea     rcx, [rbp+57h+var_B8]
0x180067bb3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180067bb8  test    ebx, ebx
0x180067bba  jns     short loc_180067BD6
0x180067bbc  mov     rcx, [rbp+5Fh]; this
0x180067bc0  mov     r9d, ebx; char *
0x180067bc3  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180067bca  mov     edx, 0A5h; void *
0x180067bcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067bd4  jmp     short loc_180067BD9
0x180067bd6  mov     ebx, r15d
0x180067bd9  mov     rcx, [rbp+5Fh]; this
0x180067bdd  test    ebx, ebx
0x180067bdf  jns     short loc_180067BF6
0x180067be1  mov     r9d, ebx; char *
0x180067be4  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067beb  mov     edx, 309h; void *
0x180067bf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067bf6  mov     [rbp+57h+var_88], r15
0x180067bfa  lea     r8, [rbp+57h+var_88]; __int64 *
0x180067bfe  mov     rdx, rdi; unsigned __int16 *
0x180067c01  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Cache::Manager_NoThrow *
0x180067c05  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180067c0a  mov     rcx, [rbp+5Fh]; this
0x180067c0e  test    eax, eax
0x180067c10  jns     short loc_180067C27
0x180067c12  mov     r9d, eax; char *
0x180067c15  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067c1c  mov     edx, 30Ch; void *
0x180067c21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067c27  mov     [rbp+57h+var_A0], r15
0x180067c2b  mov     [rbp+57h+var_98], r15d
0x180067c2f  mov     [rbp+57h+var_90], r15
0x180067c33  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Cache::Manager_NoThrow *
0x180067c37  lea     rcx, [rbp+57h+var_A0]; this
0x180067c3b  call    ?Open@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180067c40  mov     ebx, eax
0x180067c42  test    eax, eax
0x180067c44  jns     short loc_180067C60
0x180067c46  mov     rcx, [rbp+5Fh]; this
0x180067c4a  mov     r9d, eax; char *
0x180067c4d  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x180067c54  mov     edx, 264h; void *
0x180067c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067c5e  jmp     short loc_180067C63
0x180067c60  mov     ebx, r15d
0x180067c63  mov     rcx, [rbp+5Fh]; this
0x180067c67  test    ebx, ebx
0x180067c69  jns     short loc_180067C80
0x180067c6b  mov     r9d, ebx; char *
0x180067c6e  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067c75  mov     edx, 30Fh; void *
0x180067c7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067c80  mov     [rbp+57h+arg_18], r15b
0x180067c84  xorps   xmm0, xmm0
0x180067c87  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180067c8c  xorps   xmm1, xmm1
0x180067c8f  movdqu  xmmword ptr [rbp+57h+lpString1], xmm1
0x180067c94  lea     r9, [rbp+57h+arg_18]
0x180067c98  lea     r8, [rbp+57h+var_80]
0x180067c9c  lea     rcx, [rbp+57h+var_A0]
0x180067ca0  call    ?Get@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x180067ca5  mov     rcx, [rbp+5Fh]; this
0x180067ca9  test    eax, eax
0x180067cab  jns     short loc_180067CC2
0x180067cad  mov     r9d, eax; char *
0x180067cb0  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067cb7  mov     edx, 315h; void *
0x180067cbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067cc2  mov     bl, r15b
0x180067cc5  cmp     [rbp+57h+arg_18], r15b
0x180067cc9  jz      loc_180067E15
0x180067ccf  mov     rdi, [rbp+57h+lpString1]
0x180067cd3  mov     [rsp+0F0h+bIgnoreCase], 1; int
0x180067cdb  or      r9d, 0FFFFFFFFh; cchCount2
0x180067cdf  mov     r8, rsi; lpString2
0x180067ce2  or      edx, r9d; cchCount1
0x180067ce5  mov     rcx, [rbp+57h+lpString1+8]; lpString1
0x180067ce9  call    cs:__imp_CompareStringOrdinal
0x180067cef  cmp     eax, 2
0x180067cf2  jnz     short loc_180067CFA
0x180067cf4  cmp     rdi, [rbp+57h+var_88]
0x180067cf8  jz      short loc_180067D2B
0x180067cfa  inc     [rbp+57h+var_98]
0x180067cfd  lea     r9, [rbp+57h+arg_18]
0x180067d01  lea     r8, [rbp+57h+var_80]
0x180067d05  lea     rcx, [rbp+57h+var_A0]
0x180067d09  call    ?Get@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x180067d0e  mov     rcx, [rbp+5Fh]; this
0x180067d12  test    eax, eax
0x180067d14  jns     short loc_180067CC5
0x180067d16  mov     r9d, eax; char *
0x180067d19  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067d20  mov     edx, 323h; void *
0x180067d25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067d2b  mov     [rbp+57h+var_B8], r15
0x180067d2f  mov     dword ptr [rbp+57h+var_B0], r15d
0x180067d33  mov     [rbp+57h+var_A8], r15
0x180067d37  lea     r8, [rbp+57h+var_B8]; this
0x180067d3b  mov     rdx, [rbp+57h+var_80]; __int64
0x180067d3f  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Cache::Manager_NoThrow *
0x180067d43  call    ?FindByDynamicAppUriHandlerGroup@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVDynamicAppUriHandlerIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::FindByDynamicAppUriHandlerGroup(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow &)
0x180067d48  mov     rcx, [rbp+5Fh]; this
0x180067d4c  test    eax, eax
0x180067d4e  jns     short loc_180067D65
0x180067d50  mov     r9d, eax; char *
0x180067d53  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067d5a  mov     edx, 32Ch; void *
0x180067d5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067d65  xorps   xmm0, xmm0
0x180067d68  movdqu  [rbp+57h+var_60], xmm0
0x180067d6d  xorps   xmm1, xmm1
0x180067d70  movdqu  [rbp+57h+var_50], xmm1
0x180067d75  mov     [rbp+57h+var_40], r15
0x180067d79  lea     r9, [rbp+57h+arg_18]
0x180067d7d  lea     r8, [rbp+57h+var_60]
0x180067d81  xor     edx, edx
0x180067d83  lea     rcx, [rbp+57h+var_B8]
0x180067d87  call    ?Get@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x180067d8c  mov     rcx, [rbp+5Fh]; this
0x180067d90  test    eax, eax
0x180067d92  jns     short loc_180067DA9
0x180067d94  mov     r9d, eax; char *
0x180067d97  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067d9e  mov     edx, 32Fh; void *
0x180067da3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067da9  mov     bl, r15b
0x180067dac  cmp     [rbp+57h+arg_18], r15b
0x180067db0  jz      short loc_180067DF7
0x180067db2  mov     rdx, r14; unsigned __int16 *
0x180067db5  lea     rcx, [rbp+57h+var_60]; this
0x180067db9  call    ?IsHostNameMatch@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEBA_NPEBG@Z; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::IsHostNameMatch(ushort const *)
0x180067dbe  test    al, al
0x180067dc0  jnz     short loc_180067DF5
0x180067dc2  inc     dword ptr [rbp+57h+var_B0]
0x180067dc5  lea     r9, [rbp+57h+arg_18]
0x180067dc9  lea     r8, [rbp+57h+var_60]
0x180067dcd  xor     edx, edx
0x180067dcf  lea     rcx, [rbp+57h+var_B8]
0x180067dd3  call    ?Get@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x180067dd8  mov     rcx, [rbp+5Fh]; this
0x180067ddc  test    eax, eax
0x180067dde  jns     short loc_180067DAC
0x180067de0  mov     r9d, eax; char *
0x180067de3  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180067dea  mov     edx, 337h; void *
0x180067def  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067df5  mov     bl, 1
0x180067df7  lea     rcx, [rbp+57h+var_60]; this
0x180067dfb  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x180067e00  nop
0x180067e01  mov     rcx, [rbp+57h+var_B8]
0x180067e05  mov     [rbp+57h+var_B8], r15
0x180067e09  test    rcx, rcx
0x180067e0c  jz      short loc_180067E15
0x180067e0e  call    cs:__imp_SRCacheContext_Close
0x180067e14  nop
0x180067e15  mov     rcx, [rbp+57h+lpString1+8]
0x180067e19  mov     [rbp+57h+lpString1+8], r15
0x180067e1d  test    rcx, rcx
0x180067e20  jz      short loc_180067E29
0x180067e22  call    cs:__imp_SRCache_Free
0x180067e28  nop
0x180067e29  mov     rcx, [rbp+57h+var_A0]
0x180067e2d  mov     [rbp+57h+var_A0], r15
0x180067e31  test    rcx, rcx
0x180067e34  jz      short loc_180067E3D
0x180067e36  call    cs:__imp_SRCacheContext_Close
0x180067e3c  nop
0x180067e3d  mov     rcx, [rbp+57h+var_C0]
0x180067e41  mov     [rbp+57h+var_C0], r15
0x180067e45  test    rcx, rcx
0x180067e48  jz      short loc_180067E50
0x180067e4a  call    cs:__imp_SRCacheManager_Close
0x180067e50  mov     al, bl
0x180067e52  add     rsp, 0C8h
0x180067e59  pop     r15
0x180067e5b  pop     r14
0x180067e5d  pop     rdi
0x180067e5e  pop     rsi
0x180067e5f  pop     rbx
0x180067e60  pop     rbp
0x180067e61  retn
```
