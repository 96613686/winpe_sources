# wil::CreateDirectoryDeepNoThrow(wchar_t const *)

- ea: `0x18044c784`
- end: `0x18044c906`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEB_W@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18044c784`
- `0x18044ca30`

## callees

- `0x18005ebf0`
- `0x1800e34bc`
- `0x1800e3660`
- `0x18015cfa0`
- `0x180277780`
- `0x18044c784`
- `0x18044e4c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18044c7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18044c8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18044c7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18044c8b3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18044c79b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18044c8a9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18044c79b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18044c8a9`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18044c7c8`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18044c7c8`

## string_xrefs

- `0x18044c82b`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18044c881`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18044c8ce`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const wchar_t *a2)
{
  DWORD LastError; // eax
  const wchar_t *v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  int DirectoryDeepNoThrow; // eax
  const wchar_t *v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+10h] BYREF

  if ( !CreateDirectoryW(this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      ppszRootEnd = 0;
      if ( PathCchSkipRoot(this, &ppszRootEnd) >= 0 )
      {
        if ( *ppszRootEnd )
        {
          v5 = wil::find_last_path_segment(this, v4) - this;
          if ( v5 )
          {
            v6 = 2 * (v5 + 1);
            if ( !is_mul_ok(v5 + 1, 2u) )
              v6 = -1;
            v7 = (wchar_t *)operator new[](v6, (const struct std::nothrow_t *)std::nothrow);
            v8 = v7;
            if ( !v7 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)0x8007000ELL,
                v17);
              return 2147942414LL;
            }
            DirectoryDeepNoThrow = StringCchCopyNW(v7, v5 + 1, this, v5);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 131;
LABEL_14:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v13,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)(unsigned int)DirectoryDeepNoThrow,
                v17);
              operator delete(v8, v15);
              return v12;
            }
            DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v8, v11);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 132;
              goto LABEL_14;
            }
            operator delete(v8, v14);
          }
        }
      }
      if ( !CreateDirectoryW(this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v16 = 139;
            return wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v16,
                     (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                     (const char *)LastError,
                     v17);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v16 = 145;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
               (const char *)LastError,
               v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18044c784  mov     [rsp+arg_0], rbx
0x18044c789  mov     [rsp+arg_10], rbp
0x18044c78e  push    rsi
0x18044c78f  push    rdi
0x18044c790  push    r14; unsigned int
0x18044c792  sub     rsp, 20h
0x18044c796  xor     edx, edx; lpSecurityAttributes
0x18044c798  mov     rbx, rcx
0x18044c79b  call    cs:__imp_CreateDirectoryW
0x18044c7a1  xor     r14d, r14d
0x18044c7a4  test    eax, eax
0x18044c7a6  jnz     loc_18044C8F1
0x18044c7ac  call    cs:__imp_GetLastError
0x18044c7b2  cmp     eax, 3
0x18044c7b5  jnz     loc_18044C8DF
0x18044c7bb  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x18044c7c0  mov     [rsp+38h+ppszRootEnd], r14
0x18044c7c5  mov     rcx, rbx; pszPath
0x18044c7c8  call    cs:__imp_PathCchSkipRoot
0x18044c7ce  test    eax, eax
0x18044c7d0  js      loc_18044C8A4
0x18044c7d6  mov     rax, [rsp+38h+ppszRootEnd]
0x18044c7db  cmp     [rax], r14w
0x18044c7df  jz      loc_18044C8A4
0x18044c7e5  mov     rcx, rbx; lpStringSource
0x18044c7e8  call    ?find_last_path_segment@wil@@YAPEB_WPEB_W@Z; wil::find_last_path_segment(wchar_t const *)
0x18044c7ed  mov     rdi, rax
0x18044c7f0  sub     rdi, rbx
0x18044c7f3  sar     rdi, 1
0x18044c7f6  jz      loc_18044C8A4
0x18044c7fc  lea     rcx, [r14-1]
0x18044c800  lea     rbp, [rdi+1]
0x18044c804  lea     eax, [r14+2]
0x18044c808  mul     rbp
0x18044c80b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18044c812  cmovb   rax, rcx
0x18044c816  mov     rcx, rax; unsigned __int64
0x18044c819  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18044c81e  mov     rsi, rax
0x18044c821  test    rax, rax
0x18044c824  jnz     short loc_18044C84B
0x18044c826  mov     rcx, [rsp+38h]; this
0x18044c82b  lea     r8, aOnecoreInterna_25; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18044c832  mov     ebx, 8007000Eh
0x18044c837  mov     edx, 82h; void *
0x18044c83c  mov     r9d, ebx; char *
0x18044c83f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18044c844  mov     eax, ebx
0x18044c846  jmp     loc_18044C8F3
0x18044c84b  mov     r9, rdi; unsigned __int64
0x18044c84e  mov     r8, rbx; wchar_t *
0x18044c851  mov     rdx, rbp; unsigned __int64
0x18044c854  mov     rcx, rsi; wchar_t *
0x18044c857  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18044c85c  mov     edi, eax
0x18044c85e  test    eax, eax
0x18044c860  jns     short loc_18044C869
0x18044c862  mov     edx, 83h
0x18044c867  jmp     short loc_18044C87C
0x18044c869  mov     rcx, rsi; this
0x18044c86c  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEB_W@Z; wil::CreateDirectoryDeepNoThrow(wchar_t const *)
0x18044c871  mov     edi, eax
0x18044c873  test    eax, eax
0x18044c875  jns     short loc_18044C89C
0x18044c877  mov     edx, 84h; void *
0x18044c87c  mov     rcx, [rsp+38h]; this
0x18044c881  lea     r8, aOnecoreInterna_25; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18044c888  mov     r9d, eax; char *
0x18044c88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18044c890  mov     rcx, rsi; void *
0x18044c893  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18044c898  mov     eax, edi
0x18044c89a  jmp     short loc_18044C8F3
0x18044c89c  mov     rcx, rsi; void *
0x18044c89f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18044c8a4  xor     edx, edx; lpSecurityAttributes
0x18044c8a6  mov     rcx, rbx; lpPathName
0x18044c8a9  call    cs:__imp_CreateDirectoryW
0x18044c8af  test    eax, eax
0x18044c8b1  jnz     short loc_18044C8F1
0x18044c8b3  call    cs:__imp_GetLastError
0x18044c8b9  cmp     eax, 0B7h
0x18044c8be  jz      short loc_18044C8F1
0x18044c8c0  test    eax, eax
0x18044c8c2  jz      short loc_18044C8F1
0x18044c8c4  mov     edx, 8Bh; void *
0x18044c8c9  mov     rcx, [rsp+38h]; this
0x18044c8ce  lea     r8, aOnecoreInterna_25; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18044c8d5  mov     r9d, eax; char *
0x18044c8d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18044c8dd  jmp     short loc_18044C8F3
0x18044c8df  cmp     eax, 0B7h
0x18044c8e4  jz      short loc_18044C8F1
0x18044c8e6  test    eax, eax
0x18044c8e8  jz      short loc_18044C8F1
0x18044c8ea  mov     edx, 91h
0x18044c8ef  jmp     short loc_18044C8C9
0x18044c8f1  xor     eax, eax
0x18044c8f3  mov     rbx, [rsp+38h+arg_0]
0x18044c8f8  mov     rbp, [rsp+38h+arg_10]
0x18044c8fd  add     rsp, 20h
0x18044c901  pop     r14
0x18044c903  pop     rdi
0x18044c904  pop     rsi
0x18044c905  retn
```
