# OutInitializeQueue

- ea: `0x140009b80`
- end: `0x140009d83`
- name: `OutInitializeQueue`
- size: `515`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000ed00`

## callees

- `0x140009b80`
- `0x14000a030`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140009c5b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140009c5b`
- `ntoskrnl!KeInitializeDpc` at `0x140009bf2`
- `ntoskrnl!KeInitializeDpc` at `0x140009c0f`
- `ntoskrnl!KeInitializeDpc` at `0x140009bf2`
- `ntoskrnl!KeInitializeDpc` at `0x140009c0f`
- `ntoskrnl!IoAllocateMdl` at `0x140009d05`
- `ntoskrnl!IoAllocateMdl` at `0x140009d4b`
- `ntoskrnl!IoAllocateMdl` at `0x140009d05`
- `ntoskrnl!IoAllocateMdl` at `0x140009d4b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009ba1`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009bb4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009ba1`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009bb4`
- `ntoskrnl!KeInitializeTimer` at `0x140009bd5`
- `ntoskrnl!KeInitializeTimer` at `0x140009bd5`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140009cde`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140009d24`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140009cde`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140009d24`

## pseudocode

```c
__int64 __fastcall OutInitializeQueue(char *DeferredContext)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  int v4; // edx
  unsigned int v5; // ecx
  PVOID MappingAddress; // rax
  PMDL Mdl; // rax
  PVOID v8; // rax
  PMDL v9; // rax

  v2 = 0;
  *((_DWORD *)DeferredContext + 66) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 32);
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 88);
  *((_QWORD *)DeferredContext + 35) = DeferredContext + 272;
  *((_QWORD *)DeferredContext + 34) = DeferredContext + 272;
  KeInitializeTimer((PKTIMER)(DeferredContext + 840));
  KeInitializeDpc((PRKDPC)(DeferredContext + 904), OutpPollingDpcRoutine, DeferredContext);
  KeInitializeDpc((PRKDPC)(DeferredContext + 968), OutpPollingDpcRoutine, DeferredContext);
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(DeferredContext + 320),
    0,
    0,
    0x200u,
    *(unsigned int *)(*(_QWORD *)DeferredContext + 1752LL)
  + 240LL
  + *(unsigned int *)(*(_QWORD *)DeferredContext + 1736LL),
    *((_DWORD *)DeferredContext + 268),
    0);
  v3 = *(_QWORD *)DeferredContext;
  v4 = 0x4000;
  DeferredContext[448] = 1;
  v5 = *(_DWORD *)(v3 + 1732);
  *((_QWORD *)DeferredContext + 91) = 1668115286;
  *((_QWORD *)DeferredContext + 93) = 0;
  if ( v5 > 0x4000 )
    v4 = v5;
  *((_QWORD *)DeferredContext + 94) = 0;
  *((_DWORD *)DeferredContext + 181) = v4;
  *((_QWORD *)DeferredContext + 89) = DeferredContext + 744;
  *((_QWORD *)DeferredContext + 92) = 64;
  *((_DWORD *)DeferredContext + 180) = 1;
  if ( *(_BYTE *)(*(_QWORD *)DeferredContext + 2897LL) )
  {
    MappingAddress = MmAllocateMappingAddress(0x1000u, 0x636D6B56u);
    *((_QWORD *)DeferredContext + 81) = MappingAddress;
    if ( !MappingAddress
      || (Mdl = IoAllocateMdl(0, 0x1000u, 0, 0, 0), (*((_QWORD *)DeferredContext + 82) = Mdl) == 0)
      || (v8 = MmAllocateMappingAddress(0x1000u, 0x636D6B56u), (*((_QWORD *)DeferredContext + 95) = v8) == 0)
      || (v9 = IoAllocateMdl(0, 0x1000u, 0, 0, 0), (*((_QWORD *)DeferredContext + 96) = v9) == 0) )
    {
      v2 = -1073741670;
      OutUninitializeQueue(DeferredContext);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140009b80  mov     [rsp+arg_0], rbx
0x140009b85  mov     [rsp+arg_8], rbp
0x140009b8a  push    rdi
0x140009b8b  sub     rsp, 40h
0x140009b8f  mov     rdi, rcx
0x140009b92  xor     ebx, ebx
0x140009b94  mov     [rcx+108h], ebx
0x140009b9a  add     rcx, 100h; SpinLock
0x140009ba1  call    cs:__imp_KeInitializeSpinLock
0x140009ba8  nop     dword ptr [rax+rax+00h]
0x140009bad  lea     rcx, [rdi+2C0h]; SpinLock
0x140009bb4  call    cs:__imp_KeInitializeSpinLock
0x140009bbb  nop     dword ptr [rax+rax+00h]
0x140009bc0  lea     rax, [rdi+110h]
0x140009bc7  lea     rcx, [rdi+348h]; Timer
0x140009bce  mov     [rax+8], rax
0x140009bd2  mov     [rax], rax
0x140009bd5  call    cs:__imp_KeInitializeTimer
0x140009bdc  nop     dword ptr [rax+rax+00h]
0x140009be1  lea     rcx, [rdi+388h]; Dpc
0x140009be8  mov     r8, rdi; DeferredContext
0x140009beb  lea     rdx, OutpPollingDpcRoutine; DeferredRoutine
0x140009bf2  call    cs:__imp_KeInitializeDpc
0x140009bf9  nop     dword ptr [rax+rax+00h]
0x140009bfe  lea     rcx, [rdi+3C8h]; Dpc
0x140009c05  mov     r8, rdi; DeferredContext
0x140009c08  lea     rdx, OutpPollingDpcRoutine; DeferredRoutine
0x140009c0f  call    cs:__imp_KeInitializeDpc
0x140009c16  nop     dword ptr [rax+rax+00h]
0x140009c1b  mov     rax, [rdi]
0x140009c1e  xor     edx, edx; Allocate
0x140009c20  mov     [rsp+48h+Depth], dx; Depth
0x140009c25  mov     r9d, 200h; Flags
0x140009c2b  mov     ecx, [rax+6D8h]
0x140009c31  mov     r8d, [rax+6C8h]
0x140009c38  add     rcx, 0F0h
0x140009c3f  mov     eax, [rdi+430h]
0x140009c45  add     r8, rcx
0x140009c48  mov     [rsp+48h+Tag], eax; Tag
0x140009c4c  lea     rcx, [rdi+140h]; Lookaside
0x140009c53  mov     [rsp+48h+Size], r8; Size
0x140009c58  xor     r8d, r8d; Free
0x140009c5b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140009c62  nop     dword ptr [rax+rax+00h]
0x140009c67  mov     rax, [rdi]
0x140009c6a  mov     edx, 4000h
0x140009c6f  mov     byte ptr [rdi+1C0h], 1
0x140009c76  mov     ecx, [rax+6C4h]
0x140009c7c  cmp     ecx, edx
0x140009c7e  mov     qword ptr [rdi+2D8h], 636D6B56h
0x140009c89  lea     rax, [rdi+2E8h]
0x140009c90  mov     [rdi+2E8h], rbx
0x140009c97  cmova   edx, ecx
0x140009c9a  mov     [rdi+2F0h], rbx
0x140009ca1  mov     [rdi+2D4h], edx
0x140009ca7  mov     [rdi+2C8h], rax
0x140009cae  mov     qword ptr [rdi+2E0h], 40h ; '@'
0x140009cb9  mov     dword ptr [rdi+2D0h], 1
0x140009cc3  mov     rax, [rdi]
0x140009cc6  cmp     [rax+0B51h], bl
0x140009ccc  jz      loc_140009D70
0x140009cd2  mov     ebp, 1000h
0x140009cd7  mov     edx, 636D6B56h; PoolTag
0x140009cdc  mov     ecx, ebp; NumberOfBytes
0x140009cde  call    cs:__imp_MmAllocateMappingAddress
0x140009ce5  nop     dword ptr [rax+rax+00h]
0x140009cea  mov     [rdi+288h], rax
0x140009cf1  test    rax, rax
0x140009cf4  jz      short loc_140009D63
0x140009cf6  xor     r9d, r9d; ChargeQuota
0x140009cf9  mov     [rsp+48h+Size], rbx; Irp
0x140009cfe  xor     r8d, r8d; SecondaryBuffer
0x140009d01  mov     edx, ebp; Length
0x140009d03  xor     ecx, ecx; VirtualAddress
0x140009d05  call    cs:__imp_IoAllocateMdl
0x140009d0c  nop     dword ptr [rax+rax+00h]
0x140009d11  mov     [rdi+290h], rax
0x140009d18  test    rax, rax
0x140009d1b  jz      short loc_140009D63
0x140009d1d  mov     edx, 636D6B56h; PoolTag
0x140009d22  mov     ecx, ebp; NumberOfBytes
0x140009d24  call    cs:__imp_MmAllocateMappingAddress
0x140009d2b  nop     dword ptr [rax+rax+00h]
0x140009d30  mov     [rdi+2F8h], rax
0x140009d37  test    rax, rax
0x140009d3a  jz      short loc_140009D63
0x140009d3c  xor     r9d, r9d; ChargeQuota
0x140009d3f  mov     [rsp+48h+Size], rbx; Irp
0x140009d44  xor     r8d, r8d; SecondaryBuffer
0x140009d47  mov     edx, ebp; Length
0x140009d49  xor     ecx, ecx; VirtualAddress
0x140009d4b  call    cs:__imp_IoAllocateMdl
0x140009d52  nop     dword ptr [rax+rax+00h]
0x140009d57  mov     [rdi+300h], rax
0x140009d5e  test    rax, rax
0x140009d61  jnz     short loc_140009D70
0x140009d63  mov     ebx, 0C000009Ah
0x140009d68  mov     rcx, rdi
0x140009d6b  call    OutUninitializeQueue
0x140009d70  mov     rbp, [rsp+48h+arg_8]
0x140009d75  mov     eax, ebx
0x140009d77  mov     rbx, [rsp+48h+arg_0]
0x140009d7c  add     rsp, 40h
0x140009d80  pop     rdi
0x140009d81  retn
```
