# CNtfsFileSystemApplier::CompareFileContent(IFspFile *,IFspFile *,int *)

- ea: `0x18010ca50`
- end: `0x18010d271`
- name: `?CompareFileContent@CNtfsFileSystemApplier@@UEAAJPEAUIFspFile@@0PEAH@Z`
- size: `2081`
- prototype: `__int64 __fastcall(CNtfsFileSystemApplier *__hidden this, struct IFspFile *, struct IFspFile *, int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x18000430d`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x18001133c`
- `0x180022688`
- `0x180047d10`
- `0x18008b634`
- `0x18008c260`
- `0x18008c2d0`
- `0x18010ca50`
- `0x18010eae8`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CancelIo` at `0x18010d19d`
- `KERNEL32!CancelIo` at `0x18010d19d`
- `KERNEL32!GetOverlappedResult` at `0x18010cfda`
- `KERNEL32!GetOverlappedResult` at `0x18010cfda`
- `KERNEL32!ReadFile` at `0x18010cf25`
- `KERNEL32!ReadFile` at `0x18010cf25`
- `KERNEL32!WaitForSingleObject` at `0x18010d1c6`
- `KERNEL32!WaitForSingleObject` at `0x18010d1d7`
- `KERNEL32!WaitForSingleObject` at `0x18010d1c6`
- `KERNEL32!WaitForSingleObject` at `0x18010d1d7`
- `KERNEL32!CloseHandle` at `0x18010d1ee`
- `KERNEL32!CloseHandle` at `0x18010d205`
- `KERNEL32!CloseHandle` at `0x18010d1ee`
- `KERNEL32!CloseHandle` at `0x18010d205`
- `KERNEL32!GetLastError` at `0x18010cf2f`
- `KERNEL32!GetLastError` at `0x18010cf2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010cd57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010cd8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010cd57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010cd8c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010cf8c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18010cf8c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010ce7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010ce7b`
- `ntdll!NtClose` at `0x18010d1a8`
- `ntdll!NtClose` at `0x18010d1a8`

## string_xrefs

- `0x18010cae2`: `CNtfsFileSystemApplier::CompareFileContent`

## pseudocode

