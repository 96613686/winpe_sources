# UnionFs::UfsPathCacheManager::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsPathCacheManager,utl::default_delete<UnionFs::UfsPathCacheManager>> &,UnionFs::StackEventTracer &)

- ea: `0x14003e10c`
- end: `0x14003e3d4`
- name: `?AllocAndInit@UfsPathCacheManager@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsPathCacheManager@UnionFs@@U?$default_delete@VUfsPathCacheManager@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x14000701c`

## callees

- `0x140005574`
- `0x14003daf4`
- `0x14003db04`
- `0x14003de50`
- `0x14003e10c`
- `0x14003ea58`
- `0x1400551cc`
- `0x140056ac4`
- `0x140056afc`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e1da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e371`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e1da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e371`
- `ntoskrnl!ExAllocatePool2` at `0x14003e145`
- `ntoskrnl!ExAllocatePool2` at `0x14003e145`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e189`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e206`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e189`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e206`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e16e`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e1eb`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e16e`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e1eb`

## string_xrefs

- `0x14003e381`: `ORIGIN: Allocating UfsPathCacheManager`
- `0x14003e1be`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e300`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e394`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e285`: `PUSH: Allocating RegistryWatcher`
- `0x14003e2ef`: `PUSH: Reading initial value of trimmer threshold`
- `0x14003e2d9`: `UnionFs::UfsRegistryWatcher::InvokeCallbackNow`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCacheManager::AllocAndInit(
        __int64 a1,
        UnionFs::UfsPathCacheManager **a2,
        struct UnionFs::StackEventTracer *a3)
{
  UnionFs::UfsPathCacheManager *Pool2; // rax
  __int64 v7; // rbx
  PFLT_GENERIC_WORKITEM GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v9; // rcx
  PFLT_GENERIC_WORKITEM v10; // rdi
  const char *v11; // rax
  __int64 v12; // r8
  int v13; // edi
  PFLT_GENERIC_WORKITEM v14; // rax
  struct _FLT_GENERIC_WORKITEM *v15; // rcx
  PFLT_GENERIC_WORKITEM v16; // rdi
  __int64 v17; // rax
  const char *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  UnionFs::UfsPathCacheManager *v23; // rdi
  const char *v25; // [rsp+28h] [rbp-130h]
  _BYTE v26[120]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v27[8]; // [rsp+A8h] [rbp-B0h] BYREF
  _QWORD v28[13]; // [rsp+B0h] [rbp-A8h] BYREF
  _QWORD *v29; // [rsp+118h] [rbp-40h]

  Pool2 = (UnionFs::UfsPathCacheManager *)ExAllocatePool2(64, 416, 1835222613);
  if ( !Pool2 || (v7 = UnionFs::UfsPathCacheManager::UfsPathCacheManager(Pool2)) == 0 )
  {
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x5C900110027LL,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      "ORIGIN: Allocating UfsPathCacheManager",
      v25);
    return (unsigned int)v13;
  }
  GenericWorkItem = FltAllocateGenericWorkItem();
  v9 = *(struct _FLT_GENERIC_WORKITEM **)(v7 + 224);
  v10 = GenericWorkItem;
  if ( v9 )
    FltFreeGenericWorkItem(v9);
  *(_QWORD *)(v7 + 224) = v10;
  if ( !v10 )
  {
    v11 = "ORIGIN: Allocating RemovalWorkItem";
    v12 = 0x4330011002FLL;
LABEL_7:
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a3,
      (struct UnionFs::StackEventTracer *)v12,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      v11,
      v25);
LABEL_8:
    UnionFs::UfsPathCacheManager::~UfsPathCacheManager((UnionFs::UfsPathCacheManager *)v7);
    ExFreePoolWithTag((PVOID)v7, 0);
    return (unsigned int)v13;
  }
  v14 = FltAllocateGenericWorkItem();
  v15 = *(struct _FLT_GENERIC_WORKITEM **)(v7 + 272);
  v16 = v14;
  if ( v15 )
    FltFreeGenericWorkItem(v15);
  *(_QWORD *)(v7 + 272) = v16;
  if ( !v16 )
  {
    v11 = "ORIGIN: Allocating TrimmerWorkItem";
    v12 = 0x41500110037LL;
    goto LABEL_7;
  }
  v28[1] = v7;
  v28[0] = off_14007EA00;
  v29 = v28;
  v17 = wistd::function<void (bool)>::function<void (bool)>(v26, v27);
  v13 = UnionFs::UfsRegistryWatcher::AllocAndInit(a1, v17, (UnionFs::UfsRegistryWatcher **)(v7 + 408), a3);
  if ( v13 < 0 )
  {
    v18 = "PUSH: Allocating RegistryWatcher";
    v19 = 0x5BC00110075LL;
    goto LABEL_18;
  }
  v20 = *(_QWORD *)(v7 + 408);
  v21 = *(_QWORD *)(v20 + 160);
  if ( !v21 )
    wistd::__throw_bad_function_call(0);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct UnionFs::StackEventTracer *))(*(_QWORD *)v21 + 32LL))(
          v21,
          *(_QWORD *)(v20 + 40),
          a3);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x598001A0073LL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::InvokeCallbackNow",
      "PUSH: Invoking callback on demand",
      v25);
    v18 = "PUSH: Reading initial value of trimmer threshold";
    v19 = 0x5000011007BLL;
LABEL_18:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a3,
      (struct UnionFs::StackEventTracer *)v19,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      v18,
      v25);
    if ( v29 )
      (*(void (__fastcall **)(_QWORD *))(*v29 + 24LL))(v29);
    goto LABEL_8;
  }
  UnionFs::UfsPathCacheManager::SetRemovalTimer((UnionFs::UfsPathCacheManager *)v7);
  v22 = v29;
  v23 = *a2;
  *a2 = (UnionFs::UfsPathCacheManager *)v7;
  if ( v22 )
    (*(void (__fastcall **)(_QWORD *))(*v22 + 24LL))(v22);
  if ( v23 )
  {
    UnionFs::UfsPathCacheManager::~UfsPathCacheManager(v23);
    ExFreePoolWithTag(v23, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14003e10c  push    rbx
0x14003e10e  push    rbp
0x14003e10f  push    rsi
0x14003e110  push    rdi
0x14003e111  push    r14
0x14003e113  sub     rsp, 130h
0x14003e11a  mov     rax, cs:__security_cookie
0x14003e121  xor     rax, rsp
0x14003e124  mov     [rsp+158h+var_38], rax
0x14003e12c  mov     rsi, r8
0x14003e12f  mov     r14, rdx
0x14003e132  mov     rbp, rcx
0x14003e135  mov     edx, 1A0h
0x14003e13a  mov     ecx, 40h ; '@'
0x14003e13f  mov     r8d, 6D634655h
0x14003e145  call    cs:__imp_ExAllocatePool2
0x14003e14c  nop     dword ptr [rax+rax+00h]
0x14003e151  test    rax, rax
0x14003e154  jz      loc_14003E381
0x14003e15a  mov     rcx, rax; this
0x14003e15d  call    ??0UfsPathCacheManager@UnionFs@@AEAA@XZ; UnionFs::UfsPathCacheManager::UfsPathCacheManager(void)
0x14003e162  mov     rbx, rax
0x14003e165  test    rax, rax
0x14003e168  jz      loc_14003E381
0x14003e16e  call    cs:__imp_FltAllocateGenericWorkItem
0x14003e175  nop     dword ptr [rax+rax+00h]
0x14003e17a  mov     rcx, [rbx+0E0h]; FltWorkItem
0x14003e181  mov     rdi, rax
0x14003e184  test    rcx, rcx
0x14003e187  jz      short loc_14003E195
0x14003e189  call    cs:__imp_FltFreeGenericWorkItem
0x14003e190  nop     dword ptr [rax+rax+00h]
0x14003e195  mov     [rbx+0E0h], rdi
0x14003e19c  test    rdi, rdi
0x14003e19f  jnz     short loc_14003E1EB
0x14003e1a1  lea     rax, aOriginAllocati_82; "ORIGIN: Allocating RemovalWorkItem"
0x14003e1a8  mov     r8, 4330011002Fh; struct UnionFs::StackEventTracer *
0x14003e1b2  mov     edi, 0C000009Ah
0x14003e1b7  mov     [rsp+158h+var_138], rax; char *
0x14003e1bc  mov     ecx, edi; this
0x14003e1be  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e1c5  mov     rdx, rsi; int
0x14003e1c8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e1cd  mov     rcx, rbx; this
0x14003e1d0  call    ??1UfsPathCacheManager@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheManager::~UfsPathCacheManager(void)
0x14003e1d5  xor     edx, edx; Tag
0x14003e1d7  mov     rcx, rbx; P
0x14003e1da  call    cs:__imp_ExFreePoolWithTag
0x14003e1e1  nop     dword ptr [rax+rax+00h]
0x14003e1e6  jmp     loc_14003E3AD
0x14003e1eb  call    cs:__imp_FltAllocateGenericWorkItem
0x14003e1f2  nop     dword ptr [rax+rax+00h]
0x14003e1f7  mov     rcx, [rbx+110h]; FltWorkItem
0x14003e1fe  mov     rdi, rax
0x14003e201  test    rcx, rcx
0x14003e204  jz      short loc_14003E212
0x14003e206  call    cs:__imp_FltFreeGenericWorkItem
0x14003e20d  nop     dword ptr [rax+rax+00h]
0x14003e212  mov     [rbx+110h], rdi
0x14003e219  test    rdi, rdi
0x14003e21c  jnz     short loc_14003E231
0x14003e21e  lea     rax, aOriginAllocati_26; "ORIGIN: Allocating TrimmerWorkItem"
0x14003e225  mov     r8, 41500110037h
0x14003e22f  jmp     short loc_14003E1B2
0x14003e231  lea     rax, off_14007EA00
0x14003e238  mov     [rsp+158h+var_A0], rbx
0x14003e240  mov     [rsp+158h+var_A8], rax
0x14003e248  lea     rdx, [rsp+158h+var_B0]
0x14003e250  lea     rax, [rsp+158h+var_A8]
0x14003e258  lea     rcx, [rsp+158h+var_128]
0x14003e25d  mov     [rsp+158h+var_40], rax
0x14003e265  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003e26a  lea     r8, [rbx+198h]
0x14003e271  mov     r9, rsi
0x14003e274  mov     rdx, rax
0x14003e277  mov     rcx, rbp
0x14003e27a  call    ?AllocAndInit@UfsRegistryWatcher@UnionFs@@SAJAEBU_UNICODE_STRING@@V?$function@$$A6AJAEAVUfsRegistryReader@UnionFs@@AEAVStackEventTracer@2@@Z@wistd@@AEAV?$unique_ptr@VUfsRegistryWatcher@UnionFs@@U?$default_delete@VUfsRegistryWatcher@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryWatcher::AllocAndInit(_UNICODE_STRING const &,wistd::function<long (UnionFs::UfsRegistryReader &,UnionFs::StackEventTracer &)>,utl::unique_ptr<UnionFs::UfsRegistryWatcher,utl::default_delete<UnionFs::UfsRegistryWatcher>> &,UnionFs::StackEventTracer &)
0x14003e27f  mov     edi, eax
0x14003e281  test    eax, eax
0x14003e283  jns     short loc_14003E298
0x14003e285  lea     rax, aPushAllocating_8; "PUSH: Allocating RegistryWatcher"
0x14003e28c  mov     r8, 5BC00110075h
0x14003e296  jmp     short loc_14003E300
0x14003e298  mov     rdx, [rbx+198h]
0x14003e29f  mov     rcx, [rdx+0A0h]; this
0x14003e2a6  test    rcx, rcx
0x14003e2a9  jz      loc_14003E3CE
0x14003e2af  mov     rax, [rcx]
0x14003e2b2  mov     r8, rsi
0x14003e2b5  mov     rdx, [rdx+28h]
0x14003e2b9  mov     rax, [rax+20h]
0x14003e2bd  call    _guard_dispatch_icall
0x14003e2c2  mov     edi, eax
0x14003e2c4  test    eax, eax
0x14003e2c6  jns     short loc_14003E338
0x14003e2c8  lea     rax, aPushInvokingCa; "PUSH: Invoking callback on demand"
0x14003e2cf  mov     r8, 598001A0073h; struct UnionFs::StackEventTracer *
0x14003e2d9  lea     r9, aUnionfsUfsregi_4; "UnionFs::UfsRegistryWatcher::InvokeCall"...
0x14003e2e0  mov     [rsp+158h+var_138], rax; char *
0x14003e2e5  mov     rdx, rsi; int
0x14003e2e8  mov     ecx, edi; this
0x14003e2ea  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e2ef  lea     rax, aPushReadingIni; "PUSH: Reading initial value of trimmer "...
0x14003e2f6  mov     r8, 5000011007Bh; struct UnionFs::StackEventTracer *
0x14003e300  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e307  mov     [rsp+158h+var_138], rax; char *
0x14003e30c  mov     rdx, rsi; int
0x14003e30f  mov     ecx, edi; this
0x14003e311  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e316  mov     rcx, [rsp+158h+var_40]
0x14003e31e  test    rcx, rcx
0x14003e321  jz      loc_14003E1CD
0x14003e327  mov     rax, [rcx]
0x14003e32a  mov     rax, [rax+18h]
0x14003e32e  call    _guard_dispatch_icall
0x14003e333  jmp     loc_14003E1CD
0x14003e338  mov     rcx, rbx; this
0x14003e33b  call    ?SetRemovalTimer@UfsPathCacheManager@UnionFs@@AEAAXXZ; UnionFs::UfsPathCacheManager::SetRemovalTimer(void)
0x14003e340  mov     rcx, [rsp+158h+var_40]
0x14003e348  mov     rdi, [r14]
0x14003e34b  mov     [r14], rbx
0x14003e34e  test    rcx, rcx
0x14003e351  jz      short loc_14003E35F
0x14003e353  mov     rax, [rcx]
0x14003e356  mov     rax, [rax+18h]
0x14003e35a  call    _guard_dispatch_icall
0x14003e35f  test    rdi, rdi
0x14003e362  jz      short loc_14003E37D
0x14003e364  mov     rcx, rdi; this
0x14003e367  call    ??1UfsPathCacheManager@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheManager::~UfsPathCacheManager(void)
0x14003e36c  xor     edx, edx; Tag
0x14003e36e  mov     rcx, rdi; P
0x14003e371  call    cs:__imp_ExFreePoolWithTag
0x14003e378  nop     dword ptr [rax+rax+00h]
0x14003e37d  xor     eax, eax
0x14003e37f  jmp     short loc_14003E3AF
0x14003e381  lea     rax, aOriginAllocati_71; "ORIGIN: Allocating UfsPathCacheManager"
0x14003e388  mov     edi, 0C000009Ah
0x14003e38d  mov     ecx, edi; this
0x14003e38f  mov     [rsp+158h+var_138], rax; char *
0x14003e394  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e39b  mov     r8, 5C900110027h; struct UnionFs::StackEventTracer *
0x14003e3a5  mov     rdx, rsi; int
0x14003e3a8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e3ad  mov     eax, edi
0x14003e3af  mov     rcx, [rsp+158h+var_38]
0x14003e3b7  xor     rcx, rsp; StackCookie
0x14003e3ba  call    __security_check_cookie
0x14003e3bf  add     rsp, 130h
0x14003e3c6  pop     r14
0x14003e3c8  pop     rdi
0x14003e3c9  pop     rsi
0x14003e3ca  pop     rbp
0x14003e3cb  pop     rbx
0x14003e3cc  retn
0x14003e3ce  call    ?__throw_bad_function_call@wistd@@YAXXZ; wistd::__throw_bad_function_call(void)
```
