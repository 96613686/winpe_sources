# VhdmpiAsyncOpThread(void *)

- ea: `0x1400e64c0`
- end: `0x1400e660a`
- name: `?VhdmpiAsyncOpThread@@YAXPEAX@Z`
- size: `330`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140022750`
- `0x140029498`
- `0x140033d50`
- `0x14005dc30`
- `0x14009f364`
- `0x1400e64c0`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400e65f4`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400e65f4`
- `ntoskrnl!IofCompleteRequest` at `0x1400e65ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400e65ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e64e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e64e8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400e65b3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400e65b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e65e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e65e6`
- `ntoskrnl!KeSetEvent` at `0x1400e6590`
- `ntoskrnl!KeSetEvent` at `0x1400e6590`

## pseudocode

```c
void __fastcall VhdmpiAsyncOpThread(struct _EX_RUNDOWN_REF **StartContext)
{
  struct _EX_RUNDOWN_REF *v1; // rbp
  ULONG_PTR Count; // rdi
  __int64 v4; // rbx
  __int64 i; // rbx
  void (__fastcall *v6)(ULONG_PTR); // rax
  IRP *v7; // rbx

  v1 = *StartContext;
  Count = (*StartContext)[15].Count;
  KeWaitForSingleObject(StartContext + 2, Executive, 0, 0, 0);
  if ( *((_BYTE *)StartContext + 40) )
  {
    ((void (__fastcall *)(struct _EX_RUNDOWN_REF *, ULONG_PTR))StartContext[1][5].Count)(v1, Count);
    v4 = *(_QWORD *)(Count + 136);
    if ( v4 )
    {
      for ( i = *(_QWORD *)(v4 + 144); i; i = *(_QWORD *)(i + 1144) )
      {
        if ( *(_DWORD *)(i + 672) == 3
          && *(_BYTE *)(i + 8)
          && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)i + 120LL))(i) )
        {
          VhdmpiLockAndTryTruncateBackingStoreFile(i);
        }
      }
    }
    if ( *(_BYTE *)(Count + 8) )
    {
      v6 = *(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)Count + 32LL);
      if ( v6 )
        v6(Count);
    }
    v7 = (IRP *)VhdmpiDequeueControlDeviceIoctl(v1, LODWORD(StartContext[1]->Count));
    KeSetEvent((PRKEVENT)(Count + 24), 0, 0);
    if ( v7 )
    {
      VhdmpiDisconnectAsyncOp((struct _VHD_ASYNC_OP_CONTEXT *)Count, *(_DWORD *)(Count + 12));
      ExReleaseRundownProtection(v1 + 33);
      v7->IoStatus.Status = *(_DWORD *)(Count + 12);
      IofCompleteRequest(v7, 0);
      VhdmpiFreeAsyncContext((PVOID)Count);
    }
  }
  ExFreePoolWithTag(StartContext, 0x71444856u);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400e64c0  push    rbx