```c
__int64 __fastcall CNtfsFileSystemApplier::CompareFileContent(
        CNtfsFileSystemApplier *this,
        struct IFspFile *a2,
        struct IFspFile *a3,
        int *a4)
{
  int *v4; // r13
  _DWORD *v8; // rax
  char v9; // cl
  __int64 v10; // r14
  __int64 v11; // rdi
  LPVOID *v12; // rbx
  int v13; // ebx
  __int16 v14; // ax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r9
  PVOID *v19; // rdi
  BOOL v20; // esi
  HANDLE EventW; // rax
  HANDLE v22; // rax
  struct IFspFile *v23; // rdx
  int v24; // ebx
  unsigned __int64 v25; // r12
  __int128 v26; // xmm6
  __int64 v27; // r13
  DWORD v28; // r15d
  __int64 v29; // rdx
  HANDLE v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  void *v33; // rdx
  signed int LastError; // eax
  int i; // edi
  DWORD v36; // eax
  HANDLE v37; // rcx
  size_t v38; // rbx
  __int64 j; // rbx
  HANDLE v40; // rcx
  bool v41; // zf
  HANDLE v42; // rdi
  HANDLE v43; // rcx
  unsigned int v44; // edi
  char *v45; // rbx
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-D0h] BYREF
  int v48; // [rsp+3Ch] [rbp-CCh]
  __int64 v49; // [rsp+40h] [rbp-C8h]
  const char *v50; // [rsp+48h] [rbp-C0h]
  __int64 v51; // [rsp+50h] [rbp-B8h]
  unsigned int Size; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int Size_4; // [rsp+5Ch] [rbp-ACh]
  __int64 v54; // [rsp+60h] [rbp-A8h]
  unsigned __int64 hFile; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE hFile_8[2]; // [rsp+70h] [rbp-98h] BYREF
  HANDLE hHandle_8[2]; // [rsp+80h] [rbp-88h]
  __int64 v58; // [rsp+90h] [rbp-78h] BYREF
  int *v59; // [rsp+98h] [rbp-70h]
  HANDLE hObject[2]; // [rsp+A0h] [rbp-68h]
  LPVOID lpBuffer[2]; // [rsp+B0h] [rbp-58h] BYREF
  char v62; // [rsp+C0h] [rbp-48h] BYREF
  _OWORD v63[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v64; // [rsp+108h] [rbp+0h] BYREF
  __int128 v65; // [rsp+110h] [rbp+8h]
  _OWORD v66[2]; // [rsp+120h] [rbp+18h] BYREF
  __int64 v67; // [rsp+140h] [rbp+38h]
  HANDLE Handles[2]; // [rsp+148h] [rbp+40h] BYREF
  HANDLE v69; // [rsp+158h] [rbp+50h]
  _DWORD v70[18]; // [rsp+160h] [rbp+58h] BYREF

  v4 = a4;
  v59 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
    {
LABEL_8:
      v9 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( (v8[17] & 0x100) == 0 || *((_BYTE *)v8 + 65) < 6u )
    goto LABEL_8;
  v9 = 1;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v10 = 2;
  v50 = "CNtfsFileSystemApplier::CompareFileContent";
  v11 = 2;
  v48 = 3296;
  LOBYTE(v49) = v9;
  v12 = lpBuffer;
  v51 = 0;
  do
  {
    CEcsMemPtr<unsigned char,0>::CEcsMemPtr<unsigned char,0>(v12++);
    --v11;
  }
  while ( v11 );
  v13 = 0;
  *(_OWORD *)hFile_8 = 0;
  v54 = 0;
  *(_OWORD *)hHandle_8 = 0;
  memset_0(v63, 0, sizeof(v63));
  v64 = 0;
  v67 = 0;
  v65 = 0;
  memset(v66, 0, sizeof(v66));
  *(_OWORD *)hObject = 0;
  if ( v4 )
    *v4 = 0;
  v14 = 3313;
  if ( !a2 )
    goto LABEL_93;
  LOWORD(v48) = 3313;
  v14 = 3314;
  if ( !a3 )
    goto LABEL_93;
  LOWORD(v48) = 3314;
  v14 = 3315;
  if ( !v4 )
    goto LABEL_93;
  LOWORD(v48) = 3315;
  v15 = *(_QWORD *)a2;
  LastFailureAsHRESULT = 0;
  Size = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(v15 + 40))(a2, &Size);
  v14 = 3321;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_94;
  LOWORD(v48) = 3321;
  v14 = 3322;
  if ( (Size & 0x10) != 0 )
    goto LABEL_93;
  LOWORD(v48) = 3322;
  v16 = *(_QWORD *)a3;
  LastFailureAsHRESULT = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(v16 + 40))(a3, &Size);
  v14 = 3323;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_94;
  LOWORD(v48) = 3323;
  v14 = 3324;
  if ( (Size & 0x10) != 0 )
  {
LABEL_93:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_94;
  }
  LOWORD(v48) = 3324;
  v17 = *(_QWORD *)a2;
  LastFailureAsHRESULT = 0;
  hFile = 0;
  v58 = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned __int64 *))(v17 + 64))(a2, &hFile);
  v14 = 3330;
  if ( LastFailureAsHRESULT < 0
    || (LOWORD(v48) = 3330,
        LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IFspFile *, __int64 *))(*(_QWORD *)a3 + 64LL))(
                                 a3,
                                 &v58),
        v14 = 3331,
        LastFailureAsHRESULT < 0) )
  {
LABEL_94:
    HIWORD(v48) = v14;
    goto LABEL_95;
  }
  LOWORD(v48) = 3331;
  if ( hFile != v58 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v20 = 0;
    goto LABEL_88;
  }
  if ( !hFile && !v58 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        (unsigned int)(v58 + 54),
        WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v20 = 1;
    goto LABEL_88;
  }
  while ( v13 < 2 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    hHandle_8[v13] = EventW;
    if ( !EventW )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v14 = 3349;
      goto LABEL_94;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v48) = 3349;
    v22 = CreateEventW(0, 1, 0, 0);
    hObject[v13] = v22;
    if ( !v22 )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v14 = 3352;
      goto LABEL_94;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v48) = 3352;
    v23 = a2;
    *(_QWORD *)&v66[2 * v13] = v22;
    if ( v13 )
      v23 = a3;
    LastFailureAsHRESULT = CNtfsFileSystemApplier::OpenFileForCompare(
                             this,
                             v23,
                             (struct _OVERLAPPED *)&v64 + v13,
                             (struct _REQUEST_OPLOCK_INPUT_BUFFER *)&v70[3 * v13],
                             (struct _REQUEST_OPLOCK_OUTPUT_BUFFER *)&v70[6 * v13 + 6],
                             &hFile_8[v13]);
    v14 = 3360;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_94;
    LOWORD(v48) = 3360;
    LastFailureAsHRESULT = CEcsMemPtr<unsigned short,0>::AllocBytes(&lpBuffer[v13], 0x100000u);
    if ( LastFailureAsHRESULT < 0 )
    {
      HIWORD(v48) = 3362;
      goto LABEL_95;
    }
    LOWORD(v48) = 3362;
    ++v13;
  }
  v24 = 0;
  if ( CNtfsFileSystemApplier::m_dwCompareFileDelayMs )
    Sleep(CNtfsFileSystemApplier::m_dwCompareFileDelayMs);
  v25 = hFile;
  v20 = 1;
  v26 = *(_OWORD *)hObject;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  v27 = 0;
  while ( 2 )
  {
    if ( v20 && v25 )
    {
      v69 = 0;
      v28 = 0x100000;
      *(_OWORD *)Handles = v26;
      if ( v25 < 0x100000 )
        v28 = v25;
      v29 = 0;
      do
      {
        v30 = hHandle_8[v29];
        v31 = 2 * v29++;
        v63[v31] = 0;
        v63[v31 + 1] = 0;
        *((_QWORD *)&v63[v31 + 1] + 1) = v30;
      }
      while ( v29 != 2 );
      while ( v24 < 2 )
      {
        v32 = 2LL * v24;
        v33 = lpBuffer[v24];
        DWORD1(v63[v32 + 1]) = HIDWORD(v27);
        LODWORD(v63[v32 + 1]) = v27;
        if ( !ReadFile(hFile_8[v24], v33, v28, 0, (LPOVERLAPPED)&v63[v32]) )
        {
          LastError = GetLastError();
          if ( LastError != 997 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            LastFailureAsHRESULT = LastError;
            v14 = 3416;
            goto LABEL_94;
          }
          LastFailureAsHRESULT = 0;
          LOWORD(v48) = 3416;
          *((_DWORD *)&v54 + v24) = 1;
        }
        ++v24;
      }
      for ( i = 0; i < 2; ++i )
      {
        v69 = hHandle_8[i];
        v36 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
        if ( v36 == -1 )
        {
          LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
          v14 = 3429;
          goto LABEL_94;
        }
        LastFailureAsHRESULT = 0;
        LOWORD(v48) = 3429;
        if ( v36 != 2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
          }
          *(&Size + i) = 0;
          v14 = 3444;
          LastFailureAsHRESULT = -2134376425;
          goto LABEL_94;
        }
        v37 = hFile_8[i];
        *((_DWORD *)&v54 + i) = 0;
        if ( !GetOverlappedResult(v37, (LPOVERLAPPED)&v63[2 * i], &Size + i, 0) )
        {
          LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
          v14 = 3437;
          goto LABEL_94;
        }
        LastFailureAsHRESULT = 0;
        LOWORD(v48) = 3437;
      }
      v38 = Size_4;
      if ( Size < Size_4 )
        v38 = Size;
      if ( !(_DWORD)v38 )
      {
        LastFailureAsHRESULT = -2147418113;
        v14 = 3451;
        goto LABEL_94;
      }
      LastFailureAsHRESULT = 0;
      LOWORD(v48) = 3451;
      if ( (_DWORD)v38 != v28 )
      {
        v19 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
        {
          goto LABEL_75;
        }
        WPP_SF_lll(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          56,
          WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids,
          v28,
          Size,
          Size_4);
      }
      v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_75:
      v20 = memcmp_0(lpBuffer[0], lpBuffer[1], v38) == 0;
      v25 -= v38;
      v27 += v38;
      v24 = 0;
      continue;
    }
    break;
  }
  v4 = v59;
LABEL_88:
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 17) & 0x100) != 0 && *((_BYTE *)v19 + 65) >= 4u )
  {
    LOBYTE(v18) = v20 ? 89 : 78;
    WPP_SF_c(v19[7], 57, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids, v18);
  }
  *v4 = v20;
LABEL_95:
  for ( j = 0; j != 2; ++j )
  {
    v40 = hFile_8[j];
    if ( v40 )
    {
      CancelIo(v40);
      NtClose(hFile_8[j]);
      v41 = *((_DWORD *)&v54 + j) == 0;
      hFile_8[j] = 0;
      if ( !v41 )
        WaitForSingleObject(hHandle_8[j], 0xFFFFFFFF);
      v42 = hObject[j];
      WaitForSingleObject(v42, 0xFFFFFFFF);
    }
    else
    {
      v42 = hObject[j];
    }
    v43 = hHandle_8[j];
    if ( v43 )
    {
      CloseHandle(v43);
      hHandle_8[j] = 0;
    }
    if ( v42 )
    {
      CloseHandle(v42);
      hObject[j] = 0;
    }
  }
  v44 = LastFailureAsHRESULT;
  v45 = &v62;
  do
  {
    v45 -= 8;
    CEcsMemPtr<unsigned char,0>::~CEcsMemPtr<unsigned char,0>(v45);
    --v10;
  }
  while ( v10 );
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v44;
}

```

