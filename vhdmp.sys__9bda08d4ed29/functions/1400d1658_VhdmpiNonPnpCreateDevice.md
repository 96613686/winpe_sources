# VhdmpiNonPnpCreateDevice

- ea: `0x1400d1658`
- end: `0x1400d1c21`
- name: `VhdmpiNonPnpCreateDevice`
- size: `1481`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400d1cb4`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x140023980`
- `0x140036284`
- `0x14004ac94`
- `0x14004acd4`
- `0x14004b26c`
- `0x14004b654`
- `0x14004b760`
- `0x14004bb08`
- `0x14005dbb0`
- `0x1400d15c4`
- `0x1400d1658`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x1400d199d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400d199d`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400d1949`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400d1949`
- `ntoskrnl!IoCreateDevice` at `0x1400d189e`
- `ntoskrnl!IoCreateDevice` at `0x1400d189e`

## string_xrefs

- `0x1400d1af5`: `Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 )) << 14) | ((11) << 2) | (0) ))]`
- `0x1400d1b3f`: `Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 ) | ( 0x0002 )) << 14) | ((19) << 2) | (0) ))]`
- `0x1400d18e6`: `Return with status 0x%08X [IoCreateDevice( VhdmpDriverObject, sizeof(VHD_NONPNP_DEVICE) - sizeof(DEVICE_OBJECT), &DevicePath, 0x00000007, 0x00020000 | Characteristics, 0, wil::out_param(DeviceObject))]`
- `0x1400d1988`: `Return with status 0x%08X [ObSetSecurityObjectByPointer( &Device->DeviceObject, (0x00000004L) | (0x00000010L), Surface->AclBuffer)]`
- `0x1400d19dc`: `Return with status 0x%08X [IoCreateSymbolicLink(&SymbolicLink, &DevicePath)]`
- `0x1400d17bd`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&SymbolicLink, L"DosDevices", Surface->VirtualDisk->InstanceID)]`
- `0x1400d183d`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DiskPhysicalPath, L"??", Surface->VirtualDisk->InstanceID)]`
- `0x1400d1732`: `VhdmpiNonPnpCreateDevice`
- `0x1400d1b54`: `VhdmpiNonPnpCreateDevice`
- `0x1400d1beb`: `VhdmpiNonPnpCreateDevice`
- `0x1400d171d`: `Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DevicePath, L"Device", Surface->VirtualDisk->InstanceID)]`

## pseudocode

```c
__int64 __fastcall VhdmpiNonPnpCreateDevice(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  _QWORD *v3; // r15
  __int64 v6; // rcx
  NTSTATUS v7; // ebx
  unsigned int v8; // edx
  unsigned __int16 v9; // cx
  char *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned __int16 v15; // cx
  char *v16; // rax
  __int64 v17; // rsi
  unsigned int v19; // edx
  BOOLEAN Exclusivea[4]; // [rsp+28h] [rbp-D8h]
  __int64 Exclusive; // [rsp+28h] [rbp-D8h]
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      TraceEvents(
        "VhdmpiNonPnpCreateDevice",
        0xEFu,
        2u,
        v19,
        "Return with status 0x%08X: offset %llu, length %llu, sector %d",
        -1073741811,
        *(_QWORD *)(a2 + 72),
        *v3,
        *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL));
    return (unsigned int)v7;
  }
  *(_QWORD *)&DeviceName.Length = 7471104;
  DeviceName.Buffer = (PWSTR)&v27;
  v7 = VhdmpiNonPnpBuildPath(&DeviceName, L"Device", v2 + 2416);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
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
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
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
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
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
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
          goto LABEL_43;
        v15 = 286;
        v16 = "Return with status 0x%08X [IoCreateSymbolicLink(&SymbolicLink, &DevicePath)]";
        goto LABEL_42;
      }
      *(_QWORD *)(v17 + 352) = a1;
      *(_QWORD *)(v17 + 360) = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(v17 + 368) = *(_QWORD *)(a2 + 72);
      *(_QWORD *)(v17 + 376) = *v3;
      VhdmpiAcquirePassiveLock(a1 + 280);
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
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
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
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
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
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
        goto LABEL_43;
      v15 = 322;
      v16 = "Return with status 0x%08X [VhdmpiNonPnpNotifyMountManager(&DevicePath, ( ((0x0000006D) << 16) | ((( 0x0001 )"
            " | ( 0x0002 )) << 14) | ((19) << 2) | (0) ))]";
    }
    else
    {
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
        goto LABEL_43;
      v15 = 270;
      v16 = "Return with status 0x%08X [IoCreateDevice( VhdmpDriverObject, sizeof(VHD_NONPNP_DEVICE) - sizeof(DEVICE_OBJE"
            "CT), &DevicePath, 0x00000007, 0x00020000 | Characteristics, 0, wil::out_param(DeviceObject))]";
    }
