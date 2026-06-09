# QueryRemoteServerConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)

- ea: `0x180007e2c`
- end: `0x180007f61`
- name: `?GetDWORDValue@QueryRemoteServerConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z`
- size: `309`
- prototype: `__int64 __fastcall(QueryRemoteServerConfiguration *this, HKEY, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007f68`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180007e2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007eda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007eda`

## string_xrefs

- `0x180007e9b`: `QueryRemoteServerConfiguration::GetDWORDValue`
- `0x180007f0b`: `QueryRemoteServerConfiguration::GetDWORDValue`
- `0x180007f24`: `QueryRemoteServerConfiguration::GetDWORDValue`
- `0x180007f48`: `QueryRemoteServerConfiguration::GetDWORDValue`
- `0x180007e60`: `ConfigurationKey`

## pseudocode

```c
__int64 __fastcall QueryRemoteServerConfiguration::GetDWORDValue(
        QueryRemoteServerConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        BYTE *lpData)
{
  unsigned int v5; // ebx
  const char *v6; // rax
  LSTATUS v7; // eax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v10; // [rsp+54h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  cbData = 0;
  if ( a2 )
  {
    if ( lpData )
    {
      *(_DWORD *)lpData = 1;
      cbData = 4;
      v7 = RegQueryValueExW(a2, L"EnableQueryRemoteServer", 0, 0, lpData, &cbData);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 != -2147024809 )
      {
        if ( v5 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0sq_EventWriteTransfer(this, a2, "QueryRemoteServerConfiguration::GetDWORDValue", v5);
          return 0;
        }
        else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        {
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "QueryRemoteServerConfiguration::GetDWORDValue");
        }
        return v5;
      }
    }
    else
    {
      v5 = -2147024809;
    }
    if ( lpData )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(this, a2, "QueryRemoteServerConfiguration::GetDWORDValue", 2147942487LL);
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v6 = "Value";
      goto LABEL_9;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v6 = "ConfigurationKey";
LABEL_9:
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (unsigned int)"QueryRemoteServerConfiguration::GetDWORDValue",
        -2147024809,
        (__int64)v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180007e2c  mov     [rsp+arg_0], rbx
0x180007e31  mov     qword ptr [rsp+cbData], r8
0x180007e36  push    rdi
0x180007e37  sub     rsp, 30h
0x180007e3b  mov     [rsp+38h+cbData], 0
0x180007e43  mov     rdi, r9
0x180007e46  mov     rax, rdx
0x180007e49  test    rdx, rdx
0x180007e4c  jnz     short loc_180007E69
0x180007e4e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180007e55  mov     ebx, 80070057h
0x180007e5a  jz      loc_180007F54
0x180007e60  lea     rax, aConfigurationk; "ConfigurationKey"
0x180007e67  jmp     short loc_180007E90
0x180007e69  test    rdi, rdi
0x180007e6c  jnz     short loc_180007EAC
0x180007e6e  mov     ebx, 80070057h
0x180007e73  test    rdi, rdi
0x180007e76  jnz     loc_180007F39
0x180007e7c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180007e83  jz      loc_180007F54
0x180007e89  lea     rax, aValue; "Value"
0x180007e90  mov     r9d, 80070057h
0x180007e96  mov     [rsp+38h+lpData], rax
0x180007e9b  lea     r8, aQueryremoteser_0; "QueryRemoteServerConfiguration::GetDWOR"...
0x180007ea2  call    McTemplateU0sqs_EventWriteTransfer
0x180007ea7  jmp     loc_180007F54
0x180007eac  lea     rcx, [rsp+38h+cbData]
0x180007eb1  mov     dword ptr [r9], 1
0x180007eb8  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x180007ebd  lea     rdx, ValueName; "EnableQueryRemoteServer"
0x180007ec4  mov     rcx, rax; hKey
0x180007ec7  mov     [rsp+38h+cbData], 4
0x180007ecf  xor     r9d, r9d; lpType
0x180007ed2  mov     [rsp+38h+lpData], rdi; lpData
0x180007ed7  xor     r8d, r8d; lpReserved
0x180007eda  call    cs:__imp_RegQueryValueExW
0x180007ee0  mov     ebx, eax
0x180007ee2  test    eax, eax
0x180007ee4  jle     short loc_180007EEF
0x180007ee6  movzx   ebx, ax
0x180007ee9  or      ebx, 80070000h
0x180007eef  cmp     ebx, 80070057h
0x180007ef5  jz      loc_180007E73
0x180007efb  test    ebx, ebx
0x180007efd  jz      short loc_180007F1B
0x180007eff  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180007f06  jz      short loc_180007F17
0x180007f08  mov     r9d, ebx
0x180007f0b  lea     r8, aQueryremoteser_0; "QueryRemoteServerConfiguration::GetDWOR"...
0x180007f12  call    McTemplateU0sq_EventWriteTransfer
0x180007f17  xor     ebx, ebx
0x180007f19  jmp     short loc_180007F54
0x180007f1b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180007f22  jz      short loc_180007F54
0x180007f24  lea     r8, aQueryremoteser_0; "QueryRemoteServerConfiguration::GetDWOR"...
0x180007f2b  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180007f32  call    McTemplateU0s_EventWriteTransfer
0x180007f37  jmp     short loc_180007F54
0x180007f39  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180007f40  jz      short loc_180007F54
0x180007f42  mov     r9d, 80070057h
0x180007f48  lea     r8, aQueryremoteser_0; "QueryRemoteServerConfiguration::GetDWOR"...
0x180007f4f  call    McTemplateU0sq_EventWriteTransfer
0x180007f54  mov     eax, ebx
0x180007f56  mov     rbx, [rsp+38h+arg_0]
0x180007f5b  add     rsp, 30h
0x180007f5f  pop     rdi
0x180007f60  retn
```
