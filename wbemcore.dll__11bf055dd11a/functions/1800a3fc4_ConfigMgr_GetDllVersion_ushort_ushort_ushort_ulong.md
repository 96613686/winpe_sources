# ConfigMgr::GetDllVersion(ushort *,ushort *,ushort *,ulong)

- ea: `0x1800a3fc4`
- end: `0x1800a43af`
- name: `?GetDllVersion@ConfigMgr@@SAHPEAG00K@Z`
- size: `1003`
- prototype: `static int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b3a1c`

## callees

- `0x18000b140`
- `0x18000e8c0`
- `0x18001cce0`
- `0x18001d390`
- `0x1800a3fc4`
- `0x1800ce510`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800a4156`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800a4156`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a41e6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a4288`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a431a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a41e6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a4288`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a431a`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800a41af`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800a41af`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4184`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4184`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4388`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4388`
- `wbemcomn!GetMemLogObject` at `0x1800a4047`
- `wbemcomn!GetMemLogObject` at `0x1800a40a5`
- `wbemcomn!GetMemLogObject` at `0x1800a4103`
- `wbemcomn!GetMemLogObject` at `0x1800a422c`
- `wbemcomn!GetMemLogObject` at `0x1800a42be`
- `wbemcomn!GetMemLogObject` at `0x1800a433c`
- `wbemcomn!GetMemLogObject` at `0x1800a4047`
- `wbemcomn!GetMemLogObject` at `0x1800a40a5`
- `wbemcomn!GetMemLogObject` at `0x1800a4103`
- `wbemcomn!GetMemLogObject` at `0x1800a422c`
- `wbemcomn!GetMemLogObject` at `0x1800a42be`
- `wbemcomn!GetMemLogObject` at `0x1800a433c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4052`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a40b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a410e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4237`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a42c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4347`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4052`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a40b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a410e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4237`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a42c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4347`

## string_xrefs

- `0x1800a40e9`: `wbemcore.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConfigMgr::GetDllVersion(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v4; // rax
  int v5; // ebx
  CMemoryLog *MemLogObject; // rax
  int v7; // ebx
  CMemoryLog *v8; // rax
  int v9; // ebx
  CMemoryLog *v10; // rax
  signed int FileVersionInfoSize; // eax
  DWORD v12; // esi
  unsigned int FileVersionInfo; // ebx
  void *v15; // rax
  void *v16; // rdi
  int v17; // ebx
  CMemoryLog *v18; // rax
  int v19; // ebx
  CMemoryLog *v20; // rax
  int v21; // esi
  CMemoryLog *v22; // rax
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpBuffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR wstrFilename[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubBlock[264]; // [rsp+260h] [rbp+160h] BYREF

  dwHandle = 0;
  wstrFilename[0] = 0;
  if ( g_pWorkDir )
  {
    v4 = -1;
    do
      ++v4;
    while ( g_pWorkDir[v4] );
    if ( (int)v4 + 14 > 260 )
      return 0;
  }
  if ( g_pWorkDir )
  {
    v5 = StringCchCopyW(wstrFilename, 0x104u, g_pWorkDir);
    if ( v5 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v5);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v5);
      }
    }
  }
  v7 = StringCchCatW(wstrFilename, 0x104u, L"\\");
  if ( v7 < 0 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, v7);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v7);
    }
  }
  v9 = StringCchCatW(wstrFilename, 0x104u, L"wbemcore.dll");
  if ( v9 < 0 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, v9);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v9);
    }
  }
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, wstrFilename, &dwHandle);
  v12 = FileVersionInfoSize;
  if ( FileVersionInfoSize < 1 )
    return 0;
  FileVersionInfo = 0;
  v15 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(FileVersionInfoSize, 2u));
  v16 = v15;
  if ( v15 )
  {
    lpBuffer[1] = v15;
    FileVersionInfo = GetFileVersionInfoExW(3u, wstrFilename, 0, v12, v15);
    if ( FileVersionInfo )
    {
      v26 = 0;
      puLen = 260;
      lpBuffer[0] = 0;
      if ( VerQueryValueW(v16, L"\\VarFileInfo\\Translation", lpBuffer, &puLen) )
      {
        LODWORD(lpData) = *((__int16 *)lpBuffer[0] + 1);
        v17 = StringCchPrintfW(
                SubBlock,
                0x104u,
                L"\\StringFileInfo\\%04x%04x\\%s",
                (unsigned int)*(__int16 *)lpBuffer[0],
                lpData,
                L"ProductVersion");
        if ( v17 < 0 )
        {
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, v17);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              (unsigned int)v17);
          }
        }
        FileVersionInfo = VerQueryValueW(v16, SubBlock, (LPVOID *)&v26, &puLen);
        if ( FileVersionInfo )
          goto LABEL_38;
      }
      v19 = StringCchPrintfW(SubBlock, 0x104u, L"\\StringFileInfo\\040904E4\\%s", L"ProductVersion");
      if ( v19 < 0 )
      {
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, v19);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)v19);
        }
      }
      FileVersionInfo = VerQueryValueW(v16, SubBlock, (LPVOID *)&v26, &puLen);
      if ( FileVersionInfo )
      {
LABEL_38:
        v21 = StringCchCopyW(a3, 0x104u, v26);
        if ( v21 < 0 )
        {
          v22 = GetMemLogObject();
          CMemoryLog::Write(v22, v21);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              108,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              (unsigned int)v21);
          }
        }
      }
    }
    CWin32DefaultArena::WbemMemFree(v16);
  }
  return FileVersionInfo;
}

```

