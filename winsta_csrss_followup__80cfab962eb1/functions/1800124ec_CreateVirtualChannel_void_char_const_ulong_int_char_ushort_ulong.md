# CreateVirtualChannel(void *,char const *,ulong,int,char *,ushort,ulong)

- ea: `0x1800124ec`
- end: `0x18001280b`
- name: `?CreateVirtualChannel@@YAPEAXPEAXPEBDKHPEADGK@Z`
- size: `799`
- prototype: `void *__usercall@<rax>(void *@<rcx>, const char *String1@<rdx>, unsigned int@<r8d>, int@<r9d>, char *, unsigned __int16, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012470`
- `0x18002a4f0`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000a784`
- `0x1800124ec`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180012665`
- `msvcrt!_strnicmp` at `0x180012665`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012575`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012575`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800125b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800125b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127c5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033585`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033585`
- `RPCRT4!NdrClientCall3` at `0x1800126cb`
- `RPCRT4!NdrClientCall3` at `0x180012724`
- `RPCRT4!NdrClientCall3` at `0x1800126cb`
- `RPCRT4!NdrClientCall3` at `0x180012724`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800125f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800125f8`

## string_xrefs

- `0x18001253c`: `Failed to open binding`
- `0x180012644`: `OpenProcessToken failed: %d`
- `0x180012769`: `RpcCreateVirtualChannel threw an exception: 0x%x (dwIsAppContainer=%d, fIsWebAuthnDVC=%d)`
- `0x180012617`: `GetTokenInformation failed: %d`
- `0x18001277f`: `CreateVirtualChannel`
- `0x180012789`: `RpcCreateVirtualChannel failed: 0x%x in %s`

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
    v16.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18003B0D0, 0, 0, v15, ReturnLength, a7, &a5).Pointer;
    Pointer = (int)v16.Pointer;
    v24.Pointer = v16.Pointer;
  }
  else
  {
    v17 = CSmartPublicBinding::operator void *(v26);
    v25.Simple = 0;
    LODWORD(ReturnLength) = SessionId;
    v25.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 0, 0, v17, ReturnLength, String1, a7, &a5).Pointer;
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
0x1800124ec  mov     rax, rsp
0x1800124ef  mov     [rax+20h], r9d
0x1800124f3  push    rbx
0x1800124f4  push    rsi
0x1800124f5  push    r14
0x1800124f7  push    r15
0x1800124f9  sub     rsp, 78h
0x1800124fd  mov     esi, r8d
0x180012500  mov     r15, rdx
0x180012503  mov     r14, rcx
0x180012506  mov     qword ptr [rax+28h], 0
0x18001250e  mov     ebx, 80004001h
0x180012513  mov     qword ptr [rax-50h], 0
0x18001251b  mov     r8d, 1; int
0x180012521  mov     rdx, rcx; void *
0x180012524  lea     rcx, [rax-38h]; this
0x180012528  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18001252d  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180012532  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012537  test    rax, rax
0x18001253a  jnz     short loc_180012550
0x18001253c  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180012543  lea     ecx, [rax+8]; int
0x180012546  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001254b  jmp     loc_1800127BB
0x180012550  cmp     esi, 0FFFFFFFFh
0x180012553  jnz     short loc_180012595
0x180012555  mov     rcx, r14; void *
0x180012558  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18001255d  test    eax, eax
0x18001255f  jnz     short loc_180012586
0x180012561  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180012568  lea     ecx, [rax+4]; int
0x18001256b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012570  mov     ecx, 57h ; 'W'; dwErrCode
0x180012575  call    cs:__imp_SetLastError
0x18001257c  nop     dword ptr [rax+rax+00h]
0x180012581  jmp     loc_1800127BB
0x180012586  mov     rax, gs:60h
0x18001258f  mov     esi, [rax+2C0h]
0x180012595  mov     [rsp+98h+TokenInformation], 0
0x1800125a0  call    cs:__imp_GetCurrentProcess
0x1800125a7  nop     dword ptr [rax+rax+00h]
0x1800125ac  mov     rcx, rax; ProcessHandle
0x1800125af  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x1800125b4  mov     edx, 8; DesiredAccess
0x1800125b9  call    cs:__imp_OpenProcessToken
0x1800125c0  nop     dword ptr [rax+rax+00h]
0x1800125c5  test    eax, eax
0x1800125c7  jz      short loc_180012635
0x1800125c9  mov     [rsp+98h+arg_18], 0
0x1800125d4  lea     rax, [rsp+98h+arg_18]
0x1800125dc  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x1800125e1  mov     r9d, 4; TokenInformationLength
0x1800125e7  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x1800125ef  lea     edx, [r9+19h]; TokenInformationClass
0x1800125f3  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800125f8  call    cs:__imp_GetTokenInformation
0x1800125ff  nop     dword ptr [rax+rax+00h]
0x180012604  test    eax, eax
0x180012606  jnz     short loc_180012655
0x180012608  call    cs:__imp_GetLastError
0x18001260f  nop     dword ptr [rax+rax+00h]
0x180012614  mov     r8d, eax
0x180012617  lea     rdx, aGettokeninform_1; "GetTokenInformation failed: %d"
0x18001261e  mov     ecx, 4; int
0x180012623  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012628  mov     [rsp+98h+TokenInformation], 0
0x180012633  jmp     short loc_180012655
0x180012635  call    cs:__imp_GetLastError
0x18001263c  nop     dword ptr [rax+rax+00h]
0x180012641  mov     r8d, eax
0x180012644  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: %d"
0x18001264b  mov     ecx, 4; int
0x180012650  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012655  mov     r8d, 11h; MaxCount
0x18001265b  lea     rdx, String2; "WebAuthN_Channel"
0x180012662  mov     rcx, r15; String1
0x180012665  call    cs:__imp__strnicmp
0x18001266c  nop     dword ptr [rax+rax+00h]
0x180012671  xor     ecx, ecx
0x180012673  test    eax, eax
0x180012675  setz    cl
0x180012678  mov     [rsp+98h+arg_18], ecx
0x18001267f  cmp     [rsp+98h+TokenInformation], 0
0x180012687  jz      short loc_1800126E1
0x180012689  test    ecx, ecx
0x18001268b  jz      short loc_1800126E1
0x18001268d  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180012692  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012697  mov     [rsp+98h+var_48], 0
0x1800126a0  lea     rcx, [rsp+98h+arg_20]
0x1800126a8  mov     [rsp+98h+var_68], rcx
0x1800126ad  mov     ecx, [rsp+98h+arg_30]
0x1800126b4  mov     dword ptr [rsp+98h+var_70], ecx
0x1800126b8  mov     dword ptr [rsp+98h+ReturnLength], esi
0x1800126bc  mov     r9, rax
0x1800126bf  xor     r8d, r8d; pReturnValue
0x1800126c2  xor     edx, edx; nProcNum
0x1800126c4  lea     rcx, stru_18003B0D0; pProxyInfo
0x1800126cb  call    cs:__imp_NdrClientCall3
0x1800126d2  nop     dword ptr [rax+rax+00h]
0x1800126d7  mov     rbx, rax
0x1800126da  mov     [rsp+98h+var_48], rax
0x1800126df  jmp     short loc_180012737
0x1800126e1  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800126e6  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800126eb  mov     [rsp+98h+var_40], 0
0x1800126f4  lea     rcx, [rsp+98h+arg_20]
0x1800126fc  mov     [rsp+98h+var_60], rcx
0x180012701  mov     ecx, [rsp+98h+arg_30]
0x180012708  mov     dword ptr [rsp+98h+var_68], ecx
0x18001270c  mov     [rsp+98h+var_70], r15
0x180012711  mov     dword ptr [rsp+98h+ReturnLength], esi
0x180012715  mov     r9, rax
0x180012718  xor     r8d, r8d; pReturnValue
0x18001271b  xor     edx, edx; nProcNum
0x18001271d  lea     rcx, stru_180035140; pProxyInfo
0x180012724  call    cs:__imp_NdrClientCall3
0x18001272b  nop     dword ptr [rax+rax+00h]
0x180012730  mov     [rsp+98h+var_40], rax
0x180012735  mov     ebx, eax
0x180012737  mov     [rsp+98h+var_58], eax
0x18001273b  jmp     short loc_18001277B
0x18001273d  mov     r8d, eax
0x180012740  test    eax, eax
0x180012742  jle     short loc_18001274F
0x180012744  movzx   r8d, ax
0x180012748  or      r8d, 80070000h
0x18001274f  mov     ebx, r8d
0x180012752  mov     [rsp+98h+var_58], ebx
0x180012756  mov     eax, [rsp+98h+arg_18]
0x18001275d  mov     dword ptr [rsp+98h+ReturnLength], eax
0x180012761  mov     r9d, [rsp+98h+TokenInformation]
0x180012769  lea     rdx, aRpccreatevirtu_0; "RpcCreateVirtualChannel threw an except"...
0x180012770  mov     ecx, 8; int
0x180012775  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001277a  nop
0x18001277b  test    ebx, ebx
0x18001277d  jns     short loc_1800127BB
0x18001277f  lea     r9, aCreatevirtualc; "CreateVirtualChannel"
0x180012786  mov     r8d, ebx
0x180012789  lea     rdx, aRpccreatevirtu; "RpcCreateVirtualChannel failed: 0x%x in"...
0x180012790  mov     ecx, 8; int
0x180012795  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001279a  mov     ecx, ebx; int
0x18001279c  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800127a1  mov     ecx, eax; dwErrCode
0x1800127a3  call    cs:__imp_SetLastError
0x1800127aa  nop     dword ptr [rax+rax+00h]
0x1800127af  mov     [rsp+98h+arg_20], 0
0x1800127bb  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1800127c0  test    rcx, rcx
0x1800127c3  jz      short loc_1800127D1
0x1800127c5  call    cs:__imp_CloseHandle
0x1800127cc  nop     dword ptr [rax+rax+00h]
0x1800127d1  test    ebx, ebx
0x1800127d3  jns     short loc_1800127EA
0x1800127d5  mov     ecx, ebx; int
0x1800127d7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800127dc  mov     ecx, eax; dwErrCode
0x1800127de  call    cs:__imp_SetLastError
0x1800127e5  nop     dword ptr [rax+rax+00h]
0x1800127ea  mov     rbx, [rsp+98h+arg_20]
0x1800127f2  lea     rcx, [rsp+98h+var_38]; this
0x1800127f7  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800127fc  mov     rax, rbx
0x1800127ff  add     rsp, 78h
0x180012803  pop     r15
0x180012805  pop     r14
0x180012807  pop     rsi
0x180012808  pop     rbx
0x180012809  retn
0x180033577  push    rbp
0x180033579  sub     rsp, 40h
0x18003357d  mov     rbp, rdx
0x180033580  mov     rcx, [rcx]
0x180033583  mov     ecx, [rcx]; ExceptionCode
0x180033585  call    cs:__imp_I_RpcExceptionFilter
0x18003358c  nop     dword ptr [rax+rax+00h]
0x180033591  nop
0x180033592  add     rsp, 40h
0x180033596  pop     rbp
0x180033597  retn
```
