# TFunction6<void *,_PRINTER_CONTAINER *,_DEVMODE_CONTAINER *,_SECURITY_CONTAINER *,ulong,Call_Route>::Run(void)

- ea: `0x14004a130`
- end: `0x14004a220`
- name: `?Run@?$TFunction6@PEAXPEAU_PRINTER_CONTAINER@@PEAU_DEVMODE_CONTAINER@@PEAU_SECURITY_CONTAINER@@KW4Call_Route@@@@UEAAJXZ`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004a130`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a1dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a159`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a1ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a159`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004a1ce`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a1ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004a1ba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a1f8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004a1f8`
- `RPCRT4!RpcImpersonateClient` at `0x14004a16c`
- `RPCRT4!RpcImpersonateClient` at `0x14004a16c`

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
0x14004a130  mov     [rsp+arg_8], rbx
0x14004a135  push    rdi
0x14004a136  sub     rsp, 40h
0x14004a13a  mov     rax, [rcx+98h]
0x14004a141  mov     rbx, rcx
0x14004a144  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a14a  mov     [rsp+48h+Reply], 0
0x14004a152  mov     rdi, [rax+20h]
0x14004a156  mov     rdx, rdi; lpTlsValue
0x14004a159  call    cs:__imp_TlsSetValue
0x14004a160  nop     dword ptr [rax+rax+00h]
0x14004a165  test    eax, eax
0x14004a167  jz      short loc_14004A1DC
0x14004a169  mov     rcx, rdi; BindingHandle
0x14004a16c  call    cs:__imp_RpcImpersonateClient
0x14004a173  nop     dword ptr [rax+rax+00h]
0x14004a178  mov     [rsp+48h+Reply], eax
0x14004a17c  test    eax, eax
0x14004a17e  jnz     short loc_14004A1C6
0x14004a180  mov     edx, [rbx+8Ch]
0x14004a186  mov     r9, [rbx+80h]
0x14004a18d  mov     r8, [rbx+78h]
0x14004a191  mov     rcx, [rbx+68h]
0x14004a195  mov     rax, [rbx+90h]
0x14004a19c  mov     [rsp+48h+var_20], edx
0x14004a1a0  mov     edx, [rbx+88h]
0x14004a1a6  mov     [rsp+48h+var_28], edx
0x14004a1aa  mov     rdx, [rbx+70h]
0x14004a1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a1b3  mov     rcx, rdi; BindingHandle
0x14004a1b6  mov     [rsp+48h+Reply], eax
0x14004a1ba  call    cs:__imp_RpcRevertToSelfEx
0x14004a1c1  nop     dword ptr [rax+rax+00h]
0x14004a1c6  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004a1cc  xor     edx, edx; lpTlsValue
0x14004a1ce  call    cs:__imp_TlsSetValue
0x14004a1d5  nop     dword ptr [rax+rax+00h]
0x14004a1da  jmp     short loc_14004A1EC
0x14004a1dc  call    cs:__imp_GetLastError
0x14004a1e3  nop     dword ptr [rax+rax+00h]
0x14004a1e8  mov     [rsp+48h+Reply], eax
0x14004a1ec  mov     rcx, [rbx+98h]; pAsync
0x14004a1f3  lea     rdx, [rsp+48h+Reply]; Reply
0x14004a1f8  call    cs:__imp_RpcAsyncCompleteCall
0x14004a1ff  nop     dword ptr [rax+rax+00h]
0x14004a204  mov     eax, [rsp+48h+Reply]
0x14004a208  test    eax, eax
0x14004a20a  jle     short loc_14004A214
0x14004a20c  movzx   eax, ax
0x14004a20f  or      eax, 80070000h
0x14004a214  mov     rbx, [rsp+48h+arg_8]
0x14004a219  add     rsp, 40h
0x14004a21d  pop     rdi
0x14004a21e  retn
```
