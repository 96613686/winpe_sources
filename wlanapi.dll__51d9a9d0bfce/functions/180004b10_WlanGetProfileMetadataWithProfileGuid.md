# WlanGetProfileMetadataWithProfileGuid

- ea: `0x180004b10`
- end: `0x18000501a`
- name: `WlanGetProfileMetadataWithProfileGuid`
- size: `1290`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, int, LPCWSTR lpValueName, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180004b10`
- `0x180005020`
- `0x180005330`
- `0x180005430`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x18001a5bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dca`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180004e76`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180004e76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004e5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004e5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004caf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004f0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004f0c`

## pseudocode

```c
__int64 __fastcall WlanGetProfileMetadataWithProfileGuid(
        GUID *rguid,
        GUID *a2,
        int a3,
        LPCWSTR lpValueName,
        DWORD *a5,
        _QWORD *a6)
{
  __int64 v10; // r15
  union DOT11_OUI_HEADER *v11; // r10
  __int64 i; // rcx
  int v13; // edx
  __int64 v14; // rcx
  int v15; // edx
  __int64 v16; // rax
  int v17; // edx
  unsigned int ProfileFilePath; // edi
  HKEY v19; // rsi
  BYTE *v20; // r14
  __int64 v22; // r8
  HANDLE FileW; // rax
  _FILETIME *Memory; // rax
  DWORD v25; // eax
  DWORD LastError; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  _FILETIME LastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v10 = -1;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 218, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !rguid || !a2 || !lpValueName || !a5 || !a6 )
  {
    ProfileFilePath = 87;
    goto LABEL_29;
  }
  for ( i = 0; i != 12; i += 2 )
  {
    v13 = lpValueName[i] - aPublicCost[i];
    if ( v13 )
      break;
    v13 = lpValueName[i + 1] - aPublicCost[i + 1];
    if ( v13 )
      break;
  }
  if ( !v13 )
    goto LABEL_64;
  v14 = -1;
  do
  {
    v15 = lpValueName[v14 + 1] - aFullHotspotPro[v14 + 1];
    if ( v15 )
      break;
    v14 += 2;
    if ( v14 == 21 )
      break;
    v15 = lpValueName[v14] - aFullHotspotPro[v14];
  }
  while ( !v15 );
  if ( !v15 )
  {
LABEL_64:
    ProfileFilePath = 50;
    goto LABEL_29;
  }
  v16 = -1;
  do
  {
    v17 = lpValueName[v16 + 1] - aLastmodified[v16 + 1];
    if ( v17 )
      break;
    v16 += 2;
    if ( v16 == 13 )
      break;
    v17 = lpValueName[v16] - aLastmodified[v16];
  }
  while ( !v17 );
  if ( !v17 )
  {
    memset_0(SubKey, 0, 0x208u);
    LastWriteTime = 0;
    ProfileFilePath = StpGetProfileFilePath(rguid, a2, v22, SubKey);
    if ( !ProfileFilePath )
    {
      FileW = CreateFileW(SubKey, 0x80u, 1u, 0, 3u, 0, 0);
      v10 = (__int64)FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( GetFileTime(FileW, 0, 0, &LastWriteTime)
          && (*a5 = 8, Memory = (_FILETIME *)WlanAllocateMemory(8u), (*a6 = Memory) != 0) )
        {
          *Memory = LastWriteTime;
          v11 = WPP_GLOBAL_Control;
        }
        else
        {
          LastError = GetLastError();
          v11 = WPP_GLOBAL_Control;
          ProfileFilePath = LastError;
        }
        goto LABEL_29;
      }
      ProfileFilePath = GetLastError();
    }
LABEL_41:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  ProfileFilePath = StpGetRegKeyPath(
                      rguid,
                      a3,
                      a2,
                      (int)lpValueName,
                      phkResult,
                      SubKey,
                      (unsigned __int64)hTemplateFile);
  if ( ProfileFilePath )
    goto LABEL_41;
  ProfileFilePath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  if ( ProfileFilePath )
    goto LABEL_41;
  v19 = hKey;
  v20 = 0;
  Type = 0;
  cbData = 0;
  LastWriteTime.dwLowDateTime = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 216, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
  }
  ProfileFilePath = RegQueryValueExW(v19, lpValueName, 0, &Type, 0, &cbData);
  if ( ProfileFilePath )
    goto LABEL_27;
  if ( Type != 3 )
  {
    ProfileFilePath = 13;
    goto LABEL_27;
  }
  v25 = cbData;
  if ( !cbData )
    goto LABEL_53;
  v20 = (BYTE *)WlanAllocateMemory(cbData);
  if ( !v20 )
  {
    ProfileFilePath = GetLastError();
    goto LABEL_27;
  }
  LastWriteTime.dwLowDateTime = cbData;
  ProfileFilePath = RegQueryValueExW(v19, lpValueName, 0, &Type, v20, (LPDWORD)&LastWriteTime);
  if ( ProfileFilePath )
  {
LABEL_55:
    FreeWLMem(v20);
    goto LABEL_27;
  }
  if ( Type != 3 || (v25 = cbData, LastWriteTime.dwLowDateTime != cbData) )
  {
    ProfileFilePath = 13;
    goto LABEL_55;
  }
LABEL_53:
  *a6 = v20;
  *a5 = v25;
LABEL_27:
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      217,
      WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids,
      ProfileFilePath);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v10 != -1 )
  {
    CloseHandle((HANDLE)v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v11 + 105) >= 4u
    && (*((_BYTE *)v11 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 12), 219, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, ProfileFilePath);
  }
  return ProfileFilePath;
}

```

