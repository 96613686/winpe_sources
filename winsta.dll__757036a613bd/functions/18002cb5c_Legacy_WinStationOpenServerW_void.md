# Legacy_WinStationOpenServerW(void *)

- ea: `0x18002cb5c`
- end: `0x18002ccf7`
- name: `?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z`
- size: `411`
- prototype: `void *__fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d438`
- `0x18002eabc`

## callees

- `0x180007890`
- `0x18000c0e8`
- `0x18000c250`
- `0x180024618`
- `0x18002cb5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cce8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cce8`
- `RPCRT4!RpcBindingFree` at `0x18002cbf2`
- `RPCRT4!RpcBindingFree` at `0x18002ccbd`
- `RPCRT4!RpcBindingFree` at `0x18002cbf2`
- `RPCRT4!RpcBindingFree` at `0x18002ccbd`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d44`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d60`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d44`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d60`

## string_xrefs

- `0x18002cc40`: `Security=Impersonation Dynamic False`
- `0x18002ccd3`: `WinStationOpenServerW: Error %d getting context handle`
- `0x18002cb8c`: `\pipe\Ctx_WinStation_API_service`
- `0x18002cc4c`: `\pipe\Ctx_WinStation_API_service`

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
0x18002cb5c  mov     rax, rsp
0x18002cb5f  mov     [rax+8], rcx
0x18002cb63  push    rbx
0x18002cb64  push    rdi
0x18002cb65  sub     rsp, 48h
0x18002cb69  mov     rdi, rcx
0x18002cb6c  mov     dword ptr [rax+10h], 5
0x18002cb73  mov     qword ptr [rax+20h], 0
0x18002cb7b  mov     qword ptr [rax+18h], 0
0x18002cb83  lea     rax, [rax+18h]
0x18002cb87  mov     [rsp+58h+var_30], rax; void **
0x18002cb8c  lea     r9, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x18002cb93  mov     r8, rcx; unsigned __int16 *
0x18002cb96  lea     rcx, a5ca4a760Ebb111; "5ca4a760-ebb1-11cf-8611-00a0245420ed"
0x18002cb9d  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002cba2  mov     [rsp+58h+dwErrCode], eax
0x18002cba6  lea     r8, [rsp+58h+arg_18]
0x18002cbab  lea     rdx, [rsp+58h+dwErrCode]
0x18002cbb0  mov     rcx, [rsp+58h+Binding]
0x18002cbb5  call    RpcWinStationOpenServer
0x18002cbba  mov     bl, al
0x18002cbbc  mov     [rsp+58h+var_28], al
0x18002cbc0  jmp     short loc_18002CBE5
0x18002cbc2  mov     [rsp+58h+dwErrCode], eax
0x18002cbc6  xor     bl, bl
0x18002cbc8  mov     [rsp+58h+var_28], bl
0x18002cbcc  mov     r8d, eax
0x18002cbcf  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002cbd6  mov     ecx, 8; int
0x18002cbdb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cbe0  mov     rdi, [rsp+58h+arg_0]
0x18002cbe5  cmp     [rsp+58h+Binding], 0
0x18002cbeb  jz      short loc_18002CC10
0x18002cbed  lea     rcx, [rsp+58h+Binding]; Binding
0x18002cbf2  call    cs:__imp_RpcBindingFree
0x18002cbf8  test    eax, eax
0x18002cbfa  jz      short loc_18002CC10
0x18002cbfc  mov     r8d, eax
0x18002cbff  lea     rdx, aRpcbindingfree_0; "RpcBindingFree failed 0x%x"
0x18002cc06  mov     ecx, 8; int
0x18002cc0b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cc10  test    bl, bl
0x18002cc12  jnz     loc_18002CCC7
0x18002cc18  cmp     [rsp+58h+dwErrCode], 6D3h
0x18002cc20  jz      short loc_18002CC2D
0x18002cc22  cmp     [rsp+58h+dwErrCode], 5
0x18002cc27  jnz     loc_18002CCC3
0x18002cc2d  mov     [rsp+58h+arg_0], 0
0x18002cc36  lea     rax, [rsp+58h+arg_0]
0x18002cc3b  mov     [rsp+58h+var_30], rax; Binding
0x18002cc40  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18002cc47  mov     [rsp+58h+var_38], rax; RPC_WSTR
0x18002cc4c  lea     r9, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x18002cc53  mov     r8, rdi; unsigned __int16 *
0x18002cc56  lea     rdx, aNcacnNp; "ncacn_np"
0x18002cc5d  lea     rcx, a5ca4a760Ebb111; "5ca4a760-ebb1-11cf-8611-00a0245420ed"
0x18002cc64  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002cc69  test    eax, eax
0x18002cc6b  jnz     short loc_18002CCC3
0x18002cc6d  lea     rdx, aUsingNonsecure; "Using nonsecure connection!!!"
0x18002cc74  lea     ecx, [rax+8]; int
0x18002cc77  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cc7c  nop
0x18002cc7d  lea     r8, [rsp+58h+arg_18]
0x18002cc82  lea     rdx, [rsp+58h+dwErrCode]
0x18002cc87  mov     rcx, [rsp+58h+arg_0]
0x18002cc8c  call    RpcWinStationOpenServer
0x18002cc91  mov     bl, al
0x18002cc93  mov     [rsp+58h+var_28], al
0x18002cc97  jmp     short loc_18002CCB8
0x18002cc99  mov     [rsp+58h+dwErrCode], eax
0x18002cc9d  xor     bl, bl
0x18002cc9f  mov     [rsp+58h+var_28], bl
0x18002cca3  mov     r8d, eax
0x18002cca6  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002ccad  mov     ecx, 8; int
0x18002ccb2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ccb7  nop
0x18002ccb8  lea     rcx, [rsp+58h+arg_0]; Binding
0x18002ccbd  call    cs:__imp_RpcBindingFree
0x18002ccc3  test    bl, bl
0x18002ccc5  jz      short loc_18002CCCE
0x18002ccc7  mov     rax, [rsp+58h+arg_18]
0x18002cccc  jmp     short loc_18002CCF0
0x18002ccce  mov     r8d, [rsp+58h+dwErrCode]
0x18002ccd3  lea     rdx, aWinstationopen_5; "WinStationOpenServerW: Error %d getting"...
0x18002ccda  mov     ecx, 8; int
0x18002ccdf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cce4  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18002cce8  call    cs:__imp_SetLastError
0x18002ccee  xor     eax, eax
0x18002ccf0  add     rsp, 48h
0x18002ccf4  pop     rdi
0x18002ccf5  pop     rbx
0x18002ccf6  retn
0x180030d36  push    rbp
0x180030d38  sub     rsp, 30h
0x180030d3c  mov     rbp, rdx
0x180030d3f  mov     rcx, [rcx]
0x180030d42  mov     ecx, [rcx]; ExceptionCode
0x180030d44  call    cs:__imp_I_RpcExceptionFilter
0x180030d4a  nop
0x180030d4b  add     rsp, 30h
0x180030d4f  pop     rbp
0x180030d50  retn
0x180030d52  push    rbp
0x180030d54  sub     rsp, 30h
0x180030d58  mov     rbp, rdx
0x180030d5b  mov     rcx, [rcx]
0x180030d5e  mov     ecx, [rcx]; ExceptionCode
0x180030d60  call    cs:__imp_I_RpcExceptionFilter
0x180030d66  nop
0x180030d67  add     rsp, 30h
0x180030d6b  pop     rbp
0x180030d6c  retn
```
