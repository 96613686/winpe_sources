# VhdmpiAsyncOpThread(void *)

- ea: `0x1400e6530`
- end: `0x1400e667a`
- name: `?VhdmpiAsyncOpThread@@YAXPEAX@Z`
- size: `330`
- prototype: `void __fastcall(struct _EX_RUNDOWN_REF **StartContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140022330`
- `0x140028f78`
- `0x140033890`
- `0x14005d840`
- `0x14009f364`
- `0x1400e6530`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400e6664`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400e6664`
- `ntoskrnl!IofCompleteRequest` at `0x1400e663a`
- `ntoskrnl!IofCompleteRequest` at `0x1400e663a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6558`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6558`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400e6623`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400e6623`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6656`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6656`
- `ntoskrnl!KeSetEvent` at `0x1400e6600`
- `ntoskrnl!KeSetEvent` at `0x1400e6600`

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
0x1400e6530  push    rbx
0x1400e6532  push    rbp
0x1400e6533  push    rsi
0x1400e6534  push    rdi
0x1400e6535  sub     rsp, 38h
0x1400e6539  mov     rbp, [rcx]
0x1400e653c  mov     rsi, rcx
0x1400e653f  add     rcx, 10h; Object
0x1400e6543  mov     [rsp+58h+Timeout], 0; Timeout
0x1400e654c  xor     r9d, r9d; Alertable
0x1400e654f  xor     r8d, r8d; WaitMode
0x1400e6552  xor     edx, edx; WaitReason
0x1400e6554  mov     rdi, [rbp+78h]
0x1400e6558  call    cs:__imp_KeWaitForSingleObject
0x1400e655f  nop     dword ptr [rax+rax+00h]
0x1400e6564  cmp     byte ptr [rsi+28h], 0
0x1400e6568  jz      loc_1400E664E
0x1400e656e  mov     rax, [rsi+8]
0x1400e6572  mov     rdx, rdi
0x1400e6575  mov     rcx, rbp
0x1400e6578  mov     rax, [rax+28h]
0x1400e657c  call    _guard_dispatch_icall
0x1400e6581  mov     rbx, [rdi+88h]
0x1400e6588  test    rbx, rbx
0x1400e658b  jz      short loc_1400E65CC
0x1400e658d  mov     rbx, [rbx+90h]
0x1400e6594  jmp     short loc_1400E65C7
0x1400e6596  cmp     dword ptr [rbx+2A0h], 3
0x1400e659d  jnz     short loc_1400E65C0
0x1400e659f  cmp     byte ptr [rbx+8], 0
0x1400e65a3  jz      short loc_1400E65C0
0x1400e65a5  mov     rax, [rbx]
0x1400e65a8  mov     rcx, rbx
0x1400e65ab  mov     rax, [rax+78h]
0x1400e65af  call    _guard_dispatch_icall
0x1400e65b4  test    al, al
0x1400e65b6  jnz     short loc_1400E65C0
0x1400e65b8  mov     rcx, rbx; char
0x1400e65bb  call    VhdmpiLockAndTryTruncateBackingStoreFile
0x1400e65c0  mov     rbx, [rbx+478h]
0x1400e65c7  test    rbx, rbx
0x1400e65ca  jnz     short loc_1400E6596
0x1400e65cc  cmp     byte ptr [rdi+8], 0
0x1400e65d0  jz      short loc_1400E65E6
0x1400e65d2  mov     rax, [rdi]
0x1400e65d5  mov     rax, [rax+20h]
0x1400e65d9  test    rax, rax
0x1400e65dc  jz      short loc_1400E65E6
0x1400e65de  mov     rcx, rdi
0x1400e65e1  call    _guard_dispatch_icall
0x1400e65e6  mov     rdx, [rsi+8]
0x1400e65ea  mov     rcx, rbp
0x1400e65ed  mov     edx, [rdx]
0x1400e65ef  call    VhdmpiDequeueControlDeviceIoctl
0x1400e65f4  lea     rcx, [rdi+18h]; Event
0x1400e65f8  xor     r8d, r8d; Wait
0x1400e65fb  xor     edx, edx; Increment
0x1400e65fd  mov     rbx, rax
0x1400e6600  call    cs:__imp_KeSetEvent
0x1400e6607  nop     dword ptr [rax+rax+00h]
0x1400e660c  test    rbx, rbx
0x1400e660f  jz      short loc_1400E664E
0x1400e6611  mov     edx, [rdi+0Ch]; int
0x1400e6614  mov     rcx, rdi; struct _VHD_ASYNC_OP_CONTEXT *
0x1400e6617  call    ?VhdmpiDisconnectAsyncOp@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@J@Z; VhdmpiDisconnectAsyncOp(_VHD_ASYNC_OP_CONTEXT *,long)
0x1400e661c  lea     rcx, [rbp+108h]; RunRef
0x1400e6623  call    cs:__imp_ExReleaseRundownProtection
0x1400e662a  nop     dword ptr [rax+rax+00h]
0x1400e662f  mov     edx, [rdi+0Ch]
0x1400e6632  mov     rcx, rbx; Irp
0x1400e6635  mov     [rbx+30h], edx
0x1400e6638  xor     edx, edx; PriorityBoost
0x1400e663a  call    cs:__imp_IofCompleteRequest
0x1400e6641  nop     dword ptr [rax+rax+00h]
0x1400e6646  mov     rcx, rdi; P
0x1400e6649  call    ?VhdmpiFreeAsyncContext@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiFreeAsyncContext(_VHD_ASYNC_OP_CONTEXT *)
0x1400e664e  mov     edx, 71444856h; Tag
0x1400e6653  mov     rcx, rsi; P
0x1400e6656  call    cs:__imp_ExFreePoolWithTag
0x1400e665d  nop     dword ptr [rax+rax+00h]
0x1400e6662  xor     ecx, ecx; ExitStatus
0x1400e6664  call    cs:__imp_PsTerminateSystemThread
0x1400e666b  nop     dword ptr [rax+rax+00h]
0x1400e6670  add     rsp, 38h
0x1400e6674  pop     rdi
0x1400e6675  pop     rsi
0x1400e6676  pop     rbp
0x1400e6677  pop     rbx
0x1400e6678  retn
```
