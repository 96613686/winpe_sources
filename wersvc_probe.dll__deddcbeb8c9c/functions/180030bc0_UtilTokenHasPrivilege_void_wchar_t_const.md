# UtilTokenHasPrivilege(void *,wchar_t const *)

- ea: `0x180030bc0`
- end: `0x180030dbf`
- name: `?UtilTokenHasPrivilege@@YAHPEAXPEB_W@Z`
- size: `511`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800300c0`

## callees

- `0x1800029d0`
- `0x180002a00`
- `0x180002ff0`
- `0x180011ef8`
- `0x180030bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030c55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030ca8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030c55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030ca8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180030c05`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180030c05`

## string_xrefs

- `0x180030be9`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall UtilTokenHasPrivilege(HANDLE TokenHandle, const wchar_t *a2)
{
  unsigned int v3; // edi
  DWORD LastError; // eax
  __int64 v5; // rdx
  _DWORD *v6; // rbx
  DWORD v7; // eax
  __int64 v8; // rcx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h] BYREF

  v11 = 0;
  v3 = 0;
  LODWORD(v11) = 1;
  TokenInformationLength = 0;
  if ( LookupPrivilegeValueW(0, L"SeDebugPrivilege", (PLUID)((char *)&v11 + 4)) )
  {
    if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        v5 = 13;
        goto LABEL_26;
      }
    }
    else
    {
      v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
      {
        if ( GetTokenInformation(TokenHandle, TokenPrivileges, v6, TokenInformationLength, &TokenInformationLength) )
        {
          if ( *v6 )
          {
            v8 = 0;
            while ( DWORD1(v11) != v6[3 * v8 + 1] || DWORD2(v11) != v6[3 * v8 + 2] )
            {
              v8 = (unsigned int)(v8 + 1);
              if ( (unsigned int)v8 >= *v6 )
                goto LABEL_19;
            }
            v3 = 1;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, v7);
        }
LABEL_19:
        operator delete(v6);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids,
          TokenInformationLength);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v5 = 12;
LABEL_26:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, LastError);
  }
  return v3;
}

