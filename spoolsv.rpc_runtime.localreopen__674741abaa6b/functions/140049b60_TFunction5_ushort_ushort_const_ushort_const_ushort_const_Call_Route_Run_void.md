# TFunction5<ushort *,ushort const *,ushort const *,ushort const *,Call_Route>::Run(void)

- ea: `0x140049b60`
- end: `0x140049c46`
- name: `?Run@?$TFunction5@PEAGPEBGPEBGPEBGW4Call_Route@@@@UEAAJXZ`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140049b60`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049c02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049bf4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049bf4`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049be0`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049be0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049c1e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049c1e`
- `RPCRT4!RpcImpersonateClient` at `0x140049b9c`
- `RPCRT4!RpcImpersonateClient` at `0x140049b9c`

## pseudocode

```c
__int64 __fastcall TFunction5<unsigned short *,unsigned short const *,unsigned short const *,unsigned short const *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 144))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
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
0x140049b60  mov     [rsp+arg_8], rbx
0x140049b65  push    rdi
0x140049b66  sub     rsp, 30h
0x140049b6a  mov     rax, [rcx+98h]
0x140049b71  mov     rbx, rcx
0x140049b74  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049b7a  mov     [rsp+38h+Reply], 0
0x140049b82  mov     rdi, [rax+20h]
0x140049b86  mov     rdx, rdi; lpTlsValue
0x140049b89  call    cs:__imp_TlsSetValue
0x140049b90  nop     dword ptr [rax+rax+00h]
0x140049b95  test    eax, eax
0x140049b97  jz      short loc_140049C02
0x140049b99  mov     rcx, rdi; BindingHandle
0x140049b9c  call    cs:__imp_RpcImpersonateClient
0x140049ba3  nop     dword ptr [rax+rax+00h]
0x140049ba8  mov     [rsp+38h+Reply], eax
0x140049bac  test    eax, eax
0x140049bae  jnz     short loc_140049BEC
0x140049bb0  mov     edx, [rbx+88h]
0x140049bb6  mov     r9, [rbx+80h]
0x140049bbd  mov     r8, [rbx+78h]
0x140049bc1  mov     rcx, [rbx+68h]
0x140049bc5  mov     rax, [rbx+90h]
0x140049bcc  mov     [rsp+38h+var_18], edx
0x140049bd0  mov     rdx, [rbx+70h]
0x140049bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049bd9  mov     rcx, rdi; BindingHandle
0x140049bdc  mov     [rsp+38h+Reply], eax
0x140049be0  call    cs:__imp_RpcRevertToSelfEx
0x140049be7  nop     dword ptr [rax+rax+00h]
0x140049bec  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049bf2  xor     edx, edx; lpTlsValue
0x140049bf4  call    cs:__imp_TlsSetValue
0x140049bfb  nop     dword ptr [rax+rax+00h]
0x140049c00  jmp     short loc_140049C12
0x140049c02  call    cs:__imp_GetLastError
0x140049c09  nop     dword ptr [rax+rax+00h]
0x140049c0e  mov     [rsp+38h+Reply], eax
0x140049c12  mov     rcx, [rbx+98h]; pAsync
0x140049c19  lea     rdx, [rsp+38h+Reply]; Reply
0x140049c1e  call    cs:__imp_RpcAsyncCompleteCall
0x140049c25  nop     dword ptr [rax+rax+00h]
0x140049c2a  mov     eax, [rsp+38h+Reply]
0x140049c2e  test    eax, eax
0x140049c30  jle     short loc_140049C3A
0x140049c32  movzx   eax, ax
0x140049c35  or      eax, 80070000h
0x140049c3a  mov     rbx, [rsp+38h+arg_8]
0x140049c3f  add     rsp, 30h
0x140049c43  pop     rdi
0x140049c44  retn
```
