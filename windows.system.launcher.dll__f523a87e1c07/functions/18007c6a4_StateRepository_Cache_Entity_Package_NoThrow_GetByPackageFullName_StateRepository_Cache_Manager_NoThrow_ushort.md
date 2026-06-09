# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18007c6a4`
- end: `0x18007c93e`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180066144`
- `0x18007bbe8`
- `0x180099c54`

## callees

- `0x180004cf0`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034540`
- `0x18007c6a4`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c904`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c904`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c75d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c88f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c8ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c919`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c75d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c88f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c8ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c919`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007c830`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007c830`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007c702`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007c702`

## string_xrefs

- `0x18007c71f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007c84d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007c73f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007c7d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007c86d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  int *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  char v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h]
  __int64 v25; // [rsp+260h] [rbp+160h]
  _BYTE *v26; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v21 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v17 = 0;
  v19 = v17;
  v20 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v7 = 1128;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
LABEL_4:
    v8 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v17 )
  {
    v6 = -2140733422;
    v7 = 1129;
    goto LABEL_3;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v17[0]);
LABEL_11:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCache_Free(v11);
    goto LABEL_4;
  }
  v19 = (int *)&v18;
  v18 = 0;
  v20 = 0;
  v21 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v26, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v12 = 1136;
    goto LABEL_15;
  }
  if ( v18 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v18, 0, a3);
    if ( v6 < 0 )
    {
      v12 = 1139;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"Package\\Index\\PackageFullName");
  if ( v6 < 0 )
  {
    v12 = 1142;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v13 = v18;
    v18 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_11;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v22;
  v22 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18007c6a4  push    rbp
0x18007c6a6  push    rbx
0x18007c6a7  push    rsi
0x18007c6a8  push    rdi
0x18007c6a9  push    r14
0x18007c6ab  lea     rbp, [rsp-180h]
0x18007c6b3  sub     rsp, 280h
0x18007c6ba  mov     rax, cs:__security_cookie
0x18007c6c1  xor     rax, rsp
0x18007c6c4  mov     [rbp+1A0h+var_30], rax
0x18007c6cb  xor     r14d, r14d
0x18007c6ce  mov     [rsp+2A0h+var_260], 1
0x18007c6d3  mov     [r8], r14
0x18007c6d6  lea     rax, [rsp+2A0h+var_280]
0x18007c6db  mov     rcx, [rcx]
0x18007c6de  lea     r9, [rsp+2A0h+var_268]
0x18007c6e3  mov     rdi, r8
0x18007c6e6  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18007c6eb  mov     rsi, rdx
0x18007c6ee  mov     [rsp+2A0h+var_270], rax
0x18007c6f3  xor     r8d, r8d
0x18007c6f6  mov     [rsp+2A0h+var_268], r14
0x18007c6fb  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18007c702  call    cs:__imp_SRCacheContext_Open
0x18007c708  lea     rcx, [rsp+2A0h+var_270]
0x18007c70d  mov     ebx, eax
0x18007c70f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007c714  test    ebx, ebx
0x18007c716  jns     short loc_18007C76A
0x18007c718  mov     rcx, [rbp+1A8h]; this
0x18007c71f  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c726  mov     r9d, ebx; char *
0x18007c729  mov     edx, 18Ch; void *
0x18007c72e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c733  mov     edx, 468h; void *
0x18007c738  mov     rcx, [rbp+1A8h]; this
0x18007c73f  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c746  mov     r9d, ebx; char *
0x18007c749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c74e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007c753  mov     qword ptr [rsp+2A0h+var_280], r14
0x18007c758  test    rcx, rcx
0x18007c75b  jz      short loc_18007C763
0x18007c75d  call    cs:__imp_SRCacheContext_Close
0x18007c763  mov     eax, ebx
0x18007c765  jmp     loc_18007C921
0x18007c76a  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18007c76f  setnz   al
0x18007c772  test    al, al
0x18007c774  jnz     short loc_18007C782
0x18007c776  mov     ebx, 80670012h
0x18007c77b  mov     edx, 469h
0x18007c780  jmp     short loc_18007C738
0x18007c782  xor     edx, edx; Val
0x18007c784  mov     [rsp+2A0h+var_250], r14
0x18007c789  mov     r8d, 200h; Size
0x18007c78f  lea     rcx, [rsp+2A0h+var_248]; void *
0x18007c794  call    memset_0
0x18007c799  lea     rax, [rsp+2A0h+var_248]
0x18007c79e  mov     [rbp+1A0h+var_48], r14
0x18007c7a5  mov     rdx, rsi; unsigned __int16 *
0x18007c7a8  mov     [rbp+1A0h+var_38], rax
0x18007c7af  lea     rcx, [rsp+2A0h+var_250]; this
0x18007c7b4  mov     [rbp+1A0h+var_40], 100h
0x18007c7bf  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18007c7c4  mov     ebx, eax
0x18007c7c6  test    eax, eax
0x18007c7c8  jns     short loc_18007C803
0x18007c7ca  mov     rcx, [rbp+1A8h]; this
0x18007c7d1  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c7d8  mov     r9d, eax; char *
0x18007c7db  mov     edx, 46Ch; void *
0x18007c7e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c7e5  mov     rcx, [rsp+2A0h+var_250]
0x18007c7ea  mov     [rsp+2A0h+var_250], r14
0x18007c7ef  test    rcx, rcx
0x18007c7f2  jz      loc_18007C74E
0x18007c7f8  call    cs:__imp_SRCache_Free
0x18007c7fe  jmp     loc_18007C74E
0x18007c803  mov     rdx, [rbp+1A0h+var_38]
0x18007c80a  lea     rax, [rsp+2A0h+var_278]
0x18007c80f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007c814  lea     r9, [rsp+2A0h+var_268]
0x18007c819  xor     r8d, r8d
0x18007c81c  mov     [rsp+2A0h+var_270], rax
0x18007c821  mov     [rsp+2A0h+var_278], r14
0x18007c826  mov     [rsp+2A0h+var_268], r14
0x18007c82b  mov     [rsp+2A0h+var_260], 1
0x18007c830  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007c836  lea     rcx, [rsp+2A0h+var_270]
0x18007c83b  mov     ebx, eax
0x18007c83d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007c842  test    ebx, ebx
0x18007c844  jns     short loc_18007C89A
0x18007c846  mov     rcx, [rbp+1A8h]; this
0x18007c84d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c854  mov     r9d, ebx; char *
0x18007c857  mov     edx, 1B0h; void *
0x18007c85c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c861  mov     edx, 470h; void *
0x18007c866  mov     rcx, [rbp+1A8h]; this
0x18007c86d  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c874  mov     r9d, ebx; char *
0x18007c877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c87c  mov     rcx, [rsp+2A0h+var_278]
0x18007c881  mov     [rsp+2A0h+var_278], r14
0x18007c886  test    rcx, rcx
0x18007c889  jz      loc_18007C7E5
0x18007c88f  call    cs:__imp_SRCacheContext_Close
0x18007c895  jmp     loc_18007C7E5
0x18007c89a  cmp     [rsp+2A0h+var_278], r14
0x18007c89f  setnz   al
0x18007c8a2  test    al, al
0x18007c8a4  jz      short loc_18007C8C2
0x18007c8a6  mov     r8, rdi; __int64 *
0x18007c8a9  lea     rcx, [rsp+2A0h+var_278]; this
0x18007c8ae  xor     edx, edx; int
0x18007c8b0  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18007c8b5  mov     ebx, eax
0x18007c8b7  test    eax, eax
0x18007c8b9  jns     short loc_18007C8C2
0x18007c8bb  mov     edx, 473h
0x18007c8c0  jmp     short loc_18007C866
0x18007c8c2  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18007c8c9  lea     rcx, [rsp+2A0h+var_280]; this
0x18007c8ce  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007c8d3  mov     ebx, eax
0x18007c8d5  test    eax, eax
0x18007c8d7  jns     short loc_18007C8E0
0x18007c8d9  mov     edx, 476h
0x18007c8de  jmp     short loc_18007C866
0x18007c8e0  mov     rcx, [rsp+2A0h+var_278]
0x18007c8e5  mov     [rsp+2A0h+var_278], r14
0x18007c8ea  test    rcx, rcx
0x18007c8ed  jz      short loc_18007C8F5
0x18007c8ef  call    cs:__imp_SRCacheContext_Close
0x18007c8f5  mov     rcx, [rsp+2A0h+var_250]
0x18007c8fa  mov     [rsp+2A0h+var_250], r14
0x18007c8ff  test    rcx, rcx
0x18007c902  jz      short loc_18007C90A
0x18007c904  call    cs:__imp_SRCache_Free
0x18007c90a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007c90f  mov     qword ptr [rsp+2A0h+var_280], r14
0x18007c914  test    rcx, rcx
0x18007c917  jz      short loc_18007C91F
0x18007c919  call    cs:__imp_SRCacheContext_Close
0x18007c91f  xor     eax, eax
0x18007c921  mov     rcx, [rbp+1A0h+var_30]
0x18007c928  xor     rcx, rsp; StackCookie
0x18007c92b  call    __security_check_cookie
0x18007c930  add     rsp, 280h
0x18007c937  pop     r14
0x18007c939  pop     rdi
0x18007c93a  pop     rsi
0x18007c93b  pop     rbx
0x18007c93c  pop     rbp
0x18007c93d  retn
```
