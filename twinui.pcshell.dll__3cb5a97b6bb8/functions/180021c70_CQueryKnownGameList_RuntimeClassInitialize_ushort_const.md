# CQueryKnownGameList::RuntimeClassInitialize(ushort const *)

- ea: `0x180021c70`
- end: `0x1800223a1`
- name: `?RuntimeClassInitialize@CQueryKnownGameList@@QEAAJPEBG@Z`
- size: `1841`
- prototype: `__int64 __fastcall(CQueryKnownGameList *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021a90`

## callees

- `0x180021c70`
- `0x180022800`
- `0x1800237c8`
- `0x180051b5c`
- `0x180176308`
- `0x180181910`
- `0x1802bbaf8`
- `0x180356360`
- `0x180356760`
- `0x18035b6a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021e0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021e0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021e8b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021f39`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022084`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800220de`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002213e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022176`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021e8b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021f39`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022084`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800220de`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002213e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022176`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180021ee3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180021ee3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180021e3b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180021e3b`

## string_xrefs

- `0x180021da0`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021e53`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021f57`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021f86`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021fab`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021fd0`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180021ff5`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002201a`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002209c`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800220f9`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022192`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800221b7`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800221dc`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800221f6`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022225`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022261`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022285`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800222aa`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800222c4`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800222de`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800222f8`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002231c`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022341`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002235b`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022386`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`

## pseudocode

```c
__int64 __fastcall CQueryKnownGameList::RuntimeClassInitialize(CQueryKnownGameList *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rcx
  const unsigned __int16 *v5; // rax
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rax
  void *v8; // rax
  __int64 v9; // rcx
  void *v10; // rdx
  _WORD *v11; // rdx
  __int64 v12; // rcx
  _WORD *v13; // rcx
  unsigned int v14; // ebx
  wil::details::in1diag3 *v15; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  HANDLE FileW; // rbx
  wil::details *v20; // rcx
  const char *v21; // r9
  const char *v22; // r9
  int v23; // ecx
  void *v24; // rax
  void *v25; // rcx
  void *v26; // rdx
  const char *v27; // r9
  unsigned int v28; // eax
  DWORD nFileSizeLow; // edx
  int v30; // eax
  const char *v31; // r9
  const char *v32; // r9
  const char *v33; // r9
  const char *v34; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-29h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-29h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-29h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-9h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  NumberOfBytesRead = 0;
  v2 = a2;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
    return 2147500035LL;
  }
  v4 = 0x7FFFFFFF;
  v5 = a2;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return 2147942487LL;
  }
  v6 = 0x80000000LL - v4;
  v7 = 2 * (0x80000000LL - v4);
  if ( !is_mul_ok(0x80000000LL - v4, 2u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v10 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v8;
  if ( v10 )
    std::default_delete<unsigned short [0]>::operator()<unsigned short,0>(v9, v10);
  v11 = (_WORD *)*((_QWORD *)this + 2);
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    return 2147942414LL;
  }
  if ( !v6 )
  {
    v14 = -2147024809;
    goto LABEL_20;
  }
  if ( v6 > 0x7FFFFFFF )
  {
    v14 = -2147024809;
    *v11 = 0;
LABEL_20:
    v15 = retaddr;
    v16 = v14;
    v17 = 232;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      v15,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)v16,
      dwCreationDisposition);
    return v14;
  }
  v12 = 2147483646;
  do
  {
    if ( !v12 )
      break;
    if ( !*v2 )
      break;
    *v11++ = *v2++;
    --v12;
    --v6;
  }
  while ( v6 );
  v13 = v11 - 1;
  v14 = -2147024774;
  if ( v6 )
  {
    v13 = v11;
    v14 = 0;
  }
  *v13 = 0;
  if ( !v6 )
    goto LABEL_20;
  FileW = CreateFileW(*((LPCWSTR *)this + 2), 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v20 = (wil::details *)(*((_QWORD *)this + 3) - 1LL);
  if ( (unsigned __int64)v20 <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*((HANDLE *)this + 3));
  *((_QWORD *)this + 3) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::GetLastErrorFailHr(v20);
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xEE,
             (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
             v21);
  if ( FileInformation.nFileSizeHigh )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDispositiona);
    return 2147942487LL;
  }
  if ( !ReadFile(*((HANDLE *)this + 3), (char *)this + 32, 0x18u, &NumberOfBytesRead, 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF3,
             (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
             v22);
  if ( NumberOfBytesRead != 24 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDispositionb);
    return 2147942487LL;
  }
  v23 = *((_DWORD *)this + 9);
  if ( !v23 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDispositionb);
    return 2147942487LL;
  }
  if ( v23 == 1 )
  {
    if ( *((_DWORD *)this + 8) != 24 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        dwCreationDispositionb);
      return 2147942487LL;
    }
  }
  else
  {
    if ( !ReadFile(*((HANDLE *)this + 3), (char *)this + 56, 8u, &NumberOfBytesRead, 0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x101,
               (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
               v31);
    if ( NumberOfBytesRead != 8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        dwCreationDispositionb);
      return 2147942487LL;
    }
    if ( *((_DWORD *)this + 9) >= 3u )
    {
      if ( !ReadFile(*((HANDLE *)this + 3), (char *)this + 64, 0x298u, &NumberOfBytesRead, 0) )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x106,
                 (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                 v32);
      if ( NumberOfBytesRead != 664 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)0x80070057LL,
          dwCreationDispositionb);
        return 2147942487LL;
      }
      if ( *((_DWORD *)this + 9) >= 4u )
      {
        if ( !ReadFile(*((HANDLE *)this + 3), (char *)this + 728, 8u, &NumberOfBytesRead, 0) )
          return wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x10B,
                   (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                   v33);
        if ( NumberOfBytesRead != 8 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10C,
            (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
            (const char *)0x80070057LL,
            dwCreationDispositionb);
          return 2147942487LL;
        }
        if ( *((_DWORD *)this + 9) >= 5u )
        {
          if ( !ReadFile(*((HANDLE *)this + 3), (char *)this + 736, 4u, &NumberOfBytesRead, 0) )
            return wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x110,
                     (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                     v34);
          if ( NumberOfBytesRead != 4 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x111,
              (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
              (const char *)0x80070057LL,
              dwCreationDispositionb);
            return 2147942487LL;
          }
        }
      }
    }
  }
  if ( *((_DWORD *)this + 12) >= FileInformation.nFileSizeLow )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDispositionb);
    return 2147942487LL;
  }
  else if ( *((_DWORD *)this + 13) )
  {
    if ( SetFilePointer(*((HANDLE *)this + 3), *((_DWORD *)this + 11), 0, 0) == -1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDispositionb);
      return 2147549183LL;
    }
    else
    {
      v24 = operator new[](*((unsigned int *)this + 12), (const struct std::nothrow_t *)std::nothrow);
      v25 = (void *)*((_QWORD *)this + 93);
      *((_QWORD *)this + 93) = v24;
      if ( v25 )
        operator delete(v25);
      v26 = (void *)*((_QWORD *)this + 93);
      if ( v26 )
      {
        if ( ReadFile(*((HANDLE *)this + 3), v26, *((_DWORD *)this + 12), &NumberOfBytesRead, 0) )
        {
          v28 = *((_DWORD *)this + 12);
          if ( NumberOfBytesRead == v28 )
          {
            nFileSizeLow = FileInformation.nFileSizeLow;
            *((_DWORD *)this + 200) = v28 / *((_DWORD *)this + 13);
            v30 = CQueryKnownGameList::ValidateKGL(this, nFileSizeLow);
            v14 = v30;
            if ( v30 == -2147024809 )
              return 2147942487LL;
            if ( v30 < 0 )
            {
              v15 = retaddr;
              v16 = (unsigned int)v30;
              v17 = 296;
              goto LABEL_21;
            }
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x122,
              (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
              (const char *)0x80070057LL,
              dwCreationDisposition);
            return 2147942487LL;
          }
        }
        else
        {
          return wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x121,
                   (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                   v27);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11E,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)0x8007000ELL,
          dwCreationDispositionb);
        return 2147942414LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      dwCreationDispositionb);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180021c70  mov     [rsp-8+arg_18], rbx
