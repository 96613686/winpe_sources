# TFunction9<void *,ushort const *,uchar *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140047240`
- end: `0x140047333`
- name: `?Run@?$TFunction9@PEAXPEBGPEAEKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140047240`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400472fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400472fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047269`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400472f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047269`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400472f4`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400472e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400472e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047312`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047312`
- `RPCRT4!RpcImpersonateClient` at `0x14004727a`
- `RPCRT4!RpcImpersonateClient` at `0x14004727a`

## pseudocode

```c
__int64 __fastcall TFunction9<void *,unsigned short const *,unsigned char *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 184);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 176))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152),
                *(_QWORD *)(a1 + 160),
                *(_DWORD *)(a1 + 168));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 184), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140047240  mov     [rsp+arg_8], rbx
0x140047245  push    rdi
0x140047246  sub     rsp, 50h
0x14004724a  mov     rax, [rcx+0B8h]
0x140047251  mov     rbx, rcx
0x140047254  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004725a  mov     [rsp+58h+Reply], 0
0x140047262  mov     rdi, [rax+20h]
0x140047266  mov     rdx, rdi; lpTlsValue
0x140047269  call    cs:__imp_TlsSetValue
0x14004726f  test    eax, eax
0x140047271  jz      loc_1400472FC
0x140047277  mov     rcx, rdi; BindingHandle
0x14004727a  call    cs:__imp_RpcImpersonateClient
0x140047280  mov     [rsp+58h+Reply], eax
0x140047284  test    eax, eax
0x140047286  jnz     short loc_1400472EC
0x140047288  mov     ecx, [rbx+0A8h]
0x14004728e  mov     rdx, [rbx+0A0h]
0x140047295  mov     r9d, [rbx+80h]
0x14004729c  mov     r8, [rbx+78h]
0x1400472a0  mov     rax, [rbx+0B0h]
0x1400472a7  mov     [rsp+58h+var_18], ecx
0x1400472ab  mov     rcx, [rbx+68h]
0x1400472af  mov     [rsp+58h+var_20], rdx
0x1400472b4  mov     rdx, [rbx+98h]
0x1400472bb  mov     [rsp+58h+var_28], rdx
0x1400472c0  mov     edx, [rbx+90h]
0x1400472c6  mov     [rsp+58h+var_30], edx
0x1400472ca  mov     rdx, [rbx+88h]
0x1400472d1  mov     [rsp+58h+var_38], rdx
0x1400472d6  mov     rdx, [rbx+70h]
0x1400472da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400472df  mov     rcx, rdi; BindingHandle
0x1400472e2  mov     [rsp+58h+Reply], eax
0x1400472e6  call    cs:__imp_RpcRevertToSelfEx
0x1400472ec  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400472f2  xor     edx, edx; lpTlsValue
0x1400472f4  call    cs:__imp_TlsSetValue
0x1400472fa  jmp     short loc_140047306
0x1400472fc  call    cs:__imp_GetLastError
0x140047302  mov     [rsp+58h+Reply], eax
0x140047306  mov     rcx, [rbx+0B8h]; pAsync
0x14004730d  lea     rdx, [rsp+58h+Reply]; Reply
0x140047312  call    cs:__imp_RpcAsyncCompleteCall
0x140047318  mov     eax, [rsp+58h+Reply]
0x14004731c  test    eax, eax
0x14004731e  jle     short loc_140047328
0x140047320  movzx   eax, ax
0x140047323  or      eax, 80070000h
0x140047328  mov     rbx, [rsp+58h+arg_8]
0x14004732d  add     rsp, 50h
0x140047331  pop     rdi
0x140047332  retn
```
