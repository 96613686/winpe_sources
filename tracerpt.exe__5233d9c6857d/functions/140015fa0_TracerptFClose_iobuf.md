# TracerptFClose(_iobuf *)

- ea: `0x140015fa0`
- end: `0x140016013`
- name: `?TracerptFClose@@YAHPEAU_iobuf@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct _iobuf *)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140011a0c`
- `0x140011c74`
- `0x1400152e8`
- `0x140016ae0`
- `0x140017398`
- `0x1400192b4`

## callees

- `0x140015fa0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140015fe4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140015fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016007`

## pseudocode

```c
BOOL __fastcall TracerptFClose(struct _iobuf *a1)
{
  DWORD flag; // r8d
  char *ptr; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a1 )
    return 0;
  flag = a1[1365]._flag;
  if ( flag )
  {
    if ( !BYTE1(a1[1365]._charbuf) )
    {
      WriteFile(a1->_ptr, &a1->_cnt, flag, &NumberOfBytesWritten, 0);
      a1[1365]._file += NumberOfBytesWritten;
    }
  }
  --NumFileOpen;
  ptr = a1->_ptr;
  a1[1365]._flag = 0;
  return CloseHandle(ptr);
}

```

## disassembly

```asm
0x140015fa0  push    rbx
0x140015fa2  sub     rsp, 30h
0x140015fa6  mov     [rsp+38h+NumberOfBytesWritten], 0
0x140015fae  mov     rbx, rcx
0x140015fb1  test    rcx, rcx
0x140015fb4  jnz     short loc_140015FBA
0x140015fb6  xor     eax, eax
0x140015fb8  jmp     short loc_14001600D
0x140015fba  mov     r8d, [rcx+10008h]; nNumberOfBytesToWrite
0x140015fc1  test    r8d, r8d
0x140015fc4  jz      short loc_140015FF4
0x140015fc6  cmp     byte ptr [rcx+10011h], 0
0x140015fcd  jnz     short loc_140015FF4
0x140015fcf  lea     rdx, [rcx+8]; lpBuffer
0x140015fd3  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140015fdc  mov     rcx, [rcx]; hFile
0x140015fdf  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140015fe4  call    cs:__imp_WriteFile
0x140015fea  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x140015fee  add     [rbx+1000Ch], eax
0x140015ff4  dec     cs:?NumFileOpen@@3KA; ulong NumFileOpen
0x140015ffa  mov     rcx, [rbx]; hObject
0x140015ffd  mov     dword ptr [rbx+10008h], 0
0x140016007  call    cs:__imp_CloseHandle
0x14001600d  add     rsp, 30h
0x140016011  pop     rbx
0x140016012  retn
```
