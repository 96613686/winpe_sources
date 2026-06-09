# DisableTimeZoneAutoUpdate

- ea: `0x18000bc30`
- end: `0x18000bf13`
- name: `DisableTimeZoneAutoUpdate`
- size: `739`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000bf20`

## callees

- `0x1800011e4`
- `0x180001384`
- `0x18000166c`
- `0x1800045d4`
- `0x18000883c`
- `0x18000885c`
- `0x18000bc30`
- `0x180016d18`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bddf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000bc5f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000bc5f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000bc98`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000bc98`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000bd12`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000bd12`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000bd69`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000bdd1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000bd69`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000bdd1`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000bdbf`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000bdbf`

## string_xrefs

- `0x18000bc8e`: `tzautoupdate`
- `0x18000bc72`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000bcb1`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000bd39`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000bead`: `tzautoupdate disabled via API.`
- `0x18000be50`: `tzautoupdate failed to disable.`

## pseudocode

```c
__int64 DisableTimeZoneAutoUpdate()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  signed int LastError; // edi
  SC_HANDLE v3; // rax
  const char *v4; // r9
  SC_HANDLE v5; // rbx
  __int64 v6; // rdx
  int updated; // eax
  __int64 dwCurrentState; // rcx
  __int64 v9; // r8
  DWORD v10; // eax
  signed int v11; // edx
  bool v12; // zf
  DWORD v13; // eax
  DWORD v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int lpBinaryPathName; // [rsp+20h] [rbp-39h]
  SC_HANDLE v23; // [rsp+60h] [rbp+7h] BYREF
  signed int v24; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+70h] [rbp+17h] BYREF
  __int64 v26; // [rsp+78h] [rbp+1Fh] BYREF
  SC_HANDLE v27; // [rsp+80h] [rbp+27h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v27 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"tzautoupdate", 0xF01FFu);
    v23 = v3;
    v5 = v3;
    if ( !v3 )
    {
      v6 = 122;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v6,
                    (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                    v4);
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v23);
      goto LABEL_36;
    }
    if ( !ChangeServiceConfigW(v3, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v6 = 135;
      goto LABEL_5;
    }
    updated = UpdateTimeZoneCache((const BYTE *)&qword_180021DC8);
    LastError = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
        (const char *)(unsigned int)updated,
        lpBinaryPathName);
      goto LABEL_35;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    LastError = 0;
    if ( ControlService(v5, 1u, &ServiceStatus) )
    {
LABEL_32:
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(dwCurrentState, 0x400000000000LL, v9) )
      {
        v25 = 0x1000000;
        v26 = (__int64)L"tzautoupdate disabled via API.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v18,
          (unsigned int)&dword_1800280EC,
          v19,
          v20,
          (__int64)&v25,
          (__int64)&v26);
      }
      goto LABEL_35;
    }
    v10 = GetLastError();
    v11 = v10;
    if ( v10 )
    {
      if ( v10 != 1052 )
      {
        dwCurrentState = v10 - 1061;
        if ( (unsigned int)dwCurrentState > 1 )
          goto LABEL_14;
      }
    }
    dwCurrentState = ServiceStatus.dwCurrentState;
    if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) != 0 )
    {
      v13 = ServiceStatus.dwCurrentState - 1;
    }
    else
    {
      WaitServiceState(v5, 8, 1000);
      if ( ControlService(v5, 1u, &ServiceStatus) )
        goto LABEL_32;
      v14 = GetLastError();
      v11 = v14;
      if ( v14 )
      {
        if ( v14 != 1052 )
        {
          dwCurrentState = v14 - 1061;
          if ( (unsigned int)dwCurrentState > 1 )
          {
LABEL_14:
            v12 = v11 == 1115;
LABEL_24:
            if ( !v12 )
            {
              LastError = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
              if ( LastError < 0 )
              {
                if ( (unsigned int)dword_180030000 > 5
                  && (unsigned __int8)tlgKeywordOn(dwCurrentState, 0x400000000000LL, v9) )
                {
                  v24 = LastError;
                  v25 = (__int64)L"tzautoupdate failed to disable.";
                  v26 = 0x1000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    v15,
                    (unsigned int)&unk_1800281D0,
                    v16,
                    v17,
                    (__int64)&v26,
                    (__int64)&v25,
                    (__int64)&v24);
                }
                goto LABEL_35;
              }
            }
            goto LABEL_32;
          }
        }
      }
      v13 = ServiceStatus.dwCurrentState - 1;
    }
    if ( (v13 & 0xFFFFFFFD) == 0 )
      goto LABEL_32;
    v12 = v11 == 1062;
    goto LABEL_24;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x77,
                (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                v1);
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v27);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000bc30  mov     [rsp-8+arg_0], rbx
0x18000bc35  mov     [rsp-8+arg_8], rdi
0x18000bc3a  push    rbp
0x18000bc3b  lea     rbp, [rsp-57h]
0x18000bc40  sub     rsp, 0B0h
0x18000bc47  mov     rax, cs:__security_cookie
0x18000bc4e  xor     rax, rsp
0x18000bc51  mov     [rbp+57h+var_8], rax
0x18000bc55  xor     edx, edx; lpDatabaseName
0x18000bc57  xor     ecx, ecx; lpMachineName
0x18000bc59  mov     r8d, 0F003Fh; dwDesiredAccess
0x18000bc5f  call    cs:__imp_OpenSCManagerW
0x18000bc65  mov     [rbp+57h+var_30], rax
0x18000bc69  test    rax, rax
0x18000bc6c  jnz     short loc_18000BC88
0x18000bc6e  mov     rcx, [rbp+5Fh]; this
0x18000bc72  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000bc79  lea     edx, [rax+77h]; void *
0x18000bc7c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bc81  mov     edi, eax
0x18000bc83  jmp     loc_18000BEE7
0x18000bc88  mov     r8d, 0F01FFh; dwDesiredAccess
0x18000bc8e  lea     rdx, ServiceName; "tzautoupdate"
0x18000bc95  mov     rcx, rax; hSCManager
0x18000bc98  call    cs:__imp_OpenServiceW
0x18000bc9e  mov     [rbp+57h+var_50], rax
0x18000bca2  mov     rbx, rax
0x18000bca5  test    rax, rax
0x18000bca8  jnz     short loc_18000BCC4
0x18000bcaa  lea     edx, [rax+7Ah]; void *
0x18000bcad  mov     rcx, [rbp+5Fh]; this
0x18000bcb1  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000bcb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bcbd  mov     edi, eax
0x18000bcbf  jmp     loc_18000BEDE
0x18000bcc4  mov     [rsp+0B0h+lpDisplayName], 0; lpDisplayName
0x18000bccd  or      edx, 0FFFFFFFFh; dwServiceType
0x18000bcd0  mov     [rsp+0B0h+lpPassword], 0; lpPassword
0x18000bcd9  mov     r9d, edx; dwErrorControl
0x18000bcdc  mov     [rsp+0B0h+lpServiceStartName], 0; lpServiceStartName
0x18000bce5  mov     r8d, 4; dwStartType
0x18000bceb  mov     [rsp+0B0h+lpDependencies], 0; lpDependencies
0x18000bcf4  mov     rcx, rbx; hService
0x18000bcf7  mov     [rsp+0B0h+lpdwTagId], 0; lpdwTagId
0x18000bd00  mov     [rsp+0B0h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18000bd09  mov     [rsp+0B0h+lpBinaryPathName], 0; int
0x18000bd12  call    cs:__imp_ChangeServiceConfigW
0x18000bd18  test    eax, eax
0x18000bd1a  jnz     short loc_18000BD23
0x18000bd1c  mov     edx, 87h
0x18000bd21  jmp     short loc_18000BCAD
0x18000bd23  lea     rcx, qword_180021DC8; unsigned __int16 *
0x18000bd2a  call    ?UpdateTimeZoneCache@@YAJPEBG@Z; UpdateTimeZoneCache(ushort const *)
0x18000bd2f  mov     edi, eax
0x18000bd31  test    eax, eax
0x18000bd33  jns     short loc_18000BD52
0x18000bd35  mov     rcx, [rbp+5Fh]; this
0x18000bd39  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000bd40  mov     r9d, eax; char *
0x18000bd43  mov     edx, 8Bh; void *
0x18000bd48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd4d  jmp     loc_18000BEDE
0x18000bd52  xorps   xmm0, xmm0
0x18000bd55  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18000bd59  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18000bd5d  xor     edi, edi
0x18000bd5f  mov     rcx, rbx; hService
0x18000bd62  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000bd66  lea     edx, [rdi+1]; dwControl
0x18000bd69  call    cs:__imp_ControlService
0x18000bd6f  test    eax, eax
0x18000bd71  jnz     loc_18000BE8F
0x18000bd77  call    cs:__imp_GetLastError
0x18000bd7d  mov     edx, eax
0x18000bd7f  test    eax, eax
0x18000bd81  jz      short loc_18000BD9D
0x18000bd83  cmp     eax, 41Ch
0x18000bd88  jz      short loc_18000BD9D
0x18000bd8a  lea     ecx, [rax-425h]
0x18000bd90  cmp     ecx, 1
0x18000bd93  jbe     short loc_18000BD9D
0x18000bd95  cmp     edx, 45Bh
0x18000bd9b  jmp     short loc_18000BE13
0x18000bd9d  mov     ecx, [rbp+57h+ServiceStatus.dwCurrentState]
0x18000bda0  lea     eax, [rcx-2]
0x18000bda3  test    eax, 0FFFFFFFDh
0x18000bda8  jz      short loc_18000BDAF
0x18000bdaa  lea     eax, [rcx-1]
0x18000bdad  jmp     short loc_18000BE02
0x18000bdaf  xor     r9d, r9d
0x18000bdb2  mov     r8d, 3E8h
0x18000bdb8  mov     rcx, rbx
0x18000bdbb  lea     edx, [r9+8]
0x18000bdbf  call    cs:__imp_WaitServiceState
0x18000bdc5  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18000bdc9  mov     edx, 1; dwControl
0x18000bdce  mov     rcx, rbx; hService
0x18000bdd1  call    cs:__imp_ControlService
0x18000bdd7  test    eax, eax
0x18000bdd9  jnz     loc_18000BE8F
0x18000bddf  call    cs:__imp_GetLastError
0x18000bde5  mov     edx, eax
0x18000bde7  test    eax, eax
0x18000bde9  jz      short loc_18000BDFD
0x18000bdeb  cmp     eax, 41Ch
0x18000bdf0  jz      short loc_18000BDFD
0x18000bdf2  lea     ecx, [rax-425h]
0x18000bdf8  cmp     ecx, 1
0x18000bdfb  ja      short loc_18000BD95
0x18000bdfd  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x18000be00  dec     eax
0x18000be02  test    eax, 0FFFFFFFDh
0x18000be07  jz      loc_18000BE8F
0x18000be0d  cmp     edx, 426h
0x18000be13  jz      short loc_18000BE8F
0x18000be15  test    edx, edx
0x18000be17  jg      short loc_18000BE1D
0x18000be19  mov     edi, edx
0x18000be1b  jmp     short loc_18000BE26
0x18000be1d  movzx   edi, dx
0x18000be20  or      edi, 80070000h
0x18000be26  test    edi, edi
0x18000be28  jns     short loc_18000BE8F
0x18000be2a  mov     eax, cs:dword_180030000
0x18000be30  cmp     eax, 5
0x18000be33  jbe     loc_18000BEDE
0x18000be39  mov     rdx, 400000000000h
0x18000be43  call    _tlgKeywordOn
0x18000be48  test    al, al
0x18000be4a  jz      loc_18000BEDE
0x18000be50  lea     rax, aTzautoupdateFa; "tzautoupdate failed to disable."
0x18000be57  mov     [rbp+57h+var_48], edi
0x18000be5a  mov     [rbp+57h+var_40], rax
0x18000be5e  lea     rdx, unk_1800281D0
0x18000be65  lea     rax, [rbp+57h+var_48]
0x18000be69  mov     [rbp+57h+var_38], 1000000h
0x18000be71  mov     [rsp+0B0h+lpdwTagId], rax
0x18000be76  lea     rax, [rbp+57h+var_40]
0x18000be7a  mov     [rsp+0B0h+lpLoadOrderGroup], rax
0x18000be7f  lea     rax, [rbp+57h+var_38]
0x18000be83  mov     [rsp+0B0h+lpBinaryPathName], rax
0x18000be88  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000be8d  jmp     short loc_18000BEDE
0x18000be8f  mov     eax, cs:dword_180030000
0x18000be95  cmp     eax, 5
0x18000be98  jbe     short loc_18000BEDE
0x18000be9a  mov     rdx, 400000000000h
0x18000bea4  call    _tlgKeywordOn
0x18000bea9  test    al, al
0x18000beab  jz      short loc_18000BEDE
0x18000bead  lea     rax, aTzautoupdateDi; "tzautoupdate disabled via API."
0x18000beb4  mov     [rbp+57h+var_40], 1000000h
0x18000bebc  mov     [rbp+57h+var_38], rax
0x18000bec0  lea     rdx, dword_1800280EC
0x18000bec7  lea     rax, [rbp+57h+var_38]
0x18000becb  mov     [rsp+0B0h+lpLoadOrderGroup], rax
0x18000bed0  lea     rax, [rbp+57h+var_40]
0x18000bed4  mov     [rsp+0B0h+lpBinaryPathName], rax
0x18000bed9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000bede  lea     rcx, [rbp+57h+var_50]
0x18000bee2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000bee7  lea     rcx, [rbp+57h+var_30]
0x18000beeb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000bef0  mov     eax, edi
0x18000bef2  mov     rcx, [rbp+57h+var_8]
0x18000bef6  xor     rcx, rsp; StackCookie
0x18000bef9  call    __security_check_cookie
0x18000befe  lea     r11, [rsp+0B0h+var_s0]
0x18000bf06  mov     rbx, [r11+10h]
0x18000bf0a  mov     rdi, [r11+18h]
0x18000bf0e  mov     rsp, r11
0x18000bf11  pop     rbp
0x18000bf12  retn
```
