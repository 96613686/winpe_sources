# CPublicBinding::GetLSMBinding(void)

- ea: `0x180008f10`
- end: `0x180009300`
- name: `?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `1008`
- prototype: `void *__fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005374`
- `0x1800067b0`
- `0x1800083b0`
- `0x180008e30`

## callees

- `0x180005fcc`
- `0x180007890`
- `0x180008f10`
- `0x18000c368`
- `0x18000c6b0`
- `0x18000e8b8`
- `0x18002fe40`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008fde`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008fde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008fb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000929d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000929d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000922b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000922b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092f5`
- `RPCRT4!RpcBindingFree` at `0x1800090f8`
- `RPCRT4!RpcBindingFree` at `0x180009281`
- `RPCRT4!RpcBindingFree` at `0x1800090f8`
- `RPCRT4!RpcBindingFree` at `0x180009281`
- `RPCRT4!RpcStringBindingComposeW` at `0x180009034`
- `RPCRT4!RpcStringBindingComposeW` at `0x180009171`
- `RPCRT4!RpcStringBindingComposeW` at `0x180009034`
- `RPCRT4!RpcStringBindingComposeW` at `0x180009171`
- `RPCRT4!RpcStringFreeW` at `0x18000907b`
- `RPCRT4!RpcStringFreeW` at `0x1800091b7`
- `RPCRT4!RpcStringFreeW` at `0x18000907b`
- `RPCRT4!RpcStringFreeW` at `0x1800091b7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180009051`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000918d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180009051`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000918d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800090ce`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180009259`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800092ea`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800090ce`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180009259`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800092ea`

## string_xrefs

- `0x180008fa2`: `ntdll.dll`
- `0x18000901c`: `Security=Impersonation Dynamic False`
- `0x180009138`: `Security=Impersonation Dynamic False`
- `0x180009040`: `Error %d in RpcStringBindingCompose`
- `0x18000917d`: `Error %d in RpcStringBindingCompose`
- `0x1800090dd`: `OpenLocalLSM: RpcBindingSetAuthInfoExW failed %d`
- `0x180009128`: `\pipe\LSM_API_service`

## pseudocode

