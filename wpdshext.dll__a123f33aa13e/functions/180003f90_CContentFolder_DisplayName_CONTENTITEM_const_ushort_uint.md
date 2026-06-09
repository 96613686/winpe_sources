# CContentFolder::_DisplayName(CONTENTITEM const *,ushort *,uint)

- ea: `0x180003f90`
- end: `0x180004107`
- name: `?_DisplayName@CContentFolder@@AEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z`
- size: `375`
- prototype: `const unsigned __int16 *(CContentFolder *__hidden this, const struct CONTENTITEM *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002cf0`
- `0x180032658`
- `0x1800437e0`

## callees

- `0x180003f90`
- `0x180004110`
- `0x180035590`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800040e9`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800040e9`
- `SHLWAPI!PathFindFileNameW` at `0x18000403d`
- `SHLWAPI!PathFindFileNameW` at `0x18000403d`
- `SHELL32!SHGetSettings` at `0x180003fca`
- `SHELL32!SHGetSettings` at `0x180003fca`

## pseudocode

```c
unsigned __int16 *__fastcall CContentFolder::_DisplayName(
        CContentFolder *this,
        const struct CONTENTITEM *a2,
        unsigned __int16 *a3)
{
  int v5; // ebp
  __int64 v6; // rax
  __int64 v7; // rbx
  WCHAR *v8; // rdx
  __int64 v9; // rdi
  WCHAR *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r9
  WCHAR *v13; // rcx
  WCHAR *v14; // rcx
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rcx
  SHELLFLAGSTATE psfs; // [rsp+50h] [rbp-688h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-678h] BYREF
  wchar_t Filename[264]; // [rsp+270h] [rbp-468h] BYREF
  wchar_t Ext[264]; // [rsp+480h] [rbp-258h] BYREF

  psfs = 0;
  SHGetSettings(&psfs, 2u);
  v5 = (int)(*(_DWORD *)&psfs << 30) >> 31;
  if ( *(_DWORD *)((char *)a2 + 66) <= 1u )
    v6 = 74;
  else
    v6 = 2LL * *(unsigned int *)((char *)a2 + 62) + 74;
  v7 = 2147483646;
  v8 = (WCHAR *)((char *)a2 + v6);
  v9 = 260;
  v10 = pszPath;
  v11 = 2147483646;
  v12 = 260;
  do
  {
    if ( !v11 )
      break;
    if ( !*v8 )
      break;
    *v10++ = *v8++;
    --v11;
    --v12;
  }
  while ( v12 );
  v13 = v10 - 1;
  if ( v12 )
    v13 = v10;
  *v13 = 0;
  PathFindFileNameW(pszPath);
  if ( v5 || (*((_BYTE *)a2 + 10) & 2) != 0 )
  {
    v14 = pszPath;
    v15 = a3;
    do
    {
      if ( !v7 )
        break;
      if ( !*v14 )
        break;
      *v15++ = *v14++;
      --v7;
      --v9;
    }
    while ( v9 );
    v16 = v15 - 1;
    if ( v9 )
      v16 = v15;
    *v16 = 0;
  }
  else
  {
    _wsplitpath_s(pszPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
    StringCchCopyW(a3, 0x104u, Filename);
  }
  return a3;
}

```

## disassembly

