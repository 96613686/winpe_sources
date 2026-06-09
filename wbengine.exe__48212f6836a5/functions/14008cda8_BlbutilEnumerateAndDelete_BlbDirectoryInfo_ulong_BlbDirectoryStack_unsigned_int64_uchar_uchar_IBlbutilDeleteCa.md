# BlbutilEnumerateAndDelete(BlbDirectoryInfo *,ulong,BlbDirectoryStack &,unsigned __int64 &,uchar &,uchar *,IBlbutilDeleteCallback *)

- ea: `0x14008cda8`
- end: `0x14008d3d1`
- name: `?BlbutilEnumerateAndDelete@@YAJPEAUBlbDirectoryInfo@@KAEAVBlbDirectoryStack@@AEA_KAEAEPEAEPEAUIBlbutilDeleteCallback@@@Z`
- size: `1577`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, struct BlbDirectoryStack *, unsigned __int64 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task`

## callers

- `0x14008c334`

## callees

- `0x1400063b4`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x140014200`
- `0x140014260`
- `0x14003c54c`
- `0x140051e98`
- `0x14008863c`
- `0x1400889f0`
- `0x14008c1a0`
- `0x14008c1c8`
- `0x14008ca7c`
- `0x14008cda8`
- `0x14008df64`
- `0x14008eb14`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindClose` at `0x14008d32d`
- `KERNEL32!FindClose` at `0x14008d32d`
- `KERNEL32!FindNextFileW` at `0x14008d265`
- `KERNEL32!FindNextFileW` at `0x14008d265`
- `KERNEL32!FindFirstFileW` at `0x14008d042`
- `KERNEL32!FindFirstFileW` at `0x14008d042`
- `KERNEL32!GetLastError` at `0x14008d053`
- `KERNEL32!GetLastError` at `0x14008d276`
- `KERNEL32!GetLastError` at `0x14008d053`
- `KERNEL32!GetLastError` at `0x14008d276`
- `ole32!CoTaskMemFree` at `0x14008d33b`
- `ole32!CoTaskMemFree` at `0x14008d349`
- `ole32!CoTaskMemFree` at `0x14008d357`
- `ole32!CoTaskMemFree` at `0x14008d365`
- `ole32!CoTaskMemFree` at `0x14008d33b`
- `ole32!CoTaskMemFree` at `0x14008d349`
- `ole32!CoTaskMemFree` at `0x14008d357`
- `ole32!CoTaskMemFree` at `0x14008d365`

## pseudocode

```c
__int64 __fastcall BlbutilEnumerateAndDelete(
        unsigned __int16 **a1,
        __int64 a2,
        struct BlbDirectoryStack *a3,
        unsigned __int64 *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6)
{
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // r14
  WCHAR *v10; // r13
  BlbDirectoryInfo *v11; // r12
  int Path; // ebx
  bool v13; // zf
  unsigned __int16 *v14; // rdx
  void *v15; // rdi
  __int64 v16; // rax
  unsigned int v17; // edi
  int v18; // eax
  __int64 v19; // rcx
  int appended; // eax
  DWORD LastError; // eax
  struct BlbDirectoryInfo *v22; // rdi
  int v23; // edx
  int v24; // edx
  unsigned __int64 v25; // rdx
  int v26; // r8d
  int v27; // eax
  signed int v28; // edi
  unsigned int v29; // edx
  unsigned __int8 v31[8]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v34; // [rsp+48h] [rbp-B8h] BYREF
  struct BlbDirectoryInfo *v35; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hFindFile; // [rsp+60h] [rbp-A0h]
  struct BlbDirectoryInfo *v38; // [rsp+68h] [rbp-98h]
  unsigned __int64 v39; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v40; // [rsp+78h] [rbp-88h]
  BlbDirectoryStack *v41; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v42; // [rsp+88h] [rbp-78h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

  v41 = a3;
  v40 = a5;
  v42 = a4;
  v38 = (struct BlbDirectoryInfo *)a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids);
  }
  hFindFile = (HANDLE)-1LL;
  v34 = 0;
  pv = 0;
  v33 = 0;
  v8 = 0;
  lpFileName = 0;
  v9 = 0;
  v35 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *a6 = 0;
  if ( *((_DWORD *)a1 + 4) > 0x64u )
  {
    Path = -2147024809;
    goto LABEL_79;
  }
  v13 = (*(_DWORD *)a1 & 0x400) == 0;
  *((_BYTE *)a1 + 20) = 1;
  if ( !v13 )
  {
    Path = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids, a1[1]);
    }
    goto LABEL_79;
  }
  Path = BlbutilDuplicateString(*(const unsigned __int16 **)a3, (unsigned __int16 **)&pv, 0);
  if ( Path < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids);
    }
    goto LABEL_79;
  }
  v14 = a1[1];
  v15 = pv;
  Path = BlbutilMakePath((unsigned __int16 *)pv, v14, &v33);
  if ( Path < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids);
    }
    v9 = v33;
    goto LABEL_80;
  }
  v9 = v33;
  v16 = -1;
  do
    ++v16;
  while ( v33[v16] );
  v17 = v16 + 262;
  v18 = BlbutilMemalloc((void **)&v34, (int)v16 + 262, 2u);
  v8 = v34;
  Path = v18;
  if ( v18 < 0 )
    goto LABEL_79;
  v39 = v17;
  Path = StringCchCopyW(v34, v17, v9);
  if ( Path < 0 )
    goto LABEL_79;
  v19 = -1;
  do
    ++v19;
  while ( v8[v19] );
  v8[(unsigned int)v19] = 92;
  v34 = (unsigned __int16 *)(unsigned int)(v19 + 1);
  v8[(_QWORD)v34] = 0;
  appended = BlbutilAppendString(v9, L"\\*", (unsigned __int16 **)&lpFileName);
  v10 = (WCHAR *)lpFileName;
  Path = appended;
  if ( appended < 0 )
    goto LABEL_79;
  hFindFile = FindFirstFileW(lpFileName, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    Path = LastError;
    if ( LastError == 2 )
    {
      Path = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids,
          (_DWORD)v10,
          LastError);
      }
      if ( Path > 0 )
        Path = (unsigned __int16)Path | 0x80070000;
    }
    goto LABEL_79;
  }
  LODWORD(v33) = 0;
  v22 = v38;
  while ( 1 )
  {
    v23 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v23 = FindFileData.cFileName[1];
    if ( !v23 )
      goto LABEL_65;
    v24 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v24 = FindFileData.cFileName[1] - 46;
      if ( FindFileData.cFileName[1] == 46 )
        v24 = FindFileData.cFileName[2];
    }
    if ( !v24 )
      goto LABEL_65;
    v25 = v39;
    v8[(_QWORD)v34] = 0;
    Path = StringCchCatW(v8, v25, FindFileData.cFileName);
    if ( Path < 0 )
      goto LABEL_78;
    if ( (FindFileData.dwFileAttributes & 0x410) == 0x10 )
    {
      v26 = *((_DWORD *)v22 + 4);
      if ( v26 == 100 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids,
            (unsigned int)FindFileData.cFileName,
            100);
        }
      }
      else if ( (unsigned int)v33 < 0x64 )
      {
        v27 = BlbDirectoryInfo::BlbCreateDirectoryInfo(
                FindFileData.cFileName,
                FindFileData.dwFileAttributes,
                v26 + 1,
                &v35);
        v11 = v35;
        Path = v27;
        if ( v27 < 0 )
          goto LABEL_78;
        Path = BlbDirectoryStack::Push(v41, v35);
        if ( Path < 0 )
          goto LABEL_78;
        LODWORD(v33) = (_DWORD)v33 + 1;
        v11 = 0;
        v35 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids,
            100,
            (__int64)v9);
        }
        *v40 = 1;
      }
      goto LABEL_65;
    }
    v31[0] = 1;
    Path = BlbutilDeleteFile(v8, &FindFileData.dwFileAttributes, v31);
    if ( Path < 0 )
      break;
    ++*v42;
