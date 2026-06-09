# TFunction7<void *,ushort const *,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140046a00`
- end: `0x140046ad9`
- name: `?Run@?$TFunction7@PEAXPEBGPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046a00`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046aa2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046a29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046a9a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046a29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046a9a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046a8c`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046a8c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046ab8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046ab8`
- `RPCRT4!RpcImpersonateClient` at `0x140046a36`
- `RPCRT4!RpcImpersonateClient` at `0x140046a36`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned short const *,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
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
0x140046a00  mov     [rsp+arg_8], rbx
0x140046a05  push    rdi
0x140046a06  sub     rsp, 40h
0x140046a0a  mov     rax, [rcx+0A8h]
0x140046a11  mov     rbx, rcx
0x140046a14  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046a1a  mov     [rsp+48h+Reply], 0
0x140046a22  mov     rdi, [rax+20h]
0x140046a26  mov     rdx, rdi; lpTlsValue
0x140046a29  call    cs:__imp_TlsSetValue
0x140046a2f  test    eax, eax
0x140046a31  jz      short loc_140046AA2
0x140046a33  mov     rcx, rdi; BindingHandle
0x140046a36  call    cs:__imp_RpcImpersonateClient
0x140046a3c  mov     [rsp+48h+Reply], eax
0x140046a40  test    eax, eax
0x140046a42  jnz     short loc_140046A92
0x140046a44  mov     edx, [rbx+98h]
0x140046a4a  mov     r9d, [rbx+80h]
0x140046a51  mov     r8, [rbx+78h]
0x140046a55  mov     rcx, [rbx+68h]
0x140046a59  mov     rax, [rbx+0A0h]
0x140046a60  mov     [rsp+48h+var_18], edx
0x140046a64  mov     rdx, [rbx+90h]
0x140046a6b  mov     [rsp+48h+var_20], rdx
0x140046a70  mov     rdx, [rbx+88h]
0x140046a77  mov     [rsp+48h+var_28], rdx
0x140046a7c  mov     rdx, [rbx+70h]
0x140046a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046a85  mov     rcx, rdi; BindingHandle
0x140046a88  mov     [rsp+48h+Reply], eax
0x140046a8c  call    cs:__imp_RpcRevertToSelfEx
0x140046a92  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046a98  xor     edx, edx; lpTlsValue
0x140046a9a  call    cs:__imp_TlsSetValue
0x140046aa0  jmp     short loc_140046AAC
0x140046aa2  call    cs:__imp_GetLastError
0x140046aa8  mov     [rsp+48h+Reply], eax
0x140046aac  mov     rcx, [rbx+0A8h]; pAsync
0x140046ab3  lea     rdx, [rsp+48h+Reply]; Reply
0x140046ab8  call    cs:__imp_RpcAsyncCompleteCall
0x140046abe  mov     eax, [rsp+48h+Reply]
0x140046ac2  test    eax, eax
0x140046ac4  jle     short loc_140046ACE
0x140046ac6  movzx   eax, ax
0x140046ac9  or      eax, 80070000h
0x140046ace  mov     rbx, [rsp+48h+arg_8]
0x140046ad3  add     rsp, 40h
0x140046ad7  pop     rdi
0x140046ad8  retn
```
