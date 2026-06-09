# CWorkspace::CreateShortcut(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002a9a4`
- end: `0x18002b19f`
- name: `?CreateShortcut@CWorkspace@@IEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0000@Z`
- size: `2043`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b1a8`
- `0x18002cab8`

## callees

- `0x1800054c4`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18002a9a4`
- `0x180045c38`
- `0x180046358`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002ae76`
- `msvcrt!memcpy_s` at `0x18002ae76`
- `ole32!PropVariantClear` at `0x18002b10b`
- `ole32!PropVariantClear` at `0x18002b10b`
- `ole32!CoTaskMemAlloc` at `0x18002ae54`
- `ole32!CoTaskMemAlloc` at `0x18002ae54`
- `ole32!CoCreateInstance` at `0x18002aa29`
- `ole32!CoCreateInstance` at `0x18002aa29`

## string_xrefs

- `0x18002aa66`: ` CoCreateInstance CLSID_ShellLink failed`
- `0x18002abdf`: `TSWPathQuoteSpaces failed`
- `0x18002ace3`: `TSWPathQuoteSpaces failed`
- `0x18002ac5e`: `IShellLink::SetPath failed`
- `0x18002ad5f`: `IShellLink::SetArguments failed`
- `0x18002ade4`: `IShellLink::SetIconLocation failed`
- `0x18002ae18`: `%temp%`
- `0x18002afd0`: `IPropertyStore::Commit failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWorkspace::CreateShortcut(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  HRESULT v9; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  const unsigned __int16 *v13; // rax
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // eax
  const unsigned __int16 *v17; // rax
  unsigned int v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // eax
  LPVOID v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  const void *v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rbx
  void *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  const unsigned __int16 *v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rbx
  __int64 v34; // rax
  unsigned int v35; // eax
  HRESULT v36; // r14d
  unsigned int v37; // eax
  LPVOID ppv; // [rsp+38h] [rbp-4B0h] BYREF
  HRESULT v40; // [rsp+40h] [rbp-4A8h]
  __int64 v41; // [rsp+48h] [rbp-4A0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-498h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-490h] BYREF
  __int64 v44; // [rsp+68h] [rbp-480h]
  __int64 v45; // [rsp+70h] [rbp-478h]
  wchar_t Destination[264]; // [rsp+80h] [rbp-468h] BYREF
  wchar_t v47[268]; // [rsp+290h] [rbp-258h] BYREF

  v45 = -2;
  ppv = 0;
  v42 = 0;
  v41 = 0;
  *(_OWORD *)pvar = 0;
  v44 = 0;
  v9 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &ppv);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        179,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)" CoCreateInstance CLSID_ShellLink failed",
        v9,
        v9);
    }
    goto LABEL_72;
  }
  v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_0000010b_0000_0000_c000_000000000046,
         &v42);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v11,
        (__int64)"QueryInterface IPersistFile failed",
        v9,
        v9);
    }
    goto LABEL_72;
  }
  v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v41);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        181,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v12,
        (__int64)"QueryInterface IPropertyStore failed",
        v9,
        v9);
    }
    goto LABEL_72;
  }
  v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
  v9 = TSWPathQuoteSpaces(Destination, v14, v13);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v15,
        (__int64)"TSWPathQuoteSpaces failed",
        v9,
        v9);
    }
    goto LABEL_72;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)ppv + 160LL))(ppv, Destination);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        183,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v16,
        (__int64)"IShellLink::SetPath failed",
        v9,
        v9);
    }
    goto LABEL_72;
  }
  if ( *(_QWORD *)(a3 + 16) )
  {
    v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v9 = TSWPathQuoteSpaces(v47, v18, v17);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          184,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v19,
          (__int64)"TSWPathQuoteSpaces failed",
          v9,
          v9);
      }
      goto LABEL_72;
    }
    v9 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)ppv + 88LL))(ppv, v47);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          185,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v20,
          (__int64)"IShellLink::SetArguments failed",
          v9,
          v9);
      }
      goto LABEL_72;
    }
  }
  v21 = ppv;
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
  (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v21 + 136LL))(v21, v22, 0);
  (*(void (**)(LPVOID, const wchar_t *, ...))(*(_QWORD *)ppv + 72LL))(ppv, L"%temp%");
  v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  v24 = (const void *)v23;
  if ( v23 )
  {
    v40 = 0;
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(v23 + 2 * v25) );
    v26 = 2 * v25 + 2;
    v27 = CoTaskMemAlloc(v26);
    pvar[1] = v27;
    if ( v27 )
    {
      v9 = 0;
      v40 = 0;
      memcpy_s(v27, v26, v24, v26);
      LOWORD(pvar[0]) = 31;
      goto LABEL_45;
    }
    v9 = -2147024882;
  }
  else
  {
    v9 = -2147024809;
  }
  v40 = v9;
  *(_OWORD *)pvar = 0;
  v44 = 0;
