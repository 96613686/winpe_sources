# CreateVirtualChannel(void *,char const *,ulong,int,char *,ushort,ulong)

- ea: `0x1800119d4`
- end: `0x180011caa`
- name: `?CreateVirtualChannel@@YAPEAXPEAXPEBDKHPEADGK@Z`
- size: `726`
- prototype: `void *__usercall@<rax>(void *@<rcx>, const char *String1@<rdx>, unsigned int@<r8d>, int@<r9d>, char *, unsigned __int16, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011960`
- `0x180028920`

## callees

- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800119d4`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180011b29`
- `msvcrt!_strnicmp` at `0x180011b29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011a82`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011a95`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c71`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800306e9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800306e9`
- `RPCRT4!NdrClientCall3` at `0x180011b89`
- `RPCRT4!NdrClientCall3` at `0x180011bdc`
- `RPCRT4!NdrClientCall3` at `0x180011b89`
- `RPCRT4!NdrClientCall3` at `0x180011bdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ace`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ace`

## string_xrefs

- `0x180011a24`: `Failed to open binding`
- `0x180011b08`: `OpenProcessToken failed: %d`
- `0x180011c1b`: `RpcCreateVirtualChannel threw an exception: 0x%x (dwIsAppContainer=%d, fIsWebAuthnDVC=%d)`
- `0x180011ae1`: `GetTokenInformation failed: %d`
- `0x180011c31`: `CreateVirtualChannel`
- `0x180011c3b`: `RpcCreateVirtualChannel failed: 0x%x in %s`

## pseudocode

```c
char *__fastcall CreateVirtualChannel(
        void *a1,
        const char *String1,
        ULONG SessionId,
        DWORD a4,
        char *a5,
        int TokenInformation,
        unsigned int a7)
{
  int Pointer; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v13; // eax
  DWORD v14; // ecx
  __int64 v15; // rax
  CLIENT_CALL_RETURN v16; // rax
  __int64 v17; // rax
  DWORD v18; // eax
  DWORD v19; // eax
  char *v20; // rbx
  PDWORD ReturnLength; // [rsp+20h] [rbp-78h]
  void *TokenHandle; // [rsp+48h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+50h] [rbp-48h]
  CLIENT_CALL_RETURN v25; // [rsp+58h] [rbp-40h]
  unsigned __int16 v26[28]; // [rsp+60h] [rbp-38h] BYREF
  DWORD v27; // [rsp+B8h] [rbp+20h] BYREF

  v27 = a4;
  a5 = 0;
  Pointer = -2147467263;
  TokenHandle = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v26, a1, 1);
  if ( !CSmartPublicBinding::operator void *(v26) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_17;
  }
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(a1) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      SetLastError(0x57u);
      goto LABEL_17;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  TokenInformation = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v27 = 0;
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v27) )
    {
      LastError = GetLastError();
      _DbgPrintMessage(4, "GetTokenInformation failed: %d", LastError);
      TokenInformation = 0;
    }
  }
  else
  {
    v13 = GetLastError();
    _DbgPrintMessage(4, "OpenProcessToken failed: %d", v13);
  }
  v14 = _strnicmp(String1, "WebAuthN_Channel", 0x11u) == 0;
  v27 = v14;
  if ( TokenInformation && v14 )
  {
    v15 = CSmartPublicBinding::operator void *(v26);
    v24.Simple = 0;
    LODWORD(ReturnLength) = SessionId;
    v16.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800380D0, 0, 0, v15, ReturnLength, a7, &a5).Pointer;
    Pointer = (int)v16.Pointer;
    v24.Pointer = v16.Pointer;
  }
  else
  {
    v17 = CSmartPublicBinding::operator void *(v26);
    v25.Simple = 0;
    LODWORD(ReturnLength) = SessionId;
    v25.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 0, 0, v17, ReturnLength, String1, a7, &a5).Pointer;
    Pointer = (int)v25.Pointer;
  }
  if ( Pointer < 0 )
  {
    _DbgPrintMessage(8, "RpcCreateVirtualChannel failed: 0x%x in %s", Pointer, "CreateVirtualChannel");
    v18 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v18);
    a5 = 0;
  }
LABEL_17:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Pointer < 0 )
  {
    v19 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v19);
  }
  v20 = a5;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v26);
  return v20;
}

```

## disassembly

