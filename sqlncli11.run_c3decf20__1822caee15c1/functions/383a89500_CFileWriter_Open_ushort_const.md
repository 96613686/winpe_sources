# CFileWriter::Open(ushort const *)

- ea: `0x383a89500`
- end: `0x383a8960a`
- name: `?Open@CFileWriter@@UEAAJPEBG@Z`
- size: `266`
- prototype: `int(CFileWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a89f30`

## callees

- `0x383a89500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a895bd`
- `KERNEL32!GetLastError` at `0x383a895c7`
- `KERNEL32!GetLastError` at `0x383a895bd`
- `KERNEL32!GetLastError` at `0x383a895c7`
- `KERNEL32!CreateFileW` at `0x383a89598`
- `KERNEL32!CreateFileW` at `0x383a89598`
- `KERNEL32!GetFileSize` at `0x383a895af`
- `KERNEL32!GetFileSize` at `0x383a895af`

## pseudocode

```c
__int64 __fastcall CFileWriter::Open(CFileWriter *this, const unsigned __int16 *a2)
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
        FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
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
            (*(void (__fastcall **)(CFileWriter *))(*(_QWORD *)this + 48LL))(this);
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
        (*(void (__fastcall **)(CFileWriter *))(*(_QWORD *)this + 48LL))(this);
        return 2147745994LL;
      }
    }
    else
    {
      (*(void (__fastcall **)(CFileWriter *))(*(_QWORD *)this + 48LL))(this);
      return 2147745993LL;
    }
  }
  else
  {
    (*(void (__fastcall **)(CFileWriter *))(*(_QWORD *)this + 48LL))(this);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x383a89500  mov     [rsp+arg_0], rbx
0x383a89505  push    rdi
0x383a89506  sub     rsp, 40h
0x383a8950a  mov     rax, rdx
0x383a8950d  mov     rdi, rcx
0x383a89510  test    rdx, rdx
0x383a89513  jnz     short loc_383A8952D
0x383a89515  mov     rax, [rcx]
0x383a89518  mov     ebx, 80070057h
0x383a8951d  call    qword ptr [rax+30h]
0x383a89520  mov     eax, ebx
0x383a89522  mov     rbx, [rsp+48h+arg_0]
0x383a89527  add     rsp, 40h
0x383a8952b  pop     rdi
0x383a8952c  retn
0x383a8952d  cmp     word ptr [rdx], 0
0x383a89531  jnz     short loc_383A8954E
0x383a89533  mov     rax, [rdi]
0x383a89536  mov     rcx, rdi
0x383a89539  mov     ebx, 800400C9h
0x383a8953e  call    qword ptr [rax+30h]
0x383a89541  mov     eax, ebx
0x383a89543  mov     rbx, [rsp+48h+arg_0]
0x383a89548  add     rsp, 40h
0x383a8954c  pop     rdi
0x383a8954d  retn
0x383a8954e  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x383a89553  jz      short loc_383A89570
0x383a89555  mov     rax, [rdi]
0x383a89558  mov     rcx, rdi
0x383a8955b  mov     ebx, 800400CAh
0x383a89560  call    qword ptr [rax+30h]
0x383a89563  mov     eax, ebx
0x383a89565  mov     rbx, [rsp+48h+arg_0]
0x383a8956a  add     rsp, 40h
0x383a8956e  pop     rdi
0x383a8956f  retn
0x383a89570  xor     r9d, r9d; lpSecurityAttributes
0x383a89573  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a8957c  mov     edx, 0C0000000h; dwDesiredAccess
0x383a89581  lea     r8d, [r9+1]; dwShareMode
0x383a89585  mov     rcx, rax; lpFileName
0x383a89588  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x383a89590  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x383a89598  call    cs:__imp_CreateFileW
0x383a8959e  mov     [rdi+8], rax
0x383a895a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a895a6  jz      short loc_383A895C7
0x383a895a8  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x383a895ac  mov     rcx, rax; hFile
0x383a895af  call    cs:__imp_GetFileSize
0x383a895b5  mov     [rdi+10h], eax
0x383a895b8  cmp     eax, 0FFFFFFFFh
0x383a895bb  jnz     short loc_383A895F6
0x383a895bd  call    cs:__imp_GetLastError
0x383a895c3  test    eax, eax
0x383a895c5  jz      short loc_383A895F6
0x383a895c7  call    cs:__imp_GetLastError
0x383a895cd  mov     ebx, eax
0x383a895cf  test    eax, eax
0x383a895d1  jle     short loc_383A895DC
0x383a895d3  movzx   ebx, ax
0x383a895d6  or      ebx, 80070000h
0x383a895dc  test    ebx, ebx
0x383a895de  jns     short loc_383A895E9
0x383a895e0  mov     rax, [rdi]
0x383a895e3  mov     rcx, rdi
0x383a895e6  call    qword ptr [rax+30h]
0x383a895e9  mov     eax, ebx
0x383a895eb  mov     rbx, [rsp+48h+arg_0]
0x383a895f0  add     rsp, 40h
0x383a895f4  pop     rdi
0x383a895f5  retn
0x383a895f6  mov     rbx, [rsp+48h+arg_0]
0x383a895fb  mov     dword ptr [rdi+18h], 1
0x383a89602  xor     eax, eax
0x383a89604  add     rsp, 40h
0x383a89608  pop     rdi
0x383a89609  retn
```
