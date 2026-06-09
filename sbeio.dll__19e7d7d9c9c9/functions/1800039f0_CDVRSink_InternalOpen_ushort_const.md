# CDVRSink::InternalOpen(ushort const *)

- ea: `0x1800039f0`
- end: `0x1800043bd`
- name: `?InternalOpen@CDVRSink@@MEAAJPEBG@Z`
- size: `2509`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x180001f1c`
- `0x1800024c4`
- `0x1800027c4`
- `0x1800039f0`
- `0x180004b7c`
- `0x180004cb8`
- `0x180005060`
- `0x1800050cc`
- `0x180009820`
- `0x18002b010`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180003fa2`
- `KERNEL32!MapViewOfFile` at `0x180003fa2`
- `KERNEL32!CreateFileMappingW` at `0x180003f39`
- `KERNEL32!CreateFileMappingW` at `0x180003f39`
- `KERNEL32!CloseHandle` at `0x180003ded`
- `KERNEL32!CloseHandle` at `0x180004322`
- `KERNEL32!CloseHandle` at `0x180003ded`
- `KERNEL32!CloseHandle` at `0x180004322`
- `KERNEL32!GetLastError` at `0x180003acd`
- `KERNEL32!GetLastError` at `0x180003b69`
- `KERNEL32!GetLastError` at `0x180003e33`
- `KERNEL32!GetLastError` at `0x180003f46`
- `KERNEL32!GetLastError` at `0x1800041c0`
- `KERNEL32!GetLastError` at `0x180004306`
- `KERNEL32!GetLastError` at `0x180004355`
- `KERNEL32!GetLastError` at `0x18002a3d4`
- `KERNEL32!GetLastError` at `0x180003acd`
- `KERNEL32!GetLastError` at `0x180003b69`
- `KERNEL32!GetLastError` at `0x180003e33`
- `KERNEL32!GetLastError` at `0x180003f46`
- `KERNEL32!GetLastError` at `0x1800041c0`
- `KERNEL32!GetLastError` at `0x180004306`
- `KERNEL32!GetLastError` at `0x180004355`
- `KERNEL32!GetLastError` at `0x18002a3d4`
- `KERNEL32!GetFileInformationByHandle` at `0x180003ac3`
- `KERNEL32!GetFileInformationByHandle` at `0x180003ac3`
- `KERNEL32!ReleaseMutex` at `0x18000434b`
- `KERNEL32!ReleaseMutex` at `0x18002a3ca`
- `KERNEL32!ReleaseMutex` at `0x18000434b`
- `KERNEL32!ReleaseMutex` at `0x18002a3ca`
- `KERNEL32!CreateFileW` at `0x180003d91`
- `KERNEL32!CreateFileW` at `0x180003e1e`
- `KERNEL32!CreateFileW` at `0x1800041a7`
- `KERNEL32!CreateFileW` at `0x180003d91`
- `KERNEL32!CreateFileW` at `0x180003e1e`
- `KERNEL32!CreateFileW` at `0x1800041a7`
- `KERNEL32!LeaveCriticalSection` at `0x180004378`
- `KERNEL32!LeaveCriticalSection` at `0x18002a3f9`
- `KERNEL32!LeaveCriticalSection` at `0x180004378`
- `KERNEL32!LeaveCriticalSection` at `0x18002a3f9`
- `KERNEL32!WriteFile` at `0x180003dce`
- `KERNEL32!WriteFile` at `0x18000420e`
- `KERNEL32!WriteFile` at `0x180003dce`
- `KERNEL32!WriteFile` at `0x18000420e`
- `KERNEL32!GetFullPathNameW` at `0x180003b5f`
- `KERNEL32!GetFullPathNameW` at `0x180003ba3`
- `KERNEL32!GetFullPathNameW` at `0x180003b5f`
- `KERNEL32!GetFullPathNameW` at `0x180003ba3`
- `KERNEL32!EnterCriticalSection` at `0x180003a54`
- `KERNEL32!EnterCriticalSection` at `0x180003a54`

## pseudocode

