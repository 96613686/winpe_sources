# CAttachmentServices::_LoadFHC(void)

- ea: `0x180010c18`
- end: `0x180010ca1`
- name: `?_LoadFHC@CAttachmentServices@@AEAAHXZ`
- size: `137`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180010e3c`

## callees

- `0x180008320`
- `0x180010c18`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180010c60`
- `SHLWAPI!PathAppendW` at `0x180010c60`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010c4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180010c4a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010c6f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010c6f`

## string_xrefs

- `0x180010c54`: `winshfhc.dll`

## pseudocode

```c
_BOOL8 __fastcall CAttachmentServices::_LoadFHC(CAttachmentServices *this)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !*((_QWORD *)this + 39) && GetSystemDirectoryW(Buffer, 0x104u) && PathAppendW(Buffer, L"winshfhc.dll") )
    *((_QWORD *)this + 39) = LoadLibraryW(Buffer);
  return *((_QWORD *)this + 39) != 0;
}

```

## disassembly

```asm
0x180010c18  push    rbx
0x180010c1a  sub     rsp, 240h
0x180010c21  mov     rax, cs:__security_cookie
0x180010c28  xor     rax, rsp
0x180010c2b  mov     [rsp+248h+var_18], rax
0x180010c33  cmp     qword ptr [rcx+138h], 0
0x180010c3b  mov     rbx, rcx
0x180010c3e  jnz     short loc_180010C7C
0x180010c40  mov     edx, 104h; uSize
0x180010c45  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180010c4a  call    cs:__imp_GetSystemDirectoryW
0x180010c50  test    eax, eax
0x180010c52  jz      short loc_180010C7C
0x180010c54  lea     rdx, pszMore; "winshfhc.dll"
0x180010c5b  lea     rcx, [rsp+248h+Buffer]; pszPath
0x180010c60  call    cs:__imp_PathAppendW
0x180010c66  test    eax, eax
0x180010c68  jz      short loc_180010C7C
0x180010c6a  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180010c6f  call    cs:__imp_LoadLibraryW
0x180010c75  mov     [rbx+138h], rax
0x180010c7c  xor     eax, eax
0x180010c7e  cmp     [rbx+138h], rax
0x180010c85  setnz   al
0x180010c88  mov     rcx, [rsp+248h+var_18]
0x180010c90  xor     rcx, rsp; StackCookie
0x180010c93  call    __security_check_cookie
0x180010c98  add     rsp, 240h
0x180010c9f  pop     rbx
0x180010ca0  retn
```
