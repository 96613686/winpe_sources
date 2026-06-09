# CFileWriter::Seek(__int64,ulong)

- ea: `0x383a896c0`
- end: `0x383a897e9`
- name: `?Seek@CFileWriter@@UEAAJ_JK@Z`
- size: `297`
- prototype: `int(CFileWriter *__hidden this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a8a370`

## callees

- `0x383a896c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a89707`
- `KERNEL32!GetLastError` at `0x383a89757`
- `KERNEL32!GetLastError` at `0x383a897bb`
- `KERNEL32!GetLastError` at `0x383a897c5`
- `KERNEL32!GetLastError` at `0x383a89707`
- `KERNEL32!GetLastError` at `0x383a89757`
- `KERNEL32!GetLastError` at `0x383a897bb`
- `KERNEL32!GetLastError` at `0x383a897c5`
- `KERNEL32!GetFileSize` at `0x383a896f9`
- `KERNEL32!GetFileSize` at `0x383a896f9`
- `KERNEL32!SetFilePointer` at `0x383a89748`
- `KERNEL32!SetFilePointer` at `0x383a897b0`
- `KERNEL32!SetFilePointer` at `0x383a89748`
- `KERNEL32!SetFilePointer` at `0x383a897b0`

## pseudocode

```c
__int64 __fastcall CFileWriter::Seek(CFileWriter *this, __int64 a2, DWORD a3)
{
  void *v4; // rcx
  unsigned int v5; // ebx
  DWORD FileSize; // eax
  void *v10; // rcx
  void *v11; // rcx
  signed int LastError; // eax
  __int64 DistanceToMoveHigh; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  v5 = 0;
  if ( v4 == (void *)-1LL )
    return 2147745995LL;
  FileSize = GetFileSize(v4, (LPDWORD)this + 5);
  *((_DWORD *)this + 4) = FileSize;
  if ( FileSize != -1 || !GetLastError() )
  {
    if ( !a3 )
    {
      if ( a2 > *((_QWORD *)this + 2) )
        return 2147745999LL;
LABEL_14:
      v11 = (void *)*((_QWORD *)this + 1);
      v14 = a2;
      if ( SetFilePointer(v11, a2, (PLONG)&v14 + 1, a3) != -1 || !GetLastError() )
        return v5;
      goto LABEL_16;
    }
    if ( a3 != 1 )
      return 2147942487LL;
    v10 = (void *)*((_QWORD *)this + 1);
    HIDWORD(DistanceToMoveHigh) = 0;
    LODWORD(DistanceToMoveHigh) = SetFilePointer(v10, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
    if ( (_DWORD)DistanceToMoveHigh != -1 || !GetLastError() )
    {
      if ( a2 + DistanceToMoveHigh > *((_QWORD *)this + 2) )
        return 2147745999LL;
      goto LABEL_14;
    }
  }
LABEL_16:
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x383a896c0  mov     [rsp+arg_8], rbx
0x383a896c5  push    rbp
0x383a896c6  push    rsi
0x383a896c7  push    rdi
0x383a896c8  sub     rsp, 20h
0x383a896cc  mov     rdi, rcx
0x383a896cf  mov     rcx, [rcx+8]; hFile
0x383a896d3  xor     ebx, ebx
0x383a896d5  mov     ebp, r8d
0x383a896d8  mov     rsi, rdx
0x383a896db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a896df  jnz     short loc_383A896F5
0x383a896e1  mov     ebx, 800400CBh
0x383a896e6  mov     eax, ebx
0x383a896e8  mov     rbx, [rsp+38h+arg_8]
0x383a896ed  add     rsp, 20h
0x383a896f1  pop     rdi
0x383a896f2  pop     rsi
0x383a896f3  pop     rbp
0x383a896f4  retn
0x383a896f5  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x383a896f9  call    cs:__imp_GetFileSize
0x383a896ff  mov     [rdi+10h], eax
0x383a89702  cmp     eax, 0FFFFFFFFh
0x383a89705  jnz     short loc_383A89715
0x383a89707  call    cs:__imp_GetLastError
0x383a8970d  test    eax, eax
0x383a8970f  jnz     loc_383A897C5
0x383a89715  mov     eax, ebp
0x383a89717  test    ebp, ebp
0x383a89719  jz      short loc_383A89783
0x383a8971b  dec     eax
0x383a8971d  jz      short loc_383A89733
0x383a8971f  mov     ebx, 80070057h
0x383a89724  mov     eax, ebx
0x383a89726  mov     rbx, [rsp+38h+arg_8]
0x383a8972b  add     rsp, 20h
0x383a8972f  pop     rdi
0x383a89730  pop     rsi
0x383a89731  pop     rbp
0x383a89732  retn
0x383a89733  mov     rcx, [rdi+8]; hFile
0x383a89737  lea     r8, [rsp+38h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x383a8973c  mov     r9d, 1; dwMoveMethod
0x383a89742  xor     edx, edx; lDistanceToMove
0x383a89744  mov     dword ptr [rsp+38h+DistanceToMoveHigh+4], ebx
0x383a89748  call    cs:__imp_SetFilePointer
0x383a8974e  mov     dword ptr [rsp+38h+DistanceToMoveHigh], eax
0x383a89752  cmp     eax, 0FFFFFFFFh
0x383a89755  jnz     short loc_383A89761
0x383a89757  call    cs:__imp_GetLastError
0x383a8975d  test    eax, eax
0x383a8975f  jnz     short loc_383A897C5
0x383a89761  mov     rcx, [rsp+38h+DistanceToMoveHigh]
0x383a89766  add     rcx, rsi
0x383a89769  cmp     rcx, [rdi+10h]
0x383a8976d  jle     short loc_383A8979D
0x383a8976f  mov     ebx, 800400CFh
0x383a89774  mov     eax, ebx
0x383a89776  mov     rbx, [rsp+38h+arg_8]
0x383a8977b  add     rsp, 20h
0x383a8977f  pop     rdi
0x383a89780  pop     rsi
0x383a89781  pop     rbp
0x383a89782  retn
0x383a89783  cmp     rsi, [rdi+10h]
0x383a89787  jle     short loc_383A8979D
0x383a89789  mov     ebx, 800400CFh
0x383a8978e  mov     eax, ebx
0x383a89790  mov     rbx, [rsp+38h+arg_8]
0x383a89795  add     rsp, 20h
0x383a89799  pop     rdi
0x383a8979a  pop     rsi
0x383a8979b  pop     rbp
0x383a8979c  retn
0x383a8979d  mov     rcx, [rdi+8]; hFile
0x383a897a1  lea     r8, [rsp+38h+arg_1C]; lpDistanceToMoveHigh
0x383a897a6  mov     r9d, ebp; dwMoveMethod
0x383a897a9  mov     edx, esi; lDistanceToMove
0x383a897ab  mov     [rsp+58h], rsi
0x383a897b0  call    cs:__imp_SetFilePointer
0x383a897b6  cmp     eax, 0FFFFFFFFh
0x383a897b9  jnz     short loc_383A897DA
0x383a897bb  call    cs:__imp_GetLastError
0x383a897c1  test    eax, eax
0x383a897c3  jz      short loc_383A897DA
0x383a897c5  call    cs:__imp_GetLastError
0x383a897cb  mov     ebx, eax
0x383a897cd  test    eax, eax
0x383a897cf  jle     short loc_383A897DA
0x383a897d1  movzx   ebx, ax
0x383a897d4  or      ebx, 80070000h
0x383a897da  mov     eax, ebx
0x383a897dc  mov     rbx, [rsp+38h+arg_8]
0x383a897e1  add     rsp, 20h
0x383a897e5  pop     rdi
0x383a897e6  pop     rsi
0x383a897e7  pop     rbp
0x383a897e8  retn
```
