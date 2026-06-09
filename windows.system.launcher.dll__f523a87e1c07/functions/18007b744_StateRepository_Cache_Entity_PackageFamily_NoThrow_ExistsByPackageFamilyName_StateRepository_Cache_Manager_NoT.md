# StateRepository::Cache::Entity::PackageFamily_NoThrow::ExistsByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)

- ea: `0x18007b744`
- end: `0x18007b9f4`
- name: `?ExistsByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z`
- size: `688`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18007b600`

## callees

- `0x180004cf0`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180037224`
- `0x18007b744`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007b897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007b9b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007b897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007b9b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b92e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b9a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b9ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b92e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b9a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007b9ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007b8cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007b8cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007b79f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007b79f`

## string_xrefs

- `0x18007b7bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007b8ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007b7da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18007b870`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18007b90c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ExistsByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 v3; // rcx
  int IsEmpty; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  char v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h]
  __int64 v25; // [rsp+260h] [rbp+160h]
  _BYTE *v26; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v21 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v17 = 0;
  v19 = &v17;
  v20 = 0;
  IsEmpty = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v16);
    v6 = 125;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)IsEmpty,
      v16);
LABEL_4:
    v7 = v17;
    v17 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
    return (unsigned int)IsEmpty;
  }
  if ( !v17 )
  {
    IsEmpty = -2140733422;
    v6 = 126;
    goto LABEL_3;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append(
         (StateRepository::Cache::Key_NoThrow *)&v22,
         L"ProxyApp_cw5n1h2txyewy");
  IsEmpty = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v9,
      v16);
LABEL_11:
    v10 = v22;
    v22 = 0;
    if ( v10 )
      SRCache_Free(v10);
    goto LABEL_4;
  }
  v19 = &v18;
  v18 = 0;
  v20 = 0;
  v21 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v17, v26, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v16);
    v11 = 133;
    goto LABEL_15;
  }
  if ( v18 )
  {
    LOBYTE(v16) = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty(
                (StateRepository::Cache::Context_NoThrow *)&v18,
                (bool *)&v16);
    if ( IsEmpty < 0 )
    {
      v11 = 137;
      goto LABEL_15;
    }
    *a3 = (_BYTE)v16 == 0;
  }
  IsEmpty = StateRepository::Cache::Context_NoThrow::AddToCache(
              (StateRepository::Cache::Context_NoThrow *)&v17,
              L"PackageFamily\\Index\\PackageFamilyName");
  if ( IsEmpty < 0 )
  {
    v11 = 141;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)IsEmpty,
      v16);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_11;
  }
  v13 = v18;
  v18 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  v14 = v22;
  v22 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18007b744  mov     [rsp-8+arg_8], rbx
0x18007b749  push    rbp
0x18007b74a  push    rsi
0x18007b74b  push    rdi
0x18007b74c  lea     rbp, [rsp-180h]
0x18007b754  sub     rsp, 280h
0x18007b75b  mov     rax, cs:__security_cookie
0x18007b762  xor     rax, rsp
0x18007b765  mov     [rbp+190h+var_20], rax
0x18007b76c  xor     esi, esi
0x18007b76e  mov     [rsp+290h+var_248], 1
0x18007b773  mov     [r8], sil
0x18007b776  lea     rax, [rsp+290h+var_268]
0x18007b77b  mov     rcx, [rcx]
0x18007b77e  lea     r9, [rsp+290h+var_250]
0x18007b783  mov     rdi, r8
0x18007b786  mov     [rsp+290h+var_268], rsi
0x18007b78b  xor     r8d, r8d
0x18007b78e  mov     [rsp+290h+var_258], rax
0x18007b793  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18007b79a  mov     [rsp+290h+var_250], rsi
0x18007b79f  call    cs:__imp_SRCacheContext_Open
0x18007b7a5  lea     rcx, [rsp+290h+var_258]
0x18007b7aa  mov     ebx, eax
0x18007b7ac  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007b7b1  test    ebx, ebx
0x18007b7b3  jns     short loc_18007B805
0x18007b7b5  mov     rcx, [rbp+198h]; this
0x18007b7bc  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b7c3  mov     r9d, ebx; char *
0x18007b7c6  mov     edx, 18Ch; void *
0x18007b7cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b7d0  lea     edx, [rsi+7Dh]; void *
0x18007b7d3  mov     rcx, [rbp+198h]; this
0x18007b7da  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b7e1  mov     r9d, ebx; char *
0x18007b7e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b7e9  mov     rcx, [rsp+290h+var_268]
0x18007b7ee  mov     [rsp+290h+var_268], rsi
0x18007b7f3  test    rcx, rcx
0x18007b7f6  jz      short loc_18007B7FE
0x18007b7f8  call    cs:__imp_SRCacheContext_Close
0x18007b7fe  mov     eax, ebx
0x18007b800  jmp     loc_18007B9D2
0x18007b805  cmp     [rsp+290h+var_268], rsi
0x18007b80a  setnz   al
0x18007b80d  test    al, al
0x18007b80f  jnz     short loc_18007B81D
0x18007b811  mov     ebx, 80670012h
0x18007b816  mov     edx, 7Eh ; '~'
0x18007b81b  jmp     short loc_18007B7D3
0x18007b81d  xor     edx, edx; Val
0x18007b81f  mov     [rsp+290h+var_240], rsi
0x18007b824  mov     r8d, 200h; Size
0x18007b82a  lea     rcx, [rsp+290h+var_238]; void *
0x18007b82f  call    memset_0
0x18007b834  lea     rax, [rsp+290h+var_238]
0x18007b839  mov     [rbp+190h+var_38], rsi
0x18007b840  lea     rdx, aProxyappCw5n1h; "ProxyApp_cw5n1h2txyewy"
0x18007b847  mov     [rbp+190h+var_28], rax
0x18007b84e  lea     rcx, [rsp+290h+var_240]; this
0x18007b853  mov     [rbp+190h+var_30], 100h
0x18007b85e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18007b863  mov     ebx, eax
0x18007b865  test    eax, eax
0x18007b867  jns     short loc_18007B8A2
0x18007b869  mov     rcx, [rbp+198h]; this
0x18007b870  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b877  mov     r9d, eax; char *
0x18007b87a  mov     edx, 81h; void *
0x18007b87f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b884  mov     rcx, [rsp+290h+var_240]
0x18007b889  mov     [rsp+290h+var_240], rsi
0x18007b88e  test    rcx, rcx
0x18007b891  jz      loc_18007B7E9
0x18007b897  call    cs:__imp_SRCache_Free
0x18007b89d  jmp     loc_18007B7E9
0x18007b8a2  mov     rdx, [rbp+190h+var_28]
0x18007b8a9  lea     rax, [rsp+290h+var_260]
0x18007b8ae  mov     rcx, [rsp+290h+var_268]
0x18007b8b3  lea     r9, [rsp+290h+var_250]
0x18007b8b8  xor     r8d, r8d
0x18007b8bb  mov     [rsp+290h+var_258], rax
0x18007b8c0  mov     [rsp+290h+var_260], rsi
0x18007b8c5  mov     [rsp+290h+var_250], rsi
0x18007b8ca  mov     [rsp+290h+var_248], 1
0x18007b8cf  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007b8d5  lea     rcx, [rsp+290h+var_258]
0x18007b8da  mov     ebx, eax
0x18007b8dc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007b8e1  test    ebx, ebx
0x18007b8e3  jns     short loc_18007B939
0x18007b8e5  mov     rcx, [rbp+198h]; this
0x18007b8ec  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b8f3  mov     r9d, ebx; char *
0x18007b8f6  mov     edx, 1B0h; void *
0x18007b8fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b900  mov     edx, 85h; void *
0x18007b905  mov     rcx, [rbp+198h]; this
0x18007b90c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007b913  mov     r9d, ebx; char *
0x18007b916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b91b  mov     rcx, [rsp+290h+var_260]
0x18007b920  mov     [rsp+290h+var_260], rsi
0x18007b925  test    rcx, rcx
0x18007b928  jz      loc_18007B884
0x18007b92e  call    cs:__imp_SRCacheContext_Close
0x18007b934  jmp     loc_18007B884
0x18007b939  cmp     [rsp+290h+var_260], rsi
0x18007b93e  setnz   al
0x18007b941  test    al, al
0x18007b943  jz      short loc_18007B970
0x18007b945  lea     rdx, [rsp+290h+var_270]; bool *
0x18007b94a  mov     byte ptr [rsp+290h+var_270], sil
0x18007b94f  lea     rcx, [rsp+290h+var_260]; this
0x18007b954  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x18007b959  mov     ebx, eax
0x18007b95b  test    eax, eax
0x18007b95d  jns     short loc_18007B966
0x18007b95f  mov     edx, 89h
0x18007b964  jmp     short loc_18007B905
0x18007b966  cmp     byte ptr [rsp+290h+var_270], sil
0x18007b96b  setz    al
0x18007b96e  mov     [rdi], al
0x18007b970  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18007b977  lea     rcx, [rsp+290h+var_268]; this
0x18007b97c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007b981  mov     ebx, eax
0x18007b983  test    eax, eax
0x18007b985  jns     short loc_18007B991
0x18007b987  mov     edx, 8Dh
0x18007b98c  jmp     loc_18007B905
0x18007b991  mov     rcx, [rsp+290h+var_260]
0x18007b996  mov     [rsp+290h+var_260], rsi
0x18007b99b  test    rcx, rcx
0x18007b99e  jz      short loc_18007B9A6
0x18007b9a0  call    cs:__imp_SRCacheContext_Close
0x18007b9a6  mov     rcx, [rsp+290h+var_240]
0x18007b9ab  mov     [rsp+290h+var_240], rsi
0x18007b9b0  test    rcx, rcx
0x18007b9b3  jz      short loc_18007B9BB
0x18007b9b5  call    cs:__imp_SRCache_Free
0x18007b9bb  mov     rcx, [rsp+290h+var_268]
0x18007b9c0  mov     [rsp+290h+var_268], rsi
0x18007b9c5  test    rcx, rcx
0x18007b9c8  jz      short loc_18007B9D0
0x18007b9ca  call    cs:__imp_SRCacheContext_Close
0x18007b9d0  xor     eax, eax
0x18007b9d2  mov     rcx, [rbp+190h+var_20]
0x18007b9d9  xor     rcx, rsp; StackCookie
0x18007b9dc  call    __security_check_cookie
0x18007b9e1  mov     rbx, [rsp+290h+arg_8]
0x18007b9e9  add     rsp, 280h
0x18007b9f0  pop     rdi
0x18007b9f1  pop     rsi
0x18007b9f2  pop     rbp
0x18007b9f3  retn
```