## disassembly

```asm
0x18010ca50  mov     rax, rsp
0x18010ca53  push    rbp
0x18010ca54  push    rbx
0x18010ca55  push    rsi
0x18010ca56  push    rdi
0x18010ca57  push    r12
0x18010ca59  push    r13
0x18010ca5b  push    r14
0x18010ca5d  push    r15
0x18010ca5f  lea     rbp, [rax-108h]
0x18010ca66  sub     rsp, 1C8h
0x18010ca6d  movaps  xmmword ptr [rax-58h], xmm6
0x18010ca71  mov     rax, cs:__security_cookie
0x18010ca78  xor     rax, rsp
0x18010ca7b  mov     [rbp+100h+var_60], rax
0x18010ca82  mov     r13, r9
0x18010ca85  mov     [rbp+100h+var_170], r9
0x18010ca89  mov     r15, r8
0x18010ca8c  mov     rsi, rdx
0x18010ca8f  mov     r12, rcx
0x18010ca92  mov     rax, cs:WPP_GLOBAL_Control
0x18010ca99  lea     rcx, WPP_GLOBAL_Control
0x18010caa0  mov     ebx, 100h
0x18010caa5  cmp     rax, rcx
0x18010caa8  jz      short loc_18010CAD1
0x18010caaa  test    [rax+44h], ebx
0x18010caad  jz      short loc_18010CAE0
0x18010caaf  cmp     byte ptr [rax+41h], 6
0x18010cab3  jb      short loc_18010CAD1
0x18010cab5  mov     rcx, [rax+38h]
0x18010cab9  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18010cac0  mov     edx, 34h ; '4'
0x18010cac5  call    WPP_SF_
0x18010caca  mov     rax, cs:WPP_GLOBAL_Control
0x18010cad1  test    [rax+44h], ebx
0x18010cad4  jz      short loc_18010CAE0
0x18010cad6  cmp     byte ptr [rax+41h], 6
0x18010cada  jb      short loc_18010CAE0
0x18010cadc  mov     cl, 1
0x18010cade  jmp     short loc_18010CAE2
0x18010cae0  xor     cl, cl
0x18010cae2  lea     rax, aCntfsfilesyste_1; "CNtfsFileSystemApplier::CompareFileCont"...
0x18010cae9  mov     [rsp+200h+var_1D0], 0
0x18010caf1  mov     r14d, 2
0x18010caf7  mov     [rsp+200h+var_1C0], rax
0x18010cafc  mov     edi, r14d
0x18010caff  mov     [rsp+200h+var_1CC], 0CE0h
0x18010cb07  mov     byte ptr [rsp+200h+var_1C8], cl
0x18010cb0b  lea     rbx, [rbp+100h+lpBuffer]
0x18010cb0f  mov     [rsp+200h+var_1B8], 0
0x18010cb18  mov     rcx, rbx; void *
0x18010cb1b  call    ??0?$CEcsMemPtr@E$0A@@@QEAA@XZ; CEcsMemPtr<uchar,0>::CEcsMemPtr<uchar,0>(void)
0x18010cb20  add     rbx, 8
0x18010cb24  sub     rdi, 1
0x18010cb28  jnz     short loc_18010CB18
0x18010cb2a  xorps   xmm0, xmm0
0x18010cb2d  lea     r8d, [rdi+40h]; Size
0x18010cb31  xorps   xmm1, xmm1
0x18010cb34  lea     rcx, [rbp+100h+var_140]; void *
0x18010cb38  xor     ebx, ebx
0x18010cb3a  xor     edx, edx; Val
0x18010cb3c  movups  xmmword ptr [rsp+200h+hFile+8], xmm0
0x18010cb41  mov     [rsp+200h+var_1A8], rbx
0x18010cb46  movups  xmmword ptr [rsp+200h+hHandle+8], xmm1
0x18010cb4b  call    memset_0
0x18010cb50  xorps   xmm0, xmm0
0x18010cb53  mov     [rbp+100h+var_100], rbx
0x18010cb57  xor     eax, eax
0x18010cb59  mov     [rbp+100h+var_C8], rax
0x18010cb5d  movups  [rbp+100h+var_F8], xmm0
0x18010cb61  movups  [rbp+100h+var_E8], xmm0
0x18010cb65  movups  [rbp+100h+var_D8], xmm0
0x18010cb69  movups  xmmword ptr [rbp+100h+hObject], xmm0
0x18010cb6d  test    r13, r13
0x18010cb70  jz      short loc_18010CB76
0x18010cb72  mov     [r13+0], ebx
0x18010cb76  mov     eax, 0CF1h
0x18010cb7b  test    rsi, rsi
0x18010cb7e  jz      loc_18010D184
0x18010cb84  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cb89  mov     eax, 0CF2h
0x18010cb8e  test    r15, r15
0x18010cb91  jz      loc_18010D184
0x18010cb97  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cb9c  mov     eax, 0CF3h
0x18010cba1  test    r13, r13
0x18010cba4  jz      loc_18010D184
0x18010cbaa  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cbaf  lea     rdx, [rsp+200h+Size]
0x18010cbb4  mov     rax, [rsi]
0x18010cbb7  mov     rcx, rsi
0x18010cbba  mov     [rsp+200h+var_1D0], ebx
0x18010cbbe  mov     dword ptr [rsp+200h+Size], ebx
0x18010cbc2  mov     rax, [rax+28h]
0x18010cbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cbcb  mov     [rsp+200h+var_1D0], eax
0x18010cbcf  test    eax, eax
0x18010cbd1  mov     eax, 0CF9h
0x18010cbd6  js      loc_18010D18C
0x18010cbdc  test    byte ptr [rsp+200h+Size], 10h
0x18010cbe1  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cbe6  mov     eax, 0CFAh
0x18010cbeb  jnz     loc_18010D184
0x18010cbf1  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cbf6  lea     rdx, [rsp+200h+Size]
0x18010cbfb  mov     rax, [r15]
0x18010cbfe  mov     rcx, r15
0x18010cc01  mov     [rsp+200h+var_1D0], ebx
0x18010cc05  mov     rax, [rax+28h]
0x18010cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc0e  mov     [rsp+200h+var_1D0], eax
0x18010cc12  test    eax, eax
0x18010cc14  mov     eax, 0CFBh
0x18010cc19  js      loc_18010D18C
0x18010cc1f  test    byte ptr [rsp+200h+Size], 10h
0x18010cc24  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cc29  mov     eax, 0CFCh
0x18010cc2e  jnz     loc_18010D184
0x18010cc34  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cc39  lea     rdx, [rsp+200h+hFile]
0x18010cc3e  mov     rax, [rsi]
0x18010cc41  mov     rcx, rsi
0x18010cc44  mov     [rsp+200h+var_1D0], ebx
0x18010cc48  mov     [rsp+200h+hFile], rbx
0x18010cc4d  mov     [rbp+100h+var_178], rbx
0x18010cc51  mov     rax, [rax+40h]
0x18010cc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc5a  mov     [rsp+200h+var_1D0], eax
0x18010cc5e  test    eax, eax
0x18010cc60  mov     eax, 0D02h
0x18010cc65  js      loc_18010D18C
0x18010cc6b  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cc70  lea     rdx, [rbp+100h+var_178]
0x18010cc74  mov     rax, [r15]
0x18010cc77  mov     rcx, r15
0x18010cc7a  mov     rax, [rax+40h]
0x18010cc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc83  mov     [rsp+200h+var_1D0], eax
0x18010cc87  test    eax, eax
0x18010cc89  mov     eax, 0D03h
0x18010cc8e  js      loc_18010D18C
0x18010cc94  mov     rcx, [rbp+100h+var_178]
0x18010cc98  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cc9d  mov     rax, [rsp+200h+hFile]
0x18010cca2  cmp     rax, rcx
0x18010cca5  jz      short loc_18010CCEC
0x18010cca7  mov     rdi, cs:WPP_GLOBAL_Control
0x18010ccae  lea     rax, WPP_GLOBAL_Control
0x18010ccb5  cmp     rdi, rax
0x18010ccb8  jz      short loc_18010CCE5
0x18010ccba  test    dword ptr [rdi+44h], 100h
0x18010ccc1  jz      short loc_18010CCE5
0x18010ccc3  cmp     byte ptr [rdi+41h], 4
0x18010ccc7  jb      short loc_18010CCE5
0x18010ccc9  mov     rcx, [rdi+38h]
0x18010cccd  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18010ccd4  mov     edx, 35h ; '5'
0x18010ccd9  call    WPP_SF_
0x18010ccde  mov     rdi, cs:WPP_GLOBAL_Control
0x18010cce5  mov     esi, ebx
0x18010cce7  jmp     loc_18010D13F
0x18010ccec  test    rax, rax
0x18010ccef  jnz     short loc_18010CD3C
0x18010ccf1  test    rcx, rcx
0x18010ccf4  jnz     short loc_18010CD3C
0x18010ccf6  mov     rdi, cs:WPP_GLOBAL_Control
0x18010ccfd  lea     rax, WPP_GLOBAL_Control
0x18010cd04  cmp     rdi, rax
0x18010cd07  jz      short loc_18010CD32
0x18010cd09  test    dword ptr [rdi+44h], 100h
0x18010cd10  jz      short loc_18010CD32
0x18010cd12  cmp     byte ptr [rdi+41h], 4
0x18010cd16  jb      short loc_18010CD32
0x18010cd18  lea     edx, [rcx+36h]
0x18010cd1b  mov     rcx, [rdi+38h]
0x18010cd1f  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18010cd26  call    WPP_SF_
0x18010cd2b  mov     rdi, cs:WPP_GLOBAL_Control
0x18010cd32  mov     esi, 1
0x18010cd37  jmp     loc_18010D13F
0x18010cd3c  mov     r13d, 0D22h
0x18010cd42  cmp     ebx, r14d
0x18010cd45  jge     loc_18010CE6F
0x18010cd4b  xor     r9d, r9d; lpName
0x18010cd4e  xor     r8d, r8d; bInitialState
0x18010cd51  xor     ecx, ecx; lpEventAttributes
0x18010cd53  lea     edx, [r9+1]; bManualReset
0x18010cd57  call    cs:__imp_CreateEventW
0x18010cd5d  movsxd  rdi, ebx
0x18010cd60  mov     [rsp+rdi*8+200h+hHandle+8], rax
0x18010cd65  test    rax, rax
0x18010cd68  jz      loc_18010CE5C
0x18010cd6e  xor     r9d, r9d; lpName
0x18010cd71  mov     [rsp+200h+var_1D0], 0
0x18010cd79  mov     eax, 0D15h
0x18010cd7e  xor     r8d, r8d; bInitialState
0x18010cd81  xor     ecx, ecx; lpEventAttributes
0x18010cd83  mov     word ptr [rsp+200h+var_1CC], ax
0x18010cd88  lea     edx, [r9+1]; bManualReset
0x18010cd8c  call    cs:__imp_CreateEventW
0x18010cd92  mov     [rbp+rdi*8+100h+hObject], rax
0x18010cd97  test    rax, rax
0x18010cd9a  jz      loc_18010CE49
0x18010cda0  mov     ecx, 0D18h
0x18010cda5  mov     [rsp+200h+var_1D0], 0
0x18010cdad  mov     word ptr [rsp+200h+var_1CC], cx
0x18010cdb2  lea     r8, [rbp+100h+var_100]
0x18010cdb6  mov     rcx, rdi
0x18010cdb9  lea     r10, [rbp+100h+var_90]
0x18010cdbd  shl     rcx, 5
0x18010cdc1  lea     r11, [rsp+200h+hFile+8]
0x18010cdc6  add     r8, rcx; struct _OVERLAPPED *
0x18010cdc9  lea     r11, [r11+rdi*8]
0x18010cdcd  mov     [rsp+200h+var_1D8], r11; void **
0x18010cdd2  lea     r9, [rbp+100h+var_A8]
0x18010cdd6  test    ebx, ebx
0x18010cdd8  mov     rdx, rsi
0x18010cddb  mov     qword ptr [rbp+rcx+100h+var_E8], rax
0x18010cde0  lea     rax, [rdi+rdi*2]
0x18010cde4  lea     r10, [r10+rax*8]
0x18010cde8  cmovnz  rdx, r15; struct IFspFile *
0x18010cdec  lea     rax, [rdi+rdi*2]
0x18010cdf0  mov     [rsp+200h+lpOverlapped], r10; struct _REQUEST_OPLOCK_OUTPUT_BUFFER *
0x18010cdf5  lea     r9, [r9+rax*4]; struct _REQUEST_OPLOCK_INPUT_BUFFER *
0x18010cdf9  mov     rcx, r12; this
0x18010cdfc  call    ?OpenFileForCompare@CNtfsFileSystemApplier@@AEAAJPEAUIFspFile@@PEAU_OVERLAPPED@@PEAU_REQUEST_OPLOCK_INPUT_BUFFER@@PEAU_REQUEST_OPLOCK_OUTPUT_BUFFER@@PEAPEAX@Z; CNtfsFileSystemApplier::OpenFileForCompare(IFspFile *,_OVERLAPPED *,_REQUEST_OPLOCK_INPUT_BUFFER *,_REQUEST_OPLOCK_OUTPUT_BUFFER *,void * *)
0x18010ce01  mov     [rsp+200h+var_1D0], eax
0x18010ce05  test    eax, eax
0x18010ce07  mov     eax, 0D20h
0x18010ce0c  js      loc_18010D18C
0x18010ce12  lea     rcx, [rbp+100h+lpBuffer]
0x18010ce16  mov     word ptr [rsp+200h+var_1CC], ax
0x18010ce1b  lea     rcx, [rcx+rdi*8]; void **
0x18010ce1f  mov     edx, 100000h; unsigned __int64
0x18010ce24  call    ?AllocBytes@?$CEcsMemPtr@G$0A@@@QEAAJ_K@Z; CEcsMemPtr<ushort,0>::AllocBytes(unsigned __int64)
0x18010ce29  mov     [rsp+200h+var_1D0], eax
0x18010ce2d  test    eax, eax
0x18010ce2f  js      short loc_18010CE3E
0x18010ce31  mov     word ptr [rsp+200h+var_1CC], r13w
0x18010ce37  inc     ebx
0x18010ce39  jmp     loc_18010CD42
0x18010ce3e  mov     word ptr [rsp+200h+var_1CC+2], r13w
0x18010ce44  jmp     loc_18010D191
0x18010ce49  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18010ce4e  mov     [rsp+200h+var_1D0], eax
0x18010ce52  mov     eax, 0D18h
0x18010ce57  jmp     loc_18010D18C
0x18010ce5c  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18010ce61  mov     [rsp+200h+var_1D0], eax
0x18010ce65  mov     eax, 0D15h
0x18010ce6a  jmp     loc_18010D18C
0x18010ce6f  mov     ecx, cs:?m_dwCompareFileDelayMs@CNtfsFileSystemApplier@@0KA; dwMilliseconds
0x18010ce75  xor     ebx, ebx
0x18010ce77  test    ecx, ecx
0x18010ce79  jz      short loc_18010CE81
0x18010ce7b  call    cs:__imp_Sleep
0x18010ce81  mov     r12, [rsp+200h+hFile]
0x18010ce86  mov     esi, 1
0x18010ce8b  movups  xmm6, xmmword ptr [rbp+100h+hObject]
0x18010ce8f  mov     rdi, cs:WPP_GLOBAL_Control
0x18010ce96  mov     r13, rbx
0x18010ce99  test    esi, esi
0x18010ce9b  jz      loc_18010D13B
0x18010cea1  test    r12, r12
0x18010cea4  jz      loc_18010D13B
0x18010ceaa  mov     eax, 100000h
0x18010ceaf  mov     [rbp+100h+var_B0], rbx
0x18010ceb3  cmp     r12, rax
0x18010ceb6  mov     r15d, eax
0x18010ceb9  movups  xmmword ptr [rbp+100h+Handles], xmm6
0x18010cebd  cmovb   r15, r12
0x18010cec1  mov     rdx, rbx
0x18010cec4  mov     rax, [rsp+rdx*8+200h+hHandle+8]
0x18010cec9  mov     rcx, rdx
0x18010cecc  shl     rcx, 5
0x18010ced0  xorps   xmm0, xmm0
0x18010ced3  inc     rdx
0x18010ced6  movups  [rbp+rcx+100h+var_140], xmm0
0x18010cedb  movups  [rbp+rcx+100h+var_130], xmm0
0x18010cee0  mov     qword ptr [rbp+rcx+100h+var_130+8], rax
0x18010cee5  cmp     rdx, r14
0x18010cee8  jnz     short loc_18010CEC4
0x18010ceea  cmp     ebx, r14d
0x18010ceed  jge     short loc_18010CF5E
0x18010ceef  movsxd  rdi, ebx
0x18010cef2  mov     rax, r13
0x18010cef5  shr     rax, 20h
0x18010cef9  mov     rcx, rdi
0x18010cefc  shl     rcx, 5
0x18010cf00  xor     r9d, r9d; lpNumberOfBytesRead
0x18010cf03  mov     r8d, r15d; nNumberOfBytesToRead
0x18010cf06  mov     rdx, [rbp+rdi*8+100h+lpBuffer]; lpBuffer
0x18010cf0b  mov     dword ptr [rbp+rcx+100h+var_130+4], eax
0x18010cf0f  lea     rax, [rbp+100h+var_140]
0x18010cf13  add     rax, rcx
0x18010cf16  mov     dword ptr [rbp+rcx+100h+var_130], r13d
0x18010cf1b  mov     rcx, [rsp+rdi*8+200h+hFile+8]; hFile
0x18010cf20  mov     [rsp+200h+lpOverlapped], rax; lpOverlapped
0x18010cf25  call    cs:__imp_ReadFile
0x18010cf2b  test    eax, eax
  ... truncated ...
```
