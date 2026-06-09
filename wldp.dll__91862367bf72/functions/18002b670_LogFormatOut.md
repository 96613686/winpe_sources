# LogFormatOut

- ea: `0x18002b670`
- end: `0x18002b777`
- name: `LogFormatOut`
- size: `263`
- prototype: `__int64 __fastcall(char *Format)`
- caller_count: `9`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001b50c`
- `0x18001d220`
- `0x18001fdb4`
- `0x180023ff0`
- `0x18002a940`
- `0x18002ace8`
- `0x18002ad60`
- `0x18002ade4`
- `0x18002af60`

## callees

- `0x180021ec0`
- `0x180022a10`
- `0x180022a7c`
- `0x18002aa40`
- `0x18002ab2c`
- `0x18002b670`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b74f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b74f`

## pseudocode

```c
int LogFormatOut(char *Format, ...)
{
  const char *v1; // rbx
  int result; // eax
  DWORD nNumberOfBytesToWrite[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v4; // [rsp+40h] [rbp-C8h]
  char Buffer[1024]; // [rsp+48h] [rbp-C0h] BYREF
  va_list ArgList; // [rsp+480h] [rbp+378h] BYREF

  va_start(ArgList, Format);
  v1 = Format;
  *(_QWORD *)nNumberOfBytesToWrite = 0;
  result = (unsigned int)memset_0(Buffer, 0, sizeof(Buffer));
  v4 = 0;
  if ( v1 )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      result = OpenLogFile();
      if ( result < 0 )
        return result;
      v1 = Format;
    }
    result = vsnprintf(Buffer, 0x3FFu, v1, ArgList);
    if ( (unsigned int)result < 0x400 )
    {
      if ( result == 1023 )
        Buffer[1023] = 0;
      result = StringCbLengthA(Buffer, 0x400u, (unsigned __int64 *)nNumberOfBytesToWrite);
      if ( result >= 0 )
        return WriteFile(hFile, Buffer, nNumberOfBytesToWrite[0], 0, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b670  mov     rax, rsp
0x18002b673  mov     [rax+8], rcx
0x18002b677  mov     [rax+10h], rdx
0x18002b67b  mov     [rax+18h], r8
0x18002b67f  mov     [rax+20h], r9
0x18002b683  push    rbp
0x18002b684  push    rbx
0x18002b685  lea     rbp, [rax-368h]
0x18002b68c  sub     rsp, 458h
0x18002b693  mov     rax, cs:__security_cookie
0x18002b69a  xor     rax, rsp
0x18002b69d  mov     [rbp+360h+var_20], rax
0x18002b6a4  mov     rbx, rcx
0x18002b6a7  mov     qword ptr [rsp+460h+nNumberOfBytesToWrite], 0
0x18002b6b0  lea     rcx, [rsp+460h+Buffer]; void *
0x18002b6b5  xor     edx, edx; Val
0x18002b6b7  mov     r8d, 400h; Size
0x18002b6bd  call    memset_0
0x18002b6c2  mov     [rsp+460h+var_428], 0
0x18002b6cb  test    rbx, rbx
0x18002b6ce  jz      loc_18002B75E
0x18002b6d4  cmp     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x18002b6dc  jnz     short loc_18002B6EE
0x18002b6de  call    ?OpenLogFile@@YAJXZ; OpenLogFile(void)
0x18002b6e3  test    eax, eax
0x18002b6e5  js      short loc_18002B75E
0x18002b6e7  mov     rbx, [rbp+360h+arg_0]
0x18002b6ee  mov     r8, rbx; Format
0x18002b6f1  lea     r9, [rbp+360h+ArgList]; ArgList
0x18002b6f8  mov     ebx, 3FFh
0x18002b6fd  lea     rcx, [rsp+460h+Buffer]; Buffer
0x18002b702  mov     edx, ebx; BufferCount
0x18002b704  call    _vsnprintf
0x18002b709  test    eax, eax
0x18002b70b  js      short loc_18002B757
0x18002b70d  cmp     eax, ebx
0x18002b70f  ja      short loc_18002B757
0x18002b711  jnz     short loc_18002B71A
0x18002b713  mov     [rbp+360h+var_21], 0
0x18002b71a  lea     r8, [rsp+460h+nNumberOfBytesToWrite]; unsigned __int64 *
0x18002b71f  mov     edx, 400h; unsigned __int64
0x18002b724  lea     rcx, [rsp+460h+Buffer]; char *
0x18002b729  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18002b72e  test    eax, eax
0x18002b730  js      short loc_18002B75E
0x18002b732  mov     r8d, [rsp+460h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18002b737  lea     rdx, [rsp+460h+Buffer]; lpBuffer
0x18002b73c  mov     rcx, cs:hFile; hFile
0x18002b743  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002b746  mov     qword ptr [rsp+20h], 0; lpOverlapped
0x18002b74f  call    cs:__imp_WriteFile
0x18002b755  jmp     short loc_18002B75E
0x18002b757  mov     [rbp+360h+var_21], 0
0x18002b75e  mov     rcx, [rbp+360h+var_20]
0x18002b765  xor     rcx, rsp; StackCookie
0x18002b768  call    __security_check_cookie
0x18002b76d  add     rsp, 458h
0x18002b774  pop     rbx
0x18002b775  pop     rbp
0x18002b776  retn
```
