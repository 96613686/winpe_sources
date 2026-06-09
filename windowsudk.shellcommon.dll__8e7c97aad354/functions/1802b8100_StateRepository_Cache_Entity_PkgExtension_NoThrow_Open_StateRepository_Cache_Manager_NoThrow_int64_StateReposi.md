# StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b8100`
- end: `0x1802b83a6`
- name: `?Open@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b55c0`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b8100`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b8247`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b8247`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b82ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b82ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b82b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8363`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b82b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8363`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b81c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8378`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b81c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8378`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b816b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b816b`

## string_xrefs

- `0x1802b8258`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b818a`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b830d`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b81aa`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b8296`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1802b8155`: `PkgExtension\Data`
- `0x1802b832e`: `PkgExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PkgExtension\\Data", 0, &v23);
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
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
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
         L"PkgExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 318;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
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
0x1802b8100  mov     [rsp-8+arg_10], rbx
0x1802b8105  push    rbp
0x1802b8106  push    rsi
0x1802b8107  push    rdi
0x1802b8108  push    r14
0x1802b810a  push    r15
0x1802b810c  lea     rbp, [rsp-180h]
0x1802b8114  sub     rsp, 280h
0x1802b811b  mov     rax, cs:__security_cookie
0x1802b8122  xor     rax, rsp
0x1802b8125  mov     [rbp+1A0h+var_28], rax
0x1802b812c  mov     rcx, [rcx]
0x1802b812f  lea     rax, [rsp+2A0h+var_280]
0x1802b8134  mov     rsi, r9
0x1802b8137  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b813e  mov     rdi, r8
0x1802b8141  mov     [rbp+1A0h+var_40], 1
0x1802b8148  mov     r14, rdx
0x1802b814b  lea     r9, [rbp+1A0h+var_48]
0x1802b8152  xor     r15d, r15d
0x1802b8155  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x1802b815c  xor     r8d, r8d
0x1802b815f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b8164  mov     [rbp+1A0h+var_48], r15
0x1802b816b  call    cs:__imp_SRCacheContext_Open
0x1802b8171  lea     rcx, [rbp+1A0h+var_50]
0x1802b8178  mov     ebx, eax
0x1802b817a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b817f  test    ebx, ebx
0x1802b8181  jns     short loc_1802B81D5
0x1802b8183  mov     rcx, [rbp+1A8h]; this
0x1802b818a  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8191  mov     r9d, ebx; char *
0x1802b8194  mov     edx, 18Ch; void *
0x1802b8199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b819e  mov     edx, 137h; void *
0x1802b81a3  mov     rcx, [rbp+1A8h]; this
0x1802b81aa  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b81b1  mov     r9d, ebx; char *
0x1802b81b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b81b9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b81be  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b81c3  test    rcx, rcx
0x1802b81c6  jz      short loc_1802B81CE
0x1802b81c8  call    cs:__imp_SRCacheContext_Close
0x1802b81ce  mov     eax, ebx
0x1802b81d0  jmp     loc_1802B8380
0x1802b81d5  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b81da  setnz   al
0x1802b81dd  test    al, al
0x1802b81df  jnz     short loc_1802B81ED
0x1802b81e1  mov     ebx, 80670012h
0x1802b81e6  mov     edx, 138h
0x1802b81eb  jmp     short loc_1802B81A3
0x1802b81ed  mov     ebx, 200h
0x1802b81f2  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b81f7  mov     r8d, ebx; Size
0x1802b81fa  xor     edx, edx; Val
0x1802b81fc  call    memset_0
0x1802b8201  mov     r8d, ebx; Size
0x1802b8204  mov     [rsp+2A0h+var_270], r15
0x1802b8209  xor     edx, edx; Val
0x1802b820b  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b8210  call    memset_0
0x1802b8215  mov     r9d, 10h
0x1802b821b  mov     [rbp+1A0h+var_68], r15
0x1802b8222  lea     rax, [rsp+2A0h+var_268]
0x1802b8227  mov     [rbp+1A0h+var_60], 100h
0x1802b8232  lea     rdx, [rbp+1A0h+var_50]
0x1802b8239  mov     [rbp+1A0h+var_58], rax
0x1802b8240  mov     rcx, r14
0x1802b8243  lea     r8d, [r9+1]
0x1802b8247  call    cs:__imp__o__ui64tow_s
0x1802b824d  test    eax, eax
0x1802b824f  jz      short loc_1802B8273
0x1802b8251  mov     rcx, [rbp+1A8h]; this
0x1802b8258  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b825f  mov     ebx, 8000FFFFh
0x1802b8264  mov     edx, 166h; void *
0x1802b8269  mov     r9d, ebx; char *
0x1802b826c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8271  jmp     short loc_1802B828A
0x1802b8273  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b827a  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b827f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b8284  mov     ebx, eax
0x1802b8286  test    eax, eax
0x1802b8288  jns     short loc_1802B82C3
0x1802b828a  mov     edx, 13Bh; void *
0x1802b828f  mov     rcx, [rbp+1A8h]; this
0x1802b8296  lea     r8, aOnecoreInterna_15; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b829d  mov     r9d, ebx; char *
0x1802b82a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b82a5  mov     rcx, [rsp+2A0h+var_270]
0x1802b82aa  mov     [rsp+2A0h+var_270], r15
0x1802b82af  test    rcx, rcx
0x1802b82b2  jz      loc_1802B81B9
0x1802b82b8  call    cs:__imp_SRCache_Free
0x1802b82be  jmp     loc_1802B81B9
0x1802b82c3  mov     rdx, [rbp+1A0h+var_58]
0x1802b82ca  lea     r9, [rbp+1A0h+var_48]
0x1802b82d1  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b82d6  xor     r8d, r8d
0x1802b82d9  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b82e0  mov     [rbp+1A0h+var_48], r15
0x1802b82e7  mov     [rbp+1A0h+var_40], 1
0x1802b82ee  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b82f4  lea     rcx, [rbp+1A0h+var_50]
0x1802b82fb  mov     ebx, eax
0x1802b82fd  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b8302  test    ebx, ebx
0x1802b8304  jns     short loc_1802B832B
0x1802b8306  mov     rcx, [rbp+1A8h]; this
0x1802b830d  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8314  mov     r9d, ebx; char *
0x1802b8317  mov     edx, 1B0h; void *
0x1802b831c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8321  mov     edx, 13Ch
0x1802b8326  jmp     loc_1802B828F
0x1802b832b  cmp     [rdi], r15
0x1802b832e  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x1802b8335  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b833a  setnz   al
0x1802b833d  mov     [rsi], al
0x1802b833f  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b8344  mov     ebx, eax
0x1802b8346  test    eax, eax
0x1802b8348  jns     short loc_1802B8354
0x1802b834a  mov     edx, 13Eh
0x1802b834f  jmp     loc_1802B828F
0x1802b8354  mov     rcx, [rsp+2A0h+var_270]
0x1802b8359  mov     [rsp+2A0h+var_270], r15
0x1802b835e  test    rcx, rcx
0x1802b8361  jz      short loc_1802B8369
0x1802b8363  call    cs:__imp_SRCache_Free
0x1802b8369  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b836e  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b8373  test    rcx, rcx
0x1802b8376  jz      short loc_1802B837E
0x1802b8378  call    cs:__imp_SRCacheContext_Close
0x1802b837e  xor     eax, eax
0x1802b8380  mov     rcx, [rbp+1A0h+var_28]
0x1802b8387  xor     rcx, rsp; StackCookie
0x1802b838a  call    __security_check_cookie
0x1802b838f  mov     rbx, [rsp+2A0h+arg_10]
0x1802b8397  add     rsp, 280h
0x1802b839e  pop     r15
0x1802b83a0  pop     r14
0x1802b83a2  pop     rdi
0x1802b83a3  pop     rsi
0x1802b83a4  pop     rbp
0x1802b83a5  retn
```
