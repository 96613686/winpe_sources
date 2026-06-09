# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800b8d88`
- end: `0x1800b8fc5`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b5054`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800b8d88`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ee1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ee1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b8e46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b8f97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b8e46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b8f97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800b8f0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800b8f0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b8deb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b8deb`

## string_xrefs

- `0x1800b8e08`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b8f2c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b8e28`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800b8ebf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
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
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationUser\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 505;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
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
    v9 = 506;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 509;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 510;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationUser\\Data");
  if ( v8 < 0 )
  {
    v12 = 512;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x1800b8d88  mov     [rsp-8+arg_10], rbx
0x1800b8d8d  push    rbp
0x1800b8d8e  push    rsi
0x1800b8d8f  push    rdi
0x1800b8d90  push    r14
0x1800b8d92  push    r15
0x1800b8d94  lea     rbp, [rsp-170h]
0x1800b8d9c  sub     rsp, 270h
0x1800b8da3  mov     rax, cs:__security_cookie
0x1800b8daa  xor     rax, rsp
0x1800b8dad  mov     [rbp+190h+var_30], rax
0x1800b8db4  mov     rcx, [rcx]
0x1800b8db7  lea     rax, [rsp+290h+var_270]
0x1800b8dbc  mov     rsi, r9
0x1800b8dbf  mov     [rsp+290h+var_268], rax
0x1800b8dc4  mov     rdi, r8
0x1800b8dc7  mov     [rsp+290h+var_258], 1
0x1800b8dcc  mov     r14, rdx
0x1800b8dcf  lea     r9, [rsp+290h+var_260]
0x1800b8dd4  xor     r15d, r15d
0x1800b8dd7  lea     rdx, aApplicationuse_0; "ApplicationUser\\Data"
0x1800b8dde  xor     r8d, r8d
0x1800b8de1  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800b8de6  mov     [rsp+290h+var_260], r15
0x1800b8deb  call    cs:__imp_SRCacheContext_Open
0x1800b8df1  lea     rcx, [rsp+290h+var_268]
0x1800b8df6  mov     ebx, eax
0x1800b8df8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b8dfd  test    ebx, ebx
0x1800b8dff  jns     short loc_1800B8E53
0x1800b8e01  mov     rcx, [rbp+198h]; this
0x1800b8e08  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b8e0f  mov     r9d, ebx; char *
0x1800b8e12  mov     edx, 18Ch; void *
0x1800b8e17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8e1c  mov     edx, 1F9h; void *
0x1800b8e21  mov     rcx, [rbp+198h]; this
0x1800b8e28  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b8e2f  mov     r9d, ebx; char *
0x1800b8e32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8e37  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800b8e3c  mov     qword ptr [rsp+290h+var_270], r15
0x1800b8e41  test    rcx, rcx
0x1800b8e44  jz      short loc_1800B8E4C
0x1800b8e46  call    cs:__imp_SRCacheContext_Close
0x1800b8e4c  mov     eax, ebx
0x1800b8e4e  jmp     loc_1800B8F9F
0x1800b8e53  cmp     qword ptr [rsp+290h+var_270], r15
0x1800b8e58  setnz   al
0x1800b8e5b  test    al, al
0x1800b8e5d  jnz     short loc_1800B8E6B
0x1800b8e5f  mov     ebx, 80670012h
0x1800b8e64  mov     edx, 1FAh
0x1800b8e69  jmp     short loc_1800B8E21
0x1800b8e6b  xor     edx, edx; Val
0x1800b8e6d  mov     [rsp+290h+var_250], r15
0x1800b8e72  mov     r8d, 200h; Size
0x1800b8e78  lea     rcx, [rsp+290h+var_248]; void *
0x1800b8e7d  call    memset_0
0x1800b8e82  lea     rax, [rsp+290h+var_248]
0x1800b8e87  mov     [rbp+190h+var_48], r15
0x1800b8e8e  mov     rdx, r14; unsigned __int64
0x1800b8e91  mov     [rbp+190h+var_38], rax
0x1800b8e98  lea     rcx, [rsp+290h+var_250]; this
0x1800b8e9d  mov     [rbp+190h+var_40], 100h
0x1800b8ea8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800b8ead  mov     ebx, eax
0x1800b8eaf  test    eax, eax
0x1800b8eb1  jns     short loc_1800B8EEC
0x1800b8eb3  mov     edx, 1FDh; void *
0x1800b8eb8  mov     rcx, [rbp+198h]; this
0x1800b8ebf  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b8ec6  mov     r9d, ebx; char *
0x1800b8ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8ece  mov     rcx, [rsp+290h+var_250]
0x1800b8ed3  mov     [rsp+290h+var_250], r15
0x1800b8ed8  test    rcx, rcx
0x1800b8edb  jz      loc_1800B8E37
0x1800b8ee1  call    cs:__imp_SRCache_Free
0x1800b8ee7  jmp     loc_1800B8E37
0x1800b8eec  mov     rdx, [rbp+190h+var_38]
0x1800b8ef3  lea     r9, [rsp+290h+var_260]
0x1800b8ef8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800b8efd  xor     r8d, r8d
0x1800b8f00  mov     [rsp+290h+var_268], rdi
0x1800b8f05  mov     [rsp+290h+var_260], r15
0x1800b8f0a  mov     [rsp+290h+var_258], 1
0x1800b8f0f  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800b8f15  lea     rcx, [rsp+290h+var_268]
0x1800b8f1a  mov     ebx, eax
0x1800b8f1c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b8f21  test    ebx, ebx
0x1800b8f23  jns     short loc_1800B8F4A
0x1800b8f25  mov     rcx, [rbp+198h]; this
0x1800b8f2c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b8f33  mov     r9d, ebx; char *
0x1800b8f36  mov     edx, 1B0h; void *
0x1800b8f3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8f40  mov     edx, 1FEh
0x1800b8f45  jmp     loc_1800B8EB8
0x1800b8f4a  cmp     [rdi], r15
0x1800b8f4d  lea     rdx, aApplicationuse_0; "ApplicationUser\\Data"
0x1800b8f54  lea     rcx, [rsp+290h+var_270]; this
0x1800b8f59  setnz   al
0x1800b8f5c  mov     [rsi], al
0x1800b8f5e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b8f63  mov     ebx, eax
0x1800b8f65  test    eax, eax
0x1800b8f67  jns     short loc_1800B8F73
0x1800b8f69  mov     edx, 200h
0x1800b8f6e  jmp     loc_1800B8EB8
0x1800b8f73  mov     rcx, [rsp+290h+var_250]
0x1800b8f78  mov     [rsp+290h+var_250], r15
0x1800b8f7d  test    rcx, rcx
0x1800b8f80  jz      short loc_1800B8F88
0x1800b8f82  call    cs:__imp_SRCache_Free
0x1800b8f88  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800b8f8d  mov     qword ptr [rsp+290h+var_270], r15
0x1800b8f92  test    rcx, rcx
0x1800b8f95  jz      short loc_1800B8F9D
0x1800b8f97  call    cs:__imp_SRCacheContext_Close
0x1800b8f9d  xor     eax, eax
0x1800b8f9f  mov     rcx, [rbp+190h+var_30]
0x1800b8fa6  xor     rcx, rsp; StackCookie
0x1800b8fa9  call    __security_check_cookie
0x1800b8fae  mov     rbx, [rsp+290h+arg_10]
0x1800b8fb6  add     rsp, 270h
0x1800b8fbd  pop     r15
0x1800b8fbf  pop     r14
0x1800b8fc1  pop     rdi
0x1800b8fc2  pop     rsi
0x1800b8fc3  pop     rbp
0x1800b8fc4  retn
```
