# CFileReader::Seek(__int64,ulong)

- ea: `0x383a892d0`
- end: `0x383a893f4`
- name: `?Seek@CFileReader@@UEAAJ_JK@Z`
- size: `292`
- prototype: `int(CFileReader *__hidden this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a89cd0`

## callees

- `0x383a892d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a89345`
- `KERNEL32!GetLastError` at `0x383a8934f`
- `KERNEL32!GetLastError` at `0x383a893c8`
- `KERNEL32!GetLastError` at `0x383a893d2`
- `KERNEL32!GetLastError` at `0x383a89345`
- `KERNEL32!GetLastError` at `0x383a8934f`
- `KERNEL32!GetLastError` at `0x383a893c8`
- `KERNEL32!GetLastError` at `0x383a893d2`
- `KERNEL32!SetFilePointer` at `0x383a89336`
- `KERNEL32!SetFilePointer` at `0x383a893bd`
- `KERNEL32!SetFilePointer` at `0x383a89336`
- `KERNEL32!SetFilePointer` at `0x383a893bd`

## pseudocode

```c
int __fastcall CFileReader::Seek(CFileReader *this, __int64 a2, DWORD a3)
{
  void *v4; // rcx
  int v5; // ebx
  int result; // eax
  void *v9; // rcx
  __int64 DistanceToMoveHigh; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  v5 = 0;
  if ( v4 == (void *)-1LL )
    return -2147221301;
  if ( a3 )
  {
    if ( a3 != 1 )
      return -2147024809;
    HIDWORD(DistanceToMoveHigh) = 0;
    LODWORD(DistanceToMoveHigh) = SetFilePointer(v4, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
    if ( (_DWORD)DistanceToMoveHigh == -1 && GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( a2 + DistanceToMoveHigh > *((_QWORD *)this + 2) )
      return -2147221300;
  }
  else if ( a2 > *((_QWORD *)this + 2) )
  {
    return -2147221300;
  }
  v9 = (void *)*((_QWORD *)this + 1);
  v11 = a2;
  if ( SetFilePointer(v9, a2, (PLONG)&v11 + 1, a3) == -1 && GetLastError() )
  {
    result = GetLastError();
    if ( result <= 0 )
      return result;
    return (unsigned __int16)result | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x383a892d0  mov     [rsp+arg_8], rbx
0x383a892d5  push    rbp
0x383a892d6  push    rsi
0x383a892d7  push    rdi
0x383a892d8  sub     rsp, 20h
0x383a892dc  mov     rdi, rcx
0x383a892df  mov     rcx, [rcx+8]; hFile
0x383a892e3  xor     ebx, ebx
0x383a892e5  mov     ebp, r8d
0x383a892e8  mov     rsi, rdx
0x383a892eb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a892ef  jnz     short loc_383A89303
0x383a892f1  mov     eax, 800400CBh
0x383a892f6  mov     rbx, [rsp+38h+arg_8]
0x383a892fb  add     rsp, 20h
0x383a892ff  pop     rdi
0x383a89300  pop     rsi
0x383a89301  pop     rbp
0x383a89302  retn
0x383a89303  mov     eax, r8d
0x383a89306  test    r8d, r8d
0x383a89309  jz      loc_383A89392
0x383a8930f  dec     eax
0x383a89311  jz      short loc_383A89325
0x383a89313  mov     eax, 80070057h
0x383a89318  mov     rbx, [rsp+38h+arg_8]
0x383a8931d  add     rsp, 20h
0x383a89321  pop     rdi
0x383a89322  pop     rsi
0x383a89323  pop     rbp
0x383a89324  retn
0x383a89325  lea     r8, [rsp+38h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x383a8932a  mov     r9d, 1; dwMoveMethod
0x383a89330  xor     edx, edx; lDistanceToMove
0x383a89332  mov     dword ptr [rsp+38h+DistanceToMoveHigh+4], ebx
0x383a89336  call    cs:__imp_SetFilePointer
0x383a8933c  mov     dword ptr [rsp+38h+DistanceToMoveHigh], eax
0x383a89340  cmp     eax, 0FFFFFFFFh
0x383a89343  jnz     short loc_383A89372
0x383a89345  call    cs:__imp_GetLastError
0x383a8934b  test    eax, eax
0x383a8934d  jz      short loc_383A89372
0x383a8934f  call    cs:__imp_GetLastError
0x383a89355  test    eax, eax
0x383a89357  jle     loc_383A893E7
0x383a8935d  movzx   eax, ax
0x383a89360  or      eax, 80070000h
0x383a89365  mov     rbx, [rsp+38h+arg_8]
0x383a8936a  add     rsp, 20h
0x383a8936e  pop     rdi
0x383a8936f  pop     rsi
0x383a89370  pop     rbp
0x383a89371  retn
0x383a89372  mov     rcx, [rsp+38h+DistanceToMoveHigh]
0x383a89377  add     rcx, rsi
0x383a8937a  cmp     rcx, [rdi+10h]
0x383a8937e  jle     short loc_383A893AA
0x383a89380  mov     eax, 800400CCh
0x383a89385  mov     rbx, [rsp+38h+arg_8]
0x383a8938a  add     rsp, 20h
0x383a8938e  pop     rdi
0x383a8938f  pop     rsi
0x383a89390  pop     rbp
0x383a89391  retn
0x383a89392  cmp     rdx, [rdi+10h]
0x383a89396  jle     short loc_383A893AA
0x383a89398  mov     eax, 800400CCh
0x383a8939d  mov     rbx, [rsp+38h+arg_8]
0x383a893a2  add     rsp, 20h
0x383a893a6  pop     rdi
0x383a893a7  pop     rsi
0x383a893a8  pop     rbp
0x383a893a9  retn
0x383a893aa  mov     rcx, [rdi+8]; hFile
0x383a893ae  lea     r8, [rsp+38h+arg_1C]; lpDistanceToMoveHigh
0x383a893b3  mov     r9d, ebp; dwMoveMethod
0x383a893b6  mov     edx, esi; lDistanceToMove
0x383a893b8  mov     [rsp+58h], rsi
0x383a893bd  call    cs:__imp_SetFilePointer
0x383a893c3  cmp     eax, 0FFFFFFFFh
0x383a893c6  jnz     short loc_383A893E5
0x383a893c8  call    cs:__imp_GetLastError
0x383a893ce  test    eax, eax
0x383a893d0  jz      short loc_383A893E5
0x383a893d2  call    cs:__imp_GetLastError
0x383a893d8  test    eax, eax
0x383a893da  jle     short loc_383A893E7
0x383a893dc  movzx   ebx, ax
0x383a893df  or      ebx, 80070000h
0x383a893e5  mov     eax, ebx
0x383a893e7  mov     rbx, [rsp+38h+arg_8]
0x383a893ec  add     rsp, 20h
0x383a893f0  pop     rdi
0x383a893f1  pop     rsi
0x383a893f2  pop     rbp
0x383a893f3  retn
```
