# FederatedInstallJob::StaticFederationWorker(void *)

- ea: `0x180017c90`
- end: `0x180017e1f`
- name: `?StaticFederationWorker@FederatedInstallJob@@CAKPEAX@Z`
- size: `399`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180016dbc`
- `0x180017c90`
- `0x180017e28`
- `0x1800181a0`
- `0x180090bc8`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017d24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017d24`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017cde`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017d85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017cde`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d46`

## string_xrefs

- `0x180017cc1`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`
- `0x180017cff`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`
- `0x180017d6c`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`
- `0x180017dfc`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`
- `0x180017d9f`: `* END *   Federated Install encountered unrecoverable error, hr=0x%08lX (cV = %hs)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FederatedInstallJob::StaticFederationWorker(HANDLE *Parameter, unsigned int a2, bool a3)
{
  int v4; // eax
  signed int v5; // edi
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int MemberOperation; // eax
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-28h]
  signed int v15; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v17; // [rsp+50h] [rbp+8h] BYREF

  v17 = 0;
  v4 = CCoInit::Initialize((CCoInit *)&v17, a2, a3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 300;
    goto LABEL_3;
  }
  MemberOperation = FederatedInstallJob::BeginNextMemberOperation((FederatedInstallJob *)Parameter);
  v5 = MemberOperation;
  if ( MemberOperation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedInstallJob.cpp",
      (const char *)(unsigned int)MemberOperation,
      v14);
    v6 = (unsigned int)v5;
    v7 = 302;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedInstallJob.cpp",
      (const char *)v6,
      v14);
    if ( v17 )
      CoUninitialize();
