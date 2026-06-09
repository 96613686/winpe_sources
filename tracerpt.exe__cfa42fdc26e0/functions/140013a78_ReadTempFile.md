# ReadTempFile

- ea: `0x140013a78`
- end: `0x140013b57`
- name: `ReadTempFile`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011a0c`
- `0x140011c74`

## callees

- `0x140013a78`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013b18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013b18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013b0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013b0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013ac9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140013ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b00`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140013af6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140013af6`

## pseudocode

```c
char *__fastcall ReadTempFile(__int64 a1, _DWORD *a2)
{
  int v4; // r8d
  __int64 v5; // rbp
  char *v6; // rbx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  void *v9; // rcx
  HANDLE v10; // rax
  char *result; // rax
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v4 = *(_DWORD *)(a1 + 65548);
  v5 = (unsigned int)(v4 + *(_DWORD *)(a1 + 65544));
  if ( !v4 )
  {
    v6 = (char *)(a1 + 8);
    goto LABEL_10;
  }
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, v5 + 1);
  v6 = v8;
  if ( !v8 )
    return 0;
  v9 = *(void **)a1;
  NumberOfBytesRead = 0;
  if ( ReadFile(v9, v8, v5, &NumberOfBytesRead, 0) )
  {
    memcpy_0(&v6[NumberOfBytesRead], (const void *)(a1 + 8), *(unsigned int *)(a1 + 65544));
    goto LABEL_10;
  }
  if ( GetLastError() )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v6);
    return 0;
  }
LABEL_10:
  v6[v5] = 0;
  result = v6;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x140013a78  mov     [rsp+arg_0], rbx
0x140013a7d  mov     [rsp+arg_10], rbp
0x140013a82  push    rsi
0x140013a83  push    rdi
0x140013a84  push    r14
0x140013a86  sub     rsp, 30h
0x140013a8a  mov     r14, rdx
0x140013a8d  mov     rdi, rcx
0x140013a90  test    rdx, rdx
0x140013a93  jz      loc_140013B1E
0x140013a99  mov     r8d, [rcx+1000Ch]
0x140013aa0  mov     ebp, [rcx+10008h]
0x140013aa6  add     ebp, r8d
0x140013aa9  test    r8d, r8d
0x140013aac  jnz     short loc_140013AB7
0x140013aae  lea     rbx, [rcx+8]
0x140013ab2  jmp     loc_140013B4A
0x140013ab7  call    cs:__imp_GetProcessHeap
0x140013abd  lea     r8, [rbp+1]; dwBytes
0x140013ac1  mov     edx, 8; dwFlags
0x140013ac6  mov     rcx, rax; hHeap
0x140013ac9  call    cs:__imp_HeapAlloc
0x140013acf  mov     rbx, rax
0x140013ad2  test    rax, rax
0x140013ad5  jz      short loc_140013B1E
0x140013ad7  mov     rcx, [rdi]; hFile
0x140013ada  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140013adf  mov     r8d, ebp; nNumberOfBytesToRead
0x140013ae2  mov     [rsp+48h+NumberOfBytesRead], 0
0x140013aea  mov     rdx, rax; lpBuffer
0x140013aed  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140013af6  call    cs:__imp_ReadFile
0x140013afc  test    eax, eax
0x140013afe  jnz     short loc_140013B33
0x140013b00  call    cs:__imp_GetLastError
0x140013b06  test    eax, eax
0x140013b08  jz      short loc_140013B4A
0x140013b0a  call    cs:__imp_GetProcessHeap
0x140013b10  mov     r8, rbx; lpMem
0x140013b13  xor     edx, edx; dwFlags
0x140013b15  mov     rcx, rax; hHeap
0x140013b18  call    cs:__imp_HeapFree
0x140013b1e  xor     eax, eax
0x140013b20  mov     rbx, [rsp+48h+arg_0]
0x140013b25  mov     rbp, [rsp+48h+arg_10]
0x140013b2a  add     rsp, 30h
0x140013b2e  pop     r14
0x140013b30  pop     rdi
0x140013b31  pop     rsi
0x140013b32  retn
0x140013b33  mov     ecx, [rsp+48h+NumberOfBytesRead]
0x140013b37  lea     rdx, [rdi+8]; Src
0x140013b3b  mov     r8d, [rdi+10008h]; Size
0x140013b42  add     rcx, rbx; void *
0x140013b45  call    memcpy_0
0x140013b4a  mov     byte ptr [rbp+rbx+0], 0
0x140013b4f  mov     rax, rbx
0x140013b52  mov     [r14], ebp
0x140013b55  jmp     short loc_140013B20
```
