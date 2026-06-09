# SpMarkDeleted(_DEVICE_OBJECT *,uchar)

- ea: `0x1400a6014`
- end: `0x1400a614b`
- name: `?SpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400a70b4`
- `0x1400b8430`

## callees

- `0x14002ce90`
- `0x1400a6014`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a608c`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a608c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400a6041`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400a6041`
- `ntoskrnl!ZwClose` at `0x1400a60a4`
- `ntoskrnl!ZwClose` at `0x1400a60a4`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a607e`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a607e`

## string_xrefs

- `0x1400a6058`: `IsDeleted`

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
0x1400a6014  mov     rax, rsp
0x1400a6017  mov     [rax+8], rbx
0x1400a601b  push    rdi
0x1400a601c  sub     rsp, 30h
0x1400a6020  mov     dil, dl
0x1400a6023  mov     qword ptr [rax+20h], 0
0x1400a602b  mov     edx, 1; DevInstKeyType
0x1400a6030  mov     dword ptr [rax+18h], 1
0x1400a6037  lea     r9, [rax+20h]; DeviceRegKey
0x1400a603b  mov     r8d, 2001Fh; DesiredAccess
0x1400a6041  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400a6048  nop     dword ptr [rax+rax+00h]
0x1400a604d  mov     ebx, eax
0x1400a604f  test    eax, eax
0x1400a6051  js      short loc_1400A609A
0x1400a6053  mov     rdx, [rsp+38h+Path]; Path
0x1400a6058  lea     r8, ValueName; "IsDeleted"
0x1400a605f  mov     ecx, 40000000h; RelativeTo
0x1400a6064  test    dil, dil
0x1400a6067  jz      short loc_1400A608C
0x1400a6069  mov     r9d, 4; ValueType
0x1400a606f  lea     rax, [rsp+38h+arg_10]
0x1400a6074  mov     [rsp+38h+ValueLength], r9d; ValueLength
0x1400a6079  mov     [rsp+38h+ValueData], rax; ValueData
0x1400a607e  call    cs:__imp_RtlWriteRegistryValue
0x1400a6085  nop     dword ptr [rax+rax+00h]
0x1400a608a  jmp     short loc_1400A6098
0x1400a608c  call    cs:__imp_RtlDeleteRegistryValue
0x1400a6093  nop     dword ptr [rax+rax+00h]
0x1400a6098  mov     ebx, eax
0x1400a609a  mov     rcx, [rsp+38h+Path]; Handle
0x1400a609f  test    rcx, rcx
0x1400a60a2  jz      short loc_1400A60B0
0x1400a60a4  call    cs:__imp_ZwClose
0x1400a60ab  nop     dword ptr [rax+rax+00h]
0x1400a60b0  test    ebx, ebx
0x1400a60b2  jns     short loc_1400A60E3
0x1400a60b4  cmp     ebx, 80000005h
0x1400a60ba  jz      short loc_1400A60E3
0x1400a60bc  cmp     ebx, 0C0000023h
0x1400a60c2  jz      short loc_1400A60E3
0x1400a60c4  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a60ca  cmp     ecx, 1
0x1400a60cd  jz      short loc_1400A60DA
0x1400a60cf  mov     ecx, 1
0x1400a60d4  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a60da  lea     r9, aError; "Error"
0x1400a60e1  jmp     short loc_1400A6100
0x1400a60e3  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a60e9  cmp     ecx, 3
0x1400a60ec  jz      short loc_1400A60F9
0x1400a60ee  mov     ecx, 3
0x1400a60f3  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a60f9  lea     r9, aExit; "Exit "
0x1400a6100  mov     r10, cs:WPP_GLOBAL_Control
0x1400a6107  lea     rax, WPP_GLOBAL_Control
0x1400a610e  cmp     r10, rax
0x1400a6111  jz      short loc_1400A613D
0x1400a6113  mov     eax, [r10+2Ch]
0x1400a6117  test    al, 1
0x1400a6119  jz      short loc_1400A613D
0x1400a611b  movzx   eax, byte ptr [r10+29h]
0x1400a6120  cmp     eax, ecx
0x1400a6122  jb      short loc_1400A613D
0x1400a6124  mov     rcx, [r10+18h]
0x1400a6128  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a612f  mov     edx, 1Ch
0x1400a6134  mov     dword ptr [rsp+38h+ValueData], ebx
0x1400a6138  call    WPP_SF_sd
0x1400a613d  mov     eax, ebx
0x1400a613f  mov     rbx, [rsp+38h+arg_0]
0x1400a6144  add     rsp, 30h
0x1400a6148  pop     rdi
0x1400a6149  retn
```
