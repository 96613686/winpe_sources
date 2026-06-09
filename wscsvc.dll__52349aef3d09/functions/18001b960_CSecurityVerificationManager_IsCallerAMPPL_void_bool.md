# CSecurityVerificationManager::IsCallerAMPPL(void *,bool *)

- ea: `0x18001b960`
- end: `0x18001bb89`
- name: `?IsCallerAMPPL@CSecurityVerificationManager@@SAJPEAXPEA_N@Z`
- size: `553`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025520`
- `0x180031cd0`

## callees

- `0x180008e48`
- `0x18001b960`
- `0x18001bb90`
- `0x1800296d4`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18001ba28`
- `ntdll!NtQueryInformationProcess` at `0x18001ba28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001baf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001baf5`
- `RPCRT4!RpcRevertToSelf` at `0x18001ba57`
- `RPCRT4!RpcRevertToSelf` at `0x18001ba57`
- `RPCRT4!RpcImpersonateClient` at `0x18001b991`
- `RPCRT4!RpcImpersonateClient` at `0x18001b991`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b9da`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b9da`
- `RPCRT4!RpcRaiseException` at `0x18001bb43`
- `RPCRT4!RpcRaiseException` at `0x18001bb43`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b9f9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b9f9`

## string_xrefs

- `0x18001bade`: `admin\wsc\src\client\service\wscsvclib\verificationmanager.cpp`

## pseudocode

```c
__int64 __fastcall CSecurityVerificationManager::IsCallerAMPPL(RPC_BINDING_HANDLE ClientBinding, bool *a2)
{
  unsigned int v4; // eax
  int LastError; // eax
  unsigned int v6; // ebx
  HANDLE v7; // rax
  void *v8; // rbx
  NTSTATUS v9; // esi
  bool v10; // al
  unsigned int v11; // eax
  int v13; // esi
  int ReturnLength; // [rsp+20h] [rbp-B8h]
  char ProcessInformation; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v16[15]; // [rsp+31h] [rbp-A7h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-98h] BYREF
  __int64 v18; // [rsp+44h] [rbp-94h]
  int v19; // [rsp+4Ch] [rbp-8Ch]
  _BYTE v20[48]; // [rsp+50h] [rbp-88h] BYREF
  DWORD dwProcessId; // [rsp+80h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !ClientBinding )
    return 2147942487LL;
  *a2 = 0;
  v4 = RpcImpersonateClient(ClientBinding);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v4);
    }
    RpcRaiseException(5);
  }
  v19 = 0;
  RpcCallAttributes = 2;
  v18 = 16;
  memset_0(v20, 0, 0x68u);
  LastError = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  v6 = LastError;
  if ( LastError )
  {
    if ( LastError <= 0 )
      goto LABEL_15;
LABEL_14:
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
    CRpcImpersonateClient::~CRpcImpersonateClient((CRpcImpersonateClient *)v16);
    return v6;
  }
  v7 = OpenProcess(0x1000u, 0, dwProcessId);
  v8 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError <= 0 )
      goto LABEL_15;
    goto LABEL_14;
  }
  ProcessInformation = 0;
  v9 = NtQueryInformationProcess(v7, ProcessAffinityUpdateMode|ProcessUserModeIOPL, &ProcessInformation, 1u, 0);
  if ( v9 >= 0 || (v13 = v9 | 0x10000000, v13 >= 0) )
  {
    v10 = (unsigned __int8)((ProcessInformation & 7) - 1) <= 1u && (ProcessInformation & 0xF0) == 0x30;
    *a2 = v10;
    CloseHandle(v8);
    v11 = RpcRevertToSelf();
    if ( v11
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v11);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"admin\\wsc\\src\\client\\service\\wscsvclib\\verificationmanager.cpp",
      (const char *)(unsigned int)v13,
      ReturnLength);
    CloseHandle(v8);
    CRpcImpersonateClient::~CRpcImpersonateClient((CRpcImpersonateClient *)v16);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18001b960  mov     [rsp+arg_18], rbx
