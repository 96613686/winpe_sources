# CFileListener::CreateInstance(IFileChangeNotify *,ushort const *,ulong,IChangeListener * *)

- ea: `0x18009038c`
- end: `0x18009057d`
- name: `?CreateInstance@CFileListener@@SAJPEAUIFileChangeNotify@@PEBGKPEAPEAUIChangeListener@@@Z`
- size: `497`
- prototype: `static int(struct IFileChangeNotify *, const unsigned __int16 *, unsigned int, struct IChangeListener **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180085ed0`

## callees

- `0x18000161c`
- `0x1800045e4`
- `0x180009aec`
- `0x18008fc7c`
- `0x180090058`
- `0x18009038c`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x1800904e6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800904e6`
- `SHLWAPI!PathFindFileNameW` at `0x1800904bc`
- `SHLWAPI!PathFindFileNameW` at `0x1800904bc`
- `SHLWAPI!PathCombineW` at `0x180090495`
- `SHLWAPI!PathCombineW` at `0x180090495`
- `SHELL32!__imp_PathResolve` at `0x180090433`
- `SHELL32!__imp_PathResolve` at `0x180090433`
- `KERNEL32!GetCurrentDirectoryW` at `0x18009045f`
- `KERNEL32!GetCurrentDirectoryW` at `0x18009045f`
- `KERNEL32!GetLastError` at `0x1800904a0`
- `KERNEL32!GetLastError` at `0x1800904a0`

## pseudocode

```c
__int64 __fastcall CFileListener::CreateInstance(
        struct IFileChangeNotify *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        struct IChangeListener **a4)
{
  CFileListener *v7; // rax
  CFileListener *v8; // rax
  CFileListener *v9; // rbx
  signed int DirectoryListener; // edi
  signed int LastError; // eax
  WCHAR *FileNameW; // rax
  const unsigned __int16 *v13; // rdx
  WCHAR pszPath[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-238h] BYREF

  *a4 = 0;
  memset_0(pszPath, 0, 0x208u);
  v7 = (CFileListener *)operator new(0x6C0u);
  if ( !v7 )
    return (unsigned int)-2147024882;
  v8 = CFileListener::CFileListener(v7);
  if ( (v9 = v8) == 0 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v8 + 6) = a1;
  DirectoryListener = STRW::Append((CFileListener *)((char *)v8 + 1696), a2);
  if ( DirectoryListener < 0 )
    goto LABEL_8;
  DirectoryListener = StringCchCopyW(pszPath, 0x104u, a2);
  if ( DirectoryListener < 0 )
    goto LABEL_8;
  if ( !PathResolve(pszPath, 0, 1u) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetCurrentDirectoryW(0x104u, Buffer) > 0x104 )
    {
LABEL_7:
      DirectoryListener = -2147467259;
      goto LABEL_8;
    }
    if ( !PathCombineW(pszPath, Buffer, a2) )
    {
      LastError = GetLastError();
      DirectoryListener = LastError;
      if ( LastError > 0 )
        DirectoryListener = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_8;
    }
  }
  FileNameW = PathFindFileNameW(pszPath);
  if ( pszPath == FileNameW )
    goto LABEL_7;
  DirectoryListener = STRW::Append((CFileListener *)((char *)v9 + 1144), FileNameW);
  if ( DirectoryListener < 0 )
    goto LABEL_8;
  if ( !PathRemoveFileSpecW(pszPath) )
    goto LABEL_7;
  DirectoryListener = STRW::Append((CFileListener *)((char *)v9 + 592), pszPath);
  if ( DirectoryListener >= 0 )
  {
    v13 = &Str;
    if ( *((_DWORD *)v9 + 148) )
      v13 = (const unsigned __int16 *)*((_QWORD *)v9 + 75);
    DirectoryListener = CreateDirectoryListener(
                          (CFileListener *)((char *)v9 + 40),
                          v13,
                          0xFFFu,
                          0,
                          (struct IChangeListener **)v9 + 7);
    if ( DirectoryListener >= 0 )
    {
      DirectoryListener = 0;
      *a4 = (CFileListener *)((char *)v9 + 32);
      return (unsigned int)DirectoryListener;
    }
  }
