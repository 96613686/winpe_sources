# CEcsPath::DeleteDirectoryRecursive(ushort const *,ushort const *,bool)

- ea: `0x18006269c`
- end: `0x180062aaf`
- name: `?DeleteDirectoryRecursive@CEcsPath@@SA_NPEBG0_N@Z`
- size: `1043`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800451e0`
- `0x18006269c`
- `0x180080214`
- `0x1800c7390`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007e10`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x180015150`
- `0x180023c90`
- `0x18002dad0`
- `0x180061b18`
- `0x18006269c`
- `0x180063c84`
- `0x180124454`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180062995`
- `KERNEL32!RemoveDirectoryW` at `0x180062995`
- `KERNEL32!FindNextFileW` at `0x180062960`
- `KERNEL32!FindNextFileW` at `0x180062960`
- `KERNEL32!DeleteFileW` at `0x1800628eb`
- `KERNEL32!DeleteFileW` at `0x1800628eb`
- `KERNEL32!FindFirstFileExW` at `0x180062821`
- `KERNEL32!FindFirstFileExW` at `0x180062821`
- `KERNEL32!GetLastError` at `0x1800628f5`
- `KERNEL32!GetLastError` at `0x180062970`
- `KERNEL32!GetLastError` at `0x18006299f`
- `KERNEL32!GetLastError` at `0x1800628f5`
- `KERNEL32!GetLastError` at `0x180062970`
- `KERNEL32!GetLastError` at `0x18006299f`

## string_xrefs

- `0x18006273b`: `CEcsPath::DeleteDirectoryRecursive`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall CEcsPath::DeleteDirectoryRecursive(const unsigned __int16 *a1, const unsigned __int16 *a2, char a3)
{
  _BYTE *v6; // rax
  char v7; // di
  char v8; // al
  int v9; // ecx
  char v10; // r15
  const unsigned __int16 *v11; // r13
  __int64 v12; // rax
  const WCHAR *v13; // rax
  bool i; // al
  const unsigned __int16 *v15; // rcx
  char v16; // al
  int v17; // eax
  __int64 v18; // r10
  char v19; // r8
  DWORD LastError; // eax
  DWORD v21; // eax
  DWORD v22; // esi
  char v23; // cl
  char v25; // [rsp+50h] [rbp-318h]
  HANDLE hFindFile; // [rsp+58h] [rbp-310h] BYREF
  HANDLE FirstFile; // [rsp+60h] [rbp-308h] BYREF
  int v28; // [rsp+68h] [rbp-300h] BYREF
  int v29; // [rsp+6Ch] [rbp-2FCh]
  char v30; // [rsp+70h] [rbp-2F8h]
  const char *v31; // [rsp+78h] [rbp-2F0h]
  __int64 v32; // [rsp+80h] [rbp-2E8h]
  int v33; // [rsp+88h] [rbp-2E0h] BYREF
  const ATL::CAtlException *v34; // [rsp+90h] [rbp-2D8h] BYREF
  _BYTE v35[32]; // [rsp+98h] [rbp-2D0h] BYREF
  _BYTE v36[40]; // [rsp+B8h] [rbp-2B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-288h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_5d95a7213829360425c4708bf03e9463_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 2) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    v8 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v8 = 0;
  v7 = 1;
LABEL_9:
  v28 = 0;
  v29 = 148;
  v30 = v8;
  v31 = "CEcsPath::DeleteDirectoryRecursive";
  v32 = 0;
  v25 = 1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 || !*a2 )
    goto LABEL_15;
  v9 = *a2 - 42;
  if ( *a2 == 42 )
    v9 = a2[1];
  if ( !v9 || (v10 = 1, !wcscmp_0(a2, L"*.*")) )
