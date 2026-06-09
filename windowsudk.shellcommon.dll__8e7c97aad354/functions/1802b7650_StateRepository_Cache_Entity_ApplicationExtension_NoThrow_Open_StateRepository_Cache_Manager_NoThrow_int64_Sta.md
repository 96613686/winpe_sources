# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b7650`
- end: `0x1802b78f6`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b50a4`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b7650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7797`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7797`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b783e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b783e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7808`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b78b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b7808`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b78b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7718`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b78c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7718`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b78c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b76bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b76bb`

## string_xrefs

- `0x1802b77a8`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b76da`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b785d`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b76a5`: `ApplicationExtension\Data`
- `0x1802b787e`: `ApplicationExtension\Data`
- `0x1802b76fa`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1802b77e6`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v9 = 365;
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
    v12 = 368;
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
    v12 = 369;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 371;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x1802b7650  mov     [rsp-8+arg_10], rbx
0x1802b7655  push    rbp
0x1802b7656  push    rsi
0x1802b7657  push    rdi
0x1802b7658  push    r14
0x1802b765a  push    r15
0x1802b765c  lea     rbp, [rsp-180h]
0x1802b7664  sub     rsp, 280h
0x1802b766b  mov     rax, cs:__security_cookie
0x1802b7672  xor     rax, rsp
0x1802b7675  mov     [rbp+1A0h+var_28], rax
0x1802b767c  mov     rcx, [rcx]
0x1802b767f  lea     rax, [rsp+2A0h+var_280]
0x1802b7684  mov     rsi, r9
0x1802b7687  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b768e  mov     rdi, r8
0x1802b7691  mov     [rbp+1A0h+var_40], 1
0x1802b7698  mov     r14, rdx
0x1802b769b  lea     r9, [rbp+1A0h+var_48]
0x1802b76a2  xor     r15d, r15d
0x1802b76a5  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x1802b76ac  xor     r8d, r8d
0x1802b76af  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b76b4  mov     [rbp+1A0h+var_48], r15
0x1802b76bb  call    cs:__imp_SRCacheContext_Open
0x1802b76c1  lea     rcx, [rbp+1A0h+var_50]
0x1802b76c8  mov     ebx, eax
0x1802b76ca  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b76cf  test    ebx, ebx
0x1802b76d1  jns     short loc_1802B7725
0x1802b76d3  mov     rcx, [rbp+1A8h]; this
0x1802b76da  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b76e1  mov     r9d, ebx; char *
0x1802b76e4  mov     edx, 18Ch; void *
0x1802b76e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b76ee  mov     edx, 16Ch; void *
0x1802b76f3  mov     rcx, [rbp+1A8h]; this
0x1802b76fa  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7701  mov     r9d, ebx; char *
0x1802b7704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7709  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b770e  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7713  test    rcx, rcx
0x1802b7716  jz      short loc_1802B771E
0x1802b7718  call    cs:__imp_SRCacheContext_Close
0x1802b771e  mov     eax, ebx
0x1802b7720  jmp     loc_1802B78D0
0x1802b7725  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b772a  setnz   al
0x1802b772d  test    al, al
0x1802b772f  jnz     short loc_1802B773D
0x1802b7731  mov     ebx, 80670012h
0x1802b7736  mov     edx, 16Dh
0x1802b773b  jmp     short loc_1802B76F3
0x1802b773d  mov     ebx, 200h
0x1802b7742  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7747  mov     r8d, ebx; Size
0x1802b774a  xor     edx, edx; Val
0x1802b774c  call    memset_0
0x1802b7751  mov     r8d, ebx; Size
0x1802b7754  mov     [rsp+2A0h+var_270], r15
0x1802b7759  xor     edx, edx; Val
0x1802b775b  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7760  call    memset_0
0x1802b7765  mov     r9d, 10h
0x1802b776b  mov     [rbp+1A0h+var_68], r15
0x1802b7772  lea     rax, [rsp+2A0h+var_268]
0x1802b7777  mov     [rbp+1A0h+var_60], 100h
0x1802b7782  lea     rdx, [rbp+1A0h+var_50]
0x1802b7789  mov     [rbp+1A0h+var_58], rax
0x1802b7790  mov     rcx, r14
0x1802b7793  lea     r8d, [r9+1]
0x1802b7797  call    cs:__imp__o__ui64tow_s
0x1802b779d  test    eax, eax
0x1802b779f  jz      short loc_1802B77C3
0x1802b77a1  mov     rcx, [rbp+1A8h]; this
0x1802b77a8  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b77af  mov     ebx, 8000FFFFh
0x1802b77b4  mov     edx, 166h; void *
0x1802b77b9  mov     r9d, ebx; char *
0x1802b77bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b77c1  jmp     short loc_1802B77DA
0x1802b77c3  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b77ca  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b77cf  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b77d4  mov     ebx, eax
0x1802b77d6  test    eax, eax
0x1802b77d8  jns     short loc_1802B7813
0x1802b77da  mov     edx, 170h; void *
0x1802b77df  mov     rcx, [rbp+1A8h]; this
0x1802b77e6  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b77ed  mov     r9d, ebx; char *
0x1802b77f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b77f5  mov     rcx, [rsp+2A0h+var_270]
0x1802b77fa  mov     [rsp+2A0h+var_270], r15
0x1802b77ff  test    rcx, rcx
0x1802b7802  jz      loc_1802B7709
0x1802b7808  call    cs:__imp_SRCache_Free
0x1802b780e  jmp     loc_1802B7709
0x1802b7813  mov     rdx, [rbp+1A0h+var_58]
0x1802b781a  lea     r9, [rbp+1A0h+var_48]
0x1802b7821  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7826  xor     r8d, r8d
0x1802b7829  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b7830  mov     [rbp+1A0h+var_48], r15
0x1802b7837  mov     [rbp+1A0h+var_40], 1
0x1802b783e  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b7844  lea     rcx, [rbp+1A0h+var_50]
0x1802b784b  mov     ebx, eax
0x1802b784d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7852  test    ebx, ebx
0x1802b7854  jns     short loc_1802B787B
0x1802b7856  mov     rcx, [rbp+1A8h]; this
0x1802b785d  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7864  mov     r9d, ebx; char *
0x1802b7867  mov     edx, 1B0h; void *
0x1802b786c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7871  mov     edx, 171h
0x1802b7876  jmp     loc_1802B77DF
0x1802b787b  cmp     [rdi], r15
0x1802b787e  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x1802b7885  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b788a  setnz   al
0x1802b788d  mov     [rsi], al
0x1802b788f  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b7894  mov     ebx, eax
0x1802b7896  test    eax, eax
0x1802b7898  jns     short loc_1802B78A4
0x1802b789a  mov     edx, 173h
0x1802b789f  jmp     loc_1802B77DF
0x1802b78a4  mov     rcx, [rsp+2A0h+var_270]
0x1802b78a9  mov     [rsp+2A0h+var_270], r15
0x1802b78ae  test    rcx, rcx
0x1802b78b1  jz      short loc_1802B78B9
0x1802b78b3  call    cs:__imp_SRCache_Free
0x1802b78b9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b78be  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b78c3  test    rcx, rcx
0x1802b78c6  jz      short loc_1802B78CE
0x1802b78c8  call    cs:__imp_SRCacheContext_Close
0x1802b78ce  xor     eax, eax
0x1802b78d0  mov     rcx, [rbp+1A0h+var_28]
0x1802b78d7  xor     rcx, rsp; StackCookie
0x1802b78da  call    __security_check_cookie
0x1802b78df  mov     rbx, [rsp+2A0h+arg_10]
0x1802b78e7  add     rsp, 280h
0x1802b78ee  pop     r15
0x1802b78f0  pop     r14
0x1802b78f2  pop     rdi
0x1802b78f3  pop     rsi
0x1802b78f4  pop     rbp
0x1802b78f5  retn
```
