# TFunction7<void *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14004a420`
- end: `0x14004a521`
- name: `?Run@?$TFunction7@PEAXKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a420`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a4dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a449`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a4cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a449`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a4cf`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a4bb`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a4bb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a4f9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a4f9`
- `RPCRT4!RpcImpersonateClient` at `0x14004a460`
- `RPCRT4!RpcImpersonateClient` at `0x14004a460`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
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
                *(unsigned int *)(a1 + 112),
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
0x14004a420  mov     [rsp+arg_8], rbx
0x14004a425  push    rdi
0x14004a426  sub     rsp, 40h
0x14004a42a  mov     rax, [rcx+0A8h]
0x14004a431  mov     rbx, rcx
0x14004a434  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a43a  mov     [rsp+48h+Reply], 0
0x14004a442  mov     rdi, [rax+20h]
0x14004a446  mov     rdx, rdi; lpTlsValue
0x14004a449  call    cs:__imp_TlsSetValue
0x14004a450  nop     dword ptr [rax+rax+00h]
0x14004a455  test    eax, eax
0x14004a457  jz      loc_14004A4DD
0x14004a45d  mov     rcx, rdi; BindingHandle
0x14004a460  call    cs:__imp_RpcImpersonateClient
0x14004a467  nop     dword ptr [rax+rax+00h]
0x14004a46c  mov     [rsp+48h+Reply], eax
0x14004a470  test    eax, eax
0x14004a472  jnz     short loc_14004A4C7
0x14004a474  mov     edx, [rbx+98h]
0x14004a47a  mov     r9d, [rbx+80h]
0x14004a481  mov     r8, [rbx+78h]
0x14004a485  mov     rcx, [rbx+68h]
0x14004a489  mov     rax, [rbx+0A0h]
0x14004a490  mov     [rsp+48h+var_18], edx
0x14004a494  mov     rdx, [rbx+90h]
0x14004a49b  mov     [rsp+48h+var_20], rdx
0x14004a4a0  mov     rdx, [rbx+88h]
0x14004a4a7  mov     [rsp+48h+var_28], rdx
0x14004a4ac  mov     edx, [rbx+70h]
0x14004a4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a4b4  mov     rcx, rdi; BindingHandle
0x14004a4b7  mov     [rsp+48h+Reply], eax
0x14004a4bb  call    cs:__imp_RpcRevertToSelfEx
0x14004a4c2  nop     dword ptr [rax+rax+00h]
0x14004a4c7  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a4cd  xor     edx, edx; lpTlsValue
0x14004a4cf  call    cs:__imp_TlsSetValue
0x14004a4d6  nop     dword ptr [rax+rax+00h]
0x14004a4db  jmp     short loc_14004A4ED
0x14004a4dd  call    cs:__imp_GetLastError
0x14004a4e4  nop     dword ptr [rax+rax+00h]
0x14004a4e9  mov     [rsp+48h+Reply], eax
0x14004a4ed  mov     rcx, [rbx+0A8h]; pAsync
0x14004a4f4  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a4f9  call    cs:__imp_RpcAsyncCompleteCall
0x14004a500  nop     dword ptr [rax+rax+00h]
0x14004a505  mov     eax, [rsp+48h+Reply]
0x14004a509  test    eax, eax
0x14004a50b  jle     short loc_14004A515
0x14004a50d  movzx   eax, ax
0x14004a510  or      eax, 80070000h
0x14004a515  mov     rbx, [rsp+48h+arg_8]
0x14004a51a  add     rsp, 40h
0x14004a51e  pop     rdi
0x14004a51f  retn
```
