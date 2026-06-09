# CryptCATCreateStore(CRYPTCATSTORE_ *,ushort *)

- ea: `0x18002d1d4`
- end: `0x18002d254`
- name: `?CryptCATCreateStore@@YAHPEAUCRYPTCATSTORE_@@PEAG@Z`
- size: `128`
- prototype: `__int64 __fastcall(struct CRYPTCATSTORE_ *, unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800079c0`

## callees

- `0x180002028`
- `0x18002d1d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d218`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d22b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d22b`

## pseudocode

```c
__int64 __fastcall CryptCATCreateStore(struct CRYPTCATSTORE_ *a1, unsigned __int16 *Src)
{
  DWORD LastError; // esi
  HANDLE FileW; // rax

  LastError = GetLastError();
  FileW = CreateFileW(Src, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  SetLastError(LastError);
  return CryptCATOpenStore(a1, Src);
}

```

## disassembly

```asm
0x18002d1d4  mov     [rsp+arg_0], rbx
0x18002d1d9  mov     [rsp+arg_8], rsi
0x18002d1de  push    rdi
0x18002d1df  sub     rsp, 40h
0x18002d1e3  mov     rbx, rdx
0x18002d1e6  mov     rdi, rcx
0x18002d1e9  call    cs:__imp_GetLastError
0x18002d1ef  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002d1f8  xor     r9d, r9d; lpSecurityAttributes
0x18002d1fb  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d203  xor     r8d, r8d; dwShareMode
0x18002d206  mov     edx, 0C0000000h; dwDesiredAccess
0x18002d20b  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18002d213  mov     rcx, rbx; lpFileName
0x18002d216  mov     esi, eax
0x18002d218  call    cs:__imp_CreateFileW
0x18002d21e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d222  jnz     short loc_18002D228
0x18002d224  xor     eax, eax
0x18002d226  jmp     short loc_18002D244
0x18002d228  mov     rcx, rax; hObject
0x18002d22b  call    cs:__imp_CloseHandle
0x18002d231  mov     ecx, esi; dwErrCode
0x18002d233  call    cs:__imp_SetLastError
0x18002d239  mov     rdx, rbx; Src
0x18002d23c  mov     rcx, rdi; struct CRYPTCATSTORE_ *
0x18002d23f  call    ?CryptCATOpenStore@@YAHPEAUCRYPTCATSTORE_@@PEAG@Z; CryptCATOpenStore(CRYPTCATSTORE_ *,ushort *)
0x18002d244  mov     rbx, [rsp+48h+arg_0]
0x18002d249  mov     rsi, [rsp+48h+arg_8]
0x18002d24e  add     rsp, 40h
0x18002d252  pop     rdi
0x18002d253  retn
```
