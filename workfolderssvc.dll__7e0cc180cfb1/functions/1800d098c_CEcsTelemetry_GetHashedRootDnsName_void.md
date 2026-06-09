# CEcsTelemetry::GetHashedRootDnsName(void)

- ea: `0x1800d098c`
- end: `0x1800d0d95`
- name: `?GetHashedRootDnsName@CEcsTelemetry@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007b724`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180009158`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180015150`
- `0x180015904`
- `0x180023c90`
- `0x180031910`
- `0x18003510c`
- `0x1800351a0`
- `0x180063c24`
- `0x1800675bc`
- `0x180067e84`
- `0x180068cc4`
- `0x18006ad40`
- `0x18006b3a8`
- `0x180071070`
- `0x1800d098c`
- `0x18013e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800d0bcd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d0ce1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d0ce1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d0a81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d0a81`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CEcsTelemetry::GetHashedRootDnsName(__int64 a1)
{
  _BYTE *v1; // rax
  char v2; // al
  HRESULT v3; // eax
  int v4; // eax
  _QWORD *v5; // rax
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r10
  BYTE *v12; // rax
  DWORD v13; // r8d
  __int64 v14; // rax
  int v16; // [rsp+30h] [rbp-118h] BYREF
  int v17; // [rsp+34h] [rbp-114h]
  char v18; // [rsp+38h] [rbp-110h]
  const char *v19; // [rsp+40h] [rbp-108h]
  __int64 v20; // [rsp+48h] [rbp-100h]
  unsigned int v21; // [rsp+50h] [rbp-F8h] BYREF
  int v22; // [rsp+54h] [rbp-F4h]
  HRESULT pExceptionObject; // [rsp+58h] [rbp-F0h] BYREF
  int v24; // [rsp+5Ch] [rbp-ECh] BYREF
  int v25; // [rsp+60h] [rbp-E8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-E0h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v28; // [rsp+78h] [rbp-D0h]
  int v29; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v30[8]; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE v31[8]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v32[8]; // [rsp+98h] [rbp-B0h] BYREF
  char v33; // [rsp+A0h] [rbp-A8h] BYREF
  const ATL::CAtlException *v34; // [rsp+A8h] [rbp-A0h] BYREF
  _BYTE v35[32]; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v36[16]; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-68h]
  BYTE v38[32]; // [rsp+F0h] [rbp-58h] BYREF
  BYTE v39[16]; // [rsp+110h] [rbp-38h] BYREF
  __int128 v40; // [rsp+120h] [rbp-28h]

  v28 = a1;
  v22 = 1;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v2 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
  }
  if ( (v1[68] & 2) == 0 || v1[65] < 6u )
    goto LABEL_8;
  v2 = 1;
LABEL_9:
  v16 = 0;
  v17 = 41;
  v18 = v2;
  v19 = "CEcsTelemetry::GetHashedRootDnsName";
  v20 = 0;
  std::wstring::wstring(v28);
  v22 = 1;
  try
  {
    ppv = 0;
    std::string::string(v36);
    std::wstring::wstring(v35);
    bstrString = 0;
    v3 = CoCreateInstance(&CLSID_ADSystemInfo, 0, 1u, &GUID_5bb11929_afd1_11d2_9cb9_0000f87a369e, &ppv);
    v16 = v3;
    if ( v3 < 0 )
    {
      HIWORD(v17) = 54;
      pExceptionObject = v3;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v17) = 54;
    v4 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 96LL))(ppv, &bstrString);
    v16 = v4;
    if ( v4 < 0 )
    {
      HIWORD(v17) = 56;
      v24 = v4;
      throw (long *)&v24;
    }
    LOWORD(v17) = 56;
    if ( !bstrString )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids);
      }
      v16 = -2147418113;
      HIWORD(v17) = 61;
      v25 = -2147418113;
      throw (long *)&v25;
    }
    *(_OWORD *)v39 = 0;
    v40 = 0;
    v21 = 0;
    std::wstring::operator=(v35, bstrString);
    std::wstring::begin(v35, v30);
    std::wstring::end(v35, v31);
    v5 = (_QWORD *)std::wstring::begin(v35, v32);
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)&v33,
      *v5,
      v6,
      v7,
      (__int64)towupper);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
    v9 = CEcsStringUtil::Utf16ToUtf8(v38, v8);
    std::string::operator=(v36, v9);
    std::string::~string(v38);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
      WPP_SF_S(*(_QWORD *)(v11 + 56), 15, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids, v10);
    }
    if ( v37 )
    {
      v12 = (BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v36);
      CEcsHash::HashData(0x800Cu, v12, v13, v39, 0x20u, &v21);
      v14 = CEcsEncode::Base64EncodeW(v38, v39, v21);
      std::wstring::operator=(v28, v14);
      std::wstring::~wstring(v38);
    }
    SysFreeString(bstrString);
    std::wstring::~wstring(v35);
    std::string::~string(v36);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppv);
  }
  catch ( long v29 )
  {
    v16 = v29;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v17) = 85;
    v16 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v17) = 85;
    v16 = -2147418113;
  }
  catch ( const ATL::CAtlException *v34 )
  {
    HIWORD(v17) = 85;
    v16 = *(_DWORD *)v34;
  }
  if ( v16 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids);
  }
  v22 = 0;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v16);
  return v28;
}

