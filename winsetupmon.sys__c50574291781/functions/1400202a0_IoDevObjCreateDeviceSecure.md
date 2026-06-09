# IoDevObjCreateDeviceSecure

- ea: `0x1400202a0`
- end: `0x14002042b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400202a0`
- `0x140020434`
- `0x14002052c`
- `0x140021234`
- `0x1400213a0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400203e8`
- `ntoskrnl!IoDeleteDevice` at `0x1400203e8`
- `ntoskrnl!IoCreateDevice` at `0x1400203b9`
- `ntoskrnl!IoCreateDevice` at `0x1400203b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002040c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002040c`

## pseudocode

```c
__int64 __fastcall IoDevObjCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        ULONG a4,
        ULONG a5,
        BOOLEAN a6,
        __int64 a7,
        __int64 a8,
        PDEVICE_OBJECT DeviceObject)
{
  PDEVICE_OBJECT v9; // r14
  ULONG DeviceCharacteristics; // r15d
  __int64 result; // rax
  char v14; // di
  int updated; // ebx
  ULONG v16; // r9d
  BOOLEAN Exclusive; // cl
  ULONG DeviceType[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG v19[2]; // [rsp+50h] [rbp-20h]
  _QWORD v20[3]; // [rsp+58h] [rbp-18h] BYREF
  ULONG DeviceExtensionSize; // [rsp+B8h] [rbp+48h]
  __int64 v22; // [rsp+C0h] [rbp+50h] BYREF
  ULONG v23; // [rsp+C8h] [rbp+58h]

  v23 = a4;
  DeviceExtensionSize = a2;
  v9 = DeviceObject;
  DeviceCharacteristics = a5;
  v22 = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)&DeviceObject->Type = 0;
  DeviceObject = 0;
  *(_OWORD *)DeviceType = 0;
  if ( !a3 && (DeviceCharacteristics & 0x80u) == 0 )
    return 3221225485LL;
  if ( !a8 || (result = PpRegStateReadCreateClassCreationSettings(a8, DriverObject, DeviceType), (int)result >= 0) )
  {
    v14 = DeviceType[0];
    if ( (DeviceType[0] & 2) != 0 )
      goto LABEL_10;
    updated = SeSddlSecurityDescriptorFromSDDL(a7, a2, &v22);
    if ( updated >= 0 )
    {
      v14 = 2;
      DeviceType[0] = 2;
      *(_QWORD *)&DeviceType[2] = v22;
      if ( !a8
        || (v20[0] = 2,
            v20[2] = 0,
            v20[1] = v22,
            updated = PpRegStateUpdateStackCreationSettings(a8, (__int64)v20),
            updated >= 0) )
      {
LABEL_10:
        v16 = v23;
        Exclusive = a6;
        if ( (v14 & 1) != 0 )
          v16 = DeviceType[1];
        if ( (v14 & 4) != 0 )
          DeviceCharacteristics = v19[0];
        if ( (v14 & 8) != 0 )
          Exclusive = v19[1];
        updated = IoCreateDevice(
                    DriverObject,
                    DeviceExtensionSize,
                    a3,
                    v16,
                    DeviceCharacteristics,
                    Exclusive,
                    &DeviceObject);
        if ( updated >= 0 )
        {
          updated = IopDevObjApplyPostCreationSettings(DeviceObject);
          if ( updated >= 0 )
            *(_QWORD *)&v9->Type = DeviceObject;
          else
            IoDeleteDevice(DeviceObject);
        }
      }
    }
    if ( (v14 & 2) != 0 )
      ExFreePoolWithTag(*(PVOID *)&DeviceType[2], 0);
    return (unsigned int)updated;
  }
  return result;
}

```

## disassembly

