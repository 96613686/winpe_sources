# TFunction7<ushort *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,void * *,Call_Route,_SPLCLIENT_CONTAINER *>::Run(void)

- ea: `0x14004a750`
- end: `0x14004a852`
- name: `?Run@?$TFunction7@PEAGPEAU_PRINTER_CONTAINER@@PEAU_DEVMODE_CONTAINER@@PEAU_SECURITY_CONTAINER@@PEAPEAXW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@UEAAJXZ`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a750`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a80e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a779`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a800`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a779`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a800`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a7ec`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a7ec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a82a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a82a`
- `RPCRT4!RpcImpersonateClient` at `0x14004a790`
- `RPCRT4!RpcImpersonateClient` at `0x14004a790`

## pseudocode

```c
__int64 __fastcall TFunction7<unsigned short *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,void * *,enum Call_Route,_SPLCLIENT_CONTAINER *>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152));
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
0x14004a750  mov     [rsp+arg_8], rbx
0x14004a755  push    rdi
0x14004a756  sub     rsp, 40h
0x14004a75a  mov     rax, [rcx+0A8h]
0x14004a761  mov     rbx, rcx
0x14004a764  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a76a  mov     [rsp+48h+Reply], 0
0x14004a772  mov     rdi, [rax+20h]
0x14004a776  mov     rdx, rdi; lpTlsValue
0x14004a779  call    cs:__imp_TlsSetValue
0x14004a780  nop     dword ptr [rax+rax+00h]
0x14004a785  test    eax, eax
0x14004a787  jz      loc_14004A80E
0x14004a78d  mov     rcx, rdi; BindingHandle
0x14004a790  call    cs:__imp_RpcImpersonateClient
0x14004a797  nop     dword ptr [rax+rax+00h]
0x14004a79c  mov     [rsp+48h+Reply], eax
0x14004a7a0  test    eax, eax
0x14004a7a2  jnz     short loc_14004A7F8
0x14004a7a4  mov     rdx, [rbx+98h]
0x14004a7ab  mov     r9, [rbx+80h]
0x14004a7b2  mov     r8, [rbx+78h]
0x14004a7b6  mov     rcx, [rbx+68h]
0x14004a7ba  mov     rax, [rbx+0A0h]
0x14004a7c1  mov     [rsp+48h+var_18], rdx
0x14004a7c6  mov     edx, [rbx+90h]
0x14004a7cc  mov     [rsp+48h+var_20], edx
0x14004a7d0  mov     rdx, [rbx+88h]
0x14004a7d7  mov     [rsp+48h+var_28], rdx
0x14004a7dc  mov     rdx, [rbx+70h]
0x14004a7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a7e5  mov     rcx, rdi; BindingHandle
0x14004a7e8  mov     [rsp+48h+Reply], eax
0x14004a7ec  call    cs:__imp_RpcRevertToSelfEx
0x14004a7f3  nop     dword ptr [rax+rax+00h]
0x14004a7f8  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a7fe  xor     edx, edx; lpTlsValue
0x14004a800  call    cs:__imp_TlsSetValue
0x14004a807  nop     dword ptr [rax+rax+00h]
0x14004a80c  jmp     short loc_14004A81E
0x14004a80e  call    cs:__imp_GetLastError
0x14004a815  nop     dword ptr [rax+rax+00h]
0x14004a81a  mov     [rsp+48h+Reply], eax
0x14004a81e  mov     rcx, [rbx+0A8h]; pAsync
0x14004a825  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a82a  call    cs:__imp_RpcAsyncCompleteCall
0x14004a831  nop     dword ptr [rax+rax+00h]
0x14004a836  mov     eax, [rsp+48h+Reply]
0x14004a83a  test    eax, eax
0x14004a83c  jle     short loc_14004A846
0x14004a83e  movzx   eax, ax
0x14004a841  or      eax, 80070000h
0x14004a846  mov     rbx, [rsp+48h+arg_8]
0x14004a84b  add     rsp, 40h
0x14004a84f  pop     rdi
0x14004a850  retn
```
