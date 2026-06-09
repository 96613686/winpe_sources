# PgmCreateDevice

- ea: `0x140037ac4`
- end: `0x140037dc8`
- name: `PgmCreateDevice`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14003770c`

## callees

- `0x140005068`
- `0x14000a580`
- `0x14001cdf0`
- `0x14001d300`
- `0x140037ac4`
- `0x140038884`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140037c5c`
- `ntoskrnl!KeInitializeEvent` at `0x140037c5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b00`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b00`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140037bf9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140037bf9`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140037c34`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140037c34`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140037c47`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140037c47`
- `ntoskrnl!ZwClose` at `0x140037d35`
- `ntoskrnl!ZwClose` at `0x140037d35`
- `ntoskrnl!IoCreateDevice` at `0x140037b3b`
- `ntoskrnl!IoCreateDevice` at `0x140037b3b`
- `ntoskrnl!IoDeleteDevice` at `0x140037cb0`
- `ntoskrnl!IoDeleteDevice` at `0x140037cb0`
- `ntoskrnl!ObfDereferenceObject` at `0x140037d25`
- `ntoskrnl!ObfDereferenceObject` at `0x140037d25`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037bb8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037bb8`
- `TDI!TdiRegisterDeviceObject` at `0x140037cdc`
- `TDI!TdiRegisterDeviceObject` at `0x140037cdc`

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
  v2 = PgmTdiOpenControl((__int64)DeviceExtension);
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
0x140037ac4  mov     [rsp-8+arg_0], rbx
0x140037ac9  mov     [rsp-8+arg_8], rdi
0x140037ace  push    rbp
0x140037acf  mov     rbp, rsp
0x140037ad2  sub     rsp, 80h
0x140037ad9  mov     rax, cs:__security_cookie
0x140037ae0  xor     rax, rsp
0x140037ae3  mov     [rbp+var_8], rax
0x140037ae7  xorps   xmm0, xmm0
0x140037aea  lea     rdx, aDevicePgm; "\\Device\\Pgm"
0x140037af1  xorps   xmm1, xmm1
0x140037af4  lea     rcx, [rbp+DestinationString]; DestinationString
0x140037af8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140037afc  movups  xmmword ptr [rbp+String.Length], xmm1
0x140037b00  call    cs:__imp_RtlInitUnicodeString
0x140037b07  nop     dword ptr [rax+rax+00h]
0x140037b0c  mov     rcx, cs:DriverObject; DriverObject
0x140037b13  lea     rax, pPgmDeviceObject
0x140037b1a  mov     [rsp+80h+DeviceObject], rax; DeviceObject
0x140037b1f  lea     r8, [rbp+DestinationString]; DeviceName
0x140037b23  mov     [rsp+80h+Exclusive], 0; Exclusive
0x140037b28  mov     r9d, 12h; DeviceType
0x140037b2e  mov     edx, 9Eh; DeviceExtensionSize
0x140037b33  mov     [rsp+80h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140037b3b  call    cs:__imp_IoCreateDevice
0x140037b42  nop     dword ptr [rax+rax+00h]
0x140037b47  mov     ebx, eax
0x140037b49  test    eax, eax
0x140037b4b  jns     short loc_140037B99
0x140037b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b54  lea     rdx, WPP_GLOBAL_Control
0x140037b5b  cmp     rcx, rdx
0x140037b5e  jz      short loc_140037B89
0x140037b60  mov     edx, [rcx+2Ch]
0x140037b63  test    dl, 2
0x140037b66  jz      short loc_140037B89
0x140037b68  mov     rcx, [rcx+18h]
0x140037b6c  lea     rax, [rbp+DestinationString]
0x140037b70  mov     edx, 18h
0x140037b75  mov     qword ptr [rsp+80h+DeviceCharacteristics], rax
0x140037b7a  mov     r9d, ebx
0x140037b7d  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037b84  call    WPP_SF_DZ
0x140037b89  mov     cs:pgPgmDevice, 0
0x140037b94  jmp     loc_140037DA4
0x140037b99  mov     rax, cs:pPgmDeviceObject
0x140037ba0  xor     edx, edx; Val
0x140037ba2  mov     r8d, 9Eh; Size
0x140037ba8  mov     rdi, [rax+40h]
0x140037bac  mov     rcx, rdi; void *
0x140037baf  call    memset
0x140037bb4  lea     rcx, [rdi+60h]; SpinLock
0x140037bb8  call    cs:__imp_KeInitializeSpinLock
0x140037bbf  nop     dword ptr [rax+rax+00h]
0x140037bc4  inc     dword ptr [rdi+10h]
0x140037bc7  lea     rbx, [rdi+18h]
0x140037bcb  mov     dword ptr [rdi+0Ch], 43564544h
0x140037bd2  lea     rdx, aDeviceRawip; "\\Device\\RawIp"
0x140037bd9  mov     rax, cs:pPgmDeviceObject
0x140037be0  mov     rcx, rbx; Destination
0x140037be3  mov     [rdi], rax
0x140037be6  lea     rax, [rdi+70h]
0x140037bea  mov     [rdi+20h], rax
0x140037bee  xor     eax, eax
0x140037bf0  mov     [rbx], ax
0x140037bf3  mov     word ptr [rdi+1Ah], 26h ; '&'
0x140037bf9  call    cs:__imp_RtlAppendUnicodeToString
0x140037c00  nop     dword ptr [rax+rax+00h]
0x140037c05  movzx   edx, word ptr [rbx]
0x140037c08  lea     r8, [rbp+String]; String
0x140037c0c  mov     rax, [rdi+20h]
0x140037c10  shr     rdx, 1
0x140037c13  mov     word ptr [rax+rdx*2], 5Ch ; '\'
0x140037c19  lea     rax, [rbp+var_20]
0x140037c1d  add     word ptr [rbx], 2
0x140037c21  mov     [rbp+String.Buffer], rax
0x140037c25  mov     eax, 14h
0x140037c2a  mov     [rbp+String.MaximumLength], ax
0x140037c2e  lea     edx, [rax-0Ah]; Base
0x140037c31  lea     ecx, [rax+5Dh]; Value
0x140037c34  call    cs:__imp_RtlIntegerToUnicodeString
0x140037c3b  nop     dword ptr [rax+rax+00h]
0x140037c40  lea     rdx, [rbp+String]; Source
0x140037c44  mov     rcx, rbx; Destination
0x140037c47  call    cs:__imp_RtlAppendUnicodeStringToString
0x140037c4e  nop     dword ptr [rax+rax+00h]
0x140037c53  lea     rcx, [rdi+48h]; Event
0x140037c57  xor     r8d, r8d; State
0x140037c5a  xor     edx, edx; Type
0x140037c5c  call    cs:__imp_KeInitializeEvent
0x140037c63  nop     dword ptr [rax+rax+00h]
0x140037c68  mov     rcx, rdi
0x140037c6b  call    PgmTdiOpenControl
0x140037c70  mov     ebx, eax
0x140037c72  test    eax, eax
0x140037c74  jns     short loc_140037CC1
0x140037c76  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c7d  lea     rdx, WPP_GLOBAL_Control
0x140037c84  cmp     rcx, rdx
0x140037c87  jz      short loc_140037CA9
0x140037c89  mov     edx, [rcx+2Ch]
0x140037c8c  test    dl, 2
0x140037c8f  jz      short loc_140037CA9
0x140037c91  mov     rcx, [rcx+18h]
0x140037c95  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037c9c  mov     edx, 19h
0x140037ca1  mov     r9d, eax
0x140037ca4  call    WPP_SF_d
0x140037ca9  mov     rcx, cs:pPgmDeviceObject; DeviceObject
0x140037cb0  call    cs:__imp_IoDeleteDevice
0x140037cb7  nop     dword ptr [rax+rax+00h]
0x140037cbc  jmp     loc_140037DA4
0x140037cc1  mov     rax, [rdi+30h]
0x140037cc5  lea     rdx, [rdi+40h]; RegistrationHandle
0x140037cc9  mov     cl, [rax+4Ch]
0x140037ccc  mov     rax, cs:pPgmDeviceObject
0x140037cd3  inc     cl
0x140037cd5  mov     [rax+4Ch], cl
0x140037cd8  lea     rcx, [rbp+DestinationString]; DeviceName
0x140037cdc  call    cs:__imp_TdiRegisterDeviceObject
0x140037ce3  nop     dword ptr [rax+rax+00h]
0x140037ce8  mov     ebx, eax
0x140037cea  test    eax, eax
0x140037cec  jns     short loc_140037D56
0x140037cee  mov     rcx, cs:WPP_GLOBAL_Control
0x140037cf5  lea     rdx, WPP_GLOBAL_Control
0x140037cfc  cmp     rcx, rdx
0x140037cff  jz      short loc_140037D21
0x140037d01  mov     edx, [rcx+2Ch]
0x140037d04  test    dl, 2
0x140037d07  jz      short loc_140037D21
0x140037d09  mov     rcx, [rcx+18h]
0x140037d0d  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037d14  mov     edx, 1Ah
0x140037d19  mov     r9d, eax
0x140037d1c  call    WPP_SF_d
0x140037d21  mov     rcx, [rdi+38h]; Object
0x140037d25  call    cs:__imp_ObfDereferenceObject
0x140037d2c  nop     dword ptr [rax+rax+00h]
0x140037d31  mov     rcx, [rdi+28h]; Handle
0x140037d35  call    cs:__imp_ZwClose
0x140037d3c  nop     dword ptr [rax+rax+00h]
0x140037d41  mov     qword ptr [rdi+38h], 0
0x140037d49  mov     qword ptr [rdi+28h], 0
0x140037d51  jmp     loc_140037CA9
0x140037d56  mov     rax, cs:pPgmDeviceObject
0x140037d5d  btr     dword ptr [rax+30h], 7
0x140037d62  mov     cs:pgPgmDevice, rdi
0x140037d69  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d70  lea     rdx, WPP_GLOBAL_Control
0x140037d77  cmp     rcx, rdx
0x140037d7a  jz      short loc_140037DA4
0x140037d7c  mov     eax, [rcx+2Ch]
0x140037d7f  test    al, 10h
0x140037d81  jz      short loc_140037DA4
0x140037d83  mov     rcx, [rcx+18h]
0x140037d87  lea     rax, [rbp+DestinationString]
0x140037d8b  mov     edx, 1Bh
0x140037d90  mov     qword ptr [rsp+80h+DeviceCharacteristics], rax
0x140037d95  mov     r9d, ebx
0x140037d98  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037d9f  call    WPP_SF_DZ
0x140037da4  mov     eax, ebx
0x140037da6  mov     rcx, [rbp+var_8]
0x140037daa  xor     rcx, rsp; StackCookie
0x140037dad  call    __security_check_cookie
0x140037db2  lea     r11, [rsp+80h+var_s0]
0x140037dba  mov     rbx, [r11+10h]
0x140037dbe  mov     rdi, [r11+18h]
0x140037dc2  mov     rsp, r11
0x140037dc5  pop     rbp
0x140037dc6  retn
```
