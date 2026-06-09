# StartProvider(TimeProvider *)

- ea: `0x18001b850`
- end: `0x18001bb45`
- name: `?StartProvider@@YAJPEAUTimeProvider@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct TimeProvider *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a9b0`
- `0x180032ff0`

## callees

- `0x18000a7e0`
- `0x180018138`
- `0x18001a780`
- `0x18001b850`
- `0x18001d9a0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b8bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b8bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b9f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b9f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b8f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b939`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b8f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b939`
- `ntdll!RtlInitUnicodeString` at `0x18001b9a5`
- `ntdll!RtlInitUnicodeString` at `0x18001baea`
- `ntdll!RtlInitUnicodeString` at `0x18001b9a5`
- `ntdll!RtlInitUnicodeString` at `0x18001baea`

## string_xrefs

- `0x18001b90e`: `TimeProvCommand`
- `0x18001b932`: `TimeProvOpen`
- `0x18001ba6e`: `Starting '%s', dll:'%s'\n`
- `0x18001ba83`: `LoadLibrary\n`

## pseudocode

```c
__int64 __fastcall StartProvider(struct TimeProvider *a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  signed int LastError; // eax
  signed int v7; // edi
  const WCHAR *v8; // rdx
  HMODULE v9; // rcx
  int SystemErrorString; // eax
  HLOCAL v12; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v15[7]; // [rsp+50h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+8h] BYREF

  v15[0] = 40;
  v15[1] = MyGetTimeSysInfo;
  v15[2] = MyLogTimeProvEvent;
  v15[3] = MyAlertSamplesAvail;
  v15[4] = MySetProviderStatus;
  if ( (unsigned __int8)FileLogAllowEntry(61) )
    FileLogAdd(L"Starting '%s', dll:'%s'\n", *((_QWORD *)a1 + 1), *(_QWORD *)a1);
  Library = LoadLibraryExW(*(LPCWSTR *)a1, 0, 0);
  *((_QWORD *)a1 + 4) = Library;
  if ( !Library )
    goto LABEL_9;
  if ( (unsigned __int8)FileLogAllowEntry(9) )
    FileLogAdd(L"LoadLibrary\n");
  ProcAddress = GetProcAddress(*((HMODULE *)a1 + 4), "TimeProvClose");
  *((_QWORD *)a1 + 7) = ProcAddress;
  if ( !ProcAddress || (v4 = GetProcAddress(*((HMODULE *)a1 + 4), "TimeProvCommand"), (*((_QWORD *)a1 + 6) = v4) == 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError <= 0 )
    {
LABEL_11:
      if ( v7 >= 0 )
        return (unsigned int)v7;
LABEL_14:
      v8 = (const WCHAR *)*((_QWORD *)a1 + 1);
      hMem = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v8);
      if ( v7 == -2147024846 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(61) )
          FileLogAdd(
            L"Logging Info: Time provider '%s' indicated that the current operating environment is unsupported and has sto"
             "pped. This is expected for VMIC provider in non-Hyperv environments. This may be the expected behavior for "
             "the current provider in the current operating environment as well. error:%d\n",
            *((_QWORD *)a1 + 1),
            2147942450LL);
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_INDICATED_UNSUPPORTED, L"u", &DestinationString);
      }
      else
      {
        SystemErrorString = GetSystemErrorString(v7, (unsigned __int16 **)&hMem);
        v12 = hMem;
        if ( SystemErrorString >= 0 )
        {
          v14 = 0;
          RtlInitUnicodeString(&v14, (PCWSTR)hMem);
          if ( (unsigned __int8)FileLogAllowEntry(9) )
            FileLogAdd(
              L"Logging error: Time provider '%s' failed to start due to the following error: %s\n",
              *((_QWORD *)a1 + 1),
              v12);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_START, L"uu", &DestinationString);
        }
        if ( v12 )
          LocalFree(v12);
      }
      v9 = (HMODULE)*((_QWORD *)a1 + 4);
      if ( v9 )
        FreeLibrary(v9);
      return (unsigned int)v7;
    }
LABEL_10:
    v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_11;
  }
  v5 = GetProcAddress(*((HMODULE *)a1 + 4), "TimeProvOpen");
  if ( !v5 )
  {
LABEL_9:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError <= 0 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD *, char *))v5)(*((_QWORD *)a1 + 1), v15, (char *)a1 + 40);
  if ( v7 < 0 )
    goto LABEL_14;
  *((_BYTE *)a1 + 18) = 1;
  if ( (unsigned __int8)FileLogAllowEntry(61) )
    FileLogAdd(L"Logging Info: Time provider '%s' has started successfully\n", *((_QWORD *)a1 + 1));
  return 0;
}

