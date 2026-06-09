# CBlbBackupAsync::WriteMediaId(_GUID,ushort *)

- ea: `0x14003a8f0`
- end: `0x14003b13a`
- name: `?WriteMediaId@CBlbBackupAsync@@AEAAJU_GUID@@PEAG@Z`
- size: `2122`
- prototype: `int(CBlbBackupAsync *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x14002fe00`

## callees

- `0x140006d94`
- `0x140008ac8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014260`
- `0x140014384`
- `0x140014798`
- `0x140028eb8`
- `0x140035350`
- `0x14003a8f0`
- `0x14003c434`
- `0x14003cb70`
- `0x14003cbfc`
- `0x1400881ac`
- `0x14008863c`
- `0x1400889f0`
- `0x14008ca7c`
- `0x14008e808`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!ReadFile` at `0x14003ae0e`
- `KERNEL32!ReadFile` at `0x14003ae0e`
- `KERNEL32!MoveFileExW` at `0x14003acde`
- `KERNEL32!MoveFileExW` at `0x14003acde`
- `KERNEL32!FlushFileBuffers` at `0x14003ac41`
- `KERNEL32!FlushFileBuffers` at `0x14003ac41`
- `KERNEL32!WriteFile` at `0x14003ab79`
- `KERNEL32!WriteFile` at `0x14003ab79`
- `KERNEL32!DeleteFileW` at `0x14003aad8`
- `KERNEL32!DeleteFileW` at `0x14003aad8`
- `KERNEL32!CloseHandle` at `0x14003acb0`
- `KERNEL32!CloseHandle` at `0x14003b019`
- `KERNEL32!CloseHandle` at `0x14003b031`
- `KERNEL32!CloseHandle` at `0x14003acb0`
- `KERNEL32!CloseHandle` at `0x14003b019`
- `KERNEL32!CloseHandle` at `0x14003b031`
- `KERNEL32!GetLastError` at `0x14003aae6`
- `KERNEL32!GetLastError` at `0x14003ab83`
- `KERNEL32!GetLastError` at `0x14003ac54`
- `KERNEL32!GetLastError` at `0x14003ace8`
- `KERNEL32!GetLastError` at `0x14003ae18`
- `KERNEL32!GetLastError` at `0x14003aae6`
- `KERNEL32!GetLastError` at `0x14003ab83`
- `KERNEL32!GetLastError` at `0x14003ac54`
- `KERNEL32!GetLastError` at `0x14003ace8`
- `KERNEL32!GetLastError` at `0x14003ae18`
- `ntdll!RtlGetLastNtStatus` at `0x14003ac4b`
- `ntdll!RtlGetLastNtStatus` at `0x14003ac4b`
- `ole32!CoTaskMemFree` at `0x14003b0d7`
- `ole32!CoTaskMemFree` at `0x14003b0d7`

## string_xrefs

- `0x14003aab3`: `\TempMediaId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupAsync::WriteMediaId(CBlbBackupAsync *this, struct _GUID *a2, unsigned __int16 *a3)
{
  PVOID *v6; // rbx
  signed int appended; // edi
  char v8; // r12
  WCHAR *v9; // r13
  int v10; // eax
  void *v11; // rcx
  unsigned __int16 *v12; // r14
  DWORD LastError; // eax
  HANDLE v14; // rbx
  DWORD v15; // eax
  char LastNtStatus; // r14
  DWORD v17; // eax
  DWORD v18; // eax
  bool v19; // sf
  int v20; // eax
  signed int v21; // eax
  void *v22; // rax
  CBlbFileVerifier *v23; // r15
  _QWORD *v24; // rbx
  unsigned __int64 v25; // r14
  BlbGuidStr *v26; // rbx
  unsigned int v27; // eax
  int v28; // eax
  void *v30; // [rsp+28h] [rbp-D8h]
  void *v31; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v37; // [rsp+68h] [rbp-98h]
  GUID Buffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[112]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[112]; // [rsp+F0h] [rbp-10h] BYREF

  v37 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  hObject = (HANDLE)-1LL;
  hFile = (HANDLE)-1LL;
  lpFileName = 0;
  Buffer = GUID_NULL;
  NumberOfBytesWritten = 0;
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      WPP_SF_(v6[2], 255, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    appended = -2147024809;
    goto LABEL_115;
  }
  v8 = 0;
  if ( (*((_BYTE *)this + 340) & 1) != 0 )
  {
    appended = BlbutilDuplicateString(a3, (unsigned __int16 **)&lpFileName, 0);
    if ( appended >= 0 )
    {
      v9 = (WCHAR *)lpFileName;
      goto LABEL_14;
    }
LABEL_111:
    v9 = (WCHAR *)lpFileName;
    goto LABEL_112;
  }
  appended = BlbutilAppendString(
               *((const unsigned __int16 **)this + 73),
               L"\\TempMediaId",
               (unsigned __int16 **)&lpFileName);
  if ( appended < 0 )
    goto LABEL_111;
  v9 = (WCHAR *)lpFileName;
  if ( !DeleteFileW(lpFileName) )
  {
    LastError = GetLastError();
    appended = LastError;
    if ( LastError != 2 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          256,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v9,
          LastError);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( appended > 0 )
        appended = (unsigned __int16)appended | 0x80070000;
      v12 = a3;
      goto LABEL_99;
    }
  }
