# VolumeGetVolumeGuid(ushort const *,ushort *,ulong)

- ea: `0x180011870`
- end: `0x1800118f9`
- name: `?VolumeGetVolumeGuid@@YAJPEBGPEAGK@Z`
- size: `137`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180006c80`
- `0x18000b6b0`
- `0x180011130`

## callees

- `0x1800054d0`
- `0x180011870`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800118c3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800118c3`

## pseudocode

```c
__int64 __fastcall VolumeGetVolumeGuid(const unsigned __int16 *a1, unsigned __int16 *a2, DWORD a3)
{
  int v5; // ebx
  signed int LastError; // eax
  WCHAR szVolumeMountPoint; // [rsp+20h] [rbp-28h] BYREF

  if ( a1 )
  {
    v5 = StringCchPrintfW(&szVolumeMountPoint, 4u, L"%s\\", a1);
    if ( v5 >= 0 && !GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, a2, a3) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011870  push    rbx
0x180011872  push    rsi
0x180011873  push    rdi
0x180011874  sub     rsp, 30h
0x180011878  mov     rax, cs:__security_cookie
0x18001187f  xor     rax, rsp
0x180011882  mov     [rsp+48h+var_20], rax
0x180011887  mov     esi, r8d
0x18001188a  mov     rdi, rdx
0x18001188d  test    rcx, rcx
0x180011890  jnz     short loc_180011899
0x180011892  mov     ebx, 80070057h
0x180011897  jmp     short loc_1800118E2
0x180011899  mov     r9, rcx
0x18001189c  lea     r8, aS_1; "%s\\"
0x1800118a3  lea     rcx, [rsp+48h+szVolumeMountPoint]; unsigned __int16 *
0x1800118a8  mov     edx, 4; unsigned __int64
0x1800118ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800118b2  mov     ebx, eax
0x1800118b4  test    eax, eax
0x1800118b6  js      short loc_1800118E2
0x1800118b8  mov     r8d, esi; cchBufferLength
0x1800118bb  lea     rcx, [rsp+48h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800118c0  mov     rdx, rdi; lpszVolumeName
0x1800118c3  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800118c9  test    eax, eax
0x1800118cb  jnz     short loc_1800118E2
0x1800118cd  call    cs:__imp_GetLastError
0x1800118d3  mov     ebx, eax
0x1800118d5  test    eax, eax
0x1800118d7  jle     short loc_1800118E2
0x1800118d9  movzx   ebx, ax
0x1800118dc  or      ebx, 80070000h
0x1800118e2  mov     eax, ebx
0x1800118e4  mov     rcx, [rsp+48h+var_20]
0x1800118e9  xor     rcx, rsp; StackCookie
0x1800118ec  call    __security_check_cookie
0x1800118f1  add     rsp, 30h
0x1800118f5  pop     rdi
0x1800118f6  pop     rsi
0x1800118f7  pop     rbx
0x1800118f8  retn
```
