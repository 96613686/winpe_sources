# CHelper::LogListenerStartErrorToReg(ushort const *,long)

- ea: `0x18007a5bc`
- end: `0x18007aa75`
- name: `?LogListenerStartErrorToReg@CHelper@@SAJPEBGJ@Z`
- size: `1209`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004aeb0`

## callees

- `0x180001284`
- `0x180001a30`
- `0x1800020c8`
- `0x1800036a0`
- `0x180003878`
- `0x180015ab0`
- `0x1800287e0`
- `0x1800288f4`
- `0x1800321f0`
- `0x180078f80`
- `0x18007a5bc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007a8d0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007a8d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007a7c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007a7c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007a8ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007a97f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007a8ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007a97f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a770`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007a6e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007a6e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007a831`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007a831`

## string_xrefs

- `0x18007a687`: `Failed to build registry key path`
- `0x18007a6a4`: `Clearing listener start error registry key (successful start)`
- `0x18007a721`: `Failed to delete registry key`
- `0x18007a7fc`: `Failed to create/open registry key`
- `0x18007a923`: `Failed to write timestamp to registry`
- `0x18007a9a7`: `Failed to write error value to registry`
- `0x18007aa08`: `Successfully logged listener start error to registry`

## pseudocode

```c
__int64 __fastcall CHelper::LogListenerStartErrorToReg(const unsigned __int16 *a1, int a2, int a3, int a4)
{
  const unsigned __int16 *v5; // rsi
  signed int v6; // ebx
  const char *v7; // rax
  char *v8; // rdx
  int v9; // eax
  int v10; // ecx
  LSTATUS v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  char *v15; // rdx
  BYTE *v16; // rax
  LSTATUS v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  LSTATUS v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  LSTATUS v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v36; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v37; // [rsp+58h] [rbp-A8h] BYREF
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Source[64]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  v5 = a1;
  if ( a1 )
  {
    v9 = StringCchPrintfW(
           SubKey,
           0x104u,
           L"%s\\%s",
           L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStationsStartError",
           a1);
    v6 = v9;
    if ( v9 < 0 )
    {
      LODWORD(a1) = dword_180128170;
      if ( (unsigned int)dword_180128170 <= 2 )
        goto LABEL_40;
      LODWORD(v36) = v9;
      v8 = byte_18010D2D5;
      v7 = "Failed to build registry key path";
      goto LABEL_4;
    }
    if ( a2 < 0 )
    {
      hKey = 0;
      v17 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v6 = v17;
      if ( !v17 )
      {
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        LODWORD(lpdwDisposition) = SystemTime.wSecond;
        LODWORD(phkResult) = SystemTime.wMinute;
        LODWORD(lpSecurityAttributes) = SystemTime.wHour;
        samDesired[0] = SystemTime.wDay;
        dwOptions[0] = SystemTime.wMonth;
        v6 = StringCchPrintfW(
               Source,
               0x40u,
               L"%04u-%02u-%02uT%02u:%02u:%02u.%03uZ",
               SystemTime.wYear,
               *(_QWORD *)dwOptions,
               *(_QWORD *)samDesired,
               lpSecurityAttributes,
               phkResult,
               lpdwDisposition,
               SystemTime.wMilliseconds);
        if ( v6 >= 0 )
        {
          v21 = wcsnlen(Source, 0x40u);
          v22 = RegSetValueExW(hKey, L"Timestamp", 0, 1u, (const BYTE *)Source, 2 * v21 + 2);
          if ( v22 )
          {
            v6 = v22 > 0 ? (unsigned __int16)v22 | 0x80070000 : v22;
            if ( (unsigned int)dword_180128170 > 2 )
            {
              LODWORD(v36) = v6;
              v38 = "Failed to write timestamp to registry";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v23,
                (unsigned int)byte_18010D1E3,
                v24,
                v25,
                (__int64)&v38,
                (__int64)&v36);
            }
          }
          *(_DWORD *)Data = a2;
          v26 = RegSetValueExW(hKey, L"Error", 0, 4u, Data, 4u);
          if ( v26 )
          {
            if ( v26 > 0 )
              v6 = (unsigned __int16)v26 | 0x80070000;
            else
              v6 = v26;
            if ( (unsigned int)dword_180128170 > 2 )
            {
              LODWORD(v36) = a2;
              v38 = "Failed to write error value to registry";
              LODWORD(v37) = v6;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v27,
                (unsigned int)&unk_18010D1A8,
                v28,
                v29,
                (__int64)&v38,
                (__int64)&v37,
                (__int64)&v36);
            }
          }
          else if ( (unsigned int)dword_180128170 > 4 )
          {
            LODWORD(v37) = a2;
            v38 = (const char *)Source;
            v36 = v5;
            v41 = "Successfully logged listener start error to registry";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v27,
              (unsigned int)byte_18010D161,
              v28,
              v29,
              (__int64)&v41,
              (__int64)&v36,
              (__int64)&v37,
              (__int64)&v38);
          }
        }
        else if ( (unsigned int)dword_180128170 > 2 )
        {
          LODWORD(v36) = v6;
          v38 = "Failed to format timestamp string";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v18,
            (unsigned int)&word_18010D20E,
            v19,
            v20,
            (__int64)&v38,
            (__int64)&v36);
        }
        goto LABEL_40;
      }
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)dword_180128170 <= 2 )
        goto LABEL_40;
      v37 = SubKey;
      v15 = byte_18010D239;
      v38 = "Failed to create/open registry key";
      v16 = (BYTE *)&v38;
    }
    else
    {
      if ( (unsigned int)dword_180128170 > 4 )
      {
        v37 = (WCHAR *)v5;
        *(_QWORD *)Data = "Clearing listener start error registry key (successful start)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)byte_18010D2A1,
          a3,
          a4,
          (__int64)Data,
          (__int64)&v37);
      }
      v11 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
      if ( (v11 & 0xFFFFFFFD) == 0 )
        goto LABEL_40;
      v6 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
      if ( (unsigned int)dword_180128170 <= 2 )
        goto LABEL_40;
      v37 = SubKey;
      v15 = byte_18010D26D;
      *(_QWORD *)Data = "Failed to delete registry key";
      v16 = Data;
    }
    LODWORD(v36) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v12,
      (_DWORD)v15,
      v13,
      v14,
      (__int64)v16,
      (__int64)&v36,
      (__int64)&v37);
    goto LABEL_40;
  }
  v6 = -2147024809;
  if ( (unsigned int)dword_180128170 > 2 )
  {
    LODWORD(v36) = -2147024809;
    v7 = "Invalid listener name";
    v8 = (char *)&unk_18010D300;
LABEL_4:
    v37 = (WCHAR *)v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (_DWORD)v8,
      a3,
      a4,
      (__int64)&v37,
      (__int64)&v36);
  }
