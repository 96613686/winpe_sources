# TFunction9<void *,ulong,ulong,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14004b400`
- end: `0x14004b514`
- name: `?Run@?$TFunction9@PEAXKKKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004b400`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b4d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b429`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b4c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b429`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b4c2`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b4ae`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b4ae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b4ec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b4ec`
- `RPCRT4!RpcImpersonateClient` at `0x14004b440`
- `RPCRT4!RpcImpersonateClient` at `0x14004b440`

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
0x14004b400  mov     [rsp+arg_8], rbx
0x14004b405  push    rdi
0x14004b406  sub     rsp, 50h
0x14004b40a  mov     rax, [rcx+0B0h]
0x14004b411  mov     rbx, rcx
0x14004b414  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b41a  mov     [rsp+58h+Reply], 0
0x14004b422  mov     rdi, [rax+20h]
0x14004b426  mov     rdx, rdi; lpTlsValue
0x14004b429  call    cs:__imp_TlsSetValue
0x14004b430  nop     dword ptr [rax+rax+00h]
0x14004b435  test    eax, eax
0x14004b437  jz      loc_14004B4D0
0x14004b43d  mov     rcx, rdi; BindingHandle
0x14004b440  call    cs:__imp_RpcImpersonateClient
0x14004b447  nop     dword ptr [rax+rax+00h]
0x14004b44c  mov     [rsp+58h+Reply], eax
0x14004b450  test    eax, eax
0x14004b452  jnz     short loc_14004B4BA
0x14004b454  mov     ecx, [rbx+0A0h]
0x14004b45a  mov     rdx, [rbx+98h]
0x14004b461  mov     r9d, [rbx+78h]
0x14004b465  mov     r8d, [rbx+74h]
0x14004b469  mov     rax, [rbx+0A8h]
0x14004b470  mov     [rsp+58h+var_18], ecx
0x14004b474  mov     rcx, [rbx+68h]
0x14004b478  mov     [rsp+58h+var_20], rdx
0x14004b47d  mov     rdx, [rbx+90h]
0x14004b484  mov     [rsp+58h+var_28], rdx
0x14004b489  mov     edx, [rbx+88h]
0x14004b48f  mov     [rsp+58h+var_30], edx
0x14004b493  mov     rdx, [rbx+80h]
0x14004b49a  mov     [rsp+58h+var_38], rdx
0x14004b49f  mov     edx, [rbx+70h]
0x14004b4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b4a7  mov     rcx, rdi; BindingHandle
0x14004b4aa  mov     [rsp+58h+Reply], eax
0x14004b4ae  call    cs:__imp_RpcRevertToSelfEx
0x14004b4b5  nop     dword ptr [rax+rax+00h]
0x14004b4ba  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b4c0  xor     edx, edx; lpTlsValue
0x14004b4c2  call    cs:__imp_TlsSetValue
0x14004b4c9  nop     dword ptr [rax+rax+00h]
0x14004b4ce  jmp     short loc_14004B4E0
0x14004b4d0  call    cs:__imp_GetLastError
0x14004b4d7  nop     dword ptr [rax+rax+00h]
0x14004b4dc  mov     [rsp+58h+Reply], eax
0x14004b4e0  mov     rcx, [rbx+0B0h]; pAsync
0x14004b4e7  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b4ec  call    cs:__imp_RpcAsyncCompleteCall
0x14004b4f3  nop     dword ptr [rax+rax+00h]
0x14004b4f8  mov     eax, [rsp+58h+Reply]
0x14004b4fc  test    eax, eax
0x14004b4fe  jle     short loc_14004B508
0x14004b500  movzx   eax, ax
0x14004b503  or      eax, 80070000h
0x14004b508  mov     rbx, [rsp+58h+arg_8]
0x14004b50d  add     rsp, 50h
0x14004b511  pop     rdi
0x14004b512  retn
```
