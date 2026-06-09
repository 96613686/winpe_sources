# TFunction9<void *,ushort const *,uchar *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14004b520`
- end: `0x14004b638`
- name: `?Run@?$TFunction9@PEAXPEBGPEAEKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004b520`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b5f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b549`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b5e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b549`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b5e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b5d2`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b5d2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b610`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b610`
- `RPCRT4!RpcImpersonateClient` at `0x14004b560`
- `RPCRT4!RpcImpersonateClient` at `0x14004b560`

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
0x14004b520  mov     [rsp+arg_8], rbx
0x14004b525  push    rdi
0x14004b526  sub     rsp, 50h
0x14004b52a  mov     rax, [rcx+0B8h]
0x14004b531  mov     rbx, rcx
0x14004b534  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b53a  mov     [rsp+58h+Reply], 0
0x14004b542  mov     rdi, [rax+20h]
0x14004b546  mov     rdx, rdi; lpTlsValue
0x14004b549  call    cs:__imp_TlsSetValue
0x14004b550  nop     dword ptr [rax+rax+00h]
0x14004b555  test    eax, eax
0x14004b557  jz      loc_14004B5F4
0x14004b55d  mov     rcx, rdi; BindingHandle
0x14004b560  call    cs:__imp_RpcImpersonateClient
0x14004b567  nop     dword ptr [rax+rax+00h]
0x14004b56c  mov     [rsp+58h+Reply], eax
0x14004b570  test    eax, eax
0x14004b572  jnz     short loc_14004B5DE
0x14004b574  mov     ecx, [rbx+0A8h]
0x14004b57a  mov     rdx, [rbx+0A0h]
0x14004b581  mov     r9d, [rbx+80h]
0x14004b588  mov     r8, [rbx+78h]
0x14004b58c  mov     rax, [rbx+0B0h]
0x14004b593  mov     [rsp+58h+var_18], ecx
0x14004b597  mov     rcx, [rbx+68h]
0x14004b59b  mov     [rsp+58h+var_20], rdx
0x14004b5a0  mov     rdx, [rbx+98h]
0x14004b5a7  mov     [rsp+58h+var_28], rdx
0x14004b5ac  mov     edx, [rbx+90h]
0x14004b5b2  mov     [rsp+58h+var_30], edx
0x14004b5b6  mov     rdx, [rbx+88h]
0x14004b5bd  mov     [rsp+58h+var_38], rdx
0x14004b5c2  mov     rdx, [rbx+70h]
0x14004b5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b5cb  mov     rcx, rdi; BindingHandle
0x14004b5ce  mov     [rsp+58h+Reply], eax
0x14004b5d2  call    cs:__imp_RpcRevertToSelfEx
0x14004b5d9  nop     dword ptr [rax+rax+00h]
0x14004b5de  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b5e4  xor     edx, edx; lpTlsValue
0x14004b5e6  call    cs:__imp_TlsSetValue
0x14004b5ed  nop     dword ptr [rax+rax+00h]
0x14004b5f2  jmp     short loc_14004B604
0x14004b5f4  call    cs:__imp_GetLastError
0x14004b5fb  nop     dword ptr [rax+rax+00h]
0x14004b600  mov     [rsp+58h+Reply], eax
0x14004b604  mov     rcx, [rbx+0B8h]; pAsync
0x14004b60b  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b610  call    cs:__imp_RpcAsyncCompleteCall
0x14004b617  nop     dword ptr [rax+rax+00h]
0x14004b61c  mov     eax, [rsp+58h+Reply]
0x14004b620  test    eax, eax
0x14004b622  jle     short loc_14004B62C
0x14004b624  movzx   eax, ax
0x14004b627  or      eax, 80070000h
0x14004b62c  mov     rbx, [rsp+58h+arg_8]
0x14004b631  add     rsp, 50h
0x14004b635  pop     rdi
0x14004b636  retn
```
