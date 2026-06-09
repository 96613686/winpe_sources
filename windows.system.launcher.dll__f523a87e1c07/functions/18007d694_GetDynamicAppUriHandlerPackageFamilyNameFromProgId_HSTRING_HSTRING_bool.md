# GetDynamicAppUriHandlerPackageFamilyNameFromProgId(HSTRING__ *,HSTRING__ * *,bool *)

- ea: `0x18007d694`
- end: `0x18007d9c0`
- name: `?GetDynamicAppUriHandlerPackageFamilyNameFromProgId@@YAJPEAUHSTRING__@@PEAPEAU1@PEA_N@Z`
- size: `812`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007d580`

## callees

- `0x1800049e8`
- `0x180008d70`
- `0x180009a7c`
- `0x18000a790`
- `0x180010c04`
- `0x180034d10`
- `0x1800426d8`
- `0x18007d694`
- `0x18007d9c8`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800d7aec`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007d6ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007d6ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d962`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d962`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007d741`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007d995`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007d741`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18007d995`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d7ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d980`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d7ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d980`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007d785`

## string_xrefs

- `0x18007d723`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007d7a7`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007d814`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007d87a`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007d8fb`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007d706`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall GetDynamicAppUriHandlerPackageFamilyNameFromProgId(HSTRING string, HSTRING *a2, bool *a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h]
  PCNZWCH sourceString[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[72]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+108h] [rbp+8h]
  __int64 v36; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  LOBYTE(v29) = 1;
  *a2 = 0;
  *a3 = 0;
  v24 = 0;
  v28 = (unsigned __int64)&v24;
  v6 = SRCacheManager_Open(0, (char *)&v28 + 8);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v28);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v6,
      v22);
    v7 = 608;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v6,
      v22);
LABEL_4:
    v8 = v24;
    v24 = 0;
    if ( v8 )
      SRCacheManager_Close(v8);
    return (unsigned int)v6;
  }
  v30 = 0;
  v6 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
         (struct StateRepository::Cache::Manager_NoThrow *)&v24,
         0,
         &v30);
  if ( v6 < 0 )
  {
    v7 = 611;
    goto LABEL_3;
  }
  v25 = 0;
  v26 = 0;
  v27 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v11 = StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::FindByProgID(
          (struct StateRepository::Cache::Manager_NoThrow *)&v24,
          StringRawBuffer,
          (struct StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *)&v25);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v11,
      v22);
    goto LABEL_11;
  }
  LOBYTE(v23) = 0;
  v32 = 0;
  memset(v31, 0, sizeof(v31));
  v13 = StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(&v25, 1, v31, &v23);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v13,
      v22);
LABEL_15:
    StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v31);
LABEL_11:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_4;
  }
  if ( (_BYTE)v23 )
  {
    v28 = 0;
    v29 = 0;
    v14 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Get(
            &v24,
            *((_QWORD *)&v31[0] + 1),
            0,
            &v28);
    v6 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x273,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v14,
        (int)&v23);
      goto LABEL_19;
    }
    if ( (_BYTE)v23 )
    {
      *(_OWORD *)sourceString = 0;
      memset_0(v34, 0, 0x44u);
      v35 = 0;
      v36 = 0;
      v6 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(&v24, v29, v16, sourceString);
      if ( v6 < 0 )
      {
        v17 = 633;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v6,
          (int)&v23);
        StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)sourceString);
LABEL_19:
        v15 = *((_QWORD *)&v29 + 1);
        *((_QWORD *)&v29 + 1) = 0;
        if ( v15 )
          SRCache_Free(v15);
        goto LABEL_15;
      }
      if ( (_BYTE)v23 )
      {
        v18 = -1;
        do
          ++v18;
        while ( sourceString[1][v18] );
        v6 = WindowsCreateString(sourceString[1], v18, a2);
        if ( v6 < 0 )
        {
          v17 = 639;
          goto LABEL_24;
        }
        *a3 = 1;
      }
      StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)sourceString);
    }
    v19 = *((_QWORD *)&v29 + 1);
    *((_QWORD *)&v29 + 1) = 0;
    if ( v19 )
      SRCache_Free(v19);
  }
  StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v31);
  v20 = v25;
  v25 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  v21 = v24;
  v24 = 0;
  if ( v21 )
    SRCacheManager_Close(v21);
  return 0;
}

