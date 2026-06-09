# TFunction7HR<ushort const *,ushort const *,_GUID,_FILETIME,unsigned __int64,int *,Call_Route>::Run(void)

- ea: `0x140046d80`
- end: `0x140046e67`
- name: `?Run@?$TFunction7HR@PEBGPEBGU_GUID@@U_FILETIME@@_KPEAHW4Call_Route@@@@UEAAJXZ`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e14`
- `0x140046d80`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046da9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046e35`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046da9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140046e35`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046e17`
- `RPCRT4!RpcRevertToSelfEx` at `0x140046e17`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046e52`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046e52`
- `RPCRT4!RpcImpersonateClient` at `0x140046dba`
- `RPCRT4!RpcImpersonateClient` at `0x140046dba`

## pseudocode

```c
__int64 __fastcall TFunction7HR<unsigned short const *,unsigned short const *,_GUID,_FILETIME,unsigned __int64,int *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(__int64, __int64, __int128 *, __int64, __int64, __int64, int); // rax
  __int64 v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+30h] [rbp-28h]
  __int128 v14; // [rsp+40h] [rbp-18h] BYREF
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
      v6 = *(_QWORD *)(a1 + 136);
      v7 = *(_QWORD *)(a1 + 104);
      v8 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, __int64, __int64, __int64, int))(a1 + 168);
      v13 = *(_DWORD *)(a1 + 160);
      v12 = *(_QWORD *)(a1 + 152);
      v11 = *(_QWORD *)(a1 + 144);
      v9 = *(_QWORD *)(a1 + 112);
      v14 = *(_OWORD *)(a1 + 120);
      Reply = v8(v7, v9, &v14, v6, v11, v12, v13);
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
0x140046d80  mov     [rsp+arg_8], rbx
0x140046d85  push    rdi
0x140046d86  sub     rsp, 50h
0x140046d8a  mov     rax, [rcx+0B0h]
0x140046d91  mov     rbx, rcx
0x140046d94  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046d9a  mov     [rsp+58h+Reply], 0
0x140046da2  mov     rdi, [rax+20h]
0x140046da6  mov     rdx, rdi; lpTlsValue
0x140046da9  call    cs:__imp_TlsSetValue
0x140046daf  test    eax, eax
0x140046db1  jz      loc_140046E3D
0x140046db7  mov     rcx, rdi; BindingHandle
0x140046dba  call    cs:__imp_RpcImpersonateClient
0x140046dc0  test    eax, eax
0x140046dc2  jnz     short loc_140046E1F
0x140046dc4  mov     edx, [rbx+0A0h]
0x140046dca  lea     r8, [rsp+58h+var_18]
0x140046dcf  movups  xmm0, xmmword ptr [rbx+78h]
0x140046dd3  mov     r9, [rbx+88h]
0x140046dda  mov     rcx, [rbx+68h]
0x140046dde  mov     rax, [rbx+0A8h]
0x140046de5  mov     [rsp+58h+var_28], edx
0x140046de9  mov     rdx, [rbx+98h]
0x140046df0  mov     [rsp+58h+var_30], rdx
0x140046df5  mov     rdx, [rbx+90h]
0x140046dfc  mov     [rsp+58h+var_38], rdx
0x140046e01  mov     rdx, [rbx+70h]
0x140046e05  movdqu  [rsp+58h+var_18], xmm0
0x140046e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046e10  mov     rcx, rdi; BindingHandle
0x140046e13  mov     [rsp+58h+Reply], eax
0x140046e17  call    cs:__imp_RpcRevertToSelfEx
0x140046e1d  jmp     short loc_140046E2D
0x140046e1f  jle     short loc_140046E29
0x140046e21  movzx   eax, ax
0x140046e24  or      eax, 80070000h
0x140046e29  mov     [rsp+58h+Reply], eax
0x140046e2d  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140046e33  xor     edx, edx; lpTlsValue
0x140046e35  call    cs:__imp_TlsSetValue
0x140046e3b  jmp     short loc_140046E46
0x140046e3d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140046e42  mov     [rsp+58h+Reply], eax
0x140046e46  mov     rcx, [rbx+0B0h]; pAsync
0x140046e4d  lea     rdx, [rsp+58h+Reply]; Reply
0x140046e52  call    cs:__imp_RpcAsyncCompleteCall
0x140046e58  mov     eax, [rsp+58h+Reply]
0x140046e5c  mov     rbx, [rsp+58h+arg_8]
0x140046e61  add     rsp, 50h
0x140046e65  pop     rdi
0x140046e66  retn
```
