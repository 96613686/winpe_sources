# BlbSafeDumpFile(ushort const *,ushort const *,_BLB_MEDIA_TYPE,ushort const *)

- ea: `0x1400f3bbc`
- end: `0x1400f3f57`
- name: `?BlbSafeDumpFile@@YAJPEBG0W4_BLB_MEDIA_TYPE@@0@Z`
- size: `923`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1400399bc`
- `0x14003a154`
- `0x14003b140`
- `0x14003b4e4`
- `0x14003be8c`

## callees

- `0x140006ca8`
- `0x140014260`
- `0x140014384`
- `0x14003cb70`
- `0x14008e808`
- `0x14009257c`
- `0x1400f3bbc`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x1400f3e9d`
- `KERNEL32!MoveFileExW` at `0x1400f3e9d`
- `KERNEL32!FlushFileBuffers` at `0x1400f3e1a`
- `KERNEL32!FlushFileBuffers` at `0x1400f3e1a`
- `KERNEL32!WriteFile` at `0x1400f3dbd`
- `KERNEL32!WriteFile` at `0x1400f3dbd`
- `KERNEL32!DeleteFileW` at `0x1400f3c13`
- `KERNEL32!DeleteFileW` at `0x1400f3cf1`
- `KERNEL32!DeleteFileW` at `0x1400f3c13`
- `KERNEL32!DeleteFileW` at `0x1400f3cf1`
- `KERNEL32!CloseHandle` at `0x1400f3e80`
- `KERNEL32!CloseHandle` at `0x1400f3f0a`
- `KERNEL32!CloseHandle` at `0x1400f3e80`
- `KERNEL32!CloseHandle` at `0x1400f3f0a`
- `KERNEL32!GetLastError` at `0x1400f3c1d`
- `KERNEL32!GetLastError` at `0x1400f3cff`
- `KERNEL32!GetLastError` at `0x1400f3dc7`
- `KERNEL32!GetLastError` at `0x1400f3e2c`
- `KERNEL32!GetLastError` at `0x1400f3eab`
- `KERNEL32!GetLastError` at `0x1400f3c1d`
- `KERNEL32!GetLastError` at `0x1400f3cff`
- `KERNEL32!GetLastError` at `0x1400f3dc7`
- `KERNEL32!GetLastError` at `0x1400f3e2c`
- `KERNEL32!GetLastError` at `0x1400f3eab`
- `ntdll!RtlGetLastNtStatus` at `0x1400f3e24`
- `ntdll!RtlGetLastNtStatus` at `0x1400f3e24`

## pseudocode

