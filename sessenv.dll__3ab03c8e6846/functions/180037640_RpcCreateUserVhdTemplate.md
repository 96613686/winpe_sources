# RpcCreateUserVhdTemplate

- ea: `0x180037640`
- end: `0x1800377ac`
- name: `RpcCreateUserVhdTemplate`
- size: `364`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003f30`
- `0x180037640`
- `0x180050f58`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376b2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800376a0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800376a0`
- `RPCRT4!RpcImpersonateClient` at `0x18003765e`
- `RPCRT4!RpcImpersonateClient` at `0x18003765e`
- `RPCRT4!RpcRevertToSelf` at `0x1800376f7`
- `RPCRT4!RpcRevertToSelf` at `0x1800376f7`

## string_xrefs

- `0x1800376ca`: `CheckTokenMembership failed: 0x%x`
- `0x18003766b`: `Cannot impersonate client: %d`
- `0x1800376e7`: `staticRpcSecurityCallback: Callers must be admin`
- `0x18003771a`: `RpcCreateUserVhdTemplate`
- `0x180037774`: `RpcCreateUserVhdTemplate`
- `0x180037724`: `Access check failed: 0x%x in %s`
- `0x180037749`: `RdVhd::Uvhd::CUvhdDiskManager::CreateInstance(&pUvhdManager) failed: 0x%x in %s`
- `0x18003776d`: `CUvhdDiskManager::CreateUvhdTemplate() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcCreateUserVhdTemplate(__int64 a1, __int64 a2, unsigned int a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // ebp
  signed int LastError; // eax
  unsigned int v9; // esi
  RPC_STATUS v10; // eax
  int v11; // eax
  struct RdVhd::Uvhd::IUvhdDiskManager *v12; // rsi
  int v13; // eax
  struct RdVhd::Uvhd::IUvhdDiskManager *v15; // [rsp+20h] [rbp-48h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  v5 = RpcImpersonateClient(0);
  if ( v5 )
  {
    _DbgPrintMessage(8, "Cannot impersonate client: %d", v5);
    return (unsigned int)-2147024891;
  }
  v7 = 0;
  IsMember = 0;
  v6 = -2147024891;
  if ( CheckTokenMembership(0, CUtils::pAdminSid, &IsMember) )
  {
    if ( IsMember )
      goto LABEL_10;
    goto LABEL_9;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "CheckTokenMembership failed: 0x%x", v9);
  if ( v9 )
  {
LABEL_9:
    _DbgPrintMessage(8, "staticRpcSecurityCallback: Callers must be admin");
    v7 = -2147024891;
  }
LABEL_10:
  v10 = RpcRevertToSelf();
  if ( v10 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v10);
LABEL_13:
    _DbgPrintMessage(8, "Access check failed: 0x%x in %s", v6, "RpcCreateUserVhdTemplate");
    return v6;
  }
  v6 = v7;
  if ( v7 < 0 )
    goto LABEL_13;
  v11 = RdVhd::Uvhd::CUvhdDiskManager::CreateInstance(&v15);
  v12 = v15;
  v6 = v11;
  if ( v11 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(struct RdVhd::Uvhd::IUvhdDiskManager *, __int64, _QWORD))(*(_QWORD *)v15 + 8LL))(
            v15,
            a2,
            a3);
    v6 = v13;
    if ( v13 < 0 )
      _DbgPrintMessage(
        8,
        "CUvhdDiskManager::CreateUvhdTemplate() failed: 0x%x in %s",
        (unsigned int)v13,
        "RpcCreateUserVhdTemplate");
  }
  else
  {
    _DbgPrintMessage(
      8,
      "RdVhd::Uvhd::CUvhdDiskManager::CreateInstance(&pUvhdManager) failed: 0x%x in %s",
      (unsigned int)v11,
      "RpcCreateUserVhdTemplate");
  }
  if ( v12 )
    (**(void (__fastcall ***)(struct RdVhd::Uvhd::IUvhdDiskManager *, __int64))v12)(v12, 1);
  return v6;
}

```

## disassembly

