# TFunction7<void *,ushort *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140046920`
- end: `0x1400469f7`
- name: `?Run@?$TFunction7@PEAXPEAGPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046920`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400469c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400469c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046949`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400469b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046949`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400469b8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400469aa`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400469aa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400469d6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400469d6`
- `RPCRT4!RpcImpersonateClient` at `0x140046956`
- `RPCRT4!RpcImpersonateClient` at `0x140046956`

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
0x140046920  mov     [rsp+arg_8], rbx
0x140046925  push    rdi
0x140046926  sub     rsp, 40h
0x14004692a  mov     rax, [rcx+0A8h]
0x140046931  mov     rbx, rcx
0x140046934  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004693a  mov     [rsp+48h+Reply], 0
0x140046942  mov     rdi, [rax+20h]
0x140046946  mov     rdx, rdi; lpTlsValue
0x140046949  call    cs:__imp_TlsSetValue
0x14004694f  test    eax, eax
0x140046951  jz      short loc_1400469C0
0x140046953  mov     rcx, rdi; BindingHandle
0x140046956  call    cs:__imp_RpcImpersonateClient
0x14004695c  mov     [rsp+48h+Reply], eax
0x140046960  test    eax, eax
0x140046962  jnz     short loc_1400469B0
0x140046964  mov     edx, [rbx+98h]
0x14004696a  mov     r9, [rbx+80h]
0x140046971  mov     r8, [rbx+78h]
0x140046975  mov     rcx, [rbx+68h]
0x140046979  mov     rax, [rbx+0A0h]
0x140046980  mov     [rsp+48h+var_18], edx
0x140046984  mov     rdx, [rbx+90h]
0x14004698b  mov     [rsp+48h+var_20], rdx
0x140046990  mov     edx, [rbx+88h]
0x140046996  mov     [rsp+48h+var_28], edx
0x14004699a  mov     rdx, [rbx+70h]
0x14004699e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400469a3  mov     rcx, rdi; BindingHandle
0x1400469a6  mov     [rsp+48h+Reply], eax
0x1400469aa  call    cs:__imp_RpcRevertToSelfEx
0x1400469b0  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400469b6  xor     edx, edx; lpTlsValue
0x1400469b8  call    cs:__imp_TlsSetValue
0x1400469be  jmp     short loc_1400469CA
0x1400469c0  call    cs:__imp_GetLastError
0x1400469c6  mov     [rsp+48h+Reply], eax
0x1400469ca  mov     rcx, [rbx+0A8h]; pAsync
0x1400469d1  lea     rdx, [rsp+48h+Reply]; Reply
0x1400469d6  call    cs:__imp_RpcAsyncCompleteCall
0x1400469dc  mov     eax, [rsp+48h+Reply]
0x1400469e0  test    eax, eax
0x1400469e2  jle     short loc_1400469EC
0x1400469e4  movzx   eax, ax
0x1400469e7  or      eax, 80070000h
0x1400469ec  mov     rbx, [rsp+48h+arg_8]
0x1400469f1  add     rsp, 40h
0x1400469f5  pop     rdi
0x1400469f6  retn
```
