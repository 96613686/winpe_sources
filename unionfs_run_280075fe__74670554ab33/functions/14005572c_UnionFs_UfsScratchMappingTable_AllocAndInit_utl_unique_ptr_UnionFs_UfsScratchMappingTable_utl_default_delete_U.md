# UnionFs::UfsScratchMappingTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsScratchMappingTable,utl::default_delete<UnionFs::UfsScratchMappingTable>> &,UnionFs::StackEventTracer &)

- ea: `0x14005572c`
- end: `0x140055886`
- name: `?AllocAndInit@UfsScratchMappingTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsScratchMappingTable@UnionFs@@U?$default_delete@VUfsScratchMappingTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14005a6fc`
- `0x14005f20c`

## callees

- `0x140005c00`
- `0x1400096d4`
- `0x140022fc0`
- `0x140047e5c`
- `0x14005572c`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400557e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005583e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400557e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005583e`
- `ntoskrnl!ExAllocatePool2` at `0x140055749`
- `ntoskrnl!ExAllocatePool2` at `0x140055749`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400557ca`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055824`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400557ca`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055824`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400557b2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005580c`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400557b2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005580c`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsScratchMappingTable::AllocAndInit(__int64 *a1, struct UnionFs::StackEventTracer *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdi
  unsigned int v6; // ebx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v7; // rcx
  __int64 v8; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  const char *v11; // [rsp+28h] [rbp-30h]

  Pool2 = ExAllocatePool2(64, 152, 1953318485);
  v5 = Pool2;
  if ( !Pool2 )
  {
    v6 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x1F4000E0025LL,
      (unsigned __int64)"UnionFs::UfsScratchMappingTable::AllocAndInit",
      "ORIGIN: Allocating mapping table",
      v11);
    return v6;
  }
  UnionFs::UfsPathTable::UfsPathTable(Pool2, 11);
  v6 = UnionFs::UfsPathTable::InitializeRundown((UnionFs::UfsPathTable *)v5, a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v6,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x470000E0027LL,
      (unsigned __int64)"UnionFs::UfsScratchMappingTable::AllocAndInit",
      "PUSH: Initializing rundown",
      v11);
    UnionFs::UfsPathTable::EmptyAndRunDownTable((UnionFs::UfsPathTable *)v5);
    ExDeleteResourceLite((PERESOURCE)(v5 + 32));
    v7 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v5 + 136);
    if ( v7 )
      ExFreeCacheAwareRundownProtection(v7);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v5 + 8);
    ExFreePoolWithTag((PVOID)v5, 0);
    return v6;
  }
  v8 = *a1;
  *a1 = v5;
  if ( v8 )
  {
    UnionFs::UfsPathTable::EmptyAndRunDownTable((UnionFs::UfsPathTable *)v8);
    ExDeleteResourceLite((PERESOURCE)(v8 + 32));
    v9 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v8 + 136);
    if ( v9 )
      ExFreeCacheAwareRundownProtection(v9);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v8 + 8);
    ExFreePoolWithTag((PVOID)v8, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14005572c  push    rbx
0x14005572e  push    rbp
0x14005572f  push    rsi
0x140055730  push    rdi
0x140055731  sub     rsp, 38h
0x140055735  mov     rbp, rdx
0x140055738  mov     rsi, rcx
0x14005573b  mov     edx, 98h
0x140055740  mov     r8d, 746D4655h
0x140055746  lea     ecx, [rdx-58h]
0x140055749  call    cs:__imp_ExAllocatePool2
0x140055750  nop     dword ptr [rax+rax+00h]
0x140055755  mov     rdi, rax
0x140055758  test    rax, rax
0x14005575b  jz      loc_14005584E
0x140055761  mov     edx, 0Bh
0x140055766  mov     rcx, rax
0x140055769  call    ??0UfsPathTable@UnionFs@@IEAA@W4PATH_TABLE_CONFIGURATION@1@@Z; UnionFs::UfsPathTable::UfsPathTable(UnionFs::PATH_TABLE_CONFIGURATION)
0x14005576e  mov     rdx, rbp; struct UnionFs::StackEventTracer *
0x140055771  mov     rcx, rdi; this
0x140055774  call    ?InitializeRundown@UfsPathTable@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::InitializeRundown(UnionFs::StackEventTracer &)
0x140055779  mov     ebx, eax
0x14005577b  test    eax, eax
0x14005577d  jns     short loc_1400557F5
0x14005577f  lea     rax, aPushInitializi; "PUSH: Initializing rundown"
0x140055786  mov     r8, 470000E0027h; struct UnionFs::StackEventTracer *
0x140055790  lea     r9, aUnionfsUfsscra_3; "UnionFs::UfsScratchMappingTable::AllocA"...
0x140055797  mov     [rsp+58h+var_38], rax; char *
0x14005579c  mov     rdx, rbp; int
0x14005579f  mov     ecx, ebx; this
0x1400557a1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400557a6  mov     rcx, rdi; this
0x1400557a9  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x1400557ae  lea     rcx, [rdi+20h]; Resource
0x1400557b2  call    cs:__imp_ExDeleteResourceLite
0x1400557b9  nop     dword ptr [rax+rax+00h]
0x1400557be  mov     rcx, [rdi+88h]; RunRefCacheAware
0x1400557c5  test    rcx, rcx
0x1400557c8  jz      short loc_1400557D6
0x1400557ca  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400557d1  nop     dword ptr [rax+rax+00h]
0x1400557d6  lea     rcx, [rdi+8]
0x1400557da  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x1400557df  xor     edx, edx; Tag
0x1400557e1  mov     rcx, rdi; P
0x1400557e4  call    cs:__imp_ExFreePoolWithTag
0x1400557eb  nop     dword ptr [rax+rax+00h]
0x1400557f0  jmp     loc_14005587A
0x1400557f5  mov     rbx, [rsi]
0x1400557f8  mov     [rsi], rdi
0x1400557fb  test    rbx, rbx
0x1400557fe  jz      short loc_14005584A
0x140055800  mov     rcx, rbx; this
0x140055803  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x140055808  lea     rcx, [rbx+20h]; Resource
0x14005580c  call    cs:__imp_ExDeleteResourceLite
0x140055813  nop     dword ptr [rax+rax+00h]
0x140055818  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005581f  test    rcx, rcx
0x140055822  jz      short loc_140055830
0x140055824  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005582b  nop     dword ptr [rax+rax+00h]
0x140055830  lea     rcx, [rbx+8]
0x140055834  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x140055839  xor     edx, edx; Tag
0x14005583b  mov     rcx, rbx; P
0x14005583e  call    cs:__imp_ExFreePoolWithTag
0x140055845  nop     dword ptr [rax+rax+00h]
0x14005584a  xor     eax, eax
0x14005584c  jmp     short loc_14005587C
0x14005584e  lea     rax, aOriginAllocati_83; "ORIGIN: Allocating mapping table"
0x140055855  mov     ebx, 0C000009Ah
0x14005585a  mov     ecx, ebx; this
0x14005585c  mov     [rsp+58h+var_38], rax; char *
0x140055861  lea     r9, aUnionfsUfsscra_3; "UnionFs::UfsScratchMappingTable::AllocA"...
0x140055868  mov     r8, 1F4000E0025h; struct UnionFs::StackEventTracer *
0x140055872  mov     rdx, rbp; int
0x140055875  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005587a  mov     eax, ebx
0x14005587c  add     rsp, 38h
0x140055880  pop     rdi
0x140055881  pop     rsi
0x140055882  pop     rbp
0x140055883  pop     rbx
0x140055884  retn
```
