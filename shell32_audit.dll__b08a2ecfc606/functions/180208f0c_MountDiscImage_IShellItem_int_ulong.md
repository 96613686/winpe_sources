# MountDiscImage(IShellItem *,int,ulong *)

- ea: `0x180208f0c`
- end: `0x1802093b2`
- name: `?MountDiscImage@@YAJPEAUIShellItem@@HPEAK@Z`
- size: `1190`
- prototype: `__int64 __fastcall(struct IShellItem *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18042f780`

## callees

- `0x180018e4c`
- `0x18003a3e0`
- `0x1801ef368`
- `0x180208f0c`
- `0x180249490`
- `0x18042f4ac`
- `0x180430094`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x18020911e`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x18020911e`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180209298`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180209298`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180209073`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180209073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180209367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180209367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180208fb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180209252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802092c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180209379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180208fb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180209252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802092c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180209379`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18020916f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18020916f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180209275`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180209275`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x180209047`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x180209047`
- `VirtDisk!OpenVirtualDisk` at `0x1802090d5`
- `VirtDisk!OpenVirtualDisk` at `0x180209323`
- `VirtDisk!OpenVirtualDisk` at `0x1802090d5`
- `VirtDisk!OpenVirtualDisk` at `0x180209323`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180209106`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1802091e6`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180209341`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180209106`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1802091e6`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180209341`
- `VirtDisk!AttachVirtualDisk` at `0x1802091ac`
- `VirtDisk!AttachVirtualDisk` at `0x1802091ac`
- `VirtDisk!DetachVirtualDisk` at `0x1802092db`
- `VirtDisk!DetachVirtualDisk` at `0x1802092db`
- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x180208ff5`
- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x180208ff5`

## string_xrefs

