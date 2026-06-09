# TFunction8<ushort *,ushort *,ulong,uchar *,ulong,ulong *,ulong *,Call_Route>::Run(void)

- ea: `0x140046e70`
- end: `0x140046f53`
- name: `?Run@?$TFunction8@PEAGPEAGKPEAEKPEAKPEAKW4Call_Route@@@@UEAAJXZ`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140046e70`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046e99`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046f14`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046e99`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046f14`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046f06`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046f06`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046f32`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046f32`
- `RPCRT4!RpcImpersonateClient` at `0x140046ea6`
- `RPCRT4!RpcImpersonateClient` at `0x140046ea6`

## pseudocode

```c
__int64 __fastcall TFunction8<unsigned short *,unsigned short *,unsigned long,unsigned char *,unsigned long,unsigned long *,unsigned long *,enum Call_Route>::Run(
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD))(a1 + 168))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
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
0x140046e70  mov     [rsp+arg_8], rbx
0x140046e75  push    rdi
0x140046e76  sub     rsp, 50h
0x140046e7a  mov     rax, [rcx+0B0h]
0x140046e81  mov     rbx, rcx
0x140046e84  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046e8a  mov     [rsp+58h+Reply], 0
0x140046e92  mov     rdi, [rax+20h]
0x140046e96  mov     rdx, rdi; lpTlsValue
0x140046e99  call    cs:__imp_TlsSetValue
0x140046e9f  test    eax, eax
0x140046ea1  jz      short loc_140046F1C
0x140046ea3  mov     rcx, rdi; BindingHandle
0x140046ea6  call    cs:__imp_RpcImpersonateClient
0x140046eac  mov     [rsp+58h+Reply], eax
0x140046eb0  test    eax, eax
0x140046eb2  jnz     short loc_140046F0C
0x140046eb4  mov     edx, [rbx+0A0h]
0x140046eba  mov     r9, [rbx+80h]
0x140046ec1  mov     r8d, [rbx+78h]
0x140046ec5  mov     rcx, [rbx+68h]
0x140046ec9  mov     rax, [rbx+0A8h]
0x140046ed0  mov     [rsp+58h+var_20], edx
0x140046ed4  mov     rdx, [rbx+98h]
0x140046edb  mov     [rsp+58h+var_28], rdx
0x140046ee0  mov     rdx, [rbx+90h]
0x140046ee7  mov     [rsp+58h+var_30], rdx
0x140046eec  mov     edx, [rbx+88h]
0x140046ef2  mov     [rsp+58h+var_38], edx
0x140046ef6  mov     rdx, [rbx+70h]
0x140046efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046eff  mov     rcx, rdi; BindingHandle
0x140046f02  mov     [rsp+58h+Reply], eax
0x140046f06  call    cs:__imp_RpcRevertToSelfEx
0x140046f0c  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046f12  xor     edx, edx; lpTlsValue
0x140046f14  call    cs:__imp_TlsSetValue
0x140046f1a  jmp     short loc_140046F26
0x140046f1c  call    cs:__imp_GetLastError
0x140046f22  mov     [rsp+58h+Reply], eax
0x140046f26  mov     rcx, [rbx+0B0h]; pAsync
0x140046f2d  lea     rdx, [rsp+58h+Reply]; Reply
0x140046f32  call    cs:__imp_RpcAsyncCompleteCall
0x140046f38  mov     eax, [rsp+58h+Reply]
0x140046f3c  test    eax, eax
0x140046f3e  jle     short loc_140046F48
0x140046f40  movzx   eax, ax
0x140046f43  or      eax, 80070000h
0x140046f48  mov     rbx, [rsp+58h+arg_8]
0x140046f4d  add     rsp, 50h
0x140046f51  pop     rdi
0x140046f52  retn
```
