# StSaveNamedProfileMetaData(_GUID const *,int,_GUID *,ushort const *,ulong,uchar const *)

- ea: `0x18001a988`
- end: `0x18001ad4b`
- name: `?StSaveNamedProfileMetaData@@YAKPEBU_GUID@@HPEAU1@PEBGKPEBE@Z`
- size: `963`
- prototype: `__int64 __fastcall(GUID *rguid, int, GUID *, wchar_t *String1, DWORD cbData, BYTE *lpData)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18003a9b8`
- `0x1801007a8`
- `0x180105384`
- `0x1801fcf5c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180019820`
- `0x18001a988`
- `0x180027254`
- `0x180106340`
- `0x180107330`
- `0x18021e441`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ad30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ad30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa6f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ac18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001acaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ad00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ac18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001acaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ad00`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ab62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ab62`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18001ab86`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18001ab86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StSaveNamedProfileMetaData(
        GUID *rguid,
        int a2,
        GUID *a3,
        wchar_t *String1,
        DWORD cbData,
        BYTE *lpData)
{
  __int64 FileW; // rsi
  unsigned int RegKeyPath; // eax
  unsigned int ProfileFilePath; // ebx
  DWORD LastError; // eax
  DWORD v15; // r9d
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME LastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(FileName, 0, 0x208u);
  FileW = -1;
  LastWriteTime = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 34, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
  }
  if ( !wcscmp_0(String1, L"LastModified") )
  {
    if ( cbData != 8 )
    {
      ProfileFilePath = 1630;
      goto LABEL_6;
    }
    ProfileFilePath = StpGetProfileFilePath(rguid, a3, 0, FileName);
    if ( !ProfileFilePath )
    {
      FileW = (__int64)CreateFileW(FileName, 0x100u, 2u, 0, 3u, 0, 0);
      if ( FileW == -1 || (LastWriteTime = *(FILETIME *)lpData, !SetFileTime((HANDLE)FileW, 0, 0, &LastWriteTime)) )
      {
        LastError = GetLastError();
LABEL_36:
        ProfileFilePath = LastError;
        goto LABEL_6;
      }
    }
    goto LABEL_6;
  }
  if ( wcscmp_0(String1, L"Delta") )
  {
    if ( !wcscmp_0(String1, L"Name") )
    {
      ProfileFilePath = StpGetRegKeyPath(rguid, a2, a3, 0, 0, SubKey, 0x104u);
      if ( ProfileFilePath )
        goto LABEL_6;
      ProfileFilePath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      if ( ProfileFilePath )
        goto LABEL_6;
      v15 = 1;
    }
    else
    {
      if ( wcscmp_0(String1, L"Flags") )
      {
        RegKeyPath = StpGetRegKeyPath(rguid, a2, a3, 0, 1, SubKey, 0x104u);
        goto LABEL_5;
      }
      ProfileFilePath = StpGetRegKeyPath(rguid, a2, a3, 0, 0, SubKey, 0x104u);
      if ( ProfileFilePath )
        goto LABEL_6;
      ProfileFilePath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      if ( ProfileFilePath )
        goto LABEL_6;
      v15 = 4;
    }
LABEL_35:
    LastError = RegSetValueExW(hKey, String1, 0, v15, lpData, cbData);
    goto LABEL_36;
  }
  RegKeyPath = StpGetRegKeyPath(rguid, a2, a3, 0, 0, SubKey, 0x104u);
LABEL_5:
  ProfileFilePath = RegKeyPath;
  if ( !RegKeyPath )
  {
    ProfileFilePath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !ProfileFilePath )
    {
      v15 = 3;
      goto LABEL_35;
    }
  }
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      35,
      &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids,
      ProfileFilePath);
  }
  return ProfileFilePath;
}

```

## disassembly

