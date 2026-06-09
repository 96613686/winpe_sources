# OpenLocalRCM(void *)

- ea: `0x180007b10`
- end: `0x180007d18`
- name: `?OpenLocalRCM@@YAPEAXPEAX@Z`
- size: `520`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006480`
- `0x1800075a0`

## callees

- `0x180005b40`
- `0x180007b10`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007ba3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007ba3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007b6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007b6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007cf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007cf6`
- `RPCRT4!RpcBindingFree` at `0x180007ce4`
- `RPCRT4!RpcBindingFree` at `0x180007ce4`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007c07`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007c07`
- `RPCRT4!RpcStringFreeW` at `0x180007c5a`
- `RPCRT4!RpcStringFreeW` at `0x180007c5a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007c2a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007c2a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007cb4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007cb4`

## string_xrefs

- `0x180007b53`: `ntdll.dll`
- `0x180007bef`: `Security=Impersonation Dynamic False`
- `0x180007c19`: `Error %d in RpcStringBindingCompose`
- `0x180007cc9`: `OpenLocalRCM: RpcBindingSetAuthInfoExW failed %d`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall OpenLocalRCM(void *a1)
{
  HLOCAL v1; // rsi
  int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  __int64 (*ProcAddress)(void); // rax
  DWORD v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  RPC_STATUS v9; // eax
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL v12; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  RPC_WSTR String; // [rsp+98h] [rbp+28h] BYREF

  v1 = CPublicBinding::pNetsrvSid;
  Binding = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  v12 = 0;
  if ( byte_18005A9B0 )
  {
    LOBYTE(v2) = dword_18005A5B8;
  }
  else
  {
    v2 = MEMORY[0x7FFE02D0];
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetSuiteMask");
      if ( ProcAddress )
        v2 = ProcAddress();
      FreeLibrary(v4);
    }
    dword_18005A5B8 = v2;
    byte_18005A9B0 = 1;
  }
  if ( (v2 & 0x10) != 0 )
  {
    String = 0;
    v7 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           (RPC_WSTR)L"TermSrvApi",
           (RPC_WSTR)L"Security=Impersonation Dynamic False",
           &String);
    v6 = v7;
    if ( v7 )
    {
      _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v7);
    }
    else
    {
      v8 = RpcBindingFromStringBindingW(String, &Binding);
      v6 = v8;
      if ( v8 )
        _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v8);
    }
    if ( String )
      RpcStringFreeW(&String);
    if ( !v6 )
    {
      SecurityQOS[0].IdentityTracking = 1;
      *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
      *(_QWORD *)&SecurityQOS[1].IdentityTracking = 0;
      v12 = v1;
      *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
      v9 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, SecurityQOS);
      v6 = v9;
      if ( !v9 )
        return Binding;
      _DbgPrintMessage(8, "OpenLocalRCM: RpcBindingSetAuthInfoExW failed %d", v9);
    }
  }
  else
  {
    v6 = 1058;
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
  SetLastError(v6);
  return Binding;
}

