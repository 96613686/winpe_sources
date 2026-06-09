# CIniParser::ReadFromFile(wchar_t const *,int)

- ea: `0x18000eb6c`
- end: `0x18000f143`
- name: `?ReadFromFile@CIniParser@@QEAAJPEB_WH@Z`
- size: `1495`
- prototype: `__int64 __fastcall(CIniParser *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180072920`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000d8f8`
- `0x18000dad0`
- `0x18000dc5c`
- `0x18000eb6c`
- `0x180014720`
- `0x18001fe24`
- `0x18002c16c`
- `0x18003e5ec`
- `0x1800997d4`
- `0x180099830`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f0b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f0b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecf0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0f4`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000ec3b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000ec3b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ed56`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ed56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ebd3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ebd3`

## pseudocode

```c
__int64 __fastcall CIniParser::ReadFromFile(CIniParser *this, const wchar_t *a2, int a3)
{
  char *FileW; // r15
  DWORD LastError; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r14
  DWORD v13; // eax
  wchar_t *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r9
  DWORD v18; // r13d
  unsigned __int16 *v19; // rbx
  char *v20; // rcx
  unsigned __int16 *v21; // rdi
  __int64 v22; // rax
  _WORD *v23; // rbx
  _WORD *v24; // rdx
  unsigned __int16 *v25; // rsi
  int v26; // ecx
  int v27; // edx
  unsigned __int16 *v28; // rax
  int v29; // ecx
  int dwCreationDisposition; // [rsp+20h] [rbp-69h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-41h] BYREF
  int v34; // [rsp+4Ch] [rbp-3Dh]
  __int64 v35; // [rsp+50h] [rbp-39h]
  __int64 v36; // [rsp+58h] [rbp-31h]
  _QWORD v37[2]; // [rsp+60h] [rbp-29h] BYREF
  LPVOID lpMem[2]; // [rsp+70h] [rbp-19h] BYREF
  char v39; // [rsp+80h] [rbp-9h] BYREF
  char v40; // [rsp+90h] [rbp+7h] BYREF
  char v41[64]; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v43; // [rsp+F8h] [rbp+6Fh] BYREF
  int v44; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v45; // [rsp+108h] [rbp+7Fh]

  v44 = a3;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  if ( a2 && *a2 )
  {
    CIniParser::~CIniParser(this);
    FileW = (char *)CreateFileW(a2, 1u, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
    {
      LastError = GetLastError();
      v6 = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v6);
      return v6;
    }
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v7 = GetLastError();
      v6 = ERROR_HR_FROM_WIN32(v7);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v6);
      goto LABEL_84;
    }
    if ( FileSize.QuadPart > 0x400000uLL )
    {
      v6 = -2147483637;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_DI(*((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_84;
    }
    if ( !FileSize.LowPart )
    {
      v6 = -2147024883;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v9 = 25;
      v10 = 2147942413LL;
      goto LABEL_20;
    }
    v11 = (unsigned __int16 *)HeapAlloc(g_hWerheap, 0, FileSize.LowPart);
    v12 = v11;
    if ( !v11 )
    {
      v6 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v9 = 26;
      v10 = 2147942414LL;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v10);
LABEL_84:
      CloseHandle(FileW);
      return v6;
    }
    if ( !ReadFile(FileW, v11, FileSize.LowPart, &NumberOfBytesRead, 0) )
    {
      v13 = GetLastError();
      v6 = ERROR_HR_FROM_WIN32(v13);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_80;
      v15 = 27;
      v16 = v6;
      goto LABEL_25;
    }
    v17 = 0;
    v18 = NumberOfBytesRead >> 1;
    v19 = v12;
    v45 = 0;
    v43 = 0;
    v44 = 0;
    v34 = 0;
    if ( NumberOfBytesRead >> 1 && *v12 == 0xFEFF )
    {
      v34 = 1;
      v19 = v12 + 1;
      --v18;
    }
    while ( 2 )
    {
      if ( v19 && v18 )
      {
        do
        {
LABEL_31:
          if ( *v19 > 0x20u )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        if ( v18 )
        {
          v20 = (char *)v19;
          v21 = v19;
          while ( *v19 != 61 )
          {
            if ( *v19 != 13 && *v19 != 10 )
            {
              ++v19;
              if ( --v18 )
                continue;
            }
            if ( !v18 )
              goto LABEL_70;
            if ( *v19 != 61 )
              goto LABEL_31;
            break;
          }
          v22 = (char *)v19 - v20;
          v23 = v19 + 1;
          v24 = v23;
          v25 = v23;
          while ( --v18 && *v23 != 13 && *v23 != 10 )
            ++v23;
          v36 = (unsigned int)(v23 - v24);
          v35 = (unsigned int)(v22 >> 1);
          v19 = &v24[v36];
          if ( v35 != 12 || (unsigned int)utl::_Char16TraitsBase<wchar_t>::compare(v21, L"MetadataHash", 12, v17) )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                    lpMem,
                                    v21,
                                    v35) )
            {
              v37[1] = v36;
              v37[0] = v25;
              if ( *(_QWORD *)CStringMap::insert_or_assign(this, v41, lpMem, v37) )
              {
                if ( lpMem[0] != &v39 )
                  HeapFree(g_hWerheap, 0, lpMem[0]);
                v27 = 0;
                v28 = &v21[v35];
                while ( v21 != v28 )
                  v27 = *v21++ + 65599 * v27;
                v29 = 0;
                while ( v25 != v19 )
                  v29 = *v25++ + 65599 * v29;
                v17 = v29 + v27 + v45;
                v45 += v29 + v27;
                continue;
              }
            }
            v6 = -2147024882;
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
            v43 = 0;
            LOBYTE(v44) = 0;
            v16 = *(unsigned int *)(utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
                                      (unsigned int)&v40,
                                      (_DWORD)v25,
                                      (_DWORD)v19,
                                      (unsigned int)&v43,
                                      dwCreationDisposition,
                                      (__int64)&v44)
                                  + 8);
            if ( !(_DWORD)v16 )
            {
              v26 = (unsigned __int8)v44;
              if ( v43 <= (unsigned int)(unsigned __int8)v44 + 0x7FFFFFFF )
              {
                v17 = v45;
                v44 = 1;
                v43 = v26 + (v43 ^ -v26);
                continue;
              }
              v16 = 34;
            }
            v6 = -2147024809;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v15 = 29;
              goto LABEL_25;
            }
          }
          goto LABEL_80;
        }
      }
      break;
    }
LABEL_70:
    if ( v34 )
    {
      if ( !v44 )
      {
        v6 = -2147023504;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_80;
        v15 = 30;
        v16 = 2147943792LL;
LABEL_25:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v16);
LABEL_80:
        HeapFree(g_hWerheap, 0, v12);
        goto LABEL_84;
      }
      if ( v43 != (_DWORD)v17 )
      {
        v6 = -2147023504;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_llD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
        goto LABEL_80;
      }
    }
    v6 = 0;
    goto LABEL_80;
  }
  v6 = -2147024809;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x18000eb6c  mov     [rsp-8+arg_10], r8d
0x18000eb71  mov     [rsp-8+arg_0], rcx
0x18000eb76  push    rbp
0x18000eb77  push    rbx
0x18000eb78  push    rsi
0x18000eb79  push    rdi
0x18000eb7a  push    r13
0x18000eb7c  push    r14
0x18000eb7e  push    r15
0x18000eb80  lea     rbp, [rsp-27h]
0x18000eb85  sub     rsp, 0B0h
0x18000eb8c  xor     esi, esi
0x18000eb8e  mov     rdi, rdx
0x18000eb91  mov     [rbp+57h+NumberOfBytesRead], esi
0x18000eb94  mov     rax, rcx
0x18000eb97  mov     qword ptr [rbp+57h+FileSize], rsi
0x18000eb9b  test    rdx, rdx
0x18000eb9e  jz      loc_18000F0FC
0x18000eba4  cmp     [rdx], si
0x18000eba7  jz      loc_18000F0FC
0x18000ebad  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x18000ebb2  lea     edx, [rsi+1]; dwDesiredAccess
0x18000ebb5  mov     [rsp+0E0h+hTemplateFile], rsi; hTemplateFile
0x18000ebba  mov     r8d, edx; dwShareMode
0x18000ebbd  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000ebc5  xor     r9d, r9d; lpSecurityAttributes
0x18000ebc8  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ebd0  mov     rcx, rdi; lpFileName
0x18000ebd3  call    cs:__imp_CreateFileW
0x18000ebd9  mov     r15, rax
0x18000ebdc  inc     rax
0x18000ebdf  cmp     rax, 1
0x18000ebe3  ja      short loc_18000EC34
0x18000ebe5  call    cs:__imp_GetLastError
0x18000ebeb  mov     ecx, eax; unsigned int
0x18000ebed  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000ebf2  mov     ebx, eax
0x18000ebf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebfb  lea     rax, WPP_GLOBAL_Control
0x18000ec02  cmp     rcx, rax
0x18000ec05  jz      loc_18000F12F
0x18000ec0b  test    byte ptr [rcx+1Ch], 1
0x18000ec0f  jz      loc_18000F12F
0x18000ec15  mov     rcx, [rcx+10h]
0x18000ec19  lea     edx, [rsi+16h]
0x18000ec1c  mov     r9, rdi
0x18000ec1f  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x18000ec23  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000ec2a  call    WPP_SF_SD
0x18000ec2f  jmp     loc_18000F12F
0x18000ec34  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x18000ec38  mov     rcx, r15; hFile
0x18000ec3b  call    cs:__imp_GetFileSizeEx
0x18000ec41  test    eax, eax
0x18000ec43  jnz     short loc_18000EC96
0x18000ec45  call    cs:__imp_GetLastError
0x18000ec4b  mov     ecx, eax; unsigned int
0x18000ec4d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000ec52  mov     ebx, eax
0x18000ec54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec5b  lea     rax, WPP_GLOBAL_Control
0x18000ec62  cmp     rcx, rax
0x18000ec65  jz      loc_18000F0F1
0x18000ec6b  test    byte ptr [rcx+1Ch], 1
0x18000ec6f  jz      loc_18000F0F1
0x18000ec75  mov     rcx, [rcx+10h]
0x18000ec79  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000ec80  mov     edx, 17h
0x18000ec85  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x18000ec89  mov     r9, rdi
0x18000ec8c  call    WPP_SF_SD
0x18000ec91  jmp     loc_18000F0F1
0x18000ec96  cmp     dword ptr [rbp+57h+FileSize+4], esi
0x18000ec99  jnz     loc_18000F0C1
0x18000ec9f  mov     eax, dword ptr [rbp+57h+FileSize]
0x18000eca2  cmp     eax, 400000h
0x18000eca7  ja      loc_18000F0C1
0x18000ecad  test    eax, eax
0x18000ecaf  jnz     short loc_18000ECE4
0x18000ecb1  mov     ebx, 8007000Dh
0x18000ecb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecbd  lea     rax, WPP_GLOBAL_Control
0x18000ecc4  cmp     rcx, rax
0x18000ecc7  jz      loc_18000F0F1
0x18000eccd  test    byte ptr [rcx+1Ch], 1
0x18000ecd1  jz      loc_18000F0F1
0x18000ecd7  mov     edx, 19h
0x18000ecdc  mov     r9d, 8007000Dh
0x18000ece2  jmp     short loc_18000ED2E
0x18000ece4  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000eceb  mov     r8, rax; dwBytes
0x18000ecee  xor     edx, edx; dwFlags
0x18000ecf0  call    cs:__imp_HeapAlloc
0x18000ecf6  mov     r14, rax
0x18000ecf9  test    rax, rax
0x18000ecfc  jnz     short loc_18000ED43
0x18000ecfe  mov     ebx, 8007000Eh
0x18000ed03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed0a  lea     rax, WPP_GLOBAL_Control
0x18000ed11  cmp     rcx, rax
0x18000ed14  jz      loc_18000F0F1
0x18000ed1a  test    byte ptr [rcx+1Ch], 1
0x18000ed1e  jz      loc_18000F0F1
0x18000ed24  lea     edx, [r14+1Ah]
0x18000ed28  mov     r9d, 8007000Eh
0x18000ed2e  mov     rcx, [rcx+10h]
0x18000ed32  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000ed39  call    WPP_SF_d
0x18000ed3e  jmp     loc_18000F0F1
0x18000ed43  mov     r8d, dword ptr [rbp+57h+FileSize]; nNumberOfBytesToRead
0x18000ed47  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000ed4b  mov     rdx, r14; lpBuffer
0x18000ed4e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi; lpOverlapped
0x18000ed53  mov     rcx, r15; hFile
0x18000ed56  call    cs:__imp_ReadFile
0x18000ed5c  test    eax, eax
0x18000ed5e  jnz     short loc_18000EDAD
0x18000ed60  call    cs:__imp_GetLastError
0x18000ed66  mov     ecx, eax; unsigned int
0x18000ed68  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000ed6d  mov     ebx, eax
0x18000ed6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed76  lea     rax, WPP_GLOBAL_Control
0x18000ed7d  cmp     rcx, rax
0x18000ed80  jz      loc_18000F0AD
0x18000ed86  test    byte ptr [rcx+1Ch], 1
0x18000ed8a  jz      loc_18000F0AD
0x18000ed90  mov     edx, 1Bh
0x18000ed95  mov     r9d, ebx
0x18000ed98  mov     rcx, [rcx+10h]
0x18000ed9c  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000eda3  call    WPP_SF_d
0x18000eda8  jmp     loc_18000F0AD
0x18000edad  mov     r13d, [rbp+57h+NumberOfBytesRead]
0x18000edb1  mov     r9d, esi
0x18000edb4  shr     r13d, 1
0x18000edb7  mov     rbx, r14
0x18000edba  mov     [rbp+57h+arg_18], esi
0x18000edbd  mov     [rbp+57h+arg_8], esi
0x18000edc0  mov     [rbp+57h+arg_10], esi
0x18000edc3  mov     [rbp+57h+var_94], esi
0x18000edc6  jz      short loc_18000EDE1
0x18000edc8  mov     eax, 0FEFFh
0x18000edcd  cmp     [r14], ax
0x18000edd1  jnz     short loc_18000EDE1
0x18000edd3  mov     [rbp+57h+var_94], 1
0x18000edda  lea     rbx, [r14+2]
0x18000edde  dec     r13d
0x18000ede1  or      r8d, 0FFFFFFFFh
0x18000ede5  test    rbx, rbx
0x18000ede8  jz      loc_18000F02F
0x18000edee  test    r13d, r13d
0x18000edf1  jz      loc_18000F02F
0x18000edf7  cmp     word ptr [rbx], 20h ; ' '
0x18000edfb  ja      short loc_18000EE06
0x18000edfd  add     rbx, 2
0x18000ee01  add     r13d, r8d
0x18000ee04  jnz     short loc_18000EDF7
0x18000ee06  test    r13d, r13d
0x18000ee09  jz      loc_18000F02F
0x18000ee0f  mov     rcx, rbx
0x18000ee12  mov     rdi, rbx
0x18000ee15  cmp     word ptr [rbx], 3Dh ; '='
0x18000ee19  jz      short loc_18000EE3F
0x18000ee1b  cmp     word ptr [rbx], 0Dh
0x18000ee1f  jz      short loc_18000EE30
0x18000ee21  cmp     word ptr [rbx], 0Ah
0x18000ee25  jz      short loc_18000EE30
0x18000ee27  add     rbx, 2
0x18000ee2b  add     r13d, r8d
0x18000ee2e  jnz     short loc_18000EE15
0x18000ee30  test    r13d, r13d
0x18000ee33  jz      loc_18000F02F
0x18000ee39  cmp     word ptr [rbx], 3Dh ; '='
0x18000ee3d  jnz     short loc_18000EDF7
0x18000ee3f  mov     rax, rbx
0x18000ee42  sub     rax, rcx
0x18000ee45  add     rbx, 2
0x18000ee49  mov     rdx, rbx
0x18000ee4c  mov     rsi, rbx
0x18000ee4f  jmp     short loc_18000EE61
0x18000ee51  cmp     word ptr [rbx], 0Dh
0x18000ee55  jz      short loc_18000EE66
0x18000ee57  cmp     word ptr [rbx], 0Ah
0x18000ee5b  jz      short loc_18000EE66
0x18000ee5d  add     rbx, 2
0x18000ee61  add     r13d, r8d
0x18000ee64  jnz     short loc_18000EE51
0x18000ee66  sub     rbx, rdx
0x18000ee69  sar     rax, 1
0x18000ee6c  sar     rbx, 1
0x18000ee6f  mov     ecx, ebx
0x18000ee71  mov     eax, eax
0x18000ee73  mov     [rbp+57h+var_88], rcx
0x18000ee77  mov     [rbp+57h+var_90], rax
0x18000ee7b  lea     rbx, [rdx+rcx*2]
0x18000ee7f  cmp     rax, 0Ch
0x18000ee83  jnz     short loc_18000EF00
0x18000ee85  mov     r8d, eax
0x18000ee88  lea     rdx, aMetadatahash; "MetadataHash"
0x18000ee8f  mov     rcx, rdi
0x18000ee92  call    ?compare@?$_Char16TraitsBase@_W@utl@@SAHPEB_W0_K@Z; utl::_Char16TraitsBase<wchar_t>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18000ee97  test    eax, eax
0x18000ee99  jnz     short loc_18000EF00
0x18000ee9b  mov     [rbp+57h+arg_8], eax
0x18000ee9e  lea     r9, [rbp+57h+arg_8]
0x18000eea2  mov     byte ptr [rbp+57h+arg_10], al
0x18000eea5  lea     rcx, [rbp+57h+var_50]
0x18000eea9  lea     rax, [rbp+57h+arg_10]
0x18000eead  mov     r8, rbx
0x18000eeb0  mov     rdx, rsi
0x18000eeb3  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x18000eeb8  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x18000eebd  xor     esi, esi
0x18000eebf  mov     r9d, [rax+8]
0x18000eec3  test    r9d, r9d
0x18000eec6  jnz     loc_18000EFBB
0x18000eecc  movzx   ecx, byte ptr [rbp+57h+arg_10]
0x18000eed0  lea     eax, [rcx+7FFFFFFFh]
0x18000eed6  cmp     [rbp+57h+arg_8], eax
0x18000eed9  ja      loc_18000EFB5
0x18000eedf  mov     r9d, [rbp+57h+arg_18]
0x18000eee3  mov     r8d, ecx
0x18000eee6  neg     r8d
0x18000eee9  mov     [rbp+57h+arg_10], 1
0x18000eef0  xor     r8d, [rbp+57h+arg_8]
0x18000eef4  add     r8d, ecx
0x18000eef7  mov     [rbp+57h+arg_8], r8d
0x18000eefb  jmp     loc_18000EDE1
0x18000ef00  lea     rcx, [rbp+57h+lpMem]; void *
0x18000ef04  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000ef09  mov     r8, [rbp+57h+var_90]
0x18000ef0d  lea     rcx, [rbp+57h+lpMem]
0x18000ef11  mov     rdx, rdi
0x18000ef14  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000ef19  test    al, al
0x18000ef1b  jz      loc_18000EFEB
0x18000ef21  mov     rax, [rbp+57h+var_88]
0x18000ef25  lea     r9, [rbp+57h+var_80]
0x18000ef29  mov     rcx, [rbp+57h+arg_0]
0x18000ef2d  lea     r8, [rbp+57h+lpMem]
0x18000ef31  lea     rdx, [rbp+57h+var_40]
0x18000ef35  mov     [rbp+57h+var_78], rax
0x18000ef39  mov     [rbp+57h+var_80], rsi
0x18000ef3d  call    ?insert_or_assign@CStringMap@@QEAA?AU?$pair@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@utl@@_N@utl@@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z; CStringMap::insert_or_assign(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18000ef42  cmp     qword ptr [rax], 0
0x18000ef46  jz      loc_18000EFEB
0x18000ef4c  mov     r8, [rbp+57h+lpMem]; lpMem
0x18000ef50  lea     rax, [rbp+57h+var_60]
0x18000ef54  cmp     r8, rax
0x18000ef57  jz      short loc_18000EF68
0x18000ef59  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000ef60  xor     edx, edx; dwFlags
0x18000ef62  call    cs:__imp_HeapFree
0x18000ef68  mov     rax, [rbp+57h+var_90]
0x18000ef6c  xor     edx, edx
0x18000ef6e  lea     rax, [rdi+rax*2]
0x18000ef72  cmp     rdi, rax
0x18000ef75  jz      short loc_18000EF88
0x18000ef77  movzx   ecx, word ptr [rdi]
0x18000ef7a  imul    edx, 1003Fh
0x18000ef80  add     edx, ecx
0x18000ef82  add     rdi, 2
0x18000ef86  jmp     short loc_18000EF72
0x18000ef88  mov     r9d, [rbp+57h+arg_18]
0x18000ef8c  add     r9d, edx
0x18000ef8f  xor     ecx, ecx
0x18000ef91  cmp     rsi, rbx
0x18000ef94  jz      short loc_18000EFA7
0x18000ef96  movzx   eax, word ptr [rsi]
0x18000ef99  imul    ecx, 1003Fh
0x18000ef9f  add     ecx, eax
0x18000efa1  add     rsi, 2
0x18000efa5  jmp     short loc_18000EF91
0x18000efa7  add     r9d, ecx
0x18000efaa  mov     [rbp+57h+arg_18], r9d
0x18000efae  xor     esi, esi
0x18000efb0  jmp     loc_18000EDE1
0x18000efb5  mov     r9d, 22h ; '"'
0x18000efbb  mov     ebx, 80070057h
0x18000efc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efc7  lea     rax, WPP_GLOBAL_Control
0x18000efce  cmp     rcx, rax
0x18000efd1  jz      loc_18000F0AD
0x18000efd7  test    byte ptr [rcx+1Ch], 1
0x18000efdb  jz      loc_18000F0AD
0x18000efe1  mov     edx, 1Dh
0x18000efe6  jmp     loc_18000ED98
0x18000efeb  mov     ebx, 8007000Eh
0x18000eff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eff7  lea     rax, WPP_GLOBAL_Control
0x18000effe  cmp     rcx, rax
0x18000f001  jz      short loc_18000F024
0x18000f003  test    byte ptr [rcx+1Ch], 1
0x18000f007  jz      short loc_18000F024
0x18000f009  mov     rcx, [rcx+10h]
0x18000f00d  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000f014  mov     edx, 1Ch
0x18000f019  mov     r9d, 8007000Eh
0x18000f01f  call    WPP_SF_d
  ... truncated ...
```
