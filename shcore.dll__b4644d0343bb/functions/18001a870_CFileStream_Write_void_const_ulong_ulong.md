# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x18001a870`
- end: `0x18001aace`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `606`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a870`

## callees

- `0x18001a870`
- `0x18001aad4`
- `0x18001abfc`
- `0x180030138`
- `0x18009341c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001aaad`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001aaad`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa2d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa2d`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(CFileStream *this, char *a2, unsigned int a3, unsigned int *a4)
{
  int v4; // eax
  __int64 *v9; // rcx
  __int64 v10; // rax
  int TempStream; // ebp
  HANDLE v12; // r13
  __int64 v13; // rcx
  unsigned int v14; // edi
  unsigned int v16; // edi
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // [rsp+30h] [rbp-48h]
  HANDLE hFile; // [rsp+38h] [rbp-40h] BYREF
  HANDLE v22; // [rsp+40h] [rbp-38h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 13);
  if ( (v4 & 1) == 0 && (v4 & 2) == 0 )
    return 2147680261LL;
  if ( (v4 & 0x10000) != 0 )
  {
    if ( *((_QWORD *)this + 532) )
      return (unsigned int)CFileStream::Write((CFileStream *)(*((_QWORD *)this + 532) + 16LL), a2, a3, a4);
    TempStream = CFileStream::_CreateTempStream((CFileStream *)((char *)this - 16));
    if ( TempStream >= 0 )
      return (unsigned int)CFileStream::Write((CFileStream *)(*((_QWORD *)this + 532) + 16LL), a2, a3, a4);
  }
  else
  {
    v9 = (__int64 *)*((_QWORD *)this + 527);
    if ( v9 )
    {
      v10 = *v9;
      hFile = 0;
      TempStream = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(v10 + 24))(v9, &hFile);
      if ( TempStream >= 0 )
      {
        v12 = hFile;
        v22 = hFile;
        v20 = a3;
        if ( !*((_BYTE *)this + 56) )
        {
          v18 = *((_DWORD *)this + 16);
          v19 = *((_DWORD *)this + 15);
          if ( v19 < v18 )
            SetFilePointer(hFile, v19 - v18, 0, 1u);
          *(_QWORD *)((char *)this + 60) = 0;
        }
        while ( a3 )
        {
          v13 = *((unsigned int *)this + 15);
          if ( (unsigned int)v13 < 0x1000 )
          {
            v14 = a3;
            if ( 4096 - (int)v13 < a3 )
              v14 = 4096 - v13;
            memcpy_0((char *)this + v13 + 68, a2, v14);
            *((_DWORD *)this + 15) += v14;
            *((_BYTE *)this + 56) = 1;
            a3 -= v14;
            if ( !a3 )
              break;
            a2 += v14;
            v12 = v22;
          }
          TempStream = CFileStream::_NonTransactedCommit((char *)this - 16, 0);
          if ( TempStream < 0 )
            break;
          if ( a3 > 0x1000 )
          {
            NumberOfBytesWritten = 0;
            v16 = a3 & 0xFFFFF000;
            if ( !WriteFile(v12, a2, a3 & 0xFFFFF000, &NumberOfBytesWritten, 0) )
            {
              TempStream = ResultFromLastError();
              break;
            }
            v17 = NumberOfBytesWritten;
            a3 -= NumberOfBytesWritten;
            *((_BYTE *)this + 4272) = 0;
            if ( (_DWORD)v17 != v16 )
              break;
            a2 += v17;
          }
        }
        if ( a4 )
          *a4 = v20 - a3;
        if ( a3 )
        {
          if ( !TempStream )
            TempStream = 1;
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
0x18001a870  push    rbx
0x18001a872  push    rsi
0x18001a873  push    r12
0x18001a875  push    r15
0x18001a877  sub     rsp, 58h
0x18001a87b  mov     eax, [rcx+34h]
0x18001a87e  mov     r12, r9
0x18001a881  mov     esi, r8d
0x18001a884  mov     r15, rdx
0x18001a887  mov     rbx, rcx
0x18001a88a  test    al, 1
0x18001a88c  jz      loc_18001A996
0x18001a892  mov     [rsp+78h+arg_8], rbp
0x18001a89a  mov     [rsp+78h+arg_10], rdi
0x18001a8a2  mov     [rsp+78h+var_28], r14
0x18001a8a7  bt      eax, 10h
0x18001a8ab  jb      loc_18001A9AE
0x18001a8b1  mov     rcx, [rcx+1078h]
0x18001a8b8  test    rcx, rcx
0x18001a8bb  jz      loc_18001AAC4
0x18001a8c1  mov     rax, [rcx]
0x18001a8c4  lea     rdx, [rsp+78h+hFile]
0x18001a8c9  xor     edi, edi
0x18001a8cb  mov     [rsp+78h+hFile], rdi
0x18001a8d0  mov     rax, [rax+18h]
0x18001a8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d9  mov     ebp, eax
0x18001a8db  test    eax, eax
0x18001a8dd  js      loc_18001A974
0x18001a8e3  mov     [rsp+78h+arg_18], r13
0x18001a8eb  mov     r13, [rsp+78h+hFile]
0x18001a8f0  mov     [rsp+78h+var_38], r13
0x18001a8f5  mov     [rsp+78h+var_48], esi
0x18001a8f9  cmp     [rbx+38h], dil
0x18001a8fd  jz      loc_18001AA68
0x18001a903  test    esi, esi
0x18001a905  jz      short loc_18001A948
0x18001a907  mov     ecx, [rbx+3Ch]
0x18001a90a  cmp     ecx, 1000h
0x18001a910  jnb     loc_18001A9E3
0x18001a916  mov     eax, 1000h
0x18001a91b  mov     edi, esi
0x18001a91d  sub     eax, ecx
0x18001a91f  mov     rdx, r15; Src
0x18001a922  cmp     eax, esi
0x18001a924  cmovb   edi, eax
0x18001a927  add     rcx, 44h ; 'D'
0x18001a92b  add     rcx, rbx; void *
0x18001a92e  mov     r8d, edi; Size
0x18001a931  mov     r13d, edi
0x18001a934  call    memcpy_0
0x18001a939  add     [rbx+3Ch], edi
0x18001a93c  mov     byte ptr [rbx+38h], 1
0x18001a940  sub     esi, edi
0x18001a942  jnz     loc_18001A9D9
0x18001a948  mov     r13, [rsp+78h+arg_18]
0x18001a950  test    r12, r12
0x18001a953  jnz     loc_18001AA59
0x18001a959  test    esi, esi
0x18001a95b  jnz     loc_18001AAB5
0x18001a961  mov     rcx, [rbx+1078h]
0x18001a968  mov     rax, [rcx]
0x18001a96b  mov     rax, [rax+20h]
0x18001a96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a974  mov     r14, [rsp+78h+var_28]
0x18001a979  mov     eax, ebp
0x18001a97b  mov     rbp, [rsp+78h+arg_8]
0x18001a983  mov     rdi, [rsp+78h+arg_10]
0x18001a98b  add     rsp, 58h
0x18001a98f  pop     r15
0x18001a991  pop     r12
0x18001a993  pop     rsi
0x18001a994  pop     rbx
0x18001a995  retn
0x18001a996  test    al, 2
0x18001a998  jnz     loc_18001A892
0x18001a99e  mov     eax, 80030005h
0x18001a9a3  add     rsp, 58h
0x18001a9a7  pop     r15
0x18001a9a9  pop     r12
0x18001a9ab  pop     rsi
0x18001a9ac  pop     rbx
0x18001a9ad  retn
0x18001a9ae  cmp     qword ptr [rcx+10A0h], 0
0x18001a9b6  jz      loc_18001AA87
0x18001a9bc  mov     rcx, [rbx+10A0h]
0x18001a9c3  mov     r9, r12; unsigned int *
0x18001a9c6  add     rcx, 10h; this
0x18001a9ca  mov     r8d, esi; unsigned int
0x18001a9cd  mov     rdx, r15; void *
0x18001a9d0  call    ?Write@CFileStream@@UEAAJPEBXKPEAK@Z; CFileStream::Write(void const *,ulong,ulong *)
0x18001a9d5  mov     ebp, eax
0x18001a9d7  jmp     short loc_18001A974
0x18001a9d9  add     r15, r13
0x18001a9dc  mov     r13, [rsp+78h+var_38]
0x18001a9e1  xor     edi, edi
0x18001a9e3  xor     edx, edx
0x18001a9e5  lea     rcx, [rbx-10h]
0x18001a9e9  call    ?_NonTransactedCommit@CFileStream@@AEAAJW4COMMIT_TYPE@1@@Z; CFileStream::_NonTransactedCommit(CFileStream::COMMIT_TYPE)
0x18001a9ee  mov     ebp, eax
0x18001a9f0  test    eax, eax
0x18001a9f2  js      loc_18001A948
0x18001a9f8  cmp     esi, 1000h
0x18001a9fe  jbe     loc_18001A903
0x18001aa04  mov     [rsp+78h+NumberOfBytesWritten], edi
0x18001aa0b  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001aa13  mov     edi, esi
0x18001aa15  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001aa1e  and     edi, 0FFFFF000h
0x18001aa24  mov     rdx, r15; lpBuffer
0x18001aa27  mov     r8d, edi; nNumberOfBytesToWrite
0x18001aa2a  mov     rcx, r13; hFile
0x18001aa2d  call    cs:__imp_WriteFile
0x18001aa33  test    eax, eax
0x18001aa35  jz      short loc_18001AA7B
0x18001aa37  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x18001aa3e  sub     esi, eax
0x18001aa40  mov     byte ptr [rbx+10B0h], 0
0x18001aa47  cmp     eax, edi
0x18001aa49  jnz     loc_18001A948
0x18001aa4f  add     r15, rax
0x18001aa52  xor     edi, edi
0x18001aa54  jmp     loc_18001A903
0x18001aa59  mov     eax, [rsp+78h+var_48]
0x18001aa5d  sub     eax, esi
0x18001aa5f  mov     [r12], eax
0x18001aa63  jmp     loc_18001A959
0x18001aa68  mov     eax, [rbx+40h]
0x18001aa6b  mov     edx, [rbx+3Ch]
0x18001aa6e  cmp     edx, eax
0x18001aa70  jb      short loc_18001AA9F
0x18001aa72  mov     [rbx+3Ch], rdi
0x18001aa76  jmp     loc_18001A903
0x18001aa7b  call    ResultFromLastError
0x18001aa80  mov     ebp, eax
0x18001aa82  jmp     loc_18001A948
0x18001aa87  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18001aa8b  call    ?_CreateTempStream@CFileStream@@AEAAJXZ; CFileStream::_CreateTempStream(void)
0x18001aa90  mov     ebp, eax
0x18001aa92  test    eax, eax
0x18001aa94  js      loc_18001A974
0x18001aa9a  jmp     loc_18001A9BC
0x18001aa9f  sub     edx, eax; lDistanceToMove
0x18001aaa1  mov     r9d, 1; dwMoveMethod
0x18001aaa7  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001aaaa  mov     rcx, r13; hFile
0x18001aaad  call    cs:__imp_SetFilePointer
0x18001aab3  jmp     short loc_18001AA72
0x18001aab5  test    ebp, ebp
0x18001aab7  mov     eax, 1
0x18001aabc  cmovz   ebp, eax
0x18001aabf  jmp     loc_18001A961
0x18001aac4  mov     ebp, 80070006h
0x18001aac9  jmp     loc_18001A974
```
