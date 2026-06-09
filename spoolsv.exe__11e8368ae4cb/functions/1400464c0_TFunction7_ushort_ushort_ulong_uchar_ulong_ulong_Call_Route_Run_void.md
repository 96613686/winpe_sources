# TFunction7<ushort *,ushort *,ulong,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x1400464c0`
- end: `0x140046597`
- name: `?Run@?$TFunction7@PEAGPEAGKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400464c0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046560`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400464e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046558`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400464e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046558`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004654a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004654a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046576`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046576`
- `RPCRT4!RpcImpersonateClient` at `0x1400464f6`
- `RPCRT4!RpcImpersonateClient` at `0x1400464f6`

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
0x1400464c0  mov     [rsp+arg_8], rbx
0x1400464c5  push    rdi
0x1400464c6  sub     rsp, 40h
0x1400464ca  mov     rax, [rcx+0A8h]
0x1400464d1  mov     rbx, rcx
0x1400464d4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400464da  mov     [rsp+48h+Reply], 0
0x1400464e2  mov     rdi, [rax+20h]
0x1400464e6  mov     rdx, rdi; lpTlsValue
0x1400464e9  call    cs:__imp_TlsSetValue
0x1400464ef  test    eax, eax
0x1400464f1  jz      short loc_140046560
0x1400464f3  mov     rcx, rdi; BindingHandle
0x1400464f6  call    cs:__imp_RpcImpersonateClient
0x1400464fc  mov     [rsp+48h+Reply], eax
0x140046500  test    eax, eax
0x140046502  jnz     short loc_140046550
0x140046504  mov     edx, [rbx+98h]
0x14004650a  mov     r9, [rbx+80h]
0x140046511  mov     r8d, [rbx+78h]
0x140046515  mov     rcx, [rbx+68h]
0x140046519  mov     rax, [rbx+0A0h]
0x140046520  mov     [rsp+48h+var_18], edx
0x140046524  mov     rdx, [rbx+90h]
0x14004652b  mov     [rsp+48h+var_20], rdx
0x140046530  mov     edx, [rbx+88h]
0x140046536  mov     [rsp+48h+var_28], edx
0x14004653a  mov     rdx, [rbx+70h]
0x14004653e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046543  mov     rcx, rdi; BindingHandle
0x140046546  mov     [rsp+48h+Reply], eax
0x14004654a  call    cs:__imp_RpcRevertToSelfEx
0x140046550  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046556  xor     edx, edx; lpTlsValue
0x140046558  call    cs:__imp_TlsSetValue
0x14004655e  jmp     short loc_14004656A
0x140046560  call    cs:__imp_GetLastError
0x140046566  mov     [rsp+48h+Reply], eax
0x14004656a  mov     rcx, [rbx+0A8h]; pAsync
0x140046571  lea     rdx, [rsp+48h+Reply]; Reply
0x140046576  call    cs:__imp_RpcAsyncCompleteCall
0x14004657c  mov     eax, [rsp+48h+Reply]
0x140046580  test    eax, eax
0x140046582  jle     short loc_14004658C
0x140046584  movzx   eax, ax
0x140046587  or      eax, 80070000h
0x14004658c  mov     rbx, [rsp+48h+arg_8]
0x140046591  add     rsp, 40h
0x140046595  pop     rdi
0x140046596  retn
```
