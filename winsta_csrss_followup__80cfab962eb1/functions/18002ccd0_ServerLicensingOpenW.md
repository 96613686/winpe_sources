# ServerLicensingOpenW

- ea: `0x18002ccd0`
- end: `0x18002ce21`
- name: `ServerLicensingOpenW`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c6a0`
- `0x18002cc90`

## callees

- `0x18000de00`
- `0x18002ccd0`

## import_xrefs

- `ntdll!RtlGetSuiteMask` at `0x18002ccf9`
- `ntdll!RtlGetSuiteMask` at `0x18002ccf9`
- `ntdll!RtlNtStatusToDosError` at `0x18002cdb9`
- `ntdll!RtlNtStatusToDosError` at `0x18002cdb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cdc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cdc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce0c`
- `RPCRT4!RpcBindingFree` at `0x18002cd5a`
- `RPCRT4!RpcBindingFree` at `0x18002cdef`
- `RPCRT4!RpcBindingFree` at `0x18002cd5a`
- `RPCRT4!RpcBindingFree` at `0x18002cdef`
- `RPCRT4!NdrClientCall3` at `0x18002cd99`
- `RPCRT4!NdrClientCall3` at `0x18002cd99`

## string_xrefs

- `0x18002cd17`: `Security=Impersonation Dynamic False`

## pseudocode

```c
__int64 __fastcall ServerLicensingOpenW(__int64 a1)
{
  CLIENT_CALL_RETURN v1; // rax
  char Pointer; // bl
  DWORD v3; // eax
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
  v1.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18003E438, 0, 0, Binding, &v7, &Status).Pointer;
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
0x18002ccd0  push    rbx
0x18002ccd2  sub     rsp, 40h
0x18002ccd6  mov     [rsp+48h+arg_10], 0
0x18002ccdf  mov     [rsp+48h+Status], 0
0x18002cce7  mov     [rsp+48h+Binding], 0
0x18002ccf0  test    rcx, rcx
0x18002ccf3  jnz     loc_18002CE07
0x18002ccf9  call    cs:__imp_RtlGetSuiteMask
0x18002cd00  nop     dword ptr [rax+rax+00h]
0x18002cd05  test    al, 10h
0x18002cd07  jz      loc_18002CE18
0x18002cd0d  lea     rax, [rsp+48h+Binding]
0x18002cd12  mov     [rsp+48h+var_20], rax; Binding
0x18002cd17  lea     rax, Options; "Security=Impersonation Dynamic False"
0x18002cd1e  mov     [rsp+48h+var_28], rax; RPC_WSTR
0x18002cd23  lea     r9, aLcrpc; "LcRpc"
0x18002cd2a  xor     r8d, r8d; unsigned __int16 *
0x18002cd2d  lea     rdx, ProtSeq; "ncalrpc"
0x18002cd34  lea     rcx, a2f59a331Bf7d48; "2f59a331-bf7d-48cb-9e5c-7c090d76e8b8"
0x18002cd3b  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18002cd40  test    eax, eax
0x18002cd42  jz      short loc_18002CD6B
0x18002cd44  mov     ecx, 6BAh; dwErrCode
0x18002cd49  call    cs:__imp_SetLastError
0x18002cd50  nop     dword ptr [rax+rax+00h]
0x18002cd55  lea     rcx, [rsp+48h+Binding]; Binding
0x18002cd5a  call    cs:__imp_RpcBindingFree
0x18002cd61  nop     dword ptr [rax+rax+00h]
0x18002cd66  jmp     loc_18002CE18
0x18002cd6b  mov     [rsp+48h+arg_18], 0
0x18002cd74  lea     rax, [rsp+48h+Status]
0x18002cd79  mov     [rsp+48h+var_20], rax
0x18002cd7e  lea     rax, [rsp+48h+arg_10]
0x18002cd83  mov     [rsp+48h+var_28], rax
0x18002cd88  mov     r9, [rsp+48h+Binding]
0x18002cd8d  xor     r8d, r8d; pReturnValue
0x18002cd90  xor     edx, edx; nProcNum
0x18002cd92  lea     rcx, stru_18003E438; pProxyInfo
0x18002cd99  call    cs:__imp_NdrClientCall3
0x18002cda0  nop     dword ptr [rax+rax+00h]
0x18002cda5  mov     rbx, rax
0x18002cda8  mov     [rsp+48h+arg_18], rax
0x18002cdad  mov     [rsp+48h+var_18], al
0x18002cdb1  test    al, al
0x18002cdb3  jnz     short loc_18002CDD3
0x18002cdb5  mov     ecx, [rsp+48h+Status]; Status
0x18002cdb9  call    cs:__imp_RtlNtStatusToDosError
0x18002cdc0  nop     dword ptr [rax+rax+00h]
0x18002cdc5  mov     ecx, eax; dwErrCode
0x18002cdc7  call    cs:__imp_SetLastError
0x18002cdce  nop     dword ptr [rax+rax+00h]
0x18002cdd3  jmp     short loc_18002CDEA
0x18002cdd5  xor     bl, bl
0x18002cdd7  mov     [rsp+48h+var_18], bl
0x18002cddb  mov     ecx, eax; dwErrCode
0x18002cddd  call    cs:__imp_SetLastError
0x18002cde4  nop     dword ptr [rax+rax+00h]
0x18002cde9  nop
0x18002cdea  lea     rcx, [rsp+48h+Binding]; Binding
0x18002cdef  call    cs:__imp_RpcBindingFree
0x18002cdf6  nop     dword ptr [rax+rax+00h]
0x18002cdfb  neg     bl
0x18002cdfd  sbb     rax, rax
0x18002ce00  and     rax, [rsp+48h+arg_10]
0x18002ce05  jmp     short loc_18002CE1A
0x18002ce07  mov     ecx, 6BAh; dwErrCode
0x18002ce0c  call    cs:__imp_SetLastError
0x18002ce13  nop     dword ptr [rax+rax+00h]
0x18002ce18  xor     eax, eax
0x18002ce1a  add     rsp, 40h
0x18002ce1e  pop     rbx
0x18002ce1f  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
