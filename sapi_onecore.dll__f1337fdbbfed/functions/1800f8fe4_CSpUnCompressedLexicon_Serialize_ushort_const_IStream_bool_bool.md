# CSpUnCompressedLexicon::Serialize(ushort const *,IStream *,bool,bool)

- ea: `0x1800f8fe4`
- end: `0x1800f9893`
- name: `?Serialize@CSpUnCompressedLexicon@@AEAAJPEBGPEAUIStream@@_N2@Z`
- size: `2223`
- prototype: `__int64 __usercall@<rax>(CSpUnCompressedLexicon *__hidden this@<rcx>, LPCWSTR lpNewFileName@<rdx>, struct IStream *@<r8>, bool@<r9b>, bool)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800f55a8`
- `0x1800f66d4`
- `0x1800f8e50`
- `0x1800f8f20`

## callees

- `0x180013ec0`
- `0x18001d5a0`
- `0x18001f5dc`
- `0x180045938`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007d7b1`
- `0x1800f5804`
- `0x1800f5ef0`
- `0x1800f7ef4`
- `0x1800f8fe4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f970a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f979d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f970a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f979d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f97cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f97cf`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f90e1`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f90e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f9123`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f9123`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f977b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f977b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f90b2`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f90b2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800f97b5`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800f97b5`

## string_xrefs

- `0x1800f9141`: `Failed to create temp file %S, hr = 0x%.8X`
- `0x1800f97e5`: `Cannot delete temp file %S, hr = 0x%.8X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpUnCompressedLexicon::Serialize(
        CSpUnCompressedLexicon *this,
        LPCWSTR lpNewFileName,
        struct IStream *a3,
        char a4,
        bool a5)
{
  struct IStream *v5; // rbx
  const WCHAR *v6; // rdi
  unsigned int v8; // r8d
  int Win32Error; // r14d
  __int64 v10; // rax
  char v11; // r15
  char v12; // r13
  __int64 FileW; // r12
  __int64 v14; // rax
  char *v15; // rbx
  __int64 v17; // r13
  unsigned __int64 v18; // rax
  _DWORD *v19; // r8
  int v20; // ecx
  __int64 v21; // r13
  __int64 v22; // rcx
  __int64 v23; // r15
  __int64 v24; // r14
  unsigned int v25; // r12d
  unsigned int v26; // edx
  unsigned __int16 *v27; // r13
  int v28; // r14d
  DWORD v29; // r15d
  char *v30; // r12
  __int64 v31; // rdi
  __int64 v32; // rax
  DWORD v33; // r14d
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // eax
  unsigned int v37; // ecx
  int v38; // edx
  __int64 v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // rcx
  unsigned int v42; // edi
  __int64 v43; // rax
  unsigned int *v44; // rdx
  __int64 v45; // rax
  unsigned int v46; // edi
  __int64 v47; // r15
  int v48; // r13d
  double v49; // xmm1_8
  unsigned int v50; // r8d
  unsigned int v51; // ebx
  int v52; // r15d
  __int64 v53; // r13
  char *v54; // rdi
  int v55; // r10d
  unsigned int v56; // edx
  unsigned int v57; // r9d
  __int64 v58; // r8
  DWORD v59; // edi
  __int64 v60; // rcx
  DWORD v61; // r8d
  unsigned int v62; // r10d
  _DWORD *v63; // rbx
  __int64 v64; // rdx
  unsigned int v65; // r9d
  __int64 v66; // rax
  int v67; // r11d
  unsigned int v68; // edx
  __int64 v69; // r9
  __int64 j; // rcx
  const void *v71; // rdx
  __int64 v72; // r8
  int v73; // eax
  char v74; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  char v76; // [rsp+48h] [rbp-B8h]
  char v77; // [rsp+49h] [rbp-B7h]
  unsigned int i; // [rsp+4Ch] [rbp-B4h] BYREF
  char *v79; // [rsp+50h] [rbp-B0h]
  _DWORD *v80; // [rsp+58h] [rbp-A8h]
  int v81; // [rsp+60h] [rbp-A0h]
  int v82; // [rsp+64h] [rbp-9Ch]
  __int64 v83; // [rsp+68h] [rbp-98h]
  LPCWSTR v84; // [rsp+70h] [rbp-90h]
  __int64 v85; // [rsp+78h] [rbp-88h] BYREF
  __int64 v86; // [rsp+80h] [rbp-80h]
  __int64 v87; // [rsp+88h] [rbp-78h]
  __int64 v88; // [rsp+90h] [rbp-70h]
  __int64 v89; // [rsp+A0h] [rbp-60h]
  struct IStream *v90; // [rsp+A8h] [rbp-58h]
  _BYTE v91[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR TempFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR PathName[8]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v77 = a4;
  v5 = a3;
  v90 = a3;
  v6 = lpNewFileName;
  v84 = lpNewFileName;
  DoTraceMessage(16, "Begin serializing lexicon (GenId = %u) to file...", *(_DWORD *)(*((_QWORD *)this + 11) + 132LL));
  if ( !v6 )
  {
    if ( v5 )
      goto LABEL_3;
    return 2147942487LL;
  }
  if ( v5 )
    return 2147942487LL;
LABEL_3:
  v85 = 0;
  Win32Error = CSpAutoMutexLock::Init((CSpAutoMutexLock *)&v85, *((void **)this + 77), v8);
  if ( Win32Error >= 0 )
  {
    v10 = *((_QWORD *)this + 11);
    v11 = *(_BYTE *)(v10 + 128);
    v74 = v11;
    v12 = *(_BYTE *)(v10 + 129);
    v76 = v12;
    FileW = -1;
    if ( v6 )
    {
      if ( !(unsigned int)GetTempPath2W(260, PathName) )
      {
        Win32Error = SpHrFromLastWin32Error();
        if ( Win32Error < 0 )
          goto LABEL_84;
      }
      if ( !GetTempFileNameW(PathName, L"LEX", 0, TempFileName) )
      {
        Win32Error = SpHrFromLastWin32Error();
        if ( Win32Error < 0 )
          goto LABEL_84;
      }
      FileW = (__int64)CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      if ( FileW == -1 )
      {
        Win32Error = SpHrFromLastWin32Error();
        DoTraceMessage(2, "Failed to create temp file %S, hr = 0x%.8X", TempFileName, Win32Error);
        if ( Win32Error < 0 )
          goto LABEL_84;
      }
    }
    v14 = *((_QWORD *)this + 11);
    if ( *(_BYTE *)(v14 + 128) && !a5 )
    {
      v15 = (char *)operator new[](*(unsigned int *)(v14 + 120), (const struct std::nothrow_t *)&std::nothrow);
      v79 = v15;
      if ( !v15 )
      {
        Win32Error = -2147024882;
LABEL_84:
        if ( FileW != -1 )
          CloseHandle((HANDLE)FileW);
        *(_BYTE *)(*((_QWORD *)this + 11) + 128LL) = v11;
        *(_BYTE *)(*((_QWORD *)this + 11) + 129LL) = v12;
        goto LABEL_105;
      }
      v83 = FileW;
      v17 = *((_QWORD *)this + 79);
      v18 = 4LL * *(unsigned int *)(*((_QWORD *)this + 11) + 116LL);
      if ( !is_mul_ok(*(unsigned int *)(*((_QWORD *)this + 11) + 116LL), 4u) )
        v18 = -1;
      v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      v80 = v19;
      v20 = Win32Error;
      if ( !v19 )
        v20 = -2147024882;
      Win32Error = v20;
      v82 = v20;
      if ( v20 >= 0 )
      {
        v21 = v17 + 140;
        v89 = v21;
        NumberOfBytesWritten = 0;
        v81 = 0;
        v22 = 0;
        v87 = 0;
        v23 = 0;
        v88 = 0;
        do
        {
          if ( *(_WORD *)(v23 + v21) )
          {
            v24 = *((_QWORD *)this + 79) + *(unsigned int *)(v23 + v21 + 4);
            v86 = v24;
            v25 = 0;
            for ( i = 0; v25 < *(_DWORD *)(v23 + v21 + 8); i = v25 )
            {
              v26 = *(_DWORD *)(v24 + 4LL * v25);
              if ( v26 )
              {
                v27 = (unsigned __int16 *)(16 * v22 + v21);
                v28 = v81;
                v29 = NumberOfBytesWritten;
                v30 = v79;
                do
                {
                  v19[v28++] = v26;
                  v31 = v26;
                  memcpy_0(
                    &v30[v29],
                    (const void *)(v26 + *((_QWORD *)this + 79)),
                    *(unsigned int *)(v26 + *((_QWORD *)this + 79)));
                  *(_DWORD *)&v30[v29 + 4] = *v27;
                  v32 = *((_QWORD *)this + 79);
                  v29 += *(_DWORD *)(v32 + v31);
                  v26 = *(_DWORD *)(v32 + v31 + 4);
                  v19 = v80;
                }
                while ( v26 );
                NumberOfBytesWritten = v29;
                v81 = v28;
                v23 = v88;
                v21 = v89;
                v25 = i;
                v22 = v87;
                v24 = v86;
              }
              ++v25;
            }
          }
          v87 = ++v22;
          v23 += 16;
          v88 = v23;
        }
        while ( v22 != 25 );
        v33 = NumberOfBytesWritten;
        i = NumberOfBytesWritten;
        memset(v91, 0, 25);
        v34 = *((_QWORD *)this + 11);
        v35 = *(unsigned __int16 *)(v34 + 138);
        FileW = v83;
        if ( (_WORD)v35 )
        {
          v36 = *(unsigned __int16 *)(v34 + 136);
          v37 = 24;
          if ( (_WORD)v36 )
            v37 = v36 - 1;
          v38 = v35 - 1;
          if ( (int)v35 - 1 >= 0 )
          {
            v39 = *((_QWORD *)this + 81);
            do
            {
              v40 = *(_OWORD *)(v39 + 16LL * v37--);
              *(_OWORD *)&PathName[8 * v38] = v40;
              if ( v37 == -1 )
                v37 = 24;
              --v38;
            }
            while ( v38 >= 0 );
            v83 = FileW;
          }
          memcpy_0(*((void **)this + 81), PathName, 16 * v35);
          *(_WORD *)(*((_QWORD *)this + 11) + 136LL) = *(_WORD *)(*((_QWORD *)this + 11) + 138LL);
          v41 = *((_QWORD *)this + 11);
          if ( *(_WORD *)(v41 + 136) == 25 )
            *(_WORD *)(v41 + 136) = 0;
          v42 = 0;
          v34 = *((_QWORD *)this + 11);
          if ( *(_WORD *)(v34 + 138) )
          {
            do
            {
              v43 = *((_QWORD *)this + 81);
              if ( *(_BYTE *)(v43 + 16LL * v42 + 8) != 1 )
              {
                v44 = (unsigned int *)(*((_QWORD *)this + 79) + *(unsigned int *)(v43 + 16LL * v42 + 4));
                memcpy_0(&v79[v33], v44, *v44);
                v33 += *(_DWORD *)(*(unsigned int *)(*((_QWORD *)this + 81) + 16LL * v42 + 4) + *((_QWORD *)this + 79));
              }
              ++v42;
              v34 = *((_QWORD *)this + 11);
            }
            while ( v42 < *(unsigned __int16 *)(v34 + 138) );
            NumberOfBytesWritten = v33;
            FileW = v83;
          }
        }
        *(_DWORD *)(v34 + 120) = 140;
        *(_DWORD *)(*((_QWORD *)this + 11) + 120LL) += 800;
        *(_DWORD *)(*((_QWORD *)this + 11) + 124LL) = 0;
        *(_BYTE *)(*((_QWORD *)this + 11) + 128LL) = 0;
        v45 = *((_QWORD *)this + 79);
        v86 = v45;
        v46 = 0;
        Win32Error = v82;
        while ( *(_WORD *)(v45 + 16LL * v46 + 140) )
        {
          v47 = *((_QWORD *)this + 79);
          v48 = *(_DWORD *)(v47 + 16LL * v46 + 152);
          v49 = (double)v48 * 1.5;
          if ( v49 <= (double)*(int *)(v47 + 16LL * v46 + 148) )
            v50 = 50;
          else
            v50 = (int)v49;
          Win32Error = CSpUnCompressedLexicon::AllocateHashTable(this, v46, v50);
          if ( Win32Error < 0 )
            goto LABEL_78;
          *(_DWORD *)(v47 + 16LL * v46++ + 152) = v48;
          v45 = v86;
          if ( v46 >= 0x19 )
            break;
        }
        v51 = 0;
        v52 = 0;
        v53 = i;
        if ( i )
        {
          while ( 1 )
          {
            v54 = &v79[v51];
            i = 0;
            Win32Error = CSpUnCompressedLexicon::AddDictNode(this, *((_WORD *)v54 + 2), (struct tagdictnode *)v54, &i);
            if ( Win32Error < 0 )
              break;
            v55 = v80[v52++];
            v56 = 0;
            if ( *(_WORD *)(*((_QWORD *)this + 11) + 138LL) )
            {
              v57 = i;
              do
              {
                v58 = *((_QWORD *)this + 81);
                if ( *(_DWORD *)(v58 + 16LL * v56 + 4) == v55 && !v91[v56] )
                {
                  *(_DWORD *)(v58 + 16LL * v56 + 4) = v57;
                  v91[v56] = 1;
                }
                ++v56;
              }
              while ( v56 < *(unsigned __int16 *)(*((_QWORD *)this + 11) + 138LL) );
            }
            v51 += *(_DWORD *)v54;
            if ( v51 >= (unsigned int)v53 )
              goto LABEL_63;
          }
LABEL_78:
          v15 = v79;
          goto LABEL_79;
        }
LABEL_63:
        v59 = NumberOfBytesWritten;
        v15 = v79;
        memcpy_0(
          (void *)(*((_QWORD *)this + 79) + *(unsigned int *)(*((_QWORD *)this + 11) + 120LL)),
          &v79[v53],
          NumberOfBytesWritten - (unsigned int)v53);
        v60 = *((_QWORD *)this + 11);
        v61 = *(_DWORD *)(v60 + 120);
        if ( v61 < NumberOfBytesWritten + v61 - (_DWORD)v53 )
        {
          v62 = 0;
          do
          {
            v63 = (_DWORD *)(*((_QWORD *)this + 79) + v61);
            v64 = v62;
            v65 = *(unsigned __int16 *)(v60 + 138);
            if ( v62 < v65 )
            {
              do
              {
                if ( !*(_BYTE *)(*((_QWORD *)this + 81) + 16LL * (unsigned int)v64 + 8) )
                  break;
                v64 = (unsigned int)(v64 + 1);
              }
              while ( (unsigned int)v64 < v65 );
            }
            v62 = v64 + 1;
            v60 = *((_QWORD *)this + 11);
            if ( (unsigned int)v64 < v65 && (unsigned int)v64 < 0x19 )
            {
              v66 = *((_QWORD *)this + 81);
              v67 = *(_DWORD *)(v66 + 16 * v64 + 4);
              *(_DWORD *)(v66 + 16 * v64 + 4) = v61;
              v91[v64] = 1;
              v68 = 0;
              v60 = *((_QWORD *)this + 11);
              if ( *(_WORD *)(v60 + 138) )
              {
                do
                {
                  v69 = *((_QWORD *)this + 81);
                  if ( *(_DWORD *)(v69 + 16LL * v68 + 4) == v67 && !v91[v68] )
                  {
                    *(_DWORD *)(v69 + 16LL * v68 + 4) = v61;
                    v91[v68] = 1;
                  }
                  ++v68;
                  v60 = *((_QWORD *)this + 11);
                }
                while ( v68 < *(unsigned __int16 *)(v60 + 138) );
              }
            }
            v61 += *v63;
          }
          while ( v61 < v59 + *(_DWORD *)(v60 + 120) - (_DWORD)v53 );
          v15 = v79;
        }
        *(_DWORD *)(v60 + 120) = v61;
LABEL_79:
        v19 = v80;
        v6 = v84;
        v11 = v74;
      }
      if ( v19 )
        operator delete(v19);
      operator delete(v15);
      if ( Win32Error < 0 )
      {
        v12 = v76;
        goto LABEL_84;
      }
      v5 = v90;
    }
    NumberOfBytesWritten = 0;
    if ( v77 )
    {
      for ( j = 0; j != 2; ++j )
        *(_BYTE *)(j + *((_QWORD *)this + 11) + 128) = 0;
    }
    v71 = (const void *)*((_QWORD *)this + 79);
    v72 = *(unsigned int *)(*((_QWORD *)this + 11) + 120LL);
    if ( v6 )
    {
      if ( !WriteFile((HANDLE)FileW, v71, v72, &NumberOfBytesWritten, 0)
        || NumberOfBytesWritten != *(_DWORD *)(*((_QWORD *)this + 11) + 120LL) )
      {
        Win32Error = SpHrFromLastWin32Error();
      }
      CloseHandle((HANDLE)FileW);
      if ( Win32Error < 0
        || !MoveFileExW(TempFileName, v6, 3u) && (Win32Error = SpHrFromLastWin32Error(), Win32Error < 0) )
      {
        if ( !DeleteFileW(TempFileName) )
        {
          v73 = SpHrFromLastWin32Error();
          DoTraceMessage(4, "Cannot delete temp file %S, hr = 0x%.8X", TempFileName, v73);
        }
        goto LABEL_105;
      }
    }
    else
    {
      Win32Error = (*(__int64 (__fastcall **)(struct IStream *, const void *, __int64, DWORD *))(*(_QWORD *)v5 + 32LL))(
                     v5,
                     v71,
                     v72,
                     &NumberOfBytesWritten);
      if ( Win32Error < 0 )
      {
LABEL_105:
        DoTraceMessage(2, "Failed to serialize lexicon, hr = 0x%.8X", Win32Error);
        goto LABEL_106;
      }
      if ( NumberOfBytesWritten != *(_DWORD *)(*((_QWORD *)this + 11) + 120LL) )
      {
        Win32Error = -2147418113;
        goto LABEL_105;
      }
    }
    Win32Error = CSpUnCompressedLexicon::NotifyLexFileUpdate(this);
    DoTraceMessage(16, "Finished serializing lexicon to file");
    if ( Win32Error < 0 )
      goto LABEL_105;
  }
LABEL_106:
  CSpAutoMutexLock::~CSpAutoMutexLock((CSpAutoMutexLock *)&v85);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800f8fe4  mov     [rsp-8+arg_18], rbx
0x1800f8fe9  push    rbp
0x1800f8fea  push    rsi
0x1800f8feb  push    rdi
0x1800f8fec  push    r12
0x1800f8fee  push    r13
0x1800f8ff0  push    r14
0x1800f8ff2  push    r15
0x1800f8ff4  lea     rbp, [rsp-400h]
0x1800f8ffc  sub     rsp, 500h
0x1800f9003  mov     rax, cs:__security_cookie
0x1800f900a  xor     rax, rsp
0x1800f900d  mov     [rbp+430h+var_40], rax
0x1800f9014  mov     [rsp+530h+var_4E7], r9b
0x1800f9019  mov     rbx, r8
0x1800f901c  mov     [rbp+430h+var_488], rbx
0x1800f9020  mov     rdi, rdx
0x1800f9023  mov     [rsp+530h+var_4C0], rdx
0x1800f9028  mov     rsi, rcx
0x1800f902b  mov     r8, [rcx+58h]
0x1800f902f  mov     r8d, [r8+84h]
0x1800f9036  lea     rdx, aBeginSerializi; "Begin serializing lexicon (GenId = %u) "...
0x1800f903d  mov     ecx, 10h; int
0x1800f9042  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f9047  xor     r15d, r15d
0x1800f904a  test    rdi, rdi
0x1800f904d  jnz     loc_1800F91A0
0x1800f9053  test    rbx, rbx
0x1800f9056  jz      loc_1800F91A9
0x1800f905c  mov     [rsp+530h+var_4B8], r15
0x1800f9061  mov     rdx, [rsi+268h]; void *
0x1800f9068  lea     rcx, [rsp+530h+var_4B8]; this
0x1800f906d  call    ?Init@CSpAutoMutexLock@@QEAAJPEAXK@Z; CSpAutoMutexLock::Init(void *,ulong)
0x1800f9072  mov     r14d, eax
0x1800f9075  test    eax, eax
0x1800f9077  js      loc_1800F985C
0x1800f907d  mov     rax, [rsi+58h]
0x1800f9081  mov     r15b, [rax+80h]
0x1800f9088  mov     [rsp+530h+var_4F0], r15b
0x1800f908d  mov     r13b, [rax+81h]
0x1800f9094  mov     [rsp+530h+var_4E8], r13b
0x1800f9099  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800f909d  test    rdi, rdi
0x1800f90a0  jz      loc_1800F915B
0x1800f90a6  lea     rdx, [rbp+430h+PathName]
0x1800f90ad  mov     ecx, 104h
0x1800f90b2  call    cs:__imp_GetTempPath2W
0x1800f90b8  test    eax, eax
0x1800f90ba  jnz     short loc_1800F90CC
0x1800f90bc  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f90c1  mov     r14d, eax
0x1800f90c4  test    eax, eax
0x1800f90c6  js      loc_1800F9701
0x1800f90cc  lea     r9, [rbp+430h+TempFileName]; lpTempFileName
0x1800f90d0  xor     r8d, r8d; uUnique
0x1800f90d3  lea     rdx, PrefixString; "LEX"
0x1800f90da  lea     rcx, [rbp+430h+PathName]; lpPathName
0x1800f90e1  call    cs:__imp_GetTempFileNameW
0x1800f90e7  test    eax, eax
0x1800f90e9  jnz     short loc_1800F90FB
0x1800f90eb  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f90f0  mov     r14d, eax
0x1800f90f3  test    eax, eax
0x1800f90f5  js      loc_1800F9701
0x1800f90fb  mov     [rsp+530h+hTemplateFile], 0; hTemplateFile
0x1800f9104  mov     [rsp+530h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f910c  mov     [rsp+530h+dwCreationDisposition], 2; dwCreationDisposition
0x1800f9114  xor     r9d, r9d; lpSecurityAttributes
0x1800f9117  xor     r8d, r8d; dwShareMode
0x1800f911a  mov     edx, 40000000h; dwDesiredAccess
0x1800f911f  lea     rcx, [rbp+430h+TempFileName]; lpFileName
0x1800f9123  call    cs:__imp_CreateFileW
0x1800f9129  mov     r12, rax
0x1800f912c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f9130  jnz     short loc_1800F915B
0x1800f9132  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f9137  mov     r14d, eax
0x1800f913a  mov     r9d, eax
0x1800f913d  lea     r8, [rbp+430h+TempFileName]
0x1800f9141  lea     rdx, aFailedToCreate_5; "Failed to create temp file %S, hr = 0x%"...
0x1800f9148  lea     ecx, [r12+3]; int
0x1800f914d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f9152  test    r14d, r14d
0x1800f9155  js      loc_1800F9701
0x1800f915b  mov     rax, [rsi+58h]
0x1800f915f  cmp     byte ptr [rax+80h], 0
0x1800f9166  jz      loc_1800F972F
0x1800f916c  cmp     [rbp+430h+arg_20], 0
0x1800f9173  jnz     loc_1800F972F
0x1800f9179  mov     ecx, [rax+78h]; unsigned __int64
0x1800f917c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f9183  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f9188  mov     rbx, rax
0x1800f918b  mov     [rsp+530h+var_4E0], rax
0x1800f9190  test    rax, rax
0x1800f9193  jnz     short loc_1800F91B3
0x1800f9195  mov     r14d, 8007000Eh
0x1800f919b  jmp     loc_1800F9701
0x1800f91a0  test    rbx, rbx
0x1800f91a3  jz      loc_1800F905C
0x1800f91a9  mov     eax, 80070057h
0x1800f91ae  jmp     loc_1800F9869
0x1800f91b3  mov     [rsp+530h+var_4C8], r12
0x1800f91b8  mov     r13, [rsi+278h]
0x1800f91bf  mov     rax, [rsi+58h]
0x1800f91c3  mov     ecx, [rax+74h]
0x1800f91c6  mov     eax, 4
0x1800f91cb  mul     rcx
0x1800f91ce  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f91d5  cmovb   rax, rcx
0x1800f91d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f91e0  mov     rcx, rax; unsigned __int64
0x1800f91e3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f91e8  mov     r8, rax
0x1800f91eb  mov     [rsp+530h+var_4D8], rax
0x1800f91f0  mov     ecx, r14d
0x1800f91f3  mov     r14d, 8007000Eh
0x1800f91f9  xor     r11d, r11d
0x1800f91fc  test    rax, rax
0x1800f91ff  cmovz   ecx, r14d
0x1800f9203  mov     r14d, ecx
0x1800f9206  mov     [rsp+530h+var_4CC], ecx
0x1800f920a  test    ecx, ecx
0x1800f920c  js      loc_1800F96E2
0x1800f9212  add     r13, 8Ch
0x1800f9219  mov     [rbp+430h+var_490], r13
0x1800f921d  mov     [rsp+530h+NumberOfBytesWritten], r11d
0x1800f9222  mov     [rsp+530h+var_4D0], r11d
0x1800f9227  mov     ecx, r11d
0x1800f922a  mov     [rbp+430h+var_4A8], rcx
0x1800f922e  mov     r15d, r11d
0x1800f9231  mov     [rbp+430h+var_4A0], r11
0x1800f9235  lea     edi, [r11+19h]
0x1800f9239  cmp     r11w, [r15+r13]
0x1800f923e  jz      loc_1800F9310
0x1800f9244  mov     r14d, [r15+r13+4]
0x1800f9249  add     r14, [rsi+278h]
0x1800f9250  mov     [rbp+430h+var_4B0], r14
0x1800f9254  mov     r12d, r11d
0x1800f9257  mov     [rsp+530h+var_4E4], r11d
0x1800f925c  cmp     [r15+r13+8], r11d
0x1800f9261  jbe     loc_1800F9310
0x1800f9267  mov     eax, r12d
0x1800f926a  mov     edx, [r14+rax*4]
0x1800f926e  test    edx, edx
0x1800f9270  jz      loc_1800F92F8
0x1800f9276  mov     rax, rcx
0x1800f9279  shl     rax, 4
0x1800f927d  add     r13, rax
0x1800f9280  mov     r14d, [rsp+530h+var_4D0]
0x1800f9285  mov     r15d, [rsp+530h+NumberOfBytesWritten]
0x1800f928a  mov     r12, [rsp+530h+var_4E0]
0x1800f928f  mov     eax, r14d
0x1800f9292  mov     [r8+rax*4], edx
0x1800f9296  inc     r14d
0x1800f9299  mov     edi, edx
0x1800f929b  mov     rdx, [rsi+278h]
0x1800f92a2  add     rdx, rdi; Src
0x1800f92a5  mov     ebx, r15d
0x1800f92a8  add     rbx, r12
0x1800f92ab  mov     r8d, [rdx]; Size
0x1800f92ae  mov     rcx, rbx; void *
0x1800f92b1  call    memcpy_0
0x1800f92b6  movzx   eax, word ptr [r13+0]
0x1800f92bb  mov     [rbx+4], eax
0x1800f92be  mov     rax, [rsi+278h]
0x1800f92c5  add     r15d, [rax+rdi]
0x1800f92c9  mov     edx, [rax+rdi+4]
0x1800f92cd  xor     r11d, r11d
0x1800f92d0  test    edx, edx
0x1800f92d2  mov     r8, [rsp+530h+var_4D8]
0x1800f92d7  jnz     short loc_1800F928F
0x1800f92d9  mov     [rsp+530h+NumberOfBytesWritten], r15d
0x1800f92de  mov     [rsp+530h+var_4D0], r14d
0x1800f92e3  mov     r15, [rbp+430h+var_4A0]
0x1800f92e7  mov     r13, [rbp+430h+var_490]
0x1800f92eb  mov     r12d, [rsp+530h+var_4E4]
0x1800f92f0  mov     rcx, [rbp+430h+var_4A8]
0x1800f92f4  mov     r14, [rbp+430h+var_4B0]
0x1800f92f8  inc     r12d
0x1800f92fb  mov     [rsp+530h+var_4E4], r12d
0x1800f9300  cmp     r12d, [r15+r13+8]
0x1800f9305  jb      loc_1800F9267
0x1800f930b  mov     edi, 19h
0x1800f9310  inc     rcx
0x1800f9313  mov     [rbp+430h+var_4A8], rcx
0x1800f9317  add     r15, 10h
0x1800f931b  mov     [rbp+430h+var_4A0], r15
0x1800f931f  cmp     rcx, rdi
0x1800f9322  jnz     loc_1800F9239
0x1800f9328  mov     r14d, [rsp+530h+NumberOfBytesWritten]
0x1800f932d  mov     [rsp+530h+var_4E4], r14d
0x1800f9332  xorps   xmm0, xmm0
0x1800f9335  movups  xmmword ptr [rbp+430h+var_480], xmm0
0x1800f9339  movups  xmmword ptr [rbp+430h+var_480+9], xmm0
0x1800f933d  mov     rcx, [rsi+58h]
0x1800f9341  movzx   r8d, word ptr [rcx+8Ah]
0x1800f9349  test    r8w, r8w
0x1800f934d  mov     r12, [rsp+530h+var_4C8]
0x1800f9352  jz      loc_1800F9462
0x1800f9358  movzx   eax, word ptr [rcx+88h]
0x1800f935f  mov     r10d, 18h
0x1800f9365  test    ax, ax
0x1800f9368  mov     ecx, r10d
0x1800f936b  jz      short loc_1800F9370
0x1800f936d  lea     ecx, [rax-1]
0x1800f9370  mov     edx, r8d
0x1800f9373  sub     edx, 1
0x1800f9376  js      short loc_1800F93AB
0x1800f9378  mov     r9, [rsi+288h]
0x1800f937f  or      ebx, 0FFFFFFFFh
0x1800f9382  mov     eax, ecx
0x1800f9384  add     rax, rax
0x1800f9387  movups  xmm0, xmmword ptr [r9+rax*8]
0x1800f938c  dec     ecx
0x1800f938e  mov     eax, edx
0x1800f9390  add     rax, rax
0x1800f9393  movdqu  xmmword ptr [rbp+rax*8+430h+PathName], xmm0
0x1800f939c  cmp     ecx, ebx
0x1800f939e  cmovz   ecx, r10d
0x1800f93a2  add     edx, ebx
0x1800f93a4  jns     short loc_1800F9382
0x1800f93a6  mov     [rsp+530h+var_4C8], r12
0x1800f93ab  shl     r8, 4; Size
0x1800f93af  lea     rdx, [rbp+430h+PathName]; Src
0x1800f93b6  mov     rcx, [rsi+288h]; void *
0x1800f93bd  call    memcpy_0
0x1800f93c2  mov     rcx, [rsi+58h]
0x1800f93c6  movzx   eax, word ptr [rcx+8Ah]
0x1800f93cd  mov     [rcx+88h], ax
0x1800f93d4  mov     rcx, [rsi+58h]
0x1800f93d8  xor     r11d, r11d
0x1800f93db  cmp     [rcx+88h], di
0x1800f93e2  jnz     short loc_1800F93EC
0x1800f93e4  mov     [rcx+88h], r11w
0x1800f93ec  mov     edi, r11d
0x1800f93ef  mov     rcx, [rsi+58h]
0x1800f93f3  cmp     r11w, [rcx+8Ah]
0x1800f93fb  jnb     short loc_1800F9462
0x1800f93fd  mov     r12, [rsp+530h+var_4E0]
0x1800f9402  mov     ebx, edi
0x1800f9404  add     rbx, rbx
0x1800f9407  mov     rax, [rsi+288h]
0x1800f940e  cmp     byte ptr [rax+rbx*8+8], 1
0x1800f9413  jz      short loc_1800F9444
0x1800f9415  mov     edx, [rax+rbx*8+4]
0x1800f9419  add     rdx, [rsi+278h]; Src
0x1800f9420  mov     r8d, [rdx]; Size
0x1800f9423  mov     ecx, r14d
0x1800f9426  add     rcx, r12; void *
0x1800f9429  call    memcpy_0
0x1800f942e  mov     rax, [rsi+288h]
0x1800f9435  mov     ecx, [rax+rbx*8+4]
0x1800f9439  mov     rax, [rsi+278h]
0x1800f9440  add     r14d, [rcx+rax]
0x1800f9444  inc     edi
0x1800f9446  mov     rcx, [rsi+58h]
0x1800f944a  movzx   eax, word ptr [rcx+8Ah]
0x1800f9451  cmp     edi, eax
0x1800f9453  jb      short loc_1800F9402
0x1800f9455  mov     [rsp+530h+NumberOfBytesWritten], r14d
0x1800f945a  mov     r12, [rsp+530h+var_4C8]
0x1800f945f  xor     r11d, r11d
0x1800f9462  mov     dword ptr [rcx+78h], 8Ch
0x1800f9469  mov     rax, [rsi+58h]
0x1800f946d  add     dword ptr [rax+78h], 320h
0x1800f9474  mov     rax, [rsi+58h]
0x1800f9478  mov     [rax+7Ch], r11d
0x1800f947c  mov     rax, [rsi+58h]
0x1800f9480  mov     [rax+80h], r11b
0x1800f9487  mov     rax, [rsi+278h]
0x1800f948e  mov     [rbp+430h+var_4B0], rax
0x1800f9492  mov     edi, r11d
0x1800f9495  mov     r14d, [rsp+530h+var_4CC]
0x1800f949a  mov     ebx, edi
0x1800f949c  add     rbx, rbx
0x1800f949f  cmp     [rax+rbx*8+8Ch], r11w
0x1800f94a8  jz      short loc_1800F9517
0x1800f94aa  mov     r15, [rsi+278h]
0x1800f94b1  mov     r13d, [r15+rbx*8+98h]
0x1800f94b9  xorps   xmm1, xmm1
0x1800f94bc  cvtsi2sd xmm1, r13
0x1800f94c1  mulsd   xmm1, cs:__real@3ff8000000000000
0x1800f94c9  mov     eax, [r15+rbx*8+94h]
0x1800f94d1  xorps   xmm0, xmm0
0x1800f94d4  cvtsi2sd xmm0, rax
0x1800f94d9  comisd  xmm1, xmm0
0x1800f94dd  jbe     short loc_1800F94E6
0x1800f94df  cvttsd2si r8, xmm1
0x1800f94e4  jmp     short loc_1800F94EC
0x1800f94e6  mov     r8d, 32h ; '2'; unsigned int
0x1800f94ec  mov     edx, edi; unsigned int
0x1800f94ee  mov     rcx, rsi; this
0x1800f94f1  call    ?AllocateHashTable@CSpUnCompressedLexicon@@AEAAJKK@Z; CSpUnCompressedLexicon::AllocateHashTable(ulong,ulong)
0x1800f94f6  mov     r14d, eax
0x1800f94f9  xor     r11d, r11d
0x1800f94fc  test    eax, eax
0x1800f94fe  js      loc_1800F96CE
0x1800f9504  mov     [r15+rbx*8+98h], r13d
0x1800f950c  inc     edi
  ... truncated ...
```
