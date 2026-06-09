# DSA_DestroyFileCallback(FILESTRUCT const *,void *)

- ea: `0x18002a210`
- end: `0x18002a24a`
- name: `?DSA_DestroyFileCallback@@YAHPEBUFILESTRUCT@@PEAX@Z`
- size: `58`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18002a210`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a239`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a239`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a219`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a219`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a230`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a230`

## pseudocode

```c
__int64 __fastcall DSA_DestroyFileCallback(const WCHAR *p, void *pData)
{
  DWORD FileAttributesW; // eax

  FileAttributesW = GetFileAttributesW(p);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
  {
    SetFileAttributesW(p, FileAttributesW & 0xFFFFFFFE);
    DeleteFileW(p);
  }
  return 1;
}

```

## disassembly

```asm
0x18002a210  push    rbx
0x18002a212  sub     rsp, 20h
0x18002a216  mov     rbx, rcx
0x18002a219  call    cs:__imp_GetFileAttributesW
0x18002a21f  cmp     eax, 0FFFFFFFFh
0x18002a222  jz      short loc_18002A23F
0x18002a224  test    al, 1
0x18002a226  jz      short loc_18002A23F
0x18002a228  and     eax, 0FFFFFFFEh
0x18002a22b  mov     rcx, rbx; lpFileName
0x18002a22e  mov     edx, eax; dwFileAttributes
0x18002a230  call    cs:__imp_SetFileAttributesW
0x18002a236  mov     rcx, rbx; lpFileName
0x18002a239  call    cs:__imp_DeleteFileW
0x18002a23f  mov     eax, 1
0x18002a244  add     rsp, 20h
0x18002a248  pop     rbx
0x18002a249  retn
```
