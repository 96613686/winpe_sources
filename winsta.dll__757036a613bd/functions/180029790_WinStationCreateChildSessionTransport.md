# WinStationCreateChildSessionTransport

- ea: `0x180029790`
- end: `0x18002987b`
- name: `WinStationCreateChildSessionTransport`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18002961c`
- `0x180029724`
- `0x180029790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297e5`
- `RPCRT4!NdrClientCall3` at `0x180029829`
- `RPCRT4!NdrClientCall3` at `0x180029829`

## string_xrefs

- `0x180029852`: `RpcCreateChildSessionTransport threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall WinStationCreateChildSessionTransport(__int64 a1, int a2)
{
  unsigned int Pointer; // ebx
  signed int LastError; // eax
  void *v6; // rax
  int v8; // [rsp+28h] [rbp-30h]
  unsigned __int16 v9[16]; // [rsp+38h] [rbp-20h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
  {
    return (unsigned int)WinStationCreateLoopbackSessionTransport(7, a1, a2);
  }
  else
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 1);
    if ( CSmartPublicBinding::operator void *(v9) )
    {
      v6 = CSmartPublicBinding::operator void *(v9);
      v8 = a2;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 7u, 0, v6, a1, v8).Pointer;
    }
    else
    {
      LastError = GetLastError();
      Pointer = LastError;
      if ( LastError > 0 )
        Pointer = (unsigned __int16)LastError | 0x80070000;
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180029790  mov     [rsp+arg_0], rbx
0x180029795  push    rdi
0x180029796  sub     rsp, 50h
0x18002979a  mov     ebx, edx
0x18002979c  mov     rdi, rcx
0x18002979f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x1800297a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x1800297ab  test    al, al
0x1800297ad  jz      short loc_1800297C6
0x1800297af  mov     r8d, ebx
0x1800297b2  mov     rdx, rdi
0x1800297b5  mov     ecx, 7
0x1800297ba  call    ?WinStationCreateLoopbackSessionTransport@@YAJW4_SESSIONTYPE@@PEAGK@Z; WinStationCreateLoopbackSessionTransport(_SESSIONTYPE,ushort *,ulong)
0x1800297bf  mov     ebx, eax
0x1800297c1  jmp     loc_18002986E
0x1800297c6  xor     edx, edx; void *
0x1800297c8  lea     r8d, [rdx+1]; int
0x1800297cc  lea     rcx, [rsp+58h+var_20]; this
0x1800297d1  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800297d6  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800297db  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800297e0  test    rax, rax
0x1800297e3  jnz     short loc_1800297FC
0x1800297e5  call    cs:__imp_GetLastError
0x1800297eb  mov     ebx, eax
0x1800297ed  test    eax, eax
0x1800297ef  jle     short loc_180029864
0x1800297f1  movzx   ebx, ax
0x1800297f4  or      ebx, 80070000h
0x1800297fa  jmp     short loc_180029864
0x1800297fc  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029801  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029806  mov     [rsp+58h+arg_10], 0
0x18002980f  mov     [rsp+58h+var_30], ebx
0x180029813  mov     [rsp+58h+var_38], rdi
0x180029818  mov     r9, rax
0x18002981b  xor     r8d, r8d; pReturnValue
0x18002981e  lea     edx, [r8+7]; nProcNum
0x180029822  lea     rcx, stru_180032140; pProxyInfo
0x180029829  call    cs:__imp_NdrClientCall3
0x18002982f  mov     rbx, rax
0x180029832  mov     [rsp+58h+arg_10], rax
0x180029837  mov     [rsp+58h+var_28], eax
0x18002983b  jmp     short loc_180029864
0x18002983d  test    eax, eax
0x18002983f  jle     short loc_180029849
0x180029841  movzx   eax, ax
0x180029844  or      eax, 80070000h
0x180029849  mov     ebx, eax
0x18002984b  mov     [rsp+58h+var_28], eax
0x18002984f  mov     r8d, eax
0x180029852  lea     rdx, aRpccreatechild; "RpcCreateChildSessionTransport threw an"...
0x180029859  mov     ecx, 8; int
0x18002985e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029863  nop
0x180029864  lea     rcx, [rsp+58h+var_20]; this
0x180029869  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002986e  mov     eax, ebx
0x180029870  mov     rbx, [rsp+58h+arg_0]
0x180029875  add     rsp, 50h
0x180029879  pop     rdi
0x18002987a  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
