# TFunction4<ushort *,_DRIVER_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x1400499a0`
- end: `0x140049a79`
- name: `?Run@?$TFunction4@PEAGPEAU_DRIVER_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400499a0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049a35`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400499c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049a27`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400499c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049a27`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049a13`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049a13`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049a51`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049a51`
- `RPCRT4!RpcImpersonateClient` at `0x1400499dc`
- `RPCRT4!RpcImpersonateClient` at `0x1400499dc`

## pseudocode

```c
__int64 __fastcall TFunction4<unsigned short *,_DRIVER_CONTAINER *,unsigned long,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 136);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 128))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(unsigned int *)(a1 + 124));
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
0x1400499a0  mov     [rsp+arg_8], rbx
0x1400499a5  push    rdi
0x1400499a6  sub     rsp, 30h
0x1400499aa  mov     rax, [rcx+88h]
0x1400499b1  mov     rbx, rcx
0x1400499b4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400499ba  mov     [rsp+38h+Reply], 0
0x1400499c2  mov     rdi, [rax+20h]
0x1400499c6  mov     rdx, rdi; lpTlsValue
0x1400499c9  call    cs:__imp_TlsSetValue
0x1400499d0  nop     dword ptr [rax+rax+00h]
0x1400499d5  test    eax, eax
0x1400499d7  jz      short loc_140049A35
0x1400499d9  mov     rcx, rdi; BindingHandle
0x1400499dc  call    cs:__imp_RpcImpersonateClient
0x1400499e3  nop     dword ptr [rax+rax+00h]
0x1400499e8  mov     [rsp+38h+Reply], eax
0x1400499ec  test    eax, eax
0x1400499ee  jnz     short loc_140049A1F
0x1400499f0  mov     r9d, [rbx+7Ch]
0x1400499f4  mov     r8d, [rbx+78h]
0x1400499f8  mov     rdx, [rbx+70h]
0x1400499fc  mov     rcx, [rbx+68h]
0x140049a00  mov     rax, [rbx+80h]
0x140049a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049a0c  mov     rcx, rdi; BindingHandle
0x140049a0f  mov     [rsp+38h+Reply], eax
0x140049a13  call    cs:__imp_RpcRevertToSelfEx
0x140049a1a  nop     dword ptr [rax+rax+00h]
0x140049a1f  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049a25  xor     edx, edx; lpTlsValue
0x140049a27  call    cs:__imp_TlsSetValue
0x140049a2e  nop     dword ptr [rax+rax+00h]
0x140049a33  jmp     short loc_140049A45
0x140049a35  call    cs:__imp_GetLastError
0x140049a3c  nop     dword ptr [rax+rax+00h]
0x140049a41  mov     [rsp+38h+Reply], eax
0x140049a45  mov     rcx, [rbx+88h]; pAsync
0x140049a4c  lea     rdx, [rsp+38h+Reply]; Reply
0x140049a51  call    cs:__imp_RpcAsyncCompleteCall
0x140049a58  nop     dword ptr [rax+rax+00h]
0x140049a5d  mov     eax, [rsp+38h+Reply]
0x140049a61  test    eax, eax
0x140049a63  jle     short loc_140049A6D
0x140049a65  movzx   eax, ax
0x140049a68  or      eax, 80070000h
0x140049a6d  mov     rbx, [rsp+38h+arg_8]
0x140049a72  add     rsp, 30h
0x140049a76  pop     rdi
0x140049a77  retn
```
