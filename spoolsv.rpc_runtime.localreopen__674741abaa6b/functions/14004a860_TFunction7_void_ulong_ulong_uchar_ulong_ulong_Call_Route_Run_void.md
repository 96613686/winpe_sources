# TFunction7<void *,ulong,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004a860`
- end: `0x14004a958`
- name: `?Run@?$TFunction7@PEAXKKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a860`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a914`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a889`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a906`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a889`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a906`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a8f2`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a8f2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a930`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a930`
- `RPCRT4!RpcImpersonateClient` at `0x14004a89c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a89c`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned long,unsigned long,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(unsigned int *)(a1 + 116),
                *(_QWORD *)(a1 + 120),
                *(_DWORD *)(a1 + 128),
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
0x14004a860  mov     [rsp+arg_8], rbx
0x14004a865  push    rdi
0x14004a866  sub     rsp, 40h
0x14004a86a  mov     rax, [rcx+0A0h]
0x14004a871  mov     rbx, rcx
0x14004a874  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a87a  mov     [rsp+48h+Reply], 0
0x14004a882  mov     rdi, [rax+20h]
0x14004a886  mov     rdx, rdi; lpTlsValue
0x14004a889  call    cs:__imp_TlsSetValue
0x14004a890  nop     dword ptr [rax+rax+00h]
0x14004a895  test    eax, eax
0x14004a897  jz      short loc_14004A914
0x14004a899  mov     rcx, rdi; BindingHandle
0x14004a89c  call    cs:__imp_RpcImpersonateClient
0x14004a8a3  nop     dword ptr [rax+rax+00h]
0x14004a8a8  mov     [rsp+48h+Reply], eax
0x14004a8ac  test    eax, eax
0x14004a8ae  jnz     short loc_14004A8FE
0x14004a8b0  mov     edx, [rbx+90h]
0x14004a8b6  mov     r9, [rbx+78h]
0x14004a8ba  mov     r8d, [rbx+74h]
0x14004a8be  mov     rcx, [rbx+68h]
0x14004a8c2  mov     rax, [rbx+98h]
0x14004a8c9  mov     [rsp+48h+var_18], edx
0x14004a8cd  mov     rdx, [rbx+88h]
0x14004a8d4  mov     [rsp+48h+var_20], rdx
0x14004a8d9  mov     edx, [rbx+80h]
0x14004a8df  mov     [rsp+48h+var_28], edx
0x14004a8e3  mov     edx, [rbx+70h]
0x14004a8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a8eb  mov     rcx, rdi; BindingHandle
0x14004a8ee  mov     [rsp+48h+Reply], eax
0x14004a8f2  call    cs:__imp_RpcRevertToSelfEx
0x14004a8f9  nop     dword ptr [rax+rax+00h]
0x14004a8fe  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a904  xor     edx, edx; lpTlsValue
0x14004a906  call    cs:__imp_TlsSetValue
0x14004a90d  nop     dword ptr [rax+rax+00h]
0x14004a912  jmp     short loc_14004A924
0x14004a914  call    cs:__imp_GetLastError
0x14004a91b  nop     dword ptr [rax+rax+00h]
0x14004a920  mov     [rsp+48h+Reply], eax
0x14004a924  mov     rcx, [rbx+0A0h]; pAsync
0x14004a92b  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a930  call    cs:__imp_RpcAsyncCompleteCall
0x14004a937  nop     dword ptr [rax+rax+00h]
0x14004a93c  mov     eax, [rsp+48h+Reply]
0x14004a940  test    eax, eax
0x14004a942  jle     short loc_14004A94C
0x14004a944  movzx   eax, ax
0x14004a947  or      eax, 80070000h
0x14004a94c  mov     rbx, [rsp+48h+arg_8]
0x14004a951  add     rsp, 40h
0x14004a955  pop     rdi
0x14004a956  retn
```
