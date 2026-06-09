# TFunction3<void *,ulong,Call_Route>::Run(void)

- ea: `0x1400497d0`
- end: `0x1400498a1`
- name: `?Run@?$TFunction3@PEAXKW4Call_Route@@@@UEAAJXZ`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400497d0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004985d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004985d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400497f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004984f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400497f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004984f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004983b`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004983b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049879`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140049879`
- `RPCRT4!RpcImpersonateClient` at `0x14004980c`
- `RPCRT4!RpcImpersonateClient` at `0x14004980c`

## pseudocode

```c
__int64 __fastcall TFunction3<void *,unsigned long,enum Call_Route>::Run(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 128);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 120))(
                *(_QWORD *)(a1 + 104),
                *(unsigned int *)(a1 + 112),
                *(unsigned int *)(a1 + 116));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 128), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400497d0  mov     [rsp+arg_8], rbx
0x1400497d5  push    rdi
0x1400497d6  sub     rsp, 20h
0x1400497da  mov     rax, [rcx+80h]
0x1400497e1  mov     rbx, rcx
0x1400497e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400497ea  mov     [rsp+28h+Reply], 0
0x1400497f2  mov     rdi, [rax+20h]
0x1400497f6  mov     rdx, rdi; lpTlsValue
0x1400497f9  call    cs:__imp_TlsSetValue
0x140049800  nop     dword ptr [rax+rax+00h]
0x140049805  test    eax, eax
0x140049807  jz      short loc_14004985D
0x140049809  mov     rcx, rdi; BindingHandle
0x14004980c  call    cs:__imp_RpcImpersonateClient
0x140049813  nop     dword ptr [rax+rax+00h]
0x140049818  mov     [rsp+28h+Reply], eax
0x14004981c  test    eax, eax
0x14004981e  jnz     short loc_140049847
0x140049820  mov     r8d, [rbx+74h]
0x140049824  mov     edx, [rbx+70h]
0x140049827  mov     rcx, [rbx+68h]
0x14004982b  mov     rax, [rbx+78h]
0x14004982f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049834  mov     rcx, rdi; BindingHandle
0x140049837  mov     [rsp+28h+Reply], eax
0x14004983b  call    cs:__imp_RpcRevertToSelfEx
0x140049842  nop     dword ptr [rax+rax+00h]
0x140049847  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004984d  xor     edx, edx; lpTlsValue
0x14004984f  call    cs:__imp_TlsSetValue
0x140049856  nop     dword ptr [rax+rax+00h]
0x14004985b  jmp     short loc_14004986D
0x14004985d  call    cs:__imp_GetLastError
0x140049864  nop     dword ptr [rax+rax+00h]
0x140049869  mov     [rsp+28h+Reply], eax
0x14004986d  mov     rcx, [rbx+80h]; pAsync
0x140049874  lea     rdx, [rsp+28h+Reply]; Reply
0x140049879  call    cs:__imp_RpcAsyncCompleteCall
0x140049880  nop     dword ptr [rax+rax+00h]
0x140049885  mov     eax, [rsp+28h+Reply]
0x140049889  test    eax, eax
0x14004988b  jle     short loc_140049895
0x14004988d  movzx   eax, ax
0x140049890  or      eax, 80070000h
0x140049895  mov     rbx, [rsp+28h+arg_8]
0x14004989a  add     rsp, 20h
0x14004989e  pop     rdi
0x14004989f  retn
```
