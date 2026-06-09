# CDVRIndexObject::SetNextIndex(ulong,ushort)

- ea: `0x180004d10`
- end: `0x180004e5a`
- name: `?SetNextIndex@CDVRIndexObject@@QEAAJKG@Z`
- size: `330`
- prototype: `int(CDVRIndexObject *__hidden this, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002930`

## callees

- `0x180004d10`
- `0x180024be4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004de8`
- `KERNEL32!GetLastError` at `0x180004de8`
- `KERNEL32!WriteFile` at `0x180004dd8`
- `KERNEL32!WriteFile` at `0x180004dd8`

## pseudocode

```c
__int64 __fastcall CDVRIndexObject::SetNextIndex(CDVRIndexObject *this, unsigned int a2, unsigned __int16 a3)
{
  __int64 result; // rax
  unsigned int v5; // edi
  int v6; // esi
  int v7; // edx
  int v8; // eax
  int v9; // r14d
  void *v10; // rcx
  int v11; // ebp
  signed int LastError; // eax
  _DWORD *v13; // rcx
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF

  if ( (unsigned __int64)(**((_QWORD **)this + 20) + 6LL) < **((_QWORD **)this + 20) )
    return 2147500037LL;
  result = CASFIndexObject::SetIndexEntry(this, *((_DWORD *)this + 25), a2, a3);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = 1;
    **((_DWORD **)this + 22) = *((_DWORD *)this + 21);
    ++**((_DWORD **)this + 23);
    ++*((_DWORD *)this + 25);
    **((_QWORD **)this + 19) += 6LL;
    **((_QWORD **)this + 20) += 6LL;
    **((_QWORD **)this + 21) += 6LL;
    v7 = *((_DWORD *)this + 20);
    v8 = *((_DWORD *)this + 25);
    v9 = *((_DWORD *)this + 26);
    if ( v8 == v7 )
    {
      v10 = (void *)*((_QWORD *)this + 16);
      *((_DWORD *)this + 26) = 1;
      if ( v10 )
      {
        NumberOfBytesWritten = 0;
        v11 = 6 * v7;
        if ( !WriteFile(v10, *((LPCVOID *)this + 11), 6 * v7, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v11 )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          *((_QWORD *)this + 16) = 0;
        }
        ++*((_DWORD *)this + 34);
        v6 = *((_DWORD *)this + 26);
      }
      *((_DWORD *)this + 25) = 0;
      v8 = 0;
    }
    else
    {
      v6 = *((_DWORD *)this + 26);
    }
    if ( v6 )
    {
      v13 = (_DWORD *)*((_QWORD *)this + 14);
      if ( v8 )
        *v13 += 6;
      else
        *v13 = *((_DWORD *)this + 30);
      if ( v9 )
        **((_QWORD **)this + 18) += 6LL;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180004d10  mov     [rsp+arg_8], rbx
0x180004d15  mov     [rsp+arg_10], rbp
0x180004d1a  push    rsi
0x180004d1b  push    rdi
0x180004d1c  push    r14
0x180004d1e  sub     rsp, 30h
0x180004d22  mov     rax, [rcx+0A0h]
0x180004d29  mov     rbx, rcx
0x180004d2c  mov     r9, [rax]
0x180004d2f  lea     rax, [r9+6]
0x180004d33  cmp     rax, r9
0x180004d36  ja      short loc_180004D42
0x180004d38  mov     eax, 80004005h
0x180004d3d  jmp     loc_180004E47
0x180004d42  movzx   r9d, r8w; unsigned __int16
0x180004d46  mov     r8d, edx; unsigned int
0x180004d49  mov     edx, [rcx+64h]; unsigned int
0x180004d4c  call    ?SetIndexEntry@CASFIndexObject@@QEAAJKKG@Z; CASFIndexObject::SetIndexEntry(ulong,ulong,ushort)
0x180004d51  mov     edi, eax
0x180004d53  test    eax, eax
0x180004d55  js      loc_180004E47
0x180004d5b  mov     eax, [rbx+54h]
0x180004d5e  mov     esi, 1
0x180004d63  mov     rcx, [rbx+0B0h]
0x180004d6a  mov     [rcx], eax
0x180004d6c  mov     rax, [rbx+0B8h]
0x180004d73  add     [rax], esi
0x180004d75  add     [rbx+64h], esi
0x180004d78  mov     rax, [rbx+98h]
0x180004d7f  add     qword ptr [rax], 6
0x180004d83  mov     rax, [rbx+0A0h]
0x180004d8a  add     qword ptr [rax], 6
0x180004d8e  mov     rax, [rbx+0A8h]
0x180004d95  add     qword ptr [rax], 6
0x180004d99  mov     edx, [rbx+50h]
0x180004d9c  mov     eax, [rbx+64h]
0x180004d9f  mov     r14d, [rbx+68h]
0x180004da3  cmp     eax, edx
0x180004da5  jnz     short loc_180004E1C
0x180004da7  mov     rcx, [rbx+80h]; hFile
0x180004dae  mov     [rbx+68h], esi
0x180004db1  test    rcx, rcx
0x180004db4  jz      short loc_180004E11
0x180004db6  lea     ebp, [rdx+rdx*2]
0x180004db9  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180004dc1  mov     rdx, [rbx+58h]; lpBuffer
0x180004dc5  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004dca  add     ebp, ebp
0x180004dcc  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180004dd5  mov     r8d, ebp; nNumberOfBytesToWrite
0x180004dd8  call    cs:__imp_WriteFile
0x180004dde  test    eax, eax
0x180004de0  jz      short loc_180004DE8
0x180004de2  cmp     [rsp+48h+NumberOfBytesWritten], ebp
0x180004de6  jz      short loc_180004E08
0x180004de8  call    cs:__imp_GetLastError
0x180004dee  mov     edi, eax
0x180004df0  test    eax, eax
0x180004df2  jle     short loc_180004DFD
0x180004df4  movzx   edi, ax
0x180004df7  or      edi, 80070000h
0x180004dfd  mov     qword ptr [rbx+80h], 0
0x180004e08  add     [rbx+88h], esi
0x180004e0e  mov     esi, [rbx+68h]
0x180004e11  mov     dword ptr [rbx+64h], 0
0x180004e18  xor     eax, eax
0x180004e1a  jmp     short loc_180004E1F
0x180004e1c  mov     esi, r14d
0x180004e1f  test    esi, esi
0x180004e21  jz      short loc_180004E45
0x180004e23  mov     rcx, [rbx+70h]
0x180004e27  test    eax, eax
0x180004e29  jnz     short loc_180004E32
0x180004e2b  mov     eax, [rbx+78h]
0x180004e2e  mov     [rcx], eax
0x180004e30  jmp     short loc_180004E35
0x180004e32  add     dword ptr [rcx], 6
0x180004e35  test    r14d, r14d
0x180004e38  jz      short loc_180004E45
0x180004e3a  mov     rax, [rbx+90h]
0x180004e41  add     qword ptr [rax], 6
0x180004e45  mov     eax, edi
0x180004e47  mov     rbx, [rsp+48h+arg_8]
0x180004e4c  mov     rbp, [rsp+48h+arg_10]
0x180004e51  add     rsp, 30h
0x180004e55  pop     r14
0x180004e57  pop     rdi
0x180004e58  pop     rsi
0x180004e59  retn
```
