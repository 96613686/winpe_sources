# _UpdateThumbnailForContact

- ea: `0x180080848`
- end: `0x180080954`
- name: `_UpdateThumbnailForContact`
- size: `268`
- prototype: `__int64 __fastcall(struct IContact *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18007f560`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x180080848`
- `0x180086334`
- `0x180091ef0`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18008090a`
- `SHELL32!SHChangeNotify` at `0x18008090a`
- `imagehlp!TouchFileTimes` at `0x1800808e9`
- `imagehlp!TouchFileTimes` at `0x1800808e9`
- `KERNEL32!CreateFileW` at `0x1800808d5`
- `KERNEL32!CreateFileW` at `0x1800808d5`
- `KERNEL32!CloseHandle` at `0x180080915`
- `KERNEL32!CloseHandle` at `0x180080915`

## pseudocode

```c
__int64 __fastcall UpdateThumbnailForContact(struct IContact *a1)
{
  int Path; // ebx
  LPCWSTR v3; // rdi
  const WCHAR *v4; // rcx
  HANDLE FileW; // rax
  void *v6; // rsi
  int v8; // [rsp+40h] [rbp-248h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 v10[264]; // [rsp+60h] [rbp-228h] BYREF

  STRW::STRW((STRW *)&v8, v10, 0x104u);
  Path = EasyGetPath(a1, (struct STRW *)&v8);
  if ( Path >= 0 )
  {
    v3 = &Str;
    v4 = &Str;
    if ( v8 )
      v4 = lpFileName[0];
    FileW = CreateFileW(v4, 0x100u, 7u, 0, 3u, 0x80u, 0);
    v6 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      TouchFileTimes(FileW, 0);
      if ( v8 )
        v3 = lpFileName[0];
      SHChangeNotify(10240, 0x3005u, v3, 0);
      Path = 0;
      CloseHandle(v6);
    }
  }
  v8 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpFileName);
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180080848  mov     [rsp+arg_8], rbx
0x18008084d  mov     [rsp+arg_10], rsi
0x180080852  push    rdi
0x180080853  sub     rsp, 280h
0x18008085a  mov     rax, cs:__security_cookie
0x180080861  xor     rax, rsp
0x180080864  mov     [rsp+288h+var_18], rax
0x18008086c  mov     rbx, rcx
0x18008086f  lea     rdx, [rsp+288h+var_228]; unsigned __int16 *
0x180080874  lea     rcx, [rsp+288h+var_248]; this
0x180080879  mov     r8d, 104h; unsigned int
0x18008087f  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180080884  mov     rcx, rbx; struct IContact *
0x180080887  lea     rdx, [rsp+288h+var_248]; struct STRW *
0x18008088c  call    ?EasyGetPath@@YAJPEAUIContact@@PEAVSTRW@@@Z; EasyGetPath(IContact *,STRW *)
0x180080891  mov     ebx, eax
0x180080893  test    eax, eax
0x180080895  js      loc_18008091B
0x18008089b  cmp     [rsp+288h+var_248], 0
0x1800808a0  lea     rdi, Str
0x1800808a7  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800808b0  mov     rcx, rdi
0x1800808b3  cmovnz  rcx, [rsp+288h+lpFileName]; lpFileName
0x1800808b9  mov     edx, 100h; dwDesiredAccess
0x1800808be  xor     r9d, r9d; lpSecurityAttributes
0x1800808c1  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800808c9  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x1800808d1  lea     r8d, [r9+7]; dwShareMode
0x1800808d5  call    cs:__imp_CreateFileW
0x1800808db  mov     rsi, rax
0x1800808de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800808e2  jz      short loc_18008091B
0x1800808e4  xor     edx, edx; pSystemTime
0x1800808e6  mov     rcx, rax; FileHandle
0x1800808e9  call    cs:__imp_TouchFileTimes
0x1800808ef  cmp     [rsp+288h+var_248], 0
0x1800808f4  mov     edx, 3005h; uFlags
0x1800808f9  mov     ecx, 2800h; wEventId
0x1800808fe  cmovnz  rdi, [rsp+288h+lpFileName]
0x180080904  xor     r9d, r9d; dwItem2
0x180080907  mov     r8, rdi; dwItem1
0x18008090a  call    cs:__imp_SHChangeNotify
0x180080910  xor     ebx, ebx
0x180080912  mov     rcx, rsi; hObject
0x180080915  call    cs:__imp_CloseHandle
0x18008091b  lea     rcx, [rsp+288h+lpFileName]; this
0x180080920  mov     [rsp+288h+var_248], 0
0x180080928  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18008092d  mov     eax, ebx
0x18008092f  mov     rcx, [rsp+288h+var_18]
0x180080937  xor     rcx, rsp; StackCookie
0x18008093a  call    __security_check_cookie
0x18008093f  lea     r11, [rsp+288h+var_8]
0x180080947  mov     rbx, [r11+18h]
0x18008094b  mov     rsi, [r11+20h]
0x18008094f  mov     rsp, r11
0x180080952  pop     rdi
0x180080953  retn
```
