# FilterRegisterDevice

- ea: `0x14000ca14`
- end: `0x14000cc60`
- name: `FilterRegisterDevice`
- size: `588`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400027d0`
- `0x140019078`

## callees

- `0x14000ca14`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000e0b4`
- `0x14000e158`
- `0x14000f110`
- `0x14000f500`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cae0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000caf8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb10`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cae0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000caf8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb10`
- `NDIS!NdisGetDeviceReservedExtension` at `0x14000cbeb`
- `NDIS!NdisGetDeviceReservedExtension` at `0x14000cbeb`
- `NDIS!NdisRegisterDeviceEx` at `0x14000cb78`
- `NDIS!NdisRegisterDeviceEx` at `0x14000cb78`

## pseudocode

```c
__int64 FilterRegisterDevice()
{
  unsigned int v0; // ebx
  PDEVICE_OBJECT v1; // rcx
  __int64 v2; // rdx
  _QWORD *DeviceReservedExtension; // rax
  _NDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v7; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v8; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v9[28]; // [rsp+90h] [rbp-70h] BYREF

  DestinationString = 0;
  v7 = 0;
  memset(v9, 0, sizeof(v9));
  memset(&DeviceObjectAttributes, 0, 52);
  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  memset(v9, 0, sizeof(v9));
  v9[0] = &FilterDispatch;
  v9[18] = &FilterDispatch;
  v9[2] = &FilterDispatch;
  v9[14] = FilterDeviceIoControl;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\vwififlt");
  RtlInitUnicodeString(&v7, L"\\DosDevices\\vwififlt");
  RtlInitUnicodeString(&v8, L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GR;;;LS)");
  DeviceObjectAttributes.DeviceName = &DestinationString;
  *(_QWORD *)&DeviceObjectAttributes.Header.Type = 3670405;
  DeviceObjectAttributes.SymbolicName = &v7;
  *(_QWORD *)&DeviceObjectAttributes.ExtensionSize = 16;
  DeviceObjectAttributes.MajorFunctions = (PDRIVER_DISPATCH *)v9;
  DeviceObjectAttributes.DeviceClassGuid = 0;
  DeviceObjectAttributes.DefaultSDDLString = &v8;
  v0 = NdisRegisterDeviceEx(
         WPP_MAIN_CB.DeviceExtension,
         &DeviceObjectAttributes,
         &DeviceObject,
         &NdisFilterDeviceHandle);
  if ( !v0 )
  {
    v0 = WwanSetDeviceObjectDacl();
    if ( !v0 )
    {
      DeviceReservedExtension = NdisGetDeviceReservedExtension(DeviceObject);
      *(_DWORD *)DeviceReservedExtension = 1179927634;
      DeviceReservedExtension[1] = WPP_MAIN_CB.DeviceExtension;
      goto LABEL_14;
    }
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_14;
      v2 = 40;
      goto LABEL_8;
    }
LABEL_18:
    FilterDeregisterDevice();
    return v0;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v2 = 39;
LABEL_8:
    WPP_SF_d(v1->AttachedDevice, v2, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  if ( v0 )
    goto LABEL_18;
  return v0;
}

```

## disassembly

