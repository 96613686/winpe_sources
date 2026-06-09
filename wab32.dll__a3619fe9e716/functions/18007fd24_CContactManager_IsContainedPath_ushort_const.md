# CContactManager::_IsContainedPath(ushort const *)

- ea: `0x18007fd24`
- end: `0x18007ff00`
- name: `?_IsContainedPath@CContactManager@@AEAAHPEBG@Z`
- size: `476`
- prototype: `__int64 __fastcall(CContactManager *__hidden this, wchar_t *Path)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x18007fa4c`
- `0x1800805ec`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x18007fcdc`
- `0x18007fd24`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `msvcrt!_wfullpath` at `0x18007fdd8`
- `msvcrt!_wfullpath` at `0x18007fe02`
- `msvcrt!_wfullpath` at `0x18007fdd8`
- `msvcrt!_wfullpath` at `0x18007fe02`
- `SHLWAPI!PathCanonicalizeW` at `0x18007fe7a`
- `SHLWAPI!PathCanonicalizeW` at `0x18007fe7a`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18007fe8b`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18007fe8b`
- `SHLWAPI!StrCmpIW` at `0x18007fea1`
- `SHLWAPI!StrCmpIW` at `0x18007fea1`
- `SHLWAPI!StrCmpNIW` at `0x18007fe60`
- `SHLWAPI!StrCmpNIW` at `0x18007fe60`
- `SHLWAPI!PathRemoveBackslashW` at `0x18007fdec`
- `SHLWAPI!PathRemoveBackslashW` at `0x18007fdec`
- `KERNEL32!GetCurrentThreadId` at `0x18007fd9f`
- `KERNEL32!GetCurrentThreadId` at `0x18007fd9f`
- `KERNEL32!GetFileAttributesW` at `0x18007fe18`
- `KERNEL32!GetFileAttributesW` at `0x18007feb2`
- `KERNEL32!GetFileAttributesW` at `0x18007fe18`
- `KERNEL32!GetFileAttributesW` at `0x18007feb2`

## pseudocode

```c
__int64 __fastcall CContactManager::_IsContainedPath(CContactManager *this, wchar_t *Path)
{
  wchar_t *v4; // rdx
  DWORD v5; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  DWORD FileAttributesW; // eax
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *Patha; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t FileName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszBuf[264]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v15[264]; // [rsp+670h] [rbp+570h] BYREF

  STRW::STRW((STRW *)&v10, v15, 0x104u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(pszBuf, 0, 0x208u);
  GetCurrentThreadId();
  if ( CContactManager::_GetWorkingDirectory(this, (struct STRW *)&v10) < 0 )
    goto LABEL_20;
  v4 = (wchar_t *)&Str;
  if ( v10 )
    v4 = Patha;
  if ( !_wfullpath(Buffer, v4, 0x104u)
    || (PathRemoveBackslashW(Buffer), !_wfullpath(FileName, Path, 0x104u))
    || (v5 = GetFileAttributesW(FileName), v5 == -1)
    || (v5 & 0x10) != 0
    || (v5 & 2) != 0
    || (v5 & 4) != 0 )
  {
LABEL_20:
    v7 = 0;
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( Buffer[v6] );
    v7 = 0;
    if ( !StrCmpNIW(FileName, Buffer, v6) && PathCanonicalizeW(pszBuf, FileName) )
    {
      while ( PathRemoveFileSpecW(pszBuf) )
      {
        if ( !StrCmpIW(pszBuf, Buffer) )
        {
          v7 = 1;
          break;
        }
        FileAttributesW = GetFileAttributesW(pszBuf);
        if ( FileAttributesW == -1 || (FileAttributesW & 6) == 6 )
          break;
      }
    }
  }
  v10 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&Patha);
  return v7;
}

