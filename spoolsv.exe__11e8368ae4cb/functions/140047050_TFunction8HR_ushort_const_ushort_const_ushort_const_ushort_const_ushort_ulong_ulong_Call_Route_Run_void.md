# TFunction8HR<ushort const *,ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140047050`
- end: `0x140047136`
- name: `?Run@?$TFunction8HR@PEBGPEBGPEBGPEBGPEAGKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140047050`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047079`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047104`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047079`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047104`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400470e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400470e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047121`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047121`
- `RPCRT4!RpcImpersonateClient` at `0x14004708a`
- `RPCRT4!RpcImpersonateClient` at `0x14004708a`

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
0x140047050  mov     [rsp+arg_8], rbx
0x140047055  push    rdi
0x140047056  sub     rsp, 50h
0x14004705a  mov     rax, [rcx+0B0h]
0x140047061  mov     rbx, rcx
0x140047064  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004706a  mov     [rsp+58h+Reply], 0
0x140047072  mov     rdi, [rax+20h]
0x140047076  mov     rdx, rdi; lpTlsValue
0x140047079  call    cs:__imp_TlsSetValue
0x14004707f  test    eax, eax
0x140047081  jz      loc_14004710C
0x140047087  mov     rcx, rdi; BindingHandle
0x14004708a  call    cs:__imp_RpcImpersonateClient
0x140047090  test    eax, eax
0x140047092  jnz     short loc_1400470EE
0x140047094  mov     edx, [rbx+0A0h]
0x14004709a  mov     r9, [rbx+80h]
0x1400470a1  mov     r8, [rbx+78h]
0x1400470a5  mov     rcx, [rbx+68h]
0x1400470a9  mov     rax, [rbx+0A8h]
0x1400470b0  mov     [rsp+58h+var_20], edx
0x1400470b4  mov     rdx, [rbx+98h]
0x1400470bb  mov     [rsp+58h+var_28], rdx
0x1400470c0  mov     edx, [rbx+90h]
0x1400470c6  mov     [rsp+58h+var_30], edx
0x1400470ca  mov     rdx, [rbx+88h]
0x1400470d1  mov     [rsp+58h+var_38], rdx
0x1400470d6  mov     rdx, [rbx+70h]
0x1400470da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400470df  mov     rcx, rdi; BindingHandle
0x1400470e2  mov     [rsp+58h+Reply], eax
0x1400470e6  call    cs:__imp_RpcRevertToSelfEx
0x1400470ec  jmp     short loc_1400470FC
0x1400470ee  jle     short loc_1400470F8
0x1400470f0  movzx   eax, ax
0x1400470f3  or      eax, 80070000h
0x1400470f8  mov     [rsp+58h+Reply], eax
0x1400470fc  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140047102  xor     edx, edx; lpTlsValue
0x140047104  call    cs:__imp_TlsSetValue
0x14004710a  jmp     short loc_140047115
0x14004710c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140047111  mov     [rsp+58h+Reply], eax
0x140047115  mov     rcx, [rbx+0B0h]; pAsync
0x14004711c  lea     rdx, [rsp+58h+Reply]; Reply
0x140047121  call    cs:__imp_RpcAsyncCompleteCall
0x140047127  mov     eax, [rsp+58h+Reply]
0x14004712b  mov     rbx, [rsp+58h+arg_8]
0x140047130  add     rsp, 50h
0x140047134  pop     rdi
0x140047135  retn
```
