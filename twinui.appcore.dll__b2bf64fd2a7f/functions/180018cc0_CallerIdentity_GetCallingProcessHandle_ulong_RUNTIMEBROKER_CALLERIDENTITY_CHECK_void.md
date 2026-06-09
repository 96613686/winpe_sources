# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180018cc0`
- end: `0x180018dcc`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `268`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800206e8`
- `0x18007699c`
- `0x180076a58`
- `0x180076a7c`

## callees

- `0x180018cc0`
- `0x180019978`
- `0x18001cc38`
- `0x180022fb4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018d61`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d72`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180018cf6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180018cf6`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(unsigned int a1, int a2, HANDLE *a3)
{
  HRESULT v6; // eax
  int v7; // edi
  CallerIdentity *v8; // rcx
  void *v9; // rcx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *ppInterface; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface);
  v6 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( v6 != -2147417833 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v6,
        v11);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface);
      return (unsigned int)v7;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, a1, a3);
    if ( v7 < 0 )
    {
      v9 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return (unsigned int)v7;
    }
  }
  if ( a2 == 1
    && (CallerIdentity::_EnsureRuntimeBrokerPID(v8), GetProcessId(*a3) == CallerIdentity::g_dwRuntimeBrokerProcessId) )
  {
    CloseHandle(*a3);
    *a3 = 0;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface);
    return 2147500037LL;
  }
  else
  {
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface);
    return 0;
  }
}

```

## disassembly

```asm
0x180018cc0  push    rbx
0x180018cc2  push    rbp
0x180018cc3  push    rsi
0x180018cc4  push    rdi
0x180018cc5  sub     rsp, 28h
0x180018cc9  mov     ebp, ecx
0x180018ccb  mov     qword ptr [r8], 0
0x180018cd2  lea     rcx, [rsp+48h+ppInterface]
0x180018cd7  mov     [rsp+48h+ppInterface], 0
0x180018ce0  mov     rbx, r8
0x180018ce3  mov     esi, edx
0x180018ce5  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180018cea  lea     rdx, [rsp+48h+ppInterface]; ppInterface
0x180018cef  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180018cf6  call    cs:__imp_CoGetCallContext
0x180018cfc  mov     edi, eax
0x180018cfe  test    eax, eax
0x180018d00  js      short loc_180018D43
0x180018d02  mov     rcx, [rsp+48h+ppInterface]
0x180018d07  mov     r8, rbx
0x180018d0a  mov     edx, ebp
0x180018d0c  mov     rax, [rcx]
0x180018d0f  mov     rax, [rax+18h]
0x180018d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d18  mov     edi, eax
0x180018d1a  test    eax, eax
0x180018d1c  jns     short loc_180018D54
0x180018d1e  mov     rcx, [rsp+48h+ppInterface]
0x180018d23  test    rcx, rcx
0x180018d26  jz      loc_180018DC1
0x180018d2c  mov     [rsp+48h+ppInterface], 0
0x180018d35  mov     rdx, [rcx]
0x180018d38  mov     rax, [rdx+10h]
0x180018d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d41  jmp     short loc_180018DC1
0x180018d43  cmp     edi, 80010117h
0x180018d49  jnz     short loc_180018D9E
0x180018d4b  call    cs:__imp_GetCurrentProcess
0x180018d51  mov     [rbx], rax
0x180018d54  cmp     esi, 1
0x180018d57  jnz     short loc_180018D90
0x180018d59  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x180018d5e  mov     rcx, [rbx]; Process
0x180018d61  call    cs:__imp_GetProcessId
0x180018d67  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180018d6d  jnz     short loc_180018D90
0x180018d6f  mov     rcx, [rbx]; hObject
0x180018d72  call    cs:__imp_CloseHandle
0x180018d78  lea     rcx, [rsp+48h+ppInterface]
0x180018d7d  mov     qword ptr [rbx], 0
0x180018d84  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180018d89  mov     eax, 80004005h
0x180018d8e  jmp     short loc_180018DC3
0x180018d90  lea     rcx, [rsp+48h+ppInterface]
0x180018d95  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180018d9a  xor     eax, eax
0x180018d9c  jmp     short loc_180018DC3
0x180018d9e  mov     rcx, [rsp+48h]; this
0x180018da3  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180018daa  mov     r9d, edi; char *
0x180018dad  mov     edx, 58h ; 'X'; void *
0x180018db2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018db7  lea     rcx, [rsp+48h+ppInterface]
0x180018dbc  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180018dc1  mov     eax, edi
0x180018dc3  add     rsp, 28h
0x180018dc7  pop     rdi
0x180018dc8  pop     rsi
0x180018dc9  pop     rbp
0x180018dca  pop     rbx
0x180018dcb  retn
```
