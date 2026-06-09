# CThumbnailCache::_CreateCacheFileObjects(void)

- ea: `0x180015d40`
- end: `0x180016658`
- name: `?_CreateCacheFileObjects@CThumbnailCache@@AEAAJXZ`
- size: `2328`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180015868`
- `0x1800416d0`

## callees

- `0x18000b3c0`
- `0x18000bc40`
- `0x180015d40`
- `0x180017714`
- `0x180017af0`
- `0x180017b7c`
- `0x180018548`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180016305`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180016305`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016470`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016470`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800164a3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800164a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180015df1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016351`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016383`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180015df1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016351`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016383`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180016107`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180016107`

## string_xrefs

- `0x180015f2b`: `thumbcache_%d.db`
- `0x180016075`: `thumbcache_%d.db`
- `0x180015f24`: `thumbcache_wide_alternate.db`
- `0x180016059`: `thumbcache_wide_alternate.db`
- `0x180015f1d`: `thumbcache_wide.db`
- `0x180016052`: `thumbcache_wide.db`
- `0x180015dda`: `thumbcache_idx.db`
- `0x180015de1`: `iconcache_idx.db`
- `0x180015fd9`: `iconcache_%d.db`
- `0x180016539`: `thumbcache_exif.db`
- `0x180016532`: `iconcache_exif.db`
- `0x180016365`: `iconcache_sr.db`
- `0x18001636c`: `thumbcache_sr.db`
- `0x180016550`: `iconcache_wide.db`
- `0x180016567`: `iconcache_wide_alternate.db`
- `0x180016577`: `iconcache_custom_stream.db`
- `0x18001657e`: `thumbcache_custom_stream.db`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_CreateCacheFileObjects(CThumbnailCache *this)
{
  CThumbnailCache *v1; // rsi
  __int64 v2; // rax
  WCHAR *v3; // rdi
  WCHAR *v4; // r9
  __int64 v5; // rdx
  WCHAR *v6; // r8
  WCHAR v7; // cx
  unsigned int v8; // r9d
  WCHAR *v9; // rcx
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // r8
  WCHAR v15; // r9
  WCHAR *v16; // rcx
  int Error; // ebx
  CThumbnailCacheIndex *v18; // rax
  CThumbnailCacheIndex *v19; // rax
  const unsigned __int16 *v20; // rdi
  __int64 v21; // rcx
  WCHAR *v22; // rdx
  __int64 v23; // r8
  WCHAR *v24; // r9
  WCHAR v25; // ax
  WCHAR *v26; // rcx
  __int64 v27; // r13
  __int64 v28; // rcx
  WCHAR *v29; // rdx
  __int64 v30; // r8
  WCHAR *v31; // r9
  WCHAR v32; // ax
  WCHAR *v33; // rcx
  const unsigned __int16 *v34; // r8
  __int64 v35; // r9
  _WORD *v36; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  WCHAR *v40; // r8
  WCHAR v41; // ax
  WCHAR *v42; // r10
  WCHAR *v43; // rcx
  unsigned int v44; // eax
  __int64 v45; // rdx
  RTL_SRWLOCK *v46; // r15
  unsigned __int64 v47; // rdi
  WCHAR *v48; // rsi
  int v49; // r11d
  WCHAR *v50; // rcx
  __int64 v51; // rdx
  unsigned __int64 v52; // r8
  WCHAR *v53; // r9
  __int64 v54; // r10
  WCHAR v55; // ax
  __int64 v56; // rdx
  WCHAR *v57; // rcx
  WCHAR *v58; // rcx
  unsigned __int64 v59; // rax
  void *MutexWithUserSecurity; // rbx
  PVOID Ptr; // rcx
  int v62; // eax
  int v63; // ecx
  RTL_SRWLOCK **v64; // rdx
  unsigned int v65; // ebx
  __int64 v66; // rax
  WCHAR *v67; // rdx
  const WCHAR *v68; // rdx
  const wchar_t *v69; // rax
  __int64 v70; // rcx
  WCHAR *v71; // rdx
  __int64 v72; // r8
  WCHAR *v73; // r9
  WCHAR v74; // ax
  WCHAR *v75; // rcx
  CThumbnailCache *v76; // rcx
  char *v77; // rdi
  PVOID v78; // r12
  void *v79; // rsi
  RTL_SRWLOCK *v80; // rax
  RTL_SRWLOCK *v81; // r14
  __int64 v82; // rcx
  __int16 *v83; // rdx
  __int64 v84; // r8
  _WORD *v85; // r9
  __int16 v86; // ax
  CThumbnailCache *v87; // [rsp+20h] [rbp-E0h]
  WCHAR *v88; // [rsp+28h] [rbp-D8h]
  _QWORD v89[5]; // [rsp+38h] [rbp-C8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszMore[264]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v92[528]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Name[264]; // [rsp+690h] [rbp+590h] BYREF

  v1 = this;
  v87 = this;
  v2 = 2147483646;
  v3 = (WCHAR *)((char *)this + 72);
  v88 = (WCHAR *)((char *)this + 72);
  v4 = (WCHAR *)((char *)this + 72);
  v5 = 260;
  v6 = pszPath;
  do
  {
    if ( !v2 )
      break;
    v7 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v6++ = v7;
    --v2;
    --v5;
  }
  while ( v5 );
  v8 = -2147024774;
  if ( v5 )
    v8 = 0;
  v9 = v6 - 1;
  if ( v5 )
    v9 = v6;
  *v9 = 0;
  if ( !v5 )
    return v8;
  v10 = L"iconcache_idx.db";
  if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
    v10 = L"thumbcache_idx.db";
  if ( PathAppendW(pszPath, v10) )
  {
    v11 = 2147483646;
    v12 = pszPath;
    v13 = 260;
    v14 = pszMore;
    do
    {
      if ( !v11 )
        break;
      v15 = *v12;
      if ( !*v12 )
        break;
      ++v12;
      *v14++ = v15;
      --v11;
      --v13;
    }
    while ( v13 );
    v8 = -2147024774;
    if ( v13 )
      v8 = 0;
    v16 = v14 - 1;
    if ( v13 )
      v16 = v14;
    *v16 = 0;
    if ( !v13 )
      return v8;
    *((_QWORD *)v1 + 6) = 0;
    Error = -2147024882;
    v18 = (CThumbnailCacheIndex *)operator new(0x270u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v18 )
    {
      v19 = CThumbnailCacheIndex::CThumbnailCacheIndex(v18);
      v20 = (const unsigned __int16 *)v19;
      if ( v19 )
      {
        v21 = 2147483646;
        v22 = pszMore;
        v23 = 260;
        v24 = (WCHAR *)((char *)v19 + 100);
        do
        {
          if ( !v21 )
            break;
          v25 = *v22;
          if ( !*v22 )
            break;
          ++v22;
          *v24++ = v25;
          --v21;
          --v23;
        }
        while ( v23 );
        Error = -2147024774;
        if ( v23 )
          Error = 0;
        v26 = v24 - 1;
        if ( v23 )
          v26 = v24;
        *v26 = 0;
        if ( v23 && (Error = CReadersWriterLock::Initialize((CReadersWriterLock *)(v20 + 4), v20 + 50), Error >= 0) )
          *((_QWORD *)v1 + 6) = v20;
        else
          (*(void (__fastcall **)(const unsigned __int16 *, WCHAR *))(*(_QWORD *)v20 + 16LL))(v20, v22);
      }
      v3 = (WCHAR *)((char *)v1 + 72);
    }
    if ( Error < 0 )
      return (unsigned int)Error;
    v27 = 0;
    while ( 1 )
    {
      if ( Error < 0 )
        return (unsigned int)Error;
      v28 = 2147483646;
      v29 = v3;
      v30 = 260;
      v31 = pszPath;
      do
      {
        if ( !v28 )
          break;
        v32 = *v29;
        if ( !*v29 )
          break;
        ++v29;
        *v31++ = v32;
        --v28;
        --v30;
      }
      while ( v30 );
      Error = -2147024774;
      if ( v30 )
        Error = 0;
      v33 = v31 - 1;
      if ( v30 )
        v33 = v31;
      *v33 = 0;
      if ( v30 )
        break;
LABEL_67:
      v27 = (unsigned int)(v27 + 1);
      if ( (int)v27 >= 14 )
        return (unsigned int)Error;
    }
    switch ( (_DWORD)v27 )
    {
      case 9:
        v68 = L"iconcache_sr.db";
        v69 = L"thumbcache_sr.db";
        break;
      case 0xA:
        v67 = L"iconcache_wide.db";
        if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
          v67 = L"thumbcache_wide.db";
        goto LABEL_125;
      case 0xC:
        v67 = L"iconcache_wide_alternate.db";
        if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
          v67 = L"thumbcache_wide_alternate.db";
        goto LABEL_125;
      case 0xB:
        v67 = L"iconcache_exif.db";
        if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
          v67 = L"thumbcache_exif.db";
        goto LABEL_125;
      case 0xD:
        v68 = L"iconcache_custom_stream.db";
        v69 = L"thumbcache_custom_stream.db";
        break;
      default:
        v34 = L"iconcache_%d.db";
        if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
          v34 = L"thumbcache_%d.db";
        if ( (_DWORD)v27 == 2 )
        {
          v35 = 48;
        }
        else if ( (_DWORD)v27 == 3 )
        {
          v35 = 96;
        }
        else
        {
          switch ( (int)v27 )
          {
            case 0:
              v35 = 16;
              break;
            case 1:
              v35 = 32;
              break;
            case 4:
            case 9:
              v35 = 256;
              break;
            case 5:
              v35 = 768;
              break;
            case 6:
              v35 = 1280;
              break;
            case 7:
              v35 = 1920;
              break;
            case 8:
              v35 = 2560;
              break;
            default:
              v35 = 0;
              break;
          }
        }
        Error = StringCchPrintfW(pszMore, 0x104u, v34, v35, v87);
        if ( Error < 0 )
          goto LABEL_67;
        v67 = pszMore;
LABEL_125:
        if ( !PathAppendW(pszPath, v67) )
        {
          Error = -2147467259;
          goto LABEL_67;
        }
LABEL_133:
        v70 = 2147483646;
        v71 = pszPath;
        v72 = 260;
        v73 = (WCHAR *)v92;
        do
        {
          if ( !v70 )
            break;
          v74 = *v71;
          if ( !*v71 )
            break;
          ++v71;
          *v73++ = v74;
          --v70;
          --v72;
        }
        while ( v72 );
        Error = -2147024774;
        if ( v72 )
          Error = 0;
        v75 = v73 - 1;
        if ( v72 )
          v75 = v73;
        *v75 = 0;
        if ( !v72 )
          goto LABEL_67;
        v76 = v1;
        if ( (_DWORD)v27 != 9 )
          v76 = 0;
        v77 = (char *)v76 + 16;
        if ( !v76 )
          v77 = 0;
        v78 = (PVOID)*((_QWORD *)v1 + 6);
        v79 = (void *)*((_QWORD *)v1 + v27 + 76);
        Error = -2147024882;
        v80 = (RTL_SRWLOCK *)operator new(0x3D0u, (const struct std::nothrow_t *)&std::nothrow);
        v81 = v80;
        if ( !v80 )
          goto LABEL_66;
        v80->Ptr = &CThumbnailCacheDataFile::`vftable';
        v46 = v80 + 1;
        v80[1].Ptr = 0;
        LOBYTE(v80[2].Ptr) = 0;
        LODWORD(v80[3].Ptr) = 1;
        v80[4].Ptr = 0;
        v80[5].Ptr = 0;
        v80[6].Ptr = 0;
        v80[7].Ptr = 0;
        v80[9].Ptr = 0;
        InitializeSRWLock(v80 + 51);
        v81[52].Ptr = (PVOID)-1LL;
        LODWORD(v81[53].Ptr) = v27;
        v81[119].Ptr = v79;
        InitOnceExecuteOnce(
          &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
          _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
          0,
          0);
        byte_180062B08 = 1;
        (*(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                       + 8LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
        _InterlockedIncrement(&g_fhCache);
        v81[121].Ptr = v77;
        v42 = (WCHAR *)&v81[53].Ptr + 2;
        v82 = 2147483646;
        v83 = (__int16 *)v92;
        v84 = 260;
        v85 = (_WORD *)&v81[53].Ptr + 2;
        do
        {
          if ( !v82 )
            break;
          v86 = *v83;
          if ( !*v83 )
            break;
          ++v83;
          *v85++ = v86;
          --v82;
          --v84;
        }
        while ( v84 );
        Error = -2147024774;
        if ( v84 )
          Error = 0;
        v36 = v85 - 1;
        if ( v84 )
          v36 = v85;
        *v36 = 0;
        if ( !v84 )
        {
LABEL_65:
          (*((void (__fastcall **)(RTL_SRWLOCK *))v81->Ptr + 2))(v81);
LABEL_66:
          v1 = v87;
          v3 = v88;
          goto LABEL_67;
        }
        Error = 0;
        if ( !v46->Ptr )
        {
          v38 = 2147483646;
          v39 = 260;
          v40 = pszPath;
          do
          {
            if ( !v38 )
              break;
            v41 = *v42;
            if ( !*v42 )
              break;
            ++v42;
            *v40++ = v41;
            --v38;
            --v39;
          }
          while ( v39 );
          Error = -2147024774;
          if ( v39 )
            Error = 0;
          v43 = v40 - 1;
          if ( v39 )
            v43 = v40;
          *v43 = 0;
          if ( !v39 )
            goto LABEL_65;
          v44 = lstrlenW(pszPath);
          v45 = 0;
          if ( v44 )
          {
            do
            {
              if ( pszPath[v45] == 92 )
                pszPath[v45] = 58;
              v45 = (unsigned int)(v45 + 1);
            }
            while ( (unsigned int)v45 < v44 );
            v46 = v81 + 1;
          }
          v47 = 260;
          v48 = Name;
          Error = 0;
          v89[0] = L"Global\\";
          v89[1] = pszPath;
          v89[2] = L"!";
          v89[3] = L"dfMaintainer";
          v89[4] = 0;
          v49 = 0;
          while ( 1 )
          {
            if ( Error < 0 )
              goto LABEL_65;
            v50 = (WCHAR *)v89[v49];
            if ( v50 )
            {
              if ( !v47 )
              {
                v58 = 0;
                v59 = 0;
                Error = -2147024809;
LABEL_100:
                if ( Error >= 0 )
                {
                  v48 = v58;
                  v47 = v59;
                }
                goto LABEL_102;
              }
              if ( v47 <= 0x7FFFFFFF )
              {
                v51 = 2147483646;
                v52 = v47;
                v53 = v48;
                v54 = 0;
                do
                {
                  if ( !v51 )
                    break;
                  v55 = *v50;
                  if ( !*v50 )
                    break;
                  ++v50;
                  *v53++ = v55;
                  --v51;
                  ++v54;
                  --v52;
                }
                while ( v52 );
                v56 = v54 - 1;
                if ( v52 )
                  v56 = v54;
                v57 = v53 - 1;
                if ( v52 )
                  v57 = v53;
                *v57 = 0;
                Error = -2147024774;
                if ( v52 )
                  Error = 0;
                v58 = &v48[v56];
                v59 = v47 - v56;
                goto LABEL_100;
              }
              *v48 = 0;
              Error = -2147024809;
            }
LABEL_102:
            if ( (unsigned int)++v49 >= 5 )
            {
              if ( Error < 0 )
                goto LABEL_65;
              MutexWithUserSecurity = CreateMutexWithUserSecurity(Name);
              CAutoHandle<void *>::~CAutoHandle<void *>(v46);
              v46->Ptr = MutexWithUserSecurity;
              if ( !MutexWithUserSecurity )
              {
                Error = ResultFromKnownLastError();
                break;
              }
              goto LABEL_107;
            }
          }
        }
        if ( Error < 0 )
          goto LABEL_65;
LABEL_107:
        if ( v81[4].Ptr != v78 )
        {
          if ( v78 )
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v78 + 8LL))(v78);
          Ptr = v81[4].Ptr;
          v81[4].Ptr = v78;
          if ( Ptr )
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
        }
        v1 = v87;
        v62 = *((_DWORD *)v87 + 17);
        v63 = *((_DWORD *)v87 + 16);
        if ( v63 != v62 )
          goto LABEL_113;
        if ( v62 )
        {
          v65 = 2 * v63;
          if ( (v63 & 0x40000000) != 0 )
          {
LABEL_173:
            Error = -2147024882;
            (*((void (__fastcall **)(RTL_SRWLOCK *))v81->Ptr + 2))(v81);
            v3 = (WCHAR *)((char *)v87 + 72);
            goto LABEL_67;
          }
        }
        else
        {
          v65 = 1;
        }
        if ( v65 <= 0xFFFFFFFuLL )
        {
          v66 = _o__recalloc(*((_QWORD *)v87 + 7), v65, 8);
          if ( v66 )
          {
            *((_DWORD *)v87 + 17) = v65;
            *((_QWORD *)v87 + 7) = v66;
LABEL_113:
            v64 = (RTL_SRWLOCK **)(*((_QWORD *)v87 + 7) + 8LL * *((int *)v87 + 16));
            if ( v64 )
              *v64 = v81;
            ++*((_DWORD *)v87 + 16);
            Error = 0;
            v3 = (WCHAR *)((char *)v87 + 72);
            goto LABEL_67;
          }
        }
        goto LABEL_173;
    }
    if ( (*((_BYTE *)v1 + 768) & 2) == 0 )
      v68 = v69;
    Error = 0;
    if ( !PathAppendW(pszPath, v68) )
      Error = -2147467259;
    if ( Error < 0 )
      goto LABEL_67;
    goto LABEL_133;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180015d40  push    rbp