LABEL_45:
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v41 + 48LL))(
           v41,
           &PKEY_AppUserModel_ID,
           pvar);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 56LL))(v41);
      if ( v9 >= 0 )
      {
        v31 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        if ( (unsigned int)IsPathCanonical(v31) )
        {
          v33 = v42;
          v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v33 + 48LL))(v33, v34, 1);
          if ( v9 >= 0 )
          {
            v9 = 0;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v35 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              192,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v35,
              (__int64)"IpersistFile::Save failed",
              v9,
              v9);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v32 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              191,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v32,
              -2147220989);
          }
          v9 = -2147220989;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          190,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v30,
          (__int64)"IPropertyStore::Commit failed",
          v9,
          v9);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        189,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v29,
        (__int64)"IPropertyStore::SetValue(AppID) failed",
        v9,
        v9);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      188,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v28,
      (__int64)"InitPropVariantFromString failed",
      v9,
      v9);
  }
LABEL_72:
  v36 = PropVariantClear(pvar);
  if ( v36 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v37 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v37, v36);
  }
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v41);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v42);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a9a4  push    rbx
0x18002a9a6  push    rsi
0x18002a9a7  push    rdi
0x18002a9a8  push    r12
0x18002a9aa  push    r13
0x18002a9ac  push    r14
0x18002a9ae  push    r15
0x18002a9b0  sub     rsp, 4B0h
0x18002a9b7  mov     [rsp+4E8h+var_478], 0FFFFFFFFFFFFFFFEh
0x18002a9c0  mov     rax, cs:__security_cookie
0x18002a9c7  xor     rax, rsp
0x18002a9ca  mov     [rsp+4E8h+var_40], rax
0x18002a9d2  mov     r12, r9
0x18002a9d5  mov     rbx, r8
0x18002a9d8  mov     r13, rdx
0x18002a9db  mov     r14, [rsp+4E8h+arg_20]
0x18002a9e3  mov     r15, [rsp+4E8h+arg_28]
0x18002a9eb  xor     esi, esi
0x18002a9ed  mov     [rsp+4E8h+var_4B0], rsi
0x18002a9f2  mov     [rsp+4E8h+var_498], rsi
0x18002a9f7  mov     [rsp+4E8h+var_4A0], rsi
0x18002a9fc  xorps   xmm0, xmm0
0x18002a9ff  xor     eax, eax
0x18002aa01  movups  xmmword ptr [rsp+4E8h+pvar], xmm0
0x18002aa06  mov     [rsp+4E8h+var_480], rax
0x18002aa0b  lea     rax, [rsp+4E8h+var_4B0]
0x18002aa10  mov     [rsp+4E8h+ppv], rax; ppv
0x18002aa15  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18002aa1c  xor     edx, edx; pUnkOuter
0x18002aa1e  lea     r8d, [rsi+1]; dwClsContext
0x18002aa22  lea     rcx, CLSID_ShellLink; rclsid
0x18002aa29  call    cs:__imp_CoCreateInstance
0x18002aa2f  mov     edi, eax
0x18002aa31  mov     [rsp+4E8h+var_4B8], eax
0x18002aa35  test    eax, eax
0x18002aa37  jns     short loc_18002AA92
0x18002aa39  lea     rbx, WPP_GLOBAL_Control
0x18002aa40  mov     rax, cs:WPP_GLOBAL_Control
0x18002aa47  cmp     rax, rbx
0x18002aa4a  jz      short loc_18002AA8D
0x18002aa4c  test    byte ptr [rax+1Ch], 8
0x18002aa50  jz      short loc_18002AA8D
0x18002aa52  cmp     byte ptr [rax+19h], 2
0x18002aa56  jb      short loc_18002AA8D
0x18002aa58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002aa5d  mov     edx, 0B3h
0x18002aa62  mov     [rsp+4E8h+var_4C0], edi
0x18002aa66  lea     rcx, aCocreateinstan_4; " CoCreateInstance CLSID_ShellLink faile"...
0x18002aa6d  mov     [rsp+4E8h+ppv], rcx
0x18002aa72  mov     r9d, eax
0x18002aa75  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002aa7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa83  mov     rcx, [rcx+10h]
0x18002aa87  call    WPP_SF_DsD
0x18002aa8c  nop
0x18002aa8d  jmp     loc_18002B106
0x18002aa92  mov     rcx, [rsp+4E8h+var_4B0]
0x18002aa97  mov     rax, [rcx]
0x18002aa9a  lea     r8, [rsp+4E8h+var_498]
0x18002aa9f  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18002aaa6  mov     rax, [rax]
0x18002aaa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaae  mov     edi, eax
0x18002aab0  mov     [rsp+4E8h+var_4B8], eax
0x18002aab4  test    eax, eax
0x18002aab6  jns     short loc_18002AB11
0x18002aab8  lea     rbx, WPP_GLOBAL_Control
0x18002aabf  mov     rax, cs:WPP_GLOBAL_Control
0x18002aac6  cmp     rax, rbx
0x18002aac9  jz      short loc_18002AB0C
0x18002aacb  test    byte ptr [rax+1Ch], 8
0x18002aacf  jz      short loc_18002AB0C
0x18002aad1  cmp     byte ptr [rax+19h], 2
0x18002aad5  jb      short loc_18002AB0C
0x18002aad7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002aadc  mov     edx, 0B4h
0x18002aae1  mov     [rsp+4E8h+var_4C0], edi
0x18002aae5  lea     rcx, aQueryinterface_5; "QueryInterface IPersistFile failed"
0x18002aaec  mov     [rsp+4E8h+ppv], rcx
0x18002aaf1  mov     r9d, eax
0x18002aaf4  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002aafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab02  mov     rcx, [rcx+10h]
0x18002ab06  call    WPP_SF_DsD
0x18002ab0b  nop
0x18002ab0c  jmp     loc_18002B106
0x18002ab11  mov     rcx, [rsp+4E8h+var_4B0]
0x18002ab16  mov     rax, [rcx]
0x18002ab19  lea     r8, [rsp+4E8h+var_4A0]
0x18002ab1e  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002ab25  mov     rax, [rax]
0x18002ab28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab2d  mov     edi, eax
0x18002ab2f  mov     [rsp+4E8h+var_4B8], eax
0x18002ab33  test    eax, eax
0x18002ab35  jns     short loc_18002AB90
0x18002ab37  lea     rbx, WPP_GLOBAL_Control
0x18002ab3e  mov     rax, cs:WPP_GLOBAL_Control
0x18002ab45  cmp     rax, rbx
0x18002ab48  jz      short loc_18002AB8B
0x18002ab4a  test    byte ptr [rax+1Ch], 8
0x18002ab4e  jz      short loc_18002AB8B
0x18002ab50  cmp     byte ptr [rax+19h], 2
0x18002ab54  jb      short loc_18002AB8B
0x18002ab56  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ab5b  mov     edx, 0B5h
0x18002ab60  mov     [rsp+4E8h+var_4C0], edi
0x18002ab64  lea     rcx, aQueryinterface_0; "QueryInterface IPropertyStore failed"
0x18002ab6b  mov     [rsp+4E8h+ppv], rcx
0x18002ab70  mov     r9d, eax
0x18002ab73  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002ab7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab81  mov     rcx, [rcx+10h]
0x18002ab85  call    WPP_SF_DsD
0x18002ab8a  nop
0x18002ab8b  jmp     loc_18002B106
0x18002ab90  mov     rcx, r14
0x18002ab93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ab98  mov     r8, rax; unsigned __int16 *
0x18002ab9b  lea     rcx, [rsp+4E8h+Destination]; Destination
0x18002aba3  call    ?TSWPathQuoteSpaces@@YAJPEAGIPEBG@Z; TSWPathQuoteSpaces(ushort *,uint,ushort const *)
0x18002aba8  mov     edi, eax
0x18002abaa  mov     [rsp+4E8h+var_4B8], eax
0x18002abae  test    eax, eax
0x18002abb0  jns     short loc_18002AC0B
0x18002abb2  lea     rbx, WPP_GLOBAL_Control
0x18002abb9  mov     rax, cs:WPP_GLOBAL_Control
0x18002abc0  cmp     rax, rbx
0x18002abc3  jz      short loc_18002AC06
0x18002abc5  test    byte ptr [rax+1Ch], 8
0x18002abc9  jz      short loc_18002AC06
0x18002abcb  cmp     byte ptr [rax+19h], 2
0x18002abcf  jb      short loc_18002AC06
0x18002abd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002abd6  mov     edx, 0B6h
0x18002abdb  mov     [rsp+4E8h+var_4C0], edi
0x18002abdf  lea     rcx, aTswpathquotesp; "TSWPathQuoteSpaces failed"
0x18002abe6  mov     [rsp+4E8h+ppv], rcx
0x18002abeb  mov     r9d, eax
0x18002abee  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002abf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abfc  mov     rcx, [rcx+10h]
0x18002ac00  call    WPP_SF_DsD
0x18002ac05  nop
0x18002ac06  jmp     loc_18002B106
0x18002ac0b  mov     rcx, [rsp+4E8h+var_4B0]
0x18002ac10  mov     rax, [rcx]
0x18002ac13  lea     rdx, [rsp+4E8h+Destination]
0x18002ac1b  mov     rax, [rax+0A0h]
0x18002ac22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac27  mov     edi, eax
0x18002ac29  mov     [rsp+4E8h+var_4B8], eax
0x18002ac2d  test    eax, eax
0x18002ac2f  jns     short loc_18002AC8A
0x18002ac31  lea     rbx, WPP_GLOBAL_Control
0x18002ac38  mov     rax, cs:WPP_GLOBAL_Control
0x18002ac3f  cmp     rax, rbx
0x18002ac42  jz      short loc_18002AC85
0x18002ac44  test    byte ptr [rax+1Ch], 8
0x18002ac48  jz      short loc_18002AC85
0x18002ac4a  cmp     byte ptr [rax+19h], 2
0x18002ac4e  jb      short loc_18002AC85
0x18002ac50  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ac55  mov     edx, 0B7h
0x18002ac5a  mov     [rsp+4E8h+var_4C0], edi
0x18002ac5e  lea     rcx, aIshelllinkSetp; "IShellLink::SetPath failed"
0x18002ac65  mov     [rsp+4E8h+ppv], rcx
0x18002ac6a  mov     r9d, eax
0x18002ac6d  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002ac74  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac7b  mov     rcx, [rcx+10h]
0x18002ac7f  call    WPP_SF_DsD
0x18002ac84  nop
0x18002ac85  jmp     loc_18002B106
0x18002ac8a  cmp     [rbx+10h], rsi
0x18002ac8e  jbe     loc_18002AD8B
0x18002ac94  mov     rcx, rbx
0x18002ac97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ac9c  mov     r8, rax; unsigned __int16 *
0x18002ac9f  lea     rcx, [rsp+4E8h+var_258]; Destination
0x18002aca7  call    ?TSWPathQuoteSpaces@@YAJPEAGIPEBG@Z; TSWPathQuoteSpaces(ushort *,uint,ushort const *)
0x18002acac  mov     edi, eax
0x18002acae  mov     [rsp+4E8h+var_4B8], eax
0x18002acb2  test    eax, eax
0x18002acb4  jns     short loc_18002AD0F
0x18002acb6  lea     rbx, WPP_GLOBAL_Control
0x18002acbd  mov     rax, cs:WPP_GLOBAL_Control
0x18002acc4  cmp     rax, rbx
0x18002acc7  jz      short loc_18002AD0A
0x18002acc9  test    byte ptr [rax+1Ch], 8
0x18002accd  jz      short loc_18002AD0A
0x18002accf  cmp     byte ptr [rax+19h], 2
0x18002acd3  jb      short loc_18002AD0A
0x18002acd5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002acda  mov     edx, 0B8h
0x18002acdf  mov     [rsp+4E8h+var_4C0], edi
0x18002ace3  lea     rcx, aTswpathquotesp; "TSWPathQuoteSpaces failed"
0x18002acea  mov     [rsp+4E8h+ppv], rcx
0x18002acef  mov     r9d, eax
0x18002acf2  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002acf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad00  mov     rcx, [rcx+10h]
0x18002ad04  call    WPP_SF_DsD
0x18002ad09  nop
0x18002ad0a  jmp     loc_18002B106
0x18002ad0f  mov     rcx, [rsp+4E8h+var_4B0]
0x18002ad14  mov     rax, [rcx]
0x18002ad17  lea     rdx, [rsp+4E8h+var_258]
0x18002ad1f  mov     rax, [rax+58h]
0x18002ad23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad28  mov     edi, eax
0x18002ad2a  mov     [rsp+4E8h+var_4B8], eax
0x18002ad2e  test    eax, eax
0x18002ad30  jns     short loc_18002AD8B
0x18002ad32  lea     rbx, WPP_GLOBAL_Control
0x18002ad39  mov     rax, cs:WPP_GLOBAL_Control
0x18002ad40  cmp     rax, rbx
0x18002ad43  jz      short loc_18002AD86
0x18002ad45  test    byte ptr [rax+1Ch], 8
0x18002ad49  jz      short loc_18002AD86
0x18002ad4b  cmp     byte ptr [rax+19h], 2
0x18002ad4f  jb      short loc_18002AD86
0x18002ad51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ad56  mov     edx, 0B9h
0x18002ad5b  mov     [rsp+4E8h+var_4C0], edi
0x18002ad5f  lea     rcx, aIshelllinkSeta; "IShellLink::SetArguments failed"
0x18002ad66  mov     [rsp+4E8h+ppv], rcx
0x18002ad6b  mov     r9d, eax
0x18002ad6e  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002ad75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad7c  mov     rcx, [rcx+10h]
0x18002ad80  call    WPP_SF_DsD
0x18002ad85  nop
0x18002ad86  jmp     loc_18002B106
0x18002ad8b  mov     rbx, [rsp+4E8h+var_4B0]
0x18002ad90  mov     rcx, r12
0x18002ad93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ad98  mov     rcx, [rbx]
0x18002ad9b  mov     r9, [rcx+88h]
0x18002ada2  xor     r8d, r8d
0x18002ada5  mov     rdx, rax
0x18002ada8  mov     rcx, rbx
0x18002adab  mov     rax, r9
0x18002adae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb3  test    edi, edi
0x18002adb5  jns     short loc_18002AE10
0x18002adb7  lea     rbx, WPP_GLOBAL_Control
0x18002adbe  mov     rax, cs:WPP_GLOBAL_Control
0x18002adc5  cmp     rax, rbx
0x18002adc8  jz      short loc_18002AE0B
0x18002adca  test    byte ptr [rax+1Ch], 8
0x18002adce  jz      short loc_18002AE0B
0x18002add0  cmp     byte ptr [rax+19h], 2
0x18002add4  jb      short loc_18002AE0B
0x18002add6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002addb  mov     edx, 0BAh
0x18002ade0  mov     [rsp+4E8h+var_4C0], edi
0x18002ade4  lea     rcx, aIshelllinkSeti; "IShellLink::SetIconLocation failed"
0x18002adeb  mov     [rsp+4E8h+ppv], rcx
0x18002adf0  mov     r9d, eax
0x18002adf3  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002adfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae01  mov     rcx, [rcx+10h]
0x18002ae05  call    WPP_SF_DsD
0x18002ae0a  nop
0x18002ae0b  jmp     loc_18002B106
0x18002ae10  mov     rcx, [rsp+4E8h+var_4B0]
0x18002ae15  mov     rax, [rcx]
0x18002ae18  lea     rdx, aTemp; "%temp%"
0x18002ae1f  mov     rax, [rax+48h]
0x18002ae23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae28  mov     rcx, r15
0x18002ae2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ae30  mov     r14, rax
0x18002ae33  test    rax, rax
0x18002ae36  jz      short loc_18002AE8F
0x18002ae38  mov     [rsp+4E8h+var_4A8], esi
0x18002ae3c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002ae40  inc     rcx
0x18002ae43  cmp     [rax+rcx*2], si
0x18002ae47  jnz     short loc_18002AE40
0x18002ae49  lea     rbx, ds:2[rcx*2]
0x18002ae51  mov     rcx, rbx; cb
0x18002ae54  call    cs:__imp_CoTaskMemAlloc
0x18002ae5a  mov     [rsp+4E8h+pvar+8], rax
0x18002ae5f  test    rax, rax
0x18002ae62  jz      short loc_18002AE88
0x18002ae64  mov     edi, esi
0x18002ae66  mov     [rsp+4E8h+var_4A8], esi
0x18002ae6a  mov     r9, rbx; SourceSize
0x18002ae6d  mov     r8, r14; Source
0x18002ae70  mov     rdx, rbx; DestinationSize
0x18002ae73  mov     rcx, rax; Destination
0x18002ae76  call    cs:__imp_memcpy_s
0x18002ae7c  mov     eax, 1Fh
0x18002ae81  mov     word ptr [rsp+4E8h+pvar], ax
0x18002ae86  jmp     short loc_18002AEA7
0x18002ae88  mov     edi, 8007000Eh
0x18002ae8d  jmp     short loc_18002AE94
0x18002ae8f  mov     edi, 80070057h
  ... truncated ...
```
