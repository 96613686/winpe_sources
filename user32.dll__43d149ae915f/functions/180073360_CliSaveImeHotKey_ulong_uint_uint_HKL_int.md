# CliSaveImeHotKey(ulong,uint,uint,HKL__ *,int)

- ea: `0x180073360`
- end: `0x1800735f8`
- name: `?CliSaveImeHotKey@@YAHKIIPEAUHKL__@@H@Z`
- size: `664`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, HKL, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180073360`
- `0x180073640`

## callees

- `0x180073360`
- `0x180073600`
- `0x1800736d4`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18007341d`
- `ntdll!RtlSetLastWin32Error` at `0x18007341d`
- `ntdll!wcscat_s` at `0x1800733dd`
- `ntdll!wcscat_s` at `0x1800733fa`
- `ntdll!wcscat_s` at `0x1800733dd`
- `ntdll!wcscat_s` at `0x1800733fa`
- `ntdll!wcscpy_s` at `0x1800733ca`
- `ntdll!wcscpy_s` at `0x1800733ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073543`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073596`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800735c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073543`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073596`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800735c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073411`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073411`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007348a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800734f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007348a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800734f9`

## pseudocode

```c
__int64 __fastcall CliSaveImeHotKey(unsigned int a1, int a2, int a3, HKL a4, int a5)
{
  LSTATUS v6; // eax
  ULONG v7; // ecx
  int v9; // r14d
  HKEY v10; // rsi
  const WCHAR *v11; // rdx
  LSTATUS v12; // r15d
  LSTATUS v13; // r14d
  LSTATUS v14; // eax
  HKEY v15; // rcx
  ULONG v16; // esi
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v20[4]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v22[8]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Source[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Destination[48]; // [rsp+90h] [rbp-70h] BYREF

  *(_DWORD *)v20 = a2;
  *(_DWORD *)Data = a3;
  *(_QWORD *)v22 = a4;
  hKey = 0;
  if ( (unsigned int)Feature_KeyboardSettings_InputProfileHotKeys__private_IsEnabledDeviceUsageNoInline()
    && a1 - 67175425 <= 0xFBFDFBFF )
  {
    return 1;
  }
  if ( a5 )
  {
    wcscpy_s(Destination, 0x2Eu, L"Control Panel\\Input Method\\Hot Keys");
    wcscat_s(Destination, 0x2Eu, L"\\");
    NumToHexAscii(a1, Source);
    wcscat_s(Destination, 0x2Eu, Source);
    v6 = RegDeleteKeyExW(HKEY_CURRENT_USER, Destination, 0, 0);
    if ( v6 )
    {
      v7 = v6;
LABEL_6:
      RtlSetLastWin32Error(v7);
      return 0;
    }
    return 1;
  }
  v9 = 0;
  v10 = HKEY_CURRENT_USER;
  while ( 1 )
  {
    v11 = off_1800A3C10[v9];
    if ( !v11 )
      break;
    v12 = RegCreateKeyExW(v10, v11, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    RegCloseKey(v10);
    if ( v12 )
    {
      v7 = v12;
      goto LABEL_6;
    }
    v10 = hKey;
    ++v9;
  }
  NumToHexAscii(a1, Source);
  v13 = RegCreateKeyExW(v10, Source, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  RegCloseKey(v10);
  if ( v13 )
  {
    v7 = v13;
    goto LABEL_6;
  }
  v14 = RegSetValueExW(hKey, L"Virtual Key", 0, 3u, Data, 4u);
  v15 = hKey;
  v16 = v14;
  if ( v14
    || (v17 = RegSetValueExW(hKey, L"Key Modifiers", 0, 3u, v20, 4u), v15 = hKey, (v16 = v17) != 0)
    || (v18 = RegSetValueExW(hKey, L"Target IME", 0, 3u, v22, 4u), v15 = hKey, (v16 = v18) != 0) )
  {
    RegCloseKey(v15);
    CliSaveImeHotKey(a1, *(unsigned int *)Data, *(unsigned int *)v20, *(HKL *)v22, 1);
    v7 = v16;
    goto LABEL_6;
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180073360  push    rbp
0x180073362  push    rbx
0x180073363  push    rsi
0x180073364  push    rdi
0x180073365  push    r14
0x180073367  push    r15
0x180073369  lea     rbp, [rsp-8]
0x18007336e  sub     rsp, 108h
0x180073375  mov     rax, cs:__security_cookie
0x18007337c  xor     rax, rsp
0x18007337f  mov     [rbp+30h+var_40], rax
0x180073383  mov     edi, ecx
0x180073385  mov     dword ptr [rsp+130h+var_D8], edx
0x180073389  mov     dword ptr [rsp+130h+Data], r8d
0x18007338e  mov     qword ptr [rsp+130h+var_C8], r9
0x180073393  mov     [rsp+130h+hKey], 0
0x18007339c  call    Feature_KeyboardSettings_InputProfileHotKeys__private_IsEnabledDeviceUsageNoInline
0x1800733a1  test    eax, eax
0x1800733a3  jz      short loc_1800733B2
0x1800733a5  lea     eax, [rdi-4010401h]
0x1800733ab  cmp     eax, 0FBFDFBFFh
0x1800733b0  jbe     short loc_18007342A
0x1800733b2  cmp     [rbp+30h+arg_20], 0
0x1800733b6  jz      short loc_180073434
0x1800733b8  mov     ebx, 2Eh ; '.'
0x1800733bd  lea     r8, aControlPanelIn; "Control Panel\\Input Method\\Hot Keys"
0x1800733c4  mov     edx, ebx; SizeInWords
0x1800733c6  lea     rcx, [rbp+30h+Destination]; Destination
0x1800733ca  call    cs:__imp_wcscpy_s
0x1800733d0  lea     r8, asc_1800A9214; "\\"
0x1800733d7  mov     edx, ebx; SizeInWords
0x1800733d9  lea     rcx, [rbp+30h+Destination]; Destination
0x1800733dd  call    cs:__imp_wcscat_s
0x1800733e3  lea     rdx, [rsp+130h+Source]; unsigned __int16 *
0x1800733e8  mov     ecx, edi; unsigned int
0x1800733ea  call    ?NumToHexAscii@@YAXKPEAG@Z; NumToHexAscii(ulong,ushort *)
0x1800733ef  lea     r8, [rsp+130h+Source]; Source
0x1800733f4  mov     edx, ebx; SizeInWords
0x1800733f6  lea     rcx, [rbp+30h+Destination]; Destination
0x1800733fa  call    cs:__imp_wcscat_s
0x180073400  xor     r9d, r9d; Reserved
0x180073403  lea     rdx, [rbp+30h+Destination]; lpSubKey
0x180073407  xor     r8d, r8d; samDesired
0x18007340a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180073411  call    cs:__imp_RegDeleteKeyExW
0x180073417  test    eax, eax
0x180073419  jz      short loc_18007342A
0x18007341b  mov     ecx, eax; LastError
0x18007341d  call    cs:__imp_RtlSetLastWin32Error
0x180073423  xor     eax, eax
0x180073425  jmp     loc_1800735DC
0x18007342a  mov     eax, 1
0x18007342f  jmp     loc_1800735DC
0x180073434  xor     r14d, r14d
0x180073437  mov     rsi, 0FFFFFFFF80000001h
0x18007343e  lea     ebx, [r14+1]
0x180073442  movsxd  rax, r14d
0x180073445  lea     rdx, off_1800A3C10; "Control Panel"
0x18007344c  mov     rdx, [rdx+rax*8]; lpSubKey
0x180073450  test    rdx, rdx
0x180073453  jz      short loc_1800734B3
0x180073455  mov     [rsp+130h+lpdwDisposition], 0; lpdwDisposition
0x18007345e  lea     rax, [rsp+130h+hKey]
0x180073463  mov     [rsp+130h+phkResult], rax; phkResult
0x180073468  xor     r9d, r9d; lpClass
0x18007346b  mov     [rsp+130h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180073474  xor     r8d, r8d; Reserved
0x180073477  mov     [rsp+130h+samDesired], 2001Fh; samDesired
0x18007347f  mov     rcx, rsi; hKey
0x180073482  mov     [rsp+130h+dwOptions], 0; dwOptions
0x18007348a  call    cs:__imp_RegCreateKeyExW
0x180073490  mov     rcx, rsi; hKey
0x180073493  mov     r15d, eax
0x180073496  call    cs:__imp_RegCloseKey
0x18007349c  test    r15d, r15d
0x18007349f  jnz     short loc_1800734AB
0x1800734a1  mov     rsi, [rsp+130h+hKey]
0x1800734a6  add     r14d, ebx
0x1800734a9  jmp     short loc_180073442
0x1800734ab  mov     ecx, r15d
0x1800734ae  jmp     loc_18007341D
0x1800734b3  lea     rdx, [rsp+130h+Source]; unsigned __int16 *
0x1800734b8  mov     ecx, edi; unsigned int
0x1800734ba  call    ?NumToHexAscii@@YAXKPEAG@Z; NumToHexAscii(ulong,ushort *)
0x1800734bf  mov     [rsp+130h+lpdwDisposition], 0; lpdwDisposition
0x1800734c8  lea     rax, [rsp+130h+hKey]
0x1800734cd  mov     [rsp+130h+phkResult], rax; phkResult
0x1800734d2  lea     rdx, [rsp+130h+Source]; lpSubKey
0x1800734d7  mov     [rsp+130h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800734e0  xor     r9d, r9d; lpClass
0x1800734e3  mov     [rsp+130h+samDesired], 2001Fh; samDesired
0x1800734eb  xor     r8d, r8d; Reserved
0x1800734ee  mov     rcx, rsi; hKey
0x1800734f1  mov     [rsp+130h+dwOptions], 0; dwOptions
0x1800734f9  call    cs:__imp_RegCreateKeyExW
0x1800734ff  mov     rcx, rsi; hKey
0x180073502  mov     r14d, eax
0x180073505  call    cs:__imp_RegCloseKey
0x18007350b  test    r14d, r14d
0x18007350e  jz      short loc_180073518
0x180073510  mov     ecx, r14d
0x180073513  jmp     loc_18007341D
0x180073518  mov     rcx, [rsp+130h+hKey]; hKey
0x18007351d  lea     rax, [rsp+130h+Data]
0x180073522  mov     r14d, 4
0x180073528  lea     rdx, aVirtualKey; "Virtual Key"
0x18007352f  mov     [rsp+130h+samDesired], r14d; cbData
0x180073534  xor     r8d, r8d; Reserved
0x180073537  mov     qword ptr [rsp+130h+dwOptions], rax; lpData
0x18007353c  lea     r15d, [r14-1]
0x180073540  mov     r9d, r15d; dwType
0x180073543  call    cs:__imp_RegSetValueExW
0x180073549  mov     rcx, [rsp+130h+hKey]; hKey
0x18007354e  mov     esi, eax
0x180073550  test    eax, eax
0x180073552  jz      short loc_18007357A
0x180073554  call    cs:__imp_RegCloseKey
0x18007355a  mov     r9, qword ptr [rsp+130h+var_C8]; HKL
0x18007355f  mov     ecx, edi; unsigned int
0x180073561  mov     r8d, dword ptr [rsp+130h+var_D8]; unsigned int
0x180073566  mov     edx, dword ptr [rsp+130h+Data]; unsigned int
0x18007356a  mov     [rsp+130h+dwOptions], ebx; int
0x18007356e  call    ?CliSaveImeHotKey@@YAHKIIPEAUHKL__@@H@Z; CliSaveImeHotKey(ulong,uint,uint,HKL__ *,int)
0x180073573  mov     ecx, esi
0x180073575  jmp     loc_18007341D
0x18007357a  lea     rax, [rsp+130h+var_D8]
0x18007357f  mov     [rsp+130h+samDesired], r14d; cbData
0x180073584  mov     r9d, r15d; dwType
0x180073587  mov     qword ptr [rsp+130h+dwOptions], rax; lpData
0x18007358c  xor     r8d, r8d; Reserved
0x18007358f  lea     rdx, aKeyModifiers; "Key Modifiers"
0x180073596  call    cs:__imp_RegSetValueExW
0x18007359c  mov     rcx, [rsp+130h+hKey]; hKey
0x1800735a1  mov     esi, eax
0x1800735a3  test    eax, eax
0x1800735a5  jnz     short loc_180073554
0x1800735a7  lea     rax, [rsp+130h+var_C8]
0x1800735ac  mov     [rsp+130h+samDesired], r14d; cbData
0x1800735b1  mov     r9d, r15d; dwType
0x1800735b4  mov     qword ptr [rsp+130h+dwOptions], rax; lpData
0x1800735b9  xor     r8d, r8d; Reserved
0x1800735bc  lea     rdx, aTargetIme; "Target IME"
0x1800735c3  call    cs:__imp_RegSetValueExW
0x1800735c9  mov     rcx, [rsp+130h+hKey]; hKey
0x1800735ce  mov     esi, eax
0x1800735d0  test    eax, eax
0x1800735d2  jnz     short loc_180073554
0x1800735d4  call    cs:__imp_RegCloseKey
0x1800735da  mov     eax, ebx
0x1800735dc  mov     rcx, [rbp+30h+var_40]
0x1800735e0  xor     rcx, rsp; StackCookie
0x1800735e3  call    __security_check_cookie
0x1800735e8  add     rsp, 108h
0x1800735ef  pop     r15
0x1800735f1  pop     r14
0x1800735f3  pop     rdi
0x1800735f4  pop     rsi
0x1800735f5  pop     rbx
0x1800735f6  pop     rbp
0x1800735f7  retn
```
