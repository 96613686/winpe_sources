# PutFileSettingsString(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000c05c`
- end: `0x18000c334`
- name: `?PutFileSettingsString@@YAJPEBG000@Z`
- size: `728`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, LPCWCH, LPCWCH, LPCWCH)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000aeb0`
- `0x18000bfe0`

## callees

- `0x18000c05c`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringW` at `0x18000c0a4`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000c0a4`
- `KERNEL32!GetLastError` at `0x18000c0b2`
- `KERNEL32!GetLastError` at `0x18000c0b2`
- `KERNEL32!WritePrivateProfileStringA` at `0x18000c303`
- `KERNEL32!WritePrivateProfileStringA` at `0x18000c303`
- `KERNEL32!WideCharToMultiByte` at `0x18000c0ee`
- `KERNEL32!WideCharToMultiByte` at `0x18000c14b`
- `KERNEL32!WideCharToMultiByte` at `0x18000c17a`
- `KERNEL32!WideCharToMultiByte` at `0x18000c1d8`
- `KERNEL32!WideCharToMultiByte` at `0x18000c204`
- `KERNEL32!WideCharToMultiByte` at `0x18000c262`
- `KERNEL32!WideCharToMultiByte` at `0x18000c28e`
- `KERNEL32!WideCharToMultiByte` at `0x18000c2e9`
- `KERNEL32!WideCharToMultiByte` at `0x18000c0ee`
- `KERNEL32!WideCharToMultiByte` at `0x18000c14b`
- `KERNEL32!WideCharToMultiByte` at `0x18000c17a`
- `KERNEL32!WideCharToMultiByte` at `0x18000c1d8`
- `KERNEL32!WideCharToMultiByte` at `0x18000c204`
- `KERNEL32!WideCharToMultiByte` at `0x18000c262`
- `KERNEL32!WideCharToMultiByte` at `0x18000c28e`
- `KERNEL32!WideCharToMultiByte` at `0x18000c2e9`

## pseudocode

```c
signed int __fastcall PutFileSettingsString(LPCWCH lpWideCharStr, LPCWCH a2, LPCWCH a3, LPCWCH a4)
{
  BOOL v8; // eax
  signed int result; // eax
  int cbMultiByte; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  int v15; // eax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  int v20; // eax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  int v25; // eax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  _BYTE v30[32]; // [rsp+0h] [rbp-40h] BYREF
  CHAR MultiByteStr[80]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    v8 = WritePrivateProfileStringW(a2, a3, a4, lpWideCharStr);
    goto LABEL_3;
  }
  cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  if ( cbMultiByte )
  {
    v11 = cbMultiByte + 15LL;
    if ( v11 < cbMultiByte )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    if ( v30 == (_BYTE *)-64LL )
      return -2147024882;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, cbMultiByte, 0, 0) )
      goto LABEL_4;
    v15 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
    if ( !v15 )
      goto LABEL_4;
    v16 = v15 + 15LL;
    if ( v16 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
    v18 = alloca(v17);
    v19 = alloca(v17);
    if ( v30 == (_BYTE *)-64LL )
      return -2147024882;
    if ( !WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, v15, 0, 0) )
      goto LABEL_4;
    v20 = WideCharToMultiByte(0, 0, a3, -1, 0, 0, 0, 0);
    if ( !v20 )
      goto LABEL_4;
    v21 = v20 + 15LL;
    if ( v21 < v20 )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
    v23 = alloca(v22);
    v24 = alloca(v22);
    if ( v30 == (_BYTE *)-64LL )
      return -2147024882;
    if ( !WideCharToMultiByte(0, 0, a3, -1, MultiByteStr, v20, 0, 0) )
      goto LABEL_4;
    v25 = WideCharToMultiByte(0, 0, a4, -1, 0, 0, 0, 0);
    if ( !v25 )
      goto LABEL_4;
    v26 = v25 + 15LL;
    if ( v26 < v25 )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
    v28 = alloca(v27);
    v29 = alloca(v27);
    if ( v30 == (_BYTE *)-64LL )
      return -2147024882;
    if ( WideCharToMultiByte(0, 0, a4, -1, MultiByteStr, v25, 0, 0) )
    {
      v8 = WritePrivateProfileStringA(MultiByteStr, MultiByteStr, MultiByteStr, MultiByteStr);
LABEL_3:
      if ( v8 )
        return 0;
    }
  }
