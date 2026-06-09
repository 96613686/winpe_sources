# TFunction7<ushort *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,void * *,Call_Route,_SPLCLIENT_CONTAINER *>::Run(void)

- ea: `0x140046680`
- end: `0x140046759`
- name: `?Run@?$TFunction7@PEAGPEAU_PRINTER_CONTAINER@@PEAU_DEVMODE_CONTAINER@@PEAU_SECURITY_CONTAINER@@PEAPEAXW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@UEAAJXZ`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046680`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046722`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400466a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004671a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400466a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004671a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004670c`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004670c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046738`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046738`
- `RPCRT4!RpcImpersonateClient` at `0x1400466b6`
- `RPCRT4!RpcImpersonateClient` at `0x1400466b6`

## pseudocode

```c
__int64 __fastcall TFunction7<unsigned short *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,void * *,enum Call_Route,_SPLCLIENT_CONTAINER *>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152));
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
0x140046680  mov     [rsp+arg_8], rbx
0x140046685  push    rdi
0x140046686  sub     rsp, 40h
0x14004668a  mov     rax, [rcx+0A8h]
0x140046691  mov     rbx, rcx
0x140046694  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004669a  mov     [rsp+48h+Reply], 0
0x1400466a2  mov     rdi, [rax+20h]
0x1400466a6  mov     rdx, rdi; lpTlsValue
0x1400466a9  call    cs:__imp_TlsSetValue
0x1400466af  test    eax, eax
0x1400466b1  jz      short loc_140046722
0x1400466b3  mov     rcx, rdi; BindingHandle
0x1400466b6  call    cs:__imp_RpcImpersonateClient
0x1400466bc  mov     [rsp+48h+Reply], eax
0x1400466c0  test    eax, eax
0x1400466c2  jnz     short loc_140046712
0x1400466c4  mov     rdx, [rbx+98h]
0x1400466cb  mov     r9, [rbx+80h]
0x1400466d2  mov     r8, [rbx+78h]
0x1400466d6  mov     rcx, [rbx+68h]
0x1400466da  mov     rax, [rbx+0A0h]
0x1400466e1  mov     [rsp+48h+var_18], rdx
0x1400466e6  mov     edx, [rbx+90h]
0x1400466ec  mov     [rsp+48h+var_20], edx
0x1400466f0  mov     rdx, [rbx+88h]
0x1400466f7  mov     [rsp+48h+var_28], rdx
0x1400466fc  mov     rdx, [rbx+70h]
0x140046700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046705  mov     rcx, rdi; BindingHandle
0x140046708  mov     [rsp+48h+Reply], eax
0x14004670c  call    cs:__imp_RpcRevertToSelfEx
0x140046712  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046718  xor     edx, edx; lpTlsValue
0x14004671a  call    cs:__imp_TlsSetValue
0x140046720  jmp     short loc_14004672C
0x140046722  call    cs:__imp_GetLastError
0x140046728  mov     [rsp+48h+Reply], eax
0x14004672c  mov     rcx, [rbx+0A8h]; pAsync
0x140046733  lea     rdx, [rsp+48h+Reply]; Reply
0x140046738  call    cs:__imp_RpcAsyncCompleteCall
0x14004673e  mov     eax, [rsp+48h+Reply]
0x140046742  test    eax, eax
0x140046744  jle     short loc_14004674E
0x140046746  movzx   eax, ax
0x140046749  or      eax, 80070000h
0x14004674e  mov     rbx, [rsp+48h+arg_8]
0x140046753  add     rsp, 40h
0x140046757  pop     rdi
0x140046758  retn
```
