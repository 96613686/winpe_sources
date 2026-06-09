# RtlLoadObjectFromDIBFile(ushort const *,ushort *,ulong,ulong,uint)

- ea: `0x180001670`
- end: `0x180001c5b`
- name: `?RtlLoadObjectFromDIBFile@@YAPEAXPEBGPEAGKKI@Z`
- size: `1515`
- prototype: `void *__usercall@<rax>(LPCWSTR lpSrc@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x1800081d4`

## callees

- `0x1800013dc`
- `0x180001670`
- `0x180001cc4`
- `0x180003cbc`
- `0x180004cd0`
- `0x18005b418`
- `0x1800704a4`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180001c44`
- `ntdll!RtlSetLastWin32Error` at `0x180001c44`
- `ntdll!wcsncpy_s` at `0x18000171f`
- `ntdll!wcsncpy_s` at `0x18000171f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001ad2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001b45`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001ad2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001be2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001be2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c37`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c2c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c2c`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180001752`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180001752`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000178b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000178b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001805`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001805`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001bcf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001bcf`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800017e6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800017e6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800017be`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800017be`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001b17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001b17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ac9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ac9`

## pseudocode

```c
HBITMAP __fastcall RtlLoadObjectFromDIBFile(LPCWSTR lpSrc, char *a2, unsigned int a3, unsigned int a4, unsigned int a5)
{
  HBITMAP v7; // r12
  __int16 v8; // r13
  HANDLE FileW; // rax
  void *v10; // r14
  HANDLE FileMappingW; // rax
  unsigned __int8 *v12; // rdi
  DWORD FileSize; // r10d
  unsigned int v14; // edx
  __int16 v15; // cx
  unsigned int v16; // edx
  unsigned int v17; // r8d
  HBITMAP CursorIconFromFileMap; // rax
  unsigned __int8 *v19; // r14
  struct tagBITMAPINFOHEADER *v20; // r15
  void *v21; // rsi
  int v22; // eax
  unsigned int v23; // r10d
  unsigned int biSizeImage; // r13d
  __int64 v25; // rdx
  void *v26; // rax
  char *v27; // rax
  unsigned int v29; // [rsp+50h] [rbp-518h] BYREF
  int v30; // [rsp+54h] [rbp-514h]
  unsigned int v31; // [rsp+58h] [rbp-510h] BYREF
  unsigned int v32; // [rsp+5Ch] [rbp-50Ch]
  __int64 v33; // [rsp+60h] [rbp-508h] BYREF
  unsigned int v34; // [rsp+68h] [rbp-500h] BYREF
  unsigned int v35; // [rsp+6Ch] [rbp-4FCh]
  unsigned int v36; // [rsp+70h] [rbp-4F8h]
  char *v37; // [rsp+78h] [rbp-4F0h] BYREF
  HBITMAP v38; // [rsp+80h] [rbp-4E8h]
  unsigned __int8 *v39; // [rsp+88h] [rbp-4E0h]
  char *v40; // [rsp+90h] [rbp-4D8h]
  __m128i v41; // [rsp+98h] [rbp-4D0h] BYREF
  __m128i v42; // [rsp+A8h] [rbp-4C0h] BYREF
  LPWSTR FilePart; // [rsp+B8h] [rbp-4B0h] BYREF
  void *v44; // [rsp+C0h] [rbp-4A8h]
  HANDLE hObject; // [rsp+C8h] [rbp-4A0h]
  HANDLE v46; // [rsp+D0h] [rbp-498h]
  _OWORD v47[2]; // [rsp+E0h] [rbp-488h] BYREF
  wchar_t Destination[264]; // [rsp+100h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+310h] [rbp-258h] BYREF

  v35 = a4;
  v36 = a3;
  v37 = a2;
  v32 = a5;
  v41 = 0;
  v42 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(Destination, 0, 0x208u);
  FilePart = 0;
  if ( (a5 & 0x200) != 0 )
    ExpandEnvironmentStringsW(lpSrc, Destination, 0x104u);
  else
    wcsncpy_s(Destination, 0x104u, lpSrc, 0x103u);
  if ( SearchPathW(0, Destination, 0, 0x104u, Buffer, &FilePart) )
  {
    v7 = 0;
    v8 = 1;
    FileW = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0, 0);
    v10 = FileW;
    v46 = FileW;
    if ( FileW == (HANDLE)-1LL )
      return v7;
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    hObject = FileMappingW;
    if ( !FileMappingW )
    {
      v12 = (unsigned __int8 *)v41.m128i_i64[0];
      goto LABEL_55;
    }
    v12 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v41.m128i_i64[0] = (__int64)v12;
    if ( !v12 )
      goto LABEL_55;
    FileSize = GetFileSize(v10, 0);
    v29 = FileSize;
    v42.m128i_i64[0] = (__int64)&v12[FileSize];
    if ( v42.m128i_i64[0] < (unsigned __int64)v12 )
      goto LABEL_55;
    v14 = FileSize;
    v33 = FileSize;
    if ( FileSize < 0x1A )
      goto LABEL_55;
    v41.m128i_i64[1] = (__int64)v12;
    v42.m128i_i64[1] = (__int64)Buffer;
    if ( (unsigned __int16)a2 == 1 )
    {
LABEL_12:
      if ( *(_DWORD *)v12 == 1179011410 )
      {
        v29 = 0;
        CursorIconFromFileMap = (HBITMAP)LoadCursorIconFromFileMap(
                                           (struct _FILEINFO *)&v41,
                                           (unsigned __int16 **)&v37,
                                           v36,
                                           v35,
                                           v32,
                                           (int *)&v29);
        v38 = CursorIconFromFileMap;
        v12 = (unsigned __int8 *)v41.m128i_i64[0];
      }
      else
      {
        LODWORD(v33) = 0;
        WORD2(v33) = 0;
        if ( *(_WORD *)v12 )
          goto LABEL_55;
        if ( (unsigned __int16)(*((_WORD *)v12 + 1) - 1) > 1u )
          goto LABEL_55;
        v15 = *((_WORD *)v12 + 2);
        if ( !v15 )
          goto LABEL_55;
        v16 = 0;
        if ( v36 != 256 )
          v16 = v36;
        v17 = 0;
        if ( v35 != 256 )
          v17 = v35;
        if ( (v32 & 0x10000) != 0 && v15 == 1 && (v12[6] != v16 || v12[7] != v17) )
          goto LABEL_55;
        if ( a2 != (char *)3 )
          v8 = 2;
        WORD1(v33) = v8;
        WORD2(v33) = v15;
        LOWORD(v33) = 0;
        v47[0] = _mm_loadu_si128(&v41);
        v47[1] = _mm_loadu_si128(&v42);
        CursorIconFromFileMap = (HBITMAP)IconFromBestImage(v47, v12, &v33);
        v38 = CursorIconFromFileMap;
      }
      v7 = CursorIconFromFileMap;
LABEL_55:
      if ( v12 )
        UnmapViewOfFile(v12);
      if ( hObject )
        CloseHandle(hObject);
      if ( v46 )
        CloseHandle(v46);
      return v7;
    }
    if ( (unsigned __int16)a2 != 2 )
    {
      if ( (unsigned __int16)a2 != 3 )
        goto LABEL_55;
      goto LABEL_12;
    }
    v19 = 0;
    v39 = 0;
    v20 = 0;
    v40 = 0;
    v21 = 0;
    v44 = 0;
    v37 = 0;
    v34 = 0;
    v31 = 0;
    v22 = 0;
    v30 = 0;
    if ( (v32 & 0x20000) == 0 )
    {
LABEL_30:
      if ( !v19 )
      {
        v19 = v12;
        v39 = v12;
        v20 = (struct tagBITMAPINFOHEADER *)(v12 + 14);
        v40 = (char *)(v12 + 14);
      }
      if ( *(_WORD *)v19 != 19778 )
        goto LABEL_55;
      if ( v22 )
      {
        v23 = v31 + 14;
        v29 = v31 + 14;
        if ( v31 + 14 < v31 )
        {
LABEL_44:
          GlobalUnlock(v21);
          GlobalFree(v21);
          goto LABEL_55;
        }
      }
      else
      {
        v31 = v14;
        if ( (int)ULongSub(FileSize, 0xEu, &v31) < 0 )
          goto LABEL_55;
      }
      biSizeImage = v20->biSizeImage;
      if ( biSizeImage < 0x28 )
        biSizeImage = 0;
      if ( (unsigned int)CheckImageSize(v20, v23) )
      {
        v25 = *(unsigned int *)(v19 + 10);
        if ( (unsigned int)v25 < 0x1A || (unsigned int)v25 > v29 - biSizeImage )
        {
          v37 = 0;
        }
        else
        {
          v37 = (char *)v20 + v25 - 14;
          if ( (int)ULongSub(v29, v25, &v34) < 0 )
          {
            v37 = 0;
            v34 = 0;
          }
        }
        v7 = ConvertDIBBitmap(v20, v31, v36, v35, v32, 0, 0, &v37, &v34);
        v38 = v7;
      }
      if ( !v30 )
        goto LABEL_55;
      goto LABEL_44;
    }
    if ( (unsigned int)InitializeIcs() )
    {
      v26 = (void *)((__int64 (__fastcall *)(unsigned __int8 *, _QWORD, unsigned int *, __int64))gpICSProc)(
                      v12,
                      v29,
                      &v31,
                      2);
      v21 = v26;
      v44 = v26;
      if ( v26 )
      {
        v27 = (char *)GlobalLock(v26);
        v19 = (unsigned __int8 *)v27;
        v39 = (unsigned __int8 *)v27;
        if ( v27 )
        {
          v20 = (struct tagBITMAPINFOHEADER *)(v27 + 14);
          v40 = v27 + 14;
          v22 = 1;
          v30 = 1;
LABEL_51:
          v14 = v33;
          FileSize = v29;
          goto LABEL_30;
        }
        GlobalFree(v21);
      }
    }
    v22 = 0;
    goto LABEL_51;
  }
  RtlSetLastWin32Error(2u);
  return 0;
}

