# TFunction6<ushort *,ushort *,ushort *,ulong,ulong,Call_Route>::Run(void)

- ea: `0x140049f30`
- end: `0x14004a020`
- name: `?Run@?$TFunction6@PEAGPEAGPEAGKKW4Call_Route@@@@UEAAJXZ`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049f30`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049fdc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049f59`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049fce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049f59`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049fce`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049fba`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049fba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049ff8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049ff8`
- `RPCRT4!RpcImpersonateClient` at `0x140049f6c`
- `RPCRT4!RpcImpersonateClient` at `0x140049f6c`

## pseudocode

```c
__int64 __fastcall TFunction6<unsigned short *,unsigned short *,unsigned short *,unsigned long,unsigned long,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 144))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_DWORD *)(a1 + 132),
                *(_DWORD *)(a1 + 136));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 152), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140049f30  mov     [rsp+arg_8], rbx
0x140049f35  push    rdi
0x140049f36  sub     rsp, 40h
0x140049f3a  mov     rax, [rcx+98h]
0x140049f41  mov     rbx, rcx
0x140049f44  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049f4a  mov     [rsp+48h+Reply], 0
0x140049f52  mov     rdi, [rax+20h]
0x140049f56  mov     rdx, rdi; lpTlsValue
0x140049f59  call    cs:__imp_TlsSetValue
0x140049f60  nop     dword ptr [rax+rax+00h]
0x140049f65  test    eax, eax
0x140049f67  jz      short loc_140049FDC
0x140049f69  mov     rcx, rdi; BindingHandle
0x140049f6c  call    cs:__imp_RpcImpersonateClient
0x140049f73  nop     dword ptr [rax+rax+00h]
0x140049f78  mov     [rsp+48h+Reply], eax
0x140049f7c  test    eax, eax
0x140049f7e  jnz     short loc_140049FC6
0x140049f80  mov     edx, [rbx+88h]
0x140049f86  mov     r9d, [rbx+80h]
0x140049f8d  mov     r8, [rbx+78h]
0x140049f91  mov     rcx, [rbx+68h]
0x140049f95  mov     rax, [rbx+90h]
0x140049f9c  mov     [rsp+48h+var_20], edx
0x140049fa0  mov     edx, [rbx+84h]
0x140049fa6  mov     [rsp+48h+var_28], edx
0x140049faa  mov     rdx, [rbx+70h]
0x140049fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049fb3  mov     rcx, rdi; BindingHandle
0x140049fb6  mov     [rsp+48h+Reply], eax
0x140049fba  call    cs:__imp_RpcRevertToSelfEx
0x140049fc1  nop     dword ptr [rax+rax+00h]
0x140049fc6  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049fcc  xor     edx, edx; lpTlsValue
0x140049fce  call    cs:__imp_TlsSetValue
0x140049fd5  nop     dword ptr [rax+rax+00h]
0x140049fda  jmp     short loc_140049FEC
0x140049fdc  call    cs:__imp_GetLastError
0x140049fe3  nop     dword ptr [rax+rax+00h]
0x140049fe8  mov     [rsp+48h+Reply], eax
0x140049fec  mov     rcx, [rbx+98h]; pAsync
0x140049ff3  lea     rdx, [rsp+48h+Reply]; Reply
0x140049ff8  call    cs:__imp_RpcAsyncCompleteCall
0x140049fff  nop     dword ptr [rax+rax+00h]
0x14004a004  mov     eax, [rsp+48h+Reply]
0x14004a008  test    eax, eax
0x14004a00a  jle     short loc_14004A014
0x14004a00c  movzx   eax, ax
0x14004a00f  or      eax, 80070000h
0x14004a014  mov     rbx, [rsp+48h+arg_8]
0x14004a019  add     rsp, 40h
0x14004a01d  pop     rdi
0x14004a01e  retn
```
