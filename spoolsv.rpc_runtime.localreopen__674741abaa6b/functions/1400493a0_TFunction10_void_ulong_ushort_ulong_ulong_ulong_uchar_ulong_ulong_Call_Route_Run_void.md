# TFunction10<void *,ulong,ushort *,ulong,ulong *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x1400493a0`
- end: `0x1400494c3`
- name: `?Run@?$TFunction10@PEAXKPEAGKPEAKPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400493a0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004947f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004947f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400493c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049471`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400493c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049471`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004945d`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004945d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004949b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004949b`
- `RPCRT4!RpcImpersonateClient` at `0x1400493e0`
- `RPCRT4!RpcImpersonateClient` at `0x1400493e0`

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
0x1400493a0  mov     [rsp+arg_8], rbx
0x1400493a5  push    rdi
0x1400493a6  sub     rsp, 60h
0x1400493aa  mov     rax, [rcx+0C0h]
0x1400493b1  mov     rbx, rcx
0x1400493b4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400493ba  mov     [rsp+68h+Reply], 0
0x1400493c2  mov     rdi, [rax+20h]
0x1400493c6  mov     rdx, rdi; lpTlsValue
0x1400493c9  call    cs:__imp_TlsSetValue
0x1400493d0  nop     dword ptr [rax+rax+00h]
0x1400493d5  test    eax, eax
0x1400493d7  jz      loc_14004947F
0x1400493dd  mov     rcx, rdi; BindingHandle
0x1400493e0  call    cs:__imp_RpcImpersonateClient
0x1400493e7  nop     dword ptr [rax+rax+00h]
0x1400493ec  mov     [rsp+68h+Reply], eax
0x1400493f0  test    eax, eax
0x1400493f2  jnz     short loc_140049469
0x1400493f4  mov     eax, [rbx+0B0h]
0x1400493fa  mov     rcx, [rbx+0A8h]
0x140049401  mov     edx, [rbx+0A0h]
0x140049407  mov     r9d, [rbx+80h]
0x14004940e  mov     r8, [rbx+78h]
0x140049412  mov     [rsp+68h+var_20], eax
0x140049416  mov     rax, [rbx+0B8h]
0x14004941d  mov     [rsp+68h+var_28], rcx
0x140049422  mov     rcx, [rbx+68h]
0x140049426  mov     [rsp+68h+var_30], edx
0x14004942a  mov     rdx, [rbx+98h]
0x140049431  mov     [rsp+68h+var_38], rdx
0x140049436  mov     rdx, [rbx+90h]
0x14004943d  mov     [rsp+68h+var_40], rdx
0x140049442  mov     rdx, [rbx+88h]
0x140049449  mov     [rsp+68h+var_48], rdx
0x14004944e  mov     edx, [rbx+70h]
0x140049451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049456  mov     rcx, rdi; BindingHandle
0x140049459  mov     [rsp+68h+Reply], eax
0x14004945d  call    cs:__imp_RpcRevertToSelfEx
0x140049464  nop     dword ptr [rax+rax+00h]
0x140049469  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004946f  xor     edx, edx; lpTlsValue
0x140049471  call    cs:__imp_TlsSetValue
0x140049478  nop     dword ptr [rax+rax+00h]
0x14004947d  jmp     short loc_14004948F
0x14004947f  call    cs:__imp_GetLastError
0x140049486  nop     dword ptr [rax+rax+00h]
0x14004948b  mov     [rsp+68h+Reply], eax
0x14004948f  mov     rcx, [rbx+0C0h]; pAsync
0x140049496  lea     rdx, [rsp+68h+Reply]; Reply
0x14004949b  call    cs:__imp_RpcAsyncCompleteCall
0x1400494a2  nop     dword ptr [rax+rax+00h]
0x1400494a7  mov     eax, [rsp+68h+Reply]
0x1400494ab  test    eax, eax
0x1400494ad  jle     short loc_1400494B7
0x1400494af  movzx   eax, ax
0x1400494b2  or      eax, 80070000h
0x1400494b7  mov     rbx, [rsp+68h+arg_8]
0x1400494bc  add     rsp, 60h
0x1400494c0  pop     rdi
0x1400494c1  retn
```