LABEL_14:
  v10 = BlbutilTargetCreateFile(v9, 0xC0000000, 0, 2u, 0x80u, v30, *((_DWORD *)this + 84) != 4, &hFile);
  appended = v10;
  if ( v10 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        257,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v9,
        v10);
      v11 = hFile;
      v12 = a3;
LABEL_96:
      v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_97:
      if ( v11 != (void *)-1LL )
      {
        CloseHandle(v11);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_99;
    }
LABEL_37:
    v11 = hFile;
    v12 = a3;
    goto LABEL_97;
  }
  v8 = *((_BYTE *)this + 340) & 1;
  v14 = hFile;
  if ( !WriteFile(hFile, a2, 0x10u, &NumberOfBytesWritten, 0) )
  {
    v15 = GetLastError();
    appended = v15;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        258,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v9,
        v15);
LABEL_34:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( NumberOfBytesWritten != 16 )
  {
    appended = -2147023779;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_37;
  }
  if ( !FlushFileBuffers(v14) )
  {
    LastNtStatus = RtlGetLastNtStatus();
    v17 = GetLastError();
    appended = v17;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SLd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        260,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v9,
        v17,
        LastNtStatus);
      goto LABEL_34;
    }
LABEL_35:
    if ( appended > 0 )
      appended = (unsigned __int16)appended | 0x80070000;
    goto LABEL_37;
  }
  CloseHandle(v14);
  lpFileName = (LPCWSTR)-1LL;
  if ( (*((_BYTE *)this + 340) & 1) == 0 )
  {
    if ( !MoveFileExW(v9, a3, 1u) )
    {
      v18 = GetLastError();
      appended = v18;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v12 = a3;
      }
      else
      {
        v12 = a3;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            261,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v9,
            (__int64)a3,
            v18);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      v19 = appended < 0;
      if ( appended <= 0 )
        goto LABEL_100;
      appended = (unsigned __int16)appended | 0x80070000;
      goto LABEL_99;
    }
    v8 = 1;
  }
  v20 = BlbutilTargetCreateFile(a3, 0x80000000, 1u, 3u, 0x2000000u, v31, 0, &hObject);
  appended = v20;
  if ( v20 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = a3;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_94;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        262,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)a3,
        v20);
      goto LABEL_63;
    }
    goto LABEL_93;
  }
  NumberOfBytesWritten = 0;
  if ( ReadFile(hObject, &Buffer, 0x10u, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten == 16 && !memcmp_0(&Buffer, a2, 0x10u) )
    {
      if ( *((char *)this + 340) < 0 && *((_BYTE *)this + 276) )
      {
        v22 = operator new(0x40u);
        hFile = v22;
        v23 = v22 ? CBlbFileVerifier::CBlbFileVerifier((CBlbFileVerifier *)v22) : 0LL;
        appended = CBlbFileVerifier::Init(v23, a3);
        if ( appended >= 0 )
        {
          appended = CBlbFileVerifier::SetChecksumForData(v23, v37, 0x10u);
          if ( appended < 0 )
          {
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
              v6 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_93;
          }
          v24 = (_QWORD *)((char *)this + 776);
          v25 = *((_QWORD *)this + 98);
          if ( v25 >= v24[2]
            && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                   v24,
                                   v25 + 1) )
          {
            ATL::AtlThrowImpl(-2147024882);
          }
          *(_QWORD *)(*v24 + 8 * v25) = v23;
          ++v24[1];
        }
      }
    }
    else
    {
      appended = -2147023779;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v26 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v39, &Buffer);
      v27 = (unsigned int)BlbGuidStr::BlbGuidStr((BlbGuidStr *)v40, a2);
      WPP_SF_SLSL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        264,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        v27,
        16,
        (__int64)v26,
        16);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_93:
    v12 = a3;
    goto LABEL_94;
  }
  v21 = GetLastError();
  appended = v21;
  if ( v21 > 0 )
    appended = (unsigned __int16)v21 | 0x80070000;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_93;
  v12 = a3;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      263,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (_DWORD)a3,
      appended);
