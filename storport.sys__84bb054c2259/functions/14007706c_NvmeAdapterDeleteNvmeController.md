# NvmeAdapterDeleteNvmeController

- ea: `0x14007706c`
- end: `0x14007746a`
- name: `NvmeAdapterDeleteNvmeController`
- size: `1022`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140076890`
- `0x140076a1c`
- `0x1400f33e0`
- `0x1400f6f60`
- `0x1400f72a0`
- `0x1400f8094`
- `0x1401a6048`

## callees

- `0x140071854`
- `0x14007706c`
- `0x1400e7d9c`
- `0x140106c5c`
- `0x14010956c`
- `0x14010e6f8`
- `0x14010e800`
- `0x140115720`
- `0x14012ed7c`
- `0x14012ee8c`
- `0x14012ef60`
- `0x140135e5c`
- `0x140191698`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400770dd`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400770dd`
- `ntoskrnl!IoFreeWorkItem` at `0x14007712e`
- `ntoskrnl!IoFreeWorkItem` at `0x140077153`
- `ntoskrnl!IoFreeWorkItem` at `0x140077178`
- `ntoskrnl!IoFreeWorkItem` at `0x14007719d`
- `ntoskrnl!IoFreeWorkItem` at `0x1400771c2`
- `ntoskrnl!IoFreeWorkItem` at `0x1400771e7`
- `ntoskrnl!IoFreeWorkItem` at `0x14007720c`
- `ntoskrnl!IoFreeWorkItem` at `0x140077231`
- `ntoskrnl!IoFreeWorkItem` at `0x140077256`
- `ntoskrnl!IoFreeWorkItem` at `0x14007727b`
- `ntoskrnl!IoFreeWorkItem` at `0x14007712e`
- `ntoskrnl!IoFreeWorkItem` at `0x140077153`
- `ntoskrnl!IoFreeWorkItem` at `0x140077178`
- `ntoskrnl!IoFreeWorkItem` at `0x14007719d`
- `ntoskrnl!IoFreeWorkItem` at `0x1400771c2`
- `ntoskrnl!IoFreeWorkItem` at `0x1400771e7`
- `ntoskrnl!IoFreeWorkItem` at `0x14007720c`
- `ntoskrnl!IoFreeWorkItem` at `0x140077231`
- `ntoskrnl!IoFreeWorkItem` at `0x140077256`
- `ntoskrnl!IoFreeWorkItem` at `0x14007727b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007710c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077318`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077366`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007738d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400773b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007740f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077436`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077451`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007710c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077318`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077366`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007738d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400773b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007740f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077436`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077451`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140077338`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140077338`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140077098`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140077098`

## pseudocode

