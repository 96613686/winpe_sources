# IsPathInAddressBook(ushort const *)

- ea: `0x180013ee4`
- end: `0x1800140af`
- name: `?IsPathInAddressBook@@YAHPEBG@Z`
- size: `459`
- prototype: `__int64 __fastcall(wchar_t *Path)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180009300`
- `0x180009918`
- `0x18000b6b4`
- `0x18003c2e0`

## callees

- `0x180013ee4`
- `0x180024b6c`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `msvcrt!_wfullpath` at `0x180013f8c`
- `msvcrt!_wfullpath` at `0x180013fb3`
- `msvcrt!_wfullpath` at `0x180013f8c`
- `msvcrt!_wfullpath` at `0x180013fb3`
- `SHLWAPI!PathCanonicalizeW` at `0x180014036`
- `SHLWAPI!PathCanonicalizeW` at `0x180014036`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ff9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180014075`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ff9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180014075`
- `SHLWAPI!StrCmpIW` at `0x18001404c`
- `SHLWAPI!StrCmpIW` at `0x18001404c`
- `SHLWAPI!StrCmpNIW` at `0x180014020`
- `SHLWAPI!StrCmpNIW` at `0x180014020`
- `SHLWAPI!PathRemoveBackslashW` at `0x180013fa2`
- `SHLWAPI!PathRemoveBackslashW` at `0x180013fe1`
- `SHLWAPI!PathRemoveBackslashW` at `0x180013fa2`
- `SHLWAPI!PathRemoveBackslashW` at `0x180013fe1`
- `KERNEL32!GetFileAttributesW` at `0x180013fc7`
- `KERNEL32!GetFileAttributesW` at `0x18001405d`
- `KERNEL32!GetFileAttributesW` at `0x180013fc7`
- `KERNEL32!GetFileAttributesW` at `0x18001405d`

## pseudocode

