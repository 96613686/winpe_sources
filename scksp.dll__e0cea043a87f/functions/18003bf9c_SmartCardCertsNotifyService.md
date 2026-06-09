# SmartCardCertsNotifyService

- ea: `0x18003bf9c`
- end: `0x18003c12c`
- name: `SmartCardCertsNotifyService`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025ff0`
- `0x180027054`

## callees

- `0x18003bf9c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfe8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c10e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c10e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bfff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c017`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c02f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bfff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c017`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c02f`
- `KERNEL32!LoadLibraryExA` at `0x18003bfd5`
- `KERNEL32!LoadLibraryExA` at `0x18003bfd5`
- `RPCRT4!NdrClientCall3` at `0x18003c0b1`
- `RPCRT4!NdrClientCall3` at `0x18003c0b1`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003cc73`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003cc73`

## string_xrefs

- `0x18003bfce`: `rpcrt4.dll`
- `0x18003bff5`: `RpcBindingCreateW`

## pseudocode

```c
__int64 __fastcall SmartCardCertsNotifyService(__int64 a1)
{
  FARPROC v2; // rsi
  HMODULE Library; // rax
  HMODULE v4; // rdi
  DWORD Pointer; // ebx
  FARPROC ProcAddress; // rbx
  FARPROC v7; // r14
  CLIENT_CALL_RETURN v8; // rax
  __int64 v10; // [rsp+78h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+80h] [rbp+18h]

  v10 = 0;
  v2 = 0;
  Library = LoadLibraryExA("rpcrt4.dll", 0, 0);
  v4 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "RpcBindingCreateW")) != 0
    && (v7 = GetProcAddress(v4, "RpcBindingBind")) != 0
    && (v2 = GetProcAddress(v4, "RpcBindingFree")) != 0 )
  {
    Pointer = ((__int64 (__fastcall *)(struct _RPC_BINDING_HANDLE_TEMPLATE_V1_W *, struct _RPC_BINDING_HANDLE_SECURITY_V1_W *, struct _RPC_BINDING_HANDLE_OPTIONS_V1 *, __int64 *))ProcAddress)(
                &ROOTRPC_Template,
                &ROOTRPC_Security,
                &ROOTRPC_Options,
                &v10);
    if ( !Pointer )
    {
      Pointer = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))v7)(0, v10, qword_18003F0F0);
      if ( !Pointer )
      {
        v11.Simple = 0;
        v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v10, a1).Pointer;
        Pointer = (DWORD)v8.Pointer;
        v11.Pointer = v8.Pointer;
      }
    }
  }
  else
  {
    Pointer = GetLastError();
  }
  if ( v10 )
  {
    ((void (__fastcall *)(__int64 *))v2)(&v10);
    if ( v10 )
      ((void (__fastcall *)(__int64 *))v2)(&v10);
  }
  if ( v4 )
    FreeLibrary(v4);
  return Pointer;
}

