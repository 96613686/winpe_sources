# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x1800a7500`
- end: `0x1800a779a`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180099eb4`

## callees

- `0x1800211f0`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x180072f54`
- `0x1800a7500`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a75b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a76eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a774b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a7775`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a75b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a76eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a774b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a7775`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a755e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a755e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a7654`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a7760`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a7654`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a7760`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a768c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a768c`

## string_xrefs

- `0x1800a757b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a76a9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a759b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800a762d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800a76c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  int *v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  char v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+258h] [rbp+158h]
  __int64 v27; // [rsp+260h] [rbp+160h]
  _BYTE *v28; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v23 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v19 = 0;
  v21 = v19;
  v22 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v19[0]);
    v7 = 193;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v19[0]);
LABEL_4:
    v9 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v9 )
      SRCacheContext_Close(v9, v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v19 )
  {
    v6 = -2140733422;
    v7 = 194;
    goto LABEL_3;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v11,
      v19[0]);
LABEL_11:
    v12 = v24;
    v24 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v21 = (int *)&v20;
  v20 = 0;
  v22 = 0;
  v23 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v28, 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v19[0]);
    v13 = 201;
    goto LABEL_15;
  }
  if ( v20 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v20, 0, a3);
    if ( v6 < 0 )
    {
      v13 = 204;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v19,
         L"PackageFamily\\Index\\PackageFamilyName");
  if ( v6 < 0 )
  {
    v13 = 207;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v19[0]);
    v14 = v20;
    v20 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v8);
    goto LABEL_11;
  }
  v16 = v20;
  v20 = 0;
  if ( v16 )
    SRCacheContext_Close(v16, v15);
  v17 = v24;
  v24 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v19;
  *(_QWORD *)v19 = 0;
  if ( v18 )
    SRCacheContext_Close(v18, v15);
  return 0;
}

