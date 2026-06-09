# HUBFDO_CreateDeviceInterfaceForBillboard

- ea: `0x14000cbb4`
- end: `0x14000cdb0`
- name: `HUBFDO_CreateDeviceInterfaceForBillboard`
- size: `508`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, _QWORD *, _BYTE *, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14008292c`

## callees

- `0x1400024b8`
- `0x14000cbb4`
- `0x14002f938`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000cc36`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000cc36`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000cd43`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000cd43`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc1a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc1a`

## pseudocode

```c
__int64 __fastcall HUBFDO_CreateDeviceInterfaceForBillboard(
        __int64 a1,
        unsigned __int16 a2,
        _QWORD *a3,
        _BYTE *a4,
        int a5,
        __int64 a6)
{
  ULONG v7; // ebx
  int DeviceInterfacePath; // eax
  unsigned int v11; // ebx
  _UNKNOWN **v12; // rdx
  int v13; // r9d
  __int64 v15; // [rsp+28h] [rbp-71h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  __int128 v17; // [rsp+50h] [rbp-49h] BYREF
  WCHAR SourceString[32]; // [rsp+60h] [rbp-39h] BYREF

  v7 = a2;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  *a3 = 0;
  v17 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  DestinationString.MaximumLength = 64;
  DeviceInterfacePath = RtlIntegerToUnicodeString(v7, 0xAu, &DestinationString);
  v11 = DeviceInterfacePath;
  if ( DeviceInterfacePath >= 0 )
  {
    DeviceInterfacePath = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, struct _UNICODE_STRING *))(WdfFunctions_01015 + 616))(
                            WdfDriverGlobals,
                            *(_QWORD *)(a1 + 16),
                            &GUID_DEVINTERFACE_USB_BILLBOARD,
                            &DestinationString);
    v11 = DeviceInterfacePath;
    if ( DeviceInterfacePath >= 0 )
    {
      *a4 = 1;
      DeviceInterfacePath = HUBMISC_GetDeviceInterfacePath(
                              (__int64)&GUID_DEVINTERFACE_USB_BILLBOARD,
                              *(_QWORD *)(a1 + 16),
                              a3,
                              (__int64)&DestinationString,
                              *(_QWORD *)(a1 + 2536));
      v11 = DeviceInterfacePath;
      if ( DeviceInterfacePath >= 0 )
      {
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *))(WdfFunctions_01015 + 2472))(
          WdfDriverGlobals,
          *a3,
          &v17);
        DeviceInterfacePath = IoSetDeviceInterfacePropertyData(
                                &v17,
                                DEVPKEY_Device_UsbBillboardInfo,
                                0,
                                0,
                                4099,
                                a5,
                                a6);
        v11 = DeviceInterfacePath;
        if ( DeviceInterfacePath < 0 )
        {
          v12 = &WPP_RECORDER_INITIALIZED;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v13 = 105;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v12 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v13 = 104;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v12 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 103;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v12 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 102;
LABEL_13:
      LODWORD(v15) = DeviceInterfacePath;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 2536),
        (_DWORD)v12,
        3,
        v13,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v15);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14000cbb4  push    rbp
0x14000cbb6  push    rbx
0x14000cbb7  push    rsi
0x14000cbb8  push    rdi
0x14000cbb9  push    r12
0x14000cbbb  push    r14
0x14000cbbd  push    r15
0x14000cbbf  lea     rbp, [rsp-17h]
0x14000cbc4  sub     rsp, 0B0h
0x14000cbcb  mov     rax, cs:__security_cookie
0x14000cbd2  xor     rax, rsp
0x14000cbd5  mov     [rbp+47h+var_40], rax
0x14000cbd9  mov     r15, [rbp+47h+arg_28]
0x14000cbdd  mov     rsi, r8
0x14000cbe0  movzx   ebx, dx
0x14000cbe3  mov     rdi, rcx
0x14000cbe6  xorps   xmm0, xmm0
0x14000cbe9  lea     rcx, [rbp+47h+SourceString]; void *
0x14000cbed  mov     r12d, 40h ; '@'
0x14000cbf3  xor     edx, edx; Val
0x14000cbf5  mov     r8d, r12d; Size
0x14000cbf8  mov     r14, r9
0x14000cbfb  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x14000cbff  call    memset
0x14000cc04  xorps   xmm0, xmm0
0x14000cc07  mov     qword ptr [rsi], 0
0x14000cc0e  lea     rdx, [rbp+47h+SourceString]; SourceString
0x14000cc12  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000cc16  movups  [rbp+47h+var_90], xmm0
0x14000cc1a  call    cs:__imp_RtlInitUnicodeString
0x14000cc21  nop     dword ptr [rax+rax+00h]
0x14000cc26  mov     ecx, ebx; Value
0x14000cc28  mov     [rbp+47h+DestinationString.MaximumLength], r12w
0x14000cc2d  lea     r8, [rbp+47h+DestinationString]; String
0x14000cc31  lea     edx, [r12-36h]; Base
0x14000cc36  call    cs:__imp_RtlIntegerToUnicodeString
0x14000cc3d  nop     dword ptr [rax+rax+00h]
0x14000cc42  mov     ebx, eax
0x14000cc44  test    eax, eax
0x14000cc46  jns     short loc_14000CC66
0x14000cc48  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000cc4f  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000cc56  jz      loc_14000CD8F
0x14000cc5c  lea     r9d, [r12+26h]
0x14000cc61  jmp     loc_14000CD6B
0x14000cc66  mov     rax, cs:WdfFunctions_01015
0x14000cc6d  lea     r9, [rbp+47h+DestinationString]
0x14000cc71  mov     rdx, [rdi+10h]
0x14000cc75  lea     r8, GUID_DEVINTERFACE_USB_BILLBOARD
0x14000cc7c  mov     rcx, cs:WdfDriverGlobals
0x14000cc83  mov     rax, [rax+268h]
0x14000cc8a  call    _guard_dispatch_icall
0x14000cc8f  mov     ebx, eax
0x14000cc91  test    eax, eax
0x14000cc93  jns     short loc_14000CCB4
0x14000cc95  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000cc9c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000cca3  jz      loc_14000CD8F
0x14000cca9  mov     r9d, 67h ; 'g'
0x14000ccaf  jmp     loc_14000CD6B
0x14000ccb4  mov     byte ptr [r14], 1
0x14000ccb8  lea     r9, [rbp+47h+DestinationString]
0x14000ccbc  mov     rax, [rdi+9E8h]
0x14000ccc3  lea     rcx, GUID_DEVINTERFACE_USB_BILLBOARD
0x14000ccca  mov     rdx, [rdi+10h]
0x14000ccce  mov     r8, rsi
0x14000ccd1  mov     [rsp+0E0h+var_C0], rax
0x14000ccd6  call    HUBMISC_GetDeviceInterfacePath
0x14000ccdb  mov     ebx, eax
0x14000ccdd  test    eax, eax
0x14000ccdf  jns     short loc_14000CCFD
0x14000cce1  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000cce8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000ccef  jz      loc_14000CD8F
0x14000ccf5  mov     r9d, 68h ; 'h'
0x14000ccfb  jmp     short loc_14000CD6B
0x14000ccfd  mov     rax, cs:WdfFunctions_01015
0x14000cd04  lea     r8, [rbp+47h+var_90]
0x14000cd08  mov     rdx, [rsi]
0x14000cd0b  mov     rcx, cs:WdfDriverGlobals
0x14000cd12  mov     rax, [rax+9A8h]
0x14000cd19  call    _guard_dispatch_icall
0x14000cd1e  mov     eax, [rbp+47h+arg_20]
0x14000cd21  lea     rdx, DEVPKEY_Device_UsbBillboardInfo
0x14000cd28  mov     [rsp+0E0h+var_B0], r15
0x14000cd2d  lea     rcx, [rbp+47h+var_90]
0x14000cd31  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14000cd35  xor     r9d, r9d
0x14000cd38  xor     r8d, r8d
0x14000cd3b  mov     dword ptr [rsp+0E0h+var_C0], 1003h
0x14000cd43  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000cd4a  nop     dword ptr [rax+rax+00h]
0x14000cd4f  mov     ebx, eax
0x14000cd51  test    eax, eax
0x14000cd53  jns     short loc_14000CD8F
0x14000cd55  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000cd5c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000cd63  jz      short loc_14000CD8F
0x14000cd65  mov     r9d, 69h ; 'i'
0x14000cd6b  mov     rcx, [rdi+9E8h]
0x14000cd72  mov     r8d, 3
0x14000cd78  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14000cd7c  mov     dl, 2
0x14000cd7e  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000cd85  mov     [rsp+0E0h+var_C0], rax
0x14000cd8a  call    WPP_RECORDER_SF_d
0x14000cd8f  mov     eax, ebx
0x14000cd91  mov     rcx, [rbp+47h+var_40]
0x14000cd95  xor     rcx, rsp; StackCookie
0x14000cd98  call    __security_check_cookie
0x14000cd9d  add     rsp, 0B0h
0x14000cda4  pop     r15
0x14000cda6  pop     r14
0x14000cda8  pop     r12
0x14000cdaa  pop     rdi
0x14000cdab  pop     rsi
0x14000cdac  pop     rbx
0x14000cdad  pop     rbp
0x14000cdae  retn
```
