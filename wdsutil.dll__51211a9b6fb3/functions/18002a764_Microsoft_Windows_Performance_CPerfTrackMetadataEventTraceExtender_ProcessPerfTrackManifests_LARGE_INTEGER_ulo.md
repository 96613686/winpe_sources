# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18002a764`
- end: `0x18002ace3`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1407`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029f10`

## callees

- `0x18000abd4`
- `0x180027a64`
- `0x180029c00`
- `0x18002a764`
- `0x18002af78`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!malloc` at `0x18002abf8`
- `msvcrt!malloc` at `0x18002abf8`
- `msvcrt!free` at `0x18002abd3`
- `msvcrt!free` at `0x18002abd3`
- `KERNEL32!CloseHandle` at `0x18002aa35`
- `KERNEL32!CloseHandle` at `0x18002aa67`
- `KERNEL32!CloseHandle` at `0x18002aa35`
- `KERNEL32!CloseHandle` at `0x18002aa67`
- `KERNEL32!GetFileSize` at `0x18002a98b`
- `KERNEL32!GetFileSize` at `0x18002a98b`
- `KERNEL32!CreateFileMappingW` at `0x18002a9b6`
- `KERNEL32!CreateFileMappingW` at `0x18002a9b6`
- `KERNEL32!MapViewOfFileEx` at `0x18002aa0b`
- `KERNEL32!MapViewOfFileEx` at `0x18002aa0b`
- `KERNEL32!CreateFileW` at `0x18002a953`
- `KERNEL32!CreateFileW` at `0x18002a953`
- `KERNEL32!FindFirstFileW` at `0x18002a862`
- `KERNEL32!FindFirstFileW` at `0x18002a862`
- `KERNEL32!FindNextFileW` at `0x18002aa7f`
- `KERNEL32!FindNextFileW` at `0x18002aa7f`
- `KERNEL32!FindClose` at `0x18002aa96`
- `KERNEL32!FindClose` at `0x18002aa96`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // r15
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  unsigned __int16 v12; // r9
  __int64 result; // rax
  WCHAR *v14; // rdx
  HANDLE FirstFileW; // r12
  int v16; // esi
  int v17; // edi
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r8
  __int64 v20; // rdx
  WCHAR *v21; // rax
  unsigned __int16 v22; // r9
  WCHAR *v23; // rcx
  void *v24; // rbx
  HANDLE FileW; // rax
  int Error; // eax
  HANDLE FileMappingW; // r13
  int v28; // eax
  size_t v29; // r12
  char v30; // r13
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // eax
  void *v34; // rax
  _DWORD *v35; // rcx
  int v36; // eax
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-ACh]
  HANDLE v39; // [rsp+58h] [rbp-A8h]
  LPVOID v40; // [rsp+60h] [rbp-A0h]
  DWORD FileSizeHigh[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+7Ch] [rbp-84h]
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch]
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v47; // [rsp+88h] [rbp-78h]
  LPVOID v48; // [rsp+90h] [rbp-70h] BYREF
  size_t Size; // [rsp+98h] [rbp-68h]
  HANDLE v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  int v52; // [rsp+B0h] [rbp-50h]
  HANDLE v53; // [rsp+B8h] [rbp-48h]
  __int64 v54; // [rsp+C0h] [rbp-40h]
  char v55[8]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v56[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v57; // [rsp+D4h] [rbp-2Ch]
  char v58; // [rsp+D5h] [rbp-2Bh]
  __int16 v59; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+E8h] [rbp-18h]
  LPVOID v62; // [rsp+118h] [rbp+18h]
  int v63; // [rsp+120h] [rbp+20h]
  int v64; // [rsp+124h] [rbp+24h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR v67[264]; // [rsp+590h] [rbp+490h] BYREF

  v54 = -2;
  v45 = a4;
  v46 = a3;
  v7 = this;
  v47 = this;
  memset_0(FileName, 0, 0x208u);
  v8 = 2147483646;
  v9 = a5;
  v10 = 260;
  v11 = FileName;
  do
  {
    if ( !v8 )
      break;
    v12 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    *v11++ = v12;
    --v8;
    --v10;
  }
  while ( v10 );
  result = v10 == 0 ? 0x8007007A : 0;
  v14 = v11 - 1;
  if ( v10 )
    v14 = v11;
  *v14 = 0;
  if ( !v10 )
    return result;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( (int)result < 0 )
    return result;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v39 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  v16 = v44;
  v17 = v44;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(v67, 0, 0x208u);
      v18 = 2147483646;
      v19 = a5;
      v20 = 260;
      v21 = v67;
      do
      {
        if ( !v18 )
          break;
        v22 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v21++ = v22;
        --v18;
        --v20;
      }
      while ( v20 );
      v23 = v21 - 1;
      if ( v20 )
        v23 = v21;
      *v23 = 0;
      if ( v20 )
      {
        if ( (int)StringCchCatW(v67, 0x104u, FindFileData.cFileName) >= 0 )
        {
          v24 = 0;
          v53 = 0;
          v40 = 0;
          v48 = 0;
          v50 = 0;
          FileW = CreateFileW(v67, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            Error = ATL::AtlHresultFromLastError();
          }
          else
          {
            v24 = FileW;
            v53 = FileW;
            Error = 0;
          }
          if ( Error < 0 )
          {
LABEL_30:
            ATL::CAtlFileMappingBase::~CAtlFileMappingBase((ATL::CAtlFileMappingBase *)&v48);
            if ( !v24 )
              continue;
LABEL_31:
            CloseHandle(v24);
LABEL_32:
            FirstFileW = v39;
            continue;
          }
          *(_QWORD *)FileSizeHigh = 0;
          FileSizeHigh[0] = GetFileSize(v24, &FileSizeHigh[1]);
          FileMappingW = CreateFileMappingW(v24, 0, 2u, FileSizeHigh[1], FileSizeHigh[0], 0);
          v50 = FileMappingW;
          if ( FileMappingW )
          {
            v29 = *(_QWORD *)FileSizeHigh;
            Size = *(_QWORD *)FileSizeHigh;
            v52 = 4;
            v51 = 0;
            v40 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, *(SIZE_T *)FileSizeHigh, 0);
            v48 = v40;
            if ( v40 )
              goto LABEL_37;
            v38 = ATL::AtlHresultFromLastError();
            CloseHandle(FileMappingW);
            v50 = 0;
            v28 = v38;
          }
          else
          {
            v28 = ATL::AtlHresultFromLastError();
            v29 = Size;
          }
          if ( v28 < 0 )
          {
LABEL_29:
            FirstFileW = v39;
            goto LABEL_30;
          }
LABEL_37:
          if ( v29 > 0x100000 )
            goto LABEL_29;
          v37 = 0;
          if ( (unsigned int)v29 >= 4 )
          {
            v30 = *((_BYTE *)v7 + 104);
            if ( !v30 )
            {
              v33 = v29 - 4;
              v38 = v29 - 4;
              if ( *((_DWORD *)v7 + 34) < (unsigned int)(v29 - 4) )
              {
                free(*((void **)v7 + 16));
                *((_QWORD *)v7 + 16) = 0;
                *((_DWORD *)v7 + 34) = 0;
                v34 = malloc((unsigned int)v29);
                *((_QWORD *)v7 + 16) = v34;
                if ( !v34 )
                  goto LABEL_47;
                *((_DWORD *)v7 + 34) = v29;
                v33 = v38;
              }
              v35 = (_DWORD *)*((_QWORD *)v7 + 16);
              if ( !*((_QWORD *)v7 + 11)
                || (v36 = (*((__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _DWORD *, unsigned int, int, unsigned int *, _QWORD))v7
                           + 11))(
                            258,
                            v40,
                            (unsigned int)v29,
                            v35 + 1,
                            v33,
                            4096,
                            &v37,
                            *((_QWORD *)v7 + 14)),
                    v35 = (_DWORD *)*((_QWORD *)v7 + 16),
                    v36)
                || v37 > v38 )
              {
                v30 = 1;
              }
              v37 += 4;
              *v35 = v29;
              if ( !v30 )
              {
                LODWORD(v29) = v37;
                v40 = (LPVOID)*((_QWORD *)v7 + 16);
                v42 = v40;
                v44 = v17;
                v31 = 56;
                v32 = v37;
LABEL_41:
                v43 = v29;
                if ( (unsigned __int64)(v32 + 48) <= 0xFFB8 )
                {
                  if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                                    (char *)v7 + v31,
                                    v55,
                                    &v42) == *(_QWORD *)((char *)v7 + v31) )
                  {
                    memset_0(v56, 0, 0x58u);
                    v56[0] = v45;
                    v60 = a2;
                    v61 = *(_OWORD *)PerfTrackMetadataGuid;
                    v57 = 33 - (v30 != 0);
                    v59 = 0;
                    v58 = 0;
                    v62 = v40;
                    v63 = v29;
                    v64 = v46;
                    v7 = v47;
                    (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v47 + 2) + 192LL))(
                      *((_QWORD *)v47 + 2),
                      v56,
                      0,
                      0);
                  }
                  else
                  {
                    v7 = v47;
                  }
                }
LABEL_47:
                ATL::CAtlFileMappingBase::~CAtlFileMappingBase((ATL::CAtlFileMappingBase *)&v48);
                if ( !v24 )
                  goto LABEL_32;
                goto LABEL_31;
              }
            }
          }
          else
          {
            v30 = 1;
          }
          v42 = v40;
          v44 = v16;
          v31 = 40;
          v32 = (unsigned int)v29;
          goto LABEL_41;
        }
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
  return 0;
}

```

