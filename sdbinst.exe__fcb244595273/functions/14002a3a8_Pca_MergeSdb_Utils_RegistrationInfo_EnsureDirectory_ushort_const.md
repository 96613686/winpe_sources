# Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory(ushort const *)

- ea: `0x14002a3a8`
- end: `0x14002a3fd`
- name: `?EnsureDirectory@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEBG@Z`
- size: `85`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140027c80`
- `0x14002a1ac`
- `0x14002ce68`

## callees

- `0x14001008c`
- `0x14002a3a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002a3ba`
- `KERNEL32!GetLastError` at `0x14002a3ba`
- `KERNEL32!CreateDirectoryW` at `0x14002a3b0`
- `KERNEL32!CreateDirectoryW` at `0x14002a3b0`

## string_xrefs

- `0x14002a3e5`: `Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory`
- `0x14002a3d4`: `Failed to create merge sdb directory (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory(const unsigned __int16 *a1)
{
  DWORD LastError; // ebx

  if ( CreateDirectoryW(a1, 0) )
    return 0;
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1;
  if ( LastError == 183 )
    return 0;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory",
    1789,
    "Failed to create merge sdb directory (%d)",
    LastError);
  return LastError;
}

```

## disassembly

```asm
0x14002a3a8  push    rbx
0x14002a3aa  sub     rsp, 30h
0x14002a3ae  xor     edx, edx; lpSecurityAttributes
0x14002a3b0  call    cs:__imp_CreateDirectoryW
0x14002a3b6  test    eax, eax
0x14002a3b8  jnz     short loc_14002A3F5
0x14002a3ba  call    cs:__imp_GetLastError
0x14002a3c0  test    eax, eax
0x14002a3c2  mov     ebx, eax
0x14002a3c4  mov     ecx, 1
0x14002a3c9  cmovz   ebx, ecx
0x14002a3cc  cmp     ebx, 0B7h
0x14002a3d2  jz      short loc_14002A3F5
0x14002a3d4  lea     r9, aFailedToCreate; "Failed to create merge sdb directory (%"...
0x14002a3db  mov     [rsp+38h+var_18], ebx
0x14002a3df  mov     r8d, 6FDh
0x14002a3e5  lea     rdx, aPcaMergesdbUti_5; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a3ec  call    AslLogCallPrintf
0x14002a3f1  mov     eax, ebx
0x14002a3f3  jmp     short loc_14002A3F7
0x14002a3f5  xor     eax, eax
0x14002a3f7  add     rsp, 30h
0x14002a3fb  pop     rbx
0x14002a3fc  retn
```
