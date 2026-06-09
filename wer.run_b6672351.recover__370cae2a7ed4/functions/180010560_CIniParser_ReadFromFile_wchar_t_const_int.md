# CIniParser::ReadFromFile(wchar_t const *,int)

- ea: `0x180010560`
- end: `0x180010b5e`
- name: `?ReadFromFile@CIniParser@@QEAAJPEB_WH@Z`
- size: `1534`
- prototype: `int(CIniParser *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180075cc0`

## callees

- `0x180004c64`
- `0x180007514`
- `0x180009464`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000db80`
- `0x18000f1bc`
- `0x180010560`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x18002d96c`
- `0x1800404ac`
- `0x18009de80`
- `0x18009dee0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010acb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800106fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800106fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010766`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010643`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010643`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010756`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010756`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800105c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800105c7`

## pseudocode

```c
__int64 __fastcall CIniParser::ReadFromFile(CIniParser *this, const wchar_t *a2, int a3)
{
  HANDLE FileW; // r15
  __int64 v5; // rcx
  DWORD LastError; // eax
  unsigned int v7; // ebx
  wchar_t *v8; // rcx
  int v9; // edx
  DWORD v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r14
  DWORD v15; // eax
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // r9
  DWORD v20; // r13d
  unsigned __int16 *v21; // rbx
  char *v22; // rcx
  unsigned __int16 *v23; // rdi
  __int64 v24; // rax
  _WORD *v25; // rbx
  _WORD *v26; // rdx
  unsigned __int16 *v27; // rsi
  int v28; // ecx
  int v29; // edx
  unsigned __int16 *v30; // rax
  int v31; // ecx
  int dwCreationDisposition; // [rsp+20h] [rbp-69h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-41h] BYREF
  int v36; // [rsp+4Ch] [rbp-3Dh]
  __int64 v37; // [rsp+50h] [rbp-39h]
  __int64 v38; // [rsp+58h] [rbp-31h]
  _QWORD v39[2]; // [rsp+60h] [rbp-29h] BYREF
  LPVOID lpMem[2]; // [rsp+70h] [rbp-19h] BYREF
  char v41; // [rsp+80h] [rbp-9h] BYREF
  char v42; // [rsp+90h] [rbp+7h] BYREF
  char v43[64]; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v45; // [rsp+F8h] [rbp+6Fh] BYREF
  int v46; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v47; // [rsp+108h] [rbp+7Fh]

  v46 = a3;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  if ( !a2 || !*a2 )
  {
    FileW = 0;
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
    goto LABEL_88;
  }
  CIniParser::~CIniParser(this);
  FileW = CreateFileW(a2, 1u, 1u, 0, 3u, 0x80u, 0);
  tlx::file_handle_traits::operator()(v5, 0);
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    LastError = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(LastError);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 22;
LABEL_7:
      WPP_SF_SD(*((_QWORD *)v8 + 2), v9, (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, (_DWORD)a2, v7);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  if ( GetFileSizeEx(FileW, &FileSize) )
  {
    if ( FileSize.QuadPart > 0x400000uLL )
    {
      v7 = -2147483637;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_DI(*((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_88;
    }
    if ( !FileSize.LowPart )
    {
      v7 = -2147024883;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v11 = 25;
      v12 = 2147942413LL;
      goto LABEL_17;
    }
    v13 = (unsigned __int16 *)HeapAlloc(g_hWerheap, 0, FileSize.LowPart);
    v14 = v13;
    if ( !v13 )
    {
      v7 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v11 = 26;
      v12 = 2147942414LL;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v8 + 2), v11, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v12);
      goto LABEL_88;
    }
    if ( !ReadFile(FileW, v13, FileSize.LowPart, &NumberOfBytesRead, 0) )
    {
      v15 = GetLastError();
      v7 = ERROR_HR_FROM_WIN32(v15);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_81;
      v17 = 27;
      v18 = v7;
      goto LABEL_26;
    }
    v19 = 0;
    v20 = NumberOfBytesRead >> 1;
    v21 = v14;
    v47 = 0;
    v45 = 0;
    v46 = 0;
    v36 = 0;
    if ( NumberOfBytesRead >> 1 && *v14 == 0xFEFF )
    {
      v36 = 1;
      v21 = v14 + 1;
      --v20;
    }
    while ( 2 )
    {
      if ( v21 && v20 )
      {
        do
        {
LABEL_32:
          if ( *v21 > 0x20u )
            break;
          ++v21;
          --v20;
        }
        while ( v20 );
        if ( v20 )
        {
          v22 = (char *)v21;
          v23 = v21;
          while ( *v21 != 61 )
          {
            if ( *v21 != 13 && *v21 != 10 )
            {
              ++v21;
              if ( --v20 )
                continue;
            }
            if ( !v20 )
              goto LABEL_71;
            if ( *v21 != 61 )
              goto LABEL_32;
            break;
          }
          v24 = (char *)v21 - v22;
          v25 = v21 + 1;
          v26 = v25;
          v27 = v25;
          while ( --v20 && *v25 != 13 && *v25 != 10 )
            ++v25;
          v38 = (unsigned int)(v25 - v26);
          v37 = (unsigned int)(v24 >> 1);
          v21 = &v26[v38];
          if ( v37 != 12 || (unsigned int)utl::_Char16TraitsBase<wchar_t>::compare(v23, L"MetadataHash", 12, v19) )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                    lpMem,
                                    v23) )
            {
              v39[1] = v38;
              v39[0] = v27;
              if ( *(_QWORD *)CStringMap::insert_or_assign(this, v43, lpMem, v39) )
              {
                if ( lpMem[0] != &v41 )
                  HeapFree(g_hWerheap, 0, lpMem[0]);
                v29 = 0;
                v30 = &v23[v37];
                while ( v23 != v30 )
                  v29 = *v23++ + 65599 * v29;
                v31 = 0;
                while ( v27 != v21 )
                  v31 = *v27++ + 65599 * v31;
                v19 = v31 + v29 + v47;
                v47 += v31 + v29;
                continue;
              }
            }
            v7 = -2147024882;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
                2147942414LL);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
          }
          else
          {
            v45 = 0;
            LOBYTE(v46) = 0;
            v18 = *(unsigned int *)(utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
                                      (unsigned int)&v42,
                                      (_DWORD)v27,
                                      (_DWORD)v21,
                                      (unsigned int)&v45,
                                      dwCreationDisposition,
                                      (__int64)&v46)
                                  + 8);
            if ( !(_DWORD)v18 )
            {
              v28 = (unsigned __int8)v46;
              if ( v45 <= (unsigned int)(unsigned __int8)v46 + 0x7FFFFFFF )
              {
                v19 = v47;
                v46 = 1;
                v45 = v28 + (v45 ^ -v28);
                continue;
              }
              v18 = 34;
            }
            v7 = -2147024809;
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v17 = 29;
              goto LABEL_26;
            }
          }
          goto LABEL_81;
        }
      }
      break;
    }
