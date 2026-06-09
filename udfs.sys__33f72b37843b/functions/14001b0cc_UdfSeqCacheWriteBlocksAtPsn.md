# UdfSeqCacheWriteBlocksAtPsn

- ea: `0x14001b0cc`
- end: `0x14001b376`
- name: `UdfSeqCacheWriteBlocksAtPsn`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001a478`
- `0x14001b59c`

## callees

- `0x140010990`
- `0x14001b0cc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001b2e5`
- `ntoskrnl!IofCallDriver` at `0x14001b2e5`
- `ntoskrnl!IoAllocateMdl` at `0x14001b204`
- `ntoskrnl!IoAllocateMdl` at `0x14001b204`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001b222`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001b222`
- `ntoskrnl!IoFreeMdl` at `0x14001b23c`
- `ntoskrnl!IoFreeMdl` at `0x14001b34c`
- `ntoskrnl!IoFreeMdl` at `0x14001e045`
- `ntoskrnl!IoFreeMdl` at `0x14001b23c`
- `ntoskrnl!IoFreeMdl` at `0x14001b34c`
- `ntoskrnl!IoFreeMdl` at `0x14001e045`
- `ntoskrnl!MmUnlockPages` at `0x14001b33c`
- `ntoskrnl!MmUnlockPages` at `0x14001e035`
- `ntoskrnl!MmUnlockPages` at `0x14001b33c`
- `ntoskrnl!MmUnlockPages` at `0x14001e035`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b321`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b321`
- `ntoskrnl!KeClearEvent` at `0x14001b128`
- `ntoskrnl!KeClearEvent` at `0x14001b128`
- `ntoskrnl!IoReuseIrp` at `0x14001b1c6`
- `ntoskrnl!IoReuseIrp` at `0x14001b1c6`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheWriteBlocksAtPsn(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        char a6)
{
  int v9; // esi
  __int64 v10; // r10
  int v11; // eax
  ULONG v12; // r12d
  int *v13; // r14
  IRP *Irp; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  struct _IO_STACK_LOCATION *v16; // rax
  struct _MDL *MdlAddress; // rcx
  PVOID Object; // [rsp+70h] [rbp-48h]

  v9 = 0;
  v10 = *(_QWORD *)(a1 + 104);
  v11 = *(_DWORD *)(v10 + 4);
  if ( (v11 & 2) != 0 )
    *(_DWORD *)(v10 + 4) = v11 & 0xFFFFFFFD;
  Object = (PVOID)(a2 + 664);
  KeClearEvent((PRKEVENT)(a2 + 664));
  v12 = a5 << *(_DWORD *)(a1 + 72);
  v13 = (int *)(a2 + 656);
  *(_DWORD *)(a2 + 656) = 259;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_DDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      21,
      WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
      a5,
      v12,
      a4);
  }
  Irp = *(IRP **)(a2 + 648);
  IoReuseIrp(Irp, 0);
  Irp->Tail.Overlay.Thread = KeGetCurrentThread();
  Irp->MdlAddress = 0;
  IoAllocateMdl(a3, v12, 0, 0, Irp);
  if ( Irp->MdlAddress )
    MmProbeAndLockPages(Irp->MdlAddress, 0, IoReadAccess);
  if ( Irp->MdlAddress )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 4;
    CurrentStackLocation[-1].Parameters.Read.Length = v12;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (unsigned __int64)a4 << *(_DWORD *)(a1 + 72);
    v16 = Irp->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)UdfSeqCacheWriteCompletion;
    v16[-1].Context = (PVOID)a2;
    v16[-1].Control = 0;
    v16[-1].Control = 64;
    v16[-1].Control = -64;
    v16[-1].Control = -32;
    IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 24), Irp);
    Irp = 0;
    if ( a6 && *(_DWORD *)(a2 + 656) == 259 )
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
  }
  else
  {
    v9 = -1073741670;
  }
  if ( Irp )
  {
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress )
    {
      MmUnlockPages(MdlAddress);
      IoFreeMdl(Irp->MdlAddress);
      Irp->MdlAddress = 0;
    }
    *v13 = v9;
  }
  return (unsigned int)*v13;
}

```

## disassembly

