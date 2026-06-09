# T2OSSvcDeleteFontFile

- ea: `0x180022c7c`
- end: `0x180022cfc`
- name: `T2OSSvcDeleteFontFile`
- size: `128`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800190a4`
- `0x180023224`

## callees

- `0x180022c7c`

## import_xrefs

- `KERNEL32!MoveFileExA` at `0x180022ccb`
- `KERNEL32!MoveFileExA` at `0x180022ccb`
- `KERNEL32!DeleteFileA` at `0x180022cb6`
- `KERNEL32!DeleteFileA` at `0x180022ceb`
- `KERNEL32!DeleteFileA` at `0x180022cb6`
- `KERNEL32!DeleteFileA` at `0x180022ceb`

## pseudocode

```c
__int64 __fastcall T2OSSvcDeleteFontFile(LPCSTR lpFileName)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  const CHAR *v4; // rbp
  __int64 v5; // rax

  v2 = 1;
  if ( !*((_QWORD *)lpFileName + 115) )
  {
    v3 = -1;
    v4 = lpFileName + 260;
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    if ( v5 )
    {
      v2 = DeleteFileA(lpFileName + 260);
      if ( !v2 )
        MoveFileExA(v4, 0, 5u);
    }
    if ( *((_DWORD *)lpFileName + 227) )
    {
      do
        ++v3;
      while ( lpFileName[v3] );
      if ( v3 )
        DeleteFileA(lpFileName);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180022c7c  push    rbx
0x180022c7e  push    rbp
0x180022c7f  push    rsi
0x180022c80  push    rdi
0x180022c81  sub     rsp, 28h
0x180022c85  cmp     qword ptr [rcx+398h], 0
0x180022c8d  mov     rbx, rcx
0x180022c90  mov     esi, 1
0x180022c95  jnz     short loc_180022CF1
0x180022c97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022c9b  lea     rbp, [rcx+104h]
0x180022ca2  mov     rax, rdi
0x180022ca5  inc     rax
0x180022ca8  cmp     byte ptr [rax+rbp], 0
0x180022cac  jnz     short loc_180022CA5
0x180022cae  test    rax, rax
0x180022cb1  jz      short loc_180022CD1
0x180022cb3  mov     rcx, rbp; lpFileName
0x180022cb6  call    cs:__imp_DeleteFileA
0x180022cbc  mov     esi, eax
0x180022cbe  test    eax, eax
0x180022cc0  jnz     short loc_180022CD1
0x180022cc2  xor     edx, edx; lpNewFileName
0x180022cc4  lea     r8d, [rax+5]; dwFlags
0x180022cc8  mov     rcx, rbp; lpExistingFileName
0x180022ccb  call    cs:__imp_MoveFileExA
0x180022cd1  cmp     dword ptr [rbx+38Ch], 0
0x180022cd8  jz      short loc_180022CF1
0x180022cda  inc     rdi
0x180022cdd  cmp     byte ptr [rbx+rdi], 0
0x180022ce1  jnz     short loc_180022CDA
0x180022ce3  test    rdi, rdi
0x180022ce6  jz      short loc_180022CF1
0x180022ce8  mov     rcx, rbx; lpFileName
0x180022ceb  call    cs:__imp_DeleteFileA
0x180022cf1  mov     eax, esi
0x180022cf3  add     rsp, 28h
0x180022cf7  pop     rdi
0x180022cf8  pop     rsi
0x180022cf9  pop     rbp
0x180022cfa  pop     rbx
0x180022cfb  retn
```
