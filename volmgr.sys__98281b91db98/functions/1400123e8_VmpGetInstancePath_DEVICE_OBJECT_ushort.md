# VmpGetInstancePath(_DEVICE_OBJECT *,ushort * *)

- ea: `0x1400123e8`
- end: `0x140012502`
- name: `?VmpGetInstancePath@@YAJPEAU_DEVICE_OBJECT@@PEAPEAG@Z`
- size: `282`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT Pdo, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000eba0`
- `0x140010ad8`
- `0x140010d7c`

## callees

- `0x1400123e8`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x140012440`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400124ca`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140012440`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400124ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124e6`
- `ntoskrnl!ExAllocatePool2` at `0x14001247e`
- `ntoskrnl!ExAllocatePool2` at `0x14001247e`

## pseudocode

```c
__int64 __fastcall VmpGetInstancePath(PDEVICE_OBJECT Pdo, unsigned __int16 **a2)
{
  NTSTATUS DevicePropertyData; // eax
  NTSTATUS v5; // ebx
  void *Data; // rdi
  ULONG RequiredSize; // [rsp+68h] [rbp+10h] BYREF
  ULONG Type; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  RequiredSize = 0;
  Type = 0;
  DevicePropertyData = IoGetDevicePropertyData(Pdo, &DEVPKEY_Device_InstanceId, 0, 0, 0, 0, &RequiredSize, &Type);
  v5 = 0;
  if ( DevicePropertyData != -1073741789 )
    v5 = DevicePropertyData;
  if ( RequiredSize )
  {
    if ( v5 >= 0 )
    {
      Data = (void *)ExAllocatePool2(66, RequiredSize, 538987862);
      if ( Data )
      {
        v5 = IoGetDevicePropertyData(Pdo, &DEVPKEY_Device_InstanceId, 0, 0, RequiredSize, Data, &RequiredSize, &Type);
        if ( v5 < 0 )
          ExFreePoolWithTag(Data, 0);
        else
          *a2 = (unsigned __int16 *)Data;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741820;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400123e8  mov     r11, rsp
0x1400123eb  mov     [r11+8], rbx
0x1400123ef  push    rbp
0x1400123f0  push    rsi
0x1400123f1  push    rdi
0x1400123f2  sub     rsp, 40h
0x1400123f6  lea     rax, [r11+18h]
0x1400123fa  mov     qword ptr [rdx], 0
0x140012401  mov     [r11-20h], rax
0x140012405  mov     rsi, rdx
0x140012408  lea     rax, [r11+10h]
0x14001240c  mov     [rsp+58h+arg_8], 0
0x140012414  mov     [r11-28h], rax
0x140012418  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x14001241f  mov     qword ptr [r11-30h], 0
0x140012427  xor     r9d, r9d; Flags
0x14001242a  xor     r8d, r8d; Lcid
0x14001242d  mov     [rsp+58h+Size], 0; Size
0x140012435  mov     rbp, rcx
0x140012438  mov     [rsp+58h+arg_10], 0
0x140012440  call    cs:__imp_IoGetDevicePropertyData
0x140012447  nop     dword ptr [rax+rax+00h]
0x14001244c  xor     ebx, ebx
0x14001244e  cmp     eax, 0C0000023h
0x140012453  cmovnz  ebx, eax
0x140012456  mov     eax, [rsp+58h+arg_8]
0x14001245a  test    eax, eax
0x14001245c  jnz     short loc_140012468
0x14001245e  mov     ebx, 0C0000004h
0x140012463  jmp     loc_1400124F2
0x140012468  test    ebx, ebx
0x14001246a  js      loc_1400124F2
0x140012470  mov     rdx, rax
0x140012473  mov     ecx, 42h ; 'B'
0x140012478  mov     r8d, 20204D56h
0x14001247e  call    cs:__imp_ExAllocatePool2
0x140012485  nop     dword ptr [rax+rax+00h]
0x14001248a  mov     rdi, rax
0x14001248d  test    rax, rax
0x140012490  jnz     short loc_140012499
0x140012492  mov     ebx, 0C000009Ah
0x140012497  jmp     short loc_1400124F2
0x140012499  lea     rax, [rsp+58h+arg_10]
0x14001249e  xor     r9d, r9d; Flags
0x1400124a1  mov     [rsp+58h+Type], rax; Type
0x1400124a6  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1400124ad  lea     rax, [rsp+58h+arg_8]
0x1400124b2  xor     r8d, r8d; Lcid
0x1400124b5  mov     [rsp+58h+RequiredSize], rax; RequiredSize
0x1400124ba  mov     rcx, rbp; Pdo
0x1400124bd  mov     eax, [rsp+58h+arg_8]
0x1400124c1  mov     [rsp+58h+Data], rdi; Data
0x1400124c6  mov     [rsp+58h+Size], eax; Size
0x1400124ca  call    cs:__imp_IoGetDevicePropertyData
0x1400124d1  nop     dword ptr [rax+rax+00h]
0x1400124d6  mov     ebx, eax
0x1400124d8  test    eax, eax
0x1400124da  js      short loc_1400124E1
0x1400124dc  mov     [rsi], rdi
0x1400124df  jmp     short loc_1400124F2
0x1400124e1  xor     edx, edx; Tag
0x1400124e3  mov     rcx, rdi; P
0x1400124e6  call    cs:__imp_ExFreePoolWithTag
0x1400124ed  nop     dword ptr [rax+rax+00h]
0x1400124f2  mov     eax, ebx
0x1400124f4  mov     rbx, [rsp+58h+arg_0]
0x1400124f9  add     rsp, 40h
0x1400124fd  pop     rdi
0x1400124fe  pop     rsi
0x1400124ff  pop     rbp
0x140012500  retn
```