```asm
0x1400202a0  mov     [rsp-38h+arg_18], r9d
0x1400202a5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400202a9  push    rbp
0x1400202aa  push    rbx
0x1400202ab  push    rdi
0x1400202ac  push    r12
0x1400202ae  push    r13
0x1400202b0  push    r14
0x1400202b2  push    r15
0x1400202b4  mov     rbp, rsp
0x1400202b7  sub     rsp, 70h
0x1400202bb  mov     r14, [rbp+arg_40]
0x1400202c2  xor     ebx, ebx
0x1400202c4  mov     r15d, [rbp+arg_20]
0x1400202c8  xor     eax, eax
0x1400202ca  mov     [rbp+arg_10], rbx
0x1400202ce  xorps   xmm0, xmm0
0x1400202d1  mov     qword ptr [rbp+var_20], rax
0x1400202d5  mov     r13, r8
0x1400202d8  mov     [r14], rbx
0x1400202db  mov     r12, rcx
0x1400202de  mov     [rbp+arg_40], rbx
0x1400202e5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400202e9  test    r8, r8
0x1400202ec  jnz     short loc_1400202FD
0x1400202ee  test    r15b, r15b
0x1400202f1  js      short loc_1400202FD
0x1400202f3  mov     eax, 0C000000Dh
0x1400202f8  jmp     loc_14002041A
0x1400202fd  cmp     [rbp+arg_38], rbx
0x140020301  jz      short loc_14002031B
0x140020303  mov     rcx, [rbp+arg_38]
0x140020307  lea     r8, [rbp+DeviceType]
0x14002030b  mov     rdx, r12
0x14002030e  call    PpRegStateReadCreateClassCreationSettings
0x140020313  test    eax, eax
0x140020315  js      loc_14002041A
0x14002031b  mov     edi, [rbp+DeviceType]
0x14002031e  test    dil, 2
0x140020322  jnz     short loc_140020376
0x140020324  mov     rcx, [rbp+arg_30]
0x140020328  lea     r8, [rbp+arg_10]
0x14002032c  call    SeSddlSecurityDescriptorFromSDDL
0x140020331  xor     ecx, ecx
0x140020333  mov     ebx, eax
0x140020335  test    eax, eax
0x140020337  js      loc_140020400
0x14002033d  lea     edx, [rcx+2]
0x140020340  mov     rax, [rbp+arg_10]
0x140020344  mov     edi, edx
0x140020346  mov     [rbp+DeviceType], edx
0x140020349  mov     qword ptr [rbp+DeviceType+8], rax
0x14002034d  cmp     [rbp+arg_38], rcx
0x140020351  jz      short loc_140020376
0x140020353  mov     [rbp+var_18], rdx
0x140020357  lea     rdx, [rbp+var_18]
0x14002035b  mov     [rbp+var_8], rcx
0x14002035f  mov     rcx, [rbp+arg_38]
0x140020363  mov     [rbp+var_10], rax
0x140020367  call    PpRegStateUpdateStackCreationSettings
0x14002036c  mov     ebx, eax
0x14002036e  test    eax, eax
0x140020370  js      loc_140020400
0x140020376  mov     r9d, [rbp+arg_18]
0x14002037a  test    dil, 1
0x14002037e  movzx   ecx, [rbp+arg_28]
0x140020382  mov     r8, r13; DeviceName
0x140020385  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14002038a  test    dil, 4
0x14002038e  movzx   eax, byte ptr [rbp+var_20+4]
0x140020392  cmovnz  r15d, [rbp+var_20]
0x140020397  test    dil, 8
0x14002039b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14002039e  cmovnz  ecx, eax
0x1400203a1  lea     rax, [rbp+arg_40]
0x1400203a8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400203ad  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400203b1  mov     rcx, r12; DriverObject
0x1400203b4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400203b9  call    cs:__imp_IoCreateDevice
0x1400203c0  nop     dword ptr [rax+rax+00h]
0x1400203c5  mov     ebx, eax
0x1400203c7  test    eax, eax
0x1400203c9  js      short loc_140020400
0x1400203cb  mov     rcx, [rbp+arg_40]; Object
0x1400203d2  lea     rdx, [rbp+DeviceType]
0x1400203d6  call    IopDevObjApplyPostCreationSettings
0x1400203db  mov     ebx, eax
0x1400203dd  test    eax, eax
0x1400203df  jns     short loc_1400203F6
0x1400203e1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400203e8  call    cs:__imp_IoDeleteDevice
0x1400203ef  nop     dword ptr [rax+rax+00h]
0x1400203f4  jmp     short loc_140020400
0x1400203f6  mov     rax, [rbp+arg_40]
0x1400203fd  mov     [r14], rax
0x140020400  test    dil, 2
0x140020404  jz      short loc_140020418
0x140020406  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14002040a  xor     edx, edx; Tag
0x14002040c  call    cs:__imp_ExFreePoolWithTag
0x140020413  nop     dword ptr [rax+rax+00h]
0x140020418  mov     eax, ebx
0x14002041a  add     rsp, 70h
0x14002041e  pop     r15
0x140020420  pop     r14
0x140020422  pop     r13
0x140020424  pop     r12
0x140020426  pop     rdi
0x140020427  pop     rbx
0x140020428  pop     rbp
0x140020429  retn
```
