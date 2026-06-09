# TFunction6<ushort *,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140049e30`
- end: `0x140049f22`
- name: `?Run@?$TFunction6@PEAGPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049e30`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ede`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049e59`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049ed0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049e59`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049ed0`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049ebc`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049ebc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049efa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049efa`
- `RPCRT4!RpcImpersonateClient` at `0x140049e6c`
- `RPCRT4!RpcImpersonateClient` at `0x140049e6c`

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
0x140049e30  mov     [rsp+arg_8], rbx
0x140049e35  push    rdi
0x140049e36  sub     rsp, 40h
0x140049e3a  mov     rax, [rcx+0A0h]
0x140049e41  mov     rbx, rcx
0x140049e44  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049e4a  mov     [rsp+48h+Reply], 0
0x140049e52  mov     rdi, [rax+20h]
0x140049e56  mov     rdx, rdi; lpTlsValue
0x140049e59  call    cs:__imp_TlsSetValue
0x140049e60  nop     dword ptr [rax+rax+00h]
0x140049e65  test    eax, eax
0x140049e67  jz      short loc_140049EDE
0x140049e69  mov     rcx, rdi; BindingHandle
0x140049e6c  call    cs:__imp_RpcImpersonateClient
0x140049e73  nop     dword ptr [rax+rax+00h]
0x140049e78  mov     [rsp+48h+Reply], eax
0x140049e7c  test    eax, eax
0x140049e7e  jnz     short loc_140049EC8
0x140049e80  mov     edx, [rbx+90h]
0x140049e86  mov     r9, [rbx+80h]
0x140049e8d  mov     r8d, [rbx+78h]
0x140049e91  mov     rcx, [rbx+68h]
0x140049e95  mov     rax, [rbx+98h]
0x140049e9c  mov     [rsp+48h+var_20], edx
0x140049ea0  mov     rdx, [rbx+88h]
0x140049ea7  mov     [rsp+48h+var_28], rdx
0x140049eac  mov     rdx, [rbx+70h]
0x140049eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049eb5  mov     rcx, rdi; BindingHandle
0x140049eb8  mov     [rsp+48h+Reply], eax
0x140049ebc  call    cs:__imp_RpcRevertToSelfEx
0x140049ec3  nop     dword ptr [rax+rax+00h]
0x140049ec8  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049ece  xor     edx, edx; lpTlsValue
0x140049ed0  call    cs:__imp_TlsSetValue
0x140049ed7  nop     dword ptr [rax+rax+00h]
0x140049edc  jmp     short loc_140049EEE
0x140049ede  call    cs:__imp_GetLastError
0x140049ee5  nop     dword ptr [rax+rax+00h]
0x140049eea  mov     [rsp+48h+Reply], eax
0x140049eee  mov     rcx, [rbx+0A0h]; pAsync
0x140049ef5  lea     rdx, [rsp+48h+Reply]; Reply
0x140049efa  call    cs:__imp_RpcAsyncCompleteCall
0x140049f01  nop     dword ptr [rax+rax+00h]
0x140049f06  mov     eax, [rsp+48h+Reply]
0x140049f0a  test    eax, eax
0x140049f0c  jle     short loc_140049F16
0x140049f0e  movzx   eax, ax
0x140049f11  or      eax, 80070000h
0x140049f16  mov     rbx, [rsp+48h+arg_8]
0x140049f1b  add     rsp, 40h
0x140049f1f  pop     rdi
0x140049f20  retn
```
