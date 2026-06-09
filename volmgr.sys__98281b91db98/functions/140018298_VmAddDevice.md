# VmAddDevice

- ea: `0x140018298`
- end: `0x1400184aa`
- name: `VmAddDevice`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x140018078`

## callees

- `0x140014fe8`
- `0x140018298`
- `0x14001867c`

## import_xrefs

- `ntoskrnl!IoRegisterDeviceInterface` at `0x140018421`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140018421`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140018443`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140018443`
- `ntoskrnl!KeInitializeMutex` at `0x140018344`
- `ntoskrnl!KeInitializeMutex` at `0x14001835d`
- `ntoskrnl!KeInitializeMutex` at `0x140018344`
- `ntoskrnl!KeInitializeMutex` at `0x14001835d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001832b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001832b`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x140018474`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x140018474`
- `ntoskrnl!IoCreateDevice` at `0x1400182d9`
- `ntoskrnl!IoCreateDevice` at `0x1400182d9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140018463`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140018463`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400183cc`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400183cc`

## pseudocode

```c
NTSTATUS __fastcall VmAddDevice(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2)
{
  NTSTATUS result; // eax
  PVOID DeviceExtension; // rcx
  struct VM_ROOT_EXTENSION *v6; // rcx
  _QWORD *v7; // rax
  int updated; // ebx
  PDEVICE_OBJECT v9; // rax
  struct VM_ROOT_EXTENSION *v10; // rcx
  struct _DEVICE_OBJECT *v11; // rcx
  PDEVICE_OBJECT SourceDevice; // [rsp+60h] [rbp+18h] BYREF

  SourceDevice = 0;
  result = IoCreateDevice(a1, 0x190u, (PUNICODE_STRING)&DeviceName, 0x12u, 0x100u, 0, &SourceDevice);
  if ( result < 0 )
    return result;
  DeviceExtension = SourceDevice->DeviceExtension;
  VmRootExtension = (struct VM_ROOT_EXTENSION *)DeviceExtension;
  *(_QWORD *)DeviceExtension = SourceDevice;
  *((_QWORD *)DeviceExtension + 1) = DeviceExtension;
  *((_DWORD *)DeviceExtension + 4) = 0;
  *((_QWORD *)DeviceExtension + 4) = a1;
  *((_QWORD *)DeviceExtension + 6) = a2;
  *((_DWORD *)DeviceExtension + 70) = 1;
  *((_DWORD *)DeviceExtension + 96) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 3);
  KeInitializeMutex((PRKMUTEX)VmRootExtension + 1, 0);
  KeInitializeMutex((PRKMUTEX)VmRootExtension + 2, 0);
  v6 = VmRootExtension;
  v7 = (_QWORD *)((char *)VmRootExtension + 184);
  *((_QWORD *)VmRootExtension + 24) = (char *)VmRootExtension + 184;
  *v7 = v7;
  *((_QWORD *)v6 + 27) = (char *)v6 + 208;
  *((_QWORD *)v6 + 26) = (char *)v6 + 208;
  *((_QWORD *)v6 + 29) = (char *)v6 + 224;
  *((_QWORD *)v6 + 28) = (char *)v6 + 224;
  *((_QWORD *)v6 + 31) = (char *)v6 + 240;
  *((_QWORD *)v6 + 30) = (char *)v6 + 240;
  *((_QWORD *)v6 + 33) = (char *)v6 + 256;
  *((_QWORD *)v6 + 32) = (char *)v6 + 256;
  updated = VmpUpdateControlStackSd((__int64)a2);
  if ( updated >= 0 )
  {
    v9 = IoAttachDeviceToDeviceStack(SourceDevice, a2);
    v10 = VmRootExtension;
    *((_QWORD *)VmRootExtension + 5) = v9;
    if ( v9 )
    {
      updated = IoRegisterDeviceInterface(
                  *((PDEVICE_OBJECT *)v10 + 6),
                  &VOLMGR_VOLUME_MANAGER_GUID,
                  0,
                  (PUNICODE_STRING)((char *)v10 + 168));
      if ( updated >= 0 )
      {
        updated = IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)VmRootExtension + 168), 1u);
        if ( updated >= 0 )
        {
          IoCreateSymbolicLink((PUNICODE_STRING)&stru_140007020, (PUNICODE_STRING)&DeviceName);
          updated = IoRegisterLastChanceShutdownNotification(SourceDevice);
          if ( updated >= 0 )
          {
            SourceDevice->Flags &= ~0x80u;
            v11 = 0;
            SourceDevice = 0;
            goto LABEL_6;
          }
        }
      }
    }
    else
    {
      updated = -1073741810;
    }
  }
  v11 = SourceDevice;
LABEL_6:
  if ( v11 )
    VmpRemoveDevice(v11, 1);
  return updated;
}

