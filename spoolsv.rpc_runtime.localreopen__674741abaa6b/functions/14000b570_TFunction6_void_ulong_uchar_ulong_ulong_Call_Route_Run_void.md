# TFunction6<void *,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14000b570`
- end: `0x14000b666`
- name: `?Run@?$TFunction6@PEAXKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b570`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b5a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b599`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b655`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b599`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000b655`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000b641`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000b641`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b5c5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b5c5`
- `RPCRT4!RpcImpersonateClient` at `0x14000b5f2`
- `RPCRT4!RpcImpersonateClient` at `0x14000b5f2`

## pseudocode

```c
__int64 __fastcall TFunction6<void *,unsigned long,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
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
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
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
0x14000b570  mov     [rsp+arg_8], rbx
0x14000b575  push    rdi
0x14000b576  sub     rsp, 40h
0x14000b57a  mov     rax, [rcx+0A0h]
0x14000b581  mov     rbx, rcx
0x14000b584  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000b58a  mov     [rsp+48h+Reply], 0
0x14000b592  mov     rdi, [rax+20h]
0x14000b596  mov     rdx, rdi; lpTlsValue
0x14000b599  call    cs:__imp_TlsSetValue
0x14000b5a0  nop     dword ptr [rax+rax+00h]
0x14000b5a5  test    eax, eax
0x14000b5a7  jnz     short loc_14000B5EF
0x14000b5a9  call    cs:__imp_GetLastError
0x14000b5b0  nop     dword ptr [rax+rax+00h]
0x14000b5b5  mov     [rsp+48h+Reply], eax
0x14000b5b9  mov     rcx, [rbx+0A0h]; pAsync
0x14000b5c0  lea     rdx, [rsp+48h+Reply]; Reply
0x14000b5c5  call    cs:__imp_RpcAsyncCompleteCall
0x14000b5cc  nop     dword ptr [rax+rax+00h]
0x14000b5d1  mov     eax, [rsp+48h+Reply]
0x14000b5d5  test    eax, eax
0x14000b5d7  jg      short loc_14000B5E5
0x14000b5d9  mov     rbx, [rsp+48h+arg_8]
0x14000b5de  add     rsp, 40h
0x14000b5e2  pop     rdi
0x14000b5e3  retn
0x14000b5e5  movzx   eax, ax
0x14000b5e8  or      eax, 80070000h
0x14000b5ed  jmp     short loc_14000B5D9
0x14000b5ef  mov     rcx, rdi; BindingHandle
0x14000b5f2  call    cs:__imp_RpcImpersonateClient
0x14000b5f9  nop     dword ptr [rax+rax+00h]
0x14000b5fe  mov     [rsp+48h+Reply], eax
0x14000b602  test    eax, eax
0x14000b604  jnz     short loc_14000B64D
0x14000b606  mov     edx, [rbx+90h]
0x14000b60c  mov     r9d, [rbx+80h]
0x14000b613  mov     r8, [rbx+78h]
0x14000b617  mov     rcx, [rbx+68h]
0x14000b61b  mov     rax, [rbx+98h]
0x14000b622  mov     [rsp+48h+var_20], edx
0x14000b626  mov     rdx, [rbx+88h]
0x14000b62d  mov     [rsp+48h+var_28], rdx
0x14000b632  mov     edx, [rbx+70h]
0x14000b635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b63a  mov     rcx, rdi; BindingHandle
0x14000b63d  mov     [rsp+48h+Reply], eax
0x14000b641  call    cs:__imp_RpcRevertToSelfEx
0x14000b648  nop     dword ptr [rax+rax+00h]
0x14000b64d  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000b653  xor     edx, edx; lpTlsValue
0x14000b655  call    cs:__imp_TlsSetValue
0x14000b65c  nop     dword ptr [rax+rax+00h]
0x14000b661  jmp     loc_14000B5B9
```
