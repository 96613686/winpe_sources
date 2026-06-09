# TFunction3<ushort *,ushort const *,Call_Route>::Run(void)

- ea: `0x140045880`
- end: `0x140045930`
- name: `?Run@?$TFunction3@PEAGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045880`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400458f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400458f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400458a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400458f1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400458a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400458f1`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400458e3`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400458e3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004590f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004590f`
- `RPCRT4!RpcImpersonateClient` at `0x1400458b6`
- `RPCRT4!RpcImpersonateClient` at `0x1400458b6`

## pseudocode

```c
__int64 __fastcall TFunction3<unsigned short *,unsigned short const *,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 136);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 128))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 136), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140045880  mov     [rsp+arg_8], rbx
0x140045885  push    rdi
0x140045886  sub     rsp, 20h
0x14004588a  mov     rax, [rcx+88h]
0x140045891  mov     rbx, rcx
0x140045894  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004589a  mov     [rsp+28h+Reply], 0
0x1400458a2  mov     rdi, [rax+20h]
0x1400458a6  mov     rdx, rdi; lpTlsValue
0x1400458a9  call    cs:__imp_TlsSetValue
0x1400458af  test    eax, eax
0x1400458b1  jz      short loc_1400458F9
0x1400458b3  mov     rcx, rdi; BindingHandle
0x1400458b6  call    cs:__imp_RpcImpersonateClient
0x1400458bc  mov     [rsp+28h+Reply], eax
0x1400458c0  test    eax, eax
0x1400458c2  jnz     short loc_1400458E9
0x1400458c4  mov     r8d, [rbx+78h]
0x1400458c8  mov     rdx, [rbx+70h]
0x1400458cc  mov     rcx, [rbx+68h]
0x1400458d0  mov     rax, [rbx+80h]
0x1400458d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400458dc  mov     rcx, rdi; BindingHandle
0x1400458df  mov     [rsp+28h+Reply], eax
0x1400458e3  call    cs:__imp_RpcRevertToSelfEx
0x1400458e9  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400458ef  xor     edx, edx; lpTlsValue
0x1400458f1  call    cs:__imp_TlsSetValue
0x1400458f7  jmp     short loc_140045903
0x1400458f9  call    cs:__imp_GetLastError
0x1400458ff  mov     [rsp+28h+Reply], eax
0x140045903  mov     rcx, [rbx+88h]; pAsync
0x14004590a  lea     rdx, [rsp+28h+Reply]; Reply
0x14004590f  call    cs:__imp_RpcAsyncCompleteCall
0x140045915  mov     eax, [rsp+28h+Reply]
0x140045919  test    eax, eax
0x14004591b  jle     short loc_140045925
0x14004591d  movzx   eax, ax
0x140045920  or      eax, 80070000h
0x140045925  mov     rbx, [rsp+28h+arg_8]
0x14004592a  add     rsp, 20h
0x14004592e  pop     rdi
0x14004592f  retn
```
