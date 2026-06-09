# CDevice::Initialize(ushort const *)

- ea: `0x1800139f0`
- end: `0x180013a87`
- name: `?Initialize@CDevice@@QEAAJPEBG@Z`
- size: `151`
- prototype: `__int64 __fastcall(CDevice *__hidden this, LPCWSTR lpFileName)`
- caller_count: `21`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800092a8`
- `0x180009758`
- `0x180009a50`
- `0x18000ea14`
- `0x1800104ac`
- `0x180010738`
- `0x180011490`
- `0x18001155c`
- `0x180013a90`
- `0x180013b90`
- `0x180013bc0`
- `0x1800151b0`
- `0x1800155f0`
- `0x180015870`
- `0x1800162e0`
- `0x1800163b0`
- `0x180016840`
- `0x180016a74`
- `0x180017100`
- `0x180017890`
- `0x18001aa08`

## callees

- `0x18000e96c`
- `0x180013100`
- `0x1800139f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013a50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013a50`

## pseudocode

```c
__int64 __fastcall CDevice::Initialize(CDevice *this, LPCWSTR lpFileName)
{
  unsigned int v3; // ebx
  char v5; // al
  HANDLE FileW; // rax
  signed int LastError; // eax
  bool v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  v9 = 0;
  if ( (int)CheckTokenMembershipHelper((enum WELL_KNOWN_SID_TYPE)this, &v9) < 0 || (v5 = 1, !v9) )
    v5 = 0;
  *((_BYTE *)this + 16) = v5;
  CDevice::Close(this);
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
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
0x1800139f0  mov     rax, rsp
0x1800139f3  mov     [rax+10h], rbx
0x1800139f7  mov     [rax+18h], rsi
0x1800139fb  push    rdi
0x1800139fc  sub     rsp, 40h
0x180013a00  mov     rsi, rdx
0x180013a03  xor     ebx, ebx
0x180013a05  lea     rdx, [rax+8]; bool *
0x180013a09  mov     [rax+8], bl
0x180013a0c  mov     rdi, rcx
0x180013a0f  call    ?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)
0x180013a14  test    eax, eax
0x180013a16  js      short loc_180013A20
0x180013a18  mov     al, 1
0x180013a1a  cmp     [rsp+48h+arg_0], al
0x180013a1e  jz      short loc_180013A22
0x180013a20  xor     al, al
0x180013a22  mov     rcx, rdi; this
0x180013a25  mov     [rdi+10h], al
0x180013a28  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180013a2d  mov     r8d, 3; dwShareMode
0x180013a33  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180013a38  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013a40  xor     r9d, r9d; lpSecurityAttributes
0x180013a43  mov     edx, 0C0000000h; dwDesiredAccess
0x180013a48  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180013a4d  mov     rcx, rsi; lpFileName
0x180013a50  call    cs:__imp_CreateFileW
0x180013a56  mov     [rdi+8], rax
0x180013a5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013a5e  jnz     short loc_180013A75
0x180013a60  call    cs:__imp_GetLastError
0x180013a66  mov     ebx, eax
0x180013a68  test    eax, eax
0x180013a6a  jle     short loc_180013A75
0x180013a6c  movzx   ebx, ax
0x180013a6f  or      ebx, 80070000h
0x180013a75  mov     rsi, [rsp+48h+arg_10]
0x180013a7a  mov     eax, ebx
0x180013a7c  mov     rbx, [rsp+48h+arg_8]
0x180013a81  add     rsp, 40h
0x180013a85  pop     rdi
0x180013a86  retn
```
