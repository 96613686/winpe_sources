# SIPObject_::MapFile(void)

- ea: `0x18001fe70`
- end: `0x18001ff55`
- name: `?MapFile@SIPObject_@@MEAAHXZ`
- size: `229`
- prototype: `__int64 __fastcall(SIPObject_ *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001fe70`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001fe9b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001fe9b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ff0e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ff0e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001feda`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001feda`

## pseudocode

```c
__int64 __fastcall SIPObject_::MapFile(SIPObject_ *this)
{
  DWORD FileSize; // eax
  HANDLE FileMappingA; // rax
  LPVOID v5; // rax
  __int64 v6; // rax

  if ( !*((_DWORD *)this + 4) )
    return 1;
  if ( *((_QWORD *)this + 3) )
    (*(void (__fastcall **)(SIPObject_ *))(*(_QWORD *)this + 152LL))(this);
  FileSize = GetFileSize(*((HANDLE *)this + 1), 0);
  *((_DWORD *)this + 8) = FileSize;
  if ( FileSize <= 0x40000000 )
  {
    FileMappingA = CreateFileMappingA(
                     *((HANDLE *)this + 1),
                     0,
                     (*((_DWORD *)this + 12) & 0x40000000) != 0 ? 4 : 2,
                     0,
                     0,
                     0);
    *((_QWORD *)this + 5) = FileMappingA;
    if ( FileMappingA )
    {
      v5 = MapViewOfFile(FileMappingA, (*((_DWORD *)this + 12) & 0x40000000) != 0 ? 2 : 4, 0, 0, 0);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
        return 1;
    }
  }
  v6 = *(_QWORD *)this;
  *((_DWORD *)this + 8) = 0;
  (*(void (__fastcall **)(SIPObject_ *))(v6 + 152))(this);
  return 0;
}

```

## disassembly

```asm
0x18001fe70  push    rbx
0x18001fe72  sub     rsp, 30h
0x18001fe76  cmp     dword ptr [rcx+10h], 0
0x18001fe7a  mov     rbx, rcx
0x18001fe7d  jnz     short loc_18001FE8A
0x18001fe7f  mov     eax, 1
0x18001fe84  add     rsp, 30h
0x18001fe88  pop     rbx
0x18001fe89  retn
0x18001fe8a  cmp     qword ptr [rcx+18h], 0
0x18001fe8f  jnz     loc_18001FF41
0x18001fe95  mov     rcx, [rbx+8]; hFile
0x18001fe99  xor     edx, edx; lpFileSizeHigh
0x18001fe9b  call    cs:__imp_GetFileSize
0x18001fea1  mov     [rbx+20h], eax
0x18001fea4  cmp     eax, 40000000h
0x18001fea9  ja      short loc_18001FF21
0x18001feab  mov     eax, [rbx+30h]
0x18001feae  mov     rcx, [rbx+8]; hFile
0x18001feb2  and     eax, 40000000h
0x18001feb7  neg     eax
0x18001feb9  mov     [rsp+38h+lpName], 0; lpName
0x18001fec2  mov     [rsp+38h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18001feca  sbb     r8d, r8d
0x18001fecd  xor     r9d, r9d; dwMaximumSizeHigh
0x18001fed0  and     r8d, 2
0x18001fed4  xor     edx, edx; lpFileMappingAttributes
0x18001fed6  add     r8d, 2; flProtect
0x18001feda  call    cs:__imp_CreateFileMappingA
0x18001fee0  mov     [rbx+28h], rax
0x18001fee4  test    rax, rax
0x18001fee7  jz      short loc_18001FF21
0x18001fee9  mov     ecx, [rbx+30h]
0x18001feec  and     ecx, 40000000h
0x18001fef2  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001fefb  neg     ecx
0x18001fefd  mov     rcx, rax; hFileMappingObject
0x18001ff00  sbb     edx, edx
0x18001ff02  xor     r9d, r9d; dwFileOffsetLow
0x18001ff05  and     edx, 0FFFFFFFEh
0x18001ff08  xor     r8d, r8d; dwFileOffsetHigh
0x18001ff0b  add     edx, 4; dwDesiredAccess
0x18001ff0e  call    cs:__imp_MapViewOfFile
0x18001ff14  mov     [rbx+18h], rax
0x18001ff18  test    rax, rax
0x18001ff1b  jnz     loc_18001FE7F
0x18001ff21  mov     rax, [rbx]
0x18001ff24  mov     rcx, rbx
0x18001ff27  mov     dword ptr [rbx+20h], 0
0x18001ff2e  mov     rax, [rax+98h]
0x18001ff35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff3a  xor     eax, eax
0x18001ff3c  jmp     loc_18001FE84
0x18001ff41  mov     rax, [rcx]
0x18001ff44  mov     rax, [rax+98h]
0x18001ff4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff50  jmp     loc_18001FE95
```
