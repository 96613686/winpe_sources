# VmpStartDevice(VM_VOLUME_EXTENSION *)

- ea: `0x1400046a4`
- end: `0x1400047e9`
- name: `?VmpStartDevice@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x140016aa0`

## callees

- `0x140003eb0`
- `0x140004028`
- `0x1400046a4`
- `0x14000fd48`
- `0x140010014`
- `0x140010470`
- `0x140011920`
- `0x140012664`
- `0x14001541c`
- `0x140016990`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400047cf`
- `ntoskrnl!KeReleaseMutex` at `0x1400047cf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400046cd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400046cd`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400047b6`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400047b6`

## pseudocode

```c
__int64 __fastcall VmpStartDevice(struct VM_VOLUME_EXTENSION *a1)
{
  int v2; // edi
  struct _DEVICE_OBJECT *v3; // rcx
  int v4; // r8d
  int v5; // eax

  KeWaitForSingleObject((char *)VmRootExtension + 112, Executive, 0, 0, 0);
  if ( (unsigned __int8)VmpIsVolumeDead(a1) )
  {
    v2 = -1073741810;
    goto LABEL_16;
  }
  *((_BYTE *)a1 + 156) = 1;
  v3 = *(struct _DEVICE_OBJECT **)a1;
  *((_BYTE *)a1 + 157) = 1;
  VmpMarkDeleted(v3, 0);
  *(_DWORD *)(*(_QWORD *)a1 + 52LL) &= ~0x100u;
  v4 = *(_DWORD *)(*(_QWORD *)a1 + 52LL);
  if ( *((_BYTE *)a1 + 425) )
  {
    v5 = VmpApplyEspProtection(a1);
    goto LABEL_11;
  }
  if ( *((_BYTE *)a1 + 153) )
  {
    v5 = VmpApplyServiceProtection(a1);
    goto LABEL_11;
  }
  if ( ((v4 & 0x40000) != 0 || (v4 & 1) != 0) && (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x600100) == 0 )
  {
    v5 = VmpApplyHotplugProtection(a1);
LABEL_11:
    v2 = v5;
    if ( v5 < 0 )
      goto LABEL_16;
  }
  v2 = VmpInitializeInterfaces(a1);
  if ( v2 >= 0 )
  {
    VmpCreateLegacyNameLinks(a1, 0);
    if ( *((_BYTE *)a1 + 152) || (v2 = VmpRegisterDevice(*(_QWORD *)a1), v2 >= 0) )
    {
      VmpSetDevicePowerState(a1, PowerDeviceD0);
      IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)a1, PowerRelations);
    }
  }
LABEL_16:
  KeReleaseMutex((PRKMUTEX)VmRootExtension + 2, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400046a4  mov     [rsp+arg_0], rbx
0x1400046a9  push    rdi
0x1400046aa  sub     rsp, 30h
0x1400046ae  mov     rbx, rcx
0x1400046b1  mov     [rsp+38h+Timeout], 0; Timeout
0x1400046ba  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400046c1  xor     r9d, r9d; Alertable
0x1400046c4  add     rcx, 70h ; 'p'; Object
0x1400046c8  xor     r8d, r8d; WaitMode
0x1400046cb  xor     edx, edx; WaitReason
0x1400046cd  call    cs:__imp_KeWaitForSingleObject
0x1400046d4  nop     dword ptr [rax+rax+00h]
0x1400046d9  mov     rcx, rbx
0x1400046dc  call    VmpIsVolumeDead
0x1400046e1  test    al, al
0x1400046e3  jz      short loc_1400046EF
0x1400046e5  mov     edi, 0C000000Eh
0x1400046ea  jmp     loc_1400047C2
0x1400046ef  mov     byte ptr [rbx+9Ch], 1
0x1400046f6  xor     edx, edx; unsigned __int8
0x1400046f8  mov     rcx, [rbx]; struct _DEVICE_OBJECT *
0x1400046fb  mov     byte ptr [rbx+9Dh], 1
0x140004702  call    ?VmpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z; VmpMarkDeleted(_DEVICE_OBJECT *,uchar)
0x140004707  mov     rax, [rbx]
0x14000470a  mov     ecx, [rax+34h]
0x14000470d  mov     rax, [rbx]
0x140004710  btr     ecx, 8
0x140004714  mov     [rax+34h], ecx
0x140004717  mov     rax, [rbx]
0x14000471a  mov     ecx, [rax+30h]
0x14000471d  mov     rax, [rbx]
0x140004720  mov     r8d, [rax+34h]
0x140004724  mov     rax, [rbx]
0x140004727  mov     edx, [rax+34h]
0x14000472a  cmp     byte ptr [rbx+1A9h], 0
0x140004731  jz      short loc_14000473D
0x140004733  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140004736  call    ?VmpApplyEspProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpApplyEspProtection(VM_VOLUME_EXTENSION *)
0x14000473b  jmp     short loc_14000476C
0x14000473d  cmp     byte ptr [rbx+99h], 0
0x140004744  jz      short loc_140004750
0x140004746  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140004749  call    ?VmpApplyServiceProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpApplyServiceProtection(VM_VOLUME_EXTENSION *)
0x14000474e  jmp     short loc_14000476C
0x140004750  bt      r8d, 12h
0x140004755  jb      short loc_14000475C
0x140004757  test    dl, 1
0x14000475a  jz      short loc_140004772
0x14000475c  test    ecx, 600100h
0x140004762  jnz     short loc_140004772
0x140004764  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140004767  call    ?VmpApplyHotplugProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpApplyHotplugProtection(VM_VOLUME_EXTENSION *)
0x14000476c  mov     edi, eax
0x14000476e  test    eax, eax
0x140004770  js      short loc_1400047C2
0x140004772  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140004775  call    ?VmpInitializeInterfaces@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpInitializeInterfaces(VM_VOLUME_EXTENSION *)
0x14000477a  mov     edi, eax
0x14000477c  test    eax, eax
0x14000477e  js      short loc_1400047C2
0x140004780  xor     edx, edx; unsigned __int8
0x140004782  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140004785  call    ?VmpCreateLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpCreateLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x14000478a  cmp     byte ptr [rbx+98h], 0
0x140004791  jnz     short loc_1400047A1
0x140004793  mov     rcx, [rbx]
0x140004796  call    VmpRegisterDevice
0x14000479b  mov     edi, eax
0x14000479d  test    eax, eax
0x14000479f  js      short loc_1400047C2
0x1400047a1  mov     edx, 1; enum _DEVICE_POWER_STATE
0x1400047a6  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x1400047a9  call    ?VmpSetDevicePowerState@@YAXPEAVVM_VOLUME_EXTENSION@@W4_DEVICE_POWER_STATE@@@Z; VmpSetDevicePowerState(VM_VOLUME_EXTENSION *,_DEVICE_POWER_STATE)
0x1400047ae  mov     rcx, [rbx]; DeviceObject
0x1400047b1  mov     edx, 2; Type
0x1400047b6  call    cs:__imp_IoInvalidateDeviceRelations
0x1400047bd  nop     dword ptr [rax+rax+00h]
0x1400047c2  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400047c9  xor     edx, edx; Wait
0x1400047cb  add     rcx, 70h ; 'p'; Mutex
0x1400047cf  call    cs:__imp_KeReleaseMutex
0x1400047d6  nop     dword ptr [rax+rax+00h]
0x1400047db  mov     rbx, [rsp+38h+arg_0]
0x1400047e0  mov     eax, edi
0x1400047e2  add     rsp, 30h
0x1400047e6  pop     rdi
0x1400047e7  retn
```
