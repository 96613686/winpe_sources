# CBufferedFile::SeekTo(unsigned __int64,CBufferedFile::BFILE_STATUS_FLAGS *)

- ea: `0x18003ece0`
- end: `0x18003ed84`
- name: `?SeekTo@CBufferedFile@@UEAAJ_KPEAW4BFILE_STATUS_FLAGS@1@@Z`
- size: `164`
- prototype: `__int64 __fastcall(CBufferedFile *__hidden this, LONG lDistanceToMove, enum CBufferedFile::BFILE_STATUS_FLAGS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d0`
- `0x18003e3fc`
- `0x18003e9a4`
- `0x18003ece0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ed36`
- `KERNEL32!GetLastError` at `0x18003ed36`
- `KERNEL32!SetFilePointer` at `0x18003ed2b`
- `KERNEL32!SetFilePointer` at `0x18003ed2b`

## pseudocode

```c
__int64 __fastcall CBufferedFile::SeekTo(
        CBufferedFile *this,
        __int64 lDistanceToMove,
        enum CBufferedFile::BFILE_STATUS_FLAGS *a3)
{
  void *v6; // rcx
  LONG DistanceToMoveHigh; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 19) )
    CBufferedFile::CommitBuffer(this);
  v6 = (void *)*((_QWORD *)this + 1);
  DistanceToMoveHigh = HIDWORD(lDistanceToMove);
  if ( SetFilePointer(v6, lDistanceToMove, &DistanceToMoveHigh, 0) == -1 && GetLastError() )
  {
    if ( a3 )
      *(_DWORD *)a3 = 8;
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
0x18003ece0  push    rbx
0x18003ece2  push    rsi
0x18003ece3  push    rdi
0x18003ece4  sub     rsp, 30h
0x18003ece8  mov     rax, cs:__security_cookie
0x18003ecef  xor     rax, rsp
0x18003ecf2  mov     [rsp+48h+var_20], rax
0x18003ecf7  cmp     qword ptr [rcx+8], 0
0x18003ecfc  mov     rdi, r8
0x18003ecff  mov     rsi, rdx
0x18003ed02  mov     rbx, rcx
0x18003ed05  jz      short loc_18003ED4B
0x18003ed07  cmp     dword ptr [rcx+4Ch], 0
0x18003ed0b  jz      short loc_18003ED12
0x18003ed0d  call    ?CommitBuffer@CBufferedFile@@IEAAJXZ; CBufferedFile::CommitBuffer(void)
0x18003ed12  mov     rcx, [rbx+8]; hFile
0x18003ed16  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18003ed1b  mov     rax, rsi
0x18003ed1e  mov     edx, esi; lDistanceToMove
0x18003ed20  shr     rax, 20h
0x18003ed24  xor     r9d, r9d; dwMoveMethod
0x18003ed27  mov     [rsp+48h+DistanceToMoveHigh], eax
0x18003ed2b  call    cs:__imp_SetFilePointer
0x18003ed31  cmp     eax, 0FFFFFFFFh
0x18003ed34  jnz     short loc_18003ED65
0x18003ed36  call    cs:__imp_GetLastError
0x18003ed3c  test    eax, eax
0x18003ed3e  jz      short loc_18003ED65
0x18003ed40  test    rdi, rdi
0x18003ed43  jz      short loc_18003ED4B
0x18003ed45  mov     dword ptr [rdi], 8
0x18003ed4b  mov     eax, 80004005h
0x18003ed50  mov     rcx, [rsp+48h+var_20]
0x18003ed55  xor     rcx, rsp; StackCookie
0x18003ed58  call    __security_check_cookie
0x18003ed5d  add     rsp, 30h
0x18003ed61  pop     rdi
0x18003ed62  pop     rsi
0x18003ed63  pop     rbx
0x18003ed64  retn
0x18003ed65  xor     r8d, r8d; int
0x18003ed68  mov     dword ptr [rbx+18h], 0
0x18003ed6f  xor     edx, edx; unsigned int
0x18003ed71  mov     dword ptr [rbx+3Ch], 0
0x18003ed78  mov     rcx, rbx; this
0x18003ed7b  call    ?RefillBuffer@CBufferedFile@@IEAAJKH@Z; CBufferedFile::RefillBuffer(ulong,int)
0x18003ed80  xor     eax, eax
0x18003ed82  jmp     short loc_18003ED50
```
