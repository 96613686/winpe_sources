# TFunction4<void *,_DOC_INFO_CONTAINER *,ulong *,Call_Route>::Run(void)

- ea: `0x1400498b0`
- end: `0x14004998c`
- name: `?Run@?$TFunction4@PEAXPEAU_DOC_INFO_CONTAINER@@PEAKW4Call_Route@@@@UEAAJXZ`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400498b0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049948`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400498d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004993a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400498d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004993a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049926`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049926`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049964`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049964`
- `RPCRT4!RpcImpersonateClient` at `0x1400498ec`
- `RPCRT4!RpcImpersonateClient` at `0x1400498ec`

## pseudocode

```c
__int64 __fastcall TFunction4<void *,_DOC_INFO_CONTAINER *,unsigned long *,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 144);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 136))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 144), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400498b0  mov     [rsp+arg_8], rbx
0x1400498b5  push    rdi
0x1400498b6  sub     rsp, 30h
0x1400498ba  mov     rax, [rcx+90h]
0x1400498c1  mov     rbx, rcx
0x1400498c4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400498ca  mov     [rsp+38h+Reply], 0
0x1400498d2  mov     rdi, [rax+20h]
0x1400498d6  mov     rdx, rdi; lpTlsValue
0x1400498d9  call    cs:__imp_TlsSetValue
0x1400498e0  nop     dword ptr [rax+rax+00h]
0x1400498e5  test    eax, eax
0x1400498e7  jz      short loc_140049948
0x1400498e9  mov     rcx, rdi; BindingHandle
0x1400498ec  call    cs:__imp_RpcImpersonateClient
0x1400498f3  nop     dword ptr [rax+rax+00h]
0x1400498f8  mov     [rsp+38h+Reply], eax
0x1400498fc  test    eax, eax
0x1400498fe  jnz     short loc_140049932
0x140049900  mov     r9d, [rbx+80h]
0x140049907  mov     r8, [rbx+78h]
0x14004990b  mov     rdx, [rbx+70h]
0x14004990f  mov     rcx, [rbx+68h]
0x140049913  mov     rax, [rbx+88h]
0x14004991a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004991f  mov     rcx, rdi; BindingHandle
0x140049922  mov     [rsp+38h+Reply], eax
0x140049926  call    cs:__imp_RpcRevertToSelfEx
0x14004992d  nop     dword ptr [rax+rax+00h]
0x140049932  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140049938  xor     edx, edx; lpTlsValue
0x14004993a  call    cs:__imp_TlsSetValue
0x140049941  nop     dword ptr [rax+rax+00h]
0x140049946  jmp     short loc_140049958
0x140049948  call    cs:__imp_GetLastError
0x14004994f  nop     dword ptr [rax+rax+00h]
0x140049954  mov     [rsp+38h+Reply], eax
0x140049958  mov     rcx, [rbx+90h]; pAsync
0x14004995f  lea     rdx, [rsp+38h+Reply]; Reply
0x140049964  call    cs:__imp_RpcAsyncCompleteCall
0x14004996b  nop     dword ptr [rax+rax+00h]
0x140049970  mov     eax, [rsp+38h+Reply]
0x140049974  test    eax, eax
0x140049976  jle     short loc_140049980
0x140049978  movzx   eax, ax
0x14004997b  or      eax, 80070000h
0x140049980  mov     rbx, [rsp+38h+arg_8]
0x140049985  add     rsp, 30h
0x140049989  pop     rdi
0x14004998a  retn
```
