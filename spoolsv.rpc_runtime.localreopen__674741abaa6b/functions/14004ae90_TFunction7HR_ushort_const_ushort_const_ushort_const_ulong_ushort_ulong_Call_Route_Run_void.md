# TFunction7HR<ushort const *,ushort const *,ushort const *,ulong,ushort *,ulong *,Call_Route>::Run(void)

- ea: `0x14004ae90`
- end: `0x14004af8b`
- name: `?Run@?$TFunction7HR@PEBGPEBGPEBGKPEAGPEAKW4Call_Route@@@@UEAAJXZ`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x14004ae90`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aeb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004af4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aeb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004af4c`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004af28`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004af28`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004af6f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004af6f`
- `RPCRT4!RpcImpersonateClient` at `0x14004aed0`
- `RPCRT4!RpcImpersonateClient` at `0x14004aed0`

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
0x14004ae90  mov     [rsp+arg_8], rbx
0x14004ae95  push    rdi
0x14004ae96  sub     rsp, 40h
0x14004ae9a  mov     rax, [rcx+0A8h]
0x14004aea1  mov     rbx, rcx
0x14004aea4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004aeaa  mov     [rsp+48h+Reply], 0
0x14004aeb2  mov     rdi, [rax+20h]
0x14004aeb6  mov     rdx, rdi; lpTlsValue
0x14004aeb9  call    cs:__imp_TlsSetValue
0x14004aec0  nop     dword ptr [rax+rax+00h]
0x14004aec5  test    eax, eax
0x14004aec7  jz      loc_14004AF5A
0x14004aecd  mov     rcx, rdi; BindingHandle
0x14004aed0  call    cs:__imp_RpcImpersonateClient
0x14004aed7  nop     dword ptr [rax+rax+00h]
0x14004aedc  test    eax, eax
0x14004aede  jnz     short loc_14004AF36
0x14004aee0  mov     edx, [rbx+98h]
0x14004aee6  mov     r9d, [rbx+80h]
0x14004aeed  mov     r8, [rbx+78h]
0x14004aef1  mov     rcx, [rbx+68h]
0x14004aef5  mov     rax, [rbx+0A0h]
0x14004aefc  mov     [rsp+48h+var_18], edx
0x14004af00  mov     rdx, [rbx+90h]
0x14004af07  mov     [rsp+48h+var_20], rdx
0x14004af0c  mov     rdx, [rbx+88h]
0x14004af13  mov     [rsp+48h+var_28], rdx
0x14004af18  mov     rdx, [rbx+70h]
0x14004af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004af21  mov     rcx, rdi; BindingHandle
0x14004af24  mov     [rsp+48h+Reply], eax
0x14004af28  call    cs:__imp_RpcRevertToSelfEx
0x14004af2f  nop     dword ptr [rax+rax+00h]
0x14004af34  jmp     short loc_14004AF44
0x14004af36  jle     short loc_14004AF40
0x14004af38  movzx   eax, ax
0x14004af3b  or      eax, 80070000h
0x14004af40  mov     [rsp+48h+Reply], eax
0x14004af44  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004af4a  xor     edx, edx; lpTlsValue
0x14004af4c  call    cs:__imp_TlsSetValue
0x14004af53  nop     dword ptr [rax+rax+00h]
0x14004af58  jmp     short loc_14004AF63
0x14004af5a  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14004af5f  mov     [rsp+48h+Reply], eax
0x14004af63  mov     rcx, [rbx+0A8h]; pAsync
0x14004af6a  lea     rdx, [rsp+48h+Reply]; Reply
0x14004af6f  call    cs:__imp_RpcAsyncCompleteCall
0x14004af76  nop     dword ptr [rax+rax+00h]
0x14004af7b  mov     eax, [rsp+48h+Reply]
0x14004af7f  mov     rbx, [rsp+48h+arg_8]
0x14004af84  add     rsp, 40h
0x14004af88  pop     rdi
0x14004af89  retn
```
