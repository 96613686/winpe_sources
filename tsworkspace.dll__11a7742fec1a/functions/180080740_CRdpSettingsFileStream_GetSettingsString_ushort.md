# CRdpSettingsFileStream::GetSettingsString(ushort * *)

- ea: `0x180080740`
- end: `0x180080c24`
- name: `?GetSettingsString@CRdpSettingsFileStream@@UEAAJPEAPEAG@Z`
- size: `1252`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001c6e4`
- `0x180080740`
- `0x180080f14`

## import_xrefs

- `ADVAPI32!IsTextUnicode` at `0x180080a20`
- `ADVAPI32!IsTextUnicode` at `0x180080a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008080e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008080e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ba9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180080aa0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180080b9f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180080aa0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180080b9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008097d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080c19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008097d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080c19`
- `KERNEL32!GetFileSize` at `0x1800807b9`
- `KERNEL32!GetFileSize` at `0x1800807b9`
- `KERNEL32!ReadFile` at `0x180080801`
- `KERNEL32!ReadFile` at `0x180080970`
- `KERNEL32!ReadFile` at `0x180080801`
- `KERNEL32!ReadFile` at `0x180080970`

## string_xrefs

- `0x1800808bb`: `Failed to move pointer to the beginning of the file!`
- `0x1800809c8`: `Failed to move pointer to the beginning of the file!`

## pseudocode

```c
__int64 __fastcall CRdpSettingsFileStream::GetSettingsString(HANDLE *this, unsigned __int16 **a2)
{
  int v2; // r15d
  signed int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  DWORD FileSize; // edi
  WCHAR *v8; // r14
  int v9; // r13d
  UINT v10; // r12d
  void *v11; // rdi
  signed int LastError; // eax
  DWORD v13; // ebx
  void *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  signed int v17; // ebx
  int v18; // r9d
  int v19; // ecx
  DWORD i; // r8d
  char v21; // dl
  int v22; // eax
  int v23; // eax
  bool v24; // sf
  int cchWideChar; // ebx
  WCHAR *v26; // rax
  unsigned int v27; // eax
  signed int v29; // eax
  unsigned int v30; // eax
  int iResult[4]; // [rsp+30h] [rbp-10h] BYREF
  int Buffer; // [rsp+90h] [rbp+50h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  *a2 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, 0);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 26;
LABEL_25:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to move pointer to the beginning of the file!",
        v4);
      return (unsigned int)v4;
    }
    return (unsigned int)v4;
  }
  FileSize = GetFileSize(this[10], 0);
  if ( !FileSize )
    return (unsigned int)-2147024872;
  if ( FileSize > 0x80000 )
    return (unsigned int)-2147024883;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !ReadFile(this[10], &Buffer, 4u, &NumberOfBytesRead, 0) )
    goto LABEL_11;
  if ( (_BYTE)Buffer == 0xEF )
  {
    if ( *(_WORD *)((char *)&Buffer + 1) == 0xBFBB )
    {
      v2 = 3;
      v10 = 65001;
    }
  }
  else if ( (_WORD)Buffer == 0xFFFE || (_WORD)Buffer == 0xFEFF )
  {
    if ( (FileSize & 1) != 0 )
      return (unsigned int)-2147024883;
    v9 = 1;
    v2 = 2;
  }
  v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, v2);
  if ( v4 >= 0 )
  {
    v13 = FileSize - v2 + 2;
    v14 = (void *)PAL_System_MemAlloc(v13);
    v11 = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v15);
      }
      return (unsigned int)-2147024882;
    }
    memset_0(v14, 0, v13);
    if ( !ReadFile(this[10], v11, v13, &NumberOfBytesRead, 0) )
    {
      LocalFree(v11);
LABEL_11:
      v11 = 0;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_80;
    }
    v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, 0);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v16,
          (__int64)"Failed to move pointer to the beginning of the file!",
          v4);
      }
      goto LABEL_71;
    }
    if ( v9 )
    {
      if ( v10 != 65001 )
        goto LABEL_66;
    }
    else if ( v10 != 65001 )
    {
      v17 = NumberOfBytesRead;
      iResult[0] = -1;
      if ( IsTextUnicode(v11, NumberOfBytesRead, iResult) && (iResult[0] != 2 || v17 >= 100) )
      {
        v9 = 1;
LABEL_66:
        v8 = (WCHAR *)v11;
        goto LABEL_67;
      }
      v18 = 1;
      v19 = 0;
      for ( i = 0; i < NumberOfBytesRead; ++i )
      {
        v21 = *((_BYTE *)v11 + i);
        v22 = 0;
        if ( v21 >= 0 )
          v22 = v18;
        v18 = v22;
        if ( v19 )
        {
          if ( (v21 & 0xC0) != 0x80 )
            goto LABEL_53;
          --v19;
        }
        else if ( (unsigned __int8)v21 >= 0x80u )
        {
          do
          {
            v23 = v19++;
            v24 = (v21 & 0x40) != 0;
            v21 *= 2;
          }
          while ( v24 );
          v19 = v23;
          if ( !v23 )
            goto LABEL_53;
        }
      }
      if ( !v19 && !v18 )
        v10 = 65001;
    }
