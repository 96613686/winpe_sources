# TFunction8HR<ushort const *,ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x14004b2f0`
- end: `0x14004b3f5`
- name: `?Run@?$TFunction8HR@PEBGPEBGPEBGPEBGPEAGKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x14004b2f0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b319`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b3b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b319`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b3b6`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b392`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b392`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b3d9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b3d9`
- `RPCRT4!RpcImpersonateClient` at `0x14004b330`
- `RPCRT4!RpcImpersonateClient` at `0x14004b330`

## pseudocode

```c
__int64 __fastcall TFunction8HR<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short *,unsigned long,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 176);
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 168))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_QWORD *)(a1 + 152),
                *(_DWORD *)(a1 + 160));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 176), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x14004b2f0  mov     [rsp+arg_8], rbx
0x14004b2f5  push    rdi
0x14004b2f6  sub     rsp, 50h
0x14004b2fa  mov     rax, [rcx+0B0h]
0x14004b301  mov     rbx, rcx
0x14004b304  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b30a  mov     [rsp+58h+Reply], 0
0x14004b312  mov     rdi, [rax+20h]
0x14004b316  mov     rdx, rdi; lpTlsValue
0x14004b319  call    cs:__imp_TlsSetValue
0x14004b320  nop     dword ptr [rax+rax+00h]
0x14004b325  test    eax, eax
0x14004b327  jz      loc_14004B3C4
0x14004b32d  mov     rcx, rdi; BindingHandle
0x14004b330  call    cs:__imp_RpcImpersonateClient
0x14004b337  nop     dword ptr [rax+rax+00h]
0x14004b33c  test    eax, eax
0x14004b33e  jnz     short loc_14004B3A0
0x14004b340  mov     edx, [rbx+0A0h]
0x14004b346  mov     r9, [rbx+80h]
0x14004b34d  mov     r8, [rbx+78h]
0x14004b351  mov     rcx, [rbx+68h]
0x14004b355  mov     rax, [rbx+0A8h]
0x14004b35c  mov     [rsp+58h+var_20], edx
0x14004b360  mov     rdx, [rbx+98h]
0x14004b367  mov     [rsp+58h+var_28], rdx
0x14004b36c  mov     edx, [rbx+90h]
0x14004b372  mov     [rsp+58h+var_30], edx
0x14004b376  mov     rdx, [rbx+88h]
0x14004b37d  mov     [rsp+58h+var_38], rdx
0x14004b382  mov     rdx, [rbx+70h]
0x14004b386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b38b  mov     rcx, rdi; BindingHandle
0x14004b38e  mov     [rsp+58h+Reply], eax
0x14004b392  call    cs:__imp_RpcRevertToSelfEx
0x14004b399  nop     dword ptr [rax+rax+00h]
0x14004b39e  jmp     short loc_14004B3AE
0x14004b3a0  jle     short loc_14004B3AA
0x14004b3a2  movzx   eax, ax
0x14004b3a5  or      eax, 80070000h
0x14004b3aa  mov     [rsp+58h+Reply], eax
0x14004b3ae  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b3b4  xor     edx, edx; lpTlsValue
0x14004b3b6  call    cs:__imp_TlsSetValue
0x14004b3bd  nop     dword ptr [rax+rax+00h]
0x14004b3c2  jmp     short loc_14004B3CD
0x14004b3c4  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14004b3c9  mov     [rsp+58h+Reply], eax
0x14004b3cd  mov     rcx, [rbx+0B0h]; pAsync
0x14004b3d4  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b3d9  call    cs:__imp_RpcAsyncCompleteCall
0x14004b3e0  nop     dword ptr [rax+rax+00h]
0x14004b3e5  mov     eax, [rsp+58h+Reply]
0x14004b3e9  mov     rbx, [rsp+58h+arg_8]
0x14004b3ee  add     rsp, 50h
0x14004b3f2  pop     rdi
0x14004b3f3  retn
```
