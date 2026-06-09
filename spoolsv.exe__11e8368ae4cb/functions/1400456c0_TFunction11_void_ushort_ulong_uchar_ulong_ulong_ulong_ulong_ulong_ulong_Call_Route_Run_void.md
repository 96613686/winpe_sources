# TFunction11<void *,ushort *,ulong,uchar *,ulong,ulong *,ulong,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x1400456c0`
- end: `0x1400457c7`
- name: `?Run@?$TFunction11@PEAXPEAGKPEAEKPEAKKKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400456c0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045790`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400456e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045788`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400456e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140045788`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004577a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004577a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400457a6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400457a6`
- `RPCRT4!RpcImpersonateClient` at `0x1400456fa`
- `RPCRT4!RpcImpersonateClient` at `0x1400456fa`

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
0x1400456c0  mov     [rsp+arg_8], rbx
0x1400456c5  push    rdi
0x1400456c6  sub     rsp, 60h
0x1400456ca  mov     rax, [rcx+0C0h]
0x1400456d1  mov     rbx, rcx
0x1400456d4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400456da  mov     [rsp+68h+Reply], 0
0x1400456e2  mov     rdi, [rax+20h]
0x1400456e6  mov     rdx, rdi; lpTlsValue
0x1400456e9  call    cs:__imp_TlsSetValue
0x1400456ef  test    eax, eax
0x1400456f1  jz      loc_140045790
0x1400456f7  mov     rcx, rdi; BindingHandle
0x1400456fa  call    cs:__imp_RpcImpersonateClient
0x140045700  mov     [rsp+68h+Reply], eax
0x140045704  test    eax, eax
0x140045706  jnz     short loc_140045780
0x140045708  mov     edx, [rbx+9Ch]
0x14004570e  mov     eax, [rbx+0B0h]
0x140045714  mov     rcx, [rbx+0A0h]
0x14004571b  mov     r9, [rbx+80h]
0x140045722  mov     r8d, [rbx+78h]
0x140045726  mov     [rsp+68h+var_18], eax
0x14004572a  mov     rax, [rbx+0A8h]
0x140045731  mov     [rsp+68h+var_20], rax
0x140045736  mov     rax, [rbx+0B8h]
0x14004573d  mov     [rsp+68h+var_28], rcx
0x140045742  mov     rcx, [rbx+68h]
0x140045746  mov     [rsp+68h+var_30], edx
0x14004574a  mov     edx, [rbx+98h]
0x140045750  mov     [rsp+68h+var_38], edx
0x140045754  mov     rdx, [rbx+90h]
0x14004575b  mov     [rsp+68h+var_40], rdx
0x140045760  mov     edx, [rbx+88h]
0x140045766  mov     [rsp+68h+var_48], edx
0x14004576a  mov     rdx, [rbx+70h]
0x14004576e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045773  mov     rcx, rdi; BindingHandle
0x140045776  mov     [rsp+68h+Reply], eax
0x14004577a  call    cs:__imp_RpcRevertToSelfEx
0x140045780  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140045786  xor     edx, edx; lpTlsValue
0x140045788  call    cs:__imp_TlsSetValue
0x14004578e  jmp     short loc_14004579A
0x140045790  call    cs:__imp_GetLastError
0x140045796  mov     [rsp+68h+Reply], eax
0x14004579a  mov     rcx, [rbx+0C0h]; pAsync
0x1400457a1  lea     rdx, [rsp+68h+Reply]; Reply
0x1400457a6  call    cs:__imp_RpcAsyncCompleteCall
0x1400457ac  mov     eax, [rsp+68h+Reply]
0x1400457b0  test    eax, eax
0x1400457b2  jle     short loc_1400457BC
0x1400457b4  movzx   eax, ax
0x1400457b7  or      eax, 80070000h
0x1400457bc  mov     rbx, [rsp+68h+arg_8]
0x1400457c1  add     rsp, 60h
0x1400457c5  pop     rdi
0x1400457c6  retn
```
