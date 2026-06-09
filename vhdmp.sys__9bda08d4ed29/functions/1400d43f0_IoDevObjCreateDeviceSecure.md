# IoDevObjCreateDeviceSecure

- ea: `0x1400d43f0`
- end: `0x1400d457b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400d3a84`
- `0x1400d43f0`
- `0x1400d4584`
- `0x1400d49f8`
- `0x1400d4b64`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400d4538`
- `ntoskrnl!IoDeleteDevice` at `0x1400d4538`
- `ntoskrnl!IoCreateDevice` at `0x1400d4509`
- `ntoskrnl!IoCreateDevice` at `0x1400d4509`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d455c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d455c`

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
0x1400d43f0  mov     [rsp-38h+arg_18], r9d
0x1400d43f5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400d43f9  push    rbp
0x1400d43fa  push    rbx
0x1400d43fb  push    rdi
0x1400d43fc  push    r12
0x1400d43fe  push    r13
0x1400d4400  push    r14
0x1400d4402  push    r15
0x1400d4404  mov     rbp, rsp
0x1400d4407  sub     rsp, 70h
0x1400d440b  mov     r14, [rbp+arg_40]
0x1400d4412  xor     ebx, ebx
0x1400d4414  mov     r15d, [rbp+arg_20]
0x1400d4418  xor     eax, eax
0x1400d441a  mov     [rbp+arg_10], rbx
0x1400d441e  xorps   xmm0, xmm0
0x1400d4421  mov     qword ptr [rbp+var_20], rax
0x1400d4425  mov     r13, r8
0x1400d4428  mov     [r14], rbx
0x1400d442b  mov     r12, rcx
0x1400d442e  mov     [rbp+arg_40], rbx
0x1400d4435  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400d4439  test    r8, r8
0x1400d443c  jnz     short loc_1400D444D
0x1400d443e  test    r15b, r15b
0x1400d4441  js      short loc_1400D444D
0x1400d4443  mov     eax, 0C000000Dh
0x1400d4448  jmp     loc_1400D456A
0x1400d444d  cmp     [rbp+arg_38], rbx
0x1400d4451  jz      short loc_1400D446B
0x1400d4453  mov     rcx, [rbp+arg_38]
0x1400d4457  lea     r8, [rbp+DeviceType]
0x1400d445b  mov     rdx, r12
0x1400d445e  call    PpRegStateReadCreateClassCreationSettings
0x1400d4463  test    eax, eax
0x1400d4465  js      loc_1400D456A
0x1400d446b  mov     edi, [rbp+DeviceType]
0x1400d446e  test    dil, 2
0x1400d4472  jnz     short loc_1400D44C6
0x1400d4474  mov     rcx, [rbp+arg_30]
0x1400d4478  lea     r8, [rbp+arg_10]
0x1400d447c  call    SeSddlSecurityDescriptorFromSDDL
0x1400d4481  xor     ecx, ecx
0x1400d4483  mov     ebx, eax
0x1400d4485  test    eax, eax
0x1400d4487  js      loc_1400D4550
0x1400d448d  lea     edx, [rcx+2]
0x1400d4490  mov     rax, [rbp+arg_10]
0x1400d4494  mov     edi, edx
0x1400d4496  mov     [rbp+DeviceType], edx
0x1400d4499  mov     qword ptr [rbp+DeviceType+8], rax
0x1400d449d  cmp     [rbp+arg_38], rcx
0x1400d44a1  jz      short loc_1400D44C6
0x1400d44a3  mov     [rbp+var_18], rdx
0x1400d44a7  lea     rdx, [rbp+var_18]
0x1400d44ab  mov     [rbp+var_8], rcx
0x1400d44af  mov     rcx, [rbp+arg_38]
0x1400d44b3  mov     [rbp+var_10], rax
0x1400d44b7  call    PpRegStateUpdateStackCreationSettings
0x1400d44bc  mov     ebx, eax
0x1400d44be  test    eax, eax
0x1400d44c0  js      loc_1400D4550
0x1400d44c6  mov     r9d, [rbp+arg_18]
0x1400d44ca  test    dil, 1
0x1400d44ce  movzx   ecx, [rbp+arg_28]
0x1400d44d2  mov     r8, r13; DeviceName
0x1400d44d5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x1400d44da  test    dil, 4
0x1400d44de  movzx   eax, byte ptr [rbp+var_20+4]
0x1400d44e2  cmovnz  r15d, [rbp+var_20]
0x1400d44e7  test    dil, 8
0x1400d44eb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400d44ee  cmovnz  ecx, eax
0x1400d44f1  lea     rax, [rbp+arg_40]
0x1400d44f8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400d44fd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400d4501  mov     rcx, r12; DriverObject
0x1400d4504  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400d4509  call    cs:__imp_IoCreateDevice
0x1400d4510  nop     dword ptr [rax+rax+00h]
0x1400d4515  mov     ebx, eax
0x1400d4517  test    eax, eax
0x1400d4519  js      short loc_1400D4550
0x1400d451b  mov     rcx, [rbp+arg_40]; Object
0x1400d4522  lea     rdx, [rbp+DeviceType]
0x1400d4526  call    IopDevObjApplyPostCreationSettings
0x1400d452b  mov     ebx, eax
0x1400d452d  test    eax, eax
0x1400d452f  jns     short loc_1400D4546
0x1400d4531  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400d4538  call    cs:__imp_IoDeleteDevice
0x1400d453f  nop     dword ptr [rax+rax+00h]
0x1400d4544  jmp     short loc_1400D4550
0x1400d4546  mov     rax, [rbp+arg_40]
0x1400d454d  mov     [r14], rax
0x1400d4550  test    dil, 2
0x1400d4554  jz      short loc_1400D4568
0x1400d4556  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400d455a  xor     edx, edx; Tag
0x1400d455c  call    cs:__imp_ExFreePoolWithTag
0x1400d4563  nop     dword ptr [rax+rax+00h]
0x1400d4568  mov     eax, ebx
0x1400d456a  add     rsp, 70h
0x1400d456e  pop     r15
0x1400d4570  pop     r14
0x1400d4572  pop     r13
0x1400d4574  pop     r12
0x1400d4576  pop     rdi
0x1400d4577  pop     rbx
0x1400d4578  pop     rbp
0x1400d4579  retn
```
