# WinStationIsCurrentSessionRemoteable

- ea: `0x18000b870`
- end: `0x18000baa5`
- name: `WinStationIsCurrentSessionRemoteable`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180005a70`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x180009d10`
- `0x18000b870`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba89`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003052a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003052a`
- `RPCRT4!NdrClientCall3` at `0x18000b99e`
- `RPCRT4!NdrClientCall3` at `0x18000b99e`

## string_xrefs

- `0x18000ba05`: `StringCchCopy failed: %x`

## pseudocode

```c
char __fastcall WinStationIsCurrentSessionRemoteable(_BYTE *a1)
{
  char v2; // di
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _WORD *v5; // rcx
  __int64 v6; // rax
  int *v7; // r8
  __int64 v8; // rdx
  __int16 v9; // r9
  int v10; // esi
  _WORD *v11; // rax
  void *v12; // rax
  int Pointer; // ebx
  DWORD v15; // eax
  unsigned __int16 v16[4]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v17; // [rsp+40h] [rbp-38h]

  v2 = 0;
  *a1 = 0;
  if ( TestServiceStarted() )
  {
    *(_QWORD *)v16 = 0;
    v3 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v3;
    if ( v3 )
    {
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
      v3[3] = 0;
      v3[4] = 0;
      v3[5] = 0;
      v3[6] = 1;
      v3[7] = 0;
      v5 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v4[5] = v5;
      if ( v5 )
      {
        v6 = 2147483646;
        v7 = &dword_18003D0CC;
        v8 = 1;
        do
        {
          if ( !v6 )
            break;
          v9 = *(_WORD *)v7;
          if ( !*(_WORD *)v7 )
            break;
          v7 = (int *)((char *)v7 + 2);
          *v5++ = v9;
          --v6;
          --v8;
        }
        while ( v8 );
        v10 = v8 == 0 ? 0x8007007A : 0;
        v11 = v5 - 1;
        if ( v8 )
          v11 = v5;
        *v11 = 0;
        if ( v8 )
        {
          if ( !v4[3] && !*((_DWORD *)v4 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v4) == -2147023174 )
              *((_DWORD *)v4 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v4);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v10);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v10);
        }
      }
    }
    else
    {
      v4 = 0;
    }
    v17 = v4;
    if ( v4 )
    {
      *(_DWORD *)&v16[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
    if ( CSmartPublicBinding::operator void *(v16)
      && (v12 = CSmartPublicBinding::operator void *(v16),
          Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032230, 0, 0, v12, a1).Pointer,
          Pointer < 0) )
    {
      _DbgPrintMessage(
        8,
        "RpcIsCurrentSessionTerminalRemote failed: 0x%x in %s",
        Pointer,
        "WinStationIsCurrentSessionRemoteable");
      v15 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v15);
    }
    else
    {
      v2 = 1;
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v16);
  }
  else
  {
    SetLastError(0x548u);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b870  push    rbx
0x18000b872  push    rsi
0x18000b873  push    rdi
0x18000b874  push    r14
0x18000b876  sub     rsp, 58h
0x18000b87a  mov     r14, rcx
0x18000b87d  xor     edi, edi
0x18000b87f  mov     [rcx], dil
0x18000b882  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x18000b887  test    eax, eax
0x18000b889  jz      loc_18000BA63
0x18000b88f  mov     qword ptr [rsp+78h+var_40], rdi
0x18000b894  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b89b  lea     ecx, [rdi+40h]; unsigned __int64
0x18000b89e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b8a3  mov     rbx, rax
0x18000b8a6  test    rax, rax
0x18000b8a9  jz      loc_18000BA7C
0x18000b8af  mov     [rax], rdi
0x18000b8b2  mov     [rax+8], rdi
0x18000b8b6  mov     [rax+10h], rdi
0x18000b8ba  mov     [rax+18h], rdi
0x18000b8be  mov     [rax+20h], rdi
0x18000b8c2  mov     [rax+28h], rdi
0x18000b8c6  mov     qword ptr [rax+30h], 1
0x18000b8ce  mov     [rax+38h], rdi
0x18000b8d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b8d9  lea     ecx, [rdi+2]; unsigned __int64
0x18000b8dc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b8e1  mov     rcx, rax
0x18000b8e4  mov     [rbx+28h], rax
0x18000b8e8  test    rax, rax
0x18000b8eb  jz      short loc_18000B953
0x18000b8ed  mov     eax, 7FFFFFFEh
0x18000b8f2  lea     r8, dword_18003D0CC
0x18000b8f9  lea     edx, [rdi+1]
0x18000b8fc  test    rax, rax
0x18000b8ff  jz      short loc_18000B920
0x18000b901  movzx   r9d, word ptr [r8]
0x18000b905  test    r9w, r9w
0x18000b909  jz      short loc_18000B920
0x18000b90b  add     r8, 2
0x18000b90f  mov     [rcx], r9w
0x18000b913  add     rcx, 2
0x18000b917  dec     rax
0x18000b91a  sub     rdx, 1
0x18000b91e  jnz     short loc_18000B8FC
0x18000b920  mov     rax, rdx
0x18000b923  neg     rax
0x18000b926  sbb     esi, esi
0x18000b928  not     esi
0x18000b92a  and     esi, 8007007Ah
0x18000b930  lea     rax, [rcx-2]
0x18000b934  test    rdx, rdx
0x18000b937  cmovnz  rax, rcx
0x18000b93b  mov     [rax], di
0x18000b93e  jz      loc_18000B9FB
0x18000b944  cmp     [rbx+18h], rdi
0x18000b948  jnz     short loc_18000B953
0x18000b94a  cmp     [rbx+30h], edi
0x18000b94d  jz      loc_18000BA1B
0x18000b953  mov     [rsp+78h+var_38], rbx
0x18000b958  test    rbx, rbx
0x18000b95b  jz      loc_18000BA84
0x18000b961  mov     dword ptr [rsp+78h+var_40+4], 1
0x18000b969  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000b96e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000b973  test    rax, rax
0x18000b976  jz      short loc_18000B9E1
0x18000b978  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000b97d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000b982  mov     [rsp+78h+arg_0], rdi
0x18000b98a  mov     [rsp+78h+var_58], r14
0x18000b98f  mov     r9, rax
0x18000b992  xor     r8d, r8d; pReturnValue
0x18000b995  xor     edx, edx; nProcNum
0x18000b997  lea     rcx, stru_180032230; pProxyInfo
0x18000b99e  call    cs:__imp_NdrClientCall3
0x18000b9a4  mov     rbx, rax
0x18000b9a7  mov     [rsp+78h+arg_0], rax
0x18000b9af  mov     [rsp+78h+var_48], eax
0x18000b9b3  jmp     short loc_18000B9DD
0x18000b9b5  test    eax, eax
0x18000b9b7  jle     short loc_18000B9C1
0x18000b9b9  movzx   eax, ax
0x18000b9bc  or      eax, 80070000h
0x18000b9c1  mov     ebx, eax
0x18000b9c3  mov     [rsp+78h+var_48], eax
0x18000b9c7  mov     r8d, eax
0x18000b9ca  lea     rdx, aRpciscurrentse_0; "RpcIsCurrentSessionTerminalRemote threw"...
0x18000b9d1  mov     ecx, 8; int
0x18000b9d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b9db  xor     edi, edi
0x18000b9dd  test    ebx, ebx
0x18000b9df  js      short loc_18000BA37
0x18000b9e1  mov     dil, 1
0x18000b9e4  lea     rcx, [rsp+78h+var_40]; this
0x18000b9e9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000b9ee  mov     al, dil
0x18000b9f1  add     rsp, 58h
0x18000b9f5  pop     r14
0x18000b9f7  pop     rdi
0x18000b9f8  pop     rsi
0x18000b9f9  pop     rbx
0x18000b9fa  retn
0x18000b9fb  mov     ecx, esi; int
0x18000b9fd  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000ba02  mov     r8d, esi
0x18000ba05  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000ba0c  mov     ecx, 8; int
0x18000ba11  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ba16  jmp     loc_18000B953
0x18000ba1b  mov     rcx, rbx; this
0x18000ba1e  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000ba23  cmp     eax, 800706BAh
0x18000ba28  jz      short loc_18000BA73
0x18000ba2a  mov     rcx, rbx; this
0x18000ba2d  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000ba32  jmp     loc_18000B953
0x18000ba37  lea     r9, aWinstationiscu_0; "WinStationIsCurrentSessionRemoteable"
0x18000ba3e  mov     r8d, ebx
0x18000ba41  lea     rdx, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote faile"...
0x18000ba48  mov     ecx, 8; int
0x18000ba4d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ba52  mov     ecx, ebx; int
0x18000ba54  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000ba59  mov     ecx, eax; dwErrCode
0x18000ba5b  call    cs:__imp_SetLastError
0x18000ba61  jmp     short loc_18000B9E4
0x18000ba63  mov     ecx, 548h; dwErrCode
0x18000ba68  call    cs:__imp_SetLastError
0x18000ba6e  jmp     loc_18000B9EE
0x18000ba73  mov     dword ptr [rbx+34h], 1
0x18000ba7a  jmp     short loc_18000BA2A
0x18000ba7c  mov     rbx, rdi
0x18000ba7f  jmp     loc_18000B953
0x18000ba84  mov     ecx, 0Eh; dwErrCode
0x18000ba89  call    cs:__imp_SetLastError
0x18000ba8f  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000ba96  mov     ecx, 8; int
0x18000ba9b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000baa0  jmp     loc_18000B969
0x18003051c  push    rbp
0x18003051e  sub     rsp, 30h
0x180030522  mov     rbp, rdx
0x180030525  mov     rcx, [rcx]
0x180030528  mov     ecx, [rcx]; ExceptionCode
0x18003052a  call    cs:__imp_I_RpcExceptionFilter
0x180030530  nop
0x180030531  add     rsp, 30h
0x180030535  pop     rbp
0x180030536  retn
```
