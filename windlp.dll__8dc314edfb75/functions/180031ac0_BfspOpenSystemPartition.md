# BfspOpenSystemPartition

- ea: `0x180031ac0`
- end: `0x180031b47`
- name: `BfspOpenSystemPartition`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180032518`

## callees

- `0x1800315c4`
- `0x180031ac0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031b0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031b0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031b34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b17`

## pseudocode

```c
__int64 __fastcall BfspOpenSystemPartition(_QWORD *a1)
{
  wchar_t *SystemPartition; // rax
  wchar_t *v3; // rdi
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  HANDLE ProcessHeap; // rax

  SystemPartition = BfspGetSystemPartition();
  v3 = SystemPartition;
  if ( SystemPartition )
  {
    FileW = CreateFileW(SystemPartition, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      *a1 = FileW;
      LastError = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180031ac0  mov     [rsp+arg_0], rbx
0x180031ac5  push    rdi
0x180031ac6  sub     rsp, 40h
0x180031aca  mov     rbx, rcx
0x180031acd  call    BfspGetSystemPartition
0x180031ad2  mov     rdi, rax
0x180031ad5  test    rax, rax
0x180031ad8  jnz     short loc_180031AE4
0x180031ada  call    cs:__imp_GetLastError
0x180031ae0  mov     ebx, eax
0x180031ae2  jmp     short loc_180031B3A
0x180031ae4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180031aed  mov     r8d, 3; dwShareMode
0x180031af3  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180031afb  xor     r9d, r9d; lpSecurityAttributes
0x180031afe  mov     edx, 0C0000000h; dwDesiredAccess
0x180031b03  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180031b08  mov     rcx, rdi; lpFileName
0x180031b0b  call    cs:__imp_CreateFileW
0x180031b11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031b15  jnz     short loc_180031B21
0x180031b17  call    cs:__imp_GetLastError
0x180031b1d  mov     ebx, eax
0x180031b1f  jmp     short loc_180031B26
0x180031b21  mov     [rbx], rax
0x180031b24  xor     ebx, ebx
0x180031b26  call    cs:__imp_GetProcessHeap
0x180031b2c  mov     r8, rdi; lpMem
0x180031b2f  xor     edx, edx; dwFlags
0x180031b31  mov     rcx, rax; hHeap
0x180031b34  call    cs:__imp_HeapFree
0x180031b3a  mov     eax, ebx
0x180031b3c  mov     rbx, [rsp+48h+arg_0]
0x180031b41  add     rsp, 40h
0x180031b45  pop     rdi
0x180031b46  retn
```
