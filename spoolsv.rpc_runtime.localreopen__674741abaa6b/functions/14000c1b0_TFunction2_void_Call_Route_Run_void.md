# TFunction2<void * *,Call_Route>::Run(void)

- ea: `0x14000c1b0`
- end: `0x14000c283`
- name: `?Run@?$TFunction2@PEAPEAXW4Call_Route@@@@UEAAJXZ`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000c1b0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c271`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c1d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c22f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c1d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c22f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000c21b`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000c21b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000c247`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000c247`
- `RPCRT4!RpcImpersonateClient` at `0x14000c1f0`
- `RPCRT4!RpcImpersonateClient` at `0x14000c1f0`

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
0x14000c1b0  mov     [rsp+arg_8], rbx
0x14000c1b5  push    rdi
0x14000c1b6  sub     rsp, 20h
0x14000c1ba  mov     rax, [rcx+80h]
0x14000c1c1  mov     rbx, rcx
0x14000c1c4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000c1ca  mov     [rsp+28h+Reply], 0
0x14000c1d2  mov     rdi, [rax+20h]
0x14000c1d6  mov     rdx, rdi; lpTlsValue
0x14000c1d9  call    cs:__imp_TlsSetValue
0x14000c1e0  nop     dword ptr [rax+rax+00h]
0x14000c1e5  test    eax, eax
0x14000c1e7  jz      loc_14000C271
0x14000c1ed  mov     rcx, rdi; BindingHandle
0x14000c1f0  call    cs:__imp_RpcImpersonateClient
0x14000c1f7  nop     dword ptr [rax+rax+00h]
0x14000c1fc  mov     [rsp+28h+Reply], eax
0x14000c200  test    eax, eax
0x14000c202  jnz     short loc_14000C227
0x14000c204  mov     edx, [rbx+70h]
0x14000c207  mov     rcx, [rbx+68h]
0x14000c20b  mov     rax, [rbx+78h]
0x14000c20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c214  mov     rcx, rdi; BindingHandle
0x14000c217  mov     [rsp+28h+Reply], eax
0x14000c21b  call    cs:__imp_RpcRevertToSelfEx
0x14000c222  nop     dword ptr [rax+rax+00h]
0x14000c227  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000c22d  xor     edx, edx; lpTlsValue
0x14000c22f  call    cs:__imp_TlsSetValue
0x14000c236  nop     dword ptr [rax+rax+00h]
0x14000c23b  mov     rcx, [rbx+80h]; pAsync
0x14000c242  lea     rdx, [rsp+28h+Reply]; Reply
0x14000c247  call    cs:__imp_RpcAsyncCompleteCall
0x14000c24e  nop     dword ptr [rax+rax+00h]
0x14000c253  mov     eax, [rsp+28h+Reply]
0x14000c257  test    eax, eax
0x14000c259  jg      short loc_14000C267
0x14000c25b  mov     rbx, [rsp+28h+arg_8]
0x14000c260  add     rsp, 20h
0x14000c264  pop     rdi
0x14000c265  retn
0x14000c267  movzx   eax, ax
0x14000c26a  or      eax, 80070000h
0x14000c26f  jmp     short loc_14000C25B
0x14000c271  call    cs:__imp_GetLastError
0x14000c278  nop     dword ptr [rax+rax+00h]
0x14000c27d  mov     [rsp+28h+Reply], eax
0x14000c281  jmp     short loc_14000C23B
```
