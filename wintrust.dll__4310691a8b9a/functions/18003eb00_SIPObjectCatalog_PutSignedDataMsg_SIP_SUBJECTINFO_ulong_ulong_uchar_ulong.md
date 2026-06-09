# SIPObjectCatalog_::PutSignedDataMsg(SIP_SUBJECTINFO_ *,ulong *,ulong,uchar *,ulong)

- ea: `0x18003eb00`
- end: `0x18003ebad`
- name: `?PutSignedDataMsg@SIPObjectCatalog_@@UEAAHPEAUSIP_SUBJECTINFO_@@PEAKKPEAEK@Z`
- size: `173`
- prototype: `int(SIPObjectCatalog_ *__hidden this, struct SIP_SUBJECTINFO_ *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18003eb00`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003eb6b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003eb6b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003eb5c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003eb5c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003eb93`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003eb93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb1d`

## pseudocode

```c
_BOOL8 __fastcall SIPObjectCatalog_::PutSignedDataMsg(
        SIPObjectCatalog_ *this,
        struct SIP_SUBJECTINFO_ *a2,
        unsigned int *a3,
        DWORD a4,
        unsigned __int8 *lpBuffer)
{
  __int64 v8; // rax
  void *v9; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  if ( !lpBuffer )
  {
    SetLastError(0x57u);
    return 0;
  }
  v8 = *(_QWORD *)this;
  *((_DWORD *)this + 4) = 0;
  if ( !(*(unsigned int (__fastcall **)(SIPObjectCatalog_ *, struct SIP_SUBJECTINFO_ *, __int64))(v8 + 128))(
          this,
          a2,
          3221225472LL) )
    return 0;
  if ( SetFilePointer(*((HANDLE *)this + 1), 0, 0, 0) == -1 )
    return 0;
  SetEndOfFile(*((HANDLE *)this + 1));
  v9 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  return WriteFile(v9, lpBuffer, a4, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == a4;
}

```

## disassembly

```asm
0x18003eb00  mov     [rsp+arg_0], rbx
0x18003eb05  push    rdi
0x18003eb06  sub     rsp, 40h
0x18003eb0a  cmp     [rsp+48h+lpBuffer], 0
0x18003eb10  mov     edi, r9d
0x18003eb13  mov     rbx, rcx
0x18003eb16  jnz     short loc_18003EB30
0x18003eb18  mov     ecx, 57h ; 'W'; dwErrCode
0x18003eb1d  call    cs:__imp_SetLastError
0x18003eb23  xor     eax, eax
0x18003eb25  mov     rbx, [rsp+48h+arg_0]
0x18003eb2a  add     rsp, 40h
0x18003eb2e  pop     rdi
0x18003eb2f  retn
0x18003eb30  mov     rax, [rcx]
0x18003eb33  mov     r8d, 0C0000000h
0x18003eb39  mov     dword ptr [rcx+10h], 0
0x18003eb40  mov     rax, [rax+80h]
0x18003eb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb4c  test    eax, eax
0x18003eb4e  jz      short loc_18003EB23
0x18003eb50  mov     rcx, [rbx+8]; hFile
0x18003eb54  xor     r9d, r9d; dwMoveMethod
0x18003eb57  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003eb5a  xor     edx, edx; lDistanceToMove
0x18003eb5c  call    cs:__imp_SetFilePointer
0x18003eb62  cmp     eax, 0FFFFFFFFh
0x18003eb65  jz      short loc_18003EB23
0x18003eb67  mov     rcx, [rbx+8]; hFile
0x18003eb6b  call    cs:__imp_SetEndOfFile
0x18003eb71  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x18003eb76  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003eb7b  mov     rcx, [rbx+8]; hFile
0x18003eb7f  mov     r8d, edi; nNumberOfBytesToWrite
0x18003eb82  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18003eb8a  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18003eb93  call    cs:__imp_WriteFile
0x18003eb99  test    eax, eax
0x18003eb9b  jz      short loc_18003EB23
0x18003eb9d  cmp     [rsp+48h+NumberOfBytesWritten], edi
0x18003eba1  jnz     short loc_18003EB23
0x18003eba3  mov     eax, 1
0x18003eba8  jmp     loc_18003EB25
```
