# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1800a4980`
- end: `0x1800a4cbc`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800cd2f0`

## callees

- `0x1800211f0`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x1800a4980`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a4b2d`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a4b2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a49ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4a8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4ad9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4c8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a49ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4a8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4ad9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4c8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a4a30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a4a30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4c5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4c79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4c5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4c79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a4bd4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a4bd4`

## string_xrefs

- `0x1800a4b3e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800a49c4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a4a6a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a4aad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a4b7c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a4c38`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a4a4f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a4bf3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)v28 = v22;
  *(_QWORD *)v22 = 0;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
LABEL_8:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)_o__ui64tow_s(a3, v28, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_18:
    v15 = 1948;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v10 < 0 )
    goto LABEL_18;
  *(_QWORD *)v28 = this;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v15 = 1951;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"Package\\Index\\PackageFamily");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v17,
      v22[0]);
    v19 = v23;
    v23 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = v23;
  v23 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x1800a4980  mov     [rsp-8+arg_18], rbx
0x1800a4985  push    rbp
0x1800a4986  push    rsi
0x1800a4987  push    rdi
0x1800a4988  push    r14
0x1800a498a  push    r15
0x1800a498c  lea     rbp, [rsp-180h]
0x1800a4994  sub     rsp, 280h
0x1800a499b  mov     rax, cs:__security_cookie
0x1800a49a2  xor     rax, rsp
0x1800a49a5  mov     [rbp+1A0h+var_28], rax
0x1800a49ac  xor     r15d, r15d
0x1800a49af  mov     r14, r8
0x1800a49b2  mov     rsi, rdx
0x1800a49b5  mov     rbx, rcx
0x1800a49b8  test    r8, r8
0x1800a49bb  jnz     short loc_1800A49E4
0x1800a49bd  mov     rcx, [rbp+1A8h]; this
0x1800a49c4  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a49cb  mov     ebx, 80070057h
0x1800a49d0  mov     edx, 792h; void *
0x1800a49d5  mov     r9d, ebx; char *
0x1800a49d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a49dd  mov     eax, ebx
0x1800a49df  jmp     loc_1800A4C96
0x1800a49e4  mov     rcx, [rcx]
0x1800a49e7  mov     [rbx], r15
0x1800a49ea  test    rcx, rcx
0x1800a49ed  jz      short loc_1800A49F5
0x1800a49ef  call    cs:__imp_SRCacheContext_Close
0x1800a49f5  mov     [rbx+8], r15d
0x1800a49f9  lea     rax, [rsp+2A0h+var_280]
0x1800a49fe  mov     [rbx+10h], r15
0x1800a4a02  lea     r9, [rbp+1A0h+var_48]
0x1800a4a09  mov     rcx, [rsi]
0x1800a4a0c  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x1800a4a13  xor     r8d, r8d
0x1800a4a16  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800a4a1d  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800a4a22  mov     [rbp+1A0h+var_48], r15
0x1800a4a29  mov     [rbp+1A0h+var_40], 1
0x1800a4a30  call    cs:__imp_SRCacheContext_Open
0x1800a4a36  lea     rcx, [rbp+1A0h+var_50]
0x1800a4a3d  mov     edi, eax
0x1800a4a3f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a4a44  test    edi, edi
0x1800a4a46  jns     short loc_1800A4A9A
0x1800a4a48  mov     rcx, [rbp+1A8h]; this
0x1800a4a4f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4a56  mov     r9d, edi; char *
0x1800a4a59  mov     edx, 18Ch; void *
0x1800a4a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4a63  mov     rcx, [rbp+1A8h]; this
0x1800a4a6a  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4a71  mov     r9d, edi; char *
0x1800a4a74  mov     edx, 798h; void *
0x1800a4a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4a7e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a4a83  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a4a88  test    rcx, rcx
0x1800a4a8b  jz      short loc_1800A4A93
0x1800a4a8d  call    cs:__imp_SRCacheContext_Close
0x1800a4a93  mov     eax, edi
0x1800a4a95  jmp     loc_1800A4C96
0x1800a4a9a  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800a4a9f  setnz   al
0x1800a4aa2  test    al, al
0x1800a4aa4  jnz     short loc_1800A4AE4
0x1800a4aa6  mov     rcx, [rbp+1A8h]; this
0x1800a4aad  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4ab4  mov     ebx, 80670012h
0x1800a4ab9  mov     edx, 799h; void *
0x1800a4abe  mov     r9d, ebx; char *
0x1800a4ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4ac6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a4acb  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a4ad0  test    rcx, rcx
0x1800a4ad3  jz      loc_1800A49DD
0x1800a4ad9  call    cs:__imp_SRCacheContext_Close
0x1800a4adf  jmp     loc_1800A49DD
0x1800a4ae4  xor     edx, edx; Val
0x1800a4ae6  mov     [rsp+2A0h+var_270], r15
0x1800a4aeb  mov     r8d, 200h; Size
0x1800a4af1  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800a4af6  call    memset_0
0x1800a4afb  mov     r9d, 10h
0x1800a4b01  mov     [rbp+1A0h+var_68], r15
0x1800a4b08  lea     rax, [rsp+2A0h+var_268]
0x1800a4b0d  mov     [rbp+1A0h+var_60], 100h
0x1800a4b18  lea     rdx, [rbp+1A0h+var_50]
0x1800a4b1f  mov     [rbp+1A0h+var_58], rax
0x1800a4b26  mov     rcx, r14
0x1800a4b29  lea     r8d, [r9+1]
0x1800a4b2d  call    cs:__imp__o__ui64tow_s
0x1800a4b33  test    eax, eax
0x1800a4b35  jz      short loc_1800A4B59
0x1800a4b37  mov     rcx, [rbp+1A8h]; this
0x1800a4b3e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4b45  mov     edi, 8000FFFFh
0x1800a4b4a  mov     edx, 166h; void *
0x1800a4b4f  mov     r9d, edi; char *
0x1800a4b52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4b57  jmp     short loc_1800A4B70
0x1800a4b59  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800a4b60  lea     rcx, [rsp+2A0h+var_270]; this
0x1800a4b65  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a4b6a  mov     edi, eax
0x1800a4b6c  test    eax, eax
0x1800a4b6e  jns     short loc_1800A4BA9
0x1800a4b70  mov     edx, 79Ch; void *
0x1800a4b75  mov     rcx, [rbp+1A8h]; this
0x1800a4b7c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4b83  mov     r9d, edi; char *
0x1800a4b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4b8b  mov     rcx, [rsp+2A0h+var_270]
0x1800a4b90  mov     [rsp+2A0h+var_270], r15
0x1800a4b95  test    rcx, rcx
0x1800a4b98  jz      loc_1800A4A7E
0x1800a4b9e  call    cs:__imp_SRCache_Free
0x1800a4ba4  jmp     loc_1800A4A7E
0x1800a4ba9  mov     rdx, [rbp+1A0h+var_58]
0x1800a4bb0  lea     r9, [rbp+1A0h+var_48]
0x1800a4bb7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a4bbc  xor     r8d, r8d
0x1800a4bbf  mov     qword ptr [rbp+1A0h+var_50], rbx
0x1800a4bc6  mov     [rbp+1A0h+var_48], r15
0x1800a4bcd  mov     [rbp+1A0h+var_40], 1
0x1800a4bd4  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800a4bda  lea     rcx, [rbp+1A0h+var_50]
0x1800a4be1  mov     edi, eax
0x1800a4be3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a4be8  test    edi, edi
0x1800a4bea  jns     short loc_1800A4C11
0x1800a4bec  mov     rcx, [rbp+1A8h]; this
0x1800a4bf3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4bfa  mov     r9d, edi; char *
0x1800a4bfd  mov     edx, 1B0h; void *
0x1800a4c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4c07  mov     edx, 79Fh
0x1800a4c0c  jmp     loc_1800A4B75
0x1800a4c11  cmp     [rbx], r15
0x1800a4c14  jz      short loc_1800A4C1A
0x1800a4c16  mov     [rbx+10h], rsi
0x1800a4c1a  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x1800a4c21  lea     rcx, [rsp+2A0h+var_280]; this
0x1800a4c26  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a4c2b  mov     ebx, eax
0x1800a4c2d  test    eax, eax
0x1800a4c2f  jns     short loc_1800A4C6A
0x1800a4c31  mov     rcx, [rbp+1A8h]; this
0x1800a4c38  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4c3f  mov     r9d, eax; char *
0x1800a4c42  mov     edx, 7A5h; void *
0x1800a4c47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4c4c  mov     rcx, [rsp+2A0h+var_270]
0x1800a4c51  mov     [rsp+2A0h+var_270], r15
0x1800a4c56  test    rcx, rcx
0x1800a4c59  jz      loc_1800A4AC6
0x1800a4c5f  call    cs:__imp_SRCache_Free
0x1800a4c65  jmp     loc_1800A4AC6
0x1800a4c6a  mov     rcx, [rsp+2A0h+var_270]
0x1800a4c6f  mov     [rsp+2A0h+var_270], r15
0x1800a4c74  test    rcx, rcx
0x1800a4c77  jz      short loc_1800A4C7F
0x1800a4c79  call    cs:__imp_SRCache_Free
0x1800a4c7f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a4c84  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a4c89  test    rcx, rcx
0x1800a4c8c  jz      short loc_1800A4C94
0x1800a4c8e  call    cs:__imp_SRCacheContext_Close
0x1800a4c94  xor     eax, eax
0x1800a4c96  mov     rcx, [rbp+1A0h+var_28]
0x1800a4c9d  xor     rcx, rsp; StackCookie
0x1800a4ca0  call    __security_check_cookie
0x1800a4ca5  mov     rbx, [rsp+2A0h+arg_18]
0x1800a4cad  add     rsp, 280h
0x1800a4cb4  pop     r15
0x1800a4cb6  pop     r14
0x1800a4cb8  pop     rdi
0x1800a4cb9  pop     rsi
0x1800a4cba  pop     rbp
0x1800a4cbb  retn
```
