# TFunction6<void *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x140046150`
- end: `0x14004621b`
- name: `?Run@?$TFunction6@PEAXPEAU_PRINTER_CONTAINER@@PEAU_DEVMODE_CONTAINER@@PEAU_SECURITY_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046150`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400461e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400461e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046179`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400461dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046179`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400461dc`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400461ce`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400461ce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400461fa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400461fa`
- `RPCRT4!RpcImpersonateClient` at `0x140046186`
- `RPCRT4!RpcImpersonateClient` at `0x140046186`

## pseudocode

```c
__int64 __fastcall TFunction6<void *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,unsigned long,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 144))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 152), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140046150  mov     [rsp+arg_8], rbx
0x140046155  push    rdi
0x140046156  sub     rsp, 40h
0x14004615a  mov     rax, [rcx+98h]
0x140046161  mov     rbx, rcx
0x140046164  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004616a  mov     [rsp+48h+Reply], 0
0x140046172  mov     rdi, [rax+20h]
0x140046176  mov     rdx, rdi; lpTlsValue
0x140046179  call    cs:__imp_TlsSetValue
0x14004617f  test    eax, eax
0x140046181  jz      short loc_1400461E4
0x140046183  mov     rcx, rdi; BindingHandle
0x140046186  call    cs:__imp_RpcImpersonateClient
0x14004618c  mov     [rsp+48h+Reply], eax
0x140046190  test    eax, eax
0x140046192  jnz     short loc_1400461D4
0x140046194  mov     edx, [rbx+8Ch]
0x14004619a  mov     r9, [rbx+80h]
0x1400461a1  mov     r8, [rbx+78h]
0x1400461a5  mov     rcx, [rbx+68h]
0x1400461a9  mov     rax, [rbx+90h]
0x1400461b0  mov     [rsp+48h+var_20], edx
0x1400461b4  mov     edx, [rbx+88h]
0x1400461ba  mov     [rsp+48h+var_28], edx
0x1400461be  mov     rdx, [rbx+70h]
0x1400461c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400461c7  mov     rcx, rdi; BindingHandle
0x1400461ca  mov     [rsp+48h+Reply], eax
0x1400461ce  call    cs:__imp_RpcRevertToSelfEx
0x1400461d4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400461da  xor     edx, edx; lpTlsValue
0x1400461dc  call    cs:__imp_TlsSetValue
0x1400461e2  jmp     short loc_1400461EE
0x1400461e4  call    cs:__imp_GetLastError
0x1400461ea  mov     [rsp+48h+Reply], eax
0x1400461ee  mov     rcx, [rbx+98h]; pAsync
0x1400461f5  lea     rdx, [rsp+48h+Reply]; Reply
0x1400461fa  call    cs:__imp_RpcAsyncCompleteCall
0x140046200  mov     eax, [rsp+48h+Reply]
0x140046204  test    eax, eax
0x140046206  jle     short loc_140046210
0x140046208  movzx   eax, ax
0x14004620b  or      eax, 80070000h
0x140046210  mov     rbx, [rsp+48h+arg_8]
0x140046215  add     rsp, 40h
0x140046219  pop     rdi
0x14004621a  retn
```
