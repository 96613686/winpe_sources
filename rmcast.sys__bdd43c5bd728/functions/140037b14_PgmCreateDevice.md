# PgmCreateDevice

- ea: `0x140037b14`
- end: `0x140037e18`
- name: `PgmCreateDevice`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14003775c`

## callees

- `0x140005068`
- `0x14000a580`
- `0x14001cdf0`
- `0x14001d300`
- `0x140037b14`
- `0x1400388d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140037cac`
- `ntoskrnl!KeInitializeEvent` at `0x140037cac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b50`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b50`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140037c49`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140037c49`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140037c84`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140037c84`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140037c97`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140037c97`
- `ntoskrnl!ZwClose` at `0x140037d85`
- `ntoskrnl!ZwClose` at `0x140037d85`
- `ntoskrnl!IoCreateDevice` at `0x140037b8b`
- `ntoskrnl!IoCreateDevice` at `0x140037b8b`
- `ntoskrnl!IoDeleteDevice` at `0x140037d00`
- `ntoskrnl!IoDeleteDevice` at `0x140037d00`
- `ntoskrnl!ObfDereferenceObject` at `0x140037d75`
- `ntoskrnl!ObfDereferenceObject` at `0x140037d75`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037c08`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037c08`
- `TDI!TdiRegisterDeviceObject` at `0x140037d2c`
- `TDI!TdiRegisterDeviceObject` at `0x140037d2c`

## pseudocode

```c
__int64 PgmCreateDevice()
{
  unsigned int v0; // ebx
  _QWORD *DeviceExtension; // rdi
  int v2; // eax
  NTSTATUS v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING String; // [rsp+50h] [rbp-30h] BYREF
  char v7; // [rsp+60h] [rbp-20h] BYREF

  DestinationString = 0;
  String = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Pgm");
  v0 = IoCreateDevice(DriverObject, 0x9Eu, &DestinationString, 0x12u, 0x100u, 0, &pPgmDeviceObject);
  if ( (v0 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DZ(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        (unsigned int)WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        v0,
        (__int64)&DestinationString);
    pgPgmDevice = 0;
    return v0;
  }
  DeviceExtension = pPgmDeviceObject->DeviceExtension;
  memset(DeviceExtension, 0, 0x9Eu);
  KeInitializeSpinLock(DeviceExtension + 12);
  ++*((_DWORD *)DeviceExtension + 4);
  *((_DWORD *)DeviceExtension + 3) = 1129727300;
  *DeviceExtension = pPgmDeviceObject;
  DeviceExtension[4] = DeviceExtension + 14;
  *((_WORD *)DeviceExtension + 12) = 0;
  *((_WORD *)DeviceExtension + 13) = 38;
  RtlAppendUnicodeToString((PUNICODE_STRING)(DeviceExtension + 3), L"\\Device\\RawIp");
  *(_WORD *)(DeviceExtension[4] + 2 * ((unsigned __int64)*((unsigned __int16 *)DeviceExtension + 12) >> 1)) = 92;
  *((_WORD *)DeviceExtension + 12) += 2;
  String.Buffer = (PWSTR)&v7;
  String.MaximumLength = 20;
  RtlIntegerToUnicodeString(0x71u, 0xAu, &String);
  RtlAppendUnicodeStringToString((PUNICODE_STRING)(DeviceExtension + 3), &String);
  KeInitializeEvent((PRKEVENT)DeviceExtension + 3, NotificationEvent, 0);
  v2 = PgmTdiOpenControl(DeviceExtension);
  v0 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        (unsigned int)v2);
LABEL_10:
    IoDeleteDevice(pPgmDeviceObject);
    return v0;
  }
  pPgmDeviceObject->StackSize = *(_BYTE *)(DeviceExtension[6] + 76LL) + 1;
  v3 = TdiRegisterDeviceObject(&DestinationString, (HANDLE *)DeviceExtension + 8);
  v0 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        (unsigned int)v3);
    ObfDereferenceObject((PVOID)DeviceExtension[7]);
    ZwClose((HANDLE)DeviceExtension[5]);
    DeviceExtension[7] = 0;
    DeviceExtension[5] = 0;
    goto LABEL_10;
  }
  pPgmDeviceObject->Flags &= ~0x80u;
  pgPgmDevice = (__int64)DeviceExtension;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_DZ(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      (unsigned int)WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
      v3,
      (__int64)&DestinationString);
  return v0;
}

```

## disassembly

