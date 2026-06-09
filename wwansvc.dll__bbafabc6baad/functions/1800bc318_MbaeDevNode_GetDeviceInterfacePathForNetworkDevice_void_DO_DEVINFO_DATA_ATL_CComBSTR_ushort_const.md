# MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice(void *,_DO_DEVINFO_DATA *,ATL::CComBSTR *,ushort const *)

- ea: `0x1800bc318`
- end: `0x1800bc5b2`
- name: `?_GetDeviceInterfacePathForNetworkDevice@MbaeDevNode@@KAJPEAXPEAU_DO_DEVINFO_DATA@@PEAVCComBSTR@ATL@@PEBG@Z`
- size: `666`
- prototype: `static int(void *, struct _DO_DEVINFO_DATA *, struct ATL::CComBSTR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800bbd74`

## callees

- `0x1800085d0`
- `0x180008b30`
- `0x1800094f4`
- `0x180012300`
- `0x180016c50`
- `0x180019d28`
- `0x180019f24`
- `0x180074758`
- `0x1800b9a30`
- `0x1800bc318`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800bc36b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc39e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc36b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc39e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc508`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800bc3c5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800bc420`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800bc3c5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800bc420`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800bc38d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800bc38d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800bc43f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800bc43f`

## string_xrefs

- `0x1800bc340`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc45e`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc4a1`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc4d0`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc535`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc543`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc58b`: `MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice`
- `0x1800bc44d`: ` <---- DeviceInterfacePath does not contain NetworkInterfaceId for memberIndex = %d. DeviceInterfacePath = %ws`

## pseudocode

