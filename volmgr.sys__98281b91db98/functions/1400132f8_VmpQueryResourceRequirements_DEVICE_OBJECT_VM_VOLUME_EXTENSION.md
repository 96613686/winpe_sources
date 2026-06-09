# VmpQueryResourceRequirements(_DEVICE_OBJECT *,VM_VOLUME_EXTENSION *)

- ea: `0x1400132f8`
- end: `0x140013421`
- name: `?VmpQueryResourceRequirements@@YAJPEAU_DEVICE_OBJECT@@PEAVVM_VOLUME_EXTENSION@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT Pdo, struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140016aa0`

## callees

- `0x140003170`
- `0x140003990`
- `0x140005090`
- `0x14001072c`
- `0x1400132f8`
- `0x140016990`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x1400133f4`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1400133f4`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400133b7`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400133b7`

## pseudocode

```c
__int64 __fastcall VmpQueryResourceRequirements(PDEVICE_OBJECT Pdo, struct VM_VOLUME_EXTENSION *a2)
{
  __int64 v2; // rsi
  struct VM_VOLUME_EXTENSION *v5; // rcx
  NTSTATUS v6; // ebx
  NTSTATUS DevicePropertyData; // eax
  int Data; // [rsp+68h] [rbp+10h] BYREF
  ULONG Type; // [rsp+70h] [rbp+18h] BYREF
  ULONG RequiredSize; // [rsp+78h] [rbp+20h] BYREF

  v2 = *((_QWORD *)a2 + 1);
  Data = 0;
  RequiredSize = 0;
  Type = 0;
  VmpAcquireDevices((struct VM_ROOT_EXTENSION *)v2);
  if ( (unsigned __int8)VmpIsVolumeDead(a2) )
  {
    v6 = -1073741810;
  }
  else
  {
    v6 = VmpApplySessionId(v5);
    if ( v6 >= 0 )
    {
      if ( *((_BYTE *)a2 + 426) )
        DevicePropertyData = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)(v2 + 392) + 168LL))(
                               *((_QWORD *)a2 + 54),
                               &Data);
      else
        DevicePropertyData = IoGetDevicePropertyData(
                               *((PDEVICE_OBJECT *)a2 + 45),
                               &DEVPKEY_Device_Numa_Node,
                               0,
                               0,
                               4u,
                               &Data,
                               &RequiredSize,
                               &Type);
      if ( DevicePropertyData >= 0 )
      {
        v6 = IoSetDevicePropertyData(Pdo, &DEVPKEY_Device_Numa_Node, 0, 1u, 7u, 4u, &Data);
        if ( v6 < 0 )
          v6 = 0;
      }
      else
      {
        v6 = 0;
      }
    }
  }
  VmpReleaseDevices((struct _KMUTANT *)v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400132f8  mov     rax, rsp
0x1400132fb  mov     [rax+8], rbx
0x1400132ff  push    rbp
0x140013300  push    rsi
0x140013301  push    rdi
0x140013302  sub     rsp, 40h
0x140013306  mov     rsi, [rdx+8]
0x14001330a  mov     rbp, rcx
0x14001330d  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x140013310  mov     dword ptr [rax+10h], 0
0x140013317  mov     rdi, rdx
0x14001331a  mov     dword ptr [rax+20h], 0
0x140013321  mov     dword ptr [rax+18h], 0
0x140013328  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14001332d  mov     rcx, rdi
0x140013330  call    VmpIsVolumeDead
0x140013335  test    al, al
0x140013337  jz      short loc_140013343
0x140013339  mov     ebx, 0C000000Eh
0x14001333e  jmp     loc_140013409
0x140013343  call    ?VmpApplySessionId@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpApplySessionId(VM_VOLUME_EXTENSION *)
0x140013348  mov     ebx, eax
0x14001334a  test    eax, eax
0x14001334c  js      loc_140013409
0x140013352  cmp     byte ptr [rdi+1AAh], 0
0x140013359  mov     ebx, 4
0x14001335e  jz      short loc_140013381
0x140013360  mov     rax, [rsi+188h]
0x140013367  lea     rdx, [rsp+58h+arg_8]
0x14001336c  mov     rcx, [rdi+1B0h]
0x140013373  mov     rax, [rax+0A8h]
0x14001337a  call    _guard_dispatch_icall
0x14001337f  jmp     short loc_1400133C3
0x140013381  mov     rcx, [rdi+168h]; Pdo
0x140013388  lea     rax, [rsp+58h+arg_10]
0x14001338d  mov     [rsp+58h+Type], rax; Type
0x140013392  lea     rdx, DEVPKEY_Device_Numa_Node; PropertyKey
0x140013399  lea     rax, [rsp+58h+arg_18]
0x14001339e  xor     r9d, r9d; Flags
0x1400133a1  mov     [rsp+58h+RequiredSize], rax; RequiredSize
0x1400133a6  xor     r8d, r8d; Lcid
0x1400133a9  lea     rax, [rsp+58h+arg_8]
0x1400133ae  mov     [rsp+58h+Data], rax; Data
0x1400133b3  mov     [rsp+58h+Size], ebx; Size
0x1400133b7  call    cs:__imp_IoGetDevicePropertyData
0x1400133be  nop     dword ptr [rax+rax+00h]
0x1400133c3  test    eax, eax
0x1400133c5  jns     short loc_1400133CB
0x1400133c7  xor     ebx, ebx
0x1400133c9  jmp     short loc_140013409
0x1400133cb  lea     rax, [rsp+58h+arg_8]
0x1400133d0  mov     r9d, 1; Flags
0x1400133d6  mov     [rsp+58h+RequiredSize], rax; Data
0x1400133db  lea     rdx, DEVPKEY_Device_Numa_Node; PropertyKey
0x1400133e2  mov     dword ptr [rsp+58h+Data], ebx; Size
0x1400133e6  xor     r8d, r8d; Lcid
0x1400133e9  mov     rcx, rbp; Pdo
0x1400133ec  mov     [rsp+58h+Size], 7; Type
0x1400133f4  call    cs:__imp_IoSetDevicePropertyData
0x1400133fb  nop     dword ptr [rax+rax+00h]
0x140013400  mov     ebx, eax
0x140013402  xor     eax, eax
0x140013404  test    ebx, ebx
0x140013406  cmovs   ebx, eax
0x140013409  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14001340c  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013411  mov     eax, ebx
0x140013413  mov     rbx, [rsp+58h+arg_0]
0x140013418  add     rsp, 40h
0x14001341c  pop     rdi
0x14001341d  pop     rsi
0x14001341e  pop     rbp
0x14001341f  retn
```