LABEL_8:
  (*(void (__fastcall **)(CFileListener *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)DirectoryListener;
}

```

## disassembly

```asm
0x18009038c  mov     [rsp+arg_0], rbx
0x180090391  push    rsi
0x180090392  push    rdi
0x180090393  push    r14
0x180090395  sub     rsp, 460h
0x18009039c  mov     rax, cs:__security_cookie
0x1800903a3  xor     rax, rsp
0x1800903a6  mov     [rsp+478h+var_28], rax
0x1800903ae  mov     rsi, rdx
0x1800903b1  mov     qword ptr [r9], 0
0x1800903b8  mov     rdi, rcx
0x1800903bb  xor     edx, edx; Val
0x1800903bd  lea     rcx, [rsp+478h+pszPath]; void *
0x1800903c2  mov     r8d, 208h; Size
0x1800903c8  mov     r14, r9
0x1800903cb  call    memset_0
0x1800903d0  mov     ecx, 6C0h; Size
0x1800903d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800903da  test    rax, rax
0x1800903dd  jz      loc_180090552
0x1800903e3  mov     rcx, rax; this
0x1800903e6  call    ??0CFileListener@@AEAA@XZ; CFileListener::CFileListener(void)
0x1800903eb  mov     rbx, rax
0x1800903ee  test    rax, rax
0x1800903f1  jz      loc_180090552
0x1800903f7  lea     rcx, [rax+6A0h]; this
0x1800903fe  mov     [rax+30h], rdi
0x180090402  mov     rdx, rsi; unsigned __int16 *
0x180090405  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18009040a  mov     edi, eax
0x18009040c  test    eax, eax
0x18009040e  js      short loc_180090471
0x180090410  mov     r8, rsi; unsigned __int16 *
0x180090413  lea     rcx, [rsp+478h+pszPath]; unsigned __int16 *
0x180090418  mov     edx, 104h; unsigned __int64
0x18009041d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180090422  mov     edi, eax
0x180090424  test    eax, eax
0x180090426  js      short loc_180090471
0x180090428  xor     edx, edx; dirs
0x18009042a  lea     rcx, [rsp+478h+pszPath]; pszPath
0x18009042f  lea     r8d, [rdx+1]; fFlags
0x180090433  call    cs:__imp_PathResolve
0x180090439  test    eax, eax
0x18009043b  jnz     short loc_1800904B7
0x18009043d  xor     edx, edx; Val
0x18009043f  lea     rcx, [rsp+478h+Buffer]; void *
0x180090447  mov     r8d, 208h; Size
0x18009044d  call    memset_0
0x180090452  lea     rdx, [rsp+478h+Buffer]; lpBuffer
0x18009045a  mov     ecx, 104h; nBufferLength
0x18009045f  call    cs:__imp_GetCurrentDirectoryW
0x180090465  cmp     eax, 104h
0x18009046a  jbe     short loc_180090485
0x18009046c  mov     edi, 80004005h
0x180090471  mov     rax, [rbx]
0x180090474  mov     rcx, rbx
0x180090477  mov     rax, [rax+10h]
0x18009047b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090480  jmp     loc_180090557
0x180090485  mov     r8, rsi; pszFile
0x180090488  lea     rdx, [rsp+478h+Buffer]; pszDir
0x180090490  lea     rcx, [rsp+478h+pszPath]; pszDest
0x180090495  call    cs:__imp_PathCombineW
0x18009049b  test    rax, rax
0x18009049e  jnz     short loc_1800904B7
0x1800904a0  call    cs:__imp_GetLastError
0x1800904a6  mov     edi, eax
0x1800904a8  test    eax, eax
0x1800904aa  jle     short loc_180090471
0x1800904ac  movzx   edi, ax
0x1800904af  or      edi, 80070000h
0x1800904b5  jmp     short loc_180090471
0x1800904b7  lea     rcx, [rsp+478h+pszPath]; pszPath
0x1800904bc  call    cs:__imp_PathFindFileNameW
0x1800904c2  lea     rcx, [rsp+478h+pszPath]
0x1800904c7  cmp     rcx, rax
0x1800904ca  jz      short loc_18009046C
0x1800904cc  lea     rcx, [rbx+478h]; this
0x1800904d3  mov     rdx, rax; unsigned __int16 *
0x1800904d6  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x1800904db  mov     edi, eax
0x1800904dd  test    eax, eax
0x1800904df  js      short loc_180090471
0x1800904e1  lea     rcx, [rsp+478h+pszPath]; pszPath
0x1800904e6  call    cs:__imp_PathRemoveFileSpecW
0x1800904ec  test    eax, eax
0x1800904ee  jz      loc_18009046C
0x1800904f4  lea     rsi, [rbx+250h]
0x1800904fb  mov     rcx, rsi; this
0x1800904fe  lea     rdx, [rsp+478h+pszPath]; unsigned __int16 *
0x180090503  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180090508  mov     edi, eax
0x18009050a  test    eax, eax
0x18009050c  js      loc_180090471
0x180090512  cmp     dword ptr [rsi], 0
0x180090515  lea     rdx, Str
0x18009051c  jz      short loc_180090522
0x18009051e  mov     rdx, [rsi+8]; unsigned __int16 *
0x180090522  lea     rax, [rbx+38h]
0x180090526  xor     r9d, r9d; int
0x180090529  lea     rcx, [rbx+28h]; struct IDirectoryChangeNotify *
0x18009052d  mov     [rsp+478h+var_458], rax; struct IChangeListener **
0x180090532  mov     r8d, 0FFFh; unsigned int
0x180090538  call    ?CreateDirectoryListener@@YAJPEAUIDirectoryChangeNotify@@PEBGKHPEAPEAUIChangeListener@@@Z; CreateDirectoryListener(IDirectoryChangeNotify *,ushort const *,ulong,int,IChangeListener * *)
0x18009053d  mov     edi, eax
0x18009053f  test    eax, eax
0x180090541  js      loc_180090471
0x180090547  lea     rax, [rbx+20h]
0x18009054b  xor     edi, edi
0x18009054d  mov     [r14], rax
0x180090550  jmp     short loc_180090557
0x180090552  mov     edi, 8007000Eh
0x180090557  mov     eax, edi
0x180090559  mov     rcx, [rsp+478h+var_28]
0x180090561  xor     rcx, rsp; StackCookie
0x180090564  call    __security_check_cookie
0x180090569  mov     rbx, [rsp+478h+arg_0]
0x180090571  add     rsp, 460h
0x180090578  pop     r14
0x18009057a  pop     rdi
0x18009057b  pop     rsi
0x18009057c  retn
```
