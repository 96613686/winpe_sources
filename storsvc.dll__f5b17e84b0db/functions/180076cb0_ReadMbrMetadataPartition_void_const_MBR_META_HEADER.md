# ReadMbrMetadataPartition(void * const,MBR_META_HEADER * *)

- ea: `0x180076cb0`
- end: `0x180076f18`
- name: `?ReadMbrMetadataPartition@@YAJQEAXPEAPEAUMBR_META_HEADER@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(HANDLE hFile, struct MBR_META_HEADER **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180076bcc`

## callees

- `0x18000d030`
- `0x18000d400`
- `0x18007318c`
- `0x18007342c`
- `0x180074bd4`
- `0x180074cd4`
- `0x180074d94`
- `0x180076cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e45`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180076e3b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180076e3b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180076ddc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180076ddc`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180076d81`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180076d81`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180076eea`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180076eea`

## string_xrefs

- `0x180076e08`: `SetFilePointerEx`
- `0x180076e63`: `ReadFile`
- `0x180076cfb`: `ReadMbrMetadataPartition`
- `0x180076db8`: `ReadMbrMetadataPartition`
- `0x180076e0f`: `ReadMbrMetadataPartition`
- `0x180076e89`: `ReadMbrMetadataPartition`

## pseudocode

```c
__int64 __fastcall ReadMbrMetadataPartition(HANDLE hFile, struct MBR_META_HEADER **a2, unsigned int *a3)
{
  struct MBR_META_HEADER *v3; // rdi
  signed int DiskLayoutInternal; // ebx
  LARGE_INTEGER v7; // r15
  DWORD v8; // r14d
  __int64 i; // r8
  signed int LastError; // eax
  __int64 v11; // rcx
  signed int v12; // eax
  int v13; // edx
  int v14; // ecx
  const wchar_t *v15; // r9
  unsigned __int64 v16; // rcx
  signed int v17; // eax
  __int64 *v18; // rdx
  struct _DISK_GEOMETRY_EX *v20; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  NumberOfBytesRead = 0;
  v20 = 0;
  if ( !a2 )
  {
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(hFile, NullParameter, L"ReadMbrMetadataPartition", L"ppHeader");
    DiskLayoutInternal = -2147024809;
    goto LABEL_35;
  }
  *a2 = 0;
  DiskLayoutInternal = GetDiskLayoutInternal(hFile, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v20, a3);
  if ( DiskLayoutInternal < 0 )
    goto LABEL_35;
  v7.QuadPart = 0;
  v8 = 0;
  for ( i = 0; (unsigned int)i < v20->Geometry.Cylinders.HighPart; i = (unsigned int)(i + 1) )
  {
    if ( *((_BYTE *)&v20[2].Geometry.Cylinders.LowPart + 144 * i) == 112 )
    {
      v7 = *(LARGE_INTEGER *)(&v20[1].Geometry.SectorsPerTrack + 36 * i);
      v8 = *(&v20[1].DiskSize.LowPart + 36 * i);
      break;
    }
  }
  operator delete(v20, (const struct std::nothrow_t *)v20);
  v20 = 0;
  v3 = (struct MBR_META_HEADER *)VirtualAlloc(0, v8, 0x3000u, 4u);
  if ( !v3 )
  {
    LastError = GetLastError();
    DiskLayoutInternal = LastError;
    if ( LastError > 0 )
      DiskLayoutInternal = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(v11, AllocationFailure, L"ReadMbrMetadataPartition", L"MBR_META_HEADER");
    goto LABEL_35;
  }
  if ( SetFilePointerEx(hFile, v7, 0, 0) )
  {
    if ( ReadFile(hFile, v3, v8, &NumberOfBytesRead, 0) )
    {
      if ( *(_DWORD *)v3 == 524289 )
      {
        v16 = v8 - 12LL;
        if ( v16 / 0x60 >= *((unsigned int *)v3 + 2) )
        {
          *a2 = v3;
          v3 = 0;
          goto LABEL_35;
        }
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_35;
        v18 = MetadataPartitionTooSmall;
      }
      else
      {
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_35;
        v18 = InvalidMetadataSignature;
      }
      McTemplateU0z_EventWriteTransfer(v16, v18, L"ReadMbrMetadataPartition");
      goto LABEL_35;
    }
    v17 = GetLastError();
    DiskLayoutInternal = v17;
    if ( v17 > 0 )
      DiskLayoutInternal = (unsigned __int16)v17 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    {
      v15 = L"ReadFile";
      goto LABEL_21;
    }
  }
  else
  {
    v12 = GetLastError();
    DiskLayoutInternal = v12;
    if ( v12 > 0 )
      DiskLayoutInternal = (unsigned __int16)v12 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    {
      v15 = L"SetFilePointerEx";
LABEL_21:
      McTemplateU0zzq_EventWriteTransfer(
        v14,
        v13,
        (unsigned int)L"ReadMbrMetadataPartition",
        (_DWORD)v15,
        DiskLayoutInternal);
    }
  }
LABEL_35:
  SafeFreeDiskGeometry(&v20);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  return (unsigned int)DiskLayoutInternal;
}

