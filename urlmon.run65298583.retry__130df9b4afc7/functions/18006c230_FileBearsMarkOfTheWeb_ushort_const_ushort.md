# FileBearsMarkOfTheWeb(ushort const *,ushort * *)

- ea: `0x18006c230`
- end: `0x18006c6d9`
- name: `?FileBearsMarkOfTheWeb@@YAHPEBGPEAPEAG@Z`
- size: `1193`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006c028`

## callees

- `0x1800150e0`
- `0x18001e340`
- `0x180030880`
- `0x18005cc10`
- `0x18006c230`
- `0x1800a2718`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c4d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c4e6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c60c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c4d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c4e6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18006c60c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18006c5a6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18006c5a6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c493`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c546`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c589`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c493`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c546`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18006c589`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x18006c626`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x18006c626`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c3be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c42c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c69c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c3be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c42c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006c69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c3ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c3ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c5d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c665`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c5d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c665`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c4bf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c523`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c4bf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c523`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c30f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c30f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c357`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c475`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c357`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c475`

## pseudocode

```c
__int64 __fastcall FileBearsMarkOfTheWeb(LPCWSTR lpFileName, unsigned __int16 **a2)
{
  WCHAR *v2; // rbx
  __int64 v3; // r8
  unsigned int v5; // esi
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  CHAR *v9; // rcx
  bool v10; // zf
  CHAR *v11; // rax
  __int64 v12; // r9
  CHAR *v13; // rdx
  const char *v14; // rax
  CHAR *v15; // rax
  HANDLE FileW; // rax
  __int64 v17; // rdi
  char *v18; // r12
  int v19; // r15d
  HANDLE v20; // rsi
  int v21; // r13d
  __int64 v22; // rax
  int v24; // edi
  unsigned int v25; // eax
  unsigned int v26; // r14d
  WCHAR *v27; // rax
  DWORD v28; // r14d
  const WCHAR *v29; // rax
  const WCHAR *v30; // r15
  const CHAR *v31; // rax
  const CHAR *v32; // r15
  PSTR v33; // rsi
  LONG v34; // edx
  PWSTR v35; // rsi
  PWSTR v36; // rax
  PWSTR v37; // r14
  int v38; // ecx
  unsigned int v39; // edi
  unsigned __int16 *v40; // rax
  PSTR v41; // rax
  PSTR v42; // r14
  unsigned int v43; // eax
  __int64 v44; // rdi
  size_t v45; // rsi
  unsigned __int16 *v46; // rax
  LPWSTR *v47; // r15
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-85h] BYREF
  _BYTE Buffer[4]; // [rsp+48h] [rbp-81h] BYREF
  int v50; // [rsp+4Ch] [rbp-7Dh]
  HANDLE hObject; // [rsp+50h] [rbp-79h]
  unsigned __int16 **v52; // [rsp+58h] [rbp-71h]
  CHAR pszSrch[16]; // [rsp+60h] [rbp-69h] BYREF
  CHAR MultiByteStr[32]; // [rsp+70h] [rbp-59h] BYREF
  WCHAR v55[12]; // [rsp+90h] [rbp-39h] BYREF
  WCHAR WideCharStr[32]; // [rsp+A8h] [rbp-21h] BYREF

  v2 = 0;
  v52 = a2;
  v3 = 2147483646;
  *a2 = 0;
  v5 = 0;
  v6 = "<!-- saved from url=(%04d)";
  v7 = 30;
  v8 = 2147483646;
  v9 = MultiByteStr;
  do
  {
    if ( !v8 )
      break;
    if ( !*v6 )
      break;
    *v9++ = *v6++;
    --v8;
    --v7;
  }
  while ( v7 );
  v10 = v7 == 0;
  v11 = v9 - 1;
  v12 = 10;
  v13 = pszSrch;
  if ( !v10 )
    v11 = v9;
  *v11 = 0;
  v14 = " -->\r\n";
  do
  {
    if ( !v3 )
      break;
    if ( !*v14 )
      break;
    *v13++ = *v14++;
    --v3;
    --v12;
  }
  while ( v12 );
  v15 = v13 - 1;
  if ( v12 )
    v15 = v13;
  *v15 = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  hObject = FileW;
  if ( FileW == (HANDLE)-1LL )
    return v5;
  v17 = -1;
  v18 = 0;
  do
    ++v17;
  while ( MultiByteStr[v17] );
  NumberOfBytesRead = 0;
  v19 = 2;
  if ( !ReadFile(FileW, Buffer, 2u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 2 )
    goto LABEL_25;
  if ( Buffer[0] == 0xFF && Buffer[1] == 0xFE )
  {
    v20 = hObject;
    v21 = 1;
  }
  else
  {
    v20 = hObject;
    v21 = 0;
    SetFilePointer(hObject, 0, 0, 0);
    v19 = 1;
  }
  v22 = (unsigned int)(v17 - 6);
  v50 = v19;
  if ( (unsigned int)v22 >= 0x1E )
    _report_rangecheckfailure();
  MultiByteStr[v22] = 0;
  if ( v21
    && (!MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 30) || !MultiByteToWideChar(
                                                                            0,
                                                                            0,
                                                                            pszSrch,
                                                                            -1,
                                                                            v55,
                                                                            10)) )
  {
LABEL_24:
    v5 = 0;
    goto LABEL_25;
  }
  v24 = 1;
  while ( 1 )
  {
    do
    {
      v25 = 2 * ((v24 << 10) + 2085);
      if ( !v21 )
        v25 = (v24 << 10) + 2085;
      v26 = v25;
      v27 = (WCHAR *)operator new(v25);
      v2 = v27;
      if ( !v27 )
        goto LABEL_38;
      v28 = v26 - v19;
    }
    while ( !ReadFile(v20, v27, v28, &NumberOfBytesRead, 0) );
    *((_BYTE *)v2 + NumberOfBytesRead) = 0;
    if ( !v21 )
      break;
    v29 = StrStrW(v2, WideCharStr);
    v30 = v29;
    if ( !v29 )
      goto LABEL_38;
    v35 = StrStrW(v29, v55);
    if ( v35 )
    {
      v36 = StrStrW(v30, L"=(");
      if ( v36 )
      {
        v37 = v36 + 2;
        v36[6] = 0;
        v38 = StrToIntW(v36 + 2);
        if ( (unsigned int)v38 > 0x824 )
          v38 = 2084;
        if ( ((char *)v35 - (char *)v37 - 10) >> 1 >= v38 )
        {
          v39 = v38 + 1;
          v40 = (unsigned __int16 *)LocalAlloc(0, 2LL * (unsigned int)(v38 + 1));
          *v52 = v40;
          if ( v40 )
          {
            StringCchCopyW(v40, v39, v37 + 5);
            goto LABEL_63;
          }
        }
      }
      goto LABEL_38;
    }
    if ( NumberOfBytesRead < v28 )
      goto LABEL_38;
    operator delete(v2);
    v2 = 0;
    if ( v24 > 2 )
      goto LABEL_24;
    ++v24;
    v34 = 2;
LABEL_45:
    v20 = hObject;
    SetFilePointer(hObject, v34, 0, 0);
    v19 = v50;
  }
  v31 = StrStrA((PCSTR)v2, MultiByteStr);
  v32 = v31;
  if ( !v31 )
    goto LABEL_38;
  v33 = StrStrA(v31, pszSrch);
  if ( !v33 )
  {
    if ( NumberOfBytesRead < v28 )
      goto LABEL_38;
    operator delete(v2);
    v2 = 0;
    if ( ++v24 > 2 )
      goto LABEL_24;
    v34 = 0;
    goto LABEL_45;
  }
  v41 = StrStrA(v32, "=(");
  if ( !v41 )
    goto LABEL_38;
  v42 = v41 + 2;
  v41[6] = 0;
  v43 = StrToIntA(v41 + 2);
  v44 = v43;
  if ( v43 > 0x824 )
    v44 = 2084;
  if ( v33 - v42 - 5 < (int)v44 )
  {
LABEL_38:
    v5 = 0;
    goto LABEL_25;
  }
  v45 = (unsigned int)(v44 + 1);
  v18 = (char *)operator new(v45);
  if ( v18 && (v46 = (unsigned __int16 *)LocalAlloc(0, 2 * v45), v47 = v52, (*v52 = v46) != 0) )
  {
    StringCchCopyA(v18, (unsigned int)v45, v42 + 5);
    MultiByteToWideChar(0, 0, v18, -1, *v47, v44);
    (*v47)[v44] = 0;
LABEL_63:
    operator delete(v2);
    v2 = 0;
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
LABEL_25:
  CloseHandle(hObject);
  if ( v2 )
    operator delete(v2);
  if ( v18 )
    operator delete(v18);
  return v5;
}