LABEL_15:
    v10 = 0;
  hFindFile = 0;
  std::wstring::wstring(v36);
  try
  {
    v11 = L"*";
    if ( v10 )
      v11 = a2;
    v12 = CEcsPath::ConcatenatePaths(v35, a1, v11, 0);
    std::wstring::operator=(v36, v12);
    std::wstring::~wstring(v35);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    FirstFile = FindFirstFileExW(v13, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
    EcsUniqueHandle<void *,FindFileDeleter,0>::reset(&hFindFile, &FirstFile);
    for ( i = (char *)hFindFile + 1 != 0; i; i = FindNextFileW(hFindFile, &FindFileData) )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0
        || FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        CEcsPath::ConcatenatePaths(v35, a1, FindFileData.cFileName, 0);
        v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( !CEcsPath::DeleteDirectoryRecursive(v15, v11, v10 != 1) || (v16 = 1, !v25) )
            v16 = 0;
          v25 = v16;
        }
        else if ( !DeleteFileW(v15) )
        {
          GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
          {
            v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
            WPP_SF_Sd(
              *(_QWORD *)(v18 + 56),
              11,
              (unsigned int)WPP_5d95a7213829360425c4708bf03e9463_Traceguids,
              v17,
              v19);
          }
          v25 = 0;
        }
        std::wstring::~wstring(v35);
      }
    }
    LastError = GetLastError();
    if ( ((LastError - 2) & 0xFFFFFFEE) != 0 || LastError == 19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          12,
          (unsigned int)WPP_5d95a7213829360425c4708bf03e9463_Traceguids,
          (_DWORD)a1,
          LastError);
      }
      if ( !a3 )
      {
        v25 = 0;
        goto LABEL_62;
      }
    }
    else if ( !a3 )
    {
      goto LABEL_62;
    }
    if ( !RemoveDirectoryW(a1) )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          13,
          (unsigned int)WPP_5d95a7213829360425c4708bf03e9463_Traceguids,
          (_DWORD)a1,
          v21);
      }
      v23 = v25;
      if ( v22 - 2 > 1 )
        v23 = 0;
      v25 = v23;
    }
  }
  catch ( long v33 )
  {
    v28 = v33;
    v7 = 1;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v29) = 242;
    v28 = -2147024882;
    v7 = 1;
  }
  catch ( std::exception )
  {
    HIWORD(v29) = 242;
    v28 = -2147418113;
    v7 = 1;
  }
  catch ( const ATL::CAtlException *v34 )
  {
    HIWORD(v29) = 242;
    v28 = *(_DWORD *)v34;
    v7 = 1;
  }
LABEL_62:
  if ( !v25 || v28 < 0 )
    v7 = 0;
  std::wstring::~wstring(v36);
  FirstFile = 0;
  EcsUniqueHandle<void *,FindFileDeleter,0>::reset(&hFindFile, &FirstFile);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v28);
  return v7;
}