```

## disassembly

```asm
0x1800a7500  push    rbp
0x1800a7502  push    rbx
0x1800a7503  push    rsi
0x1800a7504  push    rdi
0x1800a7505  push    r14
0x1800a7507  lea     rbp, [rsp-180h]
0x1800a750f  sub     rsp, 280h
0x1800a7516  mov     rax, cs:__security_cookie
0x1800a751d  xor     rax, rsp
0x1800a7520  mov     [rbp+1A0h+var_30], rax
0x1800a7527  xor     r14d, r14d
0x1800a752a  mov     [rsp+2A0h+var_260], 1
0x1800a752f  mov     [r8], r14
0x1800a7532  lea     rax, [rsp+2A0h+var_280]
0x1800a7537  mov     rcx, [rcx]
0x1800a753a  lea     r9, [rsp+2A0h+var_268]
0x1800a753f  mov     rdi, r8
0x1800a7542  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x1800a7547  mov     rsi, rdx
0x1800a754a  mov     [rsp+2A0h+var_270], rax
0x1800a754f  xor     r8d, r8d
0x1800a7552  mov     [rsp+2A0h+var_268], r14
0x1800a7557  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x1800a755e  call    cs:__imp_SRCacheContext_Open
0x1800a7564  lea     rcx, [rsp+2A0h+var_270]
0x1800a7569  mov     ebx, eax
0x1800a756b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a7570  test    ebx, ebx
0x1800a7572  jns     short loc_1800A75C6
0x1800a7574  mov     rcx, [rbp+1A8h]; this
0x1800a757b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a7582  mov     r9d, ebx; char *
0x1800a7585  mov     edx, 18Ch; void *
0x1800a758a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a758f  mov     edx, 0C1h; void *
0x1800a7594  mov     rcx, [rbp+1A8h]; this
0x1800a759b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a75a2  mov     r9d, ebx; char *
0x1800a75a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a75aa  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a75af  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800a75b4  test    rcx, rcx
0x1800a75b7  jz      short loc_1800A75BF
0x1800a75b9  call    cs:__imp_SRCacheContext_Close
0x1800a75bf  mov     eax, ebx
0x1800a75c1  jmp     loc_1800A777D
0x1800a75c6  cmp     qword ptr [rsp+2A0h+var_280], r14
0x1800a75cb  setnz   al
0x1800a75ce  test    al, al
0x1800a75d0  jnz     short loc_1800A75DE
0x1800a75d2  mov     ebx, 80670012h
0x1800a75d7  mov     edx, 0C2h
0x1800a75dc  jmp     short loc_1800A7594
0x1800a75de  xor     edx, edx; Val
0x1800a75e0  mov     [rsp+2A0h+var_250], r14
0x1800a75e5  mov     r8d, 200h; Size
0x1800a75eb  lea     rcx, [rsp+2A0h+var_248]; void *
0x1800a75f0  call    memset_0
0x1800a75f5  lea     rax, [rsp+2A0h+var_248]
0x1800a75fa  mov     [rbp+1A0h+var_48], r14
0x1800a7601  mov     rdx, rsi; unsigned __int16 *
0x1800a7604  mov     [rbp+1A0h+var_38], rax
0x1800a760b  lea     rcx, [rsp+2A0h+var_250]; this
0x1800a7610  mov     [rbp+1A0h+var_40], 100h
0x1800a761b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a7620  mov     ebx, eax
0x1800a7622  test    eax, eax
0x1800a7624  jns     short loc_1800A765F
0x1800a7626  mov     rcx, [rbp+1A8h]; this
0x1800a762d  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a7634  mov     r9d, eax; char *
0x1800a7637  mov     edx, 0C5h; void *
0x1800a763c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7641  mov     rcx, [rsp+2A0h+var_250]
0x1800a7646  mov     [rsp+2A0h+var_250], r14
0x1800a764b  test    rcx, rcx
0x1800a764e  jz      loc_1800A75AA
0x1800a7654  call    cs:__imp_SRCache_Free
0x1800a765a  jmp     loc_1800A75AA
0x1800a765f  mov     rdx, [rbp+1A0h+var_38]
0x1800a7666  lea     rax, [rsp+2A0h+var_278]
0x1800a766b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a7670  lea     r9, [rsp+2A0h+var_268]
0x1800a7675  xor     r8d, r8d
0x1800a7678  mov     [rsp+2A0h+var_270], rax
0x1800a767d  mov     [rsp+2A0h+var_278], r14
0x1800a7682  mov     [rsp+2A0h+var_268], r14
0x1800a7687  mov     [rsp+2A0h+var_260], 1
0x1800a768c  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800a7692  lea     rcx, [rsp+2A0h+var_270]
0x1800a7697  mov     ebx, eax
0x1800a7699  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a769e  test    ebx, ebx
0x1800a76a0  jns     short loc_1800A76F6
0x1800a76a2  mov     rcx, [rbp+1A8h]; this
0x1800a76a9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a76b0  mov     r9d, ebx; char *
0x1800a76b3  mov     edx, 1B0h; void *
0x1800a76b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a76bd  mov     edx, 0C9h; void *
0x1800a76c2  mov     rcx, [rbp+1A8h]; this
0x1800a76c9  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a76d0  mov     r9d, ebx; char *
0x1800a76d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a76d8  mov     rcx, [rsp+2A0h+var_278]
0x1800a76dd  mov     [rsp+2A0h+var_278], r14
0x1800a76e2  test    rcx, rcx
0x1800a76e5  jz      loc_1800A7641
0x1800a76eb  call    cs:__imp_SRCacheContext_Close
0x1800a76f1  jmp     loc_1800A7641
0x1800a76f6  cmp     [rsp+2A0h+var_278], r14
0x1800a76fb  setnz   al
0x1800a76fe  test    al, al
0x1800a7700  jz      short loc_1800A771E
0x1800a7702  mov     r8, rdi; __int64 *
0x1800a7705  lea     rcx, [rsp+2A0h+var_278]; this
0x1800a770a  xor     edx, edx; int
0x1800a770c  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x1800a7711  mov     ebx, eax
0x1800a7713  test    eax, eax
0x1800a7715  jns     short loc_1800A771E
0x1800a7717  mov     edx, 0CCh
0x1800a771c  jmp     short loc_1800A76C2
0x1800a771e  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x1800a7725  lea     rcx, [rsp+2A0h+var_280]; this
0x1800a772a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a772f  mov     ebx, eax
0x1800a7731  test    eax, eax
0x1800a7733  jns     short loc_1800A773C
0x1800a7735  mov     edx, 0CFh
0x1800a773a  jmp     short loc_1800A76C2
0x1800a773c  mov     rcx, [rsp+2A0h+var_278]
0x1800a7741  mov     [rsp+2A0h+var_278], r14
0x1800a7746  test    rcx, rcx
0x1800a7749  jz      short loc_1800A7751
0x1800a774b  call    cs:__imp_SRCacheContext_Close
0x1800a7751  mov     rcx, [rsp+2A0h+var_250]
0x1800a7756  mov     [rsp+2A0h+var_250], r14
0x1800a775b  test    rcx, rcx
0x1800a775e  jz      short loc_1800A7766
0x1800a7760  call    cs:__imp_SRCache_Free
0x1800a7766  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a776b  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800a7770  test    rcx, rcx
0x1800a7773  jz      short loc_1800A777B
0x1800a7775  call    cs:__imp_SRCacheContext_Close
0x1800a777b  xor     eax, eax
0x1800a777d  mov     rcx, [rbp+1A0h+var_30]
0x1800a7784  xor     rcx, rsp; StackCookie
0x1800a7787  call    __security_check_cookie
0x1800a778c  add     rsp, 280h
0x1800a7793  pop     r14
0x1800a7795  pop     rdi
0x1800a7796  pop     rsi
0x1800a7797  pop     rbx
0x1800a7798  pop     rbp
0x1800a7799  retn
```
