# CUtils::IsAppServerInstalled(int &)

- ea: `0x18009d750`
- end: `0x18009d900`
- name: `?IsAppServerInstalled@CUtils@@SAJAEAH@Z`
- size: `432`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008d3cc`
- `0x18008f264`
- `0x18008fb70`
- `0x18009d4cc`

## callees

- `0x1800053e4`
- `0x1800059d8`
- `0x18009d750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d82a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d82a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d8ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d8ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d78e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d78e`

## string_xrefs

- `0x18009d801`: `TSAppCompat`
- `0x18009d7a5`: `Unable to open TS key in HKLM`
- `0x18009d8aa`: `Unable to read APPCOMPAT key`
- `0x18009d869`: `Successfully read APPCOMPAT key`

## pseudocode

```c
__int64 __fastcall CUtils::IsAppServerInstalled(int *a1)
{
  int v2; // ebx
  LSTATUS v3; // ecx
  int v4; // r8d
  int v5; // r9d
  const char *v7; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  const WCHAR *v9; // [rsp+50h] [rbp-18h] BYREF
  const char *v10; // [rsp+58h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+28h] BYREF
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  int Data; // [rsp+A0h] [rbp+38h] BYREF
  int v14; // [rsp+A8h] [rbp+40h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v14 = v2;
      v7 = "Unable to open TS key in HKLM";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180128170,
        (unsigned int)&word_180113B3E,
        0,
        0,
        (__int64)&v7,
        (__int64)&v14);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    cbData = 4;
    v2 = 0;
    Type = 0;
    Data = 0;
    v3 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && cbData == 4 && Type == 4 )
    {
      *a1 = Data;
      if ( (unsigned int)dword_180128170 > 4 )
      {
        v14 = *a1;
        v7 = "Successfully read APPCOMPAT key";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180128170,
          (unsigned int)&word_180113B66,
          0,
          0,
          (__int64)&v7,
          (__int64)&v14);
      }
    }
    else if ( (unsigned int)dword_180128170 > 4 )
    {
      v14 = *a1;
      v10 = "Unable to read APPCOMPAT key";
      v9 = L"TSAppCompat";
      LODWORD(v7) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned int)word_180113B92,
        v4,
        v5,
        (__int64)&v10,
        (__int64)&v7,
        (__int64)&v14,
        (__int64)&v9);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18009d750  push    rbp
