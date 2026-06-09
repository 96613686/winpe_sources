# CSrmFileSafe::EnumFilesOnPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180078344`
- end: `0x180078a7f`
- name: `?EnumFilesOnPath@CSrmFileSafe@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z`
- size: `1851`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000fb7c`

## callees

- `0x180001350`
- `0x18000266c`
- `0x18000e9ec`
- `0x18000ead4`
- `0x18000ebd4`
- `0x18000ed14`
- `0x18000ee10`
- `0x180010b24`
- `0x180010bc4`
- `0x18001d934`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180074048`
- `0x180075034`
- `0x180078344`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007859c`
- `KERNEL32!GetLastError` at `0x1800785a6`
- `KERNEL32!GetLastError` at `0x180078922`
- `KERNEL32!GetLastError` at `0x18007859c`
- `KERNEL32!GetLastError` at `0x1800785a6`
- `KERNEL32!GetLastError` at `0x180078922`
- `KERNEL32!FindClose` at `0x180078970`
- `KERNEL32!FindClose` at `0x180078970`
- `KERNEL32!FindNextFileW` at `0x180078918`
- `KERNEL32!FindNextFileW` at `0x180078918`
- `KERNEL32!FindFirstFileW` at `0x180078589`
- `KERNEL32!FindFirstFileW` at `0x180078589`

## string_xrefs

- `0x18007843c`: `Enumerating files on path '%s'`
- `0x18007838f`: `CSrmFileSafe::EnumFilesOnPath`
- `0x1800785c1`: `CSrmFileSafe::EnumFilesOnPath`
- `0x1800786f7`: `CSrmFileSafe::EnumFilesOnPath`
- `0x1800787c2`: `CSrmFileSafe::EnumFilesOnPath`
- `0x180078854`: `CSrmFileSafe::EnumFilesOnPath`
- `0x18007898b`: `CSrmFileSafe::EnumFilesOnPath`
- `0x1800789e0`: `CSrmFileSafe::EnumFilesOnPath`
- `0x180078a3a`: `CSrmFileSafe::EnumFilesOnPath`
- `0x180078741`: `- File name with extension: '%s'`
- `0x18007889e`: `- Ignoring directory '%s' in enumeration`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CSrmFileSafe::EnumFilesOnPath(_QWORD *a1, __int64 *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r8
  void **v10; // rcx
  void *v11; // rax
  int v12; // esi
  const WCHAR *v13; // rcx
  HANDLE FirstFileW; // rdi
  __int64 v15; // r8
  void **v16; // rbx
  void **v17; // rbx
  void **v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  const unsigned __int16 *v25; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v26; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  int v30; // [rsp+68h] [rbp-98h]
  _BYTE v31[96]; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+D0h] [rbp-30h]
  void **v33; // [rsp+D8h] [rbp-28h]
  HANDLE v34; // [rsp+E0h] [rbp-20h]
  _QWORD v35[3]; // [rsp+E8h] [rbp-18h] BYREF
  int v36; // [rsp+100h] [rbp+0h]
  int v37; // [rsp+104h] [rbp+4h]
  int v38; // [rsp+108h] [rbp+8h]
  char v39[96]; // [rsp+110h] [rbp+10h] BYREF
  int v40; // [rsp+170h] [rbp+70h]
  void *Block[2]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v42; // [rsp+188h] [rbp+88h]
  unsigned __int64 v43; // [rsp+190h] [rbp+90h]
  void *v44[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v45; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v46; // [rsp+1B8h] [rbp+B8h]
  LPCWSTR lpFileName[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v48; // [rsp+1D8h] [rbp+D8h]
  unsigned __int64 v49; // [rsp+1E0h] [rbp+E0h]
  _QWORD v50[22]; // [rsp+1F0h] [rbp+F0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+2A0h] [rbp+1A0h] BYREF

  v35[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v35[1] = L"CSrmFileSafe::EnumFilesOnPath";
  v35[2] = L"FILESF_C";
  v36 = 927;
  v37 = 17;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(v39, 0, sizeof(v39));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v50, (const struct CSrmDebugInfo *)v35, 0);
  if ( a1[3] < 8u )
    v4 = a1;
  else
    v4 = (_QWORD *)*a1;
  v25 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v26 = L"CSrmFileSafe::EnumFilesOnPath";
  v27 = L"FILESF_C";
  v28 = 929;
  v29 = 17;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::Trace(v50, &v25, L"Enumerating files on path '%s'", v4);
  v6 = a2[1];
  v7 = *a2;
  if ( *a2 != v6 )
  {
    v8 = *a2;
    do
    {
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>(v5, v8);
      v8 += 40;
    }
    while ( v8 != v6 );
    a2[1] = v7;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v43 = 7;
  v42 = 0;
  LOWORD(Block[0]) = 0;
  if ( a1[2] != 5 )
  {
    LOBYTE(v9) = 1;
    if ( (unsigned __int8)std::wstring::_Grow(Block, a1[2] + 2LL, v9) )
    {
      v10 = Block;
      if ( v43 >= 8 )
        v10 = (void **)Block[0];
      v42 = 0;
      *(_WORD *)v10 = 0;
    }
  }
  std::wstring::append(Block, a1, 0, -1);
  std::wstring::append(Block, L"\\*");
  v11 = (void *)std::wstring::append(Block, L".xml");
  v49 = 7;
  v48 = 0;
  LOWORD(lpFileName[0]) = 0;
  std::wstring::assign(lpFileName, v11);
  v12 = 2;
  if ( v43 >= 8 )
    operator delete(Block[0]);
  v43 = 7;
  v42 = 0;
  LOWORD(Block[0]) = 0;
  v13 = (const WCHAR *)lpFileName;
  if ( v49 >= 8 )
    v13 = lpFileName[0];
  FirstFileW = FindFirstFileW(v13, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() != 2 && GetLastError() != 3 )
    {
      CSrmDebugInfo::CSrmDebugInfo(
        (__int64)&v25,
        (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
        (__int64)L"FILESF_C",
        (__int64)L"CSrmFileSafe::EnumFilesOnPath",
        945,
        17);
      v23 = std::wstring::c_str(lpFileName);
      CSrmFunctionTracer::TranslateWin32Error(v50, v24, L"FindFirstFile(%s)", v23);
    }
    v25 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v26 = L"CSrmFileSafe::EnumFilesOnPath";
    v27 = L"FILESF_C";
    v28 = 941;
    v29 = 17;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CSrmFunctionTracer::Trace(v50, &v25, L"Warning: no files found");
    goto LABEL_21;
  }
  v33 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int FindClose(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v34 = FirstFileW;
  while ( 1 )
  {
    v43 = 7;
    v42 = 0;
    LOWORD(Block[0]) = 0;
    v15 = -1;
    do
      ++v15;
    while ( FindFileData.cFileName[v15] );
    std::wstring::assign(Block, FindFileData.cFileName);
    v16 = Block;
    if ( v43 >= 8 )
      v16 = (void **)Block[0];
    v25 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v26 = L"CSrmFileSafe::EnumFilesOnPath";
    v27 = L"FILESF_C";
    v28 = 957;
    v29 = 17;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CSrmFunctionTracer::Trace(v50, &v25, L"- File name with extension: '%s'", v16);
    if ( v42 <= 4 )
    {
      CSrmDebugInfo::CSrmDebugInfo(
        (__int64)&v25,
        (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
        (__int64)L"FILESF_C",
        (__int64)L"CSrmFileSafe::EnumFilesOnPath",
        963,
        17);
      v21 = std::wstring::c_str(Block);
      CSrmFunctionTracer::Throw(v50, v22, 2147767062LL, L"ERROR: Invalid file name! '%s'", v21);
    }
    v46 = 7;
    v45 = 0;
    LOWORD(v44[0]) = 0;
    std::wstring::assign(v44);
    v12 |= 4u;
    v17 = v44;
    if ( v46 >= 8 )
      v17 = (void **)v44[0];
    v25 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v26 = L"CSrmFileSafe::EnumFilesOnPath";
    v27 = L"FILESF_C";
    v28 = 970;
    v29 = 17;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CSrmFunctionTracer::Trace(v50, &v25, L"- File name: '%s'", v17);
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    v18 = v44;
    if ( v46 >= 8 )
      v18 = (void **)v44[0];
    v25 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v26 = L"CSrmFileSafe::EnumFilesOnPath";
    v27 = L"FILESF_C";
    v28 = 976;
    v29 = 17;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CSrmFunctionTracer::Trace(v50, &v25, L"- Ignoring directory '%s' in enumeration", v18);
LABEL_36:
    if ( v46 >= 8 )
      operator delete(v44[0]);
    v46 = 7;
    v45 = 0;
    LOWORD(v44[0]) = 0;
    if ( v43 >= 8 )
      operator delete(Block[0]);
  }
  std::vector<std::wstring>::push_back(a2, v44);
  if ( FindNextFileW(FirstFileW, &FindFileData) )
    goto LABEL_36;
  if ( GetLastError() != 18 )
  {
    CSrmDebugInfo::CSrmDebugInfo(
      (__int64)&v25,
      (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      (__int64)L"FILESF_C",
      (__int64)L"CSrmFileSafe::EnumFilesOnPath",
      989,
      17);
    v19 = std::wstring::c_str(lpFileName);
    CSrmFunctionTracer::TranslateWin32Error(v50, v20, L"FindNextFile(%s)", v19);
  }
  if ( v46 >= 8 )
    operator delete(v44[0]);
  v46 = 7;
  v45 = 0;
  LOWORD(v44[0]) = 0;
  if ( v43 >= 8 )
    operator delete(Block[0]);
  FindClose(FirstFileW);
LABEL_21:
  if ( v49 >= 8 )
    operator delete((void *)lpFileName[0]);
  v49 = 7;
  v48 = 0;
  LOWORD(lpFileName[0]) = 0;
  v50[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v50);
}

```

