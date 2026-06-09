# TFunction6<void *,ushort const *,ushort *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004a230`
- end: `0x14004a322`
- name: `?Run@?$TFunction6@PEAXPEBGPEAGKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a230`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a2de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a2de`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a259`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a2d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a259`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a2d0`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a2bc`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a2bc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a2fa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a2fa`
- `RPCRT4!RpcImpersonateClient` at `0x14004a26c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a26c`

## pseudocode

```c
__int64 __fastcall TFunction6<void *,unsigned short const *,unsigned short *,unsigned long,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 160);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 160), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004a230  mov     [rsp+arg_8], rbx
0x14004a235  push    rdi
0x14004a236  sub     rsp, 40h
0x14004a23a  mov     rax, [rcx+0A0h]
0x14004a241  mov     rbx, rcx
0x14004a244  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a24a  mov     [rsp+48h+Reply], 0
0x14004a252  mov     rdi, [rax+20h]
0x14004a256  mov     rdx, rdi; lpTlsValue
0x14004a259  call    cs:__imp_TlsSetValue
0x14004a260  nop     dword ptr [rax+rax+00h]
0x14004a265  test    eax, eax
0x14004a267  jz      short loc_14004A2DE
0x14004a269  mov     rcx, rdi; BindingHandle
0x14004a26c  call    cs:__imp_RpcImpersonateClient
0x14004a273  nop     dword ptr [rax+rax+00h]
0x14004a278  mov     [rsp+48h+Reply], eax
0x14004a27c  test    eax, eax
0x14004a27e  jnz     short loc_14004A2C8
0x14004a280  mov     edx, [rbx+90h]
0x14004a286  mov     r9d, [rbx+80h]
0x14004a28d  mov     r8, [rbx+78h]
0x14004a291  mov     rcx, [rbx+68h]
0x14004a295  mov     rax, [rbx+98h]
0x14004a29c  mov     [rsp+48h+var_20], edx
0x14004a2a0  mov     rdx, [rbx+88h]
0x14004a2a7  mov     [rsp+48h+var_28], rdx
0x14004a2ac  mov     rdx, [rbx+70h]
0x14004a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a2b5  mov     rcx, rdi; BindingHandle
0x14004a2b8  mov     [rsp+48h+Reply], eax
0x14004a2bc  call    cs:__imp_RpcRevertToSelfEx
0x14004a2c3  nop     dword ptr [rax+rax+00h]
0x14004a2c8  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a2ce  xor     edx, edx; lpTlsValue
0x14004a2d0  call    cs:__imp_TlsSetValue
0x14004a2d7  nop     dword ptr [rax+rax+00h]
0x14004a2dc  jmp     short loc_14004A2EE
0x14004a2de  call    cs:__imp_GetLastError
0x14004a2e5  nop     dword ptr [rax+rax+00h]
0x14004a2ea  mov     [rsp+48h+Reply], eax
0x14004a2ee  mov     rcx, [rbx+0A0h]; pAsync
0x14004a2f5  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a2fa  call    cs:__imp_RpcAsyncCompleteCall
0x14004a301  nop     dword ptr [rax+rax+00h]
0x14004a306  mov     eax, [rsp+48h+Reply]
0x14004a30a  test    eax, eax
0x14004a30c  jle     short loc_14004A316
0x14004a30e  movzx   eax, ax
0x14004a311  or      eax, 80070000h
0x14004a316  mov     rbx, [rsp+48h+arg_8]
0x14004a31b  add     rsp, 40h
0x14004a31f  pop     rdi
0x14004a320  retn
```
