# StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::GetByUserAndPackageFamilyAndName(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,ushort const *,__int64 &)

- ea: `0x18007c350`
- end: `0x18007c69b`
- name: `?GetByUserAndPackageFamilyAndName@DynamicAppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1PEBGAEA_J@Z`
- size: `843`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065450`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034540`
- `0x180034c24`
- `0x18007c350`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c4ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c65d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c4ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007c65d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c453`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c5e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c648`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c672`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c453`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c5e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c648`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007c672`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007c589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007c589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007c3f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007c3f4`

## string_xrefs

- `0x18007c3a2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x18007c431`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x18007c4ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x18007c5c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x18007c411`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007c5a6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007c3e3`: `DynamicAppUriHandlerGroup\Index\UserAndPackageFamilyAndName`
- `0x18007c61b`: `DynamicAppUriHandlerGroup\Index\UserAndPackageFamilyAndName`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::GetByUserAndPackageFamilyAndName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        __int64 *a5)
{
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 v17; // dx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  int *v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  char v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+258h] [rbp+158h]
  __int64 v31; // [rsp+260h] [rbp+160h]
  _BYTE *v32; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a5 = 0;
  if ( !a2 )
  {
    v8 = 186;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)0x80070057LL,
      v23[0]);
    return (unsigned int)v9;
  }
  if ( !a3 )
  {
    v8 = 187;
    goto LABEL_3;
  }
  v11 = *(_QWORD *)a1;
  v25 = v23;
  *(_QWORD *)v23 = 0;
  v26 = 0;
  v27 = 1;
  v9 = SRCacheContext_Open(v11, L"DynamicAppUriHandlerGroup\\Index\\UserAndPackageFamilyAndName", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v9,
      v23[0]);
    v12 = 191;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v9,
      v23[0]);
LABEL_10:
    v13 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return (unsigned int)v9;
  }
  if ( !*(_QWORD *)v23 )
  {
    v9 = -2140733422;
    v12 = 192;
    goto LABEL_9;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a2);
  if ( v9 < 0 )
  {
    v15 = 195;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v9,
      v23[0]);
LABEL_17:
    v16 = v28;
    v28 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_10;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, v14);
  if ( v9 < 0 )
  {
    v15 = 196;
    goto LABEL_16;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a3);
  if ( v9 < 0 )
  {
    v15 = 197;
    goto LABEL_16;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, v17);
  if ( v9 < 0 )
  {
    v15 = 198;
    goto LABEL_16;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a4);
  if ( v9 < 0 )
  {
    v15 = 199;
    goto LABEL_16;
  }
  v25 = (int *)&v24;
  v24 = 0;
  v26 = 0;
  v27 = 1;
  v9 = SRCacheContext_OpenSubContext(*(_QWORD *)v23, v32, 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v9,
      v23[0]);
    v18 = 203;
    goto LABEL_29;
  }
  if ( v24 )
  {
    v9 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v24, 0, a5);
    if ( v9 < 0 )
    {
      v18 = 206;
      goto LABEL_29;
    }
  }
  v9 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v23,
         L"DynamicAppUriHandlerGroup\\Index\\UserAndPackageFamilyAndName");
  if ( v9 < 0 )
  {
    v18 = 209;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v9,
      v23[0]);
    v19 = v24;
    v24 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    goto LABEL_17;
  }
  v20 = v24;
  v24 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  v21 = v28;
  v28 = 0;
  if ( v21 )
    SRCache_Free(v21);
  v22 = *(_QWORD *)v23;
  *(_QWORD *)v23 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
  return 0;
}

```

## disassembly

