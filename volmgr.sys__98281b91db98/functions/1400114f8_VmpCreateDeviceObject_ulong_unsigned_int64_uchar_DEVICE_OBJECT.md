# VmpCreateDeviceObject(ulong,unsigned __int64,uchar,_DEVICE_OBJECT * *)

- ea: `0x1400114f8`
- end: `0x140011714`
- name: `?VmpCreateDeviceObject@@YAJK_KEPEAPEAU_DEVICE_OBJECT@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64, unsigned __int8, struct _DEVICE_OBJECT **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010d7c`
- `0x14001171c`

## callees

- `0x140005050`
- `0x1400114f8`
- `0x140015490`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400116a5`
- `ntoskrnl!KeInitializeMutex` at `0x1400116a5`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x14001156a`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x14001156a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400115dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400116d6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400115dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400116d6`
- `ntoskrnl!IoCreateDevice` at `0x1400115aa`
- `ntoskrnl!IoCreateDevice` at `0x1400115aa`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400116b8`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x1400116b8`

## pseudocode

```c
__int64 __fastcall VmpCreateDeviceObject(int a1, __int64 a2, char a3, struct _DEVICE_OBJECT **a4)
{
  unsigned int v8; // r14d
  NTSTATUS v9; // edi
  char *DeviceExtension; // rbx
  struct VM_ROOT_EXTENSION *v11; // rdx
  int v12; // ecx
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+48h] [rbp-21h] BYREF
  char v16; // [rsp+58h] [rbp-11h] BYREF

  *a4 = 0;
  DeviceObject = 0;
  *(_QWORD *)&DeviceName.Length = 3932160;
  DeviceName.Buffer = (PWSTR)&v16;
  VmpBuildName(&DeviceName, 0, *((unsigned int *)VmRootExtension + 70), 0);
  v8 = ExSizeOfRundownProtectionCacheAware();
  v9 = IoCreateDevice(
         *((PDRIVER_OBJECT *)VmRootExtension + 4),
         v8 + 440,
         &DeviceName,
         7u,
         a1 | 0x20000,
         0,
         &DeviceObject);
  if ( v9 >= 0 )
  {
    DeviceObject->Flags |= 0x10u;
    DeviceExtension = (char *)DeviceObject->DeviceExtension;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 3);
    v11 = VmRootExtension;
    *((_QWORD *)DeviceExtension + 6) = MEMORY[0xFFFFF78000000014];
    *(_QWORD *)DeviceExtension = DeviceObject;
    *((_QWORD *)DeviceExtension + 1) = v11;
    *((_DWORD *)DeviceExtension + 4) = 1;
    *((_DWORD *)DeviceExtension + 76) = 0;
    DeviceExtension[158] = 0;
    DeviceExtension[152] = a3;
    DeviceExtension[160] = 1;
    v12 = *((_DWORD *)v11 + 70);
    *((_DWORD *)v11 + 70) = v12 + 1;
    *((_QWORD *)DeviceExtension + 14) = DeviceExtension + 440;
    *((_DWORD *)DeviceExtension + 41) = v12;
    *((_QWORD *)DeviceExtension + 30) = &DiskperfGuidList;
    DeviceExtension[154] = 0;
    *((_QWORD *)DeviceExtension + 31) = VmQueryWmiRegInfo;
    *((_QWORD *)DeviceExtension + 32) = VmQueryWmiDataBlock;
    *((_QWORD *)DeviceExtension + 36) = VmWmiFunctionControl;
    *((_QWORD *)DeviceExtension + 39) = a2;
    *((_DWORD *)DeviceExtension + 58) = 1;
    KeInitializeMutex((PRKMUTEX)DeviceExtension + 1, 0);
    ExInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 14), v8);
    *((_QWORD *)DeviceExtension + 16) = DeviceExtension + 120;
    *((_QWORD *)DeviceExtension + 15) = DeviceExtension + 120;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 17);
    *a4 = DeviceObject;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400114f8  mov     [rsp-8+arg_8], rbx
