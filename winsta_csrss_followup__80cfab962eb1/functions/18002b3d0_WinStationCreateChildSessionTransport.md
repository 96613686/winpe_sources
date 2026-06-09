# WinStationCreateChildSessionTransport

- ea: `0x18002b3d0`
- end: `0x18002b4c8`
- name: `WinStationCreateChildSessionTransport`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002b258`
- `0x18002b36c`
- `0x18002b3d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b425`
- `RPCRT4!NdrClientCall3` at `0x18002b46f`
- `RPCRT4!NdrClientCall3` at `0x18002b46f`

## string_xrefs

- `0x18002b49e`: `RpcCreateChildSessionTransport threw an exception: 0x%x`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 7u, 0, v6, a1, v8).Pointer;
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
0x18002b3d0  mov     [rsp+arg_0], rbx
0x18002b3d5  push    rdi
0x18002b3d6  sub     rsp, 50h
0x18002b3da  mov     ebx, edx
0x18002b3dc  mov     rdi, rcx
0x18002b3df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18002b3e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18002b3eb  test    al, al
0x18002b3ed  jz      short loc_18002B406
0x18002b3ef  mov     r8d, ebx
0x18002b3f2  mov     rdx, rdi
0x18002b3f5  mov     ecx, 7
0x18002b3fa  call    ?WinStationCreateLoopbackSessionTransport@@YAJW4_SESSIONTYPE@@PEAGK@Z; WinStationCreateLoopbackSessionTransport(_SESSIONTYPE,ushort *,ulong)
0x18002b3ff  mov     ebx, eax
0x18002b401  jmp     loc_18002B4BA
0x18002b406  xor     edx, edx; void *
0x18002b408  lea     r8d, [rdx+1]; int
0x18002b40c  lea     rcx, [rsp+58h+var_20]; this
0x18002b411  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002b416  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b41b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b420  test    rax, rax
0x18002b423  jnz     short loc_18002B442
0x18002b425  call    cs:__imp_GetLastError
0x18002b42c  nop     dword ptr [rax+rax+00h]
0x18002b431  mov     ebx, eax
0x18002b433  test    eax, eax
0x18002b435  jle     short loc_18002B4B0
0x18002b437  movzx   ebx, ax
0x18002b43a  or      ebx, 80070000h
0x18002b440  jmp     short loc_18002B4B0
0x18002b442  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b447  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b44c  mov     [rsp+58h+arg_10], 0
0x18002b455  mov     [rsp+58h+var_30], ebx
0x18002b459  mov     [rsp+58h+var_38], rdi
0x18002b45e  mov     r9, rax
0x18002b461  xor     r8d, r8d; pReturnValue
0x18002b464  lea     edx, [r8+7]; nProcNum
0x18002b468  lea     rcx, stru_180035140; pProxyInfo
0x18002b46f  call    cs:__imp_NdrClientCall3
0x18002b476  nop     dword ptr [rax+rax+00h]
0x18002b47b  mov     rbx, rax
0x18002b47e  mov     [rsp+58h+arg_10], rax
0x18002b483  mov     [rsp+58h+var_28], eax
0x18002b487  jmp     short loc_18002B4B0
0x18002b489  test    eax, eax
0x18002b48b  jle     short loc_18002B495
0x18002b48d  movzx   eax, ax
0x18002b490  or      eax, 80070000h
0x18002b495  mov     ebx, eax
0x18002b497  mov     [rsp+58h+var_28], eax
0x18002b49b  mov     r8d, eax
0x18002b49e  lea     rdx, aRpccreatechild; "RpcCreateChildSessionTransport threw an"...
0x18002b4a5  mov     ecx, 8; int
0x18002b4aa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b4af  nop
0x18002b4b0  lea     rcx, [rsp+58h+var_20]; this
0x18002b4b5  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b4ba  mov     eax, ebx
0x18002b4bc  mov     rbx, [rsp+58h+arg_0]
0x18002b4c1  add     rsp, 50h
0x18002b4c5  pop     rdi
0x18002b4c6  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
