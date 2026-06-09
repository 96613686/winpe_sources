# RDSHTelemetryLogging::GetSessDirActive(ulong *)

- ea: `0x18008e778`
- end: `0x18008e979`
- name: `?GetSessDirActive@RDSHTelemetryLogging@@CAJPEAK@Z`
- size: `513`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18008e980`

## callees

- `0x180001688`
- `0x18008e778`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e86f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e86f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e7c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e7c3`

## string_xrefs

- `0x18008e7fd`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`
- `0x18008e868`: `SessionDirectoryActive`

## pseudocode

```c
__int64 __fastcall RDSHTelemetryLogging::GetSessDirActive(unsigned int *a1)
{
  LSTATUS v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // eax
  const char **v12; // [rsp+38h] [rbp-38h]
  signed int v13; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  const char *v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v6 = v2;
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_21;
    v15 = "GetSessDirActive";
    v7 = &word_180111266;
    v16 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
    v17[0] = "Warning HResult failed";
    v12 = &v15;
    v8 = (const char **)v17;
    goto LABEL_6;
  }
  cbData = 4;
  v9 = RegQueryValueExW(hKey, L"SessionDirectoryActive", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v9 == 2 )
  {
    v10 = 0;
    Data = 0;
    goto LABEL_19;
  }
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  else
    v6 = v9;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_21;
    v17[0] = "GetSessDirActive";
    v7 = word_180111222;
    v16 = "RegQueryValueEx REG_TS_SESSDIRACTIVE failed";
    v15 = "Warning HResult failed";
    v12 = (const char **)v17;
    v8 = &v15;
    goto LABEL_6;
  }
  if ( Type != 4 )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_21;
    v17[0] = "GetSessDirActive";
    v7 = &word_1801111DE;
    v16 = "REG_TS_SESSDIRACTIVE not REG_DWORD";
    v15 = "Warning HResult failed";
    v12 = (const char **)v17;
    v8 = &v15;
LABEL_6:
    v13 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)v8,
      (__int64)&v16,
      (__int64)&v13,
      (__int64)v12);
    goto LABEL_21;
  }
  v10 = Data;