```

## disassembly

```asm
0x18003bf9c  mov     rax, rsp
0x18003bf9f  mov     [rax+8], rbx
0x18003bfa3  mov     [rax+20h], rsi
0x18003bfa7  push    rdi
0x18003bfa8  push    r14
0x18003bfaa  push    r15
0x18003bfac  sub     rsp, 50h
0x18003bfb0  mov     r15, rcx
0x18003bfb3  mov     qword ptr [rax+10h], 0
0x18003bfbb  mov     qword ptr [rax-30h], 0
0x18003bfc3  xor     esi, esi
0x18003bfc5  mov     [rax-28h], rsi
0x18003bfc9  xor     r8d, r8d; dwFlags
0x18003bfcc  xor     edx, edx; hFile
0x18003bfce  lea     rcx, LibFileName; "rpcrt4.dll"
0x18003bfd5  call    cs:__imp_LoadLibraryExA
0x18003bfdb  mov     rdi, rax
0x18003bfde  mov     [rsp+68h+var_30], rax
0x18003bfe3  test    rax, rax
0x18003bfe6  jnz     short loc_18003BFF5
0x18003bfe8  call    cs:__imp_GetLastError
0x18003bfee  mov     ebx, eax
0x18003bff0  jmp     loc_18003C0C2
0x18003bff5  lea     rdx, aRpcbindingcrea; "RpcBindingCreateW"
0x18003bffc  mov     rcx, rdi; hModule
0x18003bfff  call    cs:__imp_GetProcAddress
0x18003c005  mov     rbx, rax
0x18003c008  test    rax, rax
0x18003c00b  jz      short loc_18003BFE8
0x18003c00d  lea     rdx, aRpcbindingbind; "RpcBindingBind"
0x18003c014  mov     rcx, rdi; hModule
0x18003c017  call    cs:__imp_GetProcAddress
0x18003c01d  mov     r14, rax
0x18003c020  test    rax, rax
0x18003c023  jz      short loc_18003BFE8
0x18003c025  lea     rdx, aRpcbindingfree; "RpcBindingFree"
0x18003c02c  mov     rcx, rdi; hModule
0x18003c02f  call    cs:__imp_GetProcAddress
0x18003c035  mov     rsi, rax
0x18003c038  mov     [rsp+68h+var_28], rax
0x18003c03d  test    rax, rax
0x18003c040  jz      short loc_18003BFE8
0x18003c042  lea     r9, [rsp+68h+arg_8]
0x18003c047  lea     r8, ?ROOTRPC_Options@@3U_RPC_BINDING_HANDLE_OPTIONS_V1@@A; _RPC_BINDING_HANDLE_OPTIONS_V1 ROOTRPC_Options
0x18003c04e  lea     rdx, ?ROOTRPC_Security@@3U_RPC_BINDING_HANDLE_SECURITY_V1_W@@A; _RPC_BINDING_HANDLE_SECURITY_V1_W ROOTRPC_Security
0x18003c055  lea     rcx, ?ROOTRPC_Template@@3U_RPC_BINDING_HANDLE_TEMPLATE_V1_W@@A; _RPC_BINDING_HANDLE_TEMPLATE_V1_W ROOTRPC_Template
0x18003c05c  mov     rax, rbx
0x18003c05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c064  mov     ebx, eax
0x18003c066  mov     [rsp+68h+var_38], eax
0x18003c06a  test    eax, eax
0x18003c06c  jnz     short loc_18003C0C6
0x18003c06e  lea     r8, qword_18003F0F0
0x18003c075  mov     rdx, [rsp+68h+arg_8]
0x18003c07a  xor     ecx, ecx
0x18003c07c  mov     rax, r14
0x18003c07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c084  mov     ebx, eax
0x18003c086  mov     [rsp+68h+var_38], eax
0x18003c08a  test    eax, eax
0x18003c08c  jnz     short loc_18003C0C6
0x18003c08e  mov     [rsp+68h+arg_10], 0
0x18003c09a  mov     [rsp+68h+var_48], r15
0x18003c09f  mov     r9, [rsp+68h+arg_8]
0x18003c0a4  xor     r8d, r8d; pReturnValue
0x18003c0a7  lea     edx, [rax+1]; nProcNum
0x18003c0aa  lea     rcx, pProxyInfo; pProxyInfo
0x18003c0b1  call    cs:__imp_NdrClientCall3
0x18003c0b7  mov     rbx, rax
0x18003c0ba  mov     [rsp+68h+arg_10], rax
0x18003c0c2  mov     [rsp+68h+var_38], eax
0x18003c0c6  jmp     short loc_18003C0D8
0x18003c0c8  mov     ebx, eax
0x18003c0ca  mov     [rsp+68h+var_38], eax
0x18003c0ce  mov     rdi, [rsp+68h+var_30]
0x18003c0d3  mov     rsi, [rsp+68h+var_28]
0x18003c0d8  mov     rax, [rsp+68h+arg_8]
0x18003c0dd  test    rax, rax
0x18003c0e0  jz      short loc_18003C106
0x18003c0e2  lea     rcx, [rsp+68h+arg_8]
0x18003c0e7  mov     rax, rsi
0x18003c0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0ef  mov     rax, [rsp+68h+arg_8]
0x18003c0f4  test    rax, rax
0x18003c0f7  jz      short loc_18003C106
0x18003c0f9  lea     rcx, [rsp+68h+arg_8]
0x18003c0fe  mov     rax, rsi
0x18003c101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c106  test    rdi, rdi
0x18003c109  jz      short loc_18003C114
0x18003c10b  mov     rcx, rdi; hLibModule
0x18003c10e  call    cs:__imp_FreeLibrary
0x18003c114  mov     eax, ebx
0x18003c116  lea     r11, [rsp+68h+var_18]
0x18003c11b  mov     rbx, [r11+20h]
0x18003c11f  mov     rsi, [r11+38h]
0x18003c123  mov     rsp, r11
0x18003c126  pop     r15
0x18003c128  pop     r14
0x18003c12a  pop     rdi
0x18003c12b  retn
0x18003cc65  push    rbp
0x18003cc67  sub     rsp, 30h
0x18003cc6b  mov     rbp, rdx
0x18003cc6e  mov     rcx, [rcx]
0x18003cc71  mov     ecx, [rcx]; ExceptionCode
0x18003cc73  call    cs:__imp_I_RpcExceptionFilter
0x18003cc79  nop
0x18003cc7a  add     rsp, 30h
0x18003cc7e  pop     rbp
0x18003cc7f  retn
```
