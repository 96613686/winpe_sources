# ScCheckServiceProtectedProcess(void *,uchar)

- ea: `0x140008548`
- end: `0x1400089c2`
- name: `?ScCheckServiceProtectedProcess@@YAKPEAXE@Z`
- size: `1146`
- prototype: `unsigned int __fastcall(void *, unsigned __int8)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140007d80`
- `0x140068b60`
- `0x14006a9e0`
- `0x14006b060`
- `0x140081f50`

## callees

- `0x140004c58`
- `0x140008548`
- `0x140013b0c`
- `0x14001f99c`
- `0x14004401c`
- `0x1400575b0`
- `0x140081b6c`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400085cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400085cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008992`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400087f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400087f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008870`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140008737`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140008737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140008722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140008722`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008984`
- `RPCRT4!RpcImpersonateClient` at `0x140008709`
- `RPCRT4!RpcImpersonateClient` at `0x140008709`
- `RPCRT4!RpcRevertToSelf` at `0x14000874a`
- `RPCRT4!RpcRevertToSelf` at `0x14000874a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14000864d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14000864d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400087ee`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400087ee`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140008841`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140008841`
- `ntdll!RtlEqualSid` at `0x1400086f9`
- `ntdll!RtlEqualSid` at `0x1400086f9`
- `ntdll!RtlTestProtectedAccess` at `0x140008915`
- `ntdll!RtlTestProtectedAccess` at `0x140008915`
- `ntdll!RtlInitUnicodeString` at `0x1400085ab`
- `ntdll!RtlInitUnicodeString` at `0x1400085ab`
- `ntdll!RtlFreeHeap` at `0x140008975`
- `ntdll!RtlFreeHeap` at `0x140008975`
- `ntdll!RtlCreateServiceSid` at `0x1400086e0`
- `ntdll!RtlCreateServiceSid` at `0x1400086e0`
- `ntdll!NtQueryInformationProcess` at `0x1400088b3`
- `ntdll!NtQueryInformationProcess` at `0x1400088b3`

## string_xrefs

- `0x140008591`: `TrustedInstaller`

## pseudocode