0x18001b965  push    rdi
0x18001b966  sub     rsp, 0D0h
0x18001b96d  mov     rax, cs:__security_cookie
0x18001b974  xor     rax, rsp
0x18001b977  mov     [rsp+0D8h+var_18], rax
0x18001b97f  mov     rdi, rdx
0x18001b982  mov     rbx, rcx
0x18001b985  test    rcx, rcx
0x18001b988  jz      loc_18001BA9A
0x18001b98e  mov     byte ptr [rdx], 0
0x18001b991  call    cs:__imp_RpcImpersonateClient
0x18001b997  test    eax, eax
0x18001b999  jnz     loc_18001BB0C
0x18001b99f  xor     eax, eax
0x18001b9a1  mov     [rsp+0D8h+arg_10], rsi
0x18001b9a9  xor     edx, edx; Val
0x18001b9ab  mov     [rsp+0D8h+var_8C], eax
0x18001b9af  mov     r8d, 68h ; 'h'; Size
0x18001b9b5  mov     [rsp+0D8h+RpcCallAttributes], 2
0x18001b9bd  lea     rcx, [rsp+0D8h+var_88]; void *
0x18001b9c2  mov     [rsp+0D8h+var_94], 10h
0x18001b9cb  xor     esi, esi
0x18001b9cd  call    memset_0
0x18001b9d2  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x18001b9d7  mov     rcx, rbx; ClientBinding
0x18001b9da  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b9e0  mov     ebx, eax
0x18001b9e2  test    eax, eax
0x18001b9e4  jnz     loc_18001BAC6
0x18001b9ea  mov     r8d, [rsp+0D8h+dwProcessId]; dwProcessId
0x18001b9f2  xor     edx, edx; bInheritHandle
0x18001b9f4  mov     ecx, 1000h; dwDesiredAccess
0x18001b9f9  call    cs:__imp_OpenProcess
0x18001b9ff  mov     rbx, rax
0x18001ba02  test    rax, rax
0x18001ba05  jz      loc_18001BAB8
0x18001ba0b  mov     r9d, 1; ProcessInformationLength
0x18001ba11  mov     [rsp+0D8h+ProcessInformation], sil
0x18001ba16  lea     r8, [rsp+0D8h+ProcessInformation]; ProcessInformation
0x18001ba1b  mov     qword ptr [rsp+0D8h+ReturnLength], rsi; int
0x18001ba20  mov     edx, 3Dh ; '='; ProcessInformationClass
0x18001ba25  mov     rcx, rax; ProcessHandle
0x18001ba28  call    cs:__imp_NtQueryInformationProcess
0x18001ba2e  mov     esi, eax
0x18001ba30  test    eax, eax
0x18001ba32  js      loc_18001BACA
0x18001ba38  movzx   eax, [rsp+0D8h+ProcessInformation]
0x18001ba3d  movzx   ecx, al
0x18001ba40  and     cl, 7
0x18001ba43  dec     cl
0x18001ba45  cmp     cl, 1
0x18001ba48  jbe     short loc_18001BA90
0x18001ba4a  xor     al, al
0x18001ba4c  mov     rcx, rbx; hObject
0x18001ba4f  mov     [rdi], al
0x18001ba51  call    cs:__imp_CloseHandle
0x18001ba57  call    cs:__imp_RpcRevertToSelf
0x18001ba5d  test    eax, eax
0x18001ba5f  jnz     loc_18001BB4A
0x18001ba65  xor     eax, eax
0x18001ba67  mov     rsi, [rsp+0D8h+arg_10]
0x18001ba6f  mov     rcx, [rsp+0D8h+var_18]
0x18001ba77  xor     rcx, rsp; StackCookie
0x18001ba7a  call    __security_check_cookie
0x18001ba7f  mov     rbx, [rsp+0D8h+arg_18]
0x18001ba87  add     rsp, 0D0h
0x18001ba8e  pop     rdi
0x18001ba8f  retn
0x18001ba90  and     al, 0F0h
0x18001ba92  cmp     al, 30h ; '0'
0x18001ba94  jnz     short loc_18001BA4A
0x18001ba96  mov     al, 1
0x18001ba98  jmp     short loc_18001BA4C
0x18001ba9a  mov     eax, 80070057h
0x18001ba9f  jmp     short loc_18001BA6F
0x18001baa1  movzx   ebx, ax
0x18001baa4  or      ebx, 80070000h
0x18001baaa  lea     rcx, [rsp+0D8h+var_A7]; this
0x18001baaf  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x18001bab4  mov     eax, ebx
0x18001bab6  jmp     short loc_18001BA67
0x18001bab8  call    cs:__imp_GetLastError
0x18001babe  mov     ebx, eax
0x18001bac0  test    eax, eax
0x18001bac2  jle     short loc_18001BAAA
0x18001bac4  jmp     short loc_18001BAA1
0x18001bac6  jle     short loc_18001BAAA
0x18001bac8  jmp     short loc_18001BAA1
0x18001baca  or      esi, 10000000h
0x18001bad0  jge     loc_18001BA38
0x18001bad6  mov     rcx, [rsp+0D8h]; this
0x18001bade  lea     r8, aAdminWscSrcCli; "admin\\wsc\\src\\client\\service\\wscsv"...
0x18001bae5  mov     r9d, esi; char *
0x18001bae8  mov     edx, 66h ; 'f'; void *
0x18001baed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001baf2  mov     rcx, rbx; hObject
0x18001baf5  call    cs:__imp_CloseHandle
0x18001bafb  lea     rcx, [rsp+0D8h+var_A7]; this
0x18001bb00  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x18001bb05  mov     eax, esi
0x18001bb07  jmp     loc_18001BA67
0x18001bb0c  mov     r10, cs:WPP_GLOBAL_Control
0x18001bb13  lea     rcx, WPP_GLOBAL_Control
0x18001bb1a  cmp     r10, rcx
0x18001bb1d  jz      short loc_18001BB3E
0x18001bb1f  test    byte ptr [r10+1Ch], 1
0x18001bb24  jz      short loc_18001BB3E
0x18001bb26  mov     rcx, [r10+10h]
0x18001bb2a  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001bb31  mov     edx, 1Bh
0x18001bb36  mov     r9d, eax
0x18001bb39  call    WPP_SF_d
0x18001bb3e  mov     ecx, 5; exception
0x18001bb43  call    cs:__imp_RpcRaiseException
0x18001bb49  int     3; Trap to Debugger
0x18001bb4a  mov     r10, cs:WPP_GLOBAL_Control
0x18001bb51  lea     rcx, WPP_GLOBAL_Control
0x18001bb58  cmp     r10, rcx
0x18001bb5b  jz      loc_18001BA65
0x18001bb61  test    byte ptr [r10+1Ch], 1
0x18001bb66  jz      loc_18001BA65
0x18001bb6c  mov     rcx, [r10+10h]
0x18001bb70  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001bb77  mov     edx, 1Ch
0x18001bb7c  mov     r9d, eax
0x18001bb7f  call    WPP_SF_d
0x18001bb84  jmp     loc_18001BA65
```
