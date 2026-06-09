# CreateUpdateDeploymentSessionCF(wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,tagUpdateDeploymentSessionHostInfo *)

- ea: `0x1801bd7e8`
- end: `0x1801bdeb7`
- name: `?CreateUpdateDeploymentSessionCF@@YAJAEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAUtagUpdateDeploymentSessionHostInfo@@@Z`
- size: `1743`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004f840`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18000e3d4`
- `0x180012edc`
- `0x180016924`
- `0x18001a880`
- `0x1800549f4`
- `0x1801119a4`
- `0x18012b618`
- `0x18012bed4`
- `0x1801bd4f4`
- `0x1801bd7e8`
- `0x1801be3d0`
- `0x1801be9d8`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801bdcc8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801bdcc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801bdce8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801bde3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801bdce8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801bde3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd89a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd8d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd89a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd8d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801bd9d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801bd9d8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801bdab5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801bdab5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1801bdac6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1801bdac6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801bde15`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801bde15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801bd91e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801bd91e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd8ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd9af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bda2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bda8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bdb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bdbdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd8ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd9af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bda2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bda8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bdb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bdbdd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801bd92f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801bd92f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801bda5b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801bda5b`

## string_xrefs

- `0x1801bdc17`: `Update Deployment Session launched but was not ready in time.`
- `0x1801bdc4e`: `CreateUpdateDeploymentSessionCF`
- `0x1801bdd9b`: `CreateUpdateDeploymentSessionCF`
- `0x1801bdb08`: `ERROR: %ws deployment session CF host (CLSID %ws) exited before signaling ready event`
- `0x1801bdba1`: `%ws deployment session CF host (CLSID %ws) successfully launched.`
- `0x1801bdd65`: `Update Deployment Session timed out after signalling exit`
- `0x1801bddd7`: `%ws deployment session CF host (CLSID %ws) exit timed out even after signalling exit.`
- `0x1801bdc94`: `%ws deployment session CF host (CLSID %ws) launched but was not ready in time. Attempting to release host.`
- `0x1801bdd1d`: `%ws deployment session CF host (CLSID %ws) exited successfully upon signalling exit.`
- `0x1801bde81`: `%ws deployment session CF host (CLSID %ws) forced termination %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreateUpdateDeploymentSessionCF(__int64 a1, _BYTE *a2)
{
  unsigned int LastError; // ebx
  char v5; // r15
  __int64 v6; // rbx
  HANDLE v7; // rsi
  const char *v8; // r9
  _QWORD *v9; // rdi
  void *v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // rsi
  _QWORD *v13; // rdi
  void *v14; // rcx
  DWORD CurrentProcessId; // eax
  HANDLE v16; // rsi
  _QWORD *v17; // rdi
  void *v18; // rcx
  _QWORD *v19; // rsi
  int UpdateDeploymentSessionCFHostProcess; // eax
  const char *v21; // r9
  HANDLE Thread; // r14
  int v23; // eax
  unsigned int v24; // esi
  void *v25; // rcx
  DWORD v26; // eax
  const char *v27; // r9
  __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // rax
  const wchar_t *v32; // rsi
  unsigned int v33; // esi
  __int64 v34; // rax
  const wchar_t *v35; // rsi
  __int64 v36; // rax
  const wchar_t *v37; // rsi
  DWORD v38; // eax
  int LastErrorHr; // edi
  __int64 v40; // rax
  void *v41; // rax
  void *v42; // rax
  __int64 v43; // rax
  unsigned int v44; // eax
  void *v45; // rdx
  unsigned int v46; // r8d
  int dwCreationFlags; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationFlagsd; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsc; // [rsp+20h] [rbp-E0h]
  _QWORD v52[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v53; // [rsp+60h] [rbp-A0h]
  _BYTE v54[80]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpParameter; // [rsp+C0h] [rbp-40h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+C8h] [rbp-38h] BYREF
  char v57; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+E8h] [rbp-18h] BYREF
  HANDLE Handles[2]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  lpParameter = a2;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
      (const char *)0x80004003LL,
      dwCreationFlags);
    return LastError;
  }
  v5 = a2[8];
  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = v5 != 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  v57 = 1;
  v6 = -1;
  hObject = (HANDLE)-1LL;
  v52[0] = &v57;
  v52[1] = &lpParameter;
  v53 = 1;
  v7 = CreateEventW(&EventAttributes, 1, 0, 0);
  v9 = lpParameter;
  v10 = (void *)*((_QWORD *)lpParameter + 6);
  if ( v10 )
    CloseHandle(v10);
  v9[6] = v7;
  if ( !*((_QWORD *)lpParameter + 6) )
  {
    v11 = 258;
LABEL_12:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
                  v8);
LABEL_25:
    wil::details::lambda_call__lambda_227e4849062d9b514525184b06204690___::_lambda_call__lambda_227e4849062d9b514525184b06204690___(v52);
    return LastError;
  }
  v12 = CreateEventW(&EventAttributes, 1, 0, 0);
  v13 = lpParameter;
  v14 = (void *)*((_QWORD *)lpParameter + 7);
  if ( v14 )
    CloseHandle(v14);
  v13[7] = v12;
  if ( !*((_QWORD *)lpParameter + 7) )
  {
    v11 = 261;
    goto LABEL_12;
  }
  CurrentProcessId = GetCurrentProcessId();
  v16 = OpenProcess(0x100400u, 1, CurrentProcessId);
  v17 = lpParameter;
  v18 = (void *)*((_QWORD *)lpParameter + 8);
  if ( v18 )
    CloseHandle(v18);
  v17[8] = v16;
  v19 = lpParameter;
  if ( !*((_QWORD *)lpParameter + 8) )
  {
    v11 = 265;
    goto LABEL_12;
  }
  if ( v5 )
  {
    UpdateDeploymentSessionCFHostProcess = CreateUpdateDeploymentSessionCFHostProcess(
                                             (__int64)lpParameter,
                                             a1,
                                             (__int64)&hObject);
    LastError = UpdateDeploymentSessionCFHostProcess;
    if ( UpdateDeploymentSessionCFHostProcess < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
        (const char *)(unsigned int)UpdateDeploymentSessionCFHostProcess,
        dwCreationFlags);
      wil::details::lambda_call__lambda_227e4849062d9b514525184b06204690___::_lambda_call__lambda_227e4849062d9b514525184b06204690___(v52);
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      return LastError;
    }
    v6 = (__int64)hObject;
  }
  else
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)UpdateDeploymentSessionCFHostThread, lpParameter, 0, 0);
    if ( Thread )
    {
      v25 = (void *)v19[5];
      if ( v25 )
        CloseHandle(v25);
      v19[5] = Thread;
    }
    else
    {
      v23 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xE3,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
              v21);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
          (const char *)(unsigned int)v23,
          dwCreationFlagsa);
        LastError = v24;
        goto LABEL_25;
      }
    }
  }
  Handles[0] = *((HANDLE *)lpParameter + 5);
  Handles[1] = *((HANDLE *)lpParameter + 6);
  v26 = WaitForMultipleObjects(2u, Handles, 0, 0xEA60u);
  if ( v26 == -1 )
  {
    v28 = 283;
LABEL_31:
    v29 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v28,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
            v27);
LABEL_32:
    v30 = v29;
    wil::details::lambda_call__lambda_227e4849062d9b514525184b06204690___::_lambda_call__lambda_227e4849062d9b514525184b06204690___(v52);
    if ( v6 != -1 )
      CloseHandle((HANDLE)v6);
    return v30;
  }
  if ( v26 )
  {
    if ( v26 == 1 )
    {
      v34 = Trace::GuidToString::GuidToString(
              (Trace::GuidToString *)v54,
              (const struct _GUID *)((char *)lpParameter + 24));
      v35 = L"Local";
      if ( v5 )
        v35 = L"Remote";
      WUTrace(0, 0, 0x1000000, 4, 0, L"%ws deployment session CF host (CLSID %ws) successfully launched.", v35, v34);
      v57 = 0;
    }
    else if ( v26 == 258 )
    {
      WUTrace(
        "CreateUpdateDeploymentSessionCF",
        323,
        32,
        3,
        0,
        L"TelemetryAssert (%ws): %ws",
        L"false",
        L"Update Deployment Session launched but was not ready in time.");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      v36 = Trace::GuidToString::GuidToString(
              (Trace::GuidToString *)v54,
              (const struct _GUID *)((char *)lpParameter + 24));
      v37 = L"Local";
      if ( v5 )
        v37 = L"Remote";
      WUTrace(
        0,
        0,
        0x1000000,
        4,
        0,
        L"%ws deployment session CF host (CLSID %ws) launched but was not ready in time. Attempting to release host.",
        v37,
        v36);
      if ( !SetEvent(*((HANDLE *)lpParameter + 7)) )
      {
        v28 = 332;
        goto LABEL_31;
      }
      v38 = WaitForSingleObject(*((HANDLE *)lpParameter + 5), 0xEA60u);
      switch ( v38 )
      {
        case 0xFFFFFFFF:
          v28 = 337;
          goto LABEL_31;
        case 0u:
          Trace::GuidToString::GuidToString(
            (Trace::GuidToString *)v54,
            (const struct _GUID *)((char *)lpParameter + 24));
          WUTrace(
            0,
            0,
            0x1000000,
            4,
            0,
            L"%ws deployment session CF host (CLSID %ws) exited successfully upon signalling exit.");
          v29 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x15B,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
                  (const char *)0x102,
                  dwCreationFlagsd);
          goto LABEL_32;
        case 0x102u:
          LastErrorHr = 0;
          WUTrace(
            "CreateUpdateDeploymentSessionCF",
            354,
            32,
            3,
            0,
            L"TelemetryAssert (%ws): %ws",
            L"false",
            L"Update Deployment Session timed out after signalling exit");
          WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
          v40 = Trace::GuidToString::GuidToString(
                  (Trace::GuidToString *)v54,
                  (const struct _GUID *)((char *)lpParameter + 24));
          Trace::GuidToString::operator wchar_t const *(v40);
          WUTrace(
            0,
            0,
            0x1000000,
            4,
            0,
            L"%ws deployment session CF host (CLSID %ws) exit timed out even after signalling exit.");
          if ( v5 )
          {
            v41 = (void *)WuSmartPtr::XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy>::Get((char *)lpParameter + 40);
            if ( !TerminateProcess(v41, 0x80240FFF) )
              LastErrorHr = GetLastErrorHr(1);
            v42 = (void *)WuSmartPtr::XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy>::Get((char *)lpParameter + 40);
            WaitForSingleObject(v42, 0xEA60u);
            v43 = Trace::GuidToString::GuidToString(
                    (Trace::GuidToString *)v54,
                    (const struct _GUID *)((char *)lpParameter + 24));
            Trace::GuidToString::operator wchar_t const *(v43);
            WUTrace(
              0,
              0,
              0x1000000,
              4,
              LastErrorHr,
              L"%ws deployment session CF host (CLSID %ws) forced termination %ws.");
          }
          v44 = wil::verify_hresult<long>(2149847039LL);
          wil::details::in1diag3::FailFast_Hr(retaddr, v45, v46, (const char *)v44, dwCreationFlagsc);
      }
    }
    wil::details::lambda_call__lambda_227e4849062d9b514525184b06204690___::_lambda_call__lambda_227e4849062d9b514525184b06204690___(v52);
    if ( v6 != -1 )
      CloseHandle((HANDLE)v6);
    return 0;
  }
  else
  {
    LODWORD(hObject) = 0;
    if ( v5 )
    {
      if ( !GetExitCodeProcess(Handles[0], (LPDWORD)&hObject) )
      {
        v28 = 291;
        goto LABEL_31;
      }
    }
    else if ( !GetExitCodeThread(Handles[0], (LPDWORD)&hObject) )
    {
      v28 = 295;
      goto LABEL_31;
    }
    v31 = Trace::GuidToString::GuidToString(
            (Trace::GuidToString *)v54,
            (const struct _GUID *)((char *)lpParameter + 24));
    v32 = L"Local";
    if ( v5 )
      v32 = L"Remote";
    WUTrace(
      0,
      0,
      0x1000000,
      1,
      (_DWORD)hObject,
      L"ERROR: %ws deployment session CF host (CLSID %ws) exited before signaling ready event",
      v32,
      v31);
    v33 = (unsigned int)hObject;
    if ( (int)hObject < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
        (const char *)(unsigned int)hObject,
        dwCreationFlagsb);
    wil::details::lambda_call__lambda_227e4849062d9b514525184b06204690___::_lambda_call__lambda_227e4849062d9b514525184b06204690___(v52);
    if ( v6 != -1 )
      CloseHandle((HANDLE)v6);
    return v33;
  }
}

```