```

## disassembly

```asm
0x140018298  mov     r11, rsp
0x14001829b  mov     [r11+8], rbx
0x14001829f  push    rdi
0x1400182a0  sub     rsp, 40h
0x1400182a4  lea     rax, [r11+18h]
0x1400182a8  mov     qword ptr [r11+18h], 0
0x1400182b0  mov     [r11-18h], rax
0x1400182b4  lea     r8, DeviceName; DeviceName
0x1400182bb  mov     rdi, rdx
0x1400182be  mov     [rsp+48h+Exclusive], 0; Exclusive
0x1400182c3  mov     r9d, 12h; DeviceType
0x1400182c9  mov     [rsp+48h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1400182d1  mov     edx, 190h; DeviceExtensionSize
0x1400182d6  mov     rbx, rcx
0x1400182d9  call    cs:__imp_IoCreateDevice
0x1400182e0  nop     dword ptr [rax+rax+00h]
0x1400182e5  test    eax, eax
0x1400182e7  js      loc_140018400
0x1400182ed  mov     rax, [rsp+48h+SourceDevice]
0x1400182f2  mov     rcx, [rax+40h]
0x1400182f6  mov     cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA, rcx; VM_ROOT_EXTENSION * VmRootExtension
0x1400182fd  mov     [rcx], rax
0x140018300  mov     [rcx+8], rcx
0x140018304  mov     dword ptr [rcx+10h], 0
0x14001830b  mov     [rcx+20h], rbx
0x14001830f  mov     [rcx+30h], rdi
0x140018313  mov     dword ptr [rcx+118h], 1
0x14001831d  mov     dword ptr [rcx+180h], 1
0x140018327  add     rcx, 18h; SpinLock
0x14001832b  call    cs:__imp_KeInitializeSpinLock
0x140018332  nop     dword ptr [rax+rax+00h]
0x140018337  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001833e  xor     edx, edx; Level
0x140018340  add     rcx, 38h ; '8'; Mutex
0x140018344  call    cs:__imp_KeInitializeMutex
0x14001834b  nop     dword ptr [rax+rax+00h]
0x140018350  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140018357  xor     edx, edx; Level
0x140018359  add     rcx, 70h ; 'p'; Mutex
0x14001835d  call    cs:__imp_KeInitializeMutex
0x140018364  nop     dword ptr [rax+rax+00h]
0x140018369  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140018370  lea     rax, [rcx+0B8h]
0x140018377  mov     [rax+8], rax
0x14001837b  mov     [rax], rax
0x14001837e  lea     rax, [rcx+0D0h]
0x140018385  mov     [rax+8], rax
0x140018389  mov     [rax], rax
0x14001838c  lea     rax, [rcx+0E0h]
0x140018393  mov     [rax+8], rax
0x140018397  mov     [rax], rax
0x14001839a  lea     rax, [rcx+0F0h]
0x1400183a1  mov     [rax+8], rax
0x1400183a5  mov     [rax], rax
0x1400183a8  lea     rax, [rcx+100h]
0x1400183af  mov     rcx, rdi
0x1400183b2  mov     [rax+8], rax
0x1400183b6  mov     [rax], rax
0x1400183b9  call    VmpUpdateControlStackSd
0x1400183be  mov     ebx, eax
0x1400183c0  test    eax, eax
0x1400183c2  js      short loc_1400183ED
0x1400183c4  mov     rcx, [rsp+48h+SourceDevice]; SourceDevice
0x1400183c9  mov     rdx, rdi; TargetDevice
0x1400183cc  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400183d3  nop     dword ptr [rax+rax+00h]
0x1400183d8  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400183df  mov     [rcx+28h], rax
0x1400183e3  test    rax, rax
0x1400183e6  jnz     short loc_14001840C
0x1400183e8  mov     ebx, 0C000000Eh
0x1400183ed  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x1400183f2  test    rcx, rcx
0x1400183f5  jz      short loc_1400183FE
0x1400183f7  mov     dl, 1
0x1400183f9  call    VmpRemoveDevice
0x1400183fe  mov     eax, ebx
0x140018400  mov     rbx, [rsp+48h+arg_0]
0x140018405  add     rsp, 40h
0x140018409  pop     rdi
0x14001840a  retn
0x14001840c  lea     r9, [rcx+0A8h]; SymbolicLinkName
0x140018413  xor     r8d, r8d; ReferenceString
0x140018416  mov     rcx, [rcx+30h]; PhysicalDeviceObject
0x14001841a  lea     rdx, VOLMGR_VOLUME_MANAGER_GUID; InterfaceClassGuid
0x140018421  call    cs:__imp_IoRegisterDeviceInterface
0x140018428  nop     dword ptr [rax+rax+00h]
0x14001842d  mov     ebx, eax
0x14001842f  test    eax, eax
0x140018431  js      short loc_1400183ED
0x140018433  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001843a  mov     dl, 1; Enable
0x14001843c  add     rcx, 0A8h; SymbolicLinkName
0x140018443  call    cs:__imp_IoSetDeviceInterfaceState
0x14001844a  nop     dword ptr [rax+rax+00h]
0x14001844f  mov     ebx, eax
0x140018451  test    eax, eax
0x140018453  js      short loc_1400183ED
0x140018455  lea     rdx, DeviceName; DeviceName
0x14001845c  lea     rcx, stru_140007020; SymbolicLinkName
0x140018463  call    cs:__imp_IoCreateSymbolicLink
0x14001846a  nop     dword ptr [rax+rax+00h]
0x14001846f  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x140018474  call    cs:__imp_IoRegisterLastChanceShutdownNotification
0x14001847b  nop     dword ptr [rax+rax+00h]
0x140018480  mov     ebx, eax
0x140018482  test    eax, eax
0x140018484  js      loc_1400183ED
0x14001848a  mov     rax, [rsp+48h+SourceDevice]
0x14001848f  mov     ecx, [rax+30h]
0x140018492  mov     rax, [rsp+48h+SourceDevice]
0x140018497  btr     ecx, 7
0x14001849b  mov     [rax+30h], ecx
0x14001849e  xor     ecx, ecx
0x1400184a0  mov     [rsp+48h+SourceDevice], rcx
0x1400184a5  jmp     loc_1400183F2
```