```

## disassembly

```asm
0x180007b10  mov     [rsp-18h+arg_18], rbx
0x180007b15  mov     [rsp-18h+Binding], rcx
0x180007b1a  push    rbp
0x180007b1b  push    rsi
0x180007b1c  push    r14
0x180007b1e  mov     rbp, rsp
0x180007b21  sub     rsp, 70h
0x180007b25  mov     rsi, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pNetsrvSid
0x180007b2c  xor     r14d, r14d
0x180007b2f  xor     eax, eax
0x180007b31  mov     [rbp+Binding], r14
0x180007b35  cmp     cs:byte_18005A9B0, al
0x180007b3b  xorps   xmm0, xmm0
0x180007b3e  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180007b42  mov     [rbp+var_10], rax
0x180007b46  movups  [rbp+var_20], xmm0
0x180007b4a  jnz     short loc_180007BC6
0x180007b4c  mov     ebx, ds:7FFE02D0h
0x180007b53  lea     rcx, ModuleName; "ntdll.dll"
0x180007b5a  xor     edx, edx; hFile
0x180007b5c  mov     [rsp+70h+arg_10], rdi
0x180007b64  mov     r8d, 800h; dwFlags
0x180007b6a  call    cs:__imp_LoadLibraryExW
0x180007b71  nop     dword ptr [rax+rax+00h]
0x180007b76  mov     rdi, rax
0x180007b79  test    rax, rax
0x180007b7c  jz      short loc_180007BAF
0x180007b7e  lea     rdx, ProcName; "RtlGetSuiteMask"
0x180007b85  mov     rcx, rax; hModule
0x180007b88  call    cs:__imp_GetProcAddress
0x180007b8f  nop     dword ptr [rax+rax+00h]
0x180007b94  test    rax, rax
0x180007b97  jz      short loc_180007BA0
0x180007b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9e  mov     ebx, eax
0x180007ba0  mov     rcx, rdi; hLibModule
0x180007ba3  call    cs:__imp_FreeLibrary
0x180007baa  nop     dword ptr [rax+rax+00h]
0x180007baf  mov     rdi, [rsp+70h+arg_10]
0x180007bb7  mov     cs:dword_18005A5B8, ebx
0x180007bbd  mov     cs:byte_18005A9B0, 1
0x180007bc4  jmp     short loc_180007BCC
0x180007bc6  mov     ebx, cs:dword_18005A5B8
0x180007bcc  test    bl, 10h
0x180007bcf  jnz     short loc_180007BDB
0x180007bd1  mov     ebx, 422h
0x180007bd6  jmp     loc_180007CDA
0x180007bdb  lea     rax, [rbp+String]
0x180007bdf  mov     [rbp+String], r14
0x180007be3  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180007be8  lea     r9, aTermsrvapi; "TermSrvApi"
0x180007bef  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180007bf6  xor     r8d, r8d; NetworkAddr
0x180007bf9  lea     rdx, ProtSeq; "ncalrpc"
0x180007c00  mov     [rsp+70h+Options], rax; Options
0x180007c05  xor     ecx, ecx; ObjUuid
0x180007c07  call    cs:__imp_RpcStringBindingComposeW
0x180007c0e  nop     dword ptr [rax+rax+00h]
0x180007c13  mov     ebx, eax
0x180007c15  test    eax, eax
0x180007c17  jz      short loc_180007C22
0x180007c19  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180007c20  jmp     short loc_180007C43
0x180007c22  mov     rcx, [rbp+String]; StringBinding
0x180007c26  lea     rdx, [rbp+Binding]; Binding
0x180007c2a  call    cs:__imp_RpcBindingFromStringBindingW
0x180007c31  nop     dword ptr [rax+rax+00h]
0x180007c36  mov     ebx, eax
0x180007c38  test    eax, eax
0x180007c3a  jz      short loc_180007C50
0x180007c3c  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180007c43  mov     r8d, eax
0x180007c46  mov     ecx, 8; int
0x180007c4b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007c50  cmp     [rbp+String], r14
0x180007c54  jz      short loc_180007C66
0x180007c56  lea     rcx, [rbp+String]; String
0x180007c5a  call    cs:__imp_RpcStringFreeW
0x180007c61  nop     dword ptr [rax+rax+00h]
0x180007c66  test    ebx, ebx
0x180007c68  jnz     short loc_180007CDA
0x180007c6a  mov     rcx, [rbp+Binding]; Binding
0x180007c6e  lea     rax, [rbp+var_30]
0x180007c72  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180007c77  xor     edx, edx; ServerPrincName
0x180007c79  mov     dword ptr [rsp+70h+StringBinding], r14d; AuthzSvc
0x180007c7e  mov     r9d, 0Ah; AuthnSvc
0x180007c84  mov     r8d, 6; AuthnLevel
0x180007c8a  mov     [rsp+70h+Options], r14; AuthIdentity
0x180007c8f  mov     [rbp+var_30.Capabilities], 1
0x180007c96  mov     [rbp+var_30.IdentityTracking], 1
0x180007c9d  mov     qword ptr [rbp+var_30.ImpersonationType], 3
0x180007ca5  mov     qword ptr [rbp+var_20+8], r14
0x180007ca9  mov     [rbp+var_10], rsi
0x180007cad  mov     [rbp+var_30.Version], 3
0x180007cb4  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180007cbb  nop     dword ptr [rax+rax+00h]
0x180007cc0  mov     ebx, eax
0x180007cc2  test    eax, eax
0x180007cc4  jz      short loc_180007D02
0x180007cc6  mov     r8d, eax
0x180007cc9  lea     rdx, aOpenlocalrcmRp; "OpenLocalRCM: RpcBindingSetAuthInfoExW "...
0x180007cd0  mov     ecx, 8; int
0x180007cd5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007cda  cmp     [rbp+Binding], r14
0x180007cde  jz      short loc_180007CF4
0x180007ce0  lea     rcx, [rbp+Binding]; Binding
0x180007ce4  call    cs:__imp_RpcBindingFree
0x180007ceb  nop     dword ptr [rax+rax+00h]
0x180007cf0  mov     [rbp+Binding], r14
0x180007cf4  mov     ecx, ebx; dwErrCode
0x180007cf6  call    cs:__imp_SetLastError
0x180007cfd  nop     dword ptr [rax+rax+00h]
0x180007d02  mov     rax, [rbp+Binding]
0x180007d06  mov     rbx, [rsp+70h+arg_18]
0x180007d0e  add     rsp, 70h
0x180007d12  pop     r14
0x180007d14  pop     rsi
0x180007d15  pop     rbp
0x180007d16  retn
```
