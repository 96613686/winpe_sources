# TFunction4HR<ushort const *,ushort const *,ushort const *,Call_Route>::Run(void)

- ea: `0x140045b80`
- end: `0x140045c36`
- name: `?Run@?$TFunction4HR@PEBGPEBGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140045b80`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ba9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045c04`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ba9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045c04`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045be6`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045be6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045c21`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045c21`
- `RPCRT4!RpcImpersonateClient` at `0x140045bb6`
- `RPCRT4!RpcImpersonateClient` at `0x140045bb6`

## pseudocode

```c
__int64 __fastcall TFunction4HR<unsigned short const *,unsigned short const *,unsigned short const *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 144);
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 136))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 144), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x140045b80  mov     [rsp+arg_8], rbx
0x140045b85  push    rdi
0x140045b86  sub     rsp, 30h
0x140045b8a  mov     rax, [rcx+90h]
0x140045b91  mov     rbx, rcx
0x140045b94  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045b9a  mov     [rsp+38h+Reply], 0
0x140045ba2  mov     rdi, [rax+20h]
0x140045ba6  mov     rdx, rdi; lpTlsValue
0x140045ba9  call    cs:__imp_TlsSetValue
0x140045baf  test    eax, eax
0x140045bb1  jz      short loc_140045C0C
0x140045bb3  mov     rcx, rdi; BindingHandle
0x140045bb6  call    cs:__imp_RpcImpersonateClient
0x140045bbc  test    eax, eax
0x140045bbe  jnz     short loc_140045BEE
0x140045bc0  mov     r9d, [rbx+80h]
0x140045bc7  mov     r8, [rbx+78h]
0x140045bcb  mov     rdx, [rbx+70h]
0x140045bcf  mov     rcx, [rbx+68h]
0x140045bd3  mov     rax, [rbx+88h]
0x140045bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bdf  mov     rcx, rdi; BindingHandle
0x140045be2  mov     [rsp+38h+Reply], eax
0x140045be6  call    cs:__imp_RpcRevertToSelfEx
0x140045bec  jmp     short loc_140045BFC
0x140045bee  jle     short loc_140045BF8
0x140045bf0  movzx   eax, ax
0x140045bf3  or      eax, 80070000h
0x140045bf8  mov     [rsp+38h+Reply], eax
0x140045bfc  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045c02  xor     edx, edx; lpTlsValue
0x140045c04  call    cs:__imp_TlsSetValue
0x140045c0a  jmp     short loc_140045C15
0x140045c0c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140045c11  mov     [rsp+38h+Reply], eax
0x140045c15  mov     rcx, [rbx+90h]; pAsync
0x140045c1c  lea     rdx, [rsp+38h+Reply]; Reply
0x140045c21  call    cs:__imp_RpcAsyncCompleteCall
0x140045c27  mov     eax, [rsp+38h+Reply]
0x140045c2b  mov     rbx, [rsp+38h+arg_8]
0x140045c30  add     rsp, 30h
0x140045c34  pop     rdi
0x140045c35  retn
```
