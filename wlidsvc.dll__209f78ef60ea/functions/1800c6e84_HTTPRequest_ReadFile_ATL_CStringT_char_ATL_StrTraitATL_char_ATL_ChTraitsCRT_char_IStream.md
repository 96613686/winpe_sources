# HTTPRequest::ReadFile(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *,IStream *)

- ea: `0x1800c6e84`
- end: `0x1800c7047`
- name: `?ReadFile@HTTPRequest@@QEAAJPEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAUIStream@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c4f64`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800a3b60`
- `0x1800c6e84`
- `0x180116bb0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f90`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800c6f4e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800c6f4e`
- `WINHTTP!WinHttpReadData` at `0x1800c6f86`
- `WINHTTP!WinHttpReadData` at `0x1800c6f86`

## string_xrefs

- `0x1800c6efa`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c7004`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c6ec6`: `HTTPRequest::ReadFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HTTPRequest::ReadFile(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // ebx
  signed int LastError; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  char *v10; // [rsp+20h] [rbp-E0h]
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+34h] [rbp-CCh] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buffer[8112]; // [rsp+60h] [rbp-A0h] BYREF

  v11 = 0;
  v14[0] = "HTTPRequest::ReadFile";
  v14[1] = &v11;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    "HTTPRequest::ReadFile",
    (const char *)0xB5A,
    0,
    (const unsigned __int16 *)v10);
  dwNumberOfBytesRead = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    v5 = 1000;
    while ( 1 )
    {
      dwNumberOfBytesAvailable = 0;
      if ( !WinHttpQueryDataAvailable(*(HINTERNET *)(a1 + 16), &dwNumberOfBytesAvailable) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError;
        if ( LastError < 0 )
        {
          v7 = 2919;
          goto LABEL_19;
        }
      }
      if ( !WinHttpReadData(*(HINTERNET *)(a1 + 16), Buffer, 0x1FA1u, &dwNumberOfBytesRead) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError;
        if ( LastError < 0 )
          break;
      }
      if ( dwNumberOfBytesRead )
      {
        if ( (!a3
           || (v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a3 + 32LL))(
                       a3,
                       Buffer,
                       dwNumberOfBytesRead,
                       0)) == 0)
          && --v5 > 0 )
        {
          continue;
        }
      }
      goto LABEL_20;
    }
    v7 = 2921;
LABEL_19:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "HTTPRequest::ReadFile",
      v7,
      LastError,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
  else
  {
    v11 = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "HTTPRequest::ReadFile",
      0xB61u,
      -2147418113,
      "m_hRequest != nullptr");
  }
LABEL_20:
  v8 = v11;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14);
  return v8;
}

```

## disassembly