```asm
0x140037b14  mov     [rsp-8+arg_0], rbx
0x140037b19  mov     [rsp-8+arg_8], rdi
0x140037b1e  push    rbp
0x140037b1f  mov     rbp, rsp
0x140037b22  sub     rsp, 80h
0x140037b29  mov     rax, cs:__security_cookie
0x140037b30  xor     rax, rsp
0x140037b33  mov     [rbp+var_8], rax
0x140037b37  xorps   xmm0, xmm0
0x140037b3a  lea     rdx, aDevicePgm; "\\Device\\Pgm"
0x140037b41  xorps   xmm1, xmm1
0x140037b44  lea     rcx, [rbp+DestinationString]; DestinationString
0x140037b48  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140037b4c  movups  xmmword ptr [rbp+String.Length], xmm1
0x140037b50  call    cs:__imp_RtlInitUnicodeString
0x140037b57  nop     dword ptr [rax+rax+00h]
0x140037b5c  mov     rcx, cs:DriverObject; DriverObject
0x140037b63  lea     rax, pPgmDeviceObject
0x140037b6a  mov     [rsp+80h+DeviceObject], rax; DeviceObject
0x140037b6f  lea     r8, [rbp+DestinationString]; DeviceName
0x140037b73  mov     [rsp+80h+Exclusive], 0; Exclusive
0x140037b78  mov     r9d, 12h; DeviceType
0x140037b7e  mov     edx, 9Eh; DeviceExtensionSize
0x140037b83  mov     [rsp+80h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140037b8b  call    cs:__imp_IoCreateDevice
0x140037b92  nop     dword ptr [rax+rax+00h]
0x140037b97  mov     ebx, eax
0x140037b99  test    eax, eax
0x140037b9b  jns     short loc_140037BE9
0x140037b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ba4  lea     rdx, WPP_GLOBAL_Control
0x140037bab  cmp     rcx, rdx
0x140037bae  jz      short loc_140037BD9
0x140037bb0  mov     edx, [rcx+2Ch]
0x140037bb3  test    dl, 2
0x140037bb6  jz      short loc_140037BD9
0x140037bb8  mov     rcx, [rcx+18h]
0x140037bbc  lea     rax, [rbp+DestinationString]
0x140037bc0  mov     edx, 18h
0x140037bc5  mov     qword ptr [rsp+80h+DeviceCharacteristics], rax
0x140037bca  mov     r9d, ebx
0x140037bcd  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037bd4  call    WPP_SF_DZ
0x140037bd9  mov     cs:pgPgmDevice, 0
0x140037be4  jmp     loc_140037DF4
0x140037be9  mov     rax, cs:pPgmDeviceObject
0x140037bf0  xor     edx, edx; Val
0x140037bf2  mov     r8d, 9Eh; Size
0x140037bf8  mov     rdi, [rax+40h]
0x140037bfc  mov     rcx, rdi; void *
0x140037bff  call    memset
0x140037c04  lea     rcx, [rdi+60h]; SpinLock
0x140037c08  call    cs:__imp_KeInitializeSpinLock
0x140037c0f  nop     dword ptr [rax+rax+00h]
0x140037c14  inc     dword ptr [rdi+10h]
0x140037c17  lea     rbx, [rdi+18h]
0x140037c1b  mov     dword ptr [rdi+0Ch], 43564544h
0x140037c22  lea     rdx, aDeviceRawip; "\\Device\\RawIp"
0x140037c29  mov     rax, cs:pPgmDeviceObject
0x140037c30  mov     rcx, rbx; Destination
0x140037c33  mov     [rdi], rax
0x140037c36  lea     rax, [rdi+70h]
0x140037c3a  mov     [rdi+20h], rax
0x140037c3e  xor     eax, eax
0x140037c40  mov     [rbx], ax
0x140037c43  mov     word ptr [rdi+1Ah], 26h ; '&'
0x140037c49  call    cs:__imp_RtlAppendUnicodeToString
0x140037c50  nop     dword ptr [rax+rax+00h]
0x140037c55  movzx   edx, word ptr [rbx]
0x140037c58  lea     r8, [rbp+String]; String
0x140037c5c  mov     rax, [rdi+20h]
0x140037c60  shr     rdx, 1
0x140037c63  mov     word ptr [rax+rdx*2], 5Ch ; '\'
0x140037c69  lea     rax, [rbp+var_20]
0x140037c6d  add     word ptr [rbx], 2
0x140037c71  mov     [rbp+String.Buffer], rax
0x140037c75  mov     eax, 14h
0x140037c7a  mov     [rbp+String.MaximumLength], ax
0x140037c7e  lea     edx, [rax-0Ah]; Base
0x140037c81  lea     ecx, [rax+5Dh]; Value
0x140037c84  call    cs:__imp_RtlIntegerToUnicodeString
0x140037c8b  nop     dword ptr [rax+rax+00h]
0x140037c90  lea     rdx, [rbp+String]; Source
0x140037c94  mov     rcx, rbx; Destination
0x140037c97  call    cs:__imp_RtlAppendUnicodeStringToString
0x140037c9e  nop     dword ptr [rax+rax+00h]
0x140037ca3  lea     rcx, [rdi+48h]; Event
0x140037ca7  xor     r8d, r8d; State
0x140037caa  xor     edx, edx; Type
0x140037cac  call    cs:__imp_KeInitializeEvent
0x140037cb3  nop     dword ptr [rax+rax+00h]
0x140037cb8  mov     rcx, rdi
0x140037cbb  call    PgmTdiOpenControl
0x140037cc0  mov     ebx, eax
0x140037cc2  test    eax, eax
0x140037cc4  jns     short loc_140037D11
0x140037cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ccd  lea     rdx, WPP_GLOBAL_Control
0x140037cd4  cmp     rcx, rdx
0x140037cd7  jz      short loc_140037CF9
0x140037cd9  mov     edx, [rcx+2Ch]
0x140037cdc  test    dl, 2
0x140037cdf  jz      short loc_140037CF9
0x140037ce1  mov     rcx, [rcx+18h]
0x140037ce5  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037cec  mov     edx, 19h
0x140037cf1  mov     r9d, eax
0x140037cf4  call    WPP_SF_d
0x140037cf9  mov     rcx, cs:pPgmDeviceObject; DeviceObject
0x140037d00  call    cs:__imp_IoDeleteDevice
0x140037d07  nop     dword ptr [rax+rax+00h]
0x140037d0c  jmp     loc_140037DF4
0x140037d11  mov     rax, [rdi+30h]
0x140037d15  lea     rdx, [rdi+40h]; RegistrationHandle
0x140037d19  mov     cl, [rax+4Ch]
0x140037d1c  mov     rax, cs:pPgmDeviceObject
0x140037d23  inc     cl
0x140037d25  mov     [rax+4Ch], cl
0x140037d28  lea     rcx, [rbp+DestinationString]; DeviceName
0x140037d2c  call    cs:__imp_TdiRegisterDeviceObject
0x140037d33  nop     dword ptr [rax+rax+00h]
0x140037d38  mov     ebx, eax
0x140037d3a  test    eax, eax
0x140037d3c  jns     short loc_140037DA6
0x140037d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d45  lea     rdx, WPP_GLOBAL_Control
0x140037d4c  cmp     rcx, rdx
0x140037d4f  jz      short loc_140037D71
0x140037d51  mov     edx, [rcx+2Ch]
0x140037d54  test    dl, 2
0x140037d57  jz      short loc_140037D71
0x140037d59  mov     rcx, [rcx+18h]
0x140037d5d  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037d64  mov     edx, 1Ah
0x140037d69  mov     r9d, eax
0x140037d6c  call    WPP_SF_d
0x140037d71  mov     rcx, [rdi+38h]; Object
0x140037d75  call    cs:__imp_ObfDereferenceObject
0x140037d7c  nop     dword ptr [rax+rax+00h]
0x140037d81  mov     rcx, [rdi+28h]; Handle
0x140037d85  call    cs:__imp_ZwClose
0x140037d8c  nop     dword ptr [rax+rax+00h]
0x140037d91  mov     qword ptr [rdi+38h], 0
0x140037d99  mov     qword ptr [rdi+28h], 0
0x140037da1  jmp     loc_140037CF9
0x140037da6  mov     rax, cs:pPgmDeviceObject
0x140037dad  btr     dword ptr [rax+30h], 7
0x140037db2  mov     cs:pgPgmDevice, rdi
0x140037db9  mov     rcx, cs:WPP_GLOBAL_Control
0x140037dc0  lea     rdx, WPP_GLOBAL_Control
0x140037dc7  cmp     rcx, rdx
0x140037dca  jz      short loc_140037DF4
0x140037dcc  mov     eax, [rcx+2Ch]
0x140037dcf  test    al, 10h
0x140037dd1  jz      short loc_140037DF4
0x140037dd3  mov     rcx, [rcx+18h]
0x140037dd7  lea     rax, [rbp+DestinationString]
0x140037ddb  mov     edx, 1Bh
0x140037de0  mov     qword ptr [rsp+80h+DeviceCharacteristics], rax
0x140037de5  mov     r9d, ebx
0x140037de8  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037def  call    WPP_SF_DZ
0x140037df4  mov     eax, ebx
0x140037df6  mov     rcx, [rbp+var_8]
0x140037dfa  xor     rcx, rsp; StackCookie
0x140037dfd  call    __security_check_cookie
0x140037e02  lea     r11, [rsp+80h+var_s0]
0x140037e0a  mov     rbx, [r11+10h]
0x140037e0e  mov     rdi, [r11+18h]
0x140037e12  mov     rsp, r11
0x140037e15  pop     rbp
0x140037e16  retn
```
