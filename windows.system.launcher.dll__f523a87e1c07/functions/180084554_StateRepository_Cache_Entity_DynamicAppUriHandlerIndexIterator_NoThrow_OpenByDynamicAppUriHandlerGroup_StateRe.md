# StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByDynamicAppUriHandlerGroup(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180084554`
- end: `0x180084838`
- name: `?OpenByDynamicAppUriHandlerGroup@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800674cc`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180084554`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084724`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800847db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800847f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084724`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800847db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800847f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800845c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084657`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800846a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008480a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800845c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084657`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800846a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008480a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180084752`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180084752`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800845fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800845fc`

## string_xrefs

- `0x180084598`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180084634`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180084677`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180084702`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x1800847b4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180084619`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18008476f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800845de`: `DynamicAppUriHandler\Index\DynamicAppUriHandlerGroup`
- `0x180084796`: `DynamicAppUriHandler\Index\DynamicAppUriHandlerGroup`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByDynamicAppUriHandlerGroup(
        StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x298,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)0x80070057LL,
      v19[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v20 = v19;
  *(_QWORD *)v19 = 0;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_Open(v9, L"DynamicAppUriHandler\\Index\\DynamicAppUriHandlerGroup", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
LABEL_8:
    v11 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v19 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v12 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v10 < 0 )
  {
    v13 = 674;
    goto LABEL_17;
  }
  v20 = (int *)this;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v13 = 677;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v19,
          L"DynamicAppUriHandler\\Index\\DynamicAppUriHandlerGroup");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_13;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = *(_QWORD *)v19;
  *(_QWORD *)v19 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x180084554  mov     [rsp-8+arg_18], rbx
0x180084559  push    rbp
0x18008455a  push    rsi
0x18008455b  push    rdi
0x18008455c  push    r14
0x18008455e  push    r15
0x180084560  lea     rbp, [rsp-170h]
0x180084568  sub     rsp, 270h
0x18008456f  mov     rax, cs:__security_cookie
0x180084576  xor     rax, rsp
0x180084579  mov     [rbp+190h+var_30], rax
0x180084580  xor     r15d, r15d
0x180084583  mov     r14, r8
0x180084586  mov     rsi, rdx
0x180084589  mov     rbx, rcx
0x18008458c  test    r8, r8
0x18008458f  jnz     short loc_1800845B8
0x180084591  mov     rcx, [rbp+198h]; this
0x180084598  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008459f  mov     ebx, 80070057h
0x1800845a4  mov     edx, 298h; void *
0x1800845a9  mov     r9d, ebx; char *
0x1800845ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800845b1  mov     eax, ebx
0x1800845b3  jmp     loc_180084812
0x1800845b8  mov     rcx, [rcx]
0x1800845bb  mov     [rbx], r15
0x1800845be  test    rcx, rcx
0x1800845c1  jz      short loc_1800845C9
0x1800845c3  call    cs:__imp_SRCacheContext_Close
0x1800845c9  mov     [rbx+8], r15d
0x1800845cd  lea     rax, [rsp+290h+var_270]
0x1800845d2  mov     [rbx+10h], r15
0x1800845d6  lea     r9, [rsp+290h+var_260]
0x1800845db  mov     rcx, [rsi]
0x1800845de  lea     rdx, aDynamicappurih_4; "DynamicAppUriHandler\\Index\\DynamicApp"...
0x1800845e5  xor     r8d, r8d
0x1800845e8  mov     [rsp+290h+var_268], rax
0x1800845ed  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800845f2  mov     [rsp+290h+var_260], r15
0x1800845f7  mov     [rsp+290h+var_258], 1
0x1800845fc  call    cs:__imp_SRCacheContext_Open
0x180084602  lea     rcx, [rsp+290h+var_268]
0x180084607  mov     edi, eax
0x180084609  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18008460e  test    edi, edi
0x180084610  jns     short loc_180084664
0x180084612  mov     rcx, [rbp+198h]; this
0x180084619  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180084620  mov     r9d, edi; char *
0x180084623  mov     edx, 18Ch; void *
0x180084628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008462d  mov     rcx, [rbp+198h]; this
0x180084634  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008463b  mov     r9d, edi; char *
0x18008463e  mov     edx, 29Eh; void *
0x180084643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084648  mov     rcx, qword ptr [rsp+290h+var_270]
0x18008464d  mov     qword ptr [rsp+290h+var_270], r15
0x180084652  test    rcx, rcx
0x180084655  jz      short loc_18008465D
0x180084657  call    cs:__imp_SRCacheContext_Close
0x18008465d  mov     eax, edi
0x18008465f  jmp     loc_180084812
0x180084664  cmp     qword ptr [rsp+290h+var_270], r15
0x180084669  setnz   al
0x18008466c  test    al, al
0x18008466e  jnz     short loc_1800846AE
0x180084670  mov     rcx, [rbp+198h]; this
0x180084677  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008467e  mov     ebx, 80670012h
0x180084683  mov     edx, 29Fh; void *
0x180084688  mov     r9d, ebx; char *
0x18008468b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084690  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084695  mov     qword ptr [rsp+290h+var_270], r15
0x18008469a  test    rcx, rcx
0x18008469d  jz      loc_1800845B1
0x1800846a3  call    cs:__imp_SRCacheContext_Close
0x1800846a9  jmp     loc_1800845B1
0x1800846ae  xor     edx, edx; Val
0x1800846b0  mov     [rsp+290h+var_250], r15
0x1800846b5  mov     r8d, 200h; Size
0x1800846bb  lea     rcx, [rsp+290h+var_248]; void *
0x1800846c0  call    memset_0
0x1800846c5  lea     rax, [rsp+290h+var_248]
0x1800846ca  mov     [rbp+190h+var_48], r15
0x1800846d1  mov     rdx, r14; unsigned __int64
0x1800846d4  mov     [rbp+190h+var_38], rax
0x1800846db  lea     rcx, [rsp+290h+var_250]; this
0x1800846e0  mov     [rbp+190h+var_40], 100h
0x1800846eb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800846f0  mov     edi, eax
0x1800846f2  test    eax, eax
0x1800846f4  jns     short loc_18008472F
0x1800846f6  mov     edx, 2A2h; void *
0x1800846fb  mov     rcx, [rbp+198h]; this
0x180084702  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x180084709  mov     r9d, edi; char *
0x18008470c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084711  mov     rcx, [rsp+290h+var_250]
0x180084716  mov     [rsp+290h+var_250], r15
0x18008471b  test    rcx, rcx
0x18008471e  jz      loc_180084648
0x180084724  call    cs:__imp_SRCache_Free
0x18008472a  jmp     loc_180084648
0x18008472f  mov     rdx, [rbp+190h+var_38]
0x180084736  lea     r9, [rsp+290h+var_260]
0x18008473b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084740  xor     r8d, r8d
0x180084743  mov     [rsp+290h+var_268], rbx
0x180084748  mov     [rsp+290h+var_260], r15
0x18008474d  mov     [rsp+290h+var_258], 1
0x180084752  call    cs:__imp_SRCacheContext_OpenSubContext
0x180084758  lea     rcx, [rsp+290h+var_268]
0x18008475d  mov     edi, eax
0x18008475f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180084764  test    edi, edi
0x180084766  jns     short loc_18008478D
0x180084768  mov     rcx, [rbp+198h]; this
0x18008476f  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180084776  mov     r9d, edi; char *
0x180084779  mov     edx, 1B0h; void *
0x18008477e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084783  mov     edx, 2A5h
0x180084788  jmp     loc_1800846FB
0x18008478d  cmp     [rbx], r15
0x180084790  jz      short loc_180084796
0x180084792  mov     [rbx+10h], rsi
0x180084796  lea     rdx, aDynamicappurih_4; "DynamicAppUriHandler\\Index\\DynamicApp"...
0x18008479d  lea     rcx, [rsp+290h+var_270]; this
0x1800847a2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800847a7  mov     ebx, eax
0x1800847a9  test    eax, eax
0x1800847ab  jns     short loc_1800847E6
0x1800847ad  mov     rcx, [rbp+198h]; this
0x1800847b4  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800847bb  mov     r9d, eax; char *
0x1800847be  mov     edx, 2ABh; void *
0x1800847c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800847c8  mov     rcx, [rsp+290h+var_250]
0x1800847cd  mov     [rsp+290h+var_250], r15
0x1800847d2  test    rcx, rcx
0x1800847d5  jz      loc_180084690
0x1800847db  call    cs:__imp_SRCache_Free
0x1800847e1  jmp     loc_180084690
0x1800847e6  mov     rcx, [rsp+290h+var_250]
0x1800847eb  mov     [rsp+290h+var_250], r15
0x1800847f0  test    rcx, rcx
0x1800847f3  jz      short loc_1800847FB
0x1800847f5  call    cs:__imp_SRCache_Free
0x1800847fb  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084800  mov     qword ptr [rsp+290h+var_270], r15
0x180084805  test    rcx, rcx
0x180084808  jz      short loc_180084810
0x18008480a  call    cs:__imp_SRCacheContext_Close
0x180084810  xor     eax, eax
0x180084812  mov     rcx, [rbp+190h+var_30]
0x180084819  xor     rcx, rsp; StackCookie
0x18008481c  call    __security_check_cookie
0x180084821  mov     rbx, [rsp+290h+arg_18]
0x180084829  add     rsp, 270h
0x180084830  pop     r15
0x180084832  pop     r14
0x180084834  pop     rdi
0x180084835  pop     rsi
0x180084836  pop     rbp
0x180084837  retn
```
