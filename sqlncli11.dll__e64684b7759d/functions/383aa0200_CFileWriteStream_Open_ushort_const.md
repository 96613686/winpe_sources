# CFileWriteStream::Open(ushort const *)

- ea: `0x383aa0200`
- end: `0x383aa02d9`
- name: `?Open@CFileWriteStream@@UEAAJPEBG@Z`
- size: `217`
- prototype: `int(CFileWriteStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383aa04a0`

## callees

- `0x383aa0200`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383aa0281`
- `KERNEL32!GetLastError` at `0x383aa028b`
- `KERNEL32!GetLastError` at `0x383aa0281`
- `KERNEL32!GetLastError` at `0x383aa028b`
- `KERNEL32!CreateFileW` at `0x383aa025c`
- `KERNEL32!CreateFileW` at `0x383aa025c`
- `KERNEL32!GetFileSize` at `0x383aa0273`
- `KERNEL32!GetFileSize` at `0x383aa0273`

## pseudocode

```c
__int64 __fastcall CFileWriteStream::Open(CFileWriteStream *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax

  if ( a2 && *a2 )
  {
    if ( *((_QWORD *)this + 2) == -1 )
    {
      FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
      *((_QWORD *)this + 2) = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, (LPDWORD)this + 7);
        *((_DWORD *)this + 6) = FileSize;
        if ( FileSize != -1 || !GetLastError() )
          return 0;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        return v3;
    }
    else
    {
      v3 = -2147221302;
    }
  }
  else
  {
    v3 = -2147221303;
  }
  (*(void (__fastcall **)(CFileWriteStream *))(*(_QWORD *)this + 56LL))(this);
  return v3;
}

```

## disassembly

```asm
0x383aa0200  mov     [rsp+arg_0], rbx
0x383aa0205  push    rdi
0x383aa0206  sub     rsp, 40h
0x383aa020a  mov     rax, rdx
0x383aa020d  mov     rdi, rcx
0x383aa0210  test    rdx, rdx
0x383aa0213  jz      loc_383AA02BE
0x383aa0219  cmp     word ptr [rdx], 0
0x383aa021d  jz      loc_383AA02BE
0x383aa0223  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x383aa0228  jz      short loc_383AA0234
0x383aa022a  mov     ebx, 800400CAh
0x383aa022f  jmp     loc_383AA02C3
0x383aa0234  xor     r9d, r9d; lpSecurityAttributes
0x383aa0237  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383aa0240  mov     edx, 0C0000000h; dwDesiredAccess
0x383aa0245  lea     r8d, [r9+1]; dwShareMode
0x383aa0249  mov     rcx, rax; lpFileName
0x383aa024c  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x383aa0254  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x383aa025c  call    cs:__imp_CreateFileW
0x383aa0262  mov     [rdi+10h], rax
0x383aa0266  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383aa026a  jz      short loc_383AA028B
0x383aa026c  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x383aa0270  mov     rcx, rax; hFile
0x383aa0273  call    cs:__imp_GetFileSize
0x383aa0279  mov     [rdi+18h], eax
0x383aa027c  cmp     eax, 0FFFFFFFFh
0x383aa027f  jnz     short loc_383AA02B1
0x383aa0281  call    cs:__imp_GetLastError
0x383aa0287  test    eax, eax
0x383aa0289  jz      short loc_383AA02B1
0x383aa028b  call    cs:__imp_GetLastError
0x383aa0291  mov     ebx, eax
0x383aa0293  test    eax, eax
0x383aa0295  jle     short loc_383AA02A0
0x383aa0297  movzx   ebx, ax
0x383aa029a  or      ebx, 80070000h
0x383aa02a0  test    ebx, ebx
0x383aa02a2  js      short loc_383AA02C3
0x383aa02a4  mov     eax, ebx
0x383aa02a6  mov     rbx, [rsp+48h+arg_0]
0x383aa02ab  add     rsp, 40h
0x383aa02af  pop     rdi
0x383aa02b0  retn
0x383aa02b1  xor     eax, eax
0x383aa02b3  mov     rbx, [rsp+48h+arg_0]
0x383aa02b8  add     rsp, 40h
0x383aa02bc  pop     rdi
0x383aa02bd  retn
0x383aa02be  mov     ebx, 800400C9h
0x383aa02c3  mov     rax, [rdi]
0x383aa02c6  mov     rcx, rdi
0x383aa02c9  call    qword ptr [rax+38h]
0x383aa02cc  mov     eax, ebx
0x383aa02ce  mov     rbx, [rsp+48h+arg_0]
0x383aa02d3  add     rsp, 40h
0x383aa02d7  pop     rdi
0x383aa02d8  retn
```
