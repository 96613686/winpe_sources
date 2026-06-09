# SpMarkDeleted(_DEVICE_OBJECT *,uchar)

- ea: `0x1400a6144`
- end: `0x1400a627b`
- name: `?SpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400a71e4`
- `0x1400b85d0`

## callees

- `0x14002ce90`
- `0x1400a6144`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a61bc`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a61bc`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400a6171`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400a6171`
- `ntoskrnl!ZwClose` at `0x1400a61d4`
- `ntoskrnl!ZwClose` at `0x1400a61d4`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a61ae`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a61ae`

## string_xrefs

- `0x1400a6188`: `IsDeleted`

## pseudocode

```c
__int64 __fastcall SpMarkDeleted(struct _DEVICE_OBJECT *a1, char a2)
{
  NTSTATUS v3; // ebx
  NTSTATUS v4; // eax
  ULONG DeviceType; // ecx
  const char *v6; // r9
  int ValueData; // [rsp+50h] [rbp+18h] BYREF
  PCWSTR Path; // [rsp+58h] [rbp+20h] BYREF

  Path = 0;
  ValueData = 1;
  v3 = IoOpenDeviceRegistryKey(a1, 1u, 0x2001Fu, (PHANDLE)&Path);
  if ( v3 >= 0 )
  {
    if ( a2 )
      v4 = RtlWriteRegistryValue(0x40000000u, Path, L"IsDeleted", 4u, &ValueData, 4u);
    else
      v4 = RtlDeleteRegistryValue(0x40000000u, Path, L"IsDeleted");
    v3 = v4;
  }
  if ( Path )
    ZwClose((HANDLE)Path);
  if ( v3 >= 0 || v3 == -2147483643 || v3 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v6 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v6 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v6,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400a6144  mov     rax, rsp
0x1400a6147  mov     [rax+8], rbx
0x1400a614b  push    rdi
0x1400a614c  sub     rsp, 30h
0x1400a6150  mov     dil, dl
0x1400a6153  mov     qword ptr [rax+20h], 0
0x1400a615b  mov     edx, 1; DevInstKeyType
0x1400a6160  mov     dword ptr [rax+18h], 1
0x1400a6167  lea     r9, [rax+20h]; DeviceRegKey
0x1400a616b  mov     r8d, 2001Fh; DesiredAccess
0x1400a6171  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400a6178  nop     dword ptr [rax+rax+00h]
0x1400a617d  mov     ebx, eax
0x1400a617f  test    eax, eax
0x1400a6181  js      short loc_1400A61CA
0x1400a6183  mov     rdx, [rsp+38h+Path]; Path
0x1400a6188  lea     r8, ValueName; "IsDeleted"
0x1400a618f  mov     ecx, 40000000h; RelativeTo
0x1400a6194  test    dil, dil
0x1400a6197  jz      short loc_1400A61BC
0x1400a6199  mov     r9d, 4; ValueType
0x1400a619f  lea     rax, [rsp+38h+arg_10]
0x1400a61a4  mov     [rsp+38h+ValueLength], r9d; ValueLength
0x1400a61a9  mov     [rsp+38h+ValueData], rax; ValueData
0x1400a61ae  call    cs:__imp_RtlWriteRegistryValue
0x1400a61b5  nop     dword ptr [rax+rax+00h]
0x1400a61ba  jmp     short loc_1400A61C8
0x1400a61bc  call    cs:__imp_RtlDeleteRegistryValue
0x1400a61c3  nop     dword ptr [rax+rax+00h]
0x1400a61c8  mov     ebx, eax
0x1400a61ca  mov     rcx, [rsp+38h+Path]; Handle
0x1400a61cf  test    rcx, rcx
0x1400a61d2  jz      short loc_1400A61E0
0x1400a61d4  call    cs:__imp_ZwClose
0x1400a61db  nop     dword ptr [rax+rax+00h]
0x1400a61e0  test    ebx, ebx
0x1400a61e2  jns     short loc_1400A6213
0x1400a61e4  cmp     ebx, 80000005h
0x1400a61ea  jz      short loc_1400A6213
0x1400a61ec  cmp     ebx, 0C0000023h
0x1400a61f2  jz      short loc_1400A6213
0x1400a61f4  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a61fa  cmp     ecx, 1
0x1400a61fd  jz      short loc_1400A620A
0x1400a61ff  mov     ecx, 1
0x1400a6204  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a620a  lea     r9, aError; "Error"
0x1400a6211  jmp     short loc_1400A6230
0x1400a6213  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a6219  cmp     ecx, 3
0x1400a621c  jz      short loc_1400A6229
0x1400a621e  mov     ecx, 3
0x1400a6223  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a6229  lea     r9, aExit; "Exit "
0x1400a6230  mov     r10, cs:WPP_GLOBAL_Control
0x1400a6237  lea     rax, WPP_GLOBAL_Control
0x1400a623e  cmp     r10, rax
0x1400a6241  jz      short loc_1400A626D
0x1400a6243  mov     eax, [r10+2Ch]
0x1400a6247  test    al, 1
0x1400a6249  jz      short loc_1400A626D
0x1400a624b  movzx   eax, byte ptr [r10+29h]
0x1400a6250  cmp     eax, ecx
0x1400a6252  jb      short loc_1400A626D
0x1400a6254  mov     rcx, [r10+18h]
0x1400a6258  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a625f  mov     edx, 1Ch
0x1400a6264  mov     dword ptr [rsp+38h+ValueData], ebx
0x1400a6268  call    WPP_SF_sd
0x1400a626d  mov     eax, ebx
0x1400a626f  mov     rbx, [rsp+38h+arg_0]
0x1400a6274  add     rsp, 30h
0x1400a6278  pop     rdi
0x1400a6279  retn
```
