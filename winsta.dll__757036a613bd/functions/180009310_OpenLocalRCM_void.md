# OpenLocalRCM(void *)

- ea: `0x180009310`
- end: `0x1800094e1`
- name: `?OpenLocalRCM@@YAPEAXPEAX@Z`
- size: `465`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008150`
- `0x180008e30`

## callees

- `0x180007890`
- `0x180009310`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009382`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009397`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009397`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000936a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000936a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094c6`
- `RPCRT4!RpcBindingFree` at `0x1800094ba`
- `RPCRT4!RpcBindingFree` at `0x1800094ba`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800093f5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800093f5`
- `RPCRT4!RpcStringFreeW` at `0x18000943c`
- `RPCRT4!RpcStringFreeW` at `0x18000943c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180009412`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180009412`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180009490`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180009490`

## string_xrefs

- `0x180009353`: `ntdll.dll`
- `0x1800093dd`: `Security=Impersonation Dynamic False`
- `0x180009401`: `Error %d in RpcStringBindingCompose`
- `0x18000949f`: `OpenLocalRCM: RpcBindingSetAuthInfoExW failed %d`

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
  if ( byte_180057978 )
  {
    LOBYTE(v2) = dword_1800575B8;
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
    dword_1800575B8 = v2;
    byte_180057978 = 1;
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
0x180009310  mov     [rsp-18h+arg_18], rbx
0x180009315  mov     [rsp-18h+Binding], rcx
0x18000931a  push    rbp
0x18000931b  push    rsi
0x18000931c  push    r14
0x18000931e  mov     rbp, rsp
0x180009321  sub     rsp, 70h
0x180009325  mov     rsi, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pNetsrvSid
0x18000932c  xor     r14d, r14d
0x18000932f  xor     eax, eax
0x180009331  mov     [rbp+Binding], r14
0x180009335  cmp     cs:byte_180057978, al
0x18000933b  xorps   xmm0, xmm0
0x18000933e  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180009342  mov     [rbp+var_10], rax
0x180009346  movups  [rbp+var_20], xmm0
0x18000934a  jnz     short loc_1800093B4
0x18000934c  mov     ebx, ds:7FFE02D0h
0x180009353  lea     rcx, ModuleName; "ntdll.dll"
0x18000935a  xor     edx, edx; hFile
0x18000935c  mov     [rsp+70h+arg_10], rdi
0x180009364  mov     r8d, 800h; dwFlags
0x18000936a  call    cs:__imp_LoadLibraryExW
0x180009370  mov     rdi, rax
0x180009373  test    rax, rax
0x180009376  jz      short loc_18000939D
0x180009378  lea     rdx, ProcName; "RtlGetSuiteMask"
0x18000937f  mov     rcx, rax; hModule
0x180009382  call    cs:__imp_GetProcAddress
0x180009388  test    rax, rax
0x18000938b  jz      short loc_180009394
0x18000938d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009392  mov     ebx, eax
0x180009394  mov     rcx, rdi; hLibModule
0x180009397  call    cs:__imp_FreeLibrary
0x18000939d  mov     rdi, [rsp+70h+arg_10]
0x1800093a5  mov     cs:dword_1800575B8, ebx
0x1800093ab  mov     cs:byte_180057978, 1
0x1800093b2  jmp     short loc_1800093BA
0x1800093b4  mov     ebx, cs:dword_1800575B8
0x1800093ba  test    bl, 10h
0x1800093bd  jnz     short loc_1800093C9
0x1800093bf  mov     ebx, 422h
0x1800093c4  jmp     loc_1800094B0
0x1800093c9  lea     rax, [rbp+String]
0x1800093cd  mov     [rbp+String], r14
0x1800093d1  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800093d6  lea     r9, aTermsrvapi; "TermSrvApi"
0x1800093dd  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800093e4  xor     r8d, r8d; NetworkAddr
0x1800093e7  lea     rdx, ProtSeq; "ncalrpc"
0x1800093ee  mov     [rsp+70h+Options], rax; Options
0x1800093f3  xor     ecx, ecx; ObjUuid
0x1800093f5  call    cs:__imp_RpcStringBindingComposeW
0x1800093fb  mov     ebx, eax
0x1800093fd  test    eax, eax
0x1800093ff  jz      short loc_18000940A
0x180009401  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180009408  jmp     short loc_180009425
0x18000940a  mov     rcx, [rbp+String]; StringBinding
0x18000940e  lea     rdx, [rbp+Binding]; Binding
0x180009412  call    cs:__imp_RpcBindingFromStringBindingW
0x180009418  mov     ebx, eax
0x18000941a  test    eax, eax
0x18000941c  jz      short loc_180009432
0x18000941e  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180009425  mov     r8d, eax
0x180009428  mov     ecx, 8; int
0x18000942d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009432  cmp     [rbp+String], r14
0x180009436  jz      short loc_180009442
0x180009438  lea     rcx, [rbp+String]; String
0x18000943c  call    cs:__imp_RpcStringFreeW
0x180009442  test    ebx, ebx
0x180009444  jnz     short loc_1800094B0
0x180009446  mov     rcx, [rbp+Binding]; Binding
0x18000944a  lea     rax, [rbp+var_30]
0x18000944e  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180009453  xor     edx, edx; ServerPrincName
0x180009455  mov     dword ptr [rsp+70h+StringBinding], r14d; AuthzSvc
0x18000945a  mov     r9d, 0Ah; AuthnSvc
0x180009460  mov     r8d, 6; AuthnLevel
0x180009466  mov     [rsp+70h+Options], r14; AuthIdentity
0x18000946b  mov     [rbp+var_30.Capabilities], 1
0x180009472  mov     [rbp+var_30.IdentityTracking], 1
0x180009479  mov     qword ptr [rbp+var_30.ImpersonationType], 3
0x180009481  mov     qword ptr [rbp+var_20+8], r14
0x180009485  mov     [rbp+var_10], rsi
0x180009489  mov     [rbp+var_30.Version], 3
0x180009490  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180009496  mov     ebx, eax
0x180009498  test    eax, eax
0x18000949a  jz      short loc_1800094CC
0x18000949c  mov     r8d, eax
0x18000949f  lea     rdx, aOpenlocalrcmRp; "OpenLocalRCM: RpcBindingSetAuthInfoExW "...
0x1800094a6  mov     ecx, 8; int
0x1800094ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800094b0  cmp     [rbp+Binding], r14
0x1800094b4  jz      short loc_1800094C4
0x1800094b6  lea     rcx, [rbp+Binding]; Binding
0x1800094ba  call    cs:__imp_RpcBindingFree
0x1800094c0  mov     [rbp+Binding], r14
0x1800094c4  mov     ecx, ebx; dwErrCode
0x1800094c6  call    cs:__imp_SetLastError
0x1800094cc  mov     rax, [rbp+Binding]
0x1800094d0  mov     rbx, [rsp+70h+arg_18]
0x1800094d8  add     rsp, 70h
0x1800094dc  pop     r14
0x1800094de  pop     rsi
0x1800094df  pop     rbp
0x1800094e0  retn
```
