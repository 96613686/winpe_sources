# RdVhd::Util::CVhdHelper::AttachVhd(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,void * *,ulong *,CPathString *)

- ea: `0x180048b68`
- end: `0x180049086`
- name: `?AttachVhd@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@PEAPEAXPEAKPEAVCPathString@@@Z`
- size: `1310`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004a578`
- `0x18004a7a4`
- `0x180054158`

## callees

- `0x180004db0`
- `0x180018cac`
- `0x180019b38`
- `0x18001a280`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x1800488e4`
- `0x180048b28`
- `0x180048b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004903f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004904e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004903f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004904e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048f4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048f4e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048fdc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048fdc`
- `VirtDisk!AttachVirtualDisk` at `0x180048d8a`
- `VirtDisk!AttachVirtualDisk` at `0x180048dc4`
- `VirtDisk!AttachVirtualDisk` at `0x180048d8a`
- `VirtDisk!AttachVirtualDisk` at `0x180048dc4`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180048e8a`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180048e8a`

## string_xrefs

- `0x180048c18`: `szVhdFilePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::AttachVhd(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 *a4,
        _DWORD *a5,
        __int64 a6)
{
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  signed int v11; // ebx
  __int64 FileW; // r13
  __int64 v13; // rsi
  ATTACH_VIRTUAL_DISK_FLAG v14; // r8d
  DWORD v15; // eax
  ATTACH_VIRTUAL_DISK_FLAG v16; // r8d
  bool v17; // sf
  RdVhd::Uvhd::CUvhdDiskManager *v18; // rcx
  __int64 v19; // rdx
  WCHAR *Buffer; // rax
  signed int VirtualDiskPhysicalPath; // eax
  const WCHAR *v22; // rax
  signed int LastError; // eax
  signed int v24; // eax
  int v25; // eax
  ULONG DiskPathSizeInBytes; // [rsp+40h] [rbp-59h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+48h] [rbp-51h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-49h] BYREF
  void **v30; // [rsp+58h] [rbp-41h] BYREF
  int v31; // [rsp+60h] [rbp-39h]
  __int64 v32; // [rsp+64h] [rbp-35h]
  int v33; // [rsp+6Ch] [rbp-2Dh]
  __int64 v34; // [rsp+70h] [rbp-29h]
  int v35; // [rsp+78h] [rbp-21h]
  struct _ATTACH_VIRTUAL_DISK_PARAMETERS Parameters[2]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v37; // [rsp+90h] [rbp-9h]
  __int64 OutBuffer; // [rsp+98h] [rbp-1h] BYREF
  int v39; // [rsp+A0h] [rbp+7h]

  v30 = &CPathString::`vftable';
  v32 = 128;
  VirtualDiskHandle = (HANDLE)-1LL;
  v34 = 0;
  v33 = 0;
  *(_OWORD *)&Parameters[0].Version = 0;
  Parameters[0].Version = ATTACH_VIRTUAL_DISK_VERSION_1;
  v35 = 0x8000000;
  v31 = 0;
  DiskPathSizeInBytes = 0;
  OutBuffer = 0;
  v39 = 0;
  BytesReturned = 0;
  v37 = 0;
  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 61;
    v10 = L"szVhdFilePath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v10);
