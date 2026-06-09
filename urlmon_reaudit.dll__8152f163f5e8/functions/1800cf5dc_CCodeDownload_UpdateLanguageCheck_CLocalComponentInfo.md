# CCodeDownload::UpdateLanguageCheck(CLocalComponentInfo *)

- ea: `0x1800cf5dc`
- end: `0x1800cf87a`
- name: `?UpdateLanguageCheck@CCodeDownload@@AEAAJPEAVCLocalComponentInfo@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(CCodeDownload *__hidden this, struct CLocalComponentInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c673c`

## callees

- `0x18002fee0`
- `0x18007bcc8`
- `0x1800c6334`
- `0x1800cf5dc`
- `0x18011a3d8`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf6da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf724`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf752`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf6da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf724`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf7e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf7e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf836`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf836`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf853`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf79e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf79e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800cf67a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800cf67a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800cf68e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800cf68e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800cf660`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800cf660`

## string_xrefs

- `0x1800cf6cc`: `CLSID`

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
0x1800cf5dc  push    rbp
0x1800cf5de  push    rbx
0x1800cf5df  push    rsi
0x1800cf5e0  push    rdi
0x1800cf5e1  lea     rbp, [rsp-3Fh]
0x1800cf5e6  sub     rsp, 0A8h
0x1800cf5ed  mov     rax, cs:__security_cookie
0x1800cf5f4  xor     rax, rsp
0x1800cf5f7  mov     [rbp+57h+var_30], rax
0x1800cf5fb  mov     rdx, [rcx+80h]
0x1800cf602  mov     rsi, rcx
0x1800cf605  xor     ebx, ebx
0x1800cf607  mov     rax, [rdx+10h]
0x1800cf60b  mov     rcx, [rax+10h]
0x1800cf60f  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x1800cf616  jnz     short loc_1800CF623
0x1800cf618  mov     rcx, [rax+18h]
0x1800cf61c  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x1800cf623  xor     eax, eax
0x1800cf625  mov     [rbp+57h+var_58], rbx
0x1800cf629  test    rcx, rcx
0x1800cf62c  mov     [rbp+57h+hKey], rbx
0x1800cf630  xorps   xmm0, xmm0
0x1800cf633  mov     [rbp+57h+var_68], rbx
0x1800cf637  setz    al
0x1800cf63a  mov     [rbp+57h+lpsz], rbx
0x1800cf63e  xor     edi, edi
0x1800cf640  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x1800cf644  mov     [rbp+57h+lpSubKey], rdi
0x1800cf648  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800cf64c  test    eax, eax
0x1800cf64e  jnz     loc_1800CF85F
0x1800cf654  mov     rcx, [rdx+10h]
0x1800cf658  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800cf65c  add     rcx, 10h; rclsid
0x1800cf660  call    cs:__imp_StringFromCLSID
0x1800cf667  nop     dword ptr [rax+rax+00h]
0x1800cf66c  mov     ebx, eax
0x1800cf66e  test    eax, eax
0x1800cf670  js      loc_1800CF7ED
0x1800cf676  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800cf67a  call    cs:__imp_GetSystemTime
0x1800cf681  nop     dword ptr [rax+rax+00h]
0x1800cf686  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800cf68a  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800cf68e  call    cs:__imp_SystemTimeToFileTime
0x1800cf695  nop     dword ptr [rax+rax+00h]
0x1800cf69a  call    ?InstallBrokerIsNeeded@@YAHK@Z; InstallBrokerIsNeeded(ulong)
0x1800cf69f  test    eax, eax
0x1800cf6a1  jz      short loc_1800CF6BA
0x1800cf6a3  mov     r8, qword ptr [rbp+57h+FileTime.dwLowDateTime]; struct _FILETIME
0x1800cf6a7  mov     rcx, rsi; this
0x1800cf6aa  mov     rdx, [rbp+57h+lpsz]; unsigned __int16 *
0x1800cf6ae  call    ?CallUpdateLanguageCheckBroker@CCodeDownload@@QEAAJPEBGU_FILETIME@@@Z; CCodeDownload::CallUpdateLanguageCheckBroker(ushort const *,_FILETIME)
0x1800cf6b3  mov     ebx, eax
0x1800cf6b5  jmp     loc_1800CF7ED
0x1800cf6ba  lea     rax, [rbp+57h+hKey]
0x1800cf6be  mov     r9d, 20019h; samDesired
0x1800cf6c4  xor     r8d, r8d; ulOptions
0x1800cf6c7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800cf6cc  lea     rdx, aClsid_3; "CLSID"
0x1800cf6d3  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800cf6da  call    cs:__imp_RegOpenKeyExA
0x1800cf6e1  nop     dword ptr [rax+rax+00h]
0x1800cf6e6  test    eax, eax
0x1800cf6e8  jnz     loc_1800CF7ED
0x1800cf6ee  mov     rcx, [rbp+57h+lpsz]; lpWideCharStr
0x1800cf6f2  lea     rdx, [rbp+57h+lpSubKey]
0x1800cf6f6  call    Unicode2Ansi
0x1800cf6fb  mov     rdi, [rbp+57h+lpSubKey]
0x1800cf6ff  mov     ebx, eax
0x1800cf701  test    eax, eax
0x1800cf703  js      loc_1800CF7ED
0x1800cf709  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cf70d  lea     rax, [rbp+57h+var_68]
0x1800cf711  mov     esi, 0F003Fh
0x1800cf716  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800cf71b  mov     r9d, esi; samDesired
0x1800cf71e  xor     r8d, r8d; ulOptions
0x1800cf721  mov     rdx, rdi; lpSubKey
0x1800cf724  call    cs:__imp_RegOpenKeyExA
0x1800cf72b  nop     dword ptr [rax+rax+00h]
0x1800cf730  test    eax, eax
0x1800cf732  jnz     loc_1800CF7ED
0x1800cf738  mov     rcx, [rbp+57h+var_68]; hKey
0x1800cf73c  lea     rax, [rbp+57h+var_58]
0x1800cf740  mov     r9d, esi; samDesired
0x1800cf743  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800cf748  xor     r8d, r8d; ulOptions
0x1800cf74b  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x1800cf752  call    cs:__imp_RegOpenKeyExA
0x1800cf759  nop     dword ptr [rax+rax+00h]
0x1800cf75e  test    eax, eax
0x1800cf760  jz      short loc_1800CF7BF
0x1800cf762  mov     rcx, [rbp+57h+var_68]; hKey
0x1800cf766  lea     rax, [rbp+57h+var_58]
0x1800cf76a  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x1800cf773  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x1800cf77a  mov     [rsp+0C0h+var_88], rax; phkResult
0x1800cf77f  xor     r9d, r9d; lpClass
0x1800cf782  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cf78b  xor     r8d, r8d; Reserved
0x1800cf78e  mov     [rsp+0C0h+samDesired], 2000000h; samDesired
0x1800cf796  mov     dword ptr [rsp+0C0h+phkResult], 0; dwOptions
0x1800cf79e  call    cs:__imp_RegCreateKeyExA
0x1800cf7a5  nop     dword ptr [rax+rax+00h]
0x1800cf7aa  test    eax, eax
0x1800cf7ac  jz      short loc_1800CF7BF
0x1800cf7ae  jle     loc_1800CF6B3
0x1800cf7b4  movzx   ebx, ax
0x1800cf7b7  or      ebx, 80070000h
0x1800cf7bd  jmp     short loc_1800CF7ED
0x1800cf7bf  mov     rcx, [rbp+57h+var_58]; hKey
0x1800cf7c3  lea     rax, [rbp+57h+FileTime.dwHighDateTime]
0x1800cf7c7  mov     r9d, 4; dwType
0x1800cf7cd  lea     rdx, aLastcheckedhi; "LastCheckedHi"
0x1800cf7d4  mov     [rsp+0C0h+samDesired], r9d; cbData
0x1800cf7d9  xor     r8d, r8d; Reserved
0x1800cf7dc  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800cf7e1  call    cs:__imp_RegSetValueExA
0x1800cf7e8  nop     dword ptr [rax+rax+00h]
0x1800cf7ed  mov     rcx, [rbp+57h+lpsz]; void *
0x1800cf7f1  test    rcx, rcx
0x1800cf7f4  jz      short loc_1800CF803
0x1800cf7f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf7fb  mov     [rbp+57h+lpsz], 0
0x1800cf803  test    rdi, rdi
0x1800cf806  jz      short loc_1800CF810
0x1800cf808  mov     rcx, rdi; void *
0x1800cf80b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf810  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cf814  test    rcx, rcx
0x1800cf817  jz      short loc_1800CF82D
0x1800cf819  call    cs:__imp_RegCloseKey
0x1800cf820  nop     dword ptr [rax+rax+00h]
0x1800cf825  mov     [rbp+57h+hKey], 0
0x1800cf82d  mov     rcx, [rbp+57h+var_68]; hKey
0x1800cf831  test    rcx, rcx
0x1800cf834  jz      short loc_1800CF84A
0x1800cf836  call    cs:__imp_RegCloseKey
0x1800cf83d  nop     dword ptr [rax+rax+00h]
0x1800cf842  mov     [rbp+57h+var_68], 0
0x1800cf84a  mov     rcx, [rbp+57h+var_58]; hKey
0x1800cf84e  test    rcx, rcx
0x1800cf851  jz      short loc_1800CF85F
0x1800cf853  call    cs:__imp_RegCloseKey
0x1800cf85a  nop     dword ptr [rax+rax+00h]
0x1800cf85f  mov     eax, ebx
0x1800cf861  mov     rcx, [rbp+57h+var_30]
0x1800cf865  xor     rcx, rsp; StackCookie
0x1800cf868  call    __security_check_cookie
0x1800cf86d  add     rsp, 0A8h
0x1800cf874  pop     rdi
0x1800cf875  pop     rsi
0x1800cf876  pop     rbx
0x1800cf877  pop     rbp
0x1800cf878  retn
```