LABEL_4:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000c05c  push    rbp
0x18000c05e  push    rbx
0x18000c05f  push    rsi
0x18000c060  push    rdi
0x18000c061  push    r12
0x18000c063  push    r13
0x18000c065  push    r14
0x18000c067  push    r15
0x18000c069  sub     rsp, 58h
0x18000c06d  lea     rbp, [rsp+40h]
0x18000c072  mov     rax, cs:__security_cookie
0x18000c079  xor     rax, rbp
0x18000c07c  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18000c080  xor     r13d, r13d
0x18000c083  mov     r15, r9
0x18000c086  cmp     cs:?g_fWindowsNT@Global@@2_NA, r13b; bool Global::g_fWindowsNT
0x18000c08d  mov     r14, r8
0x18000c090  mov     rdi, rdx
0x18000c093  mov     rbx, rcx
0x18000c096  jz      short loc_18000C0CD
0x18000c098  mov     r9, rcx; lpFileName
0x18000c09b  mov     r8, r15; lpString
0x18000c09e  mov     rcx, rdi; lpAppName
0x18000c0a1  mov     rdx, r14; lpKeyName
0x18000c0a4  call    cs:__imp_WritePrivateProfileStringW
0x18000c0aa  test    eax, eax
0x18000c0ac  jnz     loc_18000C30E
0x18000c0b2  call    cs:__imp_GetLastError
0x18000c0b8  test    eax, eax
0x18000c0ba  jle     loc_18000C317
0x18000c0c0  movzx   eax, ax
0x18000c0c3  or      eax, 80070000h
0x18000c0c8  jmp     loc_18000C317
0x18000c0cd  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c0d2  or      esi, 0FFFFFFFFh
0x18000c0d5  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c0da  mov     r9d, esi; cchWideChar
0x18000c0dd  mov     [rsp+90h+cbMultiByte], r13d; cbMultiByte
0x18000c0e2  mov     r8, rbx; lpWideCharStr
0x18000c0e5  xor     edx, edx; dwFlags
0x18000c0e7  mov     [rsp+90h+lpMultiByteStr], r13; lpMultiByteStr
0x18000c0ec  xor     ecx, ecx; CodePage
0x18000c0ee  call    cs:__imp_WideCharToMultiByte
0x18000c0f4  movsxd  rdx, eax
0x18000c0f7  test    eax, eax
0x18000c0f9  jz      short loc_18000C0B2
0x18000c0fb  lea     rcx, [rdx+0Fh]
0x18000c0ff  mov     r8, 0FFFFFFFFFFFFFF0h
0x18000c109  cmp     rcx, rdx
0x18000c10c  ja      short loc_18000C111
0x18000c10e  mov     rcx, r8
0x18000c111  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c115  mov     rax, rcx
0x18000c118  call    _alloca_probe
0x18000c11d  sub     rsp, rcx
0x18000c120  lea     r12, [rsp+90h+MultiByteStr]
0x18000c125  test    r12, r12
0x18000c128  jz      loc_18000C312
0x18000c12e  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c133  mov     r9d, esi; cchWideChar
0x18000c136  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c13b  mov     r8, rbx; lpWideCharStr
0x18000c13e  mov     [rsp+90h+cbMultiByte], edx; cbMultiByte
0x18000c142  xor     ecx, ecx; CodePage
0x18000c144  xor     edx, edx; dwFlags
0x18000c146  mov     [rsp+90h+lpMultiByteStr], r12; lpMultiByteStr
0x18000c14b  call    cs:__imp_WideCharToMultiByte
0x18000c151  test    eax, eax
0x18000c153  jz      loc_18000C0B2
0x18000c159  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c15e  or      ebx, 0FFFFFFFFh
0x18000c161  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c166  mov     r9d, ebx; cchWideChar
0x18000c169  mov     [rsp+90h+cbMultiByte], r13d; cbMultiByte
0x18000c16e  mov     r8, rdi; lpWideCharStr
0x18000c171  xor     edx, edx; dwFlags
0x18000c173  mov     [rsp+90h+lpMultiByteStr], r13; lpMultiByteStr
0x18000c178  xor     ecx, ecx; CodePage
0x18000c17a  call    cs:__imp_WideCharToMultiByte
0x18000c180  movsxd  rdx, eax
0x18000c183  test    eax, eax
0x18000c185  jz      loc_18000C0B2
0x18000c18b  lea     rcx, [rdx+0Fh]
0x18000c18f  cmp     rcx, rdx
0x18000c192  ja      short loc_18000C19E
0x18000c194  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c19e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c1a2  mov     rax, rcx
0x18000c1a5  call    _alloca_probe
0x18000c1aa  sub     rsp, rcx
0x18000c1ad  lea     rsi, [rsp+90h+MultiByteStr]
0x18000c1b2  test    rsi, rsi
0x18000c1b5  jz      loc_18000C312
0x18000c1bb  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c1c0  mov     r9d, ebx; cchWideChar
0x18000c1c3  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c1c8  mov     r8, rdi; lpWideCharStr
0x18000c1cb  mov     [rsp+90h+cbMultiByte], edx; cbMultiByte
0x18000c1cf  xor     ecx, ecx; CodePage
0x18000c1d1  xor     edx, edx; dwFlags
0x18000c1d3  mov     [rsp+90h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000c1d8  call    cs:__imp_WideCharToMultiByte
0x18000c1de  test    eax, eax
0x18000c1e0  jz      loc_18000C0B2
0x18000c1e6  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c1eb  mov     r9d, ebx; cchWideChar
0x18000c1ee  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c1f3  mov     r8, r14; lpWideCharStr
0x18000c1f6  mov     [rsp+90h+cbMultiByte], r13d; cbMultiByte
0x18000c1fb  xor     edx, edx; dwFlags
0x18000c1fd  xor     ecx, ecx; CodePage
0x18000c1ff  mov     [rsp+90h+lpMultiByteStr], r13; lpMultiByteStr
0x18000c204  call    cs:__imp_WideCharToMultiByte
0x18000c20a  movsxd  rdx, eax
0x18000c20d  test    eax, eax
0x18000c20f  jz      loc_18000C0B2
0x18000c215  lea     rcx, [rdx+0Fh]
0x18000c219  cmp     rcx, rdx
0x18000c21c  ja      short loc_18000C228
0x18000c21e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c228  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c22c  mov     rax, rcx
0x18000c22f  call    _alloca_probe
0x18000c234  sub     rsp, rcx
0x18000c237  lea     rdi, [rsp+90h+MultiByteStr]
0x18000c23c  test    rdi, rdi
0x18000c23f  jz      loc_18000C312
0x18000c245  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c24a  mov     r9d, ebx; cchWideChar
0x18000c24d  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c252  mov     r8, r14; lpWideCharStr
0x18000c255  mov     [rsp+90h+cbMultiByte], edx; cbMultiByte
0x18000c259  xor     ecx, ecx; CodePage
0x18000c25b  xor     edx, edx; dwFlags
0x18000c25d  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000c262  call    cs:__imp_WideCharToMultiByte
0x18000c268  test    eax, eax
0x18000c26a  jz      loc_18000C0B2
0x18000c270  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c275  mov     r9d, ebx; cchWideChar
0x18000c278  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c27d  mov     r8, r15; lpWideCharStr
0x18000c280  mov     [rsp+90h+cbMultiByte], r13d; cbMultiByte
0x18000c285  xor     edx, edx; dwFlags
0x18000c287  xor     ecx, ecx; CodePage
0x18000c289  mov     [rsp+90h+lpMultiByteStr], r13; lpMultiByteStr
0x18000c28e  call    cs:__imp_WideCharToMultiByte
0x18000c294  movsxd  rdx, eax
0x18000c297  test    eax, eax
0x18000c299  jz      loc_18000C0B2
0x18000c29f  lea     rcx, [rdx+0Fh]
0x18000c2a3  cmp     rcx, rdx
0x18000c2a6  ja      short loc_18000C2B2
0x18000c2a8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c2b2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c2b6  mov     rax, rcx
0x18000c2b9  call    _alloca_probe
0x18000c2be  sub     rsp, rcx
0x18000c2c1  lea     rbx, [rsp+90h+MultiByteStr]
0x18000c2c6  test    rbx, rbx
0x18000c2c9  jz      short loc_18000C312
0x18000c2cb  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c2d0  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000c2d4  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000c2d9  mov     r8, r15; lpWideCharStr
0x18000c2dc  mov     [rsp+90h+cbMultiByte], edx; cbMultiByte
0x18000c2e0  xor     ecx, ecx; CodePage
0x18000c2e2  xor     edx, edx; dwFlags
0x18000c2e4  mov     [rsp+90h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000c2e9  call    cs:__imp_WideCharToMultiByte
0x18000c2ef  test    eax, eax
0x18000c2f1  jz      loc_18000C0B2
0x18000c2f7  mov     r9, r12; lpFileName
0x18000c2fa  mov     r8, rbx; lpString
0x18000c2fd  mov     rdx, rdi; lpKeyName
0x18000c300  mov     rcx, rsi; lpAppName
0x18000c303  call    cs:__imp_WritePrivateProfileStringA
0x18000c309  jmp     loc_18000C0AA
0x18000c30e  xor     eax, eax
0x18000c310  jmp     short loc_18000C317
0x18000c312  mov     eax, 8007000Eh
0x18000c317  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x18000c31b  xor     rcx, rbp; StackCookie
0x18000c31e  call    __security_check_cookie
0x18000c323  lea     rsp, [rbp+18h]
0x18000c327  pop     r15
0x18000c329  pop     r14
0x18000c32b  pop     r13
0x18000c32d  pop     r12
0x18000c32f  pop     rdi
0x18000c330  pop     rsi
0x18000c331  pop     rbx
0x18000c332  pop     rbp
0x18000c333  retn
```
