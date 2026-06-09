# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b78fc`
- end: `0x1802b7ba2`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802b5198`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b78fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7a43`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7a43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7aea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b7aea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7ab4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7b5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7ab4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7b5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b79c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7b74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b79c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7b74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7967`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7967`

## string_xrefs

- `0x1802b7a54`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b7986`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b7b09`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b79a6`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1802b7a92`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
    v9 = 434;
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
    v12 = 437;
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
    v12 = 438;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Application\\Data");
  if ( v8 < 0 )
  {
    v12 = 440;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
0x1802b78fc  mov     [rsp-8+arg_10], rbx
0x1802b7901  push    rbp
0x1802b7902  push    rsi
0x1802b7903  push    rdi
0x1802b7904  push    r14
0x1802b7906  push    r15
0x1802b7908  lea     rbp, [rsp-180h]
0x1802b7910  sub     rsp, 280h
0x1802b7917  mov     rax, cs:__security_cookie
0x1802b791e  xor     rax, rsp
0x1802b7921  mov     [rbp+1A0h+var_28], rax
0x1802b7928  mov     rcx, [rcx]
0x1802b792b  lea     rax, [rsp+2A0h+var_280]
0x1802b7930  mov     rsi, r9
0x1802b7933  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b793a  mov     rdi, r8
0x1802b793d  mov     [rbp+1A0h+var_40], 1
0x1802b7944  mov     r14, rdx
0x1802b7947  lea     r9, [rbp+1A0h+var_48]
0x1802b794e  xor     r15d, r15d
0x1802b7951  lea     rdx, aApplicationDat; "Application\\Data"
0x1802b7958  xor     r8d, r8d
0x1802b795b  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b7960  mov     [rbp+1A0h+var_48], r15
0x1802b7967  call    cs:__imp_SRCacheContext_Open
0x1802b796d  lea     rcx, [rbp+1A0h+var_50]
0x1802b7974  mov     ebx, eax
0x1802b7976  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b797b  test    ebx, ebx
0x1802b797d  jns     short loc_1802B79D1
0x1802b797f  mov     rcx, [rbp+1A8h]; this
0x1802b7986  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b798d  mov     r9d, ebx; char *
0x1802b7990  mov     edx, 18Ch; void *
0x1802b7995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b799a  mov     edx, 1B1h; void *
0x1802b799f  mov     rcx, [rbp+1A8h]; this
0x1802b79a6  lea     r8, aOnecoreInterna_28; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b79ad  mov     r9d, ebx; char *
0x1802b79b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b79b5  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b79ba  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b79bf  test    rcx, rcx
0x1802b79c2  jz      short loc_1802B79CA
0x1802b79c4  call    cs:__imp_SRCacheContext_Close
0x1802b79ca  mov     eax, ebx
0x1802b79cc  jmp     loc_1802B7B7C
0x1802b79d1  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b79d6  setnz   al
0x1802b79d9  test    al, al
0x1802b79db  jnz     short loc_1802B79E9
0x1802b79dd  mov     ebx, 80670012h
0x1802b79e2  mov     edx, 1B2h
0x1802b79e7  jmp     short loc_1802B799F
0x1802b79e9  mov     ebx, 200h
0x1802b79ee  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b79f3  mov     r8d, ebx; Size
0x1802b79f6  xor     edx, edx; Val
0x1802b79f8  call    memset_0
0x1802b79fd  mov     r8d, ebx; Size
0x1802b7a00  mov     [rsp+2A0h+var_270], r15
0x1802b7a05  xor     edx, edx; Val
0x1802b7a07  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7a0c  call    memset_0
0x1802b7a11  mov     r9d, 10h
0x1802b7a17  mov     [rbp+1A0h+var_68], r15
0x1802b7a1e  lea     rax, [rsp+2A0h+var_268]
0x1802b7a23  mov     [rbp+1A0h+var_60], 100h
0x1802b7a2e  lea     rdx, [rbp+1A0h+var_50]
0x1802b7a35  mov     [rbp+1A0h+var_58], rax
0x1802b7a3c  mov     rcx, r14
0x1802b7a3f  lea     r8d, [r9+1]
0x1802b7a43  call    cs:__imp__o__ui64tow_s
0x1802b7a49  test    eax, eax
0x1802b7a4b  jz      short loc_1802B7A6F
0x1802b7a4d  mov     rcx, [rbp+1A8h]; this
0x1802b7a54  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7a5b  mov     ebx, 8000FFFFh
0x1802b7a60  mov     edx, 166h; void *
0x1802b7a65  mov     r9d, ebx; char *
0x1802b7a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7a6d  jmp     short loc_1802B7A86
0x1802b7a6f  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b7a76  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b7a7b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b7a80  mov     ebx, eax
0x1802b7a82  test    eax, eax
0x1802b7a84  jns     short loc_1802B7ABF
0x1802b7a86  mov     edx, 1B5h; void *
0x1802b7a8b  mov     rcx, [rbp+1A8h]; this
0x1802b7a92  lea     r8, aOnecoreInterna_28; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7a99  mov     r9d, ebx; char *
0x1802b7a9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7aa1  mov     rcx, [rsp+2A0h+var_270]
0x1802b7aa6  mov     [rsp+2A0h+var_270], r15
0x1802b7aab  test    rcx, rcx
0x1802b7aae  jz      loc_1802B79B5
0x1802b7ab4  call    cs:__imp_SRCache_Free
0x1802b7aba  jmp     loc_1802B79B5
0x1802b7abf  mov     rdx, [rbp+1A0h+var_58]
0x1802b7ac6  lea     r9, [rbp+1A0h+var_48]
0x1802b7acd  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7ad2  xor     r8d, r8d
0x1802b7ad5  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b7adc  mov     [rbp+1A0h+var_48], r15
0x1802b7ae3  mov     [rbp+1A0h+var_40], 1
0x1802b7aea  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b7af0  lea     rcx, [rbp+1A0h+var_50]
0x1802b7af7  mov     ebx, eax
0x1802b7af9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7afe  test    ebx, ebx
0x1802b7b00  jns     short loc_1802B7B27
0x1802b7b02  mov     rcx, [rbp+1A8h]; this
0x1802b7b09  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7b10  mov     r9d, ebx; char *
0x1802b7b13  mov     edx, 1B0h; void *
0x1802b7b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7b1d  mov     edx, 1B6h
0x1802b7b22  jmp     loc_1802B7A8B
0x1802b7b27  cmp     [rdi], r15
0x1802b7b2a  lea     rdx, aApplicationDat; "Application\\Data"
0x1802b7b31  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b7b36  setnz   al
0x1802b7b39  mov     [rsi], al
0x1802b7b3b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b7b40  mov     ebx, eax
0x1802b7b42  test    eax, eax
0x1802b7b44  jns     short loc_1802B7B50
0x1802b7b46  mov     edx, 1B8h
0x1802b7b4b  jmp     loc_1802B7A8B
0x1802b7b50  mov     rcx, [rsp+2A0h+var_270]
0x1802b7b55  mov     [rsp+2A0h+var_270], r15
0x1802b7b5a  test    rcx, rcx
0x1802b7b5d  jz      short loc_1802B7B65
0x1802b7b5f  call    cs:__imp_SRCache_Free
0x1802b7b65  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7b6a  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7b6f  test    rcx, rcx
0x1802b7b72  jz      short loc_1802B7B7A
0x1802b7b74  call    cs:__imp_SRCacheContext_Close
0x1802b7b7a  xor     eax, eax
0x1802b7b7c  mov     rcx, [rbp+1A0h+var_28]
0x1802b7b83  xor     rcx, rsp; StackCookie
0x1802b7b86  call    __security_check_cookie
0x1802b7b8b  mov     rbx, [rsp+2A0h+arg_10]
0x1802b7b93  add     rsp, 280h
0x1802b7b9a  pop     r15
0x1802b7b9c  pop     r14
0x1802b7b9e  pop     rdi
0x1802b7b9f  pop     rsi
0x1802b7ba0  pop     rbp
0x1802b7ba1  retn
```
