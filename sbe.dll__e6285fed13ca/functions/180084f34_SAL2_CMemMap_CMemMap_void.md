# SAL2::CMemMap::~CMemMap(void)

- ea: `0x180084f34`
- end: `0x18008502a`
- name: `??1CMemMap@SAL2@@MEAA@XZ`
- size: `246`
- prototype: `void __fastcall(SAL2::CMemMap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180085210`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x180084f34`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180084f97`
- `KERNEL32!CloseHandle` at `0x180084fe2`
- `KERNEL32!CloseHandle` at `0x180084f97`
- `KERNEL32!CloseHandle` at `0x180084fe2`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180084fc6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180084fc6`
- `KERNEL32!UnmapViewOfFile` at `0x180084f7a`
- `KERNEL32!UnmapViewOfFile` at `0x180084f7a`
- `KERNEL32!DeleteFileW` at `0x180085001`
- `KERNEL32!DeleteFileW` at `0x180085001`

## pseudocode

```c
void __fastcall SAL2::CMemMap::~CMemMap(SAL2::CMemMap *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  WCHAR szFilePath[264]; // [rsp+20h] [rbp-228h] BYREF

  *(_QWORD *)this = &SAL2::CMemMap::`vftable';
  memset_0(szFilePath, 0, 0x20Au);
  v2 = (const void *)*((_QWORD *)this + 68);
  if ( v2 )
  {
    UnmapViewOfFile(v2);
    *((_QWORD *)this + 68) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 67);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 67) = 0;
  }
  if ( *((_DWORD *)this + 142) && !GetFinalPathNameByHandleW(*((HANDLE *)this + 70), szFilePath, 0x104u, 0) )
    *((_DWORD *)this + 142) = 0;
  v4 = (void *)*((_QWORD *)this + 70);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 70) = 0;
  }
  if ( *((_DWORD *)this + 142) )
    DeleteFileW(szFilePath);
  *(_QWORD *)this = &SBFThunk::CStreamCtx::`vftable';
}

```

## disassembly

```asm
0x180084f34  push    rbx
0x180084f36  sub     rsp, 240h
0x180084f3d  mov     rax, cs:__security_cookie
0x180084f44  xor     rax, rsp
0x180084f47  mov     [rsp+248h+var_18], rax
0x180084f4f  lea     rax, ??_7CMemMap@SAL2@@6B@; const SAL2::CMemMap::`vftable'
0x180084f56  mov     rbx, rcx
0x180084f59  mov     [rcx], rax
0x180084f5c  xor     edx, edx; Val
0x180084f5e  lea     rcx, [rsp+248h+szFilePath]; void *
0x180084f63  mov     r8d, 20Ah; Size
0x180084f69  call    memset_0
0x180084f6e  mov     rcx, [rbx+220h]; lpBaseAddress
0x180084f75  test    rcx, rcx
0x180084f78  jz      short loc_180084F8B
0x180084f7a  call    cs:__imp_UnmapViewOfFile
0x180084f80  mov     qword ptr [rbx+220h], 0
0x180084f8b  mov     rcx, [rbx+218h]; hObject
0x180084f92  test    rcx, rcx
0x180084f95  jz      short loc_180084FA8
0x180084f97  call    cs:__imp_CloseHandle
0x180084f9d  mov     qword ptr [rbx+218h], 0
0x180084fa8  cmp     dword ptr [rbx+238h], 0
0x180084faf  jz      short loc_180084FD6
0x180084fb1  mov     rcx, [rbx+230h]; hFile
0x180084fb8  lea     rdx, [rsp+248h+szFilePath]; lpszFilePath
0x180084fbd  xor     r9d, r9d; dwFlags
0x180084fc0  mov     r8d, 104h; cchFilePath
0x180084fc6  call    cs:__imp_GetFinalPathNameByHandleW
0x180084fcc  test    eax, eax
0x180084fce  jnz     short loc_180084FD6
0x180084fd0  mov     [rbx+238h], eax
0x180084fd6  mov     rcx, [rbx+230h]; hObject
0x180084fdd  test    rcx, rcx
0x180084fe0  jz      short loc_180084FF3
0x180084fe2  call    cs:__imp_CloseHandle
0x180084fe8  mov     qword ptr [rbx+230h], 0
0x180084ff3  cmp     dword ptr [rbx+238h], 0
0x180084ffa  jz      short loc_180085007
0x180084ffc  lea     rcx, [rsp+248h+szFilePath]; lpFileName
0x180085001  call    cs:__imp_DeleteFileW
0x180085007  lea     rax, ??_7CStreamCtx@SBFThunk@@6B@; const SBFThunk::CStreamCtx::`vftable'
0x18008500e  mov     [rbx], rax
0x180085011  mov     rcx, [rsp+248h+var_18]
0x180085019  xor     rcx, rsp; StackCookie
0x18008501c  call    __security_check_cookie
0x180085021  add     rsp, 240h
0x180085028  pop     rbx
0x180085029  retn
```
