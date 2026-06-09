# EcbDiskHasAssessmentResults

- ea: `0x1800b23a8`
- end: `0x1800b2636`
- name: `EcbDiskHasAssessmentResults`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180096e14`

## callees

- `0x180020ee8`
- `0x180021e0c`
- `0x1800b2308`
- `0x1800b23a8`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b25fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b25fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b2462`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b2462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b252d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b252d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b260a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b260a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b2523`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b2523`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2588`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2588`

## string_xrefs

- `0x1800b24ef`: `VolumeCreateTime`
- `0x1800b25a4`: `ERROR: Failed to open a volume %ws, error %d\n`

## pseudocode

```c
__int64 EcbDiskHasAssessmentResults()
{
  HKEY v0; // rcx
  __int64 v1; // rdi
  __int64 LastError; // rbx
  HRESULT v3; // eax
  HANDLE FileW; // rax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v9; // [rsp+5Ch] [rbp-A4h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  BYTE v12[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+78h] [rbp-88h]
  wchar_t pszDest[24]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  dwDisposition = 0;
  v0 = *(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL);
  v1 = -1;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_QWORD *)v12 = 0;
  v9 = 0;
  v13 = 0;
  hKey = 0;
  LODWORD(LastError) = RegCreateKeyExW(v0, L"DiskAssessment", 0, 0, 0, 1u, 0, &hKey, &dwDisposition);
  if ( !(_DWORD)LastError )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"VolumeSerialNumber", 0, &Type, Data, &cbData)
      && Type == 4
      && cbData == 4
      && (cbData = 8, !RegQueryValueExW(hKey, L"VolumeCreateTime", 0, &Type, v12, &cbData))
      && Type == 11
      && cbData == 8 )
    {
      if ( GetWindowsDirectoryW(Buffer, 0x104u) )
      {
        v3 = StringCchPrintfW(pszDest, 0x14u, L"\\\\.\\%wc:", Buffer[0]);
        if ( v3 >= 0 )
        {
          FileW = CreateFileW(pszDest, 0x80000000, 3u, 0, 3u, 0x80u, 0);
          v1 = (__int64)FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            EcbUtilsOut(1, "ERROR: Failed to open a volume %ws, error %d\n", pszDest, LastError);
          }
          else
          {
            LODWORD(LastError) = EcbDiskGetVolumeIds(FileW);
            if ( !(_DWORD)LastError && (v9 != *(_DWORD *)Data || v13 != *(_QWORD *)v12) )
              LODWORD(LastError) = 1173;
          }
        }
        else
        {
          LODWORD(LastError) = (unsigned __int16)v3;
        }
      }
      else
      {
        LODWORD(LastError) = GetLastError();
      }
    }
    else
    {
      LODWORD(LastError) = 1015;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 != -1 )
    CloseHandle((HANDLE)v1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800b23a8  mov     [rsp-8+arg_0], rbx
0x1800b23ad  mov     [rsp-8+arg_8], rdi
0x1800b23b2  push    rbp
0x1800b23b3  lea     rbp, [rsp-1D0h]
0x1800b23bb  sub     rsp, 2D0h
0x1800b23c2  mov     rax, cs:__security_cookie
0x1800b23c9  xor     rax, rsp
0x1800b23cc  mov     [rbp+1D0h+var_10], rax
0x1800b23d3  mov     rcx, cs:PfSvcGlobals
0x1800b23da  lea     rax, [rsp+2D0h+dwDisposition]
0x1800b23df  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x1800b23e4  lea     rdx, aDiskassessment; "DiskAssessment"
0x1800b23eb  lea     rax, [rsp+2D0h+hKey]
0x1800b23f0  mov     [rsp+2D0h+dwDisposition], 0
0x1800b23f8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800b23fd  xor     r9d, r9d; lpClass
0x1800b2400  mov     rcx, [rcx+598h]; hKey
0x1800b2407  xor     r8d, r8d; Reserved
0x1800b240a  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b2413  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b2417  mov     [rsp+2D0h+samDesired], 1; samDesired
0x1800b241f  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x1800b2427  mov     [rsp+2D0h+Type], 0
0x1800b242f  mov     [rsp+2D0h+cbData], 0
0x1800b2437  mov     dword ptr [rsp+2D0h+Data], 0
0x1800b243f  mov     qword ptr [rsp+2D0h+var_260], 0
0x1800b2448  mov     [rsp+2D0h+var_274], 0
0x1800b2450  mov     [rsp+2D0h+var_258], 0
0x1800b2459  mov     [rsp+2D0h+hKey], 0
0x1800b2462  call    cs:__imp_RegCreateKeyExW
0x1800b2468  mov     ebx, eax
0x1800b246a  test    eax, eax
0x1800b246c  jnz     loc_1800B25F1
0x1800b2472  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b2477  lea     rax, [rsp+2D0h+cbData]
0x1800b247c  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x1800b2481  lea     r9, [rsp+2D0h+Type]; lpType
0x1800b2486  lea     rax, [rsp+2D0h+Data]
0x1800b248b  mov     [rsp+2D0h+cbData], 4
0x1800b2493  xor     r8d, r8d; lpReserved
0x1800b2496  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800b249b  lea     rdx, aVolumeserialnu; "VolumeSerialNumber"
0x1800b24a2  call    cs:__imp_RegQueryValueExW
0x1800b24a8  test    eax, eax
0x1800b24aa  jnz     loc_1800B25EC
0x1800b24b0  cmp     [rsp+2D0h+Type], 4
0x1800b24b5  jnz     loc_1800B25EC
0x1800b24bb  cmp     [rsp+2D0h+cbData], 4
0x1800b24c0  jnz     loc_1800B25EC
0x1800b24c6  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b24cb  lea     rax, [rsp+2D0h+cbData]
0x1800b24d0  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x1800b24d5  lea     r9, [rsp+2D0h+Type]; lpType
0x1800b24da  lea     rax, [rsp+2D0h+var_260]
0x1800b24df  mov     [rsp+2D0h+cbData], 8
0x1800b24e7  xor     r8d, r8d; lpReserved
0x1800b24ea  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800b24ef  lea     rdx, aVolumecreateti; "VolumeCreateTime"
0x1800b24f6  call    cs:__imp_RegQueryValueExW
0x1800b24fc  test    eax, eax
0x1800b24fe  jnz     loc_1800B25EC
0x1800b2504  cmp     [rsp+2D0h+Type], 0Bh
0x1800b2509  jnz     loc_1800B25EC
0x1800b250f  cmp     [rsp+2D0h+cbData], 8
0x1800b2514  jnz     loc_1800B25EC
0x1800b251a  mov     edx, 104h; uSize
0x1800b251f  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x1800b2523  call    cs:__imp_GetWindowsDirectoryW
0x1800b2529  test    eax, eax
0x1800b252b  jnz     short loc_1800B253A
0x1800b252d  call    cs:__imp_GetLastError
0x1800b2533  mov     ebx, eax
0x1800b2535  jmp     loc_1800B25F1
0x1800b253a  movzx   r9d, [rbp+1D0h+Buffer]
0x1800b253f  lea     r8, aWc; "\\\\.\\%wc:"
0x1800b2546  mov     edx, 14h; cchDest
0x1800b254b  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x1800b254f  call    StringCchPrintfW
0x1800b2554  test    eax, eax
0x1800b2556  jns     short loc_1800B2560
0x1800b2558  movzx   ebx, ax
0x1800b255b  jmp     loc_1800B25F1
0x1800b2560  mov     [rsp+2D0h+lpSecurityAttributes], 0; hTemplateFile
0x1800b2569  lea     rcx, [rbp+1D0h+pszDest]; lpFileName
0x1800b256d  mov     r8d, 3; dwShareMode
0x1800b2573  mov     [rsp+2D0h+samDesired], 80h; dwFlagsAndAttributes
0x1800b257b  xor     r9d, r9d; lpSecurityAttributes
0x1800b257e  mov     [rsp+2D0h+dwOptions], r8d; dwCreationDisposition
0x1800b2583  mov     edx, 80000000h; dwDesiredAccess
0x1800b2588  call    cs:__imp_CreateFileW
0x1800b258e  mov     rdi, rax
0x1800b2591  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b2595  jnz     short loc_1800B25B7
0x1800b2597  call    cs:__imp_GetLastError
0x1800b259d  mov     r9d, eax
0x1800b25a0  lea     r8, [rbp+1D0h+pszDest]
0x1800b25a4  lea     rdx, aErrorFailedToO; "ERROR: Failed to open a volume %ws, err"...
0x1800b25ab  mov     ebx, eax
0x1800b25ad  lea     ecx, [rdi+2]
0x1800b25b0  call    EcbUtilsOut
0x1800b25b5  jmp     short loc_1800B25F1
0x1800b25b7  lea     r8, [rsp+2D0h+var_258]
0x1800b25bc  mov     rcx, rax; FileHandle
0x1800b25bf  lea     rdx, [rsp+2D0h+var_274]
0x1800b25c4  call    EcbDiskGetVolumeIds
0x1800b25c9  mov     ebx, eax
0x1800b25cb  test    eax, eax
0x1800b25cd  jnz     short loc_1800B25F1
0x1800b25cf  mov     eax, dword ptr [rsp+2D0h+Data]
0x1800b25d3  cmp     [rsp+2D0h+var_274], eax
0x1800b25d7  jnz     short loc_1800B25E5
0x1800b25d9  mov     rax, qword ptr [rsp+2D0h+var_260]
0x1800b25de  cmp     [rsp+2D0h+var_258], rax
0x1800b25e3  jz      short loc_1800B25F1
0x1800b25e5  mov     ebx, 495h
0x1800b25ea  jmp     short loc_1800B25F1
0x1800b25ec  mov     ebx, 3F7h
0x1800b25f1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b25f6  test    rcx, rcx
0x1800b25f9  jz      short loc_1800B2601
0x1800b25fb  call    cs:__imp_RegCloseKey
0x1800b2601  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800b2605  jz      short loc_1800B2610
0x1800b2607  mov     rcx, rdi; hObject
0x1800b260a  call    cs:__imp_CloseHandle
0x1800b2610  mov     eax, ebx
0x1800b2612  mov     rcx, [rbp+1D0h+var_10]
0x1800b2619  xor     rcx, rsp; StackCookie
0x1800b261c  call    __security_check_cookie
0x1800b2621  lea     r11, [rsp+2D0h+var_s0]
0x1800b2629  mov     rbx, [r11+10h]
0x1800b262d  mov     rdi, [r11+18h]
0x1800b2631  mov     rsp, r11
0x1800b2634  pop     rbp
0x1800b2635  retn
```