```asm
0x14000ca14  mov     [rsp-8+arg_0], rbx
0x14000ca19  mov     [rsp-8+arg_8], rsi
0x14000ca1e  push    rbp
0x14000ca1f  lea     rbp, [rsp-80h]
0x14000ca24  sub     rsp, 180h
0x14000ca2b  mov     rax, cs:__security_cookie
0x14000ca32  xor     rax, rsp
0x14000ca35  mov     [rbp+80h+var_10], rax
0x14000ca39  xorps   xmm0, xmm0
0x14000ca3c  lea     rcx, [rbp+80h+var_F0]; void *
0x14000ca40  xorps   xmm1, xmm1
0x14000ca43  mov     ebx, 0E0h
0x14000ca48  mov     r8d, ebx; Size
0x14000ca4b  xor     edx, edx; Val
0x14000ca4d  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x14000ca52  movups  xmmword ptr [rsp+180h+var_118.Length], xmm1
0x14000ca57  call    memset
0x14000ca5c  xorps   xmm0, xmm0
0x14000ca5f  xor     eax, eax
0x14000ca61  movups  xmmword ptr [rsp+180h+DeviceObjectAttributes.Header.Type], xmm0
0x14000ca66  mov     dword ptr [rsp+180h+DeviceObjectAttributes.DeviceClassGuid], eax
0x14000ca6a  movups  xmmword ptr [rsp+180h+DeviceObjectAttributes.SymbolicName], xmm0
0x14000ca6f  movups  xmmword ptr [rsp+180h+DeviceObjectAttributes.ExtensionSize], xmm0
0x14000ca74  movups  xmmword ptr [rsp+180h+var_108.Length], xmm0
0x14000ca79  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca80  lea     rsi, WPP_GLOBAL_Control
0x14000ca87  cmp     rcx, rsi
0x14000ca8a  jz      short loc_14000CAA8
0x14000ca8c  mov     eax, [rcx+2Ch]
0x14000ca8f  test    al, 20h
0x14000ca91  jz      short loc_14000CAA8
0x14000ca93  mov     rcx, [rcx+18h]
0x14000ca97  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000ca9e  mov     edx, 26h ; '&'
0x14000caa3  call    WPP_SF_
0x14000caa8  mov     r8, rbx; Size
0x14000caab  lea     rcx, [rbp+80h+var_F0]; void *
0x14000caaf  xor     edx, edx; Val
0x14000cab1  call    memset
0x14000cab6  lea     rax, FilterDispatch
0x14000cabd  mov     [rbp+80h+var_F0], rax
0x14000cac1  lea     rdx, SourceString; "\\Device\\vwififlt"
0x14000cac8  mov     [rbp+80h+var_60], rax
0x14000cacc  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x14000cad1  mov     [rbp+80h+var_E0], rax
0x14000cad5  lea     rax, FilterDeviceIoControl
0x14000cadc  mov     [rbp+80h+var_80], rax
0x14000cae0  call    cs:__imp_RtlInitUnicodeString
0x14000cae7  nop     dword ptr [rax+rax+00h]
0x14000caec  lea     rdx, aDosdevicesVwif; "\\DosDevices\\vwififlt"
0x14000caf3  lea     rcx, [rsp+180h+var_118]; DestinationString
0x14000caf8  call    cs:__imp_RtlInitUnicodeString
0x14000caff  nop     dword ptr [rax+rax+00h]
0x14000cb04  lea     rdx, aDPAGaBaAGaSyAG; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GR;;;LS)"
0x14000cb0b  lea     rcx, [rsp+180h+var_108]; DestinationString
0x14000cb10  call    cs:__imp_RtlInitUnicodeString
0x14000cb17  nop     dword ptr [rax+rax+00h]
0x14000cb1c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; NdisHandle
0x14000cb23  lea     rax, [rsp+180h+DestinationString]
0x14000cb28  mov     [rsp+180h+DeviceObjectAttributes.DeviceName], rax
0x14000cb2d  lea     r9, NdisFilterDeviceHandle; NdisDeviceHandle
0x14000cb34  lea     rax, [rsp+180h+var_118]
0x14000cb39  mov     qword ptr [rsp+180h+DeviceObjectAttributes.Header.Type], 380185h
0x14000cb42  mov     [rsp+180h+DeviceObjectAttributes.SymbolicName], rax
0x14000cb47  lea     r8, DeviceObject; pDeviceObject
0x14000cb4e  lea     rax, [rbp+80h+var_F0]
0x14000cb52  mov     qword ptr [rsp+180h+DeviceObjectAttributes.ExtensionSize], 10h
0x14000cb5b  mov     [rsp+180h+DeviceObjectAttributes.MajorFunctions], rax
0x14000cb60  lea     rdx, [rsp+180h+DeviceObjectAttributes]; DeviceObjectAttributes
0x14000cb65  lea     rax, [rsp+180h+var_108]
0x14000cb6a  mov     [rsp+180h+DeviceObjectAttributes.DeviceClassGuid], 0
0x14000cb73  mov     [rsp+180h+DeviceObjectAttributes.DefaultSDDLString], rax
0x14000cb78  call    cs:__imp_NdisRegisterDeviceEx
0x14000cb7f  nop     dword ptr [rax+rax+00h]
0x14000cb84  mov     ebx, eax
0x14000cb86  test    eax, eax
0x14000cb88  jz      short loc_14000CBBC
0x14000cb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb91  cmp     rcx, rsi
0x14000cb94  jz      loc_14000CC37
0x14000cb9a  mov     edx, [rcx+2Ch]
0x14000cb9d  test    dl, 1
0x14000cba0  jz      short loc_14000CC08
0x14000cba2  mov     edx, 27h ; '''
0x14000cba7  mov     r9d, eax
0x14000cbaa  mov     rcx, [rcx+18h]
0x14000cbae  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000cbb5  call    WPP_SF_d
0x14000cbba  jmp     short loc_14000CC08
0x14000cbbc  call    WwanSetDeviceObjectDacl
0x14000cbc1  mov     ebx, eax
0x14000cbc3  test    eax, eax
0x14000cbc5  jz      short loc_14000CBE4
0x14000cbc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbce  cmp     rcx, rsi
0x14000cbd1  jz      short loc_14000CC37
0x14000cbd3  mov     eax, [rcx+2Ch]
0x14000cbd6  test    al, 1
0x14000cbd8  jz      short loc_14000CC08
0x14000cbda  mov     edx, 28h ; '('
0x14000cbdf  mov     r9d, ebx
0x14000cbe2  jmp     short loc_14000CBAA
0x14000cbe4  mov     rcx, cs:DeviceObject; DeviceObject
0x14000cbeb  call    cs:__imp_NdisGetDeviceReservedExtension
0x14000cbf2  nop     dword ptr [rax+rax+00h]
0x14000cbf7  mov     dword ptr [rax], 46544452h
0x14000cbfd  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000cc04  mov     [rax+8], rcx
0x14000cc08  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc0f  cmp     rcx, rsi
0x14000cc12  jz      short loc_14000CC33
0x14000cc14  mov     eax, [rcx+2Ch]
0x14000cc17  test    al, 20h
0x14000cc19  jz      short loc_14000CC33
0x14000cc1b  mov     rcx, [rcx+18h]
0x14000cc1f  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000cc26  mov     edx, 29h ; ')'
0x14000cc2b  mov     r9d, ebx
0x14000cc2e  call    WPP_SF_d
0x14000cc33  test    ebx, ebx
0x14000cc35  jz      short loc_14000CC3C
0x14000cc37  call    FilterDeregisterDevice
0x14000cc3c  mov     eax, ebx
0x14000cc3e  mov     rcx, [rbp+80h+var_10]
0x14000cc42  xor     rcx, rsp; StackCookie
0x14000cc45  call    __security_check_cookie
0x14000cc4a  lea     r11, [rsp+180h+var_s0]
0x14000cc52  mov     rbx, [r11+10h]
0x14000cc56  mov     rsi, [r11+18h]
0x14000cc5a  mov     rsp, r11
0x14000cc5d  pop     rbp
0x14000cc5e  retn
```