```c
__int64 __fastcall IsPathInAddressBook(wchar_t *Path)
{
  unsigned int v2; // ebx
  unsigned __int64 v3; // rdx
  DWORD FileAttributesW; // eax
  __int64 v5; // r8
  BOOL i; // eax
  DWORD v7; // eax
  wchar_t FileName[264]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t Buffer[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszBuf[264]; // [rsp+440h] [rbp+340h] BYREF
  wchar_t Patha[264]; // [rsp+650h] [rbp+550h] BYREF

  v2 = 0;
  memset_0(Patha, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(pszBuf, 0, 0x208u);
  if ( (int)GetContactsFolderPath(Patha, v3) >= 0 )
  {
    if ( _wfullpath(Buffer, Patha, 0x104u) )
    {
      PathRemoveBackslashW(Buffer);
      if ( _wfullpath(FileName, Path, 0x104u) )
      {
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW != -1 )
        {
          if ( (FileAttributesW & 0x10) != 0 )
          {
            PathRemoveBackslashW(FileName);
          }
          else
          {
            if ( (FileAttributesW & 6) == 6 )
              return v2;
            PathRemoveFileSpecW(FileName);
          }
          v5 = -1;
          do
            ++v5;
          while ( Buffer[v5] );
          if ( !StrCmpNIW(FileName, Buffer, v5) )
          {
            for ( i = PathCanonicalizeW(pszBuf, FileName); i; i = PathRemoveFileSpecW(pszBuf) )
            {
              if ( !StrCmpIW(pszBuf, Buffer) )
                return 1;
              v7 = GetFileAttributesW(pszBuf);
              if ( v7 == -1 || (v7 & 6) == 6 )
                return v2;
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180013ee4  mov     [rsp-8+arg_8], rbx
0x180013ee9  mov     [rsp-8+arg_10], rsi
0x180013eee  push    rbp
0x180013eef  push    rdi
0x180013ef0  push    r14
0x180013ef2  lea     rbp, [rsp-770h]
0x180013efa  sub     rsp, 870h
0x180013f01  mov     rax, cs:__security_cookie
0x180013f08  xor     rax, rsp
0x180013f0b  mov     [rbp+780h+var_20], rax
0x180013f12  mov     rdi, rcx
0x180013f15  mov     esi, 208h
0x180013f1a  xor     r14d, r14d
0x180013f1d  lea     rcx, [rbp+780h+Path]; void *
0x180013f24  mov     r8d, esi; Size
0x180013f27  xor     edx, edx; Val
0x180013f29  mov     ebx, r14d
0x180013f2c  call    memset_0
0x180013f31  mov     r8d, esi; Size
0x180013f34  lea     rcx, [rbp+780h+Buffer]; void *
0x180013f3b  xor     edx, edx; Val
0x180013f3d  call    memset_0
0x180013f42  mov     r8d, esi; Size
0x180013f45  lea     rcx, [rsp+880h+FileName]; void *
0x180013f4a  xor     edx, edx; Val
0x180013f4c  call    memset_0
0x180013f51  mov     r8d, esi; Size
0x180013f54  lea     rcx, [rbp+780h+pszBuf]; void *
0x180013f5b  xor     edx, edx; Val
0x180013f5d  call    memset_0
0x180013f62  lea     rcx, [rbp+780h+Path]; unsigned __int16 *
0x180013f69  call    ?GetContactsFolderPath@@YAJQEAG_K@Z; GetContactsFolderPath(ushort * const,unsigned __int64)
0x180013f6e  test    eax, eax
0x180013f70  js      loc_180014086
0x180013f76  mov     esi, 104h
0x180013f7b  lea     rdx, [rbp+780h+Path]; Path
0x180013f82  mov     r8d, esi; BufferCount
0x180013f85  lea     rcx, [rbp+780h+Buffer]; Buffer
0x180013f8c  call    cs:__imp__wfullpath
0x180013f92  test    rax, rax
0x180013f95  jz      loc_180014086
0x180013f9b  lea     rcx, [rbp+780h+Buffer]; pszPath
0x180013fa2  call    cs:__imp_PathRemoveBackslashW
0x180013fa8  mov     r8d, esi; BufferCount
0x180013fab  lea     rcx, [rsp+880h+FileName]; Buffer
0x180013fb0  mov     rdx, rdi; Path
0x180013fb3  call    cs:__imp__wfullpath
0x180013fb9  test    rax, rax
0x180013fbc  jz      loc_180014086
0x180013fc2  lea     rcx, [rsp+880h+FileName]; lpFileName
0x180013fc7  call    cs:__imp_GetFileAttributesW
0x180013fcd  or      edi, 0FFFFFFFFh
0x180013fd0  cmp     eax, edi
0x180013fd2  jz      loc_180014086
0x180013fd8  test    al, 10h
0x180013fda  jz      short loc_180013FE9
0x180013fdc  lea     rcx, [rsp+880h+FileName]; pszPath
0x180013fe1  call    cs:__imp_PathRemoveBackslashW
0x180013fe7  jmp     short loc_180013FFF
0x180013fe9  and     eax, 6
0x180013fec  cmp     al, 6
0x180013fee  jz      loc_180014086
0x180013ff4  lea     rcx, [rsp+880h+FileName]; pszPath
0x180013ff9  call    cs:__imp_PathRemoveFileSpecW
0x180013fff  lea     rax, [rbp+780h+Buffer]
0x180014006  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001400a  inc     r8; nChar
0x18001400d  cmp     [rax+r8*2], r14w
0x180014012  jnz     short loc_18001400A
0x180014014  lea     rdx, [rbp+780h+Buffer]; psz2
0x18001401b  lea     rcx, [rsp+880h+FileName]; psz1
0x180014020  call    cs:__imp_StrCmpNIW
0x180014026  test    eax, eax
0x180014028  jnz     short loc_180014086
0x18001402a  lea     rdx, [rsp+880h+FileName]; pszPath
0x18001402f  lea     rcx, [rbp+780h+pszBuf]; pszBuf
0x180014036  call    cs:__imp_PathCanonicalizeW
0x18001403c  jmp     short loc_18001407B
0x18001403e  lea     rdx, [rbp+780h+Buffer]; psz2
0x180014045  lea     rcx, [rbp+780h+pszBuf]; psz1
0x18001404c  call    cs:__imp_StrCmpIW
0x180014052  test    eax, eax
0x180014054  jz      short loc_180014081
0x180014056  lea     rcx, [rbp+780h+pszBuf]; lpFileName
0x18001405d  call    cs:__imp_GetFileAttributesW
0x180014063  cmp     eax, edi
0x180014065  jz      short loc_180014086
0x180014067  and     eax, 6
0x18001406a  cmp     al, 6
0x18001406c  jz      short loc_180014086
0x18001406e  lea     rcx, [rbp+780h+pszBuf]; pszPath
0x180014075  call    cs:__imp_PathRemoveFileSpecW
0x18001407b  test    eax, eax
0x18001407d  jnz     short loc_18001403E
0x18001407f  jmp     short loc_180014086
0x180014081  mov     ebx, 1
0x180014086  mov     eax, ebx
0x180014088  mov     rcx, [rbp+780h+var_20]
0x18001408f  xor     rcx, rsp; StackCookie
0x180014092  call    __security_check_cookie
0x180014097  lea     r11, [rsp+880h+var_10]
0x18001409f  mov     rbx, [r11+28h]
0x1800140a3  mov     rsi, [r11+30h]
0x1800140a7  mov     rsp, r11
0x1800140aa  pop     r14
0x1800140ac  pop     rdi
0x1800140ad  pop     rbp
0x1800140ae  retn
```
