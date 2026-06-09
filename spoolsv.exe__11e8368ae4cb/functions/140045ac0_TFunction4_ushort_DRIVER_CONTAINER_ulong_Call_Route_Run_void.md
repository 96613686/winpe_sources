# TFunction4<ushort *,_DRIVER_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x140045ac0`
- end: `0x140045b74`
- name: `?Run@?$TFunction4@PEAGPEAU_DRIVER_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140045ac0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045b3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ae9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045b35`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045ae9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045b35`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045b27`
- `RPCRT4!RpcRevertToSelfEx` at `0x140045b27`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045b53`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045b53`
- `RPCRT4!RpcImpersonateClient` at `0x140045af6`
- `RPCRT4!RpcImpersonateClient` at `0x140045af6`

## pseudocode

```c
__int64 __fastcall TFunction4<unsigned short *,_DRIVER_CONTAINER *,unsigned long,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 136);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 128))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(unsigned int *)(a1 + 124));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 136), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140045ac0  mov     [rsp+arg_8], rbx
0x140045ac5  push    rdi
0x140045ac6  sub     rsp, 30h
0x140045aca  mov     rax, [rcx+88h]
0x140045ad1  mov     rbx, rcx
0x140045ad4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045ada  mov     [rsp+38h+Reply], 0
0x140045ae2  mov     rdi, [rax+20h]
0x140045ae6  mov     rdx, rdi; lpTlsValue
0x140045ae9  call    cs:__imp_TlsSetValue
0x140045aef  test    eax, eax
0x140045af1  jz      short loc_140045B3D
0x140045af3  mov     rcx, rdi; BindingHandle
0x140045af6  call    cs:__imp_RpcImpersonateClient
0x140045afc  mov     [rsp+38h+Reply], eax
0x140045b00  test    eax, eax
0x140045b02  jnz     short loc_140045B2D
0x140045b04  mov     r9d, [rbx+7Ch]
0x140045b08  mov     r8d, [rbx+78h]
0x140045b0c  mov     rdx, [rbx+70h]
0x140045b10  mov     rcx, [rbx+68h]
0x140045b14  mov     rax, [rbx+80h]
0x140045b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045b20  mov     rcx, rdi; BindingHandle
0x140045b23  mov     [rsp+38h+Reply], eax
0x140045b27  call    cs:__imp_RpcRevertToSelfEx
0x140045b2d  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045b33  xor     edx, edx; lpTlsValue
0x140045b35  call    cs:__imp_TlsSetValue
0x140045b3b  jmp     short loc_140045B47
0x140045b3d  call    cs:__imp_GetLastError
0x140045b43  mov     [rsp+38h+Reply], eax
0x140045b47  mov     rcx, [rbx+88h]; pAsync
0x140045b4e  lea     rdx, [rsp+38h+Reply]; Reply
0x140045b53  call    cs:__imp_RpcAsyncCompleteCall
0x140045b59  mov     eax, [rsp+38h+Reply]
0x140045b5d  test    eax, eax
0x140045b5f  jle     short loc_140045B69
0x140045b61  movzx   eax, ax
0x140045b64  or      eax, 80070000h
0x140045b69  mov     rbx, [rsp+38h+arg_8]
0x140045b6e  add     rsp, 30h
0x140045b72  pop     rdi
0x140045b73  retn
```
