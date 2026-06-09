# UdfSeqCacheIssueWriteForBuffer

- ea: `0x140008cac`
- end: `0x14000900c`
- name: `UdfSeqCacheIssueWriteForBuffer`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140006680`

## callees

- `0x140008cac`
- `0x14000a2e8`
- `0x14000ca10`
- `0x14000cbcc`
- `0x140010990`
- `0x14002c774`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140008f97`
- `ntoskrnl!IofCallDriver` at `0x140008f97`
- `ntoskrnl!IoAllocateMdl` at `0x140008e1b`
- `ntoskrnl!IoAllocateMdl` at `0x140008e1b`
- `ntoskrnl!MmProbeAndLockPages` at `0x140008e3e`
- `ntoskrnl!MmProbeAndLockPages` at `0x140008e3e`
- `ntoskrnl!IoFreeMdl` at `0x140008e62`
- `ntoskrnl!IoFreeMdl` at `0x140008fc8`
- `ntoskrnl!IoFreeMdl` at `0x14001cf57`
- `ntoskrnl!IoFreeMdl` at `0x140008e62`
- `ntoskrnl!IoFreeMdl` at `0x140008fc8`
- `ntoskrnl!IoFreeMdl` at `0x14001cf57`
- `ntoskrnl!MmUnlockPages` at `0x140008fb8`
- `ntoskrnl!MmUnlockPages` at `0x14001cf47`
- `ntoskrnl!MmUnlockPages` at `0x140008fb8`
- `ntoskrnl!MmUnlockPages` at `0x14001cf47`
- `ntoskrnl!KeClearEvent` at `0x140008d68`
- `ntoskrnl!KeClearEvent` at `0x140008d68`
- `ntoskrnl!IoReuseIrp` at `0x140008de8`
- `ntoskrnl!IoReuseIrp` at `0x140008de8`

## pseudocode

```c
void __fastcall UdfSeqCacheIssueWriteForBuffer(__int64 a1, __int64 a2, __int64 a3, char a4, char a5)
{
  __int64 v6; // r12
  IRP *Irp; // rdi
  int FreeBlocksAndNWA; // r14d
  ULONG v11; // r15d
  struct _MDL *MdlAddress; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v14; // rax
  struct _MDL *v15; // rcx
  int v16; // eax
  __int64 v17; // [rsp+40h] [rbp-58h]
  _DWORD *v18; // [rsp+50h] [rbp-48h]

  v6 = (unsigned int)a3;
  Irp = *(IRP **)(a2 + 648);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 19, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  if ( (*(_DWORD *)(a1 + 2128) & 0x80u) == 0 )
  {
    LOBYTE(a3) = a5;
    if ( !(unsigned __int8)UdfAcquireResource(0, a1 + 136, a3, 0) )
      return;
    *(_DWORD *)(a2 + 4) |= 0x40u;
  }
  v17 = a2 + 8 * (v6 + 4 * v6 + 3);
  FreeBlocksAndNWA = 0;
  KeClearEvent((PRKEVENT)(a2 + 664));
  v18 = (_DWORD *)(a1 + 72);
  v11 = (*(_DWORD *)(a2 + 8) - *(_DWORD *)(v17 + 4)) << *(_DWORD *)(a1 + 72);
  if ( !a4 || (FreeBlocksAndNWA = UdfSeqCacheSyncCache(a1), FreeBlocksAndNWA >= 0) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL) & 2) == 0 )
    {
LABEL_12:
      IoReuseIrp(Irp, 0);
      Irp->Tail.Overlay.Thread = KeGetCurrentThread();
      IoAllocateMdl(*(PVOID *)(v17 + 16), v11, 0, 0, Irp);
      MdlAddress = Irp->MdlAddress;
      if ( MdlAddress )
        MmProbeAndLockPages(MdlAddress, 0, IoReadAccess);
      if ( Irp->MdlAddress )
      {
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 4;
        CurrentStackLocation[-1].Parameters.Read.Length = v11;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (unsigned __int64)*(unsigned int *)(a1 + 684) << *v18;
        *(_DWORD *)(a2 + 656) = 259;
        *(_DWORD *)(a2 + 660) = v11 >> *v18;
        *(_DWORD *)(a2 + 688) = v6;
        *(_DWORD *)(a2 + 692) = *(_DWORD *)(a1 + 684);
        *(_WORD *)v17 = 2;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
        {
          WPP_SF_DDD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            20,
            WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
            *(unsigned int *)(a2 + 660),
            v11,
            *(_DWORD *)(a2 + 692));
        }
        v14 = Irp->Tail.Overlay.CurrentStackLocation;
        v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)UdfSeqCacheWriteCompletion;
        v14[-1].Context = (PVOID)a2;
        v14[-1].Control = 0;
        v14[-1].Control = 64;
        v14[-1].Control = -64;
        v14[-1].Control = -32;
        IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 24), Irp);
        Irp = 0;
      }
      else
      {
        FreeBlocksAndNWA = -1073741670;
      }
      goto LABEL_20;
    }
    FreeBlocksAndNWA = UdfQueryFreeBlocksAndNWA(a1, a1 + 668, a1 + 684);
    if ( FreeBlocksAndNWA >= 0 )
    {
      *(_DWORD *)(a2 + 4) &= ~2u;
      goto LABEL_12;
    }
  }
LABEL_20:
  if ( Irp )
  {
    v15 = Irp->MdlAddress;
    if ( v15 )
    {
      MmUnlockPages(v15);
      IoFreeMdl(Irp->MdlAddress);
      Irp->MdlAddress = 0;
    }
    *(_DWORD *)(a2 + 656) = FreeBlocksAndNWA;
    v16 = *(_DWORD *)(a2 + 4);
    if ( (v16 & 0x40) != 0 )
    {
      *(_DWORD *)(a2 + 4) = v16 & 0xFFFFFFBF;
      UdfReleaseDevice((__int64)v15, a1, 0);
    }
  }
}

```