0x18009d752  push    rbx
0x18009d753  push    rdi
0x18009d754  push    r15
0x18009d756  mov     rbp, rsp
0x18009d759  sub     rsp, 68h
0x18009d75d  mov     rdi, rcx
0x18009d760  mov     dword ptr [rcx], 0
0x18009d766  lea     rax, [rbp+hKey]
0x18009d76a  mov     [rbp+hKey], 0
0x18009d772  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009d779  mov     [rsp+68h+phkResult], rax; phkResult
0x18009d77e  mov     r9d, 20019h; samDesired
0x18009d784  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18009d78b  xor     r8d, r8d; ulOptions
0x18009d78e  call    cs:__imp_RegOpenKeyExW
0x18009d794  mov     ebx, eax
0x18009d796  test    eax, eax
0x18009d798  jz      short loc_18009D7F4
0x18009d79a  mov     eax, cs:dword_180128170
0x18009d7a0  cmp     eax, 2
0x18009d7a3  jbe     short loc_18009D7DE
0x18009d7a5  lea     rax, aUnableToOpenTs; "Unable to open TS key in HKLM"
0x18009d7ac  mov     [rbp+arg_18], ebx
0x18009d7af  mov     [rbp+var_28], rax
0x18009d7b3  lea     rdx, word_180113B3E
0x18009d7ba  lea     rax, [rbp+arg_18]
0x18009d7be  xor     r9d, r9d
0x18009d7c1  mov     [rsp+68h+lpcbData], rax
0x18009d7c6  lea     rcx, dword_180128170
0x18009d7cd  lea     rax, [rbp+var_28]
0x18009d7d1  xor     r8d, r8d
0x18009d7d4  mov     [rsp+68h+phkResult], rax
0x18009d7d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009d7de  test    ebx, ebx
0x18009d7e0  jle     loc_18009D8E5
0x18009d7e6  movzx   ebx, bx
0x18009d7e9  or      ebx, 80070000h
0x18009d7ef  jmp     loc_18009D8E5
0x18009d7f4  mov     rcx, [rbp+hKey]; hKey
0x18009d7f8  lea     rax, [rbp+cbData]
0x18009d7fc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18009d801  lea     r15, aTsappcompat; "TSAppCompat"
0x18009d808  lea     rax, [rbp+Data]
0x18009d80c  mov     [rbp+cbData], 4
0x18009d813  xor     ebx, ebx
0x18009d815  mov     [rsp+68h+phkResult], rax; lpData
0x18009d81a  lea     r9, [rbp+Type]; lpType
0x18009d81e  mov     [rbp+Type], ebx
0x18009d821  xor     r8d, r8d; lpReserved
0x18009d824  mov     [rbp+Data], ebx
0x18009d827  mov     rdx, r15; lpValueName
0x18009d82a  call    cs:__imp_RegQueryValueExW
0x18009d830  mov     ecx, eax
0x18009d832  test    eax, eax
0x18009d834  jnz     short loc_18009D893
0x18009d836  cmp     [rbp+cbData], 4
0x18009d83a  jnz     short loc_18009D893
0x18009d83c  cmp     [rbp+Type], 4
0x18009d840  jnz     short loc_18009D893
0x18009d842  mov     eax, [rbp+Data]
0x18009d845  mov     [rdi], eax
0x18009d847  mov     eax, cs:dword_180128170
0x18009d84d  cmp     eax, 4
0x18009d850  jbe     loc_18009D8E5
0x18009d856  mov     eax, [rdi]
0x18009d858  lea     rdx, word_180113B66
0x18009d85f  mov     [rbp+arg_18], eax
0x18009d862  lea     rcx, dword_180128170
0x18009d869  lea     rax, aSuccessfullyRe_0; "Successfully read APPCOMPAT key"
0x18009d870  xor     r9d, r9d
0x18009d873  mov     [rbp+var_28], rax
0x18009d877  xor     r8d, r8d
0x18009d87a  lea     rax, [rbp+arg_18]
0x18009d87e  mov     [rsp+68h+lpcbData], rax
0x18009d883  lea     rax, [rbp+var_28]
0x18009d887  mov     [rsp+68h+phkResult], rax
0x18009d88c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009d891  jmp     short loc_18009D8E5
0x18009d893  mov     eax, cs:dword_180128170
0x18009d899  cmp     eax, 4
0x18009d89c  jbe     short loc_18009D8E5
0x18009d89e  mov     eax, [rdi]
0x18009d8a0  lea     rdx, word_180113B92
0x18009d8a7  mov     [rbp+arg_18], eax
0x18009d8aa  lea     rax, aUnableToReadAp; "Unable to read APPCOMPAT key"
0x18009d8b1  mov     [rbp+var_10], rax
0x18009d8b5  lea     rax, [rbp+var_18]
0x18009d8b9  mov     [rsp+68h+var_30], rax
0x18009d8be  lea     rax, [rbp+arg_18]
0x18009d8c2  mov     [rsp+68h+var_38], rax
0x18009d8c7  lea     rax, [rbp+var_28]
0x18009d8cb  mov     [rsp+68h+lpcbData], rax
0x18009d8d0  lea     rax, [rbp+var_10]
0x18009d8d4  mov     [rsp+68h+phkResult], rax
0x18009d8d9  mov     [rbp+var_18], r15
0x18009d8dd  mov     dword ptr [rbp+var_28], ecx
0x18009d8e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009d8e5  mov     rcx, [rbp+hKey]; hKey
0x18009d8e9  test    rcx, rcx
0x18009d8ec  jz      short loc_18009D8F4
0x18009d8ee  call    cs:__imp_RegCloseKey
0x18009d8f4  mov     eax, ebx
0x18009d8f6  add     rsp, 68h
0x18009d8fa  pop     r15
0x18009d8fc  pop     rdi
0x18009d8fd  pop     rbx
0x18009d8fe  pop     rbp
0x18009d8ff  retn
```
