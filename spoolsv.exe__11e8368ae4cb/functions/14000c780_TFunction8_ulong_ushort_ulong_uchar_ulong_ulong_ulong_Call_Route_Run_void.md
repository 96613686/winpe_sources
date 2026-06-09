# TFunction8<ulong,ushort *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14000c780`
- end: `0x14000c86b`
- name: `?Run@?$TFunction8@KPEAGKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000c780`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c7a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c853`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c7a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000c853`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000c845`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000c845`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000c7c9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000c7c9`
- `RPCRT4!RpcImpersonateClient` at `0x14000c7e9`
- `RPCRT4!RpcImpersonateClient` at `0x14000c7e9`

## pseudocode

```c
__int64 __fastcall TFunction8<unsigned long,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 160))(
                *(unsigned int *)(a1 + 100),
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_DWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 152));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 168), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000c780  mov     [rsp+arg_8], rbx
0x14000c785  push    rdi
0x14000c786  sub     rsp, 50h
0x14000c78a  mov     rax, [rcx+0A8h]
0x14000c791  mov     rbx, rcx
0x14000c794  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000c79a  mov     [rsp+58h+Reply], 0
0x14000c7a2  mov     rdi, [rax+20h]
0x14000c7a6  mov     rdx, rdi; lpTlsValue
0x14000c7a9  call    cs:__imp_TlsSetValue
0x14000c7af  test    eax, eax
0x14000c7b1  jnz     short loc_14000C7E6
0x14000c7b3  call    cs:__imp_GetLastError
0x14000c7b9  mov     [rsp+58h+Reply], eax
0x14000c7bd  mov     rcx, [rbx+0A8h]; pAsync
0x14000c7c4  lea     rdx, [rsp+58h+Reply]; Reply
0x14000c7c9  call    cs:__imp_RpcAsyncCompleteCall
0x14000c7cf  mov     eax, [rsp+58h+Reply]
0x14000c7d3  test    eax, eax
0x14000c7d5  jg      loc_14000C85E
0x14000c7db  mov     rbx, [rsp+58h+arg_8]
0x14000c7e0  add     rsp, 50h
0x14000c7e4  pop     rdi
0x14000c7e5  retn
0x14000c7e6  mov     rcx, rdi; BindingHandle
0x14000c7e9  call    cs:__imp_RpcImpersonateClient
0x14000c7ef  mov     [rsp+58h+Reply], eax
0x14000c7f3  test    eax, eax
0x14000c7f5  jnz     short loc_14000C84B
0x14000c7f7  mov     edx, [rbx+98h]
0x14000c7fd  mov     r9, [rbx+78h]
0x14000c801  mov     r8d, [rbx+70h]
0x14000c805  mov     ecx, [rbx+64h]
0x14000c808  mov     rax, [rbx+0A0h]
0x14000c80f  mov     [rsp+58h+var_20], edx
0x14000c813  mov     rdx, [rbx+90h]
0x14000c81a  mov     [rsp+58h+var_28], rdx
0x14000c81f  mov     rdx, [rbx+88h]
0x14000c826  mov     [rsp+58h+var_30], rdx
0x14000c82b  mov     edx, [rbx+80h]
0x14000c831  mov     [rsp+58h+var_38], edx
0x14000c835  mov     rdx, [rbx+68h]
0x14000c839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c83e  mov     rcx, rdi; BindingHandle
0x14000c841  mov     [rsp+58h+Reply], eax
0x14000c845  call    cs:__imp_RpcRevertToSelfEx
0x14000c84b  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000c851  xor     edx, edx; lpTlsValue
0x14000c853  call    cs:__imp_TlsSetValue
0x14000c859  jmp     loc_14000C7BD
0x14000c85e  movzx   eax, ax
0x14000c861  or      eax, 80070000h
0x14000c866  jmp     loc_14000C7DB
```
