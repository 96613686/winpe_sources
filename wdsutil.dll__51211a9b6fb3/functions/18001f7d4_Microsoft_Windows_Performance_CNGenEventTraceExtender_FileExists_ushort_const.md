# Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)

- ea: `0x18001f7d4`
- end: `0x18001f829`
- name: `?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z`
- size: `85`
- prototype: `bool(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f284`

## callees

- `0x18001f7d4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001f811`
- `KERNEL32!CloseHandle` at `0x18001f811`
- `KERNEL32!CreateFileW` at `0x18001f7fc`
- `KERNEL32!CreateFileW` at `0x18001f7fc`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18001f7d4  sub     rsp, 48h
0x18001f7d8  mov     rcx, rdx; lpFileName
0x18001f7db  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001f7e4  mov     r8d, 3; dwShareMode
0x18001f7ea  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001f7f2  xor     edx, edx; dwDesiredAccess
0x18001f7f4  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001f7f9  xor     r9d, r9d; lpSecurityAttributes
0x18001f7fc  call    cs:__imp_CreateFileW
0x18001f803  nop     dword ptr [rax+rax+00h]
0x18001f808  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f80c  jz      short loc_18001F821
0x18001f80e  mov     rcx, rax; hObject
0x18001f811  call    cs:__imp_CloseHandle
0x18001f818  nop     dword ptr [rax+rax+00h]
0x18001f81d  mov     al, 1
0x18001f81f  jmp     short loc_18001F823
0x18001f821  xor     al, al
0x18001f823  add     rsp, 48h
0x18001f827  retn
```