LABEL_19:
    v15 = v5;
    WUTrace(
      0,
      0,
      0x10000,
      1,
      0,
      L"* END *   Federated Install encountered unrecoverable error, hr=0x%08lX (cV = %hs)",
      v15,
      Parameter[53]);
    (*((void (__fastcall **)(char *, __int64, _QWORD))Parameter[5] + 1))((char *)Parameter + 40, 6, (unsigned int)v5);
    goto LABEL_20;
  }
  if ( WaitForSingleObject(Parameter[100], 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    if ( v5 >= 0 )
      v5 = -2147418113;
    v10 = (unsigned int)v5;
    v11 = 312;
  }
  else
  {
    v9 = FederatedInstallJob::EndFederatedOperation((FederatedInstallJob *)Parameter);
    v5 = v9;
    if ( v9 >= 0 )
      goto LABEL_16;
    v10 = (unsigned int)v9;
    v11 = 308;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedInstallJob.cpp",
    (const char *)v10,
    v14);
LABEL_16:
  if ( v17 )
    CoUninitialize();
  if ( v5 < 0 )
    goto LABEL_19;
LABEL_20:
  (*((void (__fastcall **)(char *))Parameter[1] + 2))((char *)Parameter + 8);
  if ( v5 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedInstallJob.cpp",
      (const char *)(unsigned int)v5,
      v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017c90  mov     rax, rsp
0x180017c93  mov     [rax+10h], rbx
0x180017c97  mov     [rax+18h], rsi
0x180017c9b  push    rdi
0x180017c9c  sub     rsp, 40h
0x180017ca0  mov     rsi, rcx
0x180017ca3  mov     dword ptr [rax+8], 0
0x180017caa  lea     rcx, [rax+8]; this
0x180017cae  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x180017cb3  mov     edi, eax
0x180017cb5  test    eax, eax
0x180017cb7  jns     short loc_180017CE9
0x180017cb9  mov     r9d, eax; char *
0x180017cbc  mov     edx, 12Ch; void *
0x180017cc1  lea     r8, aCW1SSrcClientC_37; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180017cc8  mov     rcx, [rsp+48h]; this
0x180017ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cd2  nop
0x180017cd3  cmp     [rsp+48h+arg_0], 0
0x180017cd8  jz      loc_180017D8F
0x180017cde  call    cs:__imp_CoUninitialize
0x180017ce4  jmp     loc_180017D8F
0x180017ce9  mov     rcx, rsi; this
0x180017cec  call    ?BeginNextMemberOperation@FederatedInstallJob@@AEAAJXZ; FederatedInstallJob::BeginNextMemberOperation(void)
0x180017cf1  mov     edi, eax
0x180017cf3  test    eax, eax
0x180017cf5  jns     short loc_180017D1A
0x180017cf7  mov     rcx, [rsp+48h]; this
0x180017cfc  mov     r9d, eax; char *
0x180017cff  lea     r8, aCW1SSrcClientC_37; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180017d06  mov     edx, 145h; void *
0x180017d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d10  mov     r9d, edi
0x180017d13  mov     edx, 12Eh
0x180017d18  jmp     short loc_180017CC1
0x180017d1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017d1d  mov     rcx, [rsi+320h]; hHandle
0x180017d24  call    cs:__imp_WaitForSingleObject
0x180017d2a  test    eax, eax
0x180017d2c  jnz     short loc_180017D46
0x180017d2e  mov     rcx, rsi; this
0x180017d31  call    ?EndFederatedOperation@FederatedInstallJob@@AEAAJXZ; FederatedInstallJob::EndFederatedOperation(void)
0x180017d36  mov     edi, eax
0x180017d38  test    eax, eax
0x180017d3a  jns     short loc_180017D7E
0x180017d3c  mov     r9d, eax
0x180017d3f  mov     edx, 134h
0x180017d44  jmp     short loc_180017D6C
0x180017d46  call    cs:__imp_GetLastError
0x180017d4c  movzx   edi, ax
0x180017d4f  or      edi, 80070000h
0x180017d55  test    eax, eax
0x180017d57  cmovle  edi, eax
0x180017d5a  mov     eax, 8000FFFFh
0x180017d5f  test    edi, edi
0x180017d61  cmovns  edi, eax
0x180017d64  mov     r9d, edi; char *
0x180017d67  mov     edx, 138h; void *
0x180017d6c  lea     r8, aCW1SSrcClientC_37; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180017d73  mov     rcx, [rsp+48h]; this
0x180017d78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d7d  nop
0x180017d7e  cmp     [rsp+48h+arg_0], 0
0x180017d83  jz      short loc_180017D8B
0x180017d85  call    cs:__imp_CoUninitialize
0x180017d8b  test    edi, edi
0x180017d8d  jns     short loc_180017DE0
0x180017d8f  mov     rax, [rsi+1A8h]
0x180017d96  mov     [rsp+48h+var_10], rax
0x180017d9b  mov     [rsp+48h+var_18], edi
0x180017d9f  lea     rax, aEndFederatedIn_0; "* END *   Federated Install encountered"...
0x180017da6  mov     [rsp+48h+var_20], rax
0x180017dab  mov     qword ptr [rsp+48h+var_28], 0; int
0x180017db4  xor     edx, edx
0x180017db6  xor     ecx, ecx
0x180017db8  lea     r9d, [rdx+1]
0x180017dbc  mov     r8d, 10000h
0x180017dc2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180017dc7  mov     rax, [rsi+28h]
0x180017dcb  mov     r8d, edi
0x180017dce  mov     edx, 6
0x180017dd3  lea     rcx, [rsi+28h]
0x180017dd7  mov     rax, [rax+8]
0x180017ddb  call    _guard_dispatch_icall
0x180017de0  lea     rcx, [rsi+8]
0x180017de4  mov     rax, [rcx]
0x180017de7  mov     rax, [rax+10h]
0x180017deb  call    _guard_dispatch_icall
0x180017df0  test    edi, edi
0x180017df2  jns     short loc_180017E0D
0x180017df4  mov     rcx, [rsp+48h]; this
0x180017df9  mov     r9d, edi; char *
0x180017dfc  lea     r8, aCW1SSrcClientC_37; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180017e03  mov     edx, 125h; void *
0x180017e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e0d  mov     eax, edi
0x180017e0f  mov     rbx, [rsp+48h+arg_8]
0x180017e14  mov     rsi, [rsp+48h+arg_10]
0x180017e19  add     rsp, 40h
0x180017e1d  pop     rdi
0x180017e1e  retn
```
