# CFileReader::Open(ushort const *)

- ea: `0x383a89100`
- end: `0x383a8920a`
- name: `?Open@CFileReader@@UEAAJPEBG@Z`
- size: `266`
- prototype: `int(CFileReader *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a89960`

## callees

- `0x383a89100`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a891bd`
- `KERNEL32!GetLastError` at `0x383a891c7`
- `KERNEL32!GetLastError` at `0x383a891bd`
- `KERNEL32!GetLastError` at `0x383a891c7`
- `KERNEL32!CreateFileW` at `0x383a89198`
- `KERNEL32!CreateFileW` at `0x383a89198`
- `KERNEL32!GetFileSize` at `0x383a891af`
- `KERNEL32!GetFileSize` at `0x383a891af`

## pseudocode

```c
__int64 __fastcall CFileReader::Open(CFileReader *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax
  signed int v7; // ebx

  if ( a2 )
  {
    if ( *a2 )
    {
      if ( *((_QWORD *)this + 1) == -1 )
      {
        FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
        *((_QWORD *)this + 1) = FileW;
        if ( FileW == (HANDLE)-1LL
          || (FileSize = GetFileSize(FileW, (LPDWORD)this + 5), *((_DWORD *)this + 4) = FileSize, FileSize == -1)
          && GetLastError() )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 < 0 )
            (*(void (__fastcall **)(CFileReader *))(*(_QWORD *)this + 56LL))(this);
          return (unsigned int)v7;
        }
        else
        {
          *((_DWORD *)this + 6) = 1;
          return 0;
        }
      }
      else
      {
        (*(void (__fastcall **)(CFileReader *))(*(_QWORD *)this + 56LL))(this);
        return 2147745994LL;
      }
    }
    else
    {
      (*(void (__fastcall **)(CFileReader *))(*(_QWORD *)this + 56LL))(this);
      return 2147745993LL;
    }
  }
  else
  {
    (*(void (__fastcall **)(CFileReader *))(*(_QWORD *)this + 56LL))(this);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x383a89100  mov     [rsp+arg_0], rbx
0x383a89105  push    rdi
0x383a89106  sub     rsp, 40h
0x383a8910a  mov     rax, rdx
0x383a8910d  mov     rdi, rcx
0x383a89110  test    rdx, rdx
0x383a89113  jnz     short loc_383A8912D
0x383a89115  mov     rax, [rcx]
0x383a89118  mov     ebx, 80070057h
0x383a8911d  call    qword ptr [rax+38h]
0x383a89120  mov     eax, ebx
0x383a89122  mov     rbx, [rsp+48h+arg_0]
0x383a89127  add     rsp, 40h
0x383a8912b  pop     rdi
0x383a8912c  retn
0x383a8912d  cmp     word ptr [rdx], 0
0x383a89131  jnz     short loc_383A8914E
0x383a89133  mov     rax, [rdi]
0x383a89136  mov     rcx, rdi
0x383a89139  mov     ebx, 800400C9h
0x383a8913e  call    qword ptr [rax+38h]
0x383a89141  mov     eax, ebx
0x383a89143  mov     rbx, [rsp+48h+arg_0]
0x383a89148  add     rsp, 40h
0x383a8914c  pop     rdi
0x383a8914d  retn
0x383a8914e  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x383a89153  jz      short loc_383A89170
0x383a89155  mov     rax, [rdi]
0x383a89158  mov     rcx, rdi
0x383a8915b  mov     ebx, 800400CAh
0x383a89160  call    qword ptr [rax+38h]
0x383a89163  mov     eax, ebx
0x383a89165  mov     rbx, [rsp+48h+arg_0]
0x383a8916a  add     rsp, 40h
0x383a8916e  pop     rdi
0x383a8916f  retn
0x383a89170  xor     r9d, r9d; lpSecurityAttributes
0x383a89173  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a8917c  mov     edx, 80000000h; dwDesiredAccess
0x383a89181  lea     r8d, [r9+1]; dwShareMode
0x383a89185  mov     rcx, rax; lpFileName
0x383a89188  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x383a89190  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x383a89198  call    cs:__imp_CreateFileW
0x383a8919e  mov     [rdi+8], rax
0x383a891a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a891a6  jz      short loc_383A891C7
0x383a891a8  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x383a891ac  mov     rcx, rax; hFile
0x383a891af  call    cs:__imp_GetFileSize
0x383a891b5  mov     [rdi+10h], eax
0x383a891b8  cmp     eax, 0FFFFFFFFh
0x383a891bb  jnz     short loc_383A891F6
0x383a891bd  call    cs:__imp_GetLastError
0x383a891c3  test    eax, eax
0x383a891c5  jz      short loc_383A891F6
0x383a891c7  call    cs:__imp_GetLastError
0x383a891cd  mov     ebx, eax
0x383a891cf  test    eax, eax
0x383a891d1  jle     short loc_383A891DC
0x383a891d3  movzx   ebx, ax
0x383a891d6  or      ebx, 80070000h
0x383a891dc  test    ebx, ebx
0x383a891de  jns     short loc_383A891E9
0x383a891e0  mov     rax, [rdi]
0x383a891e3  mov     rcx, rdi
0x383a891e6  call    qword ptr [rax+38h]
0x383a891e9  mov     eax, ebx
0x383a891eb  mov     rbx, [rsp+48h+arg_0]
0x383a891f0  add     rsp, 40h
0x383a891f4  pop     rdi
0x383a891f5  retn
0x383a891f6  mov     rbx, [rsp+48h+arg_0]
0x383a891fb  mov     dword ptr [rdi+18h], 1
0x383a89202  xor     eax, eax
0x383a89204  add     rsp, 40h
0x383a89208  pop     rdi
0x383a89209  retn
```