```asm
0x1800c6e84  mov     [rsp-8+arg_8], rbx
0x1800c6e89  mov     [rsp-8+arg_18], rsi
0x1800c6e8e  push    rbp
0x1800c6e8f  push    rdi
0x1800c6e90  push    r15
0x1800c6e92  lea     rbp, [rsp-1F20h]
0x1800c6e9a  mov     eax, 2020h
0x1800c6e9f  call    _alloca_probe
0x1800c6ea4  sub     rsp, rax
0x1800c6ea7  mov     rax, cs:__security_cookie
0x1800c6eae  xor     rax, rsp
0x1800c6eb1  mov     [rbp+1F30h+var_20], rax
0x1800c6eb8  mov     rsi, r8
0x1800c6ebb  mov     rdi, rcx
0x1800c6ebe  mov     [rsp+2030h+var_2000], 0
0x1800c6ec6  lea     r15, aHttprequestRea; "HTTPRequest::ReadFile"
0x1800c6ecd  mov     [rsp+2030h+var_1FF0], r15
0x1800c6ed2  lea     rax, [rsp+2030h+var_2000]
0x1800c6ed7  mov     [rsp+2030h+var_1FE8], rax
0x1800c6edc  mov     [rsp+2030h+var_1FE0], 0
0x1800c6ee5  mov     [rsp+2030h+var_1FD8], 0
0x1800c6eee  xor     r9d, r9d; unsigned int
0x1800c6ef1  mov     r8d, 0B5Ah; char *
0x1800c6ef7  mov     rdx, r15; char *
0x1800c6efa  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6f01  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800c6f06  nop
0x1800c6f07  mov     [rsp+2030h+dwNumberOfBytesRead], 0
0x1800c6f0f  cmp     qword ptr [rdi+10h], 0
0x1800c6f14  jnz     short loc_1800C6F38
0x1800c6f16  mov     r9d, 8000FFFFh
0x1800c6f1c  mov     [rsp+2030h+var_2000], r9d
0x1800c6f21  lea     rax, aMHrequestNullp; "m_hRequest != nullptr"
0x1800c6f28  mov     [rsp+2030h+var_2010], rax
0x1800c6f2d  mov     r8d, 0B61h
0x1800c6f33  jmp     loc_1800C7001
0x1800c6f38  mov     ebx, 3E8h
0x1800c6f3d  mov     [rsp+2030h+dwNumberOfBytesAvailable], 0
0x1800c6f45  lea     rdx, [rsp+2030h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800c6f4a  mov     rcx, [rdi+10h]; hRequest
0x1800c6f4e  call    cs:__imp_WinHttpQueryDataAvailable
0x1800c6f54  test    eax, eax
0x1800c6f56  jnz     short loc_1800C6F72
0x1800c6f58  call    cs:__imp_GetLastError
0x1800c6f5e  test    eax, eax
0x1800c6f60  jle     short loc_1800C6F6A
0x1800c6f62  movzx   eax, ax
0x1800c6f65  or      eax, 80070000h
0x1800c6f6a  mov     [rsp+2030h+var_2000], eax
0x1800c6f6e  test    eax, eax
0x1800c6f70  js      short loc_1800C6FE4
0x1800c6f72  lea     r9, [rsp+2030h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800c6f77  mov     r8d, 1FA1h; dwNumberOfBytesToRead
0x1800c6f7d  lea     rdx, [rsp+2030h+Buffer]; lpBuffer
0x1800c6f82  mov     rcx, [rdi+10h]; hRequest
0x1800c6f86  call    cs:__imp_WinHttpReadData
0x1800c6f8c  test    eax, eax
0x1800c6f8e  jnz     short loc_1800C6FAA
0x1800c6f90  call    cs:__imp_GetLastError
0x1800c6f96  test    eax, eax
0x1800c6f98  jle     short loc_1800C6FA2
0x1800c6f9a  movzx   eax, ax
0x1800c6f9d  or      eax, 80070000h
0x1800c6fa2  mov     [rsp+2030h+var_2000], eax
0x1800c6fa6  test    eax, eax
0x1800c6fa8  js      short loc_1800C6FEC
0x1800c6faa  mov     r8d, [rsp+2030h+dwNumberOfBytesRead]
0x1800c6faf  test    r8d, r8d
0x1800c6fb2  jz      short loc_1800C7010
0x1800c6fb4  test    rsi, rsi
0x1800c6fb7  jz      short loc_1800C6FD8
0x1800c6fb9  mov     rax, [rsi]
0x1800c6fbc  xor     r9d, r9d
0x1800c6fbf  lea     rdx, [rsp+2030h+Buffer]
0x1800c6fc4  mov     rcx, rsi
0x1800c6fc7  mov     rax, [rax+20h]
0x1800c6fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6fd0  mov     [rsp+2030h+var_2000], eax
0x1800c6fd4  test    eax, eax
0x1800c6fd6  jnz     short loc_1800C7010
0x1800c6fd8  dec     ebx
0x1800c6fda  test    ebx, ebx
0x1800c6fdc  jg      loc_1800C6F3D
0x1800c6fe2  jmp     short loc_1800C7010
0x1800c6fe4  mov     r8d, 0B67h
0x1800c6fea  jmp     short loc_1800C6FF2
0x1800c6fec  mov     r8d, 0B69h; unsigned int
0x1800c6ff2  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c6ff9  mov     r9d, eax; int
0x1800c6ffc  mov     [rsp+2030h+var_2010], rcx; char *
0x1800c7001  mov     rdx, r15; char *
0x1800c7004  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c700b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c7010  mov     ebx, [rsp+2030h+var_2000]
0x1800c7014  lea     rcx, [rsp+2030h+var_1FF0]
0x1800c7019  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c701e  mov     eax, ebx
0x1800c7020  mov     rcx, [rbp+1F30h+var_20]
0x1800c7027  xor     rcx, rsp; StackCookie
0x1800c702a  call    __security_check_cookie
0x1800c702f  lea     r11, [rsp+2030h+var_10]
0x1800c7037  mov     rbx, [r11+28h]
0x1800c703b  mov     rsi, [r11+38h]
0x1800c703f  mov     rsp, r11
0x1800c7042  pop     r15
0x1800c7044  pop     rdi
0x1800c7045  pop     rbp
0x1800c7046  retn
```