0x180021c75  push    rbp
0x180021c76  push    rsi
0x180021c77  push    r14
0x180021c79  lea     rbp, [rsp-47h]
0x180021c7e  sub     rsp, 90h
0x180021c85  mov     rax, cs:__security_cookie
0x180021c8c  xor     rax, rsp
0x180021c8f  mov     [rbp+57h+var_20], rax
0x180021c93  xorps   xmm0, xmm0
0x180021c96  xor     r14d, r14d
0x180021c99  xor     eax, eax
0x180021c9b  mov     [rbp+57h+NumberOfBytesRead], r14d
0x180021c9f  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180021ca2  mov     rbx, rdx
0x180021ca5  mov     rsi, rcx
0x180021ca8  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180021cac  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180021cb0  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180021cb4  test    rdx, rdx
0x180021cb7  jz      loc_1800221F2
0x180021cbd  mov     [rsp+0A0h+arg_8], rdi
0x180021cc5  mov     ecx, 7FFFFFFFh
0x180021cca  mov     rax, rdx
0x180021ccd  nop     dword ptr [rax]
0x180021cd0  cmp     [rax], r14w
0x180021cd4  jz      short loc_180021CE0
0x180021cd6  add     rax, 2
0x180021cda  sub     rcx, 1
0x180021cde  jnz     short loc_180021CD0
0x180021ce0  test    rcx, rcx
0x180021ce3  mov     edi, 80070057h
0x180021ce8  cmovnz  edi, r14d
0x180021cec  jz      loc_180022382
0x180021cf2  mov     [rsp+0A0h+arg_10], r15
0x180021cfa  mov     eax, 2
0x180021cff  mov     r15d, 80000000h
0x180021d05  mov     edi, r15d
0x180021d08  sub     rdi, rcx
0x180021d0b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021d12  mul     rdi
0x180021d15  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021d1c  cmovb   rax, rcx
0x180021d20  mov     rcx, rax; unsigned __int64
0x180021d23  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180021d28  mov     rdx, [rsi+10h]
0x180021d2c  mov     [rsi+10h], rax
0x180021d30  test    rdx, rdx
0x180021d33  jnz     loc_180022217
0x180021d39  mov     rdx, [rsi+10h]
0x180021d3d  test    rdx, rdx
0x180021d40  jz      loc_180022221
0x180021d46  test    rdi, rdi
0x180021d49  jz      loc_18002236F
0x180021d4f  cmp     rdi, 7FFFFFFFh
0x180021d56  ja      loc_180022246
0x180021d5c  mov     ecx, 7FFFFFFEh
0x180021d61  test    rcx, rcx
0x180021d64  jz      short loc_180021D82
0x180021d66  movzx   eax, word ptr [rbx]
0x180021d69  test    ax, ax
0x180021d6c  jz      short loc_180021D82
0x180021d6e  mov     [rdx], ax
0x180021d71  add     rbx, 2
0x180021d75  add     rdx, 2
0x180021d79  dec     rcx
0x180021d7c  sub     rdi, 1
0x180021d80  jnz     short loc_180021D61
0x180021d82  test    rdi, rdi
0x180021d85  lea     rcx, [rdx-2]
0x180021d89  mov     ebx, 8007007Ah
0x180021d8e  cmovnz  rcx, rdx
0x180021d92  cmovnz  ebx, r14d
0x180021d96  mov     [rcx], r14w
0x180021d9a  jnz     short loc_180021DE6
0x180021d9c  mov     rcx, [rbp+5Fh]; this
0x180021da0  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021da7  mov     r9d, ebx; char *
0x180021daa  mov     edx, 0E8h; void *
0x180021daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021db4  mov     eax, ebx
0x180021db6  mov     r15, [rsp+0A0h+arg_10]
0x180021dbe  mov     rdi, [rsp+0A0h+arg_8]
0x180021dc6  mov     rcx, [rbp+57h+var_20]
0x180021dca  xor     rcx, rsp; StackCookie
0x180021dcd  call    __security_check_cookie
0x180021dd2  mov     rbx, [rsp+0A0h+arg_18]
0x180021dda  add     rsp, 90h
0x180021de1  pop     r14
0x180021de3  pop     rsi
0x180021de4  pop     rbp
0x180021de5  retn
0x180021de6  mov     rcx, [rsi+10h]; lpFileName
0x180021dea  xor     r9d, r9d; lpSecurityAttributes
0x180021ded  mov     [rsp+0A0h+hTemplateFile], r14; hTemplateFile
0x180021df2  mov     r8d, 1; dwShareMode
0x180021df8  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180021e00  mov     edx, r15d; dwDesiredAccess
0x180021e03  mov     [rsp+0A0h+dwCreationDisposition], 3; int
0x180021e0b  call    cs:__imp_CreateFileW
0x180021e11  mov     rbx, rax
0x180021e14  mov     rax, [rsi+18h]
0x180021e18  lea     rcx, [rax-1]; this
0x180021e1c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180021e20  jbe     loc_180022250
0x180021e26  mov     [rsi+18h], rbx
0x180021e2a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180021e2e  jz      loc_180021F78
0x180021e34  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180021e38  mov     rcx, rbx; hFile
0x180021e3b  call    cs:__imp_GetFileInformationByHandle
0x180021e41  test    eax, eax
0x180021e43  jz      loc_18002225D
0x180021e49  cmp     [rbp+57h+FileInformation.nFileSizeHigh], r14d
0x180021e4d  jz      short loc_180021E74
0x180021e4f  mov     rcx, [rbp+5Fh]; this
0x180021e53  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021e5a  mov     r9d, 80070057h; char *
0x180021e60  mov     edx, 0F1h; void *
0x180021e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e6a  mov     eax, 80070057h
0x180021e6f  jmp     loc_180021DB6
0x180021e74  mov     rcx, [rsi+18h]; hFile
0x180021e78  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021e7c  mov     r8d, 18h; nNumberOfBytesToRead
0x180021e82  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x180021e87  lea     rdx, [rsi+20h]; lpBuffer
0x180021e8b  call    cs:__imp_ReadFile
0x180021e91  test    eax, eax
0x180021e93  jz      loc_1800221D8
0x180021e99  cmp     [rbp+57h+NumberOfBytesRead], 18h
0x180021e9d  jnz     loc_180022016
0x180021ea3  mov     ecx, [rsi+24h]
0x180021ea6  test    ecx, ecx
0x180021ea8  jz      loc_180021FF1
0x180021eae  cmp     ecx, 1
0x180021eb1  jz      loc_180022277
0x180021eb7  cmp     ecx, 2
0x180021eba  jnb     loc_18002206D
0x180021ec0  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x180021ec3  cmp     [rsi+30h], eax
0x180021ec6  jnb     loc_180021FCC
0x180021ecc  cmp     [rsi+34h], r14d
0x180021ed0  jz      loc_180021FA7
0x180021ed6  mov     edx, [rsi+2Ch]; lDistanceToMove
0x180021ed9  xor     r9d, r9d; dwMoveMethod
0x180021edc  mov     rcx, [rsi+18h]; hFile
0x180021ee0  xor     r8d, r8d; lpDistanceToMoveHigh
0x180021ee3  call    cs:__imp_SetFilePointer
0x180021ee9  cmp     eax, 0FFFFFFFFh
0x180021eec  jz      loc_180021F82
0x180021ef2  mov     ecx, [rsi+30h]; unsigned __int64
0x180021ef5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021efc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180021f01  mov     rcx, [rsi+2E8h]; Block
0x180021f08  mov     [rsi+2E8h], rax
0x180021f0f  test    rcx, rcx
0x180021f12  jnz     loc_18002230E
0x180021f18  mov     rdx, [rsi+2E8h]; lpBuffer
0x180021f1f  test    rdx, rdx
0x180021f22  jz      loc_180022318
0x180021f28  mov     r8d, [rsi+30h]; nNumberOfBytesToRead
0x180021f2c  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021f30  mov     rcx, [rsi+18h]; hFile
0x180021f34  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x180021f39  call    cs:__imp_ReadFile
0x180021f3f  test    eax, eax
0x180021f41  jz      loc_18002233D
0x180021f47  mov     eax, [rsi+30h]
0x180021f4a  cmp     [rbp+57h+NumberOfBytesRead], eax
0x180021f4d  jz      loc_18002203B
0x180021f53  mov     rcx, [rbp+5Fh]; this
0x180021f57  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021f5e  mov     r9d, 80070057h; char *
0x180021f64  mov     edx, 122h; void *
0x180021f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f6e  mov     eax, 80070057h
0x180021f73  jmp     loc_180021DB6
0x180021f78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021f7d  jmp     loc_180021DB6
0x180021f82  mov     rcx, [rbp+5Fh]; this
0x180021f86  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021f8d  mov     r9d, 8000FFFFh; char *
0x180021f93  mov     edx, 11Bh; void *
0x180021f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f9d  mov     eax, 8000FFFFh
0x180021fa2  jmp     loc_180021DB6
0x180021fa7  mov     rcx, [rbp+5Fh]; this
0x180021fab  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021fb2  mov     r9d, 80070057h; char *
0x180021fb8  mov     edx, 118h; void *
0x180021fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fc2  mov     eax, 80070057h
0x180021fc7  jmp     loc_180021DB6
0x180021fcc  mov     rcx, [rbp+5Fh]; this
0x180021fd0  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021fd7  mov     r9d, 80070057h; char *
0x180021fdd  mov     edx, 117h; void *
0x180021fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fe7  mov     eax, 80070057h
0x180021fec  jmp     loc_180021DB6
0x180021ff1  mov     rcx, [rbp+5Fh]; this
0x180021ff5  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180021ffc  mov     r9d, 80070057h; char *
0x180022002  mov     edx, 0F8h; void *
0x180022007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002200c  mov     eax, 80070057h
0x180022011  jmp     loc_180021DB6
0x180022016  mov     rcx, [rbp+5Fh]; this
0x18002201a  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022021  mov     r9d, 80070057h; char *
0x180022027  mov     edx, 0F4h; void *
0x18002202c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022031  mov     eax, 80070057h
0x180022036  jmp     loc_180021DB6
0x18002203b  xor     edx, edx
0x18002203d  mov     rcx, rsi; this
0x180022040  div     dword ptr [rsi+34h]
0x180022043  mov     edx, [rbp+57h+FileInformation.nFileSizeLow]; unsigned int
0x180022046  mov     [rsi+320h], eax
0x18002204c  call    ?ValidateKGL@CQueryKnownGameList@@AEAAJK@Z; CQueryKnownGameList::ValidateKGL(ulong)
0x180022051  mov     ebx, eax
0x180022053  cmp     eax, 80070057h
0x180022058  jz      loc_180021E6A
0x18002205e  test    eax, eax
0x180022060  js      loc_180022357
0x180022066  xor     eax, eax
0x180022068  jmp     loc_180021DB6
0x18002206d  mov     rcx, [rsi+18h]; hFile
0x180022071  lea     rdx, [rsi+38h]; lpBuffer
0x180022075  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180022079  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x18002207e  mov     r8d, 8; nNumberOfBytesToRead
0x180022084  call    cs:__imp_ReadFile
0x18002208a  test    eax, eax
0x18002208c  jz      loc_1800222A6
0x180022092  cmp     [rbp+57h+NumberOfBytesRead], 8
0x180022096  jz      short loc_1800220BD
0x180022098  mov     rcx, [rbp+5Fh]; this
0x18002209c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800220a3  mov     r9d, 80070057h; char *
0x1800220a9  mov     edx, 102h; void *
0x1800220ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220b3  mov     eax, 80070057h
0x1800220b8  jmp     loc_180021DB6
0x1800220bd  cmp     dword ptr [rsi+24h], 3
0x1800220c1  jb      loc_180021EC0
0x1800220c7  mov     rcx, [rsi+18h]; hFile
0x1800220cb  lea     rdx, [rsi+40h]; lpBuffer
0x1800220cf  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800220d3  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x1800220d8  mov     r8d, 298h; nNumberOfBytesToRead
0x1800220de  call    cs:__imp_ReadFile
0x1800220e4  test    eax, eax
0x1800220e6  jz      loc_1800222C0
0x1800220ec  cmp     [rbp+57h+NumberOfBytesRead], 298h
0x1800220f3  jz      short loc_18002211A
0x1800220f5  mov     rcx, [rbp+5Fh]; this
0x1800220f9  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022100  mov     r9d, 80070057h; char *
0x180022106  mov     edx, 107h; void *
0x18002210b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022110  mov     eax, 80070057h
0x180022115  jmp     loc_180021DB6
0x18002211a  cmp     dword ptr [rsi+24h], 4
0x18002211e  jb      loc_180021EC0
0x180022124  mov     rcx, [rsi+18h]; hFile
0x180022128  lea     rdx, [rsi+2D8h]; lpBuffer
0x18002212f  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180022133  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x180022138  mov     r8d, 8; nNumberOfBytesToRead
0x18002213e  call    cs:__imp_ReadFile
0x180022144  test    eax, eax
0x180022146  jz      loc_1800222DA
0x18002214c  cmp     [rbp+57h+NumberOfBytesRead], 8
0x180022150  jnz     short loc_1800221B3
0x180022152  cmp     dword ptr [rsi+24h], 5
0x180022156  jb      loc_180021EC0
0x18002215c  mov     rcx, [rsi+18h]; hFile
0x180022160  lea     rdx, [rsi+2E0h]; lpBuffer
0x180022167  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002216b  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x180022170  mov     r8d, 4; nNumberOfBytesToRead
0x180022176  call    cs:__imp_ReadFile
0x18002217c  test    eax, eax
0x18002217e  jz      loc_1800222F4
0x180022184  cmp     [rbp+57h+NumberOfBytesRead], 4
0x180022188  jz      loc_180021EC0
0x18002218e  mov     rcx, [rbp+5Fh]; this
0x180022192  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022199  mov     r9d, 80070057h; char *
0x18002219f  mov     edx, 111h; void *
0x1800221a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221a9  mov     eax, 80070057h
0x1800221ae  jmp     loc_180021DB6
0x1800221b3  mov     rcx, [rbp+5Fh]; this
0x1800221b7  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800221be  mov     r9d, 80070057h; char *
0x1800221c4  mov     edx, 10Ch; void *
0x1800221c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