0x1400114fd  mov     [rsp-8+arg_10], rsi
0x140011502  push    rbp
0x140011503  push    rdi
0x140011504  push    r12
0x140011506  push    r14
0x140011508  push    r15
0x14001150a  lea     rbp, [rsp-37h]
0x14001150f  sub     rsp, 0A0h
0x140011516  mov     rax, cs:__security_cookie
0x14001151d  xor     rax, rsp
0x140011520  mov     [rbp+57h+var_28], rax
0x140011524  mov     r15b, r8b
0x140011527  mov     qword ptr [r9], 0
0x14001152e  mov     r8, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140011535  lea     rax, [rbp+57h+var_68]
0x140011539  mov     rsi, r9
0x14001153c  mov     [rbp+57h+var_80], 0
0x140011544  mov     r12, rdx
0x140011547  mov     qword ptr [rbp+57h+DeviceName.Length], 3C0000h
0x14001154f  mov     ebx, ecx
0x140011551  mov     [rbp+57h+DeviceName.Buffer], rax
0x140011555  mov     r8d, [r8+118h]
0x14001155c  lea     rcx, [rbp+57h+DeviceName]
0x140011560  xor     r9d, r9d
0x140011563  xor     edx, edx
0x140011565  call    VmpBuildName
0x14001156a  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x140011571  nop     dword ptr [rax+rax+00h]
0x140011576  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001157d  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x140011581  mov     r14, rax
0x140011584  bts     ebx, 11h
0x140011588  mov     r9d, 7; DeviceType
0x14001158e  lea     edx, [rax+1B8h]; DeviceExtensionSize
0x140011594  mov     rcx, [rcx+20h]; DriverObject
0x140011598  lea     rax, [rbp+57h+var_80]
0x14001159c  mov     [rsp+0C0h+DeviceObject], rax; DeviceObject
0x1400115a1  mov     [rsp+0C0h+Exclusive], 0; Exclusive
0x1400115a6  mov     [rsp+0C0h+DeviceCharacteristics], ebx; DeviceCharacteristics
0x1400115aa  call    cs:__imp_IoCreateDevice
0x1400115b1  nop     dword ptr [rax+rax+00h]
0x1400115b6  mov     edi, eax
0x1400115b8  test    eax, eax
0x1400115ba  js      loc_1400116E9
0x1400115c0  mov     rcx, [rbp+57h+var_80]
0x1400115c4  mov     edx, [rcx+30h]
0x1400115c7  mov     rcx, [rbp+57h+var_80]
0x1400115cb  or      edx, 10h
0x1400115ce  mov     [rcx+30h], edx
0x1400115d1  mov     rcx, [rbp+57h+var_80]
0x1400115d5  mov     rbx, [rcx+40h]
0x1400115d9  lea     rcx, [rbx+18h]; SpinLock
0x1400115dd  call    cs:__imp_KeInitializeSpinLock
0x1400115e4  nop     dword ptr [rax+rax+00h]
0x1400115e9  mov     rax, ds:0FFFFF78000000014h
0x1400115f3  mov     r8d, 1
0x1400115f9  mov     rdx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140011600  mov     [rbx+30h], rax
0x140011604  mov     rax, [rbp+57h+var_80]
0x140011608  mov     [rbx], rax
0x14001160b  mov     [rbx+8], rdx
0x14001160f  mov     [rbx+10h], r8d
0x140011613  mov     dword ptr [rbx+130h], 0
0x14001161d  mov     byte ptr [rbx+9Eh], 0
0x140011624  mov     [rbx+98h], r15b
0x14001162b  mov     [rbx+0A0h], r8b
0x140011632  mov     ecx, [rdx+118h]
0x140011638  lea     eax, [rcx+1]
0x14001163b  mov     [rdx+118h], eax
0x140011641  lea     rax, [rbx+1B8h]
0x140011648  mov     [rbx+70h], rax
0x14001164c  xor     edx, edx; Level
0x14001164e  lea     rax, DiskperfGuidList
0x140011655  mov     [rbx+0A4h], ecx
0x14001165b  mov     [rbx+0F0h], rax
0x140011662  lea     rcx, [rbx+38h]; Mutex
0x140011666  lea     rax, VmQueryWmiRegInfo
0x14001166d  mov     byte ptr [rbx+9Ah], 0
0x140011674  mov     [rbx+0F8h], rax
0x14001167b  lea     rax, VmQueryWmiDataBlock
0x140011682  mov     [rbx+100h], rax
0x140011689  lea     rax, VmWmiFunctionControl
0x140011690  mov     [rbx+120h], rax
0x140011697  mov     [rbx+138h], r12
0x14001169e  mov     [rbx+0E8h], r8d
0x1400116a5  call    cs:__imp_KeInitializeMutex
0x1400116ac  nop     dword ptr [rax+rax+00h]
0x1400116b1  mov     rcx, [rbx+70h]; RunRefCacheAware
0x1400116b5  mov     edx, r14d; RunRefSize
0x1400116b8  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x1400116bf  nop     dword ptr [rax+rax+00h]
0x1400116c4  lea     rax, [rbx+78h]
0x1400116c8  lea     rcx, [rbx+88h]; SpinLock
0x1400116cf  mov     [rax+8], rax
0x1400116d3  mov     [rax], rax
0x1400116d6  call    cs:__imp_KeInitializeSpinLock
0x1400116dd  nop     dword ptr [rax+rax+00h]
0x1400116e2  mov     rax, [rbp+57h+var_80]
0x1400116e6  mov     [rsi], rax
0x1400116e9  mov     eax, edi
0x1400116eb  mov     rcx, [rbp+57h+var_28]
0x1400116ef  xor     rcx, rsp; StackCookie
0x1400116f2  call    __security_check_cookie
0x1400116f7  lea     r11, [rsp+0C0h+var_20]
0x1400116ff  mov     rbx, [r11+38h]
0x140011703  mov     rsi, [r11+40h]
0x140011707  mov     rsp, r11
0x14001170a  pop     r15
0x14001170c  pop     r14
0x14001170e  pop     r12
0x140011710  pop     rdi
0x140011711  pop     rbp
0x140011712  retn
```
