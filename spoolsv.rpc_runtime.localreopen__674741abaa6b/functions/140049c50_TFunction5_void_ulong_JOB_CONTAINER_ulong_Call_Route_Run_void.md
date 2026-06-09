# TFunction5<void *,ulong,_JOB_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x140049c50`
- end: `0x140049d35`
- name: `?Run@?$TFunction5@PEAXKPEAU_JOB_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049c50`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049cf1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049c79`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049ce3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049c79`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049ce3`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049ccf`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049ccf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049d0d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049d0d`
- `RPCRT4!RpcImpersonateClient` at `0x140049c8c`
- `RPCRT4!RpcImpersonateClient` at `0x140049c8c`

## pseudocode

```c
__int64 __fastcall TFunction5<void *,unsigned long,_JOB_CONTAINER *,unsigned long,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 144);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 136))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_DWORD *)(a1 + 132));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 144), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140049c50  mov     [rsp+arg_8], rbx
0x140049c55  push    rdi
0x140049c56  sub     rsp, 30h
0x140049c5a  mov     rax, [rcx+90h]
0x140049c61  mov     rbx, rcx
0x140049c64  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049c6a  mov     [rsp+38h+Reply], 0
0x140049c72  mov     rdi, [rax+20h]
0x140049c76  mov     rdx, rdi; lpTlsValue
0x140049c79  call    cs:__imp_TlsSetValue
0x140049c80  nop     dword ptr [rax+rax+00h]
0x140049c85  test    eax, eax
0x140049c87  jz      short loc_140049CF1
0x140049c89  mov     rcx, rdi; BindingHandle
0x140049c8c  call    cs:__imp_RpcImpersonateClient
0x140049c93  nop     dword ptr [rax+rax+00h]
0x140049c98  mov     [rsp+38h+Reply], eax
0x140049c9c  test    eax, eax
0x140049c9e  jnz     short loc_140049CDB
0x140049ca0  mov     edx, [rbx+84h]
0x140049ca6  mov     r9d, [rbx+80h]
0x140049cad  mov     r8, [rbx+78h]
0x140049cb1  mov     rcx, [rbx+68h]
0x140049cb5  mov     rax, [rbx+88h]
0x140049cbc  mov     [rsp+38h+var_18], edx
0x140049cc0  mov     edx, [rbx+70h]
0x140049cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049cc8  mov     rcx, rdi; BindingHandle
0x140049ccb  mov     [rsp+38h+Reply], eax
0x140049ccf  call    cs:__imp_RpcRevertToSelfEx
0x140049cd6  nop     dword ptr [rax+rax+00h]
0x140049cdb  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049ce1  xor     edx, edx; lpTlsValue
0x140049ce3  call    cs:__imp_TlsSetValue
0x140049cea  nop     dword ptr [rax+rax+00h]
0x140049cef  jmp     short loc_140049D01
0x140049cf1  call    cs:__imp_GetLastError
0x140049cf8  nop     dword ptr [rax+rax+00h]
0x140049cfd  mov     [rsp+38h+Reply], eax
0x140049d01  mov     rcx, [rbx+90h]; pAsync
0x140049d08  lea     rdx, [rsp+38h+Reply]; Reply
0x140049d0d  call    cs:__imp_RpcAsyncCompleteCall
0x140049d14  nop     dword ptr [rax+rax+00h]
0x140049d19  mov     eax, [rsp+38h+Reply]
0x140049d1d  test    eax, eax
0x140049d1f  jle     short loc_140049D29
0x140049d21  movzx   eax, ax
0x140049d24  or      eax, 80070000h
0x140049d29  mov     rbx, [rsp+38h+arg_8]
0x140049d2e  add     rsp, 30h
0x140049d32  pop     rdi
0x140049d33  retn
```
