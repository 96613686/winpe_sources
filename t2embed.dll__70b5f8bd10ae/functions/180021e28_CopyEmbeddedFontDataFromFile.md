# CopyEmbeddedFontDataFromFile

- ea: `0x180021e28`
- end: `0x180021ecb`
- name: `CopyEmbeddedFontDataFromFile`
- size: `163`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, int lBytes, LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022fcc`

## callees

- `0x180021e28`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!OpenFile` at `0x180021e6d`
- `KERNEL32!OpenFile` at `0x180021e6d`
- `KERNEL32!_hread` at `0x180021e82`
- `KERNEL32!_hread` at `0x180021e82`
- `KERNEL32!_lclose` at `0x180021e8e`
- `KERNEL32!_lclose` at `0x180021eb4`
- `KERNEL32!_lclose` at `0x180021e8e`
- `KERNEL32!_lclose` at `0x180021eb4`

## pseudocode

```c
__int64 __fastcall CopyEmbeddedFontDataFromFile(LPVOID lpBuffer, int lBytes, LPCSTR lpFileName)
{
  HFILE v6; // eax
  HFILE v7; // ebx
  HFILE v9; // eax
  unsigned int v10; // ecx
  struct _OFSTRUCT ReOpenBuff; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&ReOpenBuff, 0, sizeof(ReOpenBuff));
  v6 = OpenFile(lpFileName, &ReOpenBuff, 0x40u);
  v7 = v6;
  if ( v6 == -1 )
    return 515;
  if ( _hread(v6, lpBuffer, lBytes) != lBytes )
  {
    _lclose(v7);
    return 515;
  }
  v9 = _lclose(v7);
  v10 = 0;
  if ( v9 == -1 )
    return 515;
  return v10;
}

```

## disassembly

```asm
0x180021e28  push    rbx
0x180021e2a  push    rsi
0x180021e2b  push    rdi
0x180021e2c  sub     rsp, 0C0h
0x180021e33  mov     rax, cs:__security_cookie
0x180021e3a  xor     rax, rsp
0x180021e3d  mov     [rsp+0D8h+var_28], rax
0x180021e45  mov     rbx, r8
0x180021e48  mov     edi, edx
0x180021e4a  mov     rsi, rcx
0x180021e4d  xor     edx, edx; Val
0x180021e4f  mov     r8d, 88h; Size
0x180021e55  lea     rcx, [rsp+0D8h+ReOpenBuff]; void *
0x180021e5a  call    memset_0
0x180021e5f  mov     r8d, 40h ; '@'; uStyle
0x180021e65  lea     rdx, [rsp+0D8h+ReOpenBuff]; lpReOpenBuff
0x180021e6a  mov     rcx, rbx; lpFileName
0x180021e6d  call    cs:__imp_OpenFile
0x180021e73  mov     ebx, eax
0x180021e75  cmp     eax, 0FFFFFFFFh
0x180021e78  jz      short loc_180021E94
0x180021e7a  mov     r8d, edi; lBytes
0x180021e7d  mov     rdx, rsi; lpBuffer
0x180021e80  mov     ecx, eax; hFile
0x180021e82  call    cs:__imp__hread
0x180021e88  mov     ecx, ebx; hFile
0x180021e8a  cmp     eax, edi
0x180021e8c  jz      short loc_180021EB4
0x180021e8e  call    cs:__imp__lclose
0x180021e94  mov     eax, 203h
0x180021e99  mov     rcx, [rsp+0D8h+var_28]
0x180021ea1  xor     rcx, rsp; StackCookie
0x180021ea4  call    __security_check_cookie
0x180021ea9  add     rsp, 0C0h
0x180021eb0  pop     rdi
0x180021eb1  pop     rsi
0x180021eb2  pop     rbx
0x180021eb3  retn
0x180021eb4  call    cs:__imp__lclose
0x180021eba  xor     ecx, ecx
0x180021ebc  mov     edx, 203h
0x180021ec1  cmp     eax, 0FFFFFFFFh
0x180021ec4  cmovz   ecx, edx
0x180021ec7  mov     eax, ecx
0x180021ec9  jmp     short loc_180021E99
```
