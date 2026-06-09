# IsGoodDir(ushort *)

- ea: `0x18003680c`
- end: `0x180036911`
- name: `?IsGoodDir@@YAHPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800365bc`

## callees

- `0x180036410`
- `0x18003680c`
- `0x18004d030`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800368cf`
- `KERNEL32!CloseHandle` at `0x1800368cf`
- `KERNEL32!CreateFileW` at `0x1800368c0`
- `KERNEL32!CreateFileW` at `0x1800368c0`
- `KERNEL32!GetFileAttributesW` at `0x1800368d8`
- `KERNEL32!GetFileAttributesW` at `0x1800368d8`
- `KERNEL32!DeleteFileW` at `0x180036895`
- `KERNEL32!DeleteFileW` at `0x180036895`

## pseudocode

```c
_BOOL8 __fastcall IsGoodDir(char *lpFileName)
{
  WCHAR *v3; // rcx
  signed __int64 v4; // r9
  __int64 v5; // r8
  WCHAR v6; // ax
  WCHAR *v7; // rax
  HANDLE FileW; // rax
  DWORD FileAttributesW; // eax
  _BOOL8 result; // rax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  v3 = FileName;
  v4 = lpFileName - (char *)FileName;
  v5 = 260;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v6 = *(WCHAR *)((char *)v3 + v4);
    if ( !v6 )
      break;
    *v3++ = v6;
    --v5;
  }
  while ( v5 );
  v7 = v3 - 1;
  if ( v5 )
    v7 = v3;
  *v7 = 0;
  result = 0;
  if ( v5 )
  {
    if ( (unsigned int)AddPath(FileName, 0x104u, L"TMP4352$.TMP") )
    {
      DeleteFileW(FileName);
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        CloseHandle(FileW);
        FileAttributesW = GetFileAttributesW((LPCWSTR)lpFileName);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003680c  mov     [rsp+arg_8], rbx
0x180036811  push    rdi
0x180036812  sub     rsp, 260h
0x180036819  mov     rax, cs:__security_cookie
0x180036820  xor     rax, rsp
0x180036823  mov     [rsp+268h+var_18], rax
0x18003682b  mov     rbx, rcx
0x18003682e  lea     rax, [rsp+268h+FileName]
0x180036833  mov     r9, rbx
0x180036836  lea     rcx, [rsp+268h+FileName]
0x18003683b  sub     r9, rax
0x18003683e  mov     edx, 104h; unsigned __int64
0x180036843  xor     edi, edi
0x180036845  mov     r8d, edx
0x180036848  lea     rax, [r8+7FFFFEFAh]
0x18003684f  test    rax, rax
0x180036852  jz      short loc_18003686B
0x180036854  movzx   eax, word ptr [r9+rcx]
0x180036859  test    ax, ax
0x18003685c  jz      short loc_18003686B
0x18003685e  mov     [rcx], ax
0x180036861  add     rcx, 2
0x180036865  sub     r8, 1
0x180036869  jnz     short loc_180036848
0x18003686b  test    r8, r8
0x18003686e  lea     rax, [rcx-2]
0x180036872  cmovnz  rax, rcx
0x180036876  mov     [rax], di
0x180036879  jz      short loc_1800368EE
0x18003687b  lea     r8, aTmp4352Tmp; "TMP4352$.TMP"
0x180036882  lea     rcx, [rsp+268h+FileName]; lpszStart
0x180036887  call    ?AddPath@@YAHPEAG_KPEBG@Z; AddPath(ushort *,unsigned __int64,ushort const *)
0x18003688c  test    eax, eax
0x18003688e  jz      short loc_1800368EE
0x180036890  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180036895  call    cs:__imp_DeleteFileW
0x18003689b  mov     [rsp+268h+hTemplateFile], rdi; hTemplateFile
0x1800368a0  lea     rcx, [rsp+268h+FileName]; lpFileName
0x1800368a5  mov     [rsp+268h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x1800368ad  xor     r9d, r9d; lpSecurityAttributes
0x1800368b0  xor     r8d, r8d; dwShareMode
0x1800368b3  mov     [rsp+268h+dwCreationDisposition], 1; dwCreationDisposition
0x1800368bb  mov     edx, 40000000h; dwDesiredAccess
0x1800368c0  call    cs:__imp_CreateFileW
0x1800368c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800368ca  jz      short loc_1800368EE
0x1800368cc  mov     rcx, rax; hObject
0x1800368cf  call    cs:__imp_CloseHandle
0x1800368d5  mov     rcx, rbx; lpFileName
0x1800368d8  call    cs:__imp_GetFileAttributesW
0x1800368de  cmp     eax, 0FFFFFFFFh
0x1800368e1  jz      short loc_1800368EE
0x1800368e3  test    al, 10h
0x1800368e5  jz      short loc_1800368EE
0x1800368e7  mov     eax, 1
0x1800368ec  jmp     short loc_1800368F0
0x1800368ee  xor     eax, eax
0x1800368f0  mov     rcx, [rsp+268h+var_18]
0x1800368f8  xor     rcx, rsp; StackCookie
0x1800368fb  call    __security_check_cookie
0x180036900  mov     rbx, [rsp+268h+arg_8]
0x180036908  add     rsp, 260h
0x18003690f  pop     rdi
0x180036910  retn
```
