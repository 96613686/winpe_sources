# VhdmpiInitializeGlobalData

- ea: `0x1400ee2ac`
- end: `0x1400ee423`
- name: `VhdmpiInitializeGlobalData`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400ee42c`

## callees

- `0x1400c8378`
- `0x1400ee2ac`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ee3da`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ee3da`
- `ntoskrnl!IoAllocateMdl` at `0x1400ee2d1`
- `ntoskrnl!IoAllocateMdl` at `0x1400ee2d1`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ee2fb`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ee2fb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400ee382`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400ee382`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400ee31f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400ee31f`
- `ntoskrnl!ExAllocatePool2` at `0x1400ee340`
- `ntoskrnl!ExAllocatePool2` at `0x1400ee340`

## pseudocode

```c
__int64 VhdmpiInitializeGlobalData()
{
  struct _MDL *Mdl; // rax
  unsigned int v1; // ebx
  ULONG MaximumProcessorCount; // esi
  ULONG v4; // r15d
  __int64 v5; // r14
  char *v6; // rcx
  _QWORD *v7; // rax
  char *v8; // rax

  Mdl = IoAllocateMdl(VhdZeroPage, 0x1000u, 0, 0, 0);
  VhdZeroPageMdl = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, 0, IoReadAccess);
    VhdZeroPfn = (unsigned __int64)VhdZeroPageMdl[1].Next;
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    VhdPerProcData = (PVOID)ExAllocatePool2(72, 192LL * MaximumProcessorCount, 1212434518);
    if ( !VhdPerProcData )
      return 3221225626LL;
    v4 = 0;
    if ( MaximumProcessorCount )
    {
      v5 = 0;
      do
      {
        KeInitializeSpinLock((PKSPIN_LOCK)VhdPerProcData + 24 * v5);
        v6 = (char *)VhdPerProcData;
        v7 = (char *)VhdPerProcData + 192 * v5 + 8;
        *((_QWORD *)VhdPerProcData + 24 * v5 + 2) = v7;
        *v7 = v7;
        v8 = &v6[192 * v5 + 24];
        *((_QWORD *)v8 + 1) = v8;
        *(_QWORD *)v8 = v8;
        ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&v6[192 * v5 + 64], 0, 0, 0x200u, 0x20u, 0x65444856u, 0);
        ++v4;
        ++v5;
      }
      while ( v4 < MaximumProcessorCount );
    }
    VirtualDiskNextEventIdentifier = 0;
    HandleContextNextEventIdentifier = 0;
    return 0;
  }
  else
  {
    v1 = -1073741670;
    VhdmpiFreeGlobalData(0);
  }
  return v1;
}

