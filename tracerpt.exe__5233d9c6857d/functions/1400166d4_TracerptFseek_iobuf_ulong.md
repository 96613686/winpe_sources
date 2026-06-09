# TracerptFseek(_iobuf *,ulong)

- ea: `0x1400166d4`
- end: `0x14001674b`
- name: `?TracerptFseek@@YAKPEAU_iobuf@@K@Z`
- size: `119`
- prototype: `unsigned int __fastcall(struct _iobuf *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000faa4`

## callees

- `0x1400166d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016717`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x140016722`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x140016722`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14001670c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14001670c`

## pseudocode

```c
DWORD __fastcall TracerptFseek(struct _iobuf *a1, unsigned int a2)
{
  unsigned int file; // ecx
  int v6; // ebx

  file = a1[1365]._file;
  if ( a2 > file + a1[1365]._flag )
    return 25;
  if ( a2 > file )
  {
    v6 = a2 - file;
  }
  else
  {
    if ( SetFilePointer(a1->_ptr, a2, 0, 0) == -1 || !SetEndOfFile(a1->_ptr) )
      return GetLastError();
    a1[1365]._file = a2;
    v6 = 0;
  }
  a1[1365]._flag = v6;
  return 0;
}

```

## disassembly

```asm
0x1400166d4  mov     [rsp+arg_0], rbx
0x1400166d9  push    rdi
0x1400166da  sub     rsp, 20h
0x1400166de  mov     rdi, rcx
0x1400166e1  mov     ebx, edx
0x1400166e3  mov     ecx, [rcx+1000Ch]
0x1400166e9  mov     r8d, [rdi+10008h]
0x1400166f0  add     r8d, ecx
0x1400166f3  cmp     edx, r8d
0x1400166f6  jbe     short loc_1400166FF
0x1400166f8  mov     eax, 19h
0x1400166fd  jmp     short loc_140016740
0x1400166ff  cmp     ebx, ecx
0x140016701  ja      short loc_140016736
0x140016703  mov     rcx, [rdi]; hFile
0x140016706  xor     r9d, r9d; dwMoveMethod
0x140016709  xor     r8d, r8d; lpDistanceToMoveHigh
0x14001670c  call    cs:__imp_SetFilePointer
0x140016712  cmp     eax, 0FFFFFFFFh
0x140016715  jnz     short loc_14001671F
0x140016717  call    cs:__imp_GetLastError
0x14001671d  jmp     short loc_140016740
0x14001671f  mov     rcx, [rdi]; hFile
0x140016722  call    cs:__imp_SetEndOfFile
0x140016728  test    eax, eax
0x14001672a  jz      short loc_140016717
0x14001672c  mov     [rdi+1000Ch], ebx
0x140016732  xor     ebx, ebx
0x140016734  jmp     short loc_140016738
0x140016736  sub     ebx, ecx
0x140016738  mov     [rdi+10008h], ebx
0x14001673e  xor     eax, eax
0x140016740  mov     rbx, [rsp+28h+arg_0]
0x140016745  add     rsp, 20h
0x140016749  pop     rdi
0x14001674a  retn
```
