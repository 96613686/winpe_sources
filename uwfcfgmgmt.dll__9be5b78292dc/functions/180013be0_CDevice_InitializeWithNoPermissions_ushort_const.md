# CDevice::InitializeWithNoPermissions(ushort const *)

- ea: `0x180013be0`
- end: `0x180013c74`
- name: `?InitializeWithNoPermissions@CDevice@@QEAAJPEBG@Z`
- size: `148`
- prototype: `__int64 __fastcall(CDevice *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180015d70`

## callees

- `0x18000e96c`
- `0x180013100`
- `0x180013be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013c3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013c3d`

## pseudocode

```c
__int64 __fastcall CDevice::InitializeWithNoPermissions(CDevice *this, LPCWSTR lpFileName)
{
  unsigned int v3; // ebx
  char v5; // al
  HANDLE FileW; // rax
  signed int LastError; // eax
  bool v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  v9 = 0;
  if ( CheckTokenMembershipHelper((enum WELL_KNOWN_SID_TYPE)this, &v9) < 0 || (v5 = 1, !v9) )
    v5 = 0;
  *((_BYTE *)this + 16) = v5;
  CDevice::Close(this);
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180013be0  mov     rax, rsp
0x180013be3  mov     [rax+10h], rbx
0x180013be7  mov     [rax+18h], rsi
0x180013beb  push    rdi
0x180013bec  sub     rsp, 40h
0x180013bf0  mov     rsi, rdx
0x180013bf3  xor     ebx, ebx
0x180013bf5  lea     rdx, [rax+8]; bool *
0x180013bf9  mov     [rax+8], bl
0x180013bfc  mov     rdi, rcx
0x180013bff  call    ?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)
0x180013c04  test    eax, eax
0x180013c06  js      short loc_180013C10
0x180013c08  mov     al, 1
0x180013c0a  cmp     [rsp+48h+arg_0], al
0x180013c0e  jz      short loc_180013C12
0x180013c10  xor     al, al
0x180013c12  mov     rcx, rdi; this
0x180013c15  mov     [rdi+10h], al
0x180013c18  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180013c1d  mov     r8d, 3; dwShareMode
0x180013c23  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180013c28  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013c30  xor     r9d, r9d; lpSecurityAttributes
0x180013c33  xor     edx, edx; dwDesiredAccess
0x180013c35  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180013c3a  mov     rcx, rsi; lpFileName
0x180013c3d  call    cs:__imp_CreateFileW
0x180013c43  mov     [rdi+8], rax
0x180013c47  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013c4b  jnz     short loc_180013C62
0x180013c4d  call    cs:__imp_GetLastError
0x180013c53  mov     ebx, eax
0x180013c55  test    eax, eax
0x180013c57  jle     short loc_180013C62
0x180013c59  movzx   ebx, ax
0x180013c5c  or      ebx, 80070000h
0x180013c62  mov     rsi, [rsp+48h+arg_10]
0x180013c67  mov     eax, ebx
0x180013c69  mov     rbx, [rsp+48h+arg_8]
0x180013c6e  add     rsp, 40h
0x180013c72  pop     rdi
0x180013c73  retn
```
