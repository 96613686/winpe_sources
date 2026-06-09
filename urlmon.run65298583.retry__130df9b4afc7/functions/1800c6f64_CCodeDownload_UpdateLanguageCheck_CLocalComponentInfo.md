# CCodeDownload::UpdateLanguageCheck(CLocalComponentInfo *)

- ea: `0x1800c6f64`
- end: `0x1800c71bf`
- name: `?UpdateLanguageCheck@CCodeDownload@@AEAAJPEAVCLocalComponentInfo@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(CCodeDownload *__hidden this, struct CLocalComponentInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800be538`

## callees

- `0x180030880`
- `0x1800763a8`
- `0x1800be13c`
- `0x1800c6f64`
- `0x18010e6d8`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c7050`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c7094`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c70bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c7050`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c7094`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c70bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c713f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c713f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c719f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c719f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c7102`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c7102`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c6ffc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c6ffc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800c700a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800c700a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c6fe8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c6fe8`

## string_xrefs

- `0x1800c7042`: `CLSID`

## pseudocode

```c
__int64 __fastcall CCodeDownload::UpdateLanguageCheck(CCodeDownload *this, struct CLocalComponentInfo *a2)
{
  __int64 v2; // rdx
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rcx
  CHAR *v7; // rdi
  unsigned int v8; // ecx
  LSTATUS v9; // eax
  int v10; // eax
  LPOLESTR lpsz; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  HKEY v15; // [rsp+68h] [rbp-1h] BYREF
  struct _FILETIME FileTime; // [rsp+70h] [rbp+7h] BYREF
  LPCSTR lpSubKey; // [rsp+78h] [rbp+Fh]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+17h] BYREF

  v2 = *((_QWORD *)this + 16);
  v4 = 0;
  v5 = *(_QWORD *)(v2 + 16);
  v6 = *(_QWORD *)(v5 + 16) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)(v5 + 24) - *(_QWORD *)GUID_NULL.Data4;
  v15 = 0;
  hKey = 0;
  phkResult = 0;
  lpsz = 0;
  v7 = 0;
  FileTime = 0;
  lpSubKey = 0;
  SystemTime = 0;
  if ( v6 )
  {
    v4 = StringFromCLSID((const IID *const)(*(_QWORD *)(v2 + 16) + 16LL), &lpsz);
    if ( v4 >= 0 )
    {
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, &FileTime);
      if ( (unsigned int)InstallBrokerIsNeeded(v8) )
      {
        v9 = CCodeDownload::CallUpdateLanguageCheckBroker(this, lpsz, FileTime);
      }
      else
      {
        if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey) )
          goto LABEL_16;
        v10 = Unicode2Ansi(lpsz);
        v7 = (CHAR *)lpSubKey;
        v4 = v10;
        if ( v10 < 0 || RegOpenKeyExA(hKey, lpSubKey, 0, 0xF003Fu, &phkResult) )
          goto LABEL_16;
        if ( !RegOpenKeyExA(phkResult, "LanguageCheckPeriod", 0, 0xF003Fu, &v15)
          || (v9 = RegCreateKeyExA(phkResult, "LanguageCheckPeriod", 0, 0, 0, 0x2000000u, 0, &v15, 0)) == 0 )
        {
          RegSetValueExA(v15, "LastCheckedHi", 0, 4u, (const BYTE *)&FileTime.dwHighDateTime, 4u);
          goto LABEL_16;
        }
        if ( v9 > 0 )
        {
          v4 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_16;
        }
      }
      v4 = v9;
    }
LABEL_16:
    if ( lpsz )
    {
      operator delete(lpsz);
      lpsz = 0;
    }
    if ( v7 )
      operator delete(v7);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( v15 )
      RegCloseKey(v15);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c6f64  push    rbp