LABEL_53:
    cchWideChar = MultiByteToWideChar(v10, 0, (LPCCH)v11, -1, 0, 0);
    v26 = (WCHAR *)PAL_System_MemAlloc(2LL * cchWideChar);
    v8 = v26;
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v27);
      }
      v4 = -2147024882;
      goto LABEL_71;
    }
    if ( !MultiByteToWideChar(v10, 0, (LPCCH)v11, -1, v26, cchWideChar) )
    {
      v29 = GetLastError();
      v4 = v29;
      if ( v29 > 0 )
        v4 = (unsigned __int16)v29 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v30, v4);
      }
LABEL_80:
      if ( v4 < 0 )
      {
        if ( v8 )
          LocalFree(v8);
LABEL_70:
        if ( !v11 )
          return (unsigned int)v4;
LABEL_71:
        LocalFree(v11);
        return (unsigned int)v4;
      }
LABEL_68:
      if ( v9 && v10 != 65001 )
        return (unsigned int)v4;
      goto LABEL_70;
    }
LABEL_67:
    v4 = 0;
    *a2 = v8;
    goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 27;
    goto LABEL_25;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180080740  mov     [rsp-38h+arg_0], rbx
0x180080745  mov     [rsp-38h+arg_8], rdx
0x18008074a  push    rbp
0x18008074b  push    rsi
0x18008074c  push    rdi
0x18008074d  push    r12
0x18008074f  push    r13
0x180080751  push    r14
0x180080753  push    r15
0x180080755  mov     rbp, rsp
0x180080758  sub     rsp, 40h
0x18008075c  xor     r15d, r15d
0x18008075f  mov     rsi, rcx
0x180080762  mov     [rdx], r15
0x180080765  xor     edx, edx; int
0x180080767  mov     [rbp+NumberOfBytesRead], r15d
0x18008076b  mov     [rbp+Buffer], r15d
0x18008076f  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x180080774  mov     ebx, eax
0x180080776  test    eax, eax
0x180080778  jns     short loc_1800807B3
0x18008077a  mov     rcx, cs:WPP_GLOBAL_Control
0x180080781  lea     rax, WPP_GLOBAL_Control
0x180080788  cmp     rcx, rax
0x18008078b  jz      loc_180080B71
0x180080791  test    byte ptr [rcx+1Ch], 8
0x180080795  jz      loc_180080B71
0x18008079b  cmp     byte ptr [rcx+19h], 2
0x18008079f  jb      loc_180080B71
0x1800807a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800807aa  lea     edx, [r15+1Ah]
0x1800807ae  jmp     loc_1800808BB
0x1800807b3  mov     rcx, [rsi+50h]; hFile
0x1800807b7  xor     edx, edx; lpFileSizeHigh
0x1800807b9  call    cs:__imp_GetFileSize
0x1800807bf  mov     edi, eax
0x1800807c1  test    eax, eax
0x1800807c3  jnz     short loc_1800807CF
0x1800807c5  mov     ebx, 80070018h
0x1800807ca  jmp     loc_180080B71
0x1800807cf  cmp     edi, 80000h
0x1800807d5  jbe     short loc_1800807E1
0x1800807d7  mov     ebx, 8007000Dh
0x1800807dc  jmp     loc_180080B71
0x1800807e1  mov     rcx, [rsi+50h]; hFile
0x1800807e5  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800807e9  mov     r8d, 4; nNumberOfBytesToRead
0x1800807ef  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x1800807f4  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800807f8  mov     r14, r15
0x1800807fb  mov     r13d, r15d
0x1800807fe  mov     r12d, r15d
0x180080801  call    cs:__imp_ReadFile
0x180080807  test    eax, eax
0x180080809  jnz     short loc_18008082C
0x18008080b  mov     rdi, r15
0x18008080e  call    cs:__imp_GetLastError
0x180080814  mov     ebx, eax
0x180080816  test    eax, eax
0x180080818  jle     loc_180080C05
0x18008081e  movzx   ebx, ax
0x180080821  or      ebx, 80070000h
0x180080827  jmp     loc_180080C05
0x18008082c  mov     eax, [rbp+Buffer]
0x18008082f  cmp     al, 0EFh
0x180080831  jnz     short loc_18008084D
0x180080833  cmp     byte ptr [rbp+Buffer+1], 0BBh
0x180080837  jnz     short loc_180080875
0x180080839  cmp     byte ptr [rbp+Buffer+2], 0BFh
0x18008083d  jnz     short loc_180080875
0x18008083f  mov     r15d, 3
0x180080845  mov     r12d, 0FDE9h
0x18008084b  jmp     short loc_180080875
0x18008084d  cmp     al, 0FEh
0x18008084f  jnz     short loc_180080857
0x180080851  cmp     byte ptr [rbp+Buffer+1], 0FFh
0x180080855  jz      short loc_180080861
0x180080857  cmp     al, 0FFh
0x180080859  jnz     short loc_180080875
0x18008085b  cmp     byte ptr [rbp+Buffer+1], 0FEh
0x18008085f  jnz     short loc_180080875
0x180080861  test    dil, 1
0x180080865  jnz     loc_1800807D7
0x18008086b  mov     r13d, 1
0x180080871  lea     r15d, [r13+1]
0x180080875  mov     edx, r15d; int
0x180080878  mov     rcx, rsi; this
0x18008087b  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x180080880  mov     ebx, eax
0x180080882  test    eax, eax
0x180080884  jns     short loc_1800808EA
0x180080886  mov     rcx, cs:WPP_GLOBAL_Control
0x18008088d  lea     rax, WPP_GLOBAL_Control
0x180080894  cmp     rcx, rax
0x180080897  jz      loc_180080B71
0x18008089d  test    byte ptr [rcx+1Ch], 8
0x1800808a1  jz      loc_180080B71
0x1800808a7  cmp     byte ptr [rcx+19h], 2
0x1800808ab  jb      loc_180080B71
0x1800808b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800808b6  mov     edx, 1Bh
0x1800808bb  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1800808c2  mov     [rsp+40h+cchWideChar], ebx
0x1800808c6  mov     [rsp+40h+lpOverlapped], rcx
0x1800808cb  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1800808d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800808d9  mov     r9d, eax
0x1800808dc  mov     rcx, [rcx+10h]
0x1800808e0  call    WPP_SF_DsD
0x1800808e5  jmp     loc_180080B71
0x1800808ea  sub     edi, r15d
0x1800808ed  lea     ebx, [rdi+2]
0x1800808f0  mov     ecx, ebx
0x1800808f2  mov     r15d, ebx
0x1800808f5  call    PAL_System_MemAlloc
0x1800808fa  mov     rdi, rax
0x1800808fd  test    rax, rax
0x180080900  jnz     short loc_18008094D
0x180080902  mov     rcx, cs:WPP_GLOBAL_Control
0x180080909  lea     rax, WPP_GLOBAL_Control
0x180080910  cmp     rcx, rax
0x180080913  jz      short loc_180080943
0x180080915  test    byte ptr [rcx+1Ch], 1
0x180080919  jz      short loc_180080943
0x18008091b  cmp     byte ptr [rcx+19h], 2
0x18008091f  jb      short loc_180080943
0x180080921  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180080926  mov     rcx, cs:WPP_GLOBAL_Control
0x18008092d  lea     edx, [rdi+1Ch]
0x180080930  mov     r9d, eax
0x180080933  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008093a  mov     rcx, [rcx+10h]
0x18008093e  call    WPP_SF_D
0x180080943  mov     ebx, 8007000Eh
0x180080948  jmp     loc_180080B71
0x18008094d  mov     r8, r15; Size
0x180080950  xor     edx, edx; Val
0x180080952  mov     rcx, rdi; void *
0x180080955  call    memset_0
0x18008095a  mov     rcx, [rsi+50h]; hFile
0x18008095e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180080962  xor     r15d, r15d
0x180080965  mov     r8d, ebx; nNumberOfBytesToRead
0x180080968  mov     rdx, rdi; lpBuffer
0x18008096b  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x180080970  call    cs:__imp_ReadFile
0x180080976  test    eax, eax
0x180080978  jnz     short loc_180080988
0x18008097a  mov     rcx, rdi; hMem
0x18008097d  call    cs:__imp_LocalFree
0x180080983  jmp     loc_18008080B
0x180080988  xor     edx, edx; int
0x18008098a  mov     rcx, rsi; this
0x18008098d  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x180080992  mov     ebx, eax
0x180080994  test    eax, eax
0x180080996  jns     short loc_1800809FC
0x180080998  mov     rcx, cs:WPP_GLOBAL_Control
0x18008099f  lea     rax, WPP_GLOBAL_Control
0x1800809a6  cmp     rcx, rax
0x1800809a9  jz      loc_180080B68
0x1800809af  test    byte ptr [rcx+1Ch], 8
0x1800809b3  jz      loc_180080B68
0x1800809b9  cmp     byte ptr [rcx+19h], 2
0x1800809bd  jb      loc_180080B68
0x1800809c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800809c8  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1800809cf  mov     [rsp+40h+cchWideChar], ebx
0x1800809d3  mov     [rsp+40h+lpOverlapped], rcx
0x1800809d8  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1800809df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800809e6  mov     edx, 1Dh
0x1800809eb  mov     r9d, eax
0x1800809ee  mov     rcx, [rcx+10h]
0x1800809f2  call    WPP_SF_DsD
0x1800809f7  jmp     loc_180080B68
0x1800809fc  or      esi, 0FFFFFFFFh
0x1800809ff  test    r13d, r13d
0x180080a02  jnz     loc_180080B3B
0x180080a08  cmp     r12d, 0FDE9h
0x180080a0f  jz      short loc_180080A8B
0x180080a11  mov     ebx, [rbp+NumberOfBytesRead]
0x180080a14  lea     r8, [rbp+iResult]; lpiResult
0x180080a18  mov     edx, ebx; iSize
0x180080a1a  mov     [rbp+iResult], esi
0x180080a1d  mov     rcx, rdi; lpv
0x180080a20  call    cs:__imp_IsTextUnicode
0x180080a26  test    eax, eax
0x180080a28  jz      short loc_180080A40
0x180080a2a  cmp     [rbp+iResult], 2
0x180080a2e  jnz     short loc_180080A35
0x180080a30  cmp     ebx, 64h ; 'd'
0x180080a33  jl      short loc_180080A40
0x180080a35  mov     r13d, 1
0x180080a3b  jmp     loc_180080B48
0x180080a40  mov     r9d, 1
0x180080a46  mov     ecx, r15d
0x180080a49  mov     r8d, r15d
0x180080a4c  cmp     r8d, [rbp+NumberOfBytesRead]
0x180080a50  jnb     loc_180080B1F
0x180080a56  mov     eax, r8d
0x180080a59  mov     dl, [rax+rdi]
0x180080a5c  mov     eax, r15d
0x180080a5f  test    dl, dl
0x180080a61  cmovns  eax, r9d
0x180080a65  mov     r9d, eax
0x180080a68  test    ecx, ecx
0x180080a6a  jnz     loc_180080B09
0x180080a70  cmp     dl, 80h
0x180080a73  jb      loc_180080B17
0x180080a79  mov     eax, ecx
0x180080a7b  inc     ecx
0x180080a7d  add     dl, dl
0x180080a7f  js      short loc_180080A79
0x180080a81  mov     ecx, eax
0x180080a83  test    eax, eax
0x180080a85  jnz     loc_180080B17
0x180080a8b  mov     [rsp+40h+cchWideChar], r15d; cchWideChar
0x180080a90  mov     r9d, esi; cbMultiByte
0x180080a93  mov     r8, rdi; lpMultiByteStr
0x180080a96  mov     [rsp+40h+lpOverlapped], r15; lpWideCharStr
0x180080a9b  xor     edx, edx; dwFlags
0x180080a9d  mov     ecx, r12d; CodePage
0x180080aa0  call    cs:__imp_MultiByteToWideChar
0x180080aa6  movsxd  rbx, eax
0x180080aa9  mov     rcx, rbx
0x180080aac  add     rcx, rcx
0x180080aaf  call    PAL_System_MemAlloc
0x180080ab4  mov     r14, rax
0x180080ab7  test    rax, rax
0x180080aba  jnz     loc_180080B8B
0x180080ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180080ac7  lea     rax, WPP_GLOBAL_Control
0x180080ace  cmp     rcx, rax
0x180080ad1  jz      short loc_180080B02
0x180080ad3  test    byte ptr [rcx+1Ch], 1
0x180080ad7  jz      short loc_180080B02
0x180080ad9  cmp     byte ptr [rcx+19h], 2
0x180080add  jb      short loc_180080B02
0x180080adf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180080ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180080aeb  lea     edx, [r14+1Eh]
0x180080aef  mov     r9d, eax
0x180080af2  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x180080af9  mov     rcx, [rcx+10h]
0x180080afd  call    WPP_SF_D
0x180080b02  mov     ebx, 8007000Eh
0x180080b07  jmp     short loc_180080B68
0x180080b09  and     dl, 0C0h
0x180080b0c  cmp     dl, 80h
0x180080b0f  jnz     loc_180080A8B
0x180080b15  dec     ecx
0x180080b17  inc     r8d
0x180080b1a  jmp     loc_180080A4C
0x180080b1f  test    ecx, ecx
0x180080b21  jnz     loc_180080A8B
0x180080b27  test    r9d, r9d
0x180080b2a  jnz     loc_180080A8B
0x180080b30  mov     r12d, 0FDE9h
0x180080b36  jmp     loc_180080A8B
0x180080b3b  cmp     r12d, 0FDE9h
0x180080b42  jz      loc_180080A8B
0x180080b48  mov     r14, rdi
0x180080b4b  mov     rax, [rbp+arg_8]
0x180080b4f  mov     ebx, r15d
0x180080b52  mov     [rax], r14
0x180080b55  test    r13d, r13d
0x180080b58  jz      short loc_180080B63
0x180080b5a  cmp     r12d, 0FDE9h
0x180080b61  jnz     short loc_180080B71
0x180080b63  test    rdi, rdi
0x180080b66  jz      short loc_180080B71
0x180080b68  mov     rcx, rdi; hMem
0x180080b6b  call    cs:__imp_LocalFree
0x180080b71  mov     eax, ebx
0x180080b73  mov     rbx, [rsp+40h+arg_0]
0x180080b7b  add     rsp, 40h
0x180080b7f  pop     r15
0x180080b81  pop     r14
0x180080b83  pop     r13
0x180080b85  pop     r12
0x180080b87  pop     rdi
0x180080b88  pop     rsi
0x180080b89  pop     rbp
0x180080b8a  retn
0x180080b8b  mov     [rsp+40h+cchWideChar], ebx; cchWideChar
0x180080b8f  mov     r9d, esi; cbMultiByte
0x180080b92  mov     r8, rdi; lpMultiByteStr
0x180080b95  mov     [rsp+40h+lpOverlapped], rax; lpWideCharStr
0x180080b9a  xor     edx, edx; dwFlags
0x180080b9c  mov     ecx, r12d; CodePage
0x180080b9f  call    cs:__imp_MultiByteToWideChar
0x180080ba5  test    eax, eax
0x180080ba7  jnz     short loc_180080B4B
0x180080ba9  call    cs:__imp_GetLastError
0x180080baf  mov     ebx, eax
0x180080bb1  test    eax, eax
0x180080bb3  jle     short loc_180080BBE
0x180080bb5  movzx   ebx, ax
0x180080bb8  or      ebx, 80070000h
  ... truncated ...
```
