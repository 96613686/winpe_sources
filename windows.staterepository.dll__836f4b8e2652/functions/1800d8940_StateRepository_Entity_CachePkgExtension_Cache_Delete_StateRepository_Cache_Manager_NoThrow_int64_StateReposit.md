# StateRepository::Entity::CachePkgExtension::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x1800d8940`
- end: `0x1800d8d80`
- name: `?Cache_Delete@CachePkgExtension@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180202138`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x1800d8940`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d89fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8aa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8c75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8cd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8d17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8d52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d89fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8aa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8c75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8cd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8d17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d8d52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8b2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8ba4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8ced`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8d02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8b2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8ba4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8ced`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d8d02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d89a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d8a43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d8c16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d89a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d8a43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d8c16`

## string_xrefs

- `0x1800d89bd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800d8a60`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800d8c33`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800d8c05`: `PkgExtension\Index`
- `0x1800d8cab`: `PkgExtension\Index`
- `0x1800d897f`: `PkgExtension`
- `0x1800d8d22`: `PkgExtension`
- `0x1800d8a32`: `PkgExtension\Data`
- `0x1800d8bcd`: `PkgExtension\Data`
- `0x1800d89dd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x1800d8a7b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x1800d8b05`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x1800d8b82`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x1800d8c53`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePkgExtension::Cache_Delete(__int64 *a1, unsigned __int64 a2)
{
  __int64 v4; // rcx
  int IndexKeys; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool v11; // si
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-B8h] BYREF
  char v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+268h] [rbp+168h]
  __int64 v34; // [rsp+270h] [rbp+170h]
  unsigned __int16 *v35; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v30 = 1;
  v4 = *a1;
  v28 = (__int64 *)v24;
  *(_QWORD *)v24 = 0;
  v29 = 0;
  IndexKeys = SRCacheContext_Open(v4, L"PkgExtension", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 571;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
LABEL_4:
    v7 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
    return (unsigned int)IndexKeys;
  }
  if ( *(_QWORD *)v24 )
  {
    v9 = *a1;
    v28 = &v25;
    v25 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v9, L"PkgExtension\\Data", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
LABEL_10:
      v10 = v25;
      v25 = 0;
      if ( v10 )
        SRCacheContext_Close(v10);
      goto LABEL_4;
    }
    v31 = 0;
    v11 = v25 != 0;
    memset_0(v32, 0, sizeof(v32));
    v33 = 0;
    v35 = (unsigned __int16 *)v32;
    v34 = 256;
    v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a2);
    IndexKeys = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
        (const char *)(unsigned int)v12,
        v24[0]);
LABEL_14:
      v13 = v31;
      v31 = 0;
      if ( v13 )
        SRCache_Free(v13);
      goto LABEL_10;
    }
    v28 = (__int64 *)&v26;
    v26 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = StateRepository::CacheManagement::GetIndexKeys(
                  (struct StateRepository::Cache::Context_NoThrow *)&v25,
                  v35,
                  &v29);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v28);
    if ( IndexKeys < 0 )
    {
      v14 = 579;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
LABEL_19:
      v15 = v26;
      v26 = 0;
      if ( v15 )
        SRCache_Free(v15);
      goto LABEL_14;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::Delete((StateRepository::Cache::Context_NoThrow *)&v25, v35);
    if ( IndexKeys < 0 )
    {
      v14 = 580;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"PkgExtension\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 582;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"PkgExtension\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 586;
      goto LABEL_27;
    }
    v19 = v27;
    if ( v27 )
    {
      IndexKeys = StateRepository::CacheManagement::DeleteIndexKeys(
                    (struct StateRepository::Cache::Context_NoThrow *)&v27,
                    v26);
      if ( IndexKeys < 0 )
      {
        v17 = 589;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"PkgExtension\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 590;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
          (const char *)(unsigned int)IndexKeys,
          v24[0]);
        v18 = v27;
        v27 = 0;
        if ( v18 )
          SRCacheContext_Close(v18);
        goto LABEL_19;
      }
      v19 = v27;
    }
    v27 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    v20 = v26;
    v26 = 0;
    if ( v20 )
      SRCache_Free(v20);
    v21 = v31;
    v31 = 0;
    if ( v21 )
      SRCache_Free(v21);
    v22 = v25;
    v25 = 0;
    if ( v22 )
      SRCacheContext_Close(v22);
    if ( v11 )
    {
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)v24,
                    L"PkgExtension");
      if ( IndexKeys < 0 )
      {
        v6 = 595;
        goto LABEL_3;
      }
    }
  }
  v23 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v23 )
    SRCacheContext_Close(v23);
  return 0;
}

