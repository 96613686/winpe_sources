# QueryServiceObjectSecurity

- ea: `0x18003a170`
- end: `0x18003a21a`
- name: `QueryServiceObjectSecurity`
- size: `170`
- prototype: `BOOL __stdcall(SC_HANDLE hService, SECURITY_INFORMATION dwSecurityInformation, PSECURITY_DESCRIPTOR lpSecurityDescriptor, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18003a170`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a1f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a1f1`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003a1fe`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003a1fe`
- `RPCRT4!NdrClientCall2` at `0x18003a1ca`
- `RPCRT4!NdrClientCall2` at `0x18003a1ca`

## pseudocode

```c
BOOL __stdcall QueryServiceObjectSecurity(
        SC_HANDLE hService,
        SECURITY_INFORMATION dwSecurityInformation,
        PSECURITY_DESCRIPTOR lpSecurityDescriptor,
        DWORD cbBufSize,
        LPDWORD pcbBytesNeeded)
{
  PSECURITY_DESCRIPTOR v5; // rbx
  CLIENT_CALL_RETURN v6; // rax
  DWORD Pointer; // ecx
  _DWORD v9[2]; // [rsp+40h] [rbp-18h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+48h] [rbp-10h]

  v5 = lpSecurityDescriptor;
  v9[0] = 0;
  if ( !lpSecurityDescriptor )
  {
    lpSecurityDescriptor = v9;
    if ( cbBufSize )
      lpSecurityDescriptor = 0;
  }
  v10.Simple = 0;
  v6.Pointer = NdrClientCall2(
                 &pStubDescriptor,
                 &byte_180060064,
                 hService,
                 dwSecurityInformation,
                 lpSecurityDescriptor,
                 cbBufSize,
                 pcbBytesNeeded).Pointer;
  v10.Pointer = v6.Pointer;
  v9[1] = v6.Pointer;
  if ( LODWORD(v6.Pointer) )
  {
    Pointer = (DWORD)v6.Pointer;
LABEL_6:
    SetLastError(Pointer);
    return 0;
  }
  if ( !IsValidSecurityDescriptor(v5) )
  {
    Pointer = 1338;
    goto LABEL_6;
  }
  return 1;
}

```

## disassembly

```asm
0x18003a170  mov     [rsp+arg_10], r8
0x18003a175  push    rbx
0x18003a176  sub     rsp, 50h
0x18003a17a  mov     rbx, r8
0x18003a17d  mov     [rsp+58h+var_18], 0
0x18003a185  test    r8, r8
0x18003a188  jnz     short loc_18003A196
0x18003a18a  lea     r8, [rsp+58h+var_18]
0x18003a18f  test    r9d, r9d
0x18003a192  cmovnz  r8, rbx
0x18003a196  mov     [rsp+58h+var_10], 0
0x18003a19f  mov     rax, [rsp+58h+pcbBytesNeeded]
0x18003a1a7  mov     [rsp+58h+var_28], rax
0x18003a1ac  mov     [rsp+58h+var_30], r9d
0x18003a1b1  mov     [rsp+58h+var_38], r8
0x18003a1b6  mov     r9d, edx
0x18003a1b9  mov     r8, rcx
0x18003a1bc  lea     rdx, byte_180060064; pFormat
0x18003a1c3  lea     rcx, pStubDescriptor; pStubDescriptor
0x18003a1ca  call    cs:__imp_NdrClientCall2
0x18003a1d0  mov     [rsp+58h+var_10], rax
0x18003a1d5  mov     [rsp+58h+var_14], eax
0x18003a1d9  jmp     short loc_18003A1EB
0x18003a1db  mov     ecx, eax; unsigned int
0x18003a1dd  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18003a1e2  mov     [rsp+58h+var_14], eax
0x18003a1e6  mov     rbx, [rsp+58h+arg_10]
0x18003a1eb  test    eax, eax
0x18003a1ed  jz      short loc_18003A1FB
0x18003a1ef  mov     ecx, eax; dwErrCode
0x18003a1f1  call    cs:__imp_SetLastError
0x18003a1f7  xor     eax, eax
0x18003a1f9  jmp     short loc_18003A214
0x18003a1fb  mov     rcx, rbx; pSecurityDescriptor
0x18003a1fe  call    cs:__imp_IsValidSecurityDescriptor
0x18003a204  test    eax, eax
0x18003a206  jnz     short loc_18003A20F
0x18003a208  mov     ecx, 53Ah
0x18003a20d  jmp     short loc_18003A1F1
0x18003a20f  mov     eax, 1
0x18003a214  add     rsp, 50h
0x18003a218  pop     rbx
0x18003a219  retn
0x180050468  push    rbp
0x18005046a  sub     rsp, 40h
0x18005046e  mov     rbp, rdx
0x180050471  mov     rcx, [rcx]
0x180050474  mov     ecx, [rcx]; ExceptionCode
0x180050476  call    cs:__imp_I_RpcExceptionFilter
0x18005047c  nop
0x18005047d  add     rsp, 40h
0x180050481  pop     rbp
0x180050482  retn
```
