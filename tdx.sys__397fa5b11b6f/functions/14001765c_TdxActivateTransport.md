# TdxActivateTransport

- ea: `0x14001765c`
- end: `0x140017984`
- name: `TdxActivateTransport`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400112e0`
- `0x1400174d0`

## callees

- `0x14001765c`
- `0x140017ad0`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x1400176b7`
- `ntoskrnl!IoCreateDevice` at `0x1400176ee`
- `ntoskrnl!IoCreateDevice` at `0x1400176b7`
- `ntoskrnl!IoCreateDevice` at `0x1400176ee`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001772c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001772c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400177f7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001793a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400177f7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001793a`
- `ntoskrnl!IoDeleteDevice` at `0x140017704`
- `ntoskrnl!IoDeleteDevice` at `0x14001780c`
- `ntoskrnl!IoDeleteDevice` at `0x14001794a`
- `ntoskrnl!IoDeleteDevice` at `0x14001795a`
- `ntoskrnl!IoDeleteDevice` at `0x140017704`
- `ntoskrnl!IoDeleteDevice` at `0x14001780c`
- `ntoskrnl!IoDeleteDevice` at `0x14001794a`
- `ntoskrnl!IoDeleteDevice` at `0x14001795a`
- `ntoskrnl!IoAllocateWorkItem` at `0x140017798`
- `ntoskrnl!IoAllocateWorkItem` at `0x140017798`
- `ntoskrnl!ExAllocatePool2` at `0x14001777d`
- `ntoskrnl!ExAllocatePool2` at `0x14001777d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400177b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400177b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017749`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400178ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017749`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400178ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177da`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017879`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001791c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177da`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017879`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001791c`
- `TDI!TdiDeregisterDeviceObject` at `0x140017900`
- `TDI!TdiDeregisterDeviceObject` at `0x140017900`
- `TDI!TdiRegisterDeviceObject` at `0x14001788c`
- `TDI!TdiRegisterDeviceObject` at `0x14001788c`

## pseudocode

```c
NTSTATUS __fastcall TdxActivateTransport(__int64 a1)
{
  struct _UNICODE_STRING *v1; // r12
  NTSTATUS result; // eax
  NTSTATUS SymbolicLink; // edi
  KIRQL v5; // al
  KIRQL v6; // r14
  PDEVICE_OBJECT v7; // r13
  struct _DEVICE_OBJECT *v8; // r15
  _QWORD *Pool2; // rdi
  PIO_WORKITEM WorkItem; // rax
  PDEVICE_OBJECT v11; // rax
  KIRQL v12; // dl
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+40h] BYREF
  PDEVICE_OBJECT v14; // [rsp+88h] [rbp+48h] BYREF
  HANDLE RegistrationHandle; // [rsp+90h] [rbp+50h] BYREF

  v1 = (struct _UNICODE_STRING *)(a1 + 40);
  DeviceObject = 0;
  v14 = 0;
  RegistrationHandle = 0;
  result = IoCreateDevice(TdxDriverObject, 8u, (PUNICODE_STRING)(a1 + 40), 0x12u, 0x100u, 0, &DeviceObject);
  if ( result >= 0 )
  {
    SymbolicLink = IoCreateDevice(TdxDriverObject, 8u, (PUNICODE_STRING)(a1 + 56), 0x12u, 0x100u, 0, &v14);
    if ( SymbolicLink < 0 )
    {
LABEL_3:
      IoDeleteDevice(DeviceObject);
      return SymbolicLink;
    }
    if ( (*(_DWORD *)(a1 + 168) & 8) != 0 )
    {
      SymbolicLink = IoCreateSymbolicLink(&TdxTcpSymbolicDeviceName, v1);
      if ( SymbolicLink < 0 )
      {
LABEL_17:
        IoDeleteDevice(v14);
        goto LABEL_3;
      }
    }
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    v6 = v5;
    if ( (*(_DWORD *)(a1 + 168) & 3) == 0 )
    {
      v7 = v14;
      v8 = DeviceObject;
      Pool2 = (_QWORD *)ExAllocatePool2(64, 32, 544760916);
      if ( Pool2 )
      {
        WorkItem = IoAllocateWorkItem(v8);
        Pool2[1] = WorkItem;
        if ( WorkItem )
        {
          Pool2[2] = v8;
          Pool2[3] = v7;
          goto LABEL_13;
        }
        ExFreePoolWithTag(Pool2, 0);
      }
      Pool2 = 0;
LABEL_13:
      *(_QWORD *)(a1 + 208) = Pool2;
      if ( Pool2 )
      {
        DeviceObject->Flags |= 0x10u;
        v14->Flags |= 0x10u;
        DeviceObject->Flags &= ~0x80u;
        v14->Flags &= ~0x80u;
        _InterlockedExchange64((volatile __int64 *)DeviceObject->DeviceExtension, a1);
        _InterlockedExchange64((volatile __int64 *)v14->DeviceExtension, a1);
        v11 = DeviceObject;
        *(_DWORD *)(a1 + 168) |= 2u;
        *(_QWORD *)(a1 + 88) = v11;
        *(_QWORD *)(a1 + 96) = v14;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v6);
        SymbolicLink = TdiRegisterDeviceObject(v1, &RegistrationHandle);
        if ( SymbolicLink >= 0 )
        {
          v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
          if ( (*(_DWORD *)(a1 + 168) & 3) == 2 )
          {
            *(_QWORD *)(a1 + 104) = RegistrationHandle;
            KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v12);
            _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey);
          }
          else
          {
            KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v12);
            TdiDeregisterDeviceObject(RegistrationHandle);
            return -1073741811;
          }
        }
        else
        {
          TdxDeactivateTransport(a1);
        }
        return SymbolicLink;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v6);
      if ( (*(_DWORD *)(a1 + 168) & 8) != 0 )
        IoDeleteSymbolicLink(&TdxTcpSymbolicDeviceName);
      SymbolicLink = -1073741801;
      goto LABEL_17;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v5);
    if ( (*(_DWORD *)(a1 + 168) & 8) != 0 )
      IoDeleteSymbolicLink(&TdxTcpSymbolicDeviceName);
    IoDeleteDevice(v14);
    IoDeleteDevice(DeviceObject);
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x14001765c  mov     [rsp-38h+arg_18], rbx
0x140017661  push    rbp
0x140017662  push    rsi
0x140017663  push    rdi
0x140017664  push    r12
0x140017666  push    r13
0x140017668  push    r14
0x14001766a  push    r15
0x14001766c  mov     rbp, rsp
0x14001766f  sub     rsp, 40h
0x140017673  xor     esi, esi
0x140017675  lea     r12, [rcx+28h]
0x140017679  lea     rax, [rbp+arg_0]
0x14001767d  mov     [rbp+arg_0], rsi
0x140017681  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x140017686  mov     rbx, rcx
0x140017689  mov     rcx, cs:TdxDriverObject; DriverObject
0x140017690  mov     edi, 100h
0x140017695  lea     r14d, [rsi+12h]
0x140017699  mov     [rsp+40h+Exclusive], sil; Exclusive
0x14001769e  lea     r15d, [rsi+8]
0x1400176a2  mov     [rbp+arg_8], rsi
0x1400176a6  mov     r9d, r14d; DeviceType
0x1400176a9  mov     [rbp+RegistrationHandle], rsi
0x1400176ad  mov     edx, r15d; DeviceExtensionSize
0x1400176b0  mov     [rsp+40h+DeviceCharacteristics], edi; DeviceCharacteristics
0x1400176b4  mov     r8, r12; DeviceName
0x1400176b7  call    cs:__imp_IoCreateDevice
0x1400176be  nop     dword ptr [rax+rax+00h]
0x1400176c3  test    eax, eax
0x1400176c5  js      loc_14001796B
0x1400176cb  mov     rcx, cs:TdxDriverObject; DriverObject
0x1400176d2  lea     rax, [rbp+arg_8]
0x1400176d6  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x1400176db  lea     r8, [rbx+38h]; DeviceName
0x1400176df  mov     [rsp+40h+Exclusive], sil; Exclusive
0x1400176e4  mov     r9d, r14d; DeviceType
0x1400176e7  mov     edx, r15d; DeviceExtensionSize
0x1400176ea  mov     [rsp+40h+DeviceCharacteristics], edi; DeviceCharacteristics
0x1400176ee  call    cs:__imp_IoCreateDevice
0x1400176f5  nop     dword ptr [rax+rax+00h]
0x1400176fa  mov     edi, eax
0x1400176fc  test    eax, eax
0x1400176fe  jns     short loc_140017717
0x140017700  mov     rcx, [rbp+arg_0]; DeviceObject
0x140017704  call    cs:__imp_IoDeleteDevice
0x14001770b  nop     dword ptr [rax+rax+00h]
0x140017710  mov     eax, edi
0x140017712  jmp     loc_14001796B
0x140017717  mov     eax, [rbx+0A8h]
0x14001771d  test    r15b, al
0x140017720  jz      short loc_140017742
0x140017722  mov     rdx, r12; DeviceName
0x140017725  lea     rcx, TdxTcpSymbolicDeviceName; SymbolicLinkName
0x14001772c  call    cs:__imp_IoCreateSymbolicLink
0x140017733  nop     dword ptr [rax+rax+00h]
0x140017738  mov     edi, eax
0x14001773a  test    eax, eax
0x14001773c  js      loc_140017808
0x140017742  lea     rsi, [rbx+10h]
0x140017746  mov     rcx, rsi; SpinLock
0x140017749  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017750  nop     dword ptr [rax+rax+00h]
0x140017755  mov     ecx, [rbx+0A8h]
0x14001775b  mov     r14b, al
0x14001775e  test    cl, 3
0x140017761  jnz     loc_140017916
0x140017767  mov     r13, [rbp+arg_8]
0x14001776b  mov     edx, 20h ; ' '
0x140017770  mov     r15, [rbp+arg_0]
0x140017774  mov     r8d, 20786454h
0x14001777a  lea     ecx, [rdx+20h]
0x14001777d  call    cs:__imp_ExAllocatePool2
0x140017784  nop     dword ptr [rax+rax+00h]
0x140017789  mov     rdi, rax
0x14001778c  test    rax, rax
0x14001778f  jnz     short loc_140017795
0x140017791  xor     edi, edi
0x140017793  jmp     short loc_1400177C8
0x140017795  mov     rcx, r15; DeviceObject
0x140017798  call    cs:__imp_IoAllocateWorkItem
0x14001779f  nop     dword ptr [rax+rax+00h]
0x1400177a4  mov     [rdi+8], rax
0x1400177a8  test    rax, rax
0x1400177ab  jnz     short loc_1400177C0
0x1400177ad  xor     edx, edx; Tag
0x1400177af  mov     rcx, rdi; P
0x1400177b2  call    cs:__imp_ExFreePoolWithTag
0x1400177b9  nop     dword ptr [rax+rax+00h]
0x1400177be  jmp     short loc_140017791
0x1400177c0  mov     [rdi+10h], r15
0x1400177c4  mov     [rdi+18h], r13
0x1400177c8  mov     [rbx+0D0h], rdi
0x1400177cf  test    rdi, rdi
0x1400177d2  jnz     short loc_14001781D
0x1400177d4  mov     dl, r14b; NewIrql
0x1400177d7  mov     rcx, rsi; SpinLock
0x1400177da  call    cs:__imp_KeReleaseSpinLock
0x1400177e1  nop     dword ptr [rax+rax+00h]
0x1400177e6  mov     eax, [rbx+0A8h]
0x1400177ec  test    al, 8
0x1400177ee  jz      short loc_140017803
0x1400177f0  lea     rcx, TdxTcpSymbolicDeviceName; SymbolicLinkName
0x1400177f7  call    cs:__imp_IoDeleteSymbolicLink
0x1400177fe  nop     dword ptr [rax+rax+00h]
0x140017803  mov     edi, 0C0000017h
0x140017808  mov     rcx, [rbp+arg_8]; DeviceObject
0x14001780c  call    cs:__imp_IoDeleteDevice
0x140017813  nop     dword ptr [rax+rax+00h]
0x140017818  jmp     loc_140017700
0x14001781d  mov     rax, [rbp+arg_0]
0x140017821  mov     ecx, 0FFFFFF7Fh
0x140017826  mov     rdx, rbx
0x140017829  mov     r8, rbx
0x14001782c  or      dword ptr [rax+30h], 10h
0x140017830  mov     rax, [rbp+arg_8]
0x140017834  or      dword ptr [rax+30h], 10h
0x140017838  mov     rax, [rbp+arg_0]
0x14001783c  and     [rax+30h], ecx
0x14001783f  mov     rax, [rbp+arg_8]
0x140017843  and     [rax+30h], ecx
0x140017846  mov     rax, [rbp+arg_0]
0x14001784a  mov     rcx, [rax+40h]
0x14001784e  xchg    rdx, [rcx]
0x140017851  mov     rax, [rbp+arg_8]
0x140017855  mov     rcx, rsi; SpinLock
0x140017858  mov     rdx, [rax+40h]
0x14001785c  xchg    r8, [rdx]
0x14001785f  mov     rax, [rbp+arg_0]
0x140017863  mov     dl, r14b; NewIrql
0x140017866  or      dword ptr [rbx+0A8h], 2
0x14001786d  mov     [rbx+58h], rax
0x140017871  mov     rax, [rbp+arg_8]
0x140017875  mov     [rbx+60h], rax
0x140017879  call    cs:__imp_KeReleaseSpinLock
0x140017880  nop     dword ptr [rax+rax+00h]
0x140017885  lea     rdx, [rbp+RegistrationHandle]; RegistrationHandle
0x140017889  mov     rcx, r12; DeviceName
0x14001788c  call    cs:__imp_TdiRegisterDeviceObject
0x140017893  nop     dword ptr [rax+rax+00h]
0x140017898  mov     edi, eax
0x14001789a  test    eax, eax
0x14001789c  jns     short loc_1400178AB
0x14001789e  mov     rcx, rbx
0x1400178a1  call    TdxDeactivateTransport
0x1400178a6  jmp     loc_140017710
0x1400178ab  mov     rcx, rsi; SpinLock
0x1400178ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400178b5  nop     dword ptr [rax+rax+00h]
0x1400178ba  mov     ecx, [rbx+0A8h]
0x1400178c0  mov     dl, al; NewIrql
0x1400178c2  and     cl, 3
0x1400178c5  cmp     cl, 2
0x1400178c8  jnz     short loc_1400178ED
0x1400178ca  mov     rcx, [rbp+RegistrationHandle]
0x1400178ce  mov     [rbx+68h], rcx
0x1400178d2  mov     rcx, rsi; SpinLock
0x1400178d5  call    cs:__imp_KeReleaseSpinLock
0x1400178dc  nop     dword ptr [rax+rax+00h]
0x1400178e1  lock inc dword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400178e8  jmp     loc_140017710
0x1400178ed  mov     rcx, rsi; SpinLock
0x1400178f0  call    cs:__imp_KeReleaseSpinLock
0x1400178f7  nop     dword ptr [rax+rax+00h]
0x1400178fc  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x140017900  call    cs:__imp_TdiDeregisterDeviceObject
0x140017907  nop     dword ptr [rax+rax+00h]
0x14001790c  mov     edi, 0C000000Dh
0x140017911  jmp     loc_140017710
0x140017916  mov     dl, r14b; NewIrql
0x140017919  mov     rcx, rsi; SpinLock
0x14001791c  call    cs:__imp_KeReleaseSpinLock
0x140017923  nop     dword ptr [rax+rax+00h]
0x140017928  mov     eax, [rbx+0A8h]
0x14001792e  test    r15b, al
0x140017931  jz      short loc_140017946
0x140017933  lea     rcx, TdxTcpSymbolicDeviceName; SymbolicLinkName
0x14001793a  call    cs:__imp_IoDeleteSymbolicLink
0x140017941  nop     dword ptr [rax+rax+00h]
0x140017946  mov     rcx, [rbp+arg_8]; DeviceObject
0x14001794a  call    cs:__imp_IoDeleteDevice
0x140017951  nop     dword ptr [rax+rax+00h]
0x140017956  mov     rcx, [rbp+arg_0]; DeviceObject
0x14001795a  call    cs:__imp_IoDeleteDevice
0x140017961  nop     dword ptr [rax+rax+00h]
0x140017966  mov     eax, 0C000000Dh
0x14001796b  mov     rbx, [rsp+40h+arg_18]
0x140017973  add     rsp, 40h
0x140017977  pop     r15
0x140017979  pop     r14
0x14001797b  pop     r13
0x14001797d  pop     r12
0x14001797f  pop     rdi
0x140017980  pop     rsi
0x140017981  pop     rbp
0x140017982  retn
```
