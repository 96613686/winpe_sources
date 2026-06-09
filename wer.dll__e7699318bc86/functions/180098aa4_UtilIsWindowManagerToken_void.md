# UtilIsWindowManagerToken(void *)

- ea: `0x180098aa4`
- end: `0x180098b80`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `220`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f34c`

## callees

- `0x18000716c`
- `0x18002db8c`
- `0x180048d44`
- `0x18004ac6c`
- `0x180050db0`
- `0x180098aa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b45`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098b12`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098b12`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098b31`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098b31`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  PSID *pSid; // rax
  BOOL v2; // ebx
  unsigned int v3; // ebx
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  void *v8[3]; // [rsp+70h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  pSid = (PSID *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,>(
                   v8,
                   &SidToCheck);
  v2 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, pSid);
  utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,void *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,void *,>(v8);
  if ( v2 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = ERROR_HR_FROM_WIN32(LastError);
  }
  tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>(&SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x180098aa4  mov     [rsp-8+arg_0], rbx
0x180098aa9  mov     [rsp-8+arg_8], rdi
0x180098aae  push    rbp
0x180098aaf  lea     rbp, [rsp-57h]
0x180098ab4  sub     rsp, 0A0h
0x180098abb  mov     rax, cs:__security_cookie
0x180098ac2  xor     rax, rsp
0x180098ac5  mov     [rbp+57h+var_10], rax
0x180098ac9  xor     edi, edi
0x180098acb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180098ad1  lea     rdx, [rbp+57h+SidToCheck]
0x180098ad5  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180098ad8  lea     rcx, [rbp+57h+var_30]
0x180098adc  mov     [rbp+57h+SidToCheck], rdi
0x180098ae0  mov     [rbp+57h+IsMember], edi
0x180098ae3  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x180098ae8  mov     [rsp+0A0h+pSid], rax; pSid
0x180098aed  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x180098af1  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x180098af5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180098af9  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x180098afd  xor     r9d, r9d; nSubAuthority1
0x180098b00  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x180098b04  mov     dl, 2; nSubAuthorityCount
0x180098b06  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x180098b0a  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x180098b0e  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x180098b12  call    cs:__imp_AllocateAndInitializeSid
0x180098b18  lea     rcx, [rbp+57h+var_30]
0x180098b1c  mov     ebx, eax
0x180098b1e  call    ??1?$out_ptr_t@V?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>(void)
0x180098b23  test    ebx, ebx
0x180098b25  jz      short loc_180098B45
0x180098b27  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180098b2b  lea     r8, [rbp+57h+IsMember]; IsMember
0x180098b2f  xor     ecx, ecx; TokenHandle
0x180098b31  call    cs:__imp_CheckTokenMembership
0x180098b37  test    eax, eax
0x180098b39  jz      short loc_180098B45
0x180098b3b  cmp     [rbp+57h+IsMember], edi
0x180098b3e  mov     ebx, edi
0x180098b40  setz    bl
0x180098b43  jmp     short loc_180098B54
0x180098b45  call    cs:__imp_GetLastError
0x180098b4b  mov     ecx, eax; unsigned int
0x180098b4d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098b52  mov     ebx, eax
0x180098b54  lea     rcx, [rbp+57h+SidToCheck]
0x180098b58  call    ??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)
0x180098b5d  mov     eax, ebx
0x180098b5f  mov     rcx, [rbp+57h+var_10]
0x180098b63  xor     rcx, rsp; StackCookie
0x180098b66  call    __security_check_cookie
0x180098b6b  lea     r11, [rsp+0A0h+var_s0]
0x180098b73  mov     rbx, [r11+10h]
0x180098b77  mov     rdi, [r11+18h]
0x180098b7b  mov     rsp, r11
0x180098b7e  pop     rbp
0x180098b7f  retn
```
