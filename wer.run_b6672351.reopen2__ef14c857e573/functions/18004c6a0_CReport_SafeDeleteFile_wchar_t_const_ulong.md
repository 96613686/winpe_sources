# CReport::SafeDeleteFile(wchar_t const *,ulong)

- ea: `0x18004c6a0`
- end: `0x18004c7b1`
- name: `?SafeDeleteFile@CReport@@QEAAJPEB_WK@Z`
- size: `273`
- prototype: `int(CReport *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003d4f0`
- `0x180074268`
- `0x180075eb8`

## callees

- `0x180006af0`
- `0x18001c368`
- `0x18001e658`
- `0x180020680`
- `0x18002dc4c`
- `0x18004c6a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004c757`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004c757`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004c6ea`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004c6ea`

## pseudocode

```c
__int64 __fastcall CReport::SafeDeleteFile(CReport *this, WCHAR *a2, int a3)
{
  void *v3; // rbx
  int v6; // edi
  DWORD LastError; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx

  v3 = (void *)*((_QWORD *)this + 5827);
  if ( !v3 )
    return 2147943408LL;
  v6 = 0;
  if ( (a3 & 0x800000) != 0 )
  {
    if ( UtilIsWriteRestrictedToken(*((HANDLE *)this + 5827)) )
      return 2147942405LL;
    if ( !ImpersonateLoggedOnUser(v3) )
    {
      LastError = GetLastError();
      v8 = ERROR_HR_FROM_WIN32(LastError);
      v9 = v8;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v8);
      return v9;
    }
    v6 = 1;
  }
  v9 = UtilDeleteFilePath(a2);
  if ( v6 )
    RevertToSelf();
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v9, v6);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18004c6a0  mov     [rsp+arg_0], rbx
0x18004c6a5  mov     [rsp+arg_8], rsi
0x18004c6aa  push    rdi
0x18004c6ab  sub     rsp, 30h
0x18004c6af  mov     rbx, [rcx+0B618h]
0x18004c6b6  mov     rsi, rdx
0x18004c6b9  test    rbx, rbx
0x18004c6bc  jnz     short loc_18004C6C8
0x18004c6be  mov     eax, 800703F0h
0x18004c6c3  jmp     loc_18004C7A0
0x18004c6c8  xor     edi, edi
0x18004c6ca  bt      r8d, 17h
0x18004c6cf  jnb     short loc_18004C749
0x18004c6d1  mov     rcx, rbx; ExistingTokenHandle
0x18004c6d4  call    ?UtilIsWriteRestrictedToken@@YA_NPEAX@Z; UtilIsWriteRestrictedToken(void *)
0x18004c6d9  test    al, al
0x18004c6db  jz      short loc_18004C6E7
0x18004c6dd  mov     eax, 80070005h
0x18004c6e2  jmp     loc_18004C7A0
0x18004c6e7  mov     rcx, rbx; hToken
0x18004c6ea  call    cs:__imp_ImpersonateLoggedOnUser
0x18004c6f1  nop     dword ptr [rax+rax+00h]
0x18004c6f6  test    eax, eax
0x18004c6f8  jnz     short loc_18004C744
0x18004c6fa  call    cs:__imp_GetLastError
0x18004c701  nop     dword ptr [rax+rax+00h]
0x18004c706  mov     ecx, eax; unsigned int
0x18004c708  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004c70d  mov     ebx, eax
0x18004c70f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c716  lea     rdx, WPP_GLOBAL_Control
0x18004c71d  cmp     rcx, rdx
0x18004c720  jz      short loc_18004C740
0x18004c722  test    byte ptr [rcx+1Ch], 2
0x18004c726  jz      short loc_18004C740
0x18004c728  mov     rcx, [rcx+10h]
0x18004c72c  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18004c733  mov     edx, 0B4h
0x18004c738  mov     r9d, eax
0x18004c73b  call    WPP_SF_d
0x18004c740  mov     eax, ebx
0x18004c742  jmp     short loc_18004C7A0
0x18004c744  mov     edi, 1
0x18004c749  mov     rcx, rsi; wchar_t *
0x18004c74c  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18004c751  mov     ebx, eax
0x18004c753  test    edi, edi
0x18004c755  jz      short loc_18004C763
0x18004c757  call    cs:__imp_RevertToSelf
0x18004c75e  nop     dword ptr [rax+rax+00h]
0x18004c763  test    ebx, ebx
0x18004c765  jns     short loc_18004C79E
0x18004c767  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c76e  lea     rdx, WPP_GLOBAL_Control
0x18004c775  cmp     rcx, rdx
0x18004c778  jz      short loc_18004C740
0x18004c77a  test    byte ptr [rcx+1Ch], 2
0x18004c77e  jz      short loc_18004C740
0x18004c780  mov     rcx, [rcx+10h]
0x18004c784  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18004c78b  mov     edx, 0B5h
0x18004c790  mov     [rsp+38h+var_18], edi
0x18004c794  mov     r9d, ebx
0x18004c797  call    WPP_SF_Dd
0x18004c79c  jmp     short loc_18004C740
0x18004c79e  xor     eax, eax
0x18004c7a0  mov     rbx, [rsp+38h+arg_0]
0x18004c7a5  mov     rsi, [rsp+38h+arg_8]
0x18004c7aa  add     rsp, 30h
0x18004c7ae  pop     rdi
0x18004c7af  retn
```
