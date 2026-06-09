# StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByExtension(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18007ff74`
- end: `0x180080258`
- name: `?OpenByExtension@AppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800640f4`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18007ff74`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180080144`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800801fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180080215`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180080144`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800801fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180080215`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007ffe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180080077`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800800c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008022a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007ffe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180080077`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800800c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008022a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180080172`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180080172`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18008001c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18008001c`

## string_xrefs

- `0x18007ffb8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180080054`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180080097`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180080122`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x1800801d4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180080039`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18008018f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007fffe`: `AppUriHandler\Index\Extension`
- `0x1800801b6`: `AppUriHandler\Index\Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByExtension(
        StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *this,
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
      (void *)0x2A8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
  v10 = SRCacheContext_Open(v9, L"AppUriHandler\\Index\\Extension", 0, &v21);
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
      (void *)0x2AE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
      (void *)0x2AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
    v13 = 690;
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
    v13 = 693;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
          L"AppUriHandler\\Index\\Extension");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
0x18007ff74  mov     [rsp-8+arg_18], rbx
0x18007ff79  push    rbp
0x18007ff7a  push    rsi
0x18007ff7b  push    rdi
0x18007ff7c  push    r14
0x18007ff7e  push    r15
0x18007ff80  lea     rbp, [rsp-170h]
0x18007ff88  sub     rsp, 270h
0x18007ff8f  mov     rax, cs:__security_cookie
0x18007ff96  xor     rax, rsp
0x18007ff99  mov     [rbp+190h+var_30], rax
0x18007ffa0  xor     r15d, r15d
0x18007ffa3  mov     r14, r8
0x18007ffa6  mov     rsi, rdx
0x18007ffa9  mov     rbx, rcx
0x18007ffac  test    r8, r8
0x18007ffaf  jnz     short loc_18007FFD8
0x18007ffb1  mov     rcx, [rbp+198h]; this
0x18007ffb8  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007ffbf  mov     ebx, 80070057h
0x18007ffc4  mov     edx, 2A8h; void *
0x18007ffc9  mov     r9d, ebx; char *
0x18007ffcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ffd1  mov     eax, ebx
0x18007ffd3  jmp     loc_180080232
0x18007ffd8  mov     rcx, [rcx]
0x18007ffdb  mov     [rbx], r15
0x18007ffde  test    rcx, rcx
0x18007ffe1  jz      short loc_18007FFE9
0x18007ffe3  call    cs:__imp_SRCacheContext_Close
0x18007ffe9  mov     [rbx+8], r15d
0x18007ffed  lea     rax, [rsp+290h+var_270]
0x18007fff2  mov     [rbx+10h], r15
0x18007fff6  lea     r9, [rsp+290h+var_260]
0x18007fffb  mov     rcx, [rsi]
0x18007fffe  lea     rdx, aAppurihandlerI; "AppUriHandler\\Index\\Extension"
0x180080005  xor     r8d, r8d
0x180080008  mov     [rsp+290h+var_268], rax
0x18008000d  mov     qword ptr [rsp+290h+var_270], r15; int
0x180080012  mov     [rsp+290h+var_260], r15
0x180080017  mov     [rsp+290h+var_258], 1
0x18008001c  call    cs:__imp_SRCacheContext_Open
0x180080022  lea     rcx, [rsp+290h+var_268]
0x180080027  mov     edi, eax
0x180080029  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18008002e  test    edi, edi
0x180080030  jns     short loc_180080084
0x180080032  mov     rcx, [rbp+198h]; this
0x180080039  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180080040  mov     r9d, edi; char *
0x180080043  mov     edx, 18Ch; void *
0x180080048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008004d  mov     rcx, [rbp+198h]; this
0x180080054  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008005b  mov     r9d, edi; char *
0x18008005e  mov     edx, 2AEh; void *
0x180080063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080068  mov     rcx, qword ptr [rsp+290h+var_270]
0x18008006d  mov     qword ptr [rsp+290h+var_270], r15
0x180080072  test    rcx, rcx
0x180080075  jz      short loc_18008007D
0x180080077  call    cs:__imp_SRCacheContext_Close
0x18008007d  mov     eax, edi
0x18008007f  jmp     loc_180080232
0x180080084  cmp     qword ptr [rsp+290h+var_270], r15
0x180080089  setnz   al
0x18008008c  test    al, al
0x18008008e  jnz     short loc_1800800CE
0x180080090  mov     rcx, [rbp+198h]; this
0x180080097  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008009e  mov     ebx, 80670012h
0x1800800a3  mov     edx, 2AFh; void *
0x1800800a8  mov     r9d, ebx; char *
0x1800800ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800800b0  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800800b5  mov     qword ptr [rsp+290h+var_270], r15
0x1800800ba  test    rcx, rcx
0x1800800bd  jz      loc_18007FFD1
0x1800800c3  call    cs:__imp_SRCacheContext_Close
0x1800800c9  jmp     loc_18007FFD1
0x1800800ce  xor     edx, edx; Val
0x1800800d0  mov     [rsp+290h+var_250], r15
0x1800800d5  mov     r8d, 200h; Size
0x1800800db  lea     rcx, [rsp+290h+var_248]; void *
0x1800800e0  call    memset_0
0x1800800e5  lea     rax, [rsp+290h+var_248]
0x1800800ea  mov     [rbp+190h+var_48], r15
0x1800800f1  mov     rdx, r14; unsigned __int64
0x1800800f4  mov     [rbp+190h+var_38], rax
0x1800800fb  lea     rcx, [rsp+290h+var_250]; this
0x180080100  mov     [rbp+190h+var_40], 100h
0x18008010b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180080110  mov     edi, eax
0x180080112  test    eax, eax
0x180080114  jns     short loc_18008014F
0x180080116  mov     edx, 2B2h; void *
0x18008011b  mov     rcx, [rbp+198h]; this
0x180080122  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180080129  mov     r9d, edi; char *
0x18008012c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080131  mov     rcx, [rsp+290h+var_250]
0x180080136  mov     [rsp+290h+var_250], r15
0x18008013b  test    rcx, rcx
0x18008013e  jz      loc_180080068
0x180080144  call    cs:__imp_SRCache_Free
0x18008014a  jmp     loc_180080068
0x18008014f  mov     rdx, [rbp+190h+var_38]
0x180080156  lea     r9, [rsp+290h+var_260]
0x18008015b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180080160  xor     r8d, r8d
0x180080163  mov     [rsp+290h+var_268], rbx
0x180080168  mov     [rsp+290h+var_260], r15
0x18008016d  mov     [rsp+290h+var_258], 1
0x180080172  call    cs:__imp_SRCacheContext_OpenSubContext
0x180080178  lea     rcx, [rsp+290h+var_268]
0x18008017d  mov     edi, eax
0x18008017f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180080184  test    edi, edi
0x180080186  jns     short loc_1800801AD
0x180080188  mov     rcx, [rbp+198h]; this
0x18008018f  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180080196  mov     r9d, edi; char *
0x180080199  mov     edx, 1B0h; void *
0x18008019e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800801a3  mov     edx, 2B5h
0x1800801a8  jmp     loc_18008011B
0x1800801ad  cmp     [rbx], r15
0x1800801b0  jz      short loc_1800801B6
0x1800801b2  mov     [rbx+10h], rsi
0x1800801b6  lea     rdx, aAppurihandlerI; "AppUriHandler\\Index\\Extension"
0x1800801bd  lea     rcx, [rsp+290h+var_270]; this
0x1800801c2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800801c7  mov     ebx, eax
0x1800801c9  test    eax, eax
0x1800801cb  jns     short loc_180080206
0x1800801cd  mov     rcx, [rbp+198h]; this
0x1800801d4  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800801db  mov     r9d, eax; char *
0x1800801de  mov     edx, 2BBh; void *
0x1800801e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800801e8  mov     rcx, [rsp+290h+var_250]
0x1800801ed  mov     [rsp+290h+var_250], r15
0x1800801f2  test    rcx, rcx
0x1800801f5  jz      loc_1800800B0
0x1800801fb  call    cs:__imp_SRCache_Free
0x180080201  jmp     loc_1800800B0
0x180080206  mov     rcx, [rsp+290h+var_250]
0x18008020b  mov     [rsp+290h+var_250], r15
0x180080210  test    rcx, rcx
0x180080213  jz      short loc_18008021B
0x180080215  call    cs:__imp_SRCache_Free
0x18008021b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180080220  mov     qword ptr [rsp+290h+var_270], r15
0x180080225  test    rcx, rcx
0x180080228  jz      short loc_180080230
0x18008022a  call    cs:__imp_SRCacheContext_Close
0x180080230  xor     eax, eax
0x180080232  mov     rcx, [rbp+190h+var_30]
0x180080239  xor     rcx, rsp; StackCookie
0x18008023c  call    __security_check_cookie
0x180080241  mov     rbx, [rsp+290h+arg_18]
0x180080249  add     rsp, 270h
0x180080250  pop     r15
0x180080252  pop     r14
0x180080254  pop     rdi
0x180080255  pop     rsi
0x180080256  pop     rbp
0x180080257  retn
```
