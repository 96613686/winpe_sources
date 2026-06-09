# TFunction5<void *,void *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140049d40`
- end: `0x140049e26`
- name: `?Run@?$TFunction5@PEAXPEAXKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049d40`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049de2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049d69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049dd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049d69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049dd4`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049dc0`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049dc0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049dfe`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049dfe`
- `RPCRT4!RpcImpersonateClient` at `0x140049d7c`
- `RPCRT4!RpcImpersonateClient` at `0x140049d7c`

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
0x140049d40  mov     [rsp+arg_8], rbx
0x140049d45  push    rdi
0x140049d46  sub     rsp, 30h
0x140049d4a  mov     rax, [rcx+98h]
0x140049d51  mov     rbx, rcx
0x140049d54  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049d5a  mov     [rsp+38h+Reply], 0
0x140049d62  mov     rdi, [rax+20h]
0x140049d66  mov     rdx, rdi; lpTlsValue
0x140049d69  call    cs:__imp_TlsSetValue
0x140049d70  nop     dword ptr [rax+rax+00h]
0x140049d75  test    eax, eax
0x140049d77  jz      short loc_140049DE2
0x140049d79  mov     rcx, rdi; BindingHandle
0x140049d7c  call    cs:__imp_RpcImpersonateClient
0x140049d83  nop     dword ptr [rax+rax+00h]
0x140049d88  mov     [rsp+38h+Reply], eax
0x140049d8c  test    eax, eax
0x140049d8e  jnz     short loc_140049DCC
0x140049d90  mov     edx, [rbx+88h]
0x140049d96  mov     r9, [rbx+80h]
0x140049d9d  mov     r8d, [rbx+78h]
0x140049da1  mov     rcx, [rbx+68h]
0x140049da5  mov     rax, [rbx+90h]
0x140049dac  mov     [rsp+38h+var_18], edx
0x140049db0  mov     rdx, [rbx+70h]
0x140049db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049db9  mov     rcx, rdi; BindingHandle
0x140049dbc  mov     [rsp+38h+Reply], eax
0x140049dc0  call    cs:__imp_RpcRevertToSelfEx
0x140049dc7  nop     dword ptr [rax+rax+00h]
0x140049dcc  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049dd2  xor     edx, edx; lpTlsValue
0x140049dd4  call    cs:__imp_TlsSetValue
0x140049ddb  nop     dword ptr [rax+rax+00h]
0x140049de0  jmp     short loc_140049DF2
0x140049de2  call    cs:__imp_GetLastError
0x140049de9  nop     dword ptr [rax+rax+00h]
0x140049dee  mov     [rsp+38h+Reply], eax
0x140049df2  mov     rcx, [rbx+98h]; pAsync
0x140049df9  lea     rdx, [rsp+38h+Reply]; Reply
0x140049dfe  call    cs:__imp_RpcAsyncCompleteCall
0x140049e05  nop     dword ptr [rax+rax+00h]
0x140049e0a  mov     eax, [rsp+38h+Reply]
0x140049e0e  test    eax, eax
0x140049e10  jle     short loc_140049E1A
0x140049e12  movzx   eax, ax
0x140049e15  or      eax, 80070000h
0x140049e1a  mov     rbx, [rsp+38h+arg_8]
0x140049e1f  add     rsp, 30h
0x140049e23  pop     rdi
0x140049e24  retn
```
