# SHAnsiToUnicodeCPAlloc

- ea: `0x180091990`
- end: `0x180091a62`
- name: `SHAnsiToUnicodeCPAlloc`
- size: `210`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001abfc`
- `0x18001c82c`
- `0x180091990`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800919d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180091a2a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800919d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180091a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091a00`

## pseudocode

```c
__int64 __fastcall SHAnsiToUnicodeCPAlloc(UINT CodePage, LPCCH lpMultiByteStr, WCHAR **a3)
{
  __int64 v6; // rax
  int v7; // r12d
  int v8; // eax
  __int64 cchWideChar; // r14
  int Error; // eax
  int v11; // ebx
  WCHAR *lpWideCharStr; // rax
  WCHAR *v13; // rdi

  v6 = -1;
  do
    ++v6;
  while ( lpMultiByteStr[v6] );
  v7 = v6 + 1;
  v8 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, v6 + 1, 0, 0);
  cchWideChar = v8;
  if ( v8 )
  {
    *a3 = 0;
    goto LABEL_6;
  }
  Error = ResultFromLastError();
  *a3 = 0;
  v11 = Error;
  if ( Error >= 0 )
  {
LABEL_6:
    lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2 * cchWideChar);
    v13 = lpWideCharStr;
    if ( !lpWideCharStr )
      return (unsigned int)-2147024882;
    if ( MultiByteToWideChar(CodePage, 0, lpMultiByteStr, v7, lpWideCharStr, cchWideChar) )
    {
      v11 = 0;
    }
    else
    {
      v11 = ResultFromKnownLastError();
      if ( v11 < 0 )
      {
LABEL_12:
        CoTaskMemFree(v13);
        return (unsigned int)v11;
      }
    }
    *a3 = v13;
    v13 = 0;
    goto LABEL_12;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180091990  push    rbx
0x180091992  push    rbp
0x180091993  push    rsi
0x180091994  push    rdi
0x180091995  push    r12
0x180091997  push    r14
0x180091999  push    r15
0x18009199b  sub     rsp, 30h
0x18009199f  mov     rsi, r8
0x1800919a2  mov     rbp, rdx
0x1800919a5  mov     r15d, ecx
0x1800919a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800919ac  inc     rax
0x1800919af  cmp     byte ptr [rax+rdx], 0
0x1800919b3  jnz     short loc_1800919AC
0x1800919b5  lea     r12d, [rax+1]
0x1800919b9  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x1800919c1  mov     r9d, r12d; cbMultiByte
0x1800919c4  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x1800919cd  mov     r8, rbp; lpMultiByteStr
0x1800919d0  xor     edx, edx; dwFlags
0x1800919d2  call    cs:__imp_MultiByteToWideChar
0x1800919d8  movsxd  r14, eax
0x1800919db  test    eax, eax
0x1800919dd  jz      short loc_1800919E8
0x1800919df  mov     qword ptr [rsi], 0
0x1800919e6  jmp     short loc_1800919FA
0x1800919e8  call    ResultFromLastError
0x1800919ed  mov     qword ptr [rsi], 0
0x1800919f4  mov     ebx, eax
0x1800919f6  test    eax, eax
0x1800919f8  js      short loc_180091A51
0x1800919fa  mov     rcx, r14
0x1800919fd  add     rcx, rcx; cb
0x180091a00  call    cs:__imp_CoTaskMemAlloc
0x180091a06  mov     rdi, rax
0x180091a09  test    rax, rax
0x180091a0c  jnz     short loc_180091A15
0x180091a0e  mov     ebx, 8007000Eh
0x180091a13  jmp     short loc_180091A51
0x180091a15  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180091a1a  mov     r9d, r12d; cbMultiByte
0x180091a1d  mov     r8, rbp; lpMultiByteStr
0x180091a20  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x180091a25  xor     edx, edx; dwFlags
0x180091a27  mov     ecx, r15d; CodePage
0x180091a2a  call    cs:__imp_MultiByteToWideChar
0x180091a30  test    eax, eax
0x180091a32  jz      short loc_180091A38
0x180091a34  xor     ebx, ebx
0x180091a36  jmp     short loc_180091A43
0x180091a38  call    ResultFromKnownLastError
0x180091a3d  mov     ebx, eax
0x180091a3f  test    eax, eax
0x180091a41  js      short loc_180091A48
0x180091a43  mov     [rsi], rdi
0x180091a46  xor     edi, edi
0x180091a48  mov     rcx, rdi; pv
0x180091a4b  call    cs:__imp_CoTaskMemFree
0x180091a51  mov     eax, ebx
0x180091a53  add     rsp, 30h
0x180091a57  pop     r15
0x180091a59  pop     r14
0x180091a5b  pop     r12
0x180091a5d  pop     rdi
0x180091a5e  pop     rsi
0x180091a5f  pop     rbp
0x180091a60  pop     rbx
0x180091a61  retn
```
