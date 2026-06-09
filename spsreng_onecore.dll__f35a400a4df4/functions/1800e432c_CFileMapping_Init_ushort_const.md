# CFileMapping::Init(ushort const *)

- ea: `0x1800e432c`
- end: `0x1800e4426`
- name: `?Init@CFileMapping@@QEAAJPEBG@Z`
- size: `250`
- prototype: `__int64 __fastcall(CFileMapping *__hidden this, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800e4430`
- `0x1800fbc4c`

## callees

- `0x1800055cc`
- `0x1800e4290`
- `0x1800e432c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e437a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e437a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800e43f7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800e43f7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800e43be`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800e43be`

## pseudocode

```c
__int64 __fastcall CFileMapping::Init(CFileMapping *this, LPCWSTR lpFileName)
{
  int Win32Error; // ebx
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax

  Win32Error = 0;
  FileW = CreateFileW(
            lpFileName,
            *(_DWORD *)this != 0 ? 0x80000000 : -1073741824,
            *(_DWORD *)this != 0 ? 1 : 3,
            0,
            3u,
            0x50000000u,
            0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL && (Win32Error = HrFromLastWin32Error(), Win32Error < 0)
    || (FileMappingW = CreateFileMappingW(*((HANDLE *)this + 1), 0, *(_DWORD *)this != 0 ? 2 : 4, 0, 0, 0),
        (*((_QWORD *)this + 2) = FileMappingW) == 0)
    && (Win32Error = HrFromLastWin32Error(), Win32Error < 0)
    || (v6 = MapViewOfFile(*((HANDLE *)this + 2), *(_DWORD *)this != 0 ? 4 : 2, 0, 0, 0),
        (*((_QWORD *)this + 3) = v6) == 0)
    && (Win32Error = HrFromLastWin32Error(), Win32Error < 0) )
  {
    CFileMapping::Clear(this);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800e432c  mov     [rsp+arg_0], rbx
0x1800e4331  push    rdi
0x1800e4332  sub     rsp, 40h
0x1800e4336  mov     r9d, [rcx]
0x1800e4339  mov     r10, rdx
0x1800e433c  mov     eax, r9d
0x1800e433f  xor     ebx, ebx
0x1800e4341  neg     eax
0x1800e4343  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800e4348  mov     eax, 0C0000000h
0x1800e434d  mov     [rsp+48h+dwFlagsAndAttributes], 50000000h; dwFlagsAndAttributes
0x1800e4355  sbb     r8d, r8d
0x1800e4358  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e4360  and     r8d, 0FFFFFFFEh
0x1800e4364  mov     rdi, rcx
0x1800e4367  add     r8d, 3; dwShareMode
0x1800e436b  mov     rcx, r10; lpFileName
0x1800e436e  neg     r9d
0x1800e4371  sbb     edx, edx
0x1800e4373  xor     r9d, r9d; lpSecurityAttributes
0x1800e4376  and     edx, eax
0x1800e4378  add     edx, eax; dwDesiredAccess
0x1800e437a  call    cs:__imp_CreateFileW
0x1800e4380  mov     [rdi+8], rax
0x1800e4384  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e4388  jnz     short loc_1800E4395
0x1800e438a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800e438f  mov     ebx, eax
0x1800e4391  test    eax, eax
0x1800e4393  js      short loc_1800E4411
0x1800e4395  mov     ecx, [rdi]
0x1800e4397  neg     ecx
0x1800e4399  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1800e43a2  mov     rcx, [rdi+8]; hFile
0x1800e43a6  sbb     r8d, r8d
0x1800e43a9  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800e43b1  and     r8d, 0FFFFFFFEh
0x1800e43b5  xor     r9d, r9d; dwMaximumSizeHigh
0x1800e43b8  add     r8d, 4; flProtect
0x1800e43bc  xor     edx, edx; lpFileMappingAttributes
0x1800e43be  call    cs:__imp_CreateFileMappingW
0x1800e43c4  mov     [rdi+10h], rax
0x1800e43c8  test    rax, rax
0x1800e43cb  jnz     short loc_1800E43D8
0x1800e43cd  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800e43d2  mov     ebx, eax
0x1800e43d4  test    eax, eax
0x1800e43d6  js      short loc_1800E4411
0x1800e43d8  mov     eax, [rdi]
0x1800e43da  mov     rcx, [rdi+10h]; hFileMappingObject
0x1800e43de  neg     eax
0x1800e43e0  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800e43e9  sbb     edx, edx
0x1800e43eb  xor     r9d, r9d; dwFileOffsetLow
0x1800e43ee  and     edx, 2
0x1800e43f1  xor     r8d, r8d; dwFileOffsetHigh
0x1800e43f4  add     edx, 2; dwDesiredAccess
0x1800e43f7  call    cs:__imp_MapViewOfFile
0x1800e43fd  mov     [rdi+18h], rax
0x1800e4401  test    rax, rax
0x1800e4404  jnz     short loc_1800E4419
0x1800e4406  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800e440b  mov     ebx, eax
0x1800e440d  test    eax, eax
0x1800e440f  jns     short loc_1800E4419
0x1800e4411  mov     rcx, rdi; this
0x1800e4414  call    ?Clear@CFileMapping@@AEAAXXZ; CFileMapping::Clear(void)
0x1800e4419  mov     eax, ebx
0x1800e441b  mov     rbx, [rsp+48h+arg_0]
0x1800e4420  add     rsp, 40h
0x1800e4424  pop     rdi
0x1800e4425  retn
```
