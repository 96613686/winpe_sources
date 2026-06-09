# Srv2AllocateLookasideWorkItem

- ea: `0x140016560`
- end: `0x1400167e9`
- name: `Srv2AllocateLookasideWorkItem`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140016560`
- `0x1400222ec`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x1400166b7`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400166b7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001669f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001669f`
- `ntoskrnl!MmSizeOfMdl` at `0x140016606`
- `ntoskrnl!MmSizeOfMdl` at `0x140016606`
- `ntoskrnl!ExAllocatePool3` at `0x14001659a`
- `ntoskrnl!ExAllocatePool3` at `0x14001659a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400165e0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400165e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167af`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400165be`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400165be`

## pseudocode

```c
__int64 Srv2AllocateLookasideWorkItem()
{
  __int64 v0; // rdx
  __int64 v1; // rbx
  __int64 Irp; // rax
  unsigned int v3; // eax
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  struct _MDL *v8; // rcx
  __int64 v9; // r9
  int v10; // edx
  unsigned __int64 v11; // r8
  __int64 v12; // r10
  __int128 v14; // [rsp+30h] [rbp-18h] BYREF

  v14 = 0;
  LOBYTE(v14) = 1;
  DWORD2(v14) = 0;
  v1 = ExAllocatePool3(64, 1888, 1999786828, &v14, 1);
  if ( !v1 )
    return 0;
  LOBYTE(v0) = 15;
  Irp = IoAllocateIrpEx(-1, v0, 0);
  *(_QWORD *)(v1 + 120) = Irp;
  if ( !Irp )
  {
    ExFreePoolWithTag((PVOID)v1, 0x7732534Cu);
    return 0;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v1 + 80));
  *(_QWORD *)(v1 + 560) = v1 + 912;
  v3 = MmSizeOfMdl((PVOID)0xFFF, 0x150u);
  v4 = (v1 + 1351) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v1 + 824) = v4;
  v5 = v3 + 7LL;
  v6 = (v4 + v5) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v1 + 848) = v6;
  v7 = (v6 + v5) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v1 + 792) = v7;
  v7 += 80LL;
  *(_QWORD *)v4 = 0;
  *(_WORD *)(v4 + 10) = 0;
  *(_DWORD *)(v4 + 40) = 256;
  *(_WORD *)(v4 + 8) = 8 * (((unsigned __int16)((v7 & 0xFFF) + 4351) >> 12) + 6);
  *(_QWORD *)(v4 + 32) = v7 & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(v4 + 44) = v7 & 0xFFF;
  v8 = *(struct _MDL **)(v1 + 824);
  *(_QWORD *)(v1 + 792) += 80LL;
  MmBuildMdlForNonPagedPool(v8);
  MmMdlPageContentsState(*(_QWORD *)(v1 + 824), 1);
  *(_WORD *)(*(_QWORD *)(v1 + 824) + 10LL) |= 0x1000u;
  v9 = *(_QWORD *)(v1 + 848);
  v10 = *(_QWORD *)(v1 + 792);
  v11 = *(_QWORD *)(v1 + 792) & 0xFFFFFFFFFFFFF000uLL;
  v12 = *(unsigned int *)(*(_QWORD *)(v1 + 824) + 40LL);
  *(_QWORD *)(v1 + 168) = *(_QWORD *)(v1 + 120);
  *(_QWORD *)(v1 + 800) = (unsigned int)v12;
  *(_QWORD *)v9 = 0;
  *(_WORD *)(v9 + 10) = 0;
  *(_QWORD *)(v9 + 32) = v11;
  *(_DWORD *)(v9 + 40) = v12;
  *(_WORD *)(v9 + 8) = 8 * ((((unsigned __int64)(v10 & 0xFFF) + v12 + 4095) >> 12) + 6);
  *(_DWORD *)(v9 + 44) = v10 & 0xFFF;
  *(_QWORD *)(v1 + 320) = 0;
  *(_DWORD *)(v1 + 328) = 56;
  *(_QWORD *)(v1 + 352) = 0;
  *(_QWORD *)(v1 + 360) = 7;
  *(_QWORD *)(v1 + 304) = v1 + 768;
  *(_QWORD *)(v1 + 312) = v1 + 768;
  _InterlockedIncrement(&Srv2TotalWorkItemCount);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_1f56813514af312e5a39176f5ad11993_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x140016560  mov     [rsp+arg_8], rbx
