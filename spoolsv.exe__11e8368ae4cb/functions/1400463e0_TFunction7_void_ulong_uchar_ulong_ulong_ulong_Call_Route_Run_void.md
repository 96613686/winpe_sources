# TFunction7<void *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x1400463e0`
- end: `0x1400464b8`
- name: `?Run@?$TFunction7@PEAXKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400463e0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046481`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046409`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046479`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046409`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046479`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004646b`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004646b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046497`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046497`
- `RPCRT4!RpcImpersonateClient` at `0x140046416`
- `RPCRT4!RpcImpersonateClient` at `0x140046416`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
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
0x1400463e0  mov     [rsp+arg_8], rbx
0x1400463e5  push    rdi
0x1400463e6  sub     rsp, 40h
0x1400463ea  mov     rax, [rcx+0A8h]
0x1400463f1  mov     rbx, rcx
0x1400463f4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400463fa  mov     [rsp+48h+Reply], 0
0x140046402  mov     rdi, [rax+20h]
0x140046406  mov     rdx, rdi; lpTlsValue
0x140046409  call    cs:__imp_TlsSetValue
0x14004640f  test    eax, eax
0x140046411  jz      short loc_140046481
0x140046413  mov     rcx, rdi; BindingHandle
0x140046416  call    cs:__imp_RpcImpersonateClient
0x14004641c  mov     [rsp+48h+Reply], eax
0x140046420  test    eax, eax
0x140046422  jnz     short loc_140046471
0x140046424  mov     edx, [rbx+98h]
0x14004642a  mov     r9d, [rbx+80h]
0x140046431  mov     r8, [rbx+78h]
0x140046435  mov     rcx, [rbx+68h]
0x140046439  mov     rax, [rbx+0A0h]
0x140046440  mov     [rsp+48h+var_18], edx
0x140046444  mov     rdx, [rbx+90h]
0x14004644b  mov     [rsp+48h+var_20], rdx
0x140046450  mov     rdx, [rbx+88h]
0x140046457  mov     [rsp+48h+var_28], rdx
0x14004645c  mov     edx, [rbx+70h]
0x14004645f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046464  mov     rcx, rdi; BindingHandle
0x140046467  mov     [rsp+48h+Reply], eax
0x14004646b  call    cs:__imp_RpcRevertToSelfEx
0x140046471  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046477  xor     edx, edx; lpTlsValue
0x140046479  call    cs:__imp_TlsSetValue
0x14004647f  jmp     short loc_14004648B
0x140046481  call    cs:__imp_GetLastError
0x140046487  mov     [rsp+48h+Reply], eax
0x14004648b  mov     rcx, [rbx+0A8h]; pAsync
0x140046492  lea     rdx, [rsp+48h+Reply]; Reply
0x140046497  call    cs:__imp_RpcAsyncCompleteCall
0x14004649d  mov     eax, [rsp+48h+Reply]
0x1400464a1  test    eax, eax
0x1400464a3  jle     short loc_1400464AD
0x1400464a5  movzx   eax, ax
0x1400464a8  or      eax, 80070000h
0x1400464ad  mov     rbx, [rsp+48h+arg_8]
0x1400464b2  add     rsp, 40h
0x1400464b6  pop     rdi
0x1400464b7  retn
```
