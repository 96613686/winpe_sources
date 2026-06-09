# WdfDebugModeSettings::Reload(void)

- ea: `0x140027b10`
- end: `0x140027d1c`
- name: `?Reload@WdfDebugModeSettings@@QEAAXXZ`
- size: `524`
- prototype: `void __fastcall(WdfDebugModeSettings *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14008c520`

## callees

- `0x140027998`
- `0x140027b10`
- `0x140028088`
- `0x14003056c`
- `0x140044300`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140027b37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140027b37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027ca5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027ca5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140027c2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140027c2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140027b97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140027b97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140027be7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140027be7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140027c48`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140027c48`

## pseudocode

```c
void __fastcall WdfDebugModeSettings::Reload(WdfDebugModeSettings *this)
{
  HKEY v2; // rcx
  HKEY v3; // rdi
  unsigned int v4; // eax
  HKEY v5; // r14
  int v6; // eax
  void *v7; // rcx
  HKEY v8; // rcx
  char v9; // dl
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+7h] BYREF
  HKEY v13; // [rsp+78h] [rbp+Fh] BYREF
  char v14; // [rsp+80h] [rbp+17h]
  DWORD Type; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v16; // [rsp+D8h] [rbp+6Fh] BYREF
  int Data; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v16 = *((_QWORD *)this + 1);
  if ( (unsigned __int64)(*(_QWORD *)&SystemTimeAsFileTime - v16) <= 0x989680 )
    return;
  v2 = *(HKEY *)this;
  if ( *(_QWORD *)this )
  {
    hKey = *(HKEY *)this;
    goto LABEL_11;
  }
  v14 = 1;
  hKey = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WUDF\\DebugMode",
         0,
         0x80000000,
         &hKey);
  v5 = hKey;
  if ( !v4 )
    v3 = hKey;
  v13 = v3;
  LODWORD(v16) = 0;
  v6 = ConvertWinErrorToNtstatus(v4, &v16);
  if ( (int)v16 >= 0 && v6 == 1 )
  {
    v14 = 0;
    *(_QWORD *)this = v5;
    CUmdfSvcConfig::~CUmdfSvcConfig(&v13);
    v2 = hKey;
LABEL_11:
    ftLastWriteTime = 0;
    if ( RegQueryInfoKeyW(v2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime) )
    {
      __debugbreak();
      ftLastWriteTime = SystemTimeAsFileTime;
    }
    if ( CompareFileTime((const FILETIME *)this + 1, &ftLastWriteTime) < 0 )
    {
      v7 = (void *)*((_QWORD *)this + 3);
      *((struct _FILETIME *)this + 1) = ftLastWriteTime;
      *((_BYTE *)this + 16) = Type & 0xF8;
      operator delete(v7);
      v8 = hKey;
      *((_QWORD *)this + 3) = 0;
      Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(v8, L"DebugModeFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      {
        v9 = ((Data & 5) != 5 ? 0 : 4) | ((Data & 3) != 3 ? 0 : 2) | ((Data ^ 4) & 1 ^ 4) & 0xF9;
        *((_BYTE *)this + 16) = v9;
        if ( (v9 & 1) != 0 )
          *((_QWORD *)this + 3) = WdfRegQueryString(hKey, L"DebugModeBinaries", &Type, &cbData);
      }
    }
    return;
  }
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x140027b10  push    rbp
0x140027b12  push    rbx
0x140027b13  push    rsi
0x140027b14  push    rdi
0x140027b15  push    r14
0x140027b17  push    r15
0x140027b19  lea     rbp, [rsp-2Fh]
0x140027b1e  sub     rsp, 98h
0x140027b25  mov     rbx, rcx
0x140027b28  xor     r15d, r15d
0x140027b2b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140027b2f  mov     [rbp+57h+hKey], r15
0x140027b33  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x140027b37  call    cs:__imp_GetSystemTimeAsFileTime
0x140027b3d  lea     rsi, [rbx+8]
0x140027b41  mov     eax, [rsi]
0x140027b43  mov     dword ptr [rbp+57h+arg_8], eax
0x140027b46  mov     eax, [rbx+0Ch]
0x140027b49  mov     dword ptr [rbp+57h+arg_8+4], eax
0x140027b4c  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140027b50  sub     rax, [rbp+57h+arg_8]
0x140027b54  cmp     rax, 989680h
0x140027b5a  jbe     loc_140027D0C
0x140027b60  mov     rcx, [rbx]; hKey
0x140027b63  test    rcx, rcx
0x140027b66  jnz     loc_140027BF2
0x140027b6c  lea     rax, [rbp+57h+hKey]
0x140027b70  mov     [rbp+57h+var_40], 1
0x140027b74  mov     r9d, 80000000h; samDesired
0x140027b7a  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140027b7f  xor     r8d, r8d; ulOptions
0x140027b82  mov     [rbp+57h+hKey], r15
0x140027b86  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140027b8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140027b94  mov     edi, r15d
0x140027b97  call    cs:__imp_RegOpenKeyExW
0x140027b9d  mov     r14, [rbp+57h+hKey]
0x140027ba1  test    eax, eax
0x140027ba3  cmovz   rdi, r14
0x140027ba7  mov     [rbp+57h+var_48], rdi
0x140027bab  lea     rdx, [rbp+57h+arg_8]
0x140027baf  mov     dword ptr [rbp+57h+arg_8], r15d
0x140027bb3  mov     ecx, eax
0x140027bb5  call    ConvertWinErrorToNtstatus
0x140027bba  cmp     dword ptr [rbp+57h+arg_8], r15d
0x140027bbe  jl      short loc_140027BDB
0x140027bc0  cmp     eax, 1
0x140027bc3  jnz     short loc_140027BDB
0x140027bc5  lea     rcx, [rbp+57h+var_48]; this
0x140027bc9  mov     [rbp+57h+var_40], r15b
0x140027bcd  mov     [rbx], r14
0x140027bd0  call    ??1CUmdfSvcConfig@@QEAA@XZ; CUmdfSvcConfig::~CUmdfSvcConfig(void)
0x140027bd5  mov     rcx, [rbp+57h+hKey]
0x140027bd9  jmp     short loc_140027BF6
0x140027bdb  test    rdi, rdi
0x140027bde  jz      loc_140027D0C
0x140027be4  mov     rcx, rdi; hKey
0x140027be7  call    cs:__imp_RegCloseKey
0x140027bed  jmp     loc_140027D0C
0x140027bf2  mov     [rbp+57h+hKey], rcx
0x140027bf6  lea     rax, [rbp+57h+ftLastWriteTime]
0x140027bfa  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r15
0x140027bfe  mov     [rsp+0C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140027c03  xor     r9d, r9d; lpReserved
0x140027c06  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140027c0b  xor     r8d, r8d; lpcchClass
0x140027c0e  mov     [rsp+0C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140027c13  xor     edx, edx; lpClass
0x140027c15  mov     [rsp+0C0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140027c1a  mov     [rsp+0C0h+lpcValues], r15; lpcValues
0x140027c1f  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140027c24  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140027c29  mov     [rsp+0C0h+phkResult], r15; lpcSubKeys
0x140027c2e  call    cs:__imp_RegQueryInfoKeyW
0x140027c34  test    eax, eax
0x140027c36  jz      short loc_140027C41
0x140027c38  int     3; Trap to Debugger
0x140027c39  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140027c3d  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rax
0x140027c41  lea     rdx, [rbp+57h+ftLastWriteTime]; lpFileTime2
0x140027c45  mov     rcx, rsi; lpFileTime1
0x140027c48  call    cs:__imp_CompareFileTime
0x140027c4e  test    eax, eax
0x140027c50  jns     loc_140027D0C
0x140027c56  mov     rax, qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime]
0x140027c5a  mov     rcx, [rbx+18h]; void *
0x140027c5e  mov     [rsi], rax
0x140027c61  mov     al, byte ptr [rbp+57h+Type]
0x140027c64  and     al, 0F8h
0x140027c66  mov     [rbx+10h], al
0x140027c69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140027c6e  mov     rcx, [rbp+57h+hKey]; hKey
0x140027c72  lea     rax, [rbp+57h+cbData]
0x140027c76  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x140027c7b  lea     r9, [rbp+57h+Type]; lpType
0x140027c7f  lea     rax, [rbp+57h+Data]
0x140027c83  mov     [rbx+18h], r15
0x140027c87  xor     r8d, r8d; lpReserved
0x140027c8a  mov     [rsp+0C0h+phkResult], rax; lpData
0x140027c8f  lea     rdx, aDebugmodeflags; "DebugModeFlags"
0x140027c96  mov     [rbp+57h+Data], r15d
0x140027c9a  mov     [rbp+57h+Type], r15d
0x140027c9e  mov     [rbp+57h+cbData], 4
0x140027ca5  call    cs:__imp_RegQueryValueExW
0x140027cab  test    eax, eax
0x140027cad  jnz     short loc_140027D0C
0x140027caf  cmp     [rbp+57h+Type], 4
0x140027cb3  jnz     short loc_140027D0C
0x140027cb5  mov     ecx, [rbp+57h+Data]
0x140027cb8  mov     dl, cl
0x140027cba  xor     dl, byte ptr [rbp+57h+Type]
0x140027cbd  mov     eax, ecx
0x140027cbf  and     eax, 3
0x140027cc2  and     dl, 1
0x140027cc5  xor     dl, byte ptr [rbp+57h+Type]
0x140027cc8  and     dl, 0FDh
0x140027ccb  cmp     al, 3
0x140027ccd  setnz   al
0x140027cd0  and     ecx, 5
0x140027cd3  dec     al
0x140027cd5  and     al, 2
0x140027cd7  or      dl, al
0x140027cd9  and     dl, 0FBh
0x140027cdc  cmp     cl, 5
0x140027cdf  setnz   al
0x140027ce2  dec     al
0x140027ce4  and     al, 4
0x140027ce6  or      dl, al
0x140027ce8  mov     [rbx+10h], dl
0x140027ceb  test    dl, 1
0x140027cee  jz      short loc_140027D0C
0x140027cf0  mov     rcx, [rbp+57h+hKey]; hKey
0x140027cf4  lea     r9, [rbp+57h+cbData]; unsigned int *
0x140027cf8  lea     r8, [rbp+57h+Type]; unsigned int *
0x140027cfc  lea     rdx, aDebugmodebinar; "DebugModeBinaries"
0x140027d03  call    ?WdfRegQueryString@@YAPEAGPEAUHKEY__@@PEBGPEAK2@Z; WdfRegQueryString(HKEY__ *,ushort const *,ulong *,ulong *)
0x140027d08  mov     [rbx+18h], rax
0x140027d0c  add     rsp, 98h
0x140027d13  pop     r15
0x140027d15  pop     r14
0x140027d17  pop     rdi
0x140027d18  pop     rsi
0x140027d19  pop     rbx
0x140027d1a  pop     rbp
0x140027d1b  retn
```
