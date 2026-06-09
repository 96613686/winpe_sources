# CReport::SafeDeleteFile(wchar_t const *,ulong)

- ea: `0x18004a370`
- end: `0x18004a46e`
- name: `?SafeDeleteFile@CReport@@QEAAJPEB_WK@Z`
- size: `254`
- prototype: `__int64 __fastcall(CReport *this, const wchar_t *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003b590`
- `0x180070f3c`
- `0x180072b18`

## callees

- `0x1800062d0`
- `0x18000716c`
- `0x18001dfac`
- `0x18001fe24`
- `0x18002c220`
- `0x18004a370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004a41b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004a41b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004a3ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004a3ba`

## pseudocode

```c
__int64 __fastcall CReport::SafeDeleteFile(CReport *this, const wchar_t *a2, int a3)
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v8);
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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v9, v6);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18004a370  mov     [rsp+arg_0], rbx
0x18004a375  mov     [rsp+arg_8], rsi
0x18004a37a  push    rdi
0x18004a37b  sub     rsp, 30h
0x18004a37f  mov     rbx, [rcx+0B618h]
0x18004a386  mov     rsi, rdx
0x18004a389  test    rbx, rbx
0x18004a38c  jnz     short loc_18004A398
0x18004a38e  mov     eax, 800703F0h
0x18004a393  jmp     loc_18004A45E
0x18004a398  xor     edi, edi
0x18004a39a  bt      r8d, 17h
0x18004a39f  jnb     short loc_18004A40D
0x18004a3a1  mov     rcx, rbx; ExistingTokenHandle
0x18004a3a4  call    ?UtilIsWriteRestrictedToken@@YA_NPEAX@Z; UtilIsWriteRestrictedToken(void *)
0x18004a3a9  test    al, al
0x18004a3ab  jz      short loc_18004A3B7
0x18004a3ad  mov     eax, 80070005h
0x18004a3b2  jmp     loc_18004A45E
0x18004a3b7  mov     rcx, rbx; hToken
0x18004a3ba  call    cs:__imp_ImpersonateLoggedOnUser
0x18004a3c0  test    eax, eax
0x18004a3c2  jnz     short loc_18004A408
0x18004a3c4  call    cs:__imp_GetLastError
0x18004a3ca  mov     ecx, eax; unsigned int
0x18004a3cc  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004a3d1  mov     ebx, eax
0x18004a3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3da  lea     rdx, WPP_GLOBAL_Control
0x18004a3e1  cmp     rcx, rdx
0x18004a3e4  jz      short loc_18004A404
0x18004a3e6  test    byte ptr [rcx+1Ch], 2
0x18004a3ea  jz      short loc_18004A404
0x18004a3ec  mov     rcx, [rcx+10h]
0x18004a3f0  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004a3f7  mov     edx, 0B3h
0x18004a3fc  mov     r9d, eax
0x18004a3ff  call    WPP_SF_d
0x18004a404  mov     eax, ebx
0x18004a406  jmp     short loc_18004A45E
0x18004a408  mov     edi, 1
0x18004a40d  mov     rcx, rsi; wchar_t *
0x18004a410  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18004a415  mov     ebx, eax
0x18004a417  test    edi, edi
0x18004a419  jz      short loc_18004A421
0x18004a41b  call    cs:__imp_RevertToSelf
0x18004a421  test    ebx, ebx
0x18004a423  jns     short loc_18004A45C
0x18004a425  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a42c  lea     rdx, WPP_GLOBAL_Control
0x18004a433  cmp     rcx, rdx
0x18004a436  jz      short loc_18004A404
0x18004a438  test    byte ptr [rcx+1Ch], 2
0x18004a43c  jz      short loc_18004A404
0x18004a43e  mov     rcx, [rcx+10h]
0x18004a442  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004a449  mov     edx, 0B4h
0x18004a44e  mov     [rsp+38h+var_18], edi
0x18004a452  mov     r9d, ebx
0x18004a455  call    WPP_SF_Dd
0x18004a45a  jmp     short loc_18004A404
0x18004a45c  xor     eax, eax
0x18004a45e  mov     rbx, [rsp+38h+arg_0]
0x18004a463  mov     rsi, [rsp+38h+arg_8]
0x18004a468  add     rsp, 30h
0x18004a46c  pop     rdi
0x18004a46d  retn
```