```c
void *__fastcall CPublicBinding::GetLSMBinding(RPC_BINDING_HANDLE *Binding)
{
  PSID v2; // r14
  int LocalSids; // eax
  DWORD v4; // eax
  int v6; // ebx
  HMODULE Library; // rax
  HMODULE v8; // r15
  __int64 (*ProcAddress)(void); // rax
  DWORD v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  RPC_STATUS v13; // eax
  unsigned __int16 *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r15
  RPC_WSTR String; // [rsp+40h] [rbp-29h] BYREF
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+48h] [rbp-21h] BYREF
  PSID v25; // [rsp+68h] [rbp-1h]
  RPC_SECURITY_QOS Bindinga; // [rsp+70h] [rbp+7h] BYREF

  if ( *Binding )
    return *Binding;
  if ( *((_DWORD *)Binding + 12) != 1 )
  {
    v14 = (unsigned __int16 *)Binding[5];
    Bindinga.Capabilities = 1;
    *Binding = 0;
    Bindinga.IdentityTracking = 1;
    Bindinga.ImpersonationType = 3;
    Bindinga.Version = 1;
    String = 0;
    v15 = RpcStringBindingComposeW(
            (RPC_WSTR)L"484809d6-4239-471b-b5bc-61df8c23ac48",
            (RPC_WSTR)L"ncacn_np",
            v14,
            (RPC_WSTR)L"\\pipe\\LSM_API_service",
            (RPC_WSTR)L"Security=Impersonation Dynamic False",
            &String);
    v16 = v15;
    if ( v15 )
    {
      _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v15);
    }
    else
    {
      v17 = RpcBindingFromStringBindingW(String, Binding);
      v16 = v17;
      if ( v17 )
        _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v17);
    }
    if ( String )
      RpcStringFreeW(&String);
    if ( v16 )
    {
      _DbgPrintMessage(8, "Error %d in TermSrvBind", v16);
      goto LABEL_46;
    }
    if ( v14 )
    {
      v18 = -1;
      while ( v14[++v18] != 0 )
        ;
      v20 = v18 + 8;
      v21 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v18 + 8));
      v22 = v21;
      if ( !v21 || StringCchPrintfW(v21, v20, L"host/%s", v14) >= 0 )
      {
        v16 = RpcBindingSetAuthInfoExW(*Binding, v22, 6u, 9u, 0, 1u, &Bindinga);
        LocalFree(v22);
        goto LABEL_44;
      }
      LocalFree(v22);
    }
    v16 = RpcBindingSetAuthInfoExW(*Binding, v14, 6u, 9u, 0, 1u, &Bindinga);
LABEL_44:
    if ( !v16 )
      return *Binding;
    _DbgPrintMessage(8, "Error %d in RpcBindingSetAuthInfoEx", v16);
LABEL_46:
    if ( *Binding )
      RpcBindingFree(Binding);
    _DbgPrintMessage(8, "CRpcUtils::BindSecure failed: %d", v16);
    SetLastError(v16);
    return *Binding;
  }
  v2 = CPublicBinding::pSystemSid;
  if ( !CPublicBinding::pSystemSid )
  {
    LocalSids = CPublicBinding::CreateLocalSids();
    if ( LocalSids < 0 )
    {
      v4 = ConvertHRESULT2WIN32(LocalSids);
      SetLastError(v4);
      return 0;
    }
    v2 = CPublicBinding::pSystemSid;
  }
  *(_QWORD *)&Bindinga.Version = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  v25 = 0;
  if ( byte_180057978 )
  {
    LOBYTE(v6) = dword_1800575B8;
  }
  else
  {
    v6 = MEMORY[0x7FFE02D0];
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v8 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetSuiteMask");
      if ( ProcAddress )
        v6 = ProcAddress();
      FreeLibrary(v8);
    }
    dword_1800575B8 = v6;
    byte_180057978 = 1;
  }
  if ( (v6 & 0x10) == 0 )
  {
    v10 = 1058;
LABEL_25:
    if ( *(_QWORD *)&Bindinga.Version )
    {
      RpcBindingFree((RPC_BINDING_HANDLE *)&Bindinga);
      *(_QWORD *)&Bindinga.Version = 0;
    }
    SetLastError(v10);
    goto LABEL_28;
  }
  String = 0;
  v11 = RpcStringBindingComposeW(
          0,
          (RPC_WSTR)L"ncalrpc",
          0,
          (RPC_WSTR)L"LSMApi",
          (RPC_WSTR)L"Security=Impersonation Dynamic False",
          &String);
  v10 = v11;
  if ( v11 )
  {
    _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v11);
  }
  else
  {
    v12 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)&Bindinga);
    v10 = v12;
    if ( v12 )
      _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v12);
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( v10 )
    goto LABEL_25;
  SecurityQOS[0].IdentityTracking = 1;
  *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
  *(_QWORD *)&SecurityQOS[1].IdentityTracking = 0;
  v25 = v2;
  *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
  v13 = RpcBindingSetAuthInfoExW(*(RPC_BINDING_HANDLE *)&Bindinga.Version, 0, 6u, 0xAu, 0, 0, SecurityQOS);
  v10 = v13;
  if ( v13 )
  {
    _DbgPrintMessage(8, "OpenLocalLSM: RpcBindingSetAuthInfoExW failed %d", v13);
    goto LABEL_25;
  }
LABEL_28:
  WaitForLsmStart();
  *Binding = *(RPC_BINDING_HANDLE *)&Bindinga.Version;
  return *Binding;
}

```

## disassembly