LABEL_40:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007a5bc  mov     [rsp-8+arg_10], rbx
0x18007a5c1  push    rbp
0x18007a5c2  push    rsi
0x18007a5c3  push    r14
0x18007a5c5  lea     rbp, [rsp-230h]
0x18007a5cd  sub     rsp, 330h
0x18007a5d4  mov     rax, cs:__security_cookie
0x18007a5db  xor     rax, rsp
0x18007a5de  mov     [rbp+240h+var_20], rax
0x18007a5e5  mov     [rsp+340h+hKey], 0
0x18007a5ee  mov     r14d, edx
0x18007a5f1  mov     rsi, rcx
0x18007a5f4  test    rcx, rcx
0x18007a5f7  jnz     short loc_18007A646
0x18007a5f9  mov     eax, cs:dword_180128170
0x18007a5ff  mov     ebx, 80070057h
0x18007a604  cmp     eax, 2
0x18007a607  jbe     loc_18007AA46
0x18007a60d  mov     dword ptr [rsp+340h+var_2F0], 80070057h
0x18007a615  lea     rax, aInvalidListene; "Invalid listener name"
0x18007a61c  lea     rdx, unk_18010D300
0x18007a623  mov     [rsp+340h+var_2E8], rax
0x18007a628  lea     rax, [rsp+340h+var_2F0]
0x18007a62d  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a632  lea     rax, [rsp+340h+var_2E8]
0x18007a637  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007a63c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007a641  jmp     loc_18007AA46
0x18007a646  lea     r9, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Ter"...
0x18007a64d  mov     qword ptr [rsp+340h+dwOptions], rsi
0x18007a652  lea     r8, aSS_0; "%s\\%s"
0x18007a659  mov     edx, 104h; unsigned __int64
0x18007a65e  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x18007a662  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a667  mov     ebx, eax
0x18007a669  test    eax, eax
0x18007a66b  jns     short loc_18007A690
0x18007a66d  mov     ecx, cs:dword_180128170
0x18007a673  cmp     ecx, 2
0x18007a676  jbe     loc_18007AA46
0x18007a67c  mov     dword ptr [rsp+340h+var_2F0], eax
0x18007a680  lea     rdx, byte_18010D2D5
0x18007a687  lea     rax, aFailedToBuildR; "Failed to build registry key path"
0x18007a68e  jmp     short loc_18007A623
0x18007a690  test    r14d, r14d
0x18007a693  js      loc_18007A759
0x18007a699  mov     eax, cs:dword_180128170
0x18007a69f  cmp     eax, 4
0x18007a6a2  jbe     short loc_18007A6D5
0x18007a6a4  lea     rax, aClearingListen; "Clearing listener start error registry "...
0x18007a6ab  mov     [rsp+340h+var_2E8], rsi
0x18007a6b0  mov     qword ptr [rsp+340h+Data], rax
0x18007a6b5  lea     rdx, byte_18010D2A1
0x18007a6bc  lea     rax, [rsp+340h+var_2E8]
0x18007a6c1  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a6c6  lea     rax, [rsp+340h+Data]
0x18007a6cb  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007a6d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18007a6d5  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x18007a6d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a6e0  call    cs:__imp_RegDeleteTreeW
0x18007a6e6  test    eax, 0FFFFFFFDh
0x18007a6eb  jz      loc_18007AA46
0x18007a6f1  test    eax, eax
0x18007a6f3  jg      short loc_18007A6F9
0x18007a6f5  mov     ebx, eax
0x18007a6f7  jmp     short loc_18007A702
0x18007a6f9  movzx   ebx, ax
0x18007a6fc  or      ebx, 80070000h
0x18007a702  mov     eax, cs:dword_180128170
0x18007a708  cmp     eax, 2
0x18007a70b  jbe     loc_18007AA46
0x18007a711  lea     rax, [rbp+240h+SubKey]
0x18007a715  mov     [rsp+340h+var_2E8], rax
0x18007a71a  lea     rdx, byte_18010D26D
0x18007a721  lea     rax, aFailedToDelete; "Failed to delete registry key"
0x18007a728  mov     qword ptr [rsp+340h+Data], rax
0x18007a72d  lea     rax, [rsp+340h+var_2E8]
0x18007a732  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007a737  lea     rax, [rsp+340h+var_2F0]
0x18007a73c  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a741  lea     rax, [rsp+340h+Data]
0x18007a746  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007a74b  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007a74f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007a754  jmp     loc_18007AA46
0x18007a759  mov     rbx, [rsp+340h+hKey]
0x18007a75e  test    rbx, rbx
0x18007a761  jz      short loc_18007A780
0x18007a763  lea     rcx, [rsp+340h+var_2E8]; this
0x18007a768  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007a76d  mov     rcx, rbx; hKey
0x18007a770  call    cs:__imp_RegCloseKey
0x18007a776  lea     rcx, [rsp+340h+var_2E8]; this
0x18007a77b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007a780  mov     [rsp+340h+lpdwDisposition], 0; lpdwDisposition
0x18007a789  lea     rax, [rsp+340h+hKey]
0x18007a78e  mov     [rsp+340h+phkResult], rax; phkResult
0x18007a793  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x18007a797  mov     [rsp+340h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007a7a0  xor     r9d, r9d; lpClass
0x18007a7a3  mov     [rsp+340h+samDesired], 20006h; samDesired
0x18007a7ab  xor     r8d, r8d; Reserved
0x18007a7ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a7b5  mov     [rsp+340h+dwOptions], 0; dwOptions
0x18007a7bd  mov     [rsp+340h+hKey], 0
0x18007a7c6  call    cs:__imp_RegCreateKeyExW
0x18007a7cc  mov     ebx, eax
0x18007a7ce  test    eax, eax
0x18007a7d0  jz      short loc_18007A826
0x18007a7d2  jle     short loc_18007A7DD
0x18007a7d4  movzx   ebx, ax
0x18007a7d7  or      ebx, 80070000h
0x18007a7dd  mov     eax, cs:dword_180128170
0x18007a7e3  cmp     eax, 2
0x18007a7e6  jbe     loc_18007AA46
0x18007a7ec  lea     rax, [rbp+240h+SubKey]
0x18007a7f0  mov     [rsp+340h+var_2E8], rax
0x18007a7f5  lea     rdx, byte_18010D239
0x18007a7fc  lea     rax, aFailedToCreate_3; "Failed to create/open registry key"
0x18007a803  mov     [rsp+340h+var_2E0], rax
0x18007a808  lea     rax, [rsp+340h+var_2E8]
0x18007a80d  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007a812  lea     rax, [rsp+340h+var_2F0]
0x18007a817  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a81c  lea     rax, [rsp+340h+var_2E0]
0x18007a821  jmp     loc_18007A746
0x18007a826  xorps   xmm0, xmm0
0x18007a829  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x18007a82d  movups  xmmword ptr [rbp+240h+SystemTime.wYear], xmm0
0x18007a831  call    cs:__imp_GetSystemTime
0x18007a837  movzx   ecx, [rbp+240h+SystemTime.wSecond]
0x18007a83b  movzx   edx, [rbp+240h+SystemTime.wMinute]
0x18007a83f  movzx   r8d, [rbp+240h+SystemTime.wHour]
0x18007a844  movzx   eax, [rbp+240h+SystemTime.wMilliseconds]
0x18007a848  movzx   r10d, [rbp+240h+SystemTime.wDay]
0x18007a84d  movzx   r11d, [rbp+240h+SystemTime.wMonth]
0x18007a852  movzx   r9d, [rbp+240h+SystemTime.wYear]
0x18007a857  mov     [rsp+340h+var_2F8], eax
0x18007a85b  mov     dword ptr [rsp+340h+lpdwDisposition], ecx
0x18007a85f  lea     rcx, [rbp+240h+Source]; unsigned __int16 *
0x18007a863  mov     dword ptr [rsp+340h+phkResult], edx
0x18007a867  mov     edx, 40h ; '@'; unsigned __int64
0x18007a86c  mov     dword ptr [rsp+340h+lpSecurityAttributes], r8d
0x18007a871  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x18007a878  mov     [rsp+340h+samDesired], r10d
0x18007a87d  mov     [rsp+340h+dwOptions], r11d
0x18007a882  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a887  mov     ebx, eax
0x18007a889  test    eax, eax
0x18007a88b  jns     short loc_18007A8C7
0x18007a88d  mov     eax, cs:dword_180128170
0x18007a893  cmp     eax, 2
0x18007a896  jbe     loc_18007AA46
0x18007a89c  lea     rax, aFailedToFormat; "Failed to format timestamp string"
0x18007a8a3  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007a8a7  mov     [rsp+340h+var_2E0], rax
0x18007a8ac  lea     rdx, word_18010D20E
0x18007a8b3  lea     rax, [rsp+340h+var_2F0]
0x18007a8b8  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a8bd  lea     rax, [rsp+340h+var_2E0]
0x18007a8c2  jmp     loc_18007A637
0x18007a8c7  mov     edx, 40h ; '@'; MaxCount
0x18007a8cc  lea     rcx, [rbp+240h+Source]; Source
0x18007a8d0  call    cs:__imp_wcsnlen
0x18007a8d6  mov     rcx, [rsp+340h+hKey]; hKey
0x18007a8db  lea     rdx, aTimestamp; "Timestamp"
0x18007a8e2  mov     r9d, 1; dwType
0x18007a8e8  xor     r8d, r8d; Reserved
0x18007a8eb  lea     eax, ds:2[rax*2]
0x18007a8f2  mov     [rsp+340h+samDesired], eax; cbData
0x18007a8f6  lea     rax, [rbp+240h+Source]
0x18007a8fa  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18007a8ff  call    cs:__imp_RegSetValueExW
0x18007a905  test    eax, eax
0x18007a907  jz      short loc_18007A953
0x18007a909  jg      short loc_18007A90F
0x18007a90b  mov     ebx, eax
0x18007a90d  jmp     short loc_18007A918
0x18007a90f  movzx   ebx, ax
0x18007a912  or      ebx, 80070000h
0x18007a918  mov     eax, cs:dword_180128170
0x18007a91e  cmp     eax, 2
0x18007a921  jbe     short loc_18007A953
0x18007a923  lea     rax, aFailedToWriteT; "Failed to write timestamp to registry"
0x18007a92a  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007a92e  mov     [rsp+340h+var_2E0], rax
0x18007a933  lea     rdx, byte_18010D1E3
0x18007a93a  lea     rax, [rsp+340h+var_2F0]
0x18007a93f  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a944  lea     rax, [rsp+340h+var_2E0]
0x18007a949  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007a94e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007a953  mov     rcx, [rsp+340h+hKey]; hKey
0x18007a958  lea     rax, [rsp+340h+Data]
0x18007a95d  mov     [rsp+340h+samDesired], 4; cbData
0x18007a965  lea     rdx, aError; "Error"
0x18007a96c  mov     r9d, 4; dwType
0x18007a972  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18007a977  xor     r8d, r8d; Reserved
0x18007a97a  mov     dword ptr [rsp+340h+Data], r14d
0x18007a97f  call    cs:__imp_RegSetValueExW
0x18007a985  test    eax, eax
0x18007a987  jz      short loc_18007A9E8
0x18007a989  jg      short loc_18007A98F
0x18007a98b  mov     ebx, eax
0x18007a98d  jmp     short loc_18007A998
0x18007a98f  movzx   ebx, ax
0x18007a992  or      ebx, 80070000h
0x18007a998  mov     eax, cs:dword_180128170
0x18007a99e  cmp     eax, 2
0x18007a9a1  jbe     loc_18007AA46
0x18007a9a7  lea     rax, aFailedToWriteE; "Failed to write error value to registry"
0x18007a9ae  mov     dword ptr [rsp+340h+var_2F0], r14d
0x18007a9b3  mov     [rsp+340h+var_2E0], rax
0x18007a9b8  lea     rdx, unk_18010D1A8
0x18007a9bf  lea     rax, [rsp+340h+var_2F0]
0x18007a9c4  mov     dword ptr [rsp+340h+var_2E8], ebx
0x18007a9c8  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007a9cd  lea     rax, [rsp+340h+var_2E8]
0x18007a9d2  mov     qword ptr [rsp+340h+samDesired], rax
0x18007a9d7  lea     rax, [rsp+340h+var_2E0]
0x18007a9dc  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007a9e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007a9e6  jmp     short loc_18007AA46
0x18007a9e8  mov     eax, cs:dword_180128170
0x18007a9ee  cmp     eax, 4
0x18007a9f1  jbe     short loc_18007AA46
0x18007a9f3  lea     rax, [rbp+240h+Source]
0x18007a9f7  mov     dword ptr [rsp+340h+var_2E8], r14d
0x18007a9fc  mov     [rsp+340h+var_2E0], rax
0x18007aa01  lea     rdx, byte_18010D161
0x18007aa08  lea     rax, aSuccessfullyLo; "Successfully logged listener start erro"...
0x18007aa0f  mov     [rsp+340h+var_2F0], rsi
0x18007aa14  mov     [rsp+340h+var_2C8], rax
0x18007aa19  lea     rax, [rsp+340h+var_2E0]
0x18007aa1e  mov     [rsp+340h+phkResult], rax
0x18007aa23  lea     rax, [rsp+340h+var_2E8]
0x18007aa28  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007aa2d  lea     rax, [rsp+340h+var_2F0]
0x18007aa32  mov     qword ptr [rsp+340h+samDesired], rax
0x18007aa37  lea     rax, [rsp+340h+var_2C8]
0x18007aa3c  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007aa41  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007aa46  lea     rcx, [rsp+340h+hKey]
0x18007aa4b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007aa50  mov     eax, ebx
0x18007aa52  mov     rcx, [rbp+240h+var_20]
0x18007aa59  xor     rcx, rsp; StackCookie
0x18007aa5c  call    __security_check_cookie
0x18007aa61  mov     rbx, [rsp+340h+arg_10]
0x18007aa69  add     rsp, 330h
0x18007aa70  pop     r14
0x18007aa72  pop     rsi
0x18007aa73  pop     rbp
0x18007aa74  retn
```
