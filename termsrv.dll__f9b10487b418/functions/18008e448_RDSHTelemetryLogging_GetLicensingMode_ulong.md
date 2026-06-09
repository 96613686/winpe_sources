# RDSHTelemetryLogging::GetLicensingMode(ulong *)

- ea: `0x18008e448`
- end: `0x18008e638`
- name: `?GetLicensingMode@RDSHTelemetryLogging@@CAJPEAK@Z`
- size: `496`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18008f264`
- `0x18008fb70`

## callees

- `0x180001688`
- `0x18008e448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e53f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e53f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e628`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e493`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e493`

## string_xrefs

- `0x18008e4cd`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`

## pseudocode

```c
__int64 __fastcall RDSHTelemetryLogging::GetLicensingMode(unsigned int *a1)
{
  LSTATUS v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  signed int v6; // ebx
  __int16 *v7; // rdx
  const unsigned __int16 **v8; // rax
  LSTATUS v9; // eax
  const unsigned __int16 **v11; // [rsp+38h] [rbp-38h]
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_17;
    v14 = "GetLicensingMode";
    v7 = word_18011119A;
    v15 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
    v16[0] = "Warning HResult failed";
    v11 = (const unsigned __int16 **)&v14;
    v8 = (const unsigned __int16 **)v16;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v16[0] = "GetLicensingMode";
        v7 = word_180111112;
        v15 = "REG_LICENSING_MODE_VALUE not REG_DWORD";
        v14 = "Warning HResult failed";
        v11 = (const unsigned __int16 **)v16;
        v8 = (const unsigned __int16 **)&v14;
        goto LABEL_6;
      }
    }
  }
  else if ( (unsigned int)dword_180128170 > 3 )
  {
    v16[0] = "GetLicensingMode";
    v7 = &word_180111156;
    v15 = "RegQueryValueEx REG_LICENSING_MODE_VALUE failed";
    v14 = "Warning HResult failed";
    v11 = (const unsigned __int16 **)v16;
    v8 = (const unsigned __int16 **)&v14;
LABEL_6:
    v12 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (int)v7,
      v4,
      v5,
      v8,
      (const unsigned __int16 **)&v15,
      (__int64)&v12,
      v11);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008e448  push    rbp
0x18008e44a  push    rbx
0x18008e44b  push    rdi
0x18008e44c  mov     rbp, rsp
0x18008e44f  sub     rsp, 70h
0x18008e453  mov     rdi, rcx
0x18008e456  mov     [rbp+hKey], 0
0x18008e45e  lea     rax, [rbp+hKey]
0x18008e462  mov     [rbp+Type], 0
0x18008e469  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008e470  mov     [rsp+70h+phkResult], rax; phkResult
0x18008e475  mov     r9d, 20019h; samDesired
0x18008e47b  mov     [rbp+cbData], 0
0x18008e482  xor     r8d, r8d; ulOptions
0x18008e485  mov     [rbp+Data], 0
0x18008e48c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Ter"...
0x18008e493  call    cs:__imp_RegOpenKeyExW
0x18008e499  mov     ebx, eax
0x18008e49b  test    eax, eax
0x18008e49d  jle     short loc_18008E4A8
0x18008e49f  movzx   ebx, ax
0x18008e4a2  or      ebx, 80070000h
0x18008e4a8  test    ebx, ebx
0x18008e4aa  jns     short loc_18008E514
0x18008e4ac  mov     eax, cs:dword_180128170
0x18008e4b2  cmp     eax, 3
0x18008e4b5  jbe     loc_18008E61F
0x18008e4bb  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x18008e4c2  mov     [rbp+var_20], rax
0x18008e4c6  lea     rdx, word_18011119A
0x18008e4cd  lea     rax, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x18008e4d4  mov     [rbp+var_18], rax
0x18008e4d8  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e4df  mov     [rbp+var_10], rax
0x18008e4e3  lea     rax, [rbp+var_20]
0x18008e4e7  mov     [rsp+70h+var_38], rax
0x18008e4ec  lea     rax, [rbp+var_30]
0x18008e4f0  mov     [rsp+70h+var_40], rax
0x18008e4f5  lea     rax, [rbp+var_18]
0x18008e4f9  mov     [rsp+70h+lpcbData], rax
0x18008e4fe  lea     rax, [rbp+var_10]
0x18008e502  mov     [rbp+var_30], ebx
0x18008e505  mov     [rsp+70h+phkResult], rax
0x18008e50a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008e50f  jmp     loc_18008E61F
0x18008e514  mov     rcx, [rbp+hKey]; hKey
0x18008e518  lea     rax, [rbp+cbData]
0x18008e51c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18008e521  lea     r9, [rbp+Type]; lpType
0x18008e525  lea     rax, [rbp+Data]
0x18008e529  mov     [rbp+cbData], 4
0x18008e530  xor     r8d, r8d; lpReserved
0x18008e533  mov     [rsp+70h+phkResult], rax; lpData
0x18008e538  lea     rdx, aLicensingmode; "LicensingMode"
0x18008e53f  call    cs:__imp_RegQueryValueExW
0x18008e545  mov     ebx, eax
0x18008e547  test    eax, eax
0x18008e549  jle     short loc_18008E554
0x18008e54b  movzx   ebx, ax
0x18008e54e  or      ebx, 80070000h
0x18008e554  test    ebx, ebx
0x18008e556  jns     short loc_18008E5B3
0x18008e558  mov     eax, cs:dword_180128170
0x18008e55e  cmp     eax, 3
0x18008e561  jbe     loc_18008E61F
0x18008e567  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x18008e56e  mov     [rbp+var_10], rax
0x18008e572  lea     rdx, word_180111156
0x18008e579  lea     rax, aRegqueryvaluee_5; "RegQueryValueEx REG_LICENSING_MODE_VALU"...
0x18008e580  mov     [rbp+var_18], rax
0x18008e584  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e58b  mov     [rbp+var_20], rax
0x18008e58f  lea     rax, [rbp+var_10]
0x18008e593  mov     [rsp+70h+var_38], rax
0x18008e598  lea     rax, [rbp+var_30]
0x18008e59c  mov     [rsp+70h+var_40], rax
0x18008e5a1  lea     rax, [rbp+var_18]
0x18008e5a5  mov     [rsp+70h+lpcbData], rax
0x18008e5aa  lea     rax, [rbp+var_20]
0x18008e5ae  jmp     loc_18008E502
0x18008e5b3  cmp     [rbp+Type], 4
0x18008e5b7  jz      short loc_18008E615
0x18008e5b9  mov     eax, cs:dword_180128170
0x18008e5bf  mov     ebx, 80070057h
0x18008e5c4  cmp     eax, 3
0x18008e5c7  jbe     short loc_18008E61F
0x18008e5c9  lea     rax, aGetlicensingmo; "GetLicensingMode"
0x18008e5d0  mov     [rbp+var_10], rax
0x18008e5d4  lea     rdx, word_180111112
0x18008e5db  lea     rax, aRegLicensingMo; "REG_LICENSING_MODE_VALUE not REG_DWORD"
0x18008e5e2  mov     [rbp+var_18], rax
0x18008e5e6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008e5ed  mov     [rbp+var_20], rax
0x18008e5f1  lea     rax, [rbp+var_10]
0x18008e5f5  mov     [rsp+70h+var_38], rax
0x18008e5fa  lea     rax, [rbp+var_30]
0x18008e5fe  mov     [rsp+70h+var_40], rax
0x18008e603  lea     rax, [rbp+var_18]
0x18008e607  mov     [rsp+70h+lpcbData], rax
0x18008e60c  lea     rax, [rbp+var_20]
0x18008e610  jmp     loc_18008E502
0x18008e615  test    rdi, rdi
0x18008e618  jz      short loc_18008E61F
0x18008e61a  mov     ecx, [rbp+Data]
0x18008e61d  mov     [rdi], ecx
0x18008e61f  mov     rcx, [rbp+hKey]; hKey
0x18008e623  test    rcx, rcx
0x18008e626  jz      short loc_18008E62E
0x18008e628  call    cs:__imp_RegCloseKey
0x18008e62e  mov     eax, ebx
0x18008e630  add     rsp, 70h
0x18008e634  pop     rdi
0x18008e635  pop     rbx
0x18008e636  pop     rbp
0x18008e637  retn
```
