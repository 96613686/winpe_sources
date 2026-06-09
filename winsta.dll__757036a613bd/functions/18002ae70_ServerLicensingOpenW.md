# ServerLicensingOpenW

- ea: `0x18002ae70`
- end: `0x18002af8a`
- name: `ServerLicensingOpenW`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a908`
- `0x18002ae40`

## callees

- `0x18000c250`
- `0x18002ae70`

## import_xrefs

- `ntdll!RtlGetSuiteMask` at `0x18002ae99`
- `ntdll!RtlGetSuiteMask` at `0x18002ae99`
- `ntdll!RtlNtStatusToDosError` at `0x18002af41`
- `ntdll!RtlNtStatusToDosError` at `0x18002af41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af7c`
- `RPCRT4!RpcBindingFree` at `0x18002aeee`
- `RPCRT4!RpcBindingFree` at `0x18002af65`
- `RPCRT4!RpcBindingFree` at `0x18002aeee`
- `RPCRT4!RpcBindingFree` at `0x18002af65`
- `RPCRT4!NdrClientCall3` at `0x18002af27`
- `RPCRT4!NdrClientCall3` at `0x18002af27`

## string_xrefs

- `0x18002aeb1`: `Security=Impersonation Dynamic False`

## pseudocode

```c
__int64 __fastcall ServerLicensingOpenW(__int64 a1)
{
  CLIENT_CALL_RETURN v1; // rax
  char Pointer; // bl
  ULONG v3; // eax
  NTSTATUS Status; // [rsp+50h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp+10h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v8; // [rsp+68h] [rbp+20h]

  v7 = 0;
  Status = 0;
  Binding = 0;
  if ( a1 )
  {
    SetLastError(0x6BAu);
    return 0;
  }
  if ( (RtlGetSuiteMask() & 0x10) == 0 )
    return 0;
  if ( (unsigned int)CRpcUtils::Bind(
                       L"2f59a331-bf7d-48cb-9e5c-7c090d76e8b8",
                       L"ncalrpc",
                       0,
                       L"LcRpc",
                       (RPC_WSTR)L"Security=Impersonation Dynamic False",
                       &Binding) )
  {
    SetLastError(0x6BAu);
    RpcBindingFree(&Binding);
    return 0;
  }
  v8.Simple = 0;
  v1.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18003B438, 0, 0, Binding, &v7, &Status).Pointer;
  Pointer = (char)v1.Pointer;
  v8.Pointer = v1.Pointer;
  if ( !LOBYTE(v1.Pointer) )
  {
    v3 = RtlNtStatusToDosError(Status);
    SetLastError(v3);
  }
  RpcBindingFree(&Binding);
  return v7 & -(__int64)(Pointer != 0);
}

```

## disassembly

```asm
0x18002ae70  push    rbx
0x18002ae72  sub     rsp, 40h
0x18002ae76  mov     [rsp+48h+arg_10], 0
0x18002ae7f  mov     [rsp+48h+Status], 0
0x18002ae87  mov     [rsp+48h+Binding], 0
0x18002ae90  test    rcx, rcx
0x18002ae93  jnz     loc_18002AF77
0x18002ae99  call    cs:__imp_RtlGetSuiteMask
0x18002ae9f  test    al, 10h
0x18002aea1  jz      loc_18002AF82
0x18002aea7  lea     rax, [rsp+48h+Binding]
0x18002aeac  mov     [rsp+48h+var_20], rax; Binding
0x18002aeb1  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18002aeb8  mov     [rsp+48h+var_28], rax; RPC_WSTR
0x18002aebd  lea     r9, aLcrpc; "LcRpc"
0x18002aec4  xor     r8d, r8d; unsigned __int16 *
0x18002aec7  lea     rdx, ProtSeq; "ncalrpc"
0x18002aece  lea     rcx, a2f59a331Bf7d48; "2f59a331-bf7d-48cb-9e5c-7c090d76e8b8"
0x18002aed5  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002aeda  test    eax, eax
0x18002aedc  jz      short loc_18002AEF9
0x18002aede  mov     ecx, 6BAh; dwErrCode
0x18002aee3  call    cs:__imp_SetLastError
0x18002aee9  lea     rcx, [rsp+48h+Binding]; Binding
0x18002aeee  call    cs:__imp_RpcBindingFree
0x18002aef4  jmp     loc_18002AF82
0x18002aef9  mov     [rsp+48h+arg_18], 0
0x18002af02  lea     rax, [rsp+48h+Status]
0x18002af07  mov     [rsp+48h+var_20], rax
0x18002af0c  lea     rax, [rsp+48h+arg_10]
0x18002af11  mov     [rsp+48h+var_28], rax
0x18002af16  mov     r9, [rsp+48h+Binding]
0x18002af1b  xor     r8d, r8d; pReturnValue
0x18002af1e  xor     edx, edx; nProcNum
0x18002af20  lea     rcx, stru_18003B438; pProxyInfo
0x18002af27  call    cs:__imp_NdrClientCall3
0x18002af2d  mov     rbx, rax
0x18002af30  mov     [rsp+48h+arg_18], rax
0x18002af35  mov     [rsp+48h+var_18], al
0x18002af39  test    al, al
0x18002af3b  jnz     short loc_18002AF4F
0x18002af3d  mov     ecx, [rsp+48h+Status]; Status
0x18002af41  call    cs:__imp_RtlNtStatusToDosError
0x18002af47  mov     ecx, eax; dwErrCode
0x18002af49  call    cs:__imp_SetLastError
0x18002af4f  jmp     short loc_18002AF60
0x18002af51  xor     bl, bl
0x18002af53  mov     [rsp+48h+var_18], bl
0x18002af57  mov     ecx, eax; dwErrCode
0x18002af59  call    cs:__imp_SetLastError
0x18002af5f  nop
0x18002af60  lea     rcx, [rsp+48h+Binding]; Binding
0x18002af65  call    cs:__imp_RpcBindingFree
0x18002af6b  neg     bl
0x18002af6d  sbb     rax, rax
0x18002af70  and     rax, [rsp+48h+arg_10]
0x18002af75  jmp     short loc_18002AF84
0x18002af77  mov     ecx, 6BAh; dwErrCode
0x18002af7c  call    cs:__imp_SetLastError
0x18002af82  xor     eax, eax
0x18002af84  add     rsp, 40h
0x18002af88  pop     rbx
0x18002af89  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
