# _anonymous_namespace_::sym_module_state::pid_state::load_image

- ea: `0x18008700c`
- end: `0x180087b54`
- name: `_anonymous_namespace_::sym_module_state::pid_state::load_image`
- size: `2888`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: ``

## callers

- `0x180086e70`

## callees

- `0x180004090`
- `0x1800040a0`
- `0x180004510`
- `0x18000491c`
- `0x1800054e4`
- `0x1800054fc`
- `0x180005508`
- `0x18003aaa4`
- `0x18003b0bc`
- `0x18003d720`
- `0x18003f6b8`
- `0x180040f94`
- `0x180041564`
- `0x1800416a0`
- `0x180041e58`
- `0x180042c68`
- `0x1800432dc`
- `0x180044a38`
- `0x180047150`
- `0x18004a1b4`
- `0x1800527d8`
- `0x1800571a4`
- `0x1800587c8`
- `0x180080944`
- `0x180083c7c`
- `0x18008447c`
- `0x1800845d8`
- `0x1800846e4`
- `0x18008491c`
- `0x1800851a4`
- `0x18008526c`
- `0x1800867c8`
- `0x18008700c`
- `0x1800884c0`
- `0x180096b40`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180087842`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180087842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087adf`
- `imagehlp!SymUnloadModule64` at `0x180087aa9`
- `imagehlp!SymUnloadModule64` at `0x180087aa9`
- `imagehlp!SymGetModuleInfoW64` at `0x1800877d3`
- `imagehlp!SymGetModuleInfoW64` at `0x1800877d3`
- `imagehlp!SymFindFileInPathW` at `0x1800873f2`
- `imagehlp!SymFindFileInPathW` at `0x1800873f2`
- `dbghelp!SymLoadModuleExW` at `0x180087783`
- `dbghelp!SymLoadModuleExW` at `0x180087783`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 *__fastcall anonymous_namespace_::sym_module_state::pid_state::load_image(
        int *a1,
        __int64 a2,
        unsigned __int8 a3)
{
  __int64 v5; // r8
  __int64 *v6; // rcx
  __int64 *v7; // rax
  __int64 *v8; // rbx
  unsigned __int64 v9; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 last_trivial_1; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // r15
  __int64 v20; // rdx
  __int64 v21; // r8
  void **v22; // r9
  unsigned __int64 v23; // rdx
  PCWSTR *v24; // rdi
  __int64 v25; // rbx
  DWORD v26; // r12d
  PCWSTR *v27; // rdx
  __int64 v28; // rax
  _QWORD *v29; // rdx
  const WCHAR *v30; // r8
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  PCWSTR *v33; // rdi
  __int64 v34; // rbx
  __int64 *v35; // rdi
  __int64 *v36; // rbx
  __int64 v37; // r8
  unsigned __int64 v38; // rcx
  _QWORD *v39; // r12
  _QWORD *v40; // rdx
  unsigned __int64 v41; // r10
  char *v42; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v44; // rdi
  __int64 v45; // rcx
  __int64 v46; // r8
  _QWORD *v47; // rax
  _QWORD *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // r9
  __int64 v53; // rax
  const WCHAR *v54; // r8
  DWORD64 Module; // rax
  DWORD64 v56; // rbx
  _QWORD *v57; // rdx
  PCWSTR *v58; // r8
  volatile signed __int32 *v59; // rdi
  HANDLE v60; // rax
  HANDLE v61; // rcx
  HANDLE v62; // rcx
  char v64; // [rsp+51h] [rbp-AFh]
  char v65; // [rsp+52h] [rbp-AEh]
  _QWORD v66[2]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD64 v67; // [rsp+68h] [rbp-98h] BYREF
  __int128 v68; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v69; // [rsp+80h] [rbp-80h]
  void *Src[4]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp-50h]
  char v72; // [rsp+B8h] [rbp-48h]
  GUID id; // [rsp+C0h] [rbp-40h] BYREF
  DWORD two; // [rsp+D0h] [rbp-30h]
  _QWORD v75[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v76; // [rsp+F0h] [rbp-10h]
  char v77; // [rsp+F8h] [rbp-8h]
  char v78; // [rsp+100h] [rbp+0h]
  __int64 v79; // [rsp+110h] [rbp+10h]
  __int128 v80; // [rsp+118h] [rbp+18h]
  __int128 v81; // [rsp+128h] [rbp+28h]
  __int128 v82; // [rsp+138h] [rbp+38h]
  int v83; // [rsp+148h] [rbp+48h]
  __int16 v84; // [rsp+14Dh] [rbp+4Dh]
  char v85; // [rsp+14Fh] [rbp+4Fh]
  _QWORD v86[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v87; // [rsp+160h] [rbp+60h]
  unsigned __int64 v88; // [rsp+168h] [rbp+68h]
  PCWSTR ImageName[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v90; // [rsp+180h] [rbp+80h]
  unsigned __int64 v91; // [rsp+188h] [rbp+88h]
  PCWSTR FileName[2]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v93; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v94; // [rsp+1A8h] [rbp+A8h]
  __int128 v95; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v96; // [rsp+1C0h] [rbp+C0h]
  __int64 v97; // [rsp+1C8h] [rbp+C8h]
  _QWORD v98[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v99[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v100[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v101[32]; // [rsp+230h] [rbp+130h] BYREF
  struct _IMAGEHLP_MODULEW64 ModuleInfo; // [rsp+250h] [rbp+150h] BYREF
  WCHAR FoundFile[2]; // [rsp+F10h] [rbp+E10h] BYREF
  int v104; // [rsp+F14h] [rbp+E14h]
  int v105; // [rsp+F18h] [rbp+E18h]
  __int128 v106; // [rsp+F20h] [rbp+E20h]
  _OWORD v107[2]; // [rsp+F30h] [rbp+E30h] BYREF
  int v108; // [rsp+F50h] [rbp+E50h] BYREF
  char v109; // [rsp+F54h] [rbp+E54h]
  __int16 v110; // [rsp+F55h] [rbp+E55h]
  char v111; // [rsp+F57h] [rbp+E57h]
  _BYTE v112[24]; // [rsp+F58h] [rbp+E58h] BYREF
  __int128 v113; // [rsp+F70h] [rbp+E70h]
  _OWORD v114[2]; // [rsp+F80h] [rbp+E80h] BYREF
  int v115; // [rsp+FA0h] [rbp+EA0h] BYREF
  char v116; // [rsp+FA4h] [rbp+EA4h]
  __int16 v117; // [rsp+FA5h] [rbp+EA5h]
  char v118; // [rsp+FA7h] [rbp+EA7h]
  char v119[16]; // [rsp+FA8h] [rbp+EA8h] BYREF
  _BYTE v120[16]; // [rsp+FB8h] [rbp+EB8h] BYREF
  int v121; // [rsp+FC8h] [rbp+EC8h]
  int v122; // [rsp+FCCh] [rbp+ECCh]
  char v123; // [rsp+FD0h] [rbp+ED0h]

  v5 = 0;
  v6 = (__int64 *)*((_QWORD *)a1 + 2);
  v7 = (__int64 *)v6[1];
  HIDWORD(v95) = 0;
  v8 = v6;
  if ( !*((_BYTE *)v7 + 25) )
  {
    v9 = *(_QWORD *)(a2 + 40);
    do
    {
      if ( v7[4] >= v9 )
      {
        v8 = v7;
        v7 = (__int64 *)*v7;
      }
      else
      {
        v7 = (__int64 *)v7[2];
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( !*((_BYTE *)v8 + 25) && *(_QWORD *)(a2 + 40) >= (unsigned __int64)v8[4] && v8 != v6 )
  {
    std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::insert<0,0>(
      v8 + 24,
      &v95,
      a2 + 36);
    return v8 + 5;
  }
  v11 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) <= 0xFu )
    v12 = a2;
  else
    v12 = *(_QWORD *)a2;
  if ( !v11 )
    goto LABEL_20;
  v13 = v11 - 1;
  if ( v13 == -1 )
    v13 = -1;
  v14 = v12 + v13 + 1;
  LOBYTE(v5) = 92;
  last_trivial_1 = _std_find_last_trivial_1(v12, v14, v5);
  if ( last_trivial_1 == v14 )
LABEL_20:
    v16 = -1;
  else
    v16 = last_trivial_1 - v12;
  if ( *(_QWORD *)(a2 + 24) <= 0xFu )
    v17 = a2;
  else
    v17 = *(_QWORD *)a2;
  windiag::char_to_wstring(v86, v16 + v17 + 1);
  std::string::string(v98);
  v78 = 0;
  v65 = 0;
  v64 = 0;
  v18 = v98;
  if ( v98[3] > 0xFu )
    v18 = (_QWORD *)v98[0];
  windiag::char_to_wstring(ImageName, v18);
  v19 = -1;
  v79 = -1;
  if ( *(_QWORD *)(a2 + 24) <= 0xFu )
    v20 = a2;
  else
    v20 = *(_QWORD *)a2;
  anonymous_namespace_::sym_open_nt_path(Src, v20);
  if ( v72 )
  {
    v22 = Src;
    if ( Src[3] > (void *)7 )
      v22 = (void **)Src[0];
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)v22 + v23) );
    if ( v23 > v91 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        ImageName,
        v23,
        v21,
        v22);
    }
    else
    {
      v24 = ImageName;
      if ( v91 > 7 )
        v24 = (PCWSTR *)ImageName[0];
      v90 = v23;
      v25 = 2 * v23;
      memmove_0(v24, v22, 2 * v23);
      *(_WORD *)((char *)v24 + v25) = 0;
    }
    anonymous_namespace_::file_image_info::get((__int64)FoundFile, hFile);
    if ( v123 )
    {
      std::optional__anonymous_namespace_::file_image_info::pdb_info_::operator_(&id, (char *)v114 + 8);
      if ( LOBYTE(v114[0]) )
      {
        if ( BYTE8(v113) )
          std::wstring::operator=(v86, v112);
        v80 = v106;
        v81 = v107[0];
        v82 = v107[1];
        v83 = v108;
        v65 = v109;
        v84 = v110;
        v85 = v111;
      }
      v26 = *(_DWORD *)FoundFile;
      LODWORD(v67) = *(_DWORD *)FoundFile;
      LODWORD(v68) = v104;
      LODWORD(v66[0]) = v105;
      v64 = 1;
      if ( v123 )
      {
        if ( (_BYTE)v121 && v120[8] )
          std::string::~string(&v115);
        if ( LOBYTE(v114[0]) && BYTE8(v113) )
          std::wstring::~wstring(v112);
      }
    }
    else
    {
      v26 = v66[0];
      LODWORD(v67) = v66[0];
      LODWORD(v68) = v66[0];
    }
    v27 = ImageName;
    if ( v91 > 7 )
      v27 = (PCWSTR *)ImageName[0];
    v28 = windiag::wchar_to_string(FileName, v27);
    std::string::operator=(v98, v28);
    std::string::~string(FileName);
    v19 = (__int64)hFile;
    hFile = (HANDLE)-1LL;
    v79 = v19;
    if ( !a3 && v78 && v77 )
    {
      memset_0(FoundFile, 0, 0x20Au);
      v29 = v75;
      if ( v76 > 0xF )
        v29 = (_QWORD *)v75[0];
      windiag::char_to_wstring(FileName, v29);
      v30 = (const WCHAR *)FileName;
      if ( v94 > 7 )
        v30 = FileName[0];
      if ( SymFindFileInPathW(
             *(HANDLE *)a1,
             0,
             v30,
             &id,
             two,
             0,
             8u,
             FoundFile,
             lambda_7981014a4b33dae1449f67909520e4bc_::_lambda_invoker_cdecl__unsigned_short_const___void___,
             &id) )
      {
        v32 = -1;
        do
          ++v32;
        while ( FoundFile[v32] );
        if ( v32 > v91 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            ImageName,
            v32,
            v31,
            FoundFile);
        }
        else
        {
          v33 = ImageName;
          if ( v91 > 7 )
            v33 = (PCWSTR *)ImageName[0];
          v90 = v32;
          v34 = 2 * v32;
          memmove_0(v33, FoundFile, 2 * v32);
          *(_WORD *)((char *)v33 + v34) = 0;
        }
        if ( v78 )
        {
          if ( v77 )
            std::string::~string(v75);
          v78 = 0;
        }
      }
      std::wstring::~wstring(FileName);
    }
  }
  else
  {
    v26 = v66[0];
    LODWORD(v67) = v66[0];
    LODWORD(v68) = v66[0];
  }
  v35 = (__int64 *)*((_QWORD *)a1 + 4);
  v36 = (__int64 *)v35[1];
  HIDWORD(v95) = 0;
  if ( !*((_BYTE *)v36 + 25) )
  {
    do
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v36 + 4, v86) )
      {
        v36 = (__int64 *)v36[2];
      }
      else
      {
        v35 = v36;
        v36 = (__int64 *)*v36;
      }
    }
    while ( !*((_BYTE *)v36 + 25) );
    v26 = v67;
  }
  if ( !*((_BYTE *)v35 + 25)
    && !(unsigned __int8)std::operator<<unsigned short>(v86, v35 + 4)
    && v35 != *((__int64 **)a1 + 4) )
  {
    memset_0(FoundFile, 0, 0x80u);
    _snwprintf_s<64>(FoundFile, -1, L"%llx", *(_QWORD *)(a2 + 40));
    v38 = v87;
    v39 = v86;
    v40 = (_QWORD *)v86[0];
    v41 = v88;
    if ( v88 > 7 )
      v39 = (_QWORD *)v86[0];
    if ( !v87
      || (v42 = (char *)v39 + 2 * v87,
          last_trivial_2 = _std_find_last_trivial_2(v39, v42, 46),
          v41 = v88,
          v38 = v87,
          v40 = (_QWORD *)v86[0],
          (char *)last_trivial_2 == v42) )
    {
      v44 = -1;
    }
    else
    {
      v44 = (last_trivial_2 - (__int64)v39) >> 1;
    }
    if ( v44 == -1 )
    {
      if ( v38 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v52 = v86;
      if ( v41 > 7 )
        v52 = v40;
      std::wstring::wstring(FileName, v40, v37, v52, v38, L"_", 1);
      v53 = std::operator+<unsigned short>(v99, FileName, FoundFile);
      std::wstring::operator=(v86, v53);
      std::wstring::~wstring(v99);
    }
    else
    {
      *(_OWORD *)FileName = 0;
      v93 = 0;
      v94 = 0;
      if ( v38 < v44 )
        std::_String_val<std::_Simple_types<char>>::_Xran(v38, v40);
      v45 = v38 - v44;
      v46 = -1;
      if ( v45 != -1 )
        v46 = v45;
      v47 = v86;
      if ( v41 > 7 )
        v47 = v40;
      std::wstring::_Construct<1,unsigned short const *>(FileName, (char *)v47 + 2 * v44, v46);
      v95 = 0;
      v96 = 0;
      v97 = 0;
      if ( v87 < v44 )
        v44 = v87;
      v48 = v86;
      if ( v88 > 7 )
        v48 = (_QWORD *)v86[0];
      std::wstring::_Construct<1,unsigned short const *>(&v95, v48, v44);
      v49 = std::operator+<unsigned short>(v99, &v95, L"_");
      v50 = std::operator+<unsigned short>(v101, v49, FoundFile);
      v51 = std::operator+<unsigned short>(v100, v50, FileName);
      std::wstring::operator=(v86, v51);
      std::wstring::~wstring(v100);
      std::wstring::~wstring(v101);
      std::wstring::~wstring(v99);
      std::wstring::~wstring(&v95);
    }
    std::wstring::~wstring(FileName);
    v26 = v67;
  }
  v54 = (const WCHAR *)ImageName;
  if ( v91 > 7 )
    v54 = ImageName[0];
  Module = SymLoadModuleExW(*(HANDLE *)a1, (HANDLE)v19, v54, 0, *(_QWORD *)(a2 + 40), *(_DWORD *)(a2 + 48), 0, a3);
  v56 = Module;
  v67 = Module;
  if ( Module && (!*(_QWORD *)(a2 + 40) || Module == *(_QWORD *)(a2 + 40)) )
  {
    *(_QWORD *)&ModuleInfo.SizeOfStruct = 3256;
    memset_0(&ModuleInfo.BaseOfImage, 0, 0xCB8u);
    if ( SymGetModuleInfoW64(*(HANDLE *)a1, v56, &ModuleInfo) )
    {
      if ( v78 )
      {
        ModuleInfo.PdbSig70 = id;
        ModuleInfo.PdbAge = two;
        if ( v77 )
        {
          v57 = v75;
          if ( v76 > 0xF )
            v57 = (_QWORD *)v75[0];
          windiag::char_to_wstring(FileName, v57);
          v58 = FileName;
          if ( v94 > 7 )
            v58 = (PCWSTR *)FileName[0];
          _o_wcsncpy_s(ModuleInfo.LoadedPdbName, 256, v58, -1);
          std::wstring::~wstring(FileName);
        }
      }
      if ( v64 )
      {
        ModuleInfo.TimeDateStamp = v26;
        ModuleInfo.ImageSize = v68;
        ModuleInfo.CheckSum = v66[0];
      }
      v59 = (volatile signed __int32 *)operator new(0xCD0u);
      v66[0] = v59;
      *(_OWORD *)v59 = 0;
      *((_DWORD *)v59 + 2) = 1;
      *((_DWORD *)v59 + 3) = 1;
      *(_QWORD *)v59 = &std::_Ref_count_obj2<_IMAGEHLP_MODULEW64>::`vftable';
      memcpy_0((void *)(v59 + 4), &ModuleInfo, 0xCC0u);
      *(_QWORD *)&v95 = v59 + 4;
      *((_QWORD *)&v95 + 1) = v59;
      std::string::string(FoundFile);
      std::string::string(v107);
      std::wstring::wstring(&v108, v86);
      v113 = v80;
      v114[0] = v81;
      v114[1] = v82;
      v115 = v83;
      v116 = v65;
      v117 = v84;
      v118 = v85;
      LODWORD(v66[0]) = *(_DWORD *)(a2 + 36);
      *(_QWORD *)&v68 = v66;
      *((_QWORD *)&v68 + 1) = (char *)v66 + 4;
      std::set<unsigned int>::set<unsigned int>(v119, &v68);
      v60 = *(HANDLE *)a1;
      v68 = 0;
      _InterlockedIncrement(v59 + 2);
      *(_QWORD *)&v68 = v59 + 4;
      *((_QWORD *)&v68 + 1) = v59;
      v69 = v60;
      std::shared_ptr__IMAGEHLP_MODULEW64_::shared_ptr__IMAGEHLP_MODULEW64___IMAGEHLP_MODULEW64__lambda_a42be1dd19df51563e781783950b6ab6__0_(
        v120,
        v59 + 4,
        &v68);
      v121 = *a1;
      v122 = 0;
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
        a1 + 8,
        v66,
        v86);
      std::_Tree_std::_Tmap_traits_unsigned___int64__anonymous_namespace_::sym_image_std::less_unsigned___int64__std::allocator_std::pair_unsigned___int64_const___anonymous_namespace_::sym_image____0___::emplace_unsigned___int64_const____anonymous_namespace_::sym_image_(
        a1 + 4,
        v66,
        &v67,
        FoundFile);
      v8 = (__int64 *)v66[0];
      anonymous_namespace_::sym_image::_sym_image(FoundFile);
      if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
      if ( v72 )
      {
        v61 = hFile;
        if ( hFile != (HANDLE)-1LL )
        {
          hFile = (HANDLE)-1LL;
          CloseHandle(v61);
        }
        hFile = (HANDLE)-1LL;
        std::wstring::~wstring(Src);
      }
      if ( v19 != -1 )
        CloseHandle((HANDLE)v19);
      std::wstring::~wstring(ImageName);
      if ( v78 )
      {
        if ( v77 )
          std::string::~string(v75);
      }
      std::string::~string(v98);
      std::wstring::~wstring(v86);
      return v8 + 5;
    }
    SymUnloadModule64(*(HANDLE *)a1, v56);
  }
  if ( v72 )
  {
    v62 = hFile;
    if ( hFile != (HANDLE)-1LL )
    {
      hFile = (HANDLE)-1LL;
      CloseHandle(v62);
    }
    hFile = (HANDLE)-1LL;
    std::wstring::~wstring(Src);
  }
  if ( v19 != -1 )
    CloseHandle((HANDLE)v19);
  std::wstring::~wstring(ImageName);
  if ( v78 && v77 )
    std::string::~string(v75);
  std::string::~string(v98);
  std::wstring::~wstring(v86);
  return 0;
}

```

## disassembly

```asm
0x18008700c  mov     [rsp-8+arg_10], rbx
0x180087011  push    rbp
0x180087012  push    rsi
0x180087013  push    rdi
0x180087014  push    r12
0x180087016  push    r13
0x180087018  push    r14
0x18008701a  push    r15
0x18008701c  lea     rbp, [rsp-1030h]
0x180087024  mov     eax, 1130h
0x180087029  call    _alloca_probe
0x18008702e  sub     rsp, rax
0x180087031  mov     rax, cs:__security_cookie
0x180087038  xor     rax, rsp
0x18008703b  mov     [rbp+1060h+var_40], rax
0x180087042  mov     [rsp+1160h+var_1110], r8b
0x180087047  mov     r14, rdx
0x18008704a  mov     r13, rcx
0x18008704d  xor     r8d, r8d
0x180087050  mov     rcx, [rcx+10h]
0x180087054  mov     rax, [rcx+8]
0x180087058  xor     edx, edx
0x18008705a  mov     dword ptr [rbp+1060h+var_FB0+0Ch], edx
0x180087060  mov     rbx, rcx
0x180087063  cmp     [rax+19h], r8b
0x180087067  jnz     short loc_180087085
0x180087069  mov     rdx, [r14+28h]
0x18008706d  cmp     [rax+20h], rdx
0x180087071  jnb     short loc_180087079
0x180087073  mov     rax, [rax+10h]
0x180087077  jmp     short loc_18008707F
0x180087079  mov     rbx, rax
0x18008707c  mov     rax, [rax]
0x18008707f  cmp     [rax+19h], r8b
0x180087083  jz      short loc_18008706D
0x180087085  cmp     [rbx+19h], r8b
0x180087089  jnz     short loc_1800870BA
0x18008708b  mov     rax, [rbx+20h]
0x18008708f  cmp     [r14+28h], rax
0x180087093  jb      short loc_1800870BA
0x180087095  cmp     rbx, rcx
0x180087098  jz      short loc_1800870BA
0x18008709a  lea     r8, [r14+24h]
0x18008709e  lea     rcx, [rbx+0C0h]
0x1800870a5  lea     rdx, [rbp+1060h+var_FB0]
0x1800870ac  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::insert<0,0>(uint const &)
0x1800870b1  lea     rax, [rbx+28h]
0x1800870b5  jmp     loc_180087B1E
0x1800870ba  mov     rax, [r14+10h]
0x1800870be  cmp     qword ptr [r14+18h], 0Fh
0x1800870c3  jbe     short loc_1800870CA
0x1800870c5  mov     rdi, [r14]
0x1800870c8  jmp     short loc_1800870CD
0x1800870ca  mov     rdi, r14
0x1800870cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800870d1  test    rax, rax
0x1800870d4  jz      short loc_1800870FF
0x1800870d6  dec     rax
0x1800870d9  cmp     rax, rsi
0x1800870dc  cmovnb  rax, rsi
0x1800870e0  lea     rbx, [rax+1]
0x1800870e4  add     rbx, rdi
0x1800870e7  mov     r8b, 5Ch ; '\'
0x1800870ea  mov     rdx, rbx
0x1800870ed  mov     rcx, rdi
0x1800870f0  call    __std_find_last_trivial_1
0x1800870f5  cmp     rax, rbx
0x1800870f8  jz      short loc_1800870FF
0x1800870fa  sub     rax, rdi
0x1800870fd  jmp     short loc_180087102
0x1800870ff  mov     rax, rsi
0x180087102  cmp     qword ptr [r14+18h], 0Fh
0x180087107  jbe     short loc_18008710E
0x180087109  mov     rcx, [r14]
0x18008710c  jmp     short loc_180087111
0x18008710e  mov     rcx, r14
0x180087111  lea     rdx, [rcx+1]
0x180087115  add     rdx, rax
0x180087118  lea     rcx, [rbp+1060h+var_1010]
0x18008711c  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180087121  nop
0x180087122  mov     rdx, r14
0x180087125  lea     rcx, [rbp+1060h+var_F90]
0x18008712c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180087131  nop
0x180087132  xor     edi, edi
0x180087134  mov     [rbp+1060h+var_1060], dil
0x180087138  mov     [rsp+1160h+var_110E], dil
0x18008713d  mov     [rsp+1160h+var_110F], dil
0x180087142  lea     rdx, [rbp+1060h+var_F90]
0x180087149  cmp     [rbp+1060h+var_F78], 0Fh
0x180087151  cmova   rdx, [rbp+1060h+var_F90]
0x180087159  lea     rcx, [rbp+1060h+ImageName]
0x18008715d  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180087162  nop
0x180087163  mov     r15, rsi
0x180087166  mov     [rbp+1060h+var_1050], rsi
0x18008716a  cmp     qword ptr [r14+18h], 0Fh
0x18008716f  jbe     short loc_180087176
0x180087171  mov     rdx, [r14]
0x180087174  jmp     short loc_180087179
0x180087176  mov     rdx, r14
0x180087179  lea     rcx, [rbp+1060h+Src]
0x18008717d  call    _anonymous_namespace___sym_open_nt_path
0x180087182  nop
0x180087183  cmp     [rbp+1060h+var_10A8], dil
0x180087187  jz      loc_180087487
0x18008718d  lea     r9, [rbp+1060h+Src]
0x180087191  cmp     [rbp+1060h+var_10B8], 7
0x180087196  cmova   r9, [rbp+1060h+Src]
0x18008719b  mov     rdx, rsi
0x18008719e  inc     rdx
0x1800871a1  cmp     [r9+rdx*2], di
0x1800871a6  jnz     short loc_18008719E
0x1800871a8  cmp     rdx, [rbp+1060h+var_FD8]
0x1800871af  ja      short loc_1800871E5
0x1800871b1  lea     rdi, [rbp+1060h+ImageName]
0x1800871b5  cmp     [rbp+1060h+var_FD8], 7
0x1800871bd  cmova   rdi, [rbp+1060h+ImageName]
0x1800871c2  mov     [rbp+1060h+var_FE0], rdx
0x1800871c9  lea     rbx, [rdx+rdx]
0x1800871cd  mov     r8, rbx; Size
0x1800871d0  mov     rdx, r9; Src
0x1800871d3  mov     rcx, rdi; void *
0x1800871d6  call    memmove_0
0x1800871db  xor     eax, eax
0x1800871dd  mov     [rbx+rdi], ax
0x1800871e1  xor     edi, edi
0x1800871e3  jmp     short loc_1800871EE
0x1800871e5  lea     rcx, [rbp+1060h+ImageName]
0x1800871e9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800871ee  mov     rdx, [rbp+1060h+hFile]
0x1800871f2  lea     rcx, [rbp+1060h+var_250]
0x1800871f9  call    _anonymous_namespace___file_image_info__get
0x1800871fe  cmp     [rbp+1060h+var_190], dil
0x180087205  jz      loc_1800872F1
0x18008720b  lea     rdx, [rbp+1060h+var_1E0+8]
0x180087212  lea     rcx, [rbp+1060h+id]
0x180087216  call    std__optional__anonymous_namespace___file_image_info__pdb_info___operator_
0x18008721b  cmp     byte ptr [rbp+1060h+var_1E0], dil
0x180087222  jz      short loc_180087285
0x180087224  cmp     [rbp+1060h+var_1E8], dil
0x18008722b  jz      short loc_18008723D
0x18008722d  lea     rdx, [rbp+1060h+var_208]
0x180087234  lea     rcx, [rbp+1060h+var_1010]
0x180087238  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008723d  movaps  xmm0, [rbp+1060h+var_240]
0x180087244  movups  [rbp+1060h+var_1048], xmm0
0x180087248  movaps  xmm1, [rbp+1060h+var_230]
0x18008724f  movups  [rbp+1060h+var_1038], xmm1
0x180087253  movaps  xmm0, [rbp+1060h+var_220]
0x18008725a  movups  [rbp+1060h+var_1028], xmm0
0x18008725e  mov     eax, [rbp+1060h+var_210]
0x180087264  mov     [rbp+1060h+var_1018], eax
0x180087267  mov     al, [rbp+1060h+var_20C]
0x18008726d  mov     [rsp+1160h+var_110E], al
0x180087271  movzx   eax, [rbp+1060h+var_20B]
0x180087278  mov     [rbp+1060h+var_1013], ax
0x18008727c  mov     al, [rbp+1060h+var_209]
0x180087282  mov     [rbp+1060h+var_1011], al
0x180087285  mov     r12d, dword ptr [rbp+1060h+var_250]
0x18008728c  mov     dword ptr [rsp+1160h+var_10F8], r12d
0x180087291  mov     ebx, [rbp+1060h+var_24C]
0x180087297  mov     dword ptr [rsp+1160h+var_10F0], ebx
0x18008729b  mov     ebx, [rbp+1060h+var_248]
0x1800872a1  mov     dword ptr [rsp+1160h+var_1108], ebx
0x1800872a5  mov     [rsp+1160h+var_110F], 1
0x1800872aa  cmp     [rbp+1060h+var_190], dil
0x1800872b1  jz      short loc_18008730B
0x1800872b3  cmp     byte ptr [rbp+1060h+var_198], dil
0x1800872ba  jz      short loc_1800872D1
0x1800872bc  cmp     [rbp+1060h+var_1A0], dil
0x1800872c3  jz      short loc_1800872D1
0x1800872c5  lea     rcx, [rbp+1060h+var_1C0]
0x1800872cc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800872d1  cmp     byte ptr [rbp+1060h+var_1E0], dil
0x1800872d8  jz      short loc_18008730B
0x1800872da  cmp     [rbp+1060h+var_1E8], dil
0x1800872e1  jz      short loc_18008730B
0x1800872e3  lea     rcx, [rbp+1060h+var_208]
0x1800872ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800872ef  jmp     short loc_18008730B
0x1800872f1  mov     eax, dword ptr [rsp+1160h+var_1108]
0x1800872f5  mov     dword ptr [rsp+1160h+var_1108], eax
0x1800872f9  mov     r12d, dword ptr [rsp+1160h+var_1108]
0x1800872fe  mov     dword ptr [rsp+1160h+var_10F8], r12d
0x180087303  mov     eax, dword ptr [rsp+1160h+var_1108]
0x180087307  mov     dword ptr [rsp+1160h+var_10F0], eax
0x18008730b  lea     rdx, [rbp+1060h+ImageName]
0x18008730f  cmp     [rbp+1060h+var_FD8], 7
0x180087317  cmova   rdx, [rbp+1060h+ImageName]
0x18008731c  lea     rcx, [rbp+1060h+FileName]
0x180087323  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180087328  mov     rdx, rax
0x18008732b  lea     rcx, [rbp+1060h+var_F90]
0x180087332  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180087337  lea     rcx, [rbp+1060h+FileName]
0x18008733e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180087343  mov     r15, [rbp+1060h+hFile]
0x180087347  mov     [rbp+1060h+hFile], rsi
0x18008734b  mov     [rbp+1060h+var_1050], r15
0x18008734f  cmp     [rsp+1160h+var_1110], dil
0x180087354  jnz     loc_1800874A1
0x18008735a  cmp     [rbp+1060h+var_1060], dil
0x18008735e  jz      loc_1800874A1
0x180087364  cmp     [rbp+1060h+var_1068], dil
0x180087368  jz      loc_1800874A1
0x18008736e  xor     edx, edx; Val
0x180087370  mov     r8d, 20Ah; Size
0x180087376  lea     rcx, [rbp+1060h+var_250]; void *
0x18008737d  call    memset_0
0x180087382  lea     rdx, [rbp+1060h+var_1088]
0x180087386  cmp     [rbp+1060h+var_1070], 0Fh
0x18008738b  cmova   rdx, [rbp+1060h+var_1088]
0x180087390  lea     rcx, [rbp+1060h+FileName]
0x180087397  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008739c  nop
0x18008739d  mov     eax, [rbp+1060h+var_1090]
0x1800873a0  lea     r8, [rbp+1060h+FileName]
0x1800873a7  cmp     [rbp+1060h+var_FB8], 7
0x1800873af  cmova   r8, [rbp+1060h+FileName]; FileName
0x1800873b7  lea     rcx, [rbp+1060h+id]
0x1800873bb  mov     [rsp+1160h+context], rcx; context
0x1800873c0  lea     rcx, _lambda_7981014a4b33dae1449f67909520e4bc____lambda_invoker_cdecl__unsigned_short_const___void___
0x1800873c7  mov     [rsp+1160h+callback], rcx; callback
0x1800873cc  lea     rcx, [rbp+1060h+var_250]
0x1800873d3  mov     [rsp+1160h+FoundFile], rcx; FoundFile
0x1800873d8  mov     [rsp+1160h+flags], 8; flags
0x1800873e0  mov     [rsp+1160h+three], edi; three
0x1800873e4  mov     [rsp+1160h+two], eax; two
0x1800873e8  lea     r9, [rbp+1060h+id]; id
0x1800873ec  xor     edx, edx; SearchPathA
0x1800873ee  mov     rcx, [r13+0]; hprocess
0x1800873f2  call    cs:__imp_SymFindFileInPathW
0x1800873f8  test    eax, eax
0x1800873fa  jz      short loc_180087479
0x1800873fc  lea     rax, [rbp+1060h+var_250]
0x180087403  mov     rdx, rsi
0x180087406  inc     rdx
0x180087409  cmp     [rax+rdx*2], di
0x18008740d  jnz     short loc_180087406
0x18008740f  cmp     rdx, [rbp+1060h+var_FD8]
0x180087416  ja      short loc_180087450
0x180087418  lea     rdi, [rbp+1060h+ImageName]
0x18008741c  cmp     [rbp+1060h+var_FD8], 7
0x180087424  cmova   rdi, [rbp+1060h+ImageName]
0x180087429  mov     [rbp+1060h+var_FE0], rdx
0x180087430  lea     rbx, [rdx+rdx]
0x180087434  mov     r8, rbx; Size
0x180087437  lea     rdx, [rbp+1060h+var_250]; Src
0x18008743e  mov     rcx, rdi; void *
0x180087441  call    memmove_0
0x180087446  xor     eax, eax
0x180087448  mov     [rbx+rdi], ax
0x18008744c  xor     edi, edi
0x18008744e  jmp     short loc_180087460
0x180087450  lea     r9, [rbp+1060h+var_250]
0x180087457  lea     rcx, [rbp+1060h+ImageName]
0x18008745b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180087460  cmp     [rbp+1060h+var_1060], dil
0x180087464  jz      short loc_180087479
0x180087466  cmp     [rbp+1060h+var_1068], dil
0x18008746a  jz      short loc_180087475
0x18008746c  lea     rcx, [rbp+1060h+var_1088]
0x180087470  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180087475  mov     [rbp+1060h+var_1060], dil
0x180087479  lea     rcx, [rbp+1060h+FileName]
0x180087480  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087485  jmp     short loc_1800874A1
0x180087487  mov     eax, dword ptr [rsp+1160h+var_1108]
0x18008748b  mov     dword ptr [rsp+1160h+var_1108], eax
0x18008748f  mov     r12d, dword ptr [rsp+1160h+var_1108]
0x180087494  mov     dword ptr [rsp+1160h+var_10F8], r12d
0x180087499  mov     eax, dword ptr [rsp+1160h+var_1108]
0x18008749d  mov     dword ptr [rsp+1160h+var_10F0], eax
0x1800874a1  mov     rdi, [r13+20h]
0x1800874a5  mov     rbx, [rdi+8]
0x1800874a9  xor     eax, eax
0x1800874ab  mov     dword ptr [rbp+1060h+var_FB0+0Ch], eax
0x1800874b1  cmp     [rbx+19h], al
0x1800874b4  jnz     short loc_1800874E1
0x1800874b6  xor     r12d, r12d
0x1800874b9  lea     rcx, [rbx+20h]
0x1800874bd  lea     rdx, [rbp+1060h+var_1010]
0x1800874c1  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800874c6  test    al, al
0x1800874c8  jz      short loc_1800874D0
0x1800874ca  mov     rbx, [rbx+10h]
0x1800874ce  jmp     short loc_1800874D6
0x1800874d0  mov     rdi, rbx
0x1800874d3  mov     rbx, [rbx]
0x1800874d6  cmp     [rbx+19h], r12b
0x1800874da  jz      short loc_1800874B9
0x1800874dc  mov     r12d, dword ptr [rsp+1160h+var_10F8]
0x1800874e1  xor     ebx, ebx
0x1800874e3  cmp     [rdi+19h], bl
0x1800874e6  jnz     loc_180087747
0x1800874ec  lea     rdx, [rdi+20h]
0x1800874f0  lea     rcx, [rbp+1060h+var_1010]
0x1800874f4  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
  ... truncated ...
```
