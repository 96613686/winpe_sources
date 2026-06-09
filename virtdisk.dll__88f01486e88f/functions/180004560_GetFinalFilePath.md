# GetFinalFilePath

- ea: `0x180004560`
- end: `0x1800045fe`
- name: `GetFinalFilePath`
- size: `158`
- prototype: `DWORD __fastcall(const WCHAR *, PVOID *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002740`

## callees

- `0x180003800`
- `0x180004560`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000459c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000459c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045df`

## pseudocode

```c
DWORD __fastcall GetFinalFilePath(const WCHAR *a1, PVOID *a2, _DWORD *a3)
{
  HANDLE FileW; // rax
  void *v6; // rbx
  int FinalFilePathWithHandle; // edi

  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x100080u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  FinalFilePathWithHandle = GetFinalFilePathWithHandle(FileW, a2, a3);
  CloseHandle(v6);
  return FinalFilePathWithHandle;
}

```

## disassembly

```asm
0x180004560  mov     [rsp+arg_0], rbx
0x180004565  mov     [rsp+arg_8], rsi
0x18000456a  push    rdi
0x18000456b  sub     rsp, 40h
0x18000456f  mov     rdi, r8
0x180004572  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000457b  mov     rsi, rdx
0x18000457e  mov     [rsp+48h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180004586  mov     edx, 80h; dwDesiredAccess
0x18000458b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180004593  mov     r8d, 7; dwShareMode
0x180004599  xor     r9d, r9d; lpSecurityAttributes
0x18000459c  call    cs:__imp_CreateFileW
0x1800045a3  nop     dword ptr [rax+rax+00h]
0x1800045a8  mov     rbx, rax
0x1800045ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800045af  jnz     short loc_1800045CC
0x1800045b1  mov     rbx, [rsp+48h+arg_0]
0x1800045b6  mov     rsi, [rsp+48h+arg_8]
0x1800045bb  add     rsp, 40h
0x1800045bf  pop     rdi
0x1800045c0  jmp     cs:__imp_GetLastError
0x1800045cc  mov     r8, rdi
0x1800045cf  mov     rdx, rsi
0x1800045d2  mov     rcx, rbx; hFile
0x1800045d5  call    GetFinalFilePathWithHandle
0x1800045da  mov     rcx, rbx; hObject
0x1800045dd  mov     edi, eax
0x1800045df  call    cs:__imp_CloseHandle
0x1800045e6  nop     dword ptr [rax+rax+00h]
0x1800045eb  mov     rbx, [rsp+48h+arg_0]
0x1800045f0  mov     eax, edi
0x1800045f2  mov     rsi, [rsp+48h+arg_8]
0x1800045f7  add     rsp, 40h
0x1800045fb  pop     rdi
0x1800045fc  retn
```
