# TFunction8<ulong,ushort *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14000d8d0`
- end: `0x14000d9e0`
- name: `?Run@?$TFunction8@KPEAGKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000d8d0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d909`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000d8f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000d9c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000d8f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000d9c2`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000d9ae`
- `RPCRT4!RpcRevertToSelfEx` at `0x14000d9ae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d925`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d925`
- `RPCRT4!RpcImpersonateClient` at `0x14000d94c`
- `RPCRT4!RpcImpersonateClient` at `0x14000d94c`

## pseudocode

```c
__int64 __fastcall TFunction8<unsigned long,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 160))(
                *(unsigned int *)(a1 + 100),
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_DWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
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
0x14000d8d0  mov     [rsp+arg_8], rbx
0x14000d8d5  push    rdi
0x14000d8d6  sub     rsp, 50h
0x14000d8da  mov     rax, [rcx+0A8h]
0x14000d8e1  mov     rbx, rcx
0x14000d8e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000d8ea  mov     [rsp+58h+Reply], 0
0x14000d8f2  mov     rdi, [rax+20h]
0x14000d8f6  mov     rdx, rdi; lpTlsValue
0x14000d8f9  call    cs:__imp_TlsSetValue
0x14000d900  nop     dword ptr [rax+rax+00h]
0x14000d905  test    eax, eax
0x14000d907  jnz     short loc_14000D949
0x14000d909  call    cs:__imp_GetLastError
0x14000d910  nop     dword ptr [rax+rax+00h]
0x14000d915  mov     [rsp+58h+Reply], eax
0x14000d919  mov     rcx, [rbx+0A8h]; pAsync
0x14000d920  lea     rdx, [rsp+58h+Reply]; Reply
0x14000d925  call    cs:__imp_RpcAsyncCompleteCall
0x14000d92c  nop     dword ptr [rax+rax+00h]
0x14000d931  mov     eax, [rsp+58h+Reply]
0x14000d935  test    eax, eax
0x14000d937  jg      loc_14000D9D3
0x14000d93d  mov     rbx, [rsp+58h+arg_8]
0x14000d942  add     rsp, 50h
0x14000d946  pop     rdi
0x14000d947  retn
0x14000d949  mov     rcx, rdi; BindingHandle
0x14000d94c  call    cs:__imp_RpcImpersonateClient
0x14000d953  nop     dword ptr [rax+rax+00h]
0x14000d958  mov     [rsp+58h+Reply], eax
0x14000d95c  test    eax, eax
0x14000d95e  jnz     short loc_14000D9BA
0x14000d960  mov     edx, [rbx+98h]
0x14000d966  mov     r9, [rbx+78h]
0x14000d96a  mov     r8d, [rbx+70h]
0x14000d96e  mov     ecx, [rbx+64h]
0x14000d971  mov     rax, [rbx+0A0h]
0x14000d978  mov     [rsp+58h+var_20], edx
0x14000d97c  mov     rdx, [rbx+90h]
0x14000d983  mov     [rsp+58h+var_28], rdx
0x14000d988  mov     rdx, [rbx+88h]
0x14000d98f  mov     [rsp+58h+var_30], rdx
0x14000d994  mov     edx, [rbx+80h]
0x14000d99a  mov     [rsp+58h+var_38], edx
0x14000d99e  mov     rdx, [rbx+68h]
0x14000d9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9a7  mov     rcx, rdi; BindingHandle
0x14000d9aa  mov     [rsp+58h+Reply], eax
0x14000d9ae  call    cs:__imp_RpcRevertToSelfEx
0x14000d9b5  nop     dword ptr [rax+rax+00h]
0x14000d9ba  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000d9c0  xor     edx, edx; lpTlsValue
0x14000d9c2  call    cs:__imp_TlsSetValue
0x14000d9c9  nop     dword ptr [rax+rax+00h]
0x14000d9ce  jmp     loc_14000D919
0x14000d9d3  movzx   eax, ax
0x14000d9d6  or      eax, 80070000h
0x14000d9db  jmp     loc_14000D93D
```