```asm
0x18007c350  push    rbp
0x18007c352  push    rbx
0x18007c353  push    rsi
0x18007c354  push    rdi
0x18007c355  push    r12
0x18007c357  push    r14
0x18007c359  push    r15
0x18007c35b  lea     rbp, [rsp-180h]
0x18007c363  sub     rsp, 280h
0x18007c36a  mov     rax, cs:__security_cookie
0x18007c371  xor     rax, rsp
0x18007c374  mov     [rbp+1B0h+var_40], rax
0x18007c37b  mov     r14, [rbp+1B0h+arg_20]
0x18007c382  xor     r12d, r12d
0x18007c385  mov     r15, r9
0x18007c388  mov     rdi, r8
0x18007c38b  mov     rsi, rdx
0x18007c38e  mov     [r14], r12
0x18007c391  test    rdx, rdx
0x18007c394  jnz     short loc_18007C3BD
0x18007c396  mov     edx, 0BAh; void *
0x18007c39b  mov     rcx, [rbp+1B8h]; this
0x18007c3a2  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c3a9  mov     ebx, 80070057h
0x18007c3ae  mov     r9d, ebx; char *
0x18007c3b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c3b6  mov     eax, ebx
0x18007c3b8  jmp     loc_18007C67A
0x18007c3bd  test    rdi, rdi
0x18007c3c0  jnz     short loc_18007C3C9
0x18007c3c2  mov     edx, 0BBh
0x18007c3c7  jmp     short loc_18007C39B
0x18007c3c9  mov     rcx, [rcx]
0x18007c3cc  lea     rax, [rsp+2B0h+var_290]
0x18007c3d1  lea     r9, [rsp+2B0h+var_278]
0x18007c3d6  mov     [rsp+2B0h+var_280], rax
0x18007c3db  xor     r8d, r8d
0x18007c3de  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18007c3e3  lea     rdx, aDynamicappurih; "DynamicAppUriHandlerGroup\\Index\\UserA"...
0x18007c3ea  mov     [rsp+2B0h+var_278], r12
0x18007c3ef  mov     [rsp+2B0h+var_270], 1
0x18007c3f4  call    cs:__imp_SRCacheContext_Open
0x18007c3fa  lea     rcx, [rsp+2B0h+var_280]
0x18007c3ff  mov     ebx, eax
0x18007c401  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007c406  test    ebx, ebx
0x18007c408  jns     short loc_18007C45E
0x18007c40a  mov     rcx, [rbp+1B8h]; this
0x18007c411  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c418  mov     r9d, ebx; char *
0x18007c41b  mov     edx, 18Ch; void *
0x18007c420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c425  mov     edx, 0BFh; void *
0x18007c42a  mov     rcx, [rbp+1B8h]; this
0x18007c431  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c438  mov     r9d, ebx; char *
0x18007c43b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c440  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18007c445  mov     qword ptr [rsp+2B0h+var_290], r12
0x18007c44a  test    rcx, rcx
0x18007c44d  jz      loc_18007C3B6
0x18007c453  call    cs:__imp_SRCacheContext_Close
0x18007c459  jmp     loc_18007C3B6
0x18007c45e  cmp     qword ptr [rsp+2B0h+var_290], r12
0x18007c463  setnz   al
0x18007c466  test    al, al
0x18007c468  jnz     short loc_18007C476
0x18007c46a  mov     ebx, 80670012h
0x18007c46f  mov     edx, 0C0h
0x18007c474  jmp     short loc_18007C42A
0x18007c476  xor     edx, edx; Val
0x18007c478  mov     [rsp+2B0h+var_260], r12
0x18007c47d  mov     r8d, 200h; Size
0x18007c483  lea     rcx, [rsp+2B0h+var_258]; void *
0x18007c488  call    memset_0
0x18007c48d  lea     rax, [rsp+2B0h+var_258]
0x18007c492  mov     [rbp+1B0h+var_58], r12
0x18007c499  mov     rdx, rsi; unsigned __int64
0x18007c49c  mov     [rbp+1B0h+var_48], rax
0x18007c4a3  lea     rcx, [rsp+2B0h+var_260]; this
0x18007c4a8  mov     [rbp+1B0h+var_50], 100h
0x18007c4b3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007c4b8  mov     ebx, eax
0x18007c4ba  test    eax, eax
0x18007c4bc  jns     short loc_18007C4F7
0x18007c4be  mov     edx, 0C3h; void *
0x18007c4c3  mov     rcx, [rbp+1B8h]; this
0x18007c4ca  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c4d1  mov     r9d, ebx; char *
0x18007c4d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c4d9  mov     rcx, [rsp+2B0h+var_260]
0x18007c4de  mov     [rsp+2B0h+var_260], r12
0x18007c4e3  test    rcx, rcx
0x18007c4e6  jz      loc_18007C440
0x18007c4ec  call    cs:__imp_SRCache_Free
0x18007c4f2  jmp     loc_18007C440
0x18007c4f7  lea     rcx, [rsp+2B0h+var_260]; this
0x18007c4fc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18007c501  mov     ebx, eax
0x18007c503  test    eax, eax
0x18007c505  jns     short loc_18007C50E
0x18007c507  mov     edx, 0C4h
0x18007c50c  jmp     short loc_18007C4C3
0x18007c50e  mov     rdx, rdi; unsigned __int64
0x18007c511  lea     rcx, [rsp+2B0h+var_260]; this
0x18007c516  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007c51b  mov     ebx, eax
0x18007c51d  test    eax, eax
0x18007c51f  jns     short loc_18007C528
0x18007c521  mov     edx, 0C5h
0x18007c526  jmp     short loc_18007C4C3
0x18007c528  lea     rcx, [rsp+2B0h+var_260]; this
0x18007c52d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18007c532  mov     ebx, eax
0x18007c534  test    eax, eax
0x18007c536  jns     short loc_18007C53F
0x18007c538  mov     edx, 0C6h
0x18007c53d  jmp     short loc_18007C4C3
0x18007c53f  mov     rdx, r15; unsigned __int16 *
0x18007c542  lea     rcx, [rsp+2B0h+var_260]; this
0x18007c547  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18007c54c  mov     ebx, eax
0x18007c54e  test    eax, eax
0x18007c550  jns     short loc_18007C55C
0x18007c552  mov     edx, 0C7h
0x18007c557  jmp     loc_18007C4C3
0x18007c55c  mov     rdx, [rbp+1B0h+var_48]
0x18007c563  lea     rax, [rsp+2B0h+var_288]
0x18007c568  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18007c56d  lea     r9, [rsp+2B0h+var_278]
0x18007c572  xor     r8d, r8d
0x18007c575  mov     [rsp+2B0h+var_280], rax
0x18007c57a  mov     [rsp+2B0h+var_288], r12
0x18007c57f  mov     [rsp+2B0h+var_278], r12
0x18007c584  mov     [rsp+2B0h+var_270], 1
0x18007c589  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007c58f  lea     rcx, [rsp+2B0h+var_280]
0x18007c594  mov     ebx, eax
0x18007c596  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007c59b  test    ebx, ebx
0x18007c59d  jns     short loc_18007C5F3
0x18007c59f  mov     rcx, [rbp+1B8h]; this
0x18007c5a6  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c5ad  mov     r9d, ebx; char *
0x18007c5b0  mov     edx, 1B0h; void *
0x18007c5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c5ba  mov     edx, 0CBh; void *
0x18007c5bf  mov     rcx, [rbp+1B8h]; this
0x18007c5c6  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007c5cd  mov     r9d, ebx; char *
0x18007c5d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c5d5  mov     rcx, [rsp+2B0h+var_288]
0x18007c5da  mov     [rsp+2B0h+var_288], r12
0x18007c5df  test    rcx, rcx
0x18007c5e2  jz      loc_18007C4D9
0x18007c5e8  call    cs:__imp_SRCacheContext_Close
0x18007c5ee  jmp     loc_18007C4D9
0x18007c5f3  cmp     [rsp+2B0h+var_288], r12
0x18007c5f8  setnz   al
0x18007c5fb  test    al, al
0x18007c5fd  jz      short loc_18007C61B
0x18007c5ff  mov     r8, r14; __int64 *
0x18007c602  lea     rcx, [rsp+2B0h+var_288]; this
0x18007c607  xor     edx, edx; int
0x18007c609  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18007c60e  mov     ebx, eax
0x18007c610  test    eax, eax
0x18007c612  jns     short loc_18007C61B
0x18007c614  mov     edx, 0CEh
0x18007c619  jmp     short loc_18007C5BF
0x18007c61b  lea     rdx, aDynamicappurih; "DynamicAppUriHandlerGroup\\Index\\UserA"...
0x18007c622  lea     rcx, [rsp+2B0h+var_290]; this
0x18007c627  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007c62c  mov     ebx, eax
0x18007c62e  test    eax, eax
0x18007c630  jns     short loc_18007C639
0x18007c632  mov     edx, 0D1h
0x18007c637  jmp     short loc_18007C5BF
0x18007c639  mov     rcx, [rsp+2B0h+var_288]
0x18007c63e  mov     [rsp+2B0h+var_288], r12
0x18007c643  test    rcx, rcx
0x18007c646  jz      short loc_18007C64E
0x18007c648  call    cs:__imp_SRCacheContext_Close
0x18007c64e  mov     rcx, [rsp+2B0h+var_260]
0x18007c653  mov     [rsp+2B0h+var_260], r12
0x18007c658  test    rcx, rcx
0x18007c65b  jz      short loc_18007C663
0x18007c65d  call    cs:__imp_SRCache_Free
0x18007c663  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18007c668  mov     qword ptr [rsp+2B0h+var_290], r12
0x18007c66d  test    rcx, rcx
0x18007c670  jz      short loc_18007C678
0x18007c672  call    cs:__imp_SRCacheContext_Close
0x18007c678  xor     eax, eax
0x18007c67a  mov     rcx, [rbp+1B0h+var_40]
0x18007c681  xor     rcx, rsp; StackCookie
0x18007c684  call    __security_check_cookie
0x18007c689  add     rsp, 280h
0x18007c690  pop     r15
0x18007c692  pop     r14
0x18007c694  pop     r12
0x18007c696  pop     rdi
0x18007c697  pop     rsi
0x18007c698  pop     rbx
0x18007c699  pop     rbp
0x18007c69a  retn
```
