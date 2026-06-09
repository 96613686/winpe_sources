# CSID::Initialize(CSID::enumCSIDAuthority,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x18000afcc`
- end: `0x18000b059`
- name: `?Initialize@CSID@@QEAAXW4enumCSIDAuthority@1@EKKKKKKKK@Z`
- size: `141`
- prototype: `BOOL __fastcall(__int64, __int64, BYTE, DWORD, DWORD nSubAuthority1)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000af5c`
- `0x180010638`

## callees

- `0x18000afcc`
- `0x18000d038`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b038`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000b02e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000b02e`

## pseudocode

```c
BOOL __fastcall CSID::Initialize(__int64 a1, __int64 a2, BYTE a3, DWORD a4, DWORD nSubAuthority1)
{
  BOOL result; // eax
  DWORD LastError; // eax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_DWORD *)a1 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_QWORD *)(a1 + 8) = 0;
  result = AllocateAndInitializeSid(&pIdentifierAuthority, a3, a4, nSubAuthority1, 0, 0, 0, 0, 0, 0, (PSID *)(a1 + 8));
  if ( !result )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18000afcc  push    rbx
0x18000afce  sub     rsp, 70h
0x18000afd2  mov     rax, cs:__security_cookie
0x18000afd9  xor     rax, rsp
0x18000afdc  mov     [rsp+78h+var_10], rax
0x18000afe1  xor     ebx, ebx
0x18000afe3  mov     dword ptr [rcx], 1
0x18000afe9  lea     rax, [rcx+8]
0x18000afed  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x18000aff1  mov     [rsp+78h+pSid], rax; pSid
0x18000aff6  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x18000affb  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x18000afff  mov     r11d, r9d
0x18000b002  mov     r9d, [rsp+78h+nSubAuthority1]; nSubAuthority1
0x18000b00a  mov     dl, r8b; nSubAuthorityCount
0x18000b00d  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x18000b011  mov     r8d, r11d; nSubAuthority0
0x18000b014  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x18000b018  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x18000b01c  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x18000b020  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x18000b024  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 500h
0x18000b02b  mov     [rax], rbx
0x18000b02e  call    cs:__imp_AllocateAndInitializeSid
0x18000b034  test    eax, eax
0x18000b036  jnz     short loc_18000B046
0x18000b038  call    cs:__imp_GetLastError
0x18000b03e  mov     ecx, eax; int
0x18000b040  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000b046  mov     rcx, [rsp+78h+var_10]
0x18000b04b  xor     rcx, rsp; StackCookie
0x18000b04e  call    __security_check_cookie
0x18000b053  add     rsp, 70h
0x18000b057  pop     rbx
0x18000b058  retn
```