```c
__int64 __fastcall ScCheckServiceProtectedProcess(_QWORD *a1, char a2)
{
  PVOID v2; // rsi
  __int64 v5; // rbx
  unsigned int v7; // edi
  NTSTATUS v8; // eax
  RPC_STATUS v9; // eax
  DWORD LastError; // r15d
  HANDLE CurrentThread; // rax
  unsigned int v12; // r14d
  PRPC_ASYNC_STATE v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HANDLE v16; // rax
  void *v17; // r14
  DWORD v18; // eax
  NTSTATUS InformationProcess; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  _BYTE ProcessInformation[4]; // [rsp+30h] [rbp-69h] BYREF
  WINBOOL IsMember; // [rsp+34h] [rbp-65h] BYREF
  unsigned int Pid; // [rsp+38h] [rbp-61h] BYREF
  PVOID P; // [rsp+40h] [rbp-59h] BYREF
  ULONG ServiceSidLength; // [rsp+48h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-49h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  _BYTE ServiceSid[80]; // [rsp+70h] [rbp-29h] BYREF

  v2 = 0;
  Pid = 0;
  P = 0;
  TokenHandle = 0;
  IsMember = 0;
  ProcessInformation[0] = 0;
  ServiceSidLength = 68;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"TrustedInstaller");
  v5 = a1[2];
  if ( (*(_BYTE *)(v5 + 80) & 0x30) == 0 )
    return 0;
  AcquireSRWLockShared((PSRWLOCK)(v5 + 312));
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 224LL))(v5)
    || a2
    && ((*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 224LL))(v5) == 2
     || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 224LL))(v5) == 1
     || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 224LL))(v5) == 4) )
  {
    goto LABEL_52;
  }
  v7 = 5;
  if ( !I_RpcBindingInqLocalClientPID(0, &Pid) )
  {
    if ( ScGetClientSid((struct _TOKEN_USER **)&P) )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 58, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
      v2 = P;
      goto LABEL_53;
    }
    v8 = RtlCreateServiceSid(&DestinationString, ServiceSid, &ServiceSidLength);
    v2 = P;
    if ( v8 )
      goto LABEL_38;
    if ( !RtlEqualSid(ServiceSid, *(PSID *)P) )
    {
      v9 = RpcImpersonateClient(0);
      if ( v9 )
      {
        ScLogImpersonateFailureEvent(v9);
        goto LABEL_53;
      }
      LastError = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        LastError = GetLastError();
      v12 = RpcRevertToSelf();
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v14 = 59;
          v15 = LastError;
LABEL_27:
          WPP_SF_d(v13->StubInfo, v14, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v15);
          goto LABEL_53;
        }
        goto LABEL_53;
      }
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 60, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v12);
        }
        ScLogEvent(5u, L"RpcRevertToSelf", v12);
        goto LABEL_53;
      }
      if ( !CheckTokenMembership(TokenHandle, ServiceSid, &IsMember) )
      {
        v15 = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v14 = 61;
          goto LABEL_27;
        }
LABEL_53:
        if ( v2 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
        goto LABEL_55;
      }
      if ( !IsMember )
      {
LABEL_38:
        v16 = OpenProcess(0x1000u, 0, Pid);
        v17 = v16;
        if ( v16 )
        {
          InformationProcess = NtQueryInformationProcess(
                                 v16,
                                 ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                                 ProcessInformation,
                                 1u,
                                 0);
          if ( InformationProcess >= 0 )
          {
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v5 + 224LL))(
                    v5,
                    v20,
                    v21,
                    (unsigned int)InformationProcess);
            LOBYTE(v23) = ProcessInformation[0];
            v24 = 3LL * v22;
            LOBYTE(v24) = *((_BYTE *)qword_1400BAF08 + 12 * v22);
            if ( (unsigned __int8)RtlTestProtectedAccess(v23, v24) )
            {
              v7 = 0;
            }
            else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                   && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->StubInfo, 64, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                 && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->StubInfo,
              63,
              WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
              (unsigned int)InformationProcess);
          }
          CloseHandle(v17);
        }
        else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
               && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v18 = GetLastError();
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 62, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v18);
        }
        goto LABEL_53;
      }
    }
LABEL_52:
    v7 = 0;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 57, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
LABEL_55:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 != -312 )
    ReleaseSRWLockShared((PSRWLOCK)(v5 + 312));
  return v7;
}

```

## disassembly