```c
__int64 __fastcall CDVRSink::InternalOpen(CDVRSink *this, const unsigned __int16 *a2)
{
  WCHAR *v4; // r15
  WCHAR *v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  signed int v7; // edi
  signed int v8; // eax
  int v9; // ebx
  const unsigned __int16 *v10; // r8
  signed int v11; // eax
  int v12; // edi
  const unsigned __int16 *v13; // r14
  int v14; // eax
  int v15; // r11d
  unsigned int v16; // edx
  unsigned int v17; // r15d
  unsigned __int64 v18; // rbx
  WCHAR *v19; // rax
  int v20; // eax
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  HANDLE FileW; // rax
  void *v24; // rbx
  HANDLE v25; // rcx
  enum _ACCESS_MODE v26; // r8d
  signed int v27; // eax
  ULONG v28; // eax
  struct _SECURITY_ATTRIBUTES *v29; // r10
  signed int v30; // ebx
  void *v31; // rcx
  LPVOID v32; // rax
  __int64 v33; // r10
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rdx
  HANDLE v38; // rcx
  signed int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  signed int LastError; // eax
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  enum _ACCESS_MODE dwCreationDisposition; // [rsp+20h] [rbp-5B8h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-580h] BYREF
  int v48; // [rsp+60h] [rbp-578h]
  WCHAR Buffer; // [rsp+64h] [rbp-574h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-570h] BYREF
  int v51; // [rsp+6Ch] [rbp-56Ch] BYREF
  unsigned __int64 v52; // [rsp+70h] [rbp-568h] BYREF
  void *v53; // [rsp+78h] [rbp-560h] BYREF
  LPWSTR FilePart; // [rsp+80h] [rbp-558h] BYREF
  struct _ACL *v55[2]; // [rsp+88h] [rbp-550h] BYREF
  _QWORD v56[3]; // [rsp+98h] [rbp-540h] BYREF
  int v57; // [rsp+B0h] [rbp-528h]
  int v58; // [rsp+B4h] [rbp-524h]
  __int128 v59; // [rsp+B8h] [rbp-520h] BYREF
  __int64 v60; // [rsp+C8h] [rbp-510h]
  WCHAR *v61; // [rsp+D0h] [rbp-508h]
  unsigned __int16 *v62; // [rsp+D8h] [rbp-500h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+E0h] [rbp-4F8h] BYREF
  _BYTE v64[512]; // [rsp+120h] [rbp-4B8h] BYREF
  WCHAR Name[56]; // [rsp+320h] [rbp-2B8h] BYREF
  WCHAR v66[264]; // [rsp+390h] [rbp-248h] BYREF

  v55[1] = (struct _ACL *)this;
  memset_0(v64, 0, 0x1F8u);
  v4 = 0;
  v5 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  memset(&FileInformation, 0, sizeof(FileInformation));
  FilePart = 0;
  Buffer = 0;
  v52 = 0;
  v7 = CWMFileSinkV1::InternalOpen(this, a2);
  if ( v7 < 0 )
    goto LABEL_79;
  *((_DWORD *)this + 2343) = 2;
  if ( GetFileInformationByHandle(*((HANDLE *)this + 24), &FileInformation) )
  {
    v9 = *((_DWORD *)this + 2400);
    v10 = L"Global\\MSDVRMM_%u_%u_%u";
    if ( !v9 )
      v10 = L"MSDVRMM_%u_%u_%u";
    v7 = StringCchPrintfW(
           Name,
           0x32u,
           v10,
           FileInformation.dwVolumeSerialNumber,
           FileInformation.nFileIndexHigh,
           FileInformation.nFileIndexLow);
    if ( v7 < 0 )
      goto LABEL_78;
    if ( GetFullPathNameW(*((LPCWSTR *)this + 25), 0, &Buffer, 0)
      && GetFullPathNameW(*((LPCWSTR *)this + 25), 0x104u, v66, &FilePart) )
    {
      v13 = (WCHAR *)((char *)Name + (v9 != 0 ? 0xE : 0));
      *FilePart = 0;
      v14 = StringCchLengthW(v66, 0x104u, &v52);
      if ( v14 < 0 )
        goto LABEL_16;
      v14 = StringCchLengthW(v13, (-(__int64)(v9 != 0) & 0xFFFFFFFFFFFFFFF9uLL) + 50, &v52);
      if ( v14 < 0 )
        goto LABEL_16;
      v16 = v52 + v15 + v52;
      if ( v16 < (int)v52 + v15 )
      {
        v7 = -2147024362;
        goto LABEL_78;
      }
      v17 = v16 + 1;
      v18 = v16 + 1;
      v19 = (WCHAR *)operator new[](saturated_mul(v18, 2u));
      lpFileName = v19;
      v61 = v19;
      if ( !v19 )
        goto LABEL_21;
      v20 = StringCchPrintfW(v19, v18, L"%ls%ls", v66, v13);
      if ( v20 < 0 )
      {
LABEL_24:
        v7 = v20;
        goto LABEL_22;
      }
      v21 = (unsigned __int16 *)operator new[](saturated_mul(v17 + 4, 2u));
      v5 = v21;
      v62 = v21;
      if ( !v21 )
      {
LABEL_21:
        v7 = -2147024882;
LABEL_22:
        v4 = (WCHAR *)lpFileName;
        goto LABEL_78;
      }
      if ( *((_DWORD *)this + 2342) || *((_DWORD *)this + 2338) == -1 )
      {
        *v21 = 0;
      }
      else
      {
        v20 = StringCchPrintfW(v21, v17 + 4, L"%ls%ls.tmp", v66, v13);
        if ( v20 < 0 )
          goto LABEL_24;
      }
      v22 = *((_QWORD *)this + 1199);
      if ( v22 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 24LL))(v22, (char *)this + 9312);
        if ( v20 < 0 )
          goto LABEL_24;
      }
      *((_QWORD *)this + 1160) = v64;
      v20 = (*(__int64 (__fastcall **)(CDVRSink *, _BYTE *, char *))(*(_QWORD *)this + 344LL))(
              this,
              v64,
              (char *)this + 9640);
      if ( v20 < 0 )
        goto LABEL_24;
      v4 = (WCHAR *)lpFileName;
      FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 1u, 0x8000106u, 0);
      v24 = FileW;
      if ( FileW == (HANDLE)-1LL )
        goto LABEL_10;
      NumberOfBytesWritten = 0;
      if ( !WriteFile(FileW, v64, 0x1F8u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 504 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        CloseHandle(v24);
        goto LABEL_78;
      }
      CloseHandle(v24);
      v25 = CreateFileW(lpFileName, 0xC0010000, 7u, 0, 3u, 0x14000000u, 0);
      *((_QWORD *)this + 1161) = v25;
      if ( v25 == (HANDLE)-1LL )
      {
        v27 = GetLastError();
        v7 = v27;
        if ( v27 > 0 )
          v7 = (unsigned __int16)v27 | 0x80070000;
        *((_QWORD *)this + 1161) = 0;
        goto LABEL_78;
      }
      v55[0] = 0;
      v53 = 0;
      v59 = 0;
      v60 = 0;
      v28 = *((_DWORD *)this + 2441);
      if ( v28 )
      {
        v11 = CreateACL(v28, *((void ***)this + 1222), v26, 0xF0007u, dwCreationDisposition, 7u, v55, &v53);
        if ( v11 )
        {
          if ( v11 <= 0 )
          {
            v7 = v11;
            goto LABEL_78;
          }
          goto LABEL_11;
        }
        LODWORD(v59) = 24;
        *((_QWORD *)&v59 + 1) = v53;
        LODWORD(v60) = 0;
        v25 = (HANDLE)*((_QWORD *)this + 1161);
      }
      v29 = (struct _SECURITY_ATTRIBUTES *)&v59;
      if ( !*((_DWORD *)this + 2441) )
        v29 = 0;
      *((_QWORD *)this + 1162) = CreateFileMappingW(
                                   v25,
                                   v29,
                                   4u,
                                   0,
                                   *((_DWORD *)this + 2336) * *((_DWORD *)this + 2337),
                                   Name);
      v30 = GetLastError();
      if ( *((_DWORD *)this + 2441) )
        FreeSecurityDescriptors(v55, &v53);
      v31 = (void *)*((_QWORD *)this + 1162);
      if ( !v31 || v30 == 183 )
      {
        if ( v30 <= 0 )
        {
          v7 = v30;
          goto LABEL_78;
        }
        v12 = (unsigned __int16)v30;
LABEL_12:
        v7 = v12 | 0x80070000;
        goto LABEL_78;
      }
      v32 = MapViewOfFile(v31, 0xF001Fu, 0, 0, (unsigned int)(*((_DWORD *)this + 2336) * *((_DWORD *)this + 2337)));
      *((_QWORD *)this + 1160) = v32;
      if ( !v32 )
      {
        *((_QWORD *)this + 1160) = v64;
        goto LABEL_10;
      }
      *((_DWORD *)this + 2344) = 1;
      v33 = *((_QWORD *)this + 1199);
      if ( v33 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64, _DWORD))(*(_QWORD *)v33 + 32LL))(
                v33,
                a2,
                *((unsigned int *)this + 53),
                4,
                *((_DWORD *)this + 2400));
        if ( v14 < 0 )
          goto LABEL_16;
      }
      v34 = *((_QWORD *)this + 1160);
      if ( *((_DWORD *)this + 2338) == -1 )
      {
        *(_DWORD *)(v34 + 396) = 0;
        *(_DWORD *)(*((_QWORD *)this + 1160) + 400LL) = 0;
        *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL) = 0;
        *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL) = 0;
        *((_DWORD *)this + 2346) = 0;
        goto LABEL_78;
      }
      *(_DWORD *)(v34 + 388) = 504;
      *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL) = *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL)
                                                    + *((_DWORD *)this + 2372);
      *(_DWORD *)(*((_QWORD *)this + 1160) + 396LL) = *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL);
      v51 = 0;
      if ( (*(int (__fastcall **)(char *, _QWORD, int *))(*((_QWORD *)this + 1159) + 56LL))(
             (char *)this + 9272,
             *((unsigned int *)this + 2337),
             &v51) < 0 )
      {
        v7 = -2147418113;
        goto LABEL_78;
      }
      *(_DWORD *)(*((_QWORD *)this + 1160) + 400LL) = *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL) + 6 * v51;
      *((_QWORD *)this + 1183) = *((_QWORD *)this + 1170);
      v48 = 16843266;
      v35 = *((_QWORD *)this + 1160);
      v36 = *(unsigned int *)(v35 + 392);
      v37 = v35 + *(unsigned int *)(v35 + 388);
      v58 = 16843266;
      v56[0] = v37;
      v56[1] = v37;
      v56[2] = v37 + v36;
      v57 = 1;
      v14 = (*(__int64 (__fastcall **)(char *, _QWORD *))(*((_QWORD *)this + 1174) + 8LL))((char *)this + 9392, v56);
      if ( v14 < 0 )
      {
LABEL_16:
        v7 = v14;
LABEL_78:
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
        goto LABEL_79;
      }
      if ( *((_DWORD *)this + 2342) )
        goto LABEL_68;
      v38 = CreateFileW(v5, 0xC0010000, 5u, 0, 1u, 0xC000106u, 0);
      *((_QWORD *)this + 1163) = v38;
      if ( v38 == (HANDLE)-1LL )
      {
        v39 = GetLastError();
        v7 = v39;
        if ( v39 > 0 )
          v7 = (unsigned __int16)v39 | 0x80070000;
        *((_QWORD *)this + 1163) = 0;
        goto LABEL_78;
      }
      LODWORD(lpFileName) = 0;
      if ( WriteFile(
             v38,
             (LPCVOID)(*((_QWORD *)this + 1160) + *(unsigned int *)(*((_QWORD *)this + 1160) + 388LL)),
             *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL) - *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL),
             (LPDWORD)&lpFileName,
             0) )
      {
        if ( (_DWORD)lpFileName == *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL)
                                 - *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL) )
        {
LABEL_68:
          *(_QWORD *)(*((_QWORD *)this + 1160) + 48LL) += *((unsigned int *)this + 2372);
          *(_QWORD *)(*((_QWORD *)this + 1160) + 56LL) += *((unsigned int *)this + 2372);
          v40 = *((_QWORD *)this + 1160);
          v14 = CDVRIndexObject::SetIndexParams(
                  (CDVRSink *)((char *)this + 9392),
                  (unsigned __int8 *)(v40 + *(unsigned int *)(v40 + 388)),
                  (unsigned __int8 *)(v40 + *(unsigned int *)(v40 + 392)),
                  (unsigned __int8 *)(v40 + *(unsigned int *)(v40 + 400)),
                  (unsigned int *)(v40 + 396),
                  *(_DWORD *)(v40 + 396),
                  (unsigned __int64 *)(v40 + 48),
                  (unsigned __int64 *)(v40 + 56),
                  (unsigned __int64 *)(v40 + 40),
                  *((void **)this + 1163));
          if ( v14 >= 0 )
          {
            v41 = CDVRIndexObject::SetMmsID(
                    (CDVRSink *)((char *)this + 9392),
                    (const struct _GUID *)((char *)this + 9604));
            v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
            if ( v41 >= 0 )
              *((_DWORD *)this + 2346) = 1;
            else
              v7 = v41;
            goto LABEL_79;
          }
          goto LABEL_16;
        }
      }
    }
LABEL_10:
    v11 = GetLastError();
    v7 = v11;
    if ( v11 <= 0 )
      goto LABEL_78;
LABEL_11:
    v12 = (unsigned __int16)v11;
    goto LABEL_12;
  }
  v8 = GetLastError();
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
LABEL_79:
  if ( v7 < 0 )
  {
    if ( *((_DWORD *)this + 2343) == 2 )
      (*(void (__fastcall **)(CDVRSink *))(*(_QWORD *)this + 112LL))(this);
  }
  else
  {
    *((_DWORD *)this + 2343) = 1;
    *((_DWORD *)this + 2345) = 1;
    if ( !ReleaseMutex(*((HANDLE *)this + 1205)) )
      GetLastError();
  }
  LeaveCriticalSection(v6);
  operator delete(v4, v43);
  operator delete(v5, v44);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800039f0  mov     [rsp+arg_10], rbx
0x1800039f5  mov     [rsp+arg_18], rsi
0x1800039fa  push    rdi
0x1800039fb  push    r12
0x1800039fd  push    r13
0x1800039ff  push    r14
0x180003a01  push    r15
0x180003a03  sub     rsp, 5B0h
0x180003a0a  mov     rax, cs:__security_cookie
0x180003a11  xor     rax, rsp
0x180003a14  mov     [rsp+5D8h+var_38], rax
0x180003a1c  mov     r13, rdx
0x180003a1f  mov     rsi, rcx
0x180003a22  mov     [rsp+5D8h+var_548], rcx
0x180003a2a  mov     [rsp+5D8h+var_588], 0
0x180003a32  xor     edx, edx; Val
0x180003a34  mov     r8d, 1F8h; Size
0x180003a3a  lea     rcx, [rsp+5D8h+var_4B8]; void *
0x180003a42  call    memset_0
0x180003a47  xor     r15d, r15d
0x180003a4a  xor     r12d, r12d
0x180003a4d  lea     rbx, [rsi+30h]
0x180003a51  mov     rcx, rbx; lpCriticalSection
0x180003a54  call    cs:__imp_EnterCriticalSection
0x180003a5a  nop
0x180003a5b  xorps   xmm0, xmm0
0x180003a5e  xor     eax, eax
0x180003a60  movups  xmmword ptr [rsp+5D8h+FileInformation.dwFileAttributes], xmm0
0x180003a68  movups  xmmword ptr [rsp+5D8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180003a70  movups  xmmword ptr [rsp+5D8h+FileInformation.nFileSizeHigh], xmm0
0x180003a78  mov     [rsp+5D8h+FileInformation.nFileIndexLow], eax
0x180003a7f  mov     [rsp+5D8h+FilePart], rax
0x180003a87  mov     [rsp+5D8h+Buffer], ax
0x180003a8c  mov     [rsp+5D8h+var_568], rax
0x180003a91  mov     rdx, r13; unsigned __int16 *
0x180003a94  mov     rcx, rsi; this
0x180003a97  call    ?InternalOpen@CWMFileSinkV1@@MEAAJPEBG@Z; CWMFileSinkV1::InternalOpen(ushort const *)
0x180003a9c  mov     edi, eax
0x180003a9e  mov     [rsp+5D8h+var_588], eax
0x180003aa2  test    eax, eax
0x180003aa4  js      loc_18000432C
0x180003aaa  mov     dword ptr [rsi+249Ch], 2
0x180003ab4  lea     rdx, [rsp+5D8h+FileInformation]; lpFileInformation
0x180003abc  mov     rcx, [rsi+0C0h]; hFile
0x180003ac3  call    cs:__imp_GetFileInformationByHandle
0x180003ac9  test    eax, eax
0x180003acb  jnz     short loc_180003AEB
0x180003acd  call    cs:__imp_GetLastError
0x180003ad3  mov     edi, eax
0x180003ad5  test    eax, eax
0x180003ad7  jle     short loc_180003AE2
0x180003ad9  movzx   edi, ax
0x180003adc  or      edi, 80070000h
0x180003ae2  mov     [rsp+5D8h+var_588], edi
0x180003ae6  jmp     loc_18000432C
0x180003aeb  mov     ebx, [rsi+2580h]
0x180003af1  lea     rax, aMsdvrmmUUU; "MSDVRMM_%u_%u_%u"
0x180003af8  lea     r8, aGlobalMsdvrmmU; "Global\\MSDVRMM_%u_%u_%u"
0x180003aff  test    ebx, ebx
0x180003b01  cmovz   r8, rax; unsigned __int16 *
0x180003b05  mov     eax, [rsp+5D8h+FileInformation.nFileIndexLow]
0x180003b0c  mov     [rsp+5D8h+dwFlagsAndAttributes], eax
0x180003b10  mov     eax, [rsp+5D8h+FileInformation.nFileIndexHigh]
0x180003b17  mov     [rsp+5D8h+dwCreationDisposition], eax
0x180003b1b  mov     r9d, [rsp+5D8h+FileInformation.dwVolumeSerialNumber]
0x180003b23  mov     edx, 32h ; '2'; unsigned __int64
0x180003b28  lea     rcx, [rsp+5D8h+Name]; unsigned __int16 *
0x180003b30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b35  mov     edi, eax
0x180003b37  mov     [rsp+5D8h+var_588], eax
0x180003b3b  test    eax, eax
0x180003b3d  js      loc_180004328
0x180003b43  mov     eax, ebx
0x180003b45  neg     eax
0x180003b47  sbb     r14, r14
0x180003b4a  and     r14d, 0Eh
0x180003b4e  xor     r9d, r9d; lpFilePart
0x180003b51  lea     r8, [rsp+5D8h+Buffer]; lpBuffer
0x180003b56  xor     edx, edx; nBufferLength
0x180003b58  mov     rcx, [rsi+0C8h]; lpFileName
0x180003b5f  call    cs:__imp_GetFullPathNameW
0x180003b65  test    eax, eax
0x180003b67  jnz     short loc_180003B87
0x180003b69  call    cs:__imp_GetLastError
0x180003b6f  mov     edi, eax
0x180003b71  test    eax, eax
0x180003b73  jle     short loc_180003B7E
0x180003b75  movzx   edi, ax
0x180003b78  or      edi, 80070000h
0x180003b7e  mov     [rsp+5D8h+var_588], edi
0x180003b82  jmp     loc_180004328
0x180003b87  lea     r9, [rsp+5D8h+FilePart]; lpFilePart
0x180003b8f  lea     r8, [rsp+5D8h+var_248]; lpBuffer
0x180003b97  mov     edx, 104h; nBufferLength
0x180003b9c  mov     rcx, [rsi+0C8h]; lpFileName
0x180003ba3  call    cs:__imp_GetFullPathNameW
0x180003ba9  test    eax, eax
0x180003bab  jz      short loc_180003B69
0x180003bad  lea     rax, [rsp+5D8h+Name]
0x180003bb5  add     r14, rax
0x180003bb8  xor     ecx, ecx
0x180003bba  mov     rax, [rsp+5D8h+FilePart]
0x180003bc2  mov     [rax], cx
0x180003bc5  lea     r8, [rsp+5D8h+var_568]; unsigned __int64 *
0x180003bca  mov     edx, 104h; unsigned __int64
0x180003bcf  lea     rcx, [rsp+5D8h+var_248]; unsigned __int16 *
0x180003bd7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180003bdc  test    eax, eax
0x180003bde  jns     short loc_180003BEB
0x180003be0  mov     edi, eax
0x180003be2  mov     [rsp+5D8h+var_588], eax
0x180003be6  jmp     loc_180004328
0x180003beb  mov     r11, [rsp+5D8h+var_568]
0x180003bf0  neg     ebx
0x180003bf2  sbb     rdx, rdx
0x180003bf5  and     rdx, 0FFFFFFFFFFFFFFF9h
0x180003bf9  add     rdx, 32h ; '2'; unsigned __int64
0x180003bfd  lea     r8, [rsp+5D8h+var_568]; unsigned __int64 *
0x180003c02  mov     rcx, r14; unsigned __int16 *
0x180003c05  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180003c0a  test    eax, eax
0x180003c0c  js      short loc_180003BE0
0x180003c0e  mov     rax, [rsp+5D8h+var_568]
0x180003c13  lea     ecx, [rax+r11]
0x180003c17  lea     edx, [rcx+rax]
0x180003c1a  cmp     edx, ecx
0x180003c1c  jnb     short loc_180003C28
0x180003c1e  mov     edi, 80070216h
0x180003c23  jmp     loc_180003B7E
0x180003c28  lea     r15d, [rdx+1]
0x180003c2c  mov     ebx, r15d
0x180003c2f  mov     eax, 2
0x180003c34  mul     rbx
0x180003c37  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003c3e  cmovb   rax, rcx
0x180003c42  mov     rcx, rax; unsigned __int64
0x180003c45  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003c4a  mov     [rsp+5D8h+lpFileName], rax
0x180003c4f  mov     [rsp+5D8h+var_508], rax
0x180003c57  test    rax, rax
0x180003c5a  jnz     short loc_180003C6F
0x180003c5c  mov     edi, 8007000Eh
0x180003c61  mov     [rsp+5D8h+var_588], edi
0x180003c65  mov     r15, [rsp+5D8h+lpFileName]
0x180003c6a  jmp     loc_180004328
0x180003c6f  mov     qword ptr [rsp+5D8h+dwCreationDisposition], r14
0x180003c74  lea     r9, [rsp+5D8h+var_248]
0x180003c7c  lea     r8, aLsLs; "%ls%ls"
0x180003c83  mov     rdx, rbx; unsigned __int64
0x180003c86  mov     rcx, rax; unsigned __int16 *
0x180003c89  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c8e  test    eax, eax
0x180003c90  jns     short loc_180003C9A
0x180003c92  mov     edi, eax
0x180003c94  mov     [rsp+5D8h+var_588], eax
0x180003c98  jmp     short loc_180003C65
0x180003c9a  lea     ebx, [r15+4]
0x180003c9e  mov     eax, 2
0x180003ca3  mul     rbx
0x180003ca6  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180003cad  cmovb   rax, rdx
0x180003cb1  mov     rcx, rax; unsigned __int64
0x180003cb4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003cb9  mov     r12, rax
0x180003cbc  mov     [rsp+5D8h+var_500], rax
0x180003cc4  test    rax, rax
0x180003cc7  jz      short loc_180003C5C
0x180003cc9  cmp     dword ptr [rsi+2498h], 0
0x180003cd0  jnz     short loc_180003CFF
0x180003cd2  cmp     dword ptr [rsi+2488h], 0FFFFFFFFh
0x180003cd9  jz      short loc_180003CFF
0x180003cdb  mov     qword ptr [rsp+5D8h+dwCreationDisposition], r14
0x180003ce0  lea     r9, [rsp+5D8h+var_248]
0x180003ce8  lea     r8, aLsLsTmp; "%ls%ls.tmp"
0x180003cef  mov     edx, ebx; unsigned __int64
0x180003cf1  mov     rcx, rax; unsigned __int16 *
0x180003cf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003cf9  test    eax, eax
0x180003cfb  jns     short loc_180003D06
0x180003cfd  jmp     short loc_180003C92
0x180003cff  xor     eax, eax
0x180003d01  mov     [r12], ax
0x180003d06  mov     rcx, [rsi+2578h]
0x180003d0d  test    rcx, rcx
0x180003d10  jz      short loc_180003D2D
0x180003d12  mov     rax, [rcx]
0x180003d15  lea     rdx, [rsi+2460h]
0x180003d1c  mov     rax, [rax+18h]
0x180003d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d25  test    eax, eax
0x180003d27  js      loc_180003C92
0x180003d2d  lea     rax, [rsp+5D8h+var_4B8]
0x180003d35  mov     [rsi+2440h], rax
0x180003d3c  mov     rax, [rsi]
0x180003d3f  lea     r8, [rsi+25A8h]
0x180003d46  lea     rdx, [rsp+5D8h+var_4B8]
0x180003d4e  mov     rcx, rsi
0x180003d51  mov     rax, [rax+158h]
0x180003d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5d  test    eax, eax
0x180003d5f  js      loc_180003C92
0x180003d65  mov     [rsp+5D8h+hTemplateFile], 0; hTemplateFile
0x180003d6e  mov     [rsp+5D8h+dwFlagsAndAttributes], 8000106h; dwFlagsAndAttributes
0x180003d76  mov     [rsp+5D8h+dwCreationDisposition], 1; dwCreationDisposition
0x180003d7e  xor     r9d, r9d; lpSecurityAttributes
0x180003d81  xor     r8d, r8d; dwShareMode
0x180003d84  mov     edx, 40000000h; dwDesiredAccess
0x180003d89  mov     r15, [rsp+5D8h+lpFileName]
0x180003d8e  mov     rcx, r15; lpFileName
0x180003d91  call    cs:__imp_CreateFileW
0x180003d97  mov     rbx, rax
0x180003d9a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180003d9e  cmp     rax, r14
0x180003da1  jz      loc_180003B69
0x180003da7  mov     [rsp+5D8h+NumberOfBytesWritten], 0
0x180003daf  mov     qword ptr [rsp+5D8h+dwCreationDisposition], 0; lpOverlapped
0x180003db8  lea     r9, [rsp+5D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003dbd  mov     r8d, 1F8h; nNumberOfBytesToWrite
0x180003dc3  lea     rdx, [rsp+5D8h+var_4B8]; lpBuffer
0x180003dcb  mov     rcx, rax; hFile
0x180003dce  call    cs:__imp_WriteFile
0x180003dd4  test    eax, eax
0x180003dd6  jz      loc_180004306
0x180003ddc  cmp     [rsp+5D8h+NumberOfBytesWritten], 1F8h
0x180003de4  jnz     loc_180004306
0x180003dea  mov     rcx, rbx; hObject
0x180003ded  call    cs:__imp_CloseHandle
0x180003df3  mov     [rsp+5D8h+hTemplateFile], 0; hTemplateFile
0x180003dfc  mov     [rsp+5D8h+dwFlagsAndAttributes], 14000000h; dwFlagsAndAttributes
0x180003e04  mov     [rsp+5D8h+dwCreationDisposition], 3; enum _ACCESS_MODE
0x180003e0c  xor     r9d, r9d; lpSecurityAttributes
0x180003e0f  lea     ebx, [r14+8]
0x180003e13  mov     r8d, ebx; dwShareMode
0x180003e16  mov     edx, 0C0010000h; dwDesiredAccess
0x180003e1b  mov     rcx, r15; lpFileName
0x180003e1e  call    cs:__imp_CreateFileW
0x180003e24  mov     rcx, rax
0x180003e27  mov     [rsi+2448h], rax
0x180003e2e  cmp     rax, r14
0x180003e31  jnz     short loc_180003E5C
0x180003e33  call    cs:__imp_GetLastError
0x180003e39  mov     edi, eax
0x180003e3b  test    eax, eax
0x180003e3d  jle     short loc_180003E48
0x180003e3f  movzx   edi, ax
0x180003e42  or      edi, 80070000h
0x180003e48  mov     [rsp+5D8h+var_588], edi
0x180003e4c  mov     qword ptr [rsi+2448h], 0
0x180003e57  jmp     loc_180004328
0x180003e5c  mov     [rsp+5D8h+var_550], 0
0x180003e68  mov     [rsp+5D8h+var_560], 0
0x180003e71  xorps   xmm0, xmm0
0x180003e74  xor     eax, eax
0x180003e76  movups  [rsp+5D8h+var_520], xmm0
0x180003e7e  mov     [rsp+5D8h+var_510], rax
0x180003e86  mov     eax, [rsi+2624h]
0x180003e8c  test    eax, eax
0x180003e8e  jz      short loc_180003EFA
0x180003e90  lea     rcx, [rsp+5D8h+var_560]
0x180003e95  mov     [rsp+5D8h+var_5A0], rcx; void **
0x180003e9a  lea     rcx, [rsp+5D8h+var_550]
0x180003ea2  mov     [rsp+5D8h+hTemplateFile], rcx; struct _ACL **
0x180003ea7  mov     [rsp+5D8h+dwFlagsAndAttributes], ebx; unsigned int
0x180003eab  mov     r9d, 0F0007h; unsigned int
0x180003eb1  mov     rdx, [rsi+2630h]; void **
0x180003eb8  mov     ecx, eax; cCountOfExplicitEntries
0x180003eba  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180003ebf  test    eax, eax
0x180003ec1  jz      short loc_180003ED0
0x180003ec3  jg      loc_180003B75
0x180003ec9  mov     edi, eax
0x180003ecb  jmp     loc_180003B7E
0x180003ed0  mov     dword ptr [rsp+5D8h+var_520], 18h
0x180003edb  mov     rax, [rsp+5D8h+var_560]
0x180003ee0  mov     qword ptr [rsp+5D8h+var_520+8], rax
0x180003ee8  mov     dword ptr [rsp+5D8h+var_510], 0
0x180003ef3  mov     rcx, [rsi+2448h]; hFile
0x180003efa  mov     edx, [rsi+2484h]
0x180003f00  imul    edx, [rsi+2480h]
0x180003f07  lea     r10, [rsp+5D8h+var_520]
0x180003f0f  xor     eax, eax
0x180003f11  cmp     [rsi+2624h], eax
0x180003f17  cmovbe  r10, rax
0x180003f1b  lea     rax, [rsp+5D8h+Name]
0x180003f23  mov     qword ptr [rsp+5D8h+dwFlagsAndAttributes], rax; lpName
0x180003f28  mov     [rsp+5D8h+dwCreationDisposition], edx; dwMaximumSizeLow
0x180003f2c  xor     r9d, r9d; dwMaximumSizeHigh
0x180003f2f  lea     r14d, [r9+4]
0x180003f33  mov     r8d, r14d; flProtect
0x180003f36  mov     rdx, r10; lpFileMappingAttributes
0x180003f39  call    cs:__imp_CreateFileMappingW
0x180003f3f  mov     [rsi+2450h], rax
0x180003f46  call    cs:__imp_GetLastError
0x180003f4c  mov     ebx, eax
0x180003f4e  cmp     dword ptr [rsi+2624h], 0
0x180003f55  jbe     short loc_180003F69
0x180003f57  lea     rdx, [rsp+5D8h+var_560]; void **
0x180003f5c  lea     rcx, [rsp+5D8h+var_550]; struct _ACL **
0x180003f64  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x180003f69  mov     rcx, [rsi+2450h]; hFileMappingObject
  ... truncated ...
```
