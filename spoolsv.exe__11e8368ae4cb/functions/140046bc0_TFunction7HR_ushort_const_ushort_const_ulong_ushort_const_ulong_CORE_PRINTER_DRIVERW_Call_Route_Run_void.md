# TFunction7HR<ushort const *,ushort const *,ulong,ushort const *,ulong,_CORE_PRINTER_DRIVERW *,Call_Route>::Run(void)

- ea: `0x140046bc0`
- end: `0x140046c96`
- name: `?Run@?$TFunction7HR@PEBGPEBGKPEBGKPEAU_CORE_PRINTER_DRIVERW@@W4Call_Route@@@@UEAAJXZ`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140046bc0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046be9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046c64`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046be9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046c64`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046c46`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046c46`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046c81`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046c81`
- `RPCRT4!RpcImpersonateClient` at `0x140046bf6`
- `RPCRT4!RpcImpersonateClient` at `0x140046bf6`

## pseudocode

```c
__int64 __fastcall TFunction7HR<unsigned short const *,unsigned short const *,unsigned long,unsigned short const *,unsigned long,_CORE_PRINTER_DRIVERW *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    v5 = RpcImpersonateClient(v3);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      Reply = v5;
    }
    else
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 152));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 168), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x140046bc0  mov     [rsp+arg_8], rbx
0x140046bc5  push    rdi
0x140046bc6  sub     rsp, 40h
0x140046bca  mov     rax, [rcx+0A8h]
0x140046bd1  mov     rbx, rcx
0x140046bd4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046bda  mov     [rsp+48h+Reply], 0
0x140046be2  mov     rdi, [rax+20h]
0x140046be6  mov     rdx, rdi; lpTlsValue
0x140046be9  call    cs:__imp_TlsSetValue
0x140046bef  test    eax, eax
0x140046bf1  jz      short loc_140046C6C
0x140046bf3  mov     rcx, rdi; BindingHandle
0x140046bf6  call    cs:__imp_RpcImpersonateClient
0x140046bfc  test    eax, eax
0x140046bfe  jnz     short loc_140046C4E
0x140046c00  mov     edx, [rbx+98h]
0x140046c06  mov     r9, [rbx+80h]
0x140046c0d  mov     r8d, [rbx+78h]
0x140046c11  mov     rcx, [rbx+68h]
0x140046c15  mov     rax, [rbx+0A0h]
0x140046c1c  mov     [rsp+48h+var_18], edx
0x140046c20  mov     rdx, [rbx+90h]
0x140046c27  mov     [rsp+48h+var_20], rdx
0x140046c2c  mov     edx, [rbx+88h]
0x140046c32  mov     [rsp+48h+var_28], edx
0x140046c36  mov     rdx, [rbx+70h]
0x140046c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c3f  mov     rcx, rdi; BindingHandle
0x140046c42  mov     [rsp+48h+Reply], eax
0x140046c46  call    cs:__imp_RpcRevertToSelfEx
0x140046c4c  jmp     short loc_140046C5C
0x140046c4e  jle     short loc_140046C58
0x140046c50  movzx   eax, ax
0x140046c53  or      eax, 80070000h
0x140046c58  mov     [rsp+48h+Reply], eax
0x140046c5c  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046c62  xor     edx, edx; lpTlsValue
0x140046c64  call    cs:__imp_TlsSetValue
0x140046c6a  jmp     short loc_140046C75
0x140046c6c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140046c71  mov     [rsp+48h+Reply], eax
0x140046c75  mov     rcx, [rbx+0A8h]; pAsync
0x140046c7c  lea     rdx, [rsp+48h+Reply]; Reply
0x140046c81  call    cs:__imp_RpcAsyncCompleteCall
0x140046c87  mov     eax, [rsp+48h+Reply]
0x140046c8b  mov     rbx, [rsp+48h+arg_8]
0x140046c90  add     rsp, 40h
0x140046c94  pop     rdi
0x140046c95  retn
```
