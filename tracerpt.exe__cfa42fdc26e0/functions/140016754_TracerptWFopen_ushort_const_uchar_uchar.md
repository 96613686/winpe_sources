# TracerptWFopen(ushort const *,uchar,uchar)

- ea: `0x140016754`
- end: `0x140016801`
- name: `?TracerptWFopen@@YAPEAU_iobuf@@PEBGEE@Z`
- size: `173`
- prototype: `struct _iobuf *__fastcall(const unsigned __int16 *, char, char)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140011f98`
- `0x1400152e8`
- `0x140016ae0`
- `0x140018d04`
- `0x1400192b4`

## callees

- `0x140016754`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400167a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400167a7`

## pseudocode

```c
struct _iobuf *__fastcall TracerptWFopen(const unsigned __int16 *a1, char a2, char a3)
{
  __int64 v3; // rbx
  char *FileW; // r8
  struct _iobuf *result; // rax

  v3 = NumFileOpen;
  if ( NumFileOpen >= 2 )
    return 0;
  FileW = (char *)CreateFileW(a1, 0x40000000u, 0, 0, 2u, a3 != 0 ? 67108992 : 128, 0);
  if ( FileW == (char *)-1LL )
    return 0;
  ++NumFileOpen;
  result = (struct _iobuf *)(&FileCache + 8195 * v3);
  *(_QWORD *)&result[1365]._flag = 0;
  result->_ptr = FileW;
  LOBYTE(result[1365]._charbuf) = a2;
  BYTE1(result[1365]._charbuf) = a3;
  return result;
}

```

## disassembly

```asm
0x140016754  mov     r11, rsp
0x140016757  mov     [r11+8], rbx
0x14001675b  mov     [r11+10h], rsi
0x14001675f  push    rdi
0x140016760  sub     rsp, 40h
0x140016764  mov     ebx, cs:?NumFileOpen@@3KA; ulong NumFileOpen
0x14001676a  mov     dil, r8b
0x14001676d  mov     sil, dl
0x140016770  cmp     ebx, 2
0x140016773  jnb     short loc_1400167EF
0x140016775  mov     al, r8b
0x140016778  mov     qword ptr [r11-18h], 0
0x140016780  neg     al
0x140016782  mov     edx, 40000000h; dwDesiredAccess
0x140016787  sbb     r9d, r9d
0x14001678a  xor     r8d, r8d; dwShareMode
0x14001678d  and     r9d, 4000000h
0x140016794  sub     r9d, 0FFFFFF80h
0x140016798  mov     [r11-20h], r9d
0x14001679c  xor     r9d, r9d; lpSecurityAttributes
0x14001679f  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1400167a7  call    cs:__imp_CreateFileW
0x1400167ad  mov     r8, rax
0x1400167b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400167b4  jz      short loc_1400167EF
0x1400167b6  imul    rdx, rbx, 10018h
0x1400167bd  inc     cs:?NumFileOpen@@3KA; ulong NumFileOpen
0x1400167c3  lea     rcx, ?FileCache@@3PAU_FILE_CACHE@@A; _FILE_CACHE near * FileCache
0x1400167ca  lea     rax, [rdx+rcx]
0x1400167ce  mov     qword ptr [rdx+rcx+10008h], 0
0x1400167da  mov     [rax], r8
0x1400167dd  mov     [rdx+rcx+10010h], sil
0x1400167e5  mov     [rdx+rcx+10011h], dil
0x1400167ed  jmp     short loc_1400167F1
0x1400167ef  xor     eax, eax
0x1400167f1  mov     rbx, [rsp+48h+arg_0]
0x1400167f6  mov     rsi, [rsp+48h+arg_8]
0x1400167fb  add     rsp, 40h
0x1400167ff  pop     rdi
0x140016800  retn
```
