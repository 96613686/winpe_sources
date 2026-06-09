# BlbQueryVolumeSectorSize(ushort *,ulong *)

- ea: `0x140123a04`
- end: `0x140123fe3`
- name: `?BlbQueryVolumeSectorSize@@YAJPEAGPEAK@Z`
- size: `1503`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x14001218c`
- `0x140019fd0`
- `0x140045dec`
- `0x14005baf8`
- `0x14010fc5c`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14001358c`
- `0x140014200`
- `0x140014260`
- `0x14003c54c`
- `0x140088ba4`
- `0x14008ae5c`
- `0x14012365c`
- `0x140123a04`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140123b56`
- `KERNEL32!CreateFileW` at `0x140123dce`
- `KERNEL32!CreateFileW` at `0x140123b56`
- `KERNEL32!CreateFileW` at `0x140123dce`
- `KERNEL32!CloseHandle` at `0x140123d78`
- `KERNEL32!CloseHandle` at `0x140123f24`
- `KERNEL32!CloseHandle` at `0x140123f3a`
- `KERNEL32!CloseHandle` at `0x140123d78`
- `KERNEL32!CloseHandle` at `0x140123f24`
- `KERNEL32!CloseHandle` at `0x140123f3a`
- `KERNEL32!GetLastError` at `0x140123b65`
- `KERNEL32!GetLastError` at `0x140123c2e`
- `KERNEL32!GetLastError` at `0x140123ddc`
- `KERNEL32!GetLastError` at `0x140123e75`
- `KERNEL32!GetLastError` at `0x140123b65`
- `KERNEL32!GetLastError` at `0x140123c2e`
- `KERNEL32!GetLastError` at `0x140123ddc`
- `KERNEL32!GetLastError` at `0x140123e75`
- `KERNEL32!DeviceIoControl` at `0x140123c20`
- `KERNEL32!DeviceIoControl` at `0x140123e6b`
- `KERNEL32!DeviceIoControl` at `0x140123c20`
- `KERNEL32!DeviceIoControl` at `0x140123e6b`
- `ole32!CoTaskMemAlloc` at `0x140123bd4`
- `ole32!CoTaskMemAlloc` at `0x140123bd4`
- `ole32!CoTaskMemFree` at `0x140123c52`
- `ole32!CoTaskMemFree` at `0x140123f5a`
- `ole32!CoTaskMemFree` at `0x140123f6f`
- `ole32!CoTaskMemFree` at `0x140123f84`
- `ole32!CoTaskMemFree` at `0x140123c52`
- `ole32!CoTaskMemFree` at `0x140123f5a`
- `ole32!CoTaskMemFree` at `0x140123f6f`
- `ole32!CoTaskMemFree` at `0x140123f84`

## pseudocode

```c
__int64 __fastcall BlbQueryVolumeSectorSize(unsigned __int16 *a1, unsigned int *a2)
{
  int v4; // eax
  WCHAR *v5; // r14
  signed int v6; // ebx
  unsigned int *v7; // rdi
  int VolumeFileSystem; // eax
  PVOID *v9; // rcx
  int v10; // edx
  __int64 FileW; // r15
  signed int LastError; // eax
  unsigned __int8 v13; // al
  __int64 v14; // r13
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int *v17; // rax
  DWORD v18; // eax
  signed int v19; // eax
  void *v20; // rcx
  signed int v21; // eax
  char dwCreationDisposition; // [rsp+20h] [rbp-79h]
  unsigned __int8 IsFileSystemCSVFS; // [rsp+40h] [rbp-59h]
  size_t Size; // [rsp+44h] [rbp-55h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-41h] BYREF
  __int128 OutBuffer; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h]
  WCHAR FileName[8]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v31; // [rsp+88h] [rbp-11h]
  _OWORD v32[2]; // [rsp+98h] [rbp-1h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids);
  }
  lpFileName = 0;
  Size = 0;
  v32[0] = 0;
  pv = 0;
  *a2 = 0;
  *(_OWORD *)((char *)v32 + 12) = 0;
  v29 = 0;
  OutBuffer = 0;
  *(_OWORD *)FileName = 0;
  v31 = 0;
  v4 = BlbutilRemoveTrailingBackslash(a1, (unsigned __int16 **)&lpFileName);
  v5 = (WCHAR *)lpFileName;
  v6 = v4;
  if ( v4 < 0 )
    goto LABEL_78;
  v7 = 0;
  VolumeFileSystem = BlbQueryVolumeFileSystem((unsigned __int16 *)lpFileName, (unsigned __int16 **)&pv);
  v6 = VolumeFileSystem;
  if ( VolumeFileSystem < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v10 = 55;
    dwCreationDisposition = VolumeFileSystem;
LABEL_11:
    WPP_SF_Sd(
      (unsigned int)v9[2],
      v10,
      (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
      (_DWORD)v5,
      dwCreationDisposition);
LABEL_12:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_74;
  }
  IsFileSystemCSVFS = BlbutilIsFileSystemCSVFS((unsigned __int16 *)pv);
  FileW = (__int64)CreateFileW(v5, 0, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_74;
    }
    v10 = 56;
    dwCreationDisposition = v6;
    goto LABEL_11;
  }
  v13 = IsFileSystemCSVFS;
  v14 = -1;
  if ( !IsFileSystemCSVFS )
  {
    v15 = 32;
    v16 = 0;
    LODWORD(Size) = 32;
    while ( 1 )
    {
      v7 = 0;
      if ( v16 >= 2 )
        goto LABEL_39;
      v17 = (unsigned int *)CoTaskMemAlloc(v15);
      v7 = v17;
      if ( !v17 )
      {
        v6 = -2147024882;
        goto LABEL_70;
      }
      memset_0(v17, 0, (unsigned int)Size);
      if ( DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v7, Size, (LPDWORD)&Size, 0) )
        break;
      v18 = GetLastError();
      if ( v18 != 234 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
            (_DWORD)v5,
            v18);
        }
        v6 = 0;
        *a2 = 512;
        goto LABEL_70;
      }
      if ( v16 == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
            Size,
            (__int64)a1);
        }
