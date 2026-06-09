# HandleIsKiosk(int *)

- ea: `0x18009b1f0`
- end: `0x18009b3ad`
- name: `?HandleIsKiosk@@YAJPEAH@Z`
- size: `445`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009b110`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001f968`
- `0x180022f38`
- `0x180043344`
- `0x18009b1f0`
- `0x1800f6178`
- `0x1800f6278`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b367`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b367`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b295`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b2ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b2ab`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009b2fa`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009b2fa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009b355`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009b355`

## string_xrefs

- `0x18009b21f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009b270`: `hr = client.ImpersonateClient()`
- `0x18009b2c7`: `OpenThreadToken failed with hr = 0x%x`
- `0x18009b316`: `DuplicateToken failed with hr = 0x%x`

## pseudocode

```c
__int64 __fastcall HandleIsKiosk(int *a1)
{
  int v2; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  void *v7; // rsi
  BOOL v8; // ebx
  enum _TOKEN_INFORMATION_CLASS v9; // edx
  HLOCAL UserSidFromWellKnownRid; // rdi
  PSID *v11; // rax
  PSID *v12; // rsi
  unsigned int v13; // ebx
  char *v15; // [rsp+20h] [rbp-40h]
  char *v16; // [rsp+20h] [rbp-40h]
  void *DuplicateTokenHandle; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v19[4]; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+98h] [rbp+38h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+48h] BYREF

  v20 = 0;
  v19[0] = "HandleIsKiosk";
  v19[2] = 0;
  v19[1] = &v20;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleIsKiosk",
    (const char *)0x230A,
    0,
    (const unsigned __int16 *)v15);
  v18 = 0;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  v2 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v18, 0);
  v20 = v2;
  if ( v2 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleIsKiosk",
      0x2311u,
      v2,
      "hr = client.ImpersonateClient()");
    goto LABEL_17;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = L"OpenThreadToken failed with hr = 0x%x";
    v6 = 8982;
LABEL_7:
    LODWORD(v16) = LastError;
    v20 = LastError;
    TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", v6, v5, v16);
    goto LABEL_17;
  }
  if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = L"DuplicateToken failed with hr = 0x%x";
    v6 = 8989;
    goto LABEL_7;
  }
  v7 = DuplicateTokenHandle;
  v8 = 0;
  v21 = 0;
  UserSidFromWellKnownRid = GetUserSidFromWellKnownRid();
  if ( UserSidFromWellKnownRid )
  {
    v11 = (PSID *)RetrieveTokenInformationClass(v7, v9, &v21);
    v12 = v11;
    if ( v11 )
    {
      v8 = EqualSid(UserSidFromWellKnownRid, *v11);
      LocalFree(v12);
    }
    LocalFree(UserSidFromWellKnownRid);
  }
  *a1 = v8;
LABEL_17:
  v13 = v20;
  ATL::CHandle::~CHandle((ATL::CHandle *)&TokenHandle);
  ATL::CHandle::~CHandle((ATL::CHandle *)&DuplicateTokenHandle);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v18);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return v13;
}