```

## disassembly

```asm
0x1800d8940  mov     [rsp-8+arg_10], rbx
0x1800d8945  push    rbp
0x1800d8946  push    rsi
0x1800d8947  push    rdi
0x1800d8948  push    r14
0x1800d894a  push    r15
0x1800d894c  lea     rbp, [rsp-190h]
0x1800d8954  sub     rsp, 290h
0x1800d895b  mov     rax, cs:__security_cookie
0x1800d8962  xor     rax, rsp
0x1800d8965  mov     [rbp+1B0h+var_30], rax
0x1800d896c  mov     r14, rdx
0x1800d896f  mov     [rsp+2B0h+var_260], 1
0x1800d8974  mov     rdi, rcx
0x1800d8977  lea     rax, [rsp+2B0h+var_290]
0x1800d897c  mov     rcx, [rcx]
0x1800d897f  lea     rdx, aPkgextension; "PkgExtension"
0x1800d8986  xor     r15d, r15d
0x1800d8989  mov     [rsp+2B0h+var_270], rax
0x1800d898e  lea     r9, [rsp+2B0h+var_268]
0x1800d8993  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800d8998  xor     r8d, r8d
0x1800d899b  mov     [rsp+2B0h+var_268], r15
0x1800d89a0  call    cs:__imp_SRCacheContext_Open
0x1800d89a6  lea     rcx, [rsp+2B0h+var_270]
0x1800d89ab  mov     ebx, eax
0x1800d89ad  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d89b2  test    ebx, ebx
0x1800d89b4  jns     short loc_1800D8A08
0x1800d89b6  mov     rcx, [rbp+1B8h]; this
0x1800d89bd  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d89c4  mov     r9d, ebx; char *
0x1800d89c7  mov     edx, 18Ch; void *
0x1800d89cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d89d1  mov     edx, 23Bh; void *
0x1800d89d6  mov     rcx, [rbp+1B8h]; this
0x1800d89dd  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x1800d89e4  mov     r9d, ebx; char *
0x1800d89e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d89ec  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800d89f1  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800d89f6  test    rcx, rcx
0x1800d89f9  jz      short loc_1800D8A01
0x1800d89fb  call    cs:__imp_SRCacheContext_Close
0x1800d8a01  mov     eax, ebx
0x1800d8a03  jmp     loc_1800D8D5A
0x1800d8a08  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800d8a0d  setnz   al
0x1800d8a10  test    al, al
0x1800d8a12  jz      loc_1800D8D43
0x1800d8a18  mov     rcx, [rdi]
0x1800d8a1b  lea     rax, [rsp+2B0h+var_288]
0x1800d8a20  lea     r9, [rsp+2B0h+var_268]
0x1800d8a25  mov     [rsp+2B0h+var_270], rax
0x1800d8a2a  xor     r8d, r8d
0x1800d8a2d  mov     [rsp+2B0h+var_288], r15
0x1800d8a32  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x1800d8a39  mov     [rsp+2B0h+var_268], r15
0x1800d8a3e  mov     [rsp+2B0h+var_260], 1
0x1800d8a43  call    cs:__imp_SRCacheContext_Open
0x1800d8a49  lea     rcx, [rsp+2B0h+var_270]
0x1800d8a4e  mov     ebx, eax
0x1800d8a50  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d8a55  test    ebx, ebx
0x1800d8a57  jns     short loc_1800D8AAD
0x1800d8a59  mov     rcx, [rbp+1B8h]; this
0x1800d8a60  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d8a67  mov     r9d, ebx; char *
0x1800d8a6a  mov     edx, 18Ch; void *
0x1800d8a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8a74  mov     rcx, [rbp+1B8h]; this
0x1800d8a7b  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x1800d8a82  mov     r9d, ebx; char *
0x1800d8a85  mov     edx, 23Fh; void *
0x1800d8a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8a8f  mov     rcx, [rsp+2B0h+var_288]
0x1800d8a94  mov     [rsp+2B0h+var_288], r15
0x1800d8a99  test    rcx, rcx
0x1800d8a9c  jz      loc_1800D89EC
0x1800d8aa2  call    cs:__imp_SRCacheContext_Close
0x1800d8aa8  jmp     loc_1800D89EC
0x1800d8aad  cmp     [rsp+2B0h+var_288], r15
0x1800d8ab2  lea     rcx, [rsp+2B0h+var_248]; void *
0x1800d8ab7  mov     r8d, 200h; Size
0x1800d8abd  mov     [rsp+2B0h+var_250], r15
0x1800d8ac2  setnz   sil
0x1800d8ac6  xor     edx, edx; Val
0x1800d8ac8  call    memset_0
0x1800d8acd  lea     rax, [rsp+2B0h+var_248]
0x1800d8ad2  mov     [rbp+1B0h+var_48], r15
0x1800d8ad9  mov     rdx, r14; unsigned __int64
0x1800d8adc  mov     [rbp+1B0h+var_38], rax
0x1800d8ae3  lea     rcx, [rsp+2B0h+var_250]; this
0x1800d8ae8  mov     [rbp+1B0h+var_40], 100h
0x1800d8af3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800d8af8  mov     ebx, eax
0x1800d8afa  test    eax, eax
0x1800d8afc  jns     short loc_1800D8B37
0x1800d8afe  mov     rcx, [rbp+1B8h]; this
0x1800d8b05  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x1800d8b0c  mov     r9d, eax; char *
0x1800d8b0f  mov     edx, 241h; void *
0x1800d8b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8b19  mov     rcx, [rsp+2B0h+var_250]
0x1800d8b1e  mov     [rsp+2B0h+var_250], r15
0x1800d8b23  test    rcx, rcx
0x1800d8b26  jz      loc_1800D8A8F
0x1800d8b2c  call    cs:__imp_SRCache_Free
0x1800d8b32  jmp     loc_1800D8A8F
0x1800d8b37  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800d8b3e  lea     rax, [rsp+2B0h+var_280]
0x1800d8b43  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x1800d8b48  mov     [rsp+2B0h+var_270], rax
0x1800d8b4d  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x1800d8b52  mov     [rsp+2B0h+var_280], r15
0x1800d8b57  mov     [rsp+2B0h+var_268], r15
0x1800d8b5c  mov     [rsp+2B0h+var_260], 1
0x1800d8b61  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x1800d8b66  lea     rcx, [rsp+2B0h+var_270]
0x1800d8b6b  mov     ebx, eax
0x1800d8b6d  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800d8b72  test    ebx, ebx
0x1800d8b74  jns     short loc_1800D8BAF
0x1800d8b76  mov     edx, 243h; void *
0x1800d8b7b  mov     rcx, [rbp+1B8h]; this
0x1800d8b82  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x1800d8b89  mov     r9d, ebx; char *
0x1800d8b8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8b91  mov     rcx, [rsp+2B0h+var_280]
0x1800d8b96  mov     [rsp+2B0h+var_280], r15
0x1800d8b9b  test    rcx, rcx
0x1800d8b9e  jz      loc_1800D8B19
0x1800d8ba4  call    cs:__imp_SRCache_Free
0x1800d8baa  jmp     loc_1800D8B19
0x1800d8baf  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800d8bb6  lea     rcx, [rsp+2B0h+var_288]; this
0x1800d8bbb  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x1800d8bc0  mov     ebx, eax
0x1800d8bc2  test    eax, eax
0x1800d8bc4  jns     short loc_1800D8BCD
0x1800d8bc6  mov     edx, 244h
0x1800d8bcb  jmp     short loc_1800D8B7B
0x1800d8bcd  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x1800d8bd4  lea     rcx, [rsp+2B0h+var_288]; this
0x1800d8bd9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800d8bde  mov     ebx, eax
0x1800d8be0  test    eax, eax
0x1800d8be2  jns     short loc_1800D8BEB
0x1800d8be4  mov     edx, 246h
0x1800d8be9  jmp     short loc_1800D8B7B
0x1800d8beb  mov     rcx, [rdi]
0x1800d8bee  lea     rax, [rsp+2B0h+var_278]
0x1800d8bf3  lea     r9, [rsp+2B0h+var_268]
0x1800d8bf8  mov     [rsp+2B0h+var_270], rax
0x1800d8bfd  xor     r8d, r8d
0x1800d8c00  mov     [rsp+2B0h+var_278], r15
0x1800d8c05  lea     rdx, aPkgextensionIn; "PkgExtension\\Index"
0x1800d8c0c  mov     [rsp+2B0h+var_268], r15
0x1800d8c11  mov     [rsp+2B0h+var_260], 1
0x1800d8c16  call    cs:__imp_SRCacheContext_Open
0x1800d8c1c  lea     rcx, [rsp+2B0h+var_270]
0x1800d8c21  mov     ebx, eax
0x1800d8c23  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d8c28  test    ebx, ebx
0x1800d8c2a  jns     short loc_1800D8C80
0x1800d8c2c  mov     rcx, [rbp+1B8h]; this
0x1800d8c33  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d8c3a  mov     r9d, ebx; char *
0x1800d8c3d  mov     edx, 18Ch; void *
0x1800d8c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8c47  mov     edx, 24Ah; void *
0x1800d8c4c  mov     rcx, [rbp+1B8h]; this
0x1800d8c53  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x1800d8c5a  mov     r9d, ebx; char *
0x1800d8c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8c62  mov     rcx, [rsp+2B0h+var_278]
0x1800d8c67  mov     [rsp+2B0h+var_278], r15
0x1800d8c6c  test    rcx, rcx
0x1800d8c6f  jz      loc_1800D8B91
0x1800d8c75  call    cs:__imp_SRCacheContext_Close
0x1800d8c7b  jmp     loc_1800D8B91
0x1800d8c80  mov     rcx, [rsp+2B0h+var_278]
0x1800d8c85  test    rcx, rcx
0x1800d8c88  setnz   al
0x1800d8c8b  test    al, al
0x1800d8c8d  jz      short loc_1800D8CCE
0x1800d8c8f  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x1800d8c94  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x1800d8c99  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x1800d8c9e  mov     ebx, eax
0x1800d8ca0  test    eax, eax
0x1800d8ca2  jns     short loc_1800D8CAB
0x1800d8ca4  mov     edx, 24Dh
0x1800d8ca9  jmp     short loc_1800D8C4C
0x1800d8cab  lea     rdx, aPkgextensionIn; "PkgExtension\\Index"
0x1800d8cb2  lea     rcx, [rsp+2B0h+var_278]; this
0x1800d8cb7  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800d8cbc  mov     ebx, eax
0x1800d8cbe  test    eax, eax
0x1800d8cc0  jns     short loc_1800D8CC9
0x1800d8cc2  mov     edx, 24Eh
0x1800d8cc7  jmp     short loc_1800D8C4C
0x1800d8cc9  mov     rcx, [rsp+2B0h+var_278]
0x1800d8cce  mov     [rsp+2B0h+var_278], r15
0x1800d8cd3  test    rcx, rcx
0x1800d8cd6  jz      short loc_1800D8CDE
0x1800d8cd8  call    cs:__imp_SRCacheContext_Close
0x1800d8cde  mov     rcx, [rsp+2B0h+var_280]
0x1800d8ce3  mov     [rsp+2B0h+var_280], r15
0x1800d8ce8  test    rcx, rcx
0x1800d8ceb  jz      short loc_1800D8CF3
0x1800d8ced  call    cs:__imp_SRCache_Free
0x1800d8cf3  mov     rcx, [rsp+2B0h+var_250]
0x1800d8cf8  mov     [rsp+2B0h+var_250], r15
0x1800d8cfd  test    rcx, rcx
0x1800d8d00  jz      short loc_1800D8D08
0x1800d8d02  call    cs:__imp_SRCache_Free
0x1800d8d08  mov     rcx, [rsp+2B0h+var_288]
0x1800d8d0d  mov     [rsp+2B0h+var_288], r15
0x1800d8d12  test    rcx, rcx
0x1800d8d15  jz      short loc_1800D8D1D
0x1800d8d17  call    cs:__imp_SRCacheContext_Close
0x1800d8d1d  test    sil, sil
0x1800d8d20  jz      short loc_1800D8D43
0x1800d8d22  lea     rdx, aPkgextension; "PkgExtension"
0x1800d8d29  lea     rcx, [rsp+2B0h+var_290]; this
0x1800d8d2e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800d8d33  mov     ebx, eax
0x1800d8d35  test    eax, eax
0x1800d8d37  jns     short loc_1800D8D43
0x1800d8d39  mov     edx, 253h
0x1800d8d3e  jmp     loc_1800D89D6
0x1800d8d43  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800d8d48  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800d8d4d  test    rcx, rcx
0x1800d8d50  jz      short loc_1800D8D58
0x1800d8d52  call    cs:__imp_SRCacheContext_Close
0x1800d8d58  xor     eax, eax
0x1800d8d5a  mov     rcx, [rbp+1B0h+var_30]
0x1800d8d61  xor     rcx, rsp; StackCookie
0x1800d8d64  call    __security_check_cookie
0x1800d8d69  mov     rbx, [rsp+2B0h+arg_10]
0x1800d8d71  add     rsp, 290h
0x1800d8d78  pop     r15
0x1800d8d7a  pop     r14
0x1800d8d7c  pop     rdi
0x1800d8d7d  pop     rsi
0x1800d8d7e  pop     rbp
0x1800d8d7f  retn
```