```c
void __fastcall NvmeAdapterDeleteNvmeController(PVOID *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdi
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v4; // rcx
  struct _ERESOURCE *v5; // rcx
  int v6; // eax
  void *v7; // rcx
  struct _IO_WORKITEM *v8; // rcx
  struct _IO_WORKITEM *v9; // rcx
  struct _IO_WORKITEM *v10; // rcx
  struct _IO_WORKITEM *v11; // rcx
  struct _IO_WORKITEM *v12; // rcx
  struct _IO_WORKITEM *v13; // rcx
  struct _IO_WORKITEM *v14; // rcx
  struct _IO_WORKITEM *v15; // rcx
  struct _IO_WORKITEM *v16; // rcx
  struct _IO_WORKITEM *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx

  v2 = *a1;
  v3 = v2[16];
  NvmeControllerDeleteErrorRecoveryContext(v2);
  v4 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)*a1 + 69);
  if ( v4 )
    ExWaitForRundownProtectionReleaseCacheAware(v4);
  if ( *((_QWORD *)*a1 + 70) )
    NvmeAdapterSendControlRemoveFabricNvmeController();
  v5 = (struct _ERESOURCE *)*a1;
  v6 = *((_DWORD *)*a1 + 143);
  if ( v6 == 1 )
  {
    StorDeleteDictionary(&v5[6].ExclusiveWaiters);
  }
  else if ( v6 == 2 )
  {
    ExDeleteResourceLite(v5 + 14);
  }
  NvmeControllerDeleteExtendedCommandPool(*a1);
  NvmeAdapterFreeControllerAdminQueue(*a1);
  v7 = (void *)*((_QWORD *)*a1 + 13);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0x52436152u);
    *((_QWORD *)*a1 + 13) = 0;
  }
  v8 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 21);
  if ( v8 )
  {
    IoFreeWorkItem(v8);
    *((_QWORD *)*a1 + 21) = 0;
  }
  v9 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 20);
  if ( v9 )
  {
    IoFreeWorkItem(v9);
    *((_QWORD *)*a1 + 20) = 0;
  }
  v10 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 19);
  if ( v10 )
  {
    IoFreeWorkItem(v10);
    *((_QWORD *)*a1 + 19) = 0;
  }
  v11 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 22);
  if ( v11 )
  {
    IoFreeWorkItem(v11);
    *((_QWORD *)*a1 + 22) = 0;
  }
  v12 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 18);
  if ( v12 )
  {
    IoFreeWorkItem(v12);
    *((_QWORD *)*a1 + 18) = 0;
  }
  v13 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 129);
  if ( v13 )
  {
    IoFreeWorkItem(v13);
    *((_QWORD *)*a1 + 129) = 0;
  }
  v14 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 169);
  if ( v14 )
  {
    IoFreeWorkItem(v14);
    *((_QWORD *)*a1 + 169) = 0;
  }
  v15 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 178);
  if ( v15 )
  {
    IoFreeWorkItem(v15);
    *((_QWORD *)*a1 + 178) = 0;
  }
  v16 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 130);
  if ( v16 )
  {
    IoFreeWorkItem(v16);
    *((_QWORD *)*a1 + 130) = 0;
  }
  v17 = (struct _IO_WORKITEM *)*((_QWORD *)*a1 + 131);
  if ( v17 )
  {
    IoFreeWorkItem(v17);
    *((_QWORD *)*a1 + 131) = 0;
  }
  v18 = (void *)*((_QWORD *)*a1 + 217);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0x52436152u);
    *((_QWORD *)*a1 + 217) = 0;
  }
  NvmeControllerDeleteCommandQueue(*a1);
  DeleteNVMeSplitIoContextPool(*a1);
  DeleteNVMePrpListBufferPool(*a1);
  DeleteNVMeScatterGatherListBufferPool(*a1);
  NvmeControllerDeleteReenumerationContext(*a1);
  v19 = (void *)*((_QWORD *)*a1 + 109);
  if ( v19 )
  {
    ExFreePoolWithTag(v19, 0x52436152u);
    *((_QWORD *)*a1 + 109) = 0;
  }
  v20 = (void *)*((_QWORD *)*a1 + 132);
  if ( v20 )
  {
    ExFreePoolWithTag(v20, 0x52436152u);
    *((_QWORD *)*a1 + 132) = 0;
  }
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)*a1 + 69));
  NvmeControllerReleaseInternalDbgLog(*a1);
  if ( (*((_BYTE *)*a1 + 136) & 2) == 0 )
  {
    v21 = (void *)*((_QWORD *)*a1 + 99);
    if ( v21 )
    {
      ExFreePoolWithTag(v21, 0x52436152u);
      *((_QWORD *)*a1 + 99) = 0;
    }
    v22 = (void *)*((_QWORD *)*a1 + 94);
    if ( v22 )
    {
      ExFreePoolWithTag(v22, 0x52436152u);
      *((_QWORD *)*a1 + 94) = 0;
    }
  }
  v23 = (void *)*((_QWORD *)*a1 + 206);
  if ( v23 )
  {
    ExFreePoolWithTag(v23, 0x52436152u);
    *((_QWORD *)*a1 + 206) = 0;
  }
  if ( v3 && *((_DWORD *)*a1 + 410) )
  {
    StorFreeContiguousMemory(v3 + 1160);
    *((_QWORD *)*a1 + 140) = 0;
    *((_QWORD *)*a1 + 141) = 0;
  }
  v24 = (void *)*((_QWORD *)*a1 + 161);
  if ( v24 )
  {
    ExFreePoolWithTag(v24, 0x52436152u);
    *((_QWORD *)*a1 + 161) = 0;
  }
  v25 = (void *)*((_QWORD *)*a1 + 162);
  if ( v25 )
  {
    ExFreePoolWithTag(v25, 0x52436152u);
    *((_QWORD *)*a1 + 162) = 0;
  }
  ExFreePoolWithTag(*a1, 0x52436152u);
  *a1 = 0;
}

```

