# MountDiscImage(IShellItem *,int,ulong *)

- ea: `0x1801f180c`
- end: `0x1801f1c3f`
- name: `?MountDiscImage@@YAJPEAUIShellItem@@HPEAK@Z`
- size: `1075`
- prototype: `__int64 __fastcall(struct IShellItem *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18040212c`

## callees

- `0x1800208d8`
- `0x18003eab0`
- `0x1801d7eac`
- `0x1801f180c`
- `0x180233280`
- `0x180401e8c`
- `0x1804029cc`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801f1961`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801f1961`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1801f19fa`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1801f19fa`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1801f1b50`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1801f1b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f1c01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f1c01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f18b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1b73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f18b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1b73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f1c0d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801f1a45`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801f1a45`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1801f1b33`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1801f1b33`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x1801f193b`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x1801f193b`
- `VirtDisk!OpenVirtualDisk` at `0x1801f19bd`
- `VirtDisk!OpenVirtualDisk` at `0x1801f1bc9`
- `VirtDisk!OpenVirtualDisk` at `0x1801f19bd`
- `VirtDisk!OpenVirtualDisk` at `0x1801f1bc9`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f19e8`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f1ab0`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f1be1`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f19e8`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f1ab0`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801f1be1`
- `VirtDisk!AttachVirtualDisk` at `0x1801f1a7c`
- `VirtDisk!AttachVirtualDisk` at `0x1801f1a7c`
- `VirtDisk!DetachVirtualDisk` at `0x1801f1b87`
- `VirtDisk!DetachVirtualDisk` at `0x1801f1b87`
- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x1801f18ef`
- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x1801f18ef`

## string_xrefs

- `0x1801f18e8`: `WindowsLockdownDangerousExtensionEnforcement`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MountDiscImage(struct IShellItem *a1, int a2, unsigned int *a3)
{
  int TypeFromItem; // ebx
  ATTACH_VIRTUAL_DISK_FLAG v7; // edi
  char v8; // si
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  DWORD FileAttributesW; // eax
  char v11; // si
  VIRTUAL_DISK_ACCESS_MASK v12; // esi
  signed int v13; // eax
  DWORD LogicalDrives; // esi
  signed int v15; // eax
  signed int VirtualDiskPhysicalPath; // eax
  unsigned int i; // edi
  char *v18; // rcx
  ULONG DiskPathSizeInBytes; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR ppwsz; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+68h] [rbp-98h] BYREF
  _ATTACH_VIRTUAL_DISK_PARAMETERS Parameters[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h]
  WCHAR psz[4]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR DiskPath[9]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[510]; // [rsp+B2h] [rbp-4Eh] BYREF
  WCHAR TargetPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  DiskPathSizeInBytes = 0;
  TypeFromItem = GetTypeFromItem(a1, (enum DISC_IMAGE_TYPE_FLAGS *)&DiskPathSizeInBytes);
  if ( TypeFromItem >= 0 )
  {
    v7 = ATTACH_VIRTUAL_DISK_FLAG_PERMANENT_LIFETIME;
    v8 = DiskPathSizeInBytes;
    if ( a2 )
    {
      if ( (DiskPathSizeInBytes & 3) != 0 )
        v7 = ATTACH_VIRTUAL_DISK_FLAG_PERMANENT_LIFETIME|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER;
      else
        TypeFromItem = -2147024809;
    }
    if ( TypeFromItem >= 0 )
    {
      memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
      TypeFromItem = _GetStorageTypeForOpenVirtualDisk(DiskPathSizeInBytes, &VirtualStorageType);
      if ( TypeFromItem >= 0 )
      {
        lpFileName = 0;
        GetDisplayName = a1->lpVtbl->GetDisplayName;
        CoTaskMemFree(0);
        TypeFromItem = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))GetDisplayName)(
                         a1,
                         2147844096LL,
                         &lpFileName);
        if ( TypeFromItem < 0 )
        {
LABEL_55:
          CoTaskMemFree((LPVOID)lpFileName);
          return (unsigned int)TypeFromItem;
        }
        DiskPathSizeInBytes = 0;
        if ( (int)WldpQueryPolicySettingEnabled2(
                    L"WindowsLockdownDangerousExtensionEnforcement",
                    (int *)&DiskPathSizeInBytes) >= 0 )
        {
          if ( DiskPathSizeInBytes )
          {
            DiskPathSizeInBytes = 0;
            *(_DWORD *)psz = 0;
            ZoneCheckUrlExW(lpFileName, &DiskPathSizeInBytes, 4, psz, 4, 6150, 5123, 0);
            if ( (DiskPathSizeInBytes & 0xF) == 1 )
            {
              TypeFromItem = -2147020338;
              goto LABEL_55;
            }
          }
        }
        if ( (v8 & 3) != 0 )
          goto LABEL_18;
        FileAttributesW = GetFileAttributesW(lpFileName);
        v11 = FileAttributesW;
        if ( FileAttributesW == -1 )
        {
          TypeFromItem = ResultFromKnownLastError();
          if ( TypeFromItem < 0 )
            goto LABEL_55;
        }
        if ( (v11 & 1) != 0 )
        {
LABEL_18:
          v7 |= 1u;
          v12 = VIRTUAL_DISK_ACCESS_READ;
        }
        else
        {
          v12 = VIRTUAL_DISK_ACCESS_ALL;
        }
        VirtualDiskHandle = 0;
        DiskPathSizeInBytes = 260;
        v13 = OpenVirtualDisk(&VirtualStorageType, lpFileName, v12, OPEN_VIRTUAL_DISK_FLAG_NONE, 0, &VirtualDiskHandle);
        TypeFromItem = v13;
        if ( v13 > 0 )
          TypeFromItem = (unsigned __int16)v13 | 0x80070000;
        if ( TypeFromItem < 0 )
        {
          if ( TypeFromItem == -2147024864
            && v12 != VIRTUAL_DISK_ACCESS_READ
            && !OpenVirtualDisk(
                  &VirtualStorageType,
                  lpFileName,
                  VIRTUAL_DISK_ACCESS_READ,
                  OPEN_VIRTUAL_DISK_FLAG_NONE,
                  0,
                  &VirtualDiskHandle)
            && !GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, DiskPath) )
          {
            TypeFromItem = 1;
          }
          goto LABEL_53;
        }
        if ( !GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, DiskPath) )
        {
          TypeFromItem = 1;
          goto LABEL_53;
        }
        LogicalDrives = GetLogicalDrives();
        if ( (LogicalDrives & 0x3FFFFFC) == 0x3FFFFFC )
          TypeFromItem = -2147023446;
        if ( TypeFromItem < 0 )
          goto LABEL_53;
        *(_OWORD *)&Parameters[0].Version = 0;
        v27 = 0;
        Parameters[0].Version = ATTACH_VIRTUAL_DISK_VERSION_1;
        SecurityDescriptor = 0;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                L"D:P(A;;GA;;;WD)(A;;GA;;;AC)",
                1u,
                &SecurityDescriptor,
                0) )
        {
          TypeFromItem = ResultFromKnownLastError();
          if ( TypeFromItem < 0 )
            goto LABEL_47;
        }
        v15 = AttachVirtualDisk(VirtualDiskHandle, SecurityDescriptor, v7, 0, Parameters, 0);
        TypeFromItem = v15;
        if ( v15 > 0 )
          TypeFromItem = (unsigned __int16)v15 | 0x80070000;
        if ( TypeFromItem < 0 || !a2 )
          goto LABEL_47;
        VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, DiskPath);
        TypeFromItem = VirtualDiskPhysicalPath;
        if ( VirtualDiskPhysicalPath > 0 )
          TypeFromItem = (unsigned __int16)VirtualDiskPhysicalPath | 0x80070000;
        if ( TypeFromItem < 0 )
          goto LABEL_46;
        TypeFromItem = StringCchPrintfW(TargetPath, 0x104u, L"\\Device\\CdRom%s", v30);
        if ( TypeFromItem < 0 )
          goto LABEL_46;
        for ( i = 2; i < 0x1A; ++i )
        {
          if ( (LogicalDrives & (1 << i)) != 1 << i )
            break;
        }
        ppwsz = 0;
        CoTaskMemFree(0);
        psz[0] = i + 65;
        wcscpy(&psz[1], L":");
        TypeFromItem = SHStrDupW(psz, &ppwsz);
        if ( TypeFromItem >= 0 )
        {
          if ( DefineDosDeviceW(9u, ppwsz, TargetPath) )
          {
            TypeFromItem = 0;
          }
          else
          {
            TypeFromItem = ResultFromKnownLastError();
            if ( TypeFromItem < 0 )
              goto LABEL_45;
          }
          *a3 = i;
        }
LABEL_45:
        CoTaskMemFree(ppwsz);
        if ( TypeFromItem < 0 )
LABEL_46:
          DetachVirtualDisk(VirtualDiskHandle, DETACH_VIRTUAL_DISK_FLAG_NONE, 0);
LABEL_47:
        CLocalMemPtr<_SECURITY_DESCRIPTOR>::~CLocalMemPtr<_SECURITY_DESCRIPTOR>(&SecurityDescriptor);
LABEL_53:
        v18 = (char *)VirtualDiskHandle;
        VirtualDiskHandle = 0;
        if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v18);
        goto LABEL_55;
      }
    }
  }
  return (unsigned int)TypeFromItem;
}

```

