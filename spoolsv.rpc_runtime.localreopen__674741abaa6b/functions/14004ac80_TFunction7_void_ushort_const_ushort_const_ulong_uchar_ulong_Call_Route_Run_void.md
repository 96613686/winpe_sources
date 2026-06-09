# TFunction7<void *,ushort const *,ushort const *,ulong,uchar *,ulong,Call_Route>::Run(void)

- ea: `0x14004ac80`
- end: `0x14004ad7c`
- name: `?Run@?$TFunction7@PEAXPEBGPEBGKPEAEKW4Call_Route@@@@UEAAJXZ`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14004ac80`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ad38`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aca9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ad2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004aca9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ad2a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ad16`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ad16`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ad54`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ad54`
- `RPCRT4!RpcImpersonateClient` at `0x14004acbc`
- `RPCRT4!RpcImpersonateClient` at `0x14004acbc`

## pseudocode

```c
__int64 __fastcall TFunction7<void *,unsigned short const *,unsigned short const *,unsigned long,unsigned char *,unsigned long,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 152))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(_QWORD *)(a1 + 120),
                *(unsigned int *)(a1 + 128),
                *(_QWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 148));
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
0x14004ac80  mov     [rsp+arg_8], rbx
0x14004ac85  push    rdi
0x14004ac86  sub     rsp, 40h
0x14004ac8a  mov     rax, [rcx+0A0h]
0x14004ac91  mov     rbx, rcx
0x14004ac94  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ac9a  mov     [rsp+48h+Reply], 0
0x14004aca2  mov     rdi, [rax+20h]
0x14004aca6  mov     rdx, rdi; lpTlsValue
0x14004aca9  call    cs:__imp_TlsSetValue
0x14004acb0  nop     dword ptr [rax+rax+00h]
0x14004acb5  test    eax, eax
0x14004acb7  jz      short loc_14004AD38
0x14004acb9  mov     rcx, rdi; BindingHandle
0x14004acbc  call    cs:__imp_RpcImpersonateClient
0x14004acc3  nop     dword ptr [rax+rax+00h]
0x14004acc8  mov     [rsp+48h+Reply], eax
0x14004accc  test    eax, eax
0x14004acce  jnz     short loc_14004AD22
0x14004acd0  mov     edx, [rbx+94h]
0x14004acd6  mov     r9d, [rbx+80h]
0x14004acdd  mov     r8, [rbx+78h]
0x14004ace1  mov     rcx, [rbx+68h]
0x14004ace5  mov     rax, [rbx+98h]
0x14004acec  mov     [rsp+48h+var_18], edx
0x14004acf0  mov     edx, [rbx+90h]
0x14004acf6  mov     [rsp+48h+var_20], edx
0x14004acfa  mov     rdx, [rbx+88h]
0x14004ad01  mov     [rsp+48h+var_28], rdx
0x14004ad06  mov     rdx, [rbx+70h]
0x14004ad0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad0f  mov     rcx, rdi; BindingHandle
0x14004ad12  mov     [rsp+48h+Reply], eax
0x14004ad16  call    cs:__imp_RpcRevertToSelfEx
0x14004ad1d  nop     dword ptr [rax+rax+00h]
0x14004ad22  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ad28  xor     edx, edx; lpTlsValue
0x14004ad2a  call    cs:__imp_TlsSetValue
0x14004ad31  nop     dword ptr [rax+rax+00h]
0x14004ad36  jmp     short loc_14004AD48
0x14004ad38  call    cs:__imp_GetLastError
0x14004ad3f  nop     dword ptr [rax+rax+00h]
0x14004ad44  mov     [rsp+48h+Reply], eax
0x14004ad48  mov     rcx, [rbx+0A0h]; pAsync
0x14004ad4f  lea     rdx, [rsp+48h+Reply]; Reply
0x14004ad54  call    cs:__imp_RpcAsyncCompleteCall
0x14004ad5b  nop     dword ptr [rax+rax+00h]
0x14004ad60  mov     eax, [rsp+48h+Reply]
0x14004ad64  test    eax, eax
0x14004ad66  jle     short loc_14004AD70
0x14004ad68  movzx   eax, ax
0x14004ad6b  or      eax, 80070000h
0x14004ad70  mov     rbx, [rsp+48h+arg_8]
0x14004ad75  add     rsp, 40h
0x14004ad79  pop     rdi
0x14004ad7a  retn
```