LABEL_32:
        v6 = -2147418113;
        goto LABEL_70;
      }
      LODWORD(Size) = 24 * *v7 + 8;
      CoTaskMemFree(v7);
      v15 = Size;
      ++v16;
    }
    v15 = Size;
LABEL_39:
    if ( !((v15 - 8) / 0x18) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids, a1);
      }
      goto LABEL_32;
    }
    CloseHandle((HANDLE)FileW);
    v6 = StringCchPrintfW(FileName, 0x1Eu, L"\\\\.\\PhysicalDrive%d", v7[2]);
    if ( v6 >= 0 )
    {
      FileW = -1;
      v14 = (__int64)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
      if ( v14 != -1 )
      {
        v13 = 0;
        goto LABEL_54;
      }
      v19 = GetLastError();
      v6 = v19;
      if ( v19 > 0 )
        v6 = (unsigned __int16)v19 | 0x80070000;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
          (unsigned int)FileName,
          v6);
        goto LABEL_12;
      }
      goto LABEL_74;
    }
LABEL_73:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_74;
  }
LABEL_54:
  v20 = (void *)FileW;
  if ( !v13 )
    v20 = (void *)v14;
  if ( DeviceIoControl(v20, 0x70000u, 0, 0, &OutBuffer, 0x18u, (LPDWORD)&Size + 1, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
        (unsigned int)FileName,
        SBYTE4(v29));
    }
    *a2 = HIDWORD(v29);
    goto LABEL_68;
  }
  v21 = GetLastError();
  v6 = v21;
  if ( v21 > 0 )
    v6 = (unsigned __int16)v21 | 0x80070000;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
      (unsigned int)FileName,
      v6);
LABEL_68:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( FileW != -1 )
  {
LABEL_70:
    CloseHandle((HANDLE)FileW);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != -1 )
  {
    CloseHandle((HANDLE)v14);
    goto LABEL_73;
  }
