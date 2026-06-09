# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18001c4b4`
- end: `0x18001c7f8`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `836`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180037d54`

## callees

- `0x180008c58`
- `0x18000aa58`
- `0x180018700`
- `0x18001c4b4`
- `0x18001caec`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c543`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c543`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c6ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c6ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c5a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c749`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c7a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c7d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c5a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c749`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c7a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c7d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c63b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c7bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c63b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c7bc`

## string_xrefs

- `0x18001c560`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c707`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c668`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001c4f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001c580`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001c619`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001c727`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  bool v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  int *v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  char v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h]
  __int64 v30; // [rsp+260h] [rbp+160h]
  _BYTE *v31; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return (unsigned int)v7;
  }
  v9 = *(_QWORD *)a1;
  v24 = v22;
  *(_QWORD *)v22 = 0;
  v25 = 0;
  v26 = 1;
  v7 = SRCacheContext_Open(v9, L"PackageExternalLocation\\Index\\UserAndPackage", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v22[0]);
    v10 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      v22[0]);
LABEL_7:
    v11 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v7;
  }
  if ( !*(_QWORD *)v22 )
  {
    v7 = -2140733422;
    v10 = 186;
    goto LABEL_6;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a2);
  if ( v7 < 0 )
  {
    v13 = 189;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      v22[0]);
LABEL_14:
    v14 = v27;
    v27 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_7;
  }
  v15 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v27, v29 + 2, v12);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v15,
      v22[0]);
    v13 = 190;
    goto LABEL_13;
  }
  *(_DWORD *)&v31[2 * v29++] = 94;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v7 < 0 )
  {
    v13 = 191;
    goto LABEL_13;
  }
  v24 = (int *)&v23;
  v23 = 0;
  v25 = 0;
  v26 = 1;
  v7 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v31, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v22[0]);
    v17 = 195;
    goto LABEL_22;
  }
  if ( v23 )
  {
    v7 = StateRepository::Cache::Context_NoThrow::EnumerateData(
           (StateRepository::Cache::Context_NoThrow *)&v23,
           v16,
           a4);
    if ( v7 < 0 )
    {
      v17 = 198;
      goto LABEL_22;
    }
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v22,
         L"PackageExternalLocation\\Index\\UserAndPackage");
  if ( v7 < 0 )
  {
    v17 = 201;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      v22[0]);
    v18 = v23;
    v23 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    goto LABEL_14;
  }
  v19 = v23;
  v23 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  v20 = v27;
  v27 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  return 0;
}

```

## disassembly

