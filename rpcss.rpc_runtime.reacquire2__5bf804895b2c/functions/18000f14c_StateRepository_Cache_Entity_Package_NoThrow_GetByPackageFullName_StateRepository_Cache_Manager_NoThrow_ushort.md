# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18000f14c`
- end: `0x18000f4c8`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `892`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18000caf8`
- `0x18000dae4`
- `0x18000f0b4`
- `0x18007693c`
- `0x180087818`
- `0x18009979c`

## callees

- `0x18000eccc`
- `0x18000f14c`
- `0x18000f4d0`
- `0x1800210f8`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f1d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f29b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f38f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f3ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f3e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f1d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f29b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f38f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f3ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f3e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000f1aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000f1aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000f415`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000f415`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f339`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f374`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f3c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f339`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f374`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000f3c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000f271`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000f271`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000f2ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000f2ce`

## string_xrefs

- `0x18000f30b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000f351`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000f461`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000f2eb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000f432`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000f488`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000f4ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  int *v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h]
  __int64 v29; // [rsp+260h] [rbp+160h]
  _BYTE *v30; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v25 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v21 = 0;
  v23 = v21;
  v24 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v24);
  if ( v25 )
  {
    v7 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v7 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v20 = 1128;
    goto LABEL_31;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v20 = 1129;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
LABEL_32:
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v21, 0);
    return v6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    v13 = v26;
    v26 = 0;
    if ( v13 )
      SRCache_Free();
    v14 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    return v6;
  }
  v23 = (int *)&v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
  if ( v25 )
  {
    v9 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v11 = 1136;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v22, 0);
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_32;
  }
  if ( v22 )
  {
    v19 = SRCacheContext_EnumerateData(v22, 0, a3);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v19,
        v21[0]);
      v11 = 1139;
      goto LABEL_14;
    }
  }
  v10 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFullName");
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v11 = 1142;
    goto LABEL_14;
  }
  v16 = v22;
  v22 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v26;
  v26 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x18000f14c  push    rbp
0x18000f14e  push    rbx
0x18000f14f  push    rsi
0x18000f150  push    rdi
0x18000f151  push    r14
0x18000f153  lea     rbp, [rsp-180h]
0x18000f15b  sub     rsp, 280h
0x18000f162  mov     rax, cs:__security_cookie
0x18000f169  xor     rax, rsp
0x18000f16c  mov     [rbp+1A0h+var_30], rax
0x18000f173  xor     r14d, r14d
0x18000f176  mov     [rsp+2A0h+var_260], 1
0x18000f17b  mov     [r8], r14
0x18000f17e  lea     rax, [rsp+2A0h+var_280]
0x18000f183  mov     rcx, [rcx]
0x18000f186  lea     r9, [rsp+2A0h+var_268]
0x18000f18b  mov     rdi, r8
0x18000f18e  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18000f193  mov     rsi, rdx
0x18000f196  mov     [rsp+2A0h+var_270], rax
0x18000f19b  xor     r8d, r8d
0x18000f19e  mov     [rsp+2A0h+var_268], r14
0x18000f1a3  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18000f1aa  call    cs:__imp_SRCacheContext_Open
0x18000f1b1  nop     dword ptr [rax+rax+00h]
0x18000f1b6  mov     ebx, eax
0x18000f1b8  cmp     [rsp+2A0h+var_260], r14b
0x18000f1bd  jz      short loc_18000F1E0
0x18000f1bf  mov     r8, [rsp+2A0h+var_270]
0x18000f1c4  mov     rdx, [rsp+2A0h+var_268]
0x18000f1c9  mov     rcx, [r8]
0x18000f1cc  mov     [r8], rdx
0x18000f1cf  test    rcx, rcx
0x18000f1d2  jz      short loc_18000F1E0
0x18000f1d4  call    cs:__imp_SRCacheContext_Close
0x18000f1db  nop     dword ptr [rax+rax+00h]
0x18000f1e0  test    ebx, ebx
0x18000f1e2  js      loc_18000F4A6
0x18000f1e8  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18000f1ed  setnz   al
0x18000f1f0  test    al, al
0x18000f1f2  jz      loc_18000F450
0x18000f1f8  xor     edx, edx; Val
0x18000f1fa  mov     [rsp+2A0h+var_250], r14
0x18000f1ff  mov     r8d, 200h; Size
0x18000f205  lea     rcx, [rsp+2A0h+var_248]; void *
0x18000f20a  call    memset_0
0x18000f20f  lea     rax, [rsp+2A0h+var_248]
0x18000f214  mov     [rbp+1A0h+var_48], r14
0x18000f21b  mov     rdx, rsi; unsigned __int16 *
0x18000f21e  mov     [rbp+1A0h+var_38], rax
0x18000f225  lea     rcx, [rsp+2A0h+var_250]; this
0x18000f22a  mov     [rbp+1A0h+var_40], 100h
0x18000f235  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000f23a  mov     ebx, eax
0x18000f23c  test    eax, eax
0x18000f23e  js      loc_18000F34A
0x18000f244  mov     rdx, [rbp+1A0h+var_38]
0x18000f24b  lea     rax, [rsp+2A0h+var_278]
0x18000f250  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000f255  lea     r9, [rsp+2A0h+var_268]
0x18000f25a  xor     r8d, r8d
0x18000f25d  mov     [rsp+2A0h+var_270], rax
0x18000f262  mov     [rsp+2A0h+var_278], r14
0x18000f267  mov     [rsp+2A0h+var_268], r14
0x18000f26c  mov     [rsp+2A0h+var_260], 1
0x18000f271  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000f278  nop     dword ptr [rax+rax+00h]
0x18000f27d  mov     ebx, eax
0x18000f27f  cmp     [rsp+2A0h+var_260], r14b
0x18000f284  jz      short loc_18000F2A7
0x18000f286  mov     r8, [rsp+2A0h+var_270]
0x18000f28b  mov     rdx, [rsp+2A0h+var_268]
0x18000f290  mov     rcx, [r8]
0x18000f293  mov     [r8], rdx
0x18000f296  test    rcx, rcx
0x18000f299  jz      short loc_18000F2A7
0x18000f29b  call    cs:__imp_SRCacheContext_Close
0x18000f2a2  nop     dword ptr [rax+rax+00h]
0x18000f2a7  test    ebx, ebx
0x18000f2a9  js      loc_18000F481
0x18000f2af  mov     rcx, [rsp+2A0h+var_278]
0x18000f2b4  test    rcx, rcx
0x18000f2b7  setnz   al
0x18000f2ba  test    al, al
0x18000f2bc  jnz     loc_18000F410
0x18000f2c2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000f2c7  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18000f2ce  call    cs:__imp_SRCacheContext_AddToCache
0x18000f2d5  nop     dword ptr [rax+rax+00h]
0x18000f2da  mov     ebx, eax
0x18000f2dc  test    eax, eax
0x18000f2de  jns     loc_18000F39F
0x18000f2e4  mov     rcx, [rbp+1A8h]; this
0x18000f2eb  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f2f2  mov     r9d, eax; char *
0x18000f2f5  mov     edx, 1A6h; void *
0x18000f2fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2ff  mov     edx, 476h; void *
0x18000f304  mov     rcx, [rbp+1A8h]; this
0x18000f30b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f312  mov     r9d, ebx; char *
0x18000f315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f31a  xor     edx, edx
0x18000f31c  lea     rcx, [rsp+2A0h+var_278]
0x18000f321  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000f326  mov     rcx, [rsp+2A0h+var_250]
0x18000f32b  mov     [rsp+2A0h+var_250], r14
0x18000f330  test    rcx, rcx
0x18000f333  jz      loc_18000F470
0x18000f339  call    cs:__imp_SRCache_Free
0x18000f340  nop     dword ptr [rax+rax+00h]
0x18000f345  jmp     loc_18000F470
0x18000f34a  mov     rcx, [rbp+1A8h]; this
0x18000f351  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f358  mov     r9d, ebx; char *
0x18000f35b  mov     edx, 46Ch; void *
0x18000f360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f365  mov     rcx, [rsp+2A0h+var_250]
0x18000f36a  mov     [rsp+2A0h+var_250], r14
0x18000f36f  test    rcx, rcx
0x18000f372  jz      short loc_18000F380
0x18000f374  call    cs:__imp_SRCache_Free
0x18000f37b  nop     dword ptr [rax+rax+00h]
0x18000f380  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000f385  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000f38a  test    rcx, rcx
0x18000f38d  jz      short loc_18000F39B
0x18000f38f  call    cs:__imp_SRCacheContext_Close
0x18000f396  nop     dword ptr [rax+rax+00h]
0x18000f39b  mov     eax, ebx
0x18000f39d  jmp     short loc_18000F3F2
0x18000f39f  mov     rcx, [rsp+2A0h+var_278]
0x18000f3a4  mov     [rsp+2A0h+var_278], r14
0x18000f3a9  test    rcx, rcx
0x18000f3ac  jz      short loc_18000F3BA
0x18000f3ae  call    cs:__imp_SRCacheContext_Close
0x18000f3b5  nop     dword ptr [rax+rax+00h]
0x18000f3ba  mov     rcx, [rsp+2A0h+var_250]
0x18000f3bf  mov     [rsp+2A0h+var_250], r14
0x18000f3c4  test    rcx, rcx
0x18000f3c7  jz      short loc_18000F3D5
0x18000f3c9  call    cs:__imp_SRCache_Free
0x18000f3d0  nop     dword ptr [rax+rax+00h]
0x18000f3d5  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000f3da  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000f3df  test    rcx, rcx
0x18000f3e2  jz      short loc_18000F3F0
0x18000f3e4  call    cs:__imp_SRCacheContext_Close
0x18000f3eb  nop     dword ptr [rax+rax+00h]
0x18000f3f0  xor     eax, eax
0x18000f3f2  mov     rcx, [rbp+1A0h+var_30]
0x18000f3f9  xor     rcx, rsp; StackCookie
0x18000f3fc  call    __security_check_cookie
0x18000f401  add     rsp, 280h
0x18000f408  pop     r14
0x18000f40a  pop     rdi
0x18000f40b  pop     rsi
0x18000f40c  pop     rbx
0x18000f40d  pop     rbp
0x18000f40e  retn
0x18000f410  mov     r8, rdi
0x18000f413  xor     edx, edx
0x18000f415  call    cs:__imp_SRCacheContext_EnumerateData
0x18000f41c  nop     dword ptr [rax+rax+00h]
0x18000f421  mov     ebx, eax
0x18000f423  test    eax, eax
0x18000f425  jns     loc_18000F2C2
0x18000f42b  mov     rcx, [rbp+1A8h]; this
0x18000f432  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f439  mov     r9d, eax; char *
0x18000f43c  mov     edx, 2A6h; void *
0x18000f441  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f446  mov     edx, 473h
0x18000f44b  jmp     loc_18000F304
0x18000f450  mov     ebx, 80670012h
0x18000f455  mov     edx, 469h; void *
0x18000f45a  mov     rcx, [rbp+1A8h]; this
0x18000f461  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f468  mov     r9d, ebx; char *
0x18000f46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f470  xor     edx, edx
0x18000f472  lea     rcx, [rsp+2A0h+var_280]
0x18000f477  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000f47c  jmp     loc_18000F39B
0x18000f481  mov     rcx, [rbp+1A8h]; this
0x18000f488  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f48f  mov     r9d, ebx; char *
0x18000f492  mov     edx, 1B0h; void *
0x18000f497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f49c  mov     edx, 470h
0x18000f4a1  jmp     loc_18000F304
0x18000f4a6  mov     rcx, [rbp+1A8h]; this
0x18000f4ad  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f4b4  mov     r9d, ebx; char *
0x18000f4b7  mov     edx, 18Ch; void *
0x18000f4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4c1  mov     edx, 468h
0x18000f4c6  jmp     short loc_18000F45A
```
