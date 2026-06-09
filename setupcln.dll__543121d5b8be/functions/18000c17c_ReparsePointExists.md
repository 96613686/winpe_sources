# ReparsePointExists

- ea: `0x18000c17c`
- end: `0x18000c1f3`
- name: `ReparsePointExists`
- size: `119`
- prototype: `__int64 __fastcall(const wchar_t *, BOOL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18000b380`
- `0x18000bb18`

## callees

- `0x18000a0f0`
- `0x18000c17c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1d2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c19d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c19d`

## pseudocode

```c
__int64 __fastcall ReparsePointExists(const wchar_t *a1, BOOL *a2)
{
  unsigned int v3; // ebx
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  DWORD FileAttributesW; // ebx
  DWORD LastError; // esi
  BOOL v8; // eax
  HANDLE ProcessHeap; // rax

  v3 = 0;
  v4 = PrepareUnicodePathEx(a1, 0);
  v5 = v4;
  if ( v4 )
  {
    FileAttributesW = GetFileAttributesW(v4);
    LastError = GetLastError();
    v8 = FileAttributesW != -1 && (FileAttributesW & 0x400) != 0;
    *a2 = v8;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    SetLastError(LastError);
    return LastError == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c17c  push    rbx
0x18000c17e  push    rsi
0x18000c17f  push    rdi
0x18000c180  push    r14
0x18000c182  sub     rsp, 28h
0x18000c186  mov     r14, rdx
0x18000c189  xor     ebx, ebx
0x18000c18b  xor     edx, edx
0x18000c18d  call    PrepareUnicodePathEx
0x18000c192  mov     rdi, rax
0x18000c195  test    rax, rax
0x18000c198  jz      short loc_18000C1E7
0x18000c19a  mov     rcx, rax; lpFileName
0x18000c19d  call    cs:__imp_GetFileAttributesW
0x18000c1a3  mov     ebx, eax
0x18000c1a5  call    cs:__imp_GetLastError
0x18000c1ab  mov     esi, eax
0x18000c1ad  cmp     ebx, 0FFFFFFFFh
0x18000c1b0  jz      short loc_18000C1BF
0x18000c1b2  bt      ebx, 0Ah
0x18000c1b6  jnb     short loc_18000C1BF
0x18000c1b8  mov     eax, 1
0x18000c1bd  jmp     short loc_18000C1C1
0x18000c1bf  xor     eax, eax
0x18000c1c1  mov     [r14], eax
0x18000c1c4  call    cs:__imp_GetProcessHeap
0x18000c1ca  mov     r8, rdi; lpMem
0x18000c1cd  xor     edx, edx; dwFlags
0x18000c1cf  mov     rcx, rax; hHeap
0x18000c1d2  call    cs:__imp_HeapFree
0x18000c1d8  mov     ecx, esi; dwErrCode
0x18000c1da  call    cs:__imp_SetLastError
0x18000c1e0  xor     ebx, ebx
0x18000c1e2  test    esi, esi
0x18000c1e4  setz    bl
0x18000c1e7  mov     eax, ebx
0x18000c1e9  add     rsp, 28h
0x18000c1ed  pop     r14
0x18000c1ef  pop     rdi
0x18000c1f0  pop     rsi
0x18000c1f1  pop     rbx
0x18000c1f2  retn
```
