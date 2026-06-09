# VsmmSvcPartitionChangeLifeState

- ea: `0x1400cc4b8`
- end: `0x1400cc667`
- name: `VsmmSvcPartitionChangeLifeState`
- size: `431`
- prototype: `__int64 __fastcall(__int64, int, volatile void *, ULONG)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14008b788`

## callees

- `0x140038630`
- `0x1400cc4b8`
- `0x1400ccb5c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400cc518`
- `ntoskrnl!ProbeForRead` at `0x1400cc518`
- `ntoskrnl!IoFreeMdl` at `0x1400cc63e`
- `ntoskrnl!IoFreeMdl` at `0x1400cc63e`
- `ntoskrnl!IoAllocateMdl` at `0x1400cc534`
- `ntoskrnl!IoAllocateMdl` at `0x1400cc534`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400cc563`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400cc563`
- `ntoskrnl!MmUnlockPages` at `0x1400cc62a`
- `ntoskrnl!MmUnlockPages` at `0x1400cc62a`

## pseudocode

```c
__int64 __fastcall VsmmSvcPartitionChangeLifeState(__int64 a1, int a2, volatile void *a3, ULONG a4)
{
  char v7; // r14
  struct _MDL *v8; // rdi
  int v9; // edx
  int v10; // ebx
  int v11; // r12d
  struct _MDL *Mdl; // rax
  __int16 ByteOffset; // r9
  unsigned __int16 ByteCount; // ax
  struct _MDL *v15; // r8

  v7 = 0;
  v8 = 0;
  v9 = a2 - 1;
  if ( v9 )
  {
    if ( v9 != 1 )
    {
LABEL_3:
      v10 = -1073741811;
      goto LABEL_16;
    }
    v11 = 1;
  }
  else
  {
    v11 = 0;
  }
  if ( a3 )
  {
    ProbeForRead(a3, a4, 1u);
    Mdl = IoAllocateMdl((PVOID)a3, a4, 0, 0, 0);
    v8 = Mdl;
    if ( !Mdl )
    {
      v10 = -1073741670;
      goto LABEL_16;
    }
    MmProbeAndLockPages(Mdl, 0, IoReadAccess);
    v7 = 1;
    if ( ((v8->ByteCount + ((v8->ByteOffset + LODWORD(v8->StartVa)) & 0xFFF) + 4095LL) & 0xFFFFFFFFFFFFF000uLL) > 0x8000 )
    {
      v10 = -1073741811;
      VidTraceErrorInternal0("VsmmSvcPartitionChangeLifeState", "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c", 346);
      goto LABEL_16;
    }
    ByteOffset = v8->ByteOffset;
    ByteCount = v8->ByteCount;
    v15 = v8 + 1;
  }
  else
  {
    if ( a4 )
      goto LABEL_3;
    ByteCount = 0;
    v15 = 0;
    ByteOffset = 0;
  }
  v10 = VsmmSvcpCallChangePartitionState(*(_QWORD *)(a1 + 648), v11, v15, ByteOffset, ByteCount);
  if ( v10 >= 0 )
    v10 = 0;
LABEL_16:
  if ( v7 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400cc4b8  mov     [rsp+arg_0], rbx
0x1400cc4bd  mov     [rsp+arg_10], rsi
0x1400cc4c2  push    rdi
0x1400cc4c3  push    r12
0x1400cc4c5  push    r13
0x1400cc4c7  push    r14
0x1400cc4c9  push    r15
0x1400cc4cb  sub     rsp, 40h
0x1400cc4cf  mov     ebx, r9d
0x1400cc4d2  mov     r15, r8
0x1400cc4d5  mov     r13, rcx
0x1400cc4d8  xor     esi, esi
0x1400cc4da  mov     r14b, sil
0x1400cc4dd  mov     edi, esi
0x1400cc4df  mov     [rsp+68h+var_30], rsi
0x1400cc4e4  sub     edx, 1
0x1400cc4e7  jz      short loc_1400CC500
0x1400cc4e9  cmp     edx, 1
0x1400cc4ec  jz      short loc_1400CC4F8
0x1400cc4ee  mov     ebx, 0C000000Dh
0x1400cc4f3  jmp     loc_1400CC622
0x1400cc4f8  mov     r12d, 1
0x1400cc4fe  jmp     short loc_1400CC503
0x1400cc500  mov     r12d, esi
0x1400cc503  test    r15, r15
0x1400cc506  jz      loc_1400CC5F6
0x1400cc50c  mov     rdx, rbx; Length
0x1400cc50f  mov     r8d, 1; Alignment
0x1400cc515  mov     rcx, r15; Address
0x1400cc518  call    cs:__imp_ProbeForRead
0x1400cc51f  nop     dword ptr [rax+rax+00h]
0x1400cc524  mov     qword ptr [rsp+68h+Irp], rsi; Irp
0x1400cc529  xor     r9d, r9d; ChargeQuota
0x1400cc52c  xor     r8d, r8d; SecondaryBuffer
0x1400cc52f  mov     edx, ebx; Length
0x1400cc531  mov     rcx, r15; VirtualAddress
0x1400cc534  call    cs:__imp_IoAllocateMdl
0x1400cc53b  nop     dword ptr [rax+rax+00h]
0x1400cc540  mov     rdi, rax
0x1400cc543  mov     [rsp+68h+var_30], rax
0x1400cc548  test    rax, rax
0x1400cc54b  jnz     short loc_1400CC55B
0x1400cc54d  mov     ebx, 0C000009Ah
0x1400cc552  mov     [rsp+68h+var_38], ebx
0x1400cc556  jmp     loc_1400CC622
0x1400cc55b  xor     r8d, r8d; Operation
0x1400cc55e  xor     edx, edx; AccessMode
0x1400cc560  mov     rcx, rdi; MemoryDescriptorList
0x1400cc563  call    cs:__imp_MmProbeAndLockPages
0x1400cc56a  nop     dword ptr [rax+rax+00h]
0x1400cc56f  nop
0x1400cc570  mov     r14b, 1
0x1400cc573  mov     ecx, [rdi+20h]
0x1400cc576  add     ecx, [rdi+2Ch]
0x1400cc579  and     ecx, 0FFFh
0x1400cc57f  mov     eax, [rdi+28h]
0x1400cc582  add     rcx, 0FFFh
0x1400cc589  add     rcx, rax
0x1400cc58c  and     rcx, 0FFFFFFFFFFFFF000h
0x1400cc593  cmp     rcx, 8000h
0x1400cc59a  jbe     short loc_1400CC5BC
0x1400cc59c  mov     ebx, 0C000000Dh
0x1400cc5a1  mov     r8d, 15Ah
0x1400cc5a7  lea     rdx, aOnecoreVmVidSy_4; "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c"
0x1400cc5ae  lea     rcx, aVsmmsvcpartiti_2; "VsmmSvcPartitionChangeLifeState"
0x1400cc5b5  call    VidTraceErrorInternal0
0x1400cc5ba  jmp     short loc_1400CC622
0x1400cc5bc  movzx   r9d, word ptr [rdi+2Ch]
0x1400cc5c1  movzx   eax, word ptr [rdi+28h]
0x1400cc5c5  lea     r8, [rdi+30h]
0x1400cc5c9  jmp     short loc_1400CC607
0x1400cc5cb  mov     ebx, eax
0x1400cc5cd  mov     [rsp+68h+var_38], eax
0x1400cc5d1  mov     r8d, 14Eh
0x1400cc5d7  lea     rdx, aOnecoreVmVidSy_4; "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c"
0x1400cc5de  lea     rcx, aVsmmsvcpartiti_2; "VsmmSvcPartitionChangeLifeState"
0x1400cc5e5  call    VidTraceErrorInternal0
0x1400cc5ea  xor     esi, esi
0x1400cc5ec  mov     r14b, sil
0x1400cc5ef  mov     rdi, [rsp+68h+var_30]
0x1400cc5f4  jmp     short loc_1400CC622
0x1400cc5f6  test    r9d, r9d
0x1400cc5f9  jnz     loc_1400CC4EE
0x1400cc5ff  mov     eax, esi
0x1400cc601  mov     r8, rsi
0x1400cc604  mov     r9d, esi
0x1400cc607  mov     word ptr [rsp+68h+Irp], ax
0x1400cc60c  mov     edx, r12d
0x1400cc60f  mov     rcx, [r13+288h]
0x1400cc616  call    VsmmSvcpCallChangePartitionState
0x1400cc61b  mov     ebx, eax
0x1400cc61d  test    eax, eax
0x1400cc61f  cmovns  ebx, esi
0x1400cc622  test    r14b, r14b
0x1400cc625  jz      short loc_1400CC636
0x1400cc627  mov     rcx, rdi; MemoryDescriptorList
0x1400cc62a  call    cs:__imp_MmUnlockPages
0x1400cc631  nop     dword ptr [rax+rax+00h]
0x1400cc636  test    rdi, rdi
0x1400cc639  jz      short loc_1400CC64A
0x1400cc63b  mov     rcx, rdi; Mdl
0x1400cc63e  call    cs:__imp_IoFreeMdl
0x1400cc645  nop     dword ptr [rax+rax+00h]
0x1400cc64a  mov     eax, ebx
0x1400cc64c  lea     r11, [rsp+68h+var_28]
0x1400cc651  mov     rbx, [r11+30h]
0x1400cc655  mov     rsi, [r11+40h]
0x1400cc659  mov     rsp, r11
0x1400cc65c  pop     r15
0x1400cc65e  pop     r14
0x1400cc660  pop     r13
0x1400cc662  pop     r12
0x1400cc664  pop     rdi
0x1400cc665  retn
```