LABEL_65:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
    {
      v28 = GetLastError();
      if ( v28 == 18 )
        goto LABEL_79;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids,
          (_DWORD)v10,
          v28);
      }
      if ( v28 > 0 )
        Path = (unsigned __int16)v28 | 0x80070000;
      else
        Path = v28;
LABEL_78:
      *a6 = 0;
      goto LABEL_79;
    }
  }
  *a6 = v31[0];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids,
      (_DWORD)v8,
      Path);
  }
LABEL_79:
  v15 = pv;
LABEL_80:
  FindClose(hFindFile);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v15 )
    CoTaskMemFree(v15);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v11 )
    BlbDirectoryInfo::`scalar deleting destructor'(v11, v29);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x14008cda8  mov     [rsp-8+arg_8], rbx
0x14008cdad  push    rbp
0x14008cdae  push    rsi
0x14008cdaf  push    rdi
0x14008cdb0  push    r12
0x14008cdb2  push    r13
0x14008cdb4  push    r14
0x14008cdb6  push    r15
0x14008cdb8  lea     rbp, [rsp-1F0h]
0x14008cdc0  sub     rsp, 2F0h
0x14008cdc7  mov     rax, cs:__security_cookie
0x14008cdce  xor     rax, rsp
0x14008cdd1  mov     [rbp+220h+var_40], rax
0x14008cdd8  mov     rax, [rbp+220h+arg_20]
0x14008cddf  mov     rbx, r8
0x14008cde2  mov     r15, [rbp+220h+arg_28]
0x14008cde9  mov     rdi, rcx
0x14008cdec  mov     [rbp+220h+var_2A0], rbx
0x14008cdf0  mov     [rsp+320h+var_2A8], rax
0x14008cdf5  mov     [rbp+220h+var_298], r9
0x14008cdf9  mov     [rsp+320h+var_2B8], rcx
0x14008cdfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce05  lea     rax, WPP_GLOBAL_Control
0x14008ce0c  cmp     rcx, rax
0x14008ce0f  jz      short loc_14008CE32
0x14008ce11  test    byte ptr [rcx+1Ch], 1
0x14008ce15  jz      short loc_14008CE32
0x14008ce17  cmp     byte ptr [rcx+19h], 5
0x14008ce1b  jb      short loc_14008CE32
0x14008ce1d  mov     rcx, [rcx+10h]
0x14008ce21  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008ce28  mov     edx, 1Bh
0x14008ce2d  call    WPP_SF_
0x14008ce32  xor     eax, eax
0x14008ce34  mov     [rsp+320h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x14008ce3d  xor     edx, edx; Val
0x14008ce3f  mov     [rsp+320h+var_2D8], rax
0x14008ce44  mov     r8d, 250h; Size
0x14008ce4a  mov     [rsp+320h+pv], rax
0x14008ce4f  lea     rcx, [rbp+220h+FindFileData]; void *
0x14008ce53  mov     [rsp+320h+var_2E0], rax
0x14008ce58  mov     esi, eax
0x14008ce5a  mov     [rsp+320h+lpFileName], rax
0x14008ce5f  mov     r14d, eax
0x14008ce62  mov     [rsp+320h+var_2D0], rax
0x14008ce67  mov     r13d, eax
0x14008ce6a  mov     r12d, eax
0x14008ce6d  call    memset_0
0x14008ce72  xor     eax, eax
0x14008ce74  mov     [r15], al
0x14008ce77  cmp     dword ptr [rdi+10h], 64h ; 'd'
0x14008ce7b  jbe     short loc_14008CE87
0x14008ce7d  mov     ebx, 80070057h
0x14008ce82  jmp     loc_14008D31C
0x14008ce87  test    dword ptr [rdi], 400h
0x14008ce8d  mov     byte ptr [rdi+14h], 1
0x14008ce91  jz      short loc_14008CEDE
0x14008ce93  mov     ebx, eax
0x14008ce95  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce9c  lea     r15, WPP_GLOBAL_Control
0x14008cea3  cmp     rcx, r15
0x14008cea6  jz      loc_14008D323
0x14008ceac  test    byte ptr [rcx+1Ch], 1
0x14008ceb0  jz      loc_14008D323
0x14008ceb6  cmp     byte ptr [rcx+19h], 5
0x14008ceba  jb      loc_14008D323
0x14008cec0  mov     r9, [rdi+8]
0x14008cec4  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008cecb  mov     rcx, [rcx+10h]
0x14008cecf  mov     edx, 1Ch
0x14008ced4  call    WPP_SF_S
0x14008ced9  jmp     loc_14008D323
0x14008cede  mov     rcx, [rbx]; unsigned __int16 *
0x14008cee1  lea     rdx, [rsp+320h+pv]; unsigned __int16 **
0x14008cee6  xor     r8d, r8d; unsigned __int64
0x14008cee9  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14008ceee  mov     ebx, eax
0x14008cef0  test    eax, eax
0x14008cef2  jns     short loc_14008CF3C
0x14008cef4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cefb  lea     r15, WPP_GLOBAL_Control
0x14008cf02  cmp     rcx, r15
0x14008cf05  jz      loc_14008D323
0x14008cf0b  test    byte ptr [rcx+1Ch], 1
0x14008cf0f  jz      loc_14008D323
0x14008cf15  cmp     byte ptr [rcx+19h], 2
0x14008cf19  jb      loc_14008D323
0x14008cf1f  mov     rcx, [rcx+10h]
0x14008cf23  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008cf2a  mov     edx, 1Dh
0x14008cf2f  mov     r9d, eax
0x14008cf32  call    WPP_SF_d
0x14008cf37  jmp     loc_14008D323
0x14008cf3c  mov     rdx, [rdi+8]; unsigned __int16 *
0x14008cf40  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x14008cf45  mov     rdi, [rsp+320h+pv]
0x14008cf4a  mov     rcx, rdi; unsigned __int16 *
0x14008cf4d  call    ?BlbutilMakePath@@YAJPEAG0PEAPEAG@Z; BlbutilMakePath(ushort *,ushort *,ushort * *)
0x14008cf52  xor     ecx, ecx
0x14008cf54  mov     ebx, eax
0x14008cf56  test    eax, eax
0x14008cf58  jns     short loc_14008CF9B
0x14008cf5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf61  lea     r15, WPP_GLOBAL_Control
0x14008cf68  cmp     rcx, r15
0x14008cf6b  jz      short loc_14008CF91
0x14008cf6d  test    byte ptr [rcx+1Ch], 1
0x14008cf71  jz      short loc_14008CF91
0x14008cf73  cmp     byte ptr [rcx+19h], 2
0x14008cf77  jb      short loc_14008CF91
0x14008cf79  mov     rcx, [rcx+10h]
0x14008cf7d  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008cf84  mov     edx, 1Eh
0x14008cf89  mov     r9d, eax
0x14008cf8c  call    WPP_SF_d
0x14008cf91  mov     r14, [rsp+320h+var_2E0]
0x14008cf96  jmp     loc_14008D328
0x14008cf9b  mov     r14, [rsp+320h+var_2E0]
0x14008cfa0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008cfa4  inc     rax
0x14008cfa7  cmp     [r14+rax*2], cx
0x14008cfac  jnz     short loc_14008CFA4
0x14008cfae  lea     edi, [rax+106h]
0x14008cfb4  mov     r8d, 2; unsigned int
0x14008cfba  mov     edx, edi; unsigned int
0x14008cfbc  lea     rcx, [rsp+320h+var_2D8]; void **
0x14008cfc1  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14008cfc6  mov     rsi, [rsp+320h+var_2D8]
0x14008cfcb  mov     ebx, eax
0x14008cfcd  test    eax, eax
0x14008cfcf  js      loc_14008D31C
0x14008cfd5  mov     eax, edi
0x14008cfd7  mov     r8, r14; unsigned __int16 *
0x14008cfda  mov     edx, edi; unsigned __int64
0x14008cfdc  mov     rcx, rsi; unsigned __int16 *
0x14008cfdf  mov     [rsp+320h+var_2B0], rax
0x14008cfe4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14008cfe9  xor     edi, edi
0x14008cfeb  mov     ebx, eax
0x14008cfed  test    eax, eax
0x14008cfef  js      loc_14008D31C
0x14008cff5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14008cff9  inc     rcx
0x14008cffc  cmp     [rsi+rcx*2], di
0x14008d000  jnz     short loc_14008CFF9
0x14008d002  mov     eax, ecx
0x14008d004  lea     r8, [rsp+320h+lpFileName]; unsigned __int16 **
0x14008d009  lea     rdx, asc_140142BFC; "\\*"
0x14008d010  mov     word ptr [rsi+rax*2], 5Ch ; '\'
0x14008d016  lea     eax, [rcx+1]
0x14008d019  mov     ecx, eax
0x14008d01b  mov     [rsp+320h+var_2D8], rcx
0x14008d020  mov     rcx, r14; unsigned __int16 *
0x14008d023  mov     [rsi+rax*2], di
0x14008d027  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14008d02c  mov     r13, [rsp+320h+lpFileName]
0x14008d031  mov     ebx, eax
0x14008d033  test    eax, eax
0x14008d035  js      loc_14008D31C
0x14008d03b  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x14008d03f  mov     rcx, r13; lpFileName
0x14008d042  call    cs:__imp_FindFirstFileW
0x14008d048  mov     [rsp+320h+hFindFile], rax
0x14008d04d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008d051  jnz     short loc_14008D0B8
0x14008d053  call    cs:__imp_GetLastError
0x14008d059  mov     ebx, eax
0x14008d05b  cmp     eax, 2
0x14008d05e  jz      short loc_14008D0B1
0x14008d060  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d067  lea     r15, WPP_GLOBAL_Control
0x14008d06e  cmp     rcx, r15
0x14008d071  jz      short loc_14008D09B
0x14008d073  test    byte ptr [rcx+1Ch], 1
0x14008d077  jz      short loc_14008D09B
0x14008d079  cmp     byte ptr [rcx+19h], 2
0x14008d07d  jb      short loc_14008D09B
0x14008d07f  mov     rcx, [rcx+10h]
0x14008d083  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008d08a  mov     edx, 1Fh
0x14008d08f  mov     dword ptr [rsp+320h+var_300], eax
0x14008d093  mov     r9, r13
0x14008d096  call    WPP_SF_Sd
0x14008d09b  test    ebx, ebx
0x14008d09d  jle     loc_14008D323
0x14008d0a3  movzx   ebx, bx
0x14008d0a6  or      ebx, 80070000h
0x14008d0ac  jmp     loc_14008D323
0x14008d0b1  mov     ebx, edi
0x14008d0b3  jmp     loc_14008D31C
0x14008d0b8  mov     dword ptr [rsp+320h+var_2E0], edi
0x14008d0bc  xor     r8d, r8d
0x14008d0bf  mov     rdi, [rsp+320h+var_2B8]
0x14008d0c4  movzx   edx, [rbp+220h+FindFileData.cFileName]
0x14008d0c8  mov     ecx, 2Eh ; '.'
0x14008d0cd  movzx   eax, cx
0x14008d0d0  sub     edx, eax
0x14008d0d2  jnz     short loc_14008D0E3
0x14008d0d4  movzx   edx, [rbp+220h+FindFileData.cFileName+2]
0x14008d0d8  movzx   ecx, r8w
0x14008d0dc  sub     edx, ecx
0x14008d0de  mov     ecx, 2Eh ; '.'
0x14008d0e3  test    edx, edx
0x14008d0e5  jz      loc_14008D25C
0x14008d0eb  movzx   edx, [rbp+220h+FindFileData.cFileName]
0x14008d0ef  movzx   eax, cx
0x14008d0f2  sub     edx, eax
0x14008d0f4  jnz     short loc_14008D10B
0x14008d0f6  movzx   edx, [rbp+220h+FindFileData.cFileName+2]
0x14008d0fa  movzx   eax, cx
0x14008d0fd  sub     edx, eax
0x14008d0ff  jnz     short loc_14008D10B
0x14008d101  movzx   edx, [rbp+220h+FindFileData.cFileName+4]
0x14008d105  movzx   ecx, r8w
0x14008d109  sub     edx, ecx
0x14008d10b  test    edx, edx
0x14008d10d  jz      loc_14008D25C
0x14008d113  mov     rcx, [rsp+320h+var_2D8]
0x14008d118  mov     rdx, [rsp+320h+var_2B0]; unsigned __int64
0x14008d11d  mov     [rsi+rcx*2], r8w
0x14008d122  lea     r8, [rbp+220h+FindFileData.cFileName]; unsigned __int16 *
0x14008d126  mov     rcx, rsi; unsigned __int16 *
0x14008d129  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14008d12e  mov     ebx, eax
0x14008d130  xor     eax, eax
0x14008d132  test    ebx, ebx
0x14008d134  js      loc_14008D319
0x14008d13a  mov     edx, [rbp+220h+FindFileData.dwFileAttributes]; unsigned int
0x14008d13d  mov     eax, edx
0x14008d13f  and     eax, 410h
0x14008d144  cmp     eax, 10h
0x14008d147  jnz     loc_14008D239
0x14008d14d  mov     r8d, [rdi+10h]
0x14008d151  lea     r9d, [rax+54h]
0x14008d155  cmp     r8d, r9d
0x14008d158  jnz     short loc_14008D1A7
0x14008d15a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d161  lea     rax, WPP_GLOBAL_Control
0x14008d168  cmp     rcx, rax
0x14008d16b  jz      loc_14008D25C
0x14008d171  test    byte ptr [rcx+1Ch], 1
0x14008d175  jz      loc_14008D25C
0x14008d17b  cmp     byte ptr [rcx+19h], 3
0x14008d17f  jb      loc_14008D25C
0x14008d185  mov     rcx, [rcx+10h]
0x14008d189  lea     edx, [r9-44h]
0x14008d18d  mov     dword ptr [rsp+320h+var_300], r9d
0x14008d192  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008d199  lea     r9, [rbp+220h+FindFileData.cFileName]
0x14008d19d  call    WPP_SF_Sd
0x14008d1a2  jmp     loc_14008D25C
0x14008d1a7  cmp     dword ptr [rsp+320h+var_2E0], r9d
0x14008d1ac  jb      short loc_14008D1F1
0x14008d1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d1b5  lea     rax, WPP_GLOBAL_Control
0x14008d1bc  cmp     rcx, rax
0x14008d1bf  jz      short loc_14008D1E7
0x14008d1c1  test    byte ptr [rcx+1Ch], 1
0x14008d1c5  jz      short loc_14008D1E7
0x14008d1c7  cmp     byte ptr [rcx+19h], 4
0x14008d1cb  jb      short loc_14008D1E7
0x14008d1cd  mov     rcx, [rcx+10h]
0x14008d1d1  lea     r8, WPP_bf12262e5ac430ffbe36396000eecabf_Traceguids
0x14008d1d8  mov     edx, 21h ; '!'
0x14008d1dd  mov     [rsp+320h+var_300], r14
0x14008d1e2  call    WPP_SF_dS
0x14008d1e7  mov     rax, [rsp+320h+var_2A8]
0x14008d1ec  mov     byte ptr [rax], 1
0x14008d1ef  jmp     short loc_14008D25C
0x14008d1f1  inc     r8d; unsigned int
0x14008d1f4  lea     r9, [rsp+320h+var_2D0]; struct BlbDirectoryInfo **
0x14008d1f9  lea     rcx, [rbp+220h+FindFileData.cFileName]; unsigned __int16 *
0x14008d1fd  call    ?BlbCreateDirectoryInfo@BlbDirectoryInfo@@SAJPEAGKKPEAPEAU1@@Z; BlbDirectoryInfo::BlbCreateDirectoryInfo(ushort *,ulong,ulong,BlbDirectoryInfo * *)
0x14008d202  mov     r12, [rsp+320h+var_2D0]
0x14008d207  mov     ebx, eax
0x14008d209  xor     eax, eax
0x14008d20b  test    ebx, ebx
0x14008d20d  js      loc_14008D319
0x14008d213  mov     rcx, [rbp+220h+var_2A0]; this
0x14008d217  mov     rdx, r12; struct BlbDirectoryInfo *
0x14008d21a  call    ?Push@BlbDirectoryStack@@QEAAJPEAUBlbDirectoryInfo@@@Z; BlbDirectoryStack::Push(BlbDirectoryInfo *)
0x14008d21f  mov     ebx, eax
0x14008d221  xor     eax, eax
0x14008d223  test    ebx, ebx
0x14008d225  js      loc_14008D319
0x14008d22b  inc     dword ptr [rsp+320h+var_2E0]
0x14008d22f  mov     r12d, eax
0x14008d232  mov     [rsp+320h+var_2D0], rax
0x14008d237  jmp     short loc_14008D25C
0x14008d239  lea     r8, [rsp+320h+var_2F0]; unsigned __int8 *
0x14008d23e  mov     [rsp+320h+var_2F0], 1
0x14008d243  lea     rdx, [rbp+220h+FindFileData]; unsigned int *
0x14008d247  mov     rcx, rsi; unsigned __int16 *
0x14008d24a  call    ?BlbutilDeleteFile@@YAJPEAGPEAKPEAE@Z; BlbutilDeleteFile(ushort *,ulong *,uchar *)
0x14008d24f  mov     ebx, eax
0x14008d251  test    eax, eax
0x14008d253  js      short loc_14008D2CC
0x14008d255  mov     rax, [rbp+220h+var_298]
0x14008d259  inc     qword ptr [rax]
0x14008d25c  mov     rcx, [rsp+320h+hFindFile]; hFindFile
  ... truncated ...
```
