# TFunction7<void *,uchar *,ulong,uchar *,ulong,ulong,Call_Route>::Run(void)

- ea: `0x14004a960`
- end: `0x14004aa5a`
- name: `?Run@?$TFunction7@PEAXPEAEKPEAEKKW4Call_Route@@@@UEAAJXZ`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a960`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa16`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a989`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aa08`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a989`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aa08`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a9f4`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a9f4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004aa32`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004aa32`
- `RPCRT4!RpcImpersonateClient` at `0x14004a99c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a99c`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned char *,unsigned long,unsigned char *,unsigned long,unsigned long,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140),
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
0x14004a960  mov     [rsp+arg_8], rbx
0x14004a965  push    rdi
0x14004a966  sub     rsp, 40h
0x14004a96a  mov     rax, [rcx+0A0h]
0x14004a971  mov     rbx, rcx
0x14004a974  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a97a  mov     [rsp+48h+Reply], 0
0x14004a982  mov     rdi, [rax+20h]
0x14004a986  mov     rdx, rdi; lpTlsValue
0x14004a989  call    cs:__imp_TlsSetValue
0x14004a990  nop     dword ptr [rax+rax+00h]
0x14004a995  test    eax, eax
0x14004a997  jz      short loc_14004AA16
0x14004a999  mov     rcx, rdi; BindingHandle
0x14004a99c  call    cs:__imp_RpcImpersonateClient
0x14004a9a3  nop     dword ptr [rax+rax+00h]
0x14004a9a8  mov     [rsp+48h+Reply], eax
0x14004a9ac  test    eax, eax
0x14004a9ae  jnz     short loc_14004AA00
0x14004a9b0  mov     edx, [rbx+90h]
0x14004a9b6  mov     r9, [rbx+80h]
0x14004a9bd  mov     r8d, [rbx+78h]
0x14004a9c1  mov     rcx, [rbx+68h]
0x14004a9c5  mov     rax, [rbx+98h]
0x14004a9cc  mov     [rsp+48h+var_18], edx
0x14004a9d0  mov     edx, [rbx+8Ch]
0x14004a9d6  mov     [rsp+48h+var_20], edx
0x14004a9da  mov     edx, [rbx+88h]
0x14004a9e0  mov     [rsp+48h+var_28], edx
0x14004a9e4  mov     rdx, [rbx+70h]
0x14004a9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a9ed  mov     rcx, rdi; BindingHandle
0x14004a9f0  mov     [rsp+48h+Reply], eax
0x14004a9f4  call    cs:__imp_RpcRevertToSelfEx
0x14004a9fb  nop     dword ptr [rax+rax+00h]
0x14004aa00  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004aa06  xor     edx, edx; lpTlsValue
0x14004aa08  call    cs:__imp_TlsSetValue
0x14004aa0f  nop     dword ptr [rax+rax+00h]
0x14004aa14  jmp     short loc_14004AA26
0x14004aa16  call    cs:__imp_GetLastError
0x14004aa1d  nop     dword ptr [rax+rax+00h]
0x14004aa22  mov     [rsp+48h+Reply], eax
0x14004aa26  mov     rcx, [rbx+0A0h]; pAsync
0x14004aa2d  lea     rdx, [rsp+48h+Reply]; Reply
0x14004aa32  call    cs:__imp_RpcAsyncCompleteCall
0x14004aa39  nop     dword ptr [rax+rax+00h]
0x14004aa3e  mov     eax, [rsp+48h+Reply]
0x14004aa42  test    eax, eax
0x14004aa44  jle     short loc_14004AA4E
0x14004aa46  movzx   eax, ax
0x14004aa49  or      eax, 80070000h
0x14004aa4e  mov     rbx, [rsp+48h+arg_8]
0x14004aa53  add     rsp, 40h
0x14004aa57  pop     rdi
0x14004aa58  retn
```
