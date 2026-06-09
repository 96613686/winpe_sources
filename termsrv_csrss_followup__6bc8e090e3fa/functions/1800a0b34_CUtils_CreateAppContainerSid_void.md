# CUtils::CreateAppContainerSid(void * *)

- ea: `0x1800a0b34`
- end: `0x1800a0c12`
- name: `?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a235c`
- `0x1800bfa4c`

## callees

- `0x180009940`
- `0x180033f60`
- `0x1800a0b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0bc2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a0bb2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a0bb2`

## string_xrefs

- `0x1800a0b69`: `ppAppContainerSid`
- `0x1800a0b5d`: `CUtils::CreateAppContainerSid`
- `0x1800a0be1`: `CUtils::CreateAppContainerSid`
- `0x1800a0beb`: `AllocateAndInitializeSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateAppContainerSid(PSID *pSid)
{
  signed int v1; // ebx
  signed int LastError; // eax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( pSid )
  {
    v1 = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, pSid) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
        _DbgPrintMessage(8, "AllocateAndInitializeSid failed: 0x%x in %s", v1, "CUtils::CreateAppContainerSid");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "ppAppContainerSid", "CUtils::CreateAppContainerSid");
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800a0b34  push    rbx
0x1800a0b36  sub     rsp, 70h
0x1800a0b3a  mov     rax, cs:__security_cookie
0x1800a0b41  xor     rax, rsp
0x1800a0b44  mov     [rsp+78h+var_10], rax
0x1800a0b49  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x1800a0b51  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x1800a0b58  test    rcx, rcx
0x1800a0b5b  jnz     short loc_1800A0B83
0x1800a0b5d  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x1800a0b64  mov     ecx, 8; int
0x1800a0b69  lea     r8, aPpappcontainer; "ppAppContainerSid"
0x1800a0b70  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800a0b77  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a0b7c  mov     ebx, 80070057h
0x1800a0b81  jmp     short loc_1800A0BFC
0x1800a0b83  xor     ebx, ebx
0x1800a0b85  mov     [rsp+78h+pSid], rcx; pSid
0x1800a0b8a  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x1800a0b8e  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x1800a0b93  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x1800a0b97  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x1800a0b9b  lea     r8d, [rbx+2]; nSubAuthority0
0x1800a0b9f  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x1800a0ba3  mov     dl, r8b; nSubAuthorityCount
0x1800a0ba6  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x1800a0baa  lea     r9d, [rbx+1]; nSubAuthority1
0x1800a0bae  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x1800a0bb2  call    cs:__imp_AllocateAndInitializeSid
0x1800a0bb9  nop     dword ptr [rax+rax+00h]
0x1800a0bbe  test    eax, eax
0x1800a0bc0  jnz     short loc_1800A0BFC
0x1800a0bc2  call    cs:__imp_GetLastError
0x1800a0bc9  nop     dword ptr [rax+rax+00h]
0x1800a0bce  mov     ebx, eax
0x1800a0bd0  test    eax, eax
0x1800a0bd2  jle     short loc_1800A0BDD
0x1800a0bd4  movzx   ebx, ax
0x1800a0bd7  or      ebx, 80070000h
0x1800a0bdd  test    ebx, ebx
0x1800a0bdf  jns     short loc_1800A0BFC
0x1800a0be1  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x1800a0be8  mov     r8d, ebx
0x1800a0beb  lea     rdx, aAllocateandini_2; "AllocateAndInitializeSid failed: 0x%x i"...
0x1800a0bf2  mov     ecx, 8; int
0x1800a0bf7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a0bfc  mov     eax, ebx
0x1800a0bfe  mov     rcx, [rsp+78h+var_10]
0x1800a0c03  xor     rcx, rsp; StackCookie
0x1800a0c06  call    __security_check_cookie
0x1800a0c0b  add     rsp, 70h
0x1800a0c0f  pop     rbx
0x1800a0c10  retn
```
