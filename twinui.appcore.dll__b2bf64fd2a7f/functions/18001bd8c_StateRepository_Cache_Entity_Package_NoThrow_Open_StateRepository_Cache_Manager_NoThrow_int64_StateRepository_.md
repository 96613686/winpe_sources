# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001bd8c`
- end: `0x18001bfc9`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b388`

## callees

- `0x180008c58`
- `0x18000aa58`
- `0x18001bd8c`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001bdef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001bdef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bf13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bf13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bf9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bf9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bee5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bf86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bee5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bf86`

## string_xrefs

- `0x18001be0c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bf30`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001be2c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001bec3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v9 = 1193;
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
    v12 = 1196;
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
    v12 = 1197;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Package\\Data");
  if ( v8 < 0 )
  {
    v12 = 1199;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
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
0x18001bd8c  mov     [rsp-8+arg_10], rbx
0x18001bd91  push    rbp
0x18001bd92  push    rsi
0x18001bd93  push    rdi
0x18001bd94  push    r14
0x18001bd96  push    r15
0x18001bd98  lea     rbp, [rsp-170h]
0x18001bda0  sub     rsp, 270h
0x18001bda7  mov     rax, cs:__security_cookie
0x18001bdae  xor     rax, rsp
0x18001bdb1  mov     [rbp+190h+var_30], rax
0x18001bdb8  mov     rcx, [rcx]
0x18001bdbb  lea     rax, [rsp+290h+var_270]
0x18001bdc0  mov     rsi, r9
0x18001bdc3  mov     [rsp+290h+var_268], rax
0x18001bdc8  mov     rdi, r8
0x18001bdcb  mov     [rsp+290h+var_258], 1
0x18001bdd0  mov     r14, rdx
0x18001bdd3  lea     r9, [rsp+290h+var_260]
0x18001bdd8  xor     r15d, r15d
0x18001bddb  lea     rdx, aPackageData; "Package\\Data"
0x18001bde2  xor     r8d, r8d
0x18001bde5  mov     qword ptr [rsp+290h+var_270], r15; int
0x18001bdea  mov     [rsp+290h+var_260], r15
0x18001bdef  call    cs:__imp_SRCacheContext_Open
0x18001bdf5  lea     rcx, [rsp+290h+var_268]
0x18001bdfa  mov     ebx, eax
0x18001bdfc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001be01  test    ebx, ebx
0x18001be03  jns     short loc_18001BE57
0x18001be05  mov     rcx, [rbp+198h]; this
0x18001be0c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001be13  mov     r9d, ebx; char *
0x18001be16  mov     edx, 18Ch; void *
0x18001be1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be20  mov     edx, 4A8h; void *
0x18001be25  mov     rcx, [rbp+198h]; this
0x18001be2c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001be33  mov     r9d, ebx; char *
0x18001be36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be3b  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001be40  mov     qword ptr [rsp+290h+var_270], r15
0x18001be45  test    rcx, rcx
0x18001be48  jz      short loc_18001BE50
0x18001be4a  call    cs:__imp_SRCacheContext_Close
0x18001be50  mov     eax, ebx
0x18001be52  jmp     loc_18001BFA3
0x18001be57  cmp     qword ptr [rsp+290h+var_270], r15
0x18001be5c  setnz   al
0x18001be5f  test    al, al
0x18001be61  jnz     short loc_18001BE6F
0x18001be63  mov     ebx, 80670012h
0x18001be68  mov     edx, 4A9h
0x18001be6d  jmp     short loc_18001BE25
0x18001be6f  xor     edx, edx; Val
0x18001be71  mov     [rsp+290h+var_250], r15
0x18001be76  mov     r8d, 200h; Size
0x18001be7c  lea     rcx, [rsp+290h+var_248]; void *
0x18001be81  call    memset_0
0x18001be86  lea     rax, [rsp+290h+var_248]
0x18001be8b  mov     [rbp+190h+var_48], r15
0x18001be92  mov     rdx, r14; unsigned __int64
0x18001be95  mov     [rbp+190h+var_38], rax
0x18001be9c  lea     rcx, [rsp+290h+var_250]; this
0x18001bea1  mov     [rbp+190h+var_40], 100h
0x18001beac  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001beb1  mov     ebx, eax
0x18001beb3  test    eax, eax
0x18001beb5  jns     short loc_18001BEF0
0x18001beb7  mov     edx, 4ACh; void *
0x18001bebc  mov     rcx, [rbp+198h]; this
0x18001bec3  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001beca  mov     r9d, ebx; char *
0x18001becd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bed2  mov     rcx, [rsp+290h+var_250]
0x18001bed7  mov     [rsp+290h+var_250], r15
0x18001bedc  test    rcx, rcx
0x18001bedf  jz      loc_18001BE3B
0x18001bee5  call    cs:__imp_SRCache_Free
0x18001beeb  jmp     loc_18001BE3B
0x18001bef0  mov     rdx, [rbp+190h+var_38]
0x18001bef7  lea     r9, [rsp+290h+var_260]
0x18001befc  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bf01  xor     r8d, r8d
0x18001bf04  mov     [rsp+290h+var_268], rdi
0x18001bf09  mov     [rsp+290h+var_260], r15
0x18001bf0e  mov     [rsp+290h+var_258], 1
0x18001bf13  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001bf19  lea     rcx, [rsp+290h+var_268]
0x18001bf1e  mov     ebx, eax
0x18001bf20  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001bf25  test    ebx, ebx
0x18001bf27  jns     short loc_18001BF4E
0x18001bf29  mov     rcx, [rbp+198h]; this
0x18001bf30  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bf37  mov     r9d, ebx; char *
0x18001bf3a  mov     edx, 1B0h; void *
0x18001bf3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf44  mov     edx, 4ADh
0x18001bf49  jmp     loc_18001BEBC
0x18001bf4e  cmp     [rdi], r15
0x18001bf51  lea     rdx, aPackageData; "Package\\Data"
0x18001bf58  lea     rcx, [rsp+290h+var_270]; this
0x18001bf5d  setnz   al
0x18001bf60  mov     [rsi], al
0x18001bf62  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001bf67  mov     ebx, eax
0x18001bf69  test    eax, eax
0x18001bf6b  jns     short loc_18001BF77
0x18001bf6d  mov     edx, 4AFh
0x18001bf72  jmp     loc_18001BEBC
0x18001bf77  mov     rcx, [rsp+290h+var_250]
0x18001bf7c  mov     [rsp+290h+var_250], r15
0x18001bf81  test    rcx, rcx
0x18001bf84  jz      short loc_18001BF8C
0x18001bf86  call    cs:__imp_SRCache_Free
0x18001bf8c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bf91  mov     qword ptr [rsp+290h+var_270], r15
0x18001bf96  test    rcx, rcx
0x18001bf99  jz      short loc_18001BFA1
0x18001bf9b  call    cs:__imp_SRCacheContext_Close
0x18001bfa1  xor     eax, eax
0x18001bfa3  mov     rcx, [rbp+190h+var_30]
0x18001bfaa  xor     rcx, rsp; StackCookie
0x18001bfad  call    __security_check_cookie
0x18001bfb2  mov     rbx, [rsp+290h+arg_10]
0x18001bfba  add     rsp, 270h
0x18001bfc1  pop     r15
0x18001bfc3  pop     r14
0x18001bfc5  pop     rdi
0x18001bfc6  pop     rsi
0x18001bfc7  pop     rbp
0x18001bfc8  retn
```
