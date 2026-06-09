# FileBearsMarkOfTheWeb(ushort const *,ushort * *)

- ea: `0x180071370`
- end: `0x18007188c`
- name: `?FileBearsMarkOfTheWeb@@YAHPEBGPEAPEAG@Z`
- size: `1308`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180071144`

## callees

- `0x18001db50`
- `0x180024ea0`
- `0x18002fee0`
- `0x18004d7f0`
- `0x180071370`
- `0x1800a9538`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180071642`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18007165d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800717a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180071642`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x18007165d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800717a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180071735`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180071735`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x1800715f8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x1800716c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180071712`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x1800715f8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x1800716c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180071712`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800717c7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800717c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007150a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180071585`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180071849`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007150a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180071585`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180071849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071520`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071520`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007176e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007180c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007176e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007180c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007162a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800716a0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007162a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800716a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007144f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007144f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007149d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800715d4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007149d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800715d4`

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
0x180071370  mov     [rsp-8+arg_10], rbx
0x180071375  push    rbp
0x180071376  push    rsi
0x180071377  push    rdi
0x180071378  push    r12
0x18007137a  push    r13
0x18007137c  push    r14
0x18007137e  push    r15
0x180071380  lea     rbp, [rsp-27h]
0x180071385  sub     rsp, 0F0h
0x18007138c  mov     rax, cs:__security_cookie
0x180071393  xor     rax, rsp
0x180071396  mov     [rbp+57h+var_38], rax
0x18007139a  xor     ebx, ebx
0x18007139c  mov     [rbp+57h+var_C8], rdx
0x1800713a0  mov     r8d, 7FFFFFFEh
0x1800713a6  mov     [rdx], rbx
0x1800713a9  mov     r11, rcx
0x1800713ac  mov     [rsp+120h+var_E0], ebx
0x1800713b0  mov     esi, ebx
0x1800713b2  lea     r9, aSavedFromUrl04; "<!-- saved from url=(%04d)"
0x1800713b9  lea     edx, [rbx+1Eh]
0x1800713bc  mov     eax, r8d
0x1800713bf  lea     r14d, [rbx+1]
0x1800713c3  lea     rcx, [rbp+57h+MultiByteStr]
0x1800713c7  test    rax, rax
0x1800713ca  jz      short loc_1800713E5
0x1800713cc  mov     r10b, [r9]
0x1800713cf  test    r10b, r10b
0x1800713d2  jz      short loc_1800713E5
0x1800713d4  mov     [rcx], r10b
0x1800713d7  add     r9, r14
0x1800713da  add     rcx, r14
0x1800713dd  sub     rax, r14
0x1800713e0  sub     rdx, r14
0x1800713e3  jnz     short loc_1800713C7
0x1800713e5  test    rdx, rdx
0x1800713e8  lea     rax, [rcx-1]
0x1800713ec  mov     r9d, 0Ah
0x1800713f2  lea     rdx, [rbp+57h+pszSrch]
0x1800713f6  cmovnz  rax, rcx
0x1800713fa  mov     [rax], bl
0x1800713fc  lea     rax, asc_18013BC64; " -->\r\n"
0x180071403  test    r8, r8
0x180071406  jz      short loc_18007141E
0x180071408  mov     cl, [rax]
0x18007140a  test    cl, cl
0x18007140c  jz      short loc_18007141E
0x18007140e  mov     [rdx], cl
0x180071410  add     rax, r14
0x180071413  add     rdx, r14
0x180071416  sub     r8, r14
0x180071419  sub     r9, r14
0x18007141c  jnz     short loc_180071403
0x18007141e  test    r9, r9
0x180071421  mov     [rsp+120h+hTemplateFile], rbx; hTemplateFile
0x180071426  lea     rax, [rdx-1]
0x18007142a  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180071432  cmovnz  rax, rdx
0x180071436  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18007143e  xor     r9d, r9d; lpSecurityAttributes
0x180071441  mov     edx, 80000000h; dwDesiredAccess
0x180071446  mov     rcx, r11; lpFileName
0x180071449  mov     [rax], bl
0x18007144b  lea     r8d, [r9+7]; dwShareMode
0x18007144f  call    cs:__imp_CreateFileW
0x180071456  nop     dword ptr [rax+rax+00h]
0x18007145b  mov     [rbp+57h+hObject], rax
0x18007145f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180071463  jz      loc_18007153E
0x180071469  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007146d  lea     rdx, [rbp+57h+MultiByteStr]
0x180071471  xor     ecx, ecx
0x180071473  mov     r12, rbx
0x180071476  inc     rdi
0x180071479  cmp     [rdx+rdi], cl
0x18007147c  jnz     short loc_180071476
0x18007147e  mov     [rsp+120h+NumberOfBytesRead], ecx
0x180071482  lea     r9, [rsp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180071487  mov     qword ptr [rsp+120h+dwCreationDisposition], rcx; lpOverlapped
0x18007148c  lea     rdx, [rsp+120h+Buffer]; lpBuffer
0x180071491  mov     r15d, 2
0x180071497  mov     rcx, rax; hFile
0x18007149a  mov     r8d, r15d; nNumberOfBytesToRead
0x18007149d  call    cs:__imp_ReadFile
0x1800714a4  nop     dword ptr [rax+rax+00h]
0x1800714a9  test    eax, eax
0x1800714ab  jz      short loc_18007151C
0x1800714ad  cmp     [rsp+120h+NumberOfBytesRead], r15d
0x1800714b2  jnz     short loc_18007151C
0x1800714b4  cmp     [rsp+120h+Buffer], 0FFh
0x1800714b9  jnz     loc_180071618
0x1800714bf  cmp     [rbp+57h+var_D7], 0FEh
0x1800714c3  jnz     loc_180071618
0x1800714c9  mov     rsi, [rbp+57h+hObject]
0x1800714cd  mov     r13d, r14d
0x1800714d0  lea     eax, [rdi-6]
0x1800714d3  mov     [rbp+57h+var_D4], r15d
0x1800714d7  cmp     eax, 1Eh
0x1800714da  jnb     loc_180071870
0x1800714e0  mov     [rbp+rax+57h+MultiByteStr], bl
0x1800714e4  test    r13d, r13d
0x1800714e7  jz      loc_180071595
0x1800714ed  lea     rax, [rbp+57h+WideCharStr]
0x1800714f1  mov     [rsp+120h+dwFlagsAndAttributes], 1Eh; cchWideChar
0x1800714f9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800714fd  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpWideCharStr
0x180071502  lea     r8, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x180071506  xor     edx, edx; dwFlags
0x180071508  xor     ecx, ecx; CodePage
0x18007150a  call    cs:__imp_MultiByteToWideChar
0x180071511  nop     dword ptr [rax+rax+00h]
0x180071516  test    eax, eax
0x180071518  jnz     short loc_180071568
0x18007151a  mov     esi, ebx
0x18007151c  mov     rcx, [rbp+57h+hObject]; hObject
0x180071520  call    cs:__imp_CloseHandle
0x180071527  nop     dword ptr [rax+rax+00h]
0x18007152c  test    rbx, rbx
0x18007152f  jnz     loc_1800716B5
0x180071535  test    r12, r12
0x180071538  jnz     loc_18007187F
0x18007153e  mov     eax, esi
0x180071540  mov     rcx, [rbp+57h+var_38]
0x180071544  xor     rcx, rsp; StackCookie
0x180071547  call    __security_check_cookie
0x18007154c  mov     rbx, [rsp+120h+arg_10]
0x180071554  add     rsp, 0F0h
0x18007155b  pop     r15
0x18007155d  pop     r14
0x18007155f  pop     r13
0x180071561  pop     r12
0x180071563  pop     rdi
0x180071564  pop     rsi
0x180071565  pop     rbp
0x180071566  retn
0x180071568  lea     rax, [rbp+57h+var_90]
0x18007156c  mov     [rsp+120h+dwFlagsAndAttributes], 0Ah; cchWideChar
0x180071574  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180071578  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpWideCharStr
0x18007157d  lea     r8, [rbp+57h+pszSrch]; lpMultiByteStr
0x180071581  xor     edx, edx; dwFlags
0x180071583  xor     ecx, ecx; CodePage
0x180071585  call    cs:__imp_MultiByteToWideChar
0x18007158c  nop     dword ptr [rax+rax+00h]
0x180071591  test    eax, eax
0x180071593  jz      short loc_18007151A
0x180071595  mov     edi, r14d
0x180071598  mov     ecx, edi
0x18007159a  shl     ecx, 0Ah
0x18007159d  add     ecx, 825h
0x1800715a3  test    r13d, r13d
0x1800715a6  lea     eax, [rcx+rcx]
0x1800715a9  cmovz   eax, ecx
0x1800715ac  mov     ecx, eax; Size
0x1800715ae  mov     r14d, eax
0x1800715b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800715b6  mov     rbx, rax
0x1800715b9  test    rax, rax
0x1800715bc  jz      short loc_180071610
0x1800715be  sub     r14d, r15d
0x1800715c1  mov     qword ptr [rsp+120h+dwCreationDisposition], r12; lpOverlapped
0x1800715c6  mov     r8d, r14d; nNumberOfBytesToRead
0x1800715c9  lea     r9, [rsp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800715ce  mov     rdx, rax; lpBuffer
0x1800715d1  mov     rcx, rsi; hFile
0x1800715d4  call    cs:__imp_ReadFile
0x1800715db  nop     dword ptr [rax+rax+00h]
0x1800715e0  test    eax, eax
0x1800715e2  jz      short loc_180071598
0x1800715e4  mov     eax, [rsp+120h+NumberOfBytesRead]
0x1800715e8  mov     rcx, rbx; pszFirst
0x1800715eb  mov     [rax+rbx], r12b
0x1800715ef  test    r13d, r13d
0x1800715f2  jz      short loc_18007163E
0x1800715f4  lea     rdx, [rbp+57h+WideCharStr]; pszSrch
0x1800715f8  call    cs:__imp_StrStrW
0x1800715ff  nop     dword ptr [rax+rax+00h]
0x180071604  mov     r15, rax
0x180071607  test    rax, rax
0x18007160a  jnz     loc_1800716C2
0x180071610  mov     esi, r12d
0x180071613  jmp     loc_18007151C
0x180071618  mov     rsi, [rbp+57h+hObject]
0x18007161c  xor     r13d, r13d
0x18007161f  mov     rcx, rsi; hFile
0x180071622  xor     r9d, r9d; dwMoveMethod
0x180071625  xor     r8d, r8d; lpDistanceToMoveHigh
0x180071628  xor     edx, edx; lDistanceToMove
0x18007162a  call    cs:__imp_SetFilePointer
0x180071631  nop     dword ptr [rax+rax+00h]
0x180071636  mov     r15d, r14d
0x180071639  jmp     loc_1800714D0
0x18007163e  lea     rdx, [rbp+57h+MultiByteStr]; pszSrch
0x180071642  call    cs:__imp_StrStrA
0x180071649  nop     dword ptr [rax+rax+00h]
0x18007164e  mov     r15, rax
0x180071651  test    rax, rax
0x180071654  jz      short loc_180071610
0x180071656  lea     rdx, [rbp+57h+pszSrch]; pszSrch
0x18007165a  mov     rcx, rax; pszFirst
0x18007165d  call    cs:__imp_StrStrA
0x180071664  nop     dword ptr [rax+rax+00h]
0x180071669  mov     rsi, rax
0x18007166c  test    rax, rax
0x18007166f  jnz     loc_18007179D
0x180071675  cmp     [rsp+120h+NumberOfBytesRead], r14d
0x18007167a  jb      short loc_180071610
0x18007167c  mov     rcx, rbx; void *
0x18007167f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180071684  xor     ebx, ebx
0x180071686  inc     edi
0x180071688  cmp     edi, 2
0x18007168b  jg      loc_18007151A
0x180071691  xor     r9d, r9d; dwMoveMethod
0x180071694  xor     r8d, r8d; lpDistanceToMoveHigh
0x180071697  xor     edx, edx; lDistanceToMove
0x180071699  mov     rsi, [rbp+57h+hObject]
0x18007169d  mov     rcx, rsi; hFile
0x1800716a0  call    cs:__imp_SetFilePointer
0x1800716a7  nop     dword ptr [rax+rax+00h]
0x1800716ac  mov     r15d, [rbp+57h+var_D4]
0x1800716b0  jmp     loc_180071598
0x1800716b5  mov     rcx, rbx; void *
0x1800716b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800716bd  jmp     loc_180071535
0x1800716c2  lea     rdx, [rbp+57h+var_90]; pszSrch
0x1800716c6  mov     rcx, r15; pszFirst
0x1800716c9  call    cs:__imp_StrStrW
0x1800716d0  nop     dword ptr [rax+rax+00h]
0x1800716d5  mov     rsi, rax
0x1800716d8  test    rax, rax
0x1800716db  jnz     short loc_180071708
0x1800716dd  cmp     [rsp+120h+NumberOfBytesRead], r14d
0x1800716e2  jb      loc_180071610
0x1800716e8  mov     rcx, rbx; void *
0x1800716eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800716f0  xor     ebx, ebx
0x1800716f2  cmp     edi, 2
0x1800716f5  jg      loc_18007151A
0x1800716fb  inc     edi
0x1800716fd  lea     edx, [rsi+2]
0x180071700  xor     r9d, r9d
0x180071703  xor     r8d, r8d
0x180071706  jmp     short loc_180071699
0x180071708  lea     rdx, asc_180146718; "=("
0x18007170f  mov     rcx, r15; pszFirst
0x180071712  call    cs:__imp_StrStrW
0x180071719  nop     dword ptr [rax+rax+00h]
0x18007171e  test    rax, rax
0x180071721  jz      loc_180071610
0x180071727  lea     r14, [rax+4]
0x18007172b  xor     eax, eax
0x18007172d  mov     rcx, r14; pszSrc
0x180071730  mov     [r14+8], ax
0x180071735  call    cs:__imp_StrToIntW
0x18007173c  nop     dword ptr [rax+rax+00h]
0x180071741  mov     ecx, eax
0x180071743  mov     eax, 824h
0x180071748  cmp     ecx, eax
0x18007174a  cmova   ecx, eax
0x18007174d  sub     rsi, r14
0x180071750  sub     rsi, 0Ah
0x180071754  movsxd  rax, ecx
0x180071757  sar     rsi, 1
0x18007175a  cmp     rsi, rax
0x18007175d  jl      loc_180071610
0x180071763  lea     eax, [rcx+1]
0x180071766  xor     ecx, ecx; uFlags
0x180071768  lea     rdx, [rax+rax]; uBytes
0x18007176c  mov     edi, eax
0x18007176e  call    cs:__imp_LocalAlloc
0x180071775  nop     dword ptr [rax+rax+00h]
0x18007177a  mov     r15, [rbp+57h+var_C8]
0x18007177e  mov     [r15], rax
0x180071781  test    rax, rax
0x180071784  jz      loc_180071610
0x18007178a  lea     r8, [r14+0Ah]; unsigned __int16 *
0x18007178e  mov     edx, edi; unsigned __int64
0x180071790  mov     rcx, rax; unsigned __int16 *
0x180071793  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180071798  jmp     loc_18007185E
0x18007179d  lea     rdx, asc_180146714; "=("
0x1800717a4  mov     rcx, r15; pszFirst
0x1800717a7  call    cs:__imp_StrStrA
0x1800717ae  nop     dword ptr [rax+rax+00h]
0x1800717b3  test    rax, rax
0x1800717b6  jz      loc_180071610
0x1800717bc  lea     r14, [rax+2]
0x1800717c0  mov     rcx, r14; pszSrc
0x1800717c3  mov     [r14+4], r12b
0x1800717c7  call    cs:__imp_StrToIntA
0x1800717ce  nop     dword ptr [rax+rax+00h]
0x1800717d3  mov     edi, eax
0x1800717d5  mov     eax, 824h
0x1800717da  cmp     edi, eax
0x1800717dc  cmova   edi, eax
0x1800717df  sub     rsi, r14
0x1800717e2  sub     rsi, 5
0x1800717e6  movsxd  rax, edi
  ... truncated ...
```
