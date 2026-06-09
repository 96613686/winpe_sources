# GetDeviceId

- ea: `0x1400eb04c`
- end: `0x1400eb2a5`
- name: `GetDeviceId`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1400ec420`

## callees

- `0x14003e9e4`
- `0x140046f1c`
- `0x140052460`
- `0x1400dac60`
- `0x1400e46d0`
- `0x1400eb04c`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x1400eb19a`
- `ntoskrnl!RtlGUIDFromString` at `0x1400eb19a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400eb239`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400eb239`
- `NDIS!NdisCloseConfiguration` at `0x1400eb27e`
- `NDIS!NdisCloseConfiguration` at `0x1400eb27e`
- `NDIS!NdisReadConfiguration` at `0x1400eb13b`
- `NDIS!NdisReadConfiguration` at `0x1400eb1e7`
- `NDIS!NdisReadConfiguration` at `0x1400eb13b`
- `NDIS!NdisReadConfiguration` at `0x1400eb1e7`
- `NDIS!NdisOpenConfigurationEx` at `0x1400eb0ce`
- `NDIS!NdisOpenConfigurationEx` at `0x1400eb0ce`

## pseudocode

```c
__int64 __fastcall GetDeviceId(void *a1, GUID *a2, struct _UNICODE_STRING *a3)
{
  char v4; // r14
  char v6; // di
  NDIS_STATUS v7; // eax
  int v8; // edx
  int v9; // edx
  int v10; // edx
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  int v15; // r8d
  __int64 result; // rax
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+50h] [rbp-19h] BYREF
  PNDIS_CONFIGURATION_PARAMETER v18; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING Keyword; // [rsp+60h] [rbp-9h] BYREF
  UNICODE_STRING v20; // [rsp+70h] [rbp+7h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+80h] [rbp+17h] BYREF
  int Status; // [rsp+D0h] [rbp+67h] BYREF
  PVOID ConfigurationHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  ConfigObject.NdisHandle = a1;
  Keyword.Buffer = L"NetCfgInstanceId";
  Status = 0;
  v20.Buffer = L"MiniportName";
  ConfigurationHandle = 0;
  v4 = (char)a1;
  ConfigObject.Flags = 0;
  ParameterValue = 0;
  v18 = 0;
  *(_QWORD *)&Keyword.Length = 2228256;
  v6 = 1;
  *(_QWORD *)&v20.Length = 1703960;
  *(_QWORD *)&ConfigObject.Header.Type = 1573289;
  v7 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = v7;
  if ( v7 )
  {
    v6 = 0;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrLog,
      v8,
      20,
      10,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (char)&ConfigObject,
      (char)ConfigurationHandle,
      v7);
  }
  else
  {
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterString);
    if ( Status )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qqqd(
        VmsIfrLog,
        v10,
        20,
        11,
        (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
        (char)ParameterValue,
        (char)ConfigurationHandle,
        (char)&Keyword,
        Status);
    }
    else
    {
      v11 = RtlGUIDFromString((PCUNICODE_STRING)&ParameterValue->ParameterData, a2);
      Status = v11;
      if ( v11 )
      {
        WPP_RECORDER_SF__guid_d(
          VmsIfrLog,
          v12,
          v13,
          12,
          (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
          (__int64)a2,
          v11);
      }
      else
      {
        NdisReadConfiguration(&Status, &v18, ConfigurationHandle, &v20, NdisParameterString);
        if ( Status )
          WPP_RECORDER_SF_q_guid_qd(
            VmsIfrLog,
            v14,
            v15,
            13,
            (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
            (char)v18,
            (__int64)a2,
            (char)&v20,
            Status);
        else
          RtlCopyUnicodeString(a3, (PCUNICODE_STRING)&v18->ParameterData);
      }
    }
  }
  result = (unsigned int)Status;
  if ( Status )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v9, 20, 14, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, v4, Status);
    result = (unsigned int)Status;
  }
  if ( v6 )
  {
    NdisCloseConfiguration(ConfigurationHandle);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x1400eb04c  mov     [rsp-8+arg_8], rbx
0x1400eb051  push    rbp
0x1400eb052  push    rsi
0x1400eb053  push    rdi
0x1400eb054  push    r12
0x1400eb056  push    r14
0x1400eb058  lea     rbp, [rsp-37h]
0x1400eb05d  sub     rsp, 0A0h
0x1400eb064  lea     rax, aNetcfginstance; "NetCfgInstanceId"
0x1400eb06b  mov     [rbp+57h+ConfigObject.NdisHandle], rcx
0x1400eb06f  mov     [rbp+57h+Keyword.Buffer], rax
0x1400eb073  mov     rbx, rdx
0x1400eb076  lea     rax, aMiniportname; "MiniportName"
0x1400eb07d  mov     [rbp+57h+Status], 0
0x1400eb084  mov     [rbp+57h+var_50.Buffer], rax
0x1400eb088  lea     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb08c  xor     eax, eax
0x1400eb08e  mov     [rbp+57h+ConfigurationHandle], 0
0x1400eb096  mov     r14, rcx
0x1400eb099  mov     [rbp+57h+ConfigObject.Flags], eax
0x1400eb09c  lea     rcx, [rbp+57h+ConfigObject]; ConfigObject
0x1400eb0a0  mov     [rbp+57h+ParameterValue], 0
0x1400eb0a8  mov     rsi, r8
0x1400eb0ab  mov     [rbp+57h+var_68], 0
0x1400eb0b3  mov     qword ptr [rbp+57h+Keyword.Length], 220020h
0x1400eb0bb  mov     dil, 1
0x1400eb0be  mov     qword ptr [rbp+57h+var_50.Length], 1A0018h
0x1400eb0c6  mov     qword ptr [rbp+57h+ConfigObject.Header.Type], 1801A9h
0x1400eb0ce  call    cs:__imp_NdisOpenConfigurationEx
0x1400eb0d5  nop     dword ptr [rax+rax+00h]
0x1400eb0da  mov     [rbp+57h+Status], eax
0x1400eb0dd  lea     r12, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400eb0e4  test    eax, eax
0x1400eb0e6  jz      short loc_1400EB123
0x1400eb0e8  xor     dil, dil
0x1400eb0eb  mov     rcx, cs:VmsIfrLog
0x1400eb0f2  mov     r9d, 0Ah
0x1400eb0f8  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400eb0fc  mov     dl, 2
0x1400eb0fe  mov     rax, [rbp+57h+ConfigurationHandle]
0x1400eb102  mov     [rsp+0C0h+var_90], rax
0x1400eb107  lea     rax, [rbp+57h+ConfigObject]
0x1400eb10b  mov     [rsp+0C0h+var_98], rax
0x1400eb110  lea     r8d, [r9+0Ah]
0x1400eb114  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb119  call    WPP_RECORDER_SF_qqd
0x1400eb11e  jmp     loc_1400EB245
0x1400eb123  mov     r8, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb127  lea     r9, [rbp+57h+Keyword]; Keyword
0x1400eb12b  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x1400eb12f  mov     [rsp+0C0h+ParameterType], 2; ParameterType
0x1400eb137  lea     rcx, [rbp+57h+Status]; Status
0x1400eb13b  call    cs:__imp_NdisReadConfiguration
0x1400eb142  nop     dword ptr [rax+rax+00h]
0x1400eb147  mov     eax, [rbp+57h+Status]
0x1400eb14a  test    eax, eax
0x1400eb14c  jz      short loc_1400EB18F
0x1400eb14e  mov     rcx, cs:VmsIfrLog
0x1400eb155  mov     r9d, 0Bh
0x1400eb15b  mov     [rsp+0C0h+var_80], eax
0x1400eb15f  mov     dl, 2
0x1400eb161  lea     rax, [rbp+57h+Keyword]
0x1400eb165  mov     [rsp+0C0h+var_88], rax
0x1400eb16a  mov     rax, [rbp+57h+ConfigurationHandle]
0x1400eb16e  lea     r8d, [r9+9]
0x1400eb172  mov     [rsp+0C0h+var_90], rax
0x1400eb177  mov     rax, [rbp+57h+ParameterValue]
0x1400eb17b  mov     [rsp+0C0h+var_98], rax
0x1400eb180  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb185  call    WPP_RECORDER_SF_qqqd
0x1400eb18a  jmp     loc_1400EB245
0x1400eb18f  mov     rcx, [rbp+57h+ParameterValue]
0x1400eb193  mov     rdx, rbx; Guid
0x1400eb196  add     rcx, 8; GuidString
0x1400eb19a  call    cs:__imp_RtlGUIDFromString
0x1400eb1a1  nop     dword ptr [rax+rax+00h]
0x1400eb1a6  mov     [rbp+57h+Status], eax
0x1400eb1a9  test    eax, eax
0x1400eb1ab  jz      short loc_1400EB1CF
0x1400eb1ad  mov     rcx, cs:VmsIfrLog
0x1400eb1b4  mov     r9d, 0Ch
0x1400eb1ba  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400eb1be  mov     [rsp+0C0h+var_98], rbx
0x1400eb1c3  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb1c8  call    WPP_RECORDER_SF__guid_d
0x1400eb1cd  jmp     short loc_1400EB245
0x1400eb1cf  mov     r8, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb1d3  lea     r9, [rbp+57h+var_50]; Keyword
0x1400eb1d7  lea     rdx, [rbp+57h+var_68]; ParameterValue
0x1400eb1db  mov     [rsp+0C0h+ParameterType], 2; ParameterType
0x1400eb1e3  lea     rcx, [rbp+57h+Status]; Status
0x1400eb1e7  call    cs:__imp_NdisReadConfiguration
0x1400eb1ee  nop     dword ptr [rax+rax+00h]
0x1400eb1f3  mov     eax, [rbp+57h+Status]
0x1400eb1f6  test    eax, eax
0x1400eb1f8  jz      short loc_1400EB22E
0x1400eb1fa  mov     rcx, cs:VmsIfrLog
0x1400eb201  mov     r9d, 0Dh
0x1400eb207  mov     [rsp+0C0h+var_80], eax
0x1400eb20b  lea     rax, [rbp+57h+var_50]
0x1400eb20f  mov     [rsp+0C0h+var_88], rax
0x1400eb214  mov     rax, [rbp+57h+var_68]
0x1400eb218  mov     [rsp+0C0h+var_90], rbx
0x1400eb21d  mov     [rsp+0C0h+var_98], rax
0x1400eb222  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb227  call    WPP_RECORDER_SF_q_guid_qd
0x1400eb22c  jmp     short loc_1400EB245
0x1400eb22e  mov     rdx, [rbp+57h+var_68]
0x1400eb232  mov     rcx, rsi; DestinationString
0x1400eb235  add     rdx, 8; SourceString
0x1400eb239  call    cs:__imp_RtlCopyUnicodeString
0x1400eb240  nop     dword ptr [rax+rax+00h]
0x1400eb245  mov     eax, [rbp+57h+Status]
0x1400eb248  test    eax, eax
0x1400eb24a  jz      short loc_1400EB275
0x1400eb24c  mov     rcx, cs:VmsIfrLog
0x1400eb253  mov     r9d, 0Eh
0x1400eb259  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400eb25d  mov     dl, 2
0x1400eb25f  mov     [rsp+0C0h+var_98], r14
0x1400eb264  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb269  lea     r8d, [r9+6]
0x1400eb26d  call    WPP_RECORDER_SF_id
0x1400eb272  mov     eax, [rbp+57h+Status]
0x1400eb275  test    dil, dil
0x1400eb278  jz      short loc_1400EB28D
0x1400eb27a  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb27e  call    cs:__imp_NdisCloseConfiguration
0x1400eb285  nop     dword ptr [rax+rax+00h]
0x1400eb28a  mov     eax, [rbp+57h+Status]
0x1400eb28d  mov     rbx, [rsp+0C0h+arg_8]
0x1400eb295  add     rsp, 0A0h
0x1400eb29c  pop     r14
0x1400eb29e  pop     r12
0x1400eb2a0  pop     rdi
0x1400eb2a1  pop     rsi
0x1400eb2a2  pop     rbp
0x1400eb2a3  retn
```