0x180015d42  push    rbx
0x180015d43  push    rsi
0x180015d44  push    rdi
0x180015d45  push    r12
0x180015d47  push    r13
0x180015d49  push    r14
0x180015d4b  push    r15
0x180015d4d  lea     rbp, [rsp-7B8h]
0x180015d55  sub     rsp, 8B8h
0x180015d5c  mov     rax, cs:__security_cookie
0x180015d63  xor     rax, rsp
0x180015d66  mov     [rbp+7F0h+var_50], rax
0x180015d6d  mov     rsi, rcx
0x180015d70  mov     [rsp+8F0h+var_8D0], rcx
0x180015d75  mov     eax, 7FFFFFFEh
0x180015d7a  lea     rdi, [rcx+48h]
0x180015d7e  mov     [rsp+8F0h+var_8C8], rdi
0x180015d83  mov     r9, rdi
0x180015d86  mov     edx, 104h
0x180015d8b  lea     r8, [rsp+8F0h+pszPath]
0x180015d90  test    rax, rax
0x180015d93  jz      short loc_180015DB3
0x180015d95  movzx   ecx, word ptr [r9]
0x180015d99  test    cx, cx
0x180015d9c  jz      short loc_180015DB3
0x180015d9e  add     r9, 2
0x180015da2  mov     [r8], cx
0x180015da6  add     r8, 2
0x180015daa  dec     rax
0x180015dad  sub     rdx, 1
0x180015db1  jnz     short loc_180015D90
0x180015db3  xor     eax, eax
0x180015db5  mov     r9d, 8007007Ah
0x180015dbb  test    rdx, rdx
0x180015dbe  cmovnz  r9d, eax
0x180015dc2  lea     rcx, [r8-2]
0x180015dc6  cmovnz  rcx, r8
0x180015dca  mov     [rcx], ax
0x180015dcd  jz      loc_1800165C1
0x180015dd3  test    byte ptr [rsi+300h], 2
0x180015dda  lea     rax, pszMore; "thumbcache_idx.db"
0x180015de1  lea     rdx, aIconcacheIdxDb; "iconcache_idx.db"
0x180015de8  cmovz   rdx, rax; pszMore
0x180015dec  lea     rcx, [rsp+8F0h+pszPath]; pszPath
0x180015df1  call    cs:__imp_PathAppendW
0x180015df7  xor     r9d, r9d
0x180015dfa  mov     ecx, 80004005h
0x180015dff  test    eax, eax
0x180015e01  cmovz   r9d, ecx
0x180015e05  jz      loc_1800165C1
0x180015e0b  mov     eax, 7FFFFFFEh
0x180015e10  lea     rcx, [rsp+8F0h+pszPath]
0x180015e15  mov     edx, 104h
0x180015e1a  lea     r8, [rbp+7F0h+pszMore]
0x180015e21  test    rax, rax
0x180015e24  jz      short loc_180015E45
0x180015e26  movzx   r9d, word ptr [rcx]
0x180015e2a  test    r9w, r9w
0x180015e2e  jz      short loc_180015E45
0x180015e30  add     rcx, 2
0x180015e34  mov     [r8], r9w
0x180015e38  add     r8, 2
0x180015e3c  dec     rax
0x180015e3f  sub     rdx, 1
0x180015e43  jnz     short loc_180015E21
0x180015e45  xor     eax, eax
0x180015e47  mov     r9d, 8007007Ah
0x180015e4d  test    rdx, rdx
0x180015e50  cmovnz  r9d, eax
0x180015e54  lea     rcx, [r8-2]
0x180015e58  cmovnz  rcx, r8
0x180015e5c  mov     [rcx], ax
0x180015e5f  jz      loc_1800165C1
0x180015e65  mov     [rsi+30h], rax
0x180015e69  mov     ebx, 8007000Eh
0x180015e6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015e75  mov     ecx, 270h; unsigned __int64
0x180015e7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015e7f  mov     [rsp+8F0h+var_8C0], rax
0x180015e84  test    rax, rax
0x180015e87  jz      loc_180015F12
0x180015e8d  mov     rcx, rax; this
0x180015e90  call    ??0CThumbnailCacheIndex@@AEAA@XZ; CThumbnailCacheIndex::CThumbnailCacheIndex(void)
0x180015e95  mov     rdi, rax
0x180015e98  test    rax, rax
0x180015e9b  jz      short loc_180015F0E
0x180015e9d  mov     ecx, 7FFFFFFEh
0x180015ea2  lea     rdx, [rbp+7F0h+pszMore]
0x180015ea9  mov     r8d, 104h
0x180015eaf  lea     r9, [rax+64h]
0x180015eb3  test    rcx, rcx
0x180015eb6  jz      short loc_180015ED5
0x180015eb8  movzx   eax, word ptr [rdx]
0x180015ebb  test    ax, ax
0x180015ebe  jz      short loc_180015ED5
0x180015ec0  add     rdx, 2
0x180015ec4  mov     [r9], ax
0x180015ec8  add     r9, 2
0x180015ecc  dec     rcx
0x180015ecf  sub     r8, 1
0x180015ed3  jnz     short loc_180015EB3
0x180015ed5  mov     ebx, 8007007Ah
0x180015eda  xor     eax, eax
0x180015edc  test    r8, r8
0x180015edf  cmovnz  ebx, eax
0x180015ee2  lea     rcx, [r9-2]
0x180015ee6  cmovnz  rcx, r9
0x180015eea  mov     [rcx], ax
0x180015eed  jz      loc_1800165C9
0x180015ef3  lea     rcx, [rdi+8]; this
0x180015ef7  lea     rdx, [rdi+64h]; unsigned __int16 *
0x180015efb  call    ?Initialize@CReadersWriterLock@@QEAAJPEBG@Z; CReadersWriterLock::Initialize(ushort const *)
0x180015f00  mov     ebx, eax
0x180015f02  test    eax, eax
0x180015f04  js      loc_1800165C9
0x180015f0a  mov     [rsi+30h], rdi
0x180015f0e  lea     rdi, [rsi+48h]
0x180015f12  test    ebx, ebx
0x180015f14  js      loc_180016082
0x180015f1a  xor     r13d, r13d
0x180015f1d  lea     r14, aThumbcacheWide_0; "thumbcache_wide.db"
0x180015f24  lea     r12, aThumbcacheWide; "thumbcache_wide_alternate.db"
0x180015f2b  lea     r11, aThumbcacheDDb; "thumbcache_%d.db"
0x180015f32  lea     r10, __ImageBase
0x180015f39  lea     r15, ??_7CThumbnailCacheDataFile@@6B@; const CThumbnailCacheDataFile::`vftable'
0x180015f40  test    ebx, ebx
0x180015f42  js      loc_180016082
0x180015f48  mov     ecx, 7FFFFFFEh
0x180015f4d  mov     rdx, rdi
0x180015f50  mov     r8d, 104h
0x180015f56  lea     r9, [rsp+8F0h+pszPath]
0x180015f5b  nop     dword ptr [rax+rax+00h]
0x180015f60  test    rcx, rcx
0x180015f63  jz      short loc_180015F82
0x180015f65  movzx   eax, word ptr [rdx]
0x180015f68  test    ax, ax
0x180015f6b  jz      short loc_180015F82
0x180015f6d  add     rdx, 2
0x180015f71  mov     [r9], ax
0x180015f75  add     r9, 2
0x180015f79  dec     rcx
0x180015f7c  sub     r8, 1
0x180015f80  jnz     short loc_180015F60
0x180015f82  mov     ebx, 8007007Ah
0x180015f87  xor     eax, eax
0x180015f89  test    r8, r8
0x180015f8c  cmovnz  ebx, eax
0x180015f8f  lea     rcx, [r9-2]
0x180015f93  cmovnz  rcx, r9
0x180015f97  mov     [rcx], ax
0x180015f9a  jz      loc_180016060
0x180015fa0  cmp     r13d, 9
0x180015fa4  jz      loc_180016365
0x180015faa  cmp     r13d, 0Ah
0x180015fae  jz      loc_180016549
0x180015fb4  cmp     r13d, 0Ch
0x180015fb8  jz      loc_180016560
0x180015fbe  cmp     r13d, 0Bh
0x180015fc2  jz      loc_18001652B
0x180015fc8  cmp     r13d, 0Dh
0x180015fcc  jz      loc_180016577
0x180015fd2  test    byte ptr [rsi+300h], 2
0x180015fd9  lea     r8, aIconcacheDDb; "iconcache_%d.db"
0x180015fe0  cmovz   r8, r11; unsigned __int16 *
0x180015fe4  cmp     r13d, 2
0x180015fe8  jz      loc_180016324
0x180015fee  cmp     r13d, 3
0x180015ff2  jz      loc_180016520
0x180015ff8  lea     eax, [r13+1]; switch 11 cases
0x180015ffc  cmp     eax, 0Ah
0x180015fff  ja      def_180016012; jumptable 0000000180016012 default case, cases -1,2,3
0x180016005  cdqe
0x180016007  mov     ecx, ds:(jpt_180016012 - 180000000h)[r10+rax*4]
0x18001600f  add     rcx, r10
0x180016012  jmp     rcx; switch jump
0x180016014  mov     r9d, 10h; jumptable 0000000180016012 case 0
0x18001601a  jmp     loc_18001632A
0x18001601f  mov     ebx, 8007007Ah
0x180016024  xor     eax, eax
0x180016026  test    r8, r8
0x180016029  cmovnz  ebx, eax
0x18001602c  lea     rcx, [r9-2]
0x180016030  cmovnz  rcx, r9
0x180016034  mov     [rcx], ax
0x180016037  jnz     short loc_1800160A7
0x180016039  mov     rax, [r14]
0x18001603c  mov     rcx, r14
0x18001603f  mov     rax, [rax+10h]
0x180016043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016048  mov     rsi, [rsp+8F0h+var_8D0]
0x18001604d  mov     rdi, [rsp+8F0h+var_8C8]
0x180016052  lea     r14, aThumbcacheWide_0; "thumbcache_wide.db"
0x180016059  lea     r12, aThumbcacheWide; "thumbcache_wide_alternate.db"
0x180016060  inc     r13d
0x180016063  cmp     r13d, 0Eh
0x180016067  lea     r15, ??_7CThumbnailCacheDataFile@@6B@; const CThumbnailCacheDataFile::`vftable'
0x18001606e  lea     r10, __ImageBase
0x180016075  lea     r11, aThumbcacheDDb; "thumbcache_%d.db"
0x18001607c  jl      loc_180015F40
0x180016082  mov     eax, ebx
0x180016084  mov     rcx, [rbp+7F0h+var_50]
0x18001608b  xor     rcx, rsp; StackCookie
0x18001608e  call    __security_check_cookie
0x180016093  add     rsp, 8B8h
0x18001609a  pop     r15
0x18001609c  pop     r14
0x18001609e  pop     r13
0x1800160a0  pop     r12
0x1800160a2  pop     rdi
0x1800160a3  pop     rsi
0x1800160a4  pop     rbx
0x1800160a5  pop     rbp
0x1800160a6  retn
0x1800160a7  xor     ebx, ebx
0x1800160a9  cmp     [r15], rax
0x1800160ac  jnz     loc_180016266
0x1800160b2  mov     ecx, 7FFFFFFEh
0x1800160b7  mov     edx, 104h
0x1800160bc  lea     r8, [rsp+8F0h+pszPath]
0x1800160c1  test    rcx, rcx
0x1800160c4  jz      short loc_1800160E4
0x1800160c6  movzx   eax, word ptr [r10]
0x1800160ca  test    ax, ax
0x1800160cd  jz      short loc_1800160E4
0x1800160cf  add     r10, 2
0x1800160d3  mov     [r8], ax
0x1800160d7  add     r8, 2
0x1800160db  dec     rcx
0x1800160de  sub     rdx, 1
0x1800160e2  jnz     short loc_1800160C1
0x1800160e4  mov     ebx, 8007007Ah
0x1800160e9  xor     eax, eax
0x1800160eb  test    rdx, rdx
0x1800160ee  cmovnz  ebx, eax
0x1800160f1  lea     rcx, [r8-2]
0x1800160f5  cmovnz  rcx, r8
0x1800160f9  mov     [rcx], ax
0x1800160fc  jz      loc_180016039
0x180016102  lea     rcx, [rsp+8F0h+pszPath]; lpString
0x180016107  call    cs:__imp_lstrlenW
0x18001610d  xor     edx, edx
0x18001610f  test    eax, eax
0x180016111  jz      short loc_180016136
0x180016113  mov     r15d, 3Ah ; ':'
0x180016119  nop     dword ptr [rax+00000000h]
0x180016120  cmp     [rsp+rdx*2+8F0h+pszPath], 5Ch ; '\'
0x180016126  jz      loc_180016254
0x18001612c  inc     edx
0x18001612e  cmp     edx, eax
0x180016130  jb      short loc_180016120
0x180016132  lea     r15, [r14+8]
0x180016136  mov     edi, 104h
0x18001613b  lea     rsi, [rbp+7F0h+Name]
0x180016142  xor     ebx, ebx
0x180016144  lea     rax, aGlobal; "Global\\"
0x18001614b  mov     [rsp+8F0h+var_8B8], rax
0x180016150  lea     rax, [rsp+8F0h+pszPath]
0x180016155  mov     [rsp+8F0h+var_8B0], rax
0x18001615a  lea     rax, asc_18004E6B0; "!"
0x180016161  mov     [rsp+8F0h+var_8A8], rax
0x180016166  lea     rax, aDfmaintainer; "dfMaintainer"
0x18001616d  mov     [rsp+8F0h+var_8A0], rax
0x180016172  mov     [rsp+8F0h+var_898], rbx
0x180016177  xor     r11d, r11d
0x18001617a  nop     word ptr [rax+rax+00h]
0x180016180  test    ebx, ebx
0x180016182  js      loc_180016039
0x180016188  movsxd  rax, r11d
0x18001618b  mov     rcx, [rsp+rax*8+8F0h+var_8B8]
0x180016190  test    rcx, rcx
0x180016193  jz      loc_18001621C
0x180016199  test    rdi, rdi
0x18001619c  jz      loc_1800165FF
0x1800161a2  cmp     rdi, 7FFFFFFFh
0x1800161a9  ja      loc_1800165F0
0x1800161af  mov     edx, 7FFFFFFEh
0x1800161b4  mov     r8, rdi
0x1800161b7  mov     r9, rsi
0x1800161ba  xor     r10d, r10d
0x1800161bd  nop     dword ptr [rax]
0x1800161c0  test    rdx, rdx
0x1800161c3  jz      short loc_1800161E5
0x1800161c5  movzx   eax, word ptr [rcx]
0x1800161c8  test    ax, ax
0x1800161cb  jz      short loc_1800161E5
0x1800161cd  add     rcx, 2
0x1800161d1  mov     [r9], ax
0x1800161d5  add     r9, 2
0x1800161d9  dec     rdx
0x1800161dc  inc     r10
0x1800161df  sub     r8, 1
0x1800161e3  jnz     short loc_1800161C0
0x1800161e5  lea     rdx, [r10-1]
0x1800161e9  test    r8, r8
0x1800161ec  cmovnz  rdx, r10
0x1800161f0  lea     rcx, [r9-2]
0x1800161f4  cmovnz  rcx, r9
0x1800161f8  xor     eax, eax
0x1800161fa  mov     [rcx], ax
  ... truncated ...
```
