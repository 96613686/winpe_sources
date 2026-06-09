# Legacy_WinStationOpenServerW(void *)

- ea: `0x18002eeec`
- end: `0x18002f09a`
- name: `?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z`
- size: `430`
- prototype: `void *__fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f884`
- `0x18003154c`

## callees

- `0x180005b40`
- `0x18000dc78`
- `0x18000de00`
- `0x180025f74`
- `0x18002eeec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f084`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f084`
- `RPCRT4!RpcBindingFree` at `0x18002ef82`
- `RPCRT4!RpcBindingFree` at `0x18002f053`
- `RPCRT4!RpcBindingFree` at `0x18002ef82`
- `RPCRT4!RpcBindingFree` at `0x18002f053`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033c78`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033c9a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033c78`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033c9a`

## string_xrefs

- `0x18002efd6`: `Security=Impersonation Dynamic False`
- `0x18002f06f`: `WinStationOpenServerW: Error %d getting context handle`
- `0x18002ef1c`: `\pipe\Ctx_WinStation_API_service`
- `0x18002efe2`: `\pipe\Ctx_WinStation_API_service`

## pseudocode

```c
__int64 __fastcall Legacy_WinStationOpenServerW(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v3; // bl
  RPC_STATUS v4; // eax
  const unsigned __int16 *v6; // [rsp+20h] [rbp-38h]
  RPC_BINDING_HANDLE v7; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v7 = a1;
  dwErrCode = 5;
  v10 = 0;
  Binding = 0;
  dwErrCode = CRpcUtils::BindSecure(
                L"5ca4a760-ebb1-11cf-8611-00a0245420ed",
                a2,
                a1,
                L"\\pipe\\Ctx_WinStation_API_service",
                v6,
                &Binding);
  v3 = RpcWinStationOpenServer(Binding, &dwErrCode, &v10);
  if ( Binding )
  {
    v4 = RpcBindingFree(&Binding);
    if ( v4 )
      _DbgPrintMessage(8, "RpcBindingFree failed 0x%x", v4);
  }
  if ( v3 )
    return v10;
  if ( dwErrCode == 1747 || dwErrCode == 5 )
  {
    v7 = 0;
    if ( !(unsigned int)CRpcUtils::Bind(
                          L"5ca4a760-ebb1-11cf-8611-00a0245420ed",
                          L"ncacn_np",
                          a1,
                          L"\\pipe\\Ctx_WinStation_API_service",
                          (RPC_WSTR)L"Security=Impersonation Dynamic False",
                          &v7) )
    {
      _DbgPrintMessage(8, "Using nonsecure connection!!!");
      v3 = RpcWinStationOpenServer(v7, &dwErrCode, &v10);
      RpcBindingFree(&v7);
    }
  }
  if ( v3 )
    return v10;
  _DbgPrintMessage(8, "WinStationOpenServerW: Error %d getting context handle", dwErrCode);
  SetLastError(dwErrCode);
  return 0;
}

```

## disassembly

