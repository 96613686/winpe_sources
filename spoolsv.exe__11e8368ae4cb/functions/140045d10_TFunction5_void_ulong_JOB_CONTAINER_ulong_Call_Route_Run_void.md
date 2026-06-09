# TFunction5<void *,ulong,_JOB_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x140045d10`
- end: `0x140045dd0`
- name: `?Run@?$TFunction5@PEAXKPEAU_JOB_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045d10`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045d99`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045d39`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045d91`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045d39`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045d91`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045d83`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045d83`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045daf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045daf`
- `RPCRT4!RpcImpersonateClient` at `0x140045d46`
- `RPCRT4!RpcImpersonateClient` at `0x140045d46`

## pseudocode

```c
__int64 __fastcall TFunction5<void *,unsigned long,_JOB_CONTAINER *,unsigned long,enum Call_Route>::Run(__int64 a1)
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 136))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_DWORD *)(a1 + 132));
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
0x140045d10  mov     [rsp+arg_8], rbx
0x140045d15  push    rdi
0x140045d16  sub     rsp, 30h
0x140045d1a  mov     rax, [rcx+90h]
0x140045d21  mov     rbx, rcx
0x140045d24  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045d2a  mov     [rsp+38h+Reply], 0
0x140045d32  mov     rdi, [rax+20h]
0x140045d36  mov     rdx, rdi; lpTlsValue
0x140045d39  call    cs:__imp_TlsSetValue
0x140045d3f  test    eax, eax
0x140045d41  jz      short loc_140045D99
0x140045d43  mov     rcx, rdi; BindingHandle
0x140045d46  call    cs:__imp_RpcImpersonateClient
0x140045d4c  mov     [rsp+38h+Reply], eax
0x140045d50  test    eax, eax
0x140045d52  jnz     short loc_140045D89
0x140045d54  mov     edx, [rbx+84h]
0x140045d5a  mov     r9d, [rbx+80h]
0x140045d61  mov     r8, [rbx+78h]
0x140045d65  mov     rcx, [rbx+68h]
0x140045d69  mov     rax, [rbx+88h]
0x140045d70  mov     [rsp+38h+var_18], edx
0x140045d74  mov     edx, [rbx+70h]
0x140045d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d7c  mov     rcx, rdi; BindingHandle
0x140045d7f  mov     [rsp+38h+Reply], eax
0x140045d83  call    cs:__imp_RpcRevertToSelfEx
0x140045d89  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045d8f  xor     edx, edx; lpTlsValue
0x140045d91  call    cs:__imp_TlsSetValue
0x140045d97  jmp     short loc_140045DA3
0x140045d99  call    cs:__imp_GetLastError
0x140045d9f  mov     [rsp+38h+Reply], eax
0x140045da3  mov     rcx, [rbx+90h]; pAsync
0x140045daa  lea     rdx, [rsp+38h+Reply]; Reply
0x140045daf  call    cs:__imp_RpcAsyncCompleteCall
0x140045db5  mov     eax, [rsp+38h+Reply]
0x140045db9  test    eax, eax
0x140045dbb  jle     short loc_140045DC5
0x140045dbd  movzx   eax, ax
0x140045dc0  or      eax, 80070000h
0x140045dc5  mov     rbx, [rsp+38h+arg_8]
0x140045dca  add     rsp, 30h
0x140045dce  pop     rdi
0x140045dcf  retn
```
