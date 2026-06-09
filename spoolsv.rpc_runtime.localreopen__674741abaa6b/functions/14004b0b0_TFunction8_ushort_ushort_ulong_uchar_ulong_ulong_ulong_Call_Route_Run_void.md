# TFunction8<ushort *,ushort *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14004b0b0`
- end: `0x14004b1bc`
- name: `?Run@?$TFunction8@PEAGPEAGKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004b0b0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b178`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b0d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b16a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b0d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b16a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b156`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b156`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b194`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b194`
- `RPCRT4!RpcImpersonateClient` at `0x14004b0f0`
- `RPCRT4!RpcImpersonateClient` at `0x14004b0f0`

## pseudocode

```c
__int64 __fastcall TFunction8<unsigned short *,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 168))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
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
0x14004b0b0  mov     [rsp+arg_8], rbx
0x14004b0b5  push    rdi
0x14004b0b6  sub     rsp, 50h
0x14004b0ba  mov     rax, [rcx+0B0h]
0x14004b0c1  mov     rbx, rcx
0x14004b0c4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b0ca  mov     [rsp+58h+Reply], 0
0x14004b0d2  mov     rdi, [rax+20h]
0x14004b0d6  mov     rdx, rdi; lpTlsValue
0x14004b0d9  call    cs:__imp_TlsSetValue
0x14004b0e0  nop     dword ptr [rax+rax+00h]
0x14004b0e5  test    eax, eax
0x14004b0e7  jz      loc_14004B178
0x14004b0ed  mov     rcx, rdi; BindingHandle
0x14004b0f0  call    cs:__imp_RpcImpersonateClient
0x14004b0f7  nop     dword ptr [rax+rax+00h]
0x14004b0fc  mov     [rsp+58h+Reply], eax
0x14004b100  test    eax, eax
0x14004b102  jnz     short loc_14004B162
0x14004b104  mov     edx, [rbx+0A0h]
0x14004b10a  mov     r9, [rbx+80h]
0x14004b111  mov     r8d, [rbx+78h]
0x14004b115  mov     rcx, [rbx+68h]
0x14004b119  mov     rax, [rbx+0A8h]
0x14004b120  mov     [rsp+58h+var_20], edx
0x14004b124  mov     rdx, [rbx+98h]
0x14004b12b  mov     [rsp+58h+var_28], rdx
0x14004b130  mov     rdx, [rbx+90h]
0x14004b137  mov     [rsp+58h+var_30], rdx
0x14004b13c  mov     edx, [rbx+88h]
0x14004b142  mov     [rsp+58h+var_38], edx
0x14004b146  mov     rdx, [rbx+70h]
0x14004b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b14f  mov     rcx, rdi; BindingHandle
0x14004b152  mov     [rsp+58h+Reply], eax
0x14004b156  call    cs:__imp_RpcRevertToSelfEx
0x14004b15d  nop     dword ptr [rax+rax+00h]
0x14004b162  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b168  xor     edx, edx; lpTlsValue
0x14004b16a  call    cs:__imp_TlsSetValue
0x14004b171  nop     dword ptr [rax+rax+00h]
0x14004b176  jmp     short loc_14004B188
0x14004b178  call    cs:__imp_GetLastError
0x14004b17f  nop     dword ptr [rax+rax+00h]
0x14004b184  mov     [rsp+58h+Reply], eax
0x14004b188  mov     rcx, [rbx+0B0h]; pAsync
0x14004b18f  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b194  call    cs:__imp_RpcAsyncCompleteCall
0x14004b19b  nop     dword ptr [rax+rax+00h]
0x14004b1a0  mov     eax, [rsp+58h+Reply]
0x14004b1a4  test    eax, eax
0x14004b1a6  jle     short loc_14004B1B0
0x14004b1a8  movzx   eax, ax
0x14004b1ab  or      eax, 80070000h
0x14004b1b0  mov     rbx, [rsp+58h+arg_8]
0x14004b1b5  add     rsp, 50h
0x14004b1b9  pop     rdi
0x14004b1ba  retn
```