0x1800c6f66  push    rbx
0x1800c6f67  push    rsi
0x1800c6f68  push    rdi
0x1800c6f69  lea     rbp, [rsp-3Fh]
0x1800c6f6e  sub     rsp, 0A8h
0x1800c6f75  mov     rax, cs:__security_cookie
0x1800c6f7c  xor     rax, rsp
0x1800c6f7f  mov     [rbp+57h+var_30], rax
0x1800c6f83  mov     rdx, [rcx+80h]
0x1800c6f8a  mov     rsi, rcx
0x1800c6f8d  xor     ebx, ebx
0x1800c6f8f  mov     rax, [rdx+10h]
0x1800c6f93  mov     rcx, [rax+10h]
0x1800c6f97  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x1800c6f9e  jnz     short loc_1800C6FAB
0x1800c6fa0  mov     rcx, [rax+18h]
0x1800c6fa4  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x1800c6fab  xor     eax, eax
0x1800c6fad  mov     [rbp+57h+var_58], rbx
0x1800c6fb1  test    rcx, rcx
0x1800c6fb4  mov     [rbp+57h+hKey], rbx
0x1800c6fb8  xorps   xmm0, xmm0
0x1800c6fbb  mov     [rbp+57h+var_68], rbx
0x1800c6fbf  setz    al
0x1800c6fc2  mov     [rbp+57h+lpsz], rbx
0x1800c6fc6  xor     edi, edi
0x1800c6fc8  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x1800c6fcc  mov     [rbp+57h+lpSubKey], rdi
0x1800c6fd0  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800c6fd4  test    eax, eax
0x1800c6fd6  jnz     loc_1800C71A5
0x1800c6fdc  mov     rcx, [rdx+10h]
0x1800c6fe0  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800c6fe4  add     rcx, 10h; rclsid
0x1800c6fe8  call    cs:__imp_StringFromCLSID
0x1800c6fee  mov     ebx, eax
0x1800c6ff0  test    eax, eax
0x1800c6ff2  js      loc_1800C7145
0x1800c6ff8  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800c6ffc  call    cs:__imp_GetSystemTime
0x1800c7002  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800c7006  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800c700a  call    cs:__imp_SystemTimeToFileTime
0x1800c7010  call    ?InstallBrokerIsNeeded@@YAHK@Z; InstallBrokerIsNeeded(ulong)
0x1800c7015  test    eax, eax
0x1800c7017  jz      short loc_1800C7030
0x1800c7019  mov     r8, qword ptr [rbp+57h+FileTime.dwLowDateTime]; struct _FILETIME
0x1800c701d  mov     rcx, rsi; this
0x1800c7020  mov     rdx, [rbp+57h+lpsz]; unsigned __int16 *
0x1800c7024  call    ?CallUpdateLanguageCheckBroker@CCodeDownload@@QEAAJPEBGU_FILETIME@@@Z; CCodeDownload::CallUpdateLanguageCheckBroker(ushort const *,_FILETIME)
0x1800c7029  mov     ebx, eax
0x1800c702b  jmp     loc_1800C7145
0x1800c7030  lea     rax, [rbp+57h+hKey]
0x1800c7034  mov     r9d, 20019h; samDesired
0x1800c703a  xor     r8d, r8d; ulOptions
0x1800c703d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800c7042  lea     rdx, aClsid_3; "CLSID"
0x1800c7049  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800c7050  call    cs:__imp_RegOpenKeyExA
0x1800c7056  test    eax, eax
0x1800c7058  jnz     loc_1800C7145
0x1800c705e  mov     rcx, [rbp+57h+lpsz]; lpWideCharStr
0x1800c7062  lea     rdx, [rbp+57h+lpSubKey]
0x1800c7066  call    Unicode2Ansi
0x1800c706b  mov     rdi, [rbp+57h+lpSubKey]
0x1800c706f  mov     ebx, eax
0x1800c7071  test    eax, eax
0x1800c7073  js      loc_1800C7145
0x1800c7079  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c707d  lea     rax, [rbp+57h+var_68]
0x1800c7081  mov     esi, 0F003Fh
0x1800c7086  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800c708b  mov     r9d, esi; samDesired
0x1800c708e  xor     r8d, r8d; ulOptions
0x1800c7091  mov     rdx, rdi; lpSubKey
0x1800c7094  call    cs:__imp_RegOpenKeyExA
0x1800c709a  test    eax, eax
0x1800c709c  jnz     loc_1800C7145
0x1800c70a2  mov     rcx, [rbp+57h+var_68]; hKey
0x1800c70a6  lea     rax, [rbp+57h+var_58]
0x1800c70aa  mov     r9d, esi; samDesired
0x1800c70ad  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800c70b2  xor     r8d, r8d; ulOptions
0x1800c70b5  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x1800c70bc  call    cs:__imp_RegOpenKeyExA
0x1800c70c2  test    eax, eax
0x1800c70c4  jz      short loc_1800C711D
0x1800c70c6  mov     rcx, [rbp+57h+var_68]; hKey
0x1800c70ca  lea     rax, [rbp+57h+var_58]
0x1800c70ce  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x1800c70d7  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x1800c70de  mov     [rsp+0C0h+var_88], rax; phkResult
0x1800c70e3  xor     r9d, r9d; lpClass
0x1800c70e6  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c70ef  xor     r8d, r8d; Reserved
0x1800c70f2  mov     [rsp+0C0h+samDesired], 2000000h; samDesired
0x1800c70fa  mov     dword ptr [rsp+0C0h+phkResult], 0; dwOptions
0x1800c7102  call    cs:__imp_RegCreateKeyExA
0x1800c7108  test    eax, eax
0x1800c710a  jz      short loc_1800C711D
0x1800c710c  jle     loc_1800C7029
0x1800c7112  movzx   ebx, ax
0x1800c7115  or      ebx, 80070000h
0x1800c711b  jmp     short loc_1800C7145
0x1800c711d  mov     rcx, [rbp+57h+var_58]; hKey
0x1800c7121  lea     rax, [rbp+57h+FileTime.dwHighDateTime]
0x1800c7125  mov     r9d, 4; dwType
0x1800c712b  lea     rdx, aLastcheckedhi; "LastCheckedHi"
0x1800c7132  mov     [rsp+0C0h+samDesired], r9d; cbData
0x1800c7137  xor     r8d, r8d; Reserved
0x1800c713a  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800c713f  call    cs:__imp_RegSetValueExA
0x1800c7145  mov     rcx, [rbp+57h+lpsz]; void *
0x1800c7149  test    rcx, rcx
0x1800c714c  jz      short loc_1800C715B
0x1800c714e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c7153  mov     [rbp+57h+lpsz], 0
0x1800c715b  test    rdi, rdi
0x1800c715e  jz      short loc_1800C7168
0x1800c7160  mov     rcx, rdi; void *
0x1800c7163  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c7168  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c716c  test    rcx, rcx
0x1800c716f  jz      short loc_1800C717F
0x1800c7171  call    cs:__imp_RegCloseKey
0x1800c7177  mov     [rbp+57h+hKey], 0
0x1800c717f  mov     rcx, [rbp+57h+var_68]; hKey
0x1800c7183  test    rcx, rcx
0x1800c7186  jz      short loc_1800C7196
0x1800c7188  call    cs:__imp_RegCloseKey
0x1800c718e  mov     [rbp+57h+var_68], 0
0x1800c7196  mov     rcx, [rbp+57h+var_58]; hKey
0x1800c719a  test    rcx, rcx
0x1800c719d  jz      short loc_1800C71A5
0x1800c719f  call    cs:__imp_RegCloseKey
0x1800c71a5  mov     eax, ebx
0x1800c71a7  mov     rcx, [rbp+57h+var_30]
0x1800c71ab  xor     rcx, rsp; StackCookie
0x1800c71ae  call    __security_check_cookie
0x1800c71b3  add     rsp, 0A8h
0x1800c71ba  pop     rdi
0x1800c71bb  pop     rsi
0x1800c71bc  pop     rbx
0x1800c71bd  pop     rbp
0x1800c71be  retn
```
