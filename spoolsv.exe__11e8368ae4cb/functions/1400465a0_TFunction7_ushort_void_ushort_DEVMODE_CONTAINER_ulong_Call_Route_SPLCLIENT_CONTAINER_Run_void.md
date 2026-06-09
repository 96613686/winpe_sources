# TFunction7<ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *>::Run(void)

- ea: `0x1400465a0`
- end: `0x140046677`
- name: `?Run@?$TFunction7@PEAGPEAPEAXPEAGPEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@UEAAJXZ`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400465a0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046640`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400465c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046638`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400465c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046638`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004662a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004662a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046656`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046656`
- `RPCRT4!RpcImpersonateClient` at `0x1400465d6`
- `RPCRT4!RpcImpersonateClient` at `0x1400465d6`

## pseudocode

```c
__int64 __fastcall TFunction7<unsigned short *,void * *,unsigned short *,_DEVMODE_CONTAINER *,unsigned long,enum Call_Route,_SPLCLIENT_CONTAINER *>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140),
                *(_QWORD *)(a1 + 144));
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
0x1400465a0  mov     [rsp+arg_8], rbx
0x1400465a5  push    rdi
0x1400465a6  sub     rsp, 40h
0x1400465aa  mov     rax, [rcx+0A0h]
0x1400465b1  mov     rbx, rcx
0x1400465b4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400465ba  mov     [rsp+48h+Reply], 0
0x1400465c2  mov     rdi, [rax+20h]
0x1400465c6  mov     rdx, rdi; lpTlsValue
0x1400465c9  call    cs:__imp_TlsSetValue
0x1400465cf  test    eax, eax
0x1400465d1  jz      short loc_140046640
0x1400465d3  mov     rcx, rdi; BindingHandle
0x1400465d6  call    cs:__imp_RpcImpersonateClient
0x1400465dc  mov     [rsp+48h+Reply], eax
0x1400465e0  test    eax, eax
0x1400465e2  jnz     short loc_140046630
0x1400465e4  mov     rdx, [rbx+90h]
0x1400465eb  mov     r9, [rbx+80h]
0x1400465f2  mov     r8, [rbx+78h]
0x1400465f6  mov     rcx, [rbx+68h]
0x1400465fa  mov     rax, [rbx+98h]
0x140046601  mov     [rsp+48h+var_18], rdx
0x140046606  mov     edx, [rbx+8Ch]
0x14004660c  mov     [rsp+48h+var_20], edx
0x140046610  mov     edx, [rbx+88h]
0x140046616  mov     [rsp+48h+var_28], edx
0x14004661a  mov     rdx, [rbx+70h]
0x14004661e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046623  mov     rcx, rdi; BindingHandle
0x140046626  mov     [rsp+48h+Reply], eax
0x14004662a  call    cs:__imp_RpcRevertToSelfEx
0x140046630  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046636  xor     edx, edx; lpTlsValue
0x140046638  call    cs:__imp_TlsSetValue
0x14004663e  jmp     short loc_14004664A
0x140046640  call    cs:__imp_GetLastError
0x140046646  mov     [rsp+48h+Reply], eax
0x14004664a  mov     rcx, [rbx+0A0h]; pAsync
0x140046651  lea     rdx, [rsp+48h+Reply]; Reply
0x140046656  call    cs:__imp_RpcAsyncCompleteCall
0x14004665c  mov     eax, [rsp+48h+Reply]
0x140046660  test    eax, eax
0x140046662  jle     short loc_14004666C
0x140046664  movzx   eax, ax
0x140046667  or      eax, 80070000h
0x14004666c  mov     rbx, [rsp+48h+arg_8]
0x140046671  add     rsp, 40h
0x140046675  pop     rdi
0x140046676  retn
```
