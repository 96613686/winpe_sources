# TFunction7<void *,ulong,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140046760`
- end: `0x140046833`
- name: `?Run@?$TFunction7@PEAXKKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046760`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400467fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400467fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046789`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400467f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046789`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400467f4`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400467e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400467e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046812`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046812`
- `RPCRT4!RpcImpersonateClient` at `0x140046796`
- `RPCRT4!RpcImpersonateClient` at `0x140046796`

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
0x140046760  mov     [rsp+arg_8], rbx
0x140046765  push    rdi
0x140046766  sub     rsp, 40h
0x14004676a  mov     rax, [rcx+0A0h]
0x140046771  mov     rbx, rcx
0x140046774  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004677a  mov     [rsp+48h+Reply], 0
0x140046782  mov     rdi, [rax+20h]
0x140046786  mov     rdx, rdi; lpTlsValue
0x140046789  call    cs:__imp_TlsSetValue
0x14004678f  test    eax, eax
0x140046791  jz      short loc_1400467FC
0x140046793  mov     rcx, rdi; BindingHandle
0x140046796  call    cs:__imp_RpcImpersonateClient
0x14004679c  mov     [rsp+48h+Reply], eax
0x1400467a0  test    eax, eax
0x1400467a2  jnz     short loc_1400467EC
0x1400467a4  mov     edx, [rbx+90h]
0x1400467aa  mov     r9, [rbx+78h]
0x1400467ae  mov     r8d, [rbx+74h]
0x1400467b2  mov     rcx, [rbx+68h]
0x1400467b6  mov     rax, [rbx+98h]
0x1400467bd  mov     [rsp+48h+var_18], edx
0x1400467c1  mov     rdx, [rbx+88h]
0x1400467c8  mov     [rsp+48h+var_20], rdx
0x1400467cd  mov     edx, [rbx+80h]
0x1400467d3  mov     [rsp+48h+var_28], edx
0x1400467d7  mov     edx, [rbx+70h]
0x1400467da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400467df  mov     rcx, rdi; BindingHandle
0x1400467e2  mov     [rsp+48h+Reply], eax
0x1400467e6  call    cs:__imp_RpcRevertToSelfEx
0x1400467ec  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400467f2  xor     edx, edx; lpTlsValue
0x1400467f4  call    cs:__imp_TlsSetValue
0x1400467fa  jmp     short loc_140046806
0x1400467fc  call    cs:__imp_GetLastError
0x140046802  mov     [rsp+48h+Reply], eax
0x140046806  mov     rcx, [rbx+0A0h]; pAsync
0x14004680d  lea     rdx, [rsp+48h+Reply]; Reply
0x140046812  call    cs:__imp_RpcAsyncCompleteCall
0x140046818  mov     eax, [rsp+48h+Reply]
0x14004681c  test    eax, eax
0x14004681e  jle     short loc_140046828
0x140046820  movzx   eax, ax
0x140046823  or      eax, 80070000h
0x140046828  mov     rbx, [rsp+48h+arg_8]
0x14004682d  add     rsp, 40h
0x140046831  pop     rdi
0x140046832  retn
```
