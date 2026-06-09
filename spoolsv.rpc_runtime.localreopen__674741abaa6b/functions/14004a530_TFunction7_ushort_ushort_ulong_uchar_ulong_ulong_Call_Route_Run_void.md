# TFunction7<ushort *,ushort *,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004a530`
- end: `0x14004a62c`
- name: `?Run@?$TFunction7@PEAGPEAGKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a530`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a5e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a5e8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a559`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a5da`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a559`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a5da`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a5c6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a5c6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a604`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a604`
- `RPCRT4!RpcImpersonateClient` at `0x14004a56c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a56c`

## pseudocode

```c
__int64 __fastcall TFunction7<unsigned short *,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
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
                *(unsigned int *)(a1 + 120),
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
0x14004a530  mov     [rsp+arg_8], rbx
0x14004a535  push    rdi
0x14004a536  sub     rsp, 40h
0x14004a53a  mov     rax, [rcx+0A8h]
0x14004a541  mov     rbx, rcx
0x14004a544  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a54a  mov     [rsp+48h+Reply], 0
0x14004a552  mov     rdi, [rax+20h]
0x14004a556  mov     rdx, rdi; lpTlsValue
0x14004a559  call    cs:__imp_TlsSetValue
0x14004a560  nop     dword ptr [rax+rax+00h]
0x14004a565  test    eax, eax
0x14004a567  jz      short loc_14004A5E8
0x14004a569  mov     rcx, rdi; BindingHandle
0x14004a56c  call    cs:__imp_RpcImpersonateClient
0x14004a573  nop     dword ptr [rax+rax+00h]
0x14004a578  mov     [rsp+48h+Reply], eax
0x14004a57c  test    eax, eax
0x14004a57e  jnz     short loc_14004A5D2
0x14004a580  mov     edx, [rbx+98h]
0x14004a586  mov     r9, [rbx+80h]
0x14004a58d  mov     r8d, [rbx+78h]
0x14004a591  mov     rcx, [rbx+68h]
0x14004a595  mov     rax, [rbx+0A0h]
0x14004a59c  mov     [rsp+48h+var_18], edx
0x14004a5a0  mov     rdx, [rbx+90h]
0x14004a5a7  mov     [rsp+48h+var_20], rdx
0x14004a5ac  mov     edx, [rbx+88h]
0x14004a5b2  mov     [rsp+48h+var_28], edx
0x14004a5b6  mov     rdx, [rbx+70h]
0x14004a5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a5bf  mov     rcx, rdi; BindingHandle
0x14004a5c2  mov     [rsp+48h+Reply], eax
0x14004a5c6  call    cs:__imp_RpcRevertToSelfEx
0x14004a5cd  nop     dword ptr [rax+rax+00h]
0x14004a5d2  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a5d8  xor     edx, edx; lpTlsValue
0x14004a5da  call    cs:__imp_TlsSetValue
0x14004a5e1  nop     dword ptr [rax+rax+00h]
0x14004a5e6  jmp     short loc_14004A5F8
0x14004a5e8  call    cs:__imp_GetLastError
0x14004a5ef  nop     dword ptr [rax+rax+00h]
0x14004a5f4  mov     [rsp+48h+Reply], eax
0x14004a5f8  mov     rcx, [rbx+0A8h]; pAsync
0x14004a5ff  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a604  call    cs:__imp_RpcAsyncCompleteCall
0x14004a60b  nop     dword ptr [rax+rax+00h]
0x14004a610  mov     eax, [rsp+48h+Reply]
0x14004a614  test    eax, eax
0x14004a616  jle     short loc_14004A620
0x14004a618  movzx   eax, ax
0x14004a61b  or      eax, 80070000h
0x14004a620  mov     rbx, [rsp+48h+arg_8]
0x14004a625  add     rsp, 40h
0x14004a629  pop     rdi
0x14004a62a  retn
```