LABEL_7:
    v11 = -2147024809;
    goto LABEL_83;
  }
  if ( !a4 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 62;
    v10 = L"phVhd";
    goto LABEL_6;
  }
  if ( !a5 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 63;
    v10 = L"pVhdDeviceNumber";
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, 2147942487LL);
    }
    goto LABEL_83;
  }
  *a4 = -1;
  FileW = -1;
  *a5 = 0;
  v11 = RdVhd::Util::CVhdHelper::OpenVhd(0, a2, 1, &VirtualDiskHandle, a6);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
        (unsigned int)v11);
    }
    v13 = (__int64)VirtualDiskHandle;
    goto LABEL_79;
  }
  v13 = (__int64)VirtualDiskHandle;
  v14 = ATTACH_VIRTUAL_DISK_FLAG_NO_SECURITY_DESCRIPTOR|ATTACH_VIRTUAL_DISK_FLAG_PERMANENT_LIFETIME|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER;
  if ( a3 != 2 )
    v14 = ATTACH_VIRTUAL_DISK_FLAG_NO_SECURITY_DESCRIPTOR|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER;
  v15 = AttachVirtualDisk(VirtualDiskHandle, 0, v14, 0, Parameters, 0);
  v11 = v15;
  if ( !v15 )
    goto LABEL_44;
  if ( v15 == 87 )
  {
    v16 = ATTACH_VIRTUAL_DISK_FLAG_PERMANENT_LIFETIME|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER;
    if ( a3 != 2 )
      v16 = ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER;
    v11 = AttachVirtualDisk((HANDLE)v13, 0, v16, 0, Parameters, 0);
  }
  v17 = v11 < 0;
  if ( v11 > 0 )
  {
    v11 = (unsigned __int16)v11 | 0x80070000;
    v17 = v11 < 0;
  }
  if ( v17 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_79;
    }
    v19 = 66;
  }
  else
  {
LABEL_44:
    v11 = CBaseStringT<unsigned short>::EnsureSpace(&v30, 260);
    if ( v11 >= 0 )
    {
      DiskPathSizeInBytes = CBaseStringT<unsigned short>::GetBufferLength(&v30);
      Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v30);
      VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath((HANDLE)v13, &DiskPathSizeInBytes, Buffer);
      v11 = VirtualDiskPhysicalPath;
      if ( !VirtualDiskPhysicalPath )
        goto LABEL_57;
      if ( VirtualDiskPhysicalPath > 0 )
        v11 = (unsigned __int16)VirtualDiskPhysicalPath | 0x80070000;
      if ( v11 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_79;
        }
        v19 = 68;
      }
      else
      {
LABEL_57:
        v11 = CBaseStringT<unsigned short>::SetLength(&v30, DiskPathSizeInBytes);
        if ( v11 >= 0 )
        {
          v22 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v30);
          FileW = (__int64)CreateFileW(v22, 0, 3u, 0, 3u, 0, 0);
          if ( FileW != -1 )
            goto LABEL_73;
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          if ( v11 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_79;
            }
            v19 = 70;
          }
          else
          {
LABEL_73:
            if ( DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
              goto LABEL_78;
            v24 = GetLastError();
            v11 = v24;
            if ( v24 > 0 )
              v11 = (unsigned __int16)v24 | 0x80070000;
            if ( v11 >= 0 )
            {
LABEL_78:
              v25 = HIDWORD(OutBuffer);
              *a4 = v13;
              v13 = -1;
              *a5 = v25;
              goto LABEL_79;
            }
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_79;
            }
            v19 = 71;
          }
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_79;
          }
          v19 = 69;
        }
      }
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_79;
      }
      v19 = 67;
    }
  }
  WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, (unsigned int)v11);
LABEL_79:
  if ( v13 != -1 )
    CloseHandle((HANDLE)v13);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