## disassembly

```asm
0x1800a3fc4  push    rbp
0x1800a3fc6  push    rbx
0x1800a3fc7  push    rsi
0x1800a3fc8  push    rdi
0x1800a3fc9  push    r14
0x1800a3fcb  push    r15
0x1800a3fcd  lea     rbp, [rsp-388h]
0x1800a3fd5  sub     rsp, 488h
0x1800a3fdc  mov     rax, cs:__security_cookie
0x1800a3fe3  xor     rax, rsp
0x1800a3fe6  mov     [rbp+3B0h+var_40], rax
0x1800a3fed  mov     r14, r8
0x1800a3ff0  xor     r15d, r15d
0x1800a3ff3  mov     [rsp+4B0h+dwHandle], r15d
0x1800a3ff8  mov     [rsp+4B0h+wstrFilename], r15w
0x1800a3ffe  mov     edi, 104h
0x1800a4003  mov     r8, cs:?g_pWorkDir@@3PEAGEA; unsigned __int16 *
0x1800a400a  test    r8, r8
0x1800a400d  jz      short loc_1800A4028
0x1800a400f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a4013  inc     rax
0x1800a4016  cmp     [r8+rax*2], r15w
0x1800a401b  jnz     short loc_1800A4013
0x1800a401d  add     eax, 0Eh
0x1800a4020  cmp     eax, edi
0x1800a4022  jg      loc_1800A4164
0x1800a4028  lea     rsi, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a402f  test    r8, r8
0x1800a4032  jz      short loc_1800A408B
0x1800a4034  mov     rdx, rdi; unsigned __int64
0x1800a4037  lea     rcx, [rsp+4B0h+wstrFilename]; unsigned __int16 *
0x1800a403c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a4041  mov     ebx, eax
0x1800a4043  test    eax, eax
0x1800a4045  jns     short loc_1800A408B
0x1800a4047  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a404d  mov     edx, ebx
0x1800a404f  mov     rcx, rax
0x1800a4052  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4058  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a405f  lea     rax, WPP_GLOBAL_Control
0x1800a4066  cmp     rcx, rax
0x1800a4069  jz      short loc_1800A408B
0x1800a406b  test    byte ptr [rcx+1Ch], 1
0x1800a406f  jz      short loc_1800A408B
0x1800a4071  cmp     byte ptr [rcx+19h], 2
0x1800a4075  jb      short loc_1800A408B
0x1800a4077  mov     edx, 67h ; 'g'
0x1800a407c  mov     r9d, ebx
0x1800a407f  mov     r8, rsi
0x1800a4082  mov     rcx, [rcx+10h]
0x1800a4086  call    WPP_SF_d
0x1800a408b  lea     r8, Delimiter; "\\"
0x1800a4092  mov     rdx, rdi; unsigned __int64
0x1800a4095  lea     rcx, [rsp+4B0h+wstrFilename]; unsigned __int16 *
0x1800a409a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a409f  mov     ebx, eax
0x1800a40a1  test    eax, eax
0x1800a40a3  jns     short loc_1800A40E9
0x1800a40a5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a40ab  mov     edx, ebx
0x1800a40ad  mov     rcx, rax
0x1800a40b0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a40b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a40bd  lea     rax, WPP_GLOBAL_Control
0x1800a40c4  cmp     rcx, rax
0x1800a40c7  jz      short loc_1800A40E9
0x1800a40c9  test    byte ptr [rcx+1Ch], 1
0x1800a40cd  jz      short loc_1800A40E9
0x1800a40cf  cmp     byte ptr [rcx+19h], 2
0x1800a40d3  jb      short loc_1800A40E9
0x1800a40d5  mov     edx, 68h ; 'h'
0x1800a40da  mov     r9d, ebx
0x1800a40dd  mov     r8, rsi
0x1800a40e0  mov     rcx, [rcx+10h]
0x1800a40e4  call    WPP_SF_d
0x1800a40e9  lea     r8, aWbemcoreDll_0; "wbemcore.dll"
0x1800a40f0  mov     rdx, rdi; unsigned __int64
0x1800a40f3  lea     rcx, [rsp+4B0h+wstrFilename]; unsigned __int16 *
0x1800a40f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a40fd  mov     ebx, eax
0x1800a40ff  test    eax, eax
0x1800a4101  jns     short loc_1800A4147
0x1800a4103  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4109  mov     edx, ebx
0x1800a410b  mov     rcx, rax
0x1800a410e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4114  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a411b  lea     rax, WPP_GLOBAL_Control
0x1800a4122  cmp     rcx, rax
0x1800a4125  jz      short loc_1800A4147
0x1800a4127  test    byte ptr [rcx+1Ch], 1
0x1800a412b  jz      short loc_1800A4147
0x1800a412d  cmp     byte ptr [rcx+19h], 2
0x1800a4131  jb      short loc_1800A4147
0x1800a4133  mov     edx, 69h ; 'i'
0x1800a4138  mov     r9d, ebx
0x1800a413b  mov     r8, rsi
0x1800a413e  mov     rcx, [rcx+10h]
0x1800a4142  call    WPP_SF_d
0x1800a4147  lea     r8, [rsp+4B0h+dwHandle]; lpdwHandle
0x1800a414c  lea     rdx, [rsp+4B0h+wstrFilename]; lpwstrFilename
0x1800a4151  mov     ecx, 1; dwFlags
0x1800a4156  call    cs:__imp_GetFileVersionInfoSizeExW
0x1800a415c  movsxd  rsi, eax
0x1800a415f  cmp     esi, 1
0x1800a4162  jge     short loc_1800A416B
0x1800a4164  xor     eax, eax
0x1800a4166  jmp     loc_1800A4390
0x1800a416b  mov     ebx, r15d
0x1800a416e  mov     eax, 2
0x1800a4173  mul     rsi
0x1800a4176  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a417d  cmovb   rax, rcx
0x1800a4181  mov     rcx, rax
0x1800a4184  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800a418a  mov     rdi, rax
0x1800a418d  test    rax, rax
0x1800a4190  jz      loc_1800A438E
0x1800a4196  mov     [rsp+4B0h+var_468], rax
0x1800a419b  mov     [rsp+4B0h+lpData], rax; lpData
0x1800a41a0  mov     r9d, esi; dwLen
0x1800a41a3  xor     r8d, r8d; dwHandle
0x1800a41a6  lea     rdx, [rsp+4B0h+wstrFilename]; lpwstrFilename
0x1800a41ab  lea     ecx, [r8+3]; dwFlags
0x1800a41af  call    cs:__imp_GetFileVersionInfoExW
0x1800a41b5  mov     ebx, eax
0x1800a41b7  test    eax, eax
0x1800a41b9  jz      loc_1800A4385
0x1800a41bf  mov     [rsp+4B0h+var_478], r15
0x1800a41c4  mov     esi, 104h
0x1800a41c9  mov     [rsp+4B0h+puLen], esi
0x1800a41cd  mov     [rsp+4B0h+lpBuffer], r15
0x1800a41d2  lea     r9, [rsp+4B0h+puLen]; puLen
0x1800a41d7  lea     r8, [rsp+4B0h+lpBuffer]; lplpBuffer
0x1800a41dc  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x1800a41e3  mov     rcx, rdi; pBlock
0x1800a41e6  call    cs:__imp_VerQueryValueW
0x1800a41ec  lea     rdx, aProductversion; "ProductVersion"
0x1800a41f3  test    eax, eax
0x1800a41f5  jz      loc_1800A429F
0x1800a41fb  mov     rax, [rsp+4B0h+lpBuffer]
0x1800a4200  movsx   ecx, word ptr [rax+2]
0x1800a4204  movsx   r9d, word ptr [rax]
0x1800a4208  mov     [rsp+4B0h+var_488], rdx
0x1800a420d  mov     dword ptr [rsp+4B0h+lpData], ecx
0x1800a4211  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\%s"
0x1800a4218  mov     edx, esi; unsigned __int64
0x1800a421a  lea     rcx, [rbp+3B0h+SubBlock]; unsigned __int16 *
0x1800a4221  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4226  mov     ebx, eax
0x1800a4228  test    eax, eax
0x1800a422a  jns     short loc_1800A4274
0x1800a422c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4232  mov     edx, ebx
0x1800a4234  mov     rcx, rax
0x1800a4237  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a423d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4244  lea     rax, WPP_GLOBAL_Control
0x1800a424b  cmp     rcx, rax
0x1800a424e  jz      short loc_1800A4274
0x1800a4250  test    byte ptr [rcx+1Ch], 1
0x1800a4254  jz      short loc_1800A4274
0x1800a4256  cmp     byte ptr [rcx+19h], 2
0x1800a425a  jb      short loc_1800A4274
0x1800a425c  mov     edx, 6Ah ; 'j'
0x1800a4261  mov     r9d, ebx
0x1800a4264  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a426b  mov     rcx, [rcx+10h]
0x1800a426f  call    WPP_SF_d
0x1800a4274  lea     r9, [rsp+4B0h+puLen]; puLen
0x1800a4279  lea     r8, [rsp+4B0h+var_478]; lplpBuffer
0x1800a427e  lea     rdx, [rbp+3B0h+SubBlock]; lpSubBlock
0x1800a4285  mov     rcx, rdi; pBlock
0x1800a4288  call    cs:__imp_VerQueryValueW
0x1800a428e  mov     ebx, eax
0x1800a4290  test    eax, eax
0x1800a4292  jnz     loc_1800A4326
0x1800a4298  lea     rdx, aProductversion; "ProductVersion"
0x1800a429f  mov     r9, rdx
0x1800a42a2  lea     r8, aStringfileinfo_1; "\\StringFileInfo\\040904E4\\%s"
0x1800a42a9  mov     rdx, rsi; unsigned __int64
0x1800a42ac  lea     rcx, [rbp+3B0h+SubBlock]; unsigned __int16 *
0x1800a42b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a42b8  mov     ebx, eax
0x1800a42ba  test    eax, eax
0x1800a42bc  jns     short loc_1800A4306
0x1800a42be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a42c4  mov     edx, ebx
0x1800a42c6  mov     rcx, rax
0x1800a42c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a42cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a42d6  lea     rax, WPP_GLOBAL_Control
0x1800a42dd  cmp     rcx, rax
0x1800a42e0  jz      short loc_1800A4306
0x1800a42e2  test    byte ptr [rcx+1Ch], 1
0x1800a42e6  jz      short loc_1800A4306
0x1800a42e8  cmp     byte ptr [rcx+19h], 2
0x1800a42ec  jb      short loc_1800A4306
0x1800a42ee  mov     edx, 6Bh ; 'k'
0x1800a42f3  mov     r9d, ebx
0x1800a42f6  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a42fd  mov     rcx, [rcx+10h]
0x1800a4301  call    WPP_SF_d
0x1800a4306  lea     r9, [rsp+4B0h+puLen]; puLen
0x1800a430b  lea     r8, [rsp+4B0h+var_478]; lplpBuffer
0x1800a4310  lea     rdx, [rbp+3B0h+SubBlock]; lpSubBlock
0x1800a4317  mov     rcx, rdi; pBlock
0x1800a431a  call    cs:__imp_VerQueryValueW
0x1800a4320  mov     ebx, eax
0x1800a4322  test    eax, eax
0x1800a4324  jz      short loc_1800A4385
0x1800a4326  mov     r8, [rsp+4B0h+var_478]; unsigned __int16 *
0x1800a432b  mov     rdx, rsi; unsigned __int64
0x1800a432e  mov     rcx, r14; unsigned __int16 *
0x1800a4331  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a4336  mov     esi, eax
0x1800a4338  test    eax, eax
0x1800a433a  jns     short loc_1800A4385
0x1800a433c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4342  mov     edx, esi
0x1800a4344  mov     rcx, rax
0x1800a4347  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a434d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4354  lea     rax, WPP_GLOBAL_Control
0x1800a435b  cmp     rcx, rax
0x1800a435e  jz      short loc_1800A4385
0x1800a4360  test    byte ptr [rcx+1Ch], 1
0x1800a4364  jz      short loc_1800A4385
0x1800a4366  cmp     byte ptr [rcx+19h], 2
0x1800a436a  jb      short loc_1800A4385
0x1800a436c  mov     edx, 6Ch ; 'l'
0x1800a4371  mov     r9d, esi
0x1800a4374  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a437b  mov     rcx, [rcx+10h]
0x1800a437f  call    WPP_SF_d
0x1800a4384  nop
0x1800a4385  mov     rcx, rdi
0x1800a4388  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a438e  mov     eax, ebx
0x1800a4390  mov     rcx, [rbp+3B0h+var_40]
0x1800a4397  xor     rcx, rsp; StackCookie
0x1800a439a  call    __security_check_cookie
0x1800a439f  add     rsp, 488h
0x1800a43a6  pop     r15
0x1800a43a8  pop     r14
0x1800a43aa  pop     rdi
0x1800a43ab  pop     rsi
0x1800a43ac  pop     rbx
0x1800a43ad  pop     rbp
0x1800a43ae  retn
```
