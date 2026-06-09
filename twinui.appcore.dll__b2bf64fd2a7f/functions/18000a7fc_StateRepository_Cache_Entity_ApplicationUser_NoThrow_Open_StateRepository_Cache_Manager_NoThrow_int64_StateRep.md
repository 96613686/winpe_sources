# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000a7fc`
- end: `0x18000aa51`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `597`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b47c`

## callees

- `0x180008c58`
- `0x18000a7fc`
- `0x18000aa58`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a85f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a85f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a99b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a99b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a96d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aa0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a96d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aa0e`

## string_xrefs

- `0x18000a894`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a9b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a8b4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18000a94b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

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
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v18; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  char v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+248h] [rbp+148h]
  __int64 v24; // [rsp+250h] [rbp+150h]
  _BYTE *v25; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v18 = v17;
  v20 = 1;
  *(_QWORD *)v17 = 0;
  v19 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationUser\\Data", 0, &v19);
  if ( v20 )
  {
    v9 = *(_QWORD *)v18;
    *(_QWORD *)v18 = v19;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v10 = 505;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
LABEL_7:
    v11 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v17 )
  {
    v8 = -2140733422;
    v10 = 506;
    goto LABEL_6;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  if ( v8 < 0 )
  {
    v13 = 509;
    goto LABEL_14;
  }
  v18 = (int *)a3;
  v19 = 0;
  v20 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v25, 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v13 = 510;
    goto LABEL_14;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"ApplicationUser\\Data");
  if ( v8 < 0 )
  {
    v13 = 512;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_7;
  }
  v15 = v21;
  v21 = 0;
  if ( v15 )
    SRCache_Free();
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18000a7fc  mov     [rsp-8+arg_10], rbx
0x18000a801  push    rbp
0x18000a802  push    rsi
0x18000a803  push    rdi
0x18000a804  push    r14
0x18000a806  push    r15
0x18000a808  lea     rbp, [rsp-170h]
0x18000a810  sub     rsp, 270h
0x18000a817  mov     rax, cs:__security_cookie
0x18000a81e  xor     rax, rsp
0x18000a821  mov     [rbp+190h+var_30], rax
0x18000a828  mov     rcx, [rcx]
0x18000a82b  lea     rax, [rsp+290h+var_270]
0x18000a830  mov     rsi, r9
0x18000a833  mov     [rsp+290h+var_268], rax
0x18000a838  mov     rdi, r8
0x18000a83b  mov     [rsp+290h+var_258], 1
0x18000a840  mov     r14, rdx
0x18000a843  lea     r9, [rsp+290h+var_260]
0x18000a848  xor     r15d, r15d
0x18000a84b  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x18000a852  xor     r8d, r8d
0x18000a855  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000a85a  mov     [rsp+290h+var_260], r15
0x18000a85f  call    cs:__imp_SRCacheContext_Open
0x18000a865  mov     ebx, eax
0x18000a867  cmp     [rsp+290h+var_258], r15b
0x18000a86c  jz      short loc_18000A889
0x18000a86e  mov     r8, [rsp+290h+var_268]
0x18000a873  mov     rdx, [rsp+290h+var_260]
0x18000a878  mov     rcx, [r8]
0x18000a87b  mov     [r8], rdx
0x18000a87e  test    rcx, rcx
0x18000a881  jz      short loc_18000A889
0x18000a883  call    cs:__imp_SRCacheContext_Close
0x18000a889  test    ebx, ebx
0x18000a88b  jns     short loc_18000A8DF
0x18000a88d  mov     rcx, [rbp+198h]; this
0x18000a894  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a89b  mov     r9d, ebx; char *
0x18000a89e  mov     edx, 18Ch; void *
0x18000a8a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8a8  mov     edx, 1F9h; void *
0x18000a8ad  mov     rcx, [rbp+198h]; this
0x18000a8b4  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a8bb  mov     r9d, ebx; char *
0x18000a8be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8c3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000a8c8  mov     qword ptr [rsp+290h+var_270], r15
0x18000a8cd  test    rcx, rcx
0x18000a8d0  jz      short loc_18000A8D8
0x18000a8d2  call    cs:__imp_SRCacheContext_Close
0x18000a8d8  mov     eax, ebx
0x18000a8da  jmp     loc_18000AA2B
0x18000a8df  cmp     qword ptr [rsp+290h+var_270], r15
0x18000a8e4  setnz   al
0x18000a8e7  test    al, al
0x18000a8e9  jnz     short loc_18000A8F7
0x18000a8eb  mov     ebx, 80670012h
0x18000a8f0  mov     edx, 1FAh
0x18000a8f5  jmp     short loc_18000A8AD
0x18000a8f7  xor     edx, edx; Val
0x18000a8f9  mov     [rsp+290h+var_250], r15
0x18000a8fe  mov     r8d, 200h; Size
0x18000a904  lea     rcx, [rsp+290h+var_248]; void *
0x18000a909  call    memset_0
0x18000a90e  lea     rax, [rsp+290h+var_248]
0x18000a913  mov     [rbp+190h+var_48], r15
0x18000a91a  mov     rdx, r14; unsigned __int64
0x18000a91d  mov     [rbp+190h+var_38], rax
0x18000a924  lea     rcx, [rsp+290h+var_250]; this
0x18000a929  mov     [rbp+190h+var_40], 100h
0x18000a934  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000a939  mov     ebx, eax
0x18000a93b  test    eax, eax
0x18000a93d  jns     short loc_18000A978
0x18000a93f  mov     edx, 1FDh; void *
0x18000a944  mov     rcx, [rbp+198h]; this
0x18000a94b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a952  mov     r9d, ebx; char *
0x18000a955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a95a  mov     rcx, [rsp+290h+var_250]
0x18000a95f  mov     [rsp+290h+var_250], r15
0x18000a964  test    rcx, rcx
0x18000a967  jz      loc_18000A8C3
0x18000a96d  call    cs:__imp_SRCache_Free
0x18000a973  jmp     loc_18000A8C3
0x18000a978  mov     rdx, [rbp+190h+var_38]
0x18000a97f  lea     r9, [rsp+290h+var_260]
0x18000a984  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000a989  xor     r8d, r8d
0x18000a98c  mov     [rsp+290h+var_268], rdi
0x18000a991  mov     [rsp+290h+var_260], r15
0x18000a996  mov     [rsp+290h+var_258], 1
0x18000a99b  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000a9a1  lea     rcx, [rsp+290h+var_268]
0x18000a9a6  mov     ebx, eax
0x18000a9a8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000a9ad  test    ebx, ebx
0x18000a9af  jns     short loc_18000A9D6
0x18000a9b1  mov     rcx, [rbp+198h]; this
0x18000a9b8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a9bf  mov     r9d, ebx; char *
0x18000a9c2  mov     edx, 1B0h; void *
0x18000a9c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9cc  mov     edx, 1FEh
0x18000a9d1  jmp     loc_18000A944
0x18000a9d6  cmp     [rdi], r15
0x18000a9d9  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x18000a9e0  lea     rcx, [rsp+290h+var_270]; this
0x18000a9e5  setnz   al
0x18000a9e8  mov     [rsi], al
0x18000a9ea  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000a9ef  mov     ebx, eax
0x18000a9f1  test    eax, eax
0x18000a9f3  jns     short loc_18000A9FF
0x18000a9f5  mov     edx, 200h
0x18000a9fa  jmp     loc_18000A944
0x18000a9ff  mov     rcx, [rsp+290h+var_250]
0x18000aa04  mov     [rsp+290h+var_250], r15
0x18000aa09  test    rcx, rcx
0x18000aa0c  jz      short loc_18000AA14
0x18000aa0e  call    cs:__imp_SRCache_Free
0x18000aa14  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000aa19  mov     qword ptr [rsp+290h+var_270], r15
0x18000aa1e  test    rcx, rcx
0x18000aa21  jz      short loc_18000AA29
0x18000aa23  call    cs:__imp_SRCacheContext_Close
0x18000aa29  xor     eax, eax
0x18000aa2b  mov     rcx, [rbp+190h+var_30]
0x18000aa32  xor     rcx, rsp; StackCookie
0x18000aa35  call    __security_check_cookie
0x18000aa3a  mov     rbx, [rsp+290h+arg_10]
0x18000aa42  add     rsp, 270h
0x18000aa49  pop     r15
0x18000aa4b  pop     r14
0x18000aa4d  pop     rdi
0x18000aa4e  pop     rsi
0x18000aa4f  pop     rbp
0x18000aa50  retn
```