LABEL_83:
  CPathString::~CPathString((CPathString *)&v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180048b68  mov     [rsp-8+arg_0], rbx
0x180048b6d  push    rbp
0x180048b6e  push    rsi
0x180048b6f  push    rdi
0x180048b70  push    r12
0x180048b72  push    r13
0x180048b74  push    r14
0x180048b76  push    r15
0x180048b78  lea     rbp, [rsp-17h]
0x180048b7d  sub     rsp, 0B0h
0x180048b84  mov     rax, cs:__security_cookie
0x180048b8b  xor     rax, rsp
0x180048b8e  mov     [rbp+47h+var_38], rax
0x180048b92  mov     r12, [rbp+47h+arg_20]
0x180048b96  lea     rcx, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180048b9d  mov     rax, [rbp+47h+arg_28]
0x180048ba1  xor     esi, esi
0x180048ba3  mov     r14d, r8d
0x180048ba6  mov     [rbp+47h+var_88], rcx
0x180048baa  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048bae  mov     [rbp+47h+var_7C], 80h
0x180048bb6  xor     ecx, ecx
0x180048bb8  mov     [rbp+47h+VirtualDiskHandle], r8
0x180048bbc  xorps   xmm0, xmm0
0x180048bbf  mov     [rbp+47h+var_70], rsi
0x180048bc3  lea     edi, [rsi+1]
0x180048bc6  mov     [rbp+47h+var_74], esi
0x180048bc9  movups  xmmword ptr [rbp+47h+var_60.Version], xmm0
0x180048bcd  mov     [rbp+47h+var_60.Version], edi
0x180048bd0  mov     r15, r9
0x180048bd3  mov     [rbp+47h+var_68], 8000000h
0x180048bda  mov     [rbp+47h+var_80], esi
0x180048bdd  mov     [rbp+47h+DiskPathSizeInBytes], esi
0x180048be0  mov     [rbp+47h+OutBuffer], rcx
0x180048be4  mov     [rbp+47h+var_40], ecx
0x180048be7  mov     [rbp+47h+BytesReturned], esi
0x180048bea  mov     [rbp+47h+var_50], rcx
0x180048bee  test    rdx, rdx
0x180048bf1  jnz     short loc_180048C39
0x180048bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bfa  lea     rax, WPP_GLOBAL_Control
0x180048c01  cmp     rcx, rax
0x180048c04  jz      short loc_180048C2F
0x180048c06  test    [rcx+1Ch], dil
0x180048c0a  jz      short loc_180048C2F
0x180048c0c  lea     edi, [rsi+2]
0x180048c0f  cmp     [rcx+19h], dil
0x180048c13  jb      short loc_180048C2F
0x180048c15  lea     edx, [rsi+3Dh]
0x180048c18  lea     r9, aSzvhdfilepath; "szVhdFilePath"
0x180048c1f  mov     rcx, [rcx+10h]
0x180048c23  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180048c2a  call    WPP_SF_S
0x180048c2f  mov     ebx, 80070057h
0x180048c34  jmp     loc_180049054
0x180048c39  test    r15, r15
0x180048c3c  jnz     short loc_180048C6D
0x180048c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c45  lea     rax, WPP_GLOBAL_Control
0x180048c4c  cmp     rcx, rax
0x180048c4f  jz      short loc_180048C2F
0x180048c51  test    [rcx+1Ch], dil
0x180048c55  jz      short loc_180048C2F
0x180048c57  lea     edi, [r15+2]
0x180048c5b  cmp     [rcx+19h], dil
0x180048c5f  jb      short loc_180048C2F
0x180048c61  lea     edx, [rdi+3Ch]
0x180048c64  lea     r9, aPhvhd; "phVhd"
0x180048c6b  jmp     short loc_180048C1F
0x180048c6d  test    r12, r12
0x180048c70  jnz     short loc_180048CA5
0x180048c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c79  lea     rax, WPP_GLOBAL_Control
0x180048c80  cmp     rcx, rax
0x180048c83  jz      short loc_180048C2F
0x180048c85  test    [rcx+1Ch], dil
0x180048c89  jz      short loc_180048C2F
0x180048c8b  lea     edi, [r12+2]
0x180048c90  cmp     [rcx+19h], dil
0x180048c94  jb      short loc_180048C2F
0x180048c96  lea     edx, [rdi+3Dh]
0x180048c99  lea     r9, aPvhddevicenumb; "pVhdDeviceNumber"
0x180048ca0  jmp     loc_180048C1F
0x180048ca5  test    r14d, r14d
0x180048ca8  jnz     short loc_180048CF9
0x180048caa  mov     ebx, 80070057h
0x180048caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180048cb6  lea     rax, WPP_GLOBAL_Control
0x180048cbd  cmp     rcx, rax
0x180048cc0  jz      loc_180049054
0x180048cc6  test    [rcx+1Ch], dil
0x180048cca  jz      loc_180049054
0x180048cd0  lea     edi, [r14+2]
0x180048cd4  cmp     [rcx+19h], dil
0x180048cd8  jb      loc_180049054
0x180048cde  mov     rcx, [rcx+10h]
0x180048ce2  lea     edx, [rdi+3Eh]
0x180048ce5  mov     r9d, ebx
0x180048ce8  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180048cef  call    WPP_SF_d
0x180048cf4  jmp     loc_180049054
0x180048cf9  mov     [r9], r8
0x180048cfc  mov     r13, r8
0x180048cff  lea     r9, [rbp+47h+VirtualDiskHandle]
0x180048d03  mov     [r12], esi
0x180048d07  mov     r8d, edi
0x180048d0a  mov     [rsp+0E0h+Parameters], rax
0x180048d0f  call    ?OpenVhd@CVhdHelper@Util@RdVhd@@IEBAJPEBGW4Mask@VhdAccessMask@123@PEAPEAXPEAVCPathString@@@Z; RdVhd::Util::CVhdHelper::OpenVhd(ushort const *,RdVhd::Util::CVhdHelper::VhdAccessMask::Mask,void * *,CPathString *)
0x180048d14  mov     ebx, eax
0x180048d16  test    eax, eax
0x180048d18  jns     short loc_180048D5D
0x180048d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d21  lea     rax, WPP_GLOBAL_Control
0x180048d28  cmp     rcx, rax
0x180048d2b  jz      short loc_180048D54
0x180048d2d  test    [rcx+1Ch], dil
0x180048d31  jz      short loc_180048D54
0x180048d33  mov     edi, 2
0x180048d38  cmp     [rcx+19h], dil
0x180048d3c  jb      short loc_180048D54
0x180048d3e  mov     rcx, [rcx+10h]
0x180048d42  lea     edx, [rdi+3Fh]
0x180048d45  mov     r9d, ebx
0x180048d48  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180048d4f  call    WPP_SF_d
0x180048d54  mov     rsi, [rbp+47h+VirtualDiskHandle]
0x180048d58  jmp     loc_180049036
0x180048d5d  mov     eax, 12h
0x180048d62  mov     [rsp+0E0h+Overlapped], rsi; Overlapped
0x180048d67  mov     rsi, [rbp+47h+VirtualDiskHandle]
0x180048d6b  mov     rcx, rsi; VirtualDiskHandle
0x180048d6e  lea     edi, [rax-10h]
0x180048d71  lea     r8d, [rax+4]
0x180048d75  cmp     r14d, edi
0x180048d78  cmovnz  r8d, eax; Flags
0x180048d7c  lea     rax, [rbp+47h+var_60]
0x180048d80  xor     r9d, r9d; ProviderSpecificFlags
0x180048d83  mov     [rsp+0E0h+Parameters], rax; Parameters
0x180048d88  xor     edx, edx; SecurityDescriptor
0x180048d8a  call    cs:__imp_AttachVirtualDisk
0x180048d90  mov     ebx, eax
0x180048d92  test    eax, eax
0x180048d94  jz      loc_180048E25
0x180048d9a  cmp     eax, 57h ; 'W'
0x180048d9d  jnz     short loc_180048DCC
0x180048d9f  cmp     r14d, edi
0x180048da2  mov     [rsp+0E0h+Overlapped], 0; Overlapped
0x180048dab  lea     r8d, [rdi+4]
0x180048daf  mov     rcx, rsi; VirtualDiskHandle
0x180048db2  cmovnz  r8d, edi; Flags
0x180048db6  lea     rax, [rbp+47h+var_60]
0x180048dba  xor     r9d, r9d; ProviderSpecificFlags
0x180048dbd  mov     [rsp+0E0h+Parameters], rax; Parameters
0x180048dc2  xor     edx, edx; SecurityDescriptor
0x180048dc4  call    cs:__imp_AttachVirtualDisk
0x180048dca  mov     ebx, eax
0x180048dcc  test    ebx, ebx
0x180048dce  jle     short loc_180048DDB
0x180048dd0  movzx   ebx, bx
0x180048dd3  or      ebx, 80070000h
0x180048dd9  test    ebx, ebx
0x180048ddb  jns     short loc_180048E25
0x180048ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180048de4  lea     rax, WPP_GLOBAL_Control
0x180048deb  cmp     rcx, rax
0x180048dee  jz      loc_180049036
0x180048df4  test    byte ptr [rcx+1Ch], 1
0x180048df8  jz      loc_180049036
0x180048dfe  cmp     [rcx+19h], dil
0x180048e02  jb      loc_180049036
0x180048e08  mov     edx, 42h ; 'B'
0x180048e0d  mov     rcx, [rcx+10h]
0x180048e11  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x180048e18  mov     r9d, ebx
0x180048e1b  call    WPP_SF_d
0x180048e20  jmp     loc_180049036
0x180048e25  mov     edx, 104h
0x180048e2a  lea     rcx, [rbp+47h+var_88]
0x180048e2e  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180048e33  mov     ebx, eax
0x180048e35  test    eax, eax
0x180048e37  jns     short loc_180048E6B
0x180048e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e40  lea     rax, WPP_GLOBAL_Control
0x180048e47  cmp     rcx, rax
0x180048e4a  jz      loc_180049036
0x180048e50  test    byte ptr [rcx+1Ch], 1
0x180048e54  jz      loc_180049036
0x180048e5a  cmp     [rcx+19h], dil
0x180048e5e  jb      loc_180049036
0x180048e64  mov     edx, 43h ; 'C'
0x180048e69  jmp     short loc_180048E0D
0x180048e6b  lea     rcx, [rbp+47h+var_88]
0x180048e6f  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180048e74  lea     rcx, [rbp+47h+var_88]
0x180048e78  mov     [rbp+47h+DiskPathSizeInBytes], eax
0x180048e7b  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180048e80  mov     r8, rax; DiskPath
0x180048e83  lea     rdx, [rbp+47h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180048e87  mov     rcx, rsi; VirtualDiskHandle
0x180048e8a  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180048e90  mov     ebx, eax
0x180048e92  test    eax, eax
0x180048e94  jz      short loc_180048EDA
0x180048e96  jle     short loc_180048EA1
0x180048e98  movzx   ebx, ax
0x180048e9b  or      ebx, 80070000h
0x180048ea1  test    ebx, ebx
0x180048ea3  jns     short loc_180048EDA
0x180048ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180048eac  lea     rax, WPP_GLOBAL_Control
0x180048eb3  cmp     rcx, rax
0x180048eb6  jz      loc_180049036
0x180048ebc  test    byte ptr [rcx+1Ch], 1
0x180048ec0  jz      loc_180049036
0x180048ec6  cmp     [rcx+19h], dil
0x180048eca  jb      loc_180049036
0x180048ed0  mov     edx, 44h ; 'D'
0x180048ed5  jmp     loc_180048E0D
0x180048eda  mov     edx, [rbp+47h+DiskPathSizeInBytes]
0x180048edd  lea     rcx, [rbp+47h+var_88]
0x180048ee1  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x180048ee6  mov     ebx, eax
0x180048ee8  test    eax, eax
0x180048eea  jns     short loc_180048F21
0x180048eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ef3  lea     rax, WPP_GLOBAL_Control
0x180048efa  cmp     rcx, rax
0x180048efd  jz      loc_180049036
0x180048f03  test    byte ptr [rcx+1Ch], 1
0x180048f07  jz      loc_180049036
0x180048f0d  cmp     [rcx+19h], dil
0x180048f11  jb      loc_180049036
0x180048f17  mov     edx, 45h ; 'E'
0x180048f1c  jmp     loc_180048E0D
0x180048f21  lea     rcx, [rbp+47h+var_88]
0x180048f25  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180048f2a  mov     r8d, 3; dwShareMode
0x180048f30  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180048f39  mov     rcx, rax; lpFileName
0x180048f3c  mov     dword ptr [rsp+0E0h+Overlapped], 0; dwFlagsAndAttributes
0x180048f44  xor     r9d, r9d; lpSecurityAttributes
0x180048f47  mov     dword ptr [rsp+0E0h+Parameters], r8d; dwCreationDisposition
0x180048f4c  xor     edx, edx; dwDesiredAccess
0x180048f4e  call    cs:__imp_CreateFileW
0x180048f54  mov     r13, rax
0x180048f57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180048f5b  jnz     short loc_180048FAB
0x180048f5d  call    cs:__imp_GetLastError
0x180048f63  mov     ebx, eax
0x180048f65  test    eax, eax
0x180048f67  jle     short loc_180048F72
0x180048f69  movzx   ebx, ax
0x180048f6c  or      ebx, 80070000h
0x180048f72  test    ebx, ebx
0x180048f74  jns     short loc_180048FAB
0x180048f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f7d  lea     rax, WPP_GLOBAL_Control
0x180048f84  cmp     rcx, rax
0x180048f87  jz      loc_180049036
0x180048f8d  test    byte ptr [rcx+1Ch], 1
0x180048f91  jz      loc_180049036
0x180048f97  cmp     [rcx+19h], dil
0x180048f9b  jb      loc_180049036
0x180048fa1  mov     edx, 46h ; 'F'
0x180048fa6  jmp     loc_180048E0D
0x180048fab  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x180048fb4  lea     rax, [rbp+47h+BytesReturned]
0x180048fb8  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x180048fbd  xor     r9d, r9d; nInBufferSize
0x180048fc0  lea     rax, [rbp+47h+OutBuffer]
0x180048fc4  mov     dword ptr [rsp+0E0h+Overlapped], 0Ch; nOutBufferSize
0x180048fcc  xor     r8d, r8d; lpInBuffer
0x180048fcf  mov     [rsp+0E0h+Parameters], rax; lpOutBuffer
0x180048fd4  mov     edx, 2D1080h; dwIoControlCode
0x180048fd9  mov     rcx, r13; hDevice
0x180048fdc  call    cs:__imp_DeviceIoControl
0x180048fe2  test    eax, eax
0x180048fe4  jnz     short loc_180049028
0x180048fe6  call    cs:__imp_GetLastError
0x180048fec  mov     ebx, eax
0x180048fee  test    eax, eax
0x180048ff0  jle     short loc_180048FFB
0x180048ff2  movzx   ebx, ax
0x180048ff5  or      ebx, 80070000h
0x180048ffb  test    ebx, ebx
0x180048ffd  jns     short loc_180049028
0x180048fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180049006  lea     rax, WPP_GLOBAL_Control
0x18004900d  cmp     rcx, rax
0x180049010  jz      short loc_180049036
0x180049012  test    byte ptr [rcx+1Ch], 1
0x180049016  jz      short loc_180049036
0x180049018  cmp     [rcx+19h], dil
0x18004901c  jb      short loc_180049036
0x18004901e  mov     edx, 47h ; 'G'
0x180049023  jmp     loc_180048E0D
0x180049028  mov     eax, dword ptr [rbp+47h+OutBuffer+4]
0x18004902b  mov     [r15], rsi
0x18004902e  or      rsi, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