```c
__int64 __fastcall BlbSafeDumpFile(const WCHAR *a1, const WCHAR *a2, unsigned int a3, _WORD *a4)
{
  char BackupFeatures; // al
  int v9; // r12d
  const WCHAR *v10; // rbp
  DWORD LastError; // eax
  int v12; // eax
  signed int v13; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdi
  DWORD v16; // eax
  bool v17; // sf
  __int64 v18; // r8
  const void *v19; // rdx
  DWORD v20; // eax
  char LastNtStatus; // si
  DWORD v22; // eax
  DWORD v23; // eax
  void *v25; // [rsp+28h] [rbp-70h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-58h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-50h] BYREF

  BackupFeatures = BlbutilGetBackupFeatures(a3);
  hFile = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v9 = BackupFeatures & 1;
  if ( (BackupFeatures & 1) != 0 )
  {
    v10 = a1;
    if ( !DeleteFileW(a1) )
    {
      LastError = GetLastError();
      if ( LastError != 2
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
          (_DWORD)a1,
          LastError);
      }
    }
LABEL_8:
    v12 = BlbutilTargetCreateFile(v10, 0xC0000000, 0, 2u, 0x80u, v25, a3 != 4, &hFile);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v15 = (__int64)hFile;
      }
      else
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
          (_DWORD)v10,
          v12);
        v14 = (PVOID *)WPP_GLOBAL_Control;
        v15 = (__int64)hFile;
      }
LABEL_45:
      if ( v15 != -1 )
      {
        CloseHandle((HANDLE)v15);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_47;
    }
    if ( !a4 )
      BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x191u, "lpDataToDump");
    v18 = -1;
    do
      ++v18;
    while ( a4[v18] );
    v19 = a4;
    v15 = (__int64)hFile;
    if ( WriteFile(hFile, v19, 2 * v18 + 2, &NumberOfBytesWritten, 0) )
    {
      if ( FlushFileBuffers((HANDLE)v15) )
      {
        CloseHandle((HANDLE)v15);
        v15 = -1;
        if ( v9 || MoveFileExW(a2, a1, 9u) )
          return (unsigned int)v13;
        v23 = GetLastError();
        v13 = v23;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
          (_DWORD)a2,
          (__int64)a1,
          v23);
        goto LABEL_42;
      }
      LastNtStatus = RtlGetLastNtStatus();
      v22 = GetLastError();
      v13 = v22;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
          (_DWORD)v10,
          v22,
          LastNtStatus);
        goto LABEL_42;
      }
    }
    else
    {
      v20 = GetLastError();
      v13 = v20;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
          (_DWORD)v10,
          v20);
LABEL_42:
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
LABEL_43:
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_45;
  }
  v10 = a2;
  if ( DeleteFileW(a2) )
    goto LABEL_8;
  v16 = GetLastError();
  v13 = v16;
  if ( v16 == 2 )
    goto LABEL_8;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
      (_DWORD)a2,
      v16);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = v13 < 0;
  if ( v13 <= 0 )
    goto LABEL_48;
  v13 = (unsigned __int16)v13 | 0x80070000;
LABEL_47:
  v17 = v13 < 0;
LABEL_48:
  if ( v17 && v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
    WPP_SF_Sd((unsigned int)v14[2], 26, (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids, (_DWORD)a1, v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400f3bbc  push    rbx
0x1400f3bbe  push    rbp
0x1400f3bbf  push    rsi
0x1400f3bc0  push    rdi
0x1400f3bc1  push    r12
0x1400f3bc3  push    r13
0x1400f3bc5  push    r14
0x1400f3bc7  push    r15
0x1400f3bc9  sub     rsp, 58h
0x1400f3bcd  mov     r13, rcx
0x1400f3bd0  mov     rdi, r9
0x1400f3bd3  mov     ecx, r8d
0x1400f3bd6  mov     r15d, r8d
0x1400f3bd9  mov     rsi, rdx
0x1400f3bdc  call    ?BlbutilGetBackupFeatures@@YAKW4_BLB_MEDIA_TYPE@@@Z; BlbutilGetBackupFeatures(_BLB_MEDIA_TYPE)
0x1400f3be1  mov     r12d, eax
0x1400f3be4  mov     [rsp+98h+hFile], 0FFFFFFFFFFFFFFFFh
0x1400f3bed  mov     [rsp+98h+NumberOfBytesWritten], 0
0x1400f3bf5  lea     rbx, WPP_GLOBAL_Control
0x1400f3bfc  lea     r14, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f3c03  and     r12d, 1
0x1400f3c07  jz      loc_1400F3CEB
0x1400f3c0d  mov     rcx, r13; lpFileName
0x1400f3c10  mov     rbp, r13
0x1400f3c13  call    cs:__imp_DeleteFileW
0x1400f3c19  test    eax, eax
0x1400f3c1b  jnz     short loc_1400F3C58
0x1400f3c1d  call    cs:__imp_GetLastError
0x1400f3c23  cmp     eax, 2
0x1400f3c26  jz      short loc_1400F3C58
0x1400f3c28  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3c2f  cmp     rcx, rbx
0x1400f3c32  jz      short loc_1400F3C58
0x1400f3c34  test    byte ptr [rcx+1Ch], 1
0x1400f3c38  jz      short loc_1400F3C58
0x1400f3c3a  cmp     byte ptr [rcx+19h], 3
0x1400f3c3e  jb      short loc_1400F3C58
0x1400f3c40  mov     rcx, [rcx+10h]
0x1400f3c44  mov     edx, 14h
0x1400f3c49  mov     r9, r13
0x1400f3c4c  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x1400f3c50  mov     r8, r14
0x1400f3c53  call    WPP_SF_Sd
0x1400f3c58  lea     rcx, [rsp+98h+hFile]
0x1400f3c5d  cmp     r15d, 4
0x1400f3c61  mov     [rsp+98h+var_60], rcx; void **
0x1400f3c66  mov     r9d, 2; dwCreationDisposition
0x1400f3c6c  setnz   al
0x1400f3c6f  mov     edx, 0C0000000h; dwDesiredAccess
0x1400f3c74  mov     [rsp+98h+var_68], al; char
0x1400f3c78  xor     r8d, r8d; dwShareMode
0x1400f3c7b  mov     rcx, rbp; lpFileName
0x1400f3c7e  mov     dword ptr [rsp+98h+lpOverlapped], 80h; DWORD
0x1400f3c86  call    ?BlbutilTargetCreateFile@@YAJPEBGKKKKPEAXEPEAPEAX@Z; BlbutilTargetCreateFile(ushort const *,ulong,ulong,ulong,ulong,void *,uchar,void * *)
0x1400f3c8b  xor     r15d, r15d
0x1400f3c8e  mov     ebx, eax
0x1400f3c90  test    eax, eax
0x1400f3c92  jns     loc_1400F3D75
0x1400f3c98  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3c9f  lea     r12, WPP_GLOBAL_Control
0x1400f3ca6  cmp     rcx, r12
0x1400f3ca9  jz      loc_1400F3D6B
0x1400f3caf  test    byte ptr [rcx+1Ch], 1
0x1400f3cb3  jz      loc_1400F3D6B
0x1400f3cb9  cmp     byte ptr [rcx+19h], 2
0x1400f3cbd  jb      loc_1400F3D6B
0x1400f3cc3  mov     rcx, [rcx+10h]
0x1400f3cc7  lea     edx, [r15+16h]
0x1400f3ccb  mov     r9, rbp
0x1400f3cce  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x1400f3cd2  mov     r8, r14
0x1400f3cd5  call    WPP_SF_Sd
0x1400f3cda  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3ce1  mov     rdi, [rsp+98h+hFile]
0x1400f3ce6  jmp     loc_1400F3F01
0x1400f3ceb  mov     rcx, rsi; lpFileName
0x1400f3cee  mov     rbp, rsi
0x1400f3cf1  call    cs:__imp_DeleteFileW
0x1400f3cf7  test    eax, eax
0x1400f3cf9  jnz     loc_1400F3C58
0x1400f3cff  call    cs:__imp_GetLastError
0x1400f3d05  mov     ebx, eax
0x1400f3d07  cmp     eax, 2
0x1400f3d0a  jz      loc_1400F3C58
0x1400f3d10  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3d17  lea     r12, WPP_GLOBAL_Control
0x1400f3d1e  lea     r14, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f3d25  cmp     rcx, r12
0x1400f3d28  jz      short loc_1400F3D55
0x1400f3d2a  test    byte ptr [rcx+1Ch], 1
0x1400f3d2e  jz      short loc_1400F3D55
0x1400f3d30  cmp     byte ptr [rcx+19h], 2
0x1400f3d34  jb      short loc_1400F3D55
0x1400f3d36  mov     rcx, [rcx+10h]
0x1400f3d3a  mov     edx, 15h
0x1400f3d3f  mov     r9, rsi
0x1400f3d42  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x1400f3d46  mov     r8, r14
0x1400f3d49  call    WPP_SF_Sd
0x1400f3d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3d55  test    ebx, ebx
0x1400f3d57  jle     loc_1400F3F19
0x1400f3d5d  movzx   ebx, bx
0x1400f3d60  or      ebx, 80070000h
0x1400f3d66  jmp     loc_1400F3F17
0x1400f3d6b  mov     rdi, [rsp+98h+hFile]
0x1400f3d70  jmp     loc_1400F3F01
0x1400f3d75  test    rdi, rdi
0x1400f3d78  jnz     short loc_1400F3D92
0x1400f3d7a  lea     r8, aLpdatatodump; "lpDataToDump"
0x1400f3d81  mov     edx, 191h; unsigned int
0x1400f3d86  lea     rcx, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f3d8d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f3d92  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400f3d96  inc     r8
0x1400f3d99  cmp     [rdi+r8*2], r15w
0x1400f3d9e  jnz     short loc_1400F3D96
0x1400f3da0  mov     rdx, rdi; lpBuffer
0x1400f3da3  mov     [rsp+98h+lpOverlapped], r15; lpOverlapped
0x1400f3da8  mov     rdi, [rsp+98h+hFile]
0x1400f3dad  lea     r8d, ds:2[r8*2]; nNumberOfBytesToWrite
0x1400f3db5  mov     rcx, rdi; hFile
0x1400f3db8  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400f3dbd  call    cs:__imp_WriteFile
0x1400f3dc3  test    eax, eax
0x1400f3dc5  jnz     short loc_1400F3E17
0x1400f3dc7  call    cs:__imp_GetLastError
0x1400f3dcd  mov     ebx, eax
0x1400f3dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3dd6  lea     r12, WPP_GLOBAL_Control
0x1400f3ddd  cmp     rcx, r12
0x1400f3de0  jz      loc_1400F3EF4
0x1400f3de6  test    byte ptr [rcx+1Ch], 1
0x1400f3dea  jz      loc_1400F3EF4
0x1400f3df0  cmp     byte ptr [rcx+19h], 2
0x1400f3df4  jb      loc_1400F3EF4
0x1400f3dfa  mov     rcx, [rcx+10h]
0x1400f3dfe  mov     edx, 17h
0x1400f3e03  mov     r9, rbp
0x1400f3e06  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x1400f3e0a  mov     r8, r14
0x1400f3e0d  call    WPP_SF_Sd
0x1400f3e12  jmp     loc_1400F3EED
0x1400f3e17  mov     rcx, rdi; hFile
0x1400f3e1a  call    cs:__imp_FlushFileBuffers
0x1400f3e20  test    eax, eax
0x1400f3e22  jnz     short loc_1400F3E7D
0x1400f3e24  call    cs:__imp_RtlGetLastNtStatus
0x1400f3e2a  mov     esi, eax
0x1400f3e2c  call    cs:__imp_GetLastError
0x1400f3e32  mov     ebx, eax
0x1400f3e34  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3e3b  lea     r12, WPP_GLOBAL_Control
0x1400f3e42  cmp     rcx, r12
0x1400f3e45  jz      loc_1400F3EF4
0x1400f3e4b  test    byte ptr [rcx+1Ch], 1
0x1400f3e4f  jz      loc_1400F3EF4
0x1400f3e55  cmp     byte ptr [rcx+19h], 2
0x1400f3e59  jb      loc_1400F3EF4
0x1400f3e5f  mov     rcx, [rcx+10h]
0x1400f3e63  mov     edx, 18h
0x1400f3e68  mov     dword ptr [rsp+98h+var_70], esi
0x1400f3e6c  mov     r9, rbp
0x1400f3e6f  mov     r8, r14
0x1400f3e72  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x1400f3e76  call    WPP_SF_SLd
0x1400f3e7b  jmp     short loc_1400F3EED
0x1400f3e7d  mov     rcx, rdi; hObject
0x1400f3e80  call    cs:__imp_CloseHandle
0x1400f3e86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400f3e8a  test    r12d, r12d
0x1400f3e8d  jnz     loc_1400F3F44
0x1400f3e93  lea     r8d, [rdi+0Ah]; dwFlags
0x1400f3e97  mov     rdx, r13; lpNewFileName
0x1400f3e9a  mov     rcx, rsi; lpExistingFileName
0x1400f3e9d  call    cs:__imp_MoveFileExW
0x1400f3ea3  test    eax, eax
0x1400f3ea5  jnz     loc_1400F3F44
0x1400f3eab  call    cs:__imp_GetLastError
0x1400f3eb1  mov     ebx, eax
0x1400f3eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3eba  lea     r12, WPP_GLOBAL_Control
0x1400f3ec1  cmp     rcx, r12
0x1400f3ec4  jz      short loc_1400F3EF4
0x1400f3ec6  test    byte ptr [rcx+1Ch], 1
0x1400f3eca  jz      short loc_1400F3EF4
0x1400f3ecc  cmp     byte ptr [rcx+19h], 2
0x1400f3ed0  jb      short loc_1400F3EF4
0x1400f3ed2  mov     rcx, [rcx+10h]
0x1400f3ed6  lea     edx, [rdi+1Ah]
0x1400f3ed9  mov     dword ptr [rsp+98h+var_70], eax
0x1400f3edd  mov     r9, rsi
0x1400f3ee0  mov     r8, r14
0x1400f3ee3  mov     [rsp+98h+lpOverlapped], r13
0x1400f3ee8  call    WPP_SF_SSD
0x1400f3eed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3ef4  test    ebx, ebx
0x1400f3ef6  jle     short loc_1400F3F01
0x1400f3ef8  movzx   ebx, bx
0x1400f3efb  or      ebx, 80070000h
0x1400f3f01  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400f3f05  jz      short loc_1400F3F17
0x1400f3f07  mov     rcx, rdi; hObject
0x1400f3f0a  call    cs:__imp_CloseHandle
0x1400f3f10  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3f17  test    ebx, ebx
0x1400f3f19  jns     short loc_1400F3F44
0x1400f3f1b  cmp     rcx, r12
0x1400f3f1e  jz      short loc_1400F3F44
0x1400f3f20  test    byte ptr [rcx+1Ch], 1
0x1400f3f24  jz      short loc_1400F3F44
0x1400f3f26  cmp     byte ptr [rcx+19h], 2
0x1400f3f2a  jb      short loc_1400F3F44
0x1400f3f2c  mov     rcx, [rcx+10h]
0x1400f3f30  mov     edx, 1Ah
0x1400f3f35  mov     r9, r13
0x1400f3f38  mov     dword ptr [rsp+98h+lpOverlapped], ebx
0x1400f3f3c  mov     r8, r14
0x1400f3f3f  call    WPP_SF_Sd
0x1400f3f44  mov     eax, ebx
0x1400f3f46  add     rsp, 58h
0x1400f3f4a  pop     r15
0x1400f3f4c  pop     r14
0x1400f3f4e  pop     r13
0x1400f3f50  pop     r12
0x1400f3f52  pop     rdi
0x1400f3f53  pop     rsi
0x1400f3f54  pop     rbp
0x1400f3f55  pop     rbx
0x1400f3f56  retn
```