## disassembly

```asm
0x18002a764  push    rbp
0x18002a766  push    rbx
0x18002a767  push    rsi
0x18002a768  push    rdi
0x18002a769  push    r12
0x18002a76b  push    r13
0x18002a76d  push    r14
0x18002a76f  push    r15
0x18002a771  lea     rbp, [rsp-6B8h]
0x18002a779  sub     rsp, 7B8h
0x18002a780  mov     [rbp+6F0h+var_730], 0FFFFFFFFFFFFFFFEh
0x18002a788  mov     rax, cs:__security_cookie
0x18002a78f  xor     rax, rsp
0x18002a792  mov     [rbp+6F0h+var_50], rax
0x18002a799  mov     [rbp+6F0h+var_770], r9d
0x18002a79d  mov     [rbp+6F0h+var_76C], r8d
0x18002a7a1  mov     r14, rdx
0x18002a7a4  mov     r15, rcx
0x18002a7a7  mov     [rbp+6F0h+var_768], rcx
0x18002a7ab  mov     rbx, [rbp+6F0h+arg_28]
0x18002a7b2  xor     edx, edx; Val
0x18002a7b4  mov     r8d, 208h; Size
0x18002a7ba  lea     rcx, [rbp+6F0h+FileName]; void *
0x18002a7c1  call    memset_0
0x18002a7c6  mov     eax, 7FFFFFFEh
0x18002a7cb  mov     rdx, [rbp+6F0h+arg_20]
0x18002a7d2  mov     r8d, 104h
0x18002a7d8  lea     rcx, [rbp+6F0h+FileName]
0x18002a7df  xor     r13d, r13d
0x18002a7e2  test    rax, rax
0x18002a7e5  jz      short loc_18002A806
0x18002a7e7  movzx   r9d, word ptr [rdx]
0x18002a7eb  test    r9w, r9w
0x18002a7ef  jz      short loc_18002A806
0x18002a7f1  add     rdx, 2
0x18002a7f5  mov     [rcx], r9w
0x18002a7f9  add     rcx, 2
0x18002a7fd  dec     rax
0x18002a800  sub     r8, 1
0x18002a804  jnz     short loc_18002A7E2
0x18002a806  mov     rax, r8
0x18002a809  neg     rax
0x18002a80c  sbb     eax, eax
0x18002a80e  not     eax
0x18002a810  and     eax, 8007007Ah
0x18002a815  lea     rdx, [rcx-2]
0x18002a819  test    r8, r8
0x18002a81c  cmovnz  rdx, rcx
0x18002a820  mov     [rdx], r13w
0x18002a824  jz      loc_18002AAA4
0x18002a82a  mov     r8, rbx; unsigned __int16 *
0x18002a82d  mov     edx, 104h; unsigned __int64
0x18002a832  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18002a839  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a83e  test    eax, eax
0x18002a840  js      loc_18002AAA4
0x18002a846  xor     edx, edx; Val
0x18002a848  mov     r8d, 250h; Size
0x18002a84e  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x18002a852  call    memset_0
0x18002a857  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002a85b  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x18002a862  call    cs:__imp_FindFirstFileW
0x18002a869  nop     dword ptr [rax+rax+00h]
0x18002a86e  mov     r12, rax
0x18002a871  mov     [rsp+7F0h+var_798], rax
0x18002a876  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a87a  jz      loc_18002AAA2
0x18002a880  mov     esi, [rsp+7F0h+var_774]
0x18002a884  mov     edi, [rsp+7F0h+var_774]
0x18002a888  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x18002a88c  jnz     loc_18002AA78
0x18002a892  xor     edx, edx; Val
0x18002a894  mov     r8d, 208h; Size
0x18002a89a  lea     rcx, [rbp+6F0h+var_260]; void *
0x18002a8a1  call    memset_0
0x18002a8a6  mov     ecx, 7FFFFFFEh
0x18002a8ab  mov     r8, [rbp+6F0h+arg_20]
0x18002a8b2  mov     edx, 104h
0x18002a8b7  lea     rax, [rbp+6F0h+var_260]
0x18002a8be  test    rcx, rcx
0x18002a8c1  jz      short loc_18002A8E2
0x18002a8c3  movzx   r9d, word ptr [r8]
0x18002a8c7  test    r9w, r9w
0x18002a8cb  jz      short loc_18002A8E2
0x18002a8cd  add     r8, 2
0x18002a8d1  mov     [rax], r9w
0x18002a8d5  add     rax, 2
0x18002a8d9  dec     rcx
0x18002a8dc  sub     rdx, 1
0x18002a8e0  jnz     short loc_18002A8BE
0x18002a8e2  lea     rcx, [rax-2]
0x18002a8e6  test    rdx, rdx
0x18002a8e9  cmovnz  rcx, rax
0x18002a8ed  mov     [rcx], r13w
0x18002a8f1  jz      loc_18002AA78
0x18002a8f7  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002a8fb  mov     edx, 104h; unsigned __int64
0x18002a900  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18002a907  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a90c  test    eax, eax
0x18002a90e  js      loc_18002AA78
0x18002a914  mov     rbx, r13
0x18002a917  mov     [rbp+6F0h+var_738], rbx
0x18002a91b  mov     rax, r13
0x18002a91e  mov     [rsp+7F0h+var_790], rax
0x18002a923  mov     [rbp+6F0h+var_760], rax
0x18002a927  mov     [rbp+6F0h+var_750], r13
0x18002a92b  mov     [rsp+7F0h+hTemplateFile], r13; hTemplateFile
0x18002a930  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002a938  mov     [rsp+7F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002a940  xor     r9d, r9d; lpSecurityAttributes
0x18002a943  mov     edx, 80000000h; dwDesiredAccess
0x18002a948  lea     r8d, [r9+1]; dwShareMode
0x18002a94c  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x18002a953  call    cs:__imp_CreateFileW
0x18002a95a  nop     dword ptr [rax+rax+00h]
0x18002a95f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a963  jnz     short loc_18002A96C
0x18002a965  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002a96a  jmp     short loc_18002A976
0x18002a96c  mov     rbx, rax
0x18002a96f  mov     [rbp+6F0h+var_738], rax
0x18002a973  mov     eax, r13d
0x18002a976  test    eax, eax
0x18002a978  js      loc_18002AA55
0x18002a97e  mov     qword ptr [rsp+7F0h+FileSizeHigh], r13
0x18002a983  lea     rdx, [rsp+7F0h+FileSizeHigh+4]; lpFileSizeHigh
0x18002a988  mov     rcx, rbx; hFile
0x18002a98b  call    cs:__imp_GetFileSize
0x18002a992  nop     dword ptr [rax+rax+00h]
0x18002a997  mov     [rsp+7F0h+FileSizeHigh], eax
0x18002a99b  mov     r9, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002a9a0  shr     r9, 20h; dwMaximumSizeHigh
0x18002a9a4  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], r13; lpName
0x18002a9a9  mov     [rsp+7F0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18002a9ad  xor     edx, edx; lpFileMappingAttributes
0x18002a9af  lea     r8d, [rdx+2]; flProtect
0x18002a9b3  mov     rcx, rbx; hFile
0x18002a9b6  call    cs:__imp_CreateFileMappingW
0x18002a9bd  nop     dword ptr [rax+rax+00h]
0x18002a9c2  mov     r13, rax
0x18002a9c5  mov     [rbp+6F0h+var_750], rax
0x18002a9c9  test    rax, rax
0x18002a9cc  jnz     short loc_18002A9D9
0x18002a9ce  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002a9d3  mov     r12, [rbp+6F0h+Size]
0x18002a9d7  jmp     short loc_18002AA4C
0x18002a9d9  mov     r12, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002a9de  mov     [rbp+6F0h+Size], r12
0x18002a9e2  mov     eax, 4
0x18002a9e7  mov     [rbp+6F0h+var_740], eax
0x18002a9ea  mov     [rbp+6F0h+var_748], 0
0x18002a9f2  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], 0; lpBaseAddress
0x18002a9fb  mov     qword ptr [rsp+7F0h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x18002aa00  xor     r9d, r9d; dwFileOffsetLow
0x18002aa03  xor     r8d, r8d; dwFileOffsetHigh
0x18002aa06  mov     edx, eax; dwDesiredAccess
0x18002aa08  mov     rcx, r13; hFileMappingObject
0x18002aa0b  call    cs:__imp_MapViewOfFileEx
0x18002aa12  nop     dword ptr [rax+rax+00h]
0x18002aa17  mov     [rsp+7F0h+var_790], rax
0x18002aa1c  mov     [rbp+6F0h+var_760], rax
0x18002aa20  test    rax, rax
0x18002aa23  jnz     loc_18002AAC8
0x18002aa29  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002aa2e  mov     [rsp+7F0h+var_79C], eax
0x18002aa32  mov     rcx, r13; hObject
0x18002aa35  call    cs:__imp_CloseHandle
0x18002aa3c  nop     dword ptr [rax+rax+00h]
0x18002aa41  xor     r13d, r13d
0x18002aa44  mov     [rbp+6F0h+var_750], r13
0x18002aa48  mov     eax, [rsp+7F0h+var_79C]
0x18002aa4c  test    eax, eax
0x18002aa4e  jns     short loc_18002AACB
0x18002aa50  mov     r12, [rsp+7F0h+var_798]
0x18002aa55  lea     rcx, [rbp+6F0h+var_760]; this
0x18002aa59  call    ??1CAtlFileMappingBase@ATL@@QEAA@XZ; ATL::CAtlFileMappingBase::~CAtlFileMappingBase(void)
0x18002aa5e  nop
0x18002aa5f  test    rbx, rbx
0x18002aa62  jz      short loc_18002AA78
0x18002aa64  mov     rcx, rbx; hObject
0x18002aa67  call    cs:__imp_CloseHandle
0x18002aa6e  nop     dword ptr [rax+rax+00h]
0x18002aa73  mov     r12, [rsp+7F0h+var_798]
0x18002aa78  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002aa7c  mov     rcx, r12; hFindFile
0x18002aa7f  call    cs:__imp_FindNextFileW
0x18002aa86  nop     dword ptr [rax+rax+00h]
0x18002aa8b  test    eax, eax
0x18002aa8d  jnz     loc_18002A888
0x18002aa93  mov     rcx, r12; hFindFile
0x18002aa96  call    cs:__imp_FindClose
0x18002aa9d  nop     dword ptr [rax+rax+00h]
0x18002aaa2  xor     eax, eax
0x18002aaa4  mov     rcx, [rbp+6F0h+var_50]
0x18002aaab  xor     rcx, rsp; StackCookie
0x18002aaae  call    __security_check_cookie
0x18002aab3  add     rsp, 7B8h
0x18002aaba  pop     r15
0x18002aabc  pop     r14
0x18002aabe  pop     r13
0x18002aac0  pop     r12
0x18002aac2  pop     rdi
0x18002aac3  pop     rsi
0x18002aac4  pop     rbx
0x18002aac5  pop     rbp
0x18002aac6  retn
0x18002aac8  xor     r13d, r13d
0x18002aacb  cmp     r12, 100000h
0x18002aad2  ja      loc_18002AA50
0x18002aad8  mov     [rsp+7F0h+var_7A0], 0
0x18002aae0  cmp     r12d, 4
0x18002aae4  jnb     loc_18002ABAD
0x18002aaea  mov     r13b, 1
0x18002aaed  mov     rax, [rsp+7F0h+var_790]
0x18002aaf2  mov     [rsp+7F0h+var_780], rax
0x18002aaf7  mov     [rsp+7F0h+var_774], esi
0x18002aafb  mov     ecx, 28h ; '('
0x18002ab00  mov     eax, r12d
0x18002ab03  mov     [rsp+7F0h+var_778], r12d
0x18002ab08  add     rax, 30h ; '0'
0x18002ab0c  cmp     rax, 0FFB8h
0x18002ab12  ja      loc_18002AC10
0x18002ab18  add     r15, rcx
0x18002ab1b  lea     r8, [rsp+7F0h+var_780]
0x18002ab20  lea     rdx, [rbp+6F0h+var_728]
0x18002ab24  mov     rcx, r15
0x18002ab27  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@2@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x18002ab2c  mov     rcx, [r15]
0x18002ab2f  cmp     [rax], rcx
0x18002ab32  jnz     loc_18002ACCD
0x18002ab38  xor     edx, edx; Val
0x18002ab3a  lea     r8d, [rdx+58h]; Size
0x18002ab3e  lea     rcx, [rbp+6F0h+var_720]; void *
0x18002ab42  call    memset_0
0x18002ab47  mov     eax, [rbp+6F0h+var_770]
0x18002ab4a  mov     [rbp+6F0h+var_720], ax
0x18002ab4e  mov     [rbp+6F0h+var_710], r14
0x18002ab52  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid
0x18002ab59  movdqu  [rbp+6F0h+var_708], xmm0
0x18002ab5e  neg     r13b
0x18002ab61  sbb     al, al
0x18002ab63  add     al, 21h ; '!'
0x18002ab65  mov     [rbp+6F0h+var_71C], al
0x18002ab68  xor     r13d, r13d
0x18002ab6b  mov     [rbp+6F0h+var_71A], r13w
0x18002ab70  mov     [rbp+6F0h+var_71B], r13b
0x18002ab74  mov     rax, [rsp+7F0h+var_790]
0x18002ab79  mov     [rbp+6F0h+var_6D8], rax
0x18002ab7d  mov     [rbp+6F0h+var_6D0], r12d
0x18002ab81  mov     eax, [rbp+6F0h+var_76C]
0x18002ab84  mov     [rbp+6F0h+var_6CC], eax
0x18002ab87  mov     r15, [rbp+6F0h+var_768]
0x18002ab8b  mov     rcx, [r15+10h]
0x18002ab8f  mov     rax, [rcx]
0x18002ab92  xor     r9d, r9d
0x18002ab95  xor     r8d, r8d
0x18002ab98  lea     rdx, [rbp+6F0h+var_720]
0x18002ab9c  mov     rax, [rax+0C0h]
0x18002aba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aba8  jmp     loc_18002ACD4
0x18002abad  mov     r13b, [r15+68h]
0x18002abb1  test    r13b, r13b
0x18002abb4  jnz     loc_18002AAED
0x18002abba  lea     eax, [r12-4]
0x18002abbf  mov     [rsp+7F0h+var_79C], eax
0x18002abc3  cmp     [r15+88h], eax
0x18002abca  jnb     short loc_18002AC36
0x18002abcc  mov     rcx, [r15+80h]; Block
0x18002abd3  call    cs:__imp_free
0x18002abda  nop     dword ptr [rax+rax+00h]
0x18002abdf  mov     qword ptr [r15+80h], 0
0x18002abea  mov     dword ptr [r15+88h], 0
0x18002abf5  mov     ecx, r12d; Size
0x18002abf8  call    cs:__imp_malloc
0x18002abff  nop     dword ptr [rax+rax+00h]
0x18002ac04  mov     [r15+80h], rax
0x18002ac0b  test    rax, rax
0x18002ac0e  jnz     short loc_18002AC2B
0x18002ac10  lea     rcx, [rbp+6F0h+var_760]; this
0x18002ac14  call    ??1CAtlFileMappingBase@ATL@@QEAA@XZ; ATL::CAtlFileMappingBase::~CAtlFileMappingBase(void)
0x18002ac19  nop
0x18002ac1a  xor     r13d, r13d
0x18002ac1d  test    rbx, rbx
0x18002ac20  jnz     loc_18002AA64
0x18002ac26  jmp     loc_18002AA73
0x18002ac2b  mov     [r15+88h], r12d
0x18002ac32  mov     eax, [rsp+7F0h+var_79C]
0x18002ac36  mov     rcx, [r15+80h]
0x18002ac3d  cmp     qword ptr [r15+58h], 0
0x18002ac42  jz      short loc_18002AC92
0x18002ac44  lea     r9, [rcx+4]
0x18002ac48  mov     ecx, 102h
0x18002ac4d  mov     rdx, [r15+70h]
0x18002ac51  mov     [rsp+7F0h+var_7B8], rdx
0x18002ac56  lea     rdx, [rsp+7F0h+var_7A0]
0x18002ac5b  mov     [rsp+7F0h+hTemplateFile], rdx
0x18002ac60  mov     [rsp+7F0h+dwFlagsAndAttributes], 1000h
0x18002ac68  mov     [rsp+7F0h+dwCreationDisposition], eax
  ... truncated ...
```
