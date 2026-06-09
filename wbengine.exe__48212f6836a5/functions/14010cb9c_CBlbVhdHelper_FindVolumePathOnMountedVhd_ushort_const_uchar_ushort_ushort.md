# CBlbVhdHelper::_FindVolumePathOnMountedVhd(ushort const *,uchar,ushort * *,ushort * *)

- ea: `0x14010cb9c`
- end: `0x14010d26e`
- name: `?_FindVolumePathOnMountedVhd@CBlbVhdHelper@@CAJPEBGEPEAPEAG1@Z`
- size: `1746`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, char, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x14010a688`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014260`
- `0x14003c9cc`
- `0x1400889f0`
- `0x140088d0c`
- `0x1400c3d08`
- `0x1400c3fec`
- `0x1400fff10`
- `0x14010cb9c`
- `0x140134d20`

## import_xrefs

- `KERNEL32!Sleep` at `0x14010cf78`
- `KERNEL32!Sleep` at `0x14010d16e`
- `KERNEL32!Sleep` at `0x14010cf78`
- `KERNEL32!Sleep` at `0x14010d16e`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x14010d10b`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x14010d10b`
- `KERNEL32!CreateFileW` at `0x14010cd2d`
- `KERNEL32!CreateFileW` at `0x14010cd2d`
- `KERNEL32!CloseHandle` at `0x14010d1ec`
- `KERNEL32!CloseHandle` at `0x14010d1ec`
- `KERNEL32!GetLastError` at `0x14010cd3e`
- `KERNEL32!GetLastError` at `0x14010cde5`
- `KERNEL32!GetLastError` at `0x14010cf25`
- `KERNEL32!GetLastError` at `0x14010d119`
- `KERNEL32!GetLastError` at `0x14010cd3e`
- `KERNEL32!GetLastError` at `0x14010cde5`
- `KERNEL32!GetLastError` at `0x14010cf25`
- `KERNEL32!GetLastError` at `0x14010d119`
- `KERNEL32!DeviceIoControl` at `0x14010cddb`
- `KERNEL32!DeviceIoControl` at `0x14010cddb`
- `ole32!CoTaskMemFree` at `0x14010d208`
- `ole32!CoTaskMemFree` at `0x14010d208`

## string_xrefs