```

## disassembly

```asm
0x1800d098c  mov     [rsp+arg_8], rbx
0x1800d0991  mov     [rsp+arg_10], rsi
0x1800d0996  push    rdi
0x1800d0997  sub     rsp, 140h
0x1800d099e  mov     rax, cs:__security_cookie
0x1800d09a5  xor     rax, rsp
0x1800d09a8  mov     [rsp+148h+var_18], rax
0x1800d09b0  mov     [rsp+148h+var_D0], rcx
0x1800d09b5  mov     edi, 1
0x1800d09ba  mov     [rsp+148h+var_F4], edi
0x1800d09be  lea     rsi, WPP_GLOBAL_Control
0x1800d09c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800d09cc  cmp     rax, rsi
0x1800d09cf  jz      short loc_1800D09F7
0x1800d09d1  test    byte ptr [rax+44h], 2
0x1800d09d5  jz      short loc_1800D0A0A
0x1800d09d7  cmp     byte ptr [rax+41h], 6
0x1800d09db  jb      short loc_1800D09F7
0x1800d09dd  lea     edx, [rdi+0Ch]
0x1800d09e0  lea     r8, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids
0x1800d09e7  mov     rcx, [rax+38h]
0x1800d09eb  call    WPP_SF_
0x1800d09f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800d09f7  test    byte ptr [rax+44h], 2
0x1800d09fb  jz      short loc_1800D0A0A
0x1800d09fd  cmp     byte ptr [rax+41h], 6
0x1800d0a01  jb      short loc_1800D0A0A
0x1800d0a03  mov     al, dil
0x1800d0a06  xor     ebx, ebx
0x1800d0a08  jmp     short loc_1800D0A0E
0x1800d0a0a  xor     ebx, ebx
0x1800d0a0c  mov     al, bl
0x1800d0a0e  mov     [rsp+148h+var_118], ebx
0x1800d0a12  mov     [rsp+148h+var_114], 29h ; ')'
0x1800d0a1a  mov     [rsp+148h+var_110], al
0x1800d0a1e  lea     rax, aCecstelemetryG; "CEcsTelemetry::GetHashedRootDnsName"
0x1800d0a25  mov     [rsp+148h+var_108], rax
0x1800d0a2a  mov     [rsp+148h+var_100], rbx
0x1800d0a2f  mov     rcx, [rsp+148h+var_D0]
0x1800d0a34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d0a39  nop
0x1800d0a3a  mov     [rsp+148h+var_F4], edi
0x1800d0a3e  mov     [rsp+148h+var_D8], rbx
0x1800d0a43  lea     rcx, [rsp+148h+var_78]
0x1800d0a4b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800d0a50  nop
0x1800d0a51  lea     rcx, [rsp+148h+var_98]
0x1800d0a59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d0a5e  nop
0x1800d0a5f  mov     [rsp+148h+bstrString], rbx
0x1800d0a64  lea     rax, [rsp+148h+var_D8]
0x1800d0a69  mov     [rsp+148h+ppv], rax; ppv
0x1800d0a6e  lea     r9, _GUID_5bb11929_afd1_11d2_9cb9_0000f87a369e; riid
0x1800d0a75  mov     r8d, edi; dwClsContext
0x1800d0a78  xor     edx, edx; pUnkOuter
0x1800d0a7a  lea     rcx, CLSID_ADSystemInfo; rclsid
0x1800d0a81  call    cs:__imp_CoCreateInstance
0x1800d0a87  mov     [rsp+148h+var_118], eax
0x1800d0a8b  mov     [rsp+148h+var_118], eax
0x1800d0a8f  mov     ecx, 36h ; '6'
0x1800d0a94  test    eax, eax
0x1800d0a96  jns     short loc_1800D0AB2
0x1800d0a98  mov     word ptr [rsp+148h+var_114+2], cx
0x1800d0a9d  mov     [rsp+148h+pExceptionObject], eax
0x1800d0aa1  lea     rdx, _TI1J; pThrowInfo
0x1800d0aa8  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800d0aad  call    _CxxThrowException_0
0x1800d0ab2  mov     word ptr [rsp+148h+var_114], cx
0x1800d0ab7  mov     rcx, [rsp+148h+var_D8]
0x1800d0abc  mov     rax, [rcx]
0x1800d0abf  lea     rdx, [rsp+148h+bstrString]
0x1800d0ac4  mov     rax, [rax+60h]
0x1800d0ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0acd  mov     [rsp+148h+var_118], eax
0x1800d0ad1  mov     [rsp+148h+var_118], eax
0x1800d0ad5  mov     ecx, 38h ; '8'
0x1800d0ada  test    eax, eax
0x1800d0adc  jns     short loc_1800D0AF8
0x1800d0ade  mov     word ptr [rsp+148h+var_114+2], cx
0x1800d0ae3  mov     [rsp+148h+var_EC], eax
0x1800d0ae7  lea     rdx, _TI1J; pThrowInfo
0x1800d0aee  lea     rcx, [rsp+148h+var_EC]; pExceptionObject
0x1800d0af3  call    _CxxThrowException_0
0x1800d0af8  mov     word ptr [rsp+148h+var_114], cx
0x1800d0afd  mov     rdx, [rsp+148h+bstrString]
0x1800d0b02  test    rdx, rdx
0x1800d0b05  jnz     short loc_1800D0B64
0x1800d0b07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0b0e  cmp     rcx, rsi
0x1800d0b11  jz      short loc_1800D0B38
0x1800d0b13  test    byte ptr [rcx+44h], 2
0x1800d0b17  jz      short loc_1800D0B38
0x1800d0b19  cmp     byte ptr [rcx+41h], 2
0x1800d0b1d  jb      short loc_1800D0B38
0x1800d0b1f  mov     edx, 0Eh
0x1800d0b24  lea     r8, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids
0x1800d0b2b  mov     rcx, [rcx+38h]
0x1800d0b2f  call    WPP_SF_
0x1800d0b34  mov     eax, [rsp+148h+var_118]
0x1800d0b38  mov     [rsp+148h+var_118], eax
0x1800d0b3c  mov     ecx, 8000FFFFh
0x1800d0b41  mov     [rsp+148h+var_118], ecx
0x1800d0b45  mov     eax, 3Dh ; '='
0x1800d0b4a  mov     word ptr [rsp+148h+var_114+2], ax
0x1800d0b4f  mov     [rsp+148h+var_E8], ecx
0x1800d0b53  lea     rdx, _TI1J; pThrowInfo
0x1800d0b5a  lea     rcx, [rsp+148h+var_E8]; pExceptionObject
0x1800d0b5f  call    _CxxThrowException_0
0x1800d0b64  xorps   xmm0, xmm0
0x1800d0b67  movups  xmmword ptr [rsp+148h+var_38], xmm0
0x1800d0b6f  movups  [rsp+148h+var_28], xmm0
0x1800d0b77  mov     [rsp+148h+var_F8], ebx
0x1800d0b7b  lea     rcx, [rsp+148h+var_98]
0x1800d0b83  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800d0b88  lea     rdx, [rsp+148h+var_C0]
0x1800d0b90  lea     rcx, [rsp+148h+var_98]
0x1800d0b98  call    ?begin@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::begin(void)
0x1800d0b9d  mov     r9, [rax]
0x1800d0ba0  lea     rdx, [rsp+148h+var_B8]
0x1800d0ba8  lea     rcx, [rsp+148h+var_98]
0x1800d0bb0  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800d0bb5  mov     r8, [rax]
0x1800d0bb8  lea     rdx, [rsp+148h+var_B0]
0x1800d0bc0  lea     rcx, [rsp+148h+var_98]
0x1800d0bc8  call    ?begin@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::begin(void)
0x1800d0bcd  mov     rcx, cs:__imp_towupper
0x1800d0bd4  mov     [rsp+148h+ppv], rcx
0x1800d0bd9  mov     rdx, [rax]
0x1800d0bdc  lea     rcx, [rsp+148h+var_A8]
0x1800d0be4  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800d0be9  lea     rcx, [rsp+148h+var_98]
0x1800d0bf1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d0bf6  mov     rdx, rax
0x1800d0bf9  lea     rcx, [rsp+148h+var_58]
0x1800d0c01  call    ?Utf16ToUtf8@CEcsStringUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; CEcsStringUtil::Utf16ToUtf8(ushort const *)
0x1800d0c06  nop
0x1800d0c07  mov     rdx, rax
0x1800d0c0a  lea     rcx, [rsp+148h+var_78]
0x1800d0c12  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800d0c17  nop
0x1800d0c18  lea     rcx, [rsp+148h+var_58]
0x1800d0c20  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d0c25  mov     r10, cs:WPP_GLOBAL_Control
0x1800d0c2c  cmp     r10, rsi
0x1800d0c2f  jz      short loc_1800D0C64
0x1800d0c31  test    byte ptr [r10+44h], 2
0x1800d0c36  jz      short loc_1800D0C64
0x1800d0c38  cmp     byte ptr [r10+41h], 4
0x1800d0c3d  jb      short loc_1800D0C64
0x1800d0c3f  lea     rcx, [rsp+148h+var_98]
0x1800d0c47  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d0c4c  mov     r9, rax
0x1800d0c4f  mov     edx, 0Fh
0x1800d0c54  lea     r8, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids
0x1800d0c5b  mov     rcx, [r10+38h]
0x1800d0c5f  call    WPP_SF_S
0x1800d0c64  mov     r8, [rsp+148h+var_68]
0x1800d0c6c  test    r8, r8
0x1800d0c6f  jz      short loc_1800D0CDC
0x1800d0c71  lea     rcx, [rsp+148h+var_78]
0x1800d0c79  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800d0c7e  lea     rcx, [rsp+148h+var_F8]
0x1800d0c83  mov     [rsp+148h+var_120], rcx; unsigned int *
0x1800d0c88  mov     dword ptr [rsp+148h+ppv], 20h ; ' '; pdwDataLen
0x1800d0c90  lea     r9, [rsp+148h+var_38]; BYTE *
0x1800d0c98  mov     rdx, rax; pbData
0x1800d0c9b  mov     ecx, 800Ch; Algid
0x1800d0ca0  call    ?HashData@CEcsHash@@SAJIPEBXKPEAXKPEAK@Z; CEcsHash::HashData(uint,void const *,ulong,void *,ulong,ulong *)
0x1800d0ca5  mov     r8d, [rsp+148h+var_F8]
0x1800d0caa  lea     rdx, [rsp+148h+var_38]
0x1800d0cb2  lea     rcx, [rsp+148h+var_58]
0x1800d0cba  call    ?Base64EncodeW@CEcsEncode@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBX_K@Z; CEcsEncode::Base64EncodeW(void const *,unsigned __int64)
0x1800d0cbf  nop
0x1800d0cc0  mov     rdx, rax
0x1800d0cc3  mov     rcx, [rsp+148h+var_D0]
0x1800d0cc8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800d0ccd  nop
0x1800d0cce  lea     rcx, [rsp+148h+var_58]
0x1800d0cd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d0cdb  nop
0x1800d0cdc  mov     rcx, [rsp+148h+bstrString]; bstrString
0x1800d0ce1  call    cs:__imp_SysFreeString
0x1800d0ce7  nop
0x1800d0ce8  lea     rcx, [rsp+148h+var_98]
0x1800d0cf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d0cf5  nop
0x1800d0cf6  lea     rcx, [rsp+148h+var_78]
0x1800d0cfe  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d0d03  nop
0x1800d0d04  lea     rcx, [rsp+148h+var_D8]
0x1800d0d09  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x1800d0d0e  nop
0x1800d0d0f  jmp     short loc_1800D0D23
0x1800d0d11  jmp     short loc_1800D0D17
0x1800d0d13  jmp     short loc_1800D0D17
0x1800d0d15  jmp     short $+2
0x1800d0d17  lea     rsi, WPP_GLOBAL_Control
0x1800d0d1e  mov     edi, 1
0x1800d0d23  mov     r9d, [rsp+148h+var_118]
0x1800d0d28  test    r9d, r9d
0x1800d0d2b  jns     short loc_1800D0D5A
0x1800d0d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0d34  cmp     rcx, rsi
0x1800d0d37  jz      short loc_1800D0D5A
0x1800d0d39  test    byte ptr [rcx+44h], 2
0x1800d0d3d  jz      short loc_1800D0D5A
0x1800d0d3f  cmp     byte ptr [rcx+41h], 3
0x1800d0d43  jb      short loc_1800D0D5A
0x1800d0d45  mov     edx, 10h
0x1800d0d4a  lea     r8, WPP_282f888b9ec83ebb476b4dad322a07c9_Traceguids
0x1800d0d51  mov     rcx, [rcx+38h]
0x1800d0d55  call    WPP_SF_d
0x1800d0d5a  and     edi, 0FFFFFFFEh
0x1800d0d5d  mov     [rsp+148h+var_F4], edi
0x1800d0d61  lea     rcx, [rsp+148h+var_118]; this
0x1800d0d66  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d0d6b  mov     rax, [rsp+148h+var_D0]
0x1800d0d70  mov     rcx, [rsp+148h+var_18]
0x1800d0d78  xor     rcx, rsp; StackCookie
0x1800d0d7b  call    __security_check_cookie
0x1800d0d80  lea     r11, [rsp+148h+var_8]
0x1800d0d88  mov     rbx, [r11+18h]
0x1800d0d8c  mov     rsi, [r11+20h]
0x1800d0d90  mov     rsp, r11
0x1800d0d93  pop     rdi
0x1800d0d94  retn
```
