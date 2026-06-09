# CConfigureMemoryIntegrity::IsMemoryIntegrityOverrideApplied(int *)

- ea: `0x18002f5c4`
- end: `0x18002f808`
- name: `?IsMemoryIntegrityOverrideApplied@CConfigureMemoryIntegrity@@AEAAJPEAH@Z`
- size: `580`
- prototype: `__int64 __fastcall(CConfigureMemoryIntegrity *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f150`

## callees

- `0x1800013a4`
- `0x18002f5c4`
- `0x18004325c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f764`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f764`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f7f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f7f8`

## string_xrefs

- `0x18002f6f6`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`

## pseudocode

```c
__int64 __fastcall CConfigureMemoryIntegrity::IsMemoryIntegrityOverrideApplied(
        CConfigureMemoryIntegrity *this,
        int *a2)
{
  signed int v3; // ebx
  __int16 *v4; // rdx
  const char **v5; // rax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  const char **v9; // [rsp+38h] [rbp-28h]
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  const char *v11; // [rsp+48h] [rbp-18h] BYREF
  const char *v12; // [rsp+50h] [rbp-10h] BYREF
  const char *v13; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+20h] BYREF
  int v15; // [rsp+84h] [rbp+24h]
  int Data; // [rsp+88h] [rbp+28h] BYREF
  signed int v17; // [rsp+90h] [rbp+30h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF

  v15 = HIDWORD(this);
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  if ( a2 )
  {
    v3 = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
    if ( (v6 & 0xFFFFFFFD) != 0 )
    {
      v3 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
      if ( v3 < 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v3, 0);
        if ( (unsigned int)dword_180084170 <= 3 )
          goto LABEL_21;
        v13 = "IsMemoryIntegrityOverrideApplied";
        v4 = (__int16 *)byte_180079D83;
        v12 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
        v11 = "Warning HResult failed";
        v9 = &v13;
        v5 = &v11;
        goto LABEL_4;
      }
    }
    if ( !hKey
      || (cbData = 4,
          v7 = RegQueryValueExW(hKey, L"MemoryIntegrityMultisession", 0, &Type, (LPBYTE)&Data, &cbData),
          (v7 & 0xFFFFFFFD) == 0)
      || (v7 > 0 ? (v3 = (unsigned __int16)v7 | 0x80070000) : (v3 = v7), v3 >= 0) )
    {
      *a2 = Data == 1;
      goto LABEL_21;
    }
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v3, 0);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v13 = "IsMemoryIntegrityOverrideApplied";
      v4 = word_180079D3A;
      v12 = "RegQueryValueEx REG_VALUE_MEMORY_INTEGRITY_MULTISESSION in REG_CONTROL_TSERVER failed";
      v11 = "Warning HResult failed";
      v9 = &v13;
      v5 = &v11;
      goto LABEL_4;
    }
  }
  else
  {
    v3 = -2147467261;
    MicrosoftTelemetryAssertTriggeredArgs(0, 2147500035LL, 0);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v11 = "IsMemoryIntegrityOverrideApplied";
      v4 = (__int16 *)&dword_180079DCC;
      v12 = "pfRebootRequired is NULL";
      v13 = "Warning HResult failed";
      v9 = &v11;
      v5 = &v13;
LABEL_4:
      v17 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_180084170,
        (_DWORD)v4,
        0,
        0,
        (__int64)v5,
        (__int64)&v12,
        (__int64)&v17,
        (__int64)v9);
    }
  }
LABEL_21:
  RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f5c4  mov     qword ptr [rsp-18h+cbData], rcx
