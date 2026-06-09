# TFunction3<ushort *,ushort const *,Call_Route>::Run(void)

- ea: `0x1400496f0`
- end: `0x1400497c5`
- name: `?Run@?$TFunction3@PEAGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400496f0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049781`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049719`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049773`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049719`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049773`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004975f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004975f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004979d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004979d`
- `RPCRT4!RpcImpersonateClient` at `0x14004972c`
- `RPCRT4!RpcImpersonateClient` at `0x14004972c`

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
0x1400496f0  mov     [rsp+arg_8], rbx
0x1400496f5  push    rdi
0x1400496f6  sub     rsp, 20h
0x1400496fa  mov     rax, [rcx+88h]
0x140049701  mov     rbx, rcx
0x140049704  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004970a  mov     [rsp+28h+Reply], 0
0x140049712  mov     rdi, [rax+20h]
0x140049716  mov     rdx, rdi; lpTlsValue
0x140049719  call    cs:__imp_TlsSetValue
0x140049720  nop     dword ptr [rax+rax+00h]
0x140049725  test    eax, eax
0x140049727  jz      short loc_140049781
0x140049729  mov     rcx, rdi; BindingHandle
0x14004972c  call    cs:__imp_RpcImpersonateClient
0x140049733  nop     dword ptr [rax+rax+00h]
0x140049738  mov     [rsp+28h+Reply], eax
0x14004973c  test    eax, eax
0x14004973e  jnz     short loc_14004976B
0x140049740  mov     r8d, [rbx+78h]
0x140049744  mov     rdx, [rbx+70h]
0x140049748  mov     rcx, [rbx+68h]
0x14004974c  mov     rax, [rbx+80h]
0x140049753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049758  mov     rcx, rdi; BindingHandle
0x14004975b  mov     [rsp+28h+Reply], eax
0x14004975f  call    cs:__imp_RpcRevertToSelfEx
0x140049766  nop     dword ptr [rax+rax+00h]
0x14004976b  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049771  xor     edx, edx; lpTlsValue
0x140049773  call    cs:__imp_TlsSetValue
0x14004977a  nop     dword ptr [rax+rax+00h]
0x14004977f  jmp     short loc_140049791
0x140049781  call    cs:__imp_GetLastError
0x140049788  nop     dword ptr [rax+rax+00h]
0x14004978d  mov     [rsp+28h+Reply], eax
0x140049791  mov     rcx, [rbx+88h]; pAsync
0x140049798  lea     rdx, [rsp+28h+Reply]; Reply
0x14004979d  call    cs:__imp_RpcAsyncCompleteCall
0x1400497a4  nop     dword ptr [rax+rax+00h]
0x1400497a9  mov     eax, [rsp+28h+Reply]
0x1400497ad  test    eax, eax
0x1400497af  jle     short loc_1400497B9
0x1400497b1  movzx   eax, ax
0x1400497b4  or      eax, 80070000h
0x1400497b9  mov     rbx, [rsp+28h+arg_8]
0x1400497be  add     rsp, 20h
0x1400497c2  pop     rdi
0x1400497c3  retn
```
