# CFileStream::SetSize(_ULARGE_INTEGER)

- ea: `0x180030010`
- end: `0x18003012f`
- name: `?SetSize@CFileStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180030010`

## callees

- `0x180030010`
- `0x180030138`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180030081`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800300a7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800300ce`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180030081`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800300a7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800300ce`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800300b4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800300b4`

## pseudocode

```c
__int64 __fastcall CFileStream::SetSize(CFileStream *this, union _ULARGE_INTEGER a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int TempStream; // esi
  HANDLE v7; // r14
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp+8h] BYREF
  union _ULARGE_INTEGER v11; // [rsp+68h] [rbp+10h]
  LARGE_INTEGER liDistanceToMove; // [rsp+70h] [rbp+18h]
  union _LARGE_INTEGER v13; // [rsp+78h] [rbp+20h] BYREF

  v11 = a2;
  if ( (*((_DWORD *)this + 13) & 0x10000) != 0 )
  {
    if ( *((_QWORD *)this + 532) )
      return (unsigned int)CFileStream::SetSize((CFileStream *)(*((_QWORD *)this + 532) + 16LL), a2);
    TempStream = CFileStream::_CreateTempStream((CFileStream *)((char *)this - 16));
    if ( TempStream >= 0 )
      return (unsigned int)CFileStream::SetSize((CFileStream *)(*((_QWORD *)this + 532) + 16LL), a2);
  }
  else
  {
    v4 = (__int64 *)*((_QWORD *)this + 527);
    if ( v4 )
    {
      v5 = *v4;
      hFile = 0;
      TempStream = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(v5 + 24))(v4, &hFile);
      if ( TempStream >= 0 )
      {
        v7 = hFile;
        NewFilePointer.QuadPart = 0;
        v13.QuadPart = 0;
        if ( SetFilePointerEx(hFile, 0, &NewFilePointer, 1u) )
        {
          liDistanceToMove.QuadPart = __PAIR64__(v11.HighPart, a2.LowPart);
          if ( SetFilePointerEx(v7, (LARGE_INTEGER)__PAIR64__(v11.HighPart, a2.LowPart), &v13, 0) )
          {
            if ( SetEndOfFile(v7) && SetFilePointerEx(v7, NewFilePointer, &v13, 0) )
              TempStream = 0;
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
  return (unsigned int)TempStream;
}

```

## disassembly

```asm
0x180030010  mov     [rsp+arg_8], rdx
0x180030015  push    rbx
0x180030016  push    rbp
0x180030017  push    rsi
0x180030018  push    rdi
0x180030019  push    r14
0x18003001b  sub     rsp, 30h
0x18003001f  xor     ebx, ebx
0x180030021  mov     rdi, rdx
0x180030024  test    dword ptr [rcx+34h], 10000h
0x18003002b  mov     rbp, rcx
0x18003002e  jnz     loc_1800300F9
0x180030034  mov     rcx, [rcx+1078h]
0x18003003b  test    rcx, rcx
0x18003003e  jz      loc_180030128
0x180030044  mov     rax, [rcx]
0x180030047  lea     rdx, [rsp+58h+hFile]
0x18003004c  mov     [rsp+58h+hFile], rbx
0x180030051  mov     rax, [rax+18h]
0x180030055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003005a  mov     esi, eax
0x18003005c  test    eax, eax
0x18003005e  js      loc_1800300EC
0x180030064  mov     r14, [rsp+58h+hFile]
0x180030069  lea     r9d, [rbx+1]; dwMoveMethod
0x18003006d  mov     rcx, r14; hFile
0x180030070  mov     qword ptr [rsp+58h+NewFilePointer], rbx
0x180030075  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x18003007a  mov     qword ptr [rsp+58h+arg_18], rbx
0x18003007f  mov     edx, ebx; liDistanceToMove
0x180030081  call    cs:__imp_SetFilePointerEx
0x180030087  test    eax, eax
0x180030089  jz      short loc_1800300D9
0x18003008b  mov     eax, dword ptr [rsp+58h+arg_8+4]
0x18003008f  lea     r8, [rsp+58h+arg_18]; lpNewFilePointer
0x180030094  mov     dword ptr [rsp+58h+liDistanceToMove+4], eax
0x180030098  xor     r9d, r9d; dwMoveMethod
0x18003009b  mov     dword ptr [rsp+58h+liDistanceToMove], edi
0x18003009f  mov     rcx, r14; hFile
0x1800300a2  mov     rdx, qword ptr [rsp+58h+liDistanceToMove]; liDistanceToMove
0x1800300a7  call    cs:__imp_SetFilePointerEx
0x1800300ad  test    eax, eax
0x1800300af  jz      short loc_1800300D9
0x1800300b1  mov     rcx, r14; hFile
0x1800300b4  call    cs:__imp_SetEndOfFile
0x1800300ba  test    eax, eax
0x1800300bc  jz      short loc_1800300D9
0x1800300be  mov     rdx, qword ptr [rsp+58h+NewFilePointer]; liDistanceToMove
0x1800300c3  lea     r8, [rsp+58h+arg_18]; lpNewFilePointer
0x1800300c8  xor     r9d, r9d; dwMoveMethod
0x1800300cb  mov     rcx, r14; hFile
0x1800300ce  call    cs:__imp_SetFilePointerEx
0x1800300d4  test    eax, eax
0x1800300d6  cmovnz  esi, ebx
0x1800300d9  mov     rcx, [rbp+1078h]
0x1800300e0  mov     rax, [rcx]
0x1800300e3  mov     rax, [rax+20h]
0x1800300e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ec  mov     eax, esi
0x1800300ee  add     rsp, 30h
0x1800300f2  pop     r14
0x1800300f4  pop     rdi
0x1800300f5  pop     rsi
0x1800300f6  pop     rbp
0x1800300f7  pop     rbx
0x1800300f8  retn
0x1800300f9  cmp     [rcx+10A0h], rbx
0x180030100  jnz     short loc_180030111
0x180030102  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180030106  call    ?_CreateTempStream@CFileStream@@AEAAJXZ; CFileStream::_CreateTempStream(void)
0x18003010b  mov     esi, eax
0x18003010d  test    eax, eax
0x18003010f  js      short loc_1800300EC
0x180030111  mov     rcx, [rbp+10A0h]
0x180030118  mov     rdx, rdi; union _ULARGE_INTEGER
0x18003011b  add     rcx, 10h; this
0x18003011f  call    ?SetSize@CFileStream@@UEAAJT_ULARGE_INTEGER@@@Z; CFileStream::SetSize(_ULARGE_INTEGER)
0x180030124  mov     esi, eax
0x180030126  jmp     short loc_1800300EC
0x180030128  mov     esi, 80070006h
0x18003012d  jmp     short loc_1800300EC
```
