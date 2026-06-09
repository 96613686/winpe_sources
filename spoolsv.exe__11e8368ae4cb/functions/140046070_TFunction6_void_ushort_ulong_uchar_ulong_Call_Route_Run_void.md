# TFunction6<void *,ushort *,ulong,uchar *,ulong,Call_Route>::Run(void)

- ea: `0x140046070`
- end: `0x14004613b`
- name: `?Run@?$TFunction6@PEAXPEAGKPEAEKW4Call_Route@@@@UEAAJXZ`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046070`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046104`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046099`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400460fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046099`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400460fc`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400460ee`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400460ee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004611a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004611a`
- `RPCRT4!RpcImpersonateClient` at `0x1400460a6`
- `RPCRT4!RpcImpersonateClient` at `0x1400460a6`

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
0x140046070  mov     [rsp+arg_8], rbx
0x140046075  push    rdi
0x140046076  sub     rsp, 40h
0x14004607a  mov     rax, [rcx+98h]
0x140046081  mov     rbx, rcx
0x140046084  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004608a  mov     [rsp+48h+Reply], 0
0x140046092  mov     rdi, [rax+20h]
0x140046096  mov     rdx, rdi; lpTlsValue
0x140046099  call    cs:__imp_TlsSetValue
0x14004609f  test    eax, eax
0x1400460a1  jz      short loc_140046104
0x1400460a3  mov     rcx, rdi; BindingHandle
0x1400460a6  call    cs:__imp_RpcImpersonateClient
0x1400460ac  mov     [rsp+48h+Reply], eax
0x1400460b0  test    eax, eax
0x1400460b2  jnz     short loc_1400460F4
0x1400460b4  mov     edx, [rbx+8Ch]
0x1400460ba  mov     r9, [rbx+80h]
0x1400460c1  mov     r8d, [rbx+78h]
0x1400460c5  mov     rcx, [rbx+68h]
0x1400460c9  mov     rax, [rbx+90h]
0x1400460d0  mov     [rsp+48h+var_20], edx
0x1400460d4  mov     edx, [rbx+88h]
0x1400460da  mov     [rsp+48h+var_28], edx
0x1400460de  mov     rdx, [rbx+70h]
0x1400460e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400460e7  mov     rcx, rdi; BindingHandle
0x1400460ea  mov     [rsp+48h+Reply], eax
0x1400460ee  call    cs:__imp_RpcRevertToSelfEx
0x1400460f4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400460fa  xor     edx, edx; lpTlsValue
0x1400460fc  call    cs:__imp_TlsSetValue
0x140046102  jmp     short loc_14004610E
0x140046104  call    cs:__imp_GetLastError
0x14004610a  mov     [rsp+48h+Reply], eax
0x14004610e  mov     rcx, [rbx+98h]; pAsync
0x140046115  lea     rdx, [rsp+48h+Reply]; Reply
0x14004611a  call    cs:__imp_RpcAsyncCompleteCall
0x140046120  mov     eax, [rsp+48h+Reply]
0x140046124  test    eax, eax
0x140046126  jle     short loc_140046130
0x140046128  movzx   eax, ax
0x14004612b  or      eax, 80070000h
0x140046130  mov     rbx, [rsp+48h+arg_8]
0x140046135  add     rsp, 40h
0x140046139  pop     rdi
0x14004613a  retn
```
