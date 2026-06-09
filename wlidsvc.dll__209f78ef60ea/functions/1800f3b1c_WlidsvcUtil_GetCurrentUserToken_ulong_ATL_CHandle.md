# WlidsvcUtil::GetCurrentUserToken(ulong,ATL::CHandle &)

- ea: `0x1800f3b1c`
- end: `0x1800f3c4f`
- name: `?GetCurrentUserToken@WlidsvcUtil@@SAJKAEAVCHandle@ATL@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ad50`
- `0x180069ca0`
- `0x1800f3db8`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800f3b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3bf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f3be6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f3be6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f3bd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f3bd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f3b89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f3b89`

## string_xrefs

- `0x1800f3b63`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f3bc5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f3c1f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f3bb0`: `OpenThreadToken failed with hr = 0x%x`
- `0x1800f3b2d`: `WlidsvcUtil::GetCurrentUserToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WlidsvcUtil::GetCurrentUserToken(DWORD DesiredAccess, PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  char *v10; // [rsp+20h] [rbp-38h]
  char *v11; // [rsp+20h] [rbp-38h]
  _QWORD v12[5]; // [rsp+30h] [rbp-28h] BYREF
  signed int v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = 0;
  v12[0] = "WlidsvcUtil::GetCurrentUserToken";
  v12[2] = 0;
  v12[3] = 0;
  v12[1] = &v13;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
    "WlidsvcUtil::GetCurrentUserToken",
    (const char *)0x1DC,
    0,
    (const unsigned __int16 *)v10);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, DesiredAccess, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, DesiredAccess, TokenHandle) )
      {
        v7 = GetLastError();
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        v13 = v7;
        if ( v7 < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
            "WlidsvcUtil::GetCurrentUserToken",
            0x1EAu,
            v7,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
      }
    }
    else
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError;
      LODWORD(v11) = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
        0x1E6u,
        L"OpenThreadToken failed with hr = 0x%x",
        v11);
    }
  }
  v8 = v13;
  CTraceFuncW<long>::~CTraceFuncW<long>(v12);
  return v8;
}

```

## disassembly

```asm
0x1800f3b1c  mov     r11, rsp
0x1800f3b1f  mov     [r11+8], rbx
0x1800f3b23  mov     [r11+18h], rdi
0x1800f3b27  push    r14
0x1800f3b29  sub     rsp, 50h
0x1800f3b2d  lea     r14, aWlidsvcutilGet_0; "WlidsvcUtil::GetCurrentUserToken"
0x1800f3b34  mov     [rsp+58h+arg_8], 0
0x1800f3b3c  mov     rbx, rdx
0x1800f3b3f  mov     [r11-28h], r14
0x1800f3b43  mov     edi, ecx
0x1800f3b45  mov     qword ptr [r11-18h], 0
0x1800f3b4d  lea     rax, [r11+10h]
0x1800f3b51  mov     qword ptr [r11-10h], 0
0x1800f3b59  mov     rdx, r14; char *
0x1800f3b5c  mov     [r11-20h], rax
0x1800f3b60  xor     r9d, r9d; unsigned int
0x1800f3b63  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f3b6a  mov     r8d, 1DCh; char *
0x1800f3b70  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800f3b75  call    cs:__imp_GetCurrentThread
0x1800f3b7b  mov     r9, rbx; TokenHandle
0x1800f3b7e  mov     r8d, 1; OpenAsSelf
0x1800f3b84  mov     rcx, rax; ThreadHandle
0x1800f3b87  mov     edx, edi; DesiredAccess
0x1800f3b89  call    cs:__imp_OpenThreadToken
0x1800f3b8f  test    eax, eax
0x1800f3b91  jnz     loc_1800F3C2E
0x1800f3b97  call    cs:__imp_GetLastError
0x1800f3b9d  cmp     eax, 3F0h
0x1800f3ba2  jz      short loc_1800F3BD8
0x1800f3ba4  test    eax, eax
0x1800f3ba6  jle     short loc_1800F3BB0
0x1800f3ba8  movzx   eax, ax
0x1800f3bab  or      eax, 80070000h
0x1800f3bb0  lea     r9, aOpenthreadtoke_0; "OpenThreadToken failed with hr = 0x%x"
0x1800f3bb7  mov     [rsp+58h+arg_8], eax
0x1800f3bbb  mov     r8d, 1E6h; unsigned int
0x1800f3bc1  mov     dword ptr [rsp+58h+var_38], eax
0x1800f3bc5  lea     rdx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f3bcc  mov     ecx, 2; unsigned __int8
0x1800f3bd1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800f3bd6  jmp     short loc_1800F3C2E
0x1800f3bd8  call    cs:__imp_GetCurrentProcess
0x1800f3bde  mov     r8, rbx; TokenHandle
0x1800f3be1  mov     edx, edi; DesiredAccess
0x1800f3be3  mov     rcx, rax; ProcessHandle
0x1800f3be6  call    cs:__imp_OpenProcessToken
0x1800f3bec  test    eax, eax
0x1800f3bee  jnz     short loc_1800F3C2E
0x1800f3bf0  call    cs:__imp_GetLastError
0x1800f3bf6  test    eax, eax
0x1800f3bf8  jle     short loc_1800F3C02
0x1800f3bfa  movzx   eax, ax
0x1800f3bfd  or      eax, 80070000h
0x1800f3c02  mov     [rsp+58h+arg_8], eax
0x1800f3c06  test    eax, eax
0x1800f3c08  jns     short loc_1800F3C2E
0x1800f3c0a  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800f3c11  mov     r9d, eax; int
0x1800f3c14  mov     [rsp+58h+var_38], rcx; char *
0x1800f3c19  mov     r8d, 1EAh; unsigned int
0x1800f3c1f  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f3c26  mov     rdx, r14; char *
0x1800f3c29  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f3c2e  mov     ebx, [rsp+58h+arg_8]
0x1800f3c32  lea     rcx, [rsp+58h+var_28]
0x1800f3c37  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800f3c3c  mov     rdi, [rsp+58h+arg_10]
0x1800f3c41  mov     eax, ebx
0x1800f3c43  mov     rbx, [rsp+58h+arg_0]
0x1800f3c48  add     rsp, 50h
0x1800f3c4c  pop     r14
0x1800f3c4e  retn
```