```asm
0x18001c4b4  push    rbp
0x18001c4b6  push    rbx
0x18001c4b7  push    rsi
0x18001c4b8  push    rdi
0x18001c4b9  push    r14
0x18001c4bb  push    r15
0x18001c4bd  lea     rbp, [rsp-188h]
0x18001c4c5  sub     rsp, 288h
0x18001c4cc  mov     rax, cs:__security_cookie
0x18001c4d3  xor     rax, rsp
0x18001c4d6  mov     [rbp+1B0h+var_40], rax
0x18001c4dd  xor     r15d, r15d
0x18001c4e0  mov     rdi, r9
0x18001c4e3  mov     [r9], r15
0x18001c4e6  mov     rsi, r8
0x18001c4e9  mov     r14, rdx
0x18001c4ec  test    r8, r8
0x18001c4ef  jnz     short loc_18001C518
0x18001c4f1  mov     rcx, [rbp+1B8h]; this
0x18001c4f8  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c4ff  mov     ebx, 80070057h
0x18001c504  mov     edx, 0B5h; void *
0x18001c509  mov     r9d, ebx; char *
0x18001c50c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c511  mov     eax, ebx
0x18001c513  jmp     loc_18001C7D9
0x18001c518  mov     rcx, [rcx]
0x18001c51b  lea     rax, [rsp+2B0h+var_290]
0x18001c520  lea     r9, [rsp+2B0h+var_278]
0x18001c525  mov     [rsp+2B0h+var_280], rax
0x18001c52a  xor     r8d, r8d
0x18001c52d  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18001c532  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18001c539  mov     [rsp+2B0h+var_278], r15
0x18001c53e  mov     [rsp+2B0h+var_270], 1
0x18001c543  call    cs:__imp_SRCacheContext_Open
0x18001c549  lea     rcx, [rsp+2B0h+var_280]
0x18001c54e  mov     ebx, eax
0x18001c550  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c555  test    ebx, ebx
0x18001c557  jns     short loc_18001C5AD
0x18001c559  mov     rcx, [rbp+1B8h]; this
0x18001c560  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c567  mov     r9d, ebx; char *
0x18001c56a  mov     edx, 18Ch; void *
0x18001c56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c574  mov     edx, 0B9h; void *
0x18001c579  mov     rcx, [rbp+1B8h]; this
0x18001c580  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c587  mov     r9d, ebx; char *
0x18001c58a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c58f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001c594  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001c599  test    rcx, rcx
0x18001c59c  jz      loc_18001C511
0x18001c5a2  call    cs:__imp_SRCacheContext_Close
0x18001c5a8  jmp     loc_18001C511
0x18001c5ad  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18001c5b2  setnz   al
0x18001c5b5  test    al, al
0x18001c5b7  jnz     short loc_18001C5C5
0x18001c5b9  mov     ebx, 80670012h
0x18001c5be  mov     edx, 0BAh
0x18001c5c3  jmp     short loc_18001C579
0x18001c5c5  xor     edx, edx; Val
0x18001c5c7  mov     [rsp+2B0h+var_260], r15
0x18001c5cc  mov     r8d, 200h; Size
0x18001c5d2  lea     rcx, [rsp+2B0h+var_258]; void *
0x18001c5d7  call    memset_0
0x18001c5dc  lea     rax, [rsp+2B0h+var_258]
0x18001c5e1  mov     [rbp+1B0h+var_58], r15
0x18001c5e8  mov     rdx, r14; unsigned __int64
0x18001c5eb  mov     [rbp+1B0h+var_48], rax
0x18001c5f2  lea     rcx, [rsp+2B0h+var_260]; this
0x18001c5f7  mov     [rbp+1B0h+var_50], 100h
0x18001c602  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001c607  mov     ebx, eax
0x18001c609  test    eax, eax
0x18001c60b  jns     short loc_18001C646
0x18001c60d  mov     edx, 0BDh; void *
0x18001c612  mov     rcx, [rbp+1B8h]; this
0x18001c619  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c620  mov     r9d, ebx; char *
0x18001c623  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c628  mov     rcx, [rsp+2B0h+var_260]
0x18001c62d  mov     [rsp+2B0h+var_260], r15
0x18001c632  test    rcx, rcx
0x18001c635  jz      loc_18001C58F
0x18001c63b  call    cs:__imp_SRCache_Free
0x18001c641  jmp     loc_18001C58F
0x18001c646  mov     rdx, [rbp+1B0h+var_58]
0x18001c64d  lea     rcx, [rsp+2B0h+var_260]; this
0x18001c652  add     rdx, 2; unsigned __int64
0x18001c656  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18001c65b  mov     ebx, eax
0x18001c65d  test    eax, eax
0x18001c65f  jns     short loc_18001C683
0x18001c661  mov     rcx, [rbp+1B8h]; this
0x18001c668  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c66f  mov     r9d, eax; char *
0x18001c672  mov     edx, 16Dh; void *
0x18001c677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c67c  mov     edx, 0BEh
0x18001c681  jmp     short loc_18001C612
0x18001c683  mov     r8, [rbp+1B0h+var_58]
0x18001c68a  mov     rdx, rsi; unsigned __int64
0x18001c68d  mov     rcx, [rbp+1B0h+var_48]
0x18001c694  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x18001c69c  lea     rcx, [rsp+2B0h+var_260]; this
0x18001c6a1  inc     [rbp+1B0h+var_58]
0x18001c6a8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001c6ad  mov     ebx, eax
0x18001c6af  test    eax, eax
0x18001c6b1  jns     short loc_18001C6BD
0x18001c6b3  mov     edx, 0BFh
0x18001c6b8  jmp     loc_18001C612
0x18001c6bd  mov     rdx, [rbp+1B0h+var_48]
0x18001c6c4  lea     rax, [rsp+2B0h+var_288]
0x18001c6c9  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001c6ce  lea     r9, [rsp+2B0h+var_278]
0x18001c6d3  xor     r8d, r8d
0x18001c6d6  mov     [rsp+2B0h+var_280], rax
0x18001c6db  mov     [rsp+2B0h+var_288], r15
0x18001c6e0  mov     [rsp+2B0h+var_278], r15
0x18001c6e5  mov     [rsp+2B0h+var_270], 1
0x18001c6ea  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001c6f0  lea     rcx, [rsp+2B0h+var_280]
0x18001c6f5  mov     ebx, eax
0x18001c6f7  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c6fc  test    ebx, ebx
0x18001c6fe  jns     short loc_18001C754
0x18001c700  mov     rcx, [rbp+1B8h]; this
0x18001c707  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c70e  mov     r9d, ebx; char *
0x18001c711  mov     edx, 1B0h; void *
0x18001c716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c71b  mov     edx, 0C3h; void *
0x18001c720  mov     rcx, [rbp+1B8h]; this
0x18001c727  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c72e  mov     r9d, ebx; char *
0x18001c731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c736  mov     rcx, [rsp+2B0h+var_288]
0x18001c73b  mov     [rsp+2B0h+var_288], r15
0x18001c740  test    rcx, rcx
0x18001c743  jz      loc_18001C628
0x18001c749  call    cs:__imp_SRCacheContext_Close
0x18001c74f  jmp     loc_18001C628
0x18001c754  cmp     [rsp+2B0h+var_288], r15
0x18001c759  setnz   al
0x18001c75c  test    al, al
0x18001c75e  jz      short loc_18001C77A
0x18001c760  mov     r8, rdi; __int64 *
0x18001c763  lea     rcx, [rsp+2B0h+var_288]; this
0x18001c768  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18001c76d  mov     ebx, eax
0x18001c76f  test    eax, eax
0x18001c771  jns     short loc_18001C77A
0x18001c773  mov     edx, 0C6h
0x18001c778  jmp     short loc_18001C720
0x18001c77a  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18001c781  lea     rcx, [rsp+2B0h+var_290]; this
0x18001c786  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001c78b  mov     ebx, eax
0x18001c78d  test    eax, eax
0x18001c78f  jns     short loc_18001C798
0x18001c791  mov     edx, 0C9h
0x18001c796  jmp     short loc_18001C720
0x18001c798  mov     rcx, [rsp+2B0h+var_288]
0x18001c79d  mov     [rsp+2B0h+var_288], r15
0x18001c7a2  test    rcx, rcx
0x18001c7a5  jz      short loc_18001C7AD
0x18001c7a7  call    cs:__imp_SRCacheContext_Close
0x18001c7ad  mov     rcx, [rsp+2B0h+var_260]
0x18001c7b2  mov     [rsp+2B0h+var_260], r15
0x18001c7b7  test    rcx, rcx
0x18001c7ba  jz      short loc_18001C7C2
0x18001c7bc  call    cs:__imp_SRCache_Free
0x18001c7c2  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001c7c7  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001c7cc  test    rcx, rcx
0x18001c7cf  jz      short loc_18001C7D7
0x18001c7d1  call    cs:__imp_SRCacheContext_Close
0x18001c7d7  xor     eax, eax
0x18001c7d9  mov     rcx, [rbp+1B0h+var_40]
0x18001c7e0  xor     rcx, rsp; StackCookie
0x18001c7e3  call    __security_check_cookie
0x18001c7e8  add     rsp, 288h
0x18001c7ef  pop     r15
0x18001c7f1  pop     r14
0x18001c7f3  pop     rdi
0x18001c7f4  pop     rsi
0x18001c7f5  pop     rbx
0x18001c7f6  pop     rbp
0x18001c7f7  retn
```