```

## disassembly

```asm
0x180001670  push    rbx
0x180001672  push    rsi
0x180001673  push    rdi
0x180001674  push    r12
0x180001676  push    r13
0x180001678  push    r14
0x18000167a  push    r15
0x18000167c  sub     rsp, 530h
0x180001683  mov     rax, cs:__security_cookie
0x18000168a  xor     rax, rsp
0x18000168d  mov     [rsp+568h+var_48], rax
0x180001695  mov     [rsp+568h+var_4FC], r9d
0x18000169a  mov     [rsp+568h+var_4F8], r8d
0x18000169f  mov     r15, rdx
0x1800016a2  mov     rdi, rcx
0x1800016a5  mov     [rsp+568h+var_4F0], rdx
0x1800016aa  mov     esi, [rsp+568h+arg_20]
0x1800016b1  mov     [rsp+568h+var_50C], esi
0x1800016b5  xorps   xmm0, xmm0
0x1800016b8  movdqu  [rsp+568h+var_4D0], xmm0
0x1800016c1  xorps   xmm1, xmm1
0x1800016c4  movdqu  [rsp+568h+var_4C0], xmm1
0x1800016cd  mov     ebx, 208h
0x1800016d2  mov     r8d, ebx; Size
0x1800016d5  xor     edx, edx; Val
0x1800016d7  lea     rcx, [rsp+568h+Buffer]; void *
0x1800016df  call    memset_0
0x1800016e4  mov     r8d, ebx; Size
0x1800016e7  xor     edx, edx; Val
0x1800016e9  lea     rcx, [rsp+568h+Destination]; void *
0x1800016f1  call    memset_0
0x1800016f6  xor     ebx, ebx
0x1800016f8  mov     [rsp+568h+FilePart], rbx
0x180001700  bt      esi, 9
0x180001704  jb      loc_180001C1B
0x18000170a  mov     r9d, 103h; MaxCount
0x180001710  mov     r8, rdi; Source
0x180001713  lea     edx, [r9+1]; SizeInWords
0x180001717  lea     rcx, [rsp+568h+Destination]; Destination
0x18000171f  call    cs:__imp_wcsncpy_s
0x180001725  lea     rax, [rsp+568h+FilePart]
0x18000172d  mov     [rsp+568h+lpFilePart], rax; lpFilePart
0x180001732  lea     rax, [rsp+568h+Buffer]
0x18000173a  mov     [rsp+568h+lpBuffer], rax; lpBuffer
0x18000173f  mov     r9d, 104h; nBufferLength
0x180001745  xor     r8d, r8d; lpExtension
0x180001748  lea     rdx, [rsp+568h+Destination]; lpFileName
0x180001750  xor     ecx, ecx; lpPath
0x180001752  call    cs:__imp_SearchPathW
0x180001758  test    eax, eax
0x18000175a  jz      loc_180001C3F
0x180001760  mov     r12, rbx
0x180001763  mov     [rsp+568h+hTemplateFile], rbx; hTemplateFile
0x180001768  mov     dword ptr [rsp+568h+lpFilePart], ebx; dwFlagsAndAttributes
0x18000176c  mov     dword ptr [rsp+568h+lpBuffer], 3; dwCreationDisposition
0x180001774  xor     r9d, r9d; lpSecurityAttributes
0x180001777  lea     r13d, [r9+1]
0x18000177b  mov     r8d, r13d; dwShareMode
0x18000177e  mov     edx, 80000000h; dwDesiredAccess
0x180001783  lea     rcx, [rsp+568h+Buffer]; lpFileName
0x18000178b  call    cs:__imp_CreateFileW
0x180001791  mov     r14, rax
0x180001794  mov     [rsp+568h+var_498], rax
0x18000179c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800017a0  jz      loc_180001BF5
0x1800017a6  mov     [rsp+568h+lpFilePart], rbx; lpName
0x1800017ab  mov     dword ptr [rsp+568h+lpBuffer], ebx; dwMaximumSizeLow
0x1800017af  xor     r9d, r9d; dwMaximumSizeHigh
0x1800017b2  lea     esi, [r13+1]
0x1800017b6  mov     r8d, esi; flProtect
0x1800017b9  xor     edx, edx; lpFileMappingAttributes
0x1800017bb  mov     rcx, rax; hFile
0x1800017be  call    cs:__imp_CreateFileMappingW
0x1800017c4  mov     [rsp+568h+hObject], rax
0x1800017cc  test    rax, rax
0x1800017cf  jz      loc_180001C4E
0x1800017d5  mov     [rsp+568h+lpBuffer], rbx; dwNumberOfBytesToMap
0x1800017da  xor     r9d, r9d; dwFileOffsetLow
0x1800017dd  xor     r8d, r8d; dwFileOffsetHigh
0x1800017e0  lea     edx, [rsi+2]; dwDesiredAccess
0x1800017e3  mov     rcx, rax; hFileMappingObject
0x1800017e6  call    cs:__imp_MapViewOfFile
0x1800017ec  mov     rdi, rax
0x1800017ef  mov     qword ptr [rsp+568h+var_4D0], rax
0x1800017f7  test    rax, rax
0x1800017fa  jz      loc_180001BC7
0x180001800  xor     edx, edx; lpFileSizeHigh
0x180001802  mov     rcx, r14; hFile
0x180001805  call    cs:__imp_GetFileSize
0x18000180b  mov     r10d, eax
0x18000180e  mov     [rsp+568h+var_518], r10d
0x180001813  mov     edx, eax
0x180001815  add     rdx, rdi
0x180001818  mov     qword ptr [rsp+568h+var_4C0], rdx
0x180001820  cmp     rdx, rdi
0x180001823  jb      loc_180001BC7
0x180001829  sub     edx, edi
0x18000182b  mov     [rsp+568h+var_508], rdx
0x180001830  cmp     edx, 1Ah
0x180001833  jb      loc_180001BC7
0x180001839  mov     qword ptr [rsp+568h+var_4D0+8], rdi
0x180001841  lea     rax, [rsp+568h+Buffer]
0x180001849  mov     qword ptr [rsp+568h+var_4C0+8], rax
0x180001851  movzx   ecx, r15w
0x180001855  sub     ecx, r13d
0x180001858  jz      short loc_18000186C
0x18000185a  sub     ecx, r13d
0x18000185d  jz      loc_18000196A
0x180001863  cmp     ecx, r13d
0x180001866  jnz     loc_180001BB2
0x18000186c  cmp     dword ptr [rdi], 46464952h
0x180001872  jz      loc_180001A69
0x180001878  xor     eax, eax
0x18000187a  mov     dword ptr [rsp+568h+var_508], eax
0x18000187e  mov     word ptr [rsp+568h+var_508+4], ax
0x180001883  cmp     [rdi], bx
0x180001886  jnz     loc_180001BB2
0x18000188c  movzx   eax, word ptr [rdi+2]
0x180001890  sub     ax, r13w
0x180001894  cmp     ax, r13w
0x180001898  ja      loc_180001BB2
0x18000189e  movzx   ecx, word ptr [rdi+4]
0x1800018a2  cmp     cx, r13w
0x1800018a6  jb      loc_180001BB2
0x1800018ac  mov     edx, ebx
0x1800018ae  mov     eax, 100h
0x1800018b3  mov     r9d, [rsp+568h+var_4F8]
0x1800018b8  cmp     r9d, eax
0x1800018bb  cmovnz  edx, r9d
0x1800018bf  mov     r8d, ebx
0x1800018c2  mov     r10d, [rsp+568h+var_4FC]
0x1800018c7  cmp     r10d, eax
0x1800018ca  cmovnz  r8d, r10d
0x1800018ce  mov     eax, [rsp+568h+var_50C]
0x1800018d2  bt      eax, 10h
0x1800018d6  jb      short loc_180001942
0x1800018d8  cmp     r15, 3
0x1800018dc  jz      short loc_1800018E2
0x1800018de  movzx   r13d, si
0x1800018e2  mov     word ptr [rsp+568h+var_508+2], r13w
0x1800018e8  mov     word ptr [rsp+568h+var_508+4], cx
0x1800018ed  mov     word ptr [rsp+568h+var_508], bx
0x1800018f2  movdqu  xmm0, [rsp+568h+var_4D0]
0x1800018fb  movaps  [rsp+568h+var_488], xmm0
0x180001903  movdqu  xmm1, [rsp+568h+var_4C0]
0x18000190c  movaps  [rsp+568h+var_478], xmm1
0x180001914  mov     dword ptr [rsp+568h+lpFilePart], eax
0x180001918  mov     dword ptr [rsp+568h+lpBuffer], r10d
0x18000191d  lea     r8, [rsp+568h+var_508]
0x180001922  mov     rdx, rdi
0x180001925  lea     rcx, [rsp+568h+var_488]
0x18000192d  call    ?IconFromBestImage@@YAPEAUHICON__@@U_FILEINFO@@PEAUtagICONFILEHEADER@@PEAUtagNEWHEADER@@HHI@Z; IconFromBestImage(_FILEINFO,tagICONFILEHEADER *,tagNEWHEADER *,int,int,uint)
0x180001932  mov     [rsp+568h+var_4E8], rax
0x18000193a  mov     r12, rax
0x18000193d  jmp     loc_180001BB2
0x180001942  cmp     cx, r13w
0x180001946  jnz     short loc_1800018D8
0x180001948  movzx   eax, byte ptr [rdi+6]
0x18000194c  cmp     eax, edx
0x18000194e  jnz     loc_180001BB2
0x180001954  movzx   eax, byte ptr [rdi+7]
0x180001958  cmp     eax, r8d
0x18000195b  jnz     loc_180001BB2
0x180001961  mov     eax, [rsp+568h+var_50C]
0x180001965  jmp     loc_1800018D8
0x18000196a  mov     r14, rbx
0x18000196d  mov     [rsp+568h+var_4E0], rbx
0x180001975  mov     r15, rbx
0x180001978  mov     [rsp+568h+var_4D8], rbx
0x180001980  mov     rsi, rbx
0x180001983  mov     [rsp+568h+var_4A8], rbx
0x18000198b  mov     [rsp+568h+var_4F0], rbx
0x180001990  mov     [rsp+568h+var_500], ebx
0x180001994  mov     [rsp+568h+var_510], ebx
0x180001998  mov     eax, ebx
0x18000199a  mov     [rsp+568h+var_514], ebx
0x18000199e  test    [rsp+568h+var_50C], 20000h
0x1800019a6  jnz     loc_180001ADD
0x1800019ac  test    r14, r14
0x1800019af  jnz     short loc_1800019C8
0x1800019b1  mov     r14, rdi
0x1800019b4  mov     [rsp+568h+var_4E0], rdi
0x1800019bc  lea     r15, [rdi+0Eh]
0x1800019c0  mov     [rsp+568h+var_4D8], r15
0x1800019c8  mov     ecx, 4D42h
0x1800019cd  cmp     [r14], cx
0x1800019d1  jnz     loc_180001BB2
0x1800019d7  test    eax, eax
0x1800019d9  jnz     loc_180001AB0
0x1800019df  mov     [rsp+568h+var_510], edx
0x1800019e3  lea     r8, [rsp+568h+var_510]; unsigned int *
0x1800019e8  lea     edx, [rax+0Eh]; unsigned int
0x1800019eb  mov     ecx, r10d; unsigned int
0x1800019ee  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800019f3  test    eax, eax
0x1800019f5  js      loc_180001BB2
0x1800019fb  mov     r13d, [r15+14h]
0x1800019ff  cmp     r13d, 28h ; '('
0x180001a03  cmovb   r13d, ebx
0x180001a07  mov     edx, r10d; unsigned int
0x180001a0a  mov     rcx, r15; struct tagBITMAPINFOHEADER *
0x180001a0d  call    ?CheckImageSize@@YAHPEFAUtagBITMAPINFOHEADER@@K@Z; CheckImageSize(tagBITMAPINFOHEADER *,ulong)
0x180001a12  test    eax, eax
0x180001a14  jz      loc_180001BA8
0x180001a1a  mov     edx, [r14+0Ah]; unsigned int
0x180001a1e  cmp     edx, 1Ah
0x180001a21  jb      loc_180001B5C
0x180001a27  mov     r10d, [rsp+568h+var_518]
0x180001a2c  mov     eax, r10d
0x180001a2f  sub     eax, r13d
0x180001a32  cmp     edx, eax
0x180001a34  ja      loc_180001B5C
0x180001a3a  lea     rcx, [rdx-0Eh]
0x180001a3e  add     rcx, r15
0x180001a41  mov     [rsp+568h+var_4F0], rcx
0x180001a46  lea     r8, [rsp+568h+var_500]; unsigned int *
0x180001a4b  mov     ecx, r10d; unsigned int
0x180001a4e  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x180001a53  test    eax, eax
0x180001a55  jns     loc_180001B61
0x180001a5b  mov     [rsp+568h+var_4F0], rbx
0x180001a60  mov     [rsp+568h+var_500], ebx
0x180001a64  jmp     loc_180001B61
0x180001a69  mov     [rsp+568h+var_518], ebx
0x180001a6d  lea     rax, [rsp+568h+var_518]
0x180001a72  mov     [rsp+568h+lpFilePart], rax; int *
0x180001a77  mov     eax, [rsp+568h+var_50C]
0x180001a7b  mov     dword ptr [rsp+568h+lpBuffer], eax; unsigned int
0x180001a7f  mov     r9d, [rsp+568h+var_4FC]; unsigned int
0x180001a84  mov     r8d, [rsp+568h+var_4F8]; unsigned int
0x180001a89  lea     rdx, [rsp+568h+var_4F0]; unsigned __int16 **
0x180001a8e  lea     rcx, [rsp+568h+var_4D0]; struct _FILEINFO *
0x180001a96  call    ?LoadCursorIconFromFileMap@@YAPEAXPEAU_FILEINFO@@PEAPEAGKKKPEAH@Z; LoadCursorIconFromFileMap(_FILEINFO *,ushort * *,ulong,ulong,ulong,int *)
0x180001a9b  mov     [rsp+568h+var_4E8], rax
0x180001aa3  mov     rdi, qword ptr [rsp+568h+var_4D0]
0x180001aab  jmp     loc_18000193A
0x180001ab0  mov     eax, [rsp+568h+var_510]
0x180001ab4  lea     r10d, [rax+0Eh]
0x180001ab8  mov     [rsp+568h+var_518], r10d
0x180001abd  cmp     r10d, eax
0x180001ac0  jnb     loc_1800019FB
0x180001ac6  mov     rcx, rsi; hMem
0x180001ac9  call    cs:__imp_GlobalUnlock
0x180001acf  mov     rcx, rsi; hMem
0x180001ad2  call    cs:__imp_GlobalFree
0x180001ad8  jmp     loc_180001BB2
0x180001add  call    ?InitializeIcs@@YAHXZ; InitializeIcs(void)
0x180001ae2  test    eax, eax
0x180001ae4  jz      short loc_180001B4B
0x180001ae6  mov     r9d, 2
0x180001aec  lea     r8, [rsp+568h+var_510]
0x180001af1  mov     edx, [rsp+568h+var_518]
0x180001af5  mov     rcx, rdi
0x180001af8  mov     rax, cs:?gpICSProc@@3P6APEAXPEAEKPEAKK@ZEA; void * (*gpICSProc)(uchar *,ulong,ulong *,ulong)
0x180001aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b04  mov     rsi, rax
0x180001b07  mov     [rsp+568h+var_4A8], rax
0x180001b0f  test    rax, rax
0x180001b12  jz      short loc_180001B4B
0x180001b14  mov     rcx, rax; hMem
0x180001b17  call    cs:__imp_GlobalLock
0x180001b1d  mov     r14, rax
0x180001b20  mov     [rsp+568h+var_4E0], rax
0x180001b28  test    rax, rax
0x180001b2b  jz      short loc_180001B42
0x180001b2d  lea     r15, [rax+0Eh]
0x180001b31  mov     [rsp+568h+var_4D8], r15
0x180001b39  mov     eax, r13d
0x180001b3c  mov     [rsp+568h+var_514], eax
0x180001b40  jmp     short loc_180001B4D
0x180001b42  mov     rcx, rsi; hMem
0x180001b45  call    cs:__imp_GlobalFree
0x180001b4b  mov     eax, ebx
0x180001b4d  mov     rdx, [rsp+568h+var_508]
0x180001b52  mov     r10d, [rsp+568h+var_518]
0x180001b57  jmp     loc_1800019AC
0x180001b5c  mov     [rsp+568h+var_4F0], rbx
0x180001b61  lea     rax, [rsp+568h+var_500]
0x180001b66  mov     [rsp+568h+var_528], rax; unsigned int *
0x180001b6b  lea     rax, [rsp+568h+var_4F0]
0x180001b70  mov     [rsp+568h+var_530], rax; char **
0x180001b75  mov     [rsp+568h+hTemplateFile], rbx; struct tagBITMAPINFOHEADER **
0x180001b7a  mov     [rsp+568h+lpFilePart], rbx; struct tagBITMAPINFOHEADER *
0x180001b7f  mov     eax, [rsp+568h+var_50C]
0x180001b83  mov     dword ptr [rsp+568h+lpBuffer], eax; unsigned int
0x180001b87  mov     r9d, [rsp+568h+var_4FC]; unsigned int
0x180001b8c  mov     r8d, [rsp+568h+var_4F8]; unsigned int
0x180001b91  mov     edx, [rsp+568h+var_510]; unsigned int
0x180001b95  mov     rcx, r15; struct tagBITMAPINFOHEADER *
0x180001b98  call    ?ConvertDIBBitmap@@YAPEAUHBITMAP__@@PEFAUtagBITMAPINFOHEADER@@KKKIPEAU2@PEAPEAU2@PEAPEADPEAK@Z; ConvertDIBBitmap(tagBITMAPINFOHEADER *,ulong,ulong,ulong,uint,tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER * *,char * *,ulong *)
0x180001b9d  mov     r12, rax
0x180001ba0  mov     [rsp+568h+var_4E8], rax
0x180001ba8  cmp     [rsp+568h+var_514], ebx
0x180001bac  jnz     loc_180001AC6
0x180001bb2  jmp     short loc_180001BC7
0x180001bb4  xor     r12d, r12d
0x180001bb7  mov     [rsp+568h+var_4E8], r12
0x180001bbf  mov     rdi, qword ptr [rsp+568h+var_4D0]
0x180001bc7  test    rdi, rdi
0x180001bca  jz      short loc_180001BD5
  ... truncated ...
```
