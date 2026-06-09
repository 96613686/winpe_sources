# VhdmpiNonPnpCreateDevice

- ea: `0x1400d16c8`
- end: `0x1400d1c91`
- name: `VhdmpiNonPnpCreateDevice`
- size: `1481`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400d1d24`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140023560`
- `0x140035e94`
- `0x14004a8a4`
- `0x14004a8e4`
- `0x14004ae7c`
- `0x14004b264`
- `0x14004b370`
- `0x14004b718`
- `0x14005d7c0`
- `0x1400d1634`
- `0x1400d16c8`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x1400d1a0d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400d1a0d`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400d19b9`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400d19b9`
- `ntoskrnl!IoCreateDevice` at `0x1400d190e`
- `ntoskrnl!IoCreateDevice` at `0x1400d190e`

## string_xrefs

- `0x1400d1baf`: `Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 ) | ( 0x0002 )) << 14) | ((19) << 2) | (0) ))]`
- `0x1400d19f8`: `Return with status 0x%08X [ObSetSecurityObjectByPointer( &Device->DeviceObject, (0x00000004L) | (0x00000010L), Surface->AclBuffer)]`
- `0x1400d1a4c`: `Return with status 0x%08X [IoCreateSymbolicLink(&SymbolicLink, &DevicePath)]`
- `0x1400d1b65`: `Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 )) << 14) | ((11) << 2) | (0) ))]`
- `0x1400d182d`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&SymbolicLink, L"DosDevices", Surface->VirtualDisk->InstanceID)]`
- `0x1400d18ad`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DiskPhysicalPath, L"??", Surface->VirtualDisk->InstanceID)]`
- `0x1400d1956`: `Return with status 0x%08X [IoCreateDevice( VhdmpDriverObject, sizeof(VHD_NONPNP_DEVICE) - sizeof(DEVICE_OBJECT), &DevicePath, 0x00000007, 0x00020000 | Characteristics, 0, wil::out_param(DeviceObject))]`
- `0x1400d17a2`: `VhdmpiNonPnpCreateDevice`
- `0x1400d1bc4`: `VhdmpiNonPnpCreateDevice`
- `0x1400d1c5b`: `VhdmpiNonPnpCreateDevice`
- `0x1400d178d`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DevicePath, L"Device", Surface->VirtualDisk->InstanceID)]`

## pseudocode