LABEL_74:
  if ( pv )
  {
    CoTaskMemFree(pv);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    CoTaskMemFree(v7);
LABEL_78:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    CoTaskMemFree(v5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_(v9[2], 63, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140123a04  mov     [rsp-8+arg_10], rbx
0x140123a09  push    rbp
0x140123a0a  push    rsi
0x140123a0b  push    rdi
0x140123a0c  push    r12
0x140123a0e  push    r13
0x140123a10  push    r14
0x140123a12  push    r15
0x140123a14  lea     rbp, [rsp-27h]
0x140123a19  sub     rsp, 0C0h
0x140123a20  mov     rax, cs:__security_cookie
0x140123a27  xor     rax, rsp
0x140123a2a  mov     [rbp+57h+var_38], rax
0x140123a2e  mov     r12, rdx
0x140123a31  mov     rsi, rcx
0x140123a34  mov     rcx, cs:WPP_GLOBAL_Control
0x140123a3b  lea     r13, WPP_GLOBAL_Control
0x140123a42  cmp     rcx, r13
0x140123a45  jz      short loc_140123A6B
0x140123a47  test    dword ptr [rcx+1Ch], 200h
0x140123a4e  jz      short loc_140123A6B
0x140123a50  cmp     byte ptr [rcx+19h], 5
0x140123a54  jb      short loc_140123A6B
0x140123a56  mov     rcx, [rcx+10h]
0x140123a5a  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123a61  mov     edx, 36h ; '6'
0x140123a66  call    WPP_SF_
0x140123a6b  xorps   xmm1, xmm1
0x140123a6e  mov     [rbp+57h+lpFileName], 0
0x140123a76  xorps   xmm0, xmm0
0x140123a79  mov     dword ptr [rbp+57h+Size], 0
0x140123a80  xor     eax, eax
0x140123a82  mov     dword ptr [rbp+57h+Size+4], 0
0x140123a89  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x140123a8d  lea     rdx, [rbp+57h+lpFileName]; unsigned __int16 **
0x140123a91  mov     [rbp+57h+pv], 0
0x140123a99  mov     rcx, rsi; unsigned __int16 *
0x140123a9c  mov     dword ptr [r12], 0
0x140123aa4  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm1
0x140123aa8  mov     [rbp+57h+var_80], rax
0x140123aac  movups  [rbp+57h+OutBuffer], xmm0
0x140123ab0  movups  xmmword ptr [rbp+57h+FileName], xmm1
0x140123ab4  movups  [rbp+57h+var_68], xmm1
0x140123ab8  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x140123abd  mov     r14, [rbp+57h+lpFileName]
0x140123ac1  mov     ebx, eax
0x140123ac3  test    eax, eax
0x140123ac5  js      loc_140123F75
0x140123acb  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x140123acf  mov     rcx, r14; unsigned __int16 *
0x140123ad2  xor     edi, edi
0x140123ad4  call    ?BlbQueryVolumeFileSystem@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeFileSystem(ushort *,ushort * *)
0x140123ad9  mov     ebx, eax
0x140123adb  test    eax, eax
0x140123add  jns     short loc_140123B29
0x140123adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140123ae6  cmp     rcx, r13
0x140123ae9  jz      loc_140123F4E
0x140123aef  test    byte ptr [rcx+1Ch], 1
0x140123af3  jz      loc_140123F4E
0x140123af9  cmp     byte ptr [rcx+19h], 2
0x140123afd  jb      loc_140123F4E
0x140123b03  lea     edx, [rdi+37h]
0x140123b06  mov     [rsp+0F0h+dwCreationDisposition], eax
0x140123b0a  mov     r9, r14
0x140123b0d  mov     rcx, [rcx+10h]
0x140123b11  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123b18  call    WPP_SF_Sd
0x140123b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140123b24  jmp     loc_140123F4E
0x140123b29  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x140123b2d  call    ?BlbutilIsFileSystemCSVFS@@YAEPEAG@Z; BlbutilIsFileSystemCSVFS(ushort *)
0x140123b32  mov     [rbp+57h+var_B0], al
0x140123b35  xor     r9d, r9d; lpSecurityAttributes
0x140123b38  mov     eax, 3
0x140123b3d  mov     [rsp+0F0h+hTemplateFile], rdi; hTemplateFile
0x140123b42  mov     r8d, eax; dwShareMode
0x140123b45  mov     [rsp+0F0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140123b4d  xor     edx, edx; dwDesiredAccess
0x140123b4f  mov     [rsp+0F0h+dwCreationDisposition], eax; dwCreationDisposition
0x140123b53  mov     rcx, r14; lpFileName
0x140123b56  call    cs:__imp_CreateFileW
0x140123b5c  mov     r15, rax
0x140123b5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140123b63  jnz     short loc_140123BAF
0x140123b65  call    cs:__imp_GetLastError
0x140123b6b  mov     ebx, eax
0x140123b6d  test    eax, eax
0x140123b6f  jle     short loc_140123B7A
0x140123b71  movzx   ebx, ax
0x140123b74  or      ebx, 80070000h
0x140123b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140123b81  cmp     rcx, r13
0x140123b84  jz      loc_140123F4E
0x140123b8a  test    dword ptr [rcx+1Ch], 200h
0x140123b91  jz      loc_140123F4E
0x140123b97  cmp     byte ptr [rcx+19h], 3
0x140123b9b  jb      loc_140123F4E
0x140123ba1  mov     edx, 38h ; '8'
0x140123ba6  mov     [rsp+0F0h+dwCreationDisposition], ebx
0x140123baa  jmp     loc_140123B0A
0x140123baf  mov     al, [rbp+57h+var_B0]
0x140123bb2  or      r13, 0FFFFFFFFFFFFFFFFh
0x140123bb6  test    al, al
0x140123bb8  jnz     loc_140123E34
0x140123bbe  lea     eax, [r13+21h]
0x140123bc2  xor     ebx, ebx
0x140123bc4  mov     dword ptr [rbp+57h+Size], eax
0x140123bc7  xor     edi, edi
0x140123bc9  cmp     ebx, 2
0x140123bcc  jnb     loc_140123D05
0x140123bd2  mov     ecx, eax; cb
0x140123bd4  call    cs:__imp_CoTaskMemAlloc
0x140123bda  mov     rdi, rax
0x140123bdd  test    rax, rax
0x140123be0  jz      loc_140123D6B
0x140123be6  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x140123bea  xor     edx, edx; Val
0x140123bec  mov     rcx, rax; void *
0x140123bef  call    memset_0
0x140123bf4  lea     rax, [rbp+57h+Size]
0x140123bf8  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x140123c01  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x140123c06  xor     r9d, r9d; nInBufferSize
0x140123c09  mov     eax, dword ptr [rbp+57h+Size]
0x140123c0c  xor     r8d, r8d; lpInBuffer
0x140123c0f  mov     [rsp+0F0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x140123c13  mov     edx, 560000h; dwIoControlCode
0x140123c18  mov     rcx, r15; hDevice
0x140123c1b  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rdi; lpOutBuffer
0x140123c20  call    cs:__imp_DeviceIoControl
0x140123c26  test    eax, eax
0x140123c28  jnz     loc_140123D02
0x140123c2e  call    cs:__imp_GetLastError
0x140123c34  cmp     eax, 0EAh
0x140123c39  jnz     short loc_140123CA9
0x140123c3b  cmp     ebx, 1
0x140123c3e  jz      short loc_140123C62
0x140123c40  mov     eax, [rdi]
0x140123c42  lea     ecx, [rax+rax*2]
0x140123c45  lea     ecx, ds:8[rcx*8]
0x140123c4c  mov     dword ptr [rbp+57h+Size], ecx
0x140123c4f  mov     rcx, rdi; pv
0x140123c52  call    cs:__imp_CoTaskMemFree
0x140123c58  mov     eax, dword ptr [rbp+57h+Size]
0x140123c5b  inc     ebx
0x140123c5d  jmp     loc_140123BC7
0x140123c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140123c69  lea     rdx, WPP_GLOBAL_Control
0x140123c70  cmp     rcx, rdx
0x140123c73  jz      short loc_140123C9F
0x140123c75  test    byte ptr [rcx+1Ch], 1
0x140123c79  jz      short loc_140123C9F
0x140123c7b  cmp     byte ptr [rcx+19h], 2
0x140123c7f  jb      short loc_140123C9F
0x140123c81  mov     r9d, dword ptr [rbp+57h+Size]
0x140123c85  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123c8c  mov     rcx, [rcx+10h]
0x140123c90  mov     edx, 3Ah ; ':'
0x140123c95  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi
0x140123c9a  call    WPP_SF_dS
0x140123c9f  mov     ebx, 8000FFFFh
0x140123ca4  jmp     loc_140123F21
0x140123ca9  test    eax, eax
0x140123cab  jle     short loc_140123CB5
0x140123cad  movzx   eax, ax
0x140123cb0  or      eax, 80070000h
0x140123cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140123cbc  lea     rdx, WPP_GLOBAL_Control
0x140123cc3  cmp     rcx, rdx
0x140123cc6  jz      short loc_140123CF3
0x140123cc8  test    dword ptr [rcx+1Ch], 200h
0x140123ccf  jz      short loc_140123CF3
0x140123cd1  cmp     byte ptr [rcx+19h], 3
0x140123cd5  jb      short loc_140123CF3
0x140123cd7  mov     rcx, [rcx+10h]
0x140123cdb  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123ce2  mov     edx, 39h ; '9'
0x140123ce7  mov     [rsp+0F0h+dwCreationDisposition], eax
0x140123ceb  mov     r9, r14
0x140123cee  call    WPP_SF_Sd
0x140123cf3  xor     ebx, ebx
0x140123cf5  mov     dword ptr [r12], 200h
0x140123cfd  jmp     loc_140123F21
0x140123d02  mov     eax, dword ptr [rbp+57h+Size]
0x140123d05  add     eax, 0FFFFFFF8h
0x140123d08  mov     ecx, eax
0x140123d0a  mov     rax, 0AAAAAAAAAAAAAAABh
0x140123d14  mul     rcx
0x140123d17  shr     rdx, 4
0x140123d1b  cmp     edx, 1
0x140123d1e  jnb     short loc_140123D75
0x140123d20  mov     rcx, cs:WPP_GLOBAL_Control
0x140123d27  lea     rdx, WPP_GLOBAL_Control
0x140123d2e  cmp     rcx, rdx
0x140123d31  jz      loc_140123C9F
0x140123d37  test    dword ptr [rcx+1Ch], 200h
0x140123d3e  jz      loc_140123C9F
0x140123d44  cmp     byte ptr [rcx+19h], 3
0x140123d48  jb      loc_140123C9F
0x140123d4e  mov     rcx, [rcx+10h]
0x140123d52  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123d59  mov     edx, 3Bh ; ';'
0x140123d5e  mov     r9, rsi
0x140123d61  call    WPP_SF_S
0x140123d66  jmp     loc_140123C9F
0x140123d6b  mov     ebx, 8007000Eh
0x140123d70  jmp     loc_140123F21
0x140123d75  mov     rcx, r15; hObject
0x140123d78  call    cs:__imp_CloseHandle
0x140123d7e  mov     r9d, [rdi+8]
0x140123d82  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x140123d89  mov     edx, 1Eh; unsigned __int64
0x140123d8e  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x140123d92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140123d97  mov     ebx, eax
0x140123d99  test    eax, eax
0x140123d9b  js      loc_140123F40
0x140123da1  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x140123daa  lea     rcx, [rbp+57h+FileName]; lpFileName
0x140123dae  or      r15, 0FFFFFFFFFFFFFFFFh
0x140123db2  mov     [rsp+0F0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140123dba  xor     r9d, r9d; lpSecurityAttributes
0x140123dbd  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x140123dc5  mov     edx, 80000000h; dwDesiredAccess
0x140123dca  lea     r8d, [r15+4]; dwShareMode
0x140123dce  call    cs:__imp_CreateFileW
0x140123dd4  mov     r13, rax
0x140123dd7  cmp     rax, r15
0x140123dda  jnz     short loc_140123E31
0x140123ddc  call    cs:__imp_GetLastError
0x140123de2  mov     ebx, eax
0x140123de4  test    eax, eax
0x140123de6  jle     short loc_140123DF1
0x140123de8  movzx   ebx, ax
0x140123deb  or      ebx, 80070000h
0x140123df1  mov     rcx, cs:WPP_GLOBAL_Control
0x140123df8  lea     r13, WPP_GLOBAL_Control
0x140123dff  cmp     rcx, r13
0x140123e02  jz      loc_140123F4E
0x140123e08  test    dword ptr [rcx+1Ch], 200h
0x140123e0f  jz      loc_140123F4E
0x140123e15  cmp     byte ptr [rcx+19h], 3
0x140123e19  jb      loc_140123F4E
0x140123e1f  mov     edx, 3Ch ; '<'
0x140123e24  mov     [rsp+0F0h+dwCreationDisposition], ebx
0x140123e28  lea     r9, [rbp+57h+FileName]
0x140123e2c  jmp     loc_140123B0D
0x140123e31  mov     al, [rbp+57h+var_B0]
0x140123e34  test    al, al
0x140123e36  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x140123e3f  lea     rax, [rbp+57h+Size+4]
0x140123e43  mov     rcx, r15
0x140123e46  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x140123e4b  cmovz   rcx, r13; hDevice
0x140123e4f  lea     rax, [rbp+57h+OutBuffer]
0x140123e53  mov     [rsp+0F0h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x140123e5b  xor     r9d, r9d; nInBufferSize
0x140123e5e  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; lpOutBuffer
0x140123e63  xor     r8d, r8d; lpInBuffer
0x140123e66  mov     edx, 70000h; dwIoControlCode
0x140123e6b  call    cs:__imp_DeviceIoControl
0x140123e71  test    eax, eax
0x140123e73  jnz     short loc_140123ECB
0x140123e75  call    cs:__imp_GetLastError
0x140123e7b  mov     ebx, eax
0x140123e7d  test    eax, eax
0x140123e7f  jle     short loc_140123E8A
0x140123e81  movzx   ebx, ax
0x140123e84  or      ebx, 80070000h
0x140123e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140123e91  lea     rdx, WPP_GLOBAL_Control
0x140123e98  cmp     rcx, rdx
0x140123e9b  jz      short loc_140123F1B
0x140123e9d  test    dword ptr [rcx+1Ch], 200h
0x140123ea4  jz      short loc_140123F1B
0x140123ea6  cmp     byte ptr [rcx+19h], 3
0x140123eaa  jb      short loc_140123F1B
0x140123eac  mov     rcx, [rcx+10h]
0x140123eb0  lea     r9, [rbp+57h+FileName]
0x140123eb4  mov     edx, 3Dh ; '='
0x140123eb9  mov     [rsp+0F0h+dwCreationDisposition], ebx
0x140123ebd  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123ec4  call    WPP_SF_Sd
0x140123ec9  jmp     short loc_140123F14
0x140123ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x140123ed2  lea     rdx, WPP_GLOBAL_Control
0x140123ed9  cmp     rcx, rdx
0x140123edc  jz      short loc_140123F0D
0x140123ede  test    dword ptr [rcx+1Ch], 200h
0x140123ee5  jz      short loc_140123F0D
0x140123ee7  cmp     byte ptr [rcx+19h], 4
0x140123eeb  jb      short loc_140123F0D
0x140123eed  mov     eax, dword ptr [rbp+57h+var_80+4]
0x140123ef0  lea     r9, [rbp+57h+FileName]
0x140123ef4  mov     rcx, [rcx+10h]
0x140123ef8  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140123eff  mov     edx, 3Eh ; '>'
0x140123f04  mov     [rsp+0F0h+dwCreationDisposition], eax
0x140123f08  call    WPP_SF_Sd
  ... truncated ...
```