LABEL_71:
    if ( v36 )
    {
      if ( !v46 )
      {
        v7 = -2147023504;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_81;
        v17 = 30;
        v18 = 2147943792LL;
LABEL_26:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v18);
LABEL_81:
        HeapFree(g_hWerheap, 0, v14);
        goto LABEL_88;
      }
      if ( v45 != (_DWORD)v19 )
      {
        v7 = -2147023504;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_llD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
        goto LABEL_81;
      }
    }
    v7 = 0;
    goto LABEL_81;
  }
  v10 = GetLastError();
  v7 = ERROR_HR_FROM_WIN32(v10);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v9 = 23;
    goto LABEL_7;
  }
LABEL_88:
  tlx::file_handle_traits::operator()(v8, FileW);
  return v7;
}

```

## disassembly

```asm
0x180010560  mov     [rsp-8+arg_10], r8d
0x180010565  mov     [rsp-8+arg_0], rcx
0x18001056a  push    rbp
0x18001056b  push    rbx
0x18001056c  push    rsi
0x18001056d  push    rdi
0x18001056e  push    r13
0x180010570  push    r14
0x180010572  push    r15
0x180010574  lea     rbp, [rsp-27h]
0x180010579  sub     rsp, 0B0h
0x180010580  xor     esi, esi
0x180010582  mov     rdi, rdx
0x180010585  mov     [rbp+57h+NumberOfBytesRead], esi
0x180010588  mov     rax, rcx
0x18001058b  mov     qword ptr [rbp+57h+FileSize], rsi
0x18001058f  test    rdx, rdx
0x180010592  jz      loc_180010B0B
0x180010598  cmp     [rdx], si
0x18001059b  jz      loc_180010B0B
0x1800105a1  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x1800105a6  lea     edx, [rsi+1]; dwDesiredAccess
0x1800105a9  mov     [rsp+0E0h+hTemplateFile], rsi; hTemplateFile
0x1800105ae  mov     r8d, edx; dwShareMode
0x1800105b1  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800105b9  xor     r9d, r9d; lpSecurityAttributes
0x1800105bc  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800105c4  mov     rcx, rdi; lpFileName
0x1800105c7  call    cs:__imp_CreateFileW
0x1800105ce  nop     dword ptr [rax+rax+00h]
0x1800105d3  xor     edx, edx
0x1800105d5  mov     r15, rax
0x1800105d8  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x1800105dd  lea     rax, [r15+1]
0x1800105e1  cmp     rax, 1
0x1800105e5  ja      short loc_18001063C
0x1800105e7  call    cs:__imp_GetLastError
0x1800105ee  nop     dword ptr [rax+rax+00h]
0x1800105f3  mov     ecx, eax; unsigned int
0x1800105f5  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800105fa  mov     ebx, eax
0x1800105fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010603  lea     rax, WPP_GLOBAL_Control
0x18001060a  cmp     rcx, rax
0x18001060d  jz      loc_180010B41
0x180010613  test    byte ptr [rcx+1Ch], 1
0x180010617  jz      loc_180010B41
0x18001061d  lea     edx, [rsi+16h]
0x180010620  mov     rcx, [rcx+10h]
0x180010624  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18001062b  mov     r9, rdi
0x18001062e  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x180010632  call    WPP_SF_SD
0x180010637  jmp     loc_180010B41
0x18001063c  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x180010640  mov     rcx, r15; hFile
0x180010643  call    cs:__imp_GetFileSizeEx
0x18001064a  nop     dword ptr [rax+rax+00h]
0x18001064f  test    eax, eax
0x180010651  jnz     short loc_180010690
0x180010653  call    cs:__imp_GetLastError
0x18001065a  nop     dword ptr [rax+rax+00h]
0x18001065f  mov     ecx, eax; unsigned int
0x180010661  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010666  mov     ebx, eax
0x180010668  mov     rcx, cs:WPP_GLOBAL_Control
0x18001066f  lea     rax, WPP_GLOBAL_Control
0x180010676  cmp     rcx, rax
0x180010679  jz      loc_180010B41
0x18001067f  test    byte ptr [rcx+1Ch], 1
0x180010683  jz      loc_180010B41
0x180010689  mov     edx, 17h
0x18001068e  jmp     short loc_180010620
0x180010690  cmp     dword ptr [rbp+57h+FileSize+4], esi
0x180010693  jnz     loc_180010AD9
0x180010699  mov     eax, dword ptr [rbp+57h+FileSize]
0x18001069c  cmp     eax, 400000h
0x1800106a1  ja      loc_180010AD9
0x1800106a7  test    eax, eax
0x1800106a9  jnz     short loc_1800106F1
0x1800106ab  mov     ebx, 8007000Dh
0x1800106b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106b7  lea     rax, WPP_GLOBAL_Control
0x1800106be  cmp     rcx, rax
0x1800106c1  jz      loc_180010B41
0x1800106c7  test    byte ptr [rcx+1Ch], 1
0x1800106cb  jz      loc_180010B41
0x1800106d1  mov     edx, 19h
0x1800106d6  mov     r9d, 8007000Dh
0x1800106dc  mov     rcx, [rcx+10h]
0x1800106e0  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1800106e7  call    WPP_SF_d
0x1800106ec  jmp     loc_180010B41
0x1800106f1  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800106f8  mov     r8, rax; dwBytes
0x1800106fb  xor     edx, edx; dwFlags
0x1800106fd  call    cs:__imp_HeapAlloc
0x180010704  nop     dword ptr [rax+rax+00h]
0x180010709  mov     r14, rax
0x18001070c  test    rax, rax
0x18001070f  jnz     short loc_180010743
0x180010711  mov     ebx, 8007000Eh
0x180010716  mov     rcx, cs:WPP_GLOBAL_Control
0x18001071d  lea     rax, WPP_GLOBAL_Control
0x180010724  cmp     rcx, rax
0x180010727  jz      loc_180010B41
0x18001072d  test    byte ptr [rcx+1Ch], 1
0x180010731  jz      loc_180010B41
0x180010737  lea     edx, [r14+1Ah]
0x18001073b  mov     r9d, 8007000Eh
0x180010741  jmp     short loc_1800106DC
0x180010743  mov     r8d, dword ptr [rbp+57h+FileSize]; nNumberOfBytesToRead
0x180010747  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001074b  mov     rdx, r14; lpBuffer
0x18001074e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi; lpOverlapped
0x180010753  mov     rcx, r15; hFile
0x180010756  call    cs:__imp_ReadFile
0x18001075d  nop     dword ptr [rax+rax+00h]
0x180010762  test    eax, eax
0x180010764  jnz     short loc_1800107B9
0x180010766  call    cs:__imp_GetLastError
0x18001076d  nop     dword ptr [rax+rax+00h]
0x180010772  mov     ecx, eax; unsigned int
0x180010774  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010779  mov     ebx, eax
0x18001077b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010782  lea     rax, WPP_GLOBAL_Control
0x180010789  cmp     rcx, rax
0x18001078c  jz      loc_180010ABF
0x180010792  test    byte ptr [rcx+1Ch], 1
0x180010796  jz      loc_180010ABF
0x18001079c  mov     edx, 1Bh
0x1800107a1  mov     r9d, ebx
0x1800107a4  mov     rcx, [rcx+10h]
0x1800107a8  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1800107af  call    WPP_SF_d
0x1800107b4  jmp     loc_180010ABF
0x1800107b9  mov     r13d, [rbp+57h+NumberOfBytesRead]
0x1800107bd  mov     r9d, esi
0x1800107c0  shr     r13d, 1
0x1800107c3  mov     rbx, r14
0x1800107c6  mov     [rbp+57h+arg_18], esi
0x1800107c9  mov     [rbp+57h+arg_8], esi
0x1800107cc  mov     [rbp+57h+arg_10], esi
0x1800107cf  mov     [rbp+57h+var_94], esi
0x1800107d2  jz      short loc_1800107ED
0x1800107d4  mov     eax, 0FEFFh
0x1800107d9  cmp     [r14], ax
0x1800107dd  jnz     short loc_1800107ED
0x1800107df  mov     [rbp+57h+var_94], 1
0x1800107e6  lea     rbx, [r14+2]
0x1800107ea  dec     r13d
0x1800107ed  or      r8d, 0FFFFFFFFh
0x1800107f1  test    rbx, rbx
0x1800107f4  jz      loc_180010A41
0x1800107fa  test    r13d, r13d
0x1800107fd  jz      loc_180010A41
0x180010803  cmp     word ptr [rbx], 20h ; ' '
0x180010807  ja      short loc_180010812
0x180010809  add     rbx, 2
0x18001080d  add     r13d, r8d
0x180010810  jnz     short loc_180010803
0x180010812  test    r13d, r13d
0x180010815  jz      loc_180010A41
0x18001081b  mov     rcx, rbx
0x18001081e  mov     rdi, rbx
0x180010821  cmp     word ptr [rbx], 3Dh ; '='
0x180010825  jz      short loc_18001084B
0x180010827  cmp     word ptr [rbx], 0Dh
0x18001082b  jz      short loc_18001083C
0x18001082d  cmp     word ptr [rbx], 0Ah
0x180010831  jz      short loc_18001083C
0x180010833  add     rbx, 2
0x180010837  add     r13d, r8d
0x18001083a  jnz     short loc_180010821
0x18001083c  test    r13d, r13d
0x18001083f  jz      loc_180010A41
0x180010845  cmp     word ptr [rbx], 3Dh ; '='
0x180010849  jnz     short loc_180010803
0x18001084b  mov     rax, rbx
0x18001084e  sub     rax, rcx
0x180010851  add     rbx, 2
0x180010855  mov     rdx, rbx
0x180010858  mov     rsi, rbx
0x18001085b  jmp     short loc_18001086D
0x18001085d  cmp     word ptr [rbx], 0Dh
0x180010861  jz      short loc_180010872
0x180010863  cmp     word ptr [rbx], 0Ah
0x180010867  jz      short loc_180010872
0x180010869  add     rbx, 2
0x18001086d  add     r13d, r8d
0x180010870  jnz     short loc_18001085D
0x180010872  sub     rbx, rdx
0x180010875  sar     rax, 1
0x180010878  sar     rbx, 1
0x18001087b  mov     ecx, ebx
0x18001087d  mov     eax, eax
0x18001087f  mov     [rbp+57h+var_88], rcx
0x180010883  mov     [rbp+57h+var_90], rax
0x180010887  lea     rbx, [rdx+rcx*2]
0x18001088b  cmp     rax, 0Ch
0x18001088f  jnz     short loc_18001090C
0x180010891  mov     r8d, eax
0x180010894  lea     rdx, aMetadatahash; "MetadataHash"
0x18001089b  mov     rcx, rdi
0x18001089e  call    ?compare@?$_Char16TraitsBase@_W@utl@@SAHPEB_W0_K@Z; utl::_Char16TraitsBase<wchar_t>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x1800108a3  test    eax, eax
0x1800108a5  jnz     short loc_18001090C
0x1800108a7  mov     [rbp+57h+arg_8], eax
0x1800108aa  lea     r9, [rbp+57h+arg_8]
0x1800108ae  mov     byte ptr [rbp+57h+arg_10], al
0x1800108b1  lea     rcx, [rbp+57h+var_50]
0x1800108b5  lea     rax, [rbp+57h+arg_10]
0x1800108b9  mov     r8, rbx
0x1800108bc  mov     rdx, rsi
0x1800108bf  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x1800108c4  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x1800108c9  xor     esi, esi
0x1800108cb  mov     r9d, [rax+8]
0x1800108cf  test    r9d, r9d
0x1800108d2  jnz     loc_1800109CD
0x1800108d8  movzx   ecx, byte ptr [rbp+57h+arg_10]
0x1800108dc  lea     eax, [rcx+7FFFFFFFh]
0x1800108e2  cmp     [rbp+57h+arg_8], eax
0x1800108e5  ja      loc_1800109C7
0x1800108eb  mov     r9d, [rbp+57h+arg_18]
0x1800108ef  mov     r8d, ecx
0x1800108f2  neg     r8d
0x1800108f5  mov     [rbp+57h+arg_10], 1
0x1800108fc  xor     r8d, [rbp+57h+arg_8]
0x180010900  add     r8d, ecx
0x180010903  mov     [rbp+57h+arg_8], r8d
0x180010907  jmp     loc_1800107ED
0x18001090c  lea     rcx, [rbp+57h+lpMem]; void *
0x180010910  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180010915  mov     r8, [rbp+57h+var_90]
0x180010919  lea     rcx, [rbp+57h+lpMem]
0x18001091d  mov     rdx, rdi
0x180010920  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180010925  test    al, al
0x180010927  jz      loc_1800109FD
0x18001092d  mov     rax, [rbp+57h+var_88]
0x180010931  lea     r9, [rbp+57h+var_80]
0x180010935  mov     rcx, [rbp+57h+arg_0]
0x180010939  lea     r8, [rbp+57h+lpMem]
0x18001093d  lea     rdx, [rbp+57h+var_40]
0x180010941  mov     [rbp+57h+var_78], rax
0x180010945  mov     [rbp+57h+var_80], rsi
0x180010949  call    ?insert_or_assign@CStringMap@@QEAA?AU?$pair@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@utl@@_N@utl@@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z; CStringMap::insert_or_assign(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001094e  cmp     qword ptr [rax], 0
0x180010952  jz      loc_1800109FD
0x180010958  mov     r8, [rbp+57h+lpMem]; lpMem
0x18001095c  lea     rax, [rbp+57h+var_60]
0x180010960  cmp     r8, rax
0x180010963  jz      short loc_18001097A
0x180010965  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001096c  xor     edx, edx; dwFlags
0x18001096e  call    cs:__imp_HeapFree
0x180010975  nop     dword ptr [rax+rax+00h]
0x18001097a  mov     rax, [rbp+57h+var_90]
0x18001097e  xor     edx, edx
0x180010980  lea     rax, [rdi+rax*2]
0x180010984  cmp     rdi, rax
0x180010987  jz      short loc_18001099A
0x180010989  movzx   ecx, word ptr [rdi]
0x18001098c  imul    edx, 1003Fh
0x180010992  add     edx, ecx
0x180010994  add     rdi, 2
0x180010998  jmp     short loc_180010984
0x18001099a  mov     r9d, [rbp+57h+arg_18]
0x18001099e  add     r9d, edx
0x1800109a1  xor     ecx, ecx
0x1800109a3  cmp     rsi, rbx
0x1800109a6  jz      short loc_1800109B9
0x1800109a8  movzx   eax, word ptr [rsi]
0x1800109ab  imul    ecx, 1003Fh
0x1800109b1  add     ecx, eax
0x1800109b3  add     rsi, 2
0x1800109b7  jmp     short loc_1800109A3
0x1800109b9  add     r9d, ecx
0x1800109bc  mov     [rbp+57h+arg_18], r9d
0x1800109c0  xor     esi, esi
0x1800109c2  jmp     loc_1800107ED
0x1800109c7  mov     r9d, 22h ; '"'
0x1800109cd  mov     ebx, 80070057h
0x1800109d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109d9  lea     rax, WPP_GLOBAL_Control
0x1800109e0  cmp     rcx, rax
0x1800109e3  jz      loc_180010ABF
0x1800109e9  test    byte ptr [rcx+1Ch], 1
0x1800109ed  jz      loc_180010ABF
0x1800109f3  mov     edx, 1Dh
0x1800109f8  jmp     loc_1800107A4
0x1800109fd  mov     ebx, 8007000Eh
0x180010a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a09  lea     rax, WPP_GLOBAL_Control
0x180010a10  cmp     rcx, rax
0x180010a13  jz      short loc_180010A36
0x180010a15  test    byte ptr [rcx+1Ch], 1
0x180010a19  jz      short loc_180010A36
  ... truncated ...
```