```asm
0x1800119d4  mov     rax, rsp
0x1800119d7  mov     [rax+20h], r9d
0x1800119db  push    rbx
0x1800119dc  push    rsi
0x1800119dd  push    r14
0x1800119df  push    r15
0x1800119e1  sub     rsp, 78h
0x1800119e5  mov     esi, r8d
0x1800119e8  mov     r15, rdx
0x1800119eb  mov     r14, rcx
0x1800119ee  mov     qword ptr [rax+28h], 0
0x1800119f6  mov     ebx, 80004001h
0x1800119fb  mov     qword ptr [rax-50h], 0
0x180011a03  mov     r8d, 1; int
0x180011a09  mov     rdx, rcx; void *
0x180011a0c  lea     rcx, [rax-38h]; this
0x180011a10  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180011a15  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180011a1a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011a1f  test    rax, rax
0x180011a22  jnz     short loc_180011A38
0x180011a24  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180011a2b  lea     ecx, [rax+8]; int
0x180011a2e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011a33  jmp     loc_180011C67
0x180011a38  cmp     esi, 0FFFFFFFFh
0x180011a3b  jnz     short loc_180011A77
0x180011a3d  mov     rcx, r14; void *
0x180011a40  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180011a45  test    eax, eax
0x180011a47  jnz     short loc_180011A68
0x180011a49  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180011a50  lea     ecx, [rax+4]; int
0x180011a53  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011a58  mov     ecx, 57h ; 'W'; dwErrCode
0x180011a5d  call    cs:__imp_SetLastError
0x180011a63  jmp     loc_180011C67
0x180011a68  mov     rax, gs:60h
0x180011a71  mov     esi, [rax+2C0h]
0x180011a77  mov     [rsp+98h+TokenInformation], 0
0x180011a82  call    cs:__imp_GetCurrentProcess
0x180011a88  mov     rcx, rax; ProcessHandle
0x180011a8b  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x180011a90  mov     edx, 8; DesiredAccess
0x180011a95  call    cs:__imp_OpenProcessToken
0x180011a9b  test    eax, eax
0x180011a9d  jz      short loc_180011AFF
0x180011a9f  mov     [rsp+98h+arg_18], 0
0x180011aaa  lea     rax, [rsp+98h+arg_18]
0x180011ab2  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180011ab7  mov     r9d, 4; TokenInformationLength
0x180011abd  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180011ac5  lea     edx, [r9+19h]; TokenInformationClass
0x180011ac9  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180011ace  call    cs:__imp_GetTokenInformation
0x180011ad4  test    eax, eax
0x180011ad6  jnz     short loc_180011B19
0x180011ad8  call    cs:__imp_GetLastError
0x180011ade  mov     r8d, eax
0x180011ae1  lea     rdx, aGettokeninform_1; "GetTokenInformation failed: %d"
0x180011ae8  mov     ecx, 4; int
0x180011aed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011af2  mov     [rsp+98h+TokenInformation], 0
0x180011afd  jmp     short loc_180011B19
0x180011aff  call    cs:__imp_GetLastError
0x180011b05  mov     r8d, eax
0x180011b08  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: %d"
0x180011b0f  mov     ecx, 4; int
0x180011b14  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011b19  mov     r8d, 11h; MaxCount
0x180011b1f  lea     rdx, String2; "WebAuthN_Channel"
0x180011b26  mov     rcx, r15; String1
0x180011b29  call    cs:__imp__strnicmp
0x180011b2f  xor     ecx, ecx
0x180011b31  test    eax, eax
0x180011b33  setz    cl
0x180011b36  mov     [rsp+98h+arg_18], ecx
0x180011b3d  cmp     [rsp+98h+TokenInformation], 0
0x180011b45  jz      short loc_180011B99
0x180011b47  test    ecx, ecx
0x180011b49  jz      short loc_180011B99
0x180011b4b  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180011b50  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011b55  mov     [rsp+98h+var_48], 0
0x180011b5e  lea     rcx, [rsp+98h+arg_20]
0x180011b66  mov     [rsp+98h+var_68], rcx
0x180011b6b  mov     ecx, [rsp+98h+arg_30]
0x180011b72  mov     dword ptr [rsp+98h+var_70], ecx
0x180011b76  mov     dword ptr [rsp+98h+ReturnLength], esi
0x180011b7a  mov     r9, rax
0x180011b7d  xor     r8d, r8d; pReturnValue
0x180011b80  xor     edx, edx; nProcNum
0x180011b82  lea     rcx, stru_1800380D0; pProxyInfo
0x180011b89  call    cs:__imp_NdrClientCall3
0x180011b8f  mov     rbx, rax
0x180011b92  mov     [rsp+98h+var_48], rax
0x180011b97  jmp     short loc_180011BE9
0x180011b99  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180011b9e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011ba3  mov     [rsp+98h+var_40], 0
0x180011bac  lea     rcx, [rsp+98h+arg_20]
0x180011bb4  mov     [rsp+98h+var_60], rcx
0x180011bb9  mov     ecx, [rsp+98h+arg_30]
0x180011bc0  mov     dword ptr [rsp+98h+var_68], ecx
0x180011bc4  mov     [rsp+98h+var_70], r15
0x180011bc9  mov     dword ptr [rsp+98h+ReturnLength], esi
0x180011bcd  mov     r9, rax
0x180011bd0  xor     r8d, r8d; pReturnValue
0x180011bd3  xor     edx, edx; nProcNum
0x180011bd5  lea     rcx, stru_180032140; pProxyInfo
0x180011bdc  call    cs:__imp_NdrClientCall3
0x180011be2  mov     [rsp+98h+var_40], rax
0x180011be7  mov     ebx, eax
0x180011be9  mov     [rsp+98h+var_58], eax
0x180011bed  jmp     short loc_180011C2D
0x180011bef  mov     r8d, eax
0x180011bf2  test    eax, eax
0x180011bf4  jle     short loc_180011C01
0x180011bf6  movzx   r8d, ax
0x180011bfa  or      r8d, 80070000h
0x180011c01  mov     ebx, r8d
0x180011c04  mov     [rsp+98h+var_58], ebx
0x180011c08  mov     eax, [rsp+98h+arg_18]
0x180011c0f  mov     dword ptr [rsp+98h+ReturnLength], eax
0x180011c13  mov     r9d, [rsp+98h+TokenInformation]
0x180011c1b  lea     rdx, aRpccreatevirtu_0; "RpcCreateVirtualChannel threw an except"...
0x180011c22  mov     ecx, 8; int
0x180011c27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011c2c  nop
0x180011c2d  test    ebx, ebx
0x180011c2f  jns     short loc_180011C67
0x180011c31  lea     r9, aCreatevirtualc; "CreateVirtualChannel"
0x180011c38  mov     r8d, ebx
0x180011c3b  lea     rdx, aRpccreatevirtu; "RpcCreateVirtualChannel failed: 0x%x in"...
0x180011c42  mov     ecx, 8; int
0x180011c47  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011c4c  mov     ecx, ebx; int
0x180011c4e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180011c53  mov     ecx, eax; dwErrCode
0x180011c55  call    cs:__imp_SetLastError
0x180011c5b  mov     [rsp+98h+arg_20], 0
0x180011c67  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180011c6c  test    rcx, rcx
0x180011c6f  jz      short loc_180011C77
0x180011c71  call    cs:__imp_CloseHandle
0x180011c77  test    ebx, ebx
0x180011c79  jns     short loc_180011C8A
0x180011c7b  mov     ecx, ebx; int
0x180011c7d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180011c82  mov     ecx, eax; dwErrCode
0x180011c84  call    cs:__imp_SetLastError
0x180011c8a  mov     rbx, [rsp+98h+arg_20]
0x180011c92  lea     rcx, [rsp+98h+var_38]; this
0x180011c97  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180011c9c  mov     rax, rbx
0x180011c9f  add     rsp, 78h
0x180011ca3  pop     r15
0x180011ca5  pop     r14
0x180011ca7  pop     rsi
0x180011ca8  pop     rbx
0x180011ca9  retn
0x1800306db  push    rbp
0x1800306dd  sub     rsp, 40h
0x1800306e1  mov     rbp, rdx
0x1800306e4  mov     rcx, [rcx]
0x1800306e7  mov     ecx, [rcx]; ExceptionCode
0x1800306e9  call    cs:__imp_I_RpcExceptionFilter
0x1800306ef  nop
0x1800306f0  add     rsp, 40h
0x1800306f4  pop     rbp
0x1800306f5  retn
```
