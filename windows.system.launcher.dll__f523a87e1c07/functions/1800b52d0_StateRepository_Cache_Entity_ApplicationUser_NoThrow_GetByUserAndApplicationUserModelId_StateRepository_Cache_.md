# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x1800b52d0`
- end: `0x1800b55d0`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `768`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800b55d8`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034540`
- `0x180034c24`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800b52d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5457`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5594`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5457`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5594`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b53be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b551f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b557f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b55a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b53be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b551f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b557f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b55a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800b54c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800b54c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b535f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b535f`

## string_xrefs

- `0x1800b537c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b54dd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b5314`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800b539c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800b5435`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800b54fd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // dx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int *v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      v20[0]);
    return (unsigned int)v7;
  }
  v9 = *(_QWORD *)a1;
  v22 = v20;
  *(_QWORD *)v20 = 0;
  v23 = 0;
  v24 = 1;
  v7 = SRCacheContext_Open(v9, L"ApplicationUser\\Index\\UserAndApplicationUserModelId", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v20[0]);
    v10 = 425;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v7,
      v20[0]);
LABEL_7:
    v11 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v7;
  }
  if ( !*(_QWORD *)v20 )
  {
    v7 = -2140733422;
    v10 = 426;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  if ( v7 < 0 )
  {
    v13 = 429;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v7,
      v20[0]);
LABEL_14:
    v14 = v25;
    v25 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_7;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v12);
  if ( v7 < 0 )
  {
    v13 = 430;
    goto LABEL_13;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v7 < 0 )
  {
    v13 = 431;
    goto LABEL_13;
  }
  v22 = (int *)&v21;
  v21 = 0;
  v23 = 0;
  v24 = 1;
  v7 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v29, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v20[0]);
    v15 = 435;
    goto LABEL_22;
  }
  if ( v21 )
  {
    v7 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v21, 0, a4);
    if ( v7 < 0 )
    {
      v15 = 438;
      goto LABEL_22;
    }
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"ApplicationUser\\Index\\UserAndApplicationUserModelId");
  if ( v7 < 0 )
  {
    v15 = 441;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v7,
      v20[0]);
    v16 = v21;
    v21 = 0;
    if ( v16 )
      SRCacheContext_Close(v16);
    goto LABEL_14;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v25;
  v25 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x1800b52d0  push    rbp
