# TFunction7<void *,uchar *,ulong,uchar *,ulong,ulong,Call_Route>::Run(void)

- ea: `0x140046840`
- end: `0x140046915`
- name: `?Run@?$TFunction7@PEAXPEAEKPEAEKKW4Call_Route@@@@UEAAJXZ`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046840`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400468de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400468de`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046869`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400468d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046869`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400468d6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400468c8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400468c8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400468f4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400468f4`
- `RPCRT4!RpcImpersonateClient` at `0x140046876`
- `RPCRT4!RpcImpersonateClient` at `0x140046876`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned char *,unsigned long,unsigned char *,unsigned long,unsigned long,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 140),
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
0x140046840  mov     [rsp+arg_8], rbx
0x140046845  push    rdi
0x140046846  sub     rsp, 40h
0x14004684a  mov     rax, [rcx+0A0h]
0x140046851  mov     rbx, rcx
0x140046854  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004685a  mov     [rsp+48h+Reply], 0
0x140046862  mov     rdi, [rax+20h]
0x140046866  mov     rdx, rdi; lpTlsValue
0x140046869  call    cs:__imp_TlsSetValue
0x14004686f  test    eax, eax
0x140046871  jz      short loc_1400468DE
0x140046873  mov     rcx, rdi; BindingHandle
0x140046876  call    cs:__imp_RpcImpersonateClient
0x14004687c  mov     [rsp+48h+Reply], eax
0x140046880  test    eax, eax
0x140046882  jnz     short loc_1400468CE
0x140046884  mov     edx, [rbx+90h]
0x14004688a  mov     r9, [rbx+80h]
0x140046891  mov     r8d, [rbx+78h]
0x140046895  mov     rcx, [rbx+68h]
0x140046899  mov     rax, [rbx+98h]
0x1400468a0  mov     [rsp+48h+var_18], edx
0x1400468a4  mov     edx, [rbx+8Ch]
0x1400468aa  mov     [rsp+48h+var_20], edx
0x1400468ae  mov     edx, [rbx+88h]
0x1400468b4  mov     [rsp+48h+var_28], edx
0x1400468b8  mov     rdx, [rbx+70h]
0x1400468bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400468c1  mov     rcx, rdi; BindingHandle
0x1400468c4  mov     [rsp+48h+Reply], eax
0x1400468c8  call    cs:__imp_RpcRevertToSelfEx
0x1400468ce  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400468d4  xor     edx, edx; lpTlsValue
0x1400468d6  call    cs:__imp_TlsSetValue
0x1400468dc  jmp     short loc_1400468E8
0x1400468de  call    cs:__imp_GetLastError
0x1400468e4  mov     [rsp+48h+Reply], eax
0x1400468e8  mov     rcx, [rbx+0A0h]; pAsync
0x1400468ef  lea     rdx, [rsp+48h+Reply]; Reply
0x1400468f4  call    cs:__imp_RpcAsyncCompleteCall
0x1400468fa  mov     eax, [rsp+48h+Reply]
0x1400468fe  test    eax, eax
0x140046900  jle     short loc_14004690A
0x140046902  movzx   eax, ax
0x140046905  or      eax, 80070000h
0x14004690a  mov     rbx, [rsp+48h+arg_8]
0x14004690f  add     rsp, 40h
0x140046913  pop     rdi
0x140046914  retn
```
