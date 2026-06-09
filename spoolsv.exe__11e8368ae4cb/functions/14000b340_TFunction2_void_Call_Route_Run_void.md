# TFunction2<void * *,Call_Route>::Run(void)

- ea: `0x14000b340`
- end: `0x14000b3ea`
- name: `?Run@?$TFunction2@PEAPEAXW4Call_Route@@@@UEAAJXZ`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b340`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b3de`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b369`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b3a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b369`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b3a9`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000b39b`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000b39b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b3bb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b3bb`
- `RPCRT4!RpcImpersonateClient` at `0x14000b376`
- `RPCRT4!RpcImpersonateClient` at `0x14000b376`

## pseudocode

```c
__int64 __fastcall TFunction2<void * *,enum Call_Route>::Run(__int64 a1)
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
0x14000b340  mov     [rsp+arg_8], rbx
0x14000b345  push    rdi
0x14000b346  sub     rsp, 20h
0x14000b34a  mov     rax, [rcx+80h]
0x14000b351  mov     rbx, rcx
0x14000b354  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000b35a  mov     [rsp+28h+Reply], 0
0x14000b362  mov     rdi, [rax+20h]
0x14000b366  mov     rdx, rdi; lpTlsValue
0x14000b369  call    cs:__imp_TlsSetValue
0x14000b36f  test    eax, eax
0x14000b371  jz      short loc_14000B3DE
0x14000b373  mov     rcx, rdi; BindingHandle
0x14000b376  call    cs:__imp_RpcImpersonateClient
0x14000b37c  mov     [rsp+28h+Reply], eax
0x14000b380  test    eax, eax
0x14000b382  jnz     short loc_14000B3A1
0x14000b384  mov     edx, [rbx+70h]
0x14000b387  mov     rcx, [rbx+68h]
0x14000b38b  mov     rax, [rbx+78h]
0x14000b38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b394  mov     rcx, rdi; BindingHandle
0x14000b397  mov     [rsp+28h+Reply], eax
0x14000b39b  call    cs:__imp_RpcRevertToSelfEx
0x14000b3a1  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000b3a7  xor     edx, edx; lpTlsValue
0x14000b3a9  call    cs:__imp_TlsSetValue
0x14000b3af  mov     rcx, [rbx+80h]; pAsync
0x14000b3b6  lea     rdx, [rsp+28h+Reply]; Reply
0x14000b3bb  call    cs:__imp_RpcAsyncCompleteCall
0x14000b3c1  mov     eax, [rsp+28h+Reply]
0x14000b3c5  test    eax, eax
0x14000b3c7  jg      short loc_14000B3D4
0x14000b3c9  mov     rbx, [rsp+28h+arg_8]
0x14000b3ce  add     rsp, 20h
0x14000b3d2  pop     rdi
0x14000b3d3  retn
0x14000b3d4  movzx   eax, ax
0x14000b3d7  or      eax, 80070000h
0x14000b3dc  jmp     short loc_14000B3C9
0x14000b3de  call    cs:__imp_GetLastError
0x14000b3e4  mov     [rsp+28h+Reply], eax
0x14000b3e8  jmp     short loc_14000B3AF
```
