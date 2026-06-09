# IoDevObjCreateDeviceSecure

- ea: `0x1400180b0`
- end: `0x14001823b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, __int64, struct _UNICODE_STRING *, ULONG, ULONG, BOOLEAN, __int64, __int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400180b0`
- `0x140018244`
- `0x14001833c`
- `0x140019034`
- `0x1400191a0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400181f8`
- `ntoskrnl!IoDeleteDevice` at `0x1400181f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001821c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001821c`
- `ntoskrnl!IoCreateDevice` at `0x1400181c9`
- `ntoskrnl!IoCreateDevice` at `0x1400181c9`

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
  NTSTATUS updated; // ebx
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
        || (v20[0] = 2, v20[2] = 0, v20[1] = v22, updated = PpRegStateUpdateStackCreationSettings(a8, v20), updated >= 0) )
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
0x1400180b0  mov     [rsp-38h+arg_18], r9d
0x1400180b5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400180b9  push    rbp
0x1400180ba  push    rbx
0x1400180bb  push    rdi
0x1400180bc  push    r12
0x1400180be  push    r13
0x1400180c0  push    r14
0x1400180c2  push    r15
0x1400180c4  mov     rbp, rsp
0x1400180c7  sub     rsp, 70h
0x1400180cb  mov     r14, [rbp+arg_40]
0x1400180d2  xor     ebx, ebx
0x1400180d4  mov     r15d, [rbp+arg_20]
0x1400180d8  xor     eax, eax
0x1400180da  mov     [rbp+arg_10], rbx
0x1400180de  xorps   xmm0, xmm0
0x1400180e1  mov     qword ptr [rbp+var_20], rax
0x1400180e5  mov     r13, r8
0x1400180e8  mov     [r14], rbx
0x1400180eb  mov     r12, rcx
0x1400180ee  mov     [rbp+arg_40], rbx
0x1400180f5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400180f9  test    r8, r8
0x1400180fc  jnz     short loc_14001810D
0x1400180fe  test    r15b, r15b
0x140018101  js      short loc_14001810D
0x140018103  mov     eax, 0C000000Dh
0x140018108  jmp     loc_14001822A
0x14001810d  cmp     [rbp+arg_38], rbx
0x140018111  jz      short loc_14001812B
0x140018113  mov     rcx, [rbp+arg_38]
0x140018117  lea     r8, [rbp+DeviceType]
0x14001811b  mov     rdx, r12
0x14001811e  call    PpRegStateReadCreateClassCreationSettings
0x140018123  test    eax, eax
0x140018125  js      loc_14001822A
0x14001812b  mov     edi, [rbp+DeviceType]
0x14001812e  test    dil, 2
0x140018132  jnz     short loc_140018186
0x140018134  mov     rcx, [rbp+arg_30]
0x140018138  lea     r8, [rbp+arg_10]
0x14001813c  call    SeSddlSecurityDescriptorFromSDDL
0x140018141  xor     ecx, ecx
0x140018143  mov     ebx, eax
0x140018145  test    eax, eax
0x140018147  js      loc_140018210
0x14001814d  lea     edx, [rcx+2]
0x140018150  mov     rax, [rbp+arg_10]
0x140018154  mov     edi, edx
0x140018156  mov     [rbp+DeviceType], edx
0x140018159  mov     qword ptr [rbp+DeviceType+8], rax
0x14001815d  cmp     [rbp+arg_38], rcx
0x140018161  jz      short loc_140018186
0x140018163  mov     [rbp+var_18], rdx
0x140018167  lea     rdx, [rbp+var_18]
0x14001816b  mov     [rbp+var_8], rcx
0x14001816f  mov     rcx, [rbp+arg_38]
0x140018173  mov     [rbp+var_10], rax
0x140018177  call    PpRegStateUpdateStackCreationSettings
0x14001817c  mov     ebx, eax
0x14001817e  test    eax, eax
0x140018180  js      loc_140018210
0x140018186  mov     r9d, [rbp+arg_18]
0x14001818a  test    dil, 1
0x14001818e  movzx   ecx, [rbp+arg_28]
0x140018192  mov     r8, r13; DeviceName
0x140018195  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14001819a  test    dil, 4
0x14001819e  movzx   eax, byte ptr [rbp+var_20+4]
0x1400181a2  cmovnz  r15d, [rbp+var_20]
0x1400181a7  test    dil, 8
0x1400181ab  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400181ae  cmovnz  ecx, eax
0x1400181b1  lea     rax, [rbp+arg_40]
0x1400181b8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400181bd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400181c1  mov     rcx, r12; DriverObject
0x1400181c4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400181c9  call    cs:__imp_IoCreateDevice
0x1400181d0  nop     dword ptr [rax+rax+00h]
0x1400181d5  mov     ebx, eax
0x1400181d7  test    eax, eax
0x1400181d9  js      short loc_140018210
0x1400181db  mov     rcx, [rbp+arg_40]; Object
0x1400181e2  lea     rdx, [rbp+DeviceType]
0x1400181e6  call    IopDevObjApplyPostCreationSettings
0x1400181eb  mov     ebx, eax
0x1400181ed  test    eax, eax
0x1400181ef  jns     short loc_140018206
0x1400181f1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400181f8  call    cs:__imp_IoDeleteDevice
0x1400181ff  nop     dword ptr [rax+rax+00h]
0x140018204  jmp     short loc_140018210
0x140018206  mov     rax, [rbp+arg_40]
0x14001820d  mov     [r14], rax
0x140018210  test    dil, 2
0x140018214  jz      short loc_140018228
0x140018216  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14001821a  xor     edx, edx; Tag
0x14001821c  call    cs:__imp_ExFreePoolWithTag
0x140018223  nop     dword ptr [rax+rax+00h]
0x140018228  mov     eax, ebx
0x14001822a  add     rsp, 70h
0x14001822e  pop     r15
0x140018230  pop     r14
0x140018232  pop     r13
0x140018234  pop     r12
0x140018236  pop     rdi
0x140018237  pop     rbx
0x140018238  pop     rbp
0x140018239  retn
```
