# CabWriter::FciFileOpen(char *,int,int,int *,void *)

- ea: `0x180069740`
- end: `0x18006992d`
- name: `?FciFileOpen@CabWriter@@CA_JPEADHHPEAHPEAX@Z`
- size: `493`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode, int *err, void *pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180069ec0`

## callees

- `0x1800358c0`
- `0x180068d1c`
- `0x180069740`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectory` at `0x180069817`
- `SHCORE!__imp_SHCreateDirectory` at `0x180069817`
- `SHLWAPI!PathFileExistsW` at `0x180069806`
- `SHLWAPI!PathFileExistsW` at `0x180069806`
- `SHLWAPI!StrRChrW` at `0x1800697ee`
- `SHLWAPI!StrRChrW` at `0x1800697ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006991f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006991f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800697d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800697d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006977a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006977a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069915`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069866`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800698fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069866`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800698fe`

## pseudocode

```c
_QWORD *__fastcall CabWriter::FciFileOpen(const char *pszFile, __int16 oflag, int pmode, DWORD *err, unsigned int *pv)
{
  _DWORD *v8; // rax
  unsigned __int64 v9; // r9
  __int64 v10; // rsi
  _QWORD *v11; // rdi
  int v12; // ebx
  PWSTR v13; // rax
  PWSTR v14; // r14
  int v15; // eax
  HANDLE v16; // rax
  LPVOID v17; // rax
  HANDLE FileW; // rax
  WCHAR String1[264]; // [rsp+40h] [rbp-248h] BYREF

  v8 = CoTaskMemAlloc(0x30u);
  v10 = -1;
  v11 = v8;
  if ( !v8 )
    goto LABEL_22;
  *v8 = 0;
  v12 = AnsiToUnicode(*pv, pszFile, String1, v9);
  if ( v12 < 0 )
    goto LABEL_21;
  if ( (oflag & 0x100) == 0 )
  {
    FileW = CreateFileW(String1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
    v11[4] = FileW;
    if ( FileW != (HANDLE)-1LL )
      return v11;
    goto LABEL_21;
  }
  if ( CompareStringOrdinal(String1, -1, "?", -1, 1) == 2 )
  {
    v17 = CoTaskMemAlloc(0x30D40u);
    v11[1] = v17;
    if ( !v17 )
      goto LABEL_21;
    v12 = 0;
    *(_DWORD *)v11 = 3;
    v11[2] = 0;
    *((_DWORD *)v11 + 6) = 200000;
  }
  else
  {
    v13 = StrRChrW(String1, 0, 0x5Cu);
    v14 = v13;
    if ( v13 )
    {
      *v13 = 0;
      if ( !PathFileExistsW(String1) )
      {
        v15 = SHCreateDirectory(0, String1);
        if ( !v15 || v15 == 183 )
          v12 = 0;
        else
          v12 = -2147467259;
      }
      *v14 = 92;
      if ( v12 < 0 )
        goto LABEL_21;
    }
    v16 = CreateFileW(String1, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v11[4] = v16;
    if ( v16 == (HANDLE)-1LL )
      v12 = -2147467259;
  }
  if ( v12 < 0 )
  {
LABEL_21:
    CoTaskMemFree(v11);
LABEL_22:
    *err = GetLastError();
    return (_QWORD *)v10;
  }
  return v11;
}

```

## disassembly

```asm
0x180069740  mov     [rsp+arg_8], rbx
0x180069745  push    rbp
0x180069746  push    rsi
0x180069747  push    rdi
0x180069748  push    r14
0x18006974a  push    r15
0x18006974c  sub     rsp, 260h
0x180069753  mov     rax, cs:__security_cookie
0x18006975a  xor     rax, rsp
0x18006975d  mov     [rsp+288h+var_38], rax
0x180069765  mov     rbx, [rsp+288h+pv]
0x18006976d  mov     r14, rcx
0x180069770  mov     ecx, 30h ; '0'; cb
0x180069775  mov     r15, r9
0x180069778  mov     ebp, edx
0x18006977a  call    cs:__imp_CoTaskMemAlloc
0x180069780  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180069784  mov     rdi, rax
0x180069787  test    rax, rax
0x18006978a  jz      loc_18006991F
0x180069790  mov     dword ptr [rax], 0
0x180069796  lea     r8, [rsp+288h+String1]; unsigned __int16 *
0x18006979b  mov     ecx, [rbx]; unsigned int
0x18006979d  mov     rdx, r14; char *
0x1800697a0  call    ?AnsiToUnicode@@YAJIPEBDPEAG_K@Z; AnsiToUnicode(uint,char const *,ushort *,unsigned __int64)
0x1800697a5  mov     ebx, eax
0x1800697a7  test    eax, eax
0x1800697a9  js      loc_180069912
0x1800697af  lea     rcx, [rsp+288h+String1]; lpFileName
0x1800697b4  bt      ebp, 8
0x1800697b8  jnb     loc_1800698D9
0x1800697be  mov     r9d, esi; cchCount2
0x1800697c1  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800697c9  lea     r8, asc_18007B88C; "?"
0x1800697d0  mov     edx, esi; cchCount1
0x1800697d2  call    cs:__imp_CompareStringOrdinal
0x1800697d8  cmp     eax, 2
0x1800697db  jz      loc_18006987C
0x1800697e1  lea     ebp, [rsi+5Dh]
0x1800697e4  xor     edx, edx; pszEnd
0x1800697e6  mov     r8d, ebp; wMatch
0x1800697e9  lea     rcx, [rsp+288h+String1]; pszStart
0x1800697ee  call    cs:__imp_StrRChrW
0x1800697f4  mov     r14, rax
0x1800697f7  test    rax, rax
0x1800697fa  jz      short loc_18006983D
0x1800697fc  xor     ecx, ecx
0x1800697fe  mov     [rax], cx
0x180069801  lea     rcx, [rsp+288h+String1]; pszPath
0x180069806  call    cs:__imp_PathFileExistsW
0x18006980c  test    eax, eax
0x18006980e  jnz     short loc_180069831
0x180069810  lea     rdx, [rsp+288h+String1]; pszPath
0x180069815  xor     ecx, ecx; hwnd
0x180069817  call    cs:__imp_SHCreateDirectory
0x18006981d  test    eax, eax
0x18006981f  jz      short loc_18006982F
0x180069821  cmp     eax, 0B7h
0x180069826  jz      short loc_18006982F
0x180069828  mov     ebx, 80004005h
0x18006982d  jmp     short loc_180069831
0x18006982f  xor     ebx, ebx
0x180069831  mov     [r14], bp
0x180069835  test    ebx, ebx
0x180069837  js      loc_180069912
0x18006983d  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180069846  lea     rcx, [rsp+288h+String1]; lpFileName
0x18006984b  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180069853  xor     r9d, r9d; lpSecurityAttributes
0x180069856  xor     r8d, r8d; dwShareMode
0x180069859  mov     [rsp+288h+bIgnoreCase], 2; dwCreationDisposition
0x180069861  mov     edx, 40000000h; dwDesiredAccess
0x180069866  call    cs:__imp_CreateFileW
0x18006986c  mov     [rdi+20h], rax
0x180069870  cmp     rax, rsi
0x180069873  jnz     short loc_1800698A1
0x180069875  mov     ebx, 80004005h
0x18006987a  jmp     short loc_1800698A1
0x18006987c  mov     ebp, 30D40h
0x180069881  mov     ecx, ebp; cb
0x180069883  call    cs:__imp_CoTaskMemAlloc
0x180069889  mov     [rdi+8], rax
0x18006988d  test    rax, rax
0x180069890  jz      short loc_1800698D2
0x180069892  xor     ebx, ebx
0x180069894  mov     dword ptr [rdi], 3
0x18006989a  mov     [rdi+10h], rbx
0x18006989e  mov     [rdi+18h], ebp
0x1800698a1  test    ebx, ebx
0x1800698a3  js      short loc_180069912
0x1800698a5  mov     rsi, rdi
0x1800698a8  mov     rax, rsi
0x1800698ab  mov     rcx, [rsp+288h+var_38]
0x1800698b3  xor     rcx, rsp; StackCookie
0x1800698b6  call    __security_check_cookie
0x1800698bb  mov     rbx, [rsp+288h+arg_8]
0x1800698c3  add     rsp, 260h
0x1800698ca  pop     r15
0x1800698cc  pop     r14
0x1800698ce  pop     rdi
0x1800698cf  pop     rsi
0x1800698d0  pop     rbp
0x1800698d1  retn
0x1800698d2  mov     ebx, 8007000Eh
0x1800698d7  jmp     short loc_180069912
0x1800698d9  xor     r9d, r9d; lpSecurityAttributes
0x1800698dc  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800698e5  mov     [rsp+288h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800698ed  mov     edx, 80000000h; dwDesiredAccess
0x1800698f2  mov     [rsp+288h+bIgnoreCase], 3; dwCreationDisposition
0x1800698fa  lea     r8d, [r9+1]; dwShareMode
0x1800698fe  call    cs:__imp_CreateFileW
0x180069904  mov     [rdi+20h], rax
0x180069908  cmp     rax, rsi
0x18006990b  jnz     short loc_1800698A5
0x18006990d  mov     ebx, 80004005h
0x180069912  mov     rcx, rdi; pv
0x180069915  call    cs:__imp_CoTaskMemFree
0x18006991b  test    ebx, ebx
0x18006991d  jns     short loc_1800698A5
0x18006991f  call    cs:__imp_GetLastError
0x180069925  mov     [r15], eax
0x180069928  jmp     loc_1800698A8
```