## disassembly

```asm
0x140008cac  mov     [rsp+arg_10], r8d
0x140008cb1  mov     [rsp+arg_8], rdx
0x140008cb6  mov     [rsp+arg_0], rcx
0x140008cbb  push    rbx
0x140008cbc  push    rsi
0x140008cbd  push    rdi
0x140008cbe  push    r12
0x140008cc0  push    r13
0x140008cc2  push    r14
0x140008cc4  push    r15
0x140008cc6  sub     rsp, 60h
0x140008cca  mov     r13b, r9b
0x140008ccd  mov     r12d, r8d
0x140008cd0  mov     rbx, rdx
0x140008cd3  mov     rsi, rcx
0x140008cd6  mov     rdi, [rdx+288h]
0x140008cdd  lea     rax, WPP_GLOBAL_Control
0x140008ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ceb  cmp     rcx, rax
0x140008cee  jz      short loc_140008D11
0x140008cf0  test    dword ptr [rcx+2Ch], 20000000h
0x140008cf7  jz      short loc_140008D11
0x140008cf9  mov     edx, 13h
0x140008cfe  mov     r9d, r12d
0x140008d01  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x140008d08  mov     rcx, [rcx+18h]
0x140008d0c  call    WPP_SF_d
0x140008d11  mov     eax, [rsi+850h]
0x140008d17  test    al, al
0x140008d19  js      short loc_140008D40
0x140008d1b  lea     rdx, [rsi+88h]
0x140008d22  xor     r9d, r9d
0x140008d25  mov     r8b, [rsp+98h+arg_20]
0x140008d2d  xor     ecx, ecx
0x140008d2f  call    UdfAcquireResource
0x140008d34  test    al, al
0x140008d36  jz      loc_140008FFB
0x140008d3c  or      dword ptr [rbx+4], 40h
0x140008d40  lea     rcx, ds:3[r12*4]
0x140008d48  add     rcx, r12
0x140008d4b  lea     r15, [rbx+rcx*8]
0x140008d4f  mov     [rsp+98h+var_58], r15
0x140008d54  mov     [rsp+98h+var_60], rdi
0x140008d59  xor     r14d, r14d
0x140008d5c  mov     [rsp+98h+var_68], r14d
0x140008d61  lea     rcx, [rbx+298h]; Event
0x140008d68  call    cs:__imp_KeClearEvent
0x140008d6f  nop     dword ptr [rax+rax+00h]
0x140008d74  lea     rcx, [rsi+48h]
0x140008d78  mov     [rsp+98h+var_48], rcx
0x140008d7d  mov     eax, [r15+4]
0x140008d81  mov     r15d, [rbx+8]
0x140008d85  sub     r15d, eax
0x140008d88  mov     ecx, [rcx]
0x140008d8a  shl     r15d, cl
0x140008d8d  mov     [rsp+98h+var_64], r15d
0x140008d92  test    r13b, r13b
0x140008d95  jz      short loc_140008DAE
0x140008d97  mov     rcx, rsi
0x140008d9a  call    UdfSeqCacheSyncCache
0x140008d9f  mov     r14d, eax
0x140008da2  mov     [rsp+98h+var_68], eax
0x140008da6  test    eax, eax
0x140008da8  js      loc_140008FAA
0x140008dae  mov     rcx, [rsi+68h]
0x140008db2  mov     edx, [rcx+4]
0x140008db5  test    dl, 2
0x140008db8  jz      short loc_140008DE3
0x140008dba  lea     r8, [rsi+2ACh]
0x140008dc1  lea     rdx, [rsi+29Ch]
0x140008dc8  mov     rcx, rsi
0x140008dcb  call    UdfQueryFreeBlocksAndNWA
0x140008dd0  mov     r14d, eax
0x140008dd3  mov     [rsp+98h+var_68], eax
0x140008dd7  test    eax, eax
0x140008dd9  js      loc_140008FAA
0x140008ddf  and     dword ptr [rbx+4], 0FFFFFFFDh
0x140008de3  xor     edx, edx; Iostatus
0x140008de5  mov     rcx, rdi; Irp
0x140008de8  call    cs:__imp_IoReuseIrp
0x140008def  nop     dword ptr [rax+rax+00h]
0x140008df4  mov     rax, gs:188h
0x140008dfd  mov     [rdi+98h], rax
0x140008e04  mov     [rsp+98h+Irp], rdi; Irp
0x140008e09  xor     r9d, r9d; ChargeQuota
0x140008e0c  xor     r8d, r8d; SecondaryBuffer
0x140008e0f  mov     edx, r15d; Length
0x140008e12  mov     rcx, [rsp+98h+var_58]
0x140008e17  mov     rcx, [rcx+10h]; VirtualAddress
0x140008e1b  call    cs:__imp_IoAllocateMdl
0x140008e22  nop     dword ptr [rax+rax+00h]
0x140008e27  lea     r13, [rdi+8]
0x140008e2b  mov     [rsp+98h+var_50], r13
0x140008e30  mov     rcx, [r13+0]; MemoryDescriptorList
0x140008e34  test    rcx, rcx
0x140008e37  jz      short loc_140008EAC
0x140008e39  xor     r8d, r8d; Operation
0x140008e3c  xor     edx, edx; AccessMode
0x140008e3e  call    cs:__imp_MmProbeAndLockPages
0x140008e45  nop     dword ptr [rax+rax+00h]
0x140008e4a  mov     r8d, 2
0x140008e50  lea     r9, WPP_GLOBAL_Control
0x140008e57  jmp     short loc_140008EB9
0x140008e59  mov     rdi, [rsp+98h+var_60]
0x140008e5e  mov     rcx, [rdi+8]; Mdl
0x140008e62  call    cs:__imp_IoFreeMdl
0x140008e69  nop     dword ptr [rax+rax+00h]
0x140008e6e  mov     qword ptr [rdi+8], 0
0x140008e76  lea     r9, WPP_GLOBAL_Control
0x140008e7d  mov     r8d, 2
0x140008e83  mov     r12d, [rsp+98h+arg_10]
0x140008e8b  mov     rbx, [rsp+98h+arg_8]
0x140008e93  mov     rsi, [rsp+98h+arg_0]
0x140008e9b  mov     r15d, [rsp+98h+var_64]
0x140008ea0  mov     r14d, [rsp+98h+var_68]
0x140008ea5  mov     r13, [rsp+98h+var_50]
0x140008eaa  jmp     short loc_140008EB9
0x140008eac  mov     r8d, 2
0x140008eb2  lea     r9, WPP_GLOBAL_Control
0x140008eb9  cmp     qword ptr [r13+0], 0
0x140008ebe  jnz     short loc_140008ED0
0x140008ec0  mov     r14d, 0C000009Ah
0x140008ec6  mov     [rsp+98h+var_68], r14d
0x140008ecb  jmp     loc_140008FAA
0x140008ed0  mov     rdx, [rdi+0B8h]
0x140008ed7  mov     word ptr [rdx-48h], 4
0x140008edd  mov     [rdx-40h], r15d
0x140008ee1  mov     eax, [rsi+2ACh]
0x140008ee7  mov     r10, [rsp+98h+var_48]
0x140008eec  mov     ecx, [r10]
0x140008eef  shl     rax, cl
0x140008ef2  mov     [rdx-30h], rax
0x140008ef6  mov     dword ptr [rbx+290h], 103h
0x140008f00  mov     eax, r15d
0x140008f03  mov     ecx, [r10]
0x140008f06  shr     eax, cl
0x140008f08  mov     [rbx+294h], eax
0x140008f0e  mov     [rbx+2B0h], r12d
0x140008f15  mov     eax, [rsi+2ACh]
0x140008f1b  mov     [rbx+2B4h], eax
0x140008f21  mov     rax, [rsp+98h+var_58]
0x140008f26  mov     [rax], r8w
0x140008f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f31  cmp     rcx, r9
0x140008f34  jz      short loc_140008F6A
0x140008f36  test    dword ptr [rcx+2Ch], 20000000h
0x140008f3d  jz      short loc_140008F6A
0x140008f3f  mov     edx, 14h
0x140008f44  mov     eax, [rbx+2B4h]
0x140008f4a  mov     [rsp+98h+var_70], eax
0x140008f4e  mov     dword ptr [rsp+98h+Irp], r15d
0x140008f53  mov     r9d, [rbx+294h]
0x140008f5a  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x140008f61  mov     rcx, [rcx+18h]
0x140008f65  call    WPP_SF_DDD
0x140008f6a  mov     rax, [rdi+0B8h]
0x140008f71  lea     rcx, UdfSeqCacheWriteCompletion
0x140008f78  mov     [rax-10h], rcx
0x140008f7c  mov     [rax-8], rbx
0x140008f80  mov     byte ptr [rax-45h], 0
0x140008f84  mov     byte ptr [rax-45h], 40h ; '@'
0x140008f88  mov     byte ptr [rax-45h], 0C0h
0x140008f8c  mov     byte ptr [rax-45h], 0E0h
0x140008f90  mov     rdx, rdi; Irp
0x140008f93  mov     rcx, [rsi+18h]; DeviceObject
0x140008f97  call    cs:__imp_IofCallDriver
0x140008f9e  nop     dword ptr [rax+rax+00h]
0x140008fa3  xor     edi, edi
0x140008fa5  mov     [rsp+98h+var_60], rdi
0x140008faa  test    rdi, rdi
0x140008fad  jz      short loc_140008FFB
0x140008faf  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140008fb3  test    rcx, rcx
0x140008fb6  jz      short loc_140008FDC
0x140008fb8  call    cs:__imp_MmUnlockPages
0x140008fbf  nop     dword ptr [rax+rax+00h]
0x140008fc4  mov     rcx, [rdi+8]; Mdl
0x140008fc8  call    cs:__imp_IoFreeMdl
0x140008fcf  nop     dword ptr [rax+rax+00h]
0x140008fd4  mov     qword ptr [rdi+8], 0
0x140008fdc  mov     [rbx+290h], r14d
0x140008fe3  mov     eax, [rbx+4]
0x140008fe6  test    al, 40h
0x140008fe8  jz      short loc_140008FFB
0x140008fea  and     eax, 0FFFFFFBFh
0x140008fed  mov     [rbx+4], eax
0x140008ff0  xor     r8d, r8d
0x140008ff3  mov     rdx, rsi
0x140008ff6  call    UdfReleaseDevice
0x140008ffb  add     rsp, 60h
0x140008fff  pop     r15
0x140009001  pop     r14
0x140009003  pop     r13
0x140009005  pop     r12
0x140009007  pop     rdi
0x140009008  pop     rsi
0x140009009  pop     rbx
0x14000900a  retn
0x14001cf29  push    rbx
0x14001cf2b  push    rbp
0x14001cf2c  sub     rsp, 38h
0x14001cf30  mov     rbp, rdx
0x14001cf33  mov     rbx, [rbp+38h]
0x14001cf37  test    rbx, rbx
0x14001cf3a  jz      short loc_14001CF96
0x14001cf3c  cmp     qword ptr [rbx+8], 0
0x14001cf41  jz      short loc_14001CF6B
0x14001cf43  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14001cf47  call    cs:__imp_MmUnlockPages
0x14001cf4e  nop     dword ptr [rax+rax+00h]
0x14001cf53  mov     rcx, [rbx+8]; Mdl
0x14001cf57  call    cs:__imp_IoFreeMdl
0x14001cf5e  nop     dword ptr [rax+rax+00h]
0x14001cf63  mov     qword ptr [rbx+8], 0
0x14001cf6b  mov     eax, [rbp+30h]
0x14001cf6e  mov     rcx, [rbp+0A8h]
0x14001cf75  mov     [rcx+290h], eax
0x14001cf7b  mov     eax, [rcx+4]
0x14001cf7e  test    al, 40h
0x14001cf80  jz      short loc_14001CF96
0x14001cf82  and     dword ptr [rcx+4], 0FFFFFFBFh
0x14001cf86  xor     r8d, r8d
0x14001cf89  mov     rdx, [rbp+0A0h]
0x14001cf90  call    UdfReleaseDevice
0x14001cf95  nop
0x14001cf96  add     rsp, 38h
0x14001cf9a  pop     rbp
0x14001cf9b  pop     rbx
0x14001cf9c  retn
```
