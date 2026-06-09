# TFunction7<ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *>::Run(void)

- ea: `0x14004a640`
- end: `0x14004a73c`
- name: `?Run@?$TFunction7@PEAGPEAPEAXPEAGPEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@UEAAJXZ`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a640`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a6f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a669`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a6ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a669`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a6ea`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a6d6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a6d6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a714`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a714`
- `RPCRT4!RpcImpersonateClient` at `0x14004a67c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a67c`

## pseudocode

```c
__int64 __fastcall TFunction7<unsigned short *,void * *,unsigned short *,_DEVMODE_CONTAINER *,unsigned long,enum Call_Route,_SPLCLIENT_CONTAINER *>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140),
                *(_QWORD *)(a1 + 144));
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
0x14004a640  mov     [rsp+arg_8], rbx
0x14004a645  push    rdi
0x14004a646  sub     rsp, 40h
0x14004a64a  mov     rax, [rcx+0A0h]
0x14004a651  mov     rbx, rcx
0x14004a654  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a65a  mov     [rsp+48h+Reply], 0
0x14004a662  mov     rdi, [rax+20h]
0x14004a666  mov     rdx, rdi; lpTlsValue
0x14004a669  call    cs:__imp_TlsSetValue
0x14004a670  nop     dword ptr [rax+rax+00h]
0x14004a675  test    eax, eax
0x14004a677  jz      short loc_14004A6F8
0x14004a679  mov     rcx, rdi; BindingHandle
0x14004a67c  call    cs:__imp_RpcImpersonateClient
0x14004a683  nop     dword ptr [rax+rax+00h]
0x14004a688  mov     [rsp+48h+Reply], eax
0x14004a68c  test    eax, eax
0x14004a68e  jnz     short loc_14004A6E2
0x14004a690  mov     rdx, [rbx+90h]
0x14004a697  mov     r9, [rbx+80h]
0x14004a69e  mov     r8, [rbx+78h]
0x14004a6a2  mov     rcx, [rbx+68h]
0x14004a6a6  mov     rax, [rbx+98h]
0x14004a6ad  mov     [rsp+48h+var_18], rdx
0x14004a6b2  mov     edx, [rbx+8Ch]
0x14004a6b8  mov     [rsp+48h+var_20], edx
0x14004a6bc  mov     edx, [rbx+88h]
0x14004a6c2  mov     [rsp+48h+var_28], edx
0x14004a6c6  mov     rdx, [rbx+70h]
0x14004a6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6cf  mov     rcx, rdi; BindingHandle
0x14004a6d2  mov     [rsp+48h+Reply], eax
0x14004a6d6  call    cs:__imp_RpcRevertToSelfEx
0x14004a6dd  nop     dword ptr [rax+rax+00h]
0x14004a6e2  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a6e8  xor     edx, edx; lpTlsValue
0x14004a6ea  call    cs:__imp_TlsSetValue
0x14004a6f1  nop     dword ptr [rax+rax+00h]
0x14004a6f6  jmp     short loc_14004A708
0x14004a6f8  call    cs:__imp_GetLastError
0x14004a6ff  nop     dword ptr [rax+rax+00h]
0x14004a704  mov     [rsp+48h+Reply], eax
0x14004a708  mov     rcx, [rbx+0A0h]; pAsync
0x14004a70f  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a714  call    cs:__imp_RpcAsyncCompleteCall
0x14004a71b  nop     dword ptr [rax+rax+00h]
0x14004a720  mov     eax, [rsp+48h+Reply]
0x14004a724  test    eax, eax
0x14004a726  jle     short loc_14004A730
0x14004a728  movzx   eax, ax
0x14004a72b  or      eax, 80070000h
0x14004a730  mov     rbx, [rsp+48h+arg_8]
0x14004a735  add     rsp, 40h
0x14004a739  pop     rdi
0x14004a73a  retn
```
