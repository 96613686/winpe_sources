# VmpSetPowerState(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140003000`
- end: `0x1400030c5`
- name: `?VmpSetPowerState@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003000`
- `0x1400030d0`
- `0x140003e70`
- `0x140003eb0`
- `0x140003ef0`
- `0x140005090`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140003063`
- `ntoskrnl!KeReleaseMutex` at `0x140003063`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003039`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003039`

## pseudocode

```c
__int64 __fastcall VmpSetPowerState(struct _KMUTANT *a1, struct _IRP *a2)
{
  struct _IRP *MasterIrp; // rdi
  struct VM_VOLUME_EXTENSION *ExtensionForBasicVolume; // rax

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x18 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  KeWaitForSingleObject(&a1[2], Executive, 0, 0, 0);
  ExtensionForBasicVolume = VmpFindExtensionForBasicVolume(*(struct _DEVICE_OBJECT **)&MasterIrp->Type);
  if ( ExtensionForBasicVolume )
  {
    VmpSetDevicePowerState(ExtensionForBasicVolume, (enum _DEVICE_POWER_STATE)MasterIrp->Flags);
  }
  else if ( *(_QWORD *)&a1[7].Header.Lock )
  {
    VmpRestoreExtensionDriver((__int64)a1);
    (*(void (__fastcall **)(PMDL, _QWORD, _QWORD))(*(_QWORD *)&a1[7].Header.Lock + 88LL))(
      MasterIrp->MdlAddress,
      *(_QWORD *)&MasterIrp->Type,
      MasterIrp->Flags);
    VmpPageExtensionDriver((__int64)a1);
  }
  KeReleaseMutex(a1 + 2, 0);
  return 0;
}

```

## disassembly

```asm
0x140003000  push    rsi
0x140003002  sub     rsp, 30h
0x140003006  mov     rax, [rdx+0B8h]
0x14000300d  mov     rsi, rcx
0x140003010  cmp     dword ptr [rax+10h], 18h
0x140003014  jb      short loc_140003082
0x140003016  mov     [rsp+38h+arg_0], rbx
0x14000301b  xor     r9d, r9d; Alertable
0x14000301e  mov     [rsp+38h+arg_8], rdi
0x140003023  xor     r8d, r8d; WaitMode
0x140003026  mov     rdi, [rdx+18h]
0x14000302a  add     rcx, 70h ; 'p'; Object
0x14000302e  xor     edx, edx; WaitReason
0x140003030  mov     [rsp+38h+Timeout], 0; Timeout
0x140003039  call    cs:__imp_KeWaitForSingleObject
0x140003040  nop     dword ptr [rax+rax+00h]
0x140003045  mov     rcx, [rdi]; struct _DEVICE_OBJECT *
0x140003048  call    ?VmpFindExtensionForBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpFindExtensionForBasicVolume(_DEVICE_OBJECT *)
0x14000304d  test    rax, rax
0x140003050  jz      short loc_14000308E
0x140003052  mov     edx, [rdi+10h]; enum _DEVICE_POWER_STATE
0x140003055  mov     rcx, rax; struct VM_VOLUME_EXTENSION *
0x140003058  call    ?VmpSetDevicePowerState@@YAXPEAVVM_VOLUME_EXTENSION@@W4_DEVICE_POWER_STATE@@@Z; VmpSetDevicePowerState(VM_VOLUME_EXTENSION *,_DEVICE_POWER_STATE)
0x14000305d  xor     edx, edx; Wait
0x14000305f  lea     rcx, [rsi+70h]; Mutex
0x140003063  call    cs:__imp_KeReleaseMutex
0x14000306a  nop     dword ptr [rax+rax+00h]
0x14000306f  mov     rbx, [rsp+38h+arg_0]
0x140003074  xor     eax, eax
0x140003076  mov     rdi, [rsp+38h+arg_8]
0x14000307b  add     rsp, 30h
0x14000307f  pop     rsi
0x140003080  retn
0x140003082  mov     eax, 0C000000Dh
0x140003087  add     rsp, 30h
0x14000308b  pop     rsi
0x14000308c  retn
0x14000308e  cmp     qword ptr [rsi+188h], 0
0x140003096  jz      short loc_14000305D
0x140003098  mov     rcx, rsi
0x14000309b  call    VmpRestoreExtensionDriver
0x1400030a0  mov     rax, [rsi+188h]
0x1400030a7  mov     r8d, [rdi+10h]
0x1400030ab  mov     rdx, [rdi]
0x1400030ae  mov     rcx, [rdi+8]
0x1400030b2  mov     rax, [rax+58h]
0x1400030b6  call    _guard_dispatch_icall
0x1400030bb  mov     rcx, rsi
0x1400030be  call    VmpPageExtensionDriver
0x1400030c3  jmp     short loc_14000305D
```
