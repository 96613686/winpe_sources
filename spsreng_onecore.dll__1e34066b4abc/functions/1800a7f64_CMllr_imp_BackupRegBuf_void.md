# CMllr_imp::BackupRegBuf(void)

- ea: `0x1800a7f64`
- end: `0x1800a7ffb`
- name: `?BackupRegBuf@CMllr_imp@@AEAAXXZ`
- size: `151`
- prototype: `void __fastcall(CMllr_imp *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a8104`

## callees

- `0x1800a7f64`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a7fcf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a7fcf`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800a7fb9`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800a7fea`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800a7fb9`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800a7fea`

## pseudocode

```c
void __fastcall CMllr_imp::BackupRegBuf(CMllr_imp *this)
{
  const WCHAR *v2; // rdx
  __int64 v3; // rax
  __int64 v4; // rcx
  const WCHAR *v5; // rcx

  if ( *((_DWORD *)this + 104) )
  {
    v2 = (const WCHAR *)*((_QWORD *)this + 50);
    if ( v2 )
    {
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( v2[v4] );
      if ( v4 )
      {
        v5 = (const WCHAR *)*((_QWORD *)this + 48);
        if ( v5 )
        {
          do
            ++v3;
          while ( v5[v3] );
          if ( v3 && !CopyFileW(v5, v2, 0) )
          {
            if ( SetFileAttributesW(*((LPCWSTR *)this + 50), 0x80u) )
              CopyFileW(*((LPCWSTR *)this + 48), *((LPCWSTR *)this + 50), 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a7f64  mov     [rsp+arg_0], rbx
0x1800a7f69  push    rdi
0x1800a7f6a  sub     rsp, 20h
0x1800a7f6e  xor     edi, edi
0x1800a7f70  mov     rbx, rcx
0x1800a7f73  cmp     [rcx+1A0h], edi
0x1800a7f79  jz      short loc_1800A7FF0
0x1800a7f7b  mov     rdx, [rcx+190h]; lpNewFileName
0x1800a7f82  test    rdx, rdx
0x1800a7f85  jz      short loc_1800A7FF0
0x1800a7f87  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7f8b  mov     rcx, rax
0x1800a7f8e  inc     rcx
0x1800a7f91  cmp     [rdx+rcx*2], di
0x1800a7f95  jnz     short loc_1800A7F8E
0x1800a7f97  test    rcx, rcx
0x1800a7f9a  jz      short loc_1800A7FF0
0x1800a7f9c  mov     rcx, [rbx+180h]; lpExistingFileName
0x1800a7fa3  test    rcx, rcx
0x1800a7fa6  jz      short loc_1800A7FF0
0x1800a7fa8  inc     rax
0x1800a7fab  cmp     [rcx+rax*2], di
0x1800a7faf  jnz     short loc_1800A7FA8
0x1800a7fb1  test    rax, rax
0x1800a7fb4  jz      short loc_1800A7FF0
0x1800a7fb6  xor     r8d, r8d; bFailIfExists
0x1800a7fb9  call    cs:__imp_CopyFileW
0x1800a7fbf  test    eax, eax
0x1800a7fc1  jnz     short loc_1800A7FF0
0x1800a7fc3  mov     rcx, [rbx+190h]; lpFileName
0x1800a7fca  mov     edx, 80h; dwFileAttributes
0x1800a7fcf  call    cs:__imp_SetFileAttributesW
0x1800a7fd5  test    eax, eax
0x1800a7fd7  jz      short loc_1800A7FF0
0x1800a7fd9  mov     rdx, [rbx+190h]; lpNewFileName
0x1800a7fe0  xor     r8d, r8d; bFailIfExists
0x1800a7fe3  mov     rcx, [rbx+180h]; lpExistingFileName
0x1800a7fea  call    cs:__imp_CopyFileW
0x1800a7ff0  mov     rbx, [rsp+28h+arg_0]
0x1800a7ff5  add     rsp, 20h
0x1800a7ff9  pop     rdi
0x1800a7ffa  retn
```
