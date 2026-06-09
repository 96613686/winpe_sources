# TFunction6<void *,ushort const *,ushort *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140046230`
- end: `0x1400462fd`
- name: `?Run@?$TFunction6@PEAXPEBGPEAGKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046230`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400462c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400462c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046259`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400462be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046259`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400462be`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400462b0`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400462b0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400462dc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400462dc`
- `RPCRT4!RpcImpersonateClient` at `0x140046266`
- `RPCRT4!RpcImpersonateClient` at `0x140046266`

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
0x140046230  mov     [rsp+arg_8], rbx
0x140046235  push    rdi
0x140046236  sub     rsp, 40h
0x14004623a  mov     rax, [rcx+0A0h]
0x140046241  mov     rbx, rcx
0x140046244  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004624a  mov     [rsp+48h+Reply], 0
0x140046252  mov     rdi, [rax+20h]
0x140046256  mov     rdx, rdi; lpTlsValue
0x140046259  call    cs:__imp_TlsSetValue
0x14004625f  test    eax, eax
0x140046261  jz      short loc_1400462C6
0x140046263  mov     rcx, rdi; BindingHandle
0x140046266  call    cs:__imp_RpcImpersonateClient
0x14004626c  mov     [rsp+48h+Reply], eax
0x140046270  test    eax, eax
0x140046272  jnz     short loc_1400462B6
0x140046274  mov     edx, [rbx+90h]
0x14004627a  mov     r9d, [rbx+80h]
0x140046281  mov     r8, [rbx+78h]
0x140046285  mov     rcx, [rbx+68h]
0x140046289  mov     rax, [rbx+98h]
0x140046290  mov     [rsp+48h+var_20], edx
0x140046294  mov     rdx, [rbx+88h]
0x14004629b  mov     [rsp+48h+var_28], rdx
0x1400462a0  mov     rdx, [rbx+70h]
0x1400462a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400462a9  mov     rcx, rdi; BindingHandle
0x1400462ac  mov     [rsp+48h+Reply], eax
0x1400462b0  call    cs:__imp_RpcRevertToSelfEx
0x1400462b6  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400462bc  xor     edx, edx; lpTlsValue
0x1400462be  call    cs:__imp_TlsSetValue
0x1400462c4  jmp     short loc_1400462D0
0x1400462c6  call    cs:__imp_GetLastError
0x1400462cc  mov     [rsp+48h+Reply], eax
0x1400462d0  mov     rcx, [rbx+0A0h]; pAsync
0x1400462d7  lea     rdx, [rsp+48h+Reply]; Reply
0x1400462dc  call    cs:__imp_RpcAsyncCompleteCall
0x1400462e2  mov     eax, [rsp+48h+Reply]
0x1400462e6  test    eax, eax
0x1400462e8  jle     short loc_1400462F2
0x1400462ea  movzx   eax, ax
0x1400462ed  or      eax, 80070000h
0x1400462f2  mov     rbx, [rsp+48h+arg_8]
0x1400462f7  add     rsp, 40h
0x1400462fb  pop     rdi
0x1400462fc  retn
```
