# TFunction7<void *,ushort const *,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x14004ab70`
- end: `0x14004ac72`
- name: `?Run@?$TFunction7@PEAXPEBGPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004ab70`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ac2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ac2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ab99`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ac20`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ab99`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ac20`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ac0c`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ac0c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ac4a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ac4a`
- `RPCRT4!RpcImpersonateClient` at `0x14004abb0`
- `RPCRT4!RpcImpersonateClient` at `0x14004abb0`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned short const *,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
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
0x14004ab70  mov     [rsp+arg_8], rbx
0x14004ab75  push    rdi
0x14004ab76  sub     rsp, 40h
0x14004ab7a  mov     rax, [rcx+0A8h]
0x14004ab81  mov     rbx, rcx
0x14004ab84  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ab8a  mov     [rsp+48h+Reply], 0
0x14004ab92  mov     rdi, [rax+20h]
0x14004ab96  mov     rdx, rdi; lpTlsValue
0x14004ab99  call    cs:__imp_TlsSetValue
0x14004aba0  nop     dword ptr [rax+rax+00h]
0x14004aba5  test    eax, eax
0x14004aba7  jz      loc_14004AC2E
0x14004abad  mov     rcx, rdi; BindingHandle
0x14004abb0  call    cs:__imp_RpcImpersonateClient
0x14004abb7  nop     dword ptr [rax+rax+00h]
0x14004abbc  mov     [rsp+48h+Reply], eax
0x14004abc0  test    eax, eax
0x14004abc2  jnz     short loc_14004AC18
0x14004abc4  mov     edx, [rbx+98h]
0x14004abca  mov     r9d, [rbx+80h]
0x14004abd1  mov     r8, [rbx+78h]
0x14004abd5  mov     rcx, [rbx+68h]
0x14004abd9  mov     rax, [rbx+0A0h]
0x14004abe0  mov     [rsp+48h+var_18], edx
0x14004abe4  mov     rdx, [rbx+90h]
0x14004abeb  mov     [rsp+48h+var_20], rdx
0x14004abf0  mov     rdx, [rbx+88h]
0x14004abf7  mov     [rsp+48h+var_28], rdx
0x14004abfc  mov     rdx, [rbx+70h]
0x14004ac00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ac05  mov     rcx, rdi; BindingHandle
0x14004ac08  mov     [rsp+48h+Reply], eax
0x14004ac0c  call    cs:__imp_RpcRevertToSelfEx
0x14004ac13  nop     dword ptr [rax+rax+00h]
0x14004ac18  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ac1e  xor     edx, edx; lpTlsValue
0x14004ac20  call    cs:__imp_TlsSetValue
0x14004ac27  nop     dword ptr [rax+rax+00h]
0x14004ac2c  jmp     short loc_14004AC3E
0x14004ac2e  call    cs:__imp_GetLastError
0x14004ac35  nop     dword ptr [rax+rax+00h]
0x14004ac3a  mov     [rsp+48h+Reply], eax
0x14004ac3e  mov     rcx, [rbx+0A8h]; pAsync
0x14004ac45  lea     rdx, [rsp+48h+Reply]; Reply
0x14004ac4a  call    cs:__imp_RpcAsyncCompleteCall
0x14004ac51  nop     dword ptr [rax+rax+00h]
0x14004ac56  mov     eax, [rsp+48h+Reply]
0x14004ac5a  test    eax, eax
0x14004ac5c  jle     short loc_14004AC66
0x14004ac5e  movzx   eax, ax
0x14004ac61  or      eax, 80070000h
0x14004ac66  mov     rbx, [rsp+48h+arg_8]
0x14004ac6b  add     rsp, 40h
0x14004ac6f  pop     rdi
0x14004ac70  retn
```
