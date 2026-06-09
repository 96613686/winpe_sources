# TFunction7<void *,ushort const *,ushort const *,ulong,uchar *,ulong,Call_Route>::Run(void)

- ea: `0x140046ae0`
- end: `0x140046bb7`
- name: `?Run@?$TFunction7@PEAXPEBGPEBGKPEAEKW4Call_Route@@@@UEAAJXZ`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046ae0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b80`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046b09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046b78`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046b09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046b78`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046b6a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046b6a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046b96`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046b96`
- `RPCRT4!RpcImpersonateClient` at `0x140046b16`
- `RPCRT4!RpcImpersonateClient` at `0x140046b16`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned short const *,unsigned short const *,unsigned long,unsigned char *,unsigned long,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 148));
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
0x140046ae0  mov     [rsp+arg_8], rbx
0x140046ae5  push    rdi
0x140046ae6  sub     rsp, 40h
0x140046aea  mov     rax, [rcx+0A0h]
0x140046af1  mov     rbx, rcx
0x140046af4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046afa  mov     [rsp+48h+Reply], 0
0x140046b02  mov     rdi, [rax+20h]
0x140046b06  mov     rdx, rdi; lpTlsValue
0x140046b09  call    cs:__imp_TlsSetValue
0x140046b0f  test    eax, eax
0x140046b11  jz      short loc_140046B80
0x140046b13  mov     rcx, rdi; BindingHandle
0x140046b16  call    cs:__imp_RpcImpersonateClient
0x140046b1c  mov     [rsp+48h+Reply], eax
0x140046b20  test    eax, eax
0x140046b22  jnz     short loc_140046B70
0x140046b24  mov     edx, [rbx+94h]
0x140046b2a  mov     r9d, [rbx+80h]
0x140046b31  mov     r8, [rbx+78h]
0x140046b35  mov     rcx, [rbx+68h]
0x140046b39  mov     rax, [rbx+98h]
0x140046b40  mov     [rsp+48h+var_18], edx
0x140046b44  mov     edx, [rbx+90h]
0x140046b4a  mov     [rsp+48h+var_20], edx
0x140046b4e  mov     rdx, [rbx+88h]
0x140046b55  mov     [rsp+48h+var_28], rdx
0x140046b5a  mov     rdx, [rbx+70h]
0x140046b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046b63  mov     rcx, rdi; BindingHandle
0x140046b66  mov     [rsp+48h+Reply], eax
0x140046b6a  call    cs:__imp_RpcRevertToSelfEx
0x140046b70  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046b76  xor     edx, edx; lpTlsValue
0x140046b78  call    cs:__imp_TlsSetValue
0x140046b7e  jmp     short loc_140046B8A
0x140046b80  call    cs:__imp_GetLastError
0x140046b86  mov     [rsp+48h+Reply], eax
0x140046b8a  mov     rcx, [rbx+0A0h]; pAsync
0x140046b91  lea     rdx, [rsp+48h+Reply]; Reply
0x140046b96  call    cs:__imp_RpcAsyncCompleteCall
0x140046b9c  mov     eax, [rsp+48h+Reply]
0x140046ba0  test    eax, eax
0x140046ba2  jle     short loc_140046BAC
0x140046ba4  movzx   eax, ax
0x140046ba7  or      eax, 80070000h
0x140046bac  mov     rbx, [rsp+48h+arg_8]
0x140046bb1  add     rsp, 40h
0x140046bb5  pop     rdi
0x140046bb6  retn
```
