# TFunction6HR<ushort const *,ushort const *,ushort const *,ushort const *,ulong,Call_Route>::Run(void)

- ea: `0x140046310`
- end: `0x1400463da`
- name: `?Run@?$TFunction6HR@PEBGPEBGPEBGPEBGKW4Call_Route@@@@UEAAJXZ`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140046310`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046339`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400463a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046339`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400463a8`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004638a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004638a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400463c5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400463c5`
- `RPCRT4!RpcImpersonateClient` at `0x140046346`
- `RPCRT4!RpcImpersonateClient` at `0x140046346`

## pseudocode

```c
__int64 __fastcall TFunction6HR<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned long,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
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
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 152), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x140046310  mov     [rsp+arg_8], rbx
0x140046315  push    rdi
0x140046316  sub     rsp, 40h
0x14004631a  mov     rax, [rcx+98h]
0x140046321  mov     rbx, rcx
0x140046324  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004632a  mov     [rsp+48h+Reply], 0
0x140046332  mov     rdi, [rax+20h]
0x140046336  mov     rdx, rdi; lpTlsValue
0x140046339  call    cs:__imp_TlsSetValue
0x14004633f  test    eax, eax
0x140046341  jz      short loc_1400463B0
0x140046343  mov     rcx, rdi; BindingHandle
0x140046346  call    cs:__imp_RpcImpersonateClient
0x14004634c  test    eax, eax
0x14004634e  jnz     short loc_140046392
0x140046350  mov     edx, [rbx+8Ch]
0x140046356  mov     r9, [rbx+80h]
0x14004635d  mov     r8, [rbx+78h]
0x140046361  mov     rcx, [rbx+68h]
0x140046365  mov     rax, [rbx+90h]
0x14004636c  mov     [rsp+48h+var_20], edx
0x140046370  mov     edx, [rbx+88h]
0x140046376  mov     [rsp+48h+var_28], edx
0x14004637a  mov     rdx, [rbx+70h]
0x14004637e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046383  mov     rcx, rdi; BindingHandle
0x140046386  mov     [rsp+48h+Reply], eax
0x14004638a  call    cs:__imp_RpcRevertToSelfEx
0x140046390  jmp     short loc_1400463A0
0x140046392  jle     short loc_14004639C
0x140046394  movzx   eax, ax
0x140046397  or      eax, 80070000h
0x14004639c  mov     [rsp+48h+Reply], eax
0x1400463a0  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400463a6  xor     edx, edx; lpTlsValue
0x1400463a8  call    cs:__imp_TlsSetValue
0x1400463ae  jmp     short loc_1400463B9
0x1400463b0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400463b5  mov     [rsp+48h+Reply], eax
0x1400463b9  mov     rcx, [rbx+98h]; pAsync
0x1400463c0  lea     rdx, [rsp+48h+Reply]; Reply
0x1400463c5  call    cs:__imp_RpcAsyncCompleteCall
0x1400463cb  mov     eax, [rsp+48h+Reply]
0x1400463cf  mov     rbx, [rsp+48h+arg_8]
0x1400463d4  add     rsp, 40h
0x1400463d8  pop     rdi
0x1400463d9  retn
```
