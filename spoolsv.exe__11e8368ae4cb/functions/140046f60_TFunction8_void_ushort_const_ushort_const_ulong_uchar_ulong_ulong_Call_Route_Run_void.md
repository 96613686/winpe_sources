# TFunction8<void *,ushort const *,ushort const *,ulong *,uchar *,ulong,ulong *,Call_Route>::Run(void)

- ea: `0x140046f60`
- end: `0x140047043`
- name: `?Run@?$TFunction8@PEAXPEBGPEBGPEAKPEAEKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046f60`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004700c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004700c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046f89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047004`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046f89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140047004`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046ff6`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046ff6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047022`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140047022`
- `RPCRT4!RpcImpersonateClient` at `0x140046f96`
- `RPCRT4!RpcImpersonateClient` at `0x140046f96`

## pseudocode

```c
__int64 __fastcall TFunction8<void *,unsigned short const *,unsigned short const *,unsigned long *,unsigned char *,unsigned long,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 176);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
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
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 176), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140046f60  mov     [rsp+arg_8], rbx
0x140046f65  push    rdi
0x140046f66  sub     rsp, 50h
0x140046f6a  mov     rax, [rcx+0B0h]
0x140046f71  mov     rbx, rcx
0x140046f74  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046f7a  mov     [rsp+58h+Reply], 0
0x140046f82  mov     rdi, [rax+20h]
0x140046f86  mov     rdx, rdi; lpTlsValue
0x140046f89  call    cs:__imp_TlsSetValue
0x140046f8f  test    eax, eax
0x140046f91  jz      short loc_14004700C
0x140046f93  mov     rcx, rdi; BindingHandle
0x140046f96  call    cs:__imp_RpcImpersonateClient
0x140046f9c  mov     [rsp+58h+Reply], eax
0x140046fa0  test    eax, eax
0x140046fa2  jnz     short loc_140046FFC
0x140046fa4  mov     edx, [rbx+0A0h]
0x140046faa  mov     r9, [rbx+80h]
0x140046fb1  mov     r8, [rbx+78h]
0x140046fb5  mov     rcx, [rbx+68h]
0x140046fb9  mov     rax, [rbx+0A8h]
0x140046fc0  mov     [rsp+58h+var_20], edx
0x140046fc4  mov     rdx, [rbx+98h]
0x140046fcb  mov     [rsp+58h+var_28], rdx
0x140046fd0  mov     edx, [rbx+90h]
0x140046fd6  mov     [rsp+58h+var_30], edx
0x140046fda  mov     rdx, [rbx+88h]
0x140046fe1  mov     [rsp+58h+var_38], rdx
0x140046fe6  mov     rdx, [rbx+70h]
0x140046fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046fef  mov     rcx, rdi; BindingHandle
0x140046ff2  mov     [rsp+58h+Reply], eax
0x140046ff6  call    cs:__imp_RpcRevertToSelfEx
0x140046ffc  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140047002  xor     edx, edx; lpTlsValue
0x140047004  call    cs:__imp_TlsSetValue
0x14004700a  jmp     short loc_140047016
0x14004700c  call    cs:__imp_GetLastError
0x140047012  mov     [rsp+58h+Reply], eax
0x140047016  mov     rcx, [rbx+0B0h]; pAsync
0x14004701d  lea     rdx, [rsp+58h+Reply]; Reply
0x140047022  call    cs:__imp_RpcAsyncCompleteCall
0x140047028  mov     eax, [rsp+58h+Reply]
0x14004702c  test    eax, eax
0x14004702e  jle     short loc_140047038
0x140047030  movzx   eax, ax
0x140047033  or      eax, 80070000h
0x140047038  mov     rbx, [rsp+58h+arg_8]
0x14004703d  add     rsp, 50h
0x140047041  pop     rdi
0x140047042  retn
```
