# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18007fae8`
- end: `0x18007fdcc`
- name: `?OpenByApplication@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800d1290`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18007fae8`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fcb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fd6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fd89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fcb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fd6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007fd89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fb57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fbeb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fc37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fd9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fb57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fbeb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fc37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007fd9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007fce6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007fce6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007fb90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007fb90`

## string_xrefs

- `0x18007fbad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007fd03`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007fb2c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007fbc8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007fc0b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007fc96`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007fd48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18007fb72`: `ApplicationExtension\Index\Application`
- `0x18007fd2a`: `ApplicationExtension\Index\Application`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
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
      (void *)0x2D1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
  v10 = SRCacheContext_Open(v9, L"ApplicationExtension\\Index\\Application", 0, &v21);
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
      (void *)0x2D7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
      (void *)0x2D8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v13 = 731;
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
    v13 = 734;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
          L"ApplicationExtension\\Index\\Application");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x18007fae8  mov     [rsp-8+arg_18], rbx
0x18007faed  push    rbp
0x18007faee  push    rsi
0x18007faef  push    rdi
0x18007faf0  push    r14
0x18007faf2  push    r15
0x18007faf4  lea     rbp, [rsp-170h]
0x18007fafc  sub     rsp, 270h
0x18007fb03  mov     rax, cs:__security_cookie
0x18007fb0a  xor     rax, rsp
0x18007fb0d  mov     [rbp+190h+var_30], rax
0x18007fb14  xor     r15d, r15d
0x18007fb17  mov     r14, r8
0x18007fb1a  mov     rsi, rdx
0x18007fb1d  mov     rbx, rcx
0x18007fb20  test    r8, r8
0x18007fb23  jnz     short loc_18007FB4C
0x18007fb25  mov     rcx, [rbp+198h]; this
0x18007fb2c  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fb33  mov     ebx, 80070057h
0x18007fb38  mov     edx, 2D1h; void *
0x18007fb3d  mov     r9d, ebx; char *
0x18007fb40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fb45  mov     eax, ebx
0x18007fb47  jmp     loc_18007FDA6
0x18007fb4c  mov     rcx, [rcx]
0x18007fb4f  mov     [rbx], r15
0x18007fb52  test    rcx, rcx
0x18007fb55  jz      short loc_18007FB5D
0x18007fb57  call    cs:__imp_SRCacheContext_Close
0x18007fb5d  mov     [rbx+8], r15d
0x18007fb61  lea     rax, [rsp+290h+var_270]
0x18007fb66  mov     [rbx+10h], r15
0x18007fb6a  lea     r9, [rsp+290h+var_260]
0x18007fb6f  mov     rcx, [rsi]
0x18007fb72  lea     rdx, aApplicationext_0; "ApplicationExtension\\Index\\Applicatio"...
0x18007fb79  xor     r8d, r8d
0x18007fb7c  mov     [rsp+290h+var_268], rax
0x18007fb81  mov     qword ptr [rsp+290h+var_270], r15; int
0x18007fb86  mov     [rsp+290h+var_260], r15
0x18007fb8b  mov     [rsp+290h+var_258], 1
0x18007fb90  call    cs:__imp_SRCacheContext_Open
0x18007fb96  lea     rcx, [rsp+290h+var_268]
0x18007fb9b  mov     edi, eax
0x18007fb9d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007fba2  test    edi, edi
0x18007fba4  jns     short loc_18007FBF8
0x18007fba6  mov     rcx, [rbp+198h]; this
0x18007fbad  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fbb4  mov     r9d, edi; char *
0x18007fbb7  mov     edx, 18Ch; void *
0x18007fbbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fbc1  mov     rcx, [rbp+198h]; this
0x18007fbc8  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fbcf  mov     r9d, edi; char *
0x18007fbd2  mov     edx, 2D7h; void *
0x18007fbd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fbdc  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007fbe1  mov     qword ptr [rsp+290h+var_270], r15
0x18007fbe6  test    rcx, rcx
0x18007fbe9  jz      short loc_18007FBF1
0x18007fbeb  call    cs:__imp_SRCacheContext_Close
0x18007fbf1  mov     eax, edi
0x18007fbf3  jmp     loc_18007FDA6
0x18007fbf8  cmp     qword ptr [rsp+290h+var_270], r15
0x18007fbfd  setnz   al
0x18007fc00  test    al, al
0x18007fc02  jnz     short loc_18007FC42
0x18007fc04  mov     rcx, [rbp+198h]; this
0x18007fc0b  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fc12  mov     ebx, 80670012h
0x18007fc17  mov     edx, 2D8h; void *
0x18007fc1c  mov     r9d, ebx; char *
0x18007fc1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fc24  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007fc29  mov     qword ptr [rsp+290h+var_270], r15
0x18007fc2e  test    rcx, rcx
0x18007fc31  jz      loc_18007FB45
0x18007fc37  call    cs:__imp_SRCacheContext_Close
0x18007fc3d  jmp     loc_18007FB45
0x18007fc42  xor     edx, edx; Val
0x18007fc44  mov     [rsp+290h+var_250], r15
0x18007fc49  mov     r8d, 200h; Size
0x18007fc4f  lea     rcx, [rsp+290h+var_248]; void *
0x18007fc54  call    memset_0
0x18007fc59  lea     rax, [rsp+290h+var_248]
0x18007fc5e  mov     [rbp+190h+var_48], r15
0x18007fc65  mov     rdx, r14; unsigned __int64
0x18007fc68  mov     [rbp+190h+var_38], rax
0x18007fc6f  lea     rcx, [rsp+290h+var_250]; this
0x18007fc74  mov     [rbp+190h+var_40], 100h
0x18007fc7f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007fc84  mov     edi, eax
0x18007fc86  test    eax, eax
0x18007fc88  jns     short loc_18007FCC3
0x18007fc8a  mov     edx, 2DBh; void *
0x18007fc8f  mov     rcx, [rbp+198h]; this
0x18007fc96  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fc9d  mov     r9d, edi; char *
0x18007fca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fca5  mov     rcx, [rsp+290h+var_250]
0x18007fcaa  mov     [rsp+290h+var_250], r15
0x18007fcaf  test    rcx, rcx
0x18007fcb2  jz      loc_18007FBDC
0x18007fcb8  call    cs:__imp_SRCache_Free
0x18007fcbe  jmp     loc_18007FBDC
0x18007fcc3  mov     rdx, [rbp+190h+var_38]
0x18007fcca  lea     r9, [rsp+290h+var_260]
0x18007fccf  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007fcd4  xor     r8d, r8d
0x18007fcd7  mov     [rsp+290h+var_268], rbx
0x18007fcdc  mov     [rsp+290h+var_260], r15
0x18007fce1  mov     [rsp+290h+var_258], 1
0x18007fce6  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007fcec  lea     rcx, [rsp+290h+var_268]
0x18007fcf1  mov     edi, eax
0x18007fcf3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007fcf8  test    edi, edi
0x18007fcfa  jns     short loc_18007FD21
0x18007fcfc  mov     rcx, [rbp+198h]; this
0x18007fd03  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fd0a  mov     r9d, edi; char *
0x18007fd0d  mov     edx, 1B0h; void *
0x18007fd12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fd17  mov     edx, 2DEh
0x18007fd1c  jmp     loc_18007FC8F
0x18007fd21  cmp     [rbx], r15
0x18007fd24  jz      short loc_18007FD2A
0x18007fd26  mov     [rbx+10h], rsi
0x18007fd2a  lea     rdx, aApplicationext_0; "ApplicationExtension\\Index\\Applicatio"...
0x18007fd31  lea     rcx, [rsp+290h+var_270]; this
0x18007fd36  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007fd3b  mov     ebx, eax
0x18007fd3d  test    eax, eax
0x18007fd3f  jns     short loc_18007FD7A
0x18007fd41  mov     rcx, [rbp+198h]; this
0x18007fd48  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007fd4f  mov     r9d, eax; char *
0x18007fd52  mov     edx, 2E4h; void *
0x18007fd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fd5c  mov     rcx, [rsp+290h+var_250]
0x18007fd61  mov     [rsp+290h+var_250], r15
0x18007fd66  test    rcx, rcx
0x18007fd69  jz      loc_18007FC24
0x18007fd6f  call    cs:__imp_SRCache_Free
0x18007fd75  jmp     loc_18007FC24
0x18007fd7a  mov     rcx, [rsp+290h+var_250]
0x18007fd7f  mov     [rsp+290h+var_250], r15
0x18007fd84  test    rcx, rcx
0x18007fd87  jz      short loc_18007FD8F
0x18007fd89  call    cs:__imp_SRCache_Free
0x18007fd8f  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007fd94  mov     qword ptr [rsp+290h+var_270], r15
0x18007fd99  test    rcx, rcx
0x18007fd9c  jz      short loc_18007FDA4
0x18007fd9e  call    cs:__imp_SRCacheContext_Close
0x18007fda4  xor     eax, eax
0x18007fda6  mov     rcx, [rbp+190h+var_30]
0x18007fdad  xor     rcx, rsp; StackCookie
0x18007fdb0  call    __security_check_cookie
0x18007fdb5  mov     rbx, [rsp+290h+arg_18]
0x18007fdbd  add     rsp, 270h
0x18007fdc4  pop     r15
0x18007fdc6  pop     r14
0x18007fdc8  pop     rdi
0x18007fdc9  pop     rsi
0x18007fdca  pop     rbp
0x18007fdcb  retn
```