## disassembly

```asm
0x180078344  mov     [rsp-8+arg_10], rbx
0x180078349  mov     [rsp-8+arg_18], rsi
0x18007834e  push    rbp
0x18007834f  push    rdi
0x180078350  push    r12
0x180078352  push    r14
0x180078354  push    r15
0x180078356  lea     rbp, [rsp-400h]
0x18007835e  sub     rsp, 500h
0x180078365  mov     rax, cs:__security_cookie
0x18007836c  xor     rax, rsp
0x18007836f  mov     [rbp+420h+var_30], rax
0x180078376  mov     r15, rdx
0x180078379  mov     rsi, rcx
0x18007837c  xor     r12d, r12d
0x18007837f  mov     [rsp+520h+var_4E0], r12d
0x180078384  lea     rdi, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007838b  mov     [rbp+420h+var_438], rdi
0x18007838f  lea     r14, aCsrmfilesafeEn; "CSrmFileSafe::EnumFilesOnPath"
0x180078396  mov     [rbp+420h+var_430], r14
0x18007839a  lea     rax, aFilesfC; "FILESF_C"
0x1800783a1  mov     [rbp+420h+var_428], rax
0x1800783a5  mov     [rbp+420h+var_420], 39Fh
0x1800783ac  mov     [rbp+420h+var_41C], 11h
0x1800783b3  mov     [rbp+420h+var_418], 0FFh
0x1800783ba  mov     [rbp+420h+var_3B0], 1000000h
0x1800783c1  xor     edx, edx; Val
0x1800783c3  lea     r8d, [r12+60h]; Size
0x1800783c8  lea     rcx, [rbp+420h+var_410]; void *
0x1800783cc  call    memset_0
0x1800783d1  xor     r8d, r8d
0x1800783d4  lea     rdx, [rbp+420h+var_438]
0x1800783d8  lea     rcx, [rbp+420h+var_330]
0x1800783df  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800783e4  nop
0x1800783e5  cmp     qword ptr [rsi+18h], 8
0x1800783ea  jb      short loc_1800783F1
0x1800783ec  mov     rbx, [rsi]
0x1800783ef  jmp     short loc_1800783F4
0x1800783f1  mov     rbx, rsi
0x1800783f4  mov     [rsp+520h+var_4D8], rdi
0x1800783f9  mov     [rsp+520h+var_4D0], r14
0x1800783fe  lea     rax, aFilesfC; "FILESF_C"
0x180078405  mov     [rsp+520h+var_4C8], rax
0x18007840a  mov     [rsp+520h+var_4C0], 3A1h
0x180078412  mov     [rsp+520h+var_4BC], 11h
0x18007841a  mov     [rsp+520h+var_4B8], 0FFh
0x180078422  mov     [rbp+420h+var_450], 1000000h
0x180078429  xor     edx, edx; Val
0x18007842b  lea     r8d, [rdx+60h]; Size
0x18007842f  lea     rcx, [rsp+520h+var_4B0]; void *
0x180078434  call    memset_0
0x180078439  mov     r9, rbx
0x18007843c  lea     r8, aEnumeratingFil; "Enumerating files on path '%s'"
0x180078443  lea     rdx, [rsp+520h+var_4D8]
0x180078448  lea     rcx, [rbp+420h+var_330]
0x18007844f  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078454  mov     r14, [r15+8]
0x180078458  mov     rbx, [r15]
0x18007845b  cmp     rbx, r14
0x18007845e  jz      short loc_180078478
0x180078460  mov     rdi, rbx
0x180078463  mov     rdx, rdi
0x180078466  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x18007846b  add     rdi, 28h ; '('
0x18007846f  cmp     rdi, r14
0x180078472  jnz     short loc_180078463
0x180078474  mov     [r15+8], rbx
0x180078478  xor     edx, edx; Val
0x18007847a  mov     r8d, 250h; Size
0x180078480  lea     rcx, [rbp+420h+FindFileData]; void *
0x180078487  call    memset_0
0x18007848c  nop
0x18007848d  mov     r14d, 7
0x180078493  mov     [rbp+420h+var_390], r14
0x18007849a  mov     [rbp+420h+var_398], r12
0x1800784a1  mov     word ptr [rbp+420h+Block], r12w
0x1800784a6  mov     [rsp+520h+var_4E0], 1
0x1800784ae  mov     rdx, [rsi+10h]
0x1800784b2  add     rdx, 2
0x1800784b6  cmp     rdx, r14
0x1800784b9  jz      short loc_1800784E7
0x1800784bb  mov     r8b, 1
0x1800784be  lea     rcx, [rbp+420h+Block]
0x1800784c2  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800784c7  test    al, al
0x1800784c9  jz      short loc_1800784E7
0x1800784cb  lea     rcx, [rbp+420h+Block]
0x1800784cf  cmp     [rbp+420h+var_390], 8
0x1800784d7  cmovnb  rcx, [rbp+420h+Block]
0x1800784dc  mov     [rbp+420h+var_398], r12
0x1800784e3  mov     [rcx], r12w
0x1800784e7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800784eb  xor     r8d, r8d
0x1800784ee  mov     rdx, rsi
0x1800784f1  lea     rcx, [rbp+420h+Block]
0x1800784f5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800784fa  lea     rdx, asc_1800EEA48; "\\*"
0x180078501  lea     rcx, [rbp+420h+Block]; Src
0x180078505  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007850a  lea     rdx, aXml; ".xml"
0x180078511  lea     rcx, [rbp+420h+Block]; Src
0x180078515  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007851a  mov     [rbp+420h+var_340], r14
0x180078521  mov     [rbp+420h+var_348], r12
0x180078528  mov     word ptr [rbp+420h+lpFileName], r12w
0x180078530  mov     rdx, rax; Src
0x180078533  lea     rcx, [rbp+420h+lpFileName]; void *
0x18007853a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18007853f  nop
0x180078540  mov     esi, 2
0x180078545  cmp     [rbp+420h+var_390], 8
0x18007854d  jb      short loc_180078558
0x18007854f  mov     rcx, [rbp+420h+Block]; Block
0x180078553  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078558  mov     [rbp+420h+var_390], r14
0x18007855f  mov     [rbp+420h+var_398], r12
0x180078566  mov     word ptr [rbp+420h+Block], r12w
0x18007856b  lea     rcx, [rbp+420h+lpFileName]
0x180078572  cmp     [rbp+420h+var_340], 8
0x18007857a  cmovnb  rcx, [rbp+420h+lpFileName]; lpFileName
0x180078582  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x180078589  call    cs:__imp_FindFirstFileW
0x18007858f  mov     rdi, rax
0x180078592  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180078596  jnz     loc_180078692
0x18007859c  call    cs:__imp_GetLastError
0x1800785a2  cmp     eax, esi
0x1800785a4  jz      short loc_1800785B5
0x1800785a6  call    cs:__imp_GetLastError
0x1800785ac  cmp     eax, 3
0x1800785af  jnz     loc_180078A2A
0x1800785b5  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x1800785bc  mov     [rsp+520h+var_4D8], rax
0x1800785c1  lea     rax, aCsrmfilesafeEn; "CSrmFileSafe::EnumFilesOnPath"
0x1800785c8  mov     [rsp+520h+var_4D0], rax
0x1800785cd  lea     rax, aFilesfC; "FILESF_C"
0x1800785d4  mov     [rsp+520h+var_4C8], rax
0x1800785d9  mov     [rsp+520h+var_4C0], 3ADh
0x1800785e1  mov     [rsp+520h+var_4BC], 11h
0x1800785e9  mov     [rsp+520h+var_4B8], 0FFh
0x1800785f1  mov     [rbp+420h+var_450], 1000000h
0x1800785f8  xor     edx, edx; Val
0x1800785fa  lea     r8d, [rdx+60h]; Size
0x1800785fe  lea     rcx, [rsp+520h+var_4B0]; void *
0x180078603  call    memset_0
0x180078608  lea     r8, aWarningNoFiles; "Warning: no files found"
0x18007860f  lea     rdx, [rsp+520h+var_4D8]
0x180078614  lea     rcx, [rbp+420h+var_330]
0x18007861b  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078620  nop
0x180078621  cmp     [rbp+420h+var_340], 8
0x180078629  jb      short loc_180078637
0x18007862b  mov     rcx, [rbp+420h+lpFileName]; Block
0x180078632  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078637  mov     [rbp+420h+var_340], r14
0x18007863e  mov     [rbp+420h+var_348], r12
0x180078645  mov     word ptr [rbp+420h+lpFileName], r12w
0x18007864d  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180078654  mov     [rbp+420h+var_330], rax
0x18007865b  lea     rcx, [rbp+420h+var_330]; this
0x180078662  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180078667  mov     rcx, [rbp+420h+var_30]
0x18007866e  xor     rcx, rsp; StackCookie
0x180078671  call    __security_check_cookie
0x180078676  lea     r11, [rsp+520h+var_20]
0x18007867e  mov     rbx, [r11+40h]
0x180078682  mov     rsi, [r11+48h]
0x180078686  mov     rsp, r11
0x180078689  pop     r15
0x18007868b  pop     r14
0x18007868d  pop     r12
0x18007868f  pop     rdi
0x180078690  pop     rbp
0x180078691  retn
0x180078692  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?FindClose@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&FindClose(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180078699  mov     [rbp+420h+var_448], rax
0x18007869d  mov     [rbp+420h+var_440], rdi
0x1800786a1  mov     [rbp+420h+var_390], r14
0x1800786a8  mov     [rbp+420h+var_398], r12
0x1800786af  mov     word ptr [rbp+420h+Block], r12w
0x1800786b4  lea     rax, [rbp+420h+FindFileData.cFileName]
0x1800786bb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800786bf  inc     r8
0x1800786c2  cmp     [rax+r8*2], r12w
0x1800786c7  jnz     short loc_1800786BF
0x1800786c9  lea     rdx, [rbp+420h+FindFileData.cFileName]; Src
0x1800786d0  lea     rcx, [rbp+420h+Block]; void *
0x1800786d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800786d9  nop
0x1800786da  lea     rbx, [rbp+420h+Block]
0x1800786de  cmp     [rbp+420h+var_390], 8
0x1800786e6  cmovnb  rbx, [rbp+420h+Block]
0x1800786eb  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x1800786f2  mov     [rsp+520h+var_4D8], rax
0x1800786f7  lea     rax, aCsrmfilesafeEn; "CSrmFileSafe::EnumFilesOnPath"
0x1800786fe  mov     [rsp+520h+var_4D0], rax
0x180078703  lea     rax, aFilesfC; "FILESF_C"
0x18007870a  mov     [rsp+520h+var_4C8], rax
0x18007870f  mov     [rsp+520h+var_4C0], 3BDh
0x180078717  mov     [rsp+520h+var_4BC], 11h
0x18007871f  mov     [rsp+520h+var_4B8], 0FFh
0x180078727  mov     [rbp+420h+var_450], 1000000h
0x18007872e  xor     edx, edx; Val
0x180078730  lea     r8d, [rdx+60h]; Size
0x180078734  lea     rcx, [rsp+520h+var_4B0]; void *
0x180078739  call    memset_0
0x18007873e  mov     r9, rbx
0x180078741  lea     r8, aFileNameWithEx; "- File name with extension: '%s'"
0x180078748  lea     rdx, [rsp+520h+var_4D8]
0x18007874d  lea     rcx, [rbp+420h+var_330]
0x180078754  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078759  cmp     [rbp+420h+var_398], 4
0x180078761  jbe     loc_1800789D0
0x180078767  mov     [rbp+420h+var_368], r14
0x18007876e  mov     [rbp+420h+var_370], r12
0x180078775  mov     word ptr [rbp+420h+var_380], r12w
0x18007877d  mov     eax, dword ptr [rbp+420h+var_398]
0x180078783  add     eax, 0FFFFFFFCh
0x180078786  movsxd  r9, eax
0x180078789  xor     r8d, r8d
0x18007878c  lea     rdx, [rbp+420h+Block]
0x180078790  lea     rcx, [rbp+420h+var_380]; void *
0x180078797  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18007879c  or      esi, 4
0x18007879f  lea     rbx, [rbp+420h+var_380]
0x1800787a6  cmp     [rbp+420h+var_368], 8
0x1800787ae  cmovnb  rbx, [rbp+420h+var_380]
0x1800787b6  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x1800787bd  mov     [rsp+520h+var_4D8], rax
0x1800787c2  lea     rax, aCsrmfilesafeEn; "CSrmFileSafe::EnumFilesOnPath"
0x1800787c9  mov     [rsp+520h+var_4D0], rax
0x1800787ce  lea     rax, aFilesfC; "FILESF_C"
0x1800787d5  mov     [rsp+520h+var_4C8], rax
0x1800787da  mov     [rsp+520h+var_4C0], 3CAh
0x1800787e2  mov     [rsp+520h+var_4BC], 11h
0x1800787ea  mov     [rsp+520h+var_4B8], 0FFh
0x1800787f2  mov     [rbp+420h+var_450], 1000000h
0x1800787f9  xor     edx, edx; Val
0x1800787fb  lea     r8d, [rdx+60h]; Size
0x1800787ff  lea     rcx, [rsp+520h+var_4B0]; void *
0x180078804  call    memset_0
0x180078809  mov     r9, rbx
0x18007880c  lea     r8, aFileNameS; "- File name: '%s'"
0x180078813  lea     rdx, [rsp+520h+var_4D8]
0x180078818  lea     rcx, [rbp+420h+var_330]
0x18007881f  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078824  test    byte ptr [rbp+420h+FindFileData.dwFileAttributes], 10h
0x18007882b  jz      loc_1800788FF
0x180078831  lea     rbx, [rbp+420h+var_380]
0x180078838  cmp     [rbp+420h+var_368], 8
0x180078840  cmovnb  rbx, [rbp+420h+var_380]
0x180078848  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007884f  mov     [rsp+520h+var_4D8], rax
0x180078854  lea     rax, aCsrmfilesafeEn; "CSrmFileSafe::EnumFilesOnPath"
0x18007885b  mov     [rsp+520h+var_4D0], rax
0x180078860  lea     rax, aFilesfC; "FILESF_C"
0x180078867  mov     [rsp+520h+var_4C8], rax
0x18007886c  mov     [rsp+520h+var_4C0], 3D0h
0x180078874  mov     [rsp+520h+var_4BC], 11h
0x18007887c  mov     [rsp+520h+var_4B8], 0FFh
0x180078884  mov     [rbp+420h+var_450], 1000000h
0x18007888b  xor     edx, edx; Val
0x18007888d  lea     r8d, [rdx+60h]; Size
0x180078891  lea     rcx, [rsp+520h+var_4B0]; void *
0x180078896  call    memset_0
0x18007889b  mov     r9, rbx
0x18007889e  lea     r8, aIgnoringDirect; "- Ignoring directory '%s' in enumeratio"...
0x1800788a5  lea     rdx, [rsp+520h+var_4D8]
0x1800788aa  lea     rcx, [rbp+420h+var_330]
0x1800788b1  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800788b6  nop
0x1800788b7  cmp     [rbp+420h+var_368], 8
0x1800788bf  jb      short loc_1800788CD
0x1800788c1  mov     rcx, [rbp+420h+var_380]; Block
0x1800788c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800788cd  mov     [rbp+420h+var_368], r14
0x1800788d4  mov     [rbp+420h+var_370], r12
0x1800788db  mov     word ptr [rbp+420h+var_380], r12w
0x1800788e3  cmp     [rbp+420h+var_390], 8
0x1800788eb  jb      loc_1800786A1
0x1800788f1  mov     rcx, [rbp+420h+Block]; Block
0x1800788f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800788fa  jmp     loc_1800786A1
0x1800788ff  lea     rdx, [rbp+420h+var_380]
0x180078906  mov     rcx, r15
0x180078909  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18007890e  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x180078915  mov     rcx, rdi; hFindFile
0x180078918  call    cs:__imp_FindNextFileW
0x18007891e  test    eax, eax
0x180078920  jnz     short loc_1800788B7
0x180078922  call    cs:__imp_GetLastError
0x180078928  cmp     eax, 12h
0x18007892b  jnz     short loc_18007897B
0x18007892d  cmp     [rbp+420h+var_368], 8
0x180078935  jb      short loc_180078943
0x180078937  mov     rcx, [rbp+420h+var_380]; Block
0x18007893e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078943  mov     [rbp+420h+var_368], r14
  ... truncated ...
```
