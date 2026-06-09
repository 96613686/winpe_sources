# TFunction3<void *,ulong,Call_Route>::Run(void)

- ea: `0x140045940`
- end: `0x1400459ec`
- name: `?Run@?$TFunction3@PEAXKW4Call_Route@@@@UEAAJXZ`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045940`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400459b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400459b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045969`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400459ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045969`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400459ad`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004599f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004599f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400459cb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400459cb`
- `RPCRT4!RpcImpersonateClient` at `0x140045976`
- `RPCRT4!RpcImpersonateClient` at `0x140045976`

## pseudocode

```c
__int64 __fastcall TFunction3<void *,unsigned long,enum Call_Route>::Run(__int64 a1)
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 120))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(unsigned int *)(a1 + 116));
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
0x140045940  mov     [rsp+arg_8], rbx
0x140045945  push    rdi
0x140045946  sub     rsp, 20h
0x14004594a  mov     rax, [rcx+80h]
0x140045951  mov     rbx, rcx
0x140045954  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004595a  mov     [rsp+28h+Reply], 0
0x140045962  mov     rdi, [rax+20h]
0x140045966  mov     rdx, rdi; lpTlsValue
0x140045969  call    cs:__imp_TlsSetValue
0x14004596f  test    eax, eax
0x140045971  jz      short loc_1400459B5
0x140045973  mov     rcx, rdi; BindingHandle
0x140045976  call    cs:__imp_RpcImpersonateClient
0x14004597c  mov     [rsp+28h+Reply], eax
0x140045980  test    eax, eax
0x140045982  jnz     short loc_1400459A5
0x140045984  mov     r8d, [rbx+74h]
0x140045988  mov     edx, [rbx+70h]
0x14004598b  mov     rcx, [rbx+68h]
0x14004598f  mov     rax, [rbx+78h]
0x140045993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045998  mov     rcx, rdi; BindingHandle
0x14004599b  mov     [rsp+28h+Reply], eax
0x14004599f  call    cs:__imp_RpcRevertToSelfEx
0x1400459a5  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400459ab  xor     edx, edx; lpTlsValue
0x1400459ad  call    cs:__imp_TlsSetValue
0x1400459b3  jmp     short loc_1400459BF
0x1400459b5  call    cs:__imp_GetLastError
0x1400459bb  mov     [rsp+28h+Reply], eax
0x1400459bf  mov     rcx, [rbx+80h]; pAsync
0x1400459c6  lea     rdx, [rsp+28h+Reply]; Reply
0x1400459cb  call    cs:__imp_RpcAsyncCompleteCall
0x1400459d1  mov     eax, [rsp+28h+Reply]
0x1400459d5  test    eax, eax
0x1400459d7  jle     short loc_1400459E1
0x1400459d9  movzx   eax, ax
0x1400459dc  or      eax, 80070000h
0x1400459e1  mov     rbx, [rsp+28h+arg_8]
0x1400459e6  add     rsp, 20h
0x1400459ea  pop     rdi
0x1400459eb  retn
```
