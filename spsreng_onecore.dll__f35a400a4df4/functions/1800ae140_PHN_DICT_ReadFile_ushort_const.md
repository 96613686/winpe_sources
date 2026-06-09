# PHN_DICT::ReadFile(ushort const *)

- ea: `0x1800ae140`
- end: `0x1800ae259`
- name: `?ReadFile@PHN_DICT@@MEAAJPEBG@Z`
- size: `281`
- prototype: `__int64 __fastcall(PHN_DICT *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001f10`
- `0x180002470`
- `0x180002e00`
- `0x1800ad5d0`
- `0x1800ae140`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ae182`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ae182`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ae1fd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ae1fd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800ae1a3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800ae1a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae232`

## pseudocode

```c
__int64 __fastcall PHN_DICT::ReadFile(PHN_DICT *this, LPCWSTR lpFileName)
{
  void *v2; // rdi
  HANDLE FileW; // rax
  void *v5; // rsi
  int v6; // ebx
  DWORD FileSize; // ebx
  unsigned __int64 v8; // rax
  void *v9; // rax
  PHN_DICT *v10; // rcx
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = -2147467259;
LABEL_13:
    operator delete(v2);
    return (unsigned int)v6;
  }
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize == -1 )
    goto LABEL_11;
  v8 = 4 * (((unsigned __int64)FileSize >> 2) + 1);
  if ( !is_mul_ok(((unsigned __int64)FileSize >> 2) + 1, 4u) )
    v8 = -1;
  v9 = CWinHeap::Alloc((CWinHeap *)&g_heap, v8, 0);
  v2 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    goto LABEL_12;
  }
  if ( ReadFile(v5, v9, FileSize, &NumberOfBytesRead, 0) && FileSize == NumberOfBytesRead )
  {
    PHN_DICT::DeObfuscateBlock(v10, (unsigned int *)v2, FileSize);
    v6 = PHN_DICT::Init(this, (unsigned int *)v2, FileSize);
  }
  else
  {
LABEL_11:
    v6 = -2147467259;
  }
LABEL_12:
  CloseHandle(v5);
  if ( v6 < 0 )
    goto LABEL_13;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ae140  mov     [rsp+arg_0], rbx
0x1800ae145  mov     [rsp+arg_8], rbp
0x1800ae14a  push    rsi
0x1800ae14b  push    rdi
0x1800ae14c  push    r15
0x1800ae14e  sub     rsp, 40h
0x1800ae152  xor     edi, edi
0x1800ae154  mov     rax, rdx
0x1800ae157  mov     rbp, rcx
0x1800ae15a  mov     [rsp+58h+hTemplateFile], rdi; hTemplateFile
0x1800ae15f  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ae167  xor     r9d, r9d; lpSecurityAttributes
0x1800ae16a  mov     edx, 80000000h; dwDesiredAccess
0x1800ae16f  mov     [rsp+58h+NumberOfBytesRead], edi
0x1800ae173  lea     r8d, [rdi+1]; dwShareMode
0x1800ae177  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ae17f  mov     rcx, rax; lpFileName
0x1800ae182  call    cs:__imp_CreateFileW
0x1800ae188  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ae18c  mov     rsi, rax
0x1800ae18f  cmp     rax, r15
0x1800ae192  jnz     short loc_1800AE19E
0x1800ae194  mov     ebx, 80004005h
0x1800ae199  jmp     loc_1800AE23C
0x1800ae19e  xor     edx, edx; lpFileSizeHigh
0x1800ae1a0  mov     rcx, rsi; hFile
0x1800ae1a3  call    cs:__imp_GetFileSize
0x1800ae1a9  mov     ebx, eax
0x1800ae1ab  cmp     eax, 0FFFFFFFFh
0x1800ae1ae  jz      short loc_1800AE22A
0x1800ae1b0  mov     ecx, ebx
0x1800ae1b2  mov     eax, 4
0x1800ae1b7  shr     rcx, 2
0x1800ae1bb  inc     rcx
0x1800ae1be  mul     rcx
0x1800ae1c1  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800ae1c8  cmovb   rax, r15
0x1800ae1cc  xor     r8d, r8d; bool
0x1800ae1cf  mov     rdx, rax; unsigned __int64
0x1800ae1d2  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800ae1d7  mov     rdi, rax
0x1800ae1da  test    rax, rax
0x1800ae1dd  jnz     short loc_1800AE1E6
0x1800ae1df  mov     ebx, 8007000Eh
0x1800ae1e4  jmp     short loc_1800AE22F
0x1800ae1e6  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ae1eb  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x1800ae1f4  mov     r8d, ebx; nNumberOfBytesToRead
0x1800ae1f7  mov     rdx, rdi; lpBuffer
0x1800ae1fa  mov     rcx, rsi; hFile
0x1800ae1fd  call    cs:__imp_ReadFile
0x1800ae203  test    eax, eax
0x1800ae205  jz      short loc_1800AE22A
0x1800ae207  cmp     ebx, [rsp+58h+NumberOfBytesRead]
0x1800ae20b  jnz     short loc_1800AE22A
0x1800ae20d  mov     r8d, ebx; unsigned int
0x1800ae210  mov     rdx, rdi; unsigned int *
0x1800ae213  call    ?DeObfuscateBlock@PHN_DICT@@IEAAXPEAKK@Z; PHN_DICT::DeObfuscateBlock(ulong *,ulong)
0x1800ae218  mov     r8d, ebx; unsigned int
0x1800ae21b  mov     rdx, rdi; unsigned int *
0x1800ae21e  mov     rcx, rbp; this
0x1800ae221  call    ?Init@PHN_DICT@@QEAAJPEAKK@Z; PHN_DICT::Init(ulong *,ulong)
0x1800ae226  mov     ebx, eax
0x1800ae228  jmp     short loc_1800AE22F
0x1800ae22a  mov     ebx, 80004005h
0x1800ae22f  mov     rcx, rsi; hObject
0x1800ae232  call    cs:__imp_CloseHandle
0x1800ae238  test    ebx, ebx
0x1800ae23a  jns     short loc_1800AE244
0x1800ae23c  mov     rcx, rdi; void *
0x1800ae23f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae244  mov     rbp, [rsp+58h+arg_8]
0x1800ae249  mov     eax, ebx
0x1800ae24b  mov     rbx, [rsp+58h+arg_0]
0x1800ae250  add     rsp, 40h
0x1800ae254  pop     r15
0x1800ae256  pop     rdi
0x1800ae257  pop     rsi
0x1800ae258  retn
```
