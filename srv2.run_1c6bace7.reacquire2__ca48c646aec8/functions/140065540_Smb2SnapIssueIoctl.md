# Smb2SnapIssueIoctl

- ea: `0x140065540`
- end: `0x140065652`
- name: `Smb2SnapIssueIoctl`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140064c68`
- `0x140064f90`
- `0x14006507c`
- `0x140065384`

## callees

- `0x1400604e8`
- `0x140065540`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140065622`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065622`
- `ntoskrnl!IoQueueThreadIrp` at `0x1400655e3`
- `ntoskrnl!IoQueueThreadIrp` at `0x1400655e3`
- `ntoskrnl!IofCallDriver` at `0x1400655f6`
- `ntoskrnl!IofCallDriver` at `0x1400655f6`
- `ntoskrnl!KeInitializeEvent` at `0x14006557c`
- `ntoskrnl!KeInitializeEvent` at `0x14006557c`

## pseudocode

```c
__int64 __fastcall Smb2SnapIssueIoctl(HANDLE Handle, DWORD a2, struct _IRP *a3, ULONG *a4)
{
  IRP *v8; // rax
  IRP *v9; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  NTSTATUS v12; // eax
  unsigned int v13; // ecx
  PDEVICE_OBJECT DeviceObject; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+38h] [rbp-28h]
  struct _KEVENT Event; // [rsp+48h] [rbp-18h] BYREF

  DeviceObject = 0;
  v15 = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v8 = (IRP *)Srv2BuildCoreOfSyncIoRequest(Handle, (__int64)&DeviceObject);
  v9 = v8;
  if ( !v8 )
    return 3221225626LL;
  CurrentStackLocation = v8->Tail.Overlay.CurrentStackLocation;
  v8->Flags |= 0x10u;
  v8->AssociatedIrp.MasterIrp = a3;
  *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 14;
  CurrentStackLocation[-1].Parameters.Read.Length = *a4;
  CurrentStackLocation[-1].Parameters.Create.Options = 0;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = a2;
  CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
  IoQueueThreadIrp(v8);
  v12 = IofCallDriver(DeviceObject, v9);
  v13 = v12;
  if ( v12 == 259 )
  {
    KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
LABEL_6:
    v13 = v15;
    goto LABEL_7;
  }
  if ( v12 >= 0 )
    goto LABEL_6;
LABEL_7:
  if ( v13 == -2147483643 )
    *a4 = DWORD2(v15);
  return v13;
}

```

## disassembly

```asm
0x140065540  push    rbp
0x140065542  push    rbx
0x140065543  push    rsi
0x140065544  push    rdi
0x140065545  push    r14
0x140065547  mov     rbp, rsp
0x14006554a  sub     rsp, 60h
0x14006554e  xor     eax, eax
0x140065550  mov     rsi, r8
0x140065553  mov     r14d, edx
0x140065556  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14006555a  mov     rbx, rcx
0x14006555d  mov     [rbp+DeviceObject], rax
0x140065561  xorps   xmm0, xmm0
0x140065564  lea     rcx, [rbp+Event]; Event
0x140065568  xorps   xmm1, xmm1
0x14006556b  lea     edx, [rax+1]; Type
0x14006556e  xor     r8d, r8d; State
0x140065571  mov     rdi, r9
0x140065574  movups  [rbp+var_28], xmm0
0x140065578  movups  xmmword ptr [rbp+Event.Header], xmm1
0x14006557c  call    cs:__imp_KeInitializeEvent
0x140065583  nop     dword ptr [rax+rax+00h]
0x140065588  lea     rax, [rbp+DeviceObject]
0x14006558c  mov     rcx, rbx; Handle
0x14006558f  lea     r9, [rbp+var_28]
0x140065593  mov     [rsp+60h+Timeout], rax; __int64
0x140065598  lea     r8, [rbp+Event]
0x14006559c  call    Srv2BuildCoreOfSyncIoRequest
0x1400655a1  mov     rbx, rax
0x1400655a4  test    rax, rax
0x1400655a7  jnz     short loc_1400655B3
0x1400655a9  mov     eax, 0C000009Ah
0x1400655ae  jmp     loc_140065646
0x1400655b3  mov     rcx, [rax+0B8h]
0x1400655ba  or      dword ptr [rax+10h], 10h
0x1400655be  mov     [rax+18h], rsi
0x1400655c2  mov     word ptr [rcx-48h], 0Eh
0x1400655c8  mov     eax, [rdi]
0x1400655ca  mov     [rcx-40h], eax
0x1400655cd  mov     dword ptr [rcx-38h], 0
0x1400655d4  mov     [rcx-30h], r14d
0x1400655d8  mov     qword ptr [rcx-28h], 0
0x1400655e0  mov     rcx, rbx; Irp
0x1400655e3  call    cs:__imp_IoQueueThreadIrp
0x1400655ea  nop     dword ptr [rax+rax+00h]
0x1400655ef  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400655f3  mov     rdx, rbx; Irp
0x1400655f6  call    cs:__imp_IofCallDriver
0x1400655fd  nop     dword ptr [rax+rax+00h]
0x140065602  mov     ecx, eax
0x140065604  cmp     eax, 103h
0x140065609  jnz     short loc_140065630
0x14006560b  xor     r9d, r9d; Alertable
0x14006560e  mov     [rsp+60h+Timeout], 0; Timeout
0x140065617  xor     r8d, r8d; WaitMode
0x14006561a  lea     rcx, [rbp+Event]; Object
0x14006561e  lea     edx, [r9+6]; WaitReason
0x140065622  call    cs:__imp_KeWaitForSingleObject
0x140065629  nop     dword ptr [rax+rax+00h]
0x14006562e  jmp     short loc_140065634
0x140065630  test    eax, eax
0x140065632  js      short loc_140065637
0x140065634  mov     ecx, dword ptr [rbp+var_28]
0x140065637  cmp     ecx, 80000005h
0x14006563d  jnz     short loc_140065644
0x14006563f  mov     eax, dword ptr [rbp+var_28+8]
0x140065642  mov     [rdi], eax
0x140065644  mov     eax, ecx
0x140065646  add     rsp, 60h
0x14006564a  pop     r14
0x14006564c  pop     rdi
0x14006564d  pop     rsi
0x14006564e  pop     rbx
0x14006564f  pop     rbp
0x140065650  retn
```