```asm
0x180008f10  push    rbp
0x180008f12  push    rbx
0x180008f13  push    rsi
0x180008f14  push    rdi
0x180008f15  push    r14
0x180008f17  push    r15
0x180008f19  lea     rbp, [rsp-2Fh]
0x180008f1e  sub     rsp, 98h
0x180008f25  mov     rax, cs:__security_cookie
0x180008f2c  xor     rax, rsp
0x180008f2f  mov     [rbp+57h+var_40], rax
0x180008f33  cmp     qword ptr [rcx], 0
0x180008f37  mov     rdi, rcx
0x180008f3a  jnz     loc_1800092A3
0x180008f40  cmp     dword ptr [rcx+30h], 1
0x180008f44  jnz     loc_18000911B
0x180008f4a  mov     r14, cs:?pSystemSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pSystemSid
0x180008f51  test    r14, r14
0x180008f54  jnz     short loc_180008F7C
0x180008f56  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x180008f5b  test    eax, eax
0x180008f5d  jns     short loc_180008F75
0x180008f5f  mov     ecx, eax; int
0x180008f61  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180008f66  mov     ecx, eax; dwErrCode
0x180008f68  call    cs:__imp_SetLastError
0x180008f6e  xor     eax, eax
0x180008f70  jmp     loc_1800092A6
0x180008f75  mov     r14, cs:?pSystemSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pSystemSid
0x180008f7c  xor     esi, esi
0x180008f7e  xor     eax, eax
0x180008f80  cmp     cs:byte_180057978, al
0x180008f86  xorps   xmm0, xmm0
0x180008f89  mov     [rbp+57h+Binding], rsi
0x180008f8d  movups  xmmword ptr [rbp+57h+var_78.Version], xmm0
0x180008f91  mov     [rbp+57h+var_58], rax
0x180008f95  movups  [rbp+57h+var_68], xmm0
0x180008f99  jnz     short loc_180008FF3
0x180008f9b  mov     ebx, ds:7FFE02D0h
0x180008fa2  lea     rcx, ModuleName; "ntdll.dll"
0x180008fa9  xor     edx, edx; hFile
0x180008fab  mov     r8d, 800h; dwFlags
0x180008fb1  call    cs:__imp_LoadLibraryExW
0x180008fb7  mov     r15, rax
0x180008fba  test    rax, rax
0x180008fbd  jz      short loc_180008FE4
0x180008fbf  lea     rdx, ProcName; "RtlGetSuiteMask"
0x180008fc6  mov     rcx, rax; hModule
0x180008fc9  call    cs:__imp_GetProcAddress
0x180008fcf  test    rax, rax
0x180008fd2  jz      short loc_180008FDB
0x180008fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd9  mov     ebx, eax
0x180008fdb  mov     rcx, r15; hLibModule
0x180008fde  call    cs:__imp_FreeLibrary
0x180008fe4  mov     cs:dword_1800575B8, ebx
0x180008fea  mov     cs:byte_180057978, 1
0x180008ff1  jmp     short loc_180008FF9
0x180008ff3  mov     ebx, cs:dword_1800575B8
0x180008ff9  test    bl, 10h
0x180008ffc  jnz     short loc_180009008
0x180008ffe  mov     ebx, 422h
0x180009003  jmp     loc_1800090EE
0x180009008  lea     rax, [rbp+57h+String]
0x18000900c  mov     [rbp+57h+String], rsi
0x180009010  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x180009015  lea     r9, Endpoint; "LSMApi"
0x18000901c  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180009023  xor     r8d, r8d; NetworkAddr
0x180009026  lea     rdx, ProtSeq; "ncalrpc"
0x18000902d  mov     [rsp+0C0h+Options], rax; Options
0x180009032  xor     ecx, ecx; ObjUuid
0x180009034  call    cs:__imp_RpcStringBindingComposeW
0x18000903a  mov     ebx, eax
0x18000903c  test    eax, eax
0x18000903e  jz      short loc_180009049
0x180009040  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180009047  jmp     short loc_180009064
0x180009049  mov     rcx, [rbp+57h+String]; StringBinding
0x18000904d  lea     rdx, [rbp+57h+Binding]; Binding
0x180009051  call    cs:__imp_RpcBindingFromStringBindingW
0x180009057  mov     ebx, eax
0x180009059  test    eax, eax
0x18000905b  jz      short loc_180009071
0x18000905d  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180009064  mov     r8d, eax
0x180009067  mov     ecx, 8; int
0x18000906c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009071  cmp     [rbp+57h+String], rsi
0x180009075  jz      short loc_180009081
0x180009077  lea     rcx, [rbp+57h+String]; String
0x18000907b  call    cs:__imp_RpcStringFreeW
0x180009081  test    ebx, ebx
0x180009083  jnz     short loc_1800090EE
0x180009085  mov     rcx, [rbp+57h+Binding]; Binding
0x180009089  lea     rax, [rbp+57h+var_78]
0x18000908d  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x180009092  xor     edx, edx; ServerPrincName
0x180009094  mov     dword ptr [rsp+0C0h+StringBinding], esi; AuthzSvc
0x180009098  mov     r9d, 0Ah; AuthnSvc
0x18000909e  mov     r8d, 6; AuthnLevel
0x1800090a4  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x1800090a9  mov     [rbp+57h+var_78.Capabilities], 1
0x1800090b0  mov     [rbp+57h+var_78.IdentityTracking], 1
0x1800090b7  mov     qword ptr [rbp+57h+var_78.ImpersonationType], 3
0x1800090bf  mov     qword ptr [rbp+57h+var_68+8], rsi
0x1800090c3  mov     [rbp+57h+var_58], r14
0x1800090c7  mov     [rbp+57h+var_78.Version], 3
0x1800090ce  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800090d4  mov     ebx, eax
0x1800090d6  test    eax, eax
0x1800090d8  jz      short loc_18000910A
0x1800090da  mov     r8d, eax
0x1800090dd  lea     rdx, aOpenlocallsmRp; "OpenLocalLSM: RpcBindingSetAuthInfoExW "...
0x1800090e4  mov     ecx, 8; int
0x1800090e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800090ee  cmp     [rbp+57h+Binding], rsi
0x1800090f2  jz      short loc_180009102
0x1800090f4  lea     rcx, [rbp+57h+Binding]; Binding
0x1800090f8  call    cs:__imp_RpcBindingFree
0x1800090fe  mov     [rbp+57h+Binding], rsi
0x180009102  mov     ecx, ebx; dwErrCode
0x180009104  call    cs:__imp_SetLastError
0x18000910a  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18000910f  mov     rax, [rbp+57h+Binding]
0x180009113  mov     [rdi], rax
0x180009116  jmp     loc_1800092A3
0x18000911b  mov     r14, [rcx+28h]
0x18000911f  lea     rax, [rbp+57h+String]
0x180009123  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x180009128  lea     r9, aPipeLsmApiServ; "\\pipe\\LSM_API_service"
0x18000912f  xor     esi, esi
0x180009131  mov     dword ptr [rbp+57h+Binding+4], 1
0x180009138  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18000913f  mov     [rcx], rsi
0x180009142  mov     r8, r14; NetworkAddr
0x180009145  mov     [rsp+0C0h+Options], rax; Options
0x18000914a  lea     rdx, aNcacnNp; "ncacn_np"
0x180009151  mov     [rbp+57h+var_48], 1
0x180009158  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x18000915f  mov     [rbp+57h+var_44], 3
0x180009166  mov     dword ptr [rbp+57h+Binding], 1
0x18000916d  mov     [rbp+57h+String], rsi
0x180009171  call    cs:__imp_RpcStringBindingComposeW
0x180009177  mov     ebx, eax
0x180009179  test    eax, eax
0x18000917b  jz      short loc_180009186
0x18000917d  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180009184  jmp     short loc_1800091A0
0x180009186  mov     rcx, [rbp+57h+String]; StringBinding
0x18000918a  mov     rdx, rdi; Binding
0x18000918d  call    cs:__imp_RpcBindingFromStringBindingW
0x180009193  mov     ebx, eax
0x180009195  test    eax, eax
0x180009197  jz      short loc_1800091AD
0x180009199  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x1800091a0  mov     r8d, eax
0x1800091a3  mov     ecx, 8; int
0x1800091a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800091ad  cmp     [rbp+57h+String], rsi
0x1800091b1  jz      short loc_1800091BD
0x1800091b3  lea     rcx, [rbp+57h+String]; String
0x1800091b7  call    cs:__imp_RpcStringFreeW
0x1800091bd  test    ebx, ebx
0x1800091bf  jz      short loc_1800091CD
0x1800091c1  lea     rdx, aErrorDInTermsr; "Error %d in TermSrvBind"
0x1800091c8  jmp     loc_18000926C
0x1800091cd  test    r14, r14
0x1800091d0  jz      short loc_180009231
0x1800091d2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800091d9  nop     dword ptr [rax+00000000h]
0x1800091e0  cmp     [r14+rax*2+2], si
0x1800091e6  lea     rax, [rax+1]
0x1800091ea  jnz     short loc_1800091E0
0x1800091ec  lea     rbx, [rax+8]
0x1800091f0  mov     ecx, 40h ; '@'; uFlags
0x1800091f5  lea     rdx, [rbx+rbx]; uBytes
0x1800091f9  call    cs:__imp_LocalAlloc
0x1800091ff  mov     r15, rax
0x180009202  test    rax, rax
0x180009205  jz      loc_1800092C2
0x18000920b  mov     r9, r14
0x18000920e  lea     r8, aHostS; "host/%s"
0x180009215  mov     rdx, rbx; unsigned __int64
0x180009218  mov     rcx, rax; unsigned __int16 *
0x18000921b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009220  test    eax, eax
0x180009222  jns     loc_1800092C2
0x180009228  mov     rcx, r15; hMem
0x18000922b  call    cs:__imp_LocalFree
0x180009231  mov     rcx, [rdi]; Binding
0x180009234  lea     rax, [rbp+57h+Binding]
0x180009238  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x18000923d  mov     r9d, 9; AuthnSvc
0x180009243  mov     dword ptr [rsp+0C0h+StringBinding], 1; AuthzSvc
0x18000924b  mov     r8d, 6; AuthnLevel
0x180009251  mov     rdx, r14; ServerPrincName
0x180009254  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x180009259  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000925f  mov     ebx, eax
0x180009261  test    ebx, ebx
0x180009263  jz      short loc_1800092A3
0x180009265  lea     rdx, aErrorDInRpcbin; "Error %d in RpcBindingSetAuthInfoEx"
0x18000926c  mov     r8d, ebx
0x18000926f  mov     ecx, 8; int
0x180009274  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009279  cmp     [rdi], rsi
0x18000927c  jz      short loc_180009287
0x18000927e  mov     rcx, rdi; Binding
0x180009281  call    cs:__imp_RpcBindingFree
0x180009287  mov     r8d, ebx
0x18000928a  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x180009291  mov     ecx, 8; int
0x180009296  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000929b  mov     ecx, ebx; dwErrCode
0x18000929d  call    cs:__imp_SetLastError
0x1800092a3  mov     rax, [rdi]
0x1800092a6  mov     rcx, [rbp+57h+var_40]
0x1800092aa  xor     rcx, rsp; StackCookie
0x1800092ad  call    __security_check_cookie
0x1800092b2  add     rsp, 98h
0x1800092b9  pop     r15
0x1800092bb  pop     r14
0x1800092bd  pop     rdi
0x1800092be  pop     rsi
0x1800092bf  pop     rbx
0x1800092c0  pop     rbp
0x1800092c1  retn
0x1800092c2  mov     rcx, [rdi]; Binding
0x1800092c5  lea     rax, [rbp+57h+Binding]
0x1800092c9  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x1800092ce  mov     r9d, 9; AuthnSvc
0x1800092d4  mov     dword ptr [rsp+0C0h+StringBinding], 1; AuthzSvc
0x1800092dc  mov     r8d, 6; AuthnLevel
0x1800092e2  mov     rdx, r15; ServerPrincName
0x1800092e5  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x1800092ea  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800092f0  mov     rcx, r15; hMem
0x1800092f3  mov     ebx, eax
0x1800092f5  call    cs:__imp_LocalFree
0x1800092fb  jmp     loc_180009261
```
