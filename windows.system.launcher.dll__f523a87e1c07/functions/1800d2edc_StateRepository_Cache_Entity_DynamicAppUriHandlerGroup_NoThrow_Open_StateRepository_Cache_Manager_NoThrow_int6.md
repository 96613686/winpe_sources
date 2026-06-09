# StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800d2edc`
- end: `0x1800d3119`
- name: `?Open@DynamicAppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006280`
- `0x1800426d8`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800d2edc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3035`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d30d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3035`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d30d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2f9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d30eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2f9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d30eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800d3063`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800d3063`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d2f3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d2f3f`

## string_xrefs

- `0x1800d2f7c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x1800d3013`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x1800d2f5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800d3080`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800d2f2b`: `DynamicAppUriHandlerGroup\Data`
- `0x1800d30a1`: `DynamicAppUriHandlerGroup\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"DynamicAppUriHandlerGroup\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 261;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
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
    v9 = 262;
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
    v12 = 265;
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
    v12 = 266;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"DynamicAppUriHandlerGroup\\Data");
  if ( v8 < 0 )
  {
    v12 = 268;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
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
0x1800d2edc  mov     [rsp-8+arg_10], rbx
0x1800d2ee1  push    rbp
0x1800d2ee2  push    rsi
0x1800d2ee3  push    rdi
0x1800d2ee4  push    r14
0x1800d2ee6  push    r15
0x1800d2ee8  lea     rbp, [rsp-170h]
0x1800d2ef0  sub     rsp, 270h
0x1800d2ef7  mov     rax, cs:__security_cookie
0x1800d2efe  xor     rax, rsp
0x1800d2f01  mov     [rbp+190h+var_30], rax
0x1800d2f08  mov     rcx, [rcx]
0x1800d2f0b  lea     rax, [rsp+290h+var_270]
0x1800d2f10  mov     rsi, r9
0x1800d2f13  mov     [rsp+290h+var_268], rax
0x1800d2f18  mov     rdi, r8
0x1800d2f1b  mov     [rsp+290h+var_258], 1
0x1800d2f20  mov     r14, rdx
0x1800d2f23  lea     r9, [rsp+290h+var_260]
0x1800d2f28  xor     r15d, r15d
0x1800d2f2b  lea     rdx, aDynamicappurih_1; "DynamicAppUriHandlerGroup\\Data"
0x1800d2f32  xor     r8d, r8d
0x1800d2f35  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800d2f3a  mov     [rsp+290h+var_260], r15
0x1800d2f3f  call    cs:__imp_SRCacheContext_Open
0x1800d2f45  lea     rcx, [rsp+290h+var_268]
0x1800d2f4a  mov     ebx, eax
0x1800d2f4c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d2f51  test    ebx, ebx
0x1800d2f53  jns     short loc_1800D2FA7
0x1800d2f55  mov     rcx, [rbp+198h]; this
0x1800d2f5c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d2f63  mov     r9d, ebx; char *
0x1800d2f66  mov     edx, 18Ch; void *
0x1800d2f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2f70  mov     edx, 105h; void *
0x1800d2f75  mov     rcx, [rbp+198h]; this
0x1800d2f7c  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d2f83  mov     r9d, ebx; char *
0x1800d2f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2f8b  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d2f90  mov     qword ptr [rsp+290h+var_270], r15
0x1800d2f95  test    rcx, rcx
0x1800d2f98  jz      short loc_1800D2FA0
0x1800d2f9a  call    cs:__imp_SRCacheContext_Close
0x1800d2fa0  mov     eax, ebx
0x1800d2fa2  jmp     loc_1800D30F3
0x1800d2fa7  cmp     qword ptr [rsp+290h+var_270], r15
0x1800d2fac  setnz   al
0x1800d2faf  test    al, al
0x1800d2fb1  jnz     short loc_1800D2FBF
0x1800d2fb3  mov     ebx, 80670012h
0x1800d2fb8  mov     edx, 106h
0x1800d2fbd  jmp     short loc_1800D2F75
0x1800d2fbf  xor     edx, edx; Val
0x1800d2fc1  mov     [rsp+290h+var_250], r15
0x1800d2fc6  mov     r8d, 200h; Size
0x1800d2fcc  lea     rcx, [rsp+290h+var_248]; void *
0x1800d2fd1  call    memset_0
0x1800d2fd6  lea     rax, [rsp+290h+var_248]
0x1800d2fdb  mov     [rbp+190h+var_48], r15
0x1800d2fe2  mov     rdx, r14; unsigned __int64
0x1800d2fe5  mov     [rbp+190h+var_38], rax
0x1800d2fec  lea     rcx, [rsp+290h+var_250]; this
0x1800d2ff1  mov     [rbp+190h+var_40], 100h
0x1800d2ffc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800d3001  mov     ebx, eax
0x1800d3003  test    eax, eax
0x1800d3005  jns     short loc_1800D3040
0x1800d3007  mov     edx, 109h; void *
0x1800d300c  mov     rcx, [rbp+198h]; this
0x1800d3013  lea     r8, aOnecorePrivate_20; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d301a  mov     r9d, ebx; char *
0x1800d301d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3022  mov     rcx, [rsp+290h+var_250]
0x1800d3027  mov     [rsp+290h+var_250], r15
0x1800d302c  test    rcx, rcx
0x1800d302f  jz      loc_1800D2F8B
0x1800d3035  call    cs:__imp_SRCache_Free
0x1800d303b  jmp     loc_1800D2F8B
0x1800d3040  mov     rdx, [rbp+190h+var_38]
0x1800d3047  lea     r9, [rsp+290h+var_260]
0x1800d304c  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d3051  xor     r8d, r8d
0x1800d3054  mov     [rsp+290h+var_268], rdi
0x1800d3059  mov     [rsp+290h+var_260], r15
0x1800d305e  mov     [rsp+290h+var_258], 1
0x1800d3063  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800d3069  lea     rcx, [rsp+290h+var_268]
0x1800d306e  mov     ebx, eax
0x1800d3070  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d3075  test    ebx, ebx
0x1800d3077  jns     short loc_1800D309E
0x1800d3079  mov     rcx, [rbp+198h]; this
0x1800d3080  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d3087  mov     r9d, ebx; char *
0x1800d308a  mov     edx, 1B0h; void *
0x1800d308f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3094  mov     edx, 10Ah
0x1800d3099  jmp     loc_1800D300C
0x1800d309e  cmp     [rdi], r15
0x1800d30a1  lea     rdx, aDynamicappurih_1; "DynamicAppUriHandlerGroup\\Data"
0x1800d30a8  lea     rcx, [rsp+290h+var_270]; this
0x1800d30ad  setnz   al
0x1800d30b0  mov     [rsi], al
0x1800d30b2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800d30b7  mov     ebx, eax
0x1800d30b9  test    eax, eax
0x1800d30bb  jns     short loc_1800D30C7
0x1800d30bd  mov     edx, 10Ch
0x1800d30c2  jmp     loc_1800D300C
0x1800d30c7  mov     rcx, [rsp+290h+var_250]
0x1800d30cc  mov     [rsp+290h+var_250], r15
0x1800d30d1  test    rcx, rcx
0x1800d30d4  jz      short loc_1800D30DC
0x1800d30d6  call    cs:__imp_SRCache_Free
0x1800d30dc  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d30e1  mov     qword ptr [rsp+290h+var_270], r15
0x1800d30e6  test    rcx, rcx
0x1800d30e9  jz      short loc_1800D30F1
0x1800d30eb  call    cs:__imp_SRCacheContext_Close
0x1800d30f1  xor     eax, eax
0x1800d30f3  mov     rcx, [rbp+190h+var_30]
0x1800d30fa  xor     rcx, rsp; StackCookie
0x1800d30fd  call    __security_check_cookie
0x1800d3102  mov     rbx, [rsp+290h+arg_10]
0x1800d310a  add     rsp, 270h
0x1800d3111  pop     r15
0x1800d3113  pop     r14
0x1800d3115  pop     rdi
0x1800d3116  pop     rsi
0x1800d3117  pop     rbp
0x1800d3118  retn
```
