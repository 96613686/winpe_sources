# CApplySecurityTemplate::IsRdshTemplateApplied(int *)

- ea: `0x18002e8b4`
- end: `0x18002eaf8`
- name: `?IsRdshTemplateApplied@CApplySecurityTemplate@@AEAAJPEAH@Z`
- size: `580`
- prototype: `__int64 __fastcall(CApplySecurityTemplate *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e410`

## callees

- `0x1800013a4`
- `0x18002e8b4`
- `0x18004325c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e997`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e997`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eae8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eae8`

## string_xrefs

- `0x18002e90f`: `IsRdshTemplateApplied`
- `0x18002e9d4`: `IsRdshTemplateApplied`
- `0x18002ea8d`: `IsRdshTemplateApplied`
- `0x18002e9e6`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`
- `0x18002ea48`: `SecurityTemplate`
- `0x18002ea9f`: `RegQueryValueEx REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER failed`

## pseudocode

```c
__int64 __fastcall CApplySecurityTemplate::IsRdshTemplateApplied(CApplySecurityTemplate *this, int *a2)
{
  signed int v3; // ebx
  char *v4; // rdx
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
        v13 = "IsRdshTemplateApplied";
        v4 = byte_180079873;
        v12 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
        v11 = "Warning HResult failed";
        v9 = &v13;
        v5 = &v11;
        goto LABEL_4;
      }
    }
    if ( !hKey
      || (cbData = 4,
          v7 = RegQueryValueExW(hKey, L"SecurityTemplate", 0, &Type, (LPBYTE)&Data, &cbData),
          (v7 & 0xFFFFFFFD) == 0)
      || (v7 > 0 ? (v3 = (unsigned __int16)v7 | 0x80070000) : (v3 = v7), v3 >= 0) )
    {
      *a2 = Data == 1;
      goto LABEL_21;
    }
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v3, 0);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v13 = "IsRdshTemplateApplied";
      v4 = byte_180079833;
      v12 = "RegQueryValueEx REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER failed";
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
      v11 = "IsRdshTemplateApplied";
      v4 = byte_1800798B3;
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
0x18002e8b4  mov     qword ptr [rsp-18h+cbData], rcx
0x18002e8b9  push    rbp
0x18002e8ba  push    rbx
0x18002e8bb  push    rdi
0x18002e8bc  mov     rbp, rsp
0x18002e8bf  sub     rsp, 60h
0x18002e8c3  mov     [rbp+hKey], 0
0x18002e8cb  mov     rdi, rdx
0x18002e8ce  mov     [rbp+Data], 0
0x18002e8d5  mov     [rbp+Type], 0
0x18002e8dc  mov     [rbp+cbData], 0
0x18002e8e3  test    rdx, rdx
0x18002e8e6  jnz     loc_18002E975
0x18002e8ec  mov     ebx, 80004003h
0x18002e8f1  xor     r8d, r8d
0x18002e8f4  mov     edx, 80004003h
0x18002e8f9  xor     ecx, ecx
0x18002e8fb  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e900  mov     eax, cs:dword_180084170
0x18002e906  cmp     eax, 3
0x18002e909  jbe     loc_18002EAE4
0x18002e90f  lea     rax, aIsrdshtemplate; "IsRdshTemplateApplied"
0x18002e916  mov     [rbp+var_18], rax
0x18002e91a  lea     rdx, byte_1800798B3
0x18002e921  lea     rax, aPfrebootrequir_0; "pfRebootRequired is NULL"
0x18002e928  mov     [rbp+var_10], rax
0x18002e92c  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e933  mov     [rbp+var_8], rax
0x18002e937  lea     rax, [rbp+var_18]
0x18002e93b  mov     [rsp+60h+var_28], rax
0x18002e940  lea     rax, [rbp+arg_10]
0x18002e944  mov     [rsp+60h+var_30], rax
0x18002e949  lea     rax, [rbp+var_10]
0x18002e94d  mov     [rsp+60h+lpcbData], rax
0x18002e952  lea     rax, [rbp+var_8]
0x18002e956  xor     r9d, r9d
0x18002e959  mov     [rbp+arg_10], ebx
0x18002e95c  xor     r8d, r8d
0x18002e95f  mov     [rsp+60h+phkResult], rax
0x18002e964  lea     rcx, dword_180084170
0x18002e96b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002e970  jmp     loc_18002EAE4
0x18002e975  lea     rax, [rbp+hKey]
0x18002e979  mov     r9d, 20019h; samDesired
0x18002e97f  xor     r8d, r8d; ulOptions
0x18002e982  mov     [rsp+60h+phkResult], rax; phkResult
0x18002e987  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002e98e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e995  xor     ebx, ebx
0x18002e997  call    cs:__imp_RegOpenKeyExW
0x18002e99d  test    eax, 0FFFFFFFDh
0x18002e9a2  jz      short loc_18002EA20
0x18002e9a4  test    eax, eax
0x18002e9a6  jg      short loc_18002E9AC
0x18002e9a8  mov     ebx, eax
0x18002e9aa  jmp     short loc_18002E9B5
0x18002e9ac  movzx   ebx, ax
0x18002e9af  or      ebx, 80070000h
0x18002e9b5  test    ebx, ebx
0x18002e9b7  jns     short loc_18002EA20
0x18002e9b9  xor     r8d, r8d
0x18002e9bc  mov     edx, ebx
0x18002e9be  xor     ecx, ecx
0x18002e9c0  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e9c5  mov     eax, cs:dword_180084170
0x18002e9cb  cmp     eax, 3
0x18002e9ce  jbe     loc_18002EAE4
0x18002e9d4  lea     rax, aIsrdshtemplate; "IsRdshTemplateApplied"
0x18002e9db  mov     [rbp+var_8], rax
0x18002e9df  lea     rdx, byte_180079873
0x18002e9e6  lea     rax, aRegopenkeyexRe_1; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x18002e9ed  mov     [rbp+var_10], rax
0x18002e9f1  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e9f8  mov     [rbp+var_18], rax
0x18002e9fc  lea     rax, [rbp+var_8]
0x18002ea00  mov     [rsp+60h+var_28], rax
0x18002ea05  lea     rax, [rbp+arg_10]
0x18002ea09  mov     [rsp+60h+var_30], rax
0x18002ea0e  lea     rax, [rbp+var_10]
0x18002ea12  mov     [rsp+60h+lpcbData], rax
0x18002ea17  lea     rax, [rbp+var_18]
0x18002ea1b  jmp     loc_18002E956
0x18002ea20  mov     rcx, [rbp+hKey]; hKey
0x18002ea24  test    rcx, rcx
0x18002ea27  jz      loc_18002EAD9
0x18002ea2d  lea     rax, [rbp+cbData]
0x18002ea31  mov     [rbp+cbData], 4
0x18002ea38  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002ea3d  lea     r9, [rbp+Type]; lpType
0x18002ea41  lea     rax, [rbp+Data]
0x18002ea45  xor     r8d, r8d; lpReserved
0x18002ea48  lea     rdx, aSecuritytempla; "SecurityTemplate"
0x18002ea4f  mov     [rsp+60h+phkResult], rax; lpData
0x18002ea54  call    cs:__imp_RegQueryValueExW
0x18002ea5a  test    eax, 0FFFFFFFDh
0x18002ea5f  jz      short loc_18002EAD9
0x18002ea61  test    eax, eax
0x18002ea63  jg      short loc_18002EA69
0x18002ea65  mov     ebx, eax
0x18002ea67  jmp     short loc_18002EA72
0x18002ea69  movzx   ebx, ax
0x18002ea6c  or      ebx, 80070000h
0x18002ea72  test    ebx, ebx
0x18002ea74  jns     short loc_18002EAD9
0x18002ea76  xor     r8d, r8d
0x18002ea79  mov     edx, ebx
0x18002ea7b  xor     ecx, ecx
0x18002ea7d  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002ea82  mov     eax, cs:dword_180084170
0x18002ea88  cmp     eax, 3
0x18002ea8b  jbe     short loc_18002EAE4
0x18002ea8d  lea     rax, aIsrdshtemplate; "IsRdshTemplateApplied"
0x18002ea94  mov     [rbp+var_8], rax
0x18002ea98  lea     rdx, byte_180079833
0x18002ea9f  lea     rax, aRegqueryvaluee_5; "RegQueryValueEx REG_VALUE_SECURITY_TEMP"...
0x18002eaa6  mov     [rbp+var_10], rax
0x18002eaaa  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002eab1  mov     [rbp+var_18], rax
0x18002eab5  lea     rax, [rbp+var_8]
0x18002eab9  mov     [rsp+60h+var_28], rax
0x18002eabe  lea     rax, [rbp+arg_10]
0x18002eac2  mov     [rsp+60h+var_30], rax
0x18002eac7  lea     rax, [rbp+var_10]
0x18002eacb  mov     [rsp+60h+lpcbData], rax
0x18002ead0  lea     rax, [rbp+var_18]
0x18002ead4  jmp     loc_18002E956
0x18002ead9  xor     ecx, ecx
0x18002eadb  cmp     [rbp+Data], 1
0x18002eadf  setz    cl
0x18002eae2  mov     [rdi], ecx
0x18002eae4  mov     rcx, [rbp+hKey]; hKey
0x18002eae8  call    cs:__imp_RegCloseKey
0x18002eaee  mov     eax, ebx
0x18002eaf0  add     rsp, 60h
0x18002eaf4  pop     rdi
0x18002eaf5  pop     rbx
0x18002eaf6  pop     rbp
0x18002eaf7  retn
```