```

## disassembly

```asm
0x1400ee2ac  push    rbx
0x1400ee2ae  push    rsi
0x1400ee2af  push    rdi
0x1400ee2b0  push    r14
0x1400ee2b2  push    r15
0x1400ee2b4  sub     rsp, 40h
0x1400ee2b8  xor     edi, edi
0x1400ee2ba  mov     [rsp+68h+Irp], rdi; Irp
0x1400ee2bf  xor     r9d, r9d; ChargeQuota
0x1400ee2c2  xor     r8d, r8d; SecondaryBuffer
0x1400ee2c5  mov     edx, 1000h; Length
0x1400ee2ca  lea     rcx, VhdZeroPage; VirtualAddress
0x1400ee2d1  call    cs:__imp_IoAllocateMdl
0x1400ee2d8  nop     dword ptr [rax+rax+00h]
0x1400ee2dd  mov     cs:VhdZeroPageMdl, rax
0x1400ee2e4  test    rax, rax
0x1400ee2e7  jnz     short loc_1400EE2F3
0x1400ee2e9  mov     ebx, 0C000009Ah
0x1400ee2ee  jmp     loc_1400EE40D
0x1400ee2f3  xor     r8d, r8d; Operation
0x1400ee2f6  xor     edx, edx; AccessMode
0x1400ee2f8  mov     rcx, rax; MemoryDescriptorList
0x1400ee2fb  call    cs:__imp_MmProbeAndLockPages
0x1400ee302  nop     dword ptr [rax+rax+00h]
0x1400ee307  nop
0x1400ee308  mov     rax, cs:VhdZeroPageMdl
0x1400ee30f  mov     rcx, [rax+30h]
0x1400ee313  mov     cs:VhdZeroPfn, rcx
0x1400ee31a  mov     ecx, 0FFFFh; GroupNumber
0x1400ee31f  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400ee326  nop     dword ptr [rax+rax+00h]
0x1400ee32b  mov     esi, eax
0x1400ee32d  lea     rdx, [rsi+rsi*2]
0x1400ee331  shl     rdx, 6
0x1400ee335  mov     ecx, 48h ; 'H'
0x1400ee33a  mov     r8d, 48444856h
0x1400ee340  call    cs:__imp_ExAllocatePool2
0x1400ee347  nop     dword ptr [rax+rax+00h]
0x1400ee34c  mov     cs:VhdPerProcData, rax
0x1400ee353  test    rax, rax
0x1400ee356  jnz     short loc_1400EE362
0x1400ee358  mov     eax, 0C000009Ah
0x1400ee35d  jmp     loc_1400EE416
0x1400ee362  mov     r15d, edi
0x1400ee365  test    esi, esi
0x1400ee367  jz      loc_1400EE3F5
0x1400ee36d  mov     r14, rdi
0x1400ee370  lea     rbx, [r14+r14*2]
0x1400ee374  shl     rbx, 6
0x1400ee378  mov     rcx, cs:VhdPerProcData
0x1400ee37f  add     rcx, rbx; SpinLock
0x1400ee382  call    cs:__imp_KeInitializeSpinLock
0x1400ee389  nop     dword ptr [rax+rax+00h]
0x1400ee38e  mov     rcx, cs:VhdPerProcData
0x1400ee395  lea     rax, [rcx+8]
0x1400ee399  add     rax, rbx
0x1400ee39c  mov     [rbx+rcx+10h], rax
0x1400ee3a1  mov     [rax], rax
0x1400ee3a4  lea     rax, [rcx+18h]
0x1400ee3a8  add     rax, rbx
0x1400ee3ab  mov     [rax+8], rax
0x1400ee3af  mov     [rax], rax
0x1400ee3b2  add     rcx, 40h ; '@'
0x1400ee3b6  add     rcx, rbx; Lookaside
0x1400ee3b9  mov     [rsp+68h+Depth], di; Depth
0x1400ee3be  mov     [rsp+68h+Tag], 65444856h; Tag
0x1400ee3c6  mov     [rsp+68h+Irp], 20h ; ' '; Size
0x1400ee3cf  mov     r9d, 200h; Flags
0x1400ee3d5  xor     r8d, r8d; Free
0x1400ee3d8  xor     edx, edx; Allocate
0x1400ee3da  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400ee3e1  nop     dword ptr [rax+rax+00h]
0x1400ee3e6  inc     r15d
0x1400ee3e9  inc     r14
0x1400ee3ec  cmp     r15d, esi
0x1400ee3ef  jb      loc_1400EE370
0x1400ee3f5  mov     cs:VirtualDiskNextEventIdentifier, rdi
0x1400ee3fc  mov     cs:HandleContextNextEventIdentifier, rdi
0x1400ee403  mov     ebx, edi
0x1400ee405  jmp     short loc_1400EE409
0x1400ee407  mov     ebx, eax
0x1400ee409  test    ebx, ebx
0x1400ee40b  jns     short loc_1400EE414
0x1400ee40d  xor     ecx, ecx; unsigned __int8
0x1400ee40f  call    ?VhdmpiFreeGlobalData@@YAXE@Z; VhdmpiFreeGlobalData(uchar)
0x1400ee414  mov     eax, ebx
0x1400ee416  add     rsp, 40h
0x1400ee41a  pop     r15
0x1400ee41c  pop     r14
0x1400ee41e  pop     rdi
0x1400ee41f  pop     rsi
0x1400ee420  pop     rbx
0x1400ee421  retn
```