LABEL_19:
  if ( a1 )
    *a1 = v10;
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008e778  push    rbp
0x18008e77a  push    rbx
0x18008e77b  push    rdi
0x18008e77c  mov     rbp, rsp
0x18008e77f  sub     rsp, 70h
0x18008e783  mov     rdi, rcx
0x18008e786  mov     [rbp+hKey], 0
0x18008e78e  lea     rax, [rbp+hKey]
0x18008e792  mov     [rbp+Type], 0
0x18008e799  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008e7a0  mov     [rsp+70h+phkResult], rax; phkResult
0x18008e7a5  mov     r9d, 20019h; samDesired
0x18008e7ab  mov     [rbp+cbData], 0
0x18008e7b2  xor     r8d, r8d; ulOptions
0x18008e7b5  mov     [rbp+Data], 0
0x18008e7bc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18008e7c3  call    cs:__imp_RegOpenKeyExW
0x18008e7c9  mov     ebx, eax
0x18008e7cb  test    eax, eax
0x18008e7cd  jle     short loc_18008E7D8
0x18008e7cf  movzx   ebx, ax
0x18008e7d2  or      ebx, 80070000h
0x18008e7d8  test    ebx, ebx
0x18008e7da  jns     short loc_18008E844
0x18008e7dc  mov     eax, cs:dword_180128170
0x18008e7e2  cmp     eax, 3
0x18008e7e5  jbe     loc_18008E960
0x18008e7eb  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x18008e7f2  mov     [rbp+var_20], rax
0x18008e7f6  lea     rdx, word_180111266
0x18008e7fd  lea     rax, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x18008e804  mov     [rbp+var_18], rax
0x18008e808  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e80f  mov     [rbp+var_10], rax
0x18008e813  lea     rax, [rbp+var_20]
0x18008e817  mov     [rsp+70h+var_38], rax
0x18008e81c  lea     rax, [rbp+var_30]
0x18008e820  mov     [rsp+70h+var_40], rax
0x18008e825  lea     rax, [rbp+var_18]
0x18008e829  mov     [rsp+70h+lpcbData], rax
0x18008e82e  lea     rax, [rbp+var_10]
0x18008e832  mov     [rbp+var_30], ebx
0x18008e835  mov     [rsp+70h+phkResult], rax
0x18008e83a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008e83f  jmp     loc_18008E960
0x18008e844  mov     rcx, [rbp+hKey]; hKey
0x18008e848  lea     rax, [rbp+cbData]
0x18008e84c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18008e851  lea     r9, [rbp+Type]; lpType
0x18008e855  lea     rax, [rbp+Data]
0x18008e859  mov     [rbp+cbData], 4
0x18008e860  xor     r8d, r8d; lpReserved
0x18008e863  mov     [rsp+70h+phkResult], rax; lpData
0x18008e868  lea     rdx, aSessiondirecto_3; "SessionDirectoryActive"
0x18008e86f  call    cs:__imp_RegQueryValueExW
0x18008e875  cmp     eax, 2
0x18008e878  jnz     short loc_18008E884
0x18008e87a  xor     eax, eax
0x18008e87c  mov     [rbp+Data], eax
0x18008e87f  jmp     loc_18008E959
0x18008e884  test    eax, eax
0x18008e886  jg      short loc_18008E88C
0x18008e888  mov     ebx, eax
0x18008e88a  jmp     short loc_18008E895
0x18008e88c  movzx   ebx, ax
0x18008e88f  or      ebx, 80070000h
0x18008e895  test    ebx, ebx
0x18008e897  jns     short loc_18008E8F4
0x18008e899  mov     eax, cs:dword_180128170
0x18008e89f  cmp     eax, 3
0x18008e8a2  jbe     loc_18008E960
0x18008e8a8  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x18008e8af  mov     [rbp+var_10], rax
0x18008e8b3  lea     rdx, word_180111222
0x18008e8ba  lea     rax, aRegqueryvaluee_7; "RegQueryValueEx REG_TS_SESSDIRACTIVE fa"...
0x18008e8c1  mov     [rbp+var_18], rax
0x18008e8c5  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e8cc  mov     [rbp+var_20], rax
0x18008e8d0  lea     rax, [rbp+var_10]
0x18008e8d4  mov     [rsp+70h+var_38], rax
0x18008e8d9  lea     rax, [rbp+var_30]
0x18008e8dd  mov     [rsp+70h+var_40], rax
0x18008e8e2  lea     rax, [rbp+var_18]
0x18008e8e6  mov     [rsp+70h+lpcbData], rax
0x18008e8eb  lea     rax, [rbp+var_20]
0x18008e8ef  jmp     loc_18008E832
0x18008e8f4  cmp     [rbp+Type], 4
0x18008e8f8  jz      short loc_18008E956
0x18008e8fa  mov     eax, cs:dword_180128170
0x18008e900  mov     ebx, 80070057h
0x18008e905  cmp     eax, 3
0x18008e908  jbe     short loc_18008E960
0x18008e90a  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x18008e911  mov     [rbp+var_10], rax
0x18008e915  lea     rdx, word_1801111DE
0x18008e91c  lea     rax, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD"
0x18008e923  mov     [rbp+var_18], rax
0x18008e927  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e92e  mov     [rbp+var_20], rax
0x18008e932  lea     rax, [rbp+var_10]
0x18008e936  mov     [rsp+70h+var_38], rax
0x18008e93b  lea     rax, [rbp+var_30]
0x18008e93f  mov     [rsp+70h+var_40], rax
0x18008e944  lea     rax, [rbp+var_18]
0x18008e948  mov     [rsp+70h+lpcbData], rax
0x18008e94d  lea     rax, [rbp+var_20]
0x18008e951  jmp     loc_18008E832
0x18008e956  mov     eax, [rbp+Data]
0x18008e959  test    rdi, rdi
0x18008e95c  jz      short loc_18008E960
0x18008e95e  mov     [rdi], eax
0x18008e960  mov     rcx, [rbp+hKey]; hKey
0x18008e964  test    rcx, rcx
0x18008e967  jz      short loc_18008E96F
0x18008e969  call    cs:__imp_RegCloseKey
0x18008e96f  mov     eax, ebx
0x18008e971  add     rsp, 70h
0x18008e975  pop     rdi
0x18008e976  pop     rbx
0x18008e977  pop     rbp
0x18008e978  retn
```
