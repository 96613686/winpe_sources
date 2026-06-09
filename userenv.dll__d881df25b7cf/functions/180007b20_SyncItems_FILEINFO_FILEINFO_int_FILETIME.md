# SyncItems(_FILEINFO *,_FILEINFO *,int,_FILETIME *)

- ea: `0x180007b20`
- end: `0x180007c2e`
- name: `?SyncItems@@YAHPEAU_FILEINFO@@0HPEAU_FILETIME@@@Z`
- size: `270`
- prototype: `int(struct _FILEINFO *, struct _FILEINFO *, int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ab88`

## callees

- `0x180007b20`
- `0x18000ddf0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b6b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b6b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007bdb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007bf3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007bdb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007bf3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007b92`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007b92`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007ba6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007ba6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180007c0d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180007c0d`

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
0x180007b20  push    rbp
0x180007b22  push    rsi
0x180007b23  push    rdi
0x180007b24  push    r14
0x180007b26  sub     rsp, 38h
0x180007b2a  mov     rsi, r9
0x180007b2d  mov     r14d, r8d
0x180007b30  mov     rdi, rdx
0x180007b33  mov     rbp, rcx
0x180007b36  test    rcx, rcx
0x180007b39  jz      loc_180007BC4
0x180007b3f  test    rdx, rdx
0x180007b42  jz      loc_180007BC4
0x180007b48  mov     [rsp+58h+arg_0], rbx
0x180007b4d  nop     dword ptr [rax]
0x180007b50  mov     rbx, rbp
0x180007b53  mov     r8, [rbx+8]; lpString2
0x180007b57  mov     r9d, 0FFFFFFFFh; cchCount2
0x180007b5d  mov     rcx, [rdi]; lpString1
0x180007b60  mov     edx, r9d; cchCount1
0x180007b63  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180007b6b  call    cs:__imp_CompareStringOrdinal
0x180007b72  nop     dword ptr [rax+rax+00h]
0x180007b77  cmp     eax, 2
0x180007b7a  jz      short loc_180007BB6
0x180007b7c  mov     rbx, [rbx+30h]
0x180007b80  test    rbx, rbx
0x180007b83  jnz     short loc_180007B53
0x180007b85  test    rsi, rsi
0x180007b88  jnz     short loc_180007BD4
0x180007b8a  mov     rcx, [rdi]; lpFileName
0x180007b8d  mov     edx, 80h; dwFileAttributes
0x180007b92  call    cs:__imp_SetFileAttributesW
0x180007b99  nop     dword ptr [rax+rax+00h]
0x180007b9e  mov     rcx, [rdi]; lpPathName
0x180007ba1  test    r14d, r14d
0x180007ba4  jz      short loc_180007C0D
0x180007ba6  call    cs:__imp_DeleteFileW
0x180007bad  nop     dword ptr [rax+rax+00h]
0x180007bb2  test    eax, eax
0x180007bb4  jz      short loc_180007C06
0x180007bb6  mov     rdi, [rdi+30h]
0x180007bba  test    rdi, rdi
0x180007bbd  jnz     short loc_180007B50
0x180007bbf  mov     rbx, [rsp+58h+arg_0]
0x180007bc4  mov     eax, 1
0x180007bc9  add     rsp, 38h
0x180007bcd  pop     r14
0x180007bcf  pop     rdi
0x180007bd0  pop     rsi
0x180007bd1  pop     rbp
0x180007bd2  retn
0x180007bd4  lea     rcx, [rdi+10h]; lpFileTime1
0x180007bd8  mov     rdx, rsi; lpFileTime2
0x180007bdb  call    cs:__imp_CompareFileTime
0x180007be2  nop     dword ptr [rax+rax+00h]
0x180007be7  cmp     eax, 1
0x180007bea  jz      short loc_180007BB6
0x180007bec  lea     rcx, [rdi+18h]; lpFileTime1
0x180007bf0  mov     rdx, rsi; lpFileTime2
0x180007bf3  call    cs:__imp_CompareFileTime
0x180007bfa  nop     dword ptr [rax+rax+00h]
0x180007bff  cmp     eax, 1
0x180007c02  jz      short loc_180007BB6
0x180007c04  jmp     short loc_180007B8A
0x180007c06  mov     edx, 966h
0x180007c0b  jmp     short loc_180007C22
0x180007c0d  call    cs:__imp_RemoveDirectoryW
0x180007c14  nop     dword ptr [rax+rax+00h]
0x180007c19  test    eax, eax
0x180007c1b  jnz     short loc_180007BB6
0x180007c1d  mov     edx, 96Eh; void *
0x180007c22  mov     rcx, [rsp+58h]; this
0x180007c27  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180007c2c  jmp     short loc_180007BB6
```
