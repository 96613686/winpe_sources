# StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::DependencyGraphType)

- ea: `0x18007e23c`
- end: `0x18007e588`
- name: `?OpenByUserAndDependentPackageAndDependencyType@DependencyGraphIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J1W4DependencyGraphType@34@@Z`
- size: `844`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180066144`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034c24`
- `0x18007e23c`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18007e45c`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18007e45c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007e3f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007e54a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007e3f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007e54a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e2b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e35b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e55f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e2b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e35b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007e55f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007e4d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007e4d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007e2fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007e2fa`

## string_xrefs

- `0x18007e46d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18007e319`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007e4f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007e287`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18007e339`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18007e3d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(
        __int64 *a1,
        __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // dx
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int16 v18; // dx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+238h] [rbp+138h]
  __int64 v25; // [rsp+240h] [rbp+140h]
  _BYTE *v26; // [rsp+248h] [rbp+148h]
  unsigned __int16 v27[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h] BYREF
  char v29; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v8 = 441;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return (unsigned int)v9;
  }
  if ( !a4 )
  {
    v8 = 442;
    goto LABEL_3;
  }
  v11 = *a1;
  *a1 = 0;
  if ( v11 )
    SRCacheContext_Close(v11);
  *((_DWORD *)a1 + 2) = 0;
  a1[2] = 0;
  v12 = *a2;
  *(_QWORD *)v27 = v21;
  *(_QWORD *)v21 = 0;
  v28 = 0;
  v29 = 1;
  v9 = SRCacheContext_Open(v12, L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType", 0, &v28);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v27);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v9,
      v21[0]);
    v13 = 448;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)(unsigned int)v9,
      v21[0]);
LABEL_12:
    v14 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    return (unsigned int)v9;
  }
  if ( !*(_QWORD *)v21 )
  {
    v9 = -2140733422;
    v13 = 449;
    goto LABEL_11;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a3);
  if ( v9 < 0 )
  {
    v16 = 452;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, v15);
  if ( v9 < 0 )
  {
    v16 = 453;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a4);
  if ( v9 < 0 )
  {
    v16 = 454;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, v18);
  if ( v9 < 0 )
  {
    v16 = 455;
    goto LABEL_18;
  }
  if ( (unsigned int)_o__itow_s(8, v27, 9) )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v21[0]);
LABEL_29:
    v16 = 456;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, v27);
  if ( v9 < 0 )
    goto LABEL_29;
  *(_QWORD *)v27 = a1;
  v28 = 0;
  v29 = 1;
  v9 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v26, 0, &v28);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v27);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v9,
      v21[0]);
    v16 = 459;
    goto LABEL_18;
  }
  if ( *a1 )
    a1[2] = (__int64)a2;
  v9 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v21,
         L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType");
  if ( v9 < 0 )
  {
    v16 = 465;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)(unsigned int)v9,
      v21[0]);
    v17 = v22;
    v22 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_12;
  }
  v19 = v22;
  v22 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x18007e23c  push    rbp
