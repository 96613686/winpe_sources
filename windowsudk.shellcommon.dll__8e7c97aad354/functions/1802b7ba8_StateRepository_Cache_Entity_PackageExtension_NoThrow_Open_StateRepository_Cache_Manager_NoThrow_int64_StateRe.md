# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b7ba8`
- end: `0x1802b7e4e`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b5308`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b7ba8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7cef`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7cef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7d96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7d96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7d60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7e0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7d60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7e0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7c70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7e20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7c70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7e20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7c13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7c13`

## string_xrefs

- `0x1802b7d00`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b7c32`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b7db5`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b7bfd`: `PackageExtension\Data`
- `0x1802b7dd6`: `PackageExtension\Data`
- `0x1802b7c52`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1802b7d3e`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+238h] [rbp+138h]
  __int64 v20; // [rsp+240h] [rbp+140h]
  _BYTE *v21; // [rsp+248h] [rbp+148h]
  wchar_t v22[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h] BYREF
  char v24; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v22 = v16;
  v24 = 1;
  *(_QWORD *)v16 = 0;
  v23 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageExtension\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 318;
    goto LABEL_3;
  }
  memset_0(v18, 0, sizeof(v18));
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 256;
  v21 = v18;
  if ( (unsigned int)_o__ui64tow_s(a2, v22, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v16[0]);
LABEL_12:
    v12 = 321;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v17, v22);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v22 = a3;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v21, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 322;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 324;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v17;
    v17 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x1802b7ba8  mov     [rsp-8+arg_10], rbx
0x1802b7bad  push    rbp
0x1802b7bae  push    rsi
0x1802b7baf  push    rdi
0x1802b7bb0  push    r14
0x1802b7bb2  push    r15
0x1802b7bb4  lea     rbp, [rsp-180h]
0x1802b7bbc  sub     rsp, 280h
0x1802b7bc3  mov     rax, cs:__security_cookie
0x1802b7bca  xor     rax, rsp
0x1802b7bcd  mov     [rbp+1A0h+var_28], rax
0x1802b7bd4  mov     rcx, [rcx]
0x1802b7bd7  lea     rax, [rsp+2A0h+var_280]
0x1802b7bdc  mov     rsi, r9
0x1802b7bdf  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b7be6  mov     rdi, r8
0x1802b7be9  mov     [rbp+1A0h+var_40], 1
0x1802b7bf0  mov     r14, rdx
0x1802b7bf3  lea     r9, [rbp+1A0h+var_48]
0x1802b7bfa  xor     r15d, r15d
0x1802b7bfd  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x1802b7c04  xor     r8d, r8d
0x1802b7c07  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b7c0c  mov     [rbp+1A0h+var_48], r15
0x1802b7c13  call    cs:__imp_SRCacheContext_Open
0x1802b7c19  lea     rcx, [rbp+1A0h+var_50]
0x1802b7c20  mov     ebx, eax
0x1802b7c22  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7c27  test    ebx, ebx
0x1802b7c29  jns     short loc_1802B7C7D
0x1802b7c2b  mov     rcx, [rbp+1A8h]; this
0x1802b7c32  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7c39  mov     r9d, ebx; char *
0x1802b7c3c  mov     edx, 18Ch; void *
0x1802b7c41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7c46  mov     edx, 13Dh; void *
0x1802b7c4b  mov     rcx, [rbp+1A8h]; this
0x1802b7c52  lea     r8, aOnecoreInterna_22; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7c59  mov     r9d, ebx; char *
0x1802b7c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7c61  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7c66  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7c6b  test    rcx, rcx
0x1802b7c6e  jz      short loc_1802B7C76
0x1802b7c70  call    cs:__imp_SRCacheContext_Close
0x1802b7c76  mov     eax, ebx
0x1802b7c78  jmp     loc_1802B7E28
0x1802b7c7d  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b7c82  setnz   al
0x1802b7c85  test    al, al
0x1802b7c87  jnz     short loc_1802B7C95
0x1802b7c89  mov     ebx, 80670012h
0x1802b7c8e  mov     edx, 13Eh
0x1802b7c93  jmp     short loc_1802B7C4B
0x1802b7c95  mov     ebx, 200h
0x1802b7c9a  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7c9f  mov     r8d, ebx; Size
0x1802b7ca2  xor     edx, edx; Val
0x1802b7ca4  call    memset_0
0x1802b7ca9  mov     r8d, ebx; Size
0x1802b7cac  mov     [rsp+2A0h+var_270], r15
0x1802b7cb1  xor     edx, edx; Val
0x1802b7cb3  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7cb8  call    memset_0
0x1802b7cbd  mov     r9d, 10h
0x1802b7cc3  mov     [rbp+1A0h+var_68], r15
0x1802b7cca  lea     rax, [rsp+2A0h+var_268]
0x1802b7ccf  mov     [rbp+1A0h+var_60], 100h
0x1802b7cda  lea     rdx, [rbp+1A0h+var_50]
0x1802b7ce1  mov     [rbp+1A0h+var_58], rax
0x1802b7ce8  mov     rcx, r14
0x1802b7ceb  lea     r8d, [r9+1]
0x1802b7cef  call    cs:__imp__o__ui64tow_s
0x1802b7cf5  test    eax, eax
0x1802b7cf7  jz      short loc_1802B7D1B
0x1802b7cf9  mov     rcx, [rbp+1A8h]; this
0x1802b7d00  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7d07  mov     ebx, 8000FFFFh
0x1802b7d0c  mov     edx, 166h; void *
0x1802b7d11  mov     r9d, ebx; char *
0x1802b7d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7d19  jmp     short loc_1802B7D32
0x1802b7d1b  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b7d22  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b7d27  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b7d2c  mov     ebx, eax
0x1802b7d2e  test    eax, eax
0x1802b7d30  jns     short loc_1802B7D6B
0x1802b7d32  mov     edx, 141h; void *
0x1802b7d37  mov     rcx, [rbp+1A8h]; this
0x1802b7d3e  lea     r8, aOnecoreInterna_22; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7d45  mov     r9d, ebx; char *
0x1802b7d48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7d4d  mov     rcx, [rsp+2A0h+var_270]
0x1802b7d52  mov     [rsp+2A0h+var_270], r15
0x1802b7d57  test    rcx, rcx
0x1802b7d5a  jz      loc_1802B7C61
0x1802b7d60  call    cs:__imp_SRCache_Free
0x1802b7d66  jmp     loc_1802B7C61
0x1802b7d6b  mov     rdx, [rbp+1A0h+var_58]
0x1802b7d72  lea     r9, [rbp+1A0h+var_48]
0x1802b7d79  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7d7e  xor     r8d, r8d
0x1802b7d81  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b7d88  mov     [rbp+1A0h+var_48], r15
0x1802b7d8f  mov     [rbp+1A0h+var_40], 1
0x1802b7d96  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b7d9c  lea     rcx, [rbp+1A0h+var_50]
0x1802b7da3  mov     ebx, eax
0x1802b7da5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7daa  test    ebx, ebx
0x1802b7dac  jns     short loc_1802B7DD3
0x1802b7dae  mov     rcx, [rbp+1A8h]; this
0x1802b7db5  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7dbc  mov     r9d, ebx; char *
0x1802b7dbf  mov     edx, 1B0h; void *
0x1802b7dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7dc9  mov     edx, 142h
0x1802b7dce  jmp     loc_1802B7D37
0x1802b7dd3  cmp     [rdi], r15
0x1802b7dd6  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x1802b7ddd  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b7de2  setnz   al
0x1802b7de5  mov     [rsi], al
0x1802b7de7  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b7dec  mov     ebx, eax
0x1802b7dee  test    eax, eax
0x1802b7df0  jns     short loc_1802B7DFC
0x1802b7df2  mov     edx, 144h
0x1802b7df7  jmp     loc_1802B7D37
0x1802b7dfc  mov     rcx, [rsp+2A0h+var_270]
0x1802b7e01  mov     [rsp+2A0h+var_270], r15
0x1802b7e06  test    rcx, rcx
0x1802b7e09  jz      short loc_1802B7E11
0x1802b7e0b  call    cs:__imp_SRCache_Free
0x1802b7e11  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7e16  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7e1b  test    rcx, rcx
0x1802b7e1e  jz      short loc_1802B7E26
0x1802b7e20  call    cs:__imp_SRCacheContext_Close
0x1802b7e26  xor     eax, eax
0x1802b7e28  mov     rcx, [rbp+1A0h+var_28]
0x1802b7e2f  xor     rcx, rsp; StackCookie
0x1802b7e32  call    __security_check_cookie
0x1802b7e37  mov     rbx, [rsp+2A0h+arg_10]
0x1802b7e3f  add     rsp, 280h
0x1802b7e46  pop     r15
0x1802b7e48  pop     r14
0x1802b7e4a  pop     rdi
0x1802b7e4b  pop     rsi
0x1802b7e4c  pop     rbp
0x1802b7e4d  retn
```