```

## disassembly

```asm
0x18006269c  mov     [rsp+arg_10], rbx
0x1800626a1  mov     [rsp+arg_18], rsi
0x1800626a6  push    rdi
0x1800626a7  push    r12
0x1800626a9  push    r13
0x1800626ab  push    r14
0x1800626ad  push    r15
0x1800626af  sub     rsp, 340h
0x1800626b6  mov     rax, cs:__security_cookie
0x1800626bd  xor     rax, rsp
0x1800626c0  mov     [rsp+368h+var_38], rax
0x1800626c8  mov     r12b, r8b
0x1800626cb  mov     rsi, rdx
0x1800626ce  mov     r14, rcx
0x1800626d1  lea     rcx, WPP_GLOBAL_Control
0x1800626d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800626df  cmp     rax, rcx
0x1800626e2  jz      short loc_18006270C
0x1800626e4  test    byte ptr [rax+44h], 2
0x1800626e8  jz      short loc_180062724
0x1800626ea  cmp     byte ptr [rax+41h], 6
0x1800626ee  jb      short loc_18006270C
0x1800626f0  mov     edx, 0Ah
0x1800626f5  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x1800626fc  mov     rcx, [rax+38h]
0x180062700  call    WPP_SF_
0x180062705  mov     rax, cs:WPP_GLOBAL_Control
0x18006270c  test    byte ptr [rax+44h], 2
0x180062710  jz      short loc_180062724
0x180062712  cmp     byte ptr [rax+41h], 6
0x180062716  jb      short loc_180062724
0x180062718  mov     edi, 1
0x18006271d  mov     al, dil
0x180062720  xor     ebx, ebx
0x180062722  jmp     short loc_18006272B
0x180062724  xor     ebx, ebx
0x180062726  mov     al, bl
0x180062728  lea     edi, [rbx+1]
0x18006272b  mov     [rsp+368h+var_300], ebx
0x18006272f  mov     [rsp+368h+var_2FC], 94h
0x180062737  mov     [rsp+368h+var_2F8], al
0x18006273b  lea     rax, aCecspathDelete; "CEcsPath::DeleteDirectoryRecursive"
0x180062742  mov     [rsp+368h+var_2F0], rax
0x180062747  mov     [rsp+368h+var_2E8], rbx
0x18006274f  mov     [rsp+368h+var_318], dil
0x180062754  xor     edx, edx; Val
0x180062756  mov     r8d, 250h; Size
0x18006275c  lea     rcx, [rsp+368h+FindFileData]; void *
0x180062764  call    memset_0
0x180062769  test    rsi, rsi
0x18006276c  jz      short loc_18006279E
0x18006276e  cmp     [rsi], bx
0x180062771  jz      short loc_18006279E
0x180062773  movzx   ecx, word ptr [rsi]
0x180062776  sub     ecx, 2Ah ; '*'
0x180062779  jnz     short loc_180062784
0x18006277b  movzx   ecx, word ptr [rsi+2]
0x18006277f  movzx   eax, bx
0x180062782  sub     ecx, eax
0x180062784  test    ecx, ecx
0x180062786  jz      short loc_18006279E
0x180062788  lea     rdx, asc_180155120; "*.*"
0x18006278f  mov     rcx, rsi; String1
0x180062792  call    wcscmp_0
0x180062797  test    eax, eax
0x180062799  mov     r15b, dil
0x18006279c  jnz     short loc_1800627A1
0x18006279e  mov     r15b, bl
0x1800627a1  mov     [rsp+368h+hFindFile], rbx
0x1800627a6  lea     rcx, [rsp+368h+var_2B0]
0x1800627ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800627b3  nop
0x1800627b4  lea     r13, asc_180155128; "*"
0x1800627bb  test    r15b, r15b
0x1800627be  cmovnz  r13, rsi
0x1800627c2  xor     r9d, r9d
0x1800627c5  mov     r8, r13
0x1800627c8  mov     rdx, r14
0x1800627cb  lea     rcx, [rsp+368h+var_2D0]
0x1800627d3  call    ?ConcatenatePaths@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00000000@Z; CEcsPath::ConcatenatePaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800627d8  nop
0x1800627d9  mov     rdx, rax
0x1800627dc  lea     rcx, [rsp+368h+var_2B0]
0x1800627e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800627e9  nop
0x1800627ea  lea     rcx, [rsp+368h+var_2D0]
0x1800627f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800627f7  lea     rcx, [rsp+368h+var_2B0]
0x1800627ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062804  mov     rcx, rax; lpFileName
0x180062807  mov     [rsp+368h+dwAdditionalFlags], 2; dwAdditionalFlags
0x18006280f  mov     [rsp+368h+lpSearchFilter], rbx; lpSearchFilter
0x180062814  xor     r9d, r9d; fSearchOp
0x180062817  lea     r8, [rsp+368h+FindFileData]; lpFindFileData
0x18006281f  mov     edx, edi; fInfoLevelId
0x180062821  call    cs:__imp_FindFirstFileExW
0x180062827  mov     [rsp+368h+var_308], rax
0x18006282c  lea     rdx, [rsp+368h+var_308]
0x180062831  lea     rcx, [rsp+368h+hFindFile]
0x180062836  call    ?reset@?$EcsUniqueHandle@PEAXUFindFileDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,FindFileDeleter,0>::reset(void * const &)
0x18006283b  cmp     [rsp+368h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x180062841  setnz   al
0x180062844  lea     rsi, WPP_GLOBAL_Control
0x18006284b  mov     ecx, 2Eh ; '.'
0x180062850  test    al, al
0x180062852  jz      loc_180062970
0x180062858  test    [rsp+368h+FindFileData], 10h
0x180062860  jz      short loc_180062892
0x180062862  cmp     cx, [rsp+368h+var_25C]
0x18006286a  jnz     short loc_180062892
0x18006286c  cmp     bx, [rsp+368h+var_25A]
0x180062874  jz      loc_180062953
0x18006287a  cmp     cx, [rsp+368h+var_25A]
0x180062882  jnz     short loc_180062892
0x180062884  cmp     bx, [rsp+368h+var_258]
0x18006288c  jz      loc_180062953
0x180062892  xor     r9d, r9d
0x180062895  lea     r8, [rsp+368h+var_25C]
0x18006289d  mov     rdx, r14
0x1800628a0  lea     rcx, [rsp+368h+var_2D0]
0x1800628a8  call    ?ConcatenatePaths@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00000000@Z; CEcsPath::ConcatenatePaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800628ad  nop
0x1800628ae  lea     rcx, [rsp+368h+var_2D0]
0x1800628b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800628bb  mov     rcx, rax; unsigned __int16 *
0x1800628be  test    [rsp+368h+FindFileData], 10h
0x1800628c6  jz      short loc_1800628EB
0x1800628c8  mov     r8b, r15b
0x1800628cb  xor     r8b, dil; bool
0x1800628ce  mov     rdx, r13; unsigned __int16 *
0x1800628d1  call    ?DeleteDirectoryRecursive@CEcsPath@@SA_NPEBG0_N@Z; CEcsPath::DeleteDirectoryRecursive(ushort const *,ushort const *,bool)
0x1800628d6  test    al, al
0x1800628d8  jz      short loc_1800628E3
0x1800628da  cmp     [rsp+368h+var_318], bl
0x1800628de  mov     al, dil
0x1800628e1  jnz     short loc_1800628E5
0x1800628e3  mov     al, bl
0x1800628e5  mov     [rsp+368h+var_318], al
0x1800628e9  jmp     short loc_180062946
0x1800628eb  call    cs:__imp_DeleteFileW
0x1800628f1  test    eax, eax
0x1800628f3  jnz     short loc_180062946
0x1800628f5  call    cs:__imp_GetLastError
0x1800628fb  mov     r8d, eax
0x1800628fe  mov     r10, cs:WPP_GLOBAL_Control
0x180062905  cmp     r10, rsi
0x180062908  jz      short loc_180062942
0x18006290a  test    byte ptr [r10+44h], 2
0x18006290f  jz      short loc_180062942
0x180062911  cmp     byte ptr [r10+41h], 3
0x180062916  jb      short loc_180062942
0x180062918  lea     rcx, [rsp+368h+var_2D0]
0x180062920  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062925  mov     r9, rax
0x180062928  mov     edx, 0Bh
0x18006292d  mov     dword ptr [rsp+368h+lpSearchFilter], r8d
0x180062932  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x180062939  mov     rcx, [r10+38h]
0x18006293d  call    WPP_SF_Sd
0x180062942  mov     [rsp+368h+var_318], bl
0x180062946  lea     rcx, [rsp+368h+var_2D0]
0x18006294e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180062953  lea     rdx, [rsp+368h+FindFileData]; lpFindFileData
0x18006295b  mov     rcx, [rsp+368h+hFindFile]; hFindFile
0x180062960  call    cs:__imp_FindNextFileW
0x180062966  test    eax, eax
0x180062968  setnz   al
0x18006296b  jmp     loc_18006284B
0x180062970  call    cs:__imp_GetLastError
0x180062976  lea     ecx, [rax-2]
0x180062979  test    ecx, 0FFFFFFEEh
0x18006297f  jnz     short loc_1800629EE
0x180062981  cmp     eax, 13h
0x180062984  jz      short loc_1800629EE
0x180062986  test    r12b, r12b
0x180062989  jz      short loc_1800629EC
0x18006298b  lea     r15, WPP_GLOBAL_Control
0x180062992  mov     rcx, r14; lpPathName
0x180062995  call    cs:__imp_RemoveDirectoryW
0x18006299b  test    eax, eax
0x18006299d  jnz     short loc_1800629EC
0x18006299f  call    cs:__imp_GetLastError
0x1800629a5  mov     esi, eax
0x1800629a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629ae  cmp     rcx, r15
0x1800629b1  jz      short loc_1800629DB
0x1800629b3  test    byte ptr [rcx+44h], 2
0x1800629b7  jz      short loc_1800629DB
0x1800629b9  cmp     byte ptr [rcx+41h], 3
0x1800629bd  jb      short loc_1800629DB
0x1800629bf  mov     edx, 0Dh
0x1800629c4  mov     dword ptr [rsp+368h+lpSearchFilter], eax
0x1800629c8  mov     r9, r14
0x1800629cb  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x1800629d2  mov     rcx, [rcx+38h]
0x1800629d6  call    WPP_SF_Sd
0x1800629db  lea     eax, [rsi-2]
0x1800629de  movzx   ecx, [rsp+368h+var_318]
0x1800629e3  cmp     eax, edi
0x1800629e5  cmova   ecx, ebx
0x1800629e8  mov     [rsp+368h+var_318], cl
0x1800629ec  jmp     short loc_180062A43
0x1800629ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629f5  lea     r15, WPP_GLOBAL_Control
0x1800629fc  cmp     rcx, r15
0x1800629ff  jz      short loc_180062A29
0x180062a01  test    byte ptr [rcx+44h], 2
0x180062a05  jz      short loc_180062A29
0x180062a07  cmp     byte ptr [rcx+41h], 3
0x180062a0b  jb      short loc_180062A29
0x180062a0d  mov     edx, 0Ch
0x180062a12  mov     dword ptr [rsp+368h+lpSearchFilter], eax
0x180062a16  mov     r9, r14
0x180062a19  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x180062a20  mov     rcx, [rcx+38h]
0x180062a24  call    WPP_SF_Sd
0x180062a29  test    r12b, r12b
0x180062a2c  jnz     loc_180062992
0x180062a32  mov     [rsp+368h+var_318], bl
0x180062a36  jmp     short loc_1800629EC
0x180062a38  jmp     short loc_180062A3E
0x180062a3a  jmp     short loc_180062A3E
0x180062a3c  jmp     short $+2
0x180062a3e  xor     ebx, ebx
0x180062a40  lea     edi, [rbx+1]
0x180062a43  cmp     [rsp+368h+var_318], bl
0x180062a47  jz      short loc_180062A4F
0x180062a49  cmp     [rsp+368h+var_300], ebx
0x180062a4d  jge     short loc_180062A52
0x180062a4f  mov     dil, bl
0x180062a52  lea     rcx, [rsp+368h+var_2B0]
0x180062a5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180062a5f  nop
0x180062a60  mov     [rsp+368h+var_308], rbx
0x180062a65  lea     rdx, [rsp+368h+var_308]
0x180062a6a  lea     rcx, [rsp+368h+hFindFile]
0x180062a6f  call    ?reset@?$EcsUniqueHandle@PEAXUFindFileDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,FindFileDeleter,0>::reset(void * const &)
0x180062a74  nop
0x180062a75  lea     rcx, [rsp+368h+var_300]; this
0x180062a7a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180062a7f  mov     al, dil
0x180062a82  mov     rcx, [rsp+368h+var_38]
0x180062a8a  xor     rcx, rsp; StackCookie
0x180062a8d  call    __security_check_cookie
0x180062a92  lea     r11, [rsp+368h+var_28]
0x180062a9a  mov     rbx, [r11+40h]
0x180062a9e  mov     rsi, [r11+48h]
0x180062aa2  mov     rsp, r11
0x180062aa5  pop     r15
0x180062aa7  pop     r14
0x180062aa9  pop     r13
0x180062aab  pop     r12
0x180062aad  pop     rdi
0x180062aae  retn
```
