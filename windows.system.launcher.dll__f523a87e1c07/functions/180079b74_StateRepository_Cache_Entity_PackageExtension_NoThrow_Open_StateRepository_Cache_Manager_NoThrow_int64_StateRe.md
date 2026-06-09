# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180079b74`
- end: `0x180079db1`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800d7a0c`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180079b74`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079ccd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079d6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079ccd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079d6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079d83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079d83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180079cfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180079cfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180079bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180079bd7`

## string_xrefs

- `0x180079bf4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079d18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079bc3`: `PackageExtension\Data`
- `0x180079d39`: `PackageExtension\Data`
- `0x180079c14`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180079cab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
    v9 = 318;
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
    v12 = 321;
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
    v12 = 322;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 324;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
0x180079b74  mov     [rsp-8+arg_10], rbx
0x180079b79  push    rbp
0x180079b7a  push    rsi
0x180079b7b  push    rdi
0x180079b7c  push    r14
0x180079b7e  push    r15
0x180079b80  lea     rbp, [rsp-170h]
0x180079b88  sub     rsp, 270h
0x180079b8f  mov     rax, cs:__security_cookie
0x180079b96  xor     rax, rsp
0x180079b99  mov     [rbp+190h+var_30], rax
0x180079ba0  mov     rcx, [rcx]
0x180079ba3  lea     rax, [rsp+290h+var_270]
0x180079ba8  mov     rsi, r9
0x180079bab  mov     [rsp+290h+var_268], rax
0x180079bb0  mov     rdi, r8
0x180079bb3  mov     [rsp+290h+var_258], 1
0x180079bb8  mov     r14, rdx
0x180079bbb  lea     r9, [rsp+290h+var_260]
0x180079bc0  xor     r15d, r15d
0x180079bc3  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x180079bca  xor     r8d, r8d
0x180079bcd  mov     qword ptr [rsp+290h+var_270], r15; int
0x180079bd2  mov     [rsp+290h+var_260], r15
0x180079bd7  call    cs:__imp_SRCacheContext_Open
0x180079bdd  lea     rcx, [rsp+290h+var_268]
0x180079be2  mov     ebx, eax
0x180079be4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180079be9  test    ebx, ebx
0x180079beb  jns     short loc_180079C3F
0x180079bed  mov     rcx, [rbp+198h]; this
0x180079bf4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079bfb  mov     r9d, ebx; char *
0x180079bfe  mov     edx, 18Ch; void *
0x180079c03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079c08  mov     edx, 13Dh; void *
0x180079c0d  mov     rcx, [rbp+198h]; this
0x180079c14  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079c1b  mov     r9d, ebx; char *
0x180079c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079c23  mov     rcx, qword ptr [rsp+290h+var_270]
0x180079c28  mov     qword ptr [rsp+290h+var_270], r15
0x180079c2d  test    rcx, rcx
0x180079c30  jz      short loc_180079C38
0x180079c32  call    cs:__imp_SRCacheContext_Close
0x180079c38  mov     eax, ebx
0x180079c3a  jmp     loc_180079D8B
0x180079c3f  cmp     qword ptr [rsp+290h+var_270], r15
0x180079c44  setnz   al
0x180079c47  test    al, al
0x180079c49  jnz     short loc_180079C57
0x180079c4b  mov     ebx, 80670012h
0x180079c50  mov     edx, 13Eh
0x180079c55  jmp     short loc_180079C0D
0x180079c57  xor     edx, edx; Val
0x180079c59  mov     [rsp+290h+var_250], r15
0x180079c5e  mov     r8d, 200h; Size
0x180079c64  lea     rcx, [rsp+290h+var_248]; void *
0x180079c69  call    memset_0
0x180079c6e  lea     rax, [rsp+290h+var_248]
0x180079c73  mov     [rbp+190h+var_48], r15
0x180079c7a  mov     rdx, r14; unsigned __int64
0x180079c7d  mov     [rbp+190h+var_38], rax
0x180079c84  lea     rcx, [rsp+290h+var_250]; this
0x180079c89  mov     [rbp+190h+var_40], 100h
0x180079c94  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180079c99  mov     ebx, eax
0x180079c9b  test    eax, eax
0x180079c9d  jns     short loc_180079CD8
0x180079c9f  mov     edx, 141h; void *
0x180079ca4  mov     rcx, [rbp+198h]; this
0x180079cab  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079cb2  mov     r9d, ebx; char *
0x180079cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079cba  mov     rcx, [rsp+290h+var_250]
0x180079cbf  mov     [rsp+290h+var_250], r15
0x180079cc4  test    rcx, rcx
0x180079cc7  jz      loc_180079C23
0x180079ccd  call    cs:__imp_SRCache_Free
0x180079cd3  jmp     loc_180079C23
0x180079cd8  mov     rdx, [rbp+190h+var_38]
0x180079cdf  lea     r9, [rsp+290h+var_260]
0x180079ce4  mov     rcx, qword ptr [rsp+290h+var_270]
0x180079ce9  xor     r8d, r8d
0x180079cec  mov     [rsp+290h+var_268], rdi
0x180079cf1  mov     [rsp+290h+var_260], r15
0x180079cf6  mov     [rsp+290h+var_258], 1
0x180079cfb  call    cs:__imp_SRCacheContext_OpenSubContext
0x180079d01  lea     rcx, [rsp+290h+var_268]
0x180079d06  mov     ebx, eax
0x180079d08  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180079d0d  test    ebx, ebx
0x180079d0f  jns     short loc_180079D36
0x180079d11  mov     rcx, [rbp+198h]; this
0x180079d18  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079d1f  mov     r9d, ebx; char *
0x180079d22  mov     edx, 1B0h; void *
0x180079d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d2c  mov     edx, 142h
0x180079d31  jmp     loc_180079CA4
0x180079d36  cmp     [rdi], r15
0x180079d39  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x180079d40  lea     rcx, [rsp+290h+var_270]; this
0x180079d45  setnz   al
0x180079d48  mov     [rsi], al
0x180079d4a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180079d4f  mov     ebx, eax
0x180079d51  test    eax, eax
0x180079d53  jns     short loc_180079D5F
0x180079d55  mov     edx, 144h
0x180079d5a  jmp     loc_180079CA4
0x180079d5f  mov     rcx, [rsp+290h+var_250]
0x180079d64  mov     [rsp+290h+var_250], r15
0x180079d69  test    rcx, rcx
0x180079d6c  jz      short loc_180079D74
0x180079d6e  call    cs:__imp_SRCache_Free
0x180079d74  mov     rcx, qword ptr [rsp+290h+var_270]
0x180079d79  mov     qword ptr [rsp+290h+var_270], r15
0x180079d7e  test    rcx, rcx
0x180079d81  jz      short loc_180079D89
0x180079d83  call    cs:__imp_SRCacheContext_Close
0x180079d89  xor     eax, eax
0x180079d8b  mov     rcx, [rbp+190h+var_30]
0x180079d92  xor     rcx, rsp; StackCookie
0x180079d95  call    __security_check_cookie
0x180079d9a  mov     rbx, [rsp+290h+arg_10]
0x180079da2  add     rsp, 270h
0x180079da9  pop     r15
0x180079dab  pop     r14
0x180079dad  pop     rdi
0x180079dae  pop     rsi
0x180079daf  pop     rbp
0x180079db0  retn
```
