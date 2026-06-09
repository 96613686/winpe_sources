# IoDevObjCreateDeviceSecure

- ea: `0x1400d4460`
- end: `0x1400d45eb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400d3af4`
- `0x1400d4460`
- `0x1400d45f4`
- `0x1400d4a68`
- `0x1400d4bd4`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400d45a8`
- `ntoskrnl!IoDeleteDevice` at `0x1400d45a8`
- `ntoskrnl!IoCreateDevice` at `0x1400d4579`
- `ntoskrnl!IoCreateDevice` at `0x1400d4579`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d45cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d45cc`

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
          updated = IopDevObjApplyPostCreationSettings(DeviceObject, (__int64)DeviceType);
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
0x1400d4460  mov     [rsp-38h+arg_18], r9d
0x1400d4465  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400d4469  push    rbp
0x1400d446a  push    rbx
0x1400d446b  push    rdi
0x1400d446c  push    r12
0x1400d446e  push    r13
0x1400d4470  push    r14
0x1400d4472  push    r15
0x1400d4474  mov     rbp, rsp
0x1400d4477  sub     rsp, 70h
0x1400d447b  mov     r14, [rbp+arg_40]
0x1400d4482  xor     ebx, ebx
0x1400d4484  mov     r15d, [rbp+arg_20]
0x1400d4488  xor     eax, eax
0x1400d448a  mov     [rbp+arg_10], rbx
0x1400d448e  xorps   xmm0, xmm0
0x1400d4491  mov     qword ptr [rbp+var_20], rax
0x1400d4495  mov     r13, r8
0x1400d4498  mov     [r14], rbx
0x1400d449b  mov     r12, rcx
0x1400d449e  mov     [rbp+arg_40], rbx
0x1400d44a5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400d44a9  test    r8, r8
0x1400d44ac  jnz     short loc_1400D44BD
0x1400d44ae  test    r15b, r15b
0x1400d44b1  js      short loc_1400D44BD
0x1400d44b3  mov     eax, 0C000000Dh
0x1400d44b8  jmp     loc_1400D45DA
0x1400d44bd  cmp     [rbp+arg_38], rbx
0x1400d44c1  jz      short loc_1400D44DB
0x1400d44c3  mov     rcx, [rbp+arg_38]
0x1400d44c7  lea     r8, [rbp+DeviceType]
0x1400d44cb  mov     rdx, r12
0x1400d44ce  call    PpRegStateReadCreateClassCreationSettings
0x1400d44d3  test    eax, eax
0x1400d44d5  js      loc_1400D45DA
0x1400d44db  mov     edi, [rbp+DeviceType]
0x1400d44de  test    dil, 2
0x1400d44e2  jnz     short loc_1400D4536
0x1400d44e4  mov     rcx, [rbp+arg_30]
0x1400d44e8  lea     r8, [rbp+arg_10]
0x1400d44ec  call    SeSddlSecurityDescriptorFromSDDL
0x1400d44f1  xor     ecx, ecx
0x1400d44f3  mov     ebx, eax
0x1400d44f5  test    eax, eax
0x1400d44f7  js      loc_1400D45C0
0x1400d44fd  lea     edx, [rcx+2]
0x1400d4500  mov     rax, [rbp+arg_10]
0x1400d4504  mov     edi, edx
0x1400d4506  mov     [rbp+DeviceType], edx
0x1400d4509  mov     qword ptr [rbp+DeviceType+8], rax
0x1400d450d  cmp     [rbp+arg_38], rcx
0x1400d4511  jz      short loc_1400D4536
0x1400d4513  mov     [rbp+var_18], rdx
0x1400d4517  lea     rdx, [rbp+var_18]
0x1400d451b  mov     [rbp+var_8], rcx
0x1400d451f  mov     rcx, [rbp+arg_38]
0x1400d4523  mov     [rbp+var_10], rax
0x1400d4527  call    PpRegStateUpdateStackCreationSettings
0x1400d452c  mov     ebx, eax
0x1400d452e  test    eax, eax
0x1400d4530  js      loc_1400D45C0
0x1400d4536  mov     r9d, [rbp+arg_18]
0x1400d453a  test    dil, 1
0x1400d453e  movzx   ecx, [rbp+arg_28]
0x1400d4542  mov     r8, r13; DeviceName
0x1400d4545  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x1400d454a  test    dil, 4
0x1400d454e  movzx   eax, byte ptr [rbp+var_20+4]
0x1400d4552  cmovnz  r15d, [rbp+var_20]
0x1400d4557  test    dil, 8
0x1400d455b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400d455e  cmovnz  ecx, eax
0x1400d4561  lea     rax, [rbp+arg_40]
0x1400d4568  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400d456d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400d4571  mov     rcx, r12; DriverObject
0x1400d4574  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400d4579  call    cs:__imp_IoCreateDevice
0x1400d4580  nop     dword ptr [rax+rax+00h]
0x1400d4585  mov     ebx, eax
0x1400d4587  test    eax, eax
0x1400d4589  js      short loc_1400D45C0
0x1400d458b  mov     rcx, [rbp+arg_40]; Object
0x1400d4592  lea     rdx, [rbp+DeviceType]
0x1400d4596  call    IopDevObjApplyPostCreationSettings
0x1400d459b  mov     ebx, eax
0x1400d459d  test    eax, eax
0x1400d459f  jns     short loc_1400D45B6
0x1400d45a1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400d45a8  call    cs:__imp_IoDeleteDevice
0x1400d45af  nop     dword ptr [rax+rax+00h]
0x1400d45b4  jmp     short loc_1400D45C0
0x1400d45b6  mov     rax, [rbp+arg_40]
0x1400d45bd  mov     [r14], rax
0x1400d45c0  test    dil, 2
0x1400d45c4  jz      short loc_1400D45D8
0x1400d45c6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400d45ca  xor     edx, edx; Tag
0x1400d45cc  call    cs:__imp_ExFreePoolWithTag
0x1400d45d3  nop     dword ptr [rax+rax+00h]
0x1400d45d8  mov     eax, ebx
0x1400d45da  add     rsp, 70h
0x1400d45de  pop     r15
0x1400d45e0  pop     r14
0x1400d45e2  pop     r13
0x1400d45e4  pop     r12
0x1400d45e6  pop     rdi
0x1400d45e7  pop     rbx
0x1400d45e8  pop     rbp
0x1400d45e9  retn
```
