# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18003df7c`
- end: `0x18003e0fe`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18003df48`
- `0x18003df7c`

## callees

- `0x180003204`
- `0x18000558c`
- `0x18000e5ac`
- `0x18001995c`
- `0x18003df7c`
- `0x18003f70c`
- `0x180040218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0ab`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003df93`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003e0a1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003df93`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003e0a1`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18003dfc0`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18003dfc0`

## string_xrefs

- `0x18003e023`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003e079`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003e0c6`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const unsigned __int16 *v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // edi
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
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
            v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
            v8 = v7;
            if ( !v7 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)0x8007000ELL,
                v17);
              return -2147024882;
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
0x18003df7c  mov     [rsp+arg_0], rbx
0x18003df81  mov     [rsp+arg_10], rbp
0x18003df86  push    rsi
0x18003df87  push    rdi
0x18003df88  push    r14; unsigned int
0x18003df8a  sub     rsp, 20h
0x18003df8e  xor     edx, edx; lpSecurityAttributes
0x18003df90  mov     rbx, rcx
0x18003df93  call    cs:__imp_CreateDirectoryW
0x18003df99  xor     r14d, r14d
0x18003df9c  test    eax, eax
0x18003df9e  jnz     loc_18003E0E9
0x18003dfa4  call    cs:__imp_GetLastError
0x18003dfaa  cmp     eax, 3
0x18003dfad  jnz     loc_18003E0D7
0x18003dfb3  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x18003dfb8  mov     [rsp+38h+ppszRootEnd], r14
0x18003dfbd  mov     rcx, rbx; pszPath
0x18003dfc0  call    cs:__imp_PathCchSkipRoot
0x18003dfc6  test    eax, eax
0x18003dfc8  js      loc_18003E09C
0x18003dfce  mov     rax, [rsp+38h+ppszRootEnd]
0x18003dfd3  cmp     [rax], r14w
0x18003dfd7  jz      loc_18003E09C
0x18003dfdd  mov     rcx, rbx; lpStringSource
0x18003dfe0  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x18003dfe5  mov     rdi, rax
0x18003dfe8  sub     rdi, rbx
0x18003dfeb  sar     rdi, 1
0x18003dfee  jz      loc_18003E09C
0x18003dff4  lea     rcx, [r14-1]
0x18003dff8  lea     rbp, [rdi+1]
0x18003dffc  lea     eax, [r14+2]
0x18003e000  mul     rbp
0x18003e003  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e00a  cmovb   rax, rcx
0x18003e00e  mov     rcx, rax; unsigned __int64
0x18003e011  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003e016  mov     rsi, rax
0x18003e019  test    rax, rax
0x18003e01c  jnz     short loc_18003E043
0x18003e01e  mov     rcx, [rsp+38h]; this
0x18003e023  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e02a  mov     ebx, 8007000Eh
0x18003e02f  mov     edx, 82h; void *
0x18003e034  mov     r9d, ebx; char *
0x18003e037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e03c  mov     eax, ebx
0x18003e03e  jmp     loc_18003E0EB
0x18003e043  mov     r9, rdi; unsigned __int64
0x18003e046  mov     r8, rbx; unsigned __int16 *
0x18003e049  mov     rdx, rbp; unsigned __int64
0x18003e04c  mov     rcx, rsi; unsigned __int16 *
0x18003e04f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003e054  mov     edi, eax
0x18003e056  test    eax, eax
0x18003e058  jns     short loc_18003E061
0x18003e05a  mov     edx, 83h
0x18003e05f  jmp     short loc_18003E074
0x18003e061  mov     rcx, rsi; this
0x18003e064  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003e069  mov     edi, eax
0x18003e06b  test    eax, eax
0x18003e06d  jns     short loc_18003E094
0x18003e06f  mov     edx, 84h; void *
0x18003e074  mov     rcx, [rsp+38h]; this
0x18003e079  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e080  mov     r9d, eax; char *
0x18003e083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e088  mov     rcx, rsi; void *
0x18003e08b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e090  mov     eax, edi
0x18003e092  jmp     short loc_18003E0EB
0x18003e094  mov     rcx, rsi; void *
0x18003e097  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e09c  xor     edx, edx; lpSecurityAttributes
0x18003e09e  mov     rcx, rbx; lpPathName
0x18003e0a1  call    cs:__imp_CreateDirectoryW
0x18003e0a7  test    eax, eax
0x18003e0a9  jnz     short loc_18003E0E9
0x18003e0ab  call    cs:__imp_GetLastError
0x18003e0b1  cmp     eax, 0B7h
0x18003e0b6  jz      short loc_18003E0E9
0x18003e0b8  test    eax, eax
0x18003e0ba  jz      short loc_18003E0E9
0x18003e0bc  mov     edx, 8Bh; void *
0x18003e0c1  mov     rcx, [rsp+38h]; this
0x18003e0c6  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e0cd  mov     r9d, eax; char *
0x18003e0d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e0d5  jmp     short loc_18003E0EB
0x18003e0d7  cmp     eax, 0B7h
0x18003e0dc  jz      short loc_18003E0E9
0x18003e0de  test    eax, eax
0x18003e0e0  jz      short loc_18003E0E9
0x18003e0e2  mov     edx, 91h
0x18003e0e7  jmp     short loc_18003E0C1
0x18003e0e9  xor     eax, eax
0x18003e0eb  mov     rbx, [rsp+38h+arg_0]
0x18003e0f0  mov     rbp, [rsp+38h+arg_10]
0x18003e0f5  add     rsp, 20h
0x18003e0f9  pop     r14
0x18003e0fb  pop     rdi
0x18003e0fc  pop     rsi
0x18003e0fd  retn
```
