# IoDevObjCreateDeviceSecure

- ea: `0x140020e70`
- end: `0x140020ffb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140020e70`
- `0x140021004`
- `0x1400210fc`
- `0x140021df4`
- `0x140021f60`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140020fb8`
- `ntoskrnl!IoDeleteDevice` at `0x140020fb8`
- `ntoskrnl!IoCreateDevice` at `0x140020f89`
- `ntoskrnl!IoCreateDevice` at `0x140020f89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020fdc`

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
0x140020e70  mov     [rsp-38h+arg_18], r9d
0x140020e75  mov     [rsp-38h+DeviceExtensionSize], edx
0x140020e79  push    rbp
0x140020e7a  push    rbx
0x140020e7b  push    rdi
0x140020e7c  push    r12
0x140020e7e  push    r13
0x140020e80  push    r14
0x140020e82  push    r15
0x140020e84  mov     rbp, rsp
0x140020e87  sub     rsp, 70h
0x140020e8b  mov     r14, [rbp+arg_40]
0x140020e92  xor     ebx, ebx
0x140020e94  mov     r15d, [rbp+arg_20]
0x140020e98  xor     eax, eax
0x140020e9a  mov     [rbp+arg_10], rbx
0x140020e9e  xorps   xmm0, xmm0
0x140020ea1  mov     qword ptr [rbp+var_20], rax
0x140020ea5  mov     r13, r8
0x140020ea8  mov     [r14], rbx
0x140020eab  mov     r12, rcx
0x140020eae  mov     [rbp+arg_40], rbx
0x140020eb5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140020eb9  test    r8, r8
0x140020ebc  jnz     short loc_140020ECD
0x140020ebe  test    r15b, r15b
0x140020ec1  js      short loc_140020ECD
0x140020ec3  mov     eax, 0C000000Dh
0x140020ec8  jmp     loc_140020FEA
0x140020ecd  cmp     [rbp+arg_38], rbx
0x140020ed1  jz      short loc_140020EEB
0x140020ed3  mov     rcx, [rbp+arg_38]
0x140020ed7  lea     r8, [rbp+DeviceType]
0x140020edb  mov     rdx, r12
0x140020ede  call    PpRegStateReadCreateClassCreationSettings
0x140020ee3  test    eax, eax
0x140020ee5  js      loc_140020FEA
0x140020eeb  mov     edi, [rbp+DeviceType]
0x140020eee  test    dil, 2
0x140020ef2  jnz     short loc_140020F46
0x140020ef4  mov     rcx, [rbp+arg_30]
0x140020ef8  lea     r8, [rbp+arg_10]
0x140020efc  call    SeSddlSecurityDescriptorFromSDDL
0x140020f01  xor     ecx, ecx
0x140020f03  mov     ebx, eax
0x140020f05  test    eax, eax
0x140020f07  js      loc_140020FD0
0x140020f0d  lea     edx, [rcx+2]
0x140020f10  mov     rax, [rbp+arg_10]
0x140020f14  mov     edi, edx
0x140020f16  mov     [rbp+DeviceType], edx
0x140020f19  mov     qword ptr [rbp+DeviceType+8], rax
0x140020f1d  cmp     [rbp+arg_38], rcx
0x140020f21  jz      short loc_140020F46
0x140020f23  mov     [rbp+var_18], rdx
0x140020f27  lea     rdx, [rbp+var_18]
0x140020f2b  mov     [rbp+var_8], rcx
0x140020f2f  mov     rcx, [rbp+arg_38]
0x140020f33  mov     [rbp+var_10], rax
0x140020f37  call    PpRegStateUpdateStackCreationSettings
0x140020f3c  mov     ebx, eax
0x140020f3e  test    eax, eax
0x140020f40  js      loc_140020FD0
0x140020f46  mov     r9d, [rbp+arg_18]
0x140020f4a  test    dil, 1
0x140020f4e  movzx   ecx, [rbp+arg_28]
0x140020f52  mov     r8, r13; DeviceName
0x140020f55  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x140020f5a  test    dil, 4
0x140020f5e  movzx   eax, byte ptr [rbp+var_20+4]
0x140020f62  cmovnz  r15d, [rbp+var_20]
0x140020f67  test    dil, 8
0x140020f6b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x140020f6e  cmovnz  ecx, eax
0x140020f71  lea     rax, [rbp+arg_40]
0x140020f78  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x140020f7d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140020f81  mov     rcx, r12; DriverObject
0x140020f84  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140020f89  call    cs:__imp_IoCreateDevice
0x140020f90  nop     dword ptr [rax+rax+00h]
0x140020f95  mov     ebx, eax
0x140020f97  test    eax, eax
0x140020f99  js      short loc_140020FD0
0x140020f9b  mov     rcx, [rbp+arg_40]; Object
0x140020fa2  lea     rdx, [rbp+DeviceType]
0x140020fa6  call    IopDevObjApplyPostCreationSettings
0x140020fab  mov     ebx, eax
0x140020fad  test    eax, eax
0x140020faf  jns     short loc_140020FC6
0x140020fb1  mov     rcx, [rbp+arg_40]; DeviceObject
0x140020fb8  call    cs:__imp_IoDeleteDevice
0x140020fbf  nop     dword ptr [rax+rax+00h]
0x140020fc4  jmp     short loc_140020FD0
0x140020fc6  mov     rax, [rbp+arg_40]
0x140020fcd  mov     [r14], rax
0x140020fd0  test    dil, 2
0x140020fd4  jz      short loc_140020FE8
0x140020fd6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x140020fda  xor     edx, edx; Tag
0x140020fdc  call    cs:__imp_ExFreePoolWithTag
0x140020fe3  nop     dword ptr [rax+rax+00h]
0x140020fe8  mov     eax, ebx
0x140020fea  add     rsp, 70h
0x140020fee  pop     r15
0x140020ff0  pop     r14
0x140020ff2  pop     r13
0x140020ff4  pop     r12
0x140020ff6  pop     rdi
0x140020ff7  pop     rbx
0x140020ff8  pop     rbp
0x140020ff9  retn
```
