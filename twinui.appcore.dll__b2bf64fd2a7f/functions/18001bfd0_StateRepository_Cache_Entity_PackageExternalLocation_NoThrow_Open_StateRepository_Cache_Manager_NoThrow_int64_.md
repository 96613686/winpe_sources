# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001bfd0`
- end: `0x18001c20d`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b588`

## callees

- `0x180008c58`
- `0x18000aa58`
- `0x18001bfd0`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c157`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c157`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c08e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c1df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c08e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c1df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c129`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c1ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c129`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c1ca`

## string_xrefs

- `0x18001c050`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c174`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c070`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001c107`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageExternalLocation\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v9 = 251;
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
    v12 = 254;
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
    v12 = 255;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageExternalLocation\\Data");
  if ( v8 < 0 )
  {
    v12 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18001bfd0  mov     [rsp-8+arg_10], rbx
0x18001bfd5  push    rbp
0x18001bfd6  push    rsi
0x18001bfd7  push    rdi
0x18001bfd8  push    r14
0x18001bfda  push    r15
0x18001bfdc  lea     rbp, [rsp-170h]
0x18001bfe4  sub     rsp, 270h
0x18001bfeb  mov     rax, cs:__security_cookie
0x18001bff2  xor     rax, rsp
0x18001bff5  mov     [rbp+190h+var_30], rax
0x18001bffc  mov     rcx, [rcx]
0x18001bfff  lea     rax, [rsp+290h+var_270]
0x18001c004  mov     rsi, r9
0x18001c007  mov     [rsp+290h+var_268], rax
0x18001c00c  mov     rdi, r8
0x18001c00f  mov     [rsp+290h+var_258], 1
0x18001c014  mov     r14, rdx
0x18001c017  lea     r9, [rsp+290h+var_260]
0x18001c01c  xor     r15d, r15d
0x18001c01f  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18001c026  xor     r8d, r8d
0x18001c029  mov     qword ptr [rsp+290h+var_270], r15; int
0x18001c02e  mov     [rsp+290h+var_260], r15
0x18001c033  call    cs:__imp_SRCacheContext_Open
0x18001c039  lea     rcx, [rsp+290h+var_268]
0x18001c03e  mov     ebx, eax
0x18001c040  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c045  test    ebx, ebx
0x18001c047  jns     short loc_18001C09B
0x18001c049  mov     rcx, [rbp+198h]; this
0x18001c050  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c057  mov     r9d, ebx; char *
0x18001c05a  mov     edx, 18Ch; void *
0x18001c05f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c064  mov     edx, 0FAh; void *
0x18001c069  mov     rcx, [rbp+198h]; this
0x18001c070  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c077  mov     r9d, ebx; char *
0x18001c07a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c07f  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001c084  mov     qword ptr [rsp+290h+var_270], r15
0x18001c089  test    rcx, rcx
0x18001c08c  jz      short loc_18001C094
0x18001c08e  call    cs:__imp_SRCacheContext_Close
0x18001c094  mov     eax, ebx
0x18001c096  jmp     loc_18001C1E7
0x18001c09b  cmp     qword ptr [rsp+290h+var_270], r15
0x18001c0a0  setnz   al
0x18001c0a3  test    al, al
0x18001c0a5  jnz     short loc_18001C0B3
0x18001c0a7  mov     ebx, 80670012h
0x18001c0ac  mov     edx, 0FBh
0x18001c0b1  jmp     short loc_18001C069
0x18001c0b3  xor     edx, edx; Val
0x18001c0b5  mov     [rsp+290h+var_250], r15
0x18001c0ba  mov     r8d, 200h; Size
0x18001c0c0  lea     rcx, [rsp+290h+var_248]; void *
0x18001c0c5  call    memset_0
0x18001c0ca  lea     rax, [rsp+290h+var_248]
0x18001c0cf  mov     [rbp+190h+var_48], r15
0x18001c0d6  mov     rdx, r14; unsigned __int64
0x18001c0d9  mov     [rbp+190h+var_38], rax
0x18001c0e0  lea     rcx, [rsp+290h+var_250]; this
0x18001c0e5  mov     [rbp+190h+var_40], 100h
0x18001c0f0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001c0f5  mov     ebx, eax
0x18001c0f7  test    eax, eax
0x18001c0f9  jns     short loc_18001C134
0x18001c0fb  mov     edx, 0FEh; void *
0x18001c100  mov     rcx, [rbp+198h]; this
0x18001c107  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c10e  mov     r9d, ebx; char *
0x18001c111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c116  mov     rcx, [rsp+290h+var_250]
0x18001c11b  mov     [rsp+290h+var_250], r15
0x18001c120  test    rcx, rcx
0x18001c123  jz      loc_18001C07F
0x18001c129  call    cs:__imp_SRCache_Free
0x18001c12f  jmp     loc_18001C07F
0x18001c134  mov     rdx, [rbp+190h+var_38]
0x18001c13b  lea     r9, [rsp+290h+var_260]
0x18001c140  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001c145  xor     r8d, r8d
0x18001c148  mov     [rsp+290h+var_268], rdi
0x18001c14d  mov     [rsp+290h+var_260], r15
0x18001c152  mov     [rsp+290h+var_258], 1
0x18001c157  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001c15d  lea     rcx, [rsp+290h+var_268]
0x18001c162  mov     ebx, eax
0x18001c164  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c169  test    ebx, ebx
0x18001c16b  jns     short loc_18001C192
0x18001c16d  mov     rcx, [rbp+198h]; this
0x18001c174  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c17b  mov     r9d, ebx; char *
0x18001c17e  mov     edx, 1B0h; void *
0x18001c183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c188  mov     edx, 0FFh
0x18001c18d  jmp     loc_18001C100
0x18001c192  cmp     [rdi], r15
0x18001c195  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18001c19c  lea     rcx, [rsp+290h+var_270]; this
0x18001c1a1  setnz   al
0x18001c1a4  mov     [rsi], al
0x18001c1a6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001c1ab  mov     ebx, eax
0x18001c1ad  test    eax, eax
0x18001c1af  jns     short loc_18001C1BB
0x18001c1b1  mov     edx, 101h
0x18001c1b6  jmp     loc_18001C100
0x18001c1bb  mov     rcx, [rsp+290h+var_250]
0x18001c1c0  mov     [rsp+290h+var_250], r15
0x18001c1c5  test    rcx, rcx
0x18001c1c8  jz      short loc_18001C1D0
0x18001c1ca  call    cs:__imp_SRCache_Free
0x18001c1d0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001c1d5  mov     qword ptr [rsp+290h+var_270], r15
0x18001c1da  test    rcx, rcx
0x18001c1dd  jz      short loc_18001C1E5
0x18001c1df  call    cs:__imp_SRCacheContext_Close
0x18001c1e5  xor     eax, eax
0x18001c1e7  mov     rcx, [rbp+190h+var_30]
0x18001c1ee  xor     rcx, rsp; StackCookie
0x18001c1f1  call    __security_check_cookie
0x18001c1f6  mov     rbx, [rsp+290h+arg_10]
0x18001c1fe  add     rsp, 270h
0x18001c205  pop     r15
0x18001c207  pop     r14
0x18001c209  pop     rdi
0x18001c20a  pop     rsi
0x18001c20b  pop     rbp
0x18001c20c  retn
```
