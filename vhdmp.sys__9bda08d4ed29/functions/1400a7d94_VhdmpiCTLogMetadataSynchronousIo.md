# VhdmpiCTLogMetadataSynchronousIo

- ea: `0x1400a7d94`
- end: `0x1400a7fcf`
- name: `VhdmpiCTLogMetadataSynchronousIo`
- size: `571`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a7fd8`
- `0x1400a8018`

## callees

- `0x140023980`
- `0x14002a604`
- `0x140036284`
- `0x1400a7d94`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400a7e92`
- `ntoskrnl!IofCallDriver` at `0x1400a7e92`
- `ntoskrnl!IoFreeIrp` at `0x1400a7f30`
- `ntoskrnl!IoFreeIrp` at `0x1400a7f30`
- `ntoskrnl!IoFreeMdl` at `0x1400a7f11`
- `ntoskrnl!IoFreeMdl` at `0x1400a7f11`
- `ntoskrnl!IoAllocateMdl` at `0x1400a7dfa`
- `ntoskrnl!IoAllocateMdl` at `0x1400a7dfa`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a7e26`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a7e26`
- `ntoskrnl!MmUnlockPages` at `0x1400a7f02`
- `ntoskrnl!MmUnlockPages` at `0x1400a7f02`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a7ebd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a7ebd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400a7f50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400a7f50`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7dda`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7dda`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogMetadataSynchronousIo(
        char a1,
        struct _NPAGED_LOOKASIDE_LIST *a2,
        void *a3,
        ULONG a4,
        __int64 a5,
        _OWORD *a6)
{
  char v10; // r12
  PMDL Mdl; // rax
  struct _MDL *v12; // r14
  int v13; // ebx
  __int64 v14; // rdx
  _QWORD *v15; // rsi
  _QWORD *v16; // rsi
  IRP *v17; // rcx
  unsigned int v18; // edx
  unsigned __int8 v19; // r8
  PVOID Entry[2]; // [rsp+58h] [rbp-60h] BYREF
  struct _KEVENT Object[3]; // [rsp+68h] [rbp-50h] BYREF

  memset(Object, 0, 24);
  v10 = 0;
  Entry[0] = 0;
  KeInitializeEvent(Object, NotificationEvent, 0);
  Mdl = IoAllocateMdl(a3, a4, 0, 1u, 0);
  v12 = Mdl;
  Entry[1] = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
    v10 = 1;
    v13 = VhdmpiCTLogAllocateAndInitializeIrp(
            (__int64)a2,
            v14,
            a1,
            a5,
            a4,
            (__int64)VhdmpiCTLogSetKEventIoCompletionWithContext,
            (__int64)v12,
            0,
            (__int64)Object,
            Entry);
    if ( v13 >= 0 )
    {
      v15 = Entry[0];
      v13 = IofCallDriver(*((PDEVICE_OBJECT *)Entry[0] + 4), *((PIRP *)Entry[0] + 2));
      if ( v13 == 259 )
        v13 = KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      *a6 = *(_OWORD *)(v15[2] + 48LL);
    }
  }
  else
  {
    v13 = -1073741670;
  }
  if ( v12 )
  {
    if ( v10 )
      MmUnlockPages(v12);
    IoFreeMdl(v12);
  }
  v16 = Entry[0];
  if ( Entry[0] )
  {
    v17 = (IRP *)*((_QWORD *)Entry[0] + 2);
    if ( v17 )
    {
      IoFreeIrp(v17);
      v16[2] = 0;
    }
    ExFreeToNPagedLookasideList(a2 + 33, Entry[0]);
  }
  if ( v13 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents(
      "VhdmpiCTLogMetadataSynchronousIo",
      0xE2u,
      v19,
      v18,
      "VhdmpiCTLogMetadataSynchronousIo Failed (0x%08x). (VirtualDisk = %p) (BackingStore = %p)",
      v13,
      a2->L.ListEntry.Blink,
      a2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400a7d94  mov     r11, rsp
0x1400a7d97  mov     [r11+10h], rdx
0x1400a7d9b  push    rbx
0x1400a7d9c  push    rsi
0x1400a7d9d  push    r12
0x1400a7d9f  push    r13
0x1400a7da1  push    r14
0x1400a7da3  push    r15
0x1400a7da5  sub     rsp, 88h
0x1400a7dac  mov     esi, r9d
0x1400a7daf  mov     rbx, r8
0x1400a7db2  mov     r15, rdx
0x1400a7db5  mov     r13b, cl
0x1400a7db8  xorps   xmm0, xmm0
0x1400a7dbb  xor     eax, eax
0x1400a7dbd  movups  [rsp+0B8h+Object], xmm0
0x1400a7dc2  mov     [r11-40h], rax
0x1400a7dc6  xor     r12b, r12b
0x1400a7dc9  mov     [r11-68h], r12b
0x1400a7dcd  mov     [r11-60h], rax
0x1400a7dd1  xor     r8d, r8d; State
0x1400a7dd4  xor     edx, edx; Type
0x1400a7dd6  lea     rcx, [r11-50h]; Event
0x1400a7dda  call    cs:__imp_KeInitializeEvent
0x1400a7de1  nop     dword ptr [rax+rax+00h]
0x1400a7de6  mov     [rsp+0B8h+Irp], 0; Irp
0x1400a7def  mov     r9b, 1; ChargeQuota
0x1400a7df2  xor     r8d, r8d; SecondaryBuffer
0x1400a7df5  mov     edx, esi; Length
0x1400a7df7  mov     rcx, rbx; VirtualAddress
0x1400a7dfa  call    cs:__imp_IoAllocateMdl
0x1400a7e01  nop     dword ptr [rax+rax+00h]
0x1400a7e06  mov     r14, rax
0x1400a7e09  mov     [rsp+0B8h+var_58], rax
0x1400a7e0e  test    rax, rax
0x1400a7e11  jnz     short loc_1400A7E1D
0x1400a7e13  mov     ebx, 0C000009Ah
0x1400a7e18  jmp     loc_1400A7EF5
0x1400a7e1d  xor     edx, edx; AccessMode
0x1400a7e1f  lea     r8d, [rdx+1]; Operation
0x1400a7e23  mov     rcx, r14; MemoryDescriptorList
0x1400a7e26  call    cs:__imp_MmProbeAndLockPages
0x1400a7e2d  nop     dword ptr [rax+rax+00h]
0x1400a7e32  mov     r12b, 1
0x1400a7e35  mov     [rsp+0B8h+var_68], r12b
0x1400a7e3a  lea     rax, [rsp+0B8h+Entry]
0x1400a7e3f  mov     [rsp+0B8h+var_70], rax
0x1400a7e44  lea     rax, [rsp+0B8h+Object]
0x1400a7e49  mov     [rsp+0B8h+var_78], rax
0x1400a7e4e  mov     [rsp+0B8h+var_80], 0
0x1400a7e57  mov     [rsp+0B8h+var_88], r14
0x1400a7e5c  lea     rax, VhdmpiCTLogSetKEventIoCompletionWithContext
0x1400a7e63  mov     qword ptr [rsp+0B8h+var_90], rax
0x1400a7e68  mov     dword ptr [rsp+0B8h+Irp], esi
0x1400a7e6c  mov     r9, [rsp+0B8h+arg_20]
0x1400a7e74  mov     r8b, r13b
0x1400a7e77  mov     rcx, r15
0x1400a7e7a  call    VhdmpiCTLogAllocateAndInitializeIrp
0x1400a7e7f  mov     ebx, eax
0x1400a7e81  test    eax, eax
0x1400a7e83  js      short loc_1400A7EF5
0x1400a7e85  mov     rsi, [rsp+0B8h+Entry]
0x1400a7e8a  mov     rdx, [rsi+10h]; Irp
0x1400a7e8e  mov     rcx, [rsi+20h]; DeviceObject
0x1400a7e92  call    cs:__imp_IofCallDriver
0x1400a7e99  nop     dword ptr [rax+rax+00h]
0x1400a7e9e  mov     ebx, eax
0x1400a7ea0  cmp     eax, 103h
0x1400a7ea5  jnz     short loc_1400A7ECB
0x1400a7ea7  mov     [rsp+0B8h+Irp], 0; Timeout
0x1400a7eb0  xor     r9d, r9d; Alertable
0x1400a7eb3  xor     r8d, r8d; WaitMode
0x1400a7eb6  xor     edx, edx; WaitReason
0x1400a7eb8  lea     rcx, [rsp+0B8h+Object]; Object
0x1400a7ebd  call    cs:__imp_KeWaitForSingleObject
0x1400a7ec4  nop     dword ptr [rax+rax+00h]
0x1400a7ec9  mov     ebx, eax
0x1400a7ecb  mov     rax, [rsi+10h]
0x1400a7ecf  movups  xmm0, xmmword ptr [rax+30h]
0x1400a7ed3  mov     rax, [rsp+0B8h+arg_28]
0x1400a7edb  movdqu  xmmword ptr [rax], xmm0
0x1400a7edf  jmp     short loc_1400A7EF5
0x1400a7ee1  mov     ebx, eax
0x1400a7ee3  mov     r15, [rsp+0B8h+arg_8]
0x1400a7eeb  mov     r14, [rsp+0B8h+var_58]
0x1400a7ef0  mov     r12b, [rsp+0B8h+var_68]
0x1400a7ef5  test    r14, r14
0x1400a7ef8  jz      short loc_1400A7F1D
0x1400a7efa  test    r12b, r12b
0x1400a7efd  jz      short loc_1400A7F0E
0x1400a7eff  mov     rcx, r14; MemoryDescriptorList
0x1400a7f02  call    cs:__imp_MmUnlockPages
0x1400a7f09  nop     dword ptr [rax+rax+00h]
0x1400a7f0e  mov     rcx, r14; Mdl
0x1400a7f11  call    cs:__imp_IoFreeMdl
0x1400a7f18  nop     dword ptr [rax+rax+00h]
0x1400a7f1d  mov     rsi, [rsp+0B8h+Entry]
0x1400a7f22  test    rsi, rsi
0x1400a7f25  jz      short loc_1400A7F5C
0x1400a7f27  mov     rcx, [rsi+10h]; Irp
0x1400a7f2b  test    rcx, rcx
0x1400a7f2e  jz      short loc_1400A7F44
0x1400a7f30  call    cs:__imp_IoFreeIrp
0x1400a7f37  nop     dword ptr [rax+rax+00h]
0x1400a7f3c  mov     qword ptr [rsi+10h], 0
0x1400a7f44  lea     rcx, [r15+1080h]; Lookaside
0x1400a7f4b  mov     rdx, [rsp+0B8h+Entry]; Entry
0x1400a7f50  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400a7f57  nop     dword ptr [rax+rax+00h]
0x1400a7f5c  test    ebx, ebx
0x1400a7f5e  jns     short loc_1400A7FBA
0x1400a7f60  mov     eax, cs:dword_1400876D0
0x1400a7f66  mov     r8d, 2
0x1400a7f6c  cmp     eax, r8d
0x1400a7f6f  jbe     short loc_1400A7FBA
0x1400a7f71  mov     edx, 1000h
0x1400a7f76  lea     rcx, dword_1400876D0
0x1400a7f7d  call    _tlgKeywordOn
0x1400a7f82  test    al, al
0x1400a7f84  jz      short loc_1400A7FBA
0x1400a7f86  mov     ecx, 0E2h
0x1400a7f8b  mov     [rsp+0B8h+var_80], r15
0x1400a7f90  mov     rax, [r15+48h]
0x1400a7f94  mov     [rsp+0B8h+var_88], rax
0x1400a7f99  mov     dword ptr [rsp+0B8h+var_90], ebx; char
0x1400a7f9d  lea     rax, aVhdmpictlogmet; "VhdmpiCTLogMetadataSynchronousIo Failed"...
0x1400a7fa4  mov     [rsp+0B8h+Irp], rax; char *
0x1400a7fa9  mov     r9d, edx; int
0x1400a7fac  mov     edx, ecx; int
0x1400a7fae  lea     rcx, aVhdmpictlogmet_0; "VhdmpiCTLogMetadataSynchronousIo"
0x1400a7fb5  call    TraceEvents
0x1400a7fba  mov     eax, ebx
0x1400a7fbc  add     rsp, 88h
0x1400a7fc3  pop     r15
0x1400a7fc5  pop     r14
0x1400a7fc7  pop     r13
0x1400a7fc9  pop     r12
0x1400a7fcb  pop     rsi
0x1400a7fcc  pop     rbx
0x1400a7fcd  retn
```
