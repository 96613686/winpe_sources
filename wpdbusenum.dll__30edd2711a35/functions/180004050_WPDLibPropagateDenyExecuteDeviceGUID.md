# WPDLibPropagateDenyExecuteDeviceGUID

- ea: `0x180004050`
- end: `0x1800042f8`
- name: `WPDLibPropagateDenyExecuteDeviceGUID`
- size: `680`
- prototype: `HRESULT __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180004050`
- `0x180004300`
- `0x1800097d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004219`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041f4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000420e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000420e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800042b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800042b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004268`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004268`

## pseudocode

```c
HRESULT __fastcall WPDLibPropagateDenyExecuteDeviceGUID(unsigned int *a1)
{
  __int64 v2; // r9
  HRESULT result; // eax
  __int64 v4; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int lpcbData; // [rsp+28h] [rbp-D8h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  int v8; // [rsp+38h] [rbp-C8h]
  int lpdwDisposition; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+68h] [rbp-98h]
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v19; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v20[256]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[256]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t SubKey[256]; // [rsp+490h] [rbp+390h] BYREF

  v14 = *((unsigned __int8 *)a1 + 15);
  v13 = *((unsigned __int8 *)a1 + 14);
  v12 = *((unsigned __int8 *)a1 + 13);
  v11 = *((unsigned __int8 *)a1 + 12);
  v10 = *((unsigned __int8 *)a1 + 11);
  v2 = *a1;
  lpdwDisposition = *((unsigned __int8 *)a1 + 10);
  v8 = *((unsigned __int8 *)a1 + 9);
  lpSecurityAttributes = *((unsigned __int8 *)a1 + 8);
  lpcbData = *((unsigned __int16 *)a1 + 3);
  phkResult = *((unsigned __int16 *)a1 + 2);
  *(_DWORD *)Data = 0;
  v19 = 0;
  Type = 0;
  cbData = 0;
  result = StringCchPrintfW(
             pszDest,
             0x100u,
             L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
             v2,
             phkResult,
             lpcbData,
             lpSecurityAttributes,
             v8,
             lpdwDisposition,
             v10,
             v11,
             v12,
             v13,
             v14);
  if ( !result )
  {
    result = StringCchPrintfW(
               SubKey,
               0x100u,
               L"%ws\\%ws",
               L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
               pszDest);
    if ( !result )
    {
      v4 = *(_QWORD *)a1 - *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1;
      if ( *(_QWORD *)a1 == *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1 )
        v4 = *((_QWORD *)a1 + 1) - *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4;
      result = v4
             ? StringCchPrintfW(v20, 0x100u, L"%ws\\%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage", pszDest)
             : StringCchPrintfW(v20, 0x100u, L"%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage");
      if ( !result )
      {
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v19)
          || (Type = 4, cbData = 4, RegQueryValueExW(v19, L"Deny_Execute", 0, &Type, Data, &cbData))
          || *(_DWORD *)Data != 1 )
        {
          hKey = 0;
          result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0x2001Fu, &hKey);
          if ( !result )
          {
            RegDeleteValueW(hKey, L"Deny_Execute");
            return RegCloseKey(hKey);
          }
        }
        else
        {
          hKey = 0;
          result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0, 0, 0x20006u, 0, &hKey, 0);
          if ( !result )
          {
            RegSetValueExW(hKey, L"Deny_Execute", 0, 4u, Data, 4u);
            return RegCloseKey(hKey);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004050  push    rbp
0x180004052  push    rbx
0x180004053  push    rsi
0x180004054  push    rdi
0x180004055  push    r14
0x180004057  push    r15
0x180004059  lea     rbp, [rsp-5A8h]
0x180004061  sub     rsp, 6A8h
0x180004068  mov     rax, cs:__security_cookie
0x18000406f  xor     rax, rsp
0x180004072  mov     [rbp+5D0h+var_40], rax
0x180004079  movzx   eax, byte ptr [rcx+0Fh]
0x18000407d  mov     rbx, rcx
0x180004080  movzx   ecx, byte ptr [rcx+0Eh]
0x180004084  xor     r15d, r15d
0x180004087  mov     [rsp+6D0h+var_668], eax
0x18000408b  mov     [rsp+6D0h+var_670], ecx
0x18000408f  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x180004096  movzx   edx, byte ptr [rbx+0Dh]
0x18000409a  movzx   r8d, byte ptr [rbx+0Ch]
0x18000409f  movzx   r9d, byte ptr [rbx+0Bh]
0x1800040a4  movzx   r10d, byte ptr [rbx+0Ah]
0x1800040a9  movzx   r11d, byte ptr [rbx+9]
0x1800040ae  movzx   edi, byte ptr [rbx+8]
0x1800040b2  movzx   esi, word ptr [rbx+6]
0x1800040b6  movzx   r14d, word ptr [rbx+4]
0x1800040bb  mov     [rsp+6D0h+var_678], edx
0x1800040bf  mov     edx, 100h; cchDest
0x1800040c4  mov     [rsp+6D0h+var_680], r8d
0x1800040c9  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x1800040d0  mov     [rsp+6D0h+var_688], r9d
0x1800040d5  mov     r9d, [rbx]
0x1800040d8  mov     dword ptr [rsp+6D0h+lpdwDisposition], r10d
0x1800040dd  mov     dword ptr [rsp+6D0h+var_698], r11d
0x1800040e2  mov     dword ptr [rsp+6D0h+lpSecurityAttributes], edi
0x1800040e6  mov     dword ptr [rsp+6D0h+lpcbData], esi
0x1800040ea  mov     dword ptr [rsp+6D0h+phkResult], r14d
0x1800040ef  mov     dword ptr [rsp+6D0h+Data], r15d
0x1800040f4  mov     [rbp+5D0h+var_648], r15
0x1800040f8  mov     [rbp+5D0h+Type], r15d
0x1800040fc  mov     [rbp+5D0h+cbData], r15d
0x180004100  call    StringCchPrintfW
0x180004105  test    eax, eax
0x180004107  jz      short loc_180004128
0x180004109  mov     rcx, [rbp+5D0h+var_40]
0x180004110  xor     rcx, rsp; StackCookie
0x180004113  call    __security_check_cookie
0x180004118  add     rsp, 6A8h
0x18000411f  pop     r15
0x180004121  pop     r14
0x180004123  pop     rdi
0x180004124  pop     rsi
0x180004125  pop     rbx
0x180004126  pop     rbp
0x180004127  retn
0x180004128  lea     rax, [rbp+5D0h+pszDest]
0x18000412f  mov     edx, 100h; cchDest
0x180004134  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000413b  mov     [rsp+6D0h+phkResult], rax
0x180004140  lea     r8, aWsWs; "%ws\\%ws"
0x180004147  lea     rcx, [rbp+5D0h+SubKey]; pszDest
0x18000414e  call    StringCchPrintfW
0x180004153  test    eax, eax
0x180004155  jnz     short loc_180004109
0x180004157  mov     rax, [rbx]
0x18000415a  sub     rax, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x180004161  jnz     short loc_18000416E
0x180004163  mov     rax, [rbx+8]
0x180004167  sub     rax, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data4
0x18000416e  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180004175  mov     edx, 100h; cchDest
0x18000417a  lea     rcx, [rbp+5D0h+var_640]; pszDest
0x18000417e  test    rax, rax
0x180004181  jz      loc_180004224
0x180004187  lea     rax, [rbp+5D0h+pszDest]
0x18000418e  lea     r8, aWsWs; "%ws\\%ws"
0x180004195  mov     [rsp+6D0h+phkResult], rax
0x18000419a  call    StringCchPrintfW
0x18000419f  test    eax, eax
0x1800041a1  jnz     loc_180004109
0x1800041a7  lea     rax, [rbp+5D0h+var_648]
0x1800041ab  mov     r9d, 20019h; samDesired
0x1800041b1  xor     r8d, r8d; ulOptions
0x1800041b4  mov     [rsp+6D0h+phkResult], rax; phkResult
0x1800041b9  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x1800041c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800041c7  call    cs:__imp_RegOpenKeyExW
0x1800041cd  test    eax, eax
0x1800041cf  jz      short loc_180004235
0x1800041d1  lea     rax, [rsp+6D0h+hKey]
0x1800041d6  mov     [rsp+6D0h+hKey], r15
0x1800041db  mov     r9d, 2001Fh; samDesired
0x1800041e1  mov     [rsp+6D0h+phkResult], rax; phkResult
0x1800041e6  xor     r8d, r8d; ulOptions
0x1800041e9  lea     rdx, [rbp+5D0h+var_640]; lpSubKey
0x1800041ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800041f4  call    cs:__imp_RegOpenKeyExW
0x1800041fa  test    eax, eax
0x1800041fc  jnz     loc_180004109
0x180004202  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180004207  lea     rdx, aDenyExecute; "Deny_Execute"
0x18000420e  call    cs:__imp_RegDeleteValueW
0x180004214  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180004219  call    cs:__imp_RegCloseKey
0x18000421f  jmp     loc_180004109
0x180004224  lea     r8, aWs; "%ws"
0x18000422b  call    StringCchPrintfW
0x180004230  jmp     loc_18000419F
0x180004235  mov     rcx, [rbp+5D0h+var_648]; hKey
0x180004239  lea     rax, [rbp+5D0h+cbData]
0x18000423d  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x180004242  lea     r9, [rbp+5D0h+Type]; lpType
0x180004246  lea     rax, [rsp+6D0h+Data]
0x18000424b  mov     [rbp+5D0h+Type], 4
0x180004252  xor     r8d, r8d; lpReserved
0x180004255  mov     [rsp+6D0h+phkResult], rax; lpData
0x18000425a  lea     rdx, aDenyExecute; "Deny_Execute"
0x180004261  mov     [rbp+5D0h+cbData], 4
0x180004268  call    cs:__imp_RegQueryValueExW
0x18000426e  test    eax, eax
0x180004270  jnz     loc_1800041D1
0x180004276  cmp     dword ptr [rsp+6D0h+Data], 1
0x18000427b  jnz     loc_1800041D1
0x180004281  mov     [rsp+6D0h+lpdwDisposition], r15; lpdwDisposition
0x180004286  lea     rax, [rsp+6D0h+hKey]
0x18000428b  mov     [rsp+6D0h+var_698], rax; phkResult
0x180004290  lea     rdx, [rbp+5D0h+var_640]; lpSubKey
0x180004294  mov     [rsp+6D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180004299  xor     r9d, r9d; lpClass
0x18000429c  mov     dword ptr [rsp+6D0h+lpcbData], 20006h; samDesired
0x1800042a4  xor     r8d, r8d; Reserved
0x1800042a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800042ae  mov     dword ptr [rsp+6D0h+phkResult], r15d; dwOptions
0x1800042b3  mov     [rsp+6D0h+hKey], r15
0x1800042b8  call    cs:__imp_RegCreateKeyExW
0x1800042be  test    eax, eax
0x1800042c0  jnz     loc_180004109
0x1800042c6  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1800042cb  lea     rax, [rsp+6D0h+Data]
0x1800042d0  mov     dword ptr [rsp+6D0h+lpcbData], 4; cbData
0x1800042d8  lea     rdx, aDenyExecute; "Deny_Execute"
0x1800042df  mov     r9d, 4; dwType
0x1800042e5  mov     [rsp+6D0h+phkResult], rax; lpData
0x1800042ea  xor     r8d, r8d; Reserved
0x1800042ed  call    cs:__imp_RegSetValueExW
0x1800042f3  jmp     loc_180004214
```