```asm
0x14001b0cc  mov     rax, rsp
0x14001b0cf  mov     [rax+20h], r9d
0x14001b0d3  mov     [rax+18h], r8
0x14001b0d7  mov     [rax+10h], rdx
0x14001b0db  mov     [rax+8], rcx
0x14001b0df  push    rbx
0x14001b0e0  push    rsi
0x14001b0e1  push    rdi
0x14001b0e2  push    r12
0x14001b0e4  push    r13
0x14001b0e6  push    r14
0x14001b0e8  push    r15
0x14001b0ea  sub     rsp, 80h
0x14001b0f1  mov     edi, r9d
0x14001b0f4  mov     r15, rdx
0x14001b0f7  mov     r13, rcx
0x14001b0fa  xor     ebx, ebx
0x14001b0fc  mov     esi, ebx
0x14001b0fe  mov     [rsp+0B8h+var_88], ebx
0x14001b102  mov     [rax-80h], rbx
0x14001b106  mov     r10, [rcx+68h]
0x14001b10a  mov     eax, [r10+4]
0x14001b10e  test    al, 2
0x14001b110  jz      short loc_14001B119
0x14001b112  and     eax, 0FFFFFFFDh
0x14001b115  mov     [r10+4], eax
0x14001b119  lea     rax, [rdx+298h]
0x14001b120  mov     [rsp+0B8h+Object], rax
0x14001b125  mov     rcx, rax; Event
0x14001b128  call    cs:__imp_KeClearEvent
0x14001b12f  nop     dword ptr [rax+rax+00h]
0x14001b134  lea     rax, [r13+48h]
0x14001b138  mov     [rsp+0B8h+var_58], rax
0x14001b13d  mov     ecx, [rax]
0x14001b13f  mov     r9d, [rsp+0B8h+arg_20]
0x14001b147  mov     r12d, r9d
0x14001b14a  shl     r12d, cl
0x14001b14d  mov     [rsp+0B8h+arg_20], r12d
0x14001b155  lea     r14, [r15+290h]
0x14001b15c  mov     [rsp+0B8h+var_68], r14
0x14001b161  mov     [rsp+0B8h+var_50], r14
0x14001b166  mov     dword ptr [r14], 103h
0x14001b16d  lea     rax, WPP_GLOBAL_Control
0x14001b174  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b17b  cmp     rcx, rax
0x14001b17e  jz      short loc_14001B1A8
0x14001b180  mov     eax, [rcx+2Ch]
0x14001b183  bt      eax, 1Dh
0x14001b187  jnb     short loc_14001B1A8
0x14001b189  mov     edx, 15h
0x14001b18e  mov     [rsp+0B8h+var_90], edi
0x14001b192  mov     dword ptr [rsp+0B8h+Irp], r12d
0x14001b197  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14001b19e  mov     rcx, [rcx+18h]
0x14001b1a2  call    WPP_SF_DDD
0x14001b1a7  nop
0x14001b1a8  mov     rax, [r15+288h]
0x14001b1af  mov     [rsp+0B8h+var_78], rax
0x14001b1b4  mov     [rsp+0B8h+var_60], rax
0x14001b1b9  mov     rdi, rax
0x14001b1bc  mov     [rsp+0B8h+var_80], rax
0x14001b1c1  xor     edx, edx; Iostatus
0x14001b1c3  mov     rcx, rax; Irp
0x14001b1c6  call    cs:__imp_IoReuseIrp
0x14001b1cd  nop     dword ptr [rax+rax+00h]
0x14001b1d2  mov     rax, gs:188h
0x14001b1db  mov     [rdi+98h], rax
0x14001b1e2  lea     rax, [rdi+8]
0x14001b1e6  mov     [rsp+0B8h+var_70], rax
0x14001b1eb  mov     [rax], rbx
0x14001b1ee  mov     [rsp+0B8h+Irp], rdi; Irp
0x14001b1f3  xor     r9d, r9d; ChargeQuota
0x14001b1f6  xor     r8d, r8d; SecondaryBuffer
0x14001b1f9  mov     edx, r12d; Length
0x14001b1fc  mov     rcx, [rsp+0B8h+VirtualAddress]; VirtualAddress
0x14001b204  call    cs:__imp_IoAllocateMdl
0x14001b20b  nop     dword ptr [rax+rax+00h]
0x14001b210  mov     rdx, [rsp+0B8h+var_70]
0x14001b215  mov     rcx, [rdx]; MemoryDescriptorList
0x14001b218  test    rcx, rcx
0x14001b21b  jz      short loc_14001B27A
0x14001b21d  xor     r8d, r8d; Operation
0x14001b220  xor     edx, edx; AccessMode
0x14001b222  call    cs:__imp_MmProbeAndLockPages
0x14001b229  nop     dword ptr [rax+rax+00h]
0x14001b22e  mov     rdx, rdi
0x14001b231  jmp     short loc_14001B27D
0x14001b233  mov     rdi, [rsp+0B8h+var_80]
0x14001b238  mov     rcx, [rdi+8]; Mdl
0x14001b23c  call    cs:__imp_IoFreeMdl
0x14001b243  nop     dword ptr [rax+rax+00h]
0x14001b248  mov     qword ptr [rdi+8], 0
0x14001b250  xor     ebx, ebx
0x14001b252  mov     r15, [rsp+0B8h+arg_8]
0x14001b25a  mov     r13, [rsp+0B8h+arg_0]
0x14001b262  mov     esi, [rsp+0B8h+var_88]
0x14001b266  mov     r12d, [rsp+0B8h+arg_20]
0x14001b26e  mov     r14, [rsp+0B8h+var_68]
0x14001b273  mov     rdx, [rsp+0B8h+var_60]
0x14001b278  jmp     short loc_14001B27D
0x14001b27a  mov     rdx, rdi; Irp
0x14001b27d  mov     rax, [rsp+0B8h+var_70]
0x14001b282  cmp     [rax], rbx
0x14001b285  jnz     short loc_14001B295
0x14001b287  mov     esi, 0C000009Ah
0x14001b28c  mov     [rsp+0B8h+var_88], esi
0x14001b290  jmp     loc_14001B32E
0x14001b295  mov     r8, [rdx+0B8h]
0x14001b29c  mov     word ptr [r8-48h], 4
0x14001b2a3  mov     [r8-40h], r12d
0x14001b2a7  mov     eax, [rsp+0B8h+arg_18]
0x14001b2ae  mov     rcx, [rsp+0B8h+var_58]
0x14001b2b3  mov     ecx, [rcx]
0x14001b2b5  shl     rax, cl
0x14001b2b8  mov     [r8-30h], rax
0x14001b2bc  mov     rax, [rdx+0B8h]
0x14001b2c3  lea     rcx, UdfSeqCacheWriteCompletion
0x14001b2ca  mov     [rax-10h], rcx
0x14001b2ce  mov     [rax-8], r15
0x14001b2d2  mov     [rax-45h], bl
0x14001b2d5  mov     byte ptr [rax-45h], 40h ; '@'
0x14001b2d9  mov     byte ptr [rax-45h], 0C0h
0x14001b2dd  mov     byte ptr [rax-45h], 0E0h
0x14001b2e1  mov     rcx, [r13+18h]; DeviceObject
0x14001b2e5  call    cs:__imp_IofCallDriver
0x14001b2ec  nop     dword ptr [rax+rax+00h]
0x14001b2f1  mov     rdi, rbx
0x14001b2f4  mov     [rsp+0B8h+var_80], rbx
0x14001b2f9  cmp     [rsp+0B8h+arg_28], bl
0x14001b300  jz      short loc_14001B32E
0x14001b302  mov     rax, [rsp+0B8h+var_50]
0x14001b307  cmp     dword ptr [rax], 103h
0x14001b30d  jnz     short loc_14001B32E
0x14001b30f  mov     [rsp+0B8h+Irp], rbx; Timeout
0x14001b314  xor     r9d, r9d; Alertable
0x14001b317  xor     r8d, r8d; WaitMode
0x14001b31a  xor     edx, edx; WaitReason
0x14001b31c  mov     rcx, [rsp+0B8h+Object]; Object
0x14001b321  call    cs:__imp_KeWaitForSingleObject
0x14001b328  nop     dword ptr [rax+rax+00h]
0x14001b32d  nop
0x14001b32e  test    rdi, rdi
0x14001b331  jz      short loc_14001B35F
0x14001b333  mov     rcx, [rdi+8]; MemoryDescriptorList
0x14001b337  test    rcx, rcx
0x14001b33a  jz      short loc_14001B35C
0x14001b33c  call    cs:__imp_MmUnlockPages
0x14001b343  nop     dword ptr [rax+rax+00h]
0x14001b348  mov     rcx, [rdi+8]; Mdl
0x14001b34c  call    cs:__imp_IoFreeMdl
0x14001b353  nop     dword ptr [rax+rax+00h]
0x14001b358  mov     [rdi+8], rbx
0x14001b35c  mov     [r14], esi
0x14001b35f  mov     eax, [r14]
0x14001b362  add     rsp, 80h
0x14001b369  pop     r15
0x14001b36b  pop     r14
0x14001b36d  pop     r13
0x14001b36f  pop     r12
0x14001b371  pop     rdi
0x14001b372  pop     rsi
0x14001b373  pop     rbx
0x14001b374  retn
0x14001e017  push    rbx
0x14001e019  push    rbp
0x14001e01a  sub     rsp, 38h
0x14001e01e  mov     rbp, rdx
0x14001e021  mov     rbx, [rbp+38h]
0x14001e025  test    rbx, rbx
0x14001e028  jz      short loc_14001E069
0x14001e02a  cmp     qword ptr [rbx+8], 0
0x14001e02f  jz      short loc_14001E059
0x14001e031  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14001e035  call    cs:__imp_MmUnlockPages
0x14001e03c  nop     dword ptr [rax+rax+00h]
0x14001e041  mov     rcx, [rbx+8]; Mdl
0x14001e045  call    cs:__imp_IoFreeMdl
0x14001e04c  nop     dword ptr [rax+rax+00h]
0x14001e051  mov     qword ptr [rbx+8], 0
0x14001e059  mov     ecx, [rbp+30h]
0x14001e05c  mov     rax, [rbp+0C8h]
0x14001e063  mov     [rax+290h], ecx
0x14001e069  add     rsp, 38h
0x14001e06d  pop     rbp
0x14001e06e  pop     rbx
0x14001e06f  retn
```