0x1800b52d2  push    rbx
0x1800b52d3  push    rsi
0x1800b52d4  push    rdi
0x1800b52d5  push    r14
0x1800b52d7  push    r15
0x1800b52d9  lea     rbp, [rsp-188h]
0x1800b52e1  sub     rsp, 288h
0x1800b52e8  mov     rax, cs:__security_cookie
0x1800b52ef  xor     rax, rsp
0x1800b52f2  mov     [rbp+1B0h+var_40], rax
0x1800b52f9  xor     r15d, r15d
0x1800b52fc  mov     rsi, r9
0x1800b52ff  mov     [r9], r15
0x1800b5302  mov     r14, r8
0x1800b5305  mov     rdi, rdx
0x1800b5308  test    rdx, rdx
0x1800b530b  jnz     short loc_1800B5334
0x1800b530d  mov     rcx, [rbp+1B8h]; this
0x1800b5314  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b531b  mov     ebx, 80070057h
0x1800b5320  mov     edx, 1A5h; void *
0x1800b5325  mov     r9d, ebx; char *
0x1800b5328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b532d  mov     eax, ebx
0x1800b532f  jmp     loc_1800B55B1
0x1800b5334  mov     rcx, [rcx]
0x1800b5337  lea     rax, [rsp+2B0h+var_290]
0x1800b533c  lea     r9, [rsp+2B0h+var_278]
0x1800b5341  mov     [rsp+2B0h+var_280], rax
0x1800b5346  xor     r8d, r8d
0x1800b5349  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800b534e  lea     rdx, aApplicationuse_2; "ApplicationUser\\Index\\UserAndApplicat"...
0x1800b5355  mov     [rsp+2B0h+var_278], r15
0x1800b535a  mov     [rsp+2B0h+var_270], 1
0x1800b535f  call    cs:__imp_SRCacheContext_Open
0x1800b5365  lea     rcx, [rsp+2B0h+var_280]
0x1800b536a  mov     ebx, eax
0x1800b536c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b5371  test    ebx, ebx
0x1800b5373  jns     short loc_1800B53C9
0x1800b5375  mov     rcx, [rbp+1B8h]; this
0x1800b537c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5383  mov     r9d, ebx; char *
0x1800b5386  mov     edx, 18Ch; void *
0x1800b538b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5390  mov     edx, 1A9h; void *
0x1800b5395  mov     rcx, [rbp+1B8h]; this
0x1800b539c  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b53a3  mov     r9d, ebx; char *
0x1800b53a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b53ab  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800b53b0  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800b53b5  test    rcx, rcx
0x1800b53b8  jz      loc_1800B532D
0x1800b53be  call    cs:__imp_SRCacheContext_Close
0x1800b53c4  jmp     loc_1800B532D
0x1800b53c9  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800b53ce  setnz   al
0x1800b53d1  test    al, al
0x1800b53d3  jnz     short loc_1800B53E1
0x1800b53d5  mov     ebx, 80670012h
0x1800b53da  mov     edx, 1AAh
0x1800b53df  jmp     short loc_1800B5395
0x1800b53e1  xor     edx, edx; Val
0x1800b53e3  mov     [rsp+2B0h+var_260], r15
0x1800b53e8  mov     r8d, 200h; Size
0x1800b53ee  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800b53f3  call    memset_0
0x1800b53f8  lea     rax, [rsp+2B0h+var_258]
0x1800b53fd  mov     [rbp+1B0h+var_58], r15
0x1800b5404  mov     rdx, rdi; unsigned __int64
0x1800b5407  mov     [rbp+1B0h+var_48], rax
0x1800b540e  lea     rcx, [rsp+2B0h+var_260]; this
0x1800b5413  mov     [rbp+1B0h+var_50], 100h
0x1800b541e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800b5423  mov     ebx, eax
0x1800b5425  test    eax, eax
0x1800b5427  jns     short loc_1800B5462
0x1800b5429  mov     edx, 1ADh; void *
0x1800b542e  mov     rcx, [rbp+1B8h]; this
0x1800b5435  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b543c  mov     r9d, ebx; char *
0x1800b543f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5444  mov     rcx, [rsp+2B0h+var_260]
0x1800b5449  mov     [rsp+2B0h+var_260], r15
0x1800b544e  test    rcx, rcx
0x1800b5451  jz      loc_1800B53AB
0x1800b5457  call    cs:__imp_SRCache_Free
0x1800b545d  jmp     loc_1800B53AB
0x1800b5462  lea     rcx, [rsp+2B0h+var_260]; this
0x1800b5467  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x1800b546c  mov     ebx, eax
0x1800b546e  test    eax, eax
0x1800b5470  jns     short loc_1800B5479
0x1800b5472  mov     edx, 1AEh
0x1800b5477  jmp     short loc_1800B542E
0x1800b5479  mov     rdx, r14; unsigned __int16 *
0x1800b547c  lea     rcx, [rsp+2B0h+var_260]; this
0x1800b5481  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800b5486  mov     ebx, eax
0x1800b5488  test    eax, eax
0x1800b548a  jns     short loc_1800B5493
0x1800b548c  mov     edx, 1AFh
0x1800b5491  jmp     short loc_1800B542E
0x1800b5493  mov     rdx, [rbp+1B0h+var_48]
0x1800b549a  lea     rax, [rsp+2B0h+var_288]
0x1800b549f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800b54a4  lea     r9, [rsp+2B0h+var_278]
0x1800b54a9  xor     r8d, r8d
0x1800b54ac  mov     [rsp+2B0h+var_280], rax
0x1800b54b1  mov     [rsp+2B0h+var_288], r15
0x1800b54b6  mov     [rsp+2B0h+var_278], r15
0x1800b54bb  mov     [rsp+2B0h+var_270], 1
0x1800b54c0  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800b54c6  lea     rcx, [rsp+2B0h+var_280]
0x1800b54cb  mov     ebx, eax
0x1800b54cd  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b54d2  test    ebx, ebx
0x1800b54d4  jns     short loc_1800B552A
0x1800b54d6  mov     rcx, [rbp+1B8h]; this
0x1800b54dd  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b54e4  mov     r9d, ebx; char *
0x1800b54e7  mov     edx, 1B0h; void *
0x1800b54ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54f1  mov     edx, 1B3h; void *
0x1800b54f6  mov     rcx, [rbp+1B8h]; this
0x1800b54fd  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5504  mov     r9d, ebx; char *
0x1800b5507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b550c  mov     rcx, [rsp+2B0h+var_288]
0x1800b5511  mov     [rsp+2B0h+var_288], r15
0x1800b5516  test    rcx, rcx
0x1800b5519  jz      loc_1800B5444
0x1800b551f  call    cs:__imp_SRCacheContext_Close
0x1800b5525  jmp     loc_1800B5444
0x1800b552a  cmp     [rsp+2B0h+var_288], r15
0x1800b552f  setnz   al
0x1800b5532  test    al, al
0x1800b5534  jz      short loc_1800B5552
0x1800b5536  mov     r8, rsi; __int64 *
0x1800b5539  lea     rcx, [rsp+2B0h+var_288]; this
0x1800b553e  xor     edx, edx; int
0x1800b5540  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x1800b5545  mov     ebx, eax
0x1800b5547  test    eax, eax
0x1800b5549  jns     short loc_1800B5552
0x1800b554b  mov     edx, 1B6h
0x1800b5550  jmp     short loc_1800B54F6
0x1800b5552  lea     rdx, aApplicationuse_2; "ApplicationUser\\Index\\UserAndApplicat"...
0x1800b5559  lea     rcx, [rsp+2B0h+var_290]; this
0x1800b555e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b5563  mov     ebx, eax
0x1800b5565  test    eax, eax
0x1800b5567  jns     short loc_1800B5570
0x1800b5569  mov     edx, 1B9h
0x1800b556e  jmp     short loc_1800B54F6
0x1800b5570  mov     rcx, [rsp+2B0h+var_288]
0x1800b5575  mov     [rsp+2B0h+var_288], r15
0x1800b557a  test    rcx, rcx
0x1800b557d  jz      short loc_1800B5585
0x1800b557f  call    cs:__imp_SRCacheContext_Close
0x1800b5585  mov     rcx, [rsp+2B0h+var_260]
0x1800b558a  mov     [rsp+2B0h+var_260], r15
0x1800b558f  test    rcx, rcx
0x1800b5592  jz      short loc_1800B559A
0x1800b5594  call    cs:__imp_SRCache_Free
0x1800b559a  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800b559f  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800b55a4  test    rcx, rcx
0x1800b55a7  jz      short loc_1800B55AF
0x1800b55a9  call    cs:__imp_SRCacheContext_Close
0x1800b55af  xor     eax, eax
0x1800b55b1  mov     rcx, [rbp+1B0h+var_40]
0x1800b55b8  xor     rcx, rsp; StackCookie
0x1800b55bb  call    __security_check_cookie
0x1800b55c0  add     rsp, 288h
0x1800b55c7  pop     r15
0x1800b55c9  pop     r14
0x1800b55cb  pop     rdi
0x1800b55cc  pop     rsi
0x1800b55cd  pop     rbx
0x1800b55ce  pop     rbp
0x1800b55cf  retn
```
