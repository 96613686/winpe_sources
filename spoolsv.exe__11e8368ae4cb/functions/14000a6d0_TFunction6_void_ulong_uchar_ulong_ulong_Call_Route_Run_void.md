# TFunction6<void *,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14000a6d0`
- end: `0x14000a7a1`
- name: `?Run@?$TFunction6@PEAXKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a6d0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a703`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000a6f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000a796`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000a6f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000a796`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000a788`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000a788`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000a719`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000a719`
- `RPCRT4!RpcImpersonateClient` at `0x14000a73f`
- `RPCRT4!RpcImpersonateClient` at `0x14000a73f`

## pseudocode

```c
__int64 __fastcall TFunction6<void *,unsigned long,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 160);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 160), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000a6d0  mov     [rsp+arg_8], rbx
0x14000a6d5  push    rdi
0x14000a6d6  sub     rsp, 40h
0x14000a6da  mov     rax, [rcx+0A0h]
0x14000a6e1  mov     rbx, rcx
0x14000a6e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000a6ea  mov     [rsp+48h+Reply], 0
0x14000a6f2  mov     rdi, [rax+20h]
0x14000a6f6  mov     rdx, rdi; lpTlsValue
0x14000a6f9  call    cs:__imp_TlsSetValue
0x14000a6ff  test    eax, eax
0x14000a701  jnz     short loc_14000A73C
0x14000a703  call    cs:__imp_GetLastError
0x14000a709  mov     [rsp+48h+Reply], eax
0x14000a70d  mov     rcx, [rbx+0A0h]; pAsync
0x14000a714  lea     rdx, [rsp+48h+Reply]; Reply
0x14000a719  call    cs:__imp_RpcAsyncCompleteCall
0x14000a71f  mov     eax, [rsp+48h+Reply]
0x14000a723  test    eax, eax
0x14000a725  jg      short loc_14000A732
0x14000a727  mov     rbx, [rsp+48h+arg_8]
0x14000a72c  add     rsp, 40h
0x14000a730  pop     rdi
0x14000a731  retn
0x14000a732  movzx   eax, ax
0x14000a735  or      eax, 80070000h
0x14000a73a  jmp     short loc_14000A727
0x14000a73c  mov     rcx, rdi; BindingHandle
0x14000a73f  call    cs:__imp_RpcImpersonateClient
0x14000a745  mov     [rsp+48h+Reply], eax
0x14000a749  test    eax, eax
0x14000a74b  jnz     short loc_14000A78E
0x14000a74d  mov     edx, [rbx+90h]
0x14000a753  mov     r9d, [rbx+80h]
0x14000a75a  mov     r8, [rbx+78h]
0x14000a75e  mov     rcx, [rbx+68h]
0x14000a762  mov     rax, [rbx+98h]
0x14000a769  mov     [rsp+48h+var_20], edx
0x14000a76d  mov     rdx, [rbx+88h]
0x14000a774  mov     [rsp+48h+var_28], rdx
0x14000a779  mov     edx, [rbx+70h]
0x14000a77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a781  mov     rcx, rdi; BindingHandle
0x14000a784  mov     [rsp+48h+Reply], eax
0x14000a788  call    cs:__imp_RpcRevertToSelfEx
0x14000a78e  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000a794  xor     edx, edx; lpTlsValue
0x14000a796  call    cs:__imp_TlsSetValue
0x14000a79c  jmp     loc_14000A70D
```
