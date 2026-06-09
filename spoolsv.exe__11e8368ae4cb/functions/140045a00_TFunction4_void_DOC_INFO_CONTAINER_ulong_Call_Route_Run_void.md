# TFunction4<void *,_DOC_INFO_CONTAINER *,ulong *,Call_Route>::Run(void)

- ea: `0x140045a00`
- end: `0x140045ab7`
- name: `?Run@?$TFunction4@PEAXPEAU_DOC_INFO_CONTAINER@@PEAKW4Call_Route@@@@UEAAJXZ`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045a00`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045a80`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045a29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045a78`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045a29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045a78`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045a6a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045a6a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045a96`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045a96`
- `RPCRT4!RpcImpersonateClient` at `0x140045a36`
- `RPCRT4!RpcImpersonateClient` at `0x140045a36`

## pseudocode

```c
__int64 __fastcall TFunction4<void *,_DOC_INFO_CONTAINER *,unsigned long *,enum Call_Route>::Run(__int64 a1)
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 136))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128));
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
0x140045a00  mov     [rsp+arg_8], rbx
0x140045a05  push    rdi
0x140045a06  sub     rsp, 30h
0x140045a0a  mov     rax, [rcx+90h]
0x140045a11  mov     rbx, rcx
0x140045a14  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045a1a  mov     [rsp+38h+Reply], 0
0x140045a22  mov     rdi, [rax+20h]
0x140045a26  mov     rdx, rdi; lpTlsValue
0x140045a29  call    cs:__imp_TlsSetValue
0x140045a2f  test    eax, eax
0x140045a31  jz      short loc_140045A80
0x140045a33  mov     rcx, rdi; BindingHandle
0x140045a36  call    cs:__imp_RpcImpersonateClient
0x140045a3c  mov     [rsp+38h+Reply], eax
0x140045a40  test    eax, eax
0x140045a42  jnz     short loc_140045A70
0x140045a44  mov     r9d, [rbx+80h]
0x140045a4b  mov     r8, [rbx+78h]
0x140045a4f  mov     rdx, [rbx+70h]
0x140045a53  mov     rcx, [rbx+68h]
0x140045a57  mov     rax, [rbx+88h]
0x140045a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045a63  mov     rcx, rdi; BindingHandle
0x140045a66  mov     [rsp+38h+Reply], eax
0x140045a6a  call    cs:__imp_RpcRevertToSelfEx
0x140045a70  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045a76  xor     edx, edx; lpTlsValue
0x140045a78  call    cs:__imp_TlsSetValue
0x140045a7e  jmp     short loc_140045A8A
0x140045a80  call    cs:__imp_GetLastError
0x140045a86  mov     [rsp+38h+Reply], eax
0x140045a8a  mov     rcx, [rbx+90h]; pAsync
0x140045a91  lea     rdx, [rsp+38h+Reply]; Reply
0x140045a96  call    cs:__imp_RpcAsyncCompleteCall
0x140045a9c  mov     eax, [rsp+38h+Reply]
0x140045aa0  test    eax, eax
0x140045aa2  jle     short loc_140045AAC
0x140045aa4  movzx   eax, ax
0x140045aa7  or      eax, 80070000h
0x140045aac  mov     rbx, [rsp+38h+arg_8]
0x140045ab1  add     rsp, 30h
0x140045ab5  pop     rdi
0x140045ab6  retn
```
