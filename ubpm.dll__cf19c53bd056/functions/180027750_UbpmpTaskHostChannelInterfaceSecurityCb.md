# UbpmpTaskHostChannelInterfaceSecurityCb

- ea: `0x180027750`
- end: `0x18002798d`
- name: `UbpmpTaskHostChannelInterfaceSecurityCb`
- size: `573`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180027750`
- `0x180032e38`
- `0x18003c388`
- `0x18003cbc0`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180027863`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180027863`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800278b3`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800278b3`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027820`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800277e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800277e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800277f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800277f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800278c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800278c7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002779b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002779b`
- `RPCRT4!RpcImpersonateClient` at `0x1800277d4`
- `RPCRT4!RpcImpersonateClient` at `0x1800277d4`
- `RPCRT4!RpcRevertToSelf` at `0x180027806`
- `RPCRT4!RpcRevertToSelf` at `0x180027930`
- `RPCRT4!RpcRevertToSelf` at `0x180027806`
- `RPCRT4!RpcRevertToSelf` at `0x180027930`

## pseudocode

```c
__int64 __fastcall UbpmpTaskHostChannelInterfaceSecurityCb(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // eax
  __int64 v4; // r8
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  void *v7; // r15
  int v8; // r14d
  _UNKNOWN **v9; // rsi
  _UNKNOWN **v10; // r9
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD v15; // eax
  WINBOOL IsMember; // [rsp+30h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-71h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v19[36]; // [rsp+44h] [rbp-65h] BYREF
  int v20; // [rsp+68h] [rbp-41h]
  int v21; // [rsp+6Ch] [rbp-3Dh]
  int v22; // [rsp+70h] [rbp-39h]
  int v23; // [rsp+78h] [rbp-31h]

  memset_0(v19, 0, 0x74u);
  TokenHandle = 0;
  RpcCallAttributes = 3;
  v3 = RpcServerInqCallAttributesW(Context, &RpcCallAttributes);
  LastError = v3;
  if ( v3 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v13 = 129;
    v14 = v3;
LABEL_26:
    WPP_SF_D(v12[2], v13, v4, v14);
    goto LABEL_19;
  }
  if ( v23 != 3 || v22 || v20 != 6 || v21 != 10 )
  {
LABEL_22:
    LastError = 5;
    goto LABEL_19;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_19;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    RpcRevertToSelf();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v13 = 130;
    v14 = LastError;
    goto LABEL_26;
  }
  RpcRevertToSelf();
  v7 = TokenHandle;
  IsMember = LastError;
  v8 = 1168;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  v9 = (_UNKNOWN **)g_leTaskHostContextListHead;
  while ( v9 != &g_leTaskHostContextListHead )
  {
    v10 = v9 - 1;
    v9 = (_UNKNOWN **)*v9;
    if ( ((_BYTE)v10[13] & 0x84) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 89);
    }
    else
    {
      if ( !CheckTokenMembership(v7, v10[22], &IsMember) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v15);
        }
        break;
      }
      if ( IsMember == 1 )
      {
        v8 = 0;
        break;
      }
    }
  }
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  if ( v8 )
    goto LABEL_22;
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180027750  push    rbp
0x180027752  push    rbx
0x180027753  push    rsi
0x180027754  push    rdi
0x180027755  push    r14
0x180027757  push    r15
0x180027759  lea     rbp, [rsp-2Fh]
0x18002775e  sub     rsp, 0D8h
0x180027765  mov     rax, cs:__security_cookie
0x18002776c  xor     rax, rsp
0x18002776f  mov     [rbp+57h+var_40], rax
0x180027773  mov     rbx, rdx
0x180027776  lea     rcx, [rbp+57h+var_BC]; void *
0x18002777a  xor     edx, edx; Val
0x18002777c  lea     r8d, [rdx+74h]; Size
0x180027780  call    memset_0
0x180027785  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180027789  mov     [rbp+57h+TokenHandle], 0
0x180027791  mov     rcx, rbx; ClientBinding
0x180027794  mov     [rbp+57h+RpcCallAttributes], 3
0x18002779b  call    cs:__imp_RpcServerInqCallAttributesW
0x1800277a1  mov     ebx, eax
0x1800277a3  test    eax, eax
0x1800277a5  jnz     loc_1800278F2
0x1800277ab  cmp     [rbp+57h+var_88], 3
0x1800277af  jnz     loc_1800278EB
0x1800277b5  cmp     [rbp+57h+var_90], eax
0x1800277b8  jnz     loc_1800278EB
0x1800277be  cmp     [rbp+57h+var_98], 6
0x1800277c2  jnz     loc_1800278EB
0x1800277c8  cmp     [rbp+57h+var_94], 0Ah
0x1800277cc  jnz     loc_1800278EB
0x1800277d2  xor     ecx, ecx; BindingHandle
0x1800277d4  call    cs:__imp_RpcImpersonateClient
0x1800277da  mov     ebx, eax
0x1800277dc  test    eax, eax
0x1800277de  jnz     loc_1800278BE
0x1800277e4  call    cs:__imp_GetCurrentThread
0x1800277ea  mov     rcx, rax; ThreadHandle
0x1800277ed  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800277f1  lea     edx, [rbx+8]; DesiredAccess
0x1800277f4  lea     r8d, [rbx+1]; OpenAsSelf
0x1800277f8  call    cs:__imp_OpenThreadToken
0x1800277fe  test    eax, eax
0x180027800  jz      loc_180027928
0x180027806  call    cs:__imp_RpcRevertToSelf
0x18002780c  mov     r15, [rbp+57h+TokenHandle]
0x180027810  lea     rcx, g_TaskHostContextListLock
0x180027817  mov     [rbp+57h+IsMember], ebx
0x18002781a  mov     r14d, 490h
0x180027820  call    cs:__imp_RtlAcquireSRWLockShared
0x180027826  mov     rsi, cs:g_leTaskHostContextListHead
0x18002782d  lea     rdi, WPP_GLOBAL_Control
0x180027834  mov     rcx, cs:WPP_GLOBAL_Control
0x18002783b  lea     rax, g_leTaskHostContextListHead
0x180027842  cmp     rsi, rax
0x180027845  jz      short loc_1800278AC
0x180027847  lea     r9, [rsi-8]
0x18002784b  mov     rsi, [rsi]
0x18002784e  test    byte ptr [r9+68h], 84h
0x180027853  jnz     short loc_180027878
0x180027855  mov     rdx, [r9+0B0h]; SidToCheck
0x18002785c  lea     r8, [rbp+57h+IsMember]; IsMember
0x180027860  mov     rcx, r15; TokenHandle
0x180027863  call    cs:__imp_CheckTokenMembership
0x180027869  test    eax, eax
0x18002786b  jz      short loc_18002789C
0x18002786d  cmp     [rbp+57h+IsMember], 1
0x180027871  jnz     short loc_180027834
0x180027873  xor     r14d, r14d
0x180027876  jmp     short loc_1800278AC
0x180027878  cmp     rcx, rdi
0x18002787b  jz      short loc_18002783B
0x18002787d  test    byte ptr [rcx+1Ch], 2
0x180027881  jz      short loc_18002783B
0x180027883  movzx   eax, byte ptr [r9+68h]
0x180027888  mov     edx, 59h ; 'Y'
0x18002788d  mov     rcx, [rcx+10h]
0x180027891  mov     [rsp+100h+var_E0], eax
0x180027895  call    WPP_SF_qd
0x18002789a  jmp     short loc_180027834
0x18002789c  mov     rax, cs:WPP_GLOBAL_Control
0x1800278a3  cmp     rax, rdi
0x1800278a6  jnz     loc_180027959
0x1800278ac  lea     rcx, g_TaskHostContextListLock
0x1800278b3  call    cs:__imp_RtlReleaseSRWLockShared
0x1800278b9  test    r14d, r14d
0x1800278bc  jnz     short loc_1800278EB
0x1800278be  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800278c2  test    rcx, rcx
0x1800278c5  jz      short loc_1800278CD
0x1800278c7  call    cs:__imp_CloseHandle
0x1800278cd  mov     eax, ebx
0x1800278cf  mov     rcx, [rbp+57h+var_40]
0x1800278d3  xor     rcx, rsp; StackCookie
0x1800278d6  call    __security_check_cookie
0x1800278db  add     rsp, 0D8h
0x1800278e2  pop     r15
0x1800278e4  pop     r14
0x1800278e6  pop     rdi
0x1800278e7  pop     rsi
0x1800278e8  pop     rbx
0x1800278e9  pop     rbp
0x1800278ea  retn
0x1800278eb  mov     ebx, 5
0x1800278f0  jmp     short loc_1800278BE
0x1800278f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278f9  lea     rdi, WPP_GLOBAL_Control
0x180027900  cmp     rcx, rdi
0x180027903  jz      short loc_1800278BE
0x180027905  test    byte ptr [rcx+1Ch], 1
0x180027909  jz      short loc_1800278BE
0x18002790b  mov     edx, 81h
0x180027910  mov     r9d, eax
0x180027913  jmp     short loc_18002791D
0x180027915  mov     edx, 82h
0x18002791a  mov     r9d, ebx
0x18002791d  mov     rcx, [rcx+10h]
0x180027921  call    WPP_SF_D
0x180027926  jmp     short loc_1800278BE
0x180027928  call    cs:__imp_GetLastError
0x18002792e  mov     ebx, eax
0x180027930  call    cs:__imp_RpcRevertToSelf
0x180027936  mov     rcx, cs:WPP_GLOBAL_Control
0x18002793d  lea     rdi, WPP_GLOBAL_Control
0x180027944  cmp     rcx, rdi
0x180027947  jz      loc_1800278BE
0x18002794d  test    byte ptr [rcx+1Ch], 1
0x180027951  jz      loc_1800278BE
0x180027957  jmp     short loc_180027915
0x180027959  test    byte ptr [rax+1Ch], 1
0x18002795d  jz      loc_1800278AC
0x180027963  call    cs:__imp_GetLastError
0x180027969  mov     rcx, cs:WPP_GLOBAL_Control
0x180027970  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180027977  mov     edx, 5Ah ; 'Z'
0x18002797c  mov     r9d, eax
0x18002797f  mov     rcx, [rcx+10h]
0x180027983  call    WPP_SF_d
0x180027988  jmp     loc_1800278AC
```
