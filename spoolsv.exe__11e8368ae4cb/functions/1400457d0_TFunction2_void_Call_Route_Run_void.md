# TFunction2<void *,Call_Route>::Run(void)

- ea: `0x1400457d0`
- end: `0x140045878`
- name: `?Run@?$TFunction2@PEAXW4Call_Route@@@@UEAAJXZ`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400457d0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045841`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400457f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045839`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400457f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045839`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004582b`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004582b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045857`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045857`
- `RPCRT4!RpcImpersonateClient` at `0x140045806`
- `RPCRT4!RpcImpersonateClient` at `0x140045806`

## pseudocode

```c
__int64 __fastcall TFunction2<void *,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 128);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 120))(*(_QWORD *)(a1 + 104), *(unsigned int *)(a1 + 112));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 128), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400457d0  mov     [rsp+arg_8], rbx
0x1400457d5  push    rdi
0x1400457d6  sub     rsp, 20h
0x1400457da  mov     rax, [rcx+80h]
0x1400457e1  mov     rbx, rcx
0x1400457e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400457ea  mov     [rsp+28h+Reply], 0
0x1400457f2  mov     rdi, [rax+20h]
0x1400457f6  mov     rdx, rdi; lpTlsValue
0x1400457f9  call    cs:__imp_TlsSetValue
0x1400457ff  test    eax, eax
0x140045801  jz      short loc_140045841
0x140045803  mov     rcx, rdi; BindingHandle
0x140045806  call    cs:__imp_RpcImpersonateClient
0x14004580c  mov     [rsp+28h+Reply], eax
0x140045810  test    eax, eax
0x140045812  jnz     short loc_140045831
0x140045814  mov     edx, [rbx+70h]
0x140045817  mov     rcx, [rbx+68h]
0x14004581b  mov     rax, [rbx+78h]
0x14004581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045824  mov     rcx, rdi; BindingHandle
0x140045827  mov     [rsp+28h+Reply], eax
0x14004582b  call    cs:__imp_RpcRevertToSelfEx
0x140045831  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045837  xor     edx, edx; lpTlsValue
0x140045839  call    cs:__imp_TlsSetValue
0x14004583f  jmp     short loc_14004584B
0x140045841  call    cs:__imp_GetLastError
0x140045847  mov     [rsp+28h+Reply], eax
0x14004584b  mov     rcx, [rbx+80h]; pAsync
0x140045852  lea     rdx, [rsp+28h+Reply]; Reply
0x140045857  call    cs:__imp_RpcAsyncCompleteCall
0x14004585d  mov     eax, [rsp+28h+Reply]
0x140045861  test    eax, eax
0x140045863  jle     short loc_14004586D
0x140045865  movzx   eax, ax
0x140045868  or      eax, 80070000h
0x14004586d  mov     rbx, [rsp+28h+arg_8]
0x140045872  add     rsp, 20h
0x140045876  pop     rdi
0x140045877  retn
```
