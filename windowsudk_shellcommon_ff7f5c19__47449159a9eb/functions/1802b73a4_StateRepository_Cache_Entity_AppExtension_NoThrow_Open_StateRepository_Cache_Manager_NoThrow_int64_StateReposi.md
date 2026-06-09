# StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b73a4`
- end: `0x1802b764a`
- name: `?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b4fa0`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b73a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b74eb`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b74eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7592`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7592`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b755c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7607`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b755c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7607`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b746c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b761c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b746c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b761c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b740f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b740f`

## string_xrefs

- `0x1802b74fc`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b742e`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b75b1`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b744e`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b753a`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b73f9`: `AppExtension\Data`
- `0x1802b75d2`: `AppExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"AppExtension\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
    v9 = 312;
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
    v12 = 315;
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
    v12 = 316;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"AppExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 318;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
0x1802b73a4  mov     [rsp-8+arg_10], rbx
0x1802b73a9  push    rbp
0x1802b73aa  push    rsi
0x1802b73ab  push    rdi
0x1802b73ac  push    r14
0x1802b73ae  push    r15
0x1802b73b0  lea     rbp, [rsp-180h]
0x1802b73b8  sub     rsp, 280h
0x1802b73bf  mov     rax, cs:__security_cookie
0x1802b73c6  xor     rax, rsp
0x1802b73c9  mov     [rbp+1A0h+var_28], rax
0x1802b73d0  mov     rcx, [rcx]
0x1802b73d3  lea     rax, [rsp+2A0h+var_280]
0x1802b73d8  mov     rsi, r9
0x1802b73db  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b73e2  mov     rdi, r8
0x1802b73e5  mov     [rbp+1A0h+var_40], 1
0x1802b73ec  mov     r14, rdx
0x1802b73ef  lea     r9, [rbp+1A0h+var_48]
0x1802b73f6  xor     r15d, r15d
0x1802b73f9  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x1802b7400  xor     r8d, r8d
0x1802b7403  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b7408  mov     [rbp+1A0h+var_48], r15
0x1802b740f  call    cs:__imp_SRCacheContext_Open
0x1802b7415  lea     rcx, [rbp+1A0h+var_50]
0x1802b741c  mov     ebx, eax
0x1802b741e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7423  test    ebx, ebx
0x1802b7425  jns     short loc_1802B7479
0x1802b7427  mov     rcx, [rbp+1A8h]; this
0x1802b742e  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7435  mov     r9d, ebx; char *
0x1802b7438  mov     edx, 18Ch; void *
0x1802b743d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7442  mov     edx, 137h; void *
0x1802b7447  mov     rcx, [rbp+1A8h]; this
0x1802b744e  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7455  mov     r9d, ebx; char *
0x1802b7458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b745d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7462  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7467  test    rcx, rcx
0x1802b746a  jz      short loc_1802B7472
0x1802b746c  call    cs:__imp_SRCacheContext_Close
0x1802b7472  mov     eax, ebx
0x1802b7474  jmp     loc_1802B7624
0x1802b7479  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b747e  setnz   al
0x1802b7481  test    al, al
0x1802b7483  jnz     short loc_1802B7491
0x1802b7485  mov     ebx, 80670012h
0x1802b748a  mov     edx, 138h
0x1802b748f  jmp     short loc_1802B7447
0x1802b7491  mov     ebx, 200h
0x1802b7496  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b749b  mov     r8d, ebx; Size
0x1802b749e  xor     edx, edx; Val
0x1802b74a0  call    memset_0
0x1802b74a5  mov     r8d, ebx; Size
0x1802b74a8  mov     [rsp+2A0h+var_270], r15
0x1802b74ad  xor     edx, edx; Val
0x1802b74af  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b74b4  call    memset_0
0x1802b74b9  mov     r9d, 10h
0x1802b74bf  mov     [rbp+1A0h+var_68], r15
0x1802b74c6  lea     rax, [rsp+2A0h+var_268]
0x1802b74cb  mov     [rbp+1A0h+var_60], 100h
0x1802b74d6  lea     rdx, [rbp+1A0h+var_50]
0x1802b74dd  mov     [rbp+1A0h+var_58], rax
0x1802b74e4  mov     rcx, r14
0x1802b74e7  lea     r8d, [r9+1]
0x1802b74eb  call    cs:__imp__o__ui64tow_s
0x1802b74f1  test    eax, eax
0x1802b74f3  jz      short loc_1802B7517
0x1802b74f5  mov     rcx, [rbp+1A8h]; this
0x1802b74fc  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7503  mov     ebx, 8000FFFFh
0x1802b7508  mov     edx, 166h; void *
0x1802b750d  mov     r9d, ebx; char *
0x1802b7510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7515  jmp     short loc_1802B752E
0x1802b7517  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b751e  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b7523  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b7528  mov     ebx, eax
0x1802b752a  test    eax, eax
0x1802b752c  jns     short loc_1802B7567
0x1802b752e  mov     edx, 13Bh; void *
0x1802b7533  mov     rcx, [rbp+1A8h]; this
0x1802b753a  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7541  mov     r9d, ebx; char *
0x1802b7544  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7549  mov     rcx, [rsp+2A0h+var_270]
0x1802b754e  mov     [rsp+2A0h+var_270], r15
0x1802b7553  test    rcx, rcx
0x1802b7556  jz      loc_1802B745D
0x1802b755c  call    cs:__imp_SRCache_Free
0x1802b7562  jmp     loc_1802B745D
0x1802b7567  mov     rdx, [rbp+1A0h+var_58]
0x1802b756e  lea     r9, [rbp+1A0h+var_48]
0x1802b7575  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b757a  xor     r8d, r8d
0x1802b757d  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b7584  mov     [rbp+1A0h+var_48], r15
0x1802b758b  mov     [rbp+1A0h+var_40], 1
0x1802b7592  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b7598  lea     rcx, [rbp+1A0h+var_50]
0x1802b759f  mov     ebx, eax
0x1802b75a1  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b75a6  test    ebx, ebx
0x1802b75a8  jns     short loc_1802B75CF
0x1802b75aa  mov     rcx, [rbp+1A8h]; this
0x1802b75b1  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b75b8  mov     r9d, ebx; char *
0x1802b75bb  mov     edx, 1B0h; void *
0x1802b75c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b75c5  mov     edx, 13Ch
0x1802b75ca  jmp     loc_1802B7533
0x1802b75cf  cmp     [rdi], r15
0x1802b75d2  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x1802b75d9  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b75de  setnz   al
0x1802b75e1  mov     [rsi], al
0x1802b75e3  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b75e8  mov     ebx, eax
0x1802b75ea  test    eax, eax
0x1802b75ec  jns     short loc_1802B75F8
0x1802b75ee  mov     edx, 13Eh
0x1802b75f3  jmp     loc_1802B7533
0x1802b75f8  mov     rcx, [rsp+2A0h+var_270]
0x1802b75fd  mov     [rsp+2A0h+var_270], r15
0x1802b7602  test    rcx, rcx
0x1802b7605  jz      short loc_1802B760D
0x1802b7607  call    cs:__imp_SRCache_Free
0x1802b760d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7612  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7617  test    rcx, rcx
0x1802b761a  jz      short loc_1802B7622
0x1802b761c  call    cs:__imp_SRCacheContext_Close
0x1802b7622  xor     eax, eax
0x1802b7624  mov     rcx, [rbp+1A0h+var_28]
0x1802b762b  xor     rcx, rsp; StackCookie
0x1802b762e  call    __security_check_cookie
0x1802b7633  mov     rbx, [rsp+2A0h+arg_10]
0x1802b763b  add     rsp, 280h
0x1802b7642  pop     r15
0x1802b7644  pop     r14
0x1802b7646  pop     rdi
0x1802b7647  pop     rsi
0x1802b7648  pop     rbp
0x1802b7649  retn
```
