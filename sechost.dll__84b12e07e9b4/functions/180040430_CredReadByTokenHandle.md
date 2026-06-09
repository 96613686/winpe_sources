# CredReadByTokenHandle

- ea: `0x180040430`
- end: `0x180040531`
- name: `CredReadByTokenHandle`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000f6d0`
- `0x180015c1c`
- `0x180015c70`
- `0x180040430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040518`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800404fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004050c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800404fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004050c`
- `RPCRT4!NdrClientCall3` at `0x1800404b4`
- `RPCRT4!NdrClientCall3` at `0x1800404b4`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800506da`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800506da`

## pseudocode

```c
__int64 __fastcall CredReadByTokenHandle(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  DWORD v8; // ebx
  DWORD CurrentProcessId; // eax
  HLOCAL hMem; // [rsp+58h] [rbp-40h] BYREF
  HLOCAL v12; // [rsp+60h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+68h] [rbp-30h]

  v12 = 0;
  hMem = 0;
  v8 = CredpAllocStrFromStr(3, a2, 0, &hMem);
  if ( !v8 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v13.Simple = 0;
    v13.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0,
                    0x5Cu,
                    0,
                    0,
                    a1,
                    CurrentProcessId,
                    hMem,
                    a3,
                    a4,
                    &v12).Pointer;
    v8 = CredpNtStatusToWinStatus(LODWORD(v13.Pointer));
    if ( !v8 )
      v8 = CredpConvertCredential(3, 2, v12, a5);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v12 )
    LocalFree(v12);
  if ( !v8 )
    return 1;
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x180040430  push    rbx
0x180040432  push    rsi
0x180040433  push    rdi
0x180040434  push    r14
0x180040436  sub     rsp, 78h
0x18004043a  mov     edi, r9d
0x18004043d  mov     esi, r8d
0x180040440  mov     r14, rcx
0x180040443  mov     [rsp+98h+var_38], 0
0x18004044c  mov     [rsp+98h+hMem], 0
0x180040455  lea     r9, [rsp+98h+hMem]
0x18004045a  xor     r8d, r8d
0x18004045d  lea     ecx, [r8+3]
0x180040461  call    CredpAllocStrFromStr
0x180040466  mov     ebx, eax
0x180040468  test    eax, eax
0x18004046a  jnz     loc_1800404F2
0x180040470  call    cs:__imp_GetCurrentProcessId
0x180040476  mov     [rsp+98h+var_30], 0
0x18004047f  lea     rcx, [rsp+98h+var_38]
0x180040484  mov     [rsp+98h+var_50], rcx
0x180040489  mov     [rsp+98h+var_58], edi
0x18004048d  mov     [rsp+98h+var_60], esi
0x180040491  mov     rcx, [rsp+98h+hMem]
0x180040496  mov     [rsp+98h+var_68], rcx
0x18004049b  mov     [rsp+98h+var_70], eax
0x18004049f  mov     [rsp+98h+var_78], r14
0x1800404a4  xor     r9d, r9d
0x1800404a7  xor     r8d, r8d; pReturnValue
0x1800404aa  lea     edx, [rbx+5Ch]; nProcNum
0x1800404ad  lea     rcx, stru_1800524F0; pProxyInfo
0x1800404b4  call    cs:__imp_NdrClientCall3
0x1800404ba  mov     [rsp+98h+var_30], rax
0x1800404bf  mov     ecx, eax
0x1800404c1  call    CredpNtStatusToWinStatus
0x1800404c6  mov     ebx, eax
0x1800404c8  mov     [rsp+98h+var_48], eax
0x1800404cc  jmp     short loc_1800404D4
0x1800404ce  mov     ebx, eax
0x1800404d0  mov     [rsp+98h+var_48], eax
0x1800404d4  test    ebx, ebx
0x1800404d6  jnz     short loc_1800404F2
0x1800404d8  mov     r9, [rsp+98h+arg_20]
0x1800404e0  mov     r8, [rsp+98h+var_38]
0x1800404e5  lea     edx, [rbx+2]
0x1800404e8  lea     ecx, [rbx+3]
0x1800404eb  call    CredpConvertCredential
0x1800404f0  mov     ebx, eax
0x1800404f2  mov     rcx, [rsp+98h+hMem]; hMem
0x1800404f7  test    rcx, rcx
0x1800404fa  jz      short loc_180040502
0x1800404fc  call    cs:__imp_LocalFree
0x180040502  mov     rcx, [rsp+98h+var_38]; hMem
0x180040507  test    rcx, rcx
0x18004050a  jz      short loc_180040512
0x18004050c  call    cs:__imp_LocalFree
0x180040512  test    ebx, ebx
0x180040514  jz      short loc_180040522
0x180040516  mov     ecx, ebx; dwErrCode
0x180040518  call    cs:__imp_SetLastError
0x18004051e  xor     eax, eax
0x180040520  jmp     short loc_180040527
0x180040522  mov     eax, 1
0x180040527  add     rsp, 78h
0x18004052b  pop     r14
0x18004052d  pop     rdi
0x18004052e  pop     rsi
0x18004052f  pop     rbx
0x180040530  retn
0x1800506cc  push    rbp
0x1800506ce  sub     rsp, 50h
0x1800506d2  mov     rbp, rdx
0x1800506d5  mov     rcx, [rcx]
0x1800506d8  mov     ecx, [rcx]; ExceptionCode
0x1800506da  call    cs:__imp_I_RpcExceptionFilter
0x1800506e0  nop
0x1800506e1  add     rsp, 50h
0x1800506e5  pop     rbp
0x1800506e6  retn
```
