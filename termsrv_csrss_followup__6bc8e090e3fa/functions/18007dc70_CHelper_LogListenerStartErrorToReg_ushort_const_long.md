# CHelper::LogListenerStartErrorToReg(ushort const *,long)

- ea: `0x18007dc70`
- end: `0x18007e154`
- name: `?LogListenerStartErrorToReg@CHelper@@SAJPEBGJ@Z`
- size: `1252`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004d4d0`

## callees

- `0x180001294`
- `0x180001a50`
- `0x1800020ec`
- `0x1800036d4`
- `0x1800038ac`
- `0x180016558`
- `0x180029ce4`
- `0x180029e48`
- `0x180033f60`
- `0x18007c610`
- `0x18007dc70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007df9c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007df9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007de86`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007de86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007dfd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007e057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007dfd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007e057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007de2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007de2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007dd94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007dd94`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007def7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007def7`

## string_xrefs

- `0x18007dd3b`: `Failed to build registry key path`
- `0x18007dd58`: `Clearing listener start error registry key (successful start)`
- `0x18007dddb`: `Failed to delete registry key`
- `0x18007dec2`: `Failed to create/open registry key`
- `0x18007dffb`: `Failed to write timestamp to registry`
- `0x18007e085`: `Failed to write error value to registry`
- `0x18007e0e6`: `Successfully logged listener start error to registry`

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
      LODWORD(a1) = dword_18012E170;
      if ( (unsigned int)dword_18012E170 <= 2 )
        goto LABEL_40;
      LODWORD(v36) = v9;
      v8 = byte_180113355;
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
            if ( (unsigned int)dword_18012E170 > 2 )
            {
              LODWORD(v36) = v6;
              v38 = "Failed to write timestamp to registry";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v23,
                (unsigned int)byte_180113263,
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
            if ( (unsigned int)dword_18012E170 > 2 )
            {
              LODWORD(v36) = a2;
              v38 = "Failed to write error value to registry";
              LODWORD(v37) = v6;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v27,
                (unsigned int)&unk_180113228,
                v28,
                v29,
                (__int64)&v38,
                (__int64)&v37,
                (__int64)&v36);
            }
          }
          else if ( (unsigned int)dword_18012E170 > 4 )
          {
            LODWORD(v37) = a2;
            v38 = (const char *)Source;
            v36 = v5;
            v41 = "Successfully logged listener start error to registry";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v27,
              (unsigned int)byte_1801131E1,
              v28,
              v29,
              (__int64)&v41,
              (__int64)&v36,
              (__int64)&v37,
              (__int64)&v38);
          }
        }
        else if ( (unsigned int)dword_18012E170 > 2 )
        {
          LODWORD(v36) = v6;
          v38 = "Failed to format timestamp string";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v18,
            (unsigned int)&word_18011328E,
            v19,
            v20,
            (__int64)&v38,
            (__int64)&v36);
        }
        goto LABEL_40;
      }
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)dword_18012E170 <= 2 )
        goto LABEL_40;
      v37 = SubKey;
      v15 = byte_1801132B9;
      v38 = "Failed to create/open registry key";
      v16 = (BYTE *)&v38;
    }
    else
    {
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        v37 = (WCHAR *)v5;
        *(_QWORD *)Data = "Clearing listener start error registry key (successful start)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)byte_180113321,
          a3,
          a4,
          (__int64)Data,
          (__int64)&v37);
      }
      v11 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
      if ( (v11 & 0xFFFFFFFD) == 0 )
        goto LABEL_40;
      v6 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
      if ( (unsigned int)dword_18012E170 <= 2 )
        goto LABEL_40;
      v37 = SubKey;
      v15 = byte_1801132ED;
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
  if ( (unsigned int)dword_18012E170 > 2 )
  {
    LODWORD(v36) = -2147024809;
    v7 = "Invalid listener name";
    v8 = (char *)&unk_180113380;
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
0x18007dc70  mov     [rsp-8+arg_10], rbx
0x18007dc75  push    rbp
0x18007dc76  push    rsi
0x18007dc77  push    r14
0x18007dc79  lea     rbp, [rsp-230h]
0x18007dc81  sub     rsp, 330h
0x18007dc88  mov     rax, cs:__security_cookie
0x18007dc8f  xor     rax, rsp
0x18007dc92  mov     [rbp+240h+var_20], rax
0x18007dc99  mov     [rsp+340h+hKey], 0
0x18007dca2  mov     r14d, edx
0x18007dca5  mov     rsi, rcx
0x18007dca8  test    rcx, rcx
0x18007dcab  jnz     short loc_18007DCFA
0x18007dcad  mov     eax, cs:dword_18012E170
0x18007dcb3  mov     ebx, 80070057h
0x18007dcb8  cmp     eax, 2
0x18007dcbb  jbe     loc_18007E124
0x18007dcc1  mov     dword ptr [rsp+340h+var_2F0], 80070057h
0x18007dcc9  lea     rax, aInvalidListene; "Invalid listener name"
0x18007dcd0  lea     rdx, unk_180113380
0x18007dcd7  mov     [rsp+340h+var_2E8], rax
0x18007dcdc  lea     rax, [rsp+340h+var_2F0]
0x18007dce1  mov     qword ptr [rsp+340h+samDesired], rax
0x18007dce6  lea     rax, [rsp+340h+var_2E8]
0x18007dceb  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007dcf0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007dcf5  jmp     loc_18007E124
0x18007dcfa  lea     r9, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Ter"...
0x18007dd01  mov     qword ptr [rsp+340h+dwOptions], rsi
0x18007dd06  lea     r8, aSS_0; "%s\\%s"
0x18007dd0d  mov     edx, 104h; unsigned __int64
0x18007dd12  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x18007dd16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007dd1b  mov     ebx, eax
0x18007dd1d  test    eax, eax
0x18007dd1f  jns     short loc_18007DD44
0x18007dd21  mov     ecx, cs:dword_18012E170
0x18007dd27  cmp     ecx, 2
0x18007dd2a  jbe     loc_18007E124
0x18007dd30  mov     dword ptr [rsp+340h+var_2F0], eax
0x18007dd34  lea     rdx, byte_180113355
0x18007dd3b  lea     rax, aFailedToBuildR; "Failed to build registry key path"
0x18007dd42  jmp     short loc_18007DCD7
0x18007dd44  test    r14d, r14d
0x18007dd47  js      loc_18007DE13
0x18007dd4d  mov     eax, cs:dword_18012E170
0x18007dd53  cmp     eax, 4
0x18007dd56  jbe     short loc_18007DD89
0x18007dd58  lea     rax, aClearingListen; "Clearing listener start error registry "...
0x18007dd5f  mov     [rsp+340h+var_2E8], rsi
0x18007dd64  mov     qword ptr [rsp+340h+Data], rax
0x18007dd69  lea     rdx, byte_180113321
0x18007dd70  lea     rax, [rsp+340h+var_2E8]
0x18007dd75  mov     qword ptr [rsp+340h+samDesired], rax
0x18007dd7a  lea     rax, [rsp+340h+Data]
0x18007dd7f  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007dd84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18007dd89  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x18007dd8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007dd94  call    cs:__imp_RegDeleteTreeW
0x18007dd9b  nop     dword ptr [rax+rax+00h]
0x18007dda0  test    eax, 0FFFFFFFDh
0x18007dda5  jz      loc_18007E124
0x18007ddab  test    eax, eax
0x18007ddad  jg      short loc_18007DDB3
0x18007ddaf  mov     ebx, eax
0x18007ddb1  jmp     short loc_18007DDBC
0x18007ddb3  movzx   ebx, ax
0x18007ddb6  or      ebx, 80070000h
0x18007ddbc  mov     eax, cs:dword_18012E170
0x18007ddc2  cmp     eax, 2
0x18007ddc5  jbe     loc_18007E124
0x18007ddcb  lea     rax, [rbp+240h+SubKey]
0x18007ddcf  mov     [rsp+340h+var_2E8], rax
0x18007ddd4  lea     rdx, byte_1801132ED
0x18007dddb  lea     rax, aFailedToDelete; "Failed to delete registry key"
0x18007dde2  mov     qword ptr [rsp+340h+Data], rax
0x18007dde7  lea     rax, [rsp+340h+var_2E8]
0x18007ddec  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007ddf1  lea     rax, [rsp+340h+var_2F0]
0x18007ddf6  mov     qword ptr [rsp+340h+samDesired], rax
0x18007ddfb  lea     rax, [rsp+340h+Data]
0x18007de00  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007de05  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007de09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007de0e  jmp     loc_18007E124
0x18007de13  mov     rbx, [rsp+340h+hKey]
0x18007de18  test    rbx, rbx
0x18007de1b  jz      short loc_18007DE40
0x18007de1d  lea     rcx, [rsp+340h+var_2E8]; this
0x18007de22  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007de27  mov     rcx, rbx; hKey
0x18007de2a  call    cs:__imp_RegCloseKey
0x18007de31  nop     dword ptr [rax+rax+00h]
0x18007de36  lea     rcx, [rsp+340h+var_2E8]; this
0x18007de3b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007de40  mov     [rsp+340h+lpdwDisposition], 0; lpdwDisposition
0x18007de49  lea     rax, [rsp+340h+hKey]
0x18007de4e  mov     [rsp+340h+phkResult], rax; phkResult
0x18007de53  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x18007de57  mov     [rsp+340h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007de60  xor     r9d, r9d; lpClass
0x18007de63  mov     [rsp+340h+samDesired], 20006h; samDesired
0x18007de6b  xor     r8d, r8d; Reserved
0x18007de6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007de75  mov     [rsp+340h+dwOptions], 0; dwOptions
0x18007de7d  mov     [rsp+340h+hKey], 0
0x18007de86  call    cs:__imp_RegCreateKeyExW
0x18007de8d  nop     dword ptr [rax+rax+00h]
0x18007de92  mov     ebx, eax
0x18007de94  test    eax, eax
0x18007de96  jz      short loc_18007DEEC
0x18007de98  jle     short loc_18007DEA3
0x18007de9a  movzx   ebx, ax
0x18007de9d  or      ebx, 80070000h
0x18007dea3  mov     eax, cs:dword_18012E170
0x18007dea9  cmp     eax, 2
0x18007deac  jbe     loc_18007E124
0x18007deb2  lea     rax, [rbp+240h+SubKey]
0x18007deb6  mov     [rsp+340h+var_2E8], rax
0x18007debb  lea     rdx, byte_1801132B9
0x18007dec2  lea     rax, aFailedToCreate_3; "Failed to create/open registry key"
0x18007dec9  mov     [rsp+340h+var_2E0], rax
0x18007dece  lea     rax, [rsp+340h+var_2E8]
0x18007ded3  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007ded8  lea     rax, [rsp+340h+var_2F0]
0x18007dedd  mov     qword ptr [rsp+340h+samDesired], rax
0x18007dee2  lea     rax, [rsp+340h+var_2E0]
0x18007dee7  jmp     loc_18007DE00
0x18007deec  xorps   xmm0, xmm0
0x18007deef  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x18007def3  movups  xmmword ptr [rbp+240h+SystemTime.wYear], xmm0
0x18007def7  call    cs:__imp_GetSystemTime
0x18007defe  nop     dword ptr [rax+rax+00h]
0x18007df03  movzx   ecx, [rbp+240h+SystemTime.wSecond]
0x18007df07  movzx   edx, [rbp+240h+SystemTime.wMinute]
0x18007df0b  movzx   r8d, [rbp+240h+SystemTime.wHour]
0x18007df10  movzx   eax, [rbp+240h+SystemTime.wMilliseconds]
0x18007df14  movzx   r10d, [rbp+240h+SystemTime.wDay]
0x18007df19  movzx   r11d, [rbp+240h+SystemTime.wMonth]
0x18007df1e  movzx   r9d, [rbp+240h+SystemTime.wYear]
0x18007df23  mov     [rsp+340h+var_2F8], eax
0x18007df27  mov     dword ptr [rsp+340h+lpdwDisposition], ecx
0x18007df2b  lea     rcx, [rbp+240h+Source]; unsigned __int16 *
0x18007df2f  mov     dword ptr [rsp+340h+phkResult], edx
0x18007df33  mov     edx, 40h ; '@'; unsigned __int64
0x18007df38  mov     dword ptr [rsp+340h+lpSecurityAttributes], r8d
0x18007df3d  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x18007df44  mov     [rsp+340h+samDesired], r10d
0x18007df49  mov     [rsp+340h+dwOptions], r11d
0x18007df4e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007df53  mov     ebx, eax
0x18007df55  test    eax, eax
0x18007df57  jns     short loc_18007DF93
0x18007df59  mov     eax, cs:dword_18012E170
0x18007df5f  cmp     eax, 2
0x18007df62  jbe     loc_18007E124
0x18007df68  lea     rax, aFailedToFormat; "Failed to format timestamp string"
0x18007df6f  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007df73  mov     [rsp+340h+var_2E0], rax
0x18007df78  lea     rdx, word_18011328E
0x18007df7f  lea     rax, [rsp+340h+var_2F0]
0x18007df84  mov     qword ptr [rsp+340h+samDesired], rax
0x18007df89  lea     rax, [rsp+340h+var_2E0]
0x18007df8e  jmp     loc_18007DCEB
0x18007df93  mov     edx, 40h ; '@'; MaxCount
0x18007df98  lea     rcx, [rbp+240h+Source]; Source
0x18007df9c  call    cs:__imp_wcsnlen
0x18007dfa3  nop     dword ptr [rax+rax+00h]
0x18007dfa8  mov     rcx, [rsp+340h+hKey]; hKey
0x18007dfad  lea     rdx, aTimestamp; "Timestamp"
0x18007dfb4  mov     r9d, 1; dwType
0x18007dfba  xor     r8d, r8d; Reserved
0x18007dfbd  lea     eax, ds:2[rax*2]
0x18007dfc4  mov     [rsp+340h+samDesired], eax; cbData
0x18007dfc8  lea     rax, [rbp+240h+Source]
0x18007dfcc  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18007dfd1  call    cs:__imp_RegSetValueExW
0x18007dfd8  nop     dword ptr [rax+rax+00h]
0x18007dfdd  test    eax, eax
0x18007dfdf  jz      short loc_18007E02B
0x18007dfe1  jg      short loc_18007DFE7
0x18007dfe3  mov     ebx, eax
0x18007dfe5  jmp     short loc_18007DFF0
0x18007dfe7  movzx   ebx, ax
0x18007dfea  or      ebx, 80070000h
0x18007dff0  mov     eax, cs:dword_18012E170
0x18007dff6  cmp     eax, 2
0x18007dff9  jbe     short loc_18007E02B
0x18007dffb  lea     rax, aFailedToWriteT; "Failed to write timestamp to registry"
0x18007e002  mov     dword ptr [rsp+340h+var_2F0], ebx
0x18007e006  mov     [rsp+340h+var_2E0], rax
0x18007e00b  lea     rdx, byte_180113263
0x18007e012  lea     rax, [rsp+340h+var_2F0]
0x18007e017  mov     qword ptr [rsp+340h+samDesired], rax
0x18007e01c  lea     rax, [rsp+340h+var_2E0]
0x18007e021  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007e026  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007e02b  mov     rcx, [rsp+340h+hKey]; hKey
0x18007e030  lea     rax, [rsp+340h+Data]
0x18007e035  mov     [rsp+340h+samDesired], 4; cbData
0x18007e03d  lea     rdx, aError; "Error"
0x18007e044  mov     r9d, 4; dwType
0x18007e04a  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x18007e04f  xor     r8d, r8d; Reserved
0x18007e052  mov     dword ptr [rsp+340h+Data], r14d
0x18007e057  call    cs:__imp_RegSetValueExW
0x18007e05e  nop     dword ptr [rax+rax+00h]
0x18007e063  test    eax, eax
0x18007e065  jz      short loc_18007E0C6
0x18007e067  jg      short loc_18007E06D
0x18007e069  mov     ebx, eax
0x18007e06b  jmp     short loc_18007E076
0x18007e06d  movzx   ebx, ax
0x18007e070  or      ebx, 80070000h
0x18007e076  mov     eax, cs:dword_18012E170
0x18007e07c  cmp     eax, 2
0x18007e07f  jbe     loc_18007E124
0x18007e085  lea     rax, aFailedToWriteE; "Failed to write error value to registry"
0x18007e08c  mov     dword ptr [rsp+340h+var_2F0], r14d
0x18007e091  mov     [rsp+340h+var_2E0], rax
0x18007e096  lea     rdx, unk_180113228
0x18007e09d  lea     rax, [rsp+340h+var_2F0]
0x18007e0a2  mov     dword ptr [rsp+340h+var_2E8], ebx
0x18007e0a6  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007e0ab  lea     rax, [rsp+340h+var_2E8]
0x18007e0b0  mov     qword ptr [rsp+340h+samDesired], rax
0x18007e0b5  lea     rax, [rsp+340h+var_2E0]
0x18007e0ba  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007e0bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007e0c4  jmp     short loc_18007E124
0x18007e0c6  mov     eax, cs:dword_18012E170
0x18007e0cc  cmp     eax, 4
0x18007e0cf  jbe     short loc_18007E124
0x18007e0d1  lea     rax, [rbp+240h+Source]
0x18007e0d5  mov     dword ptr [rsp+340h+var_2E8], r14d
0x18007e0da  mov     [rsp+340h+var_2E0], rax
0x18007e0df  lea     rdx, byte_1801131E1
0x18007e0e6  lea     rax, aSuccessfullyLo; "Successfully logged listener start erro"...
0x18007e0ed  mov     [rsp+340h+var_2F0], rsi
0x18007e0f2  mov     [rsp+340h+var_2C8], rax
0x18007e0f7  lea     rax, [rsp+340h+var_2E0]
0x18007e0fc  mov     [rsp+340h+phkResult], rax
0x18007e101  lea     rax, [rsp+340h+var_2E8]
0x18007e106  mov     [rsp+340h+lpSecurityAttributes], rax
0x18007e10b  lea     rax, [rsp+340h+var_2F0]
0x18007e110  mov     qword ptr [rsp+340h+samDesired], rax
0x18007e115  lea     rax, [rsp+340h+var_2C8]
0x18007e11a  mov     qword ptr [rsp+340h+dwOptions], rax
0x18007e11f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007e124  lea     rcx, [rsp+340h+hKey]
0x18007e129  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007e12e  mov     eax, ebx
0x18007e130  mov     rcx, [rbp+240h+var_20]
0x18007e137  xor     rcx, rsp; StackCookie
0x18007e13a  call    __security_check_cookie
0x18007e13f  mov     rbx, [rsp+340h+arg_10]
0x18007e147  add     rsp, 330h
0x18007e14e  pop     r14
0x18007e150  pop     rsi
0x18007e151  pop     rbp
0x18007e152  retn
```