```

## disassembly

```asm
0x18007fd24  mov     [rsp-8+arg_10], rbx
0x18007fd29  push    rbp
0x18007fd2a  push    rsi
0x18007fd2b  push    rdi
0x18007fd2c  lea     rbp, [rsp-790h]
0x18007fd34  sub     rsp, 890h
0x18007fd3b  mov     rax, cs:__security_cookie
0x18007fd42  xor     rax, rsp
0x18007fd45  mov     [rbp+7A0h+var_20], rax
0x18007fd4c  mov     rbx, rcx
0x18007fd4f  mov     rdi, rdx
0x18007fd52  lea     rdx, [rbp+7A0h+var_230]; unsigned __int16 *
0x18007fd59  mov     r8d, 104h; unsigned int
0x18007fd5f  lea     rcx, [rsp+8A0h+var_880]; this
0x18007fd64  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007fd69  mov     esi, 208h
0x18007fd6e  lea     rcx, [rsp+8A0h+Buffer]; void *
0x18007fd73  mov     r8d, esi; Size
0x18007fd76  xor     edx, edx; Val
0x18007fd78  call    memset_0
0x18007fd7d  mov     r8d, esi; Size
0x18007fd80  lea     rcx, [rbp+7A0h+FileName]; void *
0x18007fd87  xor     edx, edx; Val
0x18007fd89  call    memset_0
0x18007fd8e  mov     r8d, esi; Size
0x18007fd91  lea     rcx, [rbp+7A0h+pszBuf]; void *
0x18007fd98  xor     edx, edx; Val
0x18007fd9a  call    memset_0
0x18007fd9f  call    cs:__imp_GetCurrentThreadId
0x18007fda5  lea     rdx, [rsp+8A0h+var_880]; struct STRW *
0x18007fdaa  mov     rcx, rbx; this
0x18007fdad  call    ?_GetWorkingDirectory@CContactManager@@AEAAJPEAVSTRW@@@Z; CContactManager::_GetWorkingDirectory(STRW *)
0x18007fdb2  xor     esi, esi
0x18007fdb4  test    eax, eax
0x18007fdb6  js      loc_18007FECC
0x18007fdbc  cmp     [rsp+8A0h+var_880], esi
0x18007fdc0  lea     rdx, Str
0x18007fdc7  mov     r8d, 104h; BufferCount
0x18007fdcd  lea     rcx, [rsp+8A0h+Buffer]; Buffer
0x18007fdd2  cmovnz  rdx, [rsp+8A0h+Path]; Path
0x18007fdd8  call    cs:__imp__wfullpath
0x18007fdde  test    rax, rax
0x18007fde1  jz      loc_18007FECC
0x18007fde7  lea     rcx, [rsp+8A0h+Buffer]; pszPath
0x18007fdec  call    cs:__imp_PathRemoveBackslashW
0x18007fdf2  mov     r8d, 104h; BufferCount
0x18007fdf8  lea     rcx, [rbp+7A0h+FileName]; Buffer
0x18007fdff  mov     rdx, rdi; Path
0x18007fe02  call    cs:__imp__wfullpath
0x18007fe08  test    rax, rax
0x18007fe0b  jz      loc_18007FECC
0x18007fe11  lea     rcx, [rbp+7A0h+FileName]; lpFileName
0x18007fe18  call    cs:__imp_GetFileAttributesW
0x18007fe1e  or      edi, 0FFFFFFFFh
0x18007fe21  cmp     eax, edi
0x18007fe23  jz      loc_18007FECC
0x18007fe29  test    al, 10h
0x18007fe2b  jnz     loc_18007FECC
0x18007fe31  test    al, 2
0x18007fe33  jnz     loc_18007FECC
0x18007fe39  test    al, 4
0x18007fe3b  jnz     loc_18007FECC
0x18007fe41  lea     rax, [rsp+8A0h+Buffer]
0x18007fe46  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007fe4a  inc     r8; nChar
0x18007fe4d  cmp     [rax+r8*2], si
0x18007fe52  jnz     short loc_18007FE4A
0x18007fe54  lea     rdx, [rsp+8A0h+Buffer]; psz2
0x18007fe59  lea     rcx, [rbp+7A0h+FileName]; psz1
0x18007fe60  call    cs:__imp_StrCmpNIW
0x18007fe66  mov     ebx, esi
0x18007fe68  test    eax, eax
0x18007fe6a  jnz     short loc_18007FECE
0x18007fe6c  lea     rdx, [rbp+7A0h+FileName]; pszPath
0x18007fe73  lea     rcx, [rbp+7A0h+pszBuf]; pszBuf
0x18007fe7a  call    cs:__imp_PathCanonicalizeW
0x18007fe80  test    eax, eax
0x18007fe82  jz      short loc_18007FECE
0x18007fe84  lea     rcx, [rbp+7A0h+pszBuf]; pszPath
0x18007fe8b  call    cs:__imp_PathRemoveFileSpecW
0x18007fe91  test    eax, eax
0x18007fe93  jz      short loc_18007FECE
0x18007fe95  lea     rdx, [rsp+8A0h+Buffer]; psz2
0x18007fe9a  lea     rcx, [rbp+7A0h+pszBuf]; psz1
0x18007fea1  call    cs:__imp_StrCmpIW
0x18007fea7  test    eax, eax
0x18007fea9  jz      short loc_18007FEC5
0x18007feab  lea     rcx, [rbp+7A0h+pszBuf]; lpFileName
0x18007feb2  call    cs:__imp_GetFileAttributesW
0x18007feb8  cmp     eax, edi
0x18007feba  jz      short loc_18007FECE
0x18007febc  and     eax, 6
0x18007febf  cmp     al, 6
0x18007fec1  jnz     short loc_18007FE84
0x18007fec3  jmp     short loc_18007FECE
0x18007fec5  mov     ebx, 1
0x18007feca  jmp     short loc_18007FECE
0x18007fecc  mov     ebx, esi
0x18007fece  lea     rcx, [rsp+8A0h+Path]; this
0x18007fed3  mov     [rsp+8A0h+var_880], esi
0x18007fed7  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007fedc  mov     eax, ebx
0x18007fede  mov     rcx, [rbp+7A0h+var_20]
0x18007fee5  xor     rcx, rsp; StackCookie
0x18007fee8  call    __security_check_cookie
0x18007feed  mov     rbx, [rsp+8A0h+arg_10]
0x18007fef5  add     rsp, 890h
0x18007fefc  pop     rdi
0x18007fefd  pop     rsi
0x18007fefe  pop     rbp
0x18007feff  retn
```
