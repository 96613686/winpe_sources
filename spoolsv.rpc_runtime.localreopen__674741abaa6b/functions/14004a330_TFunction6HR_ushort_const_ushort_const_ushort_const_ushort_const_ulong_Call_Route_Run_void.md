# TFunction6HR<ushort const *,ushort const *,ushort const *,ushort const *,ulong,Call_Route>::Run(void)

- ea: `0x14004a330`
- end: `0x14004a419`
- name: `?Run@?$TFunction6HR@PEBGPEBGPEBGPEBGKW4Call_Route@@@@UEAAJXZ`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x14004a330`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a359`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a3da`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a359`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a3da`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a3b6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a3b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a3fd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a3fd`
- `RPCRT4!RpcImpersonateClient` at `0x14004a36c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a36c`

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
0x14004a330  mov     [rsp+arg_8], rbx
0x14004a335  push    rdi
0x14004a336  sub     rsp, 40h
0x14004a33a  mov     rax, [rcx+98h]
0x14004a341  mov     rbx, rcx
0x14004a344  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a34a  mov     [rsp+48h+Reply], 0
0x14004a352  mov     rdi, [rax+20h]
0x14004a356  mov     rdx, rdi; lpTlsValue
0x14004a359  call    cs:__imp_TlsSetValue
0x14004a360  nop     dword ptr [rax+rax+00h]
0x14004a365  test    eax, eax
0x14004a367  jz      short loc_14004A3E8
0x14004a369  mov     rcx, rdi; BindingHandle
0x14004a36c  call    cs:__imp_RpcImpersonateClient
0x14004a373  nop     dword ptr [rax+rax+00h]
0x14004a378  test    eax, eax
0x14004a37a  jnz     short loc_14004A3C4
0x14004a37c  mov     edx, [rbx+8Ch]
0x14004a382  mov     r9, [rbx+80h]
0x14004a389  mov     r8, [rbx+78h]
0x14004a38d  mov     rcx, [rbx+68h]
0x14004a391  mov     rax, [rbx+90h]
0x14004a398  mov     [rsp+48h+var_20], edx
0x14004a39c  mov     edx, [rbx+88h]
0x14004a3a2  mov     [rsp+48h+var_28], edx
0x14004a3a6  mov     rdx, [rbx+70h]
0x14004a3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a3af  mov     rcx, rdi; BindingHandle
0x14004a3b2  mov     [rsp+48h+Reply], eax
0x14004a3b6  call    cs:__imp_RpcRevertToSelfEx
0x14004a3bd  nop     dword ptr [rax+rax+00h]
0x14004a3c2  jmp     short loc_14004A3D2
0x14004a3c4  jle     short loc_14004A3CE
0x14004a3c6  movzx   eax, ax
0x14004a3c9  or      eax, 80070000h
0x14004a3ce  mov     [rsp+48h+Reply], eax
0x14004a3d2  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a3d8  xor     edx, edx; lpTlsValue
0x14004a3da  call    cs:__imp_TlsSetValue
0x14004a3e1  nop     dword ptr [rax+rax+00h]
0x14004a3e6  jmp     short loc_14004A3F1
0x14004a3e8  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14004a3ed  mov     [rsp+48h+Reply], eax
0x14004a3f1  mov     rcx, [rbx+98h]; pAsync
0x14004a3f8  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a3fd  call    cs:__imp_RpcAsyncCompleteCall
0x14004a404  nop     dword ptr [rax+rax+00h]
0x14004a409  mov     eax, [rsp+48h+Reply]
0x14004a40d  mov     rbx, [rsp+48h+arg_8]
0x14004a412  add     rsp, 40h
0x14004a416  pop     rdi
0x14004a417  retn
```