LABEL_63:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_94:
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    v11 = (void *)lpFileName;
    goto LABEL_96;
  }
LABEL_99:
  v19 = appended < 0;
LABEL_100:
  if ( v19 && v8 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
      WPP_SF_Sd(
        (unsigned int)v6[2],
        266,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v12,
        appended);
    v28 = BlbutilDeleteFile(v12, 0, 0);
    if ( v28 >= 0 )
      goto LABEL_112;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        267,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)v12,
        v28);
LABEL_112:
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v9 )
  {
    CoTaskMemFree(v9);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_115:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 268, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14003a8f0  mov     [rsp-8+arg_18], rbx
0x14003a8f5  push    rbp
0x14003a8f6  push    rsi
0x14003a8f7  push    rdi
0x14003a8f8  push    r12
0x14003a8fa  push    r13
0x14003a8fc  push    r14
0x14003a8fe  push    r15
0x14003a900  lea     rbp, [rsp-70h]
0x14003a905  sub     rsp, 170h
0x14003a90c  mov     rax, cs:__security_cookie
0x14003a913  xor     rax, rsp
0x14003a916  mov     [rbp+0A0h+var_40], rax
0x14003a91a  mov     rdi, r8
0x14003a91d  mov     [rsp+1A0h+lpNewFileName], r8
0x14003a922  mov     r15, rdx
0x14003a925  mov     [rsp+1A0h+var_138], rdx
0x14003a92a  mov     r14, rcx
0x14003a92d  lea     rsi, WPP_GLOBAL_Control
0x14003a934  mov     rbx, cs:WPP_GLOBAL_Control
0x14003a93b  cmp     rbx, rsi
0x14003a93e  jz      short loc_14003A968
0x14003a940  test    byte ptr [rbx+1Ch], 1
0x14003a944  jz      short loc_14003A968
0x14003a946  cmp     byte ptr [rbx+19h], 4
0x14003a94a  jb      short loc_14003A968
0x14003a94c  mov     edx, 0FEh
0x14003a951  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a958  mov     rcx, [rbx+10h]
0x14003a95c  call    WPP_SF_
0x14003a961  mov     rbx, cs:WPP_GLOBAL_Control
0x14003a968  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003a96c  mov     [rsp+1A0h+hObject], rax
0x14003a971  mov     [rsp+1A0h+hFile], rax
0x14003a976  mov     [rsp+1A0h+lpFileName], 0
0x14003a97f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14003a986  movdqu  [rsp+1A0h+Buffer], xmm0
0x14003a98c  mov     [rsp+1A0h+NumberOfBytesWritten], 0
0x14003a994  lea     r8d, [rax+11h]; Size
0x14003a998  lea     rdx, GUID_NULL; Buf2
0x14003a99f  mov     rcx, r15; Buf1
0x14003a9a2  call    memcmp_0
0x14003a9a7  test    eax, eax
0x14003a9a9  jnz     short loc_14003A9E5
0x14003a9ab  cmp     rbx, rsi
0x14003a9ae  jz      short loc_14003A9DB
0x14003a9b0  test    byte ptr [rbx+1Ch], 1
0x14003a9b4  jz      short loc_14003A9DB
0x14003a9b6  lea     esi, [rax+2]
0x14003a9b9  cmp     [rbx+19h], sil
0x14003a9bd  jb      short loc_14003A9DB
0x14003a9bf  mov     edx, 0FFh
0x14003a9c4  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a9cb  mov     rcx, [rbx+10h]
0x14003a9cf  call    WPP_SF_
0x14003a9d4  mov     rbx, cs:WPP_GLOBAL_Control
0x14003a9db  mov     edi, 80070057h
0x14003a9e0  jmp     loc_14003B0E4
0x14003a9e5  xor     r12b, r12b
0x14003a9e8  mov     esi, 2
0x14003a9ed  test    byte ptr [r14+154h], 1
0x14003a9f5  jz      loc_14003AAAE
0x14003a9fb  xor     r8d, r8d; unsigned __int64
0x14003a9fe  lea     rdx, [rsp+1A0h+lpFileName]; unsigned __int16 **
0x14003aa03  mov     rcx, rdi; unsigned __int16 *
0x14003aa06  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003aa0b  mov     edi, eax
0x14003aa0d  test    eax, eax
0x14003aa0f  js      loc_14003B0C3
0x14003aa15  mov     r13, [rsp+1A0h+lpFileName]
0x14003aa1a  cmp     dword ptr [r14+150h], 4
0x14003aa22  setnz   al
0x14003aa25  lea     rcx, [rsp+1A0h+hFile]
0x14003aa2a  mov     [rsp+1A0h+var_168], rcx; void **
0x14003aa2f  mov     [rsp+1A0h+var_170], al; char
0x14003aa33  mov     dword ptr [rsp+1A0h+lpOverlapped], 80h; DWORD
0x14003aa3b  mov     r9d, esi; dwCreationDisposition
0x14003aa3e  xor     r8d, r8d; dwShareMode
0x14003aa41  mov     edx, 0C0000000h; dwDesiredAccess
0x14003aa46  mov     rcx, r13; lpFileName
0x14003aa49  call    ?BlbutilTargetCreateFile@@YAJPEBGKKKKPEAXEPEAPEAX@Z; BlbutilTargetCreateFile(ushort const *,ulong,ulong,ulong,ulong,void *,uchar,void * *)
0x14003aa4e  mov     edi, eax
0x14003aa50  test    eax, eax
0x14003aa52  jns     loc_14003AB4F
0x14003aa58  mov     rbx, cs:WPP_GLOBAL_Control
0x14003aa5f  lea     r15, WPP_GLOBAL_Control
0x14003aa66  cmp     rbx, r15
0x14003aa69  jz      loc_14003ABDA
0x14003aa6f  test    byte ptr [rbx+1Ch], 1
0x14003aa73  jz      loc_14003ABDA
0x14003aa79  cmp     [rbx+19h], sil
0x14003aa7d  jb      loc_14003ABDA
0x14003aa83  mov     edx, 101h
0x14003aa88  mov     dword ptr [rsp+1A0h+lpOverlapped], eax
0x14003aa8c  mov     r9, r13
0x14003aa8f  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003aa96  mov     rcx, [rbx+10h]
0x14003aa9a  call    WPP_SF_Sd
0x14003aa9f  mov     rcx, [rsp+1A0h+hFile]
0x14003aaa4  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003aaa9  jmp     loc_14003B024
0x14003aaae  lea     r8, [rsp+1A0h+lpFileName]; unsigned __int16 **
0x14003aab3  lea     rdx, aTempmediaid; "\\TempMediaId"
0x14003aaba  mov     rcx, [r14+248h]; unsigned __int16 *
0x14003aac1  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14003aac6  mov     edi, eax
0x14003aac8  test    eax, eax
0x14003aaca  js      loc_14003B0C3
0x14003aad0  mov     r13, [rsp+1A0h+lpFileName]
0x14003aad5  mov     rcx, r13; lpFileName
0x14003aad8  call    cs:__imp_DeleteFileW
0x14003aade  test    eax, eax
0x14003aae0  jnz     loc_14003AA1A
0x14003aae6  call    cs:__imp_GetLastError
0x14003aaec  mov     edi, eax
0x14003aaee  cmp     eax, esi
0x14003aaf0  jz      loc_14003AA1A
0x14003aaf6  mov     rbx, cs:WPP_GLOBAL_Control
0x14003aafd  lea     r15, WPP_GLOBAL_Control
0x14003ab04  cmp     rbx, r15
0x14003ab07  jz      short loc_14003AB38
0x14003ab09  test    byte ptr [rbx+1Ch], 1
0x14003ab0d  jz      short loc_14003AB38
0x14003ab0f  cmp     [rbx+19h], sil
0x14003ab13  jb      short loc_14003AB38
0x14003ab15  mov     edx, 100h
0x14003ab1a  mov     dword ptr [rsp+1A0h+lpOverlapped], eax
0x14003ab1e  mov     r9, r13
0x14003ab21  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003ab28  mov     rcx, [rbx+10h]
0x14003ab2c  call    WPP_SF_Sd
0x14003ab31  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ab38  test    edi, edi
0x14003ab3a  jle     short loc_14003AB45
0x14003ab3c  movzx   edi, di
0x14003ab3f  or      edi, 80070000h
0x14003ab45  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003ab4a  jmp     loc_14003B03E
0x14003ab4f  mov     r12b, [r14+154h]
0x14003ab56  and     r12b, 1
0x14003ab5a  mov     [rsp+1A0h+lpOverlapped], 0; lpOverlapped
0x14003ab63  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003ab68  mov     r8d, 10h; nNumberOfBytesToWrite
0x14003ab6e  mov     rdx, r15; lpBuffer
0x14003ab71  mov     rbx, [rsp+1A0h+hFile]
0x14003ab76  mov     rcx, rbx; hFile
0x14003ab79  call    cs:__imp_WriteFile
0x14003ab7f  test    eax, eax
0x14003ab81  jnz     short loc_14003ABE9
0x14003ab83  call    cs:__imp_GetLastError
0x14003ab89  mov     edi, eax
0x14003ab8b  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ab92  lea     r15, WPP_GLOBAL_Control
0x14003ab99  cmp     rbx, r15
0x14003ab9c  jz      short loc_14003ABCD
0x14003ab9e  test    byte ptr [rbx+1Ch], 1
0x14003aba2  jz      short loc_14003ABCD
0x14003aba4  cmp     [rbx+19h], sil
0x14003aba8  jb      short loc_14003ABCD
0x14003abaa  mov     edx, 102h
0x14003abaf  mov     dword ptr [rsp+1A0h+lpOverlapped], eax
0x14003abb3  mov     r9, r13
0x14003abb6  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003abbd  mov     rcx, [rbx+10h]
0x14003abc1  call    WPP_SF_Sd
0x14003abc6  mov     rbx, cs:WPP_GLOBAL_Control
0x14003abcd  test    edi, edi
0x14003abcf  jle     short loc_14003ABDA
0x14003abd1  movzx   edi, di
0x14003abd4  or      edi, 80070000h
0x14003abda  mov     rcx, [rsp+1A0h+hFile]
0x14003abdf  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003abe4  jmp     loc_14003B02B
0x14003abe9  mov     r9d, [rsp+1A0h+NumberOfBytesWritten]
0x14003abee  cmp     r9d, 10h
0x14003abf2  jz      short loc_14003AC3E
0x14003abf4  mov     edi, 8007045Dh
0x14003abf9  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ac00  lea     r15, WPP_GLOBAL_Control
0x14003ac07  cmp     rbx, r15
0x14003ac0a  jz      short loc_14003ABDA
0x14003ac0c  test    byte ptr [rbx+1Ch], 1
0x14003ac10  jz      short loc_14003ABDA
0x14003ac12  cmp     [rbx+19h], sil
0x14003ac16  jb      short loc_14003ABDA
0x14003ac18  mov     edx, 103h
0x14003ac1d  mov     dword ptr [rsp+1A0h+lpOverlapped], 10h
0x14003ac25  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003ac2c  mov     rcx, [rbx+10h]
0x14003ac30  call    WPP_SF_dd
0x14003ac35  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ac3c  jmp     short loc_14003ABDA
0x14003ac3e  mov     rcx, rbx; hFile
0x14003ac41  call    cs:__imp_FlushFileBuffers
0x14003ac47  test    eax, eax
0x14003ac49  jnz     short loc_14003ACAD
0x14003ac4b  call    cs:__imp_RtlGetLastNtStatus
0x14003ac51  mov     r14d, eax
0x14003ac54  call    cs:__imp_GetLastError
0x14003ac5a  mov     edi, eax
0x14003ac5c  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ac63  lea     r15, WPP_GLOBAL_Control
0x14003ac6a  cmp     rbx, r15
0x14003ac6d  jz      loc_14003ABCD
0x14003ac73  test    byte ptr [rbx+1Ch], 1
0x14003ac77  jz      loc_14003ABCD
0x14003ac7d  cmp     [rbx+19h], sil
0x14003ac81  jb      loc_14003ABCD
0x14003ac87  mov     edx, 104h
0x14003ac8c  mov     dword ptr [rsp+1A0h+var_178], r14d
0x14003ac91  mov     dword ptr [rsp+1A0h+lpOverlapped], eax
0x14003ac95  mov     r9, r13
0x14003ac98  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003ac9f  mov     rcx, [rbx+10h]
0x14003aca3  call    WPP_SF_SLd
0x14003aca8  jmp     loc_14003ABC6
0x14003acad  mov     rcx, rbx; hObject
0x14003acb0  call    cs:__imp_CloseHandle
0x14003acb6  mov     [rsp+1A0h+lpFileName], 0FFFFFFFFFFFFFFFFh
0x14003acbf  mov     rbx, [rsp+1A0h+lpNewFileName]
0x14003acc4  test    byte ptr [r14+154h], 1
0x14003accc  jnz     loc_14003AD5C
0x14003acd2  mov     r8d, 1; dwFlags
0x14003acd8  mov     rdx, rbx; lpNewFileName
0x14003acdb  mov     rcx, r13; lpExistingFileName
0x14003acde  call    cs:__imp_MoveFileExW
0x14003ace4  test    eax, eax
0x14003ace6  jnz     short loc_14003AD59
0x14003ace8  call    cs:__imp_GetLastError
0x14003acee  mov     edi, eax
0x14003acf0  mov     rbx, cs:WPP_GLOBAL_Control
0x14003acf7  lea     r15, WPP_GLOBAL_Control
0x14003acfe  cmp     rbx, r15
0x14003ad01  jz      short loc_14003AD3E
0x14003ad03  test    byte ptr [rbx+1Ch], 1
0x14003ad07  jz      short loc_14003AD3E
0x14003ad09  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003ad0e  cmp     [rbx+19h], sil
0x14003ad12  jb      short loc_14003AD43
0x14003ad14  mov     edx, 105h
0x14003ad19  mov     dword ptr [rsp+1A0h+var_178], eax
0x14003ad1d  mov     [rsp+1A0h+lpOverlapped], r14
0x14003ad22  mov     r9, r13
0x14003ad25  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003ad2c  mov     rcx, [rbx+10h]
0x14003ad30  call    WPP_SF_SSD
0x14003ad35  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ad3c  jmp     short loc_14003AD43
0x14003ad3e  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003ad43  test    edi, edi
0x14003ad45  jle     loc_14003B040
0x14003ad4b  movzx   edi, di
0x14003ad4e  or      edi, 80070000h
0x14003ad54  jmp     loc_14003B03E
0x14003ad59  mov     r12b, 1
0x14003ad5c  lea     rax, [rsp+1A0h+hObject]
0x14003ad61  mov     [rsp+1A0h+var_168], rax; void **
0x14003ad66  mov     [rsp+1A0h+var_170], 0; char
0x14003ad6b  mov     dword ptr [rsp+1A0h+lpOverlapped], 2000000h; DWORD
0x14003ad73  mov     edx, 80000000h; dwDesiredAccess
0x14003ad78  mov     r9d, 3; dwCreationDisposition
0x14003ad7e  lea     r8d, [r9-2]; dwShareMode
0x14003ad82  mov     rcx, rbx; lpFileName
0x14003ad85  call    ?BlbutilTargetCreateFile@@YAJPEBGKKKKPEAXEPEAPEAX@Z; BlbutilTargetCreateFile(ushort const *,ulong,ulong,ulong,ulong,void *,uchar,void * *)
0x14003ad8a  mov     edi, eax
0x14003ad8c  test    eax, eax
0x14003ad8e  jns     short loc_14003ADE8
0x14003ad90  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ad97  lea     r15, WPP_GLOBAL_Control
0x14003ad9e  cmp     rbx, r15
0x14003ada1  jz      loc_14003B007
0x14003ada7  test    byte ptr [rbx+1Ch], 1
0x14003adab  jz      loc_14003B007
0x14003adb1  mov     r14, [rsp+1A0h+lpNewFileName]
0x14003adb6  cmp     [rbx+19h], sil
0x14003adba  jb      loc_14003B00C
0x14003adc0  mov     edx, 106h
0x14003adc5  mov     dword ptr [rsp+1A0h+lpOverlapped], eax
0x14003adc9  mov     r9, r14
0x14003adcc  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003add3  mov     rcx, [rbx+10h]
0x14003add7  call    WPP_SF_Sd
0x14003addc  mov     rbx, cs:WPP_GLOBAL_Control
0x14003ade3  jmp     loc_14003B00C
0x14003ade8  mov     [rsp+1A0h+NumberOfBytesWritten], 0
0x14003adf0  mov     [rsp+1A0h+lpOverlapped], 0; lpOverlapped
0x14003adf9  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x14003adfe  mov     r8d, 10h; nNumberOfBytesToRead
0x14003ae04  lea     rdx, [rsp+1A0h+Buffer]; lpBuffer
0x14003ae09  mov     rcx, [rsp+1A0h+hObject]; hFile
0x14003ae0e  call    cs:__imp_ReadFile
0x14003ae14  test    eax, eax
0x14003ae16  jnz     short loc_14003AE6B
0x14003ae18  call    cs:__imp_GetLastError
0x14003ae1e  mov     edi, eax
0x14003ae20  test    eax, eax
0x14003ae22  jle     short loc_14003AE2D
0x14003ae24  movzx   edi, ax
0x14003ae27  or      edi, 80070000h
0x14003ae2d  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