```

## disassembly

```asm
0x18001b850  push    rbx
0x18001b852  sub     rsp, 80h
0x18001b859  lea     rax, ?MyGetTimeSysInfo@@YAJW4TimeSysInfo@@PEAX@Z; MyGetTimeSysInfo(TimeSysInfo,void *)
0x18001b860  mov     [rsp+88h+var_38], 28h ; '('
0x18001b869  mov     [rsp+88h+var_30], rax
0x18001b86e  mov     rbx, rcx
0x18001b871  lea     rax, ?MyLogTimeProvEvent@@YAJGPEAG0@Z; MyLogTimeProvEvent(ushort,ushort *,ushort *)
0x18001b878  mov     ecx, 3Dh ; '='
0x18001b87d  mov     [rsp+88h+var_28], rax
0x18001b882  lea     rax, ?MyAlertSamplesAvail@@YAJXZ; MyAlertSamplesAvail(void)
0x18001b889  mov     [rsp+88h+var_20], rax
0x18001b88e  lea     rax, ?MySetProviderStatus@@YAJPEAUSetProviderStatusInfo@@@Z; MySetProviderStatus(SetProviderStatusInfo *)
0x18001b895  mov     [rsp+88h+var_18], rax
0x18001b89a  call    FileLogAllowEntry
0x18001b89f  test    al, al
0x18001b8a1  jnz     loc_18001BA6B
0x18001b8a7  mov     rcx, [rbx]; lpLibFileName
0x18001b8aa  xor     r8d, r8d; dwFlags
0x18001b8ad  mov     [rsp+88h+arg_8], rsi
0x18001b8b5  xor     edx, edx; hFile
0x18001b8b7  mov     [rsp+88h+arg_10], rdi
0x18001b8bf  call    cs:__imp_LoadLibraryExW
0x18001b8c6  nop     dword ptr [rax+rax+00h]
0x18001b8cb  mov     [rbx+20h], rax
0x18001b8cf  test    rax, rax
0x18001b8d2  jz      short loc_18001B94A
0x18001b8d4  mov     ecx, 9
0x18001b8d9  call    FileLogAllowEntry
0x18001b8de  test    al, al
0x18001b8e0  jnz     loc_18001BA83
0x18001b8e6  mov     rcx, [rbx+20h]; hModule
0x18001b8ea  lea     rdx, ProcName; "TimeProvClose"
0x18001b8f1  call    cs:__imp_GetProcAddress
0x18001b8f8  nop     dword ptr [rax+rax+00h]
0x18001b8fd  mov     [rbx+38h], rax
0x18001b901  test    rax, rax
0x18001b904  jz      loc_18001BA50
0x18001b90a  mov     rcx, [rbx+20h]; hModule
0x18001b90e  lea     rdx, aTimeprovcomman_0; "TimeProvCommand"
0x18001b915  call    cs:__imp_GetProcAddress
0x18001b91c  nop     dword ptr [rax+rax+00h]
0x18001b921  mov     [rbx+30h], rax
0x18001b925  test    rax, rax
0x18001b928  jz      loc_18001BA50
0x18001b92e  mov     rcx, [rbx+20h]; hModule
0x18001b932  lea     rdx, aTimeprovopen_0; "TimeProvOpen"
0x18001b939  call    cs:__imp_GetProcAddress
0x18001b940  nop     dword ptr [rax+rax+00h]
0x18001b945  test    rax, rax
0x18001b948  jnz     short loc_18001B96E
0x18001b94a  call    cs:__imp_GetLastError
0x18001b951  nop     dword ptr [rax+rax+00h]
0x18001b956  mov     edi, eax
0x18001b958  test    eax, eax
0x18001b95a  jle     short loc_18001B965
0x18001b95c  movzx   edi, ax
0x18001b95f  or      edi, 80070000h
0x18001b965  test    edi, edi
0x18001b967  js      short loc_18001B98A
0x18001b969  jmp     loc_18001B9FF
0x18001b96e  mov     rcx, [rbx+8]
0x18001b972  lea     r8, [rbx+28h]
0x18001b976  lea     rdx, [rsp+88h+var_38]
0x18001b97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b980  mov     edi, eax
0x18001b982  test    eax, eax
0x18001b984  jns     loc_18001BA94
0x18001b98a  mov     rdx, [rbx+8]; SourceString
0x18001b98e  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18001b993  xorps   xmm0, xmm0
0x18001b996  xor     esi, esi
0x18001b998  mov     [rsp+88h+hMem], rsi
0x18001b9a0  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18001b9a5  call    cs:__imp_RtlInitUnicodeString
0x18001b9ac  nop     dword ptr [rax+rax+00h]
0x18001b9b1  cmp     edi, 80070032h
0x18001b9b7  jnz     short loc_18001BA1B
0x18001b9b9  mov     ecx, 3Dh ; '='
0x18001b9be  call    FileLogAllowEntry
0x18001b9c3  test    al, al
0x18001b9c5  jnz     loc_18001BABF
0x18001b9cb  lea     r9, [rsp+88h+DestinationString]
0x18001b9d0  lea     r8, aU; "u"
0x18001b9d7  lea     rdx, W32TIME_EVENT_TIMEPROV_INDICATED_UNSUPPORTED
0x18001b9de  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18001b9e5  call    LogEvent
0x18001b9ea  mov     rcx, [rbx+20h]; hLibModule
0x18001b9ee  test    rcx, rcx
0x18001b9f1  jz      short loc_18001B9FF
0x18001b9f3  call    cs:__imp_FreeLibrary
0x18001b9fa  nop     dword ptr [rax+rax+00h]
0x18001b9ff  mov     eax, edi
0x18001ba01  mov     rdi, [rsp+88h+arg_10]
0x18001ba09  mov     rsi, [rsp+88h+arg_8]
0x18001ba11  add     rsp, 80h
0x18001ba18  pop     rbx
0x18001ba19  retn
0x18001ba1b  lea     rdx, [rsp+88h+hMem]; unsigned __int16 **
0x18001ba23  mov     ecx, edi; dwMessageId
0x18001ba25  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x18001ba2a  mov     rsi, [rsp+88h+hMem]
0x18001ba32  test    eax, eax
0x18001ba34  jns     loc_18001BADA
0x18001ba3a  test    rsi, rsi
0x18001ba3d  jz      short loc_18001B9EA
0x18001ba3f  mov     rcx, rsi; hMem
0x18001ba42  call    cs:__imp_LocalFree
0x18001ba49  nop     dword ptr [rax+rax+00h]
0x18001ba4e  jmp     short loc_18001B9EA
0x18001ba50  call    cs:__imp_GetLastError
0x18001ba57  nop     dword ptr [rax+rax+00h]
0x18001ba5c  mov     edi, eax
0x18001ba5e  test    eax, eax
0x18001ba60  jle     loc_18001B965
0x18001ba66  jmp     loc_18001B95C
0x18001ba6b  mov     r8, [rbx]
0x18001ba6e  lea     rcx, aStartingSDllS; "Starting '%s', dll:'%s'\n"
0x18001ba75  mov     rdx, [rbx+8]
0x18001ba79  call    FileLogAdd
0x18001ba7e  jmp     loc_18001B8A7
0x18001ba83  lea     rcx, aLoadlibrary; "LoadLibrary\n"
0x18001ba8a  call    FileLogAdd
0x18001ba8f  jmp     loc_18001B8E6
0x18001ba94  mov     ecx, 3Dh ; '='
0x18001ba99  mov     byte ptr [rbx+12h], 1
0x18001ba9d  xor     esi, esi
0x18001ba9f  call    FileLogAllowEntry
0x18001baa4  test    al, al
0x18001baa6  jz      short loc_18001BAB8
0x18001baa8  mov     rdx, [rbx+8]
0x18001baac  lea     rcx, aLoggingInfoTim; "Logging Info: Time provider '%s' has st"...
0x18001bab3  call    FileLogAdd
0x18001bab8  mov     eax, esi
0x18001baba  jmp     loc_18001BA01
0x18001babf  mov     rdx, [rbx+8]
0x18001bac3  lea     rcx, aLoggingInfoTim_0; "Logging Info: Time provider '%s' indica"...
0x18001baca  mov     r8d, 80070032h
0x18001bad0  call    FileLogAdd
0x18001bad5  jmp     loc_18001B9CB
0x18001bada  xorps   xmm0, xmm0
0x18001badd  lea     rcx, [rsp+88h+var_48]; DestinationString
0x18001bae2  mov     rdx, rsi; SourceString
0x18001bae5  movups  xmmword ptr [rsp+88h+var_48.Length], xmm0
0x18001baea  call    cs:__imp_RtlInitUnicodeString
0x18001baf1  nop     dword ptr [rax+rax+00h]
0x18001baf6  mov     ecx, 9
0x18001bafb  call    FileLogAllowEntry
0x18001bb00  test    al, al
0x18001bb02  jz      short loc_18001BB17
0x18001bb04  mov     rdx, [rbx+8]
0x18001bb08  lea     rcx, aLoggingErrorTi; "Logging error: Time provider '%s' faile"...
0x18001bb0f  mov     r8, rsi
0x18001bb12  call    FileLogAdd
0x18001bb17  lea     rax, [rsp+88h+var_48]
0x18001bb1c  lea     r9, [rsp+88h+DestinationString]
0x18001bb21  mov     [rsp+88h+var_68], rax
0x18001bb26  lea     r8, aUu; "uu"
0x18001bb2d  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_START
0x18001bb34  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18001bb3b  call    LogEvent
0x18001bb40  jmp     loc_18001BA3A
```
