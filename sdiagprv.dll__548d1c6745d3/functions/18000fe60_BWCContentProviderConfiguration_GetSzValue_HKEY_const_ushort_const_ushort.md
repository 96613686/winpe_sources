# BWCContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)

- ea: `0x18000fe60`
- end: `0x180010091`
- name: `?GetSzValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `561`
- prototype: `__int64 __fastcall(BWCContentProviderConfiguration *this, HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010098`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x18000fe60`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ffcb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ffcb`

## string_xrefs

- `0x18000fe9e`: `ConfigurationKey`
- `0x18000feab`: `BWCContentProviderConfiguration::GetSzValue`
- `0x18000ff67`: `BWCContentProviderConfiguration::GetSzValue`
- `0x18001001d`: `BWCContentProviderConfiguration::GetSzValue`
- `0x18001006b`: `BWCContentProviderConfiguration::GetSzValue`

## pseudocode

```c
__int64 __fastcall BWCContentProviderConfiguration::GetSzValue(
        BWCContentProviderConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  signed int v7; // ebx
  BYTE *lpData; // rdi
  const char *v9; // rax
  LSTATUS v10; // eax
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v13; // rax
  __int64 *v14; // rdx
  HANDLE v15; // rax
  LSTATUS v17; // eax
  __int64 v18; // r9
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int v20; // [rsp+54h] [rbp+Ch]

  v20 = HIDWORD(this);
  cbData = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"BWCContentProviderConfiguration::GetSzValue",
        -2147024809,
        (__int64)"ConfigurationKey");
    return (unsigned int)v7;
  }
  lpData = 0;
  if ( a3 && a4 )
  {
    *a4 = 0;
    v10 = RegQueryValueExW(a2, a3, 0, 0, 0, &cbData);
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    if ( v7 >= 0 )
    {
      v11 = cbData;
      ProcessHeap = GetProcessHeap();
      v13 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v11);
      lpData = v13;
      if ( !v13 )
      {
        v7 = -2147024882;
LABEL_15:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_18;
        v14 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
        goto LABEL_17;
      }
      memset_0(v13, 0, cbData);
      v17 = RegQueryValueExW(a2, a3, 0, 0, lpData, &cbData);
      v7 = v17;
      if ( v17 > 0 )
        v7 = (unsigned __int16)v17 | 0x80070000;
      if ( v7 >= 0 )
        v7 = SDiagPrviCopyPWSTR((const unsigned __int16 *)lpData, a4);
    }
    if ( v7 == -2147024882 )
      goto LABEL_15;
    if ( v7 != -2147024809 )
    {
      if ( v7 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_18;
        v18 = (unsigned int)v7;
        goto LABEL_30;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      {
        v14 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_17:
        McTemplateU0s_EventWriteTransfer(this, v14, "BWCContentProviderConfiguration::GetSzValue");
        goto LABEL_18;
      }
      goto LABEL_18;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( !a3 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_18;
    v9 = "ValueName";
LABEL_36:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"BWCContentProviderConfiguration::GetSzValue",
      -2147024809,
      (__int64)v9);
    goto LABEL_18;
  }
  if ( !a4 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_18;
    v9 = "Value";
    goto LABEL_36;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v18 = 2147942487LL;
LABEL_30:
    McTemplateU0sq_EventWriteTransfer(this, a2, "BWCContentProviderConfiguration::GetSzValue", v18);
  }
LABEL_18:
  if ( lpData )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, lpData);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fe60  mov     rax, rsp
