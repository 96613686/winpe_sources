# WTSSetListenerSecurityA

- ea: `0x18000b330`
- end: `0x18000b3cf`
- name: `WTSSetListenerSecurityA`
- size: `159`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPSTR pListenerName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000b330`
- `0x18000b3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b36b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b36b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3b5`

## pseudocode

```c
BOOL __stdcall WTSSetListenerSecurityA(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPSTR pListenerName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  BOOL v6; // esi
  DWORD v10; // ecx
  DWORD LastError; // ebx
  LPWSTR pListenerNamea; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  pListenerNamea = 0;
  if ( !pListenerName )
  {
    v10 = 87;
LABEL_8:
    SetLastError(v10);
    return v6;
  }
  if ( (unsigned int)CopyStringA((__int64)pListenerName, &pListenerNamea, 0) )
    v6 = WTSSetListenerSecurityW(hServer, pReserved, Reserved, pListenerNamea, SecurityInformation, pSecurityDescriptor);
  else
    SetLastError(0x57u);
  if ( pListenerNamea )
  {
    LastError = GetLastError();
    LocalFree(pListenerNamea);
    v10 = LastError;
    goto LABEL_8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000b330  push    rbx
0x18000b332  push    rbp
0x18000b333  push    rsi
0x18000b334  push    r14
0x18000b336  sub     rsp, 38h
0x18000b33a  xor     esi, esi
0x18000b33c  mov     ebx, r8d
0x18000b33f  mov     [rsp+58h+pListenerName], rsi
0x18000b344  mov     rbp, rdx
0x18000b347  mov     r14, rcx
0x18000b34a  test    r9, r9
0x18000b34d  jnz     short loc_18000B354
0x18000b34f  lea     ecx, [rsi+57h]
0x18000b352  jmp     short loc_18000B3BD
0x18000b354  xor     r8d, r8d
0x18000b357  lea     rdx, [rsp+58h+pListenerName]
0x18000b35c  mov     rcx, r9
0x18000b35f  call    _CopyStringA
0x18000b364  test    eax, eax
0x18000b366  jnz     short loc_18000B373
0x18000b368  lea     ecx, [rax+57h]; dwErrCode
0x18000b36b  call    cs:__imp_SetLastError
0x18000b371  jmp     short loc_18000B3A0
0x18000b373  mov     rax, [rsp+58h+pSecurityDescriptor]
0x18000b37b  mov     r8d, ebx; Reserved
0x18000b37e  mov     r9, [rsp+58h+pListenerName]; pListenerName
0x18000b383  mov     rdx, rbp; pReserved
0x18000b386  mov     [rsp+58h+var_30], rax; pSecurityDescriptor
0x18000b38b  mov     rcx, r14; hServer
0x18000b38e  mov     eax, [rsp+58h+SecurityInformation]
0x18000b395  mov     [rsp+58h+var_38], eax; SecurityInformation
0x18000b399  call    WTSSetListenerSecurityW
0x18000b39e  mov     esi, eax
0x18000b3a0  cmp     [rsp+58h+pListenerName], 0
0x18000b3a6  jz      short loc_18000B3C3
0x18000b3a8  call    cs:__imp_GetLastError
0x18000b3ae  mov     rcx, [rsp+58h+pListenerName]; hMem
0x18000b3b3  mov     ebx, eax
0x18000b3b5  call    cs:__imp_LocalFree
0x18000b3bb  mov     ecx, ebx; dwErrCode
0x18000b3bd  call    cs:__imp_SetLastError
0x18000b3c3  mov     eax, esi
0x18000b3c5  add     rsp, 38h
0x18000b3c9  pop     r14
0x18000b3cb  pop     rsi
0x18000b3cc  pop     rbp
0x18000b3cd  pop     rbx
0x18000b3ce  retn
```
