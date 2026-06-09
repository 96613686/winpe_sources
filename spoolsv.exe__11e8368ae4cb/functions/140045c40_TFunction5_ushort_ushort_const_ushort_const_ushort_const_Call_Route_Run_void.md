# TFunction5<ushort *,ushort const *,ushort const *,ushort const *,Call_Route>::Run(void)

- ea: `0x140045c40`
- end: `0x140045d01`
- name: `?Run@?$TFunction5@PEAGPEBGPEBGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045c40`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045cca`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045c69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045cc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045c69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045cc2`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045cb4`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045cb4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045ce0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045ce0`
- `RPCRT4!RpcImpersonateClient` at `0x140045c76`
- `RPCRT4!RpcImpersonateClient` at `0x140045c76`

## pseudocode

```c
__int64 __fastcall TFunction5<unsigned short *,unsigned short const *,unsigned short const *,unsigned short const *,enum Call_Route>::Run(
        __int64 a1)
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
                *(_QWORD *)(a1 + 120),
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
0x140045c40  mov     [rsp+arg_8], rbx
0x140045c45  push    rdi
0x140045c46  sub     rsp, 30h
0x140045c4a  mov     rax, [rcx+98h]
0x140045c51  mov     rbx, rcx
0x140045c54  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045c5a  mov     [rsp+38h+Reply], 0
0x140045c62  mov     rdi, [rax+20h]
0x140045c66  mov     rdx, rdi; lpTlsValue
0x140045c69  call    cs:__imp_TlsSetValue
0x140045c6f  test    eax, eax
0x140045c71  jz      short loc_140045CCA
0x140045c73  mov     rcx, rdi; BindingHandle
0x140045c76  call    cs:__imp_RpcImpersonateClient
0x140045c7c  mov     [rsp+38h+Reply], eax
0x140045c80  test    eax, eax
0x140045c82  jnz     short loc_140045CBA
0x140045c84  mov     edx, [rbx+88h]
0x140045c8a  mov     r9, [rbx+80h]
0x140045c91  mov     r8, [rbx+78h]
0x140045c95  mov     rcx, [rbx+68h]
0x140045c99  mov     rax, [rbx+90h]
0x140045ca0  mov     [rsp+38h+var_18], edx
0x140045ca4  mov     rdx, [rbx+70h]
0x140045ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cad  mov     rcx, rdi; BindingHandle
0x140045cb0  mov     [rsp+38h+Reply], eax
0x140045cb4  call    cs:__imp_RpcRevertToSelfEx
0x140045cba  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045cc0  xor     edx, edx; lpTlsValue
0x140045cc2  call    cs:__imp_TlsSetValue
0x140045cc8  jmp     short loc_140045CD4
0x140045cca  call    cs:__imp_GetLastError
0x140045cd0  mov     [rsp+38h+Reply], eax
0x140045cd4  mov     rcx, [rbx+98h]; pAsync
0x140045cdb  lea     rdx, [rsp+38h+Reply]; Reply
0x140045ce0  call    cs:__imp_RpcAsyncCompleteCall
0x140045ce6  mov     eax, [rsp+38h+Reply]
0x140045cea  test    eax, eax
0x140045cec  jle     short loc_140045CF6
0x140045cee  movzx   eax, ax
0x140045cf1  or      eax, 80070000h
0x140045cf6  mov     rbx, [rsp+38h+arg_8]
0x140045cfb  add     rsp, 30h
0x140045cff  pop     rdi
0x140045d00  retn
```
