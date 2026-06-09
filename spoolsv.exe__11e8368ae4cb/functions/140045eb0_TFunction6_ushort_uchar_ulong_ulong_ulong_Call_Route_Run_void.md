# TFunction6<ushort *,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140045eb0`
- end: `0x140045f7d`
- name: `?Run@?$TFunction6@PEAGPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045eb0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045f46`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ed9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045f3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ed9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045f3e`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045f30`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045f30`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045f5c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045f5c`
- `RPCRT4!RpcImpersonateClient` at `0x140045ee6`
- `RPCRT4!RpcImpersonateClient` at `0x140045ee6`

## pseudocode

```c
__int64 __fastcall TFunction6<unsigned short *,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144));
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
0x140045eb0  mov     [rsp+arg_8], rbx
0x140045eb5  push    rdi
0x140045eb6  sub     rsp, 40h
0x140045eba  mov     rax, [rcx+0A0h]
0x140045ec1  mov     rbx, rcx
0x140045ec4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045eca  mov     [rsp+48h+Reply], 0
0x140045ed2  mov     rdi, [rax+20h]
0x140045ed6  mov     rdx, rdi; lpTlsValue
0x140045ed9  call    cs:__imp_TlsSetValue
0x140045edf  test    eax, eax
0x140045ee1  jz      short loc_140045F46
0x140045ee3  mov     rcx, rdi; BindingHandle
0x140045ee6  call    cs:__imp_RpcImpersonateClient
0x140045eec  mov     [rsp+48h+Reply], eax
0x140045ef0  test    eax, eax
0x140045ef2  jnz     short loc_140045F36
0x140045ef4  mov     edx, [rbx+90h]
0x140045efa  mov     r9, [rbx+80h]
0x140045f01  mov     r8d, [rbx+78h]
0x140045f05  mov     rcx, [rbx+68h]
0x140045f09  mov     rax, [rbx+98h]
0x140045f10  mov     [rsp+48h+var_20], edx
0x140045f14  mov     rdx, [rbx+88h]
0x140045f1b  mov     [rsp+48h+var_28], rdx
0x140045f20  mov     rdx, [rbx+70h]
0x140045f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045f29  mov     rcx, rdi; BindingHandle
0x140045f2c  mov     [rsp+48h+Reply], eax
0x140045f30  call    cs:__imp_RpcRevertToSelfEx
0x140045f36  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045f3c  xor     edx, edx; lpTlsValue
0x140045f3e  call    cs:__imp_TlsSetValue
0x140045f44  jmp     short loc_140045F50
0x140045f46  call    cs:__imp_GetLastError
0x140045f4c  mov     [rsp+48h+Reply], eax
0x140045f50  mov     rcx, [rbx+0A0h]; pAsync
0x140045f57  lea     rdx, [rsp+48h+Reply]; Reply
0x140045f5c  call    cs:__imp_RpcAsyncCompleteCall
0x140045f62  mov     eax, [rsp+48h+Reply]
0x140045f66  test    eax, eax
0x140045f68  jle     short loc_140045F72
0x140045f6a  movzx   eax, ax
0x140045f6d  or      eax, 80070000h
0x140045f72  mov     rbx, [rsp+48h+arg_8]
0x140045f77  add     rsp, 40h
0x140045f7b  pop     rdi
0x140045f7c  retn
```
