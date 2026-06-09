# WinStationCreateLoopbackSessionTransport(_SESSIONTYPE,ushort *,ulong)

- ea: `0x18002b258`
- end: `0x18002b366`
- name: `?WinStationCreateLoopbackSessionTransport@@YAJW4_SESSIONTYPE@@PEAGK@Z`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002b3b0`
- `0x18002b3d0`

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002b258`
- `0x18002b36c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2a9`
- `RPCRT4!NdrClientCall3` at `0x18002b2fc`
- `RPCRT4!NdrClientCall3` at `0x18002b2fc`

## string_xrefs

- `0x18002b336`: `RpcCreateLoopbackSessionTransport(%d) threw an exception: 0x%x`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180039F20, 0, 0, v8, v10, a2, v11).Pointer;
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
0x18002b258  mov     [rsp+arg_8], rbx
0x18002b25d  mov     [rsp+arg_0], ecx
0x18002b261  push    rsi
0x18002b262  push    rdi
0x18002b263  push    r14
0x18002b265  sub     rsp, 60h
0x18002b269  mov     esi, r8d
0x18002b26c  mov     r14, rdx
0x18002b26f  mov     edi, ecx
0x18002b271  mov     ebx, 80004001h
0x18002b276  xor     edx, edx; void *
0x18002b278  lea     r8d, [rdx+1]; int
0x18002b27c  lea     rcx, [rsp+78h+var_30]; this
0x18002b281  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002b286  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18002b28d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18002b292  test    al, al
0x18002b294  jz      loc_18002B348
0x18002b29a  lea     rcx, [rsp+78h+var_30]; unsigned __int16 *
0x18002b29f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b2a4  test    rax, rax
0x18002b2a7  jnz     short loc_18002B2CA
0x18002b2a9  call    cs:__imp_GetLastError
0x18002b2b0  nop     dword ptr [rax+rax+00h]
0x18002b2b5  mov     ebx, eax
0x18002b2b7  test    eax, eax
0x18002b2b9  jle     loc_18002B348
0x18002b2bf  movzx   ebx, ax
0x18002b2c2  or      ebx, 80070000h
0x18002b2c8  jmp     short loc_18002B348
0x18002b2ca  lea     rcx, [rsp+78h+var_30]; unsigned __int16 *
0x18002b2cf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b2d4  mov     [rsp+78h+arg_18], 0
0x18002b2e0  mov     [rsp+78h+var_48], esi
0x18002b2e4  mov     [rsp+78h+var_50], r14
0x18002b2e9  mov     [rsp+78h+var_58], edi
0x18002b2ed  mov     r9, rax
0x18002b2f0  xor     r8d, r8d; pReturnValue
0x18002b2f3  xor     edx, edx; nProcNum
0x18002b2f5  lea     rcx, stru_180039F20; pProxyInfo
0x18002b2fc  call    cs:__imp_NdrClientCall3
0x18002b303  nop     dword ptr [rax+rax+00h]
0x18002b308  mov     rbx, rax
0x18002b30b  mov     [rsp+78h+arg_18], rax
0x18002b313  mov     [rsp+78h+var_38], eax
0x18002b317  jmp     short loc_18002B348
0x18002b319  test    eax, eax
0x18002b31b  jle     short loc_18002B325
0x18002b31d  movzx   eax, ax
0x18002b320  or      eax, 80070000h
0x18002b325  mov     ebx, eax
0x18002b327  mov     [rsp+78h+var_38], eax
0x18002b32b  mov     r9d, eax
0x18002b32e  mov     r8d, [rsp+78h+arg_0]
0x18002b336  lea     rdx, aRpccreateloopb; "RpcCreateLoopbackSessionTransport(%d) t"...
0x18002b33d  mov     ecx, 8; int
0x18002b342  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b347  nop
0x18002b348  lea     rcx, [rsp+78h+var_30]; this
0x18002b34d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b352  mov     eax, ebx
0x18002b354  mov     rbx, [rsp+78h+arg_8]
0x18002b35c  add     rsp, 60h
0x18002b360  pop     r14
0x18002b362  pop     rdi
0x18002b363  pop     rsi
0x18002b364  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