0x1400e64c2  push    rbp
0x1400e64c3  push    rsi
0x1400e64c4  push    rdi
0x1400e64c5  sub     rsp, 38h
0x1400e64c9  mov     rbp, [rcx]
0x1400e64cc  mov     rsi, rcx
0x1400e64cf  add     rcx, 10h; Object
0x1400e64d3  mov     [rsp+58h+Timeout], 0; Timeout
0x1400e64dc  xor     r9d, r9d; Alertable
0x1400e64df  xor     r8d, r8d; WaitMode
0x1400e64e2  xor     edx, edx; WaitReason
0x1400e64e4  mov     rdi, [rbp+78h]
0x1400e64e8  call    cs:__imp_KeWaitForSingleObject
0x1400e64ef  nop     dword ptr [rax+rax+00h]
0x1400e64f4  cmp     byte ptr [rsi+28h], 0
0x1400e64f8  jz      loc_1400E65DE
0x1400e64fe  mov     rax, [rsi+8]
0x1400e6502  mov     rdx, rdi
0x1400e6505  mov     rcx, rbp
0x1400e6508  mov     rax, [rax+28h]
0x1400e650c  call    _guard_dispatch_icall
0x1400e6511  mov     rbx, [rdi+88h]
0x1400e6518  test    rbx, rbx
0x1400e651b  jz      short loc_1400E655C
0x1400e651d  mov     rbx, [rbx+90h]
0x1400e6524  jmp     short loc_1400E6557
0x1400e6526  cmp     dword ptr [rbx+2A0h], 3
0x1400e652d  jnz     short loc_1400E6550
0x1400e652f  cmp     byte ptr [rbx+8], 0
0x1400e6533  jz      short loc_1400E6550
0x1400e6535  mov     rax, [rbx]
0x1400e6538  mov     rcx, rbx
0x1400e653b  mov     rax, [rax+78h]
0x1400e653f  call    _guard_dispatch_icall
0x1400e6544  test    al, al
0x1400e6546  jnz     short loc_1400E6550
0x1400e6548  mov     rcx, rbx; char
0x1400e654b  call    VhdmpiLockAndTryTruncateBackingStoreFile
0x1400e6550  mov     rbx, [rbx+478h]
0x1400e6557  test    rbx, rbx
0x1400e655a  jnz     short loc_1400E6526
0x1400e655c  cmp     byte ptr [rdi+8], 0
0x1400e6560  jz      short loc_1400E6576
0x1400e6562  mov     rax, [rdi]
0x1400e6565  mov     rax, [rax+20h]
0x1400e6569  test    rax, rax
0x1400e656c  jz      short loc_1400E6576
0x1400e656e  mov     rcx, rdi
0x1400e6571  call    _guard_dispatch_icall
0x1400e6576  mov     rdx, [rsi+8]
0x1400e657a  mov     rcx, rbp
0x1400e657d  mov     edx, [rdx]
0x1400e657f  call    VhdmpiDequeueControlDeviceIoctl
0x1400e6584  lea     rcx, [rdi+18h]; Event
0x1400e6588  xor     r8d, r8d; Wait
0x1400e658b  xor     edx, edx; Increment
0x1400e658d  mov     rbx, rax
0x1400e6590  call    cs:__imp_KeSetEvent
0x1400e6597  nop     dword ptr [rax+rax+00h]
0x1400e659c  test    rbx, rbx
0x1400e659f  jz      short loc_1400E65DE
0x1400e65a1  mov     edx, [rdi+0Ch]; int
0x1400e65a4  mov     rcx, rdi; struct _VHD_ASYNC_OP_CONTEXT *
0x1400e65a7  call    ?VhdmpiDisconnectAsyncOp@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@J@Z; VhdmpiDisconnectAsyncOp(_VHD_ASYNC_OP_CONTEXT *,long)
0x1400e65ac  lea     rcx, [rbp+108h]; RunRef
0x1400e65b3  call    cs:__imp_ExReleaseRundownProtection
0x1400e65ba  nop     dword ptr [rax+rax+00h]
0x1400e65bf  mov     edx, [rdi+0Ch]
0x1400e65c2  mov     rcx, rbx; Irp
0x1400e65c5  mov     [rbx+30h], edx
0x1400e65c8  xor     edx, edx; PriorityBoost
0x1400e65ca  call    cs:__imp_IofCompleteRequest
0x1400e65d1  nop     dword ptr [rax+rax+00h]
0x1400e65d6  mov     rcx, rdi; P
0x1400e65d9  call    ?VhdmpiFreeAsyncContext@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiFreeAsyncContext(_VHD_ASYNC_OP_CONTEXT *)
0x1400e65de  mov     edx, 71444856h; Tag
0x1400e65e3  mov     rcx, rsi; P
0x1400e65e6  call    cs:__imp_ExFreePoolWithTag
0x1400e65ed  nop     dword ptr [rax+rax+00h]
0x1400e65f2  xor     ecx, ecx; ExitStatus
0x1400e65f4  call    cs:__imp_PsTerminateSystemThread
0x1400e65fb  nop     dword ptr [rax+rax+00h]
0x1400e6600  add     rsp, 38h
0x1400e6604  pop     rdi
0x1400e6605  pop     rsi
0x1400e6606  pop     rbp
0x1400e6607  pop     rbx
0x1400e6608  retn
```
