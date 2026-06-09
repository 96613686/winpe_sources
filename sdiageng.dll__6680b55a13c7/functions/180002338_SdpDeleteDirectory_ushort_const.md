# SdpDeleteDirectory(ushort const *)

- ea: `0x180002338`
- end: `0x18000254b`
- name: `?SdpDeleteDirectory@@YAJPEBG@Z`
- size: `531`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180002338`
- `0x18000fc10`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180002338`
- `0x180002978`
- `0x180026fa0`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000240f`
- `msvcrt!_wcsicmp` at `0x180002429`
- `msvcrt!_wcsicmp` at `0x18000240f`
- `msvcrt!_wcsicmp` at `0x180002429`
- `KERNEL32!GetLastError` at `0x180002489`
- `KERNEL32!GetLastError` at `0x1800024e9`
- `KERNEL32!GetLastError` at `0x180002489`
- `KERNEL32!GetLastError` at `0x1800024e9`
- `KERNEL32!FindFirstFileW` at `0x1800023ec`
- `KERNEL32!FindFirstFileW` at `0x1800023ec`
- `KERNEL32!FindClose` at `0x1800024d2`
- `KERNEL32!FindClose` at `0x1800024d2`
- `KERNEL32!DeleteFileW` at `0x18000247f`
- `KERNEL32!DeleteFileW` at `0x18000247f`
- `KERNEL32!FindNextFileW` at `0x1800024c1`
- `KERNEL32!FindNextFileW` at `0x1800024c1`
- `KERNEL32!RemoveDirectoryW` at `0x1800024db`
- `KERNEL32!RemoveDirectoryW` at `0x1800024db`

## string_xrefs

- `0x180002384`: `SdpDeleteDirectory`
- `0x1800024a8`: `SdpDeleteDirectory`
- `0x18000250b`: `SdpDeleteDirectory`

## pseudocode

```c
__int64 __fastcall SdpDeleteDirectory(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v3; // r8d
  unsigned __int16 *v4; // rax
  WCHAR *v5; // rdi
  int v6; // eax
  int v7; // r9d
  int v8; // r8d
  char *FirstFileW; // rbx
  signed int LastError; // eax
  int v11; // r8d
  bool v12; // sf
  signed int v13; // eax
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 465;
LABEL_3:
    SdpDebugTrace(1u, L"SdpDeleteDirectory", v3, v2);
    return v2;
  }
  v4 = (unsigned __int16 *)operator new[](0x208u);
  v5 = v4;
  if ( !v4 )
  {
    v2 = -2147024882;
    v3 = 468;
    goto LABEL_3;
  }
  v6 = StringCchPrintfW(v4, 0x104u, L"%s\\*", a1);
  v2 = v6;
  if ( v6 < 0 )
  {
    v7 = v6;
    v8 = 471;
    goto LABEL_30;
  }
  FirstFileW = (char *)FindFirstFileW(v5, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_24;
  do
  {
    if ( _wcsicmp(FindFileData.cFileName, L".") && _wcsicmp(FindFileData.cFileName, L"..") )
    {
      LastError = StringCchPrintfW(v5, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
      if ( LastError < 0 )
      {
        v11 = 487;
LABEL_21:
        SdpDebugTrace(2u, L"SdpDeleteDirectory", v11, LastError);
        continue;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        LastError = SdpDeleteDirectory(v5);
        if ( LastError >= 0 )
          continue;
        v11 = 491;
        goto LABEL_21;
      }
      if ( !DeleteFileW(v5) )
      {
        LastError = GetLastError();
        v12 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v12 = LastError < 0;
        }
        if ( v12 )
        {
          v11 = 495;
          goto LABEL_21;
        }
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
LABEL_24:
  if ( RemoveDirectoryW(a1) )
  {
    v2 = 0;
    goto LABEL_31;
  }
  v13 = GetLastError();
  v2 = v13;
  if ( v13 > 0 )
    v2 = (unsigned __int16)v13 | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
  {
    v7 = v2;
    v8 = 504;
LABEL_30:
    SdpDebugTrace(1u, L"SdpDeleteDirectory", v8, v7);
  }
LABEL_31:
  operator delete(v5);
  return v2;
}

```

## disassembly

```asm
0x180002338  mov     [rsp+arg_8], rbx
0x18000233d  mov     [rsp+arg_10], rsi
0x180002342  push    rdi
0x180002343  sub     rsp, 290h
0x18000234a  mov     rax, cs:__security_cookie
0x180002351  xor     rax, rsp
0x180002354  mov     [rsp+298h+var_18], rax
0x18000235c  mov     rsi, rcx
0x18000235f  xor     edx, edx; Val
0x180002361  lea     rcx, [rsp+298h+FindFileData]; void *
0x180002366  mov     r8d, 250h; Size
0x18000236c  call    memset_0
0x180002371  test    rsi, rsi
0x180002374  jnz     short loc_18000239A
0x180002376  mov     ebx, 80070057h
0x18000237b  mov     r8d, 1D1h; int
0x180002381  mov     r9d, ebx; int
0x180002384  lea     rdx, aSdpdeletedirec; "SdpDeleteDirectory"
0x18000238b  mov     ecx, 1; Level
0x180002390  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002395  jmp     loc_180002524
0x18000239a  mov     ecx, 208h; unsigned __int64
0x18000239f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800023a4  mov     rdi, rax
0x1800023a7  test    rax, rax
0x1800023aa  jnz     short loc_1800023B9
0x1800023ac  mov     ebx, 8007000Eh
0x1800023b1  mov     r8d, 1D4h
0x1800023b7  jmp     short loc_180002381
0x1800023b9  mov     r9, rsi
0x1800023bc  lea     r8, aS; "%s\\*"
0x1800023c3  mov     edx, 104h; unsigned __int64
0x1800023c8  mov     rcx, rdi; unsigned __int16 *
0x1800023cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800023d0  mov     ebx, eax
0x1800023d2  test    eax, eax
0x1800023d4  jns     short loc_1800023E4
0x1800023d6  mov     r9d, eax
0x1800023d9  mov     r8d, 1D7h
0x1800023df  jmp     loc_18000250B
0x1800023e4  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x1800023e9  mov     rcx, rdi; lpFileName
0x1800023ec  call    cs:__imp_FindFirstFileW
0x1800023f2  mov     rbx, rax
0x1800023f5  lea     rcx, [rax-1]
0x1800023f9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800023fd  ja      loc_1800024D8
0x180002403  lea     rdx, String2; "."
0x18000240a  lea     rcx, [rsp+298h+FindFileData.cFileName]; String1
0x18000240f  call    cs:__imp__wcsicmp
0x180002415  test    eax, eax
0x180002417  jz      loc_1800024B9
0x18000241d  lea     rdx, asc_18002D4A0; ".."
0x180002424  lea     rcx, [rsp+298h+FindFileData.cFileName]; String1
0x180002429  call    cs:__imp__wcsicmp
0x18000242f  test    eax, eax
0x180002431  jz      loc_1800024B9
0x180002437  lea     rax, [rsp+298h+FindFileData.cFileName]
0x18000243c  mov     r9, rsi
0x18000243f  lea     r8, aSS; "%s\\%s"
0x180002446  mov     [rsp+298h+var_278], rax
0x18000244b  mov     edx, 104h; unsigned __int64
0x180002450  mov     rcx, rdi; unsigned __int16 *
0x180002453  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002458  test    eax, eax
0x18000245a  jns     short loc_180002464
0x18000245c  mov     r8d, 1E7h
0x180002462  jmp     short loc_1800024A5
0x180002464  test    byte ptr [rsp+298h+FindFileData.dwFileAttributes], 10h
0x180002469  mov     rcx, rdi; unsigned __int16 *
0x18000246c  jz      short loc_18000247F
0x18000246e  call    ?SdpDeleteDirectory@@YAJPEBG@Z; SdpDeleteDirectory(ushort const *)
0x180002473  test    eax, eax
0x180002475  jns     short loc_1800024B9
0x180002477  mov     r8d, 1EBh
0x18000247d  jmp     short loc_1800024A5
0x18000247f  call    cs:__imp_DeleteFileW
0x180002485  test    eax, eax
0x180002487  jnz     short loc_1800024B9
0x180002489  call    cs:__imp_GetLastError
0x18000248f  test    eax, eax
0x180002491  jle     short loc_18000249D
0x180002493  movzx   eax, ax
0x180002496  or      eax, 80070000h
0x18000249b  test    eax, eax
0x18000249d  jns     short loc_1800024B9
0x18000249f  mov     r8d, 1EFh; int
0x1800024a5  mov     r9d, eax; int
0x1800024a8  lea     rdx, aSdpdeletedirec; "SdpDeleteDirectory"
0x1800024af  mov     ecx, 2; Level
0x1800024b4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800024b9  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x1800024be  mov     rcx, rbx; hFindFile
0x1800024c1  call    cs:__imp_FindNextFileW
0x1800024c7  test    eax, eax
0x1800024c9  jnz     loc_180002403
0x1800024cf  mov     rcx, rbx; hFindFile
0x1800024d2  call    cs:__imp_FindClose
0x1800024d8  mov     rcx, rsi; lpPathName
0x1800024db  call    cs:__imp_RemoveDirectoryW
0x1800024e1  test    eax, eax
0x1800024e3  jz      short loc_1800024E9
0x1800024e5  xor     ebx, ebx
0x1800024e7  jmp     short loc_18000251C
0x1800024e9  call    cs:__imp_GetLastError
0x1800024ef  mov     ebx, eax
0x1800024f1  test    eax, eax
0x1800024f3  jle     short loc_1800024FE
0x1800024f5  movzx   ebx, ax
0x1800024f8  or      ebx, 80070000h
0x1800024fe  test    ebx, ebx
0x180002500  jns     short loc_18000251C
0x180002502  mov     r9d, ebx; int
0x180002505  mov     r8d, 1F8h; int
0x18000250b  lea     rdx, aSdpdeletedirec; "SdpDeleteDirectory"
0x180002512  mov     ecx, 1; Level
0x180002517  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000251c  mov     rcx, rdi; Block
0x18000251f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002524  mov     eax, ebx
0x180002526  mov     rcx, [rsp+298h+var_18]
0x18000252e  xor     rcx, rsp; StackCookie
0x180002531  call    __security_check_cookie
0x180002536  lea     r11, [rsp+298h+var_8]
0x18000253e  mov     rbx, [r11+18h]
0x180002542  mov     rsi, [r11+20h]
0x180002546  mov     rsp, r11
0x180002549  pop     rdi
0x18000254a  retn
```
