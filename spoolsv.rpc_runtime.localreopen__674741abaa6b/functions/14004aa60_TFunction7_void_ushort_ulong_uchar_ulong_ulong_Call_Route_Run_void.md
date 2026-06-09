# TFunction7<void *,ushort *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004aa60`
- end: `0x14004ab5c`
- name: `?Run@?$TFunction7@PEAXPEAGPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004aa60`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ab18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ab18`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aa89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ab0a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aa89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ab0a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004aaf6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004aaf6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ab34`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ab34`
- `RPCRT4!RpcImpersonateClient` at `0x14004aa9c`
- `RPCRT4!RpcImpersonateClient` at `0x14004aa9c`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned short *,unsigned long *,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
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
0x14004aa60  mov     [rsp+arg_8], rbx
0x14004aa65  push    rdi
0x14004aa66  sub     rsp, 40h
0x14004aa6a  mov     rax, [rcx+0A8h]
0x14004aa71  mov     rbx, rcx
0x14004aa74  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004aa7a  mov     [rsp+48h+Reply], 0
0x14004aa82  mov     rdi, [rax+20h]
0x14004aa86  mov     rdx, rdi; lpTlsValue
0x14004aa89  call    cs:__imp_TlsSetValue
0x14004aa90  nop     dword ptr [rax+rax+00h]
0x14004aa95  test    eax, eax
0x14004aa97  jz      short loc_14004AB18
0x14004aa99  mov     rcx, rdi; BindingHandle
0x14004aa9c  call    cs:__imp_RpcImpersonateClient
0x14004aaa3  nop     dword ptr [rax+rax+00h]
0x14004aaa8  mov     [rsp+48h+Reply], eax
0x14004aaac  test    eax, eax
0x14004aaae  jnz     short loc_14004AB02
0x14004aab0  mov     edx, [rbx+98h]
0x14004aab6  mov     r9, [rbx+80h]
0x14004aabd  mov     r8, [rbx+78h]
0x14004aac1  mov     rcx, [rbx+68h]
0x14004aac5  mov     rax, [rbx+0A0h]
0x14004aacc  mov     [rsp+48h+var_18], edx
0x14004aad0  mov     rdx, [rbx+90h]
0x14004aad7  mov     [rsp+48h+var_20], rdx
0x14004aadc  mov     edx, [rbx+88h]
0x14004aae2  mov     [rsp+48h+var_28], edx
0x14004aae6  mov     rdx, [rbx+70h]
0x14004aaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aaef  mov     rcx, rdi; BindingHandle
0x14004aaf2  mov     [rsp+48h+Reply], eax
0x14004aaf6  call    cs:__imp_RpcRevertToSelfEx
0x14004aafd  nop     dword ptr [rax+rax+00h]
0x14004ab02  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ab08  xor     edx, edx; lpTlsValue
0x14004ab0a  call    cs:__imp_TlsSetValue
0x14004ab11  nop     dword ptr [rax+rax+00h]
0x14004ab16  jmp     short loc_14004AB28
0x14004ab18  call    cs:__imp_GetLastError
0x14004ab1f  nop     dword ptr [rax+rax+00h]
0x14004ab24  mov     [rsp+48h+Reply], eax
0x14004ab28  mov     rcx, [rbx+0A8h]; pAsync
0x14004ab2f  lea     rdx, [rsp+48h+Reply]; Reply
0x14004ab34  call    cs:__imp_RpcAsyncCompleteCall
0x14004ab3b  nop     dword ptr [rax+rax+00h]
0x14004ab40  mov     eax, [rsp+48h+Reply]
0x14004ab44  test    eax, eax
0x14004ab46  jle     short loc_14004AB50
0x14004ab48  movzx   eax, ax
0x14004ab4b  or      eax, 80070000h
0x14004ab50  mov     rbx, [rsp+48h+arg_8]
0x14004ab55  add     rsp, 40h
0x14004ab59  pop     rdi
0x14004ab5a  retn
```
