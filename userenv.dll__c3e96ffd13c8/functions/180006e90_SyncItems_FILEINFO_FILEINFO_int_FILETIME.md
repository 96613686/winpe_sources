# SyncItems(_FILEINFO *,_FILEINFO *,int,_FILETIME *)

- ea: `0x180006e90`
- end: `0x180006f79`
- name: `?SyncItems@@YAHPEAU_FILEINFO@@0HPEAU_FILETIME@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _FILEINFO *, struct _FILEINFO *, int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a200`

## callees

- `0x180006e90`
- `0x18000d178`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006edb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006edb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006f38`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006f4a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006f38`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006f4a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180006efc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180006efc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006f0a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006f0a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180006f5e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180006f5e`

## pseudocode

```c
__int64 __fastcall SyncItems(struct _FILEINFO *a1, struct _FILEINFO *a2, int a3, struct _FILETIME *a4)
{
  struct _FILEINFO *v6; // rdi
  struct _FILEINFO *v8; // rbx
  const WCHAR *v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v13; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = a2;
  if ( a1 && a2 )
  {
    do
    {
      v8 = a1;
      while ( CompareStringOrdinal(*(LPCWCH *)v6, -1, *((LPCWCH *)v8 + 1), -1, 1) != 2 )
      {
        v8 = (struct _FILEINFO *)*((_QWORD *)v8 + 6);
        if ( !v8 )
        {
          if ( !a4
            || CompareFileTime((const FILETIME *)v6 + 2, a4) != 1 && CompareFileTime((const FILETIME *)v6 + 3, a4) != 1 )
          {
            SetFileAttributesW(*(LPCWSTR *)v6, 0x80u);
            v9 = *(const WCHAR **)v6;
            if ( a3 )
            {
              if ( DeleteFileW(v9) )
                break;
              v13 = 2406;
            }
            else
            {
              if ( RemoveDirectoryW(v9) )
                break;
              v13 = 2414;
            }
            wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v13, v10, v11);
          }
          break;
        }
      }
      v6 = (struct _FILEINFO *)*((_QWORD *)v6 + 6);
    }
    while ( v6 );
  }
  return 1;
}

```

## disassembly

```asm
0x180006e90  push    rbp
0x180006e92  push    rsi
0x180006e93  push    rdi
0x180006e94  push    r14
0x180006e96  sub     rsp, 38h
0x180006e9a  mov     rsi, r9
0x180006e9d  mov     r14d, r8d
0x180006ea0  mov     rdi, rdx
0x180006ea3  mov     rbp, rcx
0x180006ea6  test    rcx, rcx
0x180006ea9  jz      short loc_180006F22
0x180006eab  test    rdx, rdx
0x180006eae  jz      short loc_180006F22
0x180006eb0  mov     [rsp+58h+arg_0], rbx
0x180006eb5  nop     word ptr [rax+rax+00000000h]
0x180006ec0  mov     rbx, rbp
0x180006ec3  mov     r8, [rbx+8]; lpString2
0x180006ec7  mov     r9d, 0FFFFFFFFh; cchCount2
0x180006ecd  mov     rcx, [rdi]; lpString1
0x180006ed0  mov     edx, r9d; cchCount1
0x180006ed3  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180006edb  call    cs:__imp_CompareStringOrdinal
0x180006ee1  cmp     eax, 2
0x180006ee4  jz      short loc_180006F14
0x180006ee6  mov     rbx, [rbx+30h]
0x180006eea  test    rbx, rbx
0x180006eed  jnz     short loc_180006EC3
0x180006eef  test    rsi, rsi
0x180006ef2  jnz     short loc_180006F31
0x180006ef4  mov     rcx, [rdi]; lpFileName
0x180006ef7  mov     edx, 80h; dwFileAttributes
0x180006efc  call    cs:__imp_SetFileAttributesW
0x180006f02  mov     rcx, [rdi]; lpPathName
0x180006f05  test    r14d, r14d
0x180006f08  jz      short loc_180006F5E
0x180006f0a  call    cs:__imp_DeleteFileW
0x180006f10  test    eax, eax
0x180006f12  jz      short loc_180006F57
0x180006f14  mov     rdi, [rdi+30h]
0x180006f18  test    rdi, rdi
0x180006f1b  jnz     short loc_180006EC0
0x180006f1d  mov     rbx, [rsp+58h+arg_0]
0x180006f22  mov     eax, 1
0x180006f27  add     rsp, 38h
0x180006f2b  pop     r14
0x180006f2d  pop     rdi
0x180006f2e  pop     rsi
0x180006f2f  pop     rbp
0x180006f30  retn
0x180006f31  lea     rcx, [rdi+10h]; lpFileTime1
0x180006f35  mov     rdx, rsi; lpFileTime2
0x180006f38  call    cs:__imp_CompareFileTime
0x180006f3e  cmp     eax, 1
0x180006f41  jz      short loc_180006F14
0x180006f43  lea     rcx, [rdi+18h]; lpFileTime1
0x180006f47  mov     rdx, rsi; lpFileTime2
0x180006f4a  call    cs:__imp_CompareFileTime
0x180006f50  cmp     eax, 1
0x180006f53  jz      short loc_180006F14
0x180006f55  jmp     short loc_180006EF4
0x180006f57  mov     edx, 966h
0x180006f5c  jmp     short loc_180006F6D
0x180006f5e  call    cs:__imp_RemoveDirectoryW
0x180006f64  test    eax, eax
0x180006f66  jnz     short loc_180006F14
0x180006f68  mov     edx, 96Eh; void *
0x180006f6d  mov     rcx, [rsp+58h]; this
0x180006f72  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180006f77  jmp     short loc_180006F14
```
