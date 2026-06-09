# WxRpcBindingCreate(ushort const *,void * *)

- ea: `0x18001e408`
- end: `0x18001e62b`
- name: `?WxRpcBindingCreate@@YAJPEBGPEAPEAX@Z`
- size: `547`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001de88`
- `0x1801299d4`

## callees

- `0x18001e408`
- `0x1800701d0`
- `0x18014a7a0`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e4f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e4f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e4e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e4e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e58a`
- `RPCRT4!RpcBindingFree` at `0x18001e61b`
- `RPCRT4!RpcBindingFree` at `0x18001e61b`
- `RPCRT4!RpcBindingCreateW` at `0x18001e54c`
- `RPCRT4!RpcBindingCreateW` at `0x18001e54c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e51f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e51f`

## pseudocode

```c
__int64 __fastcall WxRpcBindingCreate(unsigned __int16 *a1, void **a2)
{
  HANDLE CurrentProcess; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  RPC_STATUS v9; // eax
  signed int v10; // ebx
  int v12; // eax
  int LastError; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+44h] [rbp-BCh]
  __int64 v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+54h] [rbp-ACh]
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+70h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp-68h] BYREF
  DWORD ReturnLength; // [rsp+D0h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+D8h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD TokenInformation[12]; // [rsp+F0h] [rbp-10h] BYREF

  Binding = 0;
  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  v18 = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v15;
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  Options.Version = 1;
  Options.Flags = 1;
  *(_QWORD *)&Options.ComTimeout = 5;
  v15 = 4;
  v16 = 17;
  v17 = 3;
  v20 = 1;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  memset(&Template.NetworkAddress, 0, 40);
  v19 = 0;
  if ( a2 )
    *a2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      *((_QWORD *)&v19 + 1) = TokenInformation[0];
      Template.StringEndpoint = a1;
      v9 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 >= 0 )
      {
        *a2 = Binding;
        Binding = 0;
      }
    }
    else
    {
      LastError = WxGetLastError(v8, v7);
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147418113;
    }
  }
  else
  {
    v12 = WxGetLastError(v6, v5);
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147418113;
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001e408  mov     [rsp-8+arg_10], rbx
0x18001e40d  mov     [rsp-8+arg_18], rsi
0x18001e412  push    rbp
0x18001e413  push    rdi
0x18001e414  push    r14
0x18001e416  lea     rbp, [rsp-60h]
0x18001e41b  sub     rsp, 160h
0x18001e422  mov     rax, cs:__security_cookie
0x18001e429  xor     rax, rsp
0x18001e42c  mov     [rbp+70h+var_20], rax
0x18001e430  xor     esi, esi
0x18001e432  mov     rdi, rdx
0x18001e435  mov     rbx, rcx
0x18001e438  mov     [rsp+170h+var_13C], esi
0x18001e43c  xor     edx, edx; Val
0x18001e43e  mov     [rsp+170h+Binding], rsi
0x18001e443  lea     rcx, [rbp+70h+TokenInformation]; void *
0x18001e447  mov     [rbp+70h+TokenHandle], rsi
0x18001e44b  lea     r8d, [rsi+58h]; Size
0x18001e44f  call    memset_0
0x18001e454  xor     eax, eax
0x18001e456  mov     [rbp+70h+var_A0], esi
0x18001e459  mov     qword ptr [rbp+70h+Template.ObjectUuid.Data2], rax
0x18001e45d  lea     r14d, [rsi+1]
0x18001e461  mov     dword ptr [rbp+70h+Template.ObjectUuid.Data4+4], eax
0x18001e464  xorps   xmm0, xmm0
0x18001e467  mov     [rsp+170h+var_11C], eax
0x18001e46b  lea     rax, [rsp+170h+var_130]
0x18001e470  mov     [rbp+70h+Security.SecurityQos], rax
0x18001e474  mov     qword ptr [rbp+70h+Template.Version], r14
0x18001e478  mov     qword ptr [rbp+70h+Template.ProtocolSequence], 3
0x18001e480  mov     qword ptr [rbp+70h+Template.u1], rsi
0x18001e484  mov     [rbp+70h+Template.ObjectUuid.Data1], esi
0x18001e487  mov     [rbp+70h+Options.Version], r14d
0x18001e48b  mov     [rbp+70h+Options.Flags], r14d
0x18001e48f  mov     qword ptr [rbp+70h+Options.ComTimeout], 5
0x18001e497  mov     [rsp+170h+var_130], 4
0x18001e49f  mov     [rsp+170h+var_12C], 11h
0x18001e4a8  mov     [rsp+170h+var_124], 3
0x18001e4b1  mov     [rsp+170h+var_108], r14
0x18001e4b6  mov     qword ptr [rsp+170h+Security.Version], r14
0x18001e4bb  mov     [rsp+170h+Security.ServerPrincName], rsi
0x18001e4c0  mov     [rbp+70h+Security.AuthnLevel], 6
0x18001e4c7  mov     [rbp+70h+Security.AuthnSvc], 0Ah
0x18001e4ce  mov     [rbp+70h+Security.AuthIdentity], rsi
0x18001e4d2  movdqu  xmmword ptr [rbp+70h+Template.NetworkAddress], xmm0
0x18001e4d7  movdqu  [rsp+170h+var_118], xmm0
0x18001e4dd  test    rdi, rdi
0x18001e4e0  jz      short loc_18001E4E5
0x18001e4e2  mov     [rdi], rsi
0x18001e4e5  call    cs:__imp_GetCurrentProcess
0x18001e4eb  lea     r8, [rbp+70h+TokenHandle]; TokenHandle
0x18001e4ef  mov     edx, 20008h; DesiredAccess
0x18001e4f4  mov     rcx, rax; ProcessHandle
0x18001e4f7  call    cs:__imp_OpenProcessToken
0x18001e4fd  test    eax, eax
0x18001e4ff  jz      loc_18001E5B6
0x18001e505  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x18001e509  lea     rax, [rbp+70h+var_A0]
0x18001e50d  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18001e513  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x18001e518  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x18001e51c  mov     edx, r14d; TokenInformationClass
0x18001e51f  call    cs:__imp_GetTokenInformation
0x18001e525  test    eax, eax
0x18001e527  jz      loc_18001E5DE
0x18001e52d  mov     rax, [rbp+70h+TokenInformation]
0x18001e531  lea     r9, [rsp+170h+Binding]; Binding
0x18001e536  lea     r8, [rbp+70h+Options]; Options
0x18001e53a  mov     qword ptr [rsp+170h+var_118+8], rax
0x18001e53f  lea     rdx, [rsp+170h+Security]; Security
0x18001e544  mov     [rbp+70h+Template.StringEndpoint], rbx
0x18001e548  lea     rcx, [rbp+70h+Template]; Template
0x18001e54c  call    cs:__imp_RpcBindingCreateW
0x18001e552  mov     ebx, eax
0x18001e554  test    eax, eax
0x18001e556  jle     short loc_18001E561
0x18001e558  movzx   ebx, ax
0x18001e55b  or      ebx, 80070000h
0x18001e561  test    ebx, ebx
0x18001e563  js      loc_18001E609
0x18001e569  mov     rax, [rsp+170h+Binding]
0x18001e56e  mov     [rdi], rax
0x18001e571  mov     [rsp+170h+Binding], rsi
0x18001e576  cmp     [rsp+170h+Binding], rsi
0x18001e57b  jnz     loc_18001E616
0x18001e581  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x18001e585  test    rcx, rcx
0x18001e588  jz      short loc_18001E590
0x18001e58a  call    cs:__imp_CloseHandle
0x18001e590  mov     eax, ebx
0x18001e592  mov     rcx, [rbp+70h+var_20]
0x18001e596  xor     rcx, rsp; StackCookie
0x18001e599  call    __security_check_cookie
0x18001e59e  lea     r11, [rsp+170h+var_10]
0x18001e5a6  mov     rbx, [r11+30h]
0x18001e5aa  mov     rsi, [r11+38h]
0x18001e5ae  mov     rsp, r11
0x18001e5b1  pop     r14
0x18001e5b3  pop     rdi
0x18001e5b4  pop     rbp
0x18001e5b5  retn
0x18001e5b6  call    WxGetLastError
0x18001e5bb  mov     ebx, eax
0x18001e5bd  test    eax, eax
0x18001e5bf  jle     short loc_18001E5CA
0x18001e5c1  movzx   ebx, ax
0x18001e5c4  or      ebx, 80070000h
0x18001e5ca  test    ebx, ebx
0x18001e5cc  mov     [rsp+170h+var_13C], 47h ; 'G'
0x18001e5d4  mov     eax, 8000FFFFh
0x18001e5d9  cmovns  ebx, eax
0x18001e5dc  jmp     short loc_18001E576
0x18001e5de  call    WxGetLastError
0x18001e5e3  mov     ebx, eax
0x18001e5e5  test    eax, eax
0x18001e5e7  jle     short loc_18001E5F2
0x18001e5e9  movzx   ebx, ax
0x18001e5ec  or      ebx, 80070000h
0x18001e5f2  test    ebx, ebx
0x18001e5f4  mov     [rsp+170h+var_13C], 48h ; 'H'
0x18001e5fc  mov     eax, 8000FFFFh
0x18001e601  cmovns  ebx, eax
0x18001e604  jmp     loc_18001E576
0x18001e609  mov     [rsp+170h+var_13C], 50h ; 'P'
0x18001e611  jmp     loc_18001E576
0x18001e616  lea     rcx, [rsp+170h+Binding]; Binding
0x18001e61b  call    cs:__imp_RpcBindingFree
0x18001e621  mov     [rsp+170h+Binding], rsi
0x18001e626  jmp     loc_18001E581
```
