# TFunction5<void *,void *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140045de0`
- end: `0x140045ea1`
- name: `?Run@?$TFunction5@PEAXPEAXKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045de0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045e6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045e09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045e62`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045e09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045e62`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045e54`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045e54`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045e80`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045e80`
- `RPCRT4!RpcImpersonateClient` at `0x140045e16`
- `RPCRT4!RpcImpersonateClient` at `0x140045e16`

## pseudocode

```c
__int64 __fastcall TFunction5<void *,void *,unsigned long,unsigned long *,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 144))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 152), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140045de0  mov     [rsp+arg_8], rbx
0x140045de5  push    rdi
0x140045de6  sub     rsp, 30h
0x140045dea  mov     rax, [rcx+98h]
0x140045df1  mov     rbx, rcx
0x140045df4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045dfa  mov     [rsp+38h+Reply], 0
0x140045e02  mov     rdi, [rax+20h]
0x140045e06  mov     rdx, rdi; lpTlsValue
0x140045e09  call    cs:__imp_TlsSetValue
0x140045e0f  test    eax, eax
0x140045e11  jz      short loc_140045E6A
0x140045e13  mov     rcx, rdi; BindingHandle
0x140045e16  call    cs:__imp_RpcImpersonateClient
0x140045e1c  mov     [rsp+38h+Reply], eax
0x140045e20  test    eax, eax
0x140045e22  jnz     short loc_140045E5A
0x140045e24  mov     edx, [rbx+88h]
0x140045e2a  mov     r9, [rbx+80h]
0x140045e31  mov     r8d, [rbx+78h]
0x140045e35  mov     rcx, [rbx+68h]
0x140045e39  mov     rax, [rbx+90h]
0x140045e40  mov     [rsp+38h+var_18], edx
0x140045e44  mov     rdx, [rbx+70h]
0x140045e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e4d  mov     rcx, rdi; BindingHandle
0x140045e50  mov     [rsp+38h+Reply], eax
0x140045e54  call    cs:__imp_RpcRevertToSelfEx
0x140045e5a  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045e60  xor     edx, edx; lpTlsValue
0x140045e62  call    cs:__imp_TlsSetValue
0x140045e68  jmp     short loc_140045E74
0x140045e6a  call    cs:__imp_GetLastError
0x140045e70  mov     [rsp+38h+Reply], eax
0x140045e74  mov     rcx, [rbx+98h]; pAsync
0x140045e7b  lea     rdx, [rsp+38h+Reply]; Reply
0x140045e80  call    cs:__imp_RpcAsyncCompleteCall
0x140045e86  mov     eax, [rsp+38h+Reply]
0x140045e8a  test    eax, eax
0x140045e8c  jle     short loc_140045E96
0x140045e8e  movzx   eax, ax
0x140045e91  or      eax, 80070000h
0x140045e96  mov     rbx, [rsp+38h+arg_8]
0x140045e9b  add     rsp, 30h
0x140045e9f  pop     rdi
0x140045ea0  retn
```
