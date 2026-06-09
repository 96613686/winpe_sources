# StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180008b14`
- end: `0x180008d69`
- name: `?Open@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `597`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006280`
- `0x180008db8`
- `0x18000a790`
- `0x180040358`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180008b14`
- `0x180010c04`
- `0x180030640`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008c85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008d26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008c85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008d26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008bea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008d3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008bea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008d3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008cb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008cb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008b77`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008b77`

## string_xrefs

- `0x180008b63`: `DynamicAppUriHandler\Data`
- `0x180008cf1`: `DynamicAppUriHandler\Data`
- `0x180008bcc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180008c63`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180008bac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008cd0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"DynamicAppUriHandler\\Data", 0, &v19);
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
    v10 = 394;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
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
    v10 = 395;
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
    v13 = 398;
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
    v13 = 399;
    goto LABEL_14;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"DynamicAppUriHandler\\Data");
  if ( v8 < 0 )
  {
    v13 = 401;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_7;
  }
  v15 = v21;
  v21 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180008b14  mov     [rsp-8+arg_10], rbx
0x180008b19  push    rbp
0x180008b1a  push    rsi
0x180008b1b  push    rdi
0x180008b1c  push    r14
0x180008b1e  push    r15
0x180008b20  lea     rbp, [rsp-170h]
0x180008b28  sub     rsp, 270h
0x180008b2f  mov     rax, cs:__security_cookie
0x180008b36  xor     rax, rsp
0x180008b39  mov     [rbp+190h+var_30], rax
0x180008b40  mov     rcx, [rcx]
0x180008b43  lea     rax, [rsp+290h+var_270]
0x180008b48  mov     rsi, r9
0x180008b4b  mov     [rsp+290h+var_268], rax
0x180008b50  mov     rdi, r8
0x180008b53  mov     [rsp+290h+var_258], 1
0x180008b58  mov     r14, rdx
0x180008b5b  lea     r9, [rsp+290h+var_260]
0x180008b60  xor     r15d, r15d
0x180008b63  lea     rdx, aDynamicappurih_3; "DynamicAppUriHandler\\Data"
0x180008b6a  xor     r8d, r8d
0x180008b6d  mov     qword ptr [rsp+290h+var_270], r15; int
0x180008b72  mov     [rsp+290h+var_260], r15
0x180008b77  call    cs:__imp_SRCacheContext_Open
0x180008b7d  mov     ebx, eax
0x180008b7f  cmp     [rsp+290h+var_258], r15b
0x180008b84  jz      short loc_180008BA1
0x180008b86  mov     r8, [rsp+290h+var_268]
0x180008b8b  mov     rdx, [rsp+290h+var_260]
0x180008b90  mov     rcx, [r8]
0x180008b93  mov     [r8], rdx
0x180008b96  test    rcx, rcx
0x180008b99  jz      short loc_180008BA1
0x180008b9b  call    cs:__imp_SRCacheContext_Close
0x180008ba1  test    ebx, ebx
0x180008ba3  jns     short loc_180008BF7
0x180008ba5  mov     rcx, [rbp+198h]; this
0x180008bac  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008bb3  mov     r9d, ebx; char *
0x180008bb6  mov     edx, 18Ch; void *
0x180008bbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bc0  mov     edx, 18Ah; void *
0x180008bc5  mov     rcx, [rbp+198h]; this
0x180008bcc  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008bd3  mov     r9d, ebx; char *
0x180008bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bdb  mov     rcx, qword ptr [rsp+290h+var_270]
0x180008be0  mov     qword ptr [rsp+290h+var_270], r15
0x180008be5  test    rcx, rcx
0x180008be8  jz      short loc_180008BF0
0x180008bea  call    cs:__imp_SRCacheContext_Close
0x180008bf0  mov     eax, ebx
0x180008bf2  jmp     loc_180008D43
0x180008bf7  cmp     qword ptr [rsp+290h+var_270], r15
0x180008bfc  setnz   al
0x180008bff  test    al, al
0x180008c01  jnz     short loc_180008C0F
0x180008c03  mov     ebx, 80670012h
0x180008c08  mov     edx, 18Bh
0x180008c0d  jmp     short loc_180008BC5
0x180008c0f  xor     edx, edx; Val
0x180008c11  mov     [rsp+290h+var_250], r15
0x180008c16  mov     r8d, 200h; Size
0x180008c1c  lea     rcx, [rsp+290h+var_248]; void *
0x180008c21  call    memset_0
0x180008c26  lea     rax, [rsp+290h+var_248]
0x180008c2b  mov     [rbp+190h+var_48], r15
0x180008c32  mov     rdx, r14; unsigned __int64
0x180008c35  mov     [rbp+190h+var_38], rax
0x180008c3c  lea     rcx, [rsp+290h+var_250]; this
0x180008c41  mov     [rbp+190h+var_40], 100h
0x180008c4c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180008c51  mov     ebx, eax
0x180008c53  test    eax, eax
0x180008c55  jns     short loc_180008C90
0x180008c57  mov     edx, 18Eh; void *
0x180008c5c  mov     rcx, [rbp+198h]; this
0x180008c63  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008c6a  mov     r9d, ebx; char *
0x180008c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c72  mov     rcx, [rsp+290h+var_250]
0x180008c77  mov     [rsp+290h+var_250], r15
0x180008c7c  test    rcx, rcx
0x180008c7f  jz      loc_180008BDB
0x180008c85  call    cs:__imp_SRCache_Free
0x180008c8b  jmp     loc_180008BDB
0x180008c90  mov     rdx, [rbp+190h+var_38]
0x180008c97  lea     r9, [rsp+290h+var_260]
0x180008c9c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180008ca1  xor     r8d, r8d
0x180008ca4  mov     [rsp+290h+var_268], rdi
0x180008ca9  mov     [rsp+290h+var_260], r15
0x180008cae  mov     [rsp+290h+var_258], 1
0x180008cb3  call    cs:__imp_SRCacheContext_OpenSubContext
0x180008cb9  lea     rcx, [rsp+290h+var_268]
0x180008cbe  mov     ebx, eax
0x180008cc0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180008cc5  test    ebx, ebx
0x180008cc7  jns     short loc_180008CEE
0x180008cc9  mov     rcx, [rbp+198h]; this
0x180008cd0  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008cd7  mov     r9d, ebx; char *
0x180008cda  mov     edx, 1B0h; void *
0x180008cdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ce4  mov     edx, 18Fh
0x180008ce9  jmp     loc_180008C5C
0x180008cee  cmp     [rdi], r15
0x180008cf1  lea     rdx, aDynamicappurih_3; "DynamicAppUriHandler\\Data"
0x180008cf8  lea     rcx, [rsp+290h+var_270]; this
0x180008cfd  setnz   al
0x180008d00  mov     [rsi], al
0x180008d02  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180008d07  mov     ebx, eax
0x180008d09  test    eax, eax
0x180008d0b  jns     short loc_180008D17
0x180008d0d  mov     edx, 191h
0x180008d12  jmp     loc_180008C5C
0x180008d17  mov     rcx, [rsp+290h+var_250]
0x180008d1c  mov     [rsp+290h+var_250], r15
0x180008d21  test    rcx, rcx
0x180008d24  jz      short loc_180008D2C
0x180008d26  call    cs:__imp_SRCache_Free
0x180008d2c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180008d31  mov     qword ptr [rsp+290h+var_270], r15
0x180008d36  test    rcx, rcx
0x180008d39  jz      short loc_180008D41
0x180008d3b  call    cs:__imp_SRCacheContext_Close
0x180008d41  xor     eax, eax
0x180008d43  mov     rcx, [rbp+190h+var_30]
0x180008d4a  xor     rcx, rsp; StackCookie
0x180008d4d  call    __security_check_cookie
0x180008d52  mov     rbx, [rsp+290h+arg_10]
0x180008d5a  add     rsp, 270h
0x180008d61  pop     r15
0x180008d63  pop     r14
0x180008d65  pop     rdi
0x180008d66  pop     rsi
0x180008d67  pop     rbp
0x180008d68  retn
```
