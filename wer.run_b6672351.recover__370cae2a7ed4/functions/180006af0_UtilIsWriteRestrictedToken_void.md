# UtilIsWriteRestrictedToken(void *)

- ea: `0x180006af0`
- end: `0x180006ca7`
- name: `?UtilIsWriteRestrictedToken@@YA_NPEAX@Z`
- size: `439`
- prototype: `bool __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c6a0`
- `0x180074268`

## callees

- `0x180004c64`
- `0x180006af0`
- `0x180007fd8`
- `0x180008004`
- `0x180009464`
- `0x180020680`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bfc`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006b50`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006b50`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006bd3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180006bd3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006c35`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006c35`

## pseudocode

```c
bool __fastcall UtilIsWriteRestrictedToken(HANDLE ExistingTokenHandle)
{
  BOOL v2; // ebx
  wchar_t *v3; // rcx
  DWORD v4; // eax
  DWORD LastError; // eax
  bool v7; // bl
  WINBOOL IsMember; // [rsp+20h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+28h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+30h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-21h] BYREF
  HANDLE *p_TokenHandle; // [rsp+40h] [rbp-19h]
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  p_TokenHandle = &TokenHandle;
  cbSid = 68;
  DuplicateTokenHandle = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(&TokenHandle, 0);
  v2 = DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle);
  if ( DuplicateTokenHandle )
    tlx::unique_any<tlx::file_handle_traits>::reset(p_TokenHandle, DuplicateTokenHandle);
  if ( v2 )
  {
    if ( CreateWellKnownSid(WinWriteRestrictedCodeSid, 0, pSid, &cbSid) )
    {
      if ( CheckTokenMembership(TokenHandle, pSid, &IsMember) )
      {
        v7 = IsMember != 0;
        goto LABEL_18;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, LastError);
    }
    v7 = 0;
LABEL_18:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
    return v7;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v4);
  }
  tlx::file_handle_traits::operator()(v3, TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180006af0  mov     [rsp-8+arg_8], rbx
0x180006af5  push    rbp
0x180006af6  lea     rbp, [rsp-57h]
0x180006afb  sub     rsp, 0B0h
0x180006b02  mov     rax, cs:__security_cookie
0x180006b09  xor     rax, rsp
0x180006b0c  mov     [rbp+57h+var_10], rax
0x180006b10  mov     rbx, rcx
0x180006b13  mov     [rbp+57h+TokenHandle], 0
0x180006b1b  lea     rax, [rbp+57h+TokenHandle]
0x180006b1f  mov     [rbp+57h+IsMember], 0
0x180006b26  lea     rcx, [rbp+57h+TokenHandle]
0x180006b2a  mov     [rbp+57h+var_70], rax
0x180006b2e  xor     edx, edx
0x180006b30  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180006b37  mov     [rbp+57h+DuplicateTokenHandle], 0
0x180006b3f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180006b44  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180006b48  mov     edx, 2; ImpersonationLevel
0x180006b4d  mov     rcx, rbx; ExistingTokenHandle
0x180006b50  call    cs:__imp_DuplicateToken
0x180006b57  nop     dword ptr [rax+rax+00h]
0x180006b5c  mov     rdx, [rbp+57h+DuplicateTokenHandle]
0x180006b60  mov     ebx, eax
0x180006b62  test    rdx, rdx
0x180006b65  jz      short loc_180006B70
0x180006b67  mov     rcx, [rbp+57h+var_70]
0x180006b6b  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180006b70  test    ebx, ebx
0x180006b72  jnz     short loc_180006BC6
0x180006b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b7b  lea     rax, WPP_GLOBAL_Control
0x180006b82  cmp     rcx, rax
0x180006b85  jz      short loc_180006BB6
0x180006b87  test    byte ptr [rcx+1Ch], 1
0x180006b8b  jz      short loc_180006BB6
0x180006b8d  call    cs:__imp_GetLastError
0x180006b94  nop     dword ptr [rax+rax+00h]
0x180006b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ba0  lea     edx, [rbx+2Bh]
0x180006ba3  mov     r9d, eax
0x180006ba6  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180006bad  mov     rcx, [rcx+10h]
0x180006bb1  call    WPP_SF_d
0x180006bb6  mov     rdx, [rbp+57h+TokenHandle]
0x180006bba  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180006bbf  xor     al, al
0x180006bc1  jmp     loc_180006C89
0x180006bc6  xor     edx, edx; DomainSid
0x180006bc8  lea     r9, [rbp+57h+cbSid]; cbSid
0x180006bcc  lea     r8, [rbp+57h+pSid]; pSid
0x180006bd0  lea     ecx, [rdx+46h]; WellKnownSidType
0x180006bd3  call    cs:__imp_CreateWellKnownSid
0x180006bda  nop     dword ptr [rax+rax+00h]
0x180006bdf  test    eax, eax
0x180006be1  jnz     short loc_180006C29
0x180006be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bea  lea     rax, WPP_GLOBAL_Control
0x180006bf1  cmp     rcx, rax
0x180006bf4  jz      short loc_180006C73
0x180006bf6  test    byte ptr [rcx+1Ch], 1
0x180006bfa  jz      short loc_180006C73
0x180006bfc  call    cs:__imp_GetLastError
0x180006c03  nop     dword ptr [rax+rax+00h]
0x180006c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c0f  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180006c16  mov     edx, 2Ch ; ','
0x180006c1b  mov     r9d, eax
0x180006c1e  mov     rcx, [rcx+10h]
0x180006c22  call    WPP_SF_d
0x180006c27  jmp     short loc_180006C73
0x180006c29  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180006c2d  lea     r8, [rbp+57h+IsMember]; IsMember
0x180006c31  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180006c35  call    cs:__imp_CheckTokenMembership
0x180006c3c  nop     dword ptr [rax+rax+00h]
0x180006c41  test    eax, eax
0x180006c43  jnz     short loc_180006C77
0x180006c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c4c  lea     rax, WPP_GLOBAL_Control
0x180006c53  cmp     rcx, rax
0x180006c56  jz      short loc_180006C73
0x180006c58  test    byte ptr [rcx+1Ch], 1
0x180006c5c  jz      short loc_180006C73
0x180006c5e  mov     rcx, [rcx+10h]
0x180006c62  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180006c69  mov     edx, 2Dh ; '-'
0x180006c6e  call    WPP_SF_
0x180006c73  xor     bl, bl
0x180006c75  jmp     short loc_180006C7E
0x180006c77  cmp     [rbp+57h+IsMember], 0
0x180006c7b  setnz   bl
0x180006c7e  lea     rcx, [rbp+57h+TokenHandle]
0x180006c82  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180006c87  mov     al, bl
0x180006c89  mov     rcx, [rbp+57h+var_10]
0x180006c8d  xor     rcx, rsp; StackCookie
0x180006c90  call    __security_check_cookie
0x180006c95  mov     rbx, [rsp+0B0h+arg_8]
0x180006c9d  add     rsp, 0B0h
0x180006ca4  pop     rbp
0x180006ca5  retn
```
