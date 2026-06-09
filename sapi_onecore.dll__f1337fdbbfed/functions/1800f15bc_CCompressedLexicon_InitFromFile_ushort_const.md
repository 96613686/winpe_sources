# CCompressedLexicon::InitFromFile(ushort const *)

- ea: `0x1800f15bc`
- end: `0x1800f19a3`
- name: `?InitFromFile@CCompressedLexicon@@QEAAJPEBG@Z`
- size: `999`
- prototype: `__int64 __fastcall(CCompressedLexicon *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f1a90`

## callees

- `0x180045938`
- `0x1800679fc`
- `0x180079e30`
- `0x18007aae4`
- `0x18007d31c`
- `0x18007d7a5`
- `0x1800f1084`
- `0x1800f15bc`
- `0x1800f1b60`
- `0x18025a3f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f16bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f16bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f163d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f16ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f163d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f16ea`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800f167c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800f167c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800f170a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800f170a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800f1794`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800f1794`

## pseudocode

```c
__int64 __fastcall CCompressedLexicon::InitFromFile(CCompressedLexicon *this, LPCWSTR lpFileName)
{
  int Win32Error; // ebx
  HANDLE FileW; // rax
  void *v7; // rcx
  void *v8; // rcx
  HANDLE v9; // rax
  DWORD FileSize; // eax
  unsigned int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  unsigned __int64 v14; // rbp
  void *FileMapping; // rax
  LPVOID v16; // rax
  CCompressedLexicon *v17; // rcx
  unsigned __int8 *v18; // rdx
  unsigned __int8 *v19; // r14
  unsigned __int8 *v20; // r15
  unsigned __int8 *v21; // r12
  unsigned __int8 *v22; // rcx
  __int64 v23; // rax
  unsigned __int8 *v24; // r8
  CHuffDecoder *v25; // rax
  CHuffDecoder *v26; // rcx
  CHuffDecoder *v27; // rax
  CHuffDecoder *v28; // rcx
  CHuffDecoder *v29; // rax
  CHuffDecoder *v30; // rcx
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-C8h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE Buffer[80]; // [rsp+50h] [rbp-98h] BYREF

  if ( *((_QWORD *)this + 11) )
    return 2147766274LL;
  Win32Error = 0;
  memset_0(Buffer, 0, 0x48u);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  *((_QWORD *)this + 11) = FileW;
  if ( FileW != (HANDLE)-1LL || (Win32Error = SpHrFromLastWin32Error(), Win32Error >= 0) )
  {
    v7 = (void *)*((_QWORD *)this + 11);
    NumberOfBytesRead = 0;
    if ( ReadFile(v7, Buffer, 0x48u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead != 72 )
      {
        Win32Error = -2147200891;
        goto LABEL_10;
      }
    }
    else
    {
      Win32Error = SpHrFromLastWin32Error();
    }
    if ( Win32Error >= 0 && memcmp_0(Buffer, &guidLkupValidationId, 0x10u) )
      Win32Error = -2147200891;
  }
LABEL_10:
  v8 = (void *)*((_QWORD *)this + 11);
  if ( v8 != (void *)-1LL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 11) = 0;
  }
  if ( Win32Error < 0 )
    goto LABEL_17;
  v9 = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  *((_QWORD *)this + 11) = v9;
  if ( v9 == (HANDLE)-1LL )
  {
    Win32Error = SpHrFromLastWin32Error();
    if ( Win32Error < 0 )
      goto LABEL_17;
  }
  FileSize = GetFileSize(*((HANDLE *)this + 11), 0);
  v14 = FileSize;
  if ( FileSize == -1 )
  {
    Win32Error = -2147024809;
  }
  else
  {
    FileMapping = SpCreateFileMapping(
                    *((HANDLE *)this + 11),
                    v11,
                    v12,
                    v13,
                    dwCreationDisposition,
                    dwFlagsAndAttributes);
    *((_QWORD *)this + 12) = FileMapping;
    if ( !FileMapping )
    {
      Win32Error = SpHrFromLastWin32Error();
      if ( Win32Error < 0 )
        goto LABEL_17;
    }
    v16 = MapViewOfFile(*((HANDLE *)this + 12), 4u, 0, 0, 0);
    *((_QWORD *)this + 13) = v16;
    if ( !v16 )
    {
      Win32Error = SpHrFromLastWin32Error();
      if ( Win32Error < 0 )
        goto LABEL_17;
    }
    Win32Error = CCompressedLexicon::ValidateHeader(v17, *((unsigned __int8 **)this + 13), v14);
    if ( Win32Error < 0 )
      goto LABEL_17;
    v18 = (unsigned __int8 *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 18) = v18;
    v19 = v18 + 72;
    v20 = &v18[*((unsigned int *)v18 + 15) + 72];
    v21 = &v20[*((unsigned int *)v18 + 16)];
    v22 = &v21[*((unsigned int *)v18 + 17)];
    *((_QWORD *)this + 14) = v22;
    v23 = (unsigned int)(*((_DWORD *)v18 + 13) * *((_DWORD *)v18 + 12) + 7) >> 3;
    *((_DWORD *)this + 30) = v23;
    v24 = &v22[v23];
    *((_QWORD *)this + 16) = &v22[v23];
    if ( &v22[v23] < v18 || v24 - v18 > v14 )
      Win32Error = -2147200891;
    else
      *((_DWORD *)this + 34) = (unsigned int)(v14 + (_DWORD)v18 - (_DWORD)v24) >> 2;
    *((_DWORD *)this + 31) = ~(-1 << *((_DWORD *)v18 + 13));
    if ( Win32Error < 0 )
      goto LABEL_17;
    v25 = (CHuffDecoder *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    if ( v25 )
    {
      *((_BYTE *)v25 + 48) = 0;
      *(_QWORD *)v25 = 0;
      *((_DWORD *)v25 + 2) = 0;
      *((_QWORD *)v25 + 2) = 0;
      *((_QWORD *)v25 + 3) = 0;
      *((_QWORD *)v25 + 4) = 0;
    }
    else
    {
      v26 = 0;
    }
    *((_QWORD *)this + 19) = v26;
    if ( !v26 )
      goto LABEL_35;
    Win32Error = CHuffDecoder::Initialize(
                   v26,
                   v19,
                   *(_DWORD *)(*((_QWORD *)this + 18) + 60LL),
                   *((unsigned int **)this + 16),
                   *((_DWORD *)this + 34));
    if ( Win32Error < 0 )
      goto LABEL_17;
    v27 = (CHuffDecoder *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v27;
    if ( v27 )
    {
      *((_BYTE *)v27 + 48) = 0;
      *(_QWORD *)v27 = 0;
      *((_DWORD *)v27 + 2) = 0;
      *((_QWORD *)v27 + 2) = 0;
      *((_QWORD *)v27 + 3) = 0;
      *((_QWORD *)v27 + 4) = 0;
    }
    else
    {
      v28 = 0;
    }
    *((_QWORD *)this + 20) = v28;
    if ( !v28 )
      goto LABEL_35;
    Win32Error = CHuffDecoder::Initialize(
                   v28,
                   v20,
                   *(_DWORD *)(*((_QWORD *)this + 18) + 64LL),
                   *((unsigned int **)this + 16),
                   *((_DWORD *)this + 34));
    if ( Win32Error < 0 )
      goto LABEL_17;
    v29 = (CHuffDecoder *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v29;
    if ( v29 )
    {
      *((_BYTE *)v29 + 48) = 0;
      *(_QWORD *)v29 = 0;
      *((_DWORD *)v29 + 2) = 0;
      *((_QWORD *)v29 + 2) = 0;
      *((_QWORD *)v29 + 3) = 0;
      *((_QWORD *)v29 + 4) = 0;
    }
    else
    {
      v30 = 0;
    }
    *((_QWORD *)this + 21) = v30;
    if ( v30 )
    {
      Win32Error = CHuffDecoder::Initialize(
                     v30,
                     v21,
                     *(_DWORD *)(*((_QWORD *)this + 18) + 68LL),
                     *((unsigned int **)this + 16),
                     *((_DWORD *)this + 34));
      if ( Win32Error >= 0 )
      {
        *((_BYTE *)this + 72) = 1;
        return (unsigned int)Win32Error;
      }
    }
    else
    {
LABEL_35:
      Win32Error = -2147024882;
    }
  }
LABEL_17:
  CCompressedLexicon::CleanUp(this);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800f15bc  mov     [rsp+arg_10], rbx
0x1800f15c1  push    rbp
0x1800f15c2  push    rsi
0x1800f15c3  push    rdi
0x1800f15c4  push    r12
0x1800f15c6  push    r13
0x1800f15c8  push    r14
0x1800f15ca  push    r15
0x1800f15cc  sub     rsp, 0B0h
0x1800f15d3  mov     rax, cs:__security_cookie
0x1800f15da  xor     rax, rsp
0x1800f15dd  mov     [rsp+0E8h+var_48], rax
0x1800f15e5  xor     r13d, r13d
0x1800f15e8  mov     rbp, rdx
0x1800f15eb  mov     rdi, rcx
0x1800f15ee  cmp     [rcx+58h], r13
0x1800f15f2  jz      short loc_1800F15FE
0x1800f15f4  mov     eax, 80045002h
0x1800f15f9  jmp     loc_1800F1726
0x1800f15fe  mov     r14d, 48h ; 'H'
0x1800f1604  lea     rcx, [rsp+0E8h+Buffer]; void *
0x1800f1609  mov     r8d, r14d; Size
0x1800f160c  xor     edx, edx; Val
0x1800f160e  mov     ebx, r13d
0x1800f1611  call    memset_0
0x1800f1616  mov     [rsp+0E8h+hTemplateFile], r13; hTemplateFile
0x1800f161b  lea     r8d, [r14-47h]; dwShareMode
0x1800f161f  mov     r12d, 10000080h
0x1800f1625  xor     r9d, r9d; lpSecurityAttributes
0x1800f1628  mov     [rsp+0E8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800f162d  mov     edx, 80000000h; dwDesiredAccess
0x1800f1632  mov     rcx, rbp; lpFileName
0x1800f1635  mov     [rsp+0E8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800f163d  call    cs:__imp_CreateFileW
0x1800f1643  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f1647  mov     [rdi+58h], rax
0x1800f164b  mov     r15d, 80045085h
0x1800f1651  cmp     rax, rsi
0x1800f1654  jnz     short loc_1800F1661
0x1800f1656  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f165b  mov     ebx, eax
0x1800f165d  test    eax, eax
0x1800f165f  js      short loc_1800F16B2
0x1800f1661  mov     rcx, [rdi+58h]; hFile
0x1800f1665  lea     r9, [rsp+0E8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f166a  mov     r8d, r14d; nNumberOfBytesToRead
0x1800f166d  mov     [rsp+0E8h+NumberOfBytesRead], r13d
0x1800f1672  lea     rdx, [rsp+0E8h+Buffer]; lpBuffer
0x1800f1677  mov     qword ptr [rsp+0E8h+dwCreationDisposition], r13; lpOverlapped
0x1800f167c  call    cs:__imp_ReadFile
0x1800f1682  test    eax, eax
0x1800f1684  jnz     loc_1800F1751
0x1800f168a  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f168f  mov     ebx, eax
0x1800f1691  test    ebx, ebx
0x1800f1693  js      short loc_1800F16B2
0x1800f1695  mov     r8d, 10h; Size
0x1800f169b  lea     rdx, guidLkupValidationId; Buf2
0x1800f16a2  lea     rcx, [rsp+0E8h+Buffer]; Buf1
0x1800f16a7  call    memcmp_0
0x1800f16ac  test    eax, eax
0x1800f16ae  cmovnz  ebx, r15d
0x1800f16b2  mov     rcx, [rdi+58h]; hObject
0x1800f16b6  cmp     rcx, rsi
0x1800f16b9  jz      short loc_1800F16C5
0x1800f16bb  call    cs:__imp_CloseHandle
0x1800f16c1  mov     [rdi+58h], r13
0x1800f16c5  test    ebx, ebx
0x1800f16c7  js      short loc_1800F171C
0x1800f16c9  xor     r9d, r9d; lpSecurityAttributes
0x1800f16cc  mov     [rsp+0E8h+hTemplateFile], r13; hTemplateFile
0x1800f16d1  mov     [rsp+0E8h+dwFlagsAndAttributes], r12d; unsigned int
0x1800f16d6  mov     edx, 80000000h; dwDesiredAccess
0x1800f16db  mov     rcx, rbp; lpFileName
0x1800f16de  mov     [rsp+0E8h+dwCreationDisposition], 3; unsigned __int16 *
0x1800f16e6  lea     r8d, [r9+1]; dwShareMode
0x1800f16ea  call    cs:__imp_CreateFileW
0x1800f16f0  mov     [rdi+58h], rax
0x1800f16f4  cmp     rax, rsi
0x1800f16f7  jnz     short loc_1800F1704
0x1800f16f9  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f16fe  mov     ebx, eax
0x1800f1700  test    eax, eax
0x1800f1702  js      short loc_1800F171C
0x1800f1704  mov     rcx, [rdi+58h]; hFile
0x1800f1708  xor     edx, edx; lpFileSizeHigh
0x1800f170a  call    cs:__imp_GetFileSize
0x1800f1710  mov     ebp, eax
0x1800f1712  cmp     eax, 0FFFFFFFFh
0x1800f1715  jnz     short loc_1800F1764
0x1800f1717  mov     ebx, 80070057h
0x1800f171c  mov     rcx, rdi; this
0x1800f171f  call    ?CleanUp@CCompressedLexicon@@AEAAXXZ; CCompressedLexicon::CleanUp(void)
0x1800f1724  mov     eax, ebx
0x1800f1726  mov     rcx, [rsp+0E8h+var_48]
0x1800f172e  xor     rcx, rsp; StackCookie
0x1800f1731  call    __security_check_cookie
0x1800f1736  mov     rbx, [rsp+0E8h+arg_10]
0x1800f173e  add     rsp, 0B0h
0x1800f1745  pop     r15
0x1800f1747  pop     r14
0x1800f1749  pop     r13
0x1800f174b  pop     r12
0x1800f174d  pop     rdi
0x1800f174e  pop     rsi
0x1800f174f  pop     rbp
0x1800f1750  retn
0x1800f1751  cmp     [rsp+0E8h+NumberOfBytesRead], r14d
0x1800f1756  jz      loc_1800F1691
0x1800f175c  mov     ebx, r15d
0x1800f175f  jmp     loc_1800F16B2
0x1800f1764  mov     rcx, [rdi+58h]; hFile
0x1800f1768  call    ?SpCreateFileMapping@@YAPEAXPEAXKKKPEBGK@Z; SpCreateFileMapping(void *,ulong,ulong,ulong,ushort const *,ulong)
0x1800f176d  mov     [rdi+60h], rax
0x1800f1771  test    rax, rax
0x1800f1774  jnz     short loc_1800F1781
0x1800f1776  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f177b  mov     ebx, eax
0x1800f177d  test    eax, eax
0x1800f177f  js      short loc_1800F171C
0x1800f1781  mov     rcx, [rdi+60h]; hFileMappingObject
0x1800f1785  xor     r9d, r9d; dwFileOffsetLow
0x1800f1788  xor     r8d, r8d; dwFileOffsetHigh
0x1800f178b  mov     qword ptr [rsp+0E8h+dwCreationDisposition], r13; dwNumberOfBytesToMap
0x1800f1790  lea     edx, [r9+4]; dwDesiredAccess
0x1800f1794  call    cs:__imp_MapViewOfFile
0x1800f179a  mov     [rdi+68h], rax
0x1800f179e  test    rax, rax
0x1800f17a1  jnz     short loc_1800F17B2
0x1800f17a3  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f17a8  mov     ebx, eax
0x1800f17aa  test    eax, eax
0x1800f17ac  js      loc_1800F171C
0x1800f17b2  mov     rdx, [rdi+68h]; unsigned __int8 *
0x1800f17b6  mov     r8d, ebp; unsigned int
0x1800f17b9  call    ?ValidateHeader@CCompressedLexicon@@AEAAJPEAEK@Z; CCompressedLexicon::ValidateHeader(uchar *,ulong)
0x1800f17be  mov     ebx, eax
0x1800f17c0  test    eax, eax
0x1800f17c2  js      loc_1800F171C
0x1800f17c8  mov     rdx, [rdi+68h]
0x1800f17cc  mov     [rdi+90h], rdx
0x1800f17d3  mov     r15d, [rdx+3Ch]
0x1800f17d7  lea     r14, [rdx+48h]
0x1800f17db  mov     r12d, [rdx+40h]
0x1800f17df  add     r15, r14
0x1800f17e2  mov     ecx, [rdx+44h]
0x1800f17e5  add     r12, r15
0x1800f17e8  add     rcx, r12
0x1800f17eb  mov     [rdi+70h], rcx
0x1800f17ef  mov     eax, [rdx+30h]
0x1800f17f2  imul    eax, [rdx+34h]
0x1800f17f6  add     eax, 7
0x1800f17f9  shr     eax, 3
0x1800f17fc  mov     [rdi+78h], eax
0x1800f17ff  lea     r8, [rax+rcx]
0x1800f1803  mov     [rdi+80h], r8
0x1800f180a  cmp     r8, rdx
0x1800f180d  jb      short loc_1800F182C
0x1800f180f  mov     rcx, r8
0x1800f1812  sub     rcx, rdx
0x1800f1815  cmp     rcx, rbp
0x1800f1818  ja      short loc_1800F182C
0x1800f181a  mov     eax, edx
0x1800f181c  sub     eax, r8d
0x1800f181f  add     eax, ebp
0x1800f1821  shr     eax, 2
0x1800f1824  mov     [rdi+88h], eax
0x1800f182a  jmp     short loc_1800F1831
0x1800f182c  mov     ebx, 80045085h
0x1800f1831  mov     ecx, [rdx+34h]
0x1800f1834  shl     esi, cl
0x1800f1836  not     esi
0x1800f1838  mov     [rdi+7Ch], esi
0x1800f183b  test    ebx, ebx
0x1800f183d  js      loc_1800F171C
0x1800f1843  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800f184a  mov     ebp, 38h ; '8'
0x1800f184f  mov     rdx, rsi; struct std::nothrow_t *
0x1800f1852  mov     ecx, ebp; unsigned __int64
0x1800f1854  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f1859  mov     rcx, rax
0x1800f185c  test    rax, rax
0x1800f185f  jz      short loc_1800F187B
0x1800f1861  mov     [rax+30h], r13b
0x1800f1865  xor     eax, eax
0x1800f1867  mov     [rcx], rax
0x1800f186a  mov     [rcx+8], eax
0x1800f186d  mov     [rcx+10h], r13
0x1800f1871  mov     [rcx+18h], r13
0x1800f1875  mov     [rcx+20h], r13
0x1800f1879  jmp     short loc_1800F187E
0x1800f187b  mov     rcx, r13; this
0x1800f187e  mov     [rdi+98h], rcx
0x1800f1885  test    rcx, rcx
0x1800f1888  jnz     short loc_1800F1894
0x1800f188a  mov     ebx, 8007000Eh
0x1800f188f  jmp     loc_1800F171C
0x1800f1894  mov     r8, [rdi+90h]
0x1800f189b  mov     rdx, r14; unsigned __int8 *
0x1800f189e  mov     eax, [rdi+88h]
0x1800f18a4  mov     r9, [rdi+80h]; unsigned int *
0x1800f18ab  mov     [rsp+0E8h+dwCreationDisposition], eax; unsigned int
0x1800f18af  mov     r8d, [r8+3Ch]; unsigned int
0x1800f18b3  call    ?Initialize@CHuffDecoder@@QEAAJPEAEKPEAKK@Z; CHuffDecoder::Initialize(uchar *,ulong,ulong *,ulong)
0x1800f18b8  mov     ebx, eax
0x1800f18ba  test    eax, eax
0x1800f18bc  js      loc_1800F171C
0x1800f18c2  mov     rdx, rsi; struct std::nothrow_t *
0x1800f18c5  mov     rcx, rbp; unsigned __int64
0x1800f18c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f18cd  mov     rcx, rax
0x1800f18d0  test    rax, rax
0x1800f18d3  jz      short loc_1800F18EF
0x1800f18d5  mov     [rax+30h], r13b
0x1800f18d9  xor     eax, eax
0x1800f18db  mov     [rcx], rax
0x1800f18de  mov     [rcx+8], eax
0x1800f18e1  mov     [rcx+10h], r13
0x1800f18e5  mov     [rcx+18h], r13
0x1800f18e9  mov     [rcx+20h], r13
0x1800f18ed  jmp     short loc_1800F18F2
0x1800f18ef  mov     rcx, r13; this
0x1800f18f2  mov     [rdi+0A0h], rcx
0x1800f18f9  test    rcx, rcx
0x1800f18fc  jz      short loc_1800F188A
0x1800f18fe  mov     r8, [rdi+90h]
0x1800f1905  mov     rdx, r15; unsigned __int8 *
0x1800f1908  mov     eax, [rdi+88h]
0x1800f190e  mov     r9, [rdi+80h]; unsigned int *
0x1800f1915  mov     [rsp+0E8h+dwCreationDisposition], eax; unsigned int
0x1800f1919  mov     r8d, [r8+40h]; unsigned int
0x1800f191d  call    ?Initialize@CHuffDecoder@@QEAAJPEAEKPEAKK@Z; CHuffDecoder::Initialize(uchar *,ulong,ulong *,ulong)
0x1800f1922  mov     ebx, eax
0x1800f1924  test    eax, eax
0x1800f1926  js      loc_1800F171C
0x1800f192c  mov     rdx, rsi; struct std::nothrow_t *
0x1800f192f  mov     rcx, rbp; unsigned __int64
0x1800f1932  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f1937  mov     rcx, rax
0x1800f193a  test    rax, rax
0x1800f193d  jz      short loc_1800F1959
0x1800f193f  mov     [rax+30h], r13b
0x1800f1943  xor     eax, eax
0x1800f1945  mov     [rcx], rax
0x1800f1948  mov     [rcx+8], eax
0x1800f194b  mov     [rcx+10h], r13
0x1800f194f  mov     [rcx+18h], r13
0x1800f1953  mov     [rcx+20h], r13
0x1800f1957  jmp     short loc_1800F195C
0x1800f1959  mov     rcx, r13; this
0x1800f195c  mov     [rdi+0A8h], rcx
0x1800f1963  test    rcx, rcx
0x1800f1966  jz      loc_1800F188A
0x1800f196c  mov     r8, [rdi+90h]
0x1800f1973  mov     rdx, r12; unsigned __int8 *
0x1800f1976  mov     eax, [rdi+88h]
0x1800f197c  mov     r9, [rdi+80h]; unsigned int *
0x1800f1983  mov     [rsp+0E8h+dwCreationDisposition], eax; unsigned int
0x1800f1987  mov     r8d, [r8+44h]; unsigned int
0x1800f198b  call    ?Initialize@CHuffDecoder@@QEAAJPEAEKPEAKK@Z; CHuffDecoder::Initialize(uchar *,ulong,ulong *,ulong)
0x1800f1990  mov     ebx, eax
0x1800f1992  test    eax, eax
0x1800f1994  js      loc_1800F171C
0x1800f199a  mov     byte ptr [rdi+48h], 1
0x1800f199e  jmp     loc_1800F1724
```