- `0x180208fee`: `WindowsLockdownDangerousExtensionEnforcement`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180208f0c  mov     [rsp-8+arg_8], rbx
0x180208f11  push    rbp
0x180208f12  push    rsi
0x180208f13  push    rdi
0x180208f14  push    r12
0x180208f16  push    r13
0x180208f18  push    r14
0x180208f1a  push    r15
0x180208f1c  lea     rbp, [rsp-3D0h]
0x180208f24  sub     rsp, 4D0h
0x180208f2b  mov     rax, cs:__security_cookie
0x180208f32  xor     rax, rsp
0x180208f35  mov     [rbp+400h+var_40], rax
0x180208f3c  mov     r12, r8
0x180208f3f  mov     r15d, edx
0x180208f42  mov     r14, rcx
0x180208f45  xor     r13d, r13d
0x180208f48  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x180208f4d  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; enum DISC_IMAGE_TYPE_FLAGS *
0x180208f52  call    ?GetTypeFromItem@@YAJPEAUIShellItem@@PEAW4DISC_IMAGE_TYPE_FLAGS@@@Z; GetTypeFromItem(IShellItem *,DISC_IMAGE_TYPE_FLAGS *)
0x180208f57  mov     ebx, eax
0x180208f59  test    eax, eax
0x180208f5b  js      loc_180209385
0x180208f61  lea     edi, [r13+4]
0x180208f65  mov     esi, [rsp+500h+DiskPathSizeInBytes]
0x180208f69  test    r15d, r15d
0x180208f6c  jz      short loc_180208F7F
0x180208f6e  test    sil, 3
0x180208f72  jz      short loc_180208F7A
0x180208f74  lea     edi, [r13+6]
0x180208f78  jmp     short loc_180208F7F
0x180208f7a  mov     ebx, 80070057h
0x180208f7f  test    ebx, ebx
0x180208f81  js      loc_180209385
0x180208f87  xorps   xmm0, xmm0
0x180208f8a  xor     eax, eax
0x180208f8c  movups  xmmword ptr [rsp+500h+VirtualStorageType.DeviceId], xmm0
0x180208f91  mov     dword ptr [rsp+500h+VirtualStorageType.VendorId.Data4+4], eax
0x180208f95  lea     rdx, [rsp+500h+VirtualStorageType]
0x180208f9a  mov     ecx, esi
0x180208f9c  call    ?_GetStorageTypeForOpenVirtualDisk@@YAJW4DISC_IMAGE_TYPE_FLAGS@@PEAU_VIRTUAL_STORAGE_TYPE@@@Z; _GetStorageTypeForOpenVirtualDisk(DISC_IMAGE_TYPE_FLAGS,_VIRTUAL_STORAGE_TYPE *)
0x180208fa1  mov     ebx, eax
0x180208fa3  test    eax, eax
0x180208fa5  js      loc_180209385
0x180208fab  mov     [rsp+500h+lpFileName], r13
0x180208fb0  mov     rax, [r14]
0x180208fb3  mov     rbx, [rax+28h]
0x180208fb7  xor     ecx, ecx; pv
0x180208fb9  call    cs:__imp_CoTaskMemFree
0x180208fc0  nop     dword ptr [rax+rax+00h]
0x180208fc5  lea     r8, [rsp+500h+lpFileName]
0x180208fca  mov     edx, 80058000h
0x180208fcf  mov     rcx, r14
0x180208fd2  mov     rax, rbx
0x180208fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180208fda  mov     ebx, eax
0x180208fdc  test    eax, eax
0x180208fde  js      loc_180209374
0x180208fe4  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x180208fe9  lea     rdx, [rsp+500h+DiskPathSizeInBytes]
0x180208fee  lea     rcx, aWindowslockdow; "WindowsLockdownDangerousExtensionEnforc"...
0x180208ff5  call    cs:__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z; WldpQueryPolicySettingEnabled2(ushort const *,int *)
0x180208ffc  nop     dword ptr [rax+rax+00h]
0x180209001  mov     r14d, 1
0x180209007  test    eax, eax
0x180209009  js      short loc_180209068
0x18020900b  cmp     [rsp+500h+DiskPathSizeInBytes], r13d
0x180209010  jz      short loc_180209068
0x180209012  mov     [rsp+500h+DiskPathSizeInBytes], r13d
0x180209017  mov     dword ptr [rbp+400h+psz], r13d
0x18020901b  mov     [rsp+500h+var_4C8], r13
0x180209020  mov     [rsp+500h+var_4D0], 1403h
0x180209028  mov     dword ptr [rsp+500h+Handle], 1806h
0x180209030  lea     r8d, [r14+3]
0x180209034  mov     dword ptr [rsp+500h+Parameters], r8d
0x180209039  lea     r9, [rbp+400h+psz]
0x18020903d  lea     rdx, [rsp+500h+DiskPathSizeInBytes]
0x180209042  mov     rcx, [rsp+500h+lpFileName]
0x180209047  call    cs:__imp_ZoneCheckUrlExW
0x18020904e  nop     dword ptr [rax+rax+00h]
0x180209053  mov     eax, [rsp+500h+DiskPathSizeInBytes]
0x180209057  and     al, 0Fh
0x180209059  cmp     al, r14b
0x18020905c  jnz     short loc_180209068
0x18020905e  mov     ebx, 800711CEh
0x180209063  jmp     loc_180209374
0x180209068  test    sil, 3
0x18020906c  jnz     short loc_1802090A1
0x18020906e  mov     rcx, [rsp+500h+lpFileName]; lpFileName
0x180209073  call    cs:__imp_GetFileAttributesW
0x18020907a  nop     dword ptr [rax+rax+00h]
0x18020907f  mov     esi, eax
0x180209081  cmp     eax, 0FFFFFFFFh
0x180209084  jnz     short loc_180209095
0x180209086  call    ResultFromKnownLastError
0x18020908b  mov     ebx, eax
0x18020908d  test    eax, eax
0x18020908f  js      loc_180209374
0x180209095  test    r14b, sil
0x180209098  jnz     short loc_1802090A1
0x18020909a  mov     esi, 3F0000h
0x18020909f  jmp     short loc_1802090A9
0x1802090a1  or      edi, r14d
0x1802090a4  mov     esi, 0D0000h
0x1802090a9  mov     [rsp+500h+VirtualDiskHandle], r13
0x1802090ae  mov     [rsp+500h+DiskPathSizeInBytes], 104h
0x1802090b6  lea     rax, [rsp+500h+VirtualDiskHandle]
0x1802090bb  mov     [rsp+500h+Handle], rax; Handle
0x1802090c0  mov     [rsp+500h+Parameters], r13; Parameters
0x1802090c5  xor     r9d, r9d; Flags
0x1802090c8  mov     r8d, esi; VirtualDiskAccessMask
0x1802090cb  mov     rdx, [rsp+500h+lpFileName]; Path
0x1802090d0  lea     rcx, [rsp+500h+VirtualStorageType]; VirtualStorageType
0x1802090d5  call    cs:__imp_OpenVirtualDisk
0x1802090dc  nop     dword ptr [rax+rax+00h]
0x1802090e1  mov     ebx, eax
0x1802090e3  test    eax, eax
0x1802090e5  jle     short loc_1802090F0
0x1802090e7  movzx   ebx, ax
0x1802090ea  or      ebx, 80070000h
0x1802090f0  test    ebx, ebx
0x1802090f2  js      loc_1802092F4
0x1802090f8  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x1802090fc  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180209101  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x180209106  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18020910d  nop     dword ptr [rax+rax+00h]
0x180209112  test    eax, eax
0x180209114  jnz     short loc_18020911E
0x180209116  mov     ebx, r14d
0x180209119  jmp     loc_180209353
0x18020911e  call    cs:__imp_GetLogicalDrives
0x180209125  nop     dword ptr [rax+rax+00h]
0x18020912a  mov     esi, eax
0x18020912c  mov     ecx, eax
0x18020912e  mov     edx, 3FFFFFCh
0x180209133  and     ecx, edx
0x180209135  mov     eax, 800705AAh
0x18020913a  cmp     ecx, edx
0x18020913c  cmovz   ebx, eax
0x18020913f  test    ebx, ebx
0x180209141  js      loc_180209353
0x180209147  xorps   xmm0, xmm0
0x18020914a  xor     eax, eax
0x18020914c  movups  xmmword ptr [rbp+400h+var_480.Version], xmm0
0x180209150  mov     [rbp+400h+var_470], rax
0x180209154  mov     [rbp+400h+var_480.Version], r14d
0x180209158  mov     [rsp+500h+SecurityDescriptor], r13
0x18020915d  xor     r9d, r9d; SecurityDescriptorSize
0x180209160  lea     r8, [rsp+500h+SecurityDescriptor]; SecurityDescriptor
0x180209165  mov     edx, r14d; StringSDRevision
0x180209168  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;WD)(A;;GA;;;AC)"
0x18020916f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180209176  nop     dword ptr [rax+rax+00h]
0x18020917b  test    eax, eax
0x18020917d  jnz     short loc_18020918E
0x18020917f  call    ResultFromKnownLastError
0x180209184  mov     ebx, eax
0x180209186  test    eax, eax
0x180209188  js      loc_1802092E8
0x18020918e  mov     [rsp+500h+Handle], r13; Overlapped
0x180209193  lea     rax, [rbp+400h+var_480]
0x180209197  mov     [rsp+500h+Parameters], rax; Parameters
0x18020919c  xor     r9d, r9d; ProviderSpecificFlags
0x18020919f  mov     r8d, edi; Flags
0x1802091a2  mov     rdx, [rsp+500h+SecurityDescriptor]; SecurityDescriptor
0x1802091a7  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1802091ac  call    cs:__imp_AttachVirtualDisk
0x1802091b3  nop     dword ptr [rax+rax+00h]
0x1802091b8  mov     ebx, eax
0x1802091ba  test    eax, eax
0x1802091bc  jle     short loc_1802091C7
0x1802091be  movzx   ebx, ax
0x1802091c1  or      ebx, 80070000h
0x1802091c7  test    ebx, ebx
0x1802091c9  js      loc_1802092E8
0x1802091cf  test    r15d, r15d
0x1802091d2  jz      loc_1802092E8
0x1802091d8  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x1802091dc  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1802091e1  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1802091e6  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1802091ed  nop     dword ptr [rax+rax+00h]
0x1802091f2  mov     ebx, eax
0x1802091f4  test    eax, eax
0x1802091f6  jle     short loc_180209201
0x1802091f8  movzx   ebx, ax
0x1802091fb  or      ebx, 80070000h
0x180209201  test    ebx, ebx
0x180209203  js      loc_1802092D1
0x180209209  lea     r9, [rbp+400h+var_44E]
0x18020920d  lea     r8, aDeviceCdromS; "\\Device\\CdRom%s"
0x180209214  mov     edx, 104h; unsigned __int64
0x180209219  lea     rcx, [rbp+400h+TargetPath]; unsigned __int16 *
0x180209220  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180209225  mov     ebx, eax
0x180209227  test    eax, eax
0x180209229  js      loc_1802092D1
0x18020922f  mov     edi, 2
0x180209234  mov     ecx, edi
0x180209236  mov     edx, r14d
0x180209239  shl     edx, cl
0x18020923b  mov     eax, edx
0x18020923d  and     eax, esi
0x18020923f  cmp     eax, edx
0x180209241  jnz     short loc_18020924B
0x180209243  add     edi, r14d
0x180209246  cmp     edi, 1Ah
0x180209249  jb      short loc_180209234
0x18020924b  mov     [rsp+500h+ppwsz], r13
0x180209250  xor     ecx, ecx; pv
0x180209252  call    cs:__imp_CoTaskMemFree
0x180209259  nop     dword ptr [rax+rax+00h]
0x18020925e  lea     eax, [rdi+41h]
0x180209261  mov     [rbp+400h+psz], ax
0x180209265  mov     dword ptr [rbp+400h+psz+2], 3Ah ; ':'
0x18020926c  lea     rdx, [rsp+500h+ppwsz]; ppwsz
0x180209271  lea     rcx, [rbp+400h+psz]; psz
0x180209275  call    cs:__imp_SHStrDupW
0x18020927c  nop     dword ptr [rax+rax+00h]
0x180209281  mov     ebx, eax
0x180209283  test    eax, eax
0x180209285  js      short loc_1802092BC
0x180209287  lea     r8, [rbp+400h+TargetPath]; lpTargetPath
0x18020928e  mov     rdx, [rsp+500h+ppwsz]; lpDeviceName
0x180209293  mov     ecx, 9; dwFlags
0x180209298  call    cs:__imp_DefineDosDeviceW
0x18020929f  nop     dword ptr [rax+rax+00h]
0x1802092a4  test    eax, eax
0x1802092a6  jz      short loc_1802092AD
0x1802092a8  mov     ebx, r13d
0x1802092ab  jmp     short loc_1802092B8
0x1802092ad  call    ResultFromKnownLastError
0x1802092b2  mov     ebx, eax
0x1802092b4  test    eax, eax
0x1802092b6  js      short loc_1802092BC
0x1802092b8  mov     [r12], edi
0x1802092bc  mov     rcx, [rsp+500h+ppwsz]; pv
0x1802092c1  call    cs:__imp_CoTaskMemFree
0x1802092c8  nop     dword ptr [rax+rax+00h]
0x1802092cd  test    ebx, ebx
0x1802092cf  jns     short loc_1802092E8
0x1802092d1  xor     r8d, r8d; ProviderSpecificFlags
0x1802092d4  xor     edx, edx; Flags
0x1802092d6  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x1802092db  call    cs:__imp_DetachVirtualDisk
0x1802092e2  nop     dword ptr [rax+rax+00h]
0x1802092e7  nop
0x1802092e8  lea     rcx, [rsp+500h+SecurityDescriptor]
0x1802092ed  call    ??1?$CLocalMemPtr@U_SECURITY_DESCRIPTOR@@@@QEAA@XZ; CLocalMemPtr<_SECURITY_DESCRIPTOR>::~CLocalMemPtr<_SECURITY_DESCRIPTOR>(void)
0x1802092f2  jmp     short loc_180209353
0x1802092f4  cmp     ebx, 80070020h
0x1802092fa  jnz     short loc_180209353
0x1802092fc  mov     r8d, 0D0000h; VirtualDiskAccessMask
0x180209302  cmp     esi, r8d
0x180209305  jz      short loc_180209353
0x180209307  lea     rax, [rsp+500h+VirtualDiskHandle]
0x18020930c  mov     [rsp+500h+Handle], rax; Handle
0x180209311  mov     [rsp+500h+Parameters], r13; Parameters
0x180209316  xor     r9d, r9d; Flags
0x180209319  mov     rdx, [rsp+500h+lpFileName]; Path
0x18020931e  lea     rcx, [rsp+500h+VirtualStorageType]; VirtualStorageType
0x180209323  call    cs:__imp_OpenVirtualDisk
0x18020932a  nop     dword ptr [rax+rax+00h]
0x18020932f  test    eax, eax
0x180209331  jnz     short loc_180209353
0x180209333  lea     r8, [rbp+400h+DiskPath]; DiskPath
0x180209337  lea     rdx, [rsp+500h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18020933c  mov     rcx, [rsp+500h+VirtualDiskHandle]; VirtualDiskHandle
0x180209341  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180209348  nop     dword ptr [rax+rax+00h]
0x18020934d  test    eax, eax
0x18020934f  cmovz   ebx, r14d
0x180209353  mov     rcx, [rsp+500h+VirtualDiskHandle]; hObject
0x180209358  mov     [rsp+500h+VirtualDiskHandle], r13
0x18020935d  lea     rax, [rcx-1]
0x180209361  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180209365  ja      short loc_180209374
0x180209367  call    cs:__imp_CloseHandle
0x18020936e  nop     dword ptr [rax+rax+00h]
0x180209373  nop
0x180209374  mov     rcx, [rsp+500h+lpFileName]; pv
0x180209379  call    cs:__imp_CoTaskMemFree
0x180209380  nop     dword ptr [rax+rax+00h]
0x180209385  mov     eax, ebx
0x180209387  mov     rcx, [rbp+400h+var_40]
0x18020938e  xor     rcx, rsp; StackCookie
0x180209391  call    __security_check_cookie
0x180209396  mov     rbx, [rsp+500h+arg_8]
0x18020939e  add     rsp, 4D0h
0x1802093a5  pop     r15
0x1802093a7  pop     r14
0x1802093a9  pop     r13
0x1802093ab  pop     r12
0x1802093ad  pop     rdi
0x1802093ae  pop     rsi
0x1802093af  pop     rbp
0x1802093b0  retn
```