```c
__int64 __fastcall VhdmpiNonPnpCreateDevice(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  _QWORD *v3; // r15
  __int64 v6; // rcx
  NTSTATUS v7; // ebx
  int v8; // edx
  int v9; // ecx
  char *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // edx
  int v15; // ecx
  char *v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // r8
  int v21; // edx
  _QWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  char v27; // [rsp+B0h] [rbp-50h] BYREF
  char v28; // [rsp+130h] [rbp+30h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v3 = (_QWORD *)(a2 + 80);
  v6 = (unsigned int)(*(_DWORD *)(v2 + 72) - 1);
  if ( (v6 & *(_QWORD *)(a2 + 72)) != 0 || (v6 & *v3) != 0 )
  {
    v7 = -1073741811;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents(
        (int)"VhdmpiNonPnpCreateDevice",
        239,
        2,
        v21,
        "Return with status 0x%08X: offset %llu, length %llu, sector %d",
        13);
    return (unsigned int)v7;
  }
  *(_QWORD *)&DeviceName.Length = 7471104;
  DeviceName.Buffer = (PWSTR)&v27;
  v7 = VhdmpiNonPnpBuildPath(&DeviceName, L"Device", v2 + 2416);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      return (unsigned int)v7;
    v9 = 245;
    v10 = "Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DevicePath, L\"Device\", Surface->VirtualDisk->InstanceID)]";
    goto LABEL_7;
  }
  v11 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)&v23.Length = 7995392;
  v23.Buffer = (PWSTR)&v28;
  SymbolicLinkName = v23;
  v7 = VhdmpiNonPnpBuildPath(&SymbolicLinkName, L"DosDevices", v11 + 2416);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      return (unsigned int)v7;
    v9 = 249;
    v10 = "Return with status 0x%08X [VhdmpiNonPnpBuildPath(&SymbolicLink, L\"DosDevices\", Surface->VirtualDisk->InstanceID)]";
    goto LABEL_7;
  }
  v12 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)&v23.Length = 7077888;
  v23.Buffer = (PWSTR)(a1 + 168);
  v7 = VhdmpiNonPnpBuildPath(&v23, L"??", v12 + 2416);
  if ( v7 >= 0 )
  {
    v22[0] = 0;
    v13 = wil::out_param<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>>(
            v26,
            v22);
    v7 = IoCreateDevice(
           VhdmpDriverObject,
           0x40u,
           &DeviceName,
           7u,
           (*(_QWORD *)(a1 + 488) != 0 ? 0x100 : 0) | 0x20000,
           0,
           (PDEVICE_OBJECT *)(v13 + 8));
    wil::details::out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>>::~out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>>(v26);
    if ( v7 >= 0 )
    {
      v17 = v22[0];
      *(_QWORD *)(v22[0] + 336LL) = 0x6E646876706E706FLL;
      *(_QWORD *)(v17 + 344) = 0;
      *(_QWORD *)(v17 + 352) = 0;
      *(_QWORD *)(v17 + 360) = 0;
      *(_QWORD *)(v17 + 368) = 0;
      *(_QWORD *)(v17 + 376) = 0;
      *(_BYTE *)(v17 + 384) = 0;
      *(_DWORD *)(v17 + 48) |= 0x10u;
      if ( *(_QWORD *)(a1 + 488) )
      {
        v7 = ObSetSecurityObjectByPointer(v17, 20);
        if ( v7 < 0 )
        {
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
            goto LABEL_43;
          v15 = 283;
          v16 = "Return with status 0x%08X [ObSetSecurityObjectByPointer( &Device->DeviceObject, (0x00000004L) | (0x00000"
                "010L), Surface->AclBuffer)]";
          goto LABEL_42;
        }
      }
      v7 = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
          goto LABEL_43;
        v15 = 286;
        v16 = "Return with status 0x%08X [IoCreateSymbolicLink(&SymbolicLink, &DevicePath)]";
        goto LABEL_42;
      }
      *(_QWORD *)(v17 + 352) = a1;
      *(_QWORD *)(v17 + 360) = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(v17 + 368) = *(_QWORD *)(a2 + 72);
      *(_QWORD *)(v17 + 376) = *v3;
      VhdmpiAcquirePassiveLock(a1 + 280, v18, v19);
      *(struct _UNICODE_STRING *)(a1 + 152) = v23;
      VhdmpiReleasePassiveLock(a1 + 280);
      *(_QWORD *)&v23.Length = v22[0];
      *(_DWORD *)(a1 + 92) = 1;
      v22[0] = 0;
      VhdmpiNonPnpSetSurfaceDevice(a1, &v23);
      *(_DWORD *)(v17 + 48) &= ~0x80u;
      v7 = VhdmpiNonPnpRegisterWithDepends(v17);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
          goto LABEL_43;
        v15 = 312;
        v16 = "Return with status 0x%08X [VhdmpiNonPnpRegisterWithDepends(Device)]";
        goto LABEL_42;
      }
      if ( (*(_DWORD *)a2 & 0x200) == 0 )
        goto LABEL_44;
      v7 = VhdmpiNonPnpNotifyMountManager(&DeviceName, 7159852);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
          goto LABEL_43;
        v15 = 316;
        v16 = "Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001"
              " )) << 14) | ((11) << 2) | (0) ))]";
        goto LABEL_42;
      }
      *(_BYTE *)(v17 + 384) = 1;
      v7 = VhdmpiNonPnpNotifyMountManager(&DeviceName, 7192652);
      if ( v7 >= 0 )
      {
LABEL_44:
        wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(
          v22,
          0);
        return 0;
      }
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
        goto LABEL_43;
      v15 = 322;
      v16 = "Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 )"
            " | ( 0x0002 )) << 14) | ((19) << 2) | (0) ))]";
    }
    else
    {
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
        goto LABEL_43;
      v15 = 270;
      v16 = "Return with status 0x%08X [IoCreateDevice( VhdmpDriverObject, sizeof(VHD_NONPNP_DEVICE) - sizeof(DEVICE_OBJE"
            "CT), &DevicePath, 0x00000007, 0x00020000 | Characteristics, 0, wil::out_param(DeviceObject))]";
    }
LABEL_42:
    TraceEvents((int)"VhdmpiNonPnpCreateDevice", v15, 2, v14, v16, v7);
LABEL_43:
    wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(
      v22,
      0);
    return (unsigned int)v7;
  }
  if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    return (unsigned int)v7;
  v9 = 252;
  v10 = "Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DiskPhysicalPath, L\"??\", Surface->VirtualDisk->InstanceID)]";
LABEL_7:
  TraceEvents((int)"VhdmpiNonPnpCreateDevice", v9, 2, v8, v10, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400d16c8  mov     [rsp-8+arg_10], rbx
0x1400d16cd  push    rbp
0x1400d16ce  push    rsi
0x1400d16cf  push    r12
0x1400d16d1  push    r14
0x1400d16d3  push    r15
0x1400d16d5  lea     rbp, [rsp-0C0h]
0x1400d16dd  sub     rsp, 1C0h
0x1400d16e4  mov     rax, cs:__security_cookie
0x1400d16eb  xor     rax, rsp
0x1400d16ee  mov     [rbp+0E0h+var_30], rax
0x1400d16f5  mov     r8, [rcx+10h]
0x1400d16f9  lea     r15, [rdx+50h]
0x1400d16fd  mov     r14, rcx
0x1400d1700  mov     r12, rdx
0x1400d1703  mov     ecx, [r8+48h]
0x1400d1707  dec     ecx
0x1400d1709  test    [rdx+48h], rcx
0x1400d170d  jnz     loc_1400D1BF7
0x1400d1713  test    [r15], rcx
0x1400d1716  jnz     loc_1400D1BF7
0x1400d171c  xorps   xmm0, xmm0
0x1400d171f  lea     rax, [rbp+0E0h+var_130]
0x1400d1723  movups  xmmword ptr [rsp+1E0h+DeviceName.Length], xmm0
0x1400d1728  mov     [rsp+1E0h+DeviceName.Buffer], rax
0x1400d172d  lea     rdx, aDevice; "Device"
0x1400d1734  mov     eax, 72h ; 'r'
0x1400d1739  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d173e  mov     [rsp+1E0h+DeviceName.MaximumLength], ax
0x1400d1743  add     r8, 970h
0x1400d174a  movaps  xmm0, xmmword ptr [rsp+1E0h+DeviceName.Length]
0x1400d174f  movdqa  xmmword ptr [rsp+1E0h+DeviceName.Length], xmm0
0x1400d1755  call    VhdmpiNonPnpBuildPath
0x1400d175a  mov     ebx, eax
0x1400d175c  test    eax, eax
0x1400d175e  jns     short loc_1400D17B9
0x1400d1760  mov     ecx, cs:dword_140087708
0x1400d1766  cmp     ecx, 2
0x1400d1769  jbe     loc_1400D1C67
0x1400d176f  mov     edx, 80000h
0x1400d1774  lea     rcx, dword_140087708
0x1400d177b  call    _tlgKeywordOn
0x1400d1780  test    al, al
0x1400d1782  jz      loc_1400D1C67
0x1400d1788  mov     ecx, 0F5h
0x1400d178d  lea     rax, aReturnWithStat_4; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1794  mov     r9d, edx; int
0x1400d1797  mov     dword ptr [rsp+1E0h+Exclusive], ebx; char
0x1400d179b  mov     edx, ecx; int
0x1400d179d  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; char *
0x1400d17a2  lea     rcx, aVhdmpinonpnpcr; "VhdmpiNonPnpCreateDevice"
0x1400d17a9  mov     r8d, 2; int
0x1400d17af  call    TraceEvents
0x1400d17b4  jmp     loc_1400D1C67
0x1400d17b9  mov     r8, [r14+10h]
0x1400d17bd  lea     rax, [rbp+0E0h+var_B0]
0x1400d17c1  xorps   xmm0, xmm0
0x1400d17c4  lea     rdx, aDosdevices; "DosDevices"
0x1400d17cb  movups  [rsp+1E0h+var_180], xmm0
0x1400d17d0  mov     qword ptr [rsp+1E0h+var_180+8], rax
0x1400d17d5  lea     rcx, [rbp+0E0h+SymbolicLinkName]
0x1400d17d9  mov     eax, 7Ah ; 'z'
0x1400d17de  mov     esi, 970h
0x1400d17e3  mov     word ptr [rsp+1E0h+var_180+2], ax
0x1400d17e8  add     r8, rsi
0x1400d17eb  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d17f0  movdqa  xmmword ptr [rbp+0E0h+SymbolicLinkName.Length], xmm0
0x1400d17f5  call    VhdmpiNonPnpBuildPath
0x1400d17fa  mov     ebx, eax
0x1400d17fc  test    eax, eax
0x1400d17fe  jns     short loc_1400D1839
0x1400d1800  mov     ecx, cs:dword_140087708
0x1400d1806  cmp     ecx, 2
0x1400d1809  jbe     loc_1400D1C67
0x1400d180f  mov     edx, 80000h
0x1400d1814  lea     rcx, dword_140087708
0x1400d181b  call    _tlgKeywordOn
0x1400d1820  test    al, al
0x1400d1822  jz      loc_1400D1C67
0x1400d1828  mov     ecx, 0F9h
0x1400d182d  lea     rax, aReturnWithStat_2; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1834  jmp     loc_1400D1794
0x1400d1839  mov     r8, [r14+10h]
0x1400d183d  lea     rax, [r14+0A8h]
0x1400d1844  xorps   xmm0, xmm0
0x1400d1847  lea     rdx, asc_140078064; "??"
0x1400d184e  movups  [rsp+1E0h+var_180], xmm0
0x1400d1853  mov     qword ptr [rsp+1E0h+var_180+8], rax
0x1400d1858  lea     rcx, [rsp+1E0h+var_180]
0x1400d185d  mov     eax, 6Ch ; 'l'
0x1400d1862  add     r8, rsi
0x1400d1865  mov     word ptr [rsp+1E0h+var_180+2], ax
0x1400d186a  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d186f  movdqa  [rsp+1E0h+var_180], xmm0
0x1400d1875  call    VhdmpiNonPnpBuildPath
0x1400d187a  mov     ebx, eax
0x1400d187c  test    eax, eax
0x1400d187e  jns     short loc_1400D18B9
0x1400d1880  mov     ecx, cs:dword_140087708
0x1400d1886  cmp     ecx, 2
0x1400d1889  jbe     loc_1400D1C67
0x1400d188f  mov     edx, 80000h
0x1400d1894  lea     rcx, dword_140087708
0x1400d189b  call    _tlgKeywordOn
0x1400d18a0  test    al, al
0x1400d18a2  jz      loc_1400D1C67
0x1400d18a8  mov     ecx, 0FCh
0x1400d18ad  lea     rax, aReturnWithStat_17; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d18b4  jmp     loc_1400D1794
0x1400d18b9  lea     rdx, [rsp+1E0h+var_190]
0x1400d18be  mov     [rsp+1E0h+var_190], 0
0x1400d18c7  lea     rcx, [rbp+0E0h+var_150]
0x1400d18cb  call    ??$out_param@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@wil@@YA?AU?$out_param_t@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@details@0@AEAV?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@Z; wil::out_param<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>(wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>> &)
0x1400d18d0  mov     rcx, [r14+1E8h]
0x1400d18d7  lea     r8, [rsp+1E0h+DeviceName]; DeviceName
0x1400d18dc  add     rax, 8
0x1400d18e0  mov     r9d, 7; DeviceType
0x1400d18e6  neg     rcx
0x1400d18e9  mov     [rsp+1E0h+DeviceObject], rax; DeviceObject
0x1400d18ee  mov     rcx, cs:VhdmpDriverObject; DriverObject
0x1400d18f5  sbb     edx, edx
0x1400d18f7  mov     [rsp+1E0h+Exclusive], 0; Exclusive
0x1400d18fc  and     edx, 100h
0x1400d1902  bts     edx, 11h
0x1400d1906  mov     [rsp+1E0h+DeviceCharacteristics], edx; DeviceCharacteristics
0x1400d190a  lea     edx, [r9+39h]; DeviceExtensionSize
0x1400d190e  call    cs:__imp_IoCreateDevice
0x1400d1915  nop     dword ptr [rax+rax+00h]
0x1400d191a  lea     rcx, [rbp+0E0h+var_150]
0x1400d191e  mov     ebx, eax
0x1400d1920  call    ??1?$out_param_t@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>::~out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>(void)
0x1400d1925  test    ebx, ebx
0x1400d1927  jns     short loc_1400D1962
0x1400d1929  mov     ecx, cs:dword_140087708
0x1400d192f  cmp     ecx, 2
0x1400d1932  jbe     loc_1400D1BD6
0x1400d1938  mov     edx, 80000h
0x1400d193d  lea     rcx, dword_140087708
0x1400d1944  call    _tlgKeywordOn
0x1400d1949  test    al, al
0x1400d194b  jz      loc_1400D1BD6
0x1400d1951  mov     ecx, 10Eh
0x1400d1956  lea     rax, aReturnWithStat_22; "Return with status 0x%08X [IoCreateDevi"...
0x1400d195d  jmp     loc_1400D1BB6
0x1400d1962  mov     rsi, [rsp+1E0h+var_190]
0x1400d1967  mov     rax, 6E646876706E706Fh
0x1400d1971  mov     [rsi+150h], rax
0x1400d1978  xor     eax, eax
0x1400d197a  mov     [rsi+158h], rax
0x1400d1981  mov     [rsi+160h], rax
0x1400d1988  mov     [rsi+168h], rax
0x1400d198f  mov     [rsi+170h], rax
0x1400d1996  mov     [rsi+178h], rax
0x1400d199d  mov     [rsi+180h], al
0x1400d19a3  or      dword ptr [rsi+30h], 10h
0x1400d19a7  mov     r8, [r14+1E8h]
0x1400d19ae  test    r8, r8
0x1400d19b1  jz      short loc_1400D1A04
0x1400d19b3  lea     edx, [rax+14h]
0x1400d19b6  mov     rcx, rsi
0x1400d19b9  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400d19c0  nop     dword ptr [rax+rax+00h]
0x1400d19c5  mov     ebx, eax
0x1400d19c7  test    eax, eax
0x1400d19c9  jns     short loc_1400D1A04
0x1400d19cb  mov     ecx, cs:dword_140087708
0x1400d19d1  cmp     ecx, 2
0x1400d19d4  jbe     loc_1400D1BD6
0x1400d19da  mov     edx, 80000h
0x1400d19df  lea     rcx, dword_140087708
0x1400d19e6  call    _tlgKeywordOn
0x1400d19eb  test    al, al
0x1400d19ed  jz      loc_1400D1BD6
0x1400d19f3  mov     ecx, 11Bh
0x1400d19f8  lea     rax, aReturnWithStat_14; "Return with status 0x%08X [ObSetSecurit"...
0x1400d19ff  jmp     loc_1400D1BB6
0x1400d1a04  lea     rdx, [rsp+1E0h+DeviceName]; DeviceName
0x1400d1a09  lea     rcx, [rbp+0E0h+SymbolicLinkName]; SymbolicLinkName
0x1400d1a0d  call    cs:__imp_IoCreateSymbolicLink
0x1400d1a14  nop     dword ptr [rax+rax+00h]
0x1400d1a19  mov     ebx, eax
0x1400d1a1b  test    eax, eax
0x1400d1a1d  jns     short loc_1400D1A58
0x1400d1a1f  mov     ecx, cs:dword_140087708
0x1400d1a25  cmp     ecx, 2
0x1400d1a28  jbe     loc_1400D1BD6
0x1400d1a2e  mov     edx, 80000h
0x1400d1a33  lea     rcx, dword_140087708
0x1400d1a3a  call    _tlgKeywordOn
0x1400d1a3f  test    al, al
0x1400d1a41  jz      loc_1400D1BD6
0x1400d1a47  mov     ecx, 11Eh
0x1400d1a4c  lea     rax, aReturnWithStat; "Return with status 0x%08X [IoCreateSymb"...
0x1400d1a53  jmp     loc_1400D1BB6
0x1400d1a58  mov     [rsi+160h], r14
0x1400d1a5f  lea     rbx, [r14+118h]
0x1400d1a66  mov     rax, [r14+10h]
0x1400d1a6a  mov     rcx, rbx
0x1400d1a6d  mov     [rsi+168h], rax
0x1400d1a74  mov     rax, [r12+48h]
0x1400d1a79  mov     [rsi+170h], rax
0x1400d1a80  mov     rax, [r15]
0x1400d1a83  mov     [rsi+178h], rax
0x1400d1a8a  call    VhdmpiAcquirePassiveLock
0x1400d1a8f  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d1a94  mov     rcx, rbx
0x1400d1a97  movdqu  xmmword ptr [r14+98h], xmm0
0x1400d1aa0  call    VhdmpiReleasePassiveLock
0x1400d1aa5  mov     rax, [rsp+1E0h+var_190]
0x1400d1aaa  lea     rdx, [rsp+1E0h+var_180]
0x1400d1aaf  mov     rcx, r14
0x1400d1ab2  mov     qword ptr [rsp+1E0h+var_180], rax
0x1400d1ab7  mov     dword ptr [r14+5Ch], 1
0x1400d1abf  mov     [rsp+1E0h+var_190], 0
0x1400d1ac8  call    VhdmpiNonPnpSetSurfaceDevice
0x1400d1acd  btr     dword ptr [rsi+30h], 7
0x1400d1ad2  mov     rcx, rsi
0x1400d1ad5  call    VhdmpiNonPnpRegisterWithDepends
0x1400d1ada  mov     ebx, eax
0x1400d1adc  test    eax, eax
0x1400d1ade  jns     short loc_1400D1B19
0x1400d1ae0  mov     ecx, cs:dword_140087708
0x1400d1ae6  cmp     ecx, 2
0x1400d1ae9  jbe     loc_1400D1BD6
0x1400d1aef  mov     edx, 80000h
0x1400d1af4  lea     rcx, dword_140087708
0x1400d1afb  call    _tlgKeywordOn
0x1400d1b00  test    al, al
0x1400d1b02  jz      loc_1400D1BD6
0x1400d1b08  mov     ecx, 138h
0x1400d1b0d  lea     rax, aReturnWithStat_16; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1b14  jmp     loc_1400D1BB6
0x1400d1b19  test    dword ptr [r12], 200h
0x1400d1b21  jz      loc_1400D1BE7
0x1400d1b27  mov     edx, 6D402Ch
0x1400d1b2c  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d1b31  call    VhdmpiNonPnpNotifyMountManager
0x1400d1b36  mov     ebx, eax
0x1400d1b38  test    eax, eax
0x1400d1b3a  jns     short loc_1400D1B6E
0x1400d1b3c  mov     ecx, cs:dword_140087708
0x1400d1b42  cmp     ecx, 2
0x1400d1b45  jbe     loc_1400D1BD6
0x1400d1b4b  mov     edx, 80000h
0x1400d1b50  lea     rcx, dword_140087708
0x1400d1b57  call    _tlgKeywordOn
0x1400d1b5c  test    al, al
0x1400d1b5e  jz      short loc_1400D1BD6
0x1400d1b60  mov     ecx, 13Ch
0x1400d1b65  lea     rax, aReturnWithStat_13; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1b6c  jmp     short loc_1400D1BB6
0x1400d1b6e  mov     edx, 6DC04Ch
0x1400d1b73  mov     byte ptr [rsi+180h], 1
0x1400d1b7a  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d1b7f  call    VhdmpiNonPnpNotifyMountManager
0x1400d1b84  mov     ebx, eax
0x1400d1b86  test    eax, eax
0x1400d1b88  jns     short loc_1400D1BE7
0x1400d1b8a  mov     ecx, cs:dword_140087708
0x1400d1b90  cmp     ecx, 2
0x1400d1b93  jbe     short loc_1400D1BD6
0x1400d1b95  mov     edx, 80000h
0x1400d1b9a  lea     rcx, dword_140087708
0x1400d1ba1  call    _tlgKeywordOn
0x1400d1ba6  test    al, al
0x1400d1ba8  jz      short loc_1400D1BD6
0x1400d1baa  mov     ecx, 142h
0x1400d1baf  lea     rax, aReturnWithStat_12; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1bb6  mov     r9d, edx; int
0x1400d1bb9  mov     dword ptr [rsp+1E0h+Exclusive], ebx; char
0x1400d1bbd  mov     edx, ecx; int
0x1400d1bbf  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; char *
0x1400d1bc4  lea     rcx, aVhdmpinonpnpcr; "VhdmpiNonPnpCreateDevice"
0x1400d1bcb  mov     r8d, 2; int
0x1400d1bd1  call    TraceEvents
0x1400d1bd6  xor     edx, edx
0x1400d1bd8  lea     rcx, [rsp+1E0h+var_190]
0x1400d1bdd  call    ?reset@?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVICE_OBJECT@@@Z; wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(_DEVICE_OBJECT *)
0x1400d1be2  jmp     loc_1400D1C67
0x1400d1be7  xor     edx, edx
0x1400d1be9  lea     rcx, [rsp+1E0h+var_190]
0x1400d1bee  call    ?reset@?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVICE_OBJECT@@@Z; wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(_DEVICE_OBJECT *)
0x1400d1bf3  xor     eax, eax
0x1400d1bf5  jmp     short loc_1400D1C69
0x1400d1bf7  mov     eax, cs:dword_140087708
0x1400d1bfd  mov     ebx, 0C000000Dh
0x1400d1c02  cmp     eax, 2
0x1400d1c05  jbe     short loc_1400D1C67
0x1400d1c07  mov     edx, 80000h
0x1400d1c0c  lea     rcx, dword_140087708
0x1400d1c13  call    _tlgKeywordOn
0x1400d1c18  test    al, al
0x1400d1c1a  jz      short loc_1400D1C67
0x1400d1c1c  mov     rcx, [r15]
0x1400d1c1f  mov     r10d, 0EFh
0x1400d1c25  mov     rax, [r14+10h]
0x1400d1c29  mov     r9d, edx; int
0x1400d1c2c  mov     r8d, 2; int
0x1400d1c32  mov     edx, r10d; int
0x1400d1c35  mov     eax, [rax+48h]
  ... truncated ...
```
