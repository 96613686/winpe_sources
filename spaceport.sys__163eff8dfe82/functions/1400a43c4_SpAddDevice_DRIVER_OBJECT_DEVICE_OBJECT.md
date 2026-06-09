# SpAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x1400a43c4`
- end: `0x1400a44fb`
- name: `?SpAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400bc078`

## callees

- `0x14002b048`
- `0x140031b54`
- `0x1400a1b3c`
- `0x1400a1d08`
- `0x1400a2ad0`
- `0x1400a43c4`
- `0x1400a7460`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a43f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a43f4`
- `ntoskrnl!IoDeleteDevice` at `0x1400a44dc`
- `ntoskrnl!IoDeleteDevice` at `0x1400a44dc`
- `ntoskrnl!IoCreateDevice` at `0x1400a442a`
- `ntoskrnl!IoCreateDevice` at `0x1400a442a`

## pseudocode

```c
__int64 __fastcall SpAddDevice(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2)
{
  int v4; // ebx
  _QWORD *DeviceExtension; // rcx
  SP_CONTROL *v6; // rax
  struct _DEVICE_OBJECT *v7; // r8
  struct _DEVICE_OBJECT *v8; // rcx
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+70h] [rbp+18h] BYREF

  DeviceObject = 0;
  DeviceName = 0;
  RtlInitUnicodeString(&DeviceName, L"\\Device\\Spaceport");
  v4 = IoCreateDevice(a1, 0xBD8u, &DeviceName, 4u, 0x100u, 0, &DeviceObject);
  if ( v4 < 0 )
    goto LABEL_7;
  DeviceExtension = DeviceObject->DeviceExtension;
  *DeviceExtension = qword_14006D930;
  v6 = (SP_CONTROL *)SP_DEVICE::operator new(
                       (unsigned __int64)DeviceExtension,
                       (char *)DeviceObject->DeviceExtension + 8,
                       (unsigned __int64)DeviceObject);
  if ( v6 )
  {
    v6 = SP_CONTROL::SP_CONTROL(v6);
    v7 = DeviceObject;
  }
  WPP_MAIN_CB.DeviceExtension = v6;
  v4 = SP_CONTROL::Initialize(v6, a1, v7, a2);
  if ( v4 < 0 || (v4 = SP_CONTROL::Start((SP_CONTROL *)WPP_MAIN_CB.DeviceExtension), v4 < 0) )
  {
LABEL_7:
    v8 = DeviceObject;
  }
  else
  {
    SpInitializeLimiter();
    v8 = 0;
    DeviceObject = 0;
  }
  if ( v8 )
  {
    if ( WPP_MAIN_CB.DeviceExtension )
    {
      SP_CONTROL::~SP_CONTROL((SP_CONTROL *)WPP_MAIN_CB.DeviceExtension);
      v8 = DeviceObject;
    }
    WPP_MAIN_CB.DeviceExtension = 0;
    IoDeleteDevice(v8);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400a43c4  mov     rax, rsp
0x1400a43c7  mov     [rax+8], rbx
0x1400a43cb  mov     [rax+10h], rsi
0x1400a43cf  push    rdi
0x1400a43d0  sub     rsp, 50h
0x1400a43d4  mov     rsi, rdx
0x1400a43d7  mov     qword ptr [rax+18h], 0
0x1400a43df  mov     rdi, rcx
0x1400a43e2  lea     rdx, aDeviceSpacepor; "\\Device\\Spaceport"
0x1400a43e9  xorps   xmm0, xmm0
0x1400a43ec  lea     rcx, [rax-18h]; DestinationString
0x1400a43f0  movups  xmmword ptr [rax-18h], xmm0
0x1400a43f4  call    cs:__imp_RtlInitUnicodeString
0x1400a43fb  nop     dword ptr [rax+rax+00h]
0x1400a4400  lea     rax, [rsp+58h+arg_10]
0x1400a4405  mov     r9d, 4; DeviceType
0x1400a440b  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x1400a4410  lea     r8, [rsp+58h+DeviceName]; DeviceName
0x1400a4415  mov     [rsp+58h+Exclusive], 0; Exclusive
0x1400a441a  mov     edx, 0BD8h; DeviceExtensionSize
0x1400a441f  mov     rcx, rdi; DriverObject
0x1400a4422  mov     [rsp+58h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1400a442a  call    cs:__imp_IoCreateDevice
0x1400a4431  nop     dword ptr [rax+rax+00h]
0x1400a4436  mov     ebx, eax
0x1400a4438  test    eax, eax
0x1400a443a  js      short loc_1400A44AE
0x1400a443c  mov     rax, [rsp+58h+arg_10]
0x1400a4441  mov     rcx, [rax+40h]; unsigned __int64
0x1400a4445  lea     rax, qword_14006D930
0x1400a444c  mov     [rcx], rax
0x1400a444f  mov     r8, [rsp+58h+arg_10]; unsigned __int64
0x1400a4454  mov     rdx, [r8+40h]
0x1400a4458  add     rdx, 8; void *
0x1400a445c  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a4461  test    rax, rax
0x1400a4464  jz      short loc_1400A4473
0x1400a4466  mov     rcx, rax; this
0x1400a4469  call    ??0SP_CONTROL@@QEAA@XZ; SP_CONTROL::SP_CONTROL(void)
0x1400a446e  mov     r8, [rsp+58h+arg_10]; struct _DEVICE_OBJECT *
0x1400a4473  mov     r9, rsi; struct _DEVICE_OBJECT *
0x1400a4476  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x1400a447d  mov     rdx, rdi; struct _DRIVER_OBJECT *
0x1400a4480  mov     rcx, rax; this
0x1400a4483  call    ?Initialize@SP_CONTROL@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@1@Z; SP_CONTROL::Initialize(_DRIVER_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x1400a4488  mov     ebx, eax
0x1400a448a  test    eax, eax
0x1400a448c  js      short loc_1400A44AE
0x1400a448e  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; this
0x1400a4495  call    ?Start@SP_CONTROL@@QEAAJXZ; SP_CONTROL::Start(void)
0x1400a449a  mov     ebx, eax
0x1400a449c  test    eax, eax
0x1400a449e  js      short loc_1400A44AE
0x1400a44a0  call    ?SpInitializeLimiter@@YAJXZ; SpInitializeLimiter(void)
0x1400a44a5  xor     ecx, ecx
0x1400a44a7  mov     [rsp+58h+arg_10], rcx
0x1400a44ac  jmp     short loc_1400A44B3
0x1400a44ae  mov     rcx, [rsp+58h+arg_10]
0x1400a44b3  test    rcx, rcx
0x1400a44b6  jz      short loc_1400A44E8
0x1400a44b8  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a44bf  test    rax, rax
0x1400a44c2  jz      short loc_1400A44D1
0x1400a44c4  mov     rcx, rax; this
0x1400a44c7  call    ??1SP_CONTROL@@QEAA@XZ; SP_CONTROL::~SP_CONTROL(void)
0x1400a44cc  mov     rcx, [rsp+58h+arg_10]; DeviceObject
0x1400a44d1  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400a44dc  call    cs:__imp_IoDeleteDevice
0x1400a44e3  nop     dword ptr [rax+rax+00h]
0x1400a44e8  mov     rsi, [rsp+58h+arg_8]
0x1400a44ed  mov     eax, ebx
0x1400a44ef  mov     rbx, [rsp+58h+arg_0]
0x1400a44f4  add     rsp, 50h
0x1400a44f8  pop     rdi
0x1400a44f9  retn
```
