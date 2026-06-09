# TFunction10<void *,ulong,ushort *,ulong,ulong *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x1400455b0`
- end: `0x1400456ae`
- name: `?Run@?$TFunction10@PEAXKPEAGKPEAKPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400455b0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045677`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400455d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004566f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400455d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004566f`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045661`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045661`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004568d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004568d`
- `RPCRT4!RpcImpersonateClient` at `0x1400455ea`
- `RPCRT4!RpcImpersonateClient` at `0x1400455ea`

## pseudocode

```c
__int64 __fastcall TFunction10<void *,unsigned long,unsigned short *,unsigned long,unsigned long *,unsigned long *,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 192);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 184))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152),
                *(_DWORD *)(a1 + 160),
                *(_QWORD *)(a1 + 168),
                *(_DWORD *)(a1 + 176));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 192), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400455b0  mov     [rsp+arg_8], rbx
0x1400455b5  push    rdi
0x1400455b6  sub     rsp, 60h
0x1400455ba  mov     rax, [rcx+0C0h]
0x1400455c1  mov     rbx, rcx
0x1400455c4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400455ca  mov     [rsp+68h+Reply], 0
0x1400455d2  mov     rdi, [rax+20h]
0x1400455d6  mov     rdx, rdi; lpTlsValue
0x1400455d9  call    cs:__imp_TlsSetValue
0x1400455df  test    eax, eax
0x1400455e1  jz      loc_140045677
0x1400455e7  mov     rcx, rdi; BindingHandle
0x1400455ea  call    cs:__imp_RpcImpersonateClient
0x1400455f0  mov     [rsp+68h+Reply], eax
0x1400455f4  test    eax, eax
0x1400455f6  jnz     short loc_140045667
0x1400455f8  mov     eax, [rbx+0B0h]
0x1400455fe  mov     rcx, [rbx+0A8h]
0x140045605  mov     edx, [rbx+0A0h]
0x14004560b  mov     r9d, [rbx+80h]
0x140045612  mov     r8, [rbx+78h]
0x140045616  mov     [rsp+68h+var_20], eax
0x14004561a  mov     rax, [rbx+0B8h]
0x140045621  mov     [rsp+68h+var_28], rcx
0x140045626  mov     rcx, [rbx+68h]
0x14004562a  mov     [rsp+68h+var_30], edx
0x14004562e  mov     rdx, [rbx+98h]
0x140045635  mov     [rsp+68h+var_38], rdx
0x14004563a  mov     rdx, [rbx+90h]
0x140045641  mov     [rsp+68h+var_40], rdx
0x140045646  mov     rdx, [rbx+88h]
0x14004564d  mov     [rsp+68h+var_48], rdx
0x140045652  mov     edx, [rbx+70h]
0x140045655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004565a  mov     rcx, rdi; BindingHandle
0x14004565d  mov     [rsp+68h+Reply], eax
0x140045661  call    cs:__imp_RpcRevertToSelfEx
0x140045667  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004566d  xor     edx, edx; lpTlsValue
0x14004566f  call    cs:__imp_TlsSetValue
0x140045675  jmp     short loc_140045681
0x140045677  call    cs:__imp_GetLastError
0x14004567d  mov     [rsp+68h+Reply], eax
0x140045681  mov     rcx, [rbx+0C0h]; pAsync
0x140045688  lea     rdx, [rsp+68h+Reply]; Reply
0x14004568d  call    cs:__imp_RpcAsyncCompleteCall
0x140045693  mov     eax, [rsp+68h+Reply]
0x140045697  test    eax, eax
0x140045699  jle     short loc_1400456A3
0x14004569b  movzx   eax, ax
0x14004569e  or      eax, 80070000h
0x1400456a3  mov     rbx, [rsp+68h+arg_8]
0x1400456a8  add     rsp, 60h
0x1400456ac  pop     rdi
0x1400456ad  retn
```
