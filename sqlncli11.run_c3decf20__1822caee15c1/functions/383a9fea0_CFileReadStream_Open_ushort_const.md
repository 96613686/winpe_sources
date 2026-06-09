# CFileReadStream::Open(ushort const *)

- ea: `0x383a9fea0`
- end: `0x383a9ff79`
- name: `?Open@CFileReadStream@@UEAAJPEBG@Z`
- size: `217`
- prototype: `int(CFileReadStream *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383aa1a20`
- `0x383aa1b80`

## callees

- `0x383a9fea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a9ff21`
- `KERNEL32!GetLastError` at `0x383a9ff2b`
- `KERNEL32!GetLastError` at `0x383a9ff21`
- `KERNEL32!GetLastError` at `0x383a9ff2b`
- `KERNEL32!CreateFileW` at `0x383a9fefc`
- `KERNEL32!CreateFileW` at `0x383a9fefc`
- `KERNEL32!GetFileSize` at `0x383a9ff13`
- `KERNEL32!GetFileSize` at `0x383a9ff13`

## pseudocode

```c
__int64 __fastcall CFileReadStream::Open(CFileReadStream *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax

  if ( a2 && *a2 )
  {
    if ( *((_QWORD *)this + 2) == -1 )
    {
      FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
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
  (*(void (__fastcall **)(CFileReadStream *))(*(_QWORD *)this + 56LL))(this);
  return v3;
}

```

## disassembly

```asm
0x383a9fea0  mov     [rsp+arg_0], rbx
0x383a9fea5  push    rdi
0x383a9fea6  sub     rsp, 40h
0x383a9feaa  mov     rax, rdx
0x383a9fead  mov     rdi, rcx
0x383a9feb0  test    rdx, rdx
0x383a9feb3  jz      loc_383A9FF5E
0x383a9feb9  cmp     word ptr [rdx], 0
0x383a9febd  jz      loc_383A9FF5E
0x383a9fec3  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x383a9fec8  jz      short loc_383A9FED4
0x383a9feca  mov     ebx, 800400CAh
0x383a9fecf  jmp     loc_383A9FF63
0x383a9fed4  xor     r9d, r9d; lpSecurityAttributes
0x383a9fed7  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a9fee0  mov     edx, 80000000h; dwDesiredAccess
0x383a9fee5  lea     r8d, [r9+1]; dwShareMode
0x383a9fee9  mov     rcx, rax; lpFileName
0x383a9feec  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x383a9fef4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x383a9fefc  call    cs:__imp_CreateFileW
0x383a9ff02  mov     [rdi+10h], rax
0x383a9ff06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a9ff0a  jz      short loc_383A9FF2B
0x383a9ff0c  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x383a9ff10  mov     rcx, rax; hFile
0x383a9ff13  call    cs:__imp_GetFileSize
0x383a9ff19  mov     [rdi+18h], eax
0x383a9ff1c  cmp     eax, 0FFFFFFFFh
0x383a9ff1f  jnz     short loc_383A9FF51
0x383a9ff21  call    cs:__imp_GetLastError
0x383a9ff27  test    eax, eax
0x383a9ff29  jz      short loc_383A9FF51
0x383a9ff2b  call    cs:__imp_GetLastError
0x383a9ff31  mov     ebx, eax
0x383a9ff33  test    eax, eax
0x383a9ff35  jle     short loc_383A9FF40
0x383a9ff37  movzx   ebx, ax
0x383a9ff3a  or      ebx, 80070000h
0x383a9ff40  test    ebx, ebx
0x383a9ff42  js      short loc_383A9FF63
0x383a9ff44  mov     eax, ebx
0x383a9ff46  mov     rbx, [rsp+48h+arg_0]
0x383a9ff4b  add     rsp, 40h
0x383a9ff4f  pop     rdi
0x383a9ff50  retn
0x383a9ff51  xor     eax, eax
0x383a9ff53  mov     rbx, [rsp+48h+arg_0]
0x383a9ff58  add     rsp, 40h
0x383a9ff5c  pop     rdi
0x383a9ff5d  retn
0x383a9ff5e  mov     ebx, 800400C9h
0x383a9ff63  mov     rax, [rdi]
0x383a9ff66  mov     rcx, rdi
0x383a9ff69  call    qword ptr [rax+38h]
0x383a9ff6c  mov     eax, ebx
0x383a9ff6e  mov     rbx, [rsp+48h+arg_0]
0x383a9ff73  add     rsp, 40h
0x383a9ff77  pop     rdi
0x383a9ff78  retn
```
