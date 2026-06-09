# UtilIsWindowManagerToken(void *)

- ea: `0x18009d00c`
- end: `0x18009d0fb`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `239`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030de4`

## callees

- `0x18001c368`
- `0x18002f63c`
- `0x180043178`
- `0x18004cbe8`
- `0x180053300`
- `0x18009d00c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d0b9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009d07a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009d07a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d09f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d09f`

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
  _BYTE v8[24]; // [rsp+70h] [rbp+27h] BYREF
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
0x18009d00c  mov     [rsp-8+arg_0], rbx
0x18009d011  mov     [rsp-8+arg_8], rdi
0x18009d016  push    rbp
0x18009d017  lea     rbp, [rsp-57h]
0x18009d01c  sub     rsp, 0A0h
0x18009d023  mov     rax, cs:__security_cookie
0x18009d02a  xor     rax, rsp
0x18009d02d  mov     [rbp+57h+var_10], rax
0x18009d031  xor     edi, edi
0x18009d033  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18009d039  lea     rdx, [rbp+57h+SidToCheck]
0x18009d03d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18009d040  lea     rcx, [rbp+57h+var_30]
0x18009d044  mov     [rbp+57h+SidToCheck], rdi
0x18009d048  mov     [rbp+57h+IsMember], edi
0x18009d04b  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x18009d050  mov     [rsp+0A0h+pSid], rax; pSid
0x18009d055  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x18009d059  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18009d05d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18009d061  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18009d065  xor     r9d, r9d; nSubAuthority1
0x18009d068  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18009d06c  mov     dl, 2; nSubAuthorityCount
0x18009d06e  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18009d072  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18009d076  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18009d07a  call    cs:__imp_AllocateAndInitializeSid
0x18009d081  nop     dword ptr [rax+rax+00h]
0x18009d086  lea     rcx, [rbp+57h+var_30]
0x18009d08a  mov     ebx, eax
0x18009d08c  call    ??1?$out_ptr_t@V?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>(void)
0x18009d091  test    ebx, ebx
0x18009d093  jz      short loc_18009D0B9
0x18009d095  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18009d099  lea     r8, [rbp+57h+IsMember]; IsMember
0x18009d09d  xor     ecx, ecx; TokenHandle
0x18009d09f  call    cs:__imp_CheckTokenMembership
0x18009d0a6  nop     dword ptr [rax+rax+00h]
0x18009d0ab  test    eax, eax
0x18009d0ad  jz      short loc_18009D0B9
0x18009d0af  cmp     [rbp+57h+IsMember], edi
0x18009d0b2  mov     ebx, edi
0x18009d0b4  setz    bl
0x18009d0b7  jmp     short loc_18009D0CE
0x18009d0b9  call    cs:__imp_GetLastError
0x18009d0c0  nop     dword ptr [rax+rax+00h]
0x18009d0c5  mov     ecx, eax; unsigned int
0x18009d0c7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009d0cc  mov     ebx, eax
0x18009d0ce  lea     rcx, [rbp+57h+SidToCheck]
0x18009d0d2  call    ??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)
0x18009d0d7  mov     eax, ebx
0x18009d0d9  mov     rcx, [rbp+57h+var_10]
0x18009d0dd  xor     rcx, rsp; StackCookie
0x18009d0e0  call    __security_check_cookie
0x18009d0e5  lea     r11, [rsp+0A0h+var_s0]
0x18009d0ed  mov     rbx, [r11+10h]
0x18009d0f1  mov     rdi, [r11+18h]
0x18009d0f5  mov     rsp, r11
0x18009d0f8  pop     rbp
0x18009d0f9  retn
```
