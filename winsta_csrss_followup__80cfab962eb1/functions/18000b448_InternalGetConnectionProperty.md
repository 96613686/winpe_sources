# InternalGetConnectionProperty

- ea: `0x18000b448`
- end: `0x18000b5fe`
- name: `InternalGetConnectionProperty`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a9e0`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000b448`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b56d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b56d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b59b`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033320`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033320`
- `RPCRT4!NdrClientCall3` at `0x18000b51c`
- `RPCRT4!NdrClientCall3` at `0x18000b51c`

## string_xrefs

- `0x18000b5b6`: `Failed to open binding`

## pseudocode

```c
bool __fastcall InternalGetConnectionProperty(ULONG SessionId, __int64 a2, _QWORD *a3)
{
  CPublicBinding *v6; // rax
  void *v7; // rax
  CLIENT_CALL_RETURN v8; // rax
  signed int Pointer; // ebx
  bool v10; // sf
  DWORD v11; // eax
  bool v12; // bl
  signed int LastError; // eax
  __int64 v15; // [rsp+48h] [rbp-20h] BYREF
  CPublicBinding *v16; // [rsp+50h] [rbp-18h]
  CLIENT_CALL_RETURN v17; // [rsp+88h] [rbp+20h] BYREF

  v15 = 1;
  LODWORD(v17.Pointer) = 0;
  v6 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v6 = CPublicBinding::CPublicBinding(v6, 0, 0, (unsigned int *)&v17);
  v16 = v6;
  if ( v6 )
  {
    HIDWORD(v15) = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v15) )
  {
    if ( a3 )
    {
      *a3 = 0;
      if ( SessionId == -1 )
        SessionId = NtCurrentPeb()->SessionId;
      v7 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v15);
      v17.Simple = 0;
      v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 4u, 0, v7, SessionId, a2, a3).Pointer;
      Pointer = (signed int)v8.Pointer;
      v17.Pointer = v8.Pointer;
    }
    else
    {
      Pointer = -2147024809;
      _DbgPrintMessage(8, "ppProperyValue is NULL");
    }
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  v10 = Pointer < 0;
  if ( Pointer < 0 )
  {
    v11 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v11);
    v10 = Pointer < 0;
  }
  v12 = !v10;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v15);
  return v12;
}