```

## disassembly

```asm
0x18009b1f0  push    rbp
0x18009b1f2  push    rbx
0x18009b1f3  push    rsi
0x18009b1f4  push    rdi
0x18009b1f5  push    r14
0x18009b1f7  mov     rbp, rsp
0x18009b1fa  sub     rsp, 60h
0x18009b1fe  lea     rdi, aHandleiskiosk; "HandleIsKiosk"
0x18009b205  mov     [rbp+arg_8], 0
0x18009b20c  mov     r14, rcx
0x18009b20f  mov     [rbp+var_20], rdi
0x18009b213  lea     rax, [rbp+arg_8]
0x18009b217  mov     [rbp+var_10], 0
0x18009b21f  lea     rbx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009b226  mov     [rbp+var_18], rax
0x18009b22a  mov     rdx, rdi; char *
0x18009b22d  mov     [rbp+var_8], 0
0x18009b235  mov     rcx, rbx; this
0x18009b238  xor     r9d, r9d; unsigned int
0x18009b23b  mov     r8d, 230Ah; char *
0x18009b241  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18009b246  xor     edx, edx; struct ATL::CAccessToken *
0x18009b248  mov     [rbp+var_28], 0
0x18009b250  lea     rcx, [rbp+var_28]; this
0x18009b254  mov     [rbp+DuplicateTokenHandle], 0
0x18009b25c  mov     [rbp+TokenHandle], 0
0x18009b264  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18009b269  mov     [rbp+arg_8], eax
0x18009b26c  test    eax, eax
0x18009b26e  jns     short loc_18009B295
0x18009b270  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x18009b277  mov     r9d, eax; int
0x18009b27a  mov     [rsp+60h+var_40], r8; char *
0x18009b27f  mov     rdx, rdi; char *
0x18009b282  mov     r8d, 2311h; unsigned int
0x18009b288  mov     rcx, rbx; char *
0x18009b28b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18009b290  jmp     loc_18009B379
0x18009b295  call    cs:__imp_GetCurrentThread
0x18009b29b  mov     edx, 0Ah; DesiredAccess
0x18009b2a0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18009b2a4  mov     rcx, rax; ThreadHandle
0x18009b2a7  lea     r8d, [rdx-9]; OpenAsSelf
0x18009b2ab  call    cs:__imp_OpenThreadToken
0x18009b2b1  test    eax, eax
0x18009b2b3  jnz     short loc_18009B2ED
0x18009b2b5  call    cs:__imp_GetLastError
0x18009b2bb  test    eax, eax
0x18009b2bd  jle     short loc_18009B2C7
0x18009b2bf  movzx   eax, ax
0x18009b2c2  or      eax, 80070000h
0x18009b2c7  lea     r9, aOpenthreadtoke_0; "OpenThreadToken failed with hr = 0x%x"
0x18009b2ce  mov     r8d, 2316h; unsigned int
0x18009b2d4  mov     rdx, rbx; char *
0x18009b2d7  mov     dword ptr [rsp+60h+var_40], eax
0x18009b2db  mov     ecx, 2; unsigned __int8
0x18009b2e0  mov     [rbp+arg_8], eax
0x18009b2e3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009b2e8  jmp     loc_18009B379
0x18009b2ed  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x18009b2f1  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18009b2f5  mov     edx, 2; ImpersonationLevel
0x18009b2fa  call    cs:__imp_DuplicateToken
0x18009b300  test    eax, eax
0x18009b302  jnz     short loc_18009B325
0x18009b304  call    cs:__imp_GetLastError
0x18009b30a  test    eax, eax
0x18009b30c  jle     short loc_18009B316
0x18009b30e  movzx   eax, ax
0x18009b311  or      eax, 80070000h
0x18009b316  lea     r9, aDuplicatetoken; "DuplicateToken failed with hr = 0x%x"
0x18009b31d  mov     r8d, 231Dh
0x18009b323  jmp     short loc_18009B2D4
0x18009b325  mov     rsi, [rbp+DuplicateTokenHandle]
0x18009b329  xor     ebx, ebx
0x18009b32b  mov     [rbp+arg_10], ebx
0x18009b32e  call    ?GetUserSidFromWellKnownRid@@YAPEAXK@Z; GetUserSidFromWellKnownRid(ulong)
0x18009b333  mov     rdi, rax
0x18009b336  test    rax, rax
0x18009b339  jz      short loc_18009B376
0x18009b33b  lea     r8, [rbp+arg_10]; unsigned int *
0x18009b33f  mov     rcx, rsi; TokenHandle
0x18009b342  call    ?RetrieveTokenInformationClass@@YAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@PEAK@Z; RetrieveTokenInformationClass(void *,_TOKEN_INFORMATION_CLASS,ulong *)
0x18009b347  mov     rsi, rax
0x18009b34a  test    rax, rax
0x18009b34d  jz      short loc_18009B36D
0x18009b34f  mov     rdx, [rax]; pSid2
0x18009b352  mov     rcx, rdi; pSid1
0x18009b355  call    cs:__imp_EqualSid
0x18009b35b  test    eax, eax
0x18009b35d  jz      short loc_18009B364
0x18009b35f  mov     ebx, 1
0x18009b364  mov     rcx, rsi; hMem
0x18009b367  call    cs:__imp_LocalFree
0x18009b36d  mov     rcx, rdi; hMem
0x18009b370  call    cs:__imp_LocalFree
0x18009b376  mov     [r14], ebx
0x18009b379  mov     ebx, [rbp+arg_8]
0x18009b37c  lea     rcx, [rbp+TokenHandle]; this
0x18009b380  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18009b385  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x18009b389  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18009b38e  lea     rcx, [rbp+var_28]; this
0x18009b392  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x18009b397  lea     rcx, [rbp+var_20]
0x18009b39b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18009b3a0  mov     eax, ebx
0x18009b3a2  add     rsp, 60h
0x18009b3a6  pop     r14
0x18009b3a8  pop     rdi
0x18009b3a9  pop     rsi
0x18009b3aa  pop     rbx
0x18009b3ab  pop     rbp
0x18009b3ac  retn
```
