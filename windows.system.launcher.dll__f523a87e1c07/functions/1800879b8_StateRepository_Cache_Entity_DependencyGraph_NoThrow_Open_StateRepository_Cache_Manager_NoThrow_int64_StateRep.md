# StateRepository::Cache::Entity::DependencyGraph_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800879b8`
- end: `0x180087bf5`
- name: `?Open@DependencyGraph_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d77d4`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x1800879b8`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180087b11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180087bb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180087b11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180087bb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180087a76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180087bc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180087a76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180087bc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180087b3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180087b3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180087a1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180087a1b`

## string_xrefs

- `0x180087a38`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180087b5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180087a58`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x180087aef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DependencyGraph_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"DependencyGraph\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 189;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
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
    v9 = 190;
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
    v12 = 193;
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
    v12 = 194;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"DependencyGraph\\Data");
  if ( v8 < 0 )
  {
    v12 = 196;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
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
0x1800879b8  mov     [rsp-8+arg_10], rbx
0x1800879bd  push    rbp
0x1800879be  push    rsi
0x1800879bf  push    rdi
0x1800879c0  push    r14
0x1800879c2  push    r15
0x1800879c4  lea     rbp, [rsp-170h]
0x1800879cc  sub     rsp, 270h
0x1800879d3  mov     rax, cs:__security_cookie
0x1800879da  xor     rax, rsp
0x1800879dd  mov     [rbp+190h+var_30], rax
0x1800879e4  mov     rcx, [rcx]
0x1800879e7  lea     rax, [rsp+290h+var_270]
0x1800879ec  mov     rsi, r9
0x1800879ef  mov     [rsp+290h+var_268], rax
0x1800879f4  mov     rdi, r8
0x1800879f7  mov     [rsp+290h+var_258], 1
0x1800879fc  mov     r14, rdx
0x1800879ff  lea     r9, [rsp+290h+var_260]
0x180087a04  xor     r15d, r15d
0x180087a07  lea     rdx, aDependencygrap_0; "DependencyGraph\\Data"
0x180087a0e  xor     r8d, r8d
0x180087a11  mov     qword ptr [rsp+290h+var_270], r15; int
0x180087a16  mov     [rsp+290h+var_260], r15
0x180087a1b  call    cs:__imp_SRCacheContext_Open
0x180087a21  lea     rcx, [rsp+290h+var_268]
0x180087a26  mov     ebx, eax
0x180087a28  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180087a2d  test    ebx, ebx
0x180087a2f  jns     short loc_180087A83
0x180087a31  mov     rcx, [rbp+198h]; this
0x180087a38  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087a3f  mov     r9d, ebx; char *
0x180087a42  mov     edx, 18Ch; void *
0x180087a47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087a4c  mov     edx, 0BDh; void *
0x180087a51  mov     rcx, [rbp+198h]; this
0x180087a58  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087a5f  mov     r9d, ebx; char *
0x180087a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087a67  mov     rcx, qword ptr [rsp+290h+var_270]
0x180087a6c  mov     qword ptr [rsp+290h+var_270], r15
0x180087a71  test    rcx, rcx
0x180087a74  jz      short loc_180087A7C
0x180087a76  call    cs:__imp_SRCacheContext_Close
0x180087a7c  mov     eax, ebx
0x180087a7e  jmp     loc_180087BCF
0x180087a83  cmp     qword ptr [rsp+290h+var_270], r15
0x180087a88  setnz   al
0x180087a8b  test    al, al
0x180087a8d  jnz     short loc_180087A9B
0x180087a8f  mov     ebx, 80670012h
0x180087a94  mov     edx, 0BEh
0x180087a99  jmp     short loc_180087A51
0x180087a9b  xor     edx, edx; Val
0x180087a9d  mov     [rsp+290h+var_250], r15
0x180087aa2  mov     r8d, 200h; Size
0x180087aa8  lea     rcx, [rsp+290h+var_248]; void *
0x180087aad  call    memset_0
0x180087ab2  lea     rax, [rsp+290h+var_248]
0x180087ab7  mov     [rbp+190h+var_48], r15
0x180087abe  mov     rdx, r14; unsigned __int64
0x180087ac1  mov     [rbp+190h+var_38], rax
0x180087ac8  lea     rcx, [rsp+290h+var_250]; this
0x180087acd  mov     [rbp+190h+var_40], 100h
0x180087ad8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180087add  mov     ebx, eax
0x180087adf  test    eax, eax
0x180087ae1  jns     short loc_180087B1C
0x180087ae3  mov     edx, 0C1h; void *
0x180087ae8  mov     rcx, [rbp+198h]; this
0x180087aef  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087af6  mov     r9d, ebx; char *
0x180087af9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087afe  mov     rcx, [rsp+290h+var_250]
0x180087b03  mov     [rsp+290h+var_250], r15
0x180087b08  test    rcx, rcx
0x180087b0b  jz      loc_180087A67
0x180087b11  call    cs:__imp_SRCache_Free
0x180087b17  jmp     loc_180087A67
0x180087b1c  mov     rdx, [rbp+190h+var_38]
0x180087b23  lea     r9, [rsp+290h+var_260]
0x180087b28  mov     rcx, qword ptr [rsp+290h+var_270]
0x180087b2d  xor     r8d, r8d
0x180087b30  mov     [rsp+290h+var_268], rdi
0x180087b35  mov     [rsp+290h+var_260], r15
0x180087b3a  mov     [rsp+290h+var_258], 1
0x180087b3f  call    cs:__imp_SRCacheContext_OpenSubContext
0x180087b45  lea     rcx, [rsp+290h+var_268]
0x180087b4a  mov     ebx, eax
0x180087b4c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180087b51  test    ebx, ebx
0x180087b53  jns     short loc_180087B7A
0x180087b55  mov     rcx, [rbp+198h]; this
0x180087b5c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180087b63  mov     r9d, ebx; char *
0x180087b66  mov     edx, 1B0h; void *
0x180087b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087b70  mov     edx, 0C2h
0x180087b75  jmp     loc_180087AE8
0x180087b7a  cmp     [rdi], r15
0x180087b7d  lea     rdx, aDependencygrap_0; "DependencyGraph\\Data"
0x180087b84  lea     rcx, [rsp+290h+var_270]; this
0x180087b89  setnz   al
0x180087b8c  mov     [rsi], al
0x180087b8e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180087b93  mov     ebx, eax
0x180087b95  test    eax, eax
0x180087b97  jns     short loc_180087BA3
0x180087b99  mov     edx, 0C4h
0x180087b9e  jmp     loc_180087AE8
0x180087ba3  mov     rcx, [rsp+290h+var_250]
0x180087ba8  mov     [rsp+290h+var_250], r15
0x180087bad  test    rcx, rcx
0x180087bb0  jz      short loc_180087BB8
0x180087bb2  call    cs:__imp_SRCache_Free
0x180087bb8  mov     rcx, qword ptr [rsp+290h+var_270]
0x180087bbd  mov     qword ptr [rsp+290h+var_270], r15
0x180087bc2  test    rcx, rcx
0x180087bc5  jz      short loc_180087BCD
0x180087bc7  call    cs:__imp_SRCacheContext_Close
0x180087bcd  xor     eax, eax
0x180087bcf  mov     rcx, [rbp+190h+var_30]
0x180087bd6  xor     rcx, rsp; StackCookie
0x180087bd9  call    __security_check_cookie
0x180087bde  mov     rbx, [rsp+290h+arg_10]
0x180087be6  add     rsp, 270h
0x180087bed  pop     r15
0x180087bef  pop     r14
0x180087bf1  pop     rdi
0x180087bf2  pop     rsi
0x180087bf3  pop     rbp
0x180087bf4  retn
```