```

## disassembly

```asm
0x18000b448  mov     rax, rsp
0x18000b44b  mov     [rax+8], rbx
0x18000b44f  mov     [rax+10h], rsi
0x18000b453  push    rdi
0x18000b454  sub     rsp, 60h
0x18000b458  mov     rbx, r8
0x18000b45b  mov     rsi, rdx
0x18000b45e  mov     edi, ecx
0x18000b460  mov     qword ptr [rax-20h], 1
0x18000b468  mov     dword ptr [rax+20h], 0
0x18000b46f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b476  mov     ecx, 40h ; '@'; unsigned __int64
0x18000b47b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b480  test    rax, rax
0x18000b483  jz      short loc_18000B49A
0x18000b485  lea     r9, [rsp+68h+arg_18]; unsigned int *
0x18000b48d  xor     r8d, r8d; int
0x18000b490  xor     edx, edx; unsigned __int16 *
0x18000b492  mov     rcx, rax; this
0x18000b495  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000b49a  mov     [rsp+68h+var_18], rax
0x18000b49f  test    rax, rax
0x18000b4a2  jz      loc_18000B5C9
0x18000b4a8  mov     [rsp+68h+var_1C], 1
0x18000b4b0  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x18000b4b5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000b4ba  test    rax, rax
0x18000b4bd  jz      loc_18000B59B
0x18000b4c3  test    rbx, rbx
0x18000b4c6  jz      loc_18000B5F0
0x18000b4cc  mov     qword ptr [rbx], 0
0x18000b4d3  cmp     edi, 0FFFFFFFFh
0x18000b4d6  jnz     short loc_18000B4E7
0x18000b4d8  mov     rax, gs:60h
0x18000b4e1  mov     edi, [rax+2C0h]
0x18000b4e7  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x18000b4ec  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000b4f1  mov     [rsp+68h+arg_18], 0
0x18000b4fd  mov     [rsp+68h+var_38], rbx
0x18000b502  mov     [rsp+68h+var_40], rsi
0x18000b507  mov     [rsp+68h+var_48], edi
0x18000b50b  mov     r9, rax
0x18000b50e  xor     r8d, r8d; pReturnValue
0x18000b511  lea     edx, [r8+4]; nProcNum
0x18000b515  lea     rcx, stru_180035140; pProxyInfo
0x18000b51c  call    cs:__imp_NdrClientCall3
0x18000b523  nop     dword ptr [rax+rax+00h]
0x18000b528  mov     rbx, rax
0x18000b52b  mov     [rsp+68h+arg_18], rax
0x18000b533  mov     [rsp+68h+var_28], eax
0x18000b537  jmp     short loc_18000B560
0x18000b539  test    eax, eax
0x18000b53b  jle     short loc_18000B545
0x18000b53d  movzx   eax, ax
0x18000b540  or      eax, 80070000h
0x18000b545  mov     ebx, eax
0x18000b547  mov     [rsp+68h+var_28], eax
0x18000b54b  mov     r8d, eax
0x18000b54e  lea     rdx, aRpcgetconnecti; "RpcGetConnectionProperty threw an excep"...
0x18000b555  mov     ecx, 8; int
0x18000b55a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b55f  nop
0x18000b560  test    ebx, ebx
0x18000b562  jns     short loc_18000B57B
0x18000b564  mov     ecx, ebx; int
0x18000b566  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000b56b  mov     ecx, eax; dwErrCode
0x18000b56d  call    cs:__imp_SetLastError
0x18000b574  nop     dword ptr [rax+rax+00h]
0x18000b579  test    ebx, ebx
0x18000b57b  setns   bl
0x18000b57e  lea     rcx, [rsp+68h+var_20]; this
0x18000b583  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000b588  mov     al, bl
0x18000b58a  mov     rbx, [rsp+68h+arg_0]
0x18000b58f  mov     rsi, [rsp+68h+arg_8]
0x18000b594  add     rsp, 60h
0x18000b598  pop     rdi
0x18000b599  retn
0x18000b59b  call    cs:__imp_GetLastError
0x18000b5a2  nop     dword ptr [rax+rax+00h]
0x18000b5a7  mov     ebx, eax
0x18000b5a9  test    eax, eax
0x18000b5ab  jle     short loc_18000B5B6
0x18000b5ad  movzx   ebx, ax
0x18000b5b0  or      ebx, 80070000h
0x18000b5b6  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000b5bd  mov     ecx, 8; int
0x18000b5c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5c7  jmp     short loc_18000B560
0x18000b5c9  mov     ecx, 0Eh; dwErrCode
0x18000b5ce  call    cs:__imp_SetLastError
0x18000b5d5  nop     dword ptr [rax+rax+00h]
0x18000b5da  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000b5e1  mov     ecx, 8; int
0x18000b5e6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5eb  jmp     loc_18000B4B0
0x18000b5f0  mov     ebx, 80070057h
0x18000b5f5  lea     rdx, aPpproperyvalue; "ppProperyValue is NULL"
0x18000b5fc  jmp     short loc_18000B5BD
0x180033312  push    rbp
0x180033314  sub     rsp, 40h
0x180033318  mov     rbp, rdx
0x18003331b  mov     rcx, [rcx]
0x18003331e  mov     ecx, [rcx]; ExceptionCode
0x180033320  call    cs:__imp_I_RpcExceptionFilter
0x180033327  nop     dword ptr [rax+rax+00h]
0x18003332c  nop
0x18003332d  add     rsp, 40h
0x180033331  pop     rbp
0x180033332  retn
```