```

## disassembly

```asm
0x180030bc0  mov     [rsp+arg_8], rbx
0x180030bc5  mov     [rsp+arg_10], rsi
0x180030bca  push    rdi
0x180030bcb  sub     rsp, 50h
0x180030bcf  mov     rax, cs:__security_cookie
0x180030bd6  xor     rax, rsp
0x180030bd9  mov     [rsp+58h+var_10], rax
0x180030bde  xorps   xmm0, xmm0
0x180030be1  lea     r8, [rsp+58h+Luid]; lpLuid
0x180030be6  mov     rsi, rcx
0x180030be9  lea     rdx, aSedebugprivile; "SeDebugPrivilege"
0x180030bf0  movups  xmmword ptr [rsp+38h], xmm0
0x180030bf5  xor     edi, edi
0x180030bf7  mov     [rsp+58h+var_20], 1
0x180030bff  xor     ecx, ecx; lpSystemName
0x180030c01  mov     [rsp+58h+TokenInformationLength], edi
0x180030c05  call    cs:__imp_LookupPrivilegeValueW
0x180030c0b  test    eax, eax
0x180030c0d  jnz     short loc_180030C3E
0x180030c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c16  lea     rax, WPP_GLOBAL_Control
0x180030c1d  cmp     rcx, rax
0x180030c20  jz      loc_180030DA0
0x180030c26  test    byte ptr [rcx+1Ch], 1
0x180030c2a  jz      loc_180030DA0
0x180030c30  call    cs:__imp_GetLastError
0x180030c36  lea     edx, [rdi+0Ch]
0x180030c39  jmp     loc_180030D86
0x180030c3e  xor     r9d, r9d; TokenInformationLength
0x180030c41  lea     rax, [rsp+58h+TokenInformationLength]
0x180030c46  xor     r8d, r8d; TokenInformation
0x180030c49  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180030c4e  mov     rcx, rsi; TokenHandle
0x180030c51  lea     edx, [r9+3]; TokenInformationClass
0x180030c55  call    cs:__imp_GetTokenInformation
0x180030c5b  test    eax, eax
0x180030c5d  jnz     loc_180030D62
0x180030c63  call    cs:__imp_GetLastError
0x180030c69  cmp     eax, 7Ah ; 'z'
0x180030c6c  jnz     loc_180030D62
0x180030c72  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180030c76  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030c7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180030c82  mov     rbx, rax
0x180030c85  test    rax, rax
0x180030c88  jz      loc_180030D2D
0x180030c8e  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180030c93  lea     rax, [rsp+58h+TokenInformationLength]
0x180030c98  mov     r8, rbx; TokenInformation
0x180030c9b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180030ca0  mov     edx, 3; TokenInformationClass
0x180030ca5  mov     rcx, rsi; TokenHandle
0x180030ca8  call    cs:__imp_GetTokenInformation
0x180030cae  test    eax, eax
0x180030cb0  jnz     short loc_180030CF2
0x180030cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cb9  lea     rax, WPP_GLOBAL_Control
0x180030cc0  cmp     rcx, rax
0x180030cc3  jz      short loc_180030D23
0x180030cc5  test    byte ptr [rcx+1Ch], 1
0x180030cc9  jz      short loc_180030D23
0x180030ccb  call    cs:__imp_GetLastError
0x180030cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cd8  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030cdf  mov     edx, 0Fh
0x180030ce4  mov     r9d, eax
0x180030ce7  mov     rcx, [rcx+10h]
0x180030ceb  call    WPP_SF_d
0x180030cf0  jmp     short loc_180030D23
0x180030cf2  mov     edx, [rbx]
0x180030cf4  test    edx, edx
0x180030cf6  jz      short loc_180030D23
0x180030cf8  mov     r11d, [rsp+58h+Luid.LowPart]
0x180030cfd  xor     ecx, ecx
0x180030cff  mov     r10d, [rsp+58h+Luid.HighPart]
0x180030d04  lea     r8, [rcx+rcx*2]
0x180030d08  cmp     r11d, [rbx+r8*4+4]
0x180030d0d  jnz     short loc_180030D16
0x180030d0f  cmp     r10d, [rbx+r8*4+8]
0x180030d14  jz      short loc_180030D1E
0x180030d16  inc     ecx
0x180030d18  cmp     ecx, edx
0x180030d1a  jb      short loc_180030D04
0x180030d1c  jmp     short loc_180030D23
0x180030d1e  mov     edi, 1
0x180030d23  mov     rcx, rbx; Block
0x180030d26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030d2b  jmp     short loc_180030DA0
0x180030d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d34  lea     rax, WPP_GLOBAL_Control
0x180030d3b  cmp     rcx, rax
0x180030d3e  jz      short loc_180030DA0
0x180030d40  test    byte ptr [rcx+1Ch], 1
0x180030d44  jz      short loc_180030DA0
0x180030d46  mov     r9d, [rsp+58h+TokenInformationLength]
0x180030d4b  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030d52  mov     rcx, [rcx+10h]
0x180030d56  mov     edx, 0Eh
0x180030d5b  call    WPP_SF_d
0x180030d60  jmp     short loc_180030DA0
0x180030d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d69  lea     rax, WPP_GLOBAL_Control
0x180030d70  cmp     rcx, rax
0x180030d73  jz      short loc_180030DA0
0x180030d75  test    byte ptr [rcx+1Ch], 1
0x180030d79  jz      short loc_180030DA0
0x180030d7b  call    cs:__imp_GetLastError
0x180030d81  mov     edx, 0Dh
0x180030d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d8d  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030d94  mov     r9d, eax
0x180030d97  mov     rcx, [rcx+10h]
0x180030d9b  call    WPP_SF_d
0x180030da0  mov     eax, edi
0x180030da2  mov     rcx, [rsp+58h+var_10]
0x180030da7  xor     rcx, rsp; StackCookie
0x180030daa  call    __security_check_cookie
0x180030daf  mov     rbx, [rsp+58h+arg_8]
0x180030db4  mov     rsi, [rsp+58h+arg_10]
0x180030db9  add     rsp, 50h
0x180030dbd  pop     rdi
0x180030dbe  retn
```
