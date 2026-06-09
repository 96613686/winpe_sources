# CFileStream::_NonTransactedCommit(CFileStream::COMMIT_TYPE)

- ea: `0x18001aad4`
- end: `0x18001abf6`
- name: `?_NonTransactedCommit@CFileStream@@AEAAJW4COMMIT_TYPE@1@@Z`
- size: `290`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a4c0`
- `0x18001a530`
- `0x18001a750`
- `0x18001a870`
- `0x18002b8d0`
- `0x18005dca8`

## callees

- `0x18001aad4`
- `0x180031cb0`
- `0x18005d3f0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ab4c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ab4c`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001ab9b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001abdb`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001ab9b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001abdb`

## pseudocode

```c
__int64 __fastcall CFileStream::_NonTransactedCommit(__int64 a1, int a2)
{
  int v2; // edi
  __int64 v5; // rcx
  HANDLE v6; // rbp
  struct IFileHandle *v8; // rcx
  void *NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  if ( *(_QWORD *)(a1 + 4272) )
  {
    CFileStream::Revert((CFileStream *)(a1 + 16));
    return (unsigned int)v2;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    if ( !*(_DWORD *)(a1 + 76) )
    {
      if ( a2 == 1 )
      {
        v8 = *(struct IFileHandle **)(a1 + 4232);
        NumberOfBytesWritten = 0;
        v2 = LockHandle(v8, &NumberOfBytesWritten);
        if ( v2 < 0 )
          return (unsigned int)v2;
        FlushFileBuffers(NumberOfBytesWritten);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 4232) + 32LL))(*(_QWORD *)(a1 + 4232));
      }
      goto LABEL_9;
    }
    v5 = *(_QWORD *)(a1 + 4232);
    LODWORD(NumberOfBytesWritten) = 0;
    hFile = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v5 + 24LL))(v5, &hFile);
    if ( v2 >= 0 )
    {
      v6 = hFile;
      WriteFile(hFile, (LPCVOID)(a1 + 84), *(_DWORD *)(a1 + 76), (LPDWORD)&NumberOfBytesWritten, 0);
      if ( (_DWORD)NumberOfBytesWritten == *(_DWORD *)(a1 + 76) )
      {
        *(_DWORD *)(a1 + 76) = 0;
        *(_BYTE *)(a1 + 4288) = 0;
        if ( a2 == 1 )
          FlushFileBuffers(v6);
      }
      else
      {
        v2 = -2147286928;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 4232) + 32LL))(*(_QWORD *)(a1 + 4232));
      if ( v2 >= 0 )
LABEL_9:
        *(_BYTE *)(a1 + 72) = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001aad4  mov     [rsp+arg_8], rbx
0x18001aad9  push    rbp
0x18001aada  push    rsi
0x18001aadb  push    rdi
0x18001aadc  sub     rsp, 30h
0x18001aae0  xor     edi, edi
0x18001aae2  mov     esi, edx
0x18001aae4  mov     rbx, rcx
0x18001aae7  cmp     [rcx+10B0h], rdi
0x18001aaee  jnz     loc_18001ABA3
0x18001aaf4  cmp     [rcx+48h], dil
0x18001aaf8  jz      loc_18001AB89
0x18001aafe  cmp     [rcx+4Ch], edi
0x18001ab01  jbe     loc_18001ABB5
0x18001ab07  mov     rcx, [rcx+1088h]
0x18001ab0e  lea     rdx, [rsp+48h+hFile]
0x18001ab13  mov     dword ptr [rsp+48h+NumberOfBytesWritten], edi
0x18001ab17  mov     [rsp+48h+hFile], rdi
0x18001ab1c  mov     rax, [rcx]
0x18001ab1f  mov     rax, [rax+18h]
0x18001ab23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab28  mov     edi, eax
0x18001ab2a  test    eax, eax
0x18001ab2c  js      short loc_18001AB89
0x18001ab2e  mov     rbp, [rsp+48h+hFile]
0x18001ab33  lea     rdx, [rbx+54h]; lpBuffer
0x18001ab37  mov     r8d, [rbx+4Ch]; nNumberOfBytesToWrite
0x18001ab3b  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ab40  mov     rcx, rbp; hFile
0x18001ab43  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18001ab4c  call    cs:__imp_WriteFile
0x18001ab52  mov     eax, [rbx+4Ch]
0x18001ab55  cmp     dword ptr [rsp+48h+NumberOfBytesWritten], eax
0x18001ab59  jnz     short loc_18001ABAE
0x18001ab5b  mov     dword ptr [rbx+4Ch], 0
0x18001ab62  mov     byte ptr [rbx+10C0h], 0
0x18001ab69  cmp     esi, 1
0x18001ab6c  jz      short loc_18001AB98
0x18001ab6e  mov     rcx, [rbx+1088h]
0x18001ab75  mov     rax, [rcx]
0x18001ab78  mov     rax, [rax+20h]
0x18001ab7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab81  test    edi, edi
0x18001ab83  js      short loc_18001AB89
0x18001ab85  mov     byte ptr [rbx+48h], 0
0x18001ab89  mov     rbx, [rsp+48h+arg_8]
0x18001ab8e  mov     eax, edi
0x18001ab90  add     rsp, 30h
0x18001ab94  pop     rdi
0x18001ab95  pop     rsi
0x18001ab96  pop     rbp
0x18001ab97  retn
0x18001ab98  mov     rcx, rbp; hFile
0x18001ab9b  call    cs:__imp_FlushFileBuffers
0x18001aba1  jmp     short loc_18001AB6E
0x18001aba3  add     rcx, 10h; this
0x18001aba7  call    ?Revert@CFileStream@@UEAAJXZ; CFileStream::Revert(void)
0x18001abac  jmp     short loc_18001AB89
0x18001abae  mov     edi, 80030070h
0x18001abb3  jmp     short loc_18001AB6E
0x18001abb5  cmp     esi, 1
0x18001abb8  jnz     short loc_18001AB85
0x18001abba  mov     rcx, [rcx+1088h]; struct IFileHandle *
0x18001abc1  lea     rdx, [rsp+48h+NumberOfBytesWritten]; void **
0x18001abc6  mov     [rsp+48h+NumberOfBytesWritten], rdi
0x18001abcb  call    ?LockHandle@@YAJPEAUIFileHandle@@PEAPEAX@Z; LockHandle(IFileHandle *,void * *)
0x18001abd0  mov     edi, eax
0x18001abd2  test    eax, eax
0x18001abd4  js      short loc_18001AB89
0x18001abd6  mov     rcx, [rsp+48h+NumberOfBytesWritten]; hFile
0x18001abdb  call    cs:__imp_FlushFileBuffers
0x18001abe1  mov     rcx, [rbx+1088h]
0x18001abe8  mov     rdx, [rcx]
0x18001abeb  mov     rax, [rdx+20h]
0x18001abef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf4  jmp     short loc_18001AB85
```