0x18007e23e  push    rbx
0x18007e23f  push    rsi
0x18007e240  push    rdi
0x18007e241  push    r12
0x18007e243  push    r14
0x18007e245  push    r15
0x18007e247  lea     rbp, [rsp-170h]
0x18007e24f  sub     rsp, 270h
0x18007e256  mov     rax, cs:__security_cookie
0x18007e25d  xor     rax, rsp
0x18007e260  mov     [rbp+1A0h+var_38], rax
0x18007e267  xor     r12d, r12d
0x18007e26a  mov     rsi, r9
0x18007e26d  mov     r15, r8
0x18007e270  mov     r14, rdx
0x18007e273  mov     rdi, rcx
0x18007e276  test    r8, r8
0x18007e279  jnz     short loc_18007E2A2
0x18007e27b  mov     edx, 1B9h; void *
0x18007e280  mov     rcx, [rbp+1A8h]; this
0x18007e287  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e28e  mov     ebx, 80070057h
0x18007e293  mov     r9d, ebx; char *
0x18007e296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e29b  mov     eax, ebx
0x18007e29d  jmp     loc_18007E567
0x18007e2a2  test    rsi, rsi
0x18007e2a5  jnz     short loc_18007E2AE
0x18007e2a7  mov     edx, 1BAh
0x18007e2ac  jmp     short loc_18007E280
0x18007e2ae  mov     rcx, [rcx]
0x18007e2b1  mov     [rdi], r12
0x18007e2b4  test    rcx, rcx
0x18007e2b7  jz      short loc_18007E2BF
0x18007e2b9  call    cs:__imp_SRCacheContext_Close
0x18007e2bf  mov     [rdi+8], r12d
0x18007e2c3  lea     rax, [rsp+2A0h+var_280]
0x18007e2c8  mov     [rdi+10h], r12
0x18007e2cc  lea     r9, [rbp+1A0h+var_48]
0x18007e2d3  mov     rcx, [r14]
0x18007e2d6  lea     rdx, aDependencygrap; "DependencyGraph\\Index\\UserAndDependen"...
0x18007e2dd  xor     r8d, r8d
0x18007e2e0  mov     qword ptr [rbp+1A0h+var_50], rax
0x18007e2e7  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x18007e2ec  mov     [rbp+1A0h+var_48], r12
0x18007e2f3  mov     [rbp+1A0h+var_40], 1
0x18007e2fa  call    cs:__imp_SRCacheContext_Open
0x18007e300  lea     rcx, [rbp+1A0h+var_50]
0x18007e307  mov     ebx, eax
0x18007e309  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007e30e  test    ebx, ebx
0x18007e310  jns     short loc_18007E366
0x18007e312  mov     rcx, [rbp+1A8h]; this
0x18007e319  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e320  mov     r9d, ebx; char *
0x18007e323  mov     edx, 18Ch; void *
0x18007e328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e32d  mov     edx, 1C0h; void *
0x18007e332  mov     rcx, [rbp+1A8h]; this
0x18007e339  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e340  mov     r9d, ebx; char *
0x18007e343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e348  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007e34d  mov     qword ptr [rsp+2A0h+var_280], r12
0x18007e352  test    rcx, rcx
0x18007e355  jz      loc_18007E29B
0x18007e35b  call    cs:__imp_SRCacheContext_Close
0x18007e361  jmp     loc_18007E29B
0x18007e366  cmp     qword ptr [rsp+2A0h+var_280], r12
0x18007e36b  setnz   al
0x18007e36e  test    al, al
0x18007e370  jnz     short loc_18007E37E
0x18007e372  mov     ebx, 80670012h
0x18007e377  mov     edx, 1C1h
0x18007e37c  jmp     short loc_18007E332
0x18007e37e  xor     edx, edx; Val
0x18007e380  mov     [rsp+2A0h+var_270], r12
0x18007e385  mov     r8d, 200h; Size
0x18007e38b  lea     rcx, [rsp+2A0h+var_268]; void *
0x18007e390  call    memset_0
0x18007e395  lea     rax, [rsp+2A0h+var_268]
0x18007e39a  mov     [rbp+1A0h+var_68], r12
0x18007e3a1  mov     rdx, r15; unsigned __int64
0x18007e3a4  mov     [rbp+1A0h+var_58], rax
0x18007e3ab  lea     rcx, [rsp+2A0h+var_270]; this
0x18007e3b0  mov     [rbp+1A0h+var_60], 100h
0x18007e3bb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007e3c0  mov     ebx, eax
0x18007e3c2  test    eax, eax
0x18007e3c4  jns     short loc_18007E3FF
0x18007e3c6  mov     edx, 1C4h; void *
0x18007e3cb  mov     rcx, [rbp+1A8h]; this
0x18007e3d2  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e3d9  mov     r9d, ebx; char *
0x18007e3dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e3e1  mov     rcx, [rsp+2A0h+var_270]
0x18007e3e6  mov     [rsp+2A0h+var_270], r12
0x18007e3eb  test    rcx, rcx
0x18007e3ee  jz      loc_18007E348
0x18007e3f4  call    cs:__imp_SRCache_Free
0x18007e3fa  jmp     loc_18007E348
0x18007e3ff  lea     rcx, [rsp+2A0h+var_270]; this
0x18007e404  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18007e409  mov     ebx, eax
0x18007e40b  test    eax, eax
0x18007e40d  jns     short loc_18007E416
0x18007e40f  mov     edx, 1C5h
0x18007e414  jmp     short loc_18007E3CB
0x18007e416  mov     rdx, rsi; unsigned __int64
0x18007e419  lea     rcx, [rsp+2A0h+var_270]; this
0x18007e41e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007e423  mov     ebx, eax
0x18007e425  test    eax, eax
0x18007e427  jns     short loc_18007E430
0x18007e429  mov     edx, 1C6h
0x18007e42e  jmp     short loc_18007E3CB
0x18007e430  lea     rcx, [rsp+2A0h+var_270]; this
0x18007e435  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18007e43a  mov     ebx, eax
0x18007e43c  test    eax, eax
0x18007e43e  jns     short loc_18007E447
0x18007e440  mov     edx, 1C7h
0x18007e445  jmp     short loc_18007E3CB
0x18007e447  mov     r9d, 10h
0x18007e44d  lea     rdx, [rbp+1A0h+var_50]
0x18007e454  lea     r8d, [r9-7]
0x18007e458  lea     ecx, [r9-8]
0x18007e45c  call    cs:__imp__o__itow_s
0x18007e462  test    eax, eax
0x18007e464  jz      short loc_18007E488
0x18007e466  mov     rcx, [rbp+1A8h]; this
0x18007e46d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e474  mov     ebx, 8000FFFFh
0x18007e479  mov     edx, 158h; void *
0x18007e47e  mov     r9d, ebx; char *
0x18007e481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e486  jmp     short loc_18007E49F
0x18007e488  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18007e48f  lea     rcx, [rsp+2A0h+var_270]; this
0x18007e494  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18007e499  mov     ebx, eax
0x18007e49b  test    eax, eax
0x18007e49d  jns     short loc_18007E4A9
0x18007e49f  mov     edx, 1C8h
0x18007e4a4  jmp     loc_18007E3CB
0x18007e4a9  mov     rdx, [rbp+1A0h+var_58]
0x18007e4b0  lea     r9, [rbp+1A0h+var_48]
0x18007e4b7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007e4bc  xor     r8d, r8d
0x18007e4bf  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18007e4c6  mov     [rbp+1A0h+var_48], r12
0x18007e4cd  mov     [rbp+1A0h+var_40], 1
0x18007e4d4  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007e4da  lea     rcx, [rbp+1A0h+var_50]
0x18007e4e1  mov     ebx, eax
0x18007e4e3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007e4e8  test    ebx, ebx
0x18007e4ea  jns     short loc_18007E511
0x18007e4ec  mov     rcx, [rbp+1A8h]; this
0x18007e4f3  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007e4fa  mov     r9d, ebx; char *
0x18007e4fd  mov     edx, 1B0h; void *
0x18007e502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e507  mov     edx, 1CBh
0x18007e50c  jmp     loc_18007E3CB
0x18007e511  cmp     [rdi], r12
0x18007e514  jz      short loc_18007E51A
0x18007e516  mov     [rdi+10h], r14
0x18007e51a  lea     rdx, aDependencygrap; "DependencyGraph\\Index\\UserAndDependen"...
0x18007e521  lea     rcx, [rsp+2A0h+var_280]; this
0x18007e526  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007e52b  mov     ebx, eax
0x18007e52d  test    eax, eax
0x18007e52f  jns     short loc_18007E53B
0x18007e531  mov     edx, 1D1h
0x18007e536  jmp     loc_18007E3CB
0x18007e53b  mov     rcx, [rsp+2A0h+var_270]
0x18007e540  mov     [rsp+2A0h+var_270], r12
0x18007e545  test    rcx, rcx
0x18007e548  jz      short loc_18007E550
0x18007e54a  call    cs:__imp_SRCache_Free
0x18007e550  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18007e555  mov     qword ptr [rsp+2A0h+var_280], r12
0x18007e55a  test    rcx, rcx
0x18007e55d  jz      short loc_18007E565
0x18007e55f  call    cs:__imp_SRCacheContext_Close
0x18007e565  xor     eax, eax
0x18007e567  mov     rcx, [rbp+1A0h+var_38]
0x18007e56e  xor     rcx, rsp; StackCookie
0x18007e571  call    __security_check_cookie
0x18007e576  add     rsp, 270h
0x18007e57d  pop     r15
0x18007e57f  pop     r14
0x18007e581  pop     r12
0x18007e583  pop     rdi
0x18007e584  pop     rsi
0x18007e585  pop     rbx
0x18007e586  pop     rbp
0x18007e587  retn
```
