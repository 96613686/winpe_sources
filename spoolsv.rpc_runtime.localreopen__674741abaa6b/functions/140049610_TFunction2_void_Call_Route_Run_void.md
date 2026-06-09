# TFunction2<void *,Call_Route>::Run(void)

- ea: `0x140049610`
- end: `0x1400496dd`
- name: `?Run@?$TFunction2@PEAXW4Call_Route@@@@UEAAJXZ`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049610`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049699`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049639`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004968b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049639`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004968b`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049677`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049677`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400496b5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400496b5`
- `RPCRT4!RpcImpersonateClient` at `0x14004964c`
- `RPCRT4!RpcImpersonateClient` at `0x14004964c`

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
0x140049610  mov     [rsp+arg_8], rbx
0x140049615  push    rdi
0x140049616  sub     rsp, 20h
0x14004961a  mov     rax, [rcx+80h]
0x140049621  mov     rbx, rcx
0x140049624  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004962a  mov     [rsp+28h+Reply], 0
0x140049632  mov     rdi, [rax+20h]
0x140049636  mov     rdx, rdi; lpTlsValue
0x140049639  call    cs:__imp_TlsSetValue
0x140049640  nop     dword ptr [rax+rax+00h]
0x140049645  test    eax, eax
0x140049647  jz      short loc_140049699
0x140049649  mov     rcx, rdi; BindingHandle
0x14004964c  call    cs:__imp_RpcImpersonateClient
0x140049653  nop     dword ptr [rax+rax+00h]
0x140049658  mov     [rsp+28h+Reply], eax
0x14004965c  test    eax, eax
0x14004965e  jnz     short loc_140049683
0x140049660  mov     edx, [rbx+70h]
0x140049663  mov     rcx, [rbx+68h]
0x140049667  mov     rax, [rbx+78h]
0x14004966b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049670  mov     rcx, rdi; BindingHandle
0x140049673  mov     [rsp+28h+Reply], eax
0x140049677  call    cs:__imp_RpcRevertToSelfEx
0x14004967e  nop     dword ptr [rax+rax+00h]
0x140049683  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049689  xor     edx, edx; lpTlsValue
0x14004968b  call    cs:__imp_TlsSetValue
0x140049692  nop     dword ptr [rax+rax+00h]
0x140049697  jmp     short loc_1400496A9
0x140049699  call    cs:__imp_GetLastError
0x1400496a0  nop     dword ptr [rax+rax+00h]
0x1400496a5  mov     [rsp+28h+Reply], eax
0x1400496a9  mov     rcx, [rbx+80h]; pAsync
0x1400496b0  lea     rdx, [rsp+28h+Reply]; Reply
0x1400496b5  call    cs:__imp_RpcAsyncCompleteCall
0x1400496bc  nop     dword ptr [rax+rax+00h]
0x1400496c1  mov     eax, [rsp+28h+Reply]
0x1400496c5  test    eax, eax
0x1400496c7  jle     short loc_1400496D1
0x1400496c9  movzx   eax, ax
0x1400496cc  or      eax, 80070000h
0x1400496d1  mov     rbx, [rsp+28h+arg_8]
0x1400496d6  add     rsp, 20h
0x1400496da  pop     rdi
0x1400496db  retn
```