```

## disassembly

```asm
0x18007d694  mov     [rsp-8+arg_18], rbx
0x18007d699  push    rbp
0x18007d69a  push    rsi
0x18007d69b  push    rdi
0x18007d69c  push    r14
0x18007d69e  push    r15
0x18007d6a0  lea     rbp, [rsp-30h]
0x18007d6a5  sub     rsp, 130h
0x18007d6ac  mov     rax, cs:__security_cookie
0x18007d6b3  xor     rax, rsp
0x18007d6b6  mov     [rbp+50h+var_30], rax
0x18007d6ba  xor     r15d, r15d
0x18007d6bd  mov     byte ptr [rsp+150h+var_E8], 1
0x18007d6c2  mov     [rdx], r15
0x18007d6c5  lea     rax, [rsp+150h+var_118]
0x18007d6ca  mov     r14, rdx
0x18007d6cd  mov     [r8], r15b
0x18007d6d0  mov     rsi, rcx
0x18007d6d3  mov     [rsp+150h+var_118], r15
0x18007d6d8  lea     rdx, [rsp+150h+var_F8+8]
0x18007d6dd  mov     qword ptr [rsp+150h+var_F8], rax
0x18007d6e2  xor     ecx, ecx
0x18007d6e4  mov     qword ptr [rsp+150h+var_F8+8], r15
0x18007d6e9  mov     rdi, r8
0x18007d6ec  call    cs:__imp_SRCacheManager_Open
0x18007d6f2  lea     rcx, [rsp+150h+var_F8]
0x18007d6f7  mov     ebx, eax
0x18007d6f9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18007d6fe  test    ebx, ebx
0x18007d700  jns     short loc_18007D74E
0x18007d702  mov     rcx, [rbp+58h]; this
0x18007d706  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d70d  mov     r9d, ebx; char *
0x18007d710  mov     edx, 0A5h; void *
0x18007d715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d71a  mov     edx, 260h; void *
0x18007d71f  mov     rcx, [rbp+58h]; this
0x18007d723  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007d72a  mov     r9d, ebx; char *
0x18007d72d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d732  mov     rcx, [rsp+150h+var_118]
0x18007d737  mov     [rsp+150h+var_118], r15
0x18007d73c  test    rcx, rcx
0x18007d73f  jz      short loc_18007D747
0x18007d741  call    cs:__imp_SRCacheManager_Close
0x18007d747  mov     eax, ebx
0x18007d749  jmp     loc_18007D99D
0x18007d74e  lea     r8, [rsp+150h+var_D8]; __int64 *
0x18007d753  mov     [rsp+150h+var_D8], r15
0x18007d758  xor     edx, edx; void *
0x18007d75a  lea     rcx, [rsp+150h+var_118]; struct StateRepository::Cache::Manager_NoThrow *
0x18007d75f  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18007d764  mov     ebx, eax
0x18007d766  test    eax, eax
0x18007d768  jns     short loc_18007D771
0x18007d76a  mov     edx, 263h
0x18007d76f  jmp     short loc_18007D71F
0x18007d771  xor     edx, edx; length
0x18007d773  mov     [rsp+150h+var_110], r15
0x18007d778  mov     rcx, rsi; string
0x18007d77b  mov     [rsp+150h+var_108], r15d
0x18007d780  mov     [rsp+150h+var_100], r15
0x18007d785  call    cs:__imp_WindowsGetStringRawBuffer
0x18007d78b  mov     rdx, rax; unsigned __int16 *
0x18007d78e  lea     r8, [rsp+150h+var_110]; this
0x18007d793  lea     rcx, [rsp+150h+var_118]; struct StateRepository::Cache::Manager_NoThrow *
0x18007d798  call    ?FindByProgID@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAVDynamicAppUriHandlerIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::FindByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow &)
0x18007d79d  mov     ebx, eax
0x18007d79f  test    eax, eax
0x18007d7a1  jns     short loc_18007D7D9
0x18007d7a3  mov     rcx, [rbp+58h]; this
0x18007d7a7  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007d7ae  mov     r9d, eax; char *
0x18007d7b1  mov     edx, 267h; void *
0x18007d7b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d7bb  mov     rcx, [rsp+150h+var_110]
0x18007d7c0  mov     [rsp+150h+var_110], r15
0x18007d7c5  test    rcx, rcx
0x18007d7c8  jz      loc_18007D732
0x18007d7ce  call    cs:__imp_SRCacheContext_Close
0x18007d7d4  jmp     loc_18007D732
0x18007d7d9  xorps   xmm0, xmm0
0x18007d7dc  mov     byte ptr [rsp+150h+var_120], r15b
0x18007d7e1  xorps   xmm1, xmm1
0x18007d7e4  mov     [rbp+50h+var_B0], r15
0x18007d7e8  lea     r9, [rsp+150h+var_120]
0x18007d7ed  mov     edx, 1
0x18007d7f2  lea     r8, [rbp+50h+var_D0]
0x18007d7f6  lea     rcx, [rsp+150h+var_110]
0x18007d7fb  movdqu  [rbp+50h+var_D0], xmm0
0x18007d800  movdqu  [rbp+50h+var_C0], xmm1
0x18007d805  call    ?Get@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x18007d80a  mov     ebx, eax
0x18007d80c  test    eax, eax
0x18007d80e  jns     short loc_18007D833
0x18007d810  mov     rcx, [rbp+58h]; this
0x18007d814  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007d81b  mov     r9d, eax; char *
0x18007d81e  mov     edx, 26Dh; void *
0x18007d823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d828  lea     rcx, [rbp+50h+var_D0]; this
0x18007d82c  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x18007d831  jmp     short loc_18007D7BB
0x18007d833  cmp     byte ptr [rsp+150h+var_120], r15b
0x18007d838  jz      loc_18007D968
0x18007d83e  mov     rdx, qword ptr [rbp+50h+var_D0+8]
0x18007d842  lea     rax, [rsp+150h+var_120]
0x18007d847  xorps   xmm0, xmm0
0x18007d84a  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007d84f  xorps   xmm1, xmm1
0x18007d852  lea     r9, [rsp+150h+var_F8]
0x18007d857  xor     r8d, r8d
0x18007d85a  lea     rcx, [rsp+150h+var_118]
0x18007d85f  movdqu  [rsp+150h+var_F8], xmm0
0x18007d865  movdqu  [rsp+150h+var_E8], xmm1
0x18007d86b  call    ?Get@DynamicAppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x18007d870  mov     ebx, eax
0x18007d872  test    eax, eax
0x18007d874  jns     short loc_18007D8A5
0x18007d876  mov     rcx, [rbp+58h]; this
0x18007d87a  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007d881  mov     r9d, eax; char *
0x18007d884  mov     edx, 273h; void *
0x18007d889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d88e  mov     rcx, qword ptr [rsp+150h+var_E8+8]
0x18007d893  mov     qword ptr [rsp+150h+var_E8+8], r15
0x18007d898  test    rcx, rcx
0x18007d89b  jz      short loc_18007D828
0x18007d89d  call    cs:__imp_SRCache_Free
0x18007d8a3  jmp     short loc_18007D828
0x18007d8a5  cmp     byte ptr [rsp+150h+var_120], r15b
0x18007d8aa  jz      loc_18007D953
0x18007d8b0  xor     edx, edx; Val
0x18007d8b2  lea     rcx, [rbp+50h+var_90]; void *
0x18007d8b6  xorps   xmm0, xmm0
0x18007d8b9  movdqa  xmmword ptr [rbp+50h+sourceString], xmm0
0x18007d8be  lea     r8d, [rdx+44h]; Size
0x18007d8c2  call    memset_0
0x18007d8c7  mov     rdx, qword ptr [rsp+150h+var_E8]
0x18007d8cc  lea     rax, [rsp+150h+var_120]
0x18007d8d1  lea     r9, [rbp+50h+sourceString]
0x18007d8d5  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007d8da  lea     rcx, [rsp+150h+var_118]
0x18007d8df  mov     [rbp+50h+var_48], r15
0x18007d8e3  mov     [rbp+50h+var_40], r15
0x18007d8e7  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x18007d8ec  mov     ebx, eax
0x18007d8ee  test    eax, eax
0x18007d8f0  jns     short loc_18007D918
0x18007d8f2  mov     edx, 279h; void *
0x18007d8f7  mov     rcx, [rbp+58h]; this
0x18007d8fb  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007d902  mov     r9d, ebx; char *
0x18007d905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d90a  lea     rcx, [rbp+50h+sourceString]; this
0x18007d90e  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x18007d913  jmp     loc_18007D88E
0x18007d918  cmp     byte ptr [rsp+150h+var_120], r15b
0x18007d91d  jz      short loc_18007D94A
0x18007d91f  mov     rcx, [rbp+50h+sourceString+8]; sourceString
0x18007d923  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007d927  inc     rdx; length
0x18007d92a  cmp     [rcx+rdx*2], r15w
0x18007d92f  jnz     short loc_18007D927
0x18007d931  mov     r8, r14; string
0x18007d934  call    cs:__imp_WindowsCreateString
0x18007d93a  mov     ebx, eax
0x18007d93c  test    eax, eax
0x18007d93e  jns     short loc_18007D947
0x18007d940  mov     edx, 27Fh
0x18007d945  jmp     short loc_18007D8F7
0x18007d947  mov     byte ptr [rdi], 1
0x18007d94a  lea     rcx, [rbp+50h+sourceString]; this
0x18007d94e  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x18007d953  mov     rcx, qword ptr [rsp+150h+var_E8+8]
0x18007d958  mov     qword ptr [rsp+150h+var_E8+8], r15
0x18007d95d  test    rcx, rcx
0x18007d960  jz      short loc_18007D968
0x18007d962  call    cs:__imp_SRCache_Free
0x18007d968  lea     rcx, [rbp+50h+var_D0]; this
0x18007d96c  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x18007d971  mov     rcx, [rsp+150h+var_110]
0x18007d976  mov     [rsp+150h+var_110], r15
0x18007d97b  test    rcx, rcx
0x18007d97e  jz      short loc_18007D986
0x18007d980  call    cs:__imp_SRCacheContext_Close
0x18007d986  mov     rcx, [rsp+150h+var_118]
0x18007d98b  mov     [rsp+150h+var_118], r15
0x18007d990  test    rcx, rcx
0x18007d993  jz      short loc_18007D99B
0x18007d995  call    cs:__imp_SRCacheManager_Close
0x18007d99b  xor     eax, eax
0x18007d99d  mov     rcx, [rbp+50h+var_30]
0x18007d9a1  xor     rcx, rsp; StackCookie
0x18007d9a4  call    __security_check_cookie
0x18007d9a9  mov     rbx, [rsp+150h+arg_18]
0x18007d9b1  add     rsp, 130h
0x18007d9b8  pop     r15
0x18007d9ba  pop     r14
0x18007d9bc  pop     rdi
0x18007d9bd  pop     rsi
0x18007d9be  pop     rbp
0x18007d9bf  retn
```
