# GetDeviceId

- ea: `0x1400eafdc`
- end: `0x1400eb235`
- name: `GetDeviceId`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1400ec3b0`

## callees

- `0x14003e9e4`
- `0x140046f1c`
- `0x140052460`
- `0x1400dabf0`
- `0x1400e4660`
- `0x1400eafdc`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x1400eb12a`
- `ntoskrnl!RtlGUIDFromString` at `0x1400eb12a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400eb1c9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400eb1c9`
- `NDIS!NdisCloseConfiguration` at `0x1400eb20e`
- `NDIS!NdisCloseConfiguration` at `0x1400eb20e`
- `NDIS!NdisReadConfiguration` at `0x1400eb0cb`
- `NDIS!NdisReadConfiguration` at `0x1400eb177`
- `NDIS!NdisReadConfiguration` at `0x1400eb0cb`
- `NDIS!NdisReadConfiguration` at `0x1400eb177`
- `NDIS!NdisOpenConfigurationEx` at `0x1400eb05e`
- `NDIS!NdisOpenConfigurationEx` at `0x1400eb05e`

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
0x1400eafdc  mov     [rsp-8+arg_8], rbx
0x1400eafe1  push    rbp
0x1400eafe2  push    rsi
0x1400eafe3  push    rdi
0x1400eafe4  push    r12
0x1400eafe6  push    r14
0x1400eafe8  lea     rbp, [rsp-37h]
0x1400eafed  sub     rsp, 0A0h
0x1400eaff4  lea     rax, aNetcfginstance; "NetCfgInstanceId"
0x1400eaffb  mov     [rbp+57h+ConfigObject.NdisHandle], rcx
0x1400eafff  mov     [rbp+57h+Keyword.Buffer], rax
0x1400eb003  mov     rbx, rdx
0x1400eb006  lea     rax, aMiniportname; "MiniportName"
0x1400eb00d  mov     [rbp+57h+Status], 0
0x1400eb014  mov     [rbp+57h+var_50.Buffer], rax
0x1400eb018  lea     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb01c  xor     eax, eax
0x1400eb01e  mov     [rbp+57h+ConfigurationHandle], 0
0x1400eb026  mov     r14, rcx
0x1400eb029  mov     [rbp+57h+ConfigObject.Flags], eax
0x1400eb02c  lea     rcx, [rbp+57h+ConfigObject]; ConfigObject
0x1400eb030  mov     [rbp+57h+ParameterValue], 0
0x1400eb038  mov     rsi, r8
0x1400eb03b  mov     [rbp+57h+var_68], 0
0x1400eb043  mov     qword ptr [rbp+57h+Keyword.Length], 220020h
0x1400eb04b  mov     dil, 1
0x1400eb04e  mov     qword ptr [rbp+57h+var_50.Length], 1A0018h
0x1400eb056  mov     qword ptr [rbp+57h+ConfigObject.Header.Type], 1801A9h
0x1400eb05e  call    cs:__imp_NdisOpenConfigurationEx
0x1400eb065  nop     dword ptr [rax+rax+00h]
0x1400eb06a  mov     [rbp+57h+Status], eax
0x1400eb06d  lea     r12, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400eb074  test    eax, eax
0x1400eb076  jz      short loc_1400EB0B3
0x1400eb078  xor     dil, dil
0x1400eb07b  mov     rcx, cs:VmsIfrLog
0x1400eb082  mov     r9d, 0Ah
0x1400eb088  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400eb08c  mov     dl, 2
0x1400eb08e  mov     rax, [rbp+57h+ConfigurationHandle]
0x1400eb092  mov     [rsp+0C0h+var_90], rax
0x1400eb097  lea     rax, [rbp+57h+ConfigObject]
0x1400eb09b  mov     [rsp+0C0h+var_98], rax
0x1400eb0a0  lea     r8d, [r9+0Ah]
0x1400eb0a4  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb0a9  call    WPP_RECORDER_SF_qqd
0x1400eb0ae  jmp     loc_1400EB1D5
0x1400eb0b3  mov     r8, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb0b7  lea     r9, [rbp+57h+Keyword]; Keyword
0x1400eb0bb  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x1400eb0bf  mov     [rsp+0C0h+ParameterType], 2; ParameterType
0x1400eb0c7  lea     rcx, [rbp+57h+Status]; Status
0x1400eb0cb  call    cs:__imp_NdisReadConfiguration
0x1400eb0d2  nop     dword ptr [rax+rax+00h]
0x1400eb0d7  mov     eax, [rbp+57h+Status]
0x1400eb0da  test    eax, eax
0x1400eb0dc  jz      short loc_1400EB11F
0x1400eb0de  mov     rcx, cs:VmsIfrLog
0x1400eb0e5  mov     r9d, 0Bh
0x1400eb0eb  mov     [rsp+0C0h+var_80], eax
0x1400eb0ef  mov     dl, 2
0x1400eb0f1  lea     rax, [rbp+57h+Keyword]
0x1400eb0f5  mov     [rsp+0C0h+var_88], rax
0x1400eb0fa  mov     rax, [rbp+57h+ConfigurationHandle]
0x1400eb0fe  lea     r8d, [r9+9]
0x1400eb102  mov     [rsp+0C0h+var_90], rax
0x1400eb107  mov     rax, [rbp+57h+ParameterValue]
0x1400eb10b  mov     [rsp+0C0h+var_98], rax
0x1400eb110  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb115  call    WPP_RECORDER_SF_qqqd
0x1400eb11a  jmp     loc_1400EB1D5
0x1400eb11f  mov     rcx, [rbp+57h+ParameterValue]
0x1400eb123  mov     rdx, rbx; Guid
0x1400eb126  add     rcx, 8; GuidString
0x1400eb12a  call    cs:__imp_RtlGUIDFromString
0x1400eb131  nop     dword ptr [rax+rax+00h]
0x1400eb136  mov     [rbp+57h+Status], eax
0x1400eb139  test    eax, eax
0x1400eb13b  jz      short loc_1400EB15F
0x1400eb13d  mov     rcx, cs:VmsIfrLog
0x1400eb144  mov     r9d, 0Ch
0x1400eb14a  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400eb14e  mov     [rsp+0C0h+var_98], rbx
0x1400eb153  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb158  call    WPP_RECORDER_SF__guid_d
0x1400eb15d  jmp     short loc_1400EB1D5
0x1400eb15f  mov     r8, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb163  lea     r9, [rbp+57h+var_50]; Keyword
0x1400eb167  lea     rdx, [rbp+57h+var_68]; ParameterValue
0x1400eb16b  mov     [rsp+0C0h+ParameterType], 2; ParameterType
0x1400eb173  lea     rcx, [rbp+57h+Status]; Status
0x1400eb177  call    cs:__imp_NdisReadConfiguration
0x1400eb17e  nop     dword ptr [rax+rax+00h]
0x1400eb183  mov     eax, [rbp+57h+Status]
0x1400eb186  test    eax, eax
0x1400eb188  jz      short loc_1400EB1BE
0x1400eb18a  mov     rcx, cs:VmsIfrLog
0x1400eb191  mov     r9d, 0Dh
0x1400eb197  mov     [rsp+0C0h+var_80], eax
0x1400eb19b  lea     rax, [rbp+57h+var_50]
0x1400eb19f  mov     [rsp+0C0h+var_88], rax
0x1400eb1a4  mov     rax, [rbp+57h+var_68]
0x1400eb1a8  mov     [rsp+0C0h+var_90], rbx
0x1400eb1ad  mov     [rsp+0C0h+var_98], rax
0x1400eb1b2  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb1b7  call    WPP_RECORDER_SF_q_guid_qd
0x1400eb1bc  jmp     short loc_1400EB1D5
0x1400eb1be  mov     rdx, [rbp+57h+var_68]
0x1400eb1c2  mov     rcx, rsi; DestinationString
0x1400eb1c5  add     rdx, 8; SourceString
0x1400eb1c9  call    cs:__imp_RtlCopyUnicodeString
0x1400eb1d0  nop     dword ptr [rax+rax+00h]
0x1400eb1d5  mov     eax, [rbp+57h+Status]
0x1400eb1d8  test    eax, eax
0x1400eb1da  jz      short loc_1400EB205
0x1400eb1dc  mov     rcx, cs:VmsIfrLog
0x1400eb1e3  mov     r9d, 0Eh
0x1400eb1e9  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400eb1ed  mov     dl, 2
0x1400eb1ef  mov     [rsp+0C0h+var_98], r14
0x1400eb1f4  mov     qword ptr [rsp+0C0h+ParameterType], r12
0x1400eb1f9  lea     r8d, [r9+6]
0x1400eb1fd  call    WPP_RECORDER_SF_id
0x1400eb202  mov     eax, [rbp+57h+Status]
0x1400eb205  test    dil, dil
0x1400eb208  jz      short loc_1400EB21D
0x1400eb20a  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400eb20e  call    cs:__imp_NdisCloseConfiguration
0x1400eb215  nop     dword ptr [rax+rax+00h]
0x1400eb21a  mov     eax, [rbp+57h+Status]
0x1400eb21d  mov     rbx, [rsp+0C0h+arg_8]
0x1400eb225  add     rsp, 0A0h
0x1400eb22c  pop     r14
0x1400eb22e  pop     r12
0x1400eb230  pop     rdi
0x1400eb231  pop     rsi
0x1400eb232  pop     rbp
0x1400eb233  retn
```