## disassembly

```asm
0x14007706c  push    rbx
0x14007706e  push    rbp
0x14007706f  push    rsi
0x140077070  push    rdi
0x140077071  sub     rsp, 28h
0x140077075  mov     rbx, rcx
0x140077078  mov     rcx, [rcx]
0x14007707b  mov     rdi, [rcx+80h]
0x140077082  call    NvmeControllerDeleteErrorRecoveryContext
0x140077087  mov     rax, [rbx]
0x14007708a  xor     esi, esi
0x14007708c  mov     rcx, [rax+228h]; RunRef
0x140077093  test    rcx, rcx
0x140077096  jz      short loc_1400770A4
0x140077098  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14007709f  nop     dword ptr [rax+rax+00h]
0x1400770a4  mov     rcx, [rbx]
0x1400770a7  cmp     [rcx+230h], rsi
0x1400770ae  jz      short loc_1400770B5
0x1400770b0  call    NvmeAdapterSendControlRemoveFabricNvmeController
0x1400770b5  mov     rcx, [rbx]
0x1400770b8  mov     eax, [rcx+23Ch]
0x1400770be  cmp     eax, 1
0x1400770c1  jnz     short loc_1400770D1
0x1400770c3  add     rcx, 298h
0x1400770ca  call    StorDeleteDictionary
0x1400770cf  jmp     short loc_1400770E9
0x1400770d1  cmp     eax, 2
0x1400770d4  jnz     short loc_1400770E9
0x1400770d6  add     rcx, 5B0h; Resource
0x1400770dd  call    cs:__imp_ExDeleteResourceLite
0x1400770e4  nop     dword ptr [rax+rax+00h]
0x1400770e9  mov     rcx, [rbx]
0x1400770ec  call    NvmeControllerDeleteExtendedCommandPool
0x1400770f1  mov     rcx, [rbx]
0x1400770f4  call    NvmeAdapterFreeControllerAdminQueue
0x1400770f9  mov     rax, [rbx]
0x1400770fc  mov     ebp, 52436152h
0x140077101  mov     rcx, [rax+68h]; P
0x140077105  test    rcx, rcx
0x140077108  jz      short loc_14007711F
0x14007710a  mov     edx, ebp; Tag
0x14007710c  call    cs:__imp_ExFreePoolWithTag
0x140077113  nop     dword ptr [rax+rax+00h]
0x140077118  mov     rax, [rbx]
0x14007711b  mov     [rax+68h], rsi
0x14007711f  mov     rax, [rbx]
0x140077122  mov     rcx, [rax+0A8h]; IoWorkItem
0x140077129  test    rcx, rcx
0x14007712c  jz      short loc_140077144
0x14007712e  call    cs:__imp_IoFreeWorkItem
0x140077135  nop     dword ptr [rax+rax+00h]
0x14007713a  mov     rax, [rbx]
0x14007713d  mov     [rax+0A8h], rsi
0x140077144  mov     rax, [rbx]
0x140077147  mov     rcx, [rax+0A0h]; IoWorkItem
0x14007714e  test    rcx, rcx
0x140077151  jz      short loc_140077169
0x140077153  call    cs:__imp_IoFreeWorkItem
0x14007715a  nop     dword ptr [rax+rax+00h]
0x14007715f  mov     rax, [rbx]
0x140077162  mov     [rax+0A0h], rsi
0x140077169  mov     rax, [rbx]
0x14007716c  mov     rcx, [rax+98h]; IoWorkItem
0x140077173  test    rcx, rcx
0x140077176  jz      short loc_14007718E
0x140077178  call    cs:__imp_IoFreeWorkItem
0x14007717f  nop     dword ptr [rax+rax+00h]
0x140077184  mov     rax, [rbx]
0x140077187  mov     [rax+98h], rsi
0x14007718e  mov     rax, [rbx]
0x140077191  mov     rcx, [rax+0B0h]; IoWorkItem
0x140077198  test    rcx, rcx
0x14007719b  jz      short loc_1400771B3
0x14007719d  call    cs:__imp_IoFreeWorkItem
0x1400771a4  nop     dword ptr [rax+rax+00h]
0x1400771a9  mov     rax, [rbx]
0x1400771ac  mov     [rax+0B0h], rsi
0x1400771b3  mov     rax, [rbx]
0x1400771b6  mov     rcx, [rax+90h]; IoWorkItem
0x1400771bd  test    rcx, rcx
0x1400771c0  jz      short loc_1400771D8
0x1400771c2  call    cs:__imp_IoFreeWorkItem
0x1400771c9  nop     dword ptr [rax+rax+00h]
0x1400771ce  mov     rax, [rbx]
0x1400771d1  mov     [rax+90h], rsi
0x1400771d8  mov     rax, [rbx]
0x1400771db  mov     rcx, [rax+408h]; IoWorkItem
0x1400771e2  test    rcx, rcx
0x1400771e5  jz      short loc_1400771FD
0x1400771e7  call    cs:__imp_IoFreeWorkItem
0x1400771ee  nop     dword ptr [rax+rax+00h]
0x1400771f3  mov     rax, [rbx]
0x1400771f6  mov     [rax+408h], rsi
0x1400771fd  mov     rax, [rbx]
0x140077200  mov     rcx, [rax+548h]; IoWorkItem
0x140077207  test    rcx, rcx
0x14007720a  jz      short loc_140077222
0x14007720c  call    cs:__imp_IoFreeWorkItem
0x140077213  nop     dword ptr [rax+rax+00h]
0x140077218  mov     rax, [rbx]
0x14007721b  mov     [rax+548h], rsi
0x140077222  mov     rax, [rbx]
0x140077225  mov     rcx, [rax+590h]; IoWorkItem
0x14007722c  test    rcx, rcx
0x14007722f  jz      short loc_140077247
0x140077231  call    cs:__imp_IoFreeWorkItem
0x140077238  nop     dword ptr [rax+rax+00h]
0x14007723d  mov     rax, [rbx]
0x140077240  mov     [rax+590h], rsi
0x140077247  mov     rax, [rbx]
0x14007724a  mov     rcx, [rax+410h]; IoWorkItem
0x140077251  test    rcx, rcx
0x140077254  jz      short loc_14007726C
0x140077256  call    cs:__imp_IoFreeWorkItem
0x14007725d  nop     dword ptr [rax+rax+00h]
0x140077262  mov     rax, [rbx]
0x140077265  mov     [rax+410h], rsi
0x14007726c  mov     rax, [rbx]
0x14007726f  mov     rcx, [rax+418h]; IoWorkItem
0x140077276  test    rcx, rcx
0x140077279  jz      short loc_140077291
0x14007727b  call    cs:__imp_IoFreeWorkItem
0x140077282  nop     dword ptr [rax+rax+00h]
0x140077287  mov     rax, [rbx]
0x14007728a  mov     [rax+418h], rsi
0x140077291  mov     rax, [rbx]
0x140077294  mov     rcx, [rax+6C8h]; P
0x14007729b  test    rcx, rcx
0x14007729e  jz      short loc_1400772B8
0x1400772a0  mov     edx, ebp; Tag
0x1400772a2  call    cs:__imp_ExFreePoolWithTag
0x1400772a9  nop     dword ptr [rax+rax+00h]
0x1400772ae  mov     rax, [rbx]
0x1400772b1  mov     [rax+6C8h], rsi
0x1400772b8  mov     rcx, [rbx]
0x1400772bb  call    NvmeControllerDeleteCommandQueue
0x1400772c0  mov     rcx, [rbx]
0x1400772c3  call    DeleteNVMeSplitIoContextPool
0x1400772c8  mov     rcx, [rbx]
0x1400772cb  call    DeleteNVMePrpListBufferPool
0x1400772d0  mov     rcx, [rbx]
0x1400772d3  call    DeleteNVMeScatterGatherListBufferPool
0x1400772d8  mov     rcx, [rbx]
0x1400772db  call    NvmeControllerDeleteReenumerationContext
0x1400772e0  mov     rax, [rbx]
0x1400772e3  mov     rcx, [rax+368h]; P
0x1400772ea  test    rcx, rcx
0x1400772ed  jz      short loc_140077307
0x1400772ef  mov     edx, ebp; Tag
0x1400772f1  call    cs:__imp_ExFreePoolWithTag
0x1400772f8  nop     dword ptr [rax+rax+00h]
0x1400772fd  mov     rax, [rbx]
0x140077300  mov     [rax+368h], rsi
0x140077307  mov     rax, [rbx]
0x14007730a  mov     rcx, [rax+420h]; P
0x140077311  test    rcx, rcx
0x140077314  jz      short loc_14007732E
0x140077316  mov     edx, ebp; Tag
0x140077318  call    cs:__imp_ExFreePoolWithTag
0x14007731f  nop     dword ptr [rax+rax+00h]
0x140077324  mov     rax, [rbx]
0x140077327  mov     [rax+420h], rsi
0x14007732e  mov     rcx, [rbx]
0x140077331  mov     rcx, [rcx+228h]; RunRefCacheAware
0x140077338  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14007733f  nop     dword ptr [rax+rax+00h]
0x140077344  mov     rcx, [rbx]
0x140077347  call    NvmeControllerReleaseInternalDbgLog
0x14007734c  mov     rcx, [rbx]
0x14007734f  test    byte ptr [rcx+88h], 2
0x140077356  jnz     short loc_1400773A3
0x140077358  mov     rcx, [rcx+318h]; P
0x14007735f  test    rcx, rcx
0x140077362  jz      short loc_14007737C
0x140077364  mov     edx, ebp; Tag
0x140077366  call    cs:__imp_ExFreePoolWithTag
0x14007736d  nop     dword ptr [rax+rax+00h]
0x140077372  mov     rax, [rbx]
0x140077375  mov     [rax+318h], rsi
0x14007737c  mov     rax, [rbx]
0x14007737f  mov     rcx, [rax+2F0h]; P
0x140077386  test    rcx, rcx
0x140077389  jz      short loc_1400773A3
0x14007738b  mov     edx, ebp; Tag
0x14007738d  call    cs:__imp_ExFreePoolWithTag
0x140077394  nop     dword ptr [rax+rax+00h]
0x140077399  mov     rax, [rbx]
0x14007739c  mov     [rax+2F0h], rsi
0x1400773a3  mov     rax, [rbx]
0x1400773a6  mov     rcx, [rax+670h]; P
0x1400773ad  test    rcx, rcx
0x1400773b0  jz      short loc_1400773CA
0x1400773b2  mov     edx, ebp; Tag
0x1400773b4  call    cs:__imp_ExFreePoolWithTag
0x1400773bb  nop     dword ptr [rax+rax+00h]
0x1400773c0  mov     rax, [rbx]
0x1400773c3  mov     [rax+670h], rsi
0x1400773ca  test    rdi, rdi
0x1400773cd  jz      short loc_1400773FE
0x1400773cf  mov     rdx, [rbx]
0x1400773d2  add     rdx, 658h
0x1400773d9  cmp     [rdx+10h], esi
0x1400773dc  jz      short loc_1400773FE
0x1400773de  lea     rcx, [rdi+488h]
0x1400773e5  call    StorFreeContiguousMemory
0x1400773ea  mov     rax, [rbx]
0x1400773ed  mov     [rax+460h], rsi
0x1400773f4  mov     rax, [rbx]
0x1400773f7  mov     [rax+468h], rsi
0x1400773fe  mov     rax, [rbx]
0x140077401  mov     rcx, [rax+508h]; P
0x140077408  test    rcx, rcx
0x14007740b  jz      short loc_140077425
0x14007740d  mov     edx, ebp; Tag
0x14007740f  call    cs:__imp_ExFreePoolWithTag
0x140077416  nop     dword ptr [rax+rax+00h]
0x14007741b  mov     rax, [rbx]
0x14007741e  mov     [rax+508h], rsi
0x140077425  mov     rax, [rbx]
0x140077428  mov     rcx, [rax+510h]; P
0x14007742f  test    rcx, rcx
0x140077432  jz      short loc_14007744C
0x140077434  mov     edx, ebp; Tag
0x140077436  call    cs:__imp_ExFreePoolWithTag
0x14007743d  nop     dword ptr [rax+rax+00h]
0x140077442  mov     rax, [rbx]
0x140077445  mov     [rax+510h], rsi
0x14007744c  mov     rcx, [rbx]; P
0x14007744f  mov     edx, ebp; Tag
0x140077451  call    cs:__imp_ExFreePoolWithTag
0x140077458  nop     dword ptr [rax+rax+00h]
0x14007745d  mov     [rbx], rsi
0x140077460  add     rsp, 28h
0x140077464  pop     rdi
0x140077465  pop     rsi
0x140077466  pop     rbp
0x140077467  pop     rbx
0x140077468  retn
```