## disassembly

```asm
0x180004b10  push    rbp
0x180004b12  push    rbx
0x180004b13  push    rsi
0x180004b14  push    rdi
0x180004b15  push    r12
0x180004b17  push    r13
0x180004b19  push    r14
0x180004b1b  push    r15
0x180004b1d  lea     rbp, [rsp-188h]
0x180004b25  sub     rsp, 288h
0x180004b2c  mov     rax, cs:__security_cookie
0x180004b33  xor     rax, rsp
0x180004b36  mov     [rbp+1C0h+var_50], rax
0x180004b3d  mov     r12, [rbp+1C0h+arg_20]
0x180004b44  mov     rbx, r9
0x180004b47  mov     r13, [rbp+1C0h+arg_28]
0x180004b4e  mov     r14d, r8d
0x180004b51  mov     rsi, rdx
0x180004b54  mov     [rsp+2C0h+hKey], 0
0x180004b5d  mov     rdi, rcx
0x180004b60  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180004b67  mov     r10, cs:WPP_GLOBAL_Control
0x180004b6e  lea     rax, WPP_GLOBAL_Control
0x180004b75  cmp     r10, rax
0x180004b78  jnz     loc_180004D90
0x180004b7e  test    rdi, rdi
0x180004b81  jz      loc_180004DD9
0x180004b87  test    rsi, rsi
0x180004b8a  jz      loc_180004DD9
0x180004b90  test    rbx, rbx
0x180004b93  jz      loc_180004DD9
0x180004b99  test    r12, r12
0x180004b9c  jz      loc_180004DD9
0x180004ba2  test    r13, r13
0x180004ba5  jz      loc_180004DD9
0x180004bab  lea     r8, aPublicCost; "Public Cost"
0x180004bb2  xor     ecx, ecx
0x180004bb4  nop     dword ptr [rax+00h]
0x180004bb8  nop     dword ptr [rax+rax+00000000h]
0x180004bc0  movzx   edx, word ptr [rbx+rcx*2]
0x180004bc4  movzx   eax, word ptr [r8+rcx*2]
0x180004bc9  sub     edx, eax
0x180004bcb  jnz     short loc_180004BE6
0x180004bcd  movzx   edx, word ptr [rbx+rcx*2+2]
0x180004bd2  movzx   eax, word ptr [r8+rcx*2+2]
0x180004bd8  sub     edx, eax
0x180004bda  jnz     short loc_180004BE6
0x180004bdc  add     rcx, 2
0x180004be0  cmp     rcx, 0Ch
0x180004be4  jnz     short loc_180004BC0
0x180004be6  test    edx, edx
0x180004be8  jz      loc_180004FE8
0x180004bee  lea     r8, aFullHotspotPro; "Full Hotspot Profile"
0x180004bf5  mov     rcx, r15
0x180004bf8  nop     dword ptr [rax+rax+00000000h]
0x180004c00  movzx   edx, word ptr [rbx+rcx*2+2]
0x180004c05  movzx   eax, word ptr [r8+rcx*2+2]
0x180004c0b  sub     edx, eax
0x180004c0d  jnz     short loc_180004C26
0x180004c0f  add     rcx, 2
0x180004c13  cmp     rcx, 15h
0x180004c17  jz      short loc_180004C26
0x180004c19  movzx   edx, word ptr [rbx+rcx*2]
0x180004c1d  movzx   eax, word ptr [r8+rcx*2]
0x180004c22  sub     edx, eax
0x180004c24  jz      short loc_180004C00
0x180004c26  test    edx, edx
0x180004c28  jz      loc_180004FE8
0x180004c2e  lea     r8, aLastmodified; "LastModified"
0x180004c35  mov     rax, r15
0x180004c38  nop     dword ptr [rax+rax+00000000h]
0x180004c40  movzx   edx, word ptr [rbx+rax*2+2]
0x180004c45  movzx   ecx, word ptr [r8+rax*2+2]
0x180004c4b  sub     edx, ecx
0x180004c4d  jnz     short loc_180004C66
0x180004c4f  add     rax, 2
0x180004c53  cmp     rax, 0Dh
0x180004c57  jz      short loc_180004C66
0x180004c59  movzx   edx, word ptr [rbx+rax*2]
0x180004c5d  movzx   ecx, word ptr [r8+rax*2]
0x180004c62  sub     edx, ecx
0x180004c64  jz      short loc_180004C40
0x180004c66  test    edx, edx
0x180004c68  jz      loc_180004E05
0x180004c6e  lea     rax, [rsp+2C0h+SubKey]
0x180004c73  mov     r8, rsi; struct _GUID *
0x180004c76  mov     edx, r14d; int
0x180004c79  mov     [rsp+2C0h+lpcbData], rax; unsigned __int16 *
0x180004c7e  mov     rcx, rdi; rguid
0x180004c81  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@H0HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID const *,int,int,ushort *,unsigned __int64)
0x180004c86  mov     edi, eax
0x180004c88  test    eax, eax
0x180004c8a  jnz     loc_180004DF2
0x180004c90  lea     rax, [rsp+2C0h+hKey]
0x180004c95  mov     r9d, 1; samDesired
0x180004c9b  xor     r8d, r8d; ulOptions
0x180004c9e  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180004ca3  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180004ca8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004caf  call    cs:__imp_RegOpenKeyExW
0x180004cb5  mov     edi, eax
0x180004cb7  test    eax, eax
0x180004cb9  jnz     loc_180004DF2
0x180004cbf  mov     rsi, [rsp+2C0h+hKey]
0x180004cc4  xor     r14d, r14d
0x180004cc7  mov     [rsp+2C0h+Type], r14d
0x180004ccc  mov     [rsp+2C0h+cbData], r14d
0x180004cd1  mov     [rsp+2C0h+LastWriteTime.dwLowDateTime], r14d
0x180004cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cdd  lea     rax, WPP_GLOBAL_Control
0x180004ce4  cmp     rcx, rax
0x180004ce7  jz      short loc_180004CF3
0x180004ce9  cmp     byte ptr [rcx+69h], 4
0x180004ced  jnb     loc_180004F7E
0x180004cf3  lea     rax, [rsp+2C0h+cbData]
0x180004cf8  xor     r8d, r8d; lpReserved
0x180004cfb  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180004d00  lea     r9, [rsp+2C0h+Type]; lpType
0x180004d05  mov     rdx, rbx; lpValueName
0x180004d08  mov     [rsp+2C0h+phkResult], r14; lpData
0x180004d0d  mov     rcx, rsi; hKey
0x180004d10  call    cs:__imp_RegQueryValueExW
0x180004d16  mov     edi, eax
0x180004d18  test    eax, eax
0x180004d1a  jz      loc_180004EC1
0x180004d20  mov     r10, cs:WPP_GLOBAL_Control
0x180004d27  lea     rbx, WPP_GLOBAL_Control
0x180004d2e  cmp     r10, rbx
0x180004d31  jz      short loc_180004D3E
0x180004d33  cmp     byte ptr [r10+69h], 4
0x180004d38  jnb     loc_180004FB9
0x180004d3e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180004d43  test    rcx, rcx
0x180004d46  jz      short loc_180004D55
0x180004d48  call    cs:__imp_RegCloseKey
0x180004d4e  mov     r10, cs:WPP_GLOBAL_Control
0x180004d55  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180004d59  jnz     short loc_180004DC7
0x180004d5b  cmp     r10, rbx
0x180004d5e  jz      short loc_180004D6B
0x180004d60  cmp     byte ptr [r10+69h], 4
0x180004d65  jnb     loc_180004FF2
0x180004d6b  mov     eax, edi
0x180004d6d  mov     rcx, [rbp+1C0h+var_50]
0x180004d74  xor     rcx, rsp; StackCookie
0x180004d77  call    __security_check_cookie
0x180004d7c  add     rsp, 288h
0x180004d83  pop     r15
0x180004d85  pop     r14
0x180004d87  pop     r13
0x180004d89  pop     r12
0x180004d8b  pop     rdi
0x180004d8c  pop     rsi
0x180004d8d  pop     rbx
0x180004d8e  pop     rbp
0x180004d8f  retn
0x180004d90  cmp     byte ptr [r10+69h], 4
0x180004d95  jb      loc_180004B7E
0x180004d9b  test    byte ptr [r10+6Ch], 2
0x180004da0  jz      loc_180004B7E
0x180004da6  mov     rcx, [r10+60h]
0x180004daa  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180004db1  mov     edx, 0DAh
0x180004db6  call    WPP_SF_
0x180004dbb  mov     r10, cs:WPP_GLOBAL_Control
0x180004dc2  jmp     loc_180004B7E
0x180004dc7  mov     rcx, r15; hObject
0x180004dca  call    cs:__imp_CloseHandle
0x180004dd0  mov     r10, cs:WPP_GLOBAL_Control
0x180004dd7  jmp     short loc_180004D5B
0x180004dd9  mov     edi, 57h ; 'W'
0x180004dde  lea     rbx, WPP_GLOBAL_Control
0x180004de5  jmp     loc_180004D3E
0x180004dea  call    cs:__imp_GetLastError
0x180004df0  mov     edi, eax
0x180004df2  mov     r10, cs:WPP_GLOBAL_Control
0x180004df9  lea     rbx, WPP_GLOBAL_Control
0x180004e00  jmp     loc_180004D3E
0x180004e05  xor     edx, edx; Val
0x180004e07  lea     rcx, [rsp+2C0h+SubKey]; void *
0x180004e0c  mov     r8d, 208h; Size
0x180004e12  call    memset_0
0x180004e17  xor     r14d, r14d
0x180004e1a  lea     r9, [rsp+2C0h+SubKey]; unsigned __int16 *
0x180004e1f  mov     rdx, rsi; GUID *
0x180004e22  mov     qword ptr [rsp+2C0h+LastWriteTime.dwLowDateTime], r14
0x180004e27  mov     rcx, rdi; rguid
0x180004e2a  call    ?StpGetProfileFilePath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetProfileFilePath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x180004e2f  mov     edi, eax
0x180004e31  test    eax, eax
0x180004e33  jnz     short loc_180004DF2
0x180004e35  mov     [rsp+2C0h+hTemplateFile], r14; hTemplateFile
0x180004e3a  lea     rcx, [rsp+2C0h+SubKey]; lpFileName
0x180004e3f  mov     dword ptr [rsp+2C0h+lpcbData], r14d; dwFlagsAndAttributes
0x180004e44  xor     r9d, r9d; lpSecurityAttributes
0x180004e47  mov     edx, 80h; dwDesiredAccess
0x180004e4c  mov     dword ptr [rsp+2C0h+phkResult], 3; dwCreationDisposition
0x180004e54  mov     r8d, 1; dwShareMode
0x180004e5a  call    cs:__imp_CreateFileW
0x180004e60  mov     r15, rax
0x180004e63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004e67  jz      short loc_180004DEA
0x180004e69  lea     r9, [rsp+2C0h+LastWriteTime]; lpLastWriteTime
0x180004e6e  xor     r8d, r8d; lpLastAccessTime
0x180004e71  xor     edx, edx; lpCreationTime
0x180004e73  mov     rcx, rax; hFile
0x180004e76  call    cs:__imp_GetFileTime
0x180004e7c  test    eax, eax
0x180004e7e  jz      loc_180004F63
0x180004e84  mov     ecx, 8; dwMemorySize
0x180004e89  mov     dword ptr [r12], 8
0x180004e91  call    WlanAllocateMemory
0x180004e96  mov     [r13+0], rax
0x180004e9a  mov     rcx, rax
0x180004e9d  test    rax, rax
0x180004ea0  jz      loc_180004F48
0x180004ea6  mov     rax, qword ptr [rsp+2C0h+LastWriteTime.dwLowDateTime]
0x180004eab  lea     rbx, WPP_GLOBAL_Control
0x180004eb2  mov     [rcx], rax
0x180004eb5  mov     r10, cs:WPP_GLOBAL_Control
0x180004ebc  jmp     loc_180004D3E
0x180004ec1  cmp     [rsp+2C0h+Type], 3
0x180004ec6  jnz     loc_180004FA2
0x180004ecc  mov     eax, [rsp+2C0h+cbData]
0x180004ed0  test    eax, eax
0x180004ed2  jz      short loc_180004F29
0x180004ed4  mov     ecx, eax; dwMemorySize
0x180004ed6  call    WlanAllocateMemory
0x180004edb  mov     r14, rax
0x180004ede  test    rax, rax
0x180004ee1  jz      loc_180004FAC
0x180004ee7  mov     eax, [rsp+2C0h+cbData]
0x180004eeb  lea     r9, [rsp+2C0h+Type]; lpType
0x180004ef0  mov     [rsp+2C0h+LastWriteTime.dwLowDateTime], eax
0x180004ef4  xor     r8d, r8d; lpReserved
0x180004ef7  lea     rax, [rsp+2C0h+LastWriteTime]
0x180004efc  mov     rdx, rbx; lpValueName
0x180004eff  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180004f04  mov     rcx, rsi; hKey
0x180004f07  mov     [rsp+2C0h+phkResult], r14; lpData
0x180004f0c  call    cs:__imp_RegQueryValueExW
0x180004f12  mov     edi, eax
0x180004f14  test    eax, eax
0x180004f16  jnz     short loc_180004F3B
0x180004f18  cmp     [rsp+2C0h+Type], 3
0x180004f1d  jnz     short loc_180004F36
0x180004f1f  mov     eax, [rsp+2C0h+cbData]
0x180004f23  cmp     [rsp+2C0h+LastWriteTime.dwLowDateTime], eax
0x180004f27  jnz     short loc_180004F36
0x180004f29  mov     [r13+0], r14
0x180004f2d  mov     [r12], eax
0x180004f31  jmp     loc_180004D20
0x180004f36  mov     edi, 0Dh
0x180004f3b  mov     rcx, r14
0x180004f3e  call    FreeWLMem
0x180004f43  jmp     loc_180004D20
0x180004f48  call    cs:__imp_GetLastError
0x180004f4e  mov     r10, cs:WPP_GLOBAL_Control
0x180004f55  lea     rbx, WPP_GLOBAL_Control
0x180004f5c  mov     edi, eax
0x180004f5e  jmp     loc_180004D3E
0x180004f63  call    cs:__imp_GetLastError
0x180004f69  mov     r10, cs:WPP_GLOBAL_Control
0x180004f70  lea     rbx, WPP_GLOBAL_Control
0x180004f77  mov     edi, eax
0x180004f79  jmp     loc_180004D3E
0x180004f7e  test    byte ptr [rcx+6Ch], 2
0x180004f82  jz      loc_180004CF3
0x180004f88  mov     rcx, [rcx+60h]
0x180004f8c  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180004f93  mov     edx, 0D8h
0x180004f98  call    WPP_SF_
0x180004f9d  jmp     loc_180004CF3
0x180004fa2  mov     edi, 0Dh
0x180004fa7  jmp     loc_180004D20
0x180004fac  call    cs:__imp_GetLastError
0x180004fb2  mov     edi, eax
0x180004fb4  jmp     loc_180004D20
0x180004fb9  test    byte ptr [r10+6Ch], 2
0x180004fbe  jz      loc_180004D3E
0x180004fc4  mov     rcx, [r10+60h]
0x180004fc8  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180004fcf  mov     edx, 0D9h
0x180004fd4  mov     r9d, edi
0x180004fd7  call    WPP_SF_d
0x180004fdc  mov     r10, cs:WPP_GLOBAL_Control
0x180004fe3  jmp     loc_180004D3E
0x180004fe8  mov     edi, 32h ; '2'
0x180004fed  jmp     loc_180004DDE
0x180004ff2  test    byte ptr [r10+6Ch], 2
0x180004ff7  jz      loc_180004D6B
0x180004ffd  mov     rcx, [r10+60h]
0x180005001  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180005008  mov     edx, 0DBh
0x18000500d  mov     r9d, edi
0x180005010  call    WPP_SF_d
0x180005015  jmp     loc_180004D6B
```
