# BWCContentProviderConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)

- ea: `0x18000fc2c`
- end: `0x18000fd91`
- name: `?GetDWORDValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z`
- size: `357`
- prototype: `__int64 __fastcall(BWCContentProviderConfiguration *this, HKEY, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010098`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000fc2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fccf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fccf`

## string_xrefs

- `0x18000fc68`: `ConfigurationKey`
- `0x18000fd04`: `BWCContentProviderConfiguration::GetDWORDValue`
- `0x18000fd44`: `BWCContentProviderConfiguration::GetDWORDValue`
- `0x18000fd73`: `BWCContentProviderConfiguration::GetDWORDValue`

## pseudocode

```c
__int64 __fastcall BWCContentProviderConfiguration::GetDWORDValue(
        BWCContentProviderConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        BYTE *lpData)
{
  unsigned int v6; // ebx
  const char *v7; // rax
  LSTATUS v8; // eax
  __int64 v9; // r9
  __int64 *v10; // rdx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+44h] [rbp+Ch]

  v13 = HIDWORD(this);
  cbData = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v7 = "ConfigurationKey";
LABEL_23:
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (unsigned int)"BWCContentProviderConfiguration::GetDWORDValue",
        -2147024809,
        (__int64)v7);
      return v6;
    }
    return v6;
  }
  if ( a3 && lpData )
  {
    *(_DWORD *)lpData = 0;
    cbData = 4;
    v8 = RegQueryValueExW(a2, a3, 0, 0, lpData, &cbData);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 == -2147024882 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v6;
      v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
      goto LABEL_28;
    }
    if ( v6 != -2147024809 )
    {
      if ( v6 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          return v6;
        v9 = v6;
        goto LABEL_17;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        return v6;
      v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_28:
      McTemplateU0s_EventWriteTransfer(this, v10, "BWCContentProviderConfiguration::GetDWORDValue");
      return v6;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( a3 )
  {
    if ( !lpData )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v7 = "Value";
        goto LABEL_23;
      }
      return v6;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v6;
    v9 = 2147942487LL;
LABEL_17:
    McTemplateU0sq_EventWriteTransfer(this, a2, "BWCContentProviderConfiguration::GetDWORDValue", v9);
    return v6;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v7 = "ValueName";
    goto LABEL_23;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fc2c  mov     [rsp+arg_8], rbx
0x18000fc31  mov     [rsp+arg_10], rsi
0x18000fc36  mov     qword ptr [rsp+cbData], rcx
0x18000fc3b  push    rdi
0x18000fc3c  sub     rsp, 30h
0x18000fc40  mov     [rsp+38h+cbData], 0
0x18000fc48  mov     rdi, r9
0x18000fc4b  mov     rsi, r8
0x18000fc4e  mov     rax, rdx
0x18000fc51  test    rdx, rdx
0x18000fc54  jnz     short loc_18000FC74
0x18000fc56  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fc5d  mov     ebx, 80070057h
0x18000fc62  jz      loc_18000FD7F
0x18000fc68  lea     rax, aConfigurationk; "ConfigurationKey"
0x18000fc6f  jmp     loc_18000FD39
0x18000fc74  test    rsi, rsi
0x18000fc77  jnz     short loc_18000FCA0
0x18000fc79  mov     ebx, 80070057h
0x18000fc7e  test    rsi, rsi
0x18000fc81  jnz     loc_18000FD24
0x18000fc87  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fc8e  jz      loc_18000FD7F
0x18000fc94  lea     rax, aValuename; "ValueName"
0x18000fc9b  jmp     loc_18000FD39
0x18000fca0  test    rdi, rdi
0x18000fca3  jz      short loc_18000FC79
0x18000fca5  lea     rcx, [rsp+38h+cbData]
0x18000fcaa  mov     dword ptr [r9], 0
0x18000fcb1  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x18000fcb6  xor     r9d, r9d; lpType
0x18000fcb9  mov     rcx, rax; hKey
0x18000fcbc  mov     [rsp+38h+cbData], 4
0x18000fcc4  xor     r8d, r8d; lpReserved
0x18000fcc7  mov     [rsp+38h+lpData], rdi; lpData
0x18000fccc  mov     rdx, rsi; lpValueName
0x18000fccf  call    cs:__imp_RegQueryValueExW
0x18000fcd5  mov     ebx, eax
0x18000fcd7  test    eax, eax
0x18000fcd9  jle     short loc_18000FCE4
0x18000fcdb  movzx   ebx, ax
0x18000fcde  or      ebx, 80070000h
0x18000fce4  cmp     ebx, 8007000Eh
0x18000fcea  jz      short loc_18000FD63
0x18000fcec  cmp     ebx, 80070057h
0x18000fcf2  jz      short loc_18000FC7E
0x18000fcf4  test    ebx, ebx
0x18000fcf6  jz      short loc_18000FD12
0x18000fcf8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fcff  jz      short loc_18000FD7F
0x18000fd01  mov     r9d, ebx
0x18000fd04  lea     r8, aBwccontentprov; "BWCContentProviderConfiguration::GetDWO"...
0x18000fd0b  call    McTemplateU0sq_EventWriteTransfer
0x18000fd10  jmp     short loc_18000FD7F
0x18000fd12  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000fd19  jz      short loc_18000FD7F
0x18000fd1b  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000fd22  jmp     short loc_18000FD73
0x18000fd24  test    rdi, rdi
0x18000fd27  jnz     short loc_18000FD52
0x18000fd29  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fd30  jz      short loc_18000FD7F
0x18000fd32  lea     rax, aValue; "Value"
0x18000fd39  mov     r9d, 80070057h
0x18000fd3f  mov     [rsp+38h+lpData], rax
0x18000fd44  lea     r8, aBwccontentprov; "BWCContentProviderConfiguration::GetDWO"...
0x18000fd4b  call    McTemplateU0sqs_EventWriteTransfer
0x18000fd50  jmp     short loc_18000FD7F
0x18000fd52  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fd59  jz      short loc_18000FD7F
0x18000fd5b  mov     r9d, 80070057h
0x18000fd61  jmp     short loc_18000FD04
0x18000fd63  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fd6a  jz      short loc_18000FD7F
0x18000fd6c  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000fd73  lea     r8, aBwccontentprov; "BWCContentProviderConfiguration::GetDWO"...
0x18000fd7a  call    McTemplateU0s_EventWriteTransfer
0x18000fd7f  mov     rsi, [rsp+38h+arg_10]
0x18000fd84  mov     eax, ebx
0x18000fd86  mov     rbx, [rsp+38h+arg_8]
0x18000fd8b  add     rsp, 30h
0x18000fd8f  pop     rdi
0x18000fd90  retn
```
