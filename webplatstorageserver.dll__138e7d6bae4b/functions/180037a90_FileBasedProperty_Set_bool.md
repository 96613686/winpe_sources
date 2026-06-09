# FileBasedProperty::Set(bool)

- ea: `0x180037a90`
- end: `0x180037b90`
- name: `?Set@FileBasedProperty@@QEAAX_N@Z`
- size: `256`
- prototype: `void __fastcall(FileBasedProperty *lpFileName, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180037088`
- `0x180037100`
- `0x18006f248`
- `0x1800726cc`
- `0x1800a30d4`

## callees

- `0x180037a90`
- `0x180061c90`
- `0x1800759e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037b33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037b33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037af3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037af3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037b4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037b4e`

## pseudocode

```c
void __fastcall FileBasedProperty::Set(FileBasedProperty *lpFileName, char a2)
{
  FileBasedProperty *v3; // rbx
  _DWORD *v4; // rdi
  char *FileW; // r8
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = lpFileName;
  if ( FileBasedProperty::Get(lpFileName) != a2 )
  {
    v4 = (_DWORD *)((char *)v3 + 32);
    *((_DWORD *)v3 + 8) = -1;
    if ( a2 )
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(FileBasedProperty **)v3;
      FileW = (char *)CreateFileW((LPCWSTR)v3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x23,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\utils\\filebasedproperty.cxx",
          v6);
      CloseHandle(FileW);
      *v4 = 1;
    }
    else
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(FileBasedProperty **)v3;
      if ( !DeleteFileW((LPCWSTR)v3) && GetLastError() != 2 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\utils\\filebasedproperty.cxx",
          v7);
      *v4 = 0;
    }
  }
}

```

## disassembly

```asm
0x180037a90  mov     [rsp+arg_0], rbx
0x180037a95  mov     [rsp+arg_8], rsi
0x180037a9a  push    rdi
0x180037a9b  sub     rsp, 40h
0x180037a9f  mov     sil, dl
0x180037aa2  mov     rbx, rcx
0x180037aa5  call    ?Get@FileBasedProperty@@QEBA_NXZ; FileBasedProperty::Get(void)
0x180037aaa  cmp     al, sil
0x180037aad  jz      loc_180037B80
0x180037ab3  lea     rdi, [rbx+20h]
0x180037ab7  mov     dword ptr [rdi], 0FFFFFFFFh
0x180037abd  test    sil, sil
0x180037ac0  jz      short loc_180037B41
0x180037ac2  cmp     qword ptr [rbx+18h], 7
0x180037ac7  jbe     short loc_180037ACC
0x180037ac9  mov     rbx, [rbx]
0x180037acc  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180037ad5  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180037add  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x180037ae5  xor     r9d, r9d; lpSecurityAttributes
0x180037ae8  xor     r8d, r8d; dwShareMode
0x180037aeb  mov     edx, 40000000h; dwDesiredAccess
0x180037af0  mov     rcx, rbx; lpFileName
0x180037af3  call    cs:__imp_CreateFileW
0x180037af9  mov     r8, rax
0x180037afc  mov     [rsp+48h+arg_10], rax
0x180037b01  lea     rcx, [rax-1]
0x180037b05  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180037b09  setbe   dl
0x180037b0c  mov     rcx, [rsp+48h]; this
0x180037b11  test    dl, dl
0x180037b13  jnz     short loc_180037B27
0x180037b15  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\webplatstorageser"...
0x180037b1c  mov     edx, 23h ; '#'; void *
0x180037b21  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180037b27  dec     rax
0x180037b2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037b2e  ja      short loc_180037B39
0x180037b30  mov     rcx, r8; hObject
0x180037b33  call    cs:__imp_CloseHandle
0x180037b39  mov     dword ptr [rdi], 1
0x180037b3f  jmp     short loc_180037B80
0x180037b41  cmp     qword ptr [rbx+18h], 7
0x180037b46  jbe     short loc_180037B4B
0x180037b48  mov     rbx, [rbx]
0x180037b4b  mov     rcx, rbx; lpFileName
0x180037b4e  call    cs:__imp_DeleteFileW
0x180037b54  test    eax, eax
0x180037b56  jnz     short loc_180037B7A
0x180037b58  call    cs:__imp_GetLastError
0x180037b5e  cmp     eax, 2
0x180037b61  jz      short loc_180037B7A
0x180037b63  mov     rcx, [rsp+48h]; this
0x180037b68  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\webplatstorageser"...
0x180037b6f  mov     edx, 28h ; '('; void *
0x180037b74  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180037b7a  mov     dword ptr [rdi], 0
0x180037b80  mov     rbx, [rsp+48h+arg_0]
0x180037b85  mov     rsi, [rsp+48h+arg_8]
0x180037b8a  add     rsp, 40h
0x180037b8e  pop     rdi
0x180037b8f  retn
```
