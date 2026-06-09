# I_ScValidatePnPService

- ea: `0x18000a1f0`
- end: `0x18000a2f0`
- name: `I_ScValidatePnPService`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180009cb0`

## callees

- `0x18000a1f0`
- `0x18000afb0`
- `0x18000b460`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a237`
- `RPCRT4!RpcImpersonateClient` at `0x18000a24a`
- `RPCRT4!RpcImpersonateClient` at `0x18000a24a`
- `RPCRT4!RpcRevertToSelf` at `0x18000a2b6`
- `RPCRT4!RpcRevertToSelf` at `0x18000a2b6`
- `RPCRT4!NdrClientCall2` at `0x18000a27d`
- `RPCRT4!NdrClientCall2` at `0x18000a27d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fb71`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fb71`

## pseudocode

```c
__int64 __fastcall I_ScValidatePnPService(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  SC_HANDLE v7; // rdi
  DWORD Pointer; // ebx
  CLIENT_CALL_RETURN v9; // rax
  RPC_STATUS v10; // eax
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+40h] [rbp-28h]
  SC_HANDLE v14; // [rsp+48h] [rbp-20h]

  v12 = 0;
  v7 = OpenSCManagerA(0, 0, 1u);
  v14 = v7;
  if ( v7 )
  {
    if ( !a3 || (Pointer = RpcImpersonateClient(0)) == 0 )
    {
      v13.Simple = 0;
      v9.Pointer = NdrClientCall2(&pStubDescriptor, &pFormat, v7, a2, &v12).Pointer;
      Pointer = (DWORD)v9.Pointer;
      v13.Pointer = v9.Pointer;
      if ( a3 )
      {
        v10 = RpcRevertToSelf();
        if ( v10 )
          Pointer = v10;
      }
      if ( !Pointer )
        *a4 = v12;
    }
  }
  else
  {
    Pointer = GetLastError();
  }
  if ( v7 )
    CloseServiceHandle(v7);
  return Pointer;
}

```

## disassembly

```asm
0x18000a1f0  mov     rax, rsp
0x18000a1f3  mov     [rax+8], rbx
0x18000a1f7  mov     [rax+10h], rsi
0x18000a1fb  mov     [rax+20h], r9
0x18000a1ff  mov     [rax+18h], r8d
0x18000a203  push    rdi
0x18000a204  push    r14
0x18000a206  push    r15
0x18000a208  sub     rsp, 50h
0x18000a20c  mov     r14, r9
0x18000a20f  mov     esi, r8d
0x18000a212  mov     r15, rdx
0x18000a215  mov     qword ptr [rax-30h], 0
0x18000a21d  xor     edx, edx; lpDatabaseName
0x18000a21f  xor     ecx, ecx; lpMachineName
0x18000a221  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000a225  call    OpenSCManagerA
0x18000a22a  mov     rdi, rax
0x18000a22d  mov     [rsp+68h+var_20], rax
0x18000a232  test    rax, rax
0x18000a235  jnz     short loc_18000A244
0x18000a237  call    cs:__imp_GetLastError
0x18000a23d  mov     ebx, eax
0x18000a23f  jmp     loc_18000A2CD
0x18000a244  test    esi, esi
0x18000a246  jz      short loc_18000A256
0x18000a248  xor     ecx, ecx; BindingHandle
0x18000a24a  call    cs:__imp_RpcImpersonateClient
0x18000a250  mov     ebx, eax
0x18000a252  test    eax, eax
0x18000a254  jnz     short loc_18000A2CD
0x18000a256  mov     [rsp+68h+var_28], 0
0x18000a25f  lea     rax, [rsp+68h+var_30]
0x18000a264  mov     [rsp+68h+var_48], rax
0x18000a269  mov     r9, r15
0x18000a26c  mov     r8, rdi
0x18000a26f  lea     rdx, pFormat; pFormat
0x18000a276  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000a27d  call    cs:__imp_NdrClientCall2
0x18000a283  mov     rbx, rax
0x18000a286  mov     [rsp+68h+var_28], rax
0x18000a28b  mov     [rsp+68h+var_38], eax
0x18000a28f  jmp     short loc_18000A2B2
0x18000a291  mov     ecx, eax; unsigned int
0x18000a293  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000a298  mov     ebx, eax
0x18000a29a  mov     [rsp+68h+var_38], eax
0x18000a29e  mov     r14, [rsp+68h+arg_18]
0x18000a2a6  mov     esi, [rsp+68h+arg_10]
0x18000a2ad  mov     rdi, [rsp+68h+var_20]
0x18000a2b2  test    esi, esi
0x18000a2b4  jz      short loc_18000A2C1
0x18000a2b6  call    cs:__imp_RpcRevertToSelf
0x18000a2bc  test    eax, eax
0x18000a2be  cmovnz  ebx, eax
0x18000a2c1  test    ebx, ebx
0x18000a2c3  jnz     short loc_18000A2CD
0x18000a2c5  mov     rax, [rsp+68h+var_30]
0x18000a2ca  mov     [r14], rax
0x18000a2cd  test    rdi, rdi
0x18000a2d0  jz      short loc_18000A2DA
0x18000a2d2  mov     rcx, rdi; hSCObject
0x18000a2d5  call    CloseServiceHandle
0x18000a2da  mov     eax, ebx
0x18000a2dc  mov     rbx, [rsp+68h+arg_0]
0x18000a2e1  mov     rsi, [rsp+68h+arg_8]
0x18000a2e6  add     rsp, 50h
0x18000a2ea  pop     r15
0x18000a2ec  pop     r14
0x18000a2ee  pop     rdi
0x18000a2ef  retn
0x18004fb63  push    rbp
0x18004fb65  sub     rsp, 30h
0x18004fb69  mov     rbp, rdx
0x18004fb6c  mov     rcx, [rcx]
0x18004fb6f  mov     ecx, [rcx]; ExceptionCode
0x18004fb71  call    cs:__imp_I_RpcExceptionFilter
0x18004fb77  nop
0x18004fb78  add     rsp, 30h
0x18004fb7c  pop     rbp
0x18004fb7d  retn
```