0x18002f5c9  push    rbp
0x18002f5ca  push    rbx
0x18002f5cb  push    rdi
0x18002f5cc  mov     rbp, rsp
0x18002f5cf  sub     rsp, 60h
0x18002f5d3  mov     [rbp+hKey], 0
0x18002f5db  mov     rdi, rdx
0x18002f5de  mov     [rbp+Data], 0
0x18002f5e5  mov     [rbp+Type], 0
0x18002f5ec  mov     [rbp+cbData], 0
0x18002f5f3  test    rdx, rdx
0x18002f5f6  jnz     loc_18002F685
0x18002f5fc  mov     ebx, 80004003h
0x18002f601  xor     r8d, r8d
0x18002f604  mov     edx, 80004003h
0x18002f609  xor     ecx, ecx
0x18002f60b  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f610  mov     eax, cs:dword_180084170
0x18002f616  cmp     eax, 3
0x18002f619  jbe     loc_18002F7F4
0x18002f61f  lea     rax, aIsmemoryintegr; "IsMemoryIntegrityOverrideApplied"
0x18002f626  mov     [rbp+var_18], rax
0x18002f62a  lea     rdx, dword_180079DCC
0x18002f631  lea     rax, aPfrebootrequir_0; "pfRebootRequired is NULL"
0x18002f638  mov     [rbp+var_10], rax
0x18002f63c  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f643  mov     [rbp+var_8], rax
0x18002f647  lea     rax, [rbp+var_18]
0x18002f64b  mov     [rsp+60h+var_28], rax
0x18002f650  lea     rax, [rbp+arg_10]
0x18002f654  mov     [rsp+60h+var_30], rax
0x18002f659  lea     rax, [rbp+var_10]
0x18002f65d  mov     [rsp+60h+lpcbData], rax
0x18002f662  lea     rax, [rbp+var_8]
0x18002f666  xor     r9d, r9d
0x18002f669  mov     [rbp+arg_10], ebx
0x18002f66c  xor     r8d, r8d
0x18002f66f  mov     [rsp+60h+phkResult], rax
0x18002f674  lea     rcx, dword_180084170
0x18002f67b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002f680  jmp     loc_18002F7F4
0x18002f685  lea     rax, [rbp+hKey]
0x18002f689  mov     r9d, 20019h; samDesired
0x18002f68f  xor     r8d, r8d; ulOptions
0x18002f692  mov     [rsp+60h+phkResult], rax; phkResult
0x18002f697  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002f69e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f6a5  xor     ebx, ebx
0x18002f6a7  call    cs:__imp_RegOpenKeyExW
0x18002f6ad  test    eax, 0FFFFFFFDh
0x18002f6b2  jz      short loc_18002F730
0x18002f6b4  test    eax, eax
0x18002f6b6  jg      short loc_18002F6BC
0x18002f6b8  mov     ebx, eax
0x18002f6ba  jmp     short loc_18002F6C5
0x18002f6bc  movzx   ebx, ax
0x18002f6bf  or      ebx, 80070000h
0x18002f6c5  test    ebx, ebx
0x18002f6c7  jns     short loc_18002F730
0x18002f6c9  xor     r8d, r8d
0x18002f6cc  mov     edx, ebx
0x18002f6ce  xor     ecx, ecx
0x18002f6d0  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f6d5  mov     eax, cs:dword_180084170
0x18002f6db  cmp     eax, 3
0x18002f6de  jbe     loc_18002F7F4
0x18002f6e4  lea     rax, aIsmemoryintegr; "IsMemoryIntegrityOverrideApplied"
0x18002f6eb  mov     [rbp+var_8], rax
0x18002f6ef  lea     rdx, byte_180079D83
0x18002f6f6  lea     rax, aRegopenkeyexRe_1; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x18002f6fd  mov     [rbp+var_10], rax
0x18002f701  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f708  mov     [rbp+var_18], rax
0x18002f70c  lea     rax, [rbp+var_8]
0x18002f710  mov     [rsp+60h+var_28], rax
0x18002f715  lea     rax, [rbp+arg_10]
0x18002f719  mov     [rsp+60h+var_30], rax
0x18002f71e  lea     rax, [rbp+var_10]
0x18002f722  mov     [rsp+60h+lpcbData], rax
0x18002f727  lea     rax, [rbp+var_18]
0x18002f72b  jmp     loc_18002F666
0x18002f730  mov     rcx, [rbp+hKey]; hKey
0x18002f734  test    rcx, rcx
0x18002f737  jz      loc_18002F7E9
0x18002f73d  lea     rax, [rbp+cbData]
0x18002f741  mov     [rbp+cbData], 4
0x18002f748  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002f74d  lea     r9, [rbp+Type]; lpType
0x18002f751  lea     rax, [rbp+Data]
0x18002f755  xor     r8d, r8d; lpReserved
0x18002f758  lea     rdx, aMemoryintegrit; "MemoryIntegrityMultisession"
0x18002f75f  mov     [rsp+60h+phkResult], rax; lpData
0x18002f764  call    cs:__imp_RegQueryValueExW
0x18002f76a  test    eax, 0FFFFFFFDh
0x18002f76f  jz      short loc_18002F7E9
0x18002f771  test    eax, eax
0x18002f773  jg      short loc_18002F779
0x18002f775  mov     ebx, eax
0x18002f777  jmp     short loc_18002F782
0x18002f779  movzx   ebx, ax
0x18002f77c  or      ebx, 80070000h
0x18002f782  test    ebx, ebx
0x18002f784  jns     short loc_18002F7E9
0x18002f786  xor     r8d, r8d
0x18002f789  mov     edx, ebx
0x18002f78b  xor     ecx, ecx
0x18002f78d  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f792  mov     eax, cs:dword_180084170
0x18002f798  cmp     eax, 3
0x18002f79b  jbe     short loc_18002F7F4
0x18002f79d  lea     rax, aIsmemoryintegr; "IsMemoryIntegrityOverrideApplied"
0x18002f7a4  mov     [rbp+var_8], rax
0x18002f7a8  lea     rdx, word_180079D3A
0x18002f7af  lea     rax, aRegqueryvaluee_4; "RegQueryValueEx REG_VALUE_MEMORY_INTEGR"...
0x18002f7b6  mov     [rbp+var_10], rax
0x18002f7ba  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f7c1  mov     [rbp+var_18], rax
0x18002f7c5  lea     rax, [rbp+var_8]
0x18002f7c9  mov     [rsp+60h+var_28], rax
0x18002f7ce  lea     rax, [rbp+arg_10]
0x18002f7d2  mov     [rsp+60h+var_30], rax
0x18002f7d7  lea     rax, [rbp+var_10]
0x18002f7db  mov     [rsp+60h+lpcbData], rax
0x18002f7e0  lea     rax, [rbp+var_18]
0x18002f7e4  jmp     loc_18002F666
0x18002f7e9  xor     ecx, ecx
0x18002f7eb  cmp     [rbp+Data], 1
0x18002f7ef  setz    cl
0x18002f7f2  mov     [rdi], ecx
0x18002f7f4  mov     rcx, [rbp+hKey]; hKey
0x18002f7f8  call    cs:__imp_RegCloseKey
0x18002f7fe  mov     eax, ebx
0x18002f800  add     rsp, 60h
0x18002f804  pop     rdi
0x18002f805  pop     rbx
0x18002f806  pop     rbp
0x18002f807  retn
```
