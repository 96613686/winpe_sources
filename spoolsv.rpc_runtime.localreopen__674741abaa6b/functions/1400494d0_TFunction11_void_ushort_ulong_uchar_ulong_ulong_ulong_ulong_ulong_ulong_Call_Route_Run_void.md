# TFunction11<void *,ushort *,ulong,uchar *,ulong,ulong *,ulong,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x1400494d0`
- end: `0x1400495fc`
- name: `?Run@?$TFunction11@PEAXPEAGKPEAEKPEAKKKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400494d0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400495b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400495b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400494f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400495aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400494f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400495aa`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049596`
- `RPCRT4!RpcRevertToSelfEx` at `0x140049596`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400495d4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400495d4`
- `RPCRT4!RpcImpersonateClient` at `0x140049510`
- `RPCRT4!RpcImpersonateClient` at `0x140049510`

## pseudocode

```c
__int64 __fastcall TFunction11<void *,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 result; // rax
  int Reply; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 192);
  Reply = 0;
  v3 = *(void **)(v1 + 32);
  if ( TlsSetValue(gdwTlsBindingHandle, v3) )
  {
    Reply = RpcImpersonateClient(v3);
    if ( !Reply )
    {
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 184))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 152),
                *(_DWORD *)(a1 + 156),
                *(_QWORD *)(a1 + 160),
                *(_QWORD *)(a1 + 168),
                *(_DWORD *)(a1 + 176));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = GetLastError();
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 192), &Reply);
  result = (unsigned int)Reply;
  if ( Reply > 0 )
    return (unsigned __int16)Reply | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400494d0  mov     [rsp+arg_8], rbx
0x1400494d5  push    rdi
0x1400494d6  sub     rsp, 60h
0x1400494da  mov     rax, [rcx+0C0h]
0x1400494e1  mov     rbx, rcx
0x1400494e4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400494ea  mov     [rsp+68h+Reply], 0
0x1400494f2  mov     rdi, [rax+20h]
0x1400494f6  mov     rdx, rdi; lpTlsValue
0x1400494f9  call    cs:__imp_TlsSetValue
0x140049500  nop     dword ptr [rax+rax+00h]
0x140049505  test    eax, eax
0x140049507  jz      loc_1400495B8
0x14004950d  mov     rcx, rdi; BindingHandle
0x140049510  call    cs:__imp_RpcImpersonateClient
0x140049517  nop     dword ptr [rax+rax+00h]
0x14004951c  mov     [rsp+68h+Reply], eax
0x140049520  test    eax, eax
0x140049522  jnz     short loc_1400495A2
0x140049524  mov     edx, [rbx+9Ch]
0x14004952a  mov     eax, [rbx+0B0h]
0x140049530  mov     rcx, [rbx+0A0h]
0x140049537  mov     r9, [rbx+80h]
0x14004953e  mov     r8d, [rbx+78h]
0x140049542  mov     [rsp+68h+var_18], eax
0x140049546  mov     rax, [rbx+0A8h]
0x14004954d  mov     [rsp+68h+var_20], rax
0x140049552  mov     rax, [rbx+0B8h]
0x140049559  mov     [rsp+68h+var_28], rcx
0x14004955e  mov     rcx, [rbx+68h]
0x140049562  mov     [rsp+68h+var_30], edx
0x140049566  mov     edx, [rbx+98h]
0x14004956c  mov     [rsp+68h+var_38], edx
0x140049570  mov     rdx, [rbx+90h]
0x140049577  mov     [rsp+68h+var_40], rdx
0x14004957c  mov     edx, [rbx+88h]
0x140049582  mov     [rsp+68h+var_48], edx
0x140049586  mov     rdx, [rbx+70h]
0x14004958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004958f  mov     rcx, rdi; BindingHandle
0x140049592  mov     [rsp+68h+Reply], eax
0x140049596  call    cs:__imp_RpcRevertToSelfEx
0x14004959d  nop     dword ptr [rax+rax+00h]
0x1400495a2  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400495a8  xor     edx, edx; lpTlsValue
0x1400495aa  call    cs:__imp_TlsSetValue
0x1400495b1  nop     dword ptr [rax+rax+00h]
0x1400495b6  jmp     short loc_1400495C8
0x1400495b8  call    cs:__imp_GetLastError
0x1400495bf  nop     dword ptr [rax+rax+00h]
0x1400495c4  mov     [rsp+68h+Reply], eax
0x1400495c8  mov     rcx, [rbx+0C0h]; pAsync
0x1400495cf  lea     rdx, [rsp+68h+Reply]; Reply
0x1400495d4  call    cs:__imp_RpcAsyncCompleteCall
0x1400495db  nop     dword ptr [rax+rax+00h]
0x1400495e0  mov     eax, [rsp+68h+Reply]
0x1400495e4  test    eax, eax
0x1400495e6  jle     short loc_1400495F0
0x1400495e8  movzx   eax, ax
0x1400495eb  or      eax, 80070000h
0x1400495f0  mov     rbx, [rsp+68h+arg_8]
0x1400495f5  add     rsp, 60h
0x1400495f9  pop     rdi
0x1400495fa  retn
```
