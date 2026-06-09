# RDSHTelemetryLogging::GetLicensingMode(ulong *)

- ea: `0x180092160`
- end: `0x180092363`
- name: `?GetLicensingMode@RDSHTelemetryLogging@@CAJPEAK@Z`
- size: `515`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180092fd8`
- `0x1800938f0`

## callees

- `0x1800016a8`
- `0x180092160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009225d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009225d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009234c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009234c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800921ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800921ab`

## string_xrefs

- `0x1800921eb`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`

## pseudocode

```c
__int64 __fastcall RDSHTelemetryLogging::GetLicensingMode(unsigned int *a1)
{
  LSTATUS v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  LSTATUS v9; // eax
  const char **v11; // [rsp+38h] [rbp-38h]
  signed int v12; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  const char *v15; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+28h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Licensing Core",
         0,
         0x20019u,
         &hKey);
  v6 = v2;
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_17;
    v14 = "GetLicensingMode";
    v7 = word_18011721A;
    v15 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
    v16[0] = "Warning HResult failed";
    v11 = &v14;
    v8 = (const char **)v16;
    goto LABEL_6;
  }
  cbData = 4;
  v9 = RegQueryValueExW(hKey, L"LicensingMode", 0, &Type, (LPBYTE)&Data, &cbData);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 >= 0 )
  {
    if ( Type == 4 )
    {
      if ( a1 )
        *a1 = Data;
    }
    else
    {
      v6 = -2147024809;
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v16[0] = "GetLicensingMode";
        v7 = word_180117192;
        v15 = "REG_LICENSING_MODE_VALUE not REG_DWORD";
        v14 = "Warning HResult failed";
        v11 = (const char **)v16;
        v8 = &v14;
        goto LABEL_6;
      }
    }
  }
  else if ( (unsigned int)dword_18012E170 > 3 )
  {
    v16[0] = "GetLicensingMode";
    v7 = &word_1801171D6;
    v15 = "RegQueryValueEx REG_LICENSING_MODE_VALUE failed";
    v14 = "Warning HResult failed";
    v11 = (const char **)v16;
    v8 = &v14;
LABEL_6:
    v12 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)v8,
      (__int64)&v15,
      (__int64)&v12,
      (__int64)v11);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180092160  push    rbp
0x180092162  push    rbx
0x180092163  push    rdi
0x180092164  mov     rbp, rsp
0x180092167  sub     rsp, 70h
0x18009216b  mov     rdi, rcx
0x18009216e  mov     [rbp+hKey], 0
0x180092176  lea     rax, [rbp+hKey]
0x18009217a  mov     [rbp+Type], 0
0x180092181  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180092188  mov     [rsp+70h+phkResult], rax; phkResult
0x18009218d  mov     r9d, 20019h; samDesired
0x180092193  mov     [rbp+cbData], 0
0x18009219a  xor     r8d, r8d; ulOptions
0x18009219d  mov     [rbp+Data], 0
0x1800921a4  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Ter"...
0x1800921ab  call    cs:__imp_RegOpenKeyExW
0x1800921b2  nop     dword ptr [rax+rax+00h]
0x1800921b7  mov     ebx, eax
0x1800921b9  test    eax, eax
0x1800921bb  jle     short loc_1800921C6
0x1800921bd  movzx   ebx, ax
0x1800921c0  or      ebx, 80070000h
0x1800921c6  test    ebx, ebx
0x1800921c8  jns     short loc_180092232
0x1800921ca  mov     eax, cs:dword_18012E170
0x1800921d0  cmp     eax, 3
0x1800921d3  jbe     loc_180092343
0x1800921d9  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x1800921e0  mov     [rbp+var_20], rax
0x1800921e4  lea     rdx, word_18011721A
0x1800921eb  lea     rax, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x1800921f2  mov     [rbp+var_18], rax
0x1800921f6  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800921fd  mov     [rbp+var_10], rax
0x180092201  lea     rax, [rbp+var_20]
0x180092205  mov     [rsp+70h+var_38], rax
0x18009220a  lea     rax, [rbp+var_30]
0x18009220e  mov     [rsp+70h+var_40], rax
0x180092213  lea     rax, [rbp+var_18]
0x180092217  mov     [rsp+70h+lpcbData], rax
0x18009221c  lea     rax, [rbp+var_10]
0x180092220  mov     [rbp+var_30], ebx
0x180092223  mov     [rsp+70h+phkResult], rax
0x180092228  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009222d  jmp     loc_180092343
0x180092232  mov     rcx, [rbp+hKey]; hKey
0x180092236  lea     rax, [rbp+cbData]
0x18009223a  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18009223f  lea     r9, [rbp+Type]; lpType
0x180092243  lea     rax, [rbp+Data]
0x180092247  mov     [rbp+cbData], 4
0x18009224e  xor     r8d, r8d; lpReserved
0x180092251  mov     [rsp+70h+phkResult], rax; lpData
0x180092256  lea     rdx, aLicensingmode; "LicensingMode"
0x18009225d  call    cs:__imp_RegQueryValueExW
0x180092264  nop     dword ptr [rax+rax+00h]
0x180092269  mov     ebx, eax
0x18009226b  test    eax, eax
0x18009226d  jle     short loc_180092278
0x18009226f  movzx   ebx, ax
0x180092272  or      ebx, 80070000h
0x180092278  test    ebx, ebx
0x18009227a  jns     short loc_1800922D7
0x18009227c  mov     eax, cs:dword_18012E170
0x180092282  cmp     eax, 3
0x180092285  jbe     loc_180092343
0x18009228b  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x180092292  mov     [rbp+var_10], rax
0x180092296  lea     rdx, word_1801171D6
0x18009229d  lea     rax, aRegqueryvaluee_5; "RegQueryValueEx REG_LICENSING_MODE_VALU"...
0x1800922a4  mov     [rbp+var_18], rax
0x1800922a8  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800922af  mov     [rbp+var_20], rax
0x1800922b3  lea     rax, [rbp+var_10]
0x1800922b7  mov     [rsp+70h+var_38], rax
0x1800922bc  lea     rax, [rbp+var_30]
0x1800922c0  mov     [rsp+70h+var_40], rax
0x1800922c5  lea     rax, [rbp+var_18]
0x1800922c9  mov     [rsp+70h+lpcbData], rax
0x1800922ce  lea     rax, [rbp+var_20]
0x1800922d2  jmp     loc_180092220
0x1800922d7  cmp     [rbp+Type], 4
0x1800922db  jz      short loc_180092339
0x1800922dd  mov     eax, cs:dword_18012E170
0x1800922e3  mov     ebx, 80070057h
0x1800922e8  cmp     eax, 3
0x1800922eb  jbe     short loc_180092343
0x1800922ed  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x1800922f4  mov     [rbp+var_10], rax
0x1800922f8  lea     rdx, word_180117192
0x1800922ff  lea     rax, aRegLicensingMo; "REG_LICENSING_MODE_VALUE not REG_DWORD"
0x180092306  mov     [rbp+var_18], rax
0x18009230a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092311  mov     [rbp+var_20], rax
0x180092315  lea     rax, [rbp+var_10]
0x180092319  mov     [rsp+70h+var_38], rax
0x18009231e  lea     rax, [rbp+var_30]
0x180092322  mov     [rsp+70h+var_40], rax
0x180092327  lea     rax, [rbp+var_18]
0x18009232b  mov     [rsp+70h+lpcbData], rax
0x180092330  lea     rax, [rbp+var_20]
0x180092334  jmp     loc_180092220
0x180092339  test    rdi, rdi
0x18009233c  jz      short loc_180092343
0x18009233e  mov     ecx, [rbp+Data]
0x180092341  mov     [rdi], ecx
0x180092343  mov     rcx, [rbp+hKey]; hKey
0x180092347  test    rcx, rcx
0x18009234a  jz      short loc_180092358
0x18009234c  call    cs:__imp_RegCloseKey
0x180092353  nop     dword ptr [rax+rax+00h]
0x180092358  mov     eax, ebx
0x18009235a  add     rsp, 70h
0x18009235e  pop     rdi
0x18009235f  pop     rbx
0x180092360  pop     rbp
0x180092361  retn
```