0x140016565  push    rsi
0x140016566  sub     rsp, 40h
0x14001656a  xorps   xmm0, xmm0
0x14001656d  mov     [rsp+48h+var_28], 1
0x140016575  movups  [rsp+48h+var_18], xmm0
0x14001657a  xor     esi, esi
0x14001657c  mov     byte ptr [rsp+48h+var_18], 1
0x140016581  lea     r9, [rsp+48h+var_18]
0x140016586  mov     dword ptr [rsp+48h+var_18+8], esi
0x14001658a  mov     edx, 760h
0x14001658f  mov     ecx, 40h ; '@'
0x140016594  mov     r8d, 7732534Ch
0x14001659a  call    cs:__imp_ExAllocatePool3
0x1400165a1  nop     dword ptr [rax+rax+00h]
0x1400165a6  mov     rbx, rax
0x1400165a9  test    rax, rax
0x1400165ac  jz      loc_1400167BB
0x1400165b2  xor     r8d, r8d
0x1400165b5  mov     dl, 0Fh
0x1400165b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400165be  call    cs:__imp_IoAllocateIrpEx
0x1400165c5  nop     dword ptr [rax+rax+00h]
0x1400165ca  mov     [rbx+78h], rax
0x1400165ce  test    rax, rax
0x1400165d1  jz      loc_1400167A7
0x1400165d7  lea     rcx, [rbx+50h]; SpinLock
0x1400165db  mov     [rsp+48h+arg_0], rdi
0x1400165e0  call    cs:__imp_KeInitializeSpinLock
0x1400165e7  nop     dword ptr [rax+rax+00h]
0x1400165ec  lea     rax, [rbx+390h]
0x1400165f3  mov     edi, 0FFFh
0x1400165f8  mov     ecx, edi; Base
0x1400165fa  mov     [rbx+230h], rax
0x140016601  mov     edx, 150h; Length
0x140016606  call    cs:__imp_MmSizeOfMdl
0x14001660d  nop     dword ptr [rax+rax+00h]
0x140016612  mov     ecx, eax
0x140016614  mov     edx, 10FFh
0x140016619  lea     r8, [rbx+547h]
0x140016620  and     r8, 0FFFFFFFFFFFFFFF8h
0x140016624  mov     [rbx+338h], r8
0x14001662b  lea     rax, [rcx+7]
0x14001662f  add     rcx, 7
0x140016633  add     rax, r8
0x140016636  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001663a  mov     [rbx+350h], rax
0x140016641  add     rcx, rax
0x140016644  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140016648  mov     [rbx+318h], rcx
0x14001664f  add     rcx, 50h ; 'P'
0x140016653  movzx   eax, cx
0x140016656  mov     [r8], rsi
0x140016659  and     ax, di
0x14001665c  mov     [r8+0Ah], si
0x140016661  add     ax, dx
0x140016664  mov     dword ptr [r8+28h], 100h
0x14001666c  shr     ax, 0Ch
0x140016670  add     ax, 6
0x140016674  shl     ax, 3
0x140016678  mov     [r8+8], ax
0x14001667d  mov     rax, rcx
0x140016680  and     ecx, edi
0x140016682  and     rax, 0FFFFFFFFFFFFF000h
0x140016688  mov     [r8+20h], rax
0x14001668c  mov     [r8+2Ch], ecx
0x140016690  mov     rcx, [rbx+338h]; MemoryDescriptorList
0x140016697  add     qword ptr [rbx+318h], 50h ; 'P'
0x14001669f  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400166a6  nop     dword ptr [rax+rax+00h]
0x1400166ab  mov     rcx, [rbx+338h]
0x1400166b2  mov     edx, 1
0x1400166b7  call    cs:__imp_MmMdlPageContentsState
0x1400166be  nop     dword ptr [rax+rax+00h]
0x1400166c3  mov     rax, [rbx+338h]
0x1400166ca  mov     ecx, 1000h
0x1400166cf  or      [rax+0Ah], cx
0x1400166d3  mov     rax, [rbx+338h]
0x1400166da  mov     r8, [rbx+318h]
0x1400166e1  mov     r9, [rbx+350h]
0x1400166e8  mov     edx, r8d
0x1400166eb  and     r8, 0FFFFFFFFFFFFF000h
0x1400166f2  mov     r10d, [rax+28h]
0x1400166f6  mov     rax, [rbx+78h]
0x1400166fa  mov     [rbx+0A8h], rax
0x140016701  mov     eax, edx
0x140016703  mov     [rbx+320h], r10d
0x14001670a  and     rax, rdi
0x14001670d  mov     [rbx+324h], esi
0x140016713  lea     rcx, [r10+0FFFh]
0x14001671a  mov     [r9], rsi
0x14001671d  add     rcx, rax
0x140016720  mov     [r9+0Ah], si
0x140016725  lea     rax, [rbx+300h]
0x14001672c  mov     [r9+20h], r8
0x140016730  mov     [r9+28h], r10d
0x140016734  shr     rcx, 0Ch
0x140016738  add     cx, 6
0x14001673c  shl     cx, 3
0x140016740  mov     [r9+8], cx
0x140016745  and     edx, edi
0x140016747  mov     [r9+2Ch], edx
0x14001674b  mov     [rbx+140h], rsi
0x140016752  mov     dword ptr [rbx+148h], 38h ; '8'
0x14001675c  mov     [rbx+160h], rsi
0x140016763  mov     qword ptr [rbx+168h], 7
0x14001676e  mov     [rbx+130h], rax
0x140016775  mov     [rbx+138h], rax
0x14001677c  lock inc cs:Srv2TotalWorkItemCount
0x140016783  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001678a  lea     rax, WPP_GLOBAL_Control
0x140016791  mov     rdi, [rsp+48h+arg_0]
0x140016796  cmp     rcx, rax
0x140016799  jz      short loc_1400167A2
0x14001679b  mov     eax, [rcx+2Ch]
0x14001679e  test    al, 20h
0x1400167a0  jnz     short loc_1400167C9
0x1400167a2  mov     rax, rbx
0x1400167a5  jmp     short loc_1400167BD
0x1400167a7  mov     edx, 7732534Ch; Tag
0x1400167ac  mov     rcx, rbx; P
0x1400167af  call    cs:__imp_ExFreePoolWithTag
0x1400167b6  nop     dword ptr [rax+rax+00h]
0x1400167bb  xor     eax, eax
0x1400167bd  mov     rbx, [rsp+48h+arg_8]
0x1400167c2  add     rsp, 40h
0x1400167c6  pop     rsi
0x1400167c7  retn
0x1400167c9  cmp     byte ptr [rcx+29h], 2
0x1400167cd  jb      short loc_1400167A2
0x1400167cf  mov     rcx, [rcx+18h]
0x1400167d3  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x1400167da  mov     edx, 0Bh
0x1400167df  mov     r9, rbx
0x1400167e2  call    WPP_SF_q
0x1400167e7  jmp     short loc_1400167A2
```
