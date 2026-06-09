# CSBERecordingAttributesFile::InternalInitialize_(ushort const *,int)

- ea: `0x18005b488`
- end: `0x18005b56a`
- name: `?InternalInitialize_@CSBERecordingAttributesFile@@AEAAJPEBGH@Z`
- size: `226`
- prototype: `int(CSBERecordingAttributesFile *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800575f8`

## callees

- `0x18005b488`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18005b4a4`
- `KERNEL32!InitializeCriticalSection` at `0x18005b4a4`
- `KERNEL32!GetLastError` at `0x18005b508`
- `KERNEL32!GetLastError` at `0x18005b53f`
- `KERNEL32!GetLastError` at `0x18005b508`
- `KERNEL32!GetLastError` at `0x18005b53f`
- `KERNEL32!SetFileAttributesW` at `0x18005b4b2`
- `KERNEL32!SetFileAttributesW` at `0x18005b525`
- `KERNEL32!SetFileAttributesW` at `0x18005b535`
- `KERNEL32!SetFileAttributesW` at `0x18005b4b2`
- `KERNEL32!SetFileAttributesW` at `0x18005b525`
- `KERNEL32!SetFileAttributesW` at `0x18005b535`
- `KERNEL32!CreateFileW` at `0x18005b4f5`
- `KERNEL32!CreateFileW` at `0x18005b4f5`

## pseudocode

```c
__int64 __fastcall CSBERecordingAttributesFile::InternalInitialize_(
        CSBERecordingAttributesFile *this,
        const unsigned __int16 *a2,
        int a3)
{
  DWORD v6; // edx
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax

  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  SetFileAttributesW(a2, 0x80u);
  v6 = a3 != 0 ? 0x80000000 : -1073741824;
  *((_DWORD *)this + 36) = v6;
  FileW = CreateFileW(a2, v6, a3 != 0 ? 5 : 0, 0, 4u, 0x80u, 0);
  *((_QWORD *)this + 17) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    SetFileAttributesW(a2, 6u);
  }
  else if ( SetFileAttributesW(a2, 6u) )
  {
    return 0;
  }
  else
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return v9;
}

```

## disassembly

```asm
0x18005b488  mov     [rsp+arg_0], rbx
0x18005b48d  mov     [rsp+arg_8], rsi
0x18005b492  push    rdi
0x18005b493  sub     rsp, 40h
0x18005b497  mov     rdi, rcx
0x18005b49a  mov     ebx, r8d
0x18005b49d  add     rcx, 60h ; '`'; lpCriticalSection
0x18005b4a1  mov     rsi, rdx
0x18005b4a4  call    cs:__imp_InitializeCriticalSection
0x18005b4aa  mov     edx, 80h; dwFileAttributes
0x18005b4af  mov     rcx, rsi; lpFileName
0x18005b4b2  call    cs:__imp_SetFileAttributesW
0x18005b4b8  mov     eax, ebx
0x18005b4ba  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18005b4c3  neg     eax
0x18005b4c5  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005b4cd  mov     eax, 0C0000000h
0x18005b4d2  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x18005b4da  sbb     edx, edx
0x18005b4dc  mov     rcx, rsi; lpFileName
0x18005b4df  and     edx, eax
0x18005b4e1  add     edx, eax; dwDesiredAccess
0x18005b4e3  neg     ebx
0x18005b4e5  mov     [rdi+90h], edx
0x18005b4eb  sbb     r8d, r8d
0x18005b4ee  xor     r9d, r9d; lpSecurityAttributes
0x18005b4f1  and     r8d, 5; dwShareMode
0x18005b4f5  call    cs:__imp_CreateFileW
0x18005b4fb  mov     [rdi+88h], rax
0x18005b502  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b506  jnz     short loc_18005B52D
0x18005b508  call    cs:__imp_GetLastError
0x18005b50e  mov     ebx, eax
0x18005b510  test    eax, eax
0x18005b512  jle     short loc_18005B51D
0x18005b514  movzx   ebx, ax
0x18005b517  or      ebx, 80070000h
0x18005b51d  mov     edx, 6; dwFileAttributes
0x18005b522  mov     rcx, rsi; lpFileName
0x18005b525  call    cs:__imp_SetFileAttributesW
0x18005b52b  jmp     short loc_18005B558
0x18005b52d  mov     edx, 6; dwFileAttributes
0x18005b532  mov     rcx, rsi; lpFileName
0x18005b535  call    cs:__imp_SetFileAttributesW
0x18005b53b  test    eax, eax
0x18005b53d  jnz     short loc_18005B556
0x18005b53f  call    cs:__imp_GetLastError
0x18005b545  mov     ebx, eax
0x18005b547  test    eax, eax
0x18005b549  jle     short loc_18005B558
0x18005b54b  movzx   ebx, ax
0x18005b54e  or      ebx, 80070000h
0x18005b554  jmp     short loc_18005B558
0x18005b556  xor     ebx, ebx
0x18005b558  mov     rsi, [rsp+48h+arg_8]
0x18005b55d  mov     eax, ebx
0x18005b55f  mov     rbx, [rsp+48h+arg_0]
0x18005b564  add     rsp, 40h
0x18005b568  pop     rdi
0x18005b569  retn
```