- `0x14010cc78`: `wszDiskPath && *wszDiskPath`
- `0x14010cc9c`: `pwszVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBlbVhdHelper::_FindVolumePathOnMountedVhd(
        LPCWSTR lpFileName,
        char a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  PVOID *v7; // rdi
  unsigned int v8; // r13d
  WCHAR *v9; // rsi
  HANDLE FileW; // rax
  signed int v11; // eax
  int v12; // ebx
  unsigned int v13; // r14d
  signed int LastError; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  unsigned int v18; // ebx
  signed int v19; // eax
  const WCHAR *v20; // r12
  signed int v21; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpszVolumeMountPoint; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 **v28; // [rsp+50h] [rbp-B0h]
  HANDLE hObject; // [rsp+58h] [rbp-A8h]
  __int64 OutBuffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v31; // [rsp+68h] [rbp-98h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v33[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR szVolumeName[264]; // [rsp+490h] [rbp+390h] BYREF

  v28 = a3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  BytesReturned = 0;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  lpszVolumeMountPoint = 0;
  OutBuffer = 0;
  v31 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v33, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  if ( !lpFileName || !*lpFileName )
  {
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbvhdhelper.cpp", 0x39Au, "wszDiskPath && *wszDiskPath");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbvhdhelper.cpp", 0x39Bu, "pwszVolumePath");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
  {
    WPP_SF_Sq(
      (unsigned int)v7[2],
      50,
      (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
      (_DWORD)lpFileName,
      (char)a4);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a4 || !lpFileName )
  {
    v12 = -2147024809;
LABEL_91:
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_93;
  }
  *a4 = 0;
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0x2000080u, 0);
  hObject = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v13 = 0;
    if ( !DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_89;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_88;
      v16 = 52;
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LODWORD(dwFlagsAndAttributes) = OutBuffer;
      dwCreationDisposition[0] = v31;
      WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
    }
    v17 = L"\\\\?\\Globalroot\\Device\\Harddisk%lu\\Partition1";
    if ( !a2 )
      v17 = L"\\\\?\\Globalroot\\Device\\Harddisk%lu\\Partition2";
    v12 = StringCchPrintfW(
            FileName,
            0x104u,
            v17,
            HIDWORD(OutBuffer),
            *(_QWORD *)dwCreationDisposition,
            dwFlagsAndAttributes);
    if ( v12 >= 0 )
    {
      v18 = 0;
      if ( CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs )
      {
        do
        {
          if ( (int)BlbGetVolumeNumber(FileName, &v26) >= 0 )
          {
            v8 = v26;
            goto LABEL_57;
          }
          v19 = GetLastError();
          if ( v19 > 0 )
            v19 = (unsigned __int16)v19 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_LD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
              v18,
              v19);
          }
          Sleep(CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs / 0x1E);
          v18 += CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs / 0x1E;
        }
        while ( v18 < CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs );
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
            v18,
            -2139619249);
        }
        v12 = -2139619249;
        goto LABEL_88;
      }
LABEL_57:
      v12 = StringCchPrintfW(v33, 0x104u, L"\\\\?\\Globalroot\\Device\\HarddiskVolume%lu", v8);
      if ( v12 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_88;
        }
        v16 = 57;
        goto LABEL_30;
      }
      v12 = BlbutilDuplicateString(v33, a4, 0);
      if ( v12 >= 0 )
      {
        v12 = BlbutilSlashTerminatePath(FileName, (LPVOID *)&lpszVolumeMountPoint);
        if ( v12 >= 0 )
        {
          if ( CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs )
          {
            v20 = lpszVolumeMountPoint;
            while ( !GetVolumeNameForVolumeMountPointW(v20, szVolumeName, 0x104u) )
            {
              v21 = GetLastError();
              v12 = v21;
              if ( v21 > 0 )
                v12 = (unsigned __int16)v21 | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_LD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  60,
                  &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
                  v13,
                  v12);
              }
              Sleep(CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs / 0x1E);
              v13 += CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs / 0x1E;
              if ( v13 >= CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs )
              {
                if ( v12 >= 0 )
                  break;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_LD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    61,
                    &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
                    v13,
                    v12);
                }
                goto LABEL_88;
              }
            }
          }
          v12 = BlbutilDuplicateString(szVolumeName, v28, 0);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
            (unsigned int)FileName,
            v12);
        }
        goto LABEL_88;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 58;
        goto LABEL_30;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_89;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 54;
LABEL_30:
        WPP_SF_d(v15[2], v16, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
      }
    }
LABEL_88:
    v9 = (WCHAR *)lpszVolumeMountPoint;
LABEL_89:
    CloseHandle(hObject);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_91;
  }
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
        (_DWORD)lpFileName,
        v12);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_93:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
      WPP_SF_(v7[2], 62, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14010cb9c  mov     [rsp-8+arg_8], rbx
0x14010cba1  push    rbp
0x14010cba2  push    rsi
0x14010cba3  push    rdi
0x14010cba4  push    r12
0x14010cba6  push    r13
0x14010cba8  push    r14
0x14010cbaa  push    r15
0x14010cbac  lea     rbp, [rsp-5B0h]
0x14010cbb4  sub     rsp, 6B0h
0x14010cbbb  mov     rax, cs:__security_cookie
0x14010cbc2  xor     rax, rsp
0x14010cbc5  mov     [rbp+5E0h+var_40], rax
0x14010cbcc  mov     r12, r9
0x14010cbcf  mov     [rsp+6E0h+var_690], r8
0x14010cbd4  mov     bl, dl
0x14010cbd6  mov     r14, rcx
0x14010cbd9  mov     rdi, cs:WPP_GLOBAL_Control
0x14010cbe0  lea     rax, WPP_GLOBAL_Control
0x14010cbe7  cmp     rdi, rax
0x14010cbea  jz      short loc_14010CC14
0x14010cbec  test    byte ptr [rdi+1Ch], 1
0x14010cbf0  jz      short loc_14010CC14
0x14010cbf2  cmp     byte ptr [rdi+19h], 4
0x14010cbf6  jb      short loc_14010CC14
0x14010cbf8  mov     rcx, [rdi+10h]
0x14010cbfc  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010cc03  mov     edx, 31h ; '1'
0x14010cc08  call    WPP_SF_
0x14010cc0d  mov     rdi, cs:WPP_GLOBAL_Control
0x14010cc14  xor     ecx, ecx
0x14010cc16  xor     eax, eax
0x14010cc18  mov     [rsp+6E0h+BytesReturned], ecx
0x14010cc1c  mov     r13d, ecx
0x14010cc1f  mov     [rsp+6E0h+var_698], ecx
0x14010cc23  mov     esi, ecx
0x14010cc25  mov     [rsp+6E0h+lpszVolumeMountPoint], rcx
0x14010cc2a  mov     r15d, 208h
0x14010cc30  lea     rcx, [rbp+5E0h+szVolumeName]; void *
0x14010cc37  mov     [rsp+6E0h+OutBuffer], rax
0x14010cc3c  mov     r8d, r15d; Size
0x14010cc3f  mov     [rsp+6E0h+var_678], eax
0x14010cc43  xor     edx, edx; Val
0x14010cc45  call    memset_0
0x14010cc4a  mov     r8d, r15d; Size
0x14010cc4d  lea     rcx, [rbp+5E0h+var_460]; void *
0x14010cc54  xor     edx, edx; Val
0x14010cc56  call    memset_0
0x14010cc5b  mov     r8d, r15d; Size
0x14010cc5e  lea     rcx, [rsp+6E0h+FileName]; void *
0x14010cc63  xor     edx, edx; Val
0x14010cc65  call    memset_0
0x14010cc6a  xor     r15d, r15d
0x14010cc6d  test    r14, r14
0x14010cc70  jz      short loc_14010CC78
0x14010cc72  cmp     [r14], r15w
0x14010cc76  jnz     short loc_14010CC97
0x14010cc78  lea     r8, aWszdiskpathWsz; "wszDiskPath && *wszDiskPath"
0x14010cc7f  mov     edx, 39Ah; unsigned int
0x14010cc84  lea     rcx, aBaseStorBlbEng_8; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010cc8b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010cc90  mov     rdi, cs:WPP_GLOBAL_Control
0x14010cc97  test    r12, r12
0x14010cc9a  jnz     short loc_14010CCBB
0x14010cc9c  lea     r8, aPwszvolumepath_0; "pwszVolumePath"
0x14010cca3  mov     edx, 39Bh; unsigned int
0x14010cca8  lea     rcx, aBaseStorBlbEng_8; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010ccaf  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010ccb4  mov     rdi, cs:WPP_GLOBAL_Control
0x14010ccbb  lea     rax, WPP_GLOBAL_Control
0x14010ccc2  cmp     rdi, rax
0x14010ccc5  jz      short loc_14010CCF7
0x14010ccc7  test    byte ptr [rdi+1Ch], 1
0x14010cccb  jz      short loc_14010CCF7
0x14010cccd  cmp     byte ptr [rdi+19h], 4
0x14010ccd1  jb      short loc_14010CCF7
0x14010ccd3  mov     rcx, [rdi+10h]
0x14010ccd7  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010ccde  mov     edx, 32h ; '2'
0x14010cce3  mov     qword ptr [rsp+6E0h+dwCreationDisposition], r12
0x14010cce8  mov     r9, r14
0x14010cceb  call    WPP_SF_Sq
0x14010ccf0  mov     rdi, cs:WPP_GLOBAL_Control
0x14010ccf7  test    r12, r12
0x14010ccfa  jz      loc_14010D1FB
0x14010cd00  test    r14, r14
0x14010cd03  jz      loc_14010D1FB
0x14010cd09  mov     [rsp+6E0h+hTemplateFile], r15; hTemplateFile
0x14010cd0e  mov     r8d, 3; dwShareMode
0x14010cd14  mov     dword ptr [rsp+6E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x14010cd1c  xor     r9d, r9d; lpSecurityAttributes
0x14010cd1f  xor     edx, edx; dwDesiredAccess
0x14010cd21  mov     [rsp+6E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x14010cd26  mov     rcx, r14; lpFileName
0x14010cd29  mov     [r12], r15
0x14010cd2d  call    cs:__imp_CreateFileW
0x14010cd33  mov     [rsp+6E0h+hObject], rax
0x14010cd38  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14010cd3c  jnz     short loc_14010CDA9
0x14010cd3e  call    cs:__imp_GetLastError
0x14010cd44  mov     ebx, eax
0x14010cd46  test    eax, eax
0x14010cd48  jle     short loc_14010CD53
0x14010cd4a  movzx   ebx, ax
0x14010cd4d  or      ebx, 80070000h
0x14010cd53  mov     rdi, cs:WPP_GLOBAL_Control
0x14010cd5a  lea     r15, WPP_GLOBAL_Control
0x14010cd61  cmp     rdi, r15
0x14010cd64  jz      loc_14010D242
0x14010cd6a  test    byte ptr [rdi+1Ch], 1
0x14010cd6e  jz      loc_14010D21C
0x14010cd74  mov     sil, 2
0x14010cd77  cmp     [rdi+19h], sil
0x14010cd7b  jb      loc_14010D21C
0x14010cd81  mov     rcx, [rdi+10h]
0x14010cd85  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010cd8c  mov     edx, 33h ; '3'
0x14010cd91  mov     [rsp+6E0h+dwCreationDisposition], ebx
0x14010cd95  mov     r9, r14
0x14010cd98  call    WPP_SF_Sd
0x14010cd9d  mov     rdi, cs:WPP_GLOBAL_Control
0x14010cda4  jmp     loc_14010D21C
0x14010cda9  lea     rcx, [rsp+6E0h+BytesReturned]
0x14010cdae  xor     r14d, r14d
0x14010cdb1  mov     [rsp+6E0h+lpOverlapped], r14; lpOverlapped
0x14010cdb6  xor     r9d, r9d; nInBufferSize
0x14010cdb9  mov     [rsp+6E0h+hTemplateFile], rcx; lpBytesReturned
0x14010cdbe  xor     r8d, r8d; lpInBuffer
0x14010cdc1  lea     rcx, [rsp+6E0h+OutBuffer]
0x14010cdc6  mov     dword ptr [rsp+6E0h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x14010cdce  mov     qword ptr [rsp+6E0h+dwCreationDisposition], rcx; lpOutBuffer
0x14010cdd3  mov     edx, 2D1080h; dwIoControlCode
0x14010cdd8  mov     rcx, rax; hDevice
0x14010cddb  call    cs:__imp_DeviceIoControl
0x14010cde1  test    eax, eax
0x14010cde3  jnz     short loc_14010CE45
0x14010cde5  call    cs:__imp_GetLastError
0x14010cdeb  mov     ebx, eax
0x14010cded  test    eax, eax
0x14010cdef  jle     short loc_14010CDFA
0x14010cdf1  movzx   ebx, ax
0x14010cdf4  or      ebx, 80070000h
0x14010cdfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14010ce01  lea     r13, WPP_GLOBAL_Control
0x14010ce08  cmp     rcx, r13
0x14010ce0b  jz      loc_14010D1E7
0x14010ce11  test    byte ptr [rcx+1Ch], 1
0x14010ce15  jz      loc_14010D1E7
0x14010ce1b  mov     sil, 2
0x14010ce1e  cmp     [rcx+19h], sil
0x14010ce22  jb      loc_14010D1E2
0x14010ce28  mov     edx, 34h ; '4'
0x14010ce2d  mov     rcx, [rcx+10h]
0x14010ce31  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010ce38  mov     r9d, ebx
0x14010ce3b  call    WPP_SF_d
0x14010ce40  jmp     loc_14010D1E2
0x14010ce45  mov     rcx, cs:WPP_GLOBAL_Control
0x14010ce4c  lea     rdi, WPP_GLOBAL_Control
0x14010ce53  cmp     rcx, rdi
0x14010ce56  jz      short loc_14010CE8E
0x14010ce58  test    byte ptr [rcx+1Ch], 1
0x14010ce5c  jz      short loc_14010CE8E
0x14010ce5e  cmp     byte ptr [rcx+19h], 4
0x14010ce62  jb      short loc_14010CE8E
0x14010ce64  mov     eax, dword ptr [rsp+6E0h+OutBuffer]
0x14010ce68  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010ce6f  mov     r9d, dword ptr [rsp+6E0h+OutBuffer+4]
0x14010ce74  mov     edx, 35h ; '5'
0x14010ce79  mov     rcx, [rcx+10h]
0x14010ce7d  mov     dword ptr [rsp+6E0h+dwFlagsAndAttributes], eax
0x14010ce81  mov     eax, [rsp+6E0h+var_678]
0x14010ce85  mov     [rsp+6E0h+dwCreationDisposition], eax
0x14010ce89  call    WPP_SF_LLL
0x14010ce8e  mov     r9d, dword ptr [rsp+6E0h+OutBuffer+4]
0x14010ce93  mov     r15d, 104h
0x14010ce99  lea     rcx, [rsp+6E0h+FileName]; unsigned __int16 *
0x14010ce9e  mov     edx, r15d; unsigned __int64
0x14010cea1  lea     r8, aGlobalrootDevi; "\\\\?\\Globalroot\\Device\\Harddisk%lu"...
0x14010cea8  test    bl, bl
0x14010ceaa  jnz     short loc_14010CEB3
0x14010ceac  lea     r8, aGlobalrootDevi_4; "\\\\?\\Globalroot\\Device\\Harddisk%lu"...
0x14010ceb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010ceb8  mov     ebx, eax
0x14010ceba  test    eax, eax
0x14010cebc  jns     short loc_14010CEEF
0x14010cebe  mov     rcx, cs:WPP_GLOBAL_Control
0x14010cec5  cmp     rcx, rdi
0x14010cec8  jz      loc_14010D1E7
0x14010cece  test    byte ptr [rcx+1Ch], 1
0x14010ced2  jz      loc_14010D1E7
0x14010ced8  mov     sil, 2
0x14010cedb  cmp     [rcx+19h], sil
0x14010cedf  jb      loc_14010D1E2
0x14010cee5  mov     edx, 36h ; '6'
0x14010ceea  jmp     loc_14010CE2D
0x14010ceef  cmp     cs:?m_VolumePathWaitTimeoutMilliSecs@CBlbVhdHelper@@2KA, r14d; ulong CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs
0x14010cef6  mov     ebx, r14d
0x14010cef9  mov     edi, 80070000h
0x14010cefe  mov     sil, 2
0x14010cf01  jbe     loc_14010CFE1
0x14010cf07  lea     r13, WPP_GLOBAL_Control
0x14010cf0e  lea     rdx, [rsp+6E0h+var_698]; unsigned int *
0x14010cf13  lea     rcx, [rsp+6E0h+FileName]; lpFileName
0x14010cf18  call    ?BlbGetVolumeNumber@@YAJPEBGPEAK@Z; BlbGetVolumeNumber(ushort const *,ulong *)
0x14010cf1d  test    eax, eax
0x14010cf1f  jns     loc_14010CFDC
0x14010cf25  call    cs:__imp_GetLastError
0x14010cf2b  test    eax, eax
0x14010cf2d  jle     short loc_14010CF34
0x14010cf2f  movzx   eax, ax
0x14010cf32  or      eax, edi
0x14010cf34  mov     rcx, cs:WPP_GLOBAL_Control
0x14010cf3b  cmp     rcx, r13
0x14010cf3e  jz      short loc_14010CF68
0x14010cf40  test    byte ptr [rcx+1Ch], 1
0x14010cf44  jz      short loc_14010CF68
0x14010cf46  cmp     [rcx+19h], sil
0x14010cf4a  jb      short loc_14010CF68
0x14010cf4c  mov     rcx, [rcx+10h]
0x14010cf50  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010cf57  mov     edx, 37h ; '7'
0x14010cf5c  mov     [rsp+6E0h+dwCreationDisposition], eax
0x14010cf60  mov     r9d, ebx
0x14010cf63  call    WPP_SF_LD
0x14010cf68  mov     eax, 88888889h
0x14010cf6d  mul     cs:?m_VolumePathWaitTimeoutMilliSecs@CBlbVhdHelper@@2KA; ulong CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs
0x14010cf73  shr     edx, 4
0x14010cf76  mov     ecx, edx; dwMilliseconds
0x14010cf78  call    cs:__imp_Sleep
0x14010cf7e  mov     eax, 88888889h
0x14010cf83  mul     cs:?m_VolumePathWaitTimeoutMilliSecs@CBlbVhdHelper@@2KA; ulong CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs
0x14010cf89  shr     edx, 4
0x14010cf8c  add     ebx, edx
0x14010cf8e  cmp     ebx, cs:?m_VolumePathWaitTimeoutMilliSecs@CBlbVhdHelper@@2KA; ulong CBlbVhdHelper::m_VolumePathWaitTimeoutMilliSecs
0x14010cf94  jb      loc_14010CF0E
0x14010cf9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14010cfa1  cmp     rcx, r13
0x14010cfa4  jz      short loc_14010CFD2
0x14010cfa6  test    byte ptr [rcx+1Ch], 1
0x14010cfaa  jz      short loc_14010CFD2
0x14010cfac  cmp     [rcx+19h], sil
0x14010cfb0  jb      short loc_14010CFD2
0x14010cfb2  mov     rcx, [rcx+10h]
0x14010cfb6  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010cfbd  mov     edx, 38h ; '8'
0x14010cfc2  mov     [rsp+6E0h+dwCreationDisposition], 8078004Fh
0x14010cfca  mov     r9d, ebx
0x14010cfcd  call    WPP_SF_LD
0x14010cfd2  mov     ebx, 8078004Fh
0x14010cfd7  jmp     loc_14010D1E2
0x14010cfdc  mov     r13d, [rsp+6E0h+var_698]
0x14010cfe1  mov     r9d, r13d
0x14010cfe4  lea     r8, aGlobalrootDevi_3; "\\\\?\\Globalroot\\Device\\HarddiskVolu"...
0x14010cfeb  mov     rdx, r15; unsigned __int64
0x14010cfee  lea     rcx, [rbp+5E0h+var_460]; unsigned __int16 *
0x14010cff5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010cffa  mov     ebx, eax
0x14010cffc  test    eax, eax
0x14010cffe  jns     short loc_14010D035
0x14010d000  mov     rcx, cs:WPP_GLOBAL_Control
0x14010d007  lea     rax, WPP_GLOBAL_Control
0x14010d00e  cmp     rcx, rax
0x14010d011  jz      loc_14010D1E2
0x14010d017  test    byte ptr [rcx+1Ch], 1
0x14010d01b  jz      loc_14010D1E2
0x14010d021  cmp     [rcx+19h], sil
0x14010d025  jb      loc_14010D1E2
0x14010d02b  mov     edx, 39h ; '9'
0x14010d030  jmp     loc_14010CE2D
0x14010d035  xor     r8d, r8d; unsigned __int64
0x14010d038  lea     rcx, [rbp+5E0h+var_460]; unsigned __int16 *
0x14010d03f  mov     rdx, r12; unsigned __int16 **
0x14010d042  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14010d047  mov     ebx, eax
0x14010d049  test    eax, eax
0x14010d04b  jns     short loc_14010D082
0x14010d04d  mov     rcx, cs:WPP_GLOBAL_Control
0x14010d054  lea     rax, WPP_GLOBAL_Control
0x14010d05b  cmp     rcx, rax
0x14010d05e  jz      loc_14010D1E2
0x14010d064  test    byte ptr [rcx+1Ch], 1
0x14010d068  jz      loc_14010D1E2
0x14010d06e  cmp     [rcx+19h], sil
0x14010d072  jb      loc_14010D1E2
0x14010d078  mov     edx, 3Ah ; ':'
0x14010d07d  jmp     loc_14010CE2D
0x14010d082  lea     rdx, [rsp+6E0h+lpszVolumeMountPoint]; unsigned __int16 **
0x14010d087  lea     rcx, [rsp+6E0h+FileName]; unsigned __int16 *
0x14010d08c  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14010d091  mov     ebx, eax
0x14010d093  test    eax, eax
0x14010d095  jns     short loc_14010D0E5
0x14010d097  mov     rcx, cs:WPP_GLOBAL_Control
0x14010d09e  lea     rax, WPP_GLOBAL_Control
0x14010d0a5  cmp     rcx, rax
0x14010d0a8  jz      loc_14010D1E2
0x14010d0ae  test    byte ptr [rcx+1Ch], 1
0x14010d0b2  jz      loc_14010D1E2
0x14010d0b8  cmp     [rcx+19h], sil
  ... truncated ...
```
