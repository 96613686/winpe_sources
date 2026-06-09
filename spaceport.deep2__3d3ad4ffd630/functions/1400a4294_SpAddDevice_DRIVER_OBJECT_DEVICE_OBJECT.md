# SpAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x1400a4294`
- end: `0x1400a43cb`
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
- `0x140031ae4`
- `0x1400a1a0c`
- `0x1400a1bd8`
- `0x1400a29a0`
- `0x1400a4294`
- `0x1400a7330`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a42c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a42c4`
- `ntoskrnl!IoDeleteDevice` at `0x1400a43ac`
- `ntoskrnl!IoDeleteDevice` at `0x1400a43ac`
- `ntoskrnl!IoCreateDevice` at `0x1400a42fa`
- `ntoskrnl!IoCreateDevice` at `0x1400a42fa`

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
0x1400a4294  mov     rax, rsp
0x1400a4297  mov     [rax+8], rbx
0x1400a429b  mov     [rax+10h], rsi
0x1400a429f  push    rdi
0x1400a42a0  sub     rsp, 50h
0x1400a42a4  mov     rsi, rdx
0x1400a42a7  mov     qword ptr [rax+18h], 0
0x1400a42af  mov     rdi, rcx
0x1400a42b2  lea     rdx, aDeviceSpacepor; "\\Device\\Spaceport"
0x1400a42b9  xorps   xmm0, xmm0
0x1400a42bc  lea     rcx, [rax-18h]; DestinationString
0x1400a42c0  movups  xmmword ptr [rax-18h], xmm0
0x1400a42c4  call    cs:__imp_RtlInitUnicodeString
0x1400a42cb  nop     dword ptr [rax+rax+00h]
0x1400a42d0  lea     rax, [rsp+58h+arg_10]
0x1400a42d5  mov     r9d, 4; DeviceType
0x1400a42db  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x1400a42e0  lea     r8, [rsp+58h+DeviceName]; DeviceName
0x1400a42e5  mov     [rsp+58h+Exclusive], 0; Exclusive
0x1400a42ea  mov     edx, 0BD8h; DeviceExtensionSize
0x1400a42ef  mov     rcx, rdi; DriverObject
0x1400a42f2  mov     [rsp+58h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1400a42fa  call    cs:__imp_IoCreateDevice
0x1400a4301  nop     dword ptr [rax+rax+00h]
0x1400a4306  mov     ebx, eax
0x1400a4308  test    eax, eax
0x1400a430a  js      short loc_1400A437E
0x1400a430c  mov     rax, [rsp+58h+arg_10]
0x1400a4311  mov     rcx, [rax+40h]; unsigned __int64
0x1400a4315  lea     rax, qword_14006D930
0x1400a431c  mov     [rcx], rax
0x1400a431f  mov     r8, [rsp+58h+arg_10]; unsigned __int64
0x1400a4324  mov     rdx, [r8+40h]
0x1400a4328  add     rdx, 8; void *
0x1400a432c  call    ??2SP_DEVICE@@SAPEAX_KPEAX0@Z; SP_DEVICE::operator new(unsigned __int64,void *,unsigned __int64)
0x1400a4331  test    rax, rax
0x1400a4334  jz      short loc_1400A4343
0x1400a4336  mov     rcx, rax; this
0x1400a4339  call    ??0SP_CONTROL@@QEAA@XZ; SP_CONTROL::SP_CONTROL(void)
0x1400a433e  mov     r8, [rsp+58h+arg_10]; struct _DEVICE_OBJECT *
0x1400a4343  mov     r9, rsi; struct _DEVICE_OBJECT *
0x1400a4346  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x1400a434d  mov     rdx, rdi; struct _DRIVER_OBJECT *
0x1400a4350  mov     rcx, rax; this
0x1400a4353  call    ?Initialize@SP_CONTROL@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@1@Z; SP_CONTROL::Initialize(_DRIVER_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x1400a4358  mov     ebx, eax
0x1400a435a  test    eax, eax
0x1400a435c  js      short loc_1400A437E
0x1400a435e  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; this
0x1400a4365  call    ?Start@SP_CONTROL@@QEAAJXZ; SP_CONTROL::Start(void)
0x1400a436a  mov     ebx, eax
0x1400a436c  test    eax, eax
0x1400a436e  js      short loc_1400A437E
0x1400a4370  call    ?SpInitializeLimiter@@YAJXZ; SpInitializeLimiter(void)
0x1400a4375  xor     ecx, ecx
0x1400a4377  mov     [rsp+58h+arg_10], rcx
0x1400a437c  jmp     short loc_1400A4383
0x1400a437e  mov     rcx, [rsp+58h+arg_10]
0x1400a4383  test    rcx, rcx
0x1400a4386  jz      short loc_1400A43B8
0x1400a4388  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a438f  test    rax, rax
0x1400a4392  jz      short loc_1400A43A1
0x1400a4394  mov     rcx, rax; this
0x1400a4397  call    ??1SP_CONTROL@@QEAA@XZ; SP_CONTROL::~SP_CONTROL(void)
0x1400a439c  mov     rcx, [rsp+58h+arg_10]; DeviceObject
0x1400a43a1  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400a43ac  call    cs:__imp_IoDeleteDevice
0x1400a43b3  nop     dword ptr [rax+rax+00h]
0x1400a43b8  mov     rsi, [rsp+58h+arg_8]
0x1400a43bd  mov     eax, ebx
0x1400a43bf  mov     rbx, [rsp+58h+arg_0]
0x1400a43c4  add     rsp, 50h
0x1400a43c8  pop     rdi
0x1400a43c9  retn
```
