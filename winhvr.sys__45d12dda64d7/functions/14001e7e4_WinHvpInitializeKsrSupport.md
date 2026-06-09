# WinHvpInitializeKsrSupport

- ea: `0x14001e7e4`
- end: `0x14001e9db`
- name: `WinHvpInitializeKsrSupport`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002a804`

## callees

- `0x140001008`
- `0x140001038`
- `0x140009c50`
- `0x14001e6cc`
- `0x14001e7e4`
- `0x14001ed50`

## import_xrefs

- `ntoskrnl!ExCreateCallback` at `0x14001e8fe`
- `ntoskrnl!ExCreateCallback` at `0x14001e8fe`
- `ntoskrnl!ExRegisterCallback` at `0x14001e928`
- `ntoskrnl!ExRegisterCallback` at `0x14001e928`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x14001e840`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x14001e840`

## pseudocode

```c
__int64 WinHvpInitializeKsrSupport()
{
  NTSTATUS v0; // ebx
  __int64 v1; // rcx
  unsigned __int8 *v2; // rdx
  __int16 v3; // di
  ULONG v5; // [rsp+20h] [rbp-69h]
  _WORD v6[2]; // [rsp+30h] [rbp-59h] BYREF
  NTSTATUS v7; // [rsp+34h] [rbp-55h] BYREF
  _QWORD v8[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v9; // [rsp+48h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+80h] [rbp-9h] BYREF
  const char *v12; // [rsp+A0h] [rbp+17h]
  __int64 v13; // [rsp+A8h] [rbp+1Fh]
  _WORD *v14; // [rsp+B0h] [rbp+27h]
  __int64 v15; // [rsp+B8h] [rbp+2Fh]
  NTSTATUS *v16; // [rsp+C0h] [rbp+37h]
  __int64 v17; // [rsp+C8h] [rbp+3Fh]

  v8[0] = 2883626;
  v9 = 0;
  v8[1] = L"\\Callback\\SoftRestart";
  qword_140016070 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (int)KsrGetFirmwareInformation(&v9) >= 0 )
  {
    byte_140016208 = 1;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v8;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v0 = ExCreateCallback((PCALLBACK_OBJECT *)&CallbackObject, &ObjectAttributes, 0, 0);
    if ( v0 >= 0 )
    {
      CallbackRegistration = ExRegisterCallback((PCALLBACK_OBJECT)CallbackObject, WinHvpKsrNotifyCallback, 0);
      if ( CallbackRegistration )
      {
        WinHvpRestoreKsrContext();
        return (unsigned int)v0;
      }
      v0 = -1073741670;
      v3 = 153;
    }
    else
    {
      v3 = 144;
    }
    WinHvpCleanupKsrSupport();
    if ( (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn() )
    {
      v13 = 27;
      v12 = "WinHvpInitializeKsrSupport";
      v2 = (unsigned __int8 *)word_14000E81A;
      v6[0] = v3;
      v14 = v6;
      v16 = &v7;
      v5 = 5;
      v7 = v0;
      v17 = 4;
      goto LABEL_5;
    }
  }
  else
  {
    v0 = 0;
    if ( (unsigned int)dword_140011000 > 4 && (unsigned __int8)tlgKeywordOn() )
    {
      v13 = 27;
      v12 = "WinHvpInitializeKsrSupport";
      v6[0] = 123;
      v2 = (unsigned __int8 *)byte_14000E853;
      v14 = v6;
      v5 = 4;
LABEL_5:
      v15 = 2;
      tlgWriteTransfer_EtwWriteTransfer(v1, v2, 0, 0, v5, &v11);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14001e7e4  mov     [rsp-8+arg_0], rbx
0x14001e7e9  mov     [rsp-8+arg_8], rdi
0x14001e7ee  push    rbp
0x14001e7ef  lea     rbp, [rsp-57h]
0x14001e7f4  sub     rsp, 0E0h
0x14001e7fb  mov     rax, cs:__security_cookie
0x14001e802  xor     rax, rsp
0x14001e805  mov     [rbp+57h+var_10], rax
0x14001e809  xorps   xmm0, xmm0
0x14001e80c  mov     [rbp+57h+var_A8], 2C002Ah
0x14001e814  lea     rax, aCallbackSoftre; "\\Callback\\SoftRestart"
0x14001e81b  mov     [rbp+57h+var_98], 0
0x14001e823  mov     [rbp+57h+var_A0], rax
0x14001e827  lea     rcx, [rbp+57h+var_98]
0x14001e82b  xor     eax, eax
0x14001e82d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001e831  mov     cs:qword_140016070, rax
0x14001e838  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001e83c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001e840  call    cs:__imp_KsrGetFirmwareInformation
0x14001e847  nop     dword ptr [rax+rax+00h]
0x14001e84c  test    eax, eax
0x14001e84e  jns     short loc_14001E8C0
0x14001e850  mov     eax, cs:dword_140011000
0x14001e856  xor     ebx, ebx
0x14001e858  cmp     eax, 4
0x14001e85b  jbe     loc_14001E9B7
0x14001e861  call    _tlgKeywordOn
0x14001e866  test    al, al
0x14001e868  jz      loc_14001E9B7
0x14001e86e  lea     rax, aWinhvpinitiali; "WinHvpInitializeKsrSupport"
0x14001e875  mov     [rbp+57h+var_38], 1Bh
0x14001e87d  mov     [rbp+57h+var_40], rax
0x14001e881  lea     eax, [rbx+7Bh]
0x14001e884  mov     [rbp+57h+var_B0], ax
0x14001e888  lea     rdx, byte_14000E853
0x14001e88f  lea     rax, [rbp+57h+var_B0]
0x14001e893  mov     [rbp+57h+var_30], rax
0x14001e897  lea     rax, [rbp+57h+var_60]
0x14001e89b  mov     [rsp+0E0h+var_B8], rax
0x14001e8a0  mov     [rsp+0E0h+var_C0], 4
0x14001e8a8  xor     r9d, r9d
0x14001e8ab  mov     [rbp+57h+var_28], 2
0x14001e8b3  xor     r8d, r8d
0x14001e8b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001e8bb  jmp     loc_14001E9B7
0x14001e8c0  lea     rax, [rbp+57h+var_A8]
0x14001e8c4  mov     cs:byte_140016208, 1
0x14001e8cb  xorps   xmm0, xmm0
0x14001e8ce  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001e8d2  xor     r9d, r9d; AllowMultipleCallbacks
0x14001e8d5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001e8dc  xor     r8d, r8d; Create
0x14001e8df  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001e8e7  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001e8eb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001e8f2  lea     rcx, CallbackObject; CallbackObject
0x14001e8f9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001e8fe  call    cs:__imp_ExCreateCallback
0x14001e905  nop     dword ptr [rax+rax+00h]
0x14001e90a  mov     ebx, eax
0x14001e90c  test    eax, eax
0x14001e90e  jns     short loc_14001E917
0x14001e910  mov     edi, 90h
0x14001e915  jmp     short loc_14001E94A
0x14001e917  mov     rcx, cs:CallbackObject; CallbackObject
0x14001e91e  lea     rdx, WinHvpKsrNotifyCallback; CallbackFunction
0x14001e925  xor     r8d, r8d; CallbackContext
0x14001e928  call    cs:__imp_ExRegisterCallback
0x14001e92f  nop     dword ptr [rax+rax+00h]
0x14001e934  mov     cs:CallbackRegistration, rax
0x14001e93b  test    rax, rax
0x14001e93e  jnz     short loc_14001E9B2
0x14001e940  mov     ebx, 0C000009Ah
0x14001e945  mov     edi, 99h
0x14001e94a  call    WinHvpCleanupKsrSupport
0x14001e94f  mov     eax, cs:dword_140011000
0x14001e955  cmp     eax, 2
0x14001e958  jbe     short loc_14001E9B7
0x14001e95a  call    _tlgKeywordOn
0x14001e95f  test    al, al
0x14001e961  jz      short loc_14001E9B7
0x14001e963  lea     rax, aWinhvpinitiali; "WinHvpInitializeKsrSupport"
0x14001e96a  mov     [rbp+57h+var_38], 1Bh
0x14001e972  mov     [rbp+57h+var_40], rax
0x14001e976  lea     rdx, word_14000E81A
0x14001e97d  lea     rax, [rbp+57h+var_B0]
0x14001e981  mov     [rbp+57h+var_B0], di
0x14001e985  mov     [rbp+57h+var_30], rax
0x14001e989  lea     rax, [rbp+57h+var_AC]
0x14001e98d  mov     [rbp+57h+var_20], rax
0x14001e991  lea     rax, [rbp+57h+var_60]
0x14001e995  mov     [rsp+0E0h+var_B8], rax
0x14001e99a  mov     [rsp+0E0h+var_C0], 5
0x14001e9a2  mov     [rbp+57h+var_AC], ebx
0x14001e9a5  mov     [rbp+57h+var_18], 4
0x14001e9ad  jmp     loc_14001E8A8
0x14001e9b2  call    WinHvpRestoreKsrContext
0x14001e9b7  mov     eax, ebx
0x14001e9b9  mov     rcx, [rbp+57h+var_10]
0x14001e9bd  xor     rcx, rsp; StackCookie
0x14001e9c0  call    __security_check_cookie
0x14001e9c5  lea     r11, [rsp+0E0h+var_s0]
0x14001e9cd  mov     rbx, [r11+10h]
0x14001e9d1  mov     rdi, [r11+18h]
0x14001e9d5  mov     rsp, r11
0x14001e9d8  pop     rbp
0x14001e9d9  retn
```
