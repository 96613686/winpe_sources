# RpcClientCapabilityCheck

- ea: `0x180018410`
- end: `0x180018502`
- name: `RpcClientCapabilityCheck`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180012ca0`
- `0x180018410`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800184c9`
- `ntdll!RtlNtStatusToDosError` at `0x1800184c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001847d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001847d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018473`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001845e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001845e`
- `RPCRT4!RpcRevertToSelfEx` at `0x180018494`
- `RPCRT4!RpcRevertToSelfEx` at `0x180018494`
- `RPCRT4!RpcImpersonateClient` at `0x18001843c`
- `RPCRT4!RpcImpersonateClient` at `0x18001843c`

## pseudocode

```c
__int64 __fastcall RpcClientCapabilityCheck(_WORD *a1)
{
  signed int v2; // ebx
  signed int v3; // eax
  bool v4; // cc
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  RPC_STATUS v7; // eax
  NTSTATUS v8; // eax
  char v10; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v10 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v3 = RpcImpersonateClient(0);
  v2 = v3;
  v4 = v3 <= 0;
  if ( !v3 )
  {
    v2 = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    v7 = RpcRevertToSelfEx(0);
    if ( v7 )
    {
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      else
        v2 = v7;
    }
    if ( v2 < 0 )
      goto LABEL_18;
    v8 = CapabilityCheck((__int64)TokenHandle, a1, &v10);
    if ( v8 >= 0 )
    {
      if ( !v10 )
        v2 = -2147024891;
      goto LABEL_18;
    }
    v3 = RtlNtStatusToDosError(v8);
    v2 = v3;
    v4 = v3 <= 0;
  }
  if ( !v4 )
    v2 = (unsigned __int16)v3 | 0x80070000;
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018410  mov     [rsp+arg_10], rbx
0x180018415  push    rsi
0x180018416  sub     rsp, 20h
0x18001841a  mov     [rsp+28h+TokenHandle], 0
0x180018423  mov     rsi, rcx
0x180018426  mov     [rsp+28h+arg_0], 0
0x18001842b  test    rcx, rcx
0x18001842e  jnz     short loc_18001843A
0x180018430  mov     ebx, 80070057h
0x180018435  jmp     loc_1800184F5
0x18001843a  xor     ecx, ecx; BindingHandle
0x18001843c  call    cs:__imp_RpcImpersonateClient
0x180018442  mov     ebx, eax
0x180018444  test    eax, eax
0x180018446  jz      short loc_18001845C
0x180018448  jle     loc_1800184E5
0x18001844e  movzx   ebx, ax
0x180018451  or      ebx, 80070000h
0x180018457  jmp     loc_1800184E5
0x18001845c  xor     ebx, ebx
0x18001845e  call    cs:__imp_GetCurrentThread
0x180018464  mov     rcx, rax; ThreadHandle
0x180018467  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001846c  lea     edx, [rbx+8]; DesiredAccess
0x18001846f  lea     r8d, [rbx+1]; OpenAsSelf
0x180018473  call    cs:__imp_OpenThreadToken
0x180018479  test    eax, eax
0x18001847b  jnz     short loc_180018492
0x18001847d  call    cs:__imp_GetLastError
0x180018483  mov     ebx, eax
0x180018485  test    eax, eax
0x180018487  jle     short loc_180018492
0x180018489  movzx   ebx, ax
0x18001848c  or      ebx, 80070000h
0x180018492  xor     ecx, ecx; BindingHandle
0x180018494  call    cs:__imp_RpcRevertToSelfEx
0x18001849a  test    eax, eax
0x18001849c  jz      short loc_1800184AD
0x18001849e  jg      short loc_1800184A4
0x1800184a0  mov     ebx, eax
0x1800184a2  jmp     short loc_1800184AD
0x1800184a4  movzx   ebx, ax
0x1800184a7  or      ebx, 80070000h
0x1800184ad  test    ebx, ebx
0x1800184af  js      short loc_1800184E5
0x1800184b1  mov     rcx, [rsp+28h+TokenHandle]
0x1800184b6  lea     r8, [rsp+28h+arg_0]
0x1800184bb  mov     rdx, rsi
0x1800184be  call    CapabilityCheck
0x1800184c3  test    eax, eax
0x1800184c5  jns     short loc_1800184D8
0x1800184c7  mov     ecx, eax; Status
0x1800184c9  call    cs:__imp_RtlNtStatusToDosError
0x1800184cf  mov     ebx, eax
0x1800184d1  test    eax, eax
0x1800184d3  jmp     loc_180018448
0x1800184d8  cmp     [rsp+28h+arg_0], 0
0x1800184dd  mov     eax, 80070005h
0x1800184e2  cmovz   ebx, eax
0x1800184e5  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800184ea  test    rcx, rcx
0x1800184ed  jz      short loc_1800184F5
0x1800184ef  call    cs:__imp_CloseHandle
0x1800184f5  mov     eax, ebx
0x1800184f7  mov     rbx, [rsp+28h+arg_10]
0x1800184fc  add     rsp, 20h
0x180018500  pop     rsi
0x180018501  retn
```
