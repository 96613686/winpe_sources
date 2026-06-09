# StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *)

- ea: `0x1802b867c`
- end: `0x1802b8943`
- name: `?OpenByName@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEB_W@Z`
- size: `711`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b4e88`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b867c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b885d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b885d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b882f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b88e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8900`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b882f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b88e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8900`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b86bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8753`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b879b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8915`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b86bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8753`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b879b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8915`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b86f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b86f8`

## string_xrefs

- `0x1802b8715`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b887a`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b8730`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b8773`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b880d`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b88bf`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b86da`: `PkgExtension\Index\Name`
- `0x1802b88a1`: `PkgExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const wchar_t *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  char v21; // [rsp+30h] [rbp-D0h]
  int v22[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  *(_QWORD *)v19 = v22;
  *(_QWORD *)v22 = 0;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_Open(v7, L"PkgExtension\\Index\\Name", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v19);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
LABEL_5:
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v22 )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)0x80670012LL,
      v19[0]);
LABEL_10:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v11;
  }
  memset_0(v24, 0, sizeof(v24));
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v8 < 0 )
  {
    v13 = 602;
    goto LABEL_15;
  }
  *(_QWORD *)v19 = this;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v19);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v13 = 605;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"PkgExtension\\Index\\Name");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1802b867c  mov     [rsp-8+arg_18], rbx
0x1802b8681  push    rbp
0x1802b8682  push    rsi
0x1802b8683  push    rdi
0x1802b8684  push    r14
0x1802b8686  push    r15
0x1802b8688  lea     rbp, [rsp-170h]
0x1802b8690  sub     rsp, 270h
0x1802b8697  mov     rax, cs:__security_cookie
0x1802b869e  xor     rax, rsp
0x1802b86a1  mov     [rbp+190h+var_30], rax
0x1802b86a8  mov     rbx, rcx
0x1802b86ab  xor     r15d, r15d
0x1802b86ae  mov     rcx, [rcx]
0x1802b86b1  mov     r14, r8
0x1802b86b4  mov     rsi, rdx
0x1802b86b7  mov     [rbx], r15
0x1802b86ba  test    rcx, rcx
0x1802b86bd  jz      short loc_1802B86C5
0x1802b86bf  call    cs:__imp_SRCacheContext_Close
0x1802b86c5  mov     [rbx+8], r15d
0x1802b86c9  lea     rax, [rsp+290h+var_258]
0x1802b86ce  mov     [rbx+10h], r15
0x1802b86d2  lea     r9, [rsp+290h+var_268]
0x1802b86d7  mov     rcx, [rsi]
0x1802b86da  lea     rdx, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x1802b86e1  xor     r8d, r8d
0x1802b86e4  mov     qword ptr [rsp+290h+var_270], rax; int
0x1802b86e9  mov     qword ptr [rsp+290h+var_258], r15
0x1802b86ee  mov     [rsp+290h+var_268], r15
0x1802b86f3  mov     [rsp+290h+var_260], 1
0x1802b86f8  call    cs:__imp_SRCacheContext_Open
0x1802b86fe  lea     rcx, [rsp+290h+var_270]
0x1802b8703  mov     edi, eax
0x1802b8705  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b870a  test    edi, edi
0x1802b870c  jns     short loc_1802B8760
0x1802b870e  mov     rcx, [rbp+198h]; this
0x1802b8715  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b871c  mov     r9d, edi; char *
0x1802b871f  mov     edx, 18Ch; void *
0x1802b8724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8729  mov     rcx, [rbp+198h]; this
0x1802b8730  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8737  mov     r9d, edi; char *
0x1802b873a  mov     edx, 256h; void *
0x1802b873f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8744  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b8749  mov     qword ptr [rsp+290h+var_258], r15
0x1802b874e  test    rcx, rcx
0x1802b8751  jz      short loc_1802B8759
0x1802b8753  call    cs:__imp_SRCacheContext_Close
0x1802b8759  mov     eax, edi
0x1802b875b  jmp     loc_1802B891D
0x1802b8760  cmp     qword ptr [rsp+290h+var_258], r15
0x1802b8765  setnz   al
0x1802b8768  test    al, al
0x1802b876a  jnz     short loc_1802B87A8
0x1802b876c  mov     rcx, [rbp+198h]; this
0x1802b8773  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b877a  mov     ebx, 80670012h
0x1802b877f  mov     edx, 257h; void *
0x1802b8784  mov     r9d, ebx; char *
0x1802b8787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b878c  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b8791  mov     qword ptr [rsp+290h+var_258], r15
0x1802b8796  test    rcx, rcx
0x1802b8799  jz      short loc_1802B87A1
0x1802b879b  call    cs:__imp_SRCacheContext_Close
0x1802b87a1  mov     eax, ebx
0x1802b87a3  jmp     loc_1802B891D
0x1802b87a8  mov     edi, 200h
0x1802b87ad  lea     rcx, [rsp+290h+var_248]; void *
0x1802b87b2  mov     r8d, edi; Size
0x1802b87b5  xor     edx, edx; Val
0x1802b87b7  call    memset_0
0x1802b87bc  mov     r8d, edi; Size
0x1802b87bf  mov     [rsp+290h+var_250], r15
0x1802b87c4  xor     edx, edx; Val
0x1802b87c6  lea     rcx, [rsp+290h+var_248]; void *
0x1802b87cb  call    memset_0
0x1802b87d0  lea     rax, [rsp+290h+var_248]
0x1802b87d5  mov     [rbp+190h+var_48], r15
0x1802b87dc  mov     rdx, r14; wchar_t *
0x1802b87df  mov     [rbp+190h+var_38], rax
0x1802b87e6  lea     rcx, [rsp+290h+var_250]; this
0x1802b87eb  mov     [rbp+190h+var_40], 100h
0x1802b87f6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b87fb  mov     edi, eax
0x1802b87fd  test    eax, eax
0x1802b87ff  jns     short loc_1802B883A
0x1802b8801  mov     edx, 25Ah; void *
0x1802b8806  mov     rcx, [rbp+198h]; this
0x1802b880d  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8814  mov     r9d, edi; char *
0x1802b8817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b881c  mov     rcx, [rsp+290h+var_250]
0x1802b8821  mov     [rsp+290h+var_250], r15
0x1802b8826  test    rcx, rcx
0x1802b8829  jz      loc_1802B8744
0x1802b882f  call    cs:__imp_SRCache_Free
0x1802b8835  jmp     loc_1802B8744
0x1802b883a  mov     rdx, [rbp+190h+var_38]
0x1802b8841  lea     r9, [rsp+290h+var_268]
0x1802b8846  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b884b  xor     r8d, r8d
0x1802b884e  mov     qword ptr [rsp+290h+var_270], rbx; int
0x1802b8853  mov     [rsp+290h+var_268], r15
0x1802b8858  mov     [rsp+290h+var_260], 1
0x1802b885d  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b8863  lea     rcx, [rsp+290h+var_270]
0x1802b8868  mov     edi, eax
0x1802b886a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b886f  test    edi, edi
0x1802b8871  jns     short loc_1802B8898
0x1802b8873  mov     rcx, [rbp+198h]; this
0x1802b887a  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8881  mov     r9d, edi; char *
0x1802b8884  mov     edx, 1B0h; void *
0x1802b8889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b888e  mov     edx, 25Dh
0x1802b8893  jmp     loc_1802B8806
0x1802b8898  cmp     [rbx], r15
0x1802b889b  jz      short loc_1802B88A1
0x1802b889d  mov     [rbx+10h], rsi
0x1802b88a1  lea     rdx, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x1802b88a8  lea     rcx, [rsp+290h+var_258]; this
0x1802b88ad  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b88b2  mov     ebx, eax
0x1802b88b4  test    eax, eax
0x1802b88b6  jns     short loc_1802B88F1
0x1802b88b8  mov     rcx, [rbp+198h]; this
0x1802b88bf  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b88c6  mov     r9d, eax; char *
0x1802b88c9  mov     edx, 263h; void *
0x1802b88ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b88d3  mov     rcx, [rsp+290h+var_250]
0x1802b88d8  mov     [rsp+290h+var_250], r15
0x1802b88dd  test    rcx, rcx
0x1802b88e0  jz      loc_1802B878C
0x1802b88e6  call    cs:__imp_SRCache_Free
0x1802b88ec  jmp     loc_1802B878C
0x1802b88f1  mov     rcx, [rsp+290h+var_250]
0x1802b88f6  mov     [rsp+290h+var_250], r15
0x1802b88fb  test    rcx, rcx
0x1802b88fe  jz      short loc_1802B8906
0x1802b8900  call    cs:__imp_SRCache_Free
0x1802b8906  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b890b  mov     qword ptr [rsp+290h+var_258], r15
0x1802b8910  test    rcx, rcx
0x1802b8913  jz      short loc_1802B891B
0x1802b8915  call    cs:__imp_SRCacheContext_Close
0x1802b891b  xor     eax, eax
0x1802b891d  mov     rcx, [rbp+190h+var_30]
0x1802b8924  xor     rcx, rsp; StackCookie
0x1802b8927  call    __security_check_cookie
0x1802b892c  mov     rbx, [rsp+290h+arg_18]
0x1802b8934  add     rsp, 270h
0x1802b893b  pop     r15
0x1802b893d  pop     r14
0x1802b893f  pop     rdi
0x1802b8940  pop     rsi
0x1802b8941  pop     rbp
0x1802b8942  retn
```