```

## disassembly

```asm
0x18006c230  mov     [rsp-8+arg_10], rbx
0x18006c235  push    rbp
0x18006c236  push    rsi
0x18006c237  push    rdi
0x18006c238  push    r12
0x18006c23a  push    r13
0x18006c23c  push    r14
0x18006c23e  push    r15
0x18006c240  lea     rbp, [rsp-27h]
0x18006c245  sub     rsp, 0F0h
0x18006c24c  mov     rax, cs:__security_cookie
0x18006c253  xor     rax, rsp
0x18006c256  mov     [rbp+57h+var_38], rax
0x18006c25a  xor     ebx, ebx
0x18006c25c  mov     [rbp+57h+var_C8], rdx
0x18006c260  mov     r8d, 7FFFFFFEh
0x18006c266  mov     [rdx], rbx
0x18006c269  mov     r11, rcx
0x18006c26c  mov     [rsp+120h+var_E0], ebx
0x18006c270  mov     esi, ebx
0x18006c272  lea     r9, aSavedFromUrl04; "<!-- saved from url=(%04d)"
0x18006c279  lea     edx, [rbx+1Eh]
0x18006c27c  mov     eax, r8d
0x18006c27f  lea     r14d, [rbx+1]
0x18006c283  lea     rcx, [rbp+57h+MultiByteStr]
0x18006c287  test    rax, rax
0x18006c28a  jz      short loc_18006C2A5
0x18006c28c  mov     r10b, [r9]
0x18006c28f  test    r10b, r10b
0x18006c292  jz      short loc_18006C2A5
0x18006c294  mov     [rcx], r10b
0x18006c297  add     r9, r14
0x18006c29a  add     rcx, r14
0x18006c29d  sub     rax, r14
0x18006c2a0  sub     rdx, r14
0x18006c2a3  jnz     short loc_18006C287
0x18006c2a5  test    rdx, rdx
0x18006c2a8  lea     rax, [rcx-1]
0x18006c2ac  mov     r9d, 0Ah
0x18006c2b2  lea     rdx, [rbp+57h+pszSrch]
0x18006c2b6  cmovnz  rax, rcx
0x18006c2ba  mov     [rax], bl
0x18006c2bc  lea     rax, asc_18012EAC4; " -->\r\n"
0x18006c2c3  test    r8, r8
0x18006c2c6  jz      short loc_18006C2DE
0x18006c2c8  mov     cl, [rax]
0x18006c2ca  test    cl, cl
0x18006c2cc  jz      short loc_18006C2DE
0x18006c2ce  mov     [rdx], cl
0x18006c2d0  add     rax, r14
0x18006c2d3  add     rdx, r14
0x18006c2d6  sub     r8, r14
0x18006c2d9  sub     r9, r14
0x18006c2dc  jnz     short loc_18006C2C3
0x18006c2de  test    r9, r9
0x18006c2e1  mov     [rsp+120h+hTemplateFile], rbx; hTemplateFile
0x18006c2e6  lea     rax, [rdx-1]
0x18006c2ea  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006c2f2  cmovnz  rax, rdx
0x18006c2f6  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18006c2fe  xor     r9d, r9d; lpSecurityAttributes
0x18006c301  mov     edx, 80000000h; dwDesiredAccess
0x18006c306  mov     rcx, r11; lpFileName
0x18006c309  mov     [rax], bl
0x18006c30b  lea     r8d, [r9+7]; dwShareMode
0x18006c30f  call    cs:__imp_CreateFileW
0x18006c315  mov     [rbp+57h+hObject], rax
0x18006c319  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c31d  jz      loc_18006C3E6
0x18006c323  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006c327  lea     rdx, [rbp+57h+MultiByteStr]
0x18006c32b  xor     ecx, ecx
0x18006c32d  mov     r12, rbx
0x18006c330  inc     rdi
0x18006c333  cmp     [rdx+rdi], cl
0x18006c336  jnz     short loc_18006C330
0x18006c338  mov     [rsp+120h+NumberOfBytesRead], ecx
0x18006c33c  lea     r9, [rsp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006c341  mov     qword ptr [rsp+120h+dwCreationDisposition], rcx; lpOverlapped
0x18006c346  lea     rdx, [rsp+120h+Buffer]; lpBuffer
0x18006c34b  mov     r15d, 2
0x18006c351  mov     rcx, rax; hFile
0x18006c354  mov     r8d, r15d; nNumberOfBytesToRead
0x18006c357  call    cs:__imp_ReadFile
0x18006c35d  test    eax, eax
0x18006c35f  jz      short loc_18006C3CA
0x18006c361  cmp     [rsp+120h+NumberOfBytesRead], r15d
0x18006c366  jnz     short loc_18006C3CA
0x18006c368  cmp     [rsp+120h+Buffer], 0FFh
0x18006c36d  jnz     loc_18006C4AD
0x18006c373  cmp     [rbp+57h+var_D7], 0FEh
0x18006c377  jnz     loc_18006C4AD
0x18006c37d  mov     rsi, [rbp+57h+hObject]
0x18006c381  mov     r13d, r14d
0x18006c384  lea     eax, [rdi-6]
0x18006c387  mov     [rbp+57h+var_D4], r15d
0x18006c38b  cmp     eax, 1Eh
0x18006c38e  jnb     loc_18006C6BD
0x18006c394  mov     [rbp+rax+57h+MultiByteStr], bl
0x18006c398  test    r13d, r13d
0x18006c39b  jz      loc_18006C436
0x18006c3a1  lea     rax, [rbp+57h+WideCharStr]
0x18006c3a5  mov     [rsp+120h+dwFlagsAndAttributes], 1Eh; cchWideChar
0x18006c3ad  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006c3b1  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpWideCharStr
0x18006c3b6  lea     r8, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x18006c3ba  xor     edx, edx; dwFlags
0x18006c3bc  xor     ecx, ecx; CodePage
0x18006c3be  call    cs:__imp_MultiByteToWideChar
0x18006c3c4  test    eax, eax
0x18006c3c6  jnz     short loc_18006C40F
0x18006c3c8  mov     esi, ebx
0x18006c3ca  mov     rcx, [rbp+57h+hObject]; hObject
0x18006c3ce  call    cs:__imp_CloseHandle
0x18006c3d4  test    rbx, rbx
0x18006c3d7  jnz     loc_18006C532
0x18006c3dd  test    r12, r12
0x18006c3e0  jnz     loc_18006C6CC
0x18006c3e6  mov     eax, esi
0x18006c3e8  mov     rcx, [rbp+57h+var_38]
0x18006c3ec  xor     rcx, rsp; StackCookie
0x18006c3ef  call    __security_check_cookie
0x18006c3f4  mov     rbx, [rsp+120h+arg_10]
0x18006c3fc  add     rsp, 0F0h
0x18006c403  pop     r15
0x18006c405  pop     r14
0x18006c407  pop     r13
0x18006c409  pop     r12
0x18006c40b  pop     rdi
0x18006c40c  pop     rsi
0x18006c40d  pop     rbp
0x18006c40e  retn
0x18006c40f  lea     rax, [rbp+57h+var_90]
0x18006c413  mov     [rsp+120h+dwFlagsAndAttributes], 0Ah; cchWideChar
0x18006c41b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006c41f  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpWideCharStr
0x18006c424  lea     r8, [rbp+57h+pszSrch]; lpMultiByteStr
0x18006c428  xor     edx, edx; dwFlags
0x18006c42a  xor     ecx, ecx; CodePage
0x18006c42c  call    cs:__imp_MultiByteToWideChar
0x18006c432  test    eax, eax
0x18006c434  jz      short loc_18006C3C8
0x18006c436  mov     edi, r14d
0x18006c439  mov     ecx, edi
0x18006c43b  shl     ecx, 0Ah
0x18006c43e  add     ecx, 825h
0x18006c444  test    r13d, r13d
0x18006c447  lea     eax, [rcx+rcx]
0x18006c44a  cmovz   eax, ecx
0x18006c44d  mov     ecx, eax; Size
0x18006c44f  mov     r14d, eax
0x18006c452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c457  mov     rbx, rax
0x18006c45a  test    rax, rax
0x18006c45d  jz      short loc_18006C4A5
0x18006c45f  sub     r14d, r15d
0x18006c462  mov     qword ptr [rsp+120h+dwCreationDisposition], r12; lpOverlapped
0x18006c467  mov     r8d, r14d; nNumberOfBytesToRead
0x18006c46a  lea     r9, [rsp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006c46f  mov     rdx, rax; lpBuffer
0x18006c472  mov     rcx, rsi; hFile
0x18006c475  call    cs:__imp_ReadFile
0x18006c47b  test    eax, eax
0x18006c47d  jz      short loc_18006C439
0x18006c47f  mov     eax, [rsp+120h+NumberOfBytesRead]
0x18006c483  mov     rcx, rbx; pszFirst
0x18006c486  mov     [rax+rbx], r12b
0x18006c48a  test    r13d, r13d
0x18006c48d  jz      short loc_18006C4CD
0x18006c48f  lea     rdx, [rbp+57h+WideCharStr]; pszSrch
0x18006c493  call    cs:__imp_StrStrW
0x18006c499  mov     r15, rax
0x18006c49c  test    rax, rax
0x18006c49f  jnz     loc_18006C53F
0x18006c4a5  mov     esi, r12d
0x18006c4a8  jmp     loc_18006C3CA
0x18006c4ad  mov     rsi, [rbp+57h+hObject]
0x18006c4b1  xor     r13d, r13d
0x18006c4b4  mov     rcx, rsi; hFile
0x18006c4b7  xor     r9d, r9d; dwMoveMethod
0x18006c4ba  xor     r8d, r8d; lpDistanceToMoveHigh
0x18006c4bd  xor     edx, edx; lDistanceToMove
0x18006c4bf  call    cs:__imp_SetFilePointer
0x18006c4c5  mov     r15d, r14d
0x18006c4c8  jmp     loc_18006C384
0x18006c4cd  lea     rdx, [rbp+57h+MultiByteStr]; pszSrch
0x18006c4d1  call    cs:__imp_StrStrA
0x18006c4d7  mov     r15, rax
0x18006c4da  test    rax, rax
0x18006c4dd  jz      short loc_18006C4A5
0x18006c4df  lea     rdx, [rbp+57h+pszSrch]; pszSrch
0x18006c4e3  mov     rcx, rax; pszFirst
0x18006c4e6  call    cs:__imp_StrStrA
0x18006c4ec  mov     rsi, rax
0x18006c4ef  test    rax, rax
0x18006c4f2  jnz     loc_18006C602
0x18006c4f8  cmp     [rsp+120h+NumberOfBytesRead], r14d
0x18006c4fd  jb      short loc_18006C4A5
0x18006c4ff  mov     rcx, rbx; void *
0x18006c502  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c507  xor     ebx, ebx
0x18006c509  inc     edi
0x18006c50b  cmp     edi, 2
0x18006c50e  jg      loc_18006C3C8
0x18006c514  xor     r9d, r9d; dwMoveMethod
0x18006c517  xor     r8d, r8d; lpDistanceToMoveHigh
0x18006c51a  xor     edx, edx; lDistanceToMove
0x18006c51c  mov     rsi, [rbp+57h+hObject]
0x18006c520  mov     rcx, rsi; hFile
0x18006c523  call    cs:__imp_SetFilePointer
0x18006c529  mov     r15d, [rbp+57h+var_D4]
0x18006c52d  jmp     loc_18006C439
0x18006c532  mov     rcx, rbx; void *
0x18006c535  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c53a  jmp     loc_18006C3DD
0x18006c53f  lea     rdx, [rbp+57h+var_90]; pszSrch
0x18006c543  mov     rcx, r15; pszFirst
0x18006c546  call    cs:__imp_StrStrW
0x18006c54c  mov     rsi, rax
0x18006c54f  test    rax, rax
0x18006c552  jnz     short loc_18006C57F
0x18006c554  cmp     [rsp+120h+NumberOfBytesRead], r14d
0x18006c559  jb      loc_18006C4A5
0x18006c55f  mov     rcx, rbx; void *
0x18006c562  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c567  xor     ebx, ebx
0x18006c569  cmp     edi, 2
0x18006c56c  jg      loc_18006C3C8
0x18006c572  inc     edi
0x18006c574  lea     edx, [rsi+2]
0x18006c577  xor     r9d, r9d
0x18006c57a  xor     r8d, r8d
0x18006c57d  jmp     short loc_18006C51C
0x18006c57f  lea     rdx, asc_180139724; "=("
0x18006c586  mov     rcx, r15; pszFirst
0x18006c589  call    cs:__imp_StrStrW
0x18006c58f  test    rax, rax
0x18006c592  jz      loc_18006C4A5
0x18006c598  lea     r14, [rax+4]
0x18006c59c  xor     eax, eax
0x18006c59e  mov     rcx, r14; pszSrc
0x18006c5a1  mov     [r14+8], ax
0x18006c5a6  call    cs:__imp_StrToIntW
0x18006c5ac  mov     ecx, eax
0x18006c5ae  mov     eax, 824h
0x18006c5b3  cmp     ecx, eax
0x18006c5b5  cmova   ecx, eax
0x18006c5b8  sub     rsi, r14
0x18006c5bb  sub     rsi, 0Ah
0x18006c5bf  movsxd  rax, ecx
0x18006c5c2  sar     rsi, 1
0x18006c5c5  cmp     rsi, rax
0x18006c5c8  jl      loc_18006C4A5
0x18006c5ce  lea     eax, [rcx+1]
0x18006c5d1  xor     ecx, ecx; uFlags
0x18006c5d3  lea     rdx, [rax+rax]; uBytes
0x18006c5d7  mov     edi, eax
0x18006c5d9  call    cs:__imp_LocalAlloc
0x18006c5df  mov     r15, [rbp+57h+var_C8]
0x18006c5e3  mov     [r15], rax
0x18006c5e6  test    rax, rax
0x18006c5e9  jz      loc_18006C4A5
0x18006c5ef  lea     r8, [r14+0Ah]; unsigned __int16 *
0x18006c5f3  mov     edx, edi; unsigned __int64
0x18006c5f5  mov     rcx, rax; unsigned __int16 *
0x18006c5f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006c5fd  jmp     loc_18006C6AB
0x18006c602  lea     rdx, asc_18013972C; "=("
0x18006c609  mov     rcx, r15; pszFirst
0x18006c60c  call    cs:__imp_StrStrA
0x18006c612  test    rax, rax
0x18006c615  jz      loc_18006C4A5
0x18006c61b  lea     r14, [rax+2]
0x18006c61f  mov     rcx, r14; pszSrc
0x18006c622  mov     [r14+4], r12b
0x18006c626  call    cs:__imp_StrToIntA
0x18006c62c  mov     edi, eax
0x18006c62e  mov     eax, 824h
0x18006c633  cmp     edi, eax
0x18006c635  cmova   edi, eax
0x18006c638  sub     rsi, r14
0x18006c63b  sub     rsi, 5
0x18006c63f  movsxd  rax, edi
0x18006c642  cmp     rsi, rax
0x18006c645  jl      loc_18006C4A5
0x18006c64b  lea     eax, [rdi+1]
0x18006c64e  mov     ecx, eax; Size
0x18006c650  mov     esi, eax
0x18006c652  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c657  mov     r12, rax
0x18006c65a  test    rax, rax
0x18006c65d  jz      short loc_18006C6C3
0x18006c65f  lea     rdx, [rsi+rsi]; uBytes
0x18006c663  xor     ecx, ecx; uFlags
0x18006c665  call    cs:__imp_LocalAlloc
0x18006c66b  mov     r15, [rbp+57h+var_C8]
0x18006c66f  mov     [r15], rax
0x18006c672  test    rax, rax
0x18006c675  jz      short loc_18006C6C3
0x18006c677  lea     r8, [r14+5]; char *
  ... truncated ...
```
