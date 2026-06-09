# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x18007d254`
- end: `0x18007d56d`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `793`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065450`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034c24`
- `0x18007d254`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d52a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007d52a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d2c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d357`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d3a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d53f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d2c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d357`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d3a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007d53f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007d487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007d487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007d2fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007d2fc`

## string_xrefs

- `0x18007d319`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007d4a4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007d298`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007d334`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007d377`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007d402`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007d4e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007d2de`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x18007d4cb`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x18007d446`: `windows.appUriHandler`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v7;
  }
  v9 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v9 )
    SRCacheContext_Close(v9);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v10 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v11 = SRCacheContext_Open(v10, L"ApplicationExtension\\Index\\ApplicationAndCategory", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
LABEL_8:
    v12 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v11;
  }
  if ( !*(_QWORD *)v21 )
  {
    v7 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v13 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v7;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v11 < 0 )
  {
    v15 = 759;
    goto LABEL_17;
  }
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v14);
  if ( v11 < 0 )
  {
    v15 = 760;
    goto LABEL_17;
  }
  v11 = StateRepository::Cache::Key_NoThrow::Append(
          (StateRepository::Cache::Key_NoThrow *)&v25,
          L"windows.appUriHandler");
  if ( v11 < 0 )
  {
    v15 = 761;
    goto LABEL_17;
  }
  v22 = (int *)this;
  v23 = 0;
  v24 = 1;
  v11 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    v15 = 764;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    v16 = v25;
    v25 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v21,
          L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCache_Free(v18);
    goto LABEL_13;
  }
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x18007d254  mov     [rsp-8+arg_18], rbx
0x18007d259  push    rbp
0x18007d25a  push    rsi
0x18007d25b  push    rdi
0x18007d25c  push    r14
0x18007d25e  push    r15
0x18007d260  lea     rbp, [rsp-170h]
0x18007d268  sub     rsp, 270h
0x18007d26f  mov     rax, cs:__security_cookie
0x18007d276  xor     rax, rsp
0x18007d279  mov     [rbp+190h+var_30], rax
0x18007d280  xor     r15d, r15d
0x18007d283  mov     r14, r8
0x18007d286  mov     rsi, rdx
0x18007d289  mov     rbx, rcx
0x18007d28c  test    r8, r8
0x18007d28f  jnz     short loc_18007D2B8
0x18007d291  mov     rcx, [rbp+198h]; this
0x18007d298  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d29f  mov     ebx, 80070057h
0x18007d2a4  mov     edx, 2EDh; void *
0x18007d2a9  mov     r9d, ebx; char *
0x18007d2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d2b1  mov     eax, ebx
0x18007d2b3  jmp     loc_18007D547
0x18007d2b8  mov     rcx, [rcx]
0x18007d2bb  mov     [rbx], r15
0x18007d2be  test    rcx, rcx
0x18007d2c1  jz      short loc_18007D2C9
0x18007d2c3  call    cs:__imp_SRCacheContext_Close
0x18007d2c9  mov     [rbx+8], r15d
0x18007d2cd  lea     rax, [rsp+290h+var_270]
0x18007d2d2  mov     [rbx+10h], r15
0x18007d2d6  lea     r9, [rsp+290h+var_260]
0x18007d2db  mov     rcx, [rsi]
0x18007d2de  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x18007d2e5  xor     r8d, r8d
0x18007d2e8  mov     [rsp+290h+var_268], rax
0x18007d2ed  mov     qword ptr [rsp+290h+var_270], r15; int
0x18007d2f2  mov     [rsp+290h+var_260], r15
0x18007d2f7  mov     [rsp+290h+var_258], 1
0x18007d2fc  call    cs:__imp_SRCacheContext_Open
0x18007d302  lea     rcx, [rsp+290h+var_268]
0x18007d307  mov     edi, eax
0x18007d309  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007d30e  test    edi, edi
0x18007d310  jns     short loc_18007D364
0x18007d312  mov     rcx, [rbp+198h]; this
0x18007d319  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d320  mov     r9d, edi; char *
0x18007d323  mov     edx, 18Ch; void *
0x18007d328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d32d  mov     rcx, [rbp+198h]; this
0x18007d334  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d33b  mov     r9d, edi; char *
0x18007d33e  mov     edx, 2F3h; void *
0x18007d343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d348  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007d34d  mov     qword ptr [rsp+290h+var_270], r15
0x18007d352  test    rcx, rcx
0x18007d355  jz      short loc_18007D35D
0x18007d357  call    cs:__imp_SRCacheContext_Close
0x18007d35d  mov     eax, edi
0x18007d35f  jmp     loc_18007D547
0x18007d364  cmp     qword ptr [rsp+290h+var_270], r15
0x18007d369  setnz   al
0x18007d36c  test    al, al
0x18007d36e  jnz     short loc_18007D3AE
0x18007d370  mov     rcx, [rbp+198h]; this
0x18007d377  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d37e  mov     ebx, 80670012h
0x18007d383  mov     edx, 2F4h; void *
0x18007d388  mov     r9d, ebx; char *
0x18007d38b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d390  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007d395  mov     qword ptr [rsp+290h+var_270], r15
0x18007d39a  test    rcx, rcx
0x18007d39d  jz      loc_18007D2B1
0x18007d3a3  call    cs:__imp_SRCacheContext_Close
0x18007d3a9  jmp     loc_18007D2B1
0x18007d3ae  xor     edx, edx; Val
0x18007d3b0  mov     [rsp+290h+var_250], r15
0x18007d3b5  mov     r8d, 200h; Size
0x18007d3bb  lea     rcx, [rsp+290h+var_248]; void *
0x18007d3c0  call    memset_0
0x18007d3c5  lea     rax, [rsp+290h+var_248]
0x18007d3ca  mov     [rbp+190h+var_48], r15
0x18007d3d1  mov     rdx, r14; unsigned __int64
0x18007d3d4  mov     [rbp+190h+var_38], rax
0x18007d3db  lea     rcx, [rsp+290h+var_250]; this
0x18007d3e0  mov     [rbp+190h+var_40], 100h
0x18007d3eb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007d3f0  mov     edi, eax
0x18007d3f2  test    eax, eax
0x18007d3f4  jns     short loc_18007D42F
0x18007d3f6  mov     edx, 2F7h; void *
0x18007d3fb  mov     rcx, [rbp+198h]; this
0x18007d402  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d409  mov     r9d, edi; char *
0x18007d40c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d411  mov     rcx, [rsp+290h+var_250]
0x18007d416  mov     [rsp+290h+var_250], r15
0x18007d41b  test    rcx, rcx
0x18007d41e  jz      loc_18007D348
0x18007d424  call    cs:__imp_SRCache_Free
0x18007d42a  jmp     loc_18007D348
0x18007d42f  lea     rcx, [rsp+290h+var_250]; this
0x18007d434  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18007d439  mov     edi, eax
0x18007d43b  test    eax, eax
0x18007d43d  jns     short loc_18007D446
0x18007d43f  mov     edx, 2F8h
0x18007d444  jmp     short loc_18007D3FB
0x18007d446  lea     rdx, aWindowsAppurih_0; "windows.appUriHandler"
0x18007d44d  lea     rcx, [rsp+290h+var_250]; this
0x18007d452  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18007d457  mov     edi, eax
0x18007d459  test    eax, eax
0x18007d45b  jns     short loc_18007D464
0x18007d45d  mov     edx, 2F9h
0x18007d462  jmp     short loc_18007D3FB
0x18007d464  mov     rdx, [rbp+190h+var_38]
0x18007d46b  lea     r9, [rsp+290h+var_260]
0x18007d470  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007d475  xor     r8d, r8d
0x18007d478  mov     [rsp+290h+var_268], rbx
0x18007d47d  mov     [rsp+290h+var_260], r15
0x18007d482  mov     [rsp+290h+var_258], 1
0x18007d487  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007d48d  lea     rcx, [rsp+290h+var_268]
0x18007d492  mov     edi, eax
0x18007d494  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007d499  test    edi, edi
0x18007d49b  jns     short loc_18007D4C2
0x18007d49d  mov     rcx, [rbp+198h]; this
0x18007d4a4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d4ab  mov     r9d, edi; char *
0x18007d4ae  mov     edx, 1B0h; void *
0x18007d4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d4b8  mov     edx, 2FCh
0x18007d4bd  jmp     loc_18007D3FB
0x18007d4c2  cmp     [rbx], r15
0x18007d4c5  jz      short loc_18007D4CB
0x18007d4c7  mov     [rbx+10h], rsi
0x18007d4cb  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x18007d4d2  lea     rcx, [rsp+290h+var_270]; this
0x18007d4d7  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007d4dc  mov     ebx, eax
0x18007d4de  test    eax, eax
0x18007d4e0  jns     short loc_18007D51B
0x18007d4e2  mov     rcx, [rbp+198h]; this
0x18007d4e9  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007d4f0  mov     r9d, eax; char *
0x18007d4f3  mov     edx, 302h; void *
0x18007d4f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d4fd  mov     rcx, [rsp+290h+var_250]
0x18007d502  mov     [rsp+290h+var_250], r15
0x18007d507  test    rcx, rcx
0x18007d50a  jz      loc_18007D390
0x18007d510  call    cs:__imp_SRCache_Free
0x18007d516  jmp     loc_18007D390
0x18007d51b  mov     rcx, [rsp+290h+var_250]
0x18007d520  mov     [rsp+290h+var_250], r15
0x18007d525  test    rcx, rcx
0x18007d528  jz      short loc_18007D530
0x18007d52a  call    cs:__imp_SRCache_Free
0x18007d530  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007d535  mov     qword ptr [rsp+290h+var_270], r15
0x18007d53a  test    rcx, rcx
0x18007d53d  jz      short loc_18007D545
0x18007d53f  call    cs:__imp_SRCacheContext_Close
0x18007d545  xor     eax, eax
0x18007d547  mov     rcx, [rbp+190h+var_30]
0x18007d54e  xor     rcx, rsp; StackCookie
0x18007d551  call    __security_check_cookie
0x18007d556  mov     rbx, [rsp+290h+arg_18]
0x18007d55e  add     rsp, 270h
0x18007d565  pop     r15
0x18007d567  pop     r14
0x18007d569  pop     rdi
0x18007d56a  pop     rsi
0x18007d56b  pop     rbp
0x18007d56c  retn
```
