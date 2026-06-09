# TFunction6<ushort *,ushort *,ushort *,ulong,ulong,Call_Route>::Run(void)

- ea: `0x140045f90`
- end: `0x14004605b`
- name: `?Run@?$TFunction6@PEAGPEAGPEAGKKW4Call_Route@@@@UEAAJXZ`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045f90`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046024`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045fb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004601c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045fb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004601c`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004600e`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004600e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004603a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004603a`
- `RPCRT4!RpcImpersonateClient` at `0x140045fc6`
- `RPCRT4!RpcImpersonateClient` at `0x140045fc6`

## pseudocode

```c
__int64 __fastcall TFunction6<unsigned short *,unsigned short *,unsigned short *,unsigned long,unsigned long,enum Call_Route>::Run(
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
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_DWORD *)(a1 + 132),
                *(_DWORD *)(a1 + 136));
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
0x140045f90  mov     [rsp+arg_8], rbx
0x140045f95  push    rdi
0x140045f96  sub     rsp, 40h
0x140045f9a  mov     rax, [rcx+98h]
0x140045fa1  mov     rbx, rcx
0x140045fa4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045faa  mov     [rsp+48h+Reply], 0
0x140045fb2  mov     rdi, [rax+20h]
0x140045fb6  mov     rdx, rdi; lpTlsValue
0x140045fb9  call    cs:__imp_TlsSetValue
0x140045fbf  test    eax, eax
0x140045fc1  jz      short loc_140046024
0x140045fc3  mov     rcx, rdi; BindingHandle
0x140045fc6  call    cs:__imp_RpcImpersonateClient
0x140045fcc  mov     [rsp+48h+Reply], eax
0x140045fd0  test    eax, eax
0x140045fd2  jnz     short loc_140046014
0x140045fd4  mov     edx, [rbx+88h]
0x140045fda  mov     r9d, [rbx+80h]
0x140045fe1  mov     r8, [rbx+78h]
0x140045fe5  mov     rcx, [rbx+68h]
0x140045fe9  mov     rax, [rbx+90h]
0x140045ff0  mov     [rsp+48h+var_20], edx
0x140045ff4  mov     edx, [rbx+84h]
0x140045ffa  mov     [rsp+48h+var_28], edx
0x140045ffe  mov     rdx, [rbx+70h]
0x140046002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046007  mov     rcx, rdi; BindingHandle
0x14004600a  mov     [rsp+48h+Reply], eax
0x14004600e  call    cs:__imp_RpcRevertToSelfEx
0x140046014  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004601a  xor     edx, edx; lpTlsValue
0x14004601c  call    cs:__imp_TlsSetValue
0x140046022  jmp     short loc_14004602E
0x140046024  call    cs:__imp_GetLastError
0x14004602a  mov     [rsp+48h+Reply], eax
0x14004602e  mov     rcx, [rbx+98h]; pAsync
0x140046035  lea     rdx, [rsp+48h+Reply]; Reply
0x14004603a  call    cs:__imp_RpcAsyncCompleteCall
0x140046040  mov     eax, [rsp+48h+Reply]
0x140046044  test    eax, eax
0x140046046  jle     short loc_140046050
0x140046048  movzx   eax, ax
0x14004604b  or      eax, 80070000h
0x140046050  mov     rbx, [rsp+48h+arg_8]
0x140046055  add     rsp, 40h
0x140046059  pop     rdi
0x14004605a  retn
```