LABEL_42:
    LODWORD(Exclusive) = v7;
    TraceEvents("VhdmpiNonPnpCreateDevice", v15, 2u, v14, v16, Exclusive);
LABEL_43:
    wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&void IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(
      v22,
      0);
    return (unsigned int)v7;
  }
  if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    return (unsigned int)v7;
  v9 = 252;
  v10 = "Return with status 0x%08X [VhdmpiNonPnpBuildPath(&DiskPhysicalPath, L\"??\", Surface->VirtualDisk->InstanceID)]";
LABEL_7:
  *(_DWORD *)Exclusivea = v7;
  TraceEvents("VhdmpiNonPnpCreateDevice", v9, 2u, v8, v10, *(_DWORD *)Exclusivea);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400d1658  mov     [rsp-8+arg_10], rbx
0x1400d165d  push    rbp
0x1400d165e  push    rsi
0x1400d165f  push    r12
0x1400d1661  push    r14
0x1400d1663  push    r15
0x1400d1665  lea     rbp, [rsp-0C0h]
0x1400d166d  sub     rsp, 1C0h
0x1400d1674  mov     rax, cs:__security_cookie
0x1400d167b  xor     rax, rsp
0x1400d167e  mov     [rbp+0E0h+var_30], rax
0x1400d1685  mov     r8, [rcx+10h]
0x1400d1689  lea     r15, [rdx+50h]
0x1400d168d  mov     r14, rcx
0x1400d1690  mov     r12, rdx
0x1400d1693  mov     ecx, [r8+48h]
0x1400d1697  dec     ecx
0x1400d1699  test    [rdx+48h], rcx
0x1400d169d  jnz     loc_1400D1B87
0x1400d16a3  test    [r15], rcx
0x1400d16a6  jnz     loc_1400D1B87
0x1400d16ac  xorps   xmm0, xmm0
0x1400d16af  lea     rax, [rbp+0E0h+var_130]
0x1400d16b3  movups  xmmword ptr [rsp+1E0h+DeviceName.Length], xmm0
0x1400d16b8  mov     [rsp+1E0h+DeviceName.Buffer], rax
0x1400d16bd  lea     rdx, aDevice; "Device"
0x1400d16c4  mov     eax, 72h ; 'r'
0x1400d16c9  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d16ce  mov     [rsp+1E0h+DeviceName.MaximumLength], ax
0x1400d16d3  add     r8, 970h
0x1400d16da  movaps  xmm0, xmmword ptr [rsp+1E0h+DeviceName.Length]
0x1400d16df  movdqa  xmmword ptr [rsp+1E0h+DeviceName.Length], xmm0
0x1400d16e5  call    VhdmpiNonPnpBuildPath
0x1400d16ea  mov     ebx, eax
0x1400d16ec  test    eax, eax
0x1400d16ee  jns     short loc_1400D1749
0x1400d16f0  mov     ecx, cs:dword_1400876D0
0x1400d16f6  cmp     ecx, 2
0x1400d16f9  jbe     loc_1400D1BF7
0x1400d16ff  mov     edx, 80000h
0x1400d1704  lea     rcx, dword_1400876D0
0x1400d170b  call    _tlgKeywordOn
0x1400d1710  test    al, al
0x1400d1712  jz      loc_1400D1BF7
0x1400d1718  mov     ecx, 0F5h
0x1400d171d  lea     rax, aReturnWithStat_4; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1724  mov     r9d, edx; int
0x1400d1727  mov     dword ptr [rsp+1E0h+Exclusive], ebx; char
0x1400d172b  mov     edx, ecx; int
0x1400d172d  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; char *
0x1400d1732  lea     rcx, aVhdmpinonpnpcr; "VhdmpiNonPnpCreateDevice"
0x1400d1739  mov     r8d, 2; int
0x1400d173f  call    TraceEvents
0x1400d1744  jmp     loc_1400D1BF7
0x1400d1749  mov     r8, [r14+10h]
0x1400d174d  lea     rax, [rbp+0E0h+var_B0]
0x1400d1751  xorps   xmm0, xmm0
0x1400d1754  lea     rdx, aDosdevices; "DosDevices"
0x1400d175b  movups  [rsp+1E0h+var_180], xmm0
0x1400d1760  mov     qword ptr [rsp+1E0h+var_180+8], rax
0x1400d1765  lea     rcx, [rbp+0E0h+SymbolicLinkName]
0x1400d1769  mov     eax, 7Ah ; 'z'
0x1400d176e  mov     esi, 970h
0x1400d1773  mov     word ptr [rsp+1E0h+var_180+2], ax
0x1400d1778  add     r8, rsi
0x1400d177b  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d1780  movdqa  xmmword ptr [rbp+0E0h+SymbolicLinkName.Length], xmm0
0x1400d1785  call    VhdmpiNonPnpBuildPath
0x1400d178a  mov     ebx, eax
0x1400d178c  test    eax, eax
0x1400d178e  jns     short loc_1400D17C9
0x1400d1790  mov     ecx, cs:dword_1400876D0
0x1400d1796  cmp     ecx, 2
0x1400d1799  jbe     loc_1400D1BF7
0x1400d179f  mov     edx, 80000h
0x1400d17a4  lea     rcx, dword_1400876D0
0x1400d17ab  call    _tlgKeywordOn
0x1400d17b0  test    al, al
0x1400d17b2  jz      loc_1400D1BF7
0x1400d17b8  mov     ecx, 0F9h
0x1400d17bd  lea     rax, aReturnWithStat_2; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d17c4  jmp     loc_1400D1724
0x1400d17c9  mov     r8, [r14+10h]
0x1400d17cd  lea     rax, [r14+0A8h]
0x1400d17d4  xorps   xmm0, xmm0
0x1400d17d7  lea     rdx, asc_1400780D4; "??"
0x1400d17de  movups  [rsp+1E0h+var_180], xmm0
0x1400d17e3  mov     qword ptr [rsp+1E0h+var_180+8], rax
0x1400d17e8  lea     rcx, [rsp+1E0h+var_180]
0x1400d17ed  mov     eax, 6Ch ; 'l'
0x1400d17f2  add     r8, rsi
0x1400d17f5  mov     word ptr [rsp+1E0h+var_180+2], ax
0x1400d17fa  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d17ff  movdqa  [rsp+1E0h+var_180], xmm0
0x1400d1805  call    VhdmpiNonPnpBuildPath
0x1400d180a  mov     ebx, eax
0x1400d180c  test    eax, eax
0x1400d180e  jns     short loc_1400D1849
0x1400d1810  mov     ecx, cs:dword_1400876D0
0x1400d1816  cmp     ecx, 2
0x1400d1819  jbe     loc_1400D1BF7
0x1400d181f  mov     edx, 80000h
0x1400d1824  lea     rcx, dword_1400876D0
0x1400d182b  call    _tlgKeywordOn
0x1400d1830  test    al, al
0x1400d1832  jz      loc_1400D1BF7
0x1400d1838  mov     ecx, 0FCh
0x1400d183d  lea     rax, aReturnWithStat_17; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1844  jmp     loc_1400D1724
0x1400d1849  lea     rdx, [rsp+1E0h+var_190]
0x1400d184e  mov     [rsp+1E0h+var_190], 0
0x1400d1857  lea     rcx, [rbp+0E0h+var_150]
0x1400d185b  call    ??$out_param@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@wil@@YA?AU?$out_param_t@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@details@0@AEAV?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@Z; wil::out_param<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>(wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>> &)
0x1400d1860  mov     rcx, [r14+1E8h]
0x1400d1867  lea     r8, [rsp+1E0h+DeviceName]; DeviceName
0x1400d186c  add     rax, 8
0x1400d1870  mov     r9d, 7; DeviceType
0x1400d1876  neg     rcx
0x1400d1879  mov     [rsp+1E0h+DeviceObject], rax; DeviceObject
0x1400d187e  mov     rcx, cs:VhdmpDriverObject; DriverObject
0x1400d1885  sbb     edx, edx
0x1400d1887  mov     [rsp+1E0h+Exclusive], 0; Exclusive
0x1400d188c  and     edx, 100h
0x1400d1892  bts     edx, 11h
0x1400d1896  mov     [rsp+1E0h+DeviceCharacteristics], edx; DeviceCharacteristics
0x1400d189a  lea     edx, [r9+39h]; DeviceExtensionSize
0x1400d189e  call    cs:__imp_IoCreateDevice
0x1400d18a5  nop     dword ptr [rax+rax+00h]
0x1400d18aa  lea     rcx, [rbp+0E0h+var_150]
0x1400d18ae  mov     ebx, eax
0x1400d18b0  call    ??1?$out_param_t@V?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>::~out_param_t<wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>>(void)
0x1400d18b5  test    ebx, ebx
0x1400d18b7  jns     short loc_1400D18F2
0x1400d18b9  mov     ecx, cs:dword_1400876D0
0x1400d18bf  cmp     ecx, 2
0x1400d18c2  jbe     loc_1400D1B66
0x1400d18c8  mov     edx, 80000h
0x1400d18cd  lea     rcx, dword_1400876D0
0x1400d18d4  call    _tlgKeywordOn
0x1400d18d9  test    al, al
0x1400d18db  jz      loc_1400D1B66
0x1400d18e1  mov     ecx, 10Eh
0x1400d18e6  lea     rax, aReturnWithStat_22; "Return with status 0x%08X [IoCreateDevi"...
0x1400d18ed  jmp     loc_1400D1B46
0x1400d18f2  mov     rsi, [rsp+1E0h+var_190]
0x1400d18f7  mov     rax, 6E646876706E706Fh
0x1400d1901  mov     [rsi+150h], rax
0x1400d1908  xor     eax, eax
0x1400d190a  mov     [rsi+158h], rax
0x1400d1911  mov     [rsi+160h], rax
0x1400d1918  mov     [rsi+168h], rax
0x1400d191f  mov     [rsi+170h], rax
0x1400d1926  mov     [rsi+178h], rax
0x1400d192d  mov     [rsi+180h], al
0x1400d1933  or      dword ptr [rsi+30h], 10h
0x1400d1937  mov     r8, [r14+1E8h]
0x1400d193e  test    r8, r8
0x1400d1941  jz      short loc_1400D1994
0x1400d1943  lea     edx, [rax+14h]
0x1400d1946  mov     rcx, rsi
0x1400d1949  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400d1950  nop     dword ptr [rax+rax+00h]
0x1400d1955  mov     ebx, eax
0x1400d1957  test    eax, eax
0x1400d1959  jns     short loc_1400D1994
0x1400d195b  mov     ecx, cs:dword_1400876D0
0x1400d1961  cmp     ecx, 2
0x1400d1964  jbe     loc_1400D1B66
0x1400d196a  mov     edx, 80000h
0x1400d196f  lea     rcx, dword_1400876D0
0x1400d1976  call    _tlgKeywordOn
0x1400d197b  test    al, al
0x1400d197d  jz      loc_1400D1B66
0x1400d1983  mov     ecx, 11Bh
0x1400d1988  lea     rax, aReturnWithStat_14; "Return with status 0x%08X [ObSetSecurit"...
0x1400d198f  jmp     loc_1400D1B46
0x1400d1994  lea     rdx, [rsp+1E0h+DeviceName]; DeviceName
0x1400d1999  lea     rcx, [rbp+0E0h+SymbolicLinkName]; SymbolicLinkName
0x1400d199d  call    cs:__imp_IoCreateSymbolicLink
0x1400d19a4  nop     dword ptr [rax+rax+00h]
0x1400d19a9  mov     ebx, eax
0x1400d19ab  test    eax, eax
0x1400d19ad  jns     short loc_1400D19E8
0x1400d19af  mov     ecx, cs:dword_1400876D0
0x1400d19b5  cmp     ecx, 2
0x1400d19b8  jbe     loc_1400D1B66
0x1400d19be  mov     edx, 80000h
0x1400d19c3  lea     rcx, dword_1400876D0
0x1400d19ca  call    _tlgKeywordOn
0x1400d19cf  test    al, al
0x1400d19d1  jz      loc_1400D1B66
0x1400d19d7  mov     ecx, 11Eh
0x1400d19dc  lea     rax, aReturnWithStat; "Return with status 0x%08X [IoCreateSymb"...
0x1400d19e3  jmp     loc_1400D1B46
0x1400d19e8  mov     [rsi+160h], r14
0x1400d19ef  lea     rbx, [r14+118h]
0x1400d19f6  mov     rax, [r14+10h]
0x1400d19fa  mov     rcx, rbx
0x1400d19fd  mov     [rsi+168h], rax
0x1400d1a04  mov     rax, [r12+48h]
0x1400d1a09  mov     [rsi+170h], rax
0x1400d1a10  mov     rax, [r15]
0x1400d1a13  mov     [rsi+178h], rax
0x1400d1a1a  call    VhdmpiAcquirePassiveLock
0x1400d1a1f  movaps  xmm0, [rsp+1E0h+var_180]
0x1400d1a24  mov     rcx, rbx
0x1400d1a27  movdqu  xmmword ptr [r14+98h], xmm0
0x1400d1a30  call    VhdmpiReleasePassiveLock
0x1400d1a35  mov     rax, [rsp+1E0h+var_190]
0x1400d1a3a  lea     rdx, [rsp+1E0h+var_180]
0x1400d1a3f  mov     rcx, r14
0x1400d1a42  mov     qword ptr [rsp+1E0h+var_180], rax
0x1400d1a47  mov     dword ptr [r14+5Ch], 1
0x1400d1a4f  mov     [rsp+1E0h+var_190], 0
0x1400d1a58  call    VhdmpiNonPnpSetSurfaceDevice
0x1400d1a5d  btr     dword ptr [rsi+30h], 7
0x1400d1a62  mov     rcx, rsi
0x1400d1a65  call    VhdmpiNonPnpRegisterWithDepends
0x1400d1a6a  mov     ebx, eax
0x1400d1a6c  test    eax, eax
0x1400d1a6e  jns     short loc_1400D1AA9
0x1400d1a70  mov     ecx, cs:dword_1400876D0
0x1400d1a76  cmp     ecx, 2
0x1400d1a79  jbe     loc_1400D1B66
0x1400d1a7f  mov     edx, 80000h
0x1400d1a84  lea     rcx, dword_1400876D0
0x1400d1a8b  call    _tlgKeywordOn
0x1400d1a90  test    al, al
0x1400d1a92  jz      loc_1400D1B66
0x1400d1a98  mov     ecx, 138h
0x1400d1a9d  lea     rax, aReturnWithStat_16; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1aa4  jmp     loc_1400D1B46
0x1400d1aa9  test    dword ptr [r12], 200h
0x1400d1ab1  jz      loc_1400D1B77
0x1400d1ab7  mov     edx, 6D402Ch
0x1400d1abc  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d1ac1  call    VhdmpiNonPnpNotifyMountManager
0x1400d1ac6  mov     ebx, eax
0x1400d1ac8  test    eax, eax
0x1400d1aca  jns     short loc_1400D1AFE
0x1400d1acc  mov     ecx, cs:dword_1400876D0
0x1400d1ad2  cmp     ecx, 2
0x1400d1ad5  jbe     loc_1400D1B66
0x1400d1adb  mov     edx, 80000h
0x1400d1ae0  lea     rcx, dword_1400876D0
0x1400d1ae7  call    _tlgKeywordOn
0x1400d1aec  test    al, al
0x1400d1aee  jz      short loc_1400D1B66
0x1400d1af0  mov     ecx, 13Ch
0x1400d1af5  lea     rax, aReturnWithStat_13; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1afc  jmp     short loc_1400D1B46
0x1400d1afe  mov     edx, 6DC04Ch
0x1400d1b03  mov     byte ptr [rsi+180h], 1
0x1400d1b0a  lea     rcx, [rsp+1E0h+DeviceName]
0x1400d1b0f  call    VhdmpiNonPnpNotifyMountManager
0x1400d1b14  mov     ebx, eax
0x1400d1b16  test    eax, eax
0x1400d1b18  jns     short loc_1400D1B77
0x1400d1b1a  mov     ecx, cs:dword_1400876D0
0x1400d1b20  cmp     ecx, 2
0x1400d1b23  jbe     short loc_1400D1B66
0x1400d1b25  mov     edx, 80000h
0x1400d1b2a  lea     rcx, dword_1400876D0
0x1400d1b31  call    _tlgKeywordOn
0x1400d1b36  test    al, al
0x1400d1b38  jz      short loc_1400D1B66
0x1400d1b3a  mov     ecx, 142h
0x1400d1b3f  lea     rax, aReturnWithStat_12; "Return with status 0x%08X [VhdmpiNonPnp"...
0x1400d1b46  mov     r9d, edx; int
0x1400d1b49  mov     dword ptr [rsp+1E0h+Exclusive], ebx; char
0x1400d1b4d  mov     edx, ecx; int
0x1400d1b4f  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; char *
0x1400d1b54  lea     rcx, aVhdmpinonpnpcr; "VhdmpiNonPnpCreateDevice"
0x1400d1b5b  mov     r8d, 2; int
0x1400d1b61  call    TraceEvents
0x1400d1b66  xor     edx, edx
0x1400d1b68  lea     rcx, [rsp+1E0h+var_190]
0x1400d1b6d  call    ?reset@?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVICE_OBJECT@@@Z; wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(_DEVICE_OBJECT *)
0x1400d1b72  jmp     loc_1400D1BF7
0x1400d1b77  xor     edx, edx
0x1400d1b79  lea     rcx, [rsp+1E0h+var_190]
0x1400d1b7e  call    ?reset@?$unique_ptr@U_DEVICE_OBJECT@@U?$function_deleter@P6AXPEAU_DEVICE_OBJECT@@@Z$1?IoDeleteDevice@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVICE_OBJECT@@@Z; wistd::unique_ptr<_DEVICE_OBJECT,wil::function_deleter<void (*)(_DEVICE_OBJECT *),&IoDeleteDevice(_DEVICE_OBJECT *)>>::reset(_DEVICE_OBJECT *)
0x1400d1b83  xor     eax, eax
0x1400d1b85  jmp     short loc_1400D1BF9
0x1400d1b87  mov     eax, cs:dword_1400876D0
0x1400d1b8d  mov     ebx, 0C000000Dh
0x1400d1b92  cmp     eax, 2
0x1400d1b95  jbe     short loc_1400D1BF7
0x1400d1b97  mov     edx, 80000h
0x1400d1b9c  lea     rcx, dword_1400876D0
0x1400d1ba3  call    _tlgKeywordOn
0x1400d1ba8  test    al, al
0x1400d1baa  jz      short loc_1400D1BF7
0x1400d1bac  mov     rcx, [r15]
0x1400d1baf  mov     r10d, 0EFh
0x1400d1bb5  mov     rax, [r14+10h]
0x1400d1bb9  mov     r9d, edx; int
0x1400d1bbc  mov     r8d, 2; int
0x1400d1bc2  mov     edx, r10d; int
0x1400d1bc5  mov     eax, [rax+48h]
  ... truncated ...
```
