# Smb2SnapIssueIoctl

- ea: `0x1400654f0`
- end: `0x140065602`
- name: `Smb2SnapIssueIoctl`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140064c18`
- `0x140064f40`
- `0x14006502c`
- `0x140065334`

## callees

- `0x140060498`
- `0x1400654f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400655d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400655d2`
- `ntoskrnl!IoQueueThreadIrp` at `0x140065593`
- `ntoskrnl!IoQueueThreadIrp` at `0x140065593`
- `ntoskrnl!IofCallDriver` at `0x1400655a6`
- `ntoskrnl!IofCallDriver` at `0x1400655a6`
- `ntoskrnl!KeInitializeEvent` at `0x14006552c`
- `ntoskrnl!KeInitializeEvent` at `0x14006552c`

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
0x1400654f0  push    rbp
0x1400654f2  push    rbx
0x1400654f3  push    rsi
0x1400654f4  push    rdi
0x1400654f5  push    r14
0x1400654f7  mov     rbp, rsp
0x1400654fa  sub     rsp, 60h
0x1400654fe  xor     eax, eax
0x140065500  mov     rsi, r8
0x140065503  mov     r14d, edx
0x140065506  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14006550a  mov     rbx, rcx
0x14006550d  mov     [rbp+DeviceObject], rax
0x140065511  xorps   xmm0, xmm0
0x140065514  lea     rcx, [rbp+Event]; Event
0x140065518  xorps   xmm1, xmm1
0x14006551b  lea     edx, [rax+1]; Type
0x14006551e  xor     r8d, r8d; State
0x140065521  mov     rdi, r9
0x140065524  movups  [rbp+var_28], xmm0
0x140065528  movups  xmmword ptr [rbp+Event.Header], xmm1
0x14006552c  call    cs:__imp_KeInitializeEvent
0x140065533  nop     dword ptr [rax+rax+00h]
0x140065538  lea     rax, [rbp+DeviceObject]
0x14006553c  mov     rcx, rbx; Handle
0x14006553f  lea     r9, [rbp+var_28]
0x140065543  mov     [rsp+60h+Timeout], rax; __int64
0x140065548  lea     r8, [rbp+Event]
0x14006554c  call    Srv2BuildCoreOfSyncIoRequest
0x140065551  mov     rbx, rax
0x140065554  test    rax, rax
0x140065557  jnz     short loc_140065563
0x140065559  mov     eax, 0C000009Ah
0x14006555e  jmp     loc_1400655F6
0x140065563  mov     rcx, [rax+0B8h]
0x14006556a  or      dword ptr [rax+10h], 10h
0x14006556e  mov     [rax+18h], rsi
0x140065572  mov     word ptr [rcx-48h], 0Eh
0x140065578  mov     eax, [rdi]
0x14006557a  mov     [rcx-40h], eax
0x14006557d  mov     dword ptr [rcx-38h], 0
0x140065584  mov     [rcx-30h], r14d
0x140065588  mov     qword ptr [rcx-28h], 0
0x140065590  mov     rcx, rbx; Irp
0x140065593  call    cs:__imp_IoQueueThreadIrp
0x14006559a  nop     dword ptr [rax+rax+00h]
0x14006559f  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400655a3  mov     rdx, rbx; Irp
0x1400655a6  call    cs:__imp_IofCallDriver
0x1400655ad  nop     dword ptr [rax+rax+00h]
0x1400655b2  mov     ecx, eax
0x1400655b4  cmp     eax, 103h
0x1400655b9  jnz     short loc_1400655E0
0x1400655bb  xor     r9d, r9d; Alertable
0x1400655be  mov     [rsp+60h+Timeout], 0; Timeout
0x1400655c7  xor     r8d, r8d; WaitMode
0x1400655ca  lea     rcx, [rbp+Event]; Object
0x1400655ce  lea     edx, [r9+6]; WaitReason
0x1400655d2  call    cs:__imp_KeWaitForSingleObject
0x1400655d9  nop     dword ptr [rax+rax+00h]
0x1400655de  jmp     short loc_1400655E4
0x1400655e0  test    eax, eax
0x1400655e2  js      short loc_1400655E7
0x1400655e4  mov     ecx, dword ptr [rbp+var_28]
0x1400655e7  cmp     ecx, 80000005h
0x1400655ed  jnz     short loc_1400655F4
0x1400655ef  mov     eax, dword ptr [rbp+var_28+8]
0x1400655f2  mov     [rdi], eax
0x1400655f4  mov     eax, ecx
0x1400655f6  add     rsp, 60h
0x1400655fa  pop     r14
0x1400655fc  pop     rdi
0x1400655fd  pop     rsi
0x1400655fe  pop     rbx
0x1400655ff  pop     rbp
0x140065600  retn
```
