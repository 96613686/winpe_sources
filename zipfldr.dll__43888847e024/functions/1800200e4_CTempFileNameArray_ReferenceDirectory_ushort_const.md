# CTempFileNameArray::ReferenceDirectory(ushort const *)

- ea: `0x1800200e4`
- end: `0x180020246`
- name: `?ReferenceDirectory@CTempFileNameArray@@QEAAXPEBG@Z`
- size: `354`
- prototype: `void __fastcall(CTempFileNameArray *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18001ea30`
- `0x1800200e4`
- `0x180059000`

## callees

- `0x180010c30`
- `0x1800200e4`
- `0x18002024c`
- `0x180027c6c`
- `0x180028c2c`
- `0x180036f50`
- `0x180037958`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180020175`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800201d7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180020175`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800201d7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020199`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020199`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020202`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020202`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002020f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002020f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CTempFileNameArray::ReferenceDirectory(CTempFileNameArray *this, const unsigned __int16 *a2)
{
  WCHAR *v2; // rax
  const unsigned __int16 *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  HANDLE FirstFileW; // rsi
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR v11[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPath[264]; // [rsp+480h] [rbp+380h] BYREF

  v2 = pszPath;
  v5 = a2;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v5 )
      break;
    *v2++ = *v5++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v2 - 1;
  if ( v7 )
    v8 = v2;
  *v8 = 0;
  PathCchAppend(pszPath, 0x104u, L"*.*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(pszPath, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( !(unsigned int)PathIsDotOrDotDotW(FindFileData.cFileName) )
      {
        StringCchCopyW(v11, 0x104u, a2);
        PathCchAppend(v11, 0x104u, FindFileData.cFileName);
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          CTempFileNameArray::ReferenceDirectory(this, v11);
        else
          CTempFileNameArray::_AddFile(this, v11);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
  }
  CTempFileNameArray::_AddDir(this, a2);
}

```

## disassembly

```asm
0x1800200e4  mov     [rsp-8+arg_10], rbx
0x1800200e9  push    rbp
0x1800200ea  push    rsi
0x1800200eb  push    rdi
0x1800200ec  push    r14
0x1800200ee  push    r15
0x1800200f0  lea     rbp, [rsp-5A0h]
0x1800200f8  sub     rsp, 6A0h
0x1800200ff  mov     rax, cs:__security_cookie
0x180020106  xor     rax, rsp
0x180020109  mov     [rbp+5C0h+var_30], rax
0x180020110  mov     r15d, 104h
0x180020116  lea     rax, [rbp+5C0h+pszPath]
0x18002011d  mov     rdi, rdx
0x180020120  mov     rbx, rcx
0x180020123  mov     r8, rdx
0x180020126  mov     ecx, 7FFFFFFEh
0x18002012b  mov     edx, r15d
0x18002012e  xor     r14d, r14d
0x180020131  test    rcx, rcx
0x180020134  jz      short loc_180020155
0x180020136  movzx   r9d, word ptr [r8]
0x18002013a  test    r9w, r9w
0x18002013e  jz      short loc_180020155
0x180020140  mov     [rax], r9w
0x180020144  add     r8, 2
0x180020148  add     rax, 2
0x18002014c  dec     rcx
0x18002014f  sub     rdx, 1
0x180020153  jnz     short loc_180020131
0x180020155  test    rdx, rdx
0x180020158  lea     rcx, [rax-2]
0x18002015c  lea     r8, pszMore; "*.*"
0x180020163  mov     rdx, r15; cchPath
0x180020166  cmovnz  rcx, rax
0x18002016a  mov     [rcx], r14w
0x18002016e  lea     rcx, [rbp+5C0h+pszPath]; pszPath
0x180020175  call    cs:__imp_PathCchAppend
0x18002017b  xor     edx, edx; Val
0x18002017d  lea     rcx, [rsp+6C0h+FindFileData]; void *
0x180020182  mov     r8d, 250h; Size
0x180020188  call    memset_0
0x18002018d  lea     rdx, [rsp+6C0h+FindFileData]; lpFindFileData
0x180020192  lea     rcx, [rbp+5C0h+pszPath]; lpFileName
0x180020199  call    cs:__imp_FindFirstFileW
0x18002019f  mov     rsi, rax
0x1800201a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800201a6  jz      short loc_180020215
0x1800201a8  lea     rcx, [rsp+6C0h+FindFileData.cFileName]; unsigned __int16 *
0x1800201ad  call    ?PathIsDotOrDotDotW@@YAHPEBG@Z; PathIsDotOrDotDotW(ushort const *)
0x1800201b2  test    eax, eax
0x1800201b4  jnz     short loc_1800201FA
0x1800201b6  mov     r8, rdi; unsigned __int16 *
0x1800201b9  lea     rcx, [rbp+5C0h+var_450]; unsigned __int16 *
0x1800201c0  mov     rdx, r15; unsigned __int64
0x1800201c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800201c8  lea     r8, [rsp+6C0h+FindFileData.cFileName]; pszMore
0x1800201cd  mov     rdx, r15; cchPath
0x1800201d0  lea     rcx, [rbp+5C0h+var_450]; pszPath
0x1800201d7  call    cs:__imp_PathCchAppend
0x1800201dd  test    byte ptr [rsp+6C0h+FindFileData.dwFileAttributes], 10h
0x1800201e2  lea     rdx, [rbp+5C0h+var_450]; unsigned __int16 *
0x1800201e9  mov     rcx, rbx; this
0x1800201ec  jz      short loc_1800201F5
0x1800201ee  call    ?ReferenceDirectory@CTempFileNameArray@@QEAAXPEBG@Z; CTempFileNameArray::ReferenceDirectory(ushort const *)
0x1800201f3  jmp     short loc_1800201FA
0x1800201f5  call    ?_AddFile@CTempFileNameArray@@AEAAJPEBG@Z; CTempFileNameArray::_AddFile(ushort const *)
0x1800201fa  lea     rdx, [rsp+6C0h+FindFileData]; lpFindFileData
0x1800201ff  mov     rcx, rsi; hFindFile
0x180020202  call    cs:__imp_FindNextFileW
0x180020208  test    eax, eax
0x18002020a  jnz     short loc_1800201A8
0x18002020c  mov     rcx, rsi; hFindFile
0x18002020f  call    cs:__imp_FindClose
0x180020215  mov     rdx, rdi; unsigned __int16 *
0x180020218  mov     rcx, rbx; this
0x18002021b  call    ?_AddDir@CTempFileNameArray@@AEAAJPEBG@Z; CTempFileNameArray::_AddDir(ushort const *)
0x180020220  mov     rcx, [rbp+5C0h+var_30]
0x180020227  xor     rcx, rsp; StackCookie
0x18002022a  call    __security_check_cookie
0x18002022f  mov     rbx, [rsp+6C0h+arg_10]
0x180020237  add     rsp, 6A0h
0x18002023e  pop     r15
0x180020240  pop     r14
0x180020242  pop     rdi
0x180020243  pop     rsi
0x180020244  pop     rbp
0x180020245  retn
```
