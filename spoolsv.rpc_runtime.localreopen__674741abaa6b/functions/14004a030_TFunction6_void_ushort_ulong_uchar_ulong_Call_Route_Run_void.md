# TFunction6<void *,ushort *,ulong,uchar *,ulong,Call_Route>::Run(void)

- ea: `0x14004a030`
- end: `0x14004a120`
- name: `?Run@?$TFunction6@PEAXPEAGKPEAEKW4Call_Route@@@@UEAAJXZ`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a030`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a0dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a0dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a059`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a0ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a059`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a0ce`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a0ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a0ba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a0f8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a0f8`
- `RPCRT4!RpcImpersonateClient` at `0x14004a06c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a06c`

## pseudocode

```c
__int64 __fastcall TFunction6<void *,unsigned short *,unsigned long,unsigned char *,unsigned long,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 144))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140));
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
0x14004a030  mov     [rsp+arg_8], rbx
0x14004a035  push    rdi
0x14004a036  sub     rsp, 40h
0x14004a03a  mov     rax, [rcx+98h]
0x14004a041  mov     rbx, rcx
0x14004a044  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a04a  mov     [rsp+48h+Reply], 0
0x14004a052  mov     rdi, [rax+20h]
0x14004a056  mov     rdx, rdi; lpTlsValue
0x14004a059  call    cs:__imp_TlsSetValue
0x14004a060  nop     dword ptr [rax+rax+00h]
0x14004a065  test    eax, eax
0x14004a067  jz      short loc_14004A0DC
0x14004a069  mov     rcx, rdi; BindingHandle
0x14004a06c  call    cs:__imp_RpcImpersonateClient
0x14004a073  nop     dword ptr [rax+rax+00h]
0x14004a078  mov     [rsp+48h+Reply], eax
0x14004a07c  test    eax, eax
0x14004a07e  jnz     short loc_14004A0C6
0x14004a080  mov     edx, [rbx+8Ch]
0x14004a086  mov     r9, [rbx+80h]
0x14004a08d  mov     r8d, [rbx+78h]
0x14004a091  mov     rcx, [rbx+68h]
0x14004a095  mov     rax, [rbx+90h]
0x14004a09c  mov     [rsp+48h+var_20], edx
0x14004a0a0  mov     edx, [rbx+88h]
0x14004a0a6  mov     [rsp+48h+var_28], edx
0x14004a0aa  mov     rdx, [rbx+70h]
0x14004a0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a0b3  mov     rcx, rdi; BindingHandle
0x14004a0b6  mov     [rsp+48h+Reply], eax
0x14004a0ba  call    cs:__imp_RpcRevertToSelfEx
0x14004a0c1  nop     dword ptr [rax+rax+00h]
0x14004a0c6  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a0cc  xor     edx, edx; lpTlsValue
0x14004a0ce  call    cs:__imp_TlsSetValue
0x14004a0d5  nop     dword ptr [rax+rax+00h]
0x14004a0da  jmp     short loc_14004A0EC
0x14004a0dc  call    cs:__imp_GetLastError
0x14004a0e3  nop     dword ptr [rax+rax+00h]
0x14004a0e8  mov     [rsp+48h+Reply], eax
0x14004a0ec  mov     rcx, [rbx+98h]; pAsync
0x14004a0f3  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a0f8  call    cs:__imp_RpcAsyncCompleteCall
0x14004a0ff  nop     dword ptr [rax+rax+00h]
0x14004a104  mov     eax, [rsp+48h+Reply]
0x14004a108  test    eax, eax
0x14004a10a  jle     short loc_14004A114
0x14004a10c  movzx   eax, ax
0x14004a10f  or      eax, 80070000h
0x14004a114  mov     rbx, [rsp+48h+arg_8]
0x14004a119  add     rsp, 40h
0x14004a11d  pop     rdi
0x14004a11e  retn
```
