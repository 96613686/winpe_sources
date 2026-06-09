# TFunction7HR<ushort const *,ushort const *,ulong,ushort const *,ulong,_CORE_PRINTER_DRIVERW *,Call_Route>::Run(void)

- ea: `0x14004ad90`
- end: `0x14004ae89`
- name: `?Run@?$TFunction7HR@PEBGPEBGKPEBGKPEAU_CORE_PRINTER_DRIVERW@@W4Call_Route@@@@UEAAJXZ`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016120`
- `0x14004ad90`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004adb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ae4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004adb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14004ae4a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ae26`
- `RPCRT4!RpcRevertToSelfEx` at `0x14004ae26`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ae6d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004ae6d`
- `RPCRT4!RpcImpersonateClient` at `0x14004add0`
- `RPCRT4!RpcImpersonateClient` at `0x14004add0`

## pseudocode

```c
__int64 __fastcall TFunction7HR<unsigned short const *,unsigned short const *,unsigned long,unsigned short const *,unsigned long,_CORE_PRINTER_DRIVERW *,enum Call_Route>::Run(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  NCoreLibrary *v4; // rcx
  int v5; // eax
  unsigned int Reply; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 168);
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
      Reply = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 160))(
                *(_QWORD *)(a1 + 104),
                *(_QWORD *)(a1 + 112),
                *(unsigned int *)(a1 + 120),
                *(_QWORD *)(a1 + 128),
                *(_DWORD *)(a1 + 136),
                *(_QWORD *)(a1 + 144),
                *(_DWORD *)(a1 + 152));
      RpcRevertToSelfEx(v3);
    }
    TlsSetValue(gdwTlsBindingHandle, 0);
  }
  else
  {
    Reply = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 168), &Reply);
  return Reply;
}

```

## disassembly

```asm
0x14004ad90  mov     [rsp+arg_8], rbx
0x14004ad95  push    rdi
0x14004ad96  sub     rsp, 40h
0x14004ad9a  mov     rax, [rcx+0A8h]
0x14004ada1  mov     rbx, rcx
0x14004ada4  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004adaa  mov     [rsp+48h+Reply], 0
0x14004adb2  mov     rdi, [rax+20h]
0x14004adb6  mov     rdx, rdi; lpTlsValue
0x14004adb9  call    cs:__imp_TlsSetValue
0x14004adc0  nop     dword ptr [rax+rax+00h]
0x14004adc5  test    eax, eax
0x14004adc7  jz      loc_14004AE58
0x14004adcd  mov     rcx, rdi; BindingHandle
0x14004add0  call    cs:__imp_RpcImpersonateClient
0x14004add7  nop     dword ptr [rax+rax+00h]
0x14004addc  test    eax, eax
0x14004adde  jnz     short loc_14004AE34
0x14004ade0  mov     edx, [rbx+98h]
0x14004ade6  mov     r9, [rbx+80h]
0x14004aded  mov     r8d, [rbx+78h]
0x14004adf1  mov     rcx, [rbx+68h]
0x14004adf5  mov     rax, [rbx+0A0h]
0x14004adfc  mov     [rsp+48h+var_18], edx
0x14004ae00  mov     rdx, [rbx+90h]
0x14004ae07  mov     [rsp+48h+var_20], rdx
0x14004ae0c  mov     edx, [rbx+88h]
0x14004ae12  mov     [rsp+48h+var_28], edx
0x14004ae16  mov     rdx, [rbx+70h]
0x14004ae1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ae1f  mov     rcx, rdi; BindingHandle
0x14004ae22  mov     [rsp+48h+Reply], eax
0x14004ae26  call    cs:__imp_RpcRevertToSelfEx
0x14004ae2d  nop     dword ptr [rax+rax+00h]
0x14004ae32  jmp     short loc_14004AE42
0x14004ae34  jle     short loc_14004AE3E
0x14004ae36  movzx   eax, ax
0x14004ae39  or      eax, 80070000h
0x14004ae3e  mov     [rsp+48h+Reply], eax
0x14004ae42  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14004ae48  xor     edx, edx; lpTlsValue
0x14004ae4a  call    cs:__imp_TlsSetValue
0x14004ae51  nop     dword ptr [rax+rax+00h]
0x14004ae56  jmp     short loc_14004AE61
0x14004ae58  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14004ae5d  mov     [rsp+48h+Reply], eax
0x14004ae61  mov     rcx, [rbx+0A8h]; pAsync
0x14004ae68  lea     rdx, [rsp+48h+Reply]; Reply
0x14004ae6d  call    cs:__imp_RpcAsyncCompleteCall
0x14004ae74  nop     dword ptr [rax+rax+00h]
0x14004ae79  mov     eax, [rsp+48h+Reply]
0x14004ae7d  mov     rbx, [rsp+48h+arg_8]
0x14004ae82  add     rsp, 40h
0x14004ae86  pop     rdi
0x14004ae87  retn
```