```asm
0x140008548  mov     [rsp-8+arg_8], rbx
0x14000854d  mov     [rsp-8+arg_10], rsi
0x140008552  push    rbp
0x140008553  push    rdi
0x140008554  push    r12
0x140008556  push    r14
0x140008558  push    r15
0x14000855a  lea     rbp, [rsp-37h]
0x14000855f  sub     rsp, 0D0h
0x140008566  mov     rax, cs:__security_cookie
0x14000856d  xor     rax, rsp
0x140008570  mov     [rbp+57h+var_30], rax
0x140008574  xor     esi, esi
0x140008576  mov     [rbp+57h+Pid], 0
0x14000857d  mov     dil, dl
0x140008580  mov     [rbp+57h+P], rsi
0x140008584  mov     rbx, rcx
0x140008587  mov     [rbp+57h+TokenHandle], rsi
0x14000858b  xorps   xmm0, xmm0
0x14000858e  mov     [rbp+57h+IsMember], esi
0x140008591  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x140008598  mov     [rbp+57h+ProcessInformation], 0
0x14000859c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400085a0  mov     [rbp+57h+ServiceSidLength], 44h ; 'D'
0x1400085a7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400085ab  call    cs:__imp_RtlInitUnicodeString
0x1400085b1  mov     rbx, [rbx+10h]
0x1400085b5  test    byte ptr [rbx+50h], 30h
0x1400085b9  jnz     short loc_1400085C2
0x1400085bb  xor     eax, eax
0x1400085bd  jmp     loc_14000899A
0x1400085c2  lea     r12, [rbx+138h]
0x1400085c9  mov     rcx, r12; SRWLock
0x1400085cc  call    cs:__imp_AcquireSRWLockShared
0x1400085d2  mov     rax, [rbx]
0x1400085d5  mov     rcx, rbx
0x1400085d8  mov     rax, [rax+0E0h]
0x1400085df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085e4  test    eax, eax
0x1400085e6  jz      loc_14000895C
0x1400085ec  test    dil, dil
0x1400085ef  jz      short loc_140008642
0x1400085f1  mov     rax, [rbx]
0x1400085f4  mov     rcx, rbx
0x1400085f7  mov     rax, [rax+0E0h]
0x1400085fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008603  cmp     eax, 2
0x140008606  jz      loc_14000895C
0x14000860c  mov     rax, [rbx]
0x14000860f  mov     rcx, rbx
0x140008612  mov     rax, [rax+0E0h]
0x140008619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000861e  cmp     eax, 1
0x140008621  jz      loc_14000895C
0x140008627  mov     rax, [rbx]
0x14000862a  mov     rcx, rbx
0x14000862d  mov     rax, [rax+0E0h]
0x140008634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008639  cmp     eax, 4
0x14000863c  jz      loc_14000895C
0x140008642  lea     rdx, [rbp+57h+Pid]; Pid
0x140008646  xor     ecx, ecx; Binding
0x140008648  mov     edi, 5
0x14000864d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x140008653  test    eax, eax
0x140008655  jz      short loc_140008690
0x140008657  mov     rcx, cs:WPP_GLOBAL_Control
0x14000865e  lea     rax, WPP_GLOBAL_Control
0x140008665  cmp     rcx, rax
0x140008668  jz      loc_14000897B
0x14000866e  test    byte ptr [rcx+1Ch], 1
0x140008672  jz      loc_14000897B
0x140008678  mov     rcx, [rcx+10h]
0x14000867c  lea     edx, [rdi+34h]
0x14000867f  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140008686  call    WPP_SF_
0x14000868b  jmp     loc_14000897B
0x140008690  lea     rcx, [rbp+57h+P]; struct _TOKEN_USER **
0x140008694  call    ?ScGetClientSid@@YAKPEAPEAU_TOKEN_USER@@@Z; ScGetClientSid(_TOKEN_USER * *)
0x140008699  test    eax, eax
0x14000869b  jz      short loc_1400086D4
0x14000869d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086a4  lea     rax, WPP_GLOBAL_Control
0x1400086ab  cmp     rcx, rax
0x1400086ae  jz      short loc_1400086CB
0x1400086b0  test    byte ptr [rcx+1Ch], 1
0x1400086b4  jz      short loc_1400086CB
0x1400086b6  mov     rcx, [rcx+10h]
0x1400086ba  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400086c1  mov     edx, 3Ah ; ':'
0x1400086c6  call    WPP_SF_
0x1400086cb  mov     rsi, [rbp+57h+P]
0x1400086cf  jmp     loc_14000895E
0x1400086d4  lea     r8, [rbp+57h+ServiceSidLength]; ServiceSidLength
0x1400086d8  lea     rdx, [rbp+57h+ServiceSid]; ServiceSid
0x1400086dc  lea     rcx, [rbp+57h+DestinationString]; ServiceName
0x1400086e0  call    cs:__imp_RtlCreateServiceSid
0x1400086e6  mov     rsi, [rbp+57h+P]
0x1400086ea  test    eax, eax
0x1400086ec  jnz     loc_140008836
0x1400086f2  mov     rdx, [rsi]; Sid2
0x1400086f5  lea     rcx, [rbp+57h+ServiceSid]; Sid1
0x1400086f9  call    cs:__imp_RtlEqualSid
0x1400086ff  test    al, al
0x140008701  jnz     loc_14000895C
0x140008707  xor     ecx, ecx; BindingHandle
0x140008709  call    cs:__imp_RpcImpersonateClient
0x14000870f  test    eax, eax
0x140008711  jz      short loc_14000871F
0x140008713  mov     ecx, eax; int
0x140008715  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x14000871a  jmp     loc_14000895E
0x14000871f  xor     r15d, r15d
0x140008722  call    cs:__imp_GetCurrentThread
0x140008728  mov     rcx, rax; ThreadHandle
0x14000872b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14000872f  lea     edx, [r15+8]; DesiredAccess
0x140008733  lea     r8d, [r15+1]; OpenAsSelf
0x140008737  call    cs:__imp_OpenThreadToken
0x14000873d  test    eax, eax
0x14000873f  jnz     short loc_14000874A
0x140008741  call    cs:__imp_GetLastError
0x140008747  mov     r15d, eax
0x14000874a  call    cs:__imp_RpcRevertToSelf
0x140008750  mov     r14d, eax
0x140008753  test    r15d, r15d
0x140008756  jz      short loc_140008796
0x140008758  mov     rcx, cs:WPP_GLOBAL_Control
0x14000875f  lea     rax, WPP_GLOBAL_Control
0x140008766  cmp     rcx, rax
0x140008769  jz      loc_14000895E
0x14000876f  test    byte ptr [rcx+1Ch], 1
0x140008773  jz      loc_14000895E
0x140008779  mov     edx, 3Bh ; ';'
0x14000877e  mov     r9d, r15d
0x140008781  mov     rcx, [rcx+10h]
0x140008785  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x14000878c  call    WPP_SF_d
0x140008791  jmp     loc_14000895E
0x140008796  test    r14d, r14d
0x140008799  jz      short loc_1400087E2
0x14000879b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087a2  lea     rax, WPP_GLOBAL_Control
0x1400087a9  cmp     rcx, rax
0x1400087ac  jz      short loc_1400087CC
0x1400087ae  test    byte ptr [rcx+1Ch], 1
0x1400087b2  jz      short loc_1400087CC
0x1400087b4  mov     rcx, [rcx+10h]
0x1400087b8  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400087bf  mov     edx, 3Ch ; '<'
0x1400087c4  mov     r9d, r14d
0x1400087c7  call    WPP_SF_d
0x1400087cc  mov     r8d, r14d
0x1400087cf  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x1400087d6  mov     ecx, edi; unsigned int
0x1400087d8  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x1400087dd  jmp     loc_14000895E
0x1400087e2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400087e6  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400087ea  lea     rdx, [rbp+57h+ServiceSid]; SidToCheck
0x1400087ee  call    cs:__imp_CheckTokenMembership
0x1400087f4  test    eax, eax
0x1400087f6  jnz     short loc_14000882C
0x1400087f8  call    cs:__imp_GetLastError
0x1400087fe  mov     r9d, eax
0x140008801  mov     rcx, cs:WPP_GLOBAL_Control
0x140008808  lea     rax, WPP_GLOBAL_Control
0x14000880f  cmp     rcx, rax
0x140008812  jz      loc_14000895E
0x140008818  test    byte ptr [rcx+1Ch], 1
0x14000881c  jz      loc_14000895E
0x140008822  mov     edx, 3Dh ; '='
0x140008827  jmp     loc_140008781
0x14000882c  cmp     [rbp+57h+IsMember], 0
0x140008830  jnz     loc_14000895C
0x140008836  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x14000883a  xor     edx, edx; bInheritHandle
0x14000883c  mov     ecx, 1000h; dwDesiredAccess
0x140008841  call    cs:__imp_OpenProcess
0x140008847  mov     r14, rax
0x14000884a  test    rax, rax
0x14000884d  jnz     short loc_140008899
0x14000884f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008856  lea     rax, WPP_GLOBAL_Control
0x14000885d  cmp     rcx, rax
0x140008860  jz      loc_14000895E
0x140008866  test    byte ptr [rcx+1Ch], 1
0x14000886a  jz      loc_14000895E
0x140008870  call    cs:__imp_GetLastError
0x140008876  mov     rcx, cs:WPP_GLOBAL_Control
0x14000887d  lea     edx, [r14+3Eh]
0x140008881  mov     r9d, eax
0x140008884  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x14000888b  mov     rcx, [rcx+10h]
0x14000888f  call    WPP_SF_d
0x140008894  jmp     loc_14000895E
0x140008899  mov     r9d, 1; ProcessInformationLength
0x14000889f  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x1400088a8  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1400088ac  mov     rcx, r14; ProcessHandle
0x1400088af  lea     edx, [r9+3Ch]; ProcessInformationClass
0x1400088b3  call    cs:__imp_NtQueryInformationProcess
0x1400088b9  mov     r9d, eax
0x1400088bc  test    eax, eax
0x1400088be  jns     short loc_1400088F0
0x1400088c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088c7  lea     rax, WPP_GLOBAL_Control
0x1400088ce  cmp     rcx, rax
0x1400088d1  jz      short loc_140008951
0x1400088d3  test    byte ptr [rcx+1Ch], 1
0x1400088d7  jz      short loc_140008951
0x1400088d9  mov     rcx, [rcx+10h]
0x1400088dd  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400088e4  mov     edx, 3Fh ; '?'
0x1400088e9  call    WPP_SF_d
0x1400088ee  jmp     short loc_140008951
0x1400088f0  mov     rax, [rbx]
0x1400088f3  mov     rcx, rbx
0x1400088f6  mov     rax, [rax+0E0h]
0x1400088fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008902  mov     cl, [rbp+57h+ProcessInformation]
0x140008905  mov     eax, eax
0x140008907  lea     rdx, [rax+rax*2]
0x14000890b  lea     rax, qword_1400BAF08
0x140008912  mov     dl, [rax+rdx*4]
0x140008915  call    cs:__imp_RtlTestProtectedAccess
0x14000891b  test    al, al
0x14000891d  jnz     short loc_14000894F
0x14000891f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008926  lea     rax, WPP_GLOBAL_Control
0x14000892d  cmp     rcx, rax
0x140008930  jz      short loc_140008951
0x140008932  test    byte ptr [rcx+1Ch], 1
0x140008936  jz      short loc_140008951
0x140008938  mov     rcx, [rcx+10h]
0x14000893c  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140008943  mov     edx, 40h ; '@'
0x140008948  call    WPP_SF_
0x14000894d  jmp     short loc_140008951
0x14000894f  xor     edi, edi
0x140008951  mov     rcx, r14; hObject
0x140008954  call    cs:__imp_CloseHandle
0x14000895a  jmp     short loc_14000895E
0x14000895c  xor     edi, edi
0x14000895e  test    rsi, rsi
0x140008961  jz      short loc_14000897B
0x140008963  mov     rcx, gs:60h
0x14000896c  mov     r8, rsi; P
0x14000896f  xor     edx, edx; Flags
0x140008971  mov     rcx, [rcx+30h]; HeapHandle
0x140008975  call    cs:__imp_RtlFreeHeap
0x14000897b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14000897f  test    rcx, rcx
0x140008982  jz      short loc_14000898A
0x140008984  call    cs:__imp_CloseHandle
0x14000898a  test    r12, r12
0x14000898d  jz      short loc_140008998
0x14000898f  mov     rcx, r12; SRWLock
0x140008992  call    cs:__imp_ReleaseSRWLockShared
0x140008998  mov     eax, edi
0x14000899a  mov     rcx, [rbp+57h+var_30]
0x14000899e  xor     rcx, rsp; StackCookie
0x1400089a1  call    __security_check_cookie
0x1400089a6  lea     r11, [rsp+0F0h+var_20]
0x1400089ae  mov     rbx, [r11+38h]
0x1400089b2  mov     rsi, [r11+40h]
0x1400089b6  mov     rsp, r11
0x1400089b9  pop     r15
0x1400089bb  pop     r14
0x1400089bd  pop     r12
0x1400089bf  pop     rdi
0x1400089c0  pop     rbp
0x1400089c1  retn
```