0x18000fe63  mov     [rax+10h], rbx
0x18000fe67  mov     [rax+18h], rbp
0x18000fe6b  mov     [rax+8], rcx
0x18000fe6f  push    rsi
0x18000fe70  push    rdi
0x18000fe71  push    r14
0x18000fe73  sub     rsp, 30h
0x18000fe77  mov     dword ptr [rax+8], 0
0x18000fe7e  mov     rsi, r9
0x18000fe81  mov     rbp, r8
0x18000fe84  mov     r14, rdx
0x18000fe87  test    rdx, rdx
0x18000fe8a  jnz     short loc_18000FEC1
0x18000fe8c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fe93  mov     ebx, 80070057h
0x18000fe98  jz      loc_18000FF8C
0x18000fe9e  lea     rax, aConfigurationk; "ConfigurationKey"
0x18000fea5  mov     r9d, 80070057h
0x18000feab  lea     r8, aBwccontentprov_8; "BWCContentProviderConfiguration::GetSzV"...
0x18000feb2  mov     [rsp+48h+lpData], rax
0x18000feb7  call    McTemplateU0sqs_EventWriteTransfer
0x18000febc  jmp     loc_18000FF8C
0x18000fec1  xor     edi, edi
0x18000fec3  test    rbp, rbp
0x18000fec6  jnz     short loc_18000FEEF
0x18000fec8  mov     ebx, 80070057h
0x18000fecd  test    rbp, rbp
0x18000fed0  jnz     loc_180010047
0x18000fed6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fedd  jz      loc_18000FF73
0x18000fee3  lea     rax, aValuename; "ValueName"
0x18000feea  jmp     loc_180010060
0x18000feef  test    rsi, rsi
0x18000fef2  jz      short loc_18000FEC8
0x18000fef4  lea     rax, [rsp+48h+cbData]
0x18000fef9  mov     [r9], rdi
0x18000fefc  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000ff01  xor     r9d, r9d; lpType
0x18000ff04  xor     r8d, r8d; lpReserved
0x18000ff07  mov     [rsp+48h+lpData], rdi; lpData
0x18000ff0c  mov     rdx, rbp; lpValueName
0x18000ff0f  mov     rcx, r14; hKey
0x18000ff12  call    cs:__imp_RegQueryValueExW
0x18000ff18  mov     ebx, eax
0x18000ff1a  test    eax, eax
0x18000ff1c  jle     short loc_18000FF27
0x18000ff1e  movzx   ebx, ax
0x18000ff21  or      ebx, 80070000h
0x18000ff27  test    ebx, ebx
0x18000ff29  js      loc_18000FFF1
0x18000ff2f  mov     ebx, [rsp+48h+cbData]
0x18000ff33  call    cs:__imp_GetProcessHeap
0x18000ff39  mov     r8d, ebx; dwBytes
0x18000ff3c  mov     edx, 8; dwFlags
0x18000ff41  mov     rcx, rax; hHeap
0x18000ff44  call    cs:__imp_HeapAlloc
0x18000ff4a  mov     rdi, rax
0x18000ff4d  test    rax, rax
0x18000ff50  jnz     short loc_18000FFA1
0x18000ff52  mov     ebx, 8007000Eh
0x18000ff57  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000ff5e  jz      short loc_18000FF73
0x18000ff60  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000ff67  lea     r8, aBwccontentprov_8; "BWCContentProviderConfiguration::GetSzV"...
0x18000ff6e  call    McTemplateU0s_EventWriteTransfer
0x18000ff73  test    rdi, rdi
0x18000ff76  jz      short loc_18000FF8C
0x18000ff78  call    cs:__imp_GetProcessHeap
0x18000ff7e  mov     r8, rdi; lpMem
0x18000ff81  xor     edx, edx; dwFlags
0x18000ff83  mov     rcx, rax; hHeap
0x18000ff86  call    cs:__imp_HeapFree
0x18000ff8c  mov     rbp, [rsp+48h+arg_10]
0x18000ff91  mov     eax, ebx
0x18000ff93  mov     rbx, [rsp+48h+arg_8]
0x18000ff98  add     rsp, 30h
0x18000ff9c  pop     r14
0x18000ff9e  pop     rdi
0x18000ff9f  pop     rsi
0x18000ffa0  retn
0x18000ffa1  mov     r8d, [rsp+48h+cbData]; Size
0x18000ffa6  xor     edx, edx; Val
0x18000ffa8  mov     rcx, rdi; void *
0x18000ffab  call    memset_0
0x18000ffb0  lea     rax, [rsp+48h+cbData]
0x18000ffb5  xor     r9d, r9d; lpType
0x18000ffb8  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000ffbd  xor     r8d, r8d; lpReserved
0x18000ffc0  mov     rdx, rbp; lpValueName
0x18000ffc3  mov     [rsp+48h+lpData], rdi; lpData
0x18000ffc8  mov     rcx, r14; hKey
0x18000ffcb  call    cs:__imp_RegQueryValueExW
0x18000ffd1  mov     ebx, eax
0x18000ffd3  test    eax, eax
0x18000ffd5  jle     short loc_18000FFE0
0x18000ffd7  movzx   ebx, ax
0x18000ffda  or      ebx, 80070000h
0x18000ffe0  test    ebx, ebx
0x18000ffe2  js      short loc_18000FFF1
0x18000ffe4  mov     rdx, rsi; unsigned __int16 **
0x18000ffe7  mov     rcx, rdi; unsigned __int16 *
0x18000ffea  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x18000ffef  mov     ebx, eax
0x18000fff1  cmp     ebx, 8007000Eh
0x18000fff7  jz      loc_18000FF57
0x18000fffd  cmp     ebx, 80070057h
0x180010003  jz      loc_18000FECD
0x180010009  test    ebx, ebx
0x18001000b  jz      short loc_18001002E
0x18001000d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180010014  jz      loc_18000FF73
0x18001001a  mov     r9d, ebx
0x18001001d  lea     r8, aBwccontentprov_8; "BWCContentProviderConfiguration::GetSzV"...
0x180010024  call    McTemplateU0sq_EventWriteTransfer
0x180010029  jmp     loc_18000FF73
0x18001002e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180010035  jz      loc_18000FF73
0x18001003b  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180010042  jmp     loc_18000FF67
0x180010047  test    rsi, rsi
0x18001004a  jnz     short loc_18001007C
0x18001004c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180010053  jz      loc_18000FF73
0x180010059  lea     rax, aValue; "Value"
0x180010060  mov     r9d, 80070057h
0x180010066  mov     [rsp+48h+lpData], rax
0x18001006b  lea     r8, aBwccontentprov_8; "BWCContentProviderConfiguration::GetSzV"...
0x180010072  call    McTemplateU0sqs_EventWriteTransfer
0x180010077  jmp     loc_18000FF73
0x18001007c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180010083  jz      loc_18000FF73
0x180010089  mov     r9d, 80070057h
0x18001008f  jmp     short loc_18001001D
```
