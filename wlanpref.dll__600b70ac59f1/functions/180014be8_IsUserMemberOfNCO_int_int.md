# IsUserMemberOfNCO(int *,int *)

- ea: `0x180014be8`
- end: `0x180014ce2`
- name: `?IsUserMemberOfNCO@@YAJPEAH0@Z`
- size: `250`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ef8`

## callees

- `0x180014be8`
- `0x180014ce8`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c89`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014cb9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014cb9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014c7f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014c7f`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfNCO(int *a1, int *a2)
{
  int *v4; // r8
  signed int LastError; // eax
  signed int v6; // ebx
  PSID pSid1; // [rsp+60h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-11h] BYREF
  char v9; // [rsp+70h] [rbp-9h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = &v9;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !a1 )
    return 2147942487LL;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Cu, 0, 0, 0, 0, 0, 0, &pSid1) )
    goto LABEL_7;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
LABEL_7:
    v6 = IsUserMemberOfSID(pSid1, a1, v4);
  if ( pSid1 )
    FreeSid(pSid1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014be8  mov     [rsp-8+arg_8], rbx
0x180014bed  mov     [rsp-8+arg_10], rdi
0x180014bf2  push    rbp
0x180014bf3  lea     rbp, [rsp-57h]
0x180014bf8  sub     rsp, 0D0h
0x180014bff  mov     rax, cs:__security_cookie
0x180014c06  xor     rax, rsp
0x180014c09  mov     [rbp+57h+var_10], rax
0x180014c0d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x180014c14  lea     rax, [rbp+57h+var_60]
0x180014c18  mov     [rbp+57h+pSid1], rax
0x180014c1c  mov     rdi, rcx
0x180014c1f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180014c25  test    rcx, rcx
0x180014c28  jnz     short loc_180014C34
0x180014c2a  mov     eax, 80070057h
0x180014c2f  jmp     loc_180014CC1
0x180014c34  lea     rax, [rbp+57h+pSid1]
0x180014c38  mov     r9d, 22Ch; nSubAuthority1
0x180014c3e  mov     [rsp+0D0h+pSid], rax; pSid
0x180014c43  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180014c47  mov     [rsp+0D0h+nSubAuthority7], 0; nSubAuthority7
0x180014c4f  mov     r8d, 20h ; ' '; nSubAuthority0
0x180014c55  mov     [rsp+0D0h+nSubAuthority6], 0; nSubAuthority6
0x180014c5d  mov     dl, 2; nSubAuthorityCount
0x180014c5f  mov     [rsp+0D0h+nSubAuthority5], 0; nSubAuthority5
0x180014c67  mov     [rsp+0D0h+nSubAuthority4], 0; nSubAuthority4
0x180014c6f  mov     [rsp+0D0h+nSubAuthority3], 0; nSubAuthority3
0x180014c77  mov     [rsp+0D0h+nSubAuthority2], 0; nSubAuthority2
0x180014c7f  call    cs:__imp_AllocateAndInitializeSid
0x180014c85  test    eax, eax
0x180014c87  jnz     short loc_180014CA2
0x180014c89  call    cs:__imp_GetLastError
0x180014c8f  mov     ebx, eax
0x180014c91  test    eax, eax
0x180014c93  jle     short loc_180014C9E
0x180014c95  movzx   ebx, ax
0x180014c98  or      ebx, 80070000h
0x180014c9e  test    ebx, ebx
0x180014ca0  js      short loc_180014CB0
0x180014ca2  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180014ca6  mov     rdx, rdi; int *
0x180014ca9  call    ?IsUserMemberOfSID@@YAJPEAXPEAH1@Z; IsUserMemberOfSID(void *,int *,int *)
0x180014cae  mov     ebx, eax
0x180014cb0  mov     rcx, [rbp+57h+pSid1]; pSid
0x180014cb4  test    rcx, rcx
0x180014cb7  jz      short loc_180014CBF
0x180014cb9  call    cs:__imp_FreeSid
0x180014cbf  mov     eax, ebx
0x180014cc1  mov     rcx, [rbp+57h+var_10]
0x180014cc5  xor     rcx, rsp; StackCookie
0x180014cc8  call    __security_check_cookie
0x180014ccd  lea     r11, [rsp+0D0h+var_s0]
0x180014cd5  mov     rbx, [r11+18h]
0x180014cd9  mov     rdi, [r11+20h]
0x180014cdd  mov     rsp, r11
0x180014ce0  pop     rbp
0x180014ce1  retn
```
