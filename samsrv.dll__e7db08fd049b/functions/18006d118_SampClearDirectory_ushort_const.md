# SampClearDirectory(ushort const *)

- ea: `0x18006d118`
- end: `0x18006d2f6`
- name: `?SampClearDirectory@@YAKPEBG@Z`
- size: `478`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006f2f4`

## callees

- `0x180027d08`
- `0x18002cd80`
- `0x18002d720`
- `0x18005308c`
- `0x18006d118`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006d1ec`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006d1ec`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006d284`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006d284`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006d291`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006d291`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006d235`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006d235`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006d263`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006d263`

## pseudocode

```c
__int64 __fastcall SampClearDirectory(LPCWSTR lpPathName)
{
  PUNICODE_STRING v3; // rcx
  DWORD LastError; // ebx
  __int64 v5; // rdx
  _WIN32_FIND_DATAW *p_FindFileData; // rax
  __int64 v7; // rcx
  char *FirstFileW; // rsi
  bool i; // zf
  __int64 v10; // rcx
  _WIN32_FIND_DATAW *v11; // rax
  DWORD v12; // eax
  DWORD v13; // edi
  bool v14; // zf
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-6A8h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-458h] BYREF
  WCHAR v17[264]; // [rsp+490h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( lpPathName )
  {
    if ( (int)RtlStringCbPrintfW(FileName, 0x208u, L"%s\\*.*", lpPathName) >= 0 )
    {
      LastError = 0;
      p_FindFileData = &FindFileData;
      v7 = 592;
      do
      {
        LOBYTE(p_FindFileData->dwFileAttributes) = 0;
        p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 1);
        --v7;
      }
      while ( v7 );
      FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
      for ( i = FirstFileW + 1 == 0; !i; i = !FindNextFileW(FirstFileW, &FindFileData) )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && (int)RtlStringCbPrintfW(v17, 0x208u, L"%ws\\%ws", lpPathName, FindFileData.cFileName) >= 0
          && !DeleteFileW(v17) )
        {
          LastError = GetLastError();
        }
        v10 = 592;
        v11 = &FindFileData;
        do
        {
          LOBYTE(v11->dwFileAttributes) = 0;
          v11 = (_WIN32_FIND_DATAW *)((char *)v11 + 1);
          --v10;
        }
        while ( v10 );
      }
      v12 = GetLastError();
      v13 = 0;
      if ( v12 != 18 )
        v13 = v12;
      if ( FirstFileW != (char *)-1LL )
        FindClose(FirstFileW);
      v14 = v13 == 0;
      if ( !v13 )
      {
        if ( !RemoveDirectoryW(lpPathName) )
          LastError = GetLastError();
        v14 = 1;
      }
      v3 = WPP_GLOBAL_Control;
      if ( !v14 )
        LastError = v13;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return LastError;
      v5 = 161;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      LastError = 87;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return LastError;
      v5 = 160;
    }
    WPP_SF_DdD(v3[3].Buffer, v5, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, LastError, LastError, LastError);
    return LastError;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_DdD(WPP_GLOBAL_Control[3].Buffer, 159, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18006d118  push    rbx
0x18006d11a  push    rbp
0x18006d11b  push    rsi
0x18006d11c  push    rdi
0x18006d11d  sub     rsp, 6B8h
0x18006d124  mov     rax, cs:__security_cookie
0x18006d12b  xor     rax, rsp
0x18006d12e  mov     [rsp+6D8h+var_38], rax
0x18006d136  mov     rbp, rcx
0x18006d139  mov     edi, 250h
0x18006d13e  mov     r8d, edi; Size
0x18006d141  lea     rcx, [rsp+6D8h+FindFileData]; void *
0x18006d146  xor     edx, edx; Val
0x18006d148  call    memset_0
0x18006d14d  test    rbp, rbp
0x18006d150  jnz     short loc_18006D189
0x18006d152  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d159  test    dword ptr [rcx+44h], 20000h
0x18006d160  jz      short loc_18006D182
0x18006d162  mov     rcx, [rcx+38h]
0x18006d166  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006d16d  mov     edx, 9Fh
0x18006d172  mov     [rsp+6D8h+var_6B0], ebp
0x18006d176  xor     r9d, r9d
0x18006d179  mov     dword ptr [rsp+6D8h+var_6B8], ebp
0x18006d17d  call    WPP_SF_DdD
0x18006d182  xor     eax, eax
0x18006d184  jmp     loc_18006D2DA
0x18006d189  mov     r9, rbp
0x18006d18c  lea     r8, aS; "%s\\*.*"
0x18006d193  mov     edx, 208h; unsigned __int64
0x18006d198  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x18006d1a0  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d1a5  test    eax, eax
0x18006d1a7  jns     short loc_18006D1CA
0x18006d1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d1b0  mov     ebx, 57h ; 'W'
0x18006d1b5  test    dword ptr [rcx+44h], 20000h
0x18006d1bc  jz      loc_18006D2D8
0x18006d1c2  lea     edx, [rbx+49h]
0x18006d1c5  jmp     loc_18006D2BD
0x18006d1ca  xor     ebx, ebx
0x18006d1cc  lea     rax, [rsp+6D8h+FindFileData]
0x18006d1d1  mov     rcx, rdi
0x18006d1d4  mov     [rax], bl
0x18006d1d6  inc     rax
0x18006d1d9  sub     rcx, 1
0x18006d1dd  jnz     short loc_18006D1D4
0x18006d1df  lea     rdx, [rsp+6D8h+FindFileData]; lpFindFileData
0x18006d1e4  lea     rcx, [rsp+6D8h+FileName]; lpFileName
0x18006d1ec  call    cs:__imp_FindFirstFileW
0x18006d1f2  mov     rsi, rax
0x18006d1f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006d1f9  jmp     short loc_18006D26B
0x18006d1fb  mov     eax, [rsp+6D8h+FindFileData.dwFileAttributes]
0x18006d1ff  test    al, 10h
0x18006d201  jnz     short loc_18006D247
0x18006d203  lea     rax, [rsp+6D8h+FindFileData.cFileName]
0x18006d208  mov     r9, rbp
0x18006d20b  lea     r8, aWsWs; "%ws\\%ws"
0x18006d212  mov     [rsp+6D8h+var_6B8], rax
0x18006d217  mov     edx, 208h; unsigned __int64
0x18006d21c  lea     rcx, [rsp+6D8h+var_248]; unsigned __int16 *
0x18006d224  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d229  test    eax, eax
0x18006d22b  js      short loc_18006D247
0x18006d22d  lea     rcx, [rsp+6D8h+var_248]; lpFileName
0x18006d235  call    cs:__imp_DeleteFileW
0x18006d23b  test    eax, eax
0x18006d23d  jnz     short loc_18006D247
0x18006d23f  call    cs:__imp_GetLastError
0x18006d245  mov     ebx, eax
0x18006d247  mov     rcx, rdi
0x18006d24a  lea     rax, [rsp+6D8h+FindFileData]
0x18006d24f  mov     byte ptr [rax], 0
0x18006d252  inc     rax
0x18006d255  sub     rcx, 1
0x18006d259  jnz     short loc_18006D24F
0x18006d25b  lea     rdx, [rsp+6D8h+FindFileData]; lpFindFileData
0x18006d260  mov     rcx, rsi; hFindFile
0x18006d263  call    cs:__imp_FindNextFileW
0x18006d269  test    eax, eax
0x18006d26b  jnz     short loc_18006D1FB
0x18006d26d  call    cs:__imp_GetLastError
0x18006d273  xor     edi, edi
0x18006d275  cmp     eax, 12h
0x18006d278  cmovnz  edi, eax
0x18006d27b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006d27f  jz      short loc_18006D28A
0x18006d281  mov     rcx, rsi; hFindFile
0x18006d284  call    cs:__imp_FindClose
0x18006d28a  test    edi, edi
0x18006d28c  jnz     short loc_18006D2A5
0x18006d28e  mov     rcx, rbp; lpPathName
0x18006d291  call    cs:__imp_RemoveDirectoryW
0x18006d297  test    eax, eax
0x18006d299  jnz     short loc_18006D2A3
0x18006d29b  call    cs:__imp_GetLastError
0x18006d2a1  mov     ebx, eax
0x18006d2a3  test    edi, edi
0x18006d2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d2ac  cmovnz  ebx, edi
0x18006d2af  test    dword ptr [rcx+44h], 20000h
0x18006d2b6  jz      short loc_18006D2D8
0x18006d2b8  mov     edx, 0A1h
0x18006d2bd  mov     rcx, [rcx+38h]
0x18006d2c1  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006d2c8  mov     [rsp+6D8h+var_6B0], ebx
0x18006d2cc  mov     r9d, ebx
0x18006d2cf  mov     dword ptr [rsp+6D8h+var_6B8], ebx
0x18006d2d3  call    WPP_SF_DdD
0x18006d2d8  mov     eax, ebx
0x18006d2da  mov     rcx, [rsp+6D8h+var_38]
0x18006d2e2  xor     rcx, rsp; StackCookie
0x18006d2e5  call    __security_check_cookie
0x18006d2ea  add     rsp, 6B8h
0x18006d2f1  pop     rdi
0x18006d2f2  pop     rsi
0x18006d2f3  pop     rbp
0x18006d2f4  pop     rbx
0x18006d2f5  retn
```
