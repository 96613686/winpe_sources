# WinStationCreateLoopbackSessionTransport(_SESSIONTYPE,ushort *,ulong)

- ea: `0x18002961c`
- end: `0x18002971d`
- name: `?WinStationCreateLoopbackSessionTransport@@YAJW4_SESSIONTYPE@@PEAGK@Z`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180029770`
- `0x180029790`

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18002961c`
- `0x180029724`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002966d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002966d`
- `RPCRT4!NdrClientCall3` at `0x1800296ba`
- `RPCRT4!NdrClientCall3` at `0x1800296ba`

## string_xrefs

- `0x1800296ee`: `RpcCreateLoopbackSessionTransport(%d) threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall WinStationCreateLoopbackSessionTransport(int a1, __int64 a2, int a3)
{
  unsigned int Pointer; // ebx
  signed int LastError; // eax
  __int64 v8; // rax
  int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+30h] [rbp-48h]
  unsigned __int16 v12[24]; // [rsp+48h] [rbp-30h] BYREF

  Pointer = -2147467263;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, 0, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
  {
    if ( CSmartPublicBinding::operator void *(v12) )
    {
      v8 = CSmartPublicBinding::operator void *(v12);
      v11 = a3;
      v10 = a1;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180036F20, 0, 0, v8, v10, a2, v11).Pointer;
    }
    else
    {
      LastError = GetLastError();
      Pointer = LastError;
      if ( LastError > 0 )
        Pointer = (unsigned __int16)LastError | 0x80070000;
    }
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return Pointer;
}

```

## disassembly

```asm
0x18002961c  mov     [rsp+arg_8], rbx
0x180029621  mov     [rsp+arg_0], ecx
0x180029625  push    rsi
0x180029626  push    rdi
0x180029627  push    r14
0x180029629  sub     rsp, 60h
0x18002962d  mov     esi, r8d
0x180029630  mov     r14, rdx
0x180029633  mov     edi, ecx
0x180029635  mov     ebx, 80004001h
0x18002963a  xor     edx, edx; void *
0x18002963c  lea     r8d, [rdx+1]; int
0x180029640  lea     rcx, [rsp+78h+var_30]; this
0x180029645  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002964a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x180029651  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x180029656  test    al, al
0x180029658  jz      loc_180029700
0x18002965e  lea     rcx, [rsp+78h+var_30]; unsigned __int16 *
0x180029663  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029668  test    rax, rax
0x18002966b  jnz     short loc_180029688
0x18002966d  call    cs:__imp_GetLastError
0x180029673  mov     ebx, eax
0x180029675  test    eax, eax
0x180029677  jle     loc_180029700
0x18002967d  movzx   ebx, ax
0x180029680  or      ebx, 80070000h
0x180029686  jmp     short loc_180029700
0x180029688  lea     rcx, [rsp+78h+var_30]; unsigned __int16 *
0x18002968d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029692  mov     [rsp+78h+arg_18], 0
0x18002969e  mov     [rsp+78h+var_48], esi
0x1800296a2  mov     [rsp+78h+var_50], r14
0x1800296a7  mov     [rsp+78h+var_58], edi
0x1800296ab  mov     r9, rax
0x1800296ae  xor     r8d, r8d; pReturnValue
0x1800296b1  xor     edx, edx; nProcNum
0x1800296b3  lea     rcx, stru_180036F20; pProxyInfo
0x1800296ba  call    cs:__imp_NdrClientCall3
0x1800296c0  mov     rbx, rax
0x1800296c3  mov     [rsp+78h+arg_18], rax
0x1800296cb  mov     [rsp+78h+var_38], eax
0x1800296cf  jmp     short loc_180029700
0x1800296d1  test    eax, eax
0x1800296d3  jle     short loc_1800296DD
0x1800296d5  movzx   eax, ax
0x1800296d8  or      eax, 80070000h
0x1800296dd  mov     ebx, eax
0x1800296df  mov     [rsp+78h+var_38], eax
0x1800296e3  mov     r9d, eax
0x1800296e6  mov     r8d, [rsp+78h+arg_0]
0x1800296ee  lea     rdx, aRpccreateloopb; "RpcCreateLoopbackSessionTransport(%d) t"...
0x1800296f5  mov     ecx, 8; int
0x1800296fa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800296ff  nop
0x180029700  lea     rcx, [rsp+78h+var_30]; this
0x180029705  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002970a  mov     eax, ebx
0x18002970c  mov     rbx, [rsp+78h+arg_8]
0x180029714  add     rsp, 60h
0x180029718  pop     r14
0x18002971a  pop     rdi
0x18002971b  pop     rsi
0x18002971c  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