```asm
0x18002eeec  mov     rax, rsp
0x18002eeef  mov     [rax+8], rcx
0x18002eef3  push    rbx
0x18002eef4  push    rdi
0x18002eef5  sub     rsp, 48h
0x18002eef9  mov     rdi, rcx
0x18002eefc  mov     dword ptr [rax+10h], 5
0x18002ef03  mov     qword ptr [rax+20h], 0
0x18002ef0b  mov     qword ptr [rax+18h], 0
0x18002ef13  lea     rax, [rax+18h]
0x18002ef17  mov     [rsp+58h+var_30], rax; void **
0x18002ef1c  lea     r9, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x18002ef23  mov     r8, rcx; unsigned __int16 *
0x18002ef26  lea     rcx, a5ca4a760Ebb111; "5ca4a760-ebb1-11cf-8611-00a0245420ed"
0x18002ef2d  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002ef32  mov     [rsp+58h+dwErrCode], eax
0x18002ef36  lea     r8, [rsp+58h+arg_18]
0x18002ef3b  lea     rdx, [rsp+58h+dwErrCode]
0x18002ef40  mov     rcx, [rsp+58h+Binding]
0x18002ef45  call    RpcWinStationOpenServer
0x18002ef4a  mov     bl, al
0x18002ef4c  mov     [rsp+58h+var_28], al
0x18002ef50  jmp     short loc_18002EF75
0x18002ef52  mov     [rsp+58h+dwErrCode], eax
0x18002ef56  xor     bl, bl
0x18002ef58  mov     [rsp+58h+var_28], bl
0x18002ef5c  mov     r8d, eax
0x18002ef5f  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002ef66  mov     ecx, 8; int
0x18002ef6b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ef70  mov     rdi, [rsp+58h+arg_0]
0x18002ef75  cmp     [rsp+58h+Binding], 0
0x18002ef7b  jz      short loc_18002EFA6
0x18002ef7d  lea     rcx, [rsp+58h+Binding]; Binding
0x18002ef82  call    cs:__imp_RpcBindingFree
0x18002ef89  nop     dword ptr [rax+rax+00h]
0x18002ef8e  test    eax, eax
0x18002ef90  jz      short loc_18002EFA6
0x18002ef92  mov     r8d, eax
0x18002ef95  lea     rdx, aRpcbindingfree_0; "RpcBindingFree failed 0x%x"
0x18002ef9c  mov     ecx, 8; int
0x18002efa1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002efa6  test    bl, bl
0x18002efa8  jnz     loc_18002F063
0x18002efae  cmp     [rsp+58h+dwErrCode], 6D3h
0x18002efb6  jz      short loc_18002EFC3
0x18002efb8  cmp     [rsp+58h+dwErrCode], 5
0x18002efbd  jnz     loc_18002F05F
0x18002efc3  mov     [rsp+58h+arg_0], 0
0x18002efcc  lea     rax, [rsp+58h+arg_0]
0x18002efd1  mov     [rsp+58h+var_30], rax; Binding
0x18002efd6  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18002efdd  mov     [rsp+58h+var_38], rax; RPC_WSTR
0x18002efe2  lea     r9, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x18002efe9  mov     r8, rdi; unsigned __int16 *
0x18002efec  lea     rdx, aNcacnNp; "ncacn_np"
0x18002eff3  lea     rcx, a5ca4a760Ebb111; "5ca4a760-ebb1-11cf-8611-00a0245420ed"
0x18002effa  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002efff  test    eax, eax
0x18002f001  jnz     short loc_18002F05F
0x18002f003  lea     rdx, aUsingNonsecure; "Using nonsecure connection!!!"
0x18002f00a  lea     ecx, [rax+8]; int
0x18002f00d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f012  nop
0x18002f013  lea     r8, [rsp+58h+arg_18]
0x18002f018  lea     rdx, [rsp+58h+dwErrCode]
0x18002f01d  mov     rcx, [rsp+58h+arg_0]
0x18002f022  call    RpcWinStationOpenServer
0x18002f027  mov     bl, al
0x18002f029  mov     [rsp+58h+var_28], al
0x18002f02d  jmp     short loc_18002F04E
0x18002f02f  mov     [rsp+58h+dwErrCode], eax
0x18002f033  xor     bl, bl
0x18002f035  mov     [rsp+58h+var_28], bl
0x18002f039  mov     r8d, eax
0x18002f03c  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002f043  mov     ecx, 8; int
0x18002f048  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f04d  nop
0x18002f04e  lea     rcx, [rsp+58h+arg_0]; Binding
0x18002f053  call    cs:__imp_RpcBindingFree
0x18002f05a  nop     dword ptr [rax+rax+00h]
0x18002f05f  test    bl, bl
0x18002f061  jz      short loc_18002F06A
0x18002f063  mov     rax, [rsp+58h+arg_18]
0x18002f068  jmp     short loc_18002F092
0x18002f06a  mov     r8d, [rsp+58h+dwErrCode]
0x18002f06f  lea     rdx, aWinstationopen_5; "WinStationOpenServerW: Error %d getting"...
0x18002f076  mov     ecx, 8; int
0x18002f07b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f080  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18002f084  call    cs:__imp_SetLastError
0x18002f08b  nop     dword ptr [rax+rax+00h]
0x18002f090  xor     eax, eax
0x18002f092  add     rsp, 48h
0x18002f096  pop     rdi
0x18002f097  pop     rbx
0x18002f098  retn
0x180033c6a  push    rbp
0x180033c6c  sub     rsp, 30h
0x180033c70  mov     rbp, rdx
0x180033c73  mov     rcx, [rcx]
0x180033c76  mov     ecx, [rcx]; ExceptionCode
0x180033c78  call    cs:__imp_I_RpcExceptionFilter
0x180033c7f  nop     dword ptr [rax+rax+00h]
0x180033c84  nop
0x180033c85  add     rsp, 30h
0x180033c89  pop     rbp
0x180033c8a  retn
0x180033c8c  push    rbp
0x180033c8e  sub     rsp, 30h
0x180033c92  mov     rbp, rdx
0x180033c95  mov     rcx, [rcx]
0x180033c98  mov     ecx, [rcx]; ExceptionCode
0x180033c9a  call    cs:__imp_I_RpcExceptionFilter
0x180033ca1  nop     dword ptr [rax+rax+00h]
0x180033ca6  nop
0x180033ca7  add     rsp, 30h
0x180033cab  pop     rbp
0x180033cac  retn
```
