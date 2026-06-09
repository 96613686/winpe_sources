# FSOp::MakeDirectory(wchar_t const *,ulong &,_SECURITY_ATTRIBUTES *)

- ea: `0x18016c350`
- end: `0x18016c410`
- name: `?MakeDirectory@FSOp@@YAHPEB_WAEAKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, unsigned int *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180064688`

## callees

- `0x1801480fc`
- `0x18016c350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c3c7`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18016c3bd`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18016c3bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18016c3e0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18016c3e0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18016c3ef`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18016c3ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18016c36b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18016c36b`

## string_xrefs

- `0x18016c39c`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\fsutil.cxx"`
- `0x18016c3cf`: `[UtilFileSystem] SetFileSecurity %ls failed. 0x%08x`
- `0x18016c389`: `[UtilFileSystem] CreateDirectory %ls failed. 0x%08x`

## pseudocode

```c
__int64 __fastcall FSOp::MakeDirectory(
        wchar_t *this,
        wchar_t *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  DWORD LastError; // eax
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  __int64 result; // rax
  DWORD FileAttributesW; // eax
  DWORD v12; // [rsp+20h] [rbp-18h]

  if ( !CreateDirectoryW(this, a3) )
  {
    LastError = GetLastError();
    *(_DWORD *)a2 = LastError;
    if ( LastError != 80 && LastError != 183 )
    {
      v8 = (const wchar_t *)L"[UtilFileSystem] CreateDirectory %ls failed. 0x%08x";
      v9 = 99;
LABEL_5:
      v12 = LastError;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\fsutil.cxx\"",
        (const wchar_t *)v9,
        (unsigned int)v8,
        this,
        v12);
      return 0;
    }
    if ( a3 && !SetFileSecurityW(this, 4u, a3->lpSecurityDescriptor) )
    {
      LastError = GetLastError();
      *(_DWORD *)a2 = LastError;
      v8 = L"[UtilFileSystem] SetFileSecurity %ls failed. 0x%08x";
      v9 = 109;
      goto LABEL_5;
    }
  }
  FileAttributesW = GetFileAttributesW(this);
  SetFileAttributesW(this, FileAttributesW | 0x2000);
  result = 1;
  *(_DWORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18016c350  mov     [rsp+arg_0], rbx
0x18016c355  mov     [rsp+arg_8], rsi
0x18016c35a  push    rdi
0x18016c35b  sub     rsp, 30h
0x18016c35f  mov     rdi, rdx
0x18016c362  mov     rsi, r8
0x18016c365  mov     rdx, r8; lpSecurityAttributes
0x18016c368  mov     rbx, rcx
0x18016c36b  call    cs:__imp_CreateDirectoryW
0x18016c371  test    eax, eax
0x18016c373  jnz     short loc_18016C3DD
0x18016c375  call    cs:__imp_GetLastError
0x18016c37b  mov     [rdi], eax
0x18016c37d  cmp     eax, 50h ; 'P'
0x18016c380  jz      short loc_18016C3AC
0x18016c382  cmp     eax, 0B7h
0x18016c387  jz      short loc_18016C3AC
0x18016c389  lea     r8, aUtilfilesystem; "[UtilFileSystem] CreateDirectory %ls fa"...
0x18016c390  mov     edx, 63h ; 'c'; wchar_t *
0x18016c395  mov     r9, rbx; wchar_t *
0x18016c398  mov     [rsp+38h+var_18], eax
0x18016c39c  lea     rcx, aOnecoreuapBase_220; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18016c3a3  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18016c3a8  xor     eax, eax
0x18016c3aa  jmp     short loc_18016C400
0x18016c3ac  test    rsi, rsi
0x18016c3af  jz      short loc_18016C3DD
0x18016c3b1  mov     r8, [rsi+8]; pSecurityDescriptor
0x18016c3b5  mov     edx, 4; SecurityInformation
0x18016c3ba  mov     rcx, rbx; lpFileName
0x18016c3bd  call    cs:__imp_SetFileSecurityW
0x18016c3c3  test    eax, eax
0x18016c3c5  jnz     short loc_18016C3DD
0x18016c3c7  call    cs:__imp_GetLastError
0x18016c3cd  mov     [rdi], eax
0x18016c3cf  lea     r8, aUtilfilesystem_0; "[UtilFileSystem] SetFileSecurity %ls fa"...
0x18016c3d6  mov     edx, 6Dh ; 'm'
0x18016c3db  jmp     short loc_18016C395
0x18016c3dd  mov     rcx, rbx; lpFileName
0x18016c3e0  call    cs:__imp_GetFileAttributesW
0x18016c3e6  bts     eax, 0Dh
0x18016c3ea  mov     rcx, rbx; lpFileName
0x18016c3ed  mov     edx, eax; dwFileAttributes
0x18016c3ef  call    cs:__imp_SetFileAttributesW
0x18016c3f5  mov     eax, 1
0x18016c3fa  mov     dword ptr [rdi], 0
0x18016c400  mov     rbx, [rsp+38h+arg_0]
0x18016c405  mov     rsi, [rsp+38h+arg_8]
0x18016c40a  add     rsp, 30h
0x18016c40e  pop     rdi
0x18016c40f  retn
```
