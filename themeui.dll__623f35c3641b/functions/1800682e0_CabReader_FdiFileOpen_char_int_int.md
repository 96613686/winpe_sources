# CabReader::FdiFileOpen(char *,int,int)

- ea: `0x1800682e0`
- end: `0x180068499`
- name: `?FdiFileOpen@CabReader@@CA_JPEADHH@Z`
- size: `441`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180067e40`
- `0x180067fb0`
- `0x180068804`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x1800682e0`
- `0x180068d1c`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectory` at `0x1800683aa`
- `SHCORE!__imp_SHCreateDirectory` at `0x1800683aa`
- `SHLWAPI!PathFileExistsW` at `0x180068399`
- `SHLWAPI!PathFileExistsW` at `0x180068399`
- `SHLWAPI!StrRChrW` at `0x180068381`
- `SHLWAPI!StrRChrW` at `0x180068381`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068362`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800683ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800683ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006846b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006846b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006844d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006844d`

## pseudocode

```c
INT_PTR __fastcall CabReader::FdiFileOpen(const char *pszFile, __int16 oflag, int pmode)
{
  _DWORD *v5; // rax
  unsigned __int64 v6; // r9
  _DWORD *v7; // rdi
  int v8; // ebx
  PWSTR v9; // rax
  PWSTR v10; // rsi
  int v11; // eax
  HANDLE FileW; // rax
  LPVOID v13; // rax
  int Error; // ebx
  WCHAR String1[264]; // [rsp+40h] [rbp-248h] BYREF

  v5 = CoTaskMemAlloc(0x30u);
  v7 = v5;
  if ( !v5 )
    return -1;
  *v5 = 0;
  v8 = AnsiToUnicode(0xFDE9u, pszFile, String1, v6);
  if ( v8 < 0 )
  {
LABEL_20:
    CoTaskMemFree(v7);
    return -1;
  }
  if ( (oflag & 0x100) != 0 )
  {
    if ( CompareStringOrdinal(String1, -1, L"?", -1, 1) == 2 )
    {
      v13 = CoTaskMemAlloc(0x30D40u);
      *((_QWORD *)v7 + 1) = v13;
      if ( !v13 )
        goto LABEL_20;
      Error = 0;
      *v7 = 3;
      *((_QWORD *)v7 + 2) = 0;
      v7[6] = 200000;
      goto LABEL_19;
    }
    v9 = StrRChrW(String1, 0, 0x5Cu);
    v10 = v9;
    if ( v9 )
    {
      *v9 = 0;
      if ( !PathFileExistsW(String1) )
      {
        v11 = SHCreateDirectory(0, String1);
        if ( !v11 || v11 == 183 )
          v8 = 0;
        else
          v8 = -2147467259;
      }
      *v10 = 92;
      if ( v8 < 0 )
        goto LABEL_20;
    }
    FileW = CreateFileW(String1, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  }
  else
  {
    FileW = CreateFileW(String1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  }
  *((_QWORD *)v7 + 4) = FileW;
  if ( FileW != (HANDLE)-1LL )
    return (INT_PTR)v7;
  Error = ResultFromKnownLastError();
LABEL_19:
  if ( Error < 0 )
    goto LABEL_20;
  return (INT_PTR)v7;
}

```

## disassembly

```asm
0x1800682e0  push    rbx
0x1800682e2  push    rsi
0x1800682e3  push    rdi
0x1800682e4  push    r15
0x1800682e6  sub     rsp, 268h
0x1800682ed  mov     rax, cs:__security_cookie
0x1800682f4  xor     rax, rsp
0x1800682f7  mov     [rsp+288h+var_38], rax
0x1800682ff  mov     rbx, rcx
0x180068302  mov     esi, edx
0x180068304  mov     ecx, 30h ; '0'; cb
0x180068309  call    cs:__imp_CoTaskMemAlloc
0x18006830f  mov     rdi, rax
0x180068312  test    rax, rax
0x180068315  jz      loc_180068475
0x18006831b  lea     r8, [rsp+288h+String1]; unsigned __int16 *
0x180068320  mov     dword ptr [rax], 0
0x180068326  mov     rdx, rbx; char *
0x180068329  mov     ecx, 0FDE9h; unsigned int
0x18006832e  call    ?AnsiToUnicode@@YAJIPEBDPEAG_K@Z; AnsiToUnicode(uint,char const *,ushort *,unsigned __int64)
0x180068333  mov     ebx, eax
0x180068335  test    eax, eax
0x180068337  js      loc_180068468
0x18006833d  lea     rcx, [rsp+288h+String1]; lpFileName
0x180068342  bt      esi, 8
0x180068346  jnb     loc_180068426
0x18006834c  or      r9d, 0FFFFFFFFh; cchCount2
0x180068350  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180068358  or      edx, r9d; cchCount1
0x18006835b  lea     r8, asc_18007B830; "?"
0x180068362  call    cs:__imp_CompareStringOrdinal
0x180068368  cmp     eax, 2
0x18006836b  jz      loc_1800683F8
0x180068371  mov     r15d, 5Ch ; '\'
0x180068377  lea     rcx, [rsp+288h+String1]; pszStart
0x18006837c  mov     r8d, r15d; wMatch
0x18006837f  xor     edx, edx; pszEnd
0x180068381  call    cs:__imp_StrRChrW
0x180068387  mov     rsi, rax
0x18006838a  test    rax, rax
0x18006838d  jz      short loc_1800683D0
0x18006838f  xor     ecx, ecx
0x180068391  mov     [rax], cx
0x180068394  lea     rcx, [rsp+288h+String1]; pszPath
0x180068399  call    cs:__imp_PathFileExistsW
0x18006839f  test    eax, eax
0x1800683a1  jnz     short loc_1800683C4
0x1800683a3  lea     rdx, [rsp+288h+String1]; pszPath
0x1800683a8  xor     ecx, ecx; hwnd
0x1800683aa  call    cs:__imp_SHCreateDirectory
0x1800683b0  test    eax, eax
0x1800683b2  jz      short loc_1800683C2
0x1800683b4  cmp     eax, 0B7h
0x1800683b9  jz      short loc_1800683C2
0x1800683bb  mov     ebx, 80004005h
0x1800683c0  jmp     short loc_1800683C4
0x1800683c2  xor     ebx, ebx
0x1800683c4  mov     [rsi], r15w
0x1800683c8  test    ebx, ebx
0x1800683ca  js      loc_180068468
0x1800683d0  mov     [rsp+288h+hTemplateFile], 0
0x1800683d9  lea     rcx, [rsp+288h+String1]
0x1800683de  mov     [rsp+288h+dwFlagsAndAttributes], 80h
0x1800683e6  xor     r8d, r8d
0x1800683e9  mov     [rsp+288h+bIgnoreCase], 2
0x1800683f1  mov     edx, 40000000h
0x1800683f6  jmp     short loc_18006844A
0x1800683f8  mov     esi, 30D40h
0x1800683fd  mov     ecx, esi; cb
0x1800683ff  call    cs:__imp_CoTaskMemAlloc
0x180068405  mov     [rdi+8], rax
0x180068409  test    rax, rax
0x18006840c  jz      short loc_18006841F
0x18006840e  xor     ebx, ebx
0x180068410  mov     dword ptr [rdi], 3
0x180068416  mov     [rdi+10h], rbx
0x18006841a  mov     [rdi+18h], esi
0x18006841d  jmp     short loc_180068464
0x18006841f  mov     ebx, 8007000Eh
0x180068424  jmp     short loc_180068468
0x180068426  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18006842f  mov     edx, 80000000h; dwDesiredAccess
0x180068434  mov     [rsp+288h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18006843c  mov     r8d, 1; dwShareMode
0x180068442  mov     [rsp+288h+bIgnoreCase], 3; dwCreationDisposition
0x18006844a  xor     r9d, r9d; lpSecurityAttributes
0x18006844d  call    cs:__imp_CreateFileW
0x180068453  mov     [rdi+20h], rax
0x180068457  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006845b  jnz     short loc_180068479
0x18006845d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068462  mov     ebx, eax
0x180068464  test    ebx, ebx
0x180068466  jns     short loc_180068479
0x180068468  mov     rcx, rdi; pv
0x18006846b  call    cs:__imp_CoTaskMemFree
0x180068471  test    ebx, ebx
0x180068473  jns     short loc_180068479
0x180068475  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180068479  mov     rax, rdi
0x18006847c  mov     rcx, [rsp+288h+var_38]
0x180068484  xor     rcx, rsp; StackCookie
0x180068487  call    __security_check_cookie
0x18006848c  add     rsp, 268h
0x180068493  pop     r15
0x180068495  pop     rdi
0x180068496  pop     rsi
0x180068497  pop     rbx
0x180068498  retn
```
