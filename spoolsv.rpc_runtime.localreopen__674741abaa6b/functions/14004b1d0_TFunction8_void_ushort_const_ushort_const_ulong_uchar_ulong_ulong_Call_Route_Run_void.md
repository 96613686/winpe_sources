# TFunction8<void *,ushort const *,ushort const *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004b1d0`
- end: `0x14004b2dc`
- name: `?Run@?$TFunction8@PEAXPEBGPEBGPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004b1d0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b298`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b1f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b28a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b1f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b28a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b276`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b276`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b2b4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b2b4`
- `RPCRT4!RpcImpersonateClient` at `0x14004b210`
- `RPCRT4!RpcImpersonateClient` at `0x14004b210`

## pseudocode

```c
__int64 __fastcall TFunction8<void *,unsigned short const *,unsigned short const *,unsigned long *,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 168))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
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
0x14004b1d0  mov     [rsp+arg_8], rbx
0x14004b1d5  push    rdi
0x14004b1d6  sub     rsp, 50h
0x14004b1da  mov     rax, [rcx+0B0h]
0x14004b1e1  mov     rbx, rcx
0x14004b1e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b1ea  mov     [rsp+58h+Reply], 0
0x14004b1f2  mov     rdi, [rax+20h]
0x14004b1f6  mov     rdx, rdi; lpTlsValue
0x14004b1f9  call    cs:__imp_TlsSetValue
0x14004b200  nop     dword ptr [rax+rax+00h]
0x14004b205  test    eax, eax
0x14004b207  jz      loc_14004B298
0x14004b20d  mov     rcx, rdi; BindingHandle
0x14004b210  call    cs:__imp_RpcImpersonateClient
0x14004b217  nop     dword ptr [rax+rax+00h]
0x14004b21c  mov     [rsp+58h+Reply], eax
0x14004b220  test    eax, eax
0x14004b222  jnz     short loc_14004B282
0x14004b224  mov     edx, [rbx+0A0h]
0x14004b22a  mov     r9, [rbx+80h]
0x14004b231  mov     r8, [rbx+78h]
0x14004b235  mov     rcx, [rbx+68h]
0x14004b239  mov     rax, [rbx+0A8h]
0x14004b240  mov     [rsp+58h+var_20], edx
0x14004b244  mov     rdx, [rbx+98h]
0x14004b24b  mov     [rsp+58h+var_28], rdx
0x14004b250  mov     edx, [rbx+90h]
0x14004b256  mov     [rsp+58h+var_30], edx
0x14004b25a  mov     rdx, [rbx+88h]
0x14004b261  mov     [rsp+58h+var_38], rdx
0x14004b266  mov     rdx, [rbx+70h]
0x14004b26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b26f  mov     rcx, rdi; BindingHandle
0x14004b272  mov     [rsp+58h+Reply], eax
0x14004b276  call    cs:__imp_RpcRevertToSelfEx
0x14004b27d  nop     dword ptr [rax+rax+00h]
0x14004b282  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b288  xor     edx, edx; lpTlsValue
0x14004b28a  call    cs:__imp_TlsSetValue
0x14004b291  nop     dword ptr [rax+rax+00h]
0x14004b296  jmp     short loc_14004B2A8
0x14004b298  call    cs:__imp_GetLastError
0x14004b29f  nop     dword ptr [rax+rax+00h]
0x14004b2a4  mov     [rsp+58h+Reply], eax
0x14004b2a8  mov     rcx, [rbx+0B0h]; pAsync
0x14004b2af  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b2b4  call    cs:__imp_RpcAsyncCompleteCall
0x14004b2bb  nop     dword ptr [rax+rax+00h]
0x14004b2c0  mov     eax, [rsp+58h+Reply]
0x14004b2c4  test    eax, eax
0x14004b2c6  jle     short loc_14004B2D0
0x14004b2c8  movzx   eax, ax
0x14004b2cb  or      eax, 80070000h
0x14004b2d0  mov     rbx, [rsp+58h+arg_8]
0x14004b2d5  add     rsp, 50h
0x14004b2d9  pop     rdi
0x14004b2da  retn
```
