# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18007a00c`
- end: `0x18007a2f0`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180066b04`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18007a00c`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a1dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a293`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a2ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a1dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a293`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a2ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a07b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a10f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a15b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a07b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a10f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a15b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007a20a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007a20a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007a0b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007a0b4`

## string_xrefs

- `0x18007a0d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007a227`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007a050`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007a0ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007a12f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007a1ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18007a26c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
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
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v21);
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
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v13 = 1948;
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
    v13 = 1951;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
          L"Package\\Index\\PackageFamily");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
0x18007a00c  mov     [rsp-8+arg_18], rbx
0x18007a011  push    rbp
0x18007a012  push    rsi
0x18007a013  push    rdi
0x18007a014  push    r14
0x18007a016  push    r15
0x18007a018  lea     rbp, [rsp-170h]
0x18007a020  sub     rsp, 270h
0x18007a027  mov     rax, cs:__security_cookie
0x18007a02e  xor     rax, rsp
0x18007a031  mov     [rbp+190h+var_30], rax
0x18007a038  xor     r15d, r15d
0x18007a03b  mov     r14, r8
0x18007a03e  mov     rsi, rdx
0x18007a041  mov     rbx, rcx
0x18007a044  test    r8, r8
0x18007a047  jnz     short loc_18007A070
0x18007a049  mov     rcx, [rbp+198h]; this
0x18007a050  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a057  mov     ebx, 80070057h
0x18007a05c  mov     edx, 792h; void *
0x18007a061  mov     r9d, ebx; char *
0x18007a064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a069  mov     eax, ebx
0x18007a06b  jmp     loc_18007A2CA
0x18007a070  mov     rcx, [rcx]
0x18007a073  mov     [rbx], r15
0x18007a076  test    rcx, rcx
0x18007a079  jz      short loc_18007A081
0x18007a07b  call    cs:__imp_SRCacheContext_Close
0x18007a081  mov     [rbx+8], r15d
0x18007a085  lea     rax, [rsp+290h+var_270]
0x18007a08a  mov     [rbx+10h], r15
0x18007a08e  lea     r9, [rsp+290h+var_260]
0x18007a093  mov     rcx, [rsi]
0x18007a096  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18007a09d  xor     r8d, r8d
0x18007a0a0  mov     [rsp+290h+var_268], rax
0x18007a0a5  mov     qword ptr [rsp+290h+var_270], r15; int
0x18007a0aa  mov     [rsp+290h+var_260], r15
0x18007a0af  mov     [rsp+290h+var_258], 1
0x18007a0b4  call    cs:__imp_SRCacheContext_Open
0x18007a0ba  lea     rcx, [rsp+290h+var_268]
0x18007a0bf  mov     edi, eax
0x18007a0c1  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007a0c6  test    edi, edi
0x18007a0c8  jns     short loc_18007A11C
0x18007a0ca  mov     rcx, [rbp+198h]; this
0x18007a0d1  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a0d8  mov     r9d, edi; char *
0x18007a0db  mov     edx, 18Ch; void *
0x18007a0e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a0e5  mov     rcx, [rbp+198h]; this
0x18007a0ec  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a0f3  mov     r9d, edi; char *
0x18007a0f6  mov     edx, 798h; void *
0x18007a0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a100  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007a105  mov     qword ptr [rsp+290h+var_270], r15
0x18007a10a  test    rcx, rcx
0x18007a10d  jz      short loc_18007A115
0x18007a10f  call    cs:__imp_SRCacheContext_Close
0x18007a115  mov     eax, edi
0x18007a117  jmp     loc_18007A2CA
0x18007a11c  cmp     qword ptr [rsp+290h+var_270], r15
0x18007a121  setnz   al
0x18007a124  test    al, al
0x18007a126  jnz     short loc_18007A166
0x18007a128  mov     rcx, [rbp+198h]; this
0x18007a12f  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a136  mov     ebx, 80670012h
0x18007a13b  mov     edx, 799h; void *
0x18007a140  mov     r9d, ebx; char *
0x18007a143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a148  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007a14d  mov     qword ptr [rsp+290h+var_270], r15
0x18007a152  test    rcx, rcx
0x18007a155  jz      loc_18007A069
0x18007a15b  call    cs:__imp_SRCacheContext_Close
0x18007a161  jmp     loc_18007A069
0x18007a166  xor     edx, edx; Val
0x18007a168  mov     [rsp+290h+var_250], r15
0x18007a16d  mov     r8d, 200h; Size
0x18007a173  lea     rcx, [rsp+290h+var_248]; void *
0x18007a178  call    memset_0
0x18007a17d  lea     rax, [rsp+290h+var_248]
0x18007a182  mov     [rbp+190h+var_48], r15
0x18007a189  mov     rdx, r14; unsigned __int64
0x18007a18c  mov     [rbp+190h+var_38], rax
0x18007a193  lea     rcx, [rsp+290h+var_250]; this
0x18007a198  mov     [rbp+190h+var_40], 100h
0x18007a1a3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007a1a8  mov     edi, eax
0x18007a1aa  test    eax, eax
0x18007a1ac  jns     short loc_18007A1E7
0x18007a1ae  mov     edx, 79Ch; void *
0x18007a1b3  mov     rcx, [rbp+198h]; this
0x18007a1ba  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a1c1  mov     r9d, edi; char *
0x18007a1c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a1c9  mov     rcx, [rsp+290h+var_250]
0x18007a1ce  mov     [rsp+290h+var_250], r15
0x18007a1d3  test    rcx, rcx
0x18007a1d6  jz      loc_18007A100
0x18007a1dc  call    cs:__imp_SRCache_Free
0x18007a1e2  jmp     loc_18007A100
0x18007a1e7  mov     rdx, [rbp+190h+var_38]
0x18007a1ee  lea     r9, [rsp+290h+var_260]
0x18007a1f3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007a1f8  xor     r8d, r8d
0x18007a1fb  mov     [rsp+290h+var_268], rbx
0x18007a200  mov     [rsp+290h+var_260], r15
0x18007a205  mov     [rsp+290h+var_258], 1
0x18007a20a  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007a210  lea     rcx, [rsp+290h+var_268]
0x18007a215  mov     edi, eax
0x18007a217  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007a21c  test    edi, edi
0x18007a21e  jns     short loc_18007A245
0x18007a220  mov     rcx, [rbp+198h]; this
0x18007a227  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a22e  mov     r9d, edi; char *
0x18007a231  mov     edx, 1B0h; void *
0x18007a236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a23b  mov     edx, 79Fh
0x18007a240  jmp     loc_18007A1B3
0x18007a245  cmp     [rbx], r15
0x18007a248  jz      short loc_18007A24E
0x18007a24a  mov     [rbx+10h], rsi
0x18007a24e  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18007a255  lea     rcx, [rsp+290h+var_270]; this
0x18007a25a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007a25f  mov     ebx, eax
0x18007a261  test    eax, eax
0x18007a263  jns     short loc_18007A29E
0x18007a265  mov     rcx, [rbp+198h]; this
0x18007a26c  lea     r8, aOnecorePrivate_18; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a273  mov     r9d, eax; char *
0x18007a276  mov     edx, 7A5h; void *
0x18007a27b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a280  mov     rcx, [rsp+290h+var_250]
0x18007a285  mov     [rsp+290h+var_250], r15
0x18007a28a  test    rcx, rcx
0x18007a28d  jz      loc_18007A148
0x18007a293  call    cs:__imp_SRCache_Free
0x18007a299  jmp     loc_18007A148
0x18007a29e  mov     rcx, [rsp+290h+var_250]
0x18007a2a3  mov     [rsp+290h+var_250], r15
0x18007a2a8  test    rcx, rcx
0x18007a2ab  jz      short loc_18007A2B3
0x18007a2ad  call    cs:__imp_SRCache_Free
0x18007a2b3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007a2b8  mov     qword ptr [rsp+290h+var_270], r15
0x18007a2bd  test    rcx, rcx
0x18007a2c0  jz      short loc_18007A2C8
0x18007a2c2  call    cs:__imp_SRCacheContext_Close
0x18007a2c8  xor     eax, eax
0x18007a2ca  mov     rcx, [rbp+190h+var_30]
0x18007a2d1  xor     rcx, rsp; StackCookie
0x18007a2d4  call    __security_check_cookie
0x18007a2d9  mov     rbx, [rsp+290h+arg_18]
0x18007a2e1  add     rsp, 270h
0x18007a2e8  pop     r15
0x18007a2ea  pop     r14
0x18007a2ec  pop     rdi
0x18007a2ed  pop     rsi
0x18007a2ee  pop     rbp
0x18007a2ef  retn
```