## disassembly

```asm
0x1801bd7e8  mov     [rsp-8+arg_10], rbx
0x1801bd7ed  push    rbp
0x1801bd7ee  push    rsi
0x1801bd7ef  push    rdi
0x1801bd7f0  push    r12
0x1801bd7f2  push    r13
0x1801bd7f4  push    r14
0x1801bd7f6  push    r15
0x1801bd7f8  lea     rbp, [rsp-10h]
0x1801bd7fd  sub     rsp, 110h
0x1801bd804  mov     rax, cs:__security_cookie
0x1801bd80b  xor     rax, rsp
0x1801bd80e  mov     [rbp+40h+var_40], rax
0x1801bd812  mov     r14, rcx
0x1801bd815  mov     [rbp+40h+lpParameter], rdx
0x1801bd819  xor     r13d, r13d
0x1801bd81c  test    rdx, rdx
0x1801bd81f  jnz     short loc_1801BD845
0x1801bd821  mov     rcx, [rbp+48h]; this
0x1801bd825  mov     ebx, 80004003h
0x1801bd82a  mov     r9d, ebx; char *
0x1801bd82d  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd834  mov     edx, 0EDh; void *
0x1801bd839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd83e  mov     eax, ebx
0x1801bd840  jmp     loc_1801BDBE5
0x1801bd845  mov     r15b, [rdx+8]
0x1801bd849  mov     qword ptr [rbp+40h+EventAttributes.nLength], 18h
0x1801bd851  mov     [rbp+40h+EventAttributes.lpSecurityDescriptor], r13
0x1801bd855  mov     eax, r13d
0x1801bd858  test    r15b, r15b
0x1801bd85b  setnz   al
0x1801bd85e  mov     [rbp+40h+EventAttributes.bInheritHandle], eax
0x1801bd861  xor     eax, eax
0x1801bd863  mov     dword ptr [rbp+40h+EventAttributes+14h], eax
0x1801bd866  lea     r12d, [rax+1]
0x1801bd86a  mov     [rbp+40h+var_60], r12b
0x1801bd86e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801bd872  mov     [rbp+40h+hObject], rbx
0x1801bd876  lea     rax, [rbp+40h+var_60]
0x1801bd87a  mov     [rsp+140h+var_F0], rax
0x1801bd87f  lea     rax, [rbp+40h+lpParameter]
0x1801bd883  mov     [rsp+140h+var_E8], rax
0x1801bd888  mov     [rsp+140h+var_E0], r12b
0x1801bd88d  xor     r9d, r9d; lpName
0x1801bd890  xor     r8d, r8d; bInitialState
0x1801bd893  mov     edx, r12d; bManualReset
0x1801bd896  lea     rcx, [rbp+40h+EventAttributes]; lpEventAttributes
0x1801bd89a  call    cs:__imp_CreateEventW
0x1801bd8a0  mov     rsi, rax
0x1801bd8a3  mov     rdi, [rbp+40h+lpParameter]
0x1801bd8a7  mov     rcx, [rdi+30h]; hObject
0x1801bd8ab  test    rcx, rcx
0x1801bd8ae  jz      short loc_1801BD8B6
0x1801bd8b0  call    cs:__imp_CloseHandle
0x1801bd8b6  mov     [rdi+30h], rsi
0x1801bd8ba  mov     rax, [rbp+40h+lpParameter]
0x1801bd8be  cmp     [rax+30h], r13
0x1801bd8c2  jnz     short loc_1801BD8CB
0x1801bd8c4  mov     edx, 102h
0x1801bd8c9  jmp     short loc_1801BD907
0x1801bd8cb  xor     r9d, r9d; lpName
0x1801bd8ce  xor     r8d, r8d; bInitialState
0x1801bd8d1  mov     edx, r12d; bManualReset
0x1801bd8d4  lea     rcx, [rbp+40h+EventAttributes]; lpEventAttributes
0x1801bd8d8  call    cs:__imp_CreateEventW
0x1801bd8de  mov     rsi, rax
0x1801bd8e1  mov     rdi, [rbp+40h+lpParameter]
0x1801bd8e5  mov     rcx, [rdi+38h]; hObject
0x1801bd8e9  test    rcx, rcx
0x1801bd8ec  jz      short loc_1801BD8F4
0x1801bd8ee  call    cs:__imp_CloseHandle
0x1801bd8f4  mov     [rdi+38h], rsi
0x1801bd8f8  mov     rax, [rbp+40h+lpParameter]
0x1801bd8fc  cmp     [rax+38h], r13
0x1801bd900  jnz     short loc_1801BD91E
0x1801bd902  mov     edx, 105h; void *
0x1801bd907  mov     rcx, [rbp+48h]; this
0x1801bd90b  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd912  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801bd917  mov     ebx, eax
0x1801bd919  jmp     loc_1801BDA13
0x1801bd91e  call    cs:__imp_GetCurrentProcessId
0x1801bd924  mov     r8d, eax; dwProcessId
0x1801bd927  mov     edx, r12d; bInheritHandle
0x1801bd92a  mov     ecx, 100400h; dwDesiredAccess
0x1801bd92f  call    cs:__imp_OpenProcess
0x1801bd935  mov     rsi, rax
0x1801bd938  mov     rdi, [rbp+40h+lpParameter]
0x1801bd93c  mov     rcx, [rdi+40h]; hObject
0x1801bd940  test    rcx, rcx
0x1801bd943  jz      short loc_1801BD94B
0x1801bd945  call    cs:__imp_CloseHandle
0x1801bd94b  mov     [rdi+40h], rsi
0x1801bd94f  mov     rsi, [rbp+40h+lpParameter]
0x1801bd953  cmp     [rsi+40h], r13
0x1801bd957  jnz     short loc_1801BD960
0x1801bd959  mov     edx, 109h
0x1801bd95e  jmp     short loc_1801BD907
0x1801bd960  lea     rdi, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd967  test    r15b, r15b
0x1801bd96a  jz      short loc_1801BD9C0
0x1801bd96c  lea     r8, [rbp+40h+hObject]
0x1801bd970  mov     rdx, r14
0x1801bd973  mov     rcx, rsi
0x1801bd976  call    ?CreateUpdateDeploymentSessionCFHostProcess@@YAJPEAUtagUpdateDeploymentSessionHostInfo@@AEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAPEAX@Z; CreateUpdateDeploymentSessionCFHostProcess(tagUpdateDeploymentSessionHostInfo *,wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,void * *)
0x1801bd97b  mov     ebx, eax
0x1801bd97d  test    eax, eax
0x1801bd97f  jns     short loc_1801BD9BA
0x1801bd981  mov     rcx, [rbp+48h]; this
0x1801bd985  mov     r9d, eax; char *
0x1801bd988  mov     r8, rdi; unsigned int
0x1801bd98b  mov     edx, 10Fh; void *
0x1801bd990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd995  nop
0x1801bd996  lea     rcx, [rsp+140h+var_F0]
0x1801bd99b  call    wil__details__lambda_call__lambda_227e4849062d9b514525184b06204690______lambda_call__lambda_227e4849062d9b514525184b06204690___
0x1801bd9a0  nop
0x1801bd9a1  mov     rcx, [rbp+40h+hObject]; hObject
0x1801bd9a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd9a9  jz      loc_1801BD83E
0x1801bd9af  call    cs:__imp_CloseHandle
0x1801bd9b5  jmp     loc_1801BD83E
0x1801bd9ba  mov     rbx, [rbp+40h+hObject]
0x1801bd9be  jmp     short loc_1801BDA36
0x1801bd9c0  mov     [rsp+140h+lpThreadId], r13; lpThreadId
0x1801bd9c5  mov     [rsp+140h+dwCreationFlags], r13d; int
0x1801bd9ca  mov     r9, rsi; lpParameter
0x1801bd9cd  lea     r8, UpdateDeploymentSessionCFHostThread; lpStartAddress
0x1801bd9d4  xor     edx, edx; dwStackSize
0x1801bd9d6  xor     ecx, ecx; lpThreadAttributes
0x1801bd9d8  call    cs:__imp_CreateThread
0x1801bd9de  mov     r14, rax
0x1801bd9e1  test    rax, rax
0x1801bd9e4  jnz     short loc_1801BDA23
0x1801bd9e6  mov     rcx, [rbp+48h]; this
0x1801bd9ea  mov     r8, rdi; unsigned int
0x1801bd9ed  mov     edx, 0E3h; void *
0x1801bd9f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801bd9f7  mov     esi, eax
0x1801bd9f9  test    eax, eax
0x1801bd9fb  jns     short loc_1801BDA36
0x1801bd9fd  mov     rcx, [rbp+48h]; this
0x1801bda01  mov     r9d, eax; char *
0x1801bda04  mov     r8, rdi; unsigned int
0x1801bda07  mov     edx, 113h; void *
0x1801bda0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bda11  mov     ebx, esi
0x1801bda13  lea     rcx, [rsp+140h+var_F0]
0x1801bda18  call    wil__details__lambda_call__lambda_227e4849062d9b514525184b06204690______lambda_call__lambda_227e4849062d9b514525184b06204690___
0x1801bda1d  nop
0x1801bda1e  jmp     loc_1801BD83E
0x1801bda23  mov     rcx, [rsi+28h]; hObject
0x1801bda27  test    rcx, rcx
0x1801bda2a  jz      short loc_1801BDA32
0x1801bda2c  call    cs:__imp_CloseHandle
0x1801bda32  mov     [rsi+28h], r14
0x1801bda36  mov     rcx, [rbp+40h+lpParameter]
0x1801bda3a  mov     rax, [rcx+28h]
0x1801bda3e  mov     [rbp+40h+Handles], rax
0x1801bda42  mov     rax, [rcx+30h]
0x1801bda46  mov     [rbp+40h+var_48], rax
0x1801bda4a  mov     r9d, 0EA60h; dwMilliseconds
0x1801bda50  xor     r8d, r8d; bWaitAll
0x1801bda53  lea     rdx, [rbp+40h+Handles]; lpHandles
0x1801bda57  lea     ecx, [r8+2]; nCount
0x1801bda5b  call    cs:__imp_WaitForMultipleObjects
0x1801bda61  or      esi, 0FFFFFFFFh
0x1801bda64  cmp     eax, esi
0x1801bda66  jnz     short loc_1801BDA9C
0x1801bda68  mov     edx, 11Bh; void *
0x1801bda6d  mov     rcx, [rbp+48h]; this
0x1801bda71  mov     r8, rdi; unsigned int
0x1801bda74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801bda79  mov     edi, eax
0x1801bda7b  lea     rcx, [rsp+140h+var_F0]
0x1801bda80  call    wil__details__lambda_call__lambda_227e4849062d9b514525184b06204690______lambda_call__lambda_227e4849062d9b514525184b06204690___
0x1801bda85  nop
0x1801bda86  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801bda8a  jz      short loc_1801BDA95
0x1801bda8c  mov     rcx, rbx; hObject
0x1801bda8f  call    cs:__imp_CloseHandle
0x1801bda95  mov     eax, edi
0x1801bda97  jmp     loc_1801BDBE5
0x1801bda9c  test    eax, eax
0x1801bda9e  jnz     loc_1801BDB67
0x1801bdaa4  mov     dword ptr [rbp+40h+hObject], r13d
0x1801bdaa8  lea     rdx, [rbp+40h+hObject]; lpExitCode
0x1801bdaac  mov     rcx, [rbp+40h+Handles]; hThread
0x1801bdab0  test    r15b, r15b
0x1801bdab3  jz      short loc_1801BDAC6
0x1801bdab5  call    cs:__imp_GetExitCodeProcess
0x1801bdabb  test    eax, eax
0x1801bdabd  jnz     short loc_1801BDAD7
0x1801bdabf  mov     edx, 123h
0x1801bdac4  jmp     short loc_1801BDA6D
0x1801bdac6  call    cs:__imp_GetExitCodeThread
0x1801bdacc  test    eax, eax
0x1801bdace  jnz     short loc_1801BDAD7
0x1801bdad0  mov     edx, 127h
0x1801bdad5  jmp     short loc_1801BDA6D
0x1801bdad7  mov     rdx, [rbp+40h+lpParameter]
0x1801bdadb  add     rdx, 18h; struct _GUID *
0x1801bdadf  lea     rcx, [rsp+140h+var_D0]; this
0x1801bdae4  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1801bdae9  lea     rcx, aRemote; "Remote"
0x1801bdaf0  lea     rsi, aLocal; "Local"
0x1801bdaf7  test    r15b, r15b
0x1801bdafa  cmovnz  rsi, rcx
0x1801bdafe  mov     [rsp+140h+var_108], rax
0x1801bdb03  mov     [rsp+140h+var_110], rsi
0x1801bdb08  lea     rax, aErrorWsDeploym; "ERROR: %ws deployment session CF host ("...
0x1801bdb0f  mov     [rsp+140h+lpThreadId], rax
0x1801bdb14  mov     eax, dword ptr [rbp+40h+hObject]
0x1801bdb17  mov     [rsp+140h+dwCreationFlags], eax; int
0x1801bdb1b  mov     r9d, r12d
0x1801bdb1e  xor     edx, edx
0x1801bdb20  xor     ecx, ecx
0x1801bdb22  mov     r8d, 1000000h
0x1801bdb28  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801bdb2d  mov     esi, dword ptr [rbp+40h+hObject]
0x1801bdb30  test    esi, esi
0x1801bdb32  jns     short loc_1801BDB49
0x1801bdb34  mov     rcx, [rbp+48h]; this
0x1801bdb38  mov     r9d, esi; char *
0x1801bdb3b  mov     r8, rdi; unsigned int
0x1801bdb3e  mov     edx, 131h; void *
0x1801bdb43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bdb48  nop
0x1801bdb49  lea     rcx, [rsp+140h+var_F0]
0x1801bdb4e  call    wil__details__lambda_call__lambda_227e4849062d9b514525184b06204690______lambda_call__lambda_227e4849062d9b514525184b06204690___
0x1801bdb53  nop
0x1801bdb54  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801bdb58  jz      short loc_1801BDB63
0x1801bdb5a  mov     rcx, rbx; hObject
0x1801bdb5d  call    cs:__imp_CloseHandle
0x1801bdb63  mov     eax, esi
0x1801bdb65  jmp     short loc_1801BDBE5
0x1801bdb67  cmp     eax, r12d
0x1801bdb6a  jnz     loc_1801BDC0C
0x1801bdb70  mov     rdx, [rbp+40h+lpParameter]
0x1801bdb74  add     rdx, 18h; struct _GUID *
0x1801bdb78  lea     rcx, [rsp+140h+var_D0]; this
0x1801bdb7d  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1801bdb82  lea     rcx, aRemote; "Remote"
0x1801bdb89  lea     rsi, aLocal; "Local"
0x1801bdb90  test    r15b, r15b
0x1801bdb93  cmovnz  rsi, rcx
0x1801bdb97  mov     [rsp+140h+var_108], rax
0x1801bdb9c  mov     [rsp+140h+var_110], rsi
0x1801bdba1  lea     rax, aWsDeploymentSe_0; "%ws deployment session CF host (CLSID %"...
0x1801bdba8  mov     [rsp+140h+lpThreadId], rax
0x1801bdbad  mov     qword ptr [rsp+140h+dwCreationFlags], r13
0x1801bdbb2  xor     edx, edx
0x1801bdbb4  xor     ecx, ecx
0x1801bdbb6  lea     r9d, [rdx+4]
0x1801bdbba  mov     r8d, 1000000h
0x1801bdbc0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801bdbc5  mov     [rbp+40h+var_60], 0
0x1801bdbc9  lea     rcx, [rsp+140h+var_F0]
0x1801bdbce  call    wil__details__lambda_call__lambda_227e4849062d9b514525184b06204690______lambda_call__lambda_227e4849062d9b514525184b06204690___
0x1801bdbd3  nop
0x1801bdbd4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801bdbd8  jz      short loc_1801BDBE3
0x1801bdbda  mov     rcx, rbx; hObject
0x1801bdbdd  call    cs:__imp_CloseHandle
0x1801bdbe3  xor     eax, eax
0x1801bdbe5  mov     rcx, [rbp+40h+var_40]
0x1801bdbe9  xor     rcx, rsp; StackCookie
0x1801bdbec  call    __security_check_cookie
0x1801bdbf1  mov     rbx, [rsp+140h+arg_10]
0x1801bdbf9  add     rsp, 110h
0x1801bdc00  pop     r15
0x1801bdc02  pop     r14
0x1801bdc04  pop     r13
0x1801bdc06  pop     r12
0x1801bdc08  pop     rdi
0x1801bdc09  pop     rsi
0x1801bdc0a  pop     rbp
0x1801bdc0b  retn
0x1801bdc0c  mov     r14d, 102h
0x1801bdc12  cmp     eax, r14d
0x1801bdc15  jnz     short loc_1801BDBC9
0x1801bdc17  lea     rax, aUpdateDeployme_0; "Update Deployment Session launched but "...
0x1801bdc1e  mov     [rsp+140h+var_108], rax
0x1801bdc23  lea     rax, aFalse; "false"
0x1801bdc2a  mov     [rsp+140h+var_110], rax
0x1801bdc2f  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x1801bdc36  mov     [rsp+140h+lpThreadId], rax
0x1801bdc3b  mov     qword ptr [rsp+140h+dwCreationFlags], r13
0x1801bdc40  lea     edx, [r14+41h]
0x1801bdc44  mov     r9d, 3
0x1801bdc4a  lea     r8d, [r9+1Dh]
0x1801bdc4e  lea     rcx, aCreateupdatede; "CreateUpdateDeploymentSessionCF"
0x1801bdc55  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801bdc5a  mov     edx, esi; unsigned int
0x1801bdc5c  mov     ecx, esi; unsigned int
0x1801bdc5e  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x1801bdc63  mov     rdx, [rbp+40h+lpParameter]
0x1801bdc67  add     rdx, 18h; struct _GUID *
  ... truncated ...
```