```asm
0x18001a988  push    rbp
0x18001a98a  push    rbx
0x18001a98b  push    rsi
0x18001a98c  push    rdi
0x18001a98d  push    r12
0x18001a98f  push    r13
0x18001a991  push    r14
0x18001a993  push    r15
0x18001a995  lea     rbp, [rsp-398h]
0x18001a99d  sub     rsp, 498h
0x18001a9a4  mov     rax, cs:__security_cookie
0x18001a9ab  xor     rax, rsp
0x18001a9ae  mov     [rbp+3D0h+var_50], rax
0x18001a9b5  mov     r15, [rbp+3D0h+lpData]
0x18001a9bc  mov     r14, r8
0x18001a9bf  mov     r12d, edx
0x18001a9c2  mov     rbx, rcx
0x18001a9c5  xor     r13d, r13d
0x18001a9c8  lea     rcx, [rbp+3D0h+FileName]; void *
0x18001a9cf  xor     edx, edx; Val
0x18001a9d1  mov     [rsp+4D0h+hKey], r13
0x18001a9d6  mov     r8d, 208h; Size
0x18001a9dc  mov     rdi, r9
0x18001a9df  call    memset_0
0x18001a9e4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a9e8  mov     qword ptr [rsp+4D0h+LastWriteTime.dwLowDateTime], r13
0x18001a9ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f4  lea     rax, WPP_GLOBAL_Control
0x18001a9fb  cmp     rcx, rax
0x18001a9fe  jnz     loc_18001AADD
0x18001aa04  lea     rdx, aLastmodified; "LastModified"
0x18001aa0b  mov     rcx, rdi; String1
0x18001aa0e  call    wcscmp_0
0x18001aa13  test    eax, eax
0x18001aa15  jz      loc_18001AB0B
0x18001aa1b  lea     rdx, aDelta; "Delta"
0x18001aa22  mov     rcx, rdi; String1
0x18001aa25  call    wcscmp_0
0x18001aa2a  test    eax, eax
0x18001aa2c  jnz     loc_18001AB9F
0x18001aa32  mov     [rsp+4D0h+hTemplateFile], 104h; unsigned __int64
0x18001aa3b  lea     rax, [rsp+4D0h+SubKey]
0x18001aa40  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18001aa45  mov     [rsp+4D0h+dwCreationDisposition], r13d; int
0x18001aa4a  mov     r8, r14; struct _GUID *
0x18001aa4d  xor     r9d, r9d; int
0x18001aa50  mov     edx, r12d; int
0x18001aa53  mov     rcx, rbx; struct _GUID *
0x18001aa56  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x18001aa5b  mov     ebx, eax
0x18001aa5d  test    eax, eax
0x18001aa5f  jz      loc_18001ACCD
0x18001aa65  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18001aa6a  test    rcx, rcx
0x18001aa6d  jz      short loc_18001AA75
0x18001aa6f  call    cs:__imp_RegCloseKey
0x18001aa75  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001aa79  jnz     loc_18001AD3D
0x18001aa7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa86  lea     rax, WPP_GLOBAL_Control
0x18001aa8d  cmp     rcx, rax
0x18001aa90  jnz     short loc_18001AAB7
0x18001aa92  mov     eax, ebx
0x18001aa94  mov     rcx, [rbp+3D0h+var_50]
0x18001aa9b  xor     rcx, rsp; StackCookie
0x18001aa9e  call    __security_check_cookie
0x18001aaa3  add     rsp, 498h
0x18001aaaa  pop     r15
0x18001aaac  pop     r14
0x18001aaae  pop     r13
0x18001aab0  pop     r12
0x18001aab2  pop     rdi
0x18001aab3  pop     rsi
0x18001aab4  pop     rbx
0x18001aab5  pop     rbp
0x18001aab6  retn
0x18001aab7  cmp     byte ptr [rcx+69h], 4
0x18001aabb  jb      short loc_18001AA92
0x18001aabd  test    byte ptr [rcx+6Ch], 1
0x18001aac1  jz      short loc_18001AA92
0x18001aac3  mov     rcx, [rcx+60h]
0x18001aac7  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18001aace  mov     edx, 23h ; '#'
0x18001aad3  mov     r9d, ebx
0x18001aad6  call    WPP_SF_d
0x18001aadb  jmp     short loc_18001AA92
0x18001aadd  cmp     byte ptr [rcx+69h], 4
0x18001aae1  jb      loc_18001AA04
0x18001aae7  test    byte ptr [rcx+6Ch], 1
0x18001aaeb  jz      loc_18001AA04
0x18001aaf1  mov     rcx, [rcx+60h]
0x18001aaf5  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18001aafc  mov     edx, 22h ; '"'
0x18001ab01  call    WPP_SF_
0x18001ab06  jmp     loc_18001AA04
0x18001ab0b  cmp     [rbp+3D0h+cbData], 8
0x18001ab12  jz      short loc_18001AB1E
0x18001ab14  mov     ebx, 65Eh
0x18001ab19  jmp     loc_18001AA65
0x18001ab1e  lea     r9, [rbp+3D0h+FileName]; unsigned __int16 *
0x18001ab25  xor     r8d, r8d; int
0x18001ab28  mov     rdx, r14; GUID *
0x18001ab2b  mov     rcx, rbx; rguid
0x18001ab2e  call    ?StpGetProfileFilePath@@YAKPEBU_GUID@@PEAU1@HPEAG_K@Z; StpGetProfileFilePath(_GUID const *,_GUID *,int,ushort *,unsigned __int64)
0x18001ab33  mov     ebx, eax
0x18001ab35  test    eax, eax
0x18001ab37  jnz     loc_18001AA65
0x18001ab3d  mov     [rsp+4D0h+hTemplateFile], r13; hTemplateFile
0x18001ab42  lea     r8d, [rax+2]; dwShareMode
0x18001ab46  mov     [rsp+4D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18001ab4b  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x18001ab52  xor     r9d, r9d; lpSecurityAttributes
0x18001ab55  mov     [rsp+4D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ab5d  mov     edx, 100h; dwDesiredAccess
0x18001ab62  call    cs:__imp_CreateFileW
0x18001ab68  mov     rsi, rax
0x18001ab6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ab6f  jz      short loc_18001AB94
0x18001ab71  mov     rax, [r15]
0x18001ab74  lea     r9, [rsp+4D0h+LastWriteTime]; lpLastWriteTime
0x18001ab79  xor     r8d, r8d; lpLastAccessTime
0x18001ab7c  mov     qword ptr [rsp+4D0h+LastWriteTime.dwLowDateTime], rax
0x18001ab81  xor     edx, edx; lpCreationTime
0x18001ab83  mov     rcx, rsi; hFile
0x18001ab86  call    cs:__imp_SetFileTime
0x18001ab8c  test    eax, eax
0x18001ab8e  jnz     loc_18001AA65
0x18001ab94  call    cs:__imp_GetLastError
0x18001ab9a  jmp     loc_18001AD36
0x18001ab9f  lea     rdx, aName; "Name"
0x18001aba6  mov     rcx, rdi; String1
0x18001aba9  call    wcscmp_0
0x18001abae  test    eax, eax
0x18001abb0  jnz     short loc_18001AC31
0x18001abb2  lea     rax, [rsp+4D0h+SubKey]
0x18001abb7  mov     [rsp+4D0h+hTemplateFile], 104h; unsigned __int64
0x18001abc0  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18001abc5  xor     r9d, r9d; int
0x18001abc8  mov     r8, r14; struct _GUID *
0x18001abcb  mov     [rsp+4D0h+dwCreationDisposition], r13d; int
0x18001abd0  mov     edx, r12d; int
0x18001abd3  mov     rcx, rbx; struct _GUID *
0x18001abd6  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x18001abdb  mov     ebx, eax
0x18001abdd  test    eax, eax
0x18001abdf  jnz     loc_18001AA65
0x18001abe5  mov     [rsp+4D0h+lpdwDisposition], r13; lpdwDisposition
0x18001abea  lea     rax, [rsp+4D0h+hKey]
0x18001abef  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18001abf4  lea     rdx, [rsp+4D0h+SubKey]; lpSubKey
0x18001abf9  mov     [rsp+4D0h+hTemplateFile], r13; lpSecurityAttributes
0x18001abfe  xor     r9d, r9d; lpClass
0x18001ac01  mov     [rsp+4D0h+dwFlagsAndAttributes], 20006h; samDesired
0x18001ac09  xor     r8d, r8d; Reserved
0x18001ac0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ac13  mov     [rsp+4D0h+dwCreationDisposition], r13d; dwOptions
0x18001ac18  call    cs:__imp_RegCreateKeyExW
0x18001ac1e  mov     ebx, eax
0x18001ac20  test    eax, eax
0x18001ac22  jnz     loc_18001AA65
0x18001ac28  lea     r9d, [rax+1]
0x18001ac2c  jmp     loc_18001AD16
0x18001ac31  lea     rdx, aFlags; "Flags"
0x18001ac38  mov     rcx, rdi; String1
0x18001ac3b  call    wcscmp_0
0x18001ac40  test    eax, eax
0x18001ac42  mov     [rsp+4D0h+hTemplateFile], 104h; unsigned __int64
0x18001ac4b  lea     rax, [rsp+4D0h+SubKey]
0x18001ac50  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18001ac55  jnz     short loc_18001ACC0
0x18001ac57  xor     r9d, r9d; int
0x18001ac5a  mov     [rsp+4D0h+dwCreationDisposition], r13d; int
0x18001ac5f  mov     r8, r14; struct _GUID *
0x18001ac62  mov     edx, r12d; int
0x18001ac65  mov     rcx, rbx; struct _GUID *
0x18001ac68  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x18001ac6d  mov     ebx, eax
0x18001ac6f  test    eax, eax
0x18001ac71  jnz     loc_18001AA65
0x18001ac77  mov     [rsp+4D0h+lpdwDisposition], r13; lpdwDisposition
0x18001ac7c  lea     rax, [rsp+4D0h+hKey]
0x18001ac81  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18001ac86  lea     rdx, [rsp+4D0h+SubKey]; lpSubKey
0x18001ac8b  mov     [rsp+4D0h+hTemplateFile], r13; lpSecurityAttributes
0x18001ac90  xor     r9d, r9d; lpClass
0x18001ac93  mov     [rsp+4D0h+dwFlagsAndAttributes], 20006h; samDesired
0x18001ac9b  xor     r8d, r8d; Reserved
0x18001ac9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001aca5  mov     [rsp+4D0h+dwCreationDisposition], r13d; dwOptions
0x18001acaa  call    cs:__imp_RegCreateKeyExW
0x18001acb0  mov     ebx, eax
0x18001acb2  test    eax, eax
0x18001acb4  jnz     loc_18001AA65
0x18001acba  lea     r9d, [rax+4]
0x18001acbe  jmp     short loc_18001AD16
0x18001acc0  mov     [rsp+4D0h+dwCreationDisposition], 1
0x18001acc8  jmp     loc_18001AA4A
0x18001accd  mov     [rsp+4D0h+lpdwDisposition], r13; lpdwDisposition
0x18001acd2  lea     rax, [rsp+4D0h+hKey]
0x18001acd7  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18001acdc  lea     rdx, [rsp+4D0h+SubKey]; lpSubKey
0x18001ace1  mov     [rsp+4D0h+hTemplateFile], r13; lpSecurityAttributes
0x18001ace6  xor     r9d, r9d; lpClass
0x18001ace9  mov     [rsp+4D0h+dwFlagsAndAttributes], 20006h; samDesired
0x18001acf1  xor     r8d, r8d; Reserved
0x18001acf4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001acfb  mov     [rsp+4D0h+dwCreationDisposition], r13d; dwOptions
0x18001ad00  call    cs:__imp_RegCreateKeyExW
0x18001ad06  mov     ebx, eax
0x18001ad08  test    eax, eax
0x18001ad0a  jnz     loc_18001AA65
0x18001ad10  mov     r9d, 3; dwType
0x18001ad16  mov     eax, [rbp+3D0h+cbData]
0x18001ad1c  xor     r8d, r8d; Reserved
0x18001ad1f  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18001ad24  mov     rdx, rdi; lpValueName
0x18001ad27  mov     [rsp+4D0h+dwFlagsAndAttributes], eax; cbData
0x18001ad2b  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r15; lpData
0x18001ad30  call    cs:__imp_RegSetValueExW
0x18001ad36  mov     ebx, eax
0x18001ad38  jmp     loc_18001AA65
0x18001ad3d  mov     rcx, rsi; hObject
0x18001ad40  call    cs:__imp_CloseHandle
0x18001ad46  jmp     loc_18001AA7F
```