```c
__int64 __fastcall MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice(
        void *a1,
        struct _DO_DEVINFO_DATA *a2,
        BSTR *a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v8; // rcx
  unsigned int v9; // esi
  void *v10; // rax
  unsigned __int16 *v11; // rbx
  signed int v12; // edi
  signed int v13; // eax
  signed int v14; // eax
  const unsigned __int16 *v15; // r8
  signed int LastError; // eax
  unsigned int v17; // edx
  __int64 v19; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+20h] [rbp-58h]
  size_t Size; // [rsp+30h] [rbp-48h] BYREF
  void *v22; // [rsp+38h] [rbp-40h] BYREF
  _DWORD v23[8]; // [rsp+40h] [rbp-38h] BYREF

  WwanLog::Enter("MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice");
  v8 = *a3;
  v23[0] = 32;
  memset(&v23[1], 0, 28);
  v9 = 0;
  SysFreeString(v8);
  *a3 = 0;
  while ( 1 )
  {
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(a1, a2, &GUID_DEVINTERFACE_NET, v9, v23) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError == 259 )
      {
        if ( v9 == 1 )
        {
          v12 = 0;
          goto LABEL_27;
        }
        v12 = -2147418113;
        LODWORD(v19) = -2147418113;
        WwanLog::Error(
          "MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice",
          0,
          L"DevObjEnumDeviceInterfaces failed for memberIndex = %d, hr = 0x%8x",
          v9,
          v19);
        goto LABEL_20;
      }
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v15 = L"DevObjEnumDeviceInterfaces failed for memberIndex = %d, hr = 0x%8x";
LABEL_25:
      LODWORD(v19) = v12;
      WwanLog::Error("MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice", 0, v15, v9, v19);
      goto LABEL_26;
    }
    SysFreeString(*a3);
    *a3 = 0;
    LODWORD(Size) = 0;
    DevObjGetDeviceInterfaceDetail(a1, v23, 0, 0, &Size, 0);
    if ( !(_DWORD)Size )
    {
      v14 = GetLastError();
      v12 = v14;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      v15 = L"DevObjGetDeviceInterfaceDetail failed for memberIndex = %d, hr = 0x%8x";
      goto LABEL_25;
    }
    v10 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)std::nothrow);
    v22 = v10;
    v11 = (unsigned __int16 *)v10;
    if ( !v10 )
    {
      v12 = -2147024882;
      LODWORD(v19) = -2147024882;
      WwanLog::Error(
        "MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice",
        0,
        L"HeapAlloc failed for memberIndex = %d, hr = 0x%8x",
        v9,
        v19);
      std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v22);
LABEL_29:
      v17 = (unsigned __int16)v12;
      goto LABEL_21;
    }
    memset_0(v10, 0, (unsigned int)Size);
    *(_DWORD *)v11 = 8;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(a1, v23, v11, (unsigned int)Size, 0, 0) )
      break;
    v12 = ATL::CComBSTR::Append((ATL::CComBSTR *)a3, v11 + 2);
    if ( StrStrIW(v11 + 2, a4) )
      goto LABEL_11;
    WwanLog::Verbose(
      "MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice",
      0,
      L" <---- DeviceInterfacePath does not contain NetworkInterfaceId for memberIndex = %d. DeviceInterfacePath = %ws",
      v9,
      *a3);
    std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v22);
    ++v9;
  }
  v13 = GetLastError();
  v12 = v13;
  if ( v13 > 0 )
    v12 = (unsigned __int16)v13 | 0x80070000;
  LODWORD(v20) = v12;
  WwanLog::Error(
    "MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice",
    0,
    L"DevObjGetDeviceInterfaceDetail failed for memberIndex = %d, hr = 0x%8x",
    v9,
    v20);
LABEL_11:
  std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v22);
LABEL_26:
  if ( v12 < 0 )
  {
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      goto LABEL_29;
LABEL_20:
    v17 = v12;
    goto LABEL_21;
  }
LABEL_27:
  v17 = 0;
LABEL_21:
  WwanLog::ExitWithStatus("MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice", v17);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800bc318  push    rbp
0x1800bc31a  push    rbx
0x1800bc31b  push    rsi
0x1800bc31c  push    rdi
0x1800bc31d  push    r12
0x1800bc31f  push    r13
0x1800bc321  push    r14
0x1800bc323  push    r15
0x1800bc325  mov     rbp, rsp
0x1800bc328  sub     rsp, 78h
0x1800bc32c  mov     rax, cs:__security_cookie
0x1800bc333  xor     rax, rsp
0x1800bc336  mov     [rbp+var_18], rax
0x1800bc33a  mov     r15, rcx
0x1800bc33d  mov     r13, r9
0x1800bc340  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc347  mov     r14, r8
0x1800bc34a  mov     r12, rdx
0x1800bc34d  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800bc352  mov     rcx, [r14]; bstrString
0x1800bc355  xorps   xmm0, xmm0
0x1800bc358  xor     edi, edi
0x1800bc35a  mov     [rbp+var_38], 20h ; ' '
0x1800bc361  movups  xmmword ptr [rbp+var_34], xmm0
0x1800bc365  mov     esi, edi
0x1800bc367  movups  xmmword ptr [rbp+var_34+0Ch], xmm0
0x1800bc36b  call    cs:__imp_SysFreeString
0x1800bc371  mov     [r14], rdi
0x1800bc374  lea     rax, [rbp+var_38]
0x1800bc378  mov     r9d, esi
0x1800bc37b  lea     r8, GUID_DEVINTERFACE_NET
0x1800bc382  mov     [rsp+78h+var_58], rax
0x1800bc387  mov     rdx, r12
0x1800bc38a  mov     rcx, r15
0x1800bc38d  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800bc393  test    eax, eax
0x1800bc395  jz      loc_1800BC508
0x1800bc39b  mov     rcx, [r14]; bstrString
0x1800bc39e  call    cs:__imp_SysFreeString
0x1800bc3a4  lea     rax, [rbp+Size]
0x1800bc3a8  mov     [rsp+78h+var_50], rdi
0x1800bc3ad  xor     r9d, r9d
0x1800bc3b0  mov     [rsp+78h+var_58], rax
0x1800bc3b5  xor     r8d, r8d
0x1800bc3b8  mov     [r14], rdi
0x1800bc3bb  lea     rdx, [rbp+var_38]
0x1800bc3bf  mov     dword ptr [rbp+Size], edi
0x1800bc3c2  mov     rcx, r15
0x1800bc3c5  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800bc3cb  mov     eax, dword ptr [rbp+Size]
0x1800bc3ce  test    eax, eax
0x1800bc3d0  jz      loc_1800BC4EA
0x1800bc3d6  mov     ecx, eax; unsigned __int64
0x1800bc3d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bc3df  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bc3e4  mov     [rbp+var_40], rax
0x1800bc3e8  mov     rbx, rax
0x1800bc3eb  test    rax, rax
0x1800bc3ee  jz      loc_1800BC4BB
0x1800bc3f4  mov     r8d, dword ptr [rbp+Size]; Size
0x1800bc3f8  xor     edx, edx; Val
0x1800bc3fa  mov     rcx, rax; void *
0x1800bc3fd  call    memset_0
0x1800bc402  mov     dword ptr [rbx], 8
0x1800bc408  lea     rdx, [rbp+var_38]
0x1800bc40c  mov     r9d, dword ptr [rbp+Size]
0x1800bc410  mov     r8, rbx
0x1800bc413  mov     rcx, r15
0x1800bc416  mov     [rsp+78h+var_50], rdi
0x1800bc41b  mov     [rsp+78h+var_58], rdi
0x1800bc420  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800bc426  test    eax, eax
0x1800bc428  jz      short loc_1800BC47C
0x1800bc42a  lea     rdx, [rbx+4]; unsigned __int16 *
0x1800bc42e  mov     rcx, r14; this
0x1800bc431  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800bc436  mov     rdx, r13; pszSrch
0x1800bc439  lea     rcx, [rbx+4]; pszFirst
0x1800bc43d  mov     edi, eax
0x1800bc43f  call    cs:__imp_StrStrIW
0x1800bc445  test    rax, rax
0x1800bc448  jnz     short loc_1800BC4AD
0x1800bc44a  mov     rax, [r14]
0x1800bc44d  lea     r8, aDeviceinterfac; " <---- DeviceInterfacePath does not con"...
0x1800bc454  mov     r9d, esi
0x1800bc457  mov     [rsp+78h+var_58], rax
0x1800bc45c  xor     edx, edx; struct _GUID *
0x1800bc45e  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc465  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800bc46a  lea     rcx, [rbp+var_40]
0x1800bc46e  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x1800bc473  inc     esi
0x1800bc475  xor     edi, edi
0x1800bc477  jmp     loc_1800BC374
0x1800bc47c  call    cs:__imp_GetLastError
0x1800bc482  mov     edi, eax
0x1800bc484  test    eax, eax
0x1800bc486  jle     short loc_1800BC491
0x1800bc488  movzx   edi, ax
0x1800bc48b  or      edi, 80070000h
0x1800bc491  mov     r9d, esi
0x1800bc494  mov     dword ptr [rsp+78h+var_58], edi
0x1800bc498  lea     r8, aDevobjgetdevic; "DevObjGetDeviceInterfaceDetail failed f"...
0x1800bc49f  xor     edx, edx; struct _GUID *
0x1800bc4a1  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc4a8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc4ad  lea     rcx, [rbp+var_40]
0x1800bc4b1  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x1800bc4b6  jmp     loc_1800BC597
0x1800bc4bb  mov     edi, 8007000Eh
0x1800bc4c0  lea     r8, aHeapallocFaile; "HeapAlloc failed for memberIndex = %d, "...
0x1800bc4c7  mov     r9d, esi
0x1800bc4ca  mov     dword ptr [rsp+78h+var_58], edi
0x1800bc4ce  xor     edx, edx; struct _GUID *
0x1800bc4d0  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc4d7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc4dc  lea     rcx, [rbp+var_40]
0x1800bc4e0  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x1800bc4e5  jmp     loc_1800BC5AD
0x1800bc4ea  call    cs:__imp_GetLastError
0x1800bc4f0  mov     edi, eax
0x1800bc4f2  test    eax, eax
0x1800bc4f4  jle     short loc_1800BC4FF
0x1800bc4f6  movzx   edi, ax
0x1800bc4f9  or      edi, 80070000h
0x1800bc4ff  lea     r8, aDevobjgetdevic; "DevObjGetDeviceInterfaceDetail failed f"...
0x1800bc506  jmp     short loc_1800BC582
0x1800bc508  call    cs:__imp_GetLastError
0x1800bc50e  mov     edi, eax
0x1800bc510  cmp     eax, 103h
0x1800bc515  jnz     short loc_1800BC56E
0x1800bc517  cmp     esi, 1
0x1800bc51a  jnz     short loc_1800BC520
0x1800bc51c  xor     edi, edi
0x1800bc51e  jmp     short loc_1800BC59B
0x1800bc520  mov     edi, 8000FFFFh
0x1800bc525  lea     r8, aDevobjenumdevi_0; "DevObjEnumDeviceInterfaces failed for m"...
0x1800bc52c  mov     r9d, esi
0x1800bc52f  mov     dword ptr [rsp+78h+var_58], edi
0x1800bc533  xor     edx, edx; struct _GUID *
0x1800bc535  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc53c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc541  mov     edx, edi; unsigned int
0x1800bc543  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc54a  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800bc54f  mov     eax, edi
0x1800bc551  mov     rcx, [rbp+var_18]
0x1800bc555  xor     rcx, rsp; StackCookie
0x1800bc558  call    __security_check_cookie
0x1800bc55d  add     rsp, 78h
0x1800bc561  pop     r15
0x1800bc563  pop     r14
0x1800bc565  pop     r13
0x1800bc567  pop     r12
0x1800bc569  pop     rdi
0x1800bc56a  pop     rsi
0x1800bc56b  pop     rbx
0x1800bc56c  pop     rbp
0x1800bc56d  retn
0x1800bc56e  test    eax, eax
0x1800bc570  jle     short loc_1800BC57B
0x1800bc572  movzx   edi, ax
0x1800bc575  or      edi, 80070000h
0x1800bc57b  lea     r8, aDevobjenumdevi_0; "DevObjEnumDeviceInterfaces failed for m"...
0x1800bc582  mov     r9d, esi
0x1800bc585  mov     dword ptr [rsp+78h+var_58], edi
0x1800bc589  xor     edx, edx; struct _GUID *
0x1800bc58b  lea     rcx, aMbaedevnodeGet_1; "MbaeDevNode::_GetDeviceInterfacePathFor"...
0x1800bc592  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc597  test    edi, edi
0x1800bc599  js      short loc_1800BC59F
0x1800bc59b  xor     edx, edx
0x1800bc59d  jmp     short loc_1800BC543
0x1800bc59f  mov     eax, edi
0x1800bc5a1  and     eax, 1FFF0000h
0x1800bc5a6  cmp     eax, 70000h
0x1800bc5ab  jnz     short loc_1800BC541
0x1800bc5ad  movzx   edx, di
0x1800bc5b0  jmp     short loc_1800BC543
```
