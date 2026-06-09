# TFunction7HR<ushort const *,ushort const *,ushort const *,ulong,ushort *,ulong *,Call_Route>::Run(void)

- ea: `0x140046ca0`
- end: `0x140046d78`
- name: `?Run@?$TFunction7HR@PEBGPEBGPEBGKPEAGPEAKW4Call_Route@@@@UEAAJXZ`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140046ca0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046d46`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046d46`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046d28`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046d28`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046d63`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046d63`
- `RPCRT4!RpcImpersonateClient` at `0x140046cd6`
- `RPCRT4!RpcImpersonateClient` at `0x140046cd6`

## pseudocode

```c
__int64 __fastcall TFunction7HR<unsigned short const *,unsigned short const *,unsigned short const *,unsigned long,unsigned short *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    v5 = RpcImpersonateClient(v3);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      Reply = v5;
    }
    else
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
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
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 168), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x140046ca0  mov     [rsp+arg_8], rbx
0x140046ca5  push    rdi
0x140046ca6  sub     rsp, 40h
0x140046caa  mov     rax, [rcx+0A8h]
0x140046cb1  mov     rbx, rcx
0x140046cb4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046cba  mov     [rsp+48h+Reply], 0
0x140046cc2  mov     rdi, [rax+20h]
0x140046cc6  mov     rdx, rdi; lpTlsValue
0x140046cc9  call    cs:__imp_TlsSetValue
0x140046ccf  test    eax, eax
0x140046cd1  jz      short loc_140046D4E
0x140046cd3  mov     rcx, rdi; BindingHandle
0x140046cd6  call    cs:__imp_RpcImpersonateClient
0x140046cdc  test    eax, eax
0x140046cde  jnz     short loc_140046D30
0x140046ce0  mov     edx, [rbx+98h]
0x140046ce6  mov     r9d, [rbx+80h]
0x140046ced  mov     r8, [rbx+78h]
0x140046cf1  mov     rcx, [rbx+68h]
0x140046cf5  mov     rax, [rbx+0A0h]
0x140046cfc  mov     [rsp+48h+var_18], edx
0x140046d00  mov     rdx, [rbx+90h]
0x140046d07  mov     [rsp+48h+var_20], rdx
0x140046d0c  mov     rdx, [rbx+88h]
0x140046d13  mov     [rsp+48h+var_28], rdx
0x140046d18  mov     rdx, [rbx+70h]
0x140046d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046d21  mov     rcx, rdi; BindingHandle
0x140046d24  mov     [rsp+48h+Reply], eax
0x140046d28  call    cs:__imp_RpcRevertToSelfEx
0x140046d2e  jmp     short loc_140046D3E
0x140046d30  jle     short loc_140046D3A
0x140046d32  movzx   eax, ax
0x140046d35  or      eax, 80070000h
0x140046d3a  mov     [rsp+48h+Reply], eax
0x140046d3e  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046d44  xor     edx, edx; lpTlsValue
0x140046d46  call    cs:__imp_TlsSetValue
0x140046d4c  jmp     short loc_140046D57
0x140046d4e  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140046d53  mov     [rsp+48h+Reply], eax
0x140046d57  mov     rcx, [rbx+0A8h]; pAsync
0x140046d5e  lea     rdx, [rsp+48h+Reply]; Reply
0x140046d63  call    cs:__imp_RpcAsyncCompleteCall
0x140046d69  mov     eax, [rsp+48h+Reply]
0x140046d6d  mov     rbx, [rsp+48h+arg_8]
0x140046d72  add     rsp, 40h
0x140046d76  pop     rdi
0x140046d77  retn
```
