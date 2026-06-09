# AdjustTokenIntegrity(ulong,void *)

- ea: `0x1800169ac`
- end: `0x180016a83`
- name: `?AdjustTokenIntegrity@@YAJKPEAX@Z`
- size: `215`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016b04`

## callees

- `0x180002610`
- `0x1800092b8`
- `0x1800169ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016a5c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016a5c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016a0d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016a0d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180016a43`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180016a43`

## pseudocode

```c
__int64 __fastcall AdjustTokenIntegrity(DWORD nSubAuthority0, HANDLE TokenHandle)
{
  int Error; // ebx
  PSID pSid; // [rsp+60h] [rbp+17h] BYREF
  _QWORD TokenInformation[2]; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+2Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, nSubAuthority0, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    TokenInformation[1] = 96;
    TokenInformation[0] = pSid;
    if ( SetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x10u) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    FreeSid(pSid);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800169ac  mov     [rsp-8+arg_10], rbx
0x1800169b1  push    rbp
0x1800169b2  push    rsi
0x1800169b3  push    rdi
0x1800169b4  lea     rbp, [rsp-47h]
0x1800169b9  sub     rsp, 90h
0x1800169c0  mov     rax, cs:__security_cookie
0x1800169c7  xor     rax, rsp
0x1800169ca  mov     [rbp+57h+var_20], rax
0x1800169ce  xor     esi, esi
0x1800169d0  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x1800169d6  lea     rax, [rbp+57h+var_40]
0x1800169da  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800169dd  mov     [rsp+0A0h+pSid], rax; pSid
0x1800169e2  mov     rdi, rdx
0x1800169e5  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1800169e9  mov     r8d, ecx; nSubAuthority0
0x1800169ec  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x1800169f0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800169f4  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x1800169f8  xor     r9d, r9d; nSubAuthority1
0x1800169fb  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x1800169ff  mov     dl, 1; nSubAuthorityCount
0x180016a01  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x180016a05  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x180016a09  mov     [rbp+57h+var_40], rsi
0x180016a0d  call    cs:__imp_AllocateAndInitializeSid
0x180016a13  test    eax, eax
0x180016a15  jnz     short loc_180016A22
0x180016a17  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016a1c  mov     ebx, eax
0x180016a1e  test    eax, eax
0x180016a20  js      short loc_180016A62
0x180016a22  mov     rax, [rbp+57h+var_40]
0x180016a26  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180016a2a  mov     r9d, 10h; TokenInformationLength
0x180016a30  mov     [rbp+57h+var_30], 60h ; '`'
0x180016a38  mov     rcx, rdi; TokenHandle
0x180016a3b  mov     [rbp+57h+TokenInformation], rax
0x180016a3f  lea     edx, [r9+9]; TokenInformationClass
0x180016a43  call    cs:__imp_SetTokenInformation
0x180016a49  test    eax, eax
0x180016a4b  jz      short loc_180016A51
0x180016a4d  mov     ebx, esi
0x180016a4f  jmp     short loc_180016A58
0x180016a51  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016a56  mov     ebx, eax
0x180016a58  mov     rcx, [rbp+57h+var_40]; pSid
0x180016a5c  call    cs:__imp_FreeSid
0x180016a62  mov     eax, ebx
0x180016a64  mov     rcx, [rbp+57h+var_20]
0x180016a68  xor     rcx, rsp; StackCookie
0x180016a6b  call    __security_check_cookie
0x180016a70  mov     rbx, [rsp+0A0h+arg_10]
0x180016a78  add     rsp, 90h
0x180016a7f  pop     rdi
0x180016a80  pop     rsi
0x180016a81  pop     rbp
0x180016a82  retn
```
