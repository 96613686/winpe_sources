# TFunction4HR<ushort const *,ushort const *,ushort const *,Call_Route>::Run(void)

- ea: `0x140049a80`
- end: `0x140049b55`
- name: `?Run@?$TFunction4HR@PEBGPEBGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x140049a80`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049aa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b16`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049aa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b16`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049af2`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049af2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049b39`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049b39`
- `RPCRT4!RpcImpersonateClient` at `0x140049abc`
- `RPCRT4!RpcImpersonateClient` at `0x140049abc`

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
0x140049a80  mov     [rsp+arg_8], rbx
0x140049a85  push    rdi
0x140049a86  sub     rsp, 30h
0x140049a8a  mov     rax, [rcx+90h]
0x140049a91  mov     rbx, rcx
0x140049a94  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049a9a  mov     [rsp+38h+Reply], 0
0x140049aa2  mov     rdi, [rax+20h]
0x140049aa6  mov     rdx, rdi; lpTlsValue
0x140049aa9  call    cs:__imp_TlsSetValue
0x140049ab0  nop     dword ptr [rax+rax+00h]
0x140049ab5  test    eax, eax
0x140049ab7  jz      short loc_140049B24
0x140049ab9  mov     rcx, rdi; BindingHandle
0x140049abc  call    cs:__imp_RpcImpersonateClient
0x140049ac3  nop     dword ptr [rax+rax+00h]
0x140049ac8  test    eax, eax
0x140049aca  jnz     short loc_140049B00
0x140049acc  mov     r9d, [rbx+80h]
0x140049ad3  mov     r8, [rbx+78h]
0x140049ad7  mov     rdx, [rbx+70h]
0x140049adb  mov     rcx, [rbx+68h]
0x140049adf  mov     rax, [rbx+88h]
0x140049ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049aeb  mov     rcx, rdi; BindingHandle
0x140049aee  mov     [rsp+38h+Reply], eax
0x140049af2  call    cs:__imp_RpcRevertToSelfEx
0x140049af9  nop     dword ptr [rax+rax+00h]
0x140049afe  jmp     short loc_140049B0E
0x140049b00  jle     short loc_140049B0A
0x140049b02  movzx   eax, ax
0x140049b05  or      eax, 80070000h
0x140049b0a  mov     [rsp+38h+Reply], eax
0x140049b0e  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049b14  xor     edx, edx; lpTlsValue
0x140049b16  call    cs:__imp_TlsSetValue
0x140049b1d  nop     dword ptr [rax+rax+00h]
0x140049b22  jmp     short loc_140049B2D
0x140049b24  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140049b29  mov     [rsp+38h+Reply], eax
0x140049b2d  mov     rcx, [rbx+90h]; pAsync
0x140049b34  lea     rdx, [rsp+38h+Reply]; Reply
0x140049b39  call    cs:__imp_RpcAsyncCompleteCall
0x140049b40  nop     dword ptr [rax+rax+00h]
0x140049b45  mov     eax, [rsp+38h+Reply]
0x140049b49  mov     rbx, [rsp+38h+arg_8]
0x140049b4e  add     rsp, 30h
0x140049b52  pop     rdi
0x140049b53  retn
```