```

## disassembly

```asm
0x180076cb0  mov     [rsp+arg_10], rbx
0x180076cb5  mov     [rsp+arg_18], rbp
0x180076cba  push    rsi
0x180076cbb  push    rdi
0x180076cbc  push    r13
0x180076cbe  push    r14
0x180076cc0  push    r15
0x180076cc2  sub     rsp, 50h
0x180076cc6  mov     rax, cs:__security_cookie
0x180076ccd  xor     rax, rsp
0x180076cd0  mov     [rsp+78h+var_38], rax
0x180076cd5  xor     edi, edi
0x180076cd7  mov     rsi, rdx
0x180076cda  mov     [rsp+78h+NumberOfBytesRead], edi
0x180076cde  mov     rbp, rcx
0x180076ce1  mov     [rsp+78h+var_48], rdi
0x180076ce6  test    rdx, rdx
0x180076ce9  jnz     short loc_180076D18
0x180076ceb  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076cf2  jz      short loc_180076D0E
0x180076cf4  lea     r9, aPpheader; "ppHeader"
0x180076cfb  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180076d02  lea     rdx, NullParameter
0x180076d09  call    McTemplateU0zz_EventWriteTransfer
0x180076d0e  mov     ebx, 80070057h
0x180076d13  jmp     loc_180076ED0
0x180076d18  mov     [rdx], rdi
0x180076d1b  lea     rdx, [rsp+78h+var_48]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x180076d20  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x180076d25  mov     ebx, eax
0x180076d27  test    eax, eax
0x180076d29  js      loc_180076ED0
0x180076d2f  mov     rdx, [rsp+78h+var_48]; struct std::nothrow_t *
0x180076d34  xor     r15d, r15d
0x180076d37  xor     r14d, r14d
0x180076d3a  xor     r8d, r8d
0x180076d3d  cmp     r8d, [rdx+4]
0x180076d41  jnb     short loc_180076D60
0x180076d43  lea     rcx, [r8+r8*8]
0x180076d47  add     rcx, rcx
0x180076d4a  cmp     byte ptr [rdx+rcx*8+50h], 70h ; 'p'
0x180076d4f  jz      short loc_180076D56
0x180076d51  inc     r8d
0x180076d54  jmp     short loc_180076D3D
0x180076d56  mov     r15, [rdx+rcx*8+38h]
0x180076d5b  mov     r14d, [rdx+rcx*8+40h]
0x180076d60  mov     rcx, rdx; void *
0x180076d63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076d68  mov     r9d, 4; flProtect
0x180076d6e  mov     edx, r14d; dwSize
0x180076d71  mov     r8d, 3000h; flAllocationType
0x180076d77  mov     [rsp+78h+var_48], rdi
0x180076d7c  xor     ecx, ecx; lpAddress
0x180076d7e  mov     r13d, r14d
0x180076d81  call    cs:__imp_VirtualAlloc
0x180076d87  mov     rdi, rax
0x180076d8a  test    rax, rax
0x180076d8d  jnz     short loc_180076DD0
0x180076d8f  call    cs:__imp_GetLastError
0x180076d95  mov     ebx, eax
0x180076d97  test    eax, eax
0x180076d99  jle     short loc_180076DA4
0x180076d9b  movzx   ebx, ax
0x180076d9e  or      ebx, 80070000h
0x180076da4  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 1
0x180076dab  jz      loc_180076ED0
0x180076db1  lea     r9, aMbrMetaHeader; "MBR_META_HEADER"
0x180076db8  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180076dbf  lea     rdx, AllocationFailure
0x180076dc6  call    McTemplateU0zz_EventWriteTransfer
0x180076dcb  jmp     loc_180076ED0
0x180076dd0  xor     r9d, r9d; dwMoveMethod
0x180076dd3  xor     r8d, r8d; lpNewFilePointer
0x180076dd6  mov     rdx, r15; liDistanceToMove
0x180076dd9  mov     rcx, rbp; hFile
0x180076ddc  call    cs:__imp_SetFilePointerEx
0x180076de2  test    eax, eax
0x180076de4  jnz     short loc_180076E24
0x180076de6  call    cs:__imp_GetLastError
0x180076dec  mov     ebx, eax
0x180076dee  test    eax, eax
0x180076df0  jle     short loc_180076DFB
0x180076df2  movzx   ebx, ax
0x180076df5  or      ebx, 80070000h
0x180076dfb  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076e02  jz      loc_180076ED0
0x180076e08  lea     r9, aSetfilepointer; "SetFilePointerEx"
0x180076e0f  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180076e16  mov     dword ptr [rsp+78h+lpOverlapped], ebx
0x180076e1a  call    McTemplateU0zzq_EventWriteTransfer
0x180076e1f  jmp     loc_180076ED0
0x180076e24  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180076e29  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180076e32  mov     r8d, r14d; nNumberOfBytesToRead
0x180076e35  mov     rdx, rdi; lpBuffer
0x180076e38  mov     rcx, rbp; hFile
0x180076e3b  call    cs:__imp_ReadFile
0x180076e41  test    eax, eax
0x180076e43  jnz     short loc_180076E6C
0x180076e45  call    cs:__imp_GetLastError
0x180076e4b  mov     ebx, eax
0x180076e4d  test    eax, eax
0x180076e4f  jle     short loc_180076E5A
0x180076e51  movzx   ebx, ax
0x180076e54  or      ebx, 80070000h
0x180076e5a  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076e61  jz      short loc_180076ED0
0x180076e63  lea     r9, aReadfile; "ReadFile"
0x180076e6a  jmp     short loc_180076E0F
0x180076e6c  cmp     dword ptr [rdi], 80001h
0x180076e72  jz      short loc_180076E97
0x180076e74  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076e7b  mov     ebx, 8007000Bh
0x180076e80  jz      short loc_180076ED0
0x180076e82  lea     rdx, InvalidMetadataSignature
0x180076e89  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180076e90  call    McTemplateU0z_EventWriteTransfer
0x180076e95  jmp     short loc_180076ED0
0x180076e97  lea     rcx, [r13-0Ch]
0x180076e9b  mov     rax, 0AAAAAAAAAAAAAAABh
0x180076ea5  mul     rcx
0x180076ea8  mov     eax, [rdi+8]
0x180076eab  shr     rdx, 6
0x180076eaf  cmp     rdx, rax
0x180076eb2  jnb     short loc_180076ECB
0x180076eb4  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076ebb  mov     ebx, 8007000Bh
0x180076ec0  jz      short loc_180076ED0
0x180076ec2  lea     rdx, MetadataPartitionTooSmall
0x180076ec9  jmp     short loc_180076E89
0x180076ecb  mov     [rsi], rdi
0x180076ece  xor     edi, edi
0x180076ed0  lea     rcx, [rsp+78h+var_48]; struct _DISK_GEOMETRY_EX **
0x180076ed5  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x180076eda  test    rdi, rdi
0x180076edd  jz      short loc_180076EF0
0x180076edf  xor     edx, edx; dwSize
0x180076ee1  mov     r8d, 8000h; dwFreeType
0x180076ee7  mov     rcx, rdi; lpAddress
0x180076eea  call    cs:__imp_VirtualFree
0x180076ef0  mov     eax, ebx
0x180076ef2  mov     rcx, [rsp+78h+var_38]
0x180076ef7  xor     rcx, rsp; StackCookie
0x180076efa  call    __security_check_cookie
0x180076eff  lea     r11, [rsp+78h+var_28]
0x180076f04  mov     rbx, [r11+40h]
0x180076f08  mov     rbp, [r11+48h]
0x180076f0c  mov     rsp, r11
0x180076f0f  pop     r15
0x180076f11  pop     r14
0x180076f13  pop     r13
0x180076f15  pop     rdi
0x180076f16  pop     rsi
0x180076f17  retn
```
