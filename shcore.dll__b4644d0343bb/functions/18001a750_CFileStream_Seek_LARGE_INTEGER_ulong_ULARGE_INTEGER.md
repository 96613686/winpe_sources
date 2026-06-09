# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x18001a750`
- end: `0x18001a868`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a750`
- `0x180030138`

## callees

- `0x18001a750`
- `0x18001aad4`
- `0x18001abfc`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001a805`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001a805`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001a7e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001a7e9`

## pseudocode

```c
__int64 __fastcall CFileStream::Seek(
        CFileStream *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        union _ULARGE_INTEGER *a4)
{
  __int64 v6; // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int Error; // edi
  bool v12; // zf
  unsigned int v13; // edx
  HANDLE v14; // rbp
  _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-48h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp+8h] BYREF

  v6 = *((_QWORD *)this + 532);
  if ( v6 && (*((_DWORD *)this + 13) & 0x10000) != 0 )
  {
    return (unsigned int)CFileStream::Seek((CFileStream *)(v6 + 16), a2, a3, a4);
  }
  else
  {
    v9 = (__int64 *)*((_QWORD *)this + 527);
    if ( v9 )
    {
      v10 = *v9;
      hFile = 0;
      Error = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(v10 + 24))(v9, &hFile);
      if ( Error >= 0 )
      {
        v12 = *((_BYTE *)this + 56) == 1;
        NewFilePointer.QuadPart = 0;
        if ( !v12 || (Error = CFileStream::_NonTransactedCommit((char *)this - 16, 0), Error >= 0) )
        {
          v13 = *((_DWORD *)this + 15);
          v14 = hFile;
          if ( v13 < *((_DWORD *)this + 16) )
            SetFilePointer(hFile, v13 - *((_DWORD *)this + 16), 0, 1u);
          *(_QWORD *)((char *)this + 60) = 0;
          if ( SetFilePointerEx(v14, a2, &NewFilePointer, a3) )
          {
            if ( a4 )
              *a4 = (union _ULARGE_INTEGER)NewFilePointer.QuadPart;
          }
          else
          {
            Error = ResultFromLastError();
          }
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 527) + 32LL))(*((_QWORD *)this + 527));
      }
    }
    else
    {
      return (unsigned int)-2147024890;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a750  push    rbx
0x18001a752  push    rbp
0x18001a753  push    rsi
0x18001a754  push    rdi
0x18001a755  push    r14
0x18001a757  push    r15
0x18001a759  sub     rsp, 38h
0x18001a75d  mov     rsi, rcx
0x18001a760  mov     r14, r9
0x18001a763  mov     rcx, [rcx+10A0h]
0x18001a76a  mov     r15d, r8d
0x18001a76d  mov     rbx, rdx
0x18001a770  test    rcx, rcx
0x18001a773  jnz     loc_18001A847
0x18001a779  mov     rcx, [rsi+1078h]
0x18001a780  test    rcx, rcx
0x18001a783  jz      loc_18001A861
0x18001a789  mov     rax, [rcx]
0x18001a78c  lea     rdx, [rsp+68h+hFile]
0x18001a791  mov     [rsp+68h+hFile], 0
0x18001a79a  mov     rax, [rax+18h]
0x18001a79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a3  mov     edi, eax
0x18001a7a5  test    eax, eax
0x18001a7a7  js      loc_18001A82F
0x18001a7ad  cmp     byte ptr [rsi+38h], 1
0x18001a7b1  mov     qword ptr [rsp+68h+NewFilePointer], 0
0x18001a7ba  jnz     short loc_18001A7CD
0x18001a7bc  xor     edx, edx
0x18001a7be  lea     rcx, [rsi-10h]
0x18001a7c2  call    ?_NonTransactedCommit@CFileStream@@AEAAJW4COMMIT_TYPE@1@@Z; CFileStream::_NonTransactedCommit(CFileStream::COMMIT_TYPE)
0x18001a7c7  mov     edi, eax
0x18001a7c9  test    eax, eax
0x18001a7cb  js      short loc_18001A81C
0x18001a7cd  mov     edx, [rsi+3Ch]
0x18001a7d0  mov     rbp, [rsp+68h+hFile]
0x18001a7d5  cmp     edx, [rsi+40h]
0x18001a7d8  jnb     short loc_18001A7EF
0x18001a7da  sub     edx, [rsi+40h]; lDistanceToMove
0x18001a7dd  mov     r9d, 1; dwMoveMethod
0x18001a7e3  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001a7e6  mov     rcx, rbp; hFile
0x18001a7e9  call    cs:__imp_SetFilePointer
0x18001a7ef  mov     r9d, r15d; dwMoveMethod
0x18001a7f2  mov     qword ptr [rsi+3Ch], 0
0x18001a7fa  lea     r8, [rsp+68h+NewFilePointer]; lpNewFilePointer
0x18001a7ff  mov     rdx, rbx; liDistanceToMove
0x18001a802  mov     rcx, rbp; hFile
0x18001a805  call    cs:__imp_SetFilePointerEx
0x18001a80b  test    eax, eax
0x18001a80d  jz      short loc_18001A83E
0x18001a80f  test    r14, r14
0x18001a812  jz      short loc_18001A81C
0x18001a814  mov     rax, qword ptr [rsp+68h+NewFilePointer]
0x18001a819  mov     [r14], rax
0x18001a81c  mov     rcx, [rsi+1078h]
0x18001a823  mov     rax, [rcx]
0x18001a826  mov     rax, [rax+20h]
0x18001a82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a82f  mov     eax, edi
0x18001a831  add     rsp, 38h
0x18001a835  pop     r15
0x18001a837  pop     r14
0x18001a839  pop     rdi
0x18001a83a  pop     rsi
0x18001a83b  pop     rbp
0x18001a83c  pop     rbx
0x18001a83d  retn
0x18001a83e  call    ResultFromLastError
0x18001a843  mov     edi, eax
0x18001a845  jmp     short loc_18001A81C
0x18001a847  test    dword ptr [rsi+34h], 10000h
0x18001a84e  jz      loc_18001A779
0x18001a854  add     rcx, 10h; this
0x18001a858  call    ?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x18001a85d  mov     edi, eax
0x18001a85f  jmp     short loc_18001A82F
0x18001a861  mov     edi, 80070006h
0x18001a866  jmp     short loc_18001A82F
```