```asm
0x180037640  push    rbx
0x180037642  push    rbp
0x180037643  push    rsi
0x180037644  push    rdi
0x180037645  push    r14
0x180037647  push    r15
0x180037649  sub     rsp, 38h
0x18003764d  xor     ecx, ecx; BindingHandle
0x18003764f  mov     [rsp+68h+var_48], 0
0x180037658  mov     r14d, r8d
0x18003765b  mov     r15, rdx
0x18003765e  call    cs:__imp_RpcImpersonateClient
0x180037664  test    eax, eax
0x180037666  jz      short loc_180037686
0x180037668  mov     r8d, eax
0x18003766b  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x180037672  mov     ecx, 8; int
0x180037677  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003767c  mov     ebx, 80070005h
0x180037681  jmp     loc_18003779D
0x180037686  mov     rdx, cs:?pAdminSid@CUtils@@0PEAXEA; SidToCheck
0x18003768d  lea     r8, [rsp+68h+IsMember]; IsMember
0x180037695  xor     ebp, ebp
0x180037697  xor     ecx, ecx; TokenHandle
0x180037699  mov     [rsp+68h+IsMember], ebp
0x1800376a0  call    cs:__imp_CheckTokenMembership
0x1800376a6  mov     ebx, 80070005h
0x1800376ab  lea     edi, [rbp+8]
0x1800376ae  test    eax, eax
0x1800376b0  jnz     short loc_1800376DE
0x1800376b2  call    cs:__imp_GetLastError
0x1800376b8  mov     esi, eax
0x1800376ba  test    eax, eax
0x1800376bc  jle     short loc_1800376C7
0x1800376be  movzx   esi, ax
0x1800376c1  or      esi, 80070000h
0x1800376c7  mov     r8d, esi
0x1800376ca  lea     rdx, aChecktokenmemb_0; "CheckTokenMembership failed: 0x%x"
0x1800376d1  mov     ecx, edi; int
0x1800376d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800376d8  test    esi, esi
0x1800376da  jz      short loc_1800376F7
0x1800376dc  jmp     short loc_1800376E7
0x1800376de  cmp     [rsp+68h+IsMember], ebp
0x1800376e5  jnz     short loc_1800376F7
0x1800376e7  lea     rdx, aStaticrpcsecur; "staticRpcSecurityCallback: Callers must"...
0x1800376ee  mov     ecx, edi; int
0x1800376f0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800376f5  mov     ebp, ebx
0x1800376f7  call    cs:__imp_RpcRevertToSelf
0x1800376fd  test    eax, eax
0x1800376ff  jz      short loc_180037714
0x180037701  mov     r8d, eax
0x180037704  lea     rdx, aRpcreverttosel_2; "RpcRevertToSelf failed: %d"
0x18003770b  mov     ecx, edi; int
0x18003770d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037712  jmp     short loc_18003771A
0x180037714  mov     ebx, ebp
0x180037716  test    ebp, ebp
0x180037718  jns     short loc_180037734
0x18003771a  lea     r9, aRpccreateuserv; "RpcCreateUserVhdTemplate"
0x180037721  mov     r8d, ebx
0x180037724  lea     rdx, aAccessCheckFai; "Access check failed: 0x%x in %s"
0x18003772b  mov     ecx, edi; int
0x18003772d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037732  jmp     short loc_18003779D
0x180037734  lea     rcx, [rsp+68h+var_48]; struct RdVhd::Uvhd::IUvhdDiskManager **
0x180037739  call    ?CreateInstance@CUvhdDiskManager@Uvhd@RdVhd@@SAJPEAPEAVIUvhdDiskManager@23@@Z; RdVhd::Uvhd::CUvhdDiskManager::CreateInstance(RdVhd::Uvhd::IUvhdDiskManager * *)
0x18003773e  mov     rsi, [rsp+68h+var_48]
0x180037743  mov     ebx, eax
0x180037745  test    eax, eax
0x180037747  jns     short loc_180037752
0x180037749  lea     rdx, aRdvhdUvhdCuvhd; "RdVhd::Uvhd::CUvhdDiskManager::CreateIn"...
0x180037750  jmp     short loc_180037774
0x180037752  mov     rax, [rsi]
0x180037755  mov     r8d, r14d
0x180037758  mov     rdx, r15
0x18003775b  mov     rcx, rsi
0x18003775e  mov     rax, [rax+8]
0x180037762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037767  mov     ebx, eax
0x180037769  test    eax, eax
0x18003776b  jns     short loc_180037785
0x18003776d  lea     rdx, aCuvhddiskmanag; "CUvhdDiskManager::CreateUvhdTemplate() "...
0x180037774  lea     r9, aRpccreateuserv; "RpcCreateUserVhdTemplate"
0x18003777b  mov     r8d, eax
0x18003777e  mov     ecx, edi; int
0x180037780  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037785  test    rsi, rsi
0x180037788  jz      short loc_18003779D
0x18003778a  mov     rax, [rsi]
0x18003778d  mov     edx, 1
0x180037792  mov     rcx, rsi
0x180037795  mov     rax, [rax]
0x180037798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003779d  mov     eax, ebx
0x18003779f  add     rsp, 38h
0x1800377a3  pop     r15
0x1800377a5  pop     r14
0x1800377a7  pop     rdi
0x1800377a8  pop     rsi
0x1800377a9  pop     rbp
0x1800377aa  pop     rbx
0x1800377ab  retn
```