## disassembly

```asm
0x1801f180c  mov     [rsp-8+arg_8], rbx
0x1801f1811  push    rbp
0x1801f1812  push    rsi
0x1801f1813  push    rdi
0x1801f1814  push    r12
0x1801f1816  push    r13
0x1801f1818  push    r14
0x1801f181a  push    r15
0x1801f181c  lea     rbp, [rsp-3D0h]
0x1801f1824  sub     rsp, 4D0h
0x1801f182b  mov     rax, cs:__security_cookie
0x1801f1832  xor     rax, rsp
0x1801f1835  mov     [rbp+400h+var_40], rax
0x1801f183c  mov     r12, r8
0x1801f183f  mov     r15d, edx
0x1801f1842  mov     r14, rcx
0x1801f1845  xor     r13d, r13d
0x1801f1848  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x1801f184d  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; enum DISC_IMAGE_TYPE_FLAGS *
0x1801f1852  call    ?GetTypeFromItem@@YAJPEAUIShellItem@@PEAW4DISC_IMAGE_TYPE_FLAGS@@@Z; GetTypeFromItem(IShellItem *,DISC_IMAGE_TYPE_FLAGS *)
0x1801f1857  mov     ebx, eax
0x1801f1859  test    eax, eax
0x1801f185b  js      loc_1801F1C13
0x1801f1861  lea     edi, [r13+4]
0x1801f1865  mov     esi, [rsp+500h+DiskPathSizeInBytes]
0x1801f1869  test    r15d, r15d
0x1801f186c  jz      short loc_1801F187F
0x1801f186e  test    sil, 3
0x1801f1872  jz      short loc_1801F187A
0x1801f1874  lea     edi, [r13+6]
0x1801f1878  jmp     short loc_1801F187F
0x1801f187a  mov     ebx, 80070057h
0x1801f187f  test    ebx, ebx
0x1801f1881  js      loc_1801F1C13
0x1801f1887  xorps   xmm0, xmm0
0x1801f188a  xor     eax, eax
0x1801f188c  movups  xmmword ptr [rsp+500h+VirtualStorageType.DeviceId], xmm0
0x1801f1891  mov     dword ptr [rsp+500h+VirtualStorageType.VendorId.Data4+4], eax
0x1801f1895  lea     rdx, [rsp+500h+VirtualStorageType]
0x1801f189a  mov     ecx, esi
0x1801f189c  call    ?_GetStorageTypeForOpenVirtualDisk@@YAJW4DISC_IMAGE_TYPE_FLAGS@@PEAU_VIRTUAL_STORAGE_TYPE@@@Z; _GetStorageTypeForOpenVirtualDisk(DISC_IMAGE_TYPE_FLAGS,_VIRTUAL_STORAGE_TYPE *)
0x1801f18a1  mov     ebx, eax
0x1801f18a3  test    eax, eax
0x1801f18a5  js      loc_1801F1C13
0x1801f18ab  mov     [rsp+500h+lpFileName], r13
0x1801f18b0  mov     rax, [r14]
0x1801f18b3  mov     rbx, [rax+28h]
0x1801f18b7  xor     ecx, ecx; pv
0x1801f18b9  call    cs:__imp_CoTaskMemFree
0x1801f18bf  lea     r8, [rsp+500h+lpFileName]
0x1801f18c4  mov     edx, 80058000h
0x1801f18c9  mov     rcx, r14
0x1801f18cc  mov     rax, rbx
0x1801f18cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f18d4  mov     ebx, eax
0x1801f18d6  test    eax, eax
0x1801f18d8  js      loc_1801F1C08
0x1801f18de  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x1801f18e3  lea     rdx, [rsp+500h+DiskPathSizeInBytes]
0x1801f18e8  lea     rcx, aWindowslockdow; "WindowsLockdownDangerousExtensionEnforc"...
0x1801f18ef  call    cs:__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z; WldpQueryPolicySettingEnabled2(ushort const *,int *)
0x1801f18f5  mov     r14d, 1
0x1801f18fb  test    eax, eax
0x1801f18fd  js      short loc_1801F1956
0x1801f18ff  cmp     [rsp+500h+DiskPathSizeInBytes], r13d
0x1801f1904  jz      short loc_1801F1956
0x1801f1906  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x1801f190b  mov     dword ptr [rbp+400h+psz], r13d
0x1801f190f  mov     [rsp+500h+var_4C8], r13
0x1801f1914  mov     [rsp+500h+var_4D0], 1403h
0x1801f191c  mov     dword ptr [rsp+500h+Handle], 1806h
0x1801f1924  lea     r8d, [r14+3]
0x1801f1928  mov     dword ptr [rsp+500h+Parameters], r8d
0x1801f192d  lea     r9, [rbp+400h+psz]
0x1801f1931  lea     rdx, [rsp+500h+DiskPathSizeInBytes]
0x1801f1936  mov     rcx, [rsp+500h+lpFileName]
0x1801f193b  call    cs:__imp_ZoneCheckUrlExW
0x1801f1941  mov     eax, [rsp+500h+DiskPathSizeInBytes]
0x1801f1945  and     al, 0Fh
0x1801f1947  cmp     al, r14b
0x1801f194a  jnz     short loc_1801F1956
0x1801f194c  mov     ebx, 800711CEh
0x1801f1951  jmp     loc_1801F1C08
0x1801f1956  test    sil, 3
0x1801f195a  jnz     short loc_1801F1989
0x1801f195c  mov     rcx, [rsp+500h+lpFileName]; lpFileName
0x1801f1961  call    cs:__imp_GetFileAttributesW
0x1801f1967  mov     esi, eax
0x1801f1969  cmp     eax, 0FFFFFFFFh
0x1801f196c  jnz     short loc_1801F197D
0x1801f196e  call    ResultFromKnownLastError
0x1801f1973  mov     ebx, eax
0x1801f1975  test    eax, eax
0x1801f1977  js      loc_1801F1C08
0x1801f197d  test    r14b, sil
0x1801f1980  jnz     short loc_1801F1989
0x1801f1982  mov     esi, 3F0000h
0x1801f1987  jmp     short loc_1801F1991
0x1801f1989  or      edi, r14d
0x1801f198c  mov     esi, 0D0000h
0x1801f1991  mov     [rsp+500h+VirtualDiskHandle], r13
0x1801f1996  mov     [rsp+500h+DiskPathSizeInBytes], 104h
0x1801f199e  lea     rax, [rsp+500h+VirtualDiskHandle]
0x1801f19a3  mov     [rsp+500h+Handle], rax; Handle
0x1801f19a8  mov     [rsp+500h+Parameters], r13; Parameters
0x1801f19ad  xor     r9d, r9d; Flags
0x1801f19b0  mov     r8d, esi; VirtualDiskAccessMask
0x1801f19b3  mov     rdx, [rsp+500h+lpFileName]; Path
0x1801f19b8  lea     rcx, [rsp+500h+VirtualStorageType]; VirtualStorageType
0x1801f19bd  call    cs:__imp_OpenVirtualDisk
0x1801f19c3  mov     ebx, eax
0x1801f19c5  test    eax, eax
0x1801f19c7  jle     short loc_1801F19D2
0x1801f19c9  movzx   ebx, ax
0x1801f19cc  or      ebx, 80070000h
0x1801f19d2  test    ebx, ebx
0x1801f19d4  js      loc_1801F1B9A
0x1801f19da  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x1801f19de  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1801f19e3  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1801f19e8  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1801f19ee  test    eax, eax
0x1801f19f0  jnz     short loc_1801F19FA
0x1801f19f2  mov     ebx, r14d
0x1801f19f5  jmp     loc_1801F1BED
0x1801f19fa  call    cs:__imp_GetLogicalDrives
0x1801f1a00  mov     esi, eax
0x1801f1a02  mov     ecx, eax
0x1801f1a04  mov     edx, 3FFFFFCh
0x1801f1a09  and     ecx, edx
0x1801f1a0b  mov     eax, 800705AAh
0x1801f1a10  cmp     ecx, edx
0x1801f1a12  cmovz   ebx, eax
0x1801f1a15  test    ebx, ebx
0x1801f1a17  js      loc_1801F1BED
0x1801f1a1d  xorps   xmm0, xmm0
0x1801f1a20  xor     eax, eax
0x1801f1a22  movups  xmmword ptr [rbp+400h+var_480.Version], xmm0
0x1801f1a26  mov     [rbp+400h+var_470], rax
0x1801f1a2a  mov     [rbp+400h+var_480.Version], r14d
0x1801f1a2e  mov     [rsp+500h+SecurityDescriptor], r13
0x1801f1a33  xor     r9d, r9d; SecurityDescriptorSize
0x1801f1a36  lea     r8, [rsp+500h+SecurityDescriptor]; SecurityDescriptor
0x1801f1a3b  mov     edx, r14d; StringSDRevision
0x1801f1a3e  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;WD)(A;;GA;;;AC)"
0x1801f1a45  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801f1a4b  test    eax, eax
0x1801f1a4d  jnz     short loc_1801F1A5E
0x1801f1a4f  call    ResultFromKnownLastError
0x1801f1a54  mov     ebx, eax
0x1801f1a56  test    eax, eax
0x1801f1a58  js      loc_1801F1B8E
0x1801f1a5e  mov     [rsp+500h+Handle], r13; Overlapped
0x1801f1a63  lea     rax, [rbp+400h+var_480]
0x1801f1a67  mov     [rsp+500h+Parameters], rax; Parameters
0x1801f1a6c  xor     r9d, r9d; ProviderSpecificFlags
0x1801f1a6f  mov     r8d, edi; Flags
0x1801f1a72  mov     rdx, [rsp+500h+SecurityDescriptor]; SecurityDescriptor
0x1801f1a77  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1801f1a7c  call    cs:__imp_AttachVirtualDisk
0x1801f1a82  mov     ebx, eax
0x1801f1a84  test    eax, eax
0x1801f1a86  jle     short loc_1801F1A91
0x1801f1a88  movzx   ebx, ax
0x1801f1a8b  or      ebx, 80070000h
0x1801f1a91  test    ebx, ebx
0x1801f1a93  js      loc_1801F1B8E
0x1801f1a99  test    r15d, r15d
0x1801f1a9c  jz      loc_1801F1B8E
0x1801f1aa2  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x1801f1aa6  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1801f1aab  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1801f1ab0  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1801f1ab6  mov     ebx, eax
0x1801f1ab8  test    eax, eax
0x1801f1aba  jle     short loc_1801F1AC5
0x1801f1abc  movzx   ebx, ax
0x1801f1abf  or      ebx, 80070000h
0x1801f1ac5  test    ebx, ebx
0x1801f1ac7  js      loc_1801F1B7D
0x1801f1acd  lea     r9, [rbp+400h+var_44E]
0x1801f1ad1  lea     r8, aDeviceCdromS; "\\Device\\CdRom%s"
0x1801f1ad8  mov     edx, 104h; unsigned __int64
0x1801f1add  lea     rcx, [rbp+400h+TargetPath]; unsigned __int16 *
0x1801f1ae4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801f1ae9  mov     ebx, eax
0x1801f1aeb  test    eax, eax
0x1801f1aed  js      loc_1801F1B7D
0x1801f1af3  mov     edi, 2
0x1801f1af8  mov     ecx, edi
0x1801f1afa  mov     edx, r14d
0x1801f1afd  shl     edx, cl
0x1801f1aff  mov     eax, edx
0x1801f1b01  and     eax, esi
0x1801f1b03  cmp     eax, edx
0x1801f1b05  jnz     short loc_1801F1B0F
0x1801f1b07  add     edi, r14d
0x1801f1b0a  cmp     edi, 1Ah
0x1801f1b0d  jb      short loc_1801F1AF8
0x1801f1b0f  mov     [rsp+500h+ppwsz], r13
0x1801f1b14  xor     ecx, ecx; pv
0x1801f1b16  call    cs:__imp_CoTaskMemFree
0x1801f1b1c  lea     eax, [rdi+41h]
0x1801f1b1f  mov     [rbp+400h+psz], ax
0x1801f1b23  mov     dword ptr [rbp+400h+psz+2], 3Ah ; ':'
0x1801f1b2a  lea     rdx, [rsp+500h+ppwsz]; ppwsz
0x1801f1b2f  lea     rcx, [rbp+400h+psz]; psz
0x1801f1b33  call    cs:__imp_SHStrDupW
0x1801f1b39  mov     ebx, eax
0x1801f1b3b  test    eax, eax
0x1801f1b3d  js      short loc_1801F1B6E
0x1801f1b3f  lea     r8, [rbp+400h+TargetPath]; lpTargetPath
0x1801f1b46  mov     rdx, [rsp+500h+ppwsz]; lpDeviceName
0x1801f1b4b  mov     ecx, 9; dwFlags
0x1801f1b50  call    cs:__imp_DefineDosDeviceW
0x1801f1b56  test    eax, eax
0x1801f1b58  jz      short loc_1801F1B5F
0x1801f1b5a  mov     ebx, r13d
0x1801f1b5d  jmp     short loc_1801F1B6A
0x1801f1b5f  call    ResultFromKnownLastError
0x1801f1b64  mov     ebx, eax
0x1801f1b66  test    eax, eax
0x1801f1b68  js      short loc_1801F1B6E
0x1801f1b6a  mov     [r12], edi
0x1801f1b6e  mov     rcx, [rsp+500h+ppwsz]; pv
0x1801f1b73  call    cs:__imp_CoTaskMemFree
0x1801f1b79  test    ebx, ebx
0x1801f1b7b  jns     short loc_1801F1B8E
0x1801f1b7d  xor     r8d, r8d; ProviderSpecificFlags
0x1801f1b80  xor     edx, edx; Flags
0x1801f1b82  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1801f1b87  call    cs:__imp_DetachVirtualDisk
0x1801f1b8d  nop
0x1801f1b8e  lea     rcx, [rsp+500h+SecurityDescriptor]
0x1801f1b93  call    ??1?$CLocalMemPtr@U_SECURITY_DESCRIPTOR@@@@QEAA@XZ; CLocalMemPtr<_SECURITY_DESCRIPTOR>::~CLocalMemPtr<_SECURITY_DESCRIPTOR>(void)
0x1801f1b98  jmp     short loc_1801F1BED
0x1801f1b9a  cmp     ebx, 80070020h
0x1801f1ba0  jnz     short loc_1801F1BED
0x1801f1ba2  mov     r8d, 0D0000h; VirtualDiskAccessMask
0x1801f1ba8  cmp     esi, r8d
0x1801f1bab  jz      short loc_1801F1BED
0x1801f1bad  lea     rax, [rsp+500h+VirtualDiskHandle]
0x1801f1bb2  mov     [rsp+500h+Handle], rax; Handle
0x1801f1bb7  mov     [rsp+500h+Parameters], r13; Parameters
0x1801f1bbc  xor     r9d, r9d; Flags
0x1801f1bbf  mov     rdx, [rsp+500h+lpFileName]; Path
0x1801f1bc4  lea     rcx, [rsp+500h+VirtualStorageType]; VirtualStorageType
0x1801f1bc9  call    cs:__imp_OpenVirtualDisk
0x1801f1bcf  test    eax, eax
0x1801f1bd1  jnz     short loc_1801F1BED
0x1801f1bd3  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x1801f1bd7  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1801f1bdc  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1801f1be1  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1801f1be7  test    eax, eax
0x1801f1be9  cmovz   ebx, r14d
0x1801f1bed  mov     rcx, [rsp+500h+VirtualDiskHandle]; hObject
0x1801f1bf2  mov     [rsp+500h+VirtualDiskHandle], r13
0x1801f1bf7  lea     rax, [rcx-1]
0x1801f1bfb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f1bff  ja      short loc_1801F1C08
0x1801f1c01  call    cs:__imp_CloseHandle
0x1801f1c07  nop
0x1801f1c08  mov     rcx, [rsp+500h+lpFileName]; pv
0x1801f1c0d  call    cs:__imp_CoTaskMemFree
0x1801f1c13  mov     eax, ebx
0x1801f1c15  mov     rcx, [rbp+400h+var_40]
0x1801f1c1c  xor     rcx, rsp; StackCookie
0x1801f1c1f  call    __security_check_cookie
0x1801f1c24  mov     rbx, [rsp+500h+arg_8]
0x1801f1c2c  add     rsp, 4D0h
0x1801f1c33  pop     r15
0x1801f1c35  pop     r14
0x1801f1c37  pop     r13
0x1801f1c39  pop     r12
0x1801f1c3b  pop     rdi
0x1801f1c3c  pop     rsi
0x1801f1c3d  pop     rbp
0x1801f1c3e  retn
```
