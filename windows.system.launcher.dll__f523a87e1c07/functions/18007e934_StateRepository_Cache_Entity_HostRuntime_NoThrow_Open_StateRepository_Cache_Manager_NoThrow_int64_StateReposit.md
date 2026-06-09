# StateRepository::Cache::Entity::HostRuntime_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18007e934`
- end: `0x18007eb71`
- name: `?Open@HostRuntime_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d78e0`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18007e934`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007ea8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007eb2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007ea8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007eb2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e9f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007eb43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e9f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007eb43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007eabb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007eabb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007e997`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007e997`

## string_xrefs

- `0x18007e9b4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007ead8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007e9d4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18007ea6b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::HostRuntime_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"HostRuntime\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
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
    v9 = 246;
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
    v12 = 249;
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
    v12 = 250;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"HostRuntime\\Data");
  if ( v8 < 0 )
  {
    v12 = 252;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
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
0x18007e934  mov     [rsp-8+arg_10], rbx
0x18007e939  push    rbp
0x18007e93a  push    rsi
0x18007e93b  push    rdi
0x18007e93c  push    r14
0x18007e93e  push    r15
0x18007e940  lea     rbp, [rsp-170h]
0x18007e948  sub     rsp, 270h
0x18007e94f  mov     rax, cs:__security_cookie
0x18007e956  xor     rax, rsp
0x18007e959  mov     [rbp+190h+var_30], rax
0x18007e960  mov     rcx, [rcx]
0x18007e963  lea     rax, [rsp+290h+var_270]
0x18007e968  mov     rsi, r9
0x18007e96b  mov     [rsp+290h+var_268], rax
0x18007e970  mov     rdi, r8
0x18007e973  mov     [rsp+290h+var_258], 1
0x18007e978  mov     r14, rdx
0x18007e97b  lea     r9, [rsp+290h+var_260]
0x18007e980  xor     r15d, r15d
0x18007e983  lea     rdx, aHostruntimeDat; "HostRuntime\\Data"
0x18007e98a  xor     r8d, r8d
0x18007e98d  mov     qword ptr [rsp+290h+var_270], r15; int
0x18007e992  mov     [rsp+290h+var_260], r15
0x18007e997  call    cs:__imp_SRCacheContext_Open
0x18007e99d  lea     rcx, [rsp+290h+var_268]
0x18007e9a2  mov     ebx, eax
0x18007e9a4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007e9a9  test    ebx, ebx
0x18007e9ab  jns     short loc_18007E9FF
0x18007e9ad  mov     rcx, [rbp+198h]; this
0x18007e9b4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e9bb  mov     r9d, ebx; char *
0x18007e9be  mov     edx, 18Ch; void *
0x18007e9c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e9c8  mov     edx, 0F5h; void *
0x18007e9cd  mov     rcx, [rbp+198h]; this
0x18007e9d4  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e9db  mov     r9d, ebx; char *
0x18007e9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e9e3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007e9e8  mov     qword ptr [rsp+290h+var_270], r15
0x18007e9ed  test    rcx, rcx
0x18007e9f0  jz      short loc_18007E9F8
0x18007e9f2  call    cs:__imp_SRCacheContext_Close
0x18007e9f8  mov     eax, ebx
0x18007e9fa  jmp     loc_18007EB4B
0x18007e9ff  cmp     qword ptr [rsp+290h+var_270], r15
0x18007ea04  setnz   al
0x18007ea07  test    al, al
0x18007ea09  jnz     short loc_18007EA17
0x18007ea0b  mov     ebx, 80670012h
0x18007ea10  mov     edx, 0F6h
0x18007ea15  jmp     short loc_18007E9CD
0x18007ea17  xor     edx, edx; Val
0x18007ea19  mov     [rsp+290h+var_250], r15
0x18007ea1e  mov     r8d, 200h; Size
0x18007ea24  lea     rcx, [rsp+290h+var_248]; void *
0x18007ea29  call    memset_0
0x18007ea2e  lea     rax, [rsp+290h+var_248]
0x18007ea33  mov     [rbp+190h+var_48], r15
0x18007ea3a  mov     rdx, r14; unsigned __int64
0x18007ea3d  mov     [rbp+190h+var_38], rax
0x18007ea44  lea     rcx, [rsp+290h+var_250]; this
0x18007ea49  mov     [rbp+190h+var_40], 100h
0x18007ea54  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007ea59  mov     ebx, eax
0x18007ea5b  test    eax, eax
0x18007ea5d  jns     short loc_18007EA98
0x18007ea5f  mov     edx, 0F9h; void *
0x18007ea64  mov     rcx, [rbp+198h]; this
0x18007ea6b  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007ea72  mov     r9d, ebx; char *
0x18007ea75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ea7a  mov     rcx, [rsp+290h+var_250]
0x18007ea7f  mov     [rsp+290h+var_250], r15
0x18007ea84  test    rcx, rcx
0x18007ea87  jz      loc_18007E9E3
0x18007ea8d  call    cs:__imp_SRCache_Free
0x18007ea93  jmp     loc_18007E9E3
0x18007ea98  mov     rdx, [rbp+190h+var_38]
0x18007ea9f  lea     r9, [rsp+290h+var_260]
0x18007eaa4  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007eaa9  xor     r8d, r8d
0x18007eaac  mov     [rsp+290h+var_268], rdi
0x18007eab1  mov     [rsp+290h+var_260], r15
0x18007eab6  mov     [rsp+290h+var_258], 1
0x18007eabb  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007eac1  lea     rcx, [rsp+290h+var_268]
0x18007eac6  mov     ebx, eax
0x18007eac8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007eacd  test    ebx, ebx
0x18007eacf  jns     short loc_18007EAF6
0x18007ead1  mov     rcx, [rbp+198h]; this
0x18007ead8  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007eadf  mov     r9d, ebx; char *
0x18007eae2  mov     edx, 1B0h; void *
0x18007eae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eaec  mov     edx, 0FAh
0x18007eaf1  jmp     loc_18007EA64
0x18007eaf6  cmp     [rdi], r15
0x18007eaf9  lea     rdx, aHostruntimeDat; "HostRuntime\\Data"
0x18007eb00  lea     rcx, [rsp+290h+var_270]; this
0x18007eb05  setnz   al
0x18007eb08  mov     [rsi], al
0x18007eb0a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007eb0f  mov     ebx, eax
0x18007eb11  test    eax, eax
0x18007eb13  jns     short loc_18007EB1F
0x18007eb15  mov     edx, 0FCh
0x18007eb1a  jmp     loc_18007EA64
0x18007eb1f  mov     rcx, [rsp+290h+var_250]
0x18007eb24  mov     [rsp+290h+var_250], r15
0x18007eb29  test    rcx, rcx
0x18007eb2c  jz      short loc_18007EB34
0x18007eb2e  call    cs:__imp_SRCache_Free
0x18007eb34  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007eb39  mov     qword ptr [rsp+290h+var_270], r15
0x18007eb3e  test    rcx, rcx
0x18007eb41  jz      short loc_18007EB49
0x18007eb43  call    cs:__imp_SRCacheContext_Close
0x18007eb49  xor     eax, eax
0x18007eb4b  mov     rcx, [rbp+190h+var_30]
0x18007eb52  xor     rcx, rsp; StackCookie
0x18007eb55  call    __security_check_cookie
0x18007eb5a  mov     rbx, [rsp+290h+arg_10]
0x18007eb62  add     rsp, 270h
0x18007eb69  pop     r15
0x18007eb6b  pop     r14
0x18007eb6d  pop     rdi
0x18007eb6e  pop     rsi
0x18007eb6f  pop     rbp
0x18007eb70  retn
```
