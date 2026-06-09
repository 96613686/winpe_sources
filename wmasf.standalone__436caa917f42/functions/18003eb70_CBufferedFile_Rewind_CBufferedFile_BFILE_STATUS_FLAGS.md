# CBufferedFile::Rewind(CBufferedFile::BFILE_STATUS_FLAGS *)

- ea: `0x18003eb70`
- end: `0x18003ebe3`
- name: `?Rewind@CBufferedFile@@UEAAJPEAW4BFILE_STATUS_FLAGS@1@@Z`
- size: `115`
- prototype: `__int64 __fastcall(CBufferedFile *__hidden this, enum CBufferedFile::BFILE_STATUS_FLAGS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18003e3fc`
- `0x18003e9a4`
- `0x18003eb70`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003eb9e`
- `KERNEL32!SetFilePointer` at `0x18003eb9e`

## pseudocode

```c
__int64 __fastcall CBufferedFile::Rewind(CBufferedFile *this, enum CBufferedFile::BFILE_STATUS_FLAGS *a2)
{
  if ( !*((_QWORD *)this + 1) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 19) )
    CBufferedFile::CommitBuffer(this);
  if ( SetFilePointer(*((HANDLE *)this + 1), 0, 0, 0) == -1 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 8;
    return 2147500037LL;
  }
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 15) = 0;
  CBufferedFile::RefillBuffer((const void **)this, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18003eb70  mov     [rsp+arg_0], rbx
0x18003eb75  push    rdi
0x18003eb76  sub     rsp, 20h
0x18003eb7a  cmp     qword ptr [rcx+8], 0
0x18003eb7f  mov     rdi, rdx
0x18003eb82  mov     rbx, rcx
0x18003eb85  jz      short loc_18003EBB4
0x18003eb87  cmp     dword ptr [rcx+4Ch], 0
0x18003eb8b  jz      short loc_18003EB92
0x18003eb8d  call    ?CommitBuffer@CBufferedFile@@IEAAJXZ; CBufferedFile::CommitBuffer(void)
0x18003eb92  mov     rcx, [rbx+8]; hFile
0x18003eb96  xor     r9d, r9d; dwMoveMethod
0x18003eb99  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003eb9c  xor     edx, edx; lDistanceToMove
0x18003eb9e  call    cs:__imp_SetFilePointer
0x18003eba4  cmp     eax, 0FFFFFFFFh
0x18003eba7  jnz     short loc_18003EBC4
0x18003eba9  test    rdi, rdi
0x18003ebac  jz      short loc_18003EBB4
0x18003ebae  mov     dword ptr [rdi], 8
0x18003ebb4  mov     eax, 80004005h
0x18003ebb9  mov     rbx, [rsp+28h+arg_0]
0x18003ebbe  add     rsp, 20h
0x18003ebc2  pop     rdi
0x18003ebc3  retn
0x18003ebc4  xor     r8d, r8d; int
0x18003ebc7  mov     dword ptr [rbx+18h], 0
0x18003ebce  xor     edx, edx; unsigned int
0x18003ebd0  mov     dword ptr [rbx+3Ch], 0
0x18003ebd7  mov     rcx, rbx; this
0x18003ebda  call    ?RefillBuffer@CBufferedFile@@IEAAJKH@Z; CBufferedFile::RefillBuffer(ulong,int)
0x18003ebdf  xor     eax, eax
0x18003ebe1  jmp     short loc_18003EBB9
```