```asm
0x180003f90  push    rbx
0x180003f92  push    rbp
0x180003f93  push    rsi
0x180003f94  push    rdi
0x180003f95  push    r14
0x180003f97  push    r15
0x180003f99  sub     rsp, 6A8h
0x180003fa0  mov     rax, cs:__security_cookie
0x180003fa7  xor     rax, rsp
0x180003faa  mov     [rsp+6D8h+var_48], rax
0x180003fb2  mov     rsi, rdx
0x180003fb5  lea     rcx, [rsp+6D8h+psfs]; psfs
0x180003fba  xor     r15d, r15d
0x180003fbd  mov     edx, 2; dwMask
0x180003fc2  mov     dword ptr [rsp+6D8h+psfs.fShowAllObjects], r15d
0x180003fc7  mov     r14, r8
0x180003fca  call    cs:__imp_SHGetSettings
0x180003fd0  mov     ebp, dword ptr [rsp+6D8h+psfs.fShowAllObjects]
0x180003fd4  shl     ebp, 1Eh
0x180003fd7  sar     ebp, 1Fh
0x180003fda  cmp     dword ptr [rsi+42h], 1
0x180003fde  jbe     loc_1800040A3
0x180003fe4  mov     eax, [rsi+3Eh]
0x180003fe7  lea     rax, ds:4Ah[rax*2]
0x180003fef  mov     ebx, 7FFFFFFEh
0x180003ff4  lea     rdx, [rax+rsi]
0x180003ff8  mov     edi, 104h
0x180003ffd  lea     r8, [rsp+6D8h+pszPath]
0x180004002  mov     ecx, ebx
0x180004004  mov     r9d, edi
0x180004007  test    rcx, rcx
0x18000400a  jz      short loc_180004029
0x18000400c  movzx   eax, word ptr [rdx]
0x18000400f  test    ax, ax
0x180004012  jz      short loc_180004029
0x180004014  mov     [r8], ax
0x180004018  add     rdx, 2
0x18000401c  add     r8, 2
0x180004020  dec     rcx
0x180004023  sub     r9, 1
0x180004027  jnz     short loc_180004007
0x180004029  test    r9, r9
0x18000402c  lea     rcx, [r8-2]
0x180004030  cmovnz  rcx, r8
0x180004034  mov     [rcx], r15w
0x180004038  lea     rcx, [rsp+6D8h+pszPath]; pszPath
0x18000403d  call    cs:__imp_PathFindFileNameW
0x180004043  test    ebp, ebp
0x180004045  jz      short loc_1800040AD
0x180004047  lea     rcx, [rsp+6D8h+pszPath]
0x18000404c  mov     rdx, r14
0x18000404f  nop
0x180004050  test    rbx, rbx
0x180004053  jz      short loc_180004071
0x180004055  movzx   eax, word ptr [rcx]
0x180004058  test    ax, ax
0x18000405b  jz      short loc_180004071
0x18000405d  mov     [rdx], ax
0x180004060  add     rcx, 2
0x180004064  add     rdx, 2
0x180004068  dec     rbx
0x18000406b  sub     rdi, 1
0x18000406f  jnz     short loc_180004050
0x180004071  test    rdi, rdi
0x180004074  lea     rcx, [rdx-2]
0x180004078  cmovnz  rcx, rdx
0x18000407c  mov     [rcx], r15w
0x180004080  mov     rax, r14
0x180004083  mov     rcx, [rsp+6D8h+var_48]
0x18000408b  xor     rcx, rsp; StackCookie
0x18000408e  call    __security_check_cookie
0x180004093  add     rsp, 6A8h
0x18000409a  pop     r15
0x18000409c  pop     r14
0x18000409e  pop     rdi
0x18000409f  pop     rsi
0x1800040a0  pop     rbp
0x1800040a1  pop     rbx
0x1800040a2  retn
0x1800040a3  mov     eax, 4Ah ; 'J'
0x1800040a8  jmp     loc_180003FEF
0x1800040ad  test    byte ptr [rsi+0Ah], 2
0x1800040b1  jnz     short loc_180004047
0x1800040b3  mov     [rsp+6D8h+ExtCount], rdi; ExtCount
0x1800040b8  lea     rax, [rsp+6D8h+var_258]
0x1800040c0  mov     [rsp+6D8h+Ext], rax; Ext
0x1800040c5  lea     rcx, [rsp+6D8h+pszPath]; FullPath
0x1800040ca  lea     rax, [rsp+6D8h+var_468]
0x1800040d2  mov     [rsp+6D8h+FilenameCount], rdi; FilenameCount
0x1800040d7  mov     [rsp+6D8h+Filename], rax; Filename
0x1800040dc  xor     r9d, r9d; Dir
0x1800040df  xor     r8d, r8d; DriveCount
0x1800040e2  mov     [rsp+6D8h+DirCount], r15; DirCount
0x1800040e7  xor     edx, edx; Drive
0x1800040e9  call    cs:__imp__wsplitpath_s
0x1800040ef  lea     r8, [rsp+6D8h+var_468]; unsigned __int16 *
0x1800040f7  mov     rdx, rdi; unsigned __int64
0x1800040fa  mov     rcx, r14; unsigned __int16 *
0x1800040fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004102  jmp     loc_180004080
```
