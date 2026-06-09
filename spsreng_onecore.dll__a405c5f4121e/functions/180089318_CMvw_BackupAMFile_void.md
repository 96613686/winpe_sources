# CMvw::BackupAMFile(void)

- ea: `0x180089318`
- end: `0x1800893b3`
- name: `?BackupAMFile@CMvw@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(CMvw *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a8104`

## callees

- `0x180089318`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180089387`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180089387`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180089371`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800893a2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180089371`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800893a2`

## pseudocode

```c
void __fastcall CMvw::BackupAMFile(CMvw *this)
{
  const WCHAR *v2; // r9
  __int64 v3; // rax
  __int64 v4; // rcx
  const WCHAR *v5; // rdx

  if ( *((_DWORD *)this + 264) )
  {
    v2 = (const WCHAR *)*((_QWORD *)this + 129);
    if ( v2 )
    {
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( v2[v4] );
      if ( v4 )
      {
        v5 = (const WCHAR *)*((_QWORD *)this + 130);
        if ( v5 )
        {
          do
            ++v3;
          while ( v5[v3] );
          if ( v3 && !CopyFileW(v2, v5, 0) )
          {
            if ( SetFileAttributesW(*((LPCWSTR *)this + 130), 0x80u) )
              CopyFileW(*((LPCWSTR *)this + 129), *((LPCWSTR *)this + 130), 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180089318  mov     [rsp+arg_0], rbx
0x18008931d  push    rdi
0x18008931e  sub     rsp, 20h
0x180089322  xor     edi, edi
0x180089324  mov     rbx, rcx
0x180089327  cmp     [rcx+420h], edi
0x18008932d  jz      short loc_1800893A8
0x18008932f  mov     r9, [rcx+408h]
0x180089336  test    r9, r9
0x180089339  jz      short loc_1800893A8
0x18008933b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008933f  mov     rcx, rax
0x180089342  inc     rcx
0x180089345  cmp     [r9+rcx*2], di
0x18008934a  jnz     short loc_180089342
0x18008934c  test    rcx, rcx
0x18008934f  jz      short loc_1800893A8
0x180089351  mov     rdx, [rbx+410h]; lpNewFileName
0x180089358  test    rdx, rdx
0x18008935b  jz      short loc_1800893A8
0x18008935d  inc     rax
0x180089360  cmp     [rdx+rax*2], di
0x180089364  jnz     short loc_18008935D
0x180089366  test    rax, rax
0x180089369  jz      short loc_1800893A8
0x18008936b  xor     r8d, r8d; bFailIfExists
0x18008936e  mov     rcx, r9; lpExistingFileName
0x180089371  call    cs:__imp_CopyFileW
0x180089377  test    eax, eax
0x180089379  jnz     short loc_1800893A8
0x18008937b  mov     rcx, [rbx+410h]; lpFileName
0x180089382  mov     edx, 80h; dwFileAttributes
0x180089387  call    cs:__imp_SetFileAttributesW
0x18008938d  test    eax, eax
0x18008938f  jz      short loc_1800893A8
0x180089391  mov     rdx, [rbx+410h]; lpNewFileName
0x180089398  xor     r8d, r8d; bFailIfExists
0x18008939b  mov     rcx, [rbx+408h]; lpExistingFileName
0x1800893a2  call    cs:__imp_CopyFileW
0x1800893a8  mov     rbx, [rsp+28h+arg_0]
0x1800893ad  add     rsp, 20h
0x1800893b1  pop     rdi
0x1800893b2  retn
```
