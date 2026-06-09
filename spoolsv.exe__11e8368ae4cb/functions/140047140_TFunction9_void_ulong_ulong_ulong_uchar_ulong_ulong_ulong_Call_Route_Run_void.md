# TFunction9<void *,ulong,ulong,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140047140`
- end: `0x14004722f`
- name: `?Run@?$TFunction9@PEAXKKKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140047140`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400471f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400471f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047169`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400471f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047169`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400471f0`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400471e2`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400471e2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004720e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004720e`
- `RPCRT4!RpcImpersonateClient` at `0x14004717a`
- `RPCRT4!RpcImpersonateClient` at `0x14004717a`

## pseudocode

```c
__int64 __fastcall TFunction9<void *,unsigned long,unsigned long,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 176);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 168))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(unsigned int *)(a1 + 116),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152),
                *(_DWORD *)(a1 + 160));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 176), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140047140  mov     [rsp+arg_8], rbx
0x140047145  push    rdi
0x140047146  sub     rsp, 50h
0x14004714a  mov     rax, [rcx+0B0h]
0x140047151  mov     rbx, rcx
0x140047154  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004715a  mov     [rsp+58h+Reply], 0
0x140047162  mov     rdi, [rax+20h]
0x140047166  mov     rdx, rdi; lpTlsValue
0x140047169  call    cs:__imp_TlsSetValue
0x14004716f  test    eax, eax
0x140047171  jz      loc_1400471F8
0x140047177  mov     rcx, rdi; BindingHandle
0x14004717a  call    cs:__imp_RpcImpersonateClient
0x140047180  mov     [rsp+58h+Reply], eax
0x140047184  test    eax, eax
0x140047186  jnz     short loc_1400471E8
0x140047188  mov     ecx, [rbx+0A0h]
0x14004718e  mov     rdx, [rbx+98h]
0x140047195  mov     r9d, [rbx+78h]
0x140047199  mov     r8d, [rbx+74h]
0x14004719d  mov     rax, [rbx+0A8h]
0x1400471a4  mov     [rsp+58h+var_18], ecx
0x1400471a8  mov     rcx, [rbx+68h]
0x1400471ac  mov     [rsp+58h+var_20], rdx
0x1400471b1  mov     rdx, [rbx+90h]
0x1400471b8  mov     [rsp+58h+var_28], rdx
0x1400471bd  mov     edx, [rbx+88h]
0x1400471c3  mov     [rsp+58h+var_30], edx
0x1400471c7  mov     rdx, [rbx+80h]
0x1400471ce  mov     [rsp+58h+var_38], rdx
0x1400471d3  mov     edx, [rbx+70h]
0x1400471d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400471db  mov     rcx, rdi; BindingHandle
0x1400471de  mov     [rsp+58h+Reply], eax
0x1400471e2  call    cs:__imp_RpcRevertToSelfEx
0x1400471e8  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400471ee  xor     edx, edx; lpTlsValue
0x1400471f0  call    cs:__imp_TlsSetValue
0x1400471f6  jmp     short loc_140047202
0x1400471f8  call    cs:__imp_GetLastError
0x1400471fe  mov     [rsp+58h+Reply], eax
0x140047202  mov     rcx, [rbx+0B0h]; pAsync
0x140047209  lea     rdx, [rsp+58h+Reply]; Reply
0x14004720e  call    cs:__imp_RpcAsyncCompleteCall
0x140047214  mov     eax, [rsp+58h+Reply]
0x140047218  test    eax, eax
0x14004721a  jle     short loc_140047224
0x14004721c  movzx   eax, ax
0x14004721f  or      eax, 80070000h
0x140047224  mov     rbx, [rsp+58h+arg_8]
0x140047229  add     rsp, 50h
0x14004722d  pop     rdi
0x14004722e  retn
```
