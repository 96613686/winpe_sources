# TFunction7HR<ushort const *,ushort const *,_GUID,_FILETIME,unsigned __int64,int *,Call_Route>::Run(void)

- ea: `0x14004afa0`
- end: `0x14004b0a6`
- name: `?Run@?$TFunction7HR@PEBGPEBGU_GUID@@U_FILETIME@@_KPEAHW4Call_Route@@@@UEAAJXZ`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x14004afa0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004afc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b067`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004afc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004b067`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b043`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004b043`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b08a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004b08a`
- `RPCRT4!RpcImpersonateClient` at `0x14004afe0`
- `RPCRT4!RpcImpersonateClient` at `0x14004afe0`

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
0x14004afa0  mov     [rsp+arg_8], rbx
0x14004afa5  push    rdi
0x14004afa6  sub     rsp, 50h
0x14004afaa  mov     rax, [rcx+0B0h]
0x14004afb1  mov     rbx, rcx
0x14004afb4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004afba  mov     [rsp+58h+Reply], 0
0x14004afc2  mov     rdi, [rax+20h]
0x14004afc6  mov     rdx, rdi; lpTlsValue
0x14004afc9  call    cs:__imp_TlsSetValue
0x14004afd0  nop     dword ptr [rax+rax+00h]
0x14004afd5  test    eax, eax
0x14004afd7  jz      loc_14004B075
0x14004afdd  mov     rcx, rdi; BindingHandle
0x14004afe0  call    cs:__imp_RpcImpersonateClient
0x14004afe7  nop     dword ptr [rax+rax+00h]
0x14004afec  test    eax, eax
0x14004afee  jnz     short loc_14004B051
0x14004aff0  mov     edx, [rbx+0A0h]
0x14004aff6  lea     r8, [rsp+58h+var_18]
0x14004affb  movups  xmm0, xmmword ptr [rbx+78h]
0x14004afff  mov     r9, [rbx+88h]
0x14004b006  mov     rcx, [rbx+68h]
0x14004b00a  mov     rax, [rbx+0A8h]
0x14004b011  mov     [rsp+58h+var_28], edx
0x14004b015  mov     rdx, [rbx+98h]
0x14004b01c  mov     [rsp+58h+var_30], rdx
0x14004b021  mov     rdx, [rbx+90h]
0x14004b028  mov     [rsp+58h+var_38], rdx
0x14004b02d  mov     rdx, [rbx+70h]
0x14004b031  movdqu  [rsp+58h+var_18], xmm0
0x14004b037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b03c  mov     rcx, rdi; BindingHandle
0x14004b03f  mov     [rsp+58h+Reply], eax
0x14004b043  call    cs:__imp_RpcRevertToSelfEx
0x14004b04a  nop     dword ptr [rax+rax+00h]
0x14004b04f  jmp     short loc_14004B05F
0x14004b051  jle     short loc_14004B05B
0x14004b053  movzx   eax, ax
0x14004b056  or      eax, 80070000h
0x14004b05b  mov     [rsp+58h+Reply], eax
0x14004b05f  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004b065  xor     edx, edx; lpTlsValue
0x14004b067  call    cs:__imp_TlsSetValue
0x14004b06e  nop     dword ptr [rax+rax+00h]
0x14004b073  jmp     short loc_14004B07E
0x14004b075  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14004b07a  mov     [rsp+58h+Reply], eax
0x14004b07e  mov     rcx, [rbx+0B0h]; pAsync
0x14004b085  lea     rdx, [rsp+58h+Reply]; Reply
0x14004b08a  call    cs:__imp_RpcAsyncCompleteCall
0x14004b091  nop     dword ptr [rax+rax+00h]
0x14004b096  mov     eax, [rsp+58h+Reply]
0x14004b09a  mov     rbx, [rsp+58h+arg_8]
0x14004b09f  add     rsp, 50h
0x14004b0a3  pop     rdi
0x14004b0a4  retn
```
