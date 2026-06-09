# CContentDirectory::internal_get_SearchCapabilities(ushort * *)

- ea: `0x1400319c8`
- end: `0x140031d61`
- name: `?internal_get_SearchCapabilities@CContentDirectory@@AEAAJPEAPEAG@Z`
- size: `921`
- prototype: `__int64 __fastcall(CContentDirectory *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c100`

## callees

- `0x140003750`
- `0x1400065e0`
- `0x14000b3f0`
- `0x14000c920`
- `0x14000e660`
- `0x1400319c8`
- `0x1400395c0`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140047798`
- `0x140054490`
- `0x140059e7c`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140031cde`
- `ADVAPI32!RegCloseKey` at `0x140031cde`
- `ADVAPI32!RegOpenKeyExW` at `0x140031abe`
- `ADVAPI32!RegOpenKeyExW` at `0x140031abe`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140031c89`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140031c89`

## pseudocode

```c
__int64 __fastcall CContentDirectory::internal_get_SearchCapabilities(CContentDirectory *this, const wchar_t **a2)
{
  PVOID *v3; // r10
  const wchar_t *v4; // rbx
  int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // r12d
  HKEY v8; // r13
  PVOID *v9; // r10
  unsigned int v10; // edx
  int StringValue; // eax
  _QWORD *v12; // rax
  ATL::CStringData *v13; // rsi
  unsigned __int16 *v14; // r12
  const wchar_t *v15; // rax
  _QWORD v17[11]; // [rsp+40h] [rbp-58h] BYREF
  OLECHAR *strIn; // [rsp+B0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, a2);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  LOBYTE(v4) = 0;
  if ( a2 )
  {
    v5 = 0;
    strIn = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v17[1] = 0;
    v17[2] = 0;
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0", 0, 0x2011Fu, &hKey);
    v7 = v6;
    v8 = 0;
    if ( !v6 )
      v8 = hKey;
    v17[0] = v8;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 5;
      if ( v6 )
        v10 = 2;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v10 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, v6);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( !v7 )
    {
      StringValue = GetStringValue((ATL::CRegKey *)v17, L"SearchCapabilities");
      v5 = StringValue;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((StringValue >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)&WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
          StringValue,
          (__int64)strIn);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 >= 0 )
      {
        v12 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                          &strIn,
                          &hKey,
                          1024);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&strIn, v12);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&hKey);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( !*((_DWORD *)strIn - 4) )
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(&strIn, (_QWORD *)this + 38);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v9 + 28) & 2) != 0
      && *((unsigned __int8 *)v9 + 25) >= ((v5 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dS(
        (unsigned int)v9[2],
        43,
        (unsigned int)&WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
        v5,
        (__int64)strIn);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids);
    }
    v13 = (ATL::CStringData *)(strIn - 12);
    v14 = SysAllocStringLen(strIn, *((_DWORD *)strIn - 4));
    hKey = (HKEY)v14;
    if ( !v14 )
      ATL::CSimpleStringT<char,0>::ThrowMemoryException();
    if ( v8 )
      RegCloseKey(v8);
    ATL::CStringData::Release(v13);
    if ( v5 >= 0 )
      *a2 = v14;
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 2u )
    {
      WPP_SF_(v3[2], 40, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
  }
  if ( v3 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v3 + 28) & 1) != 0
    && *((unsigned __int8 *)v3 + 25) >= ((v5 >> 31) & 0xFFFFFFFD) + 5 )
  {
    if ( v5 < 0 )
    {
      v15 = L"Unknown";
    }
    else
    {
      v15 = *a2;
      v4 = *a2;
    }
    WPP_SF_dqS(
      (unsigned int)v3[2],
      46,
      (unsigned int)&WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
      v5,
      (char)v4,
      (__int64)v15);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400319c8  mov     [rsp+arg_8], rdx
0x1400319cd  mov     [rsp+arg_0], rcx
0x1400319d2  push    rbx
0x1400319d3  push    rsi
0x1400319d4  push    rdi
0x1400319d5  push    r12
0x1400319d7  push    r13
0x1400319d9  push    r14
0x1400319db  push    r15
0x1400319dd  sub     rsp, 60h
0x1400319e1  mov     r14, rdx
0x1400319e4  lea     r15, WPP_GLOBAL_Control
0x1400319eb  mov     r10, cs:WPP_GLOBAL_Control
0x1400319f2  cmp     r10, r15
0x1400319f5  jz      short loc_140031A24
0x1400319f7  test    byte ptr [r10+1Ch], 1
0x1400319fc  jz      short loc_140031A24
0x1400319fe  cmp     byte ptr [r10+19h], 5
0x140031a03  jb      short loc_140031A24
0x140031a05  mov     edx, 27h ; '''
0x140031a0a  mov     r9, r14
0x140031a0d  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031a14  mov     rcx, [r10+10h]
0x140031a18  call    WPP_SF_q
0x140031a1d  mov     r10, cs:WPP_GLOBAL_Control
0x140031a24  xor     ebx, ebx
0x140031a26  test    r14, r14
0x140031a29  jnz     short loc_140031A63
0x140031a2b  cmp     r10, r15
0x140031a2e  jz      short loc_140031A59
0x140031a30  lea     esi, [rbx+2]
0x140031a33  test    [r10+1Ch], sil
0x140031a37  jz      short loc_140031A59
0x140031a39  cmp     [r10+19h], sil
0x140031a3d  jb      short loc_140031A59
0x140031a3f  lea     edx, [rbx+28h]
0x140031a42  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031a49  mov     rcx, [r10+10h]
0x140031a4d  call    WPP_SF_
0x140031a52  mov     r10, cs:WPP_GLOBAL_Control
0x140031a59  mov     edi, 80070057h
0x140031a5e  jmp     loc_140031CFA
0x140031a63  mov     edi, ebx
0x140031a65  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140031a6c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140031a73  mov     rax, [rax+18h]
0x140031a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031a7c  add     rax, 18h
0x140031a80  mov     [rsp+98h+strIn], rax
0x140031a88  mov     [rsp+98h+var_50], rbx
0x140031a8d  mov     [rsp+98h+var_48], rbx
0x140031a92  mov     [rsp+98h+hKey], rbx
0x140031a9a  lea     rax, [rsp+98h+hKey]
0x140031aa2  mov     [rsp+98h+phkResult], rax; phkResult
0x140031aa7  mov     r9d, 2011Fh; samDesired
0x140031aad  xor     r8d, r8d; ulOptions
0x140031ab0  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x140031ab7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140031abe  call    cs:__imp_RegOpenKeyExW
0x140031ac4  mov     r12d, eax
0x140031ac7  mov     r13, rbx
0x140031aca  test    eax, eax
0x140031acc  cmovz   r13, [rsp+98h+hKey]
0x140031ad5  mov     [rsp+98h+var_58], r13
0x140031ada  mov     r10, cs:WPP_GLOBAL_Control
0x140031ae1  mov     esi, 2
0x140031ae6  cmp     r10, r15
0x140031ae9  jz      short loc_140031B1F
0x140031aeb  test    [r10+1Ch], sil
0x140031aef  jz      short loc_140031B1F
0x140031af1  lea     edx, [rsi+3]
0x140031af4  test    eax, eax
0x140031af6  cmovnz  edx, esi
0x140031af9  movzx   eax, byte ptr [r10+19h]
0x140031afe  cmp     eax, edx
0x140031b00  jb      short loc_140031B1F
0x140031b02  lea     edx, [rsi+27h]
0x140031b05  mov     r9d, r12d
0x140031b08  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031b0f  mov     rcx, [r10+10h]
0x140031b13  call    WPP_SF_d
0x140031b18  mov     r10, cs:WPP_GLOBAL_Control
0x140031b1f  test    r12d, r12d
0x140031b22  jnz     loc_140031BD8
0x140031b28  lea     r8, [rsp+98h+strIn]
0x140031b30  lea     rdx, aSearchcapabili; "SearchCapabilities"
0x140031b37  lea     rcx, [rsp+98h+var_58]; this
0x140031b3c  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140031b41  mov     edi, eax
0x140031b43  mov     r10, cs:WPP_GLOBAL_Control
0x140031b4a  cmp     r10, r15
0x140031b4d  jz      short loc_140031B95
0x140031b4f  test    [r10+1Ch], sil
0x140031b53  jz      short loc_140031B95
0x140031b55  mov     ecx, eax
0x140031b57  sar     ecx, 1Fh
0x140031b5a  and     ecx, 0FFFFFFFDh
0x140031b5d  add     ecx, 5
0x140031b60  movzx   eax, byte ptr [r10+19h]
0x140031b65  cmp     eax, ecx
0x140031b67  jb      short loc_140031B95
0x140031b69  lea     edx, [r12+2Ah]
0x140031b6e  mov     rax, [rsp+98h+strIn]
0x140031b76  mov     [rsp+98h+phkResult], rax
0x140031b7b  mov     r9d, edi
0x140031b7e  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031b85  mov     rcx, [r10+10h]
0x140031b89  call    WPP_SF_dS
0x140031b8e  mov     r10, cs:WPP_GLOBAL_Control
0x140031b95  test    edi, edi
0x140031b97  js      short loc_140031BD8
0x140031b99  mov     r8d, 400h
0x140031b9f  lea     rdx, [rsp+98h+hKey]
0x140031ba7  lea     rcx, [rsp+98h+strIn]
0x140031baf  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x140031bb4  mov     rdx, rax
0x140031bb7  lea     rcx, [rsp+98h+strIn]
0x140031bbf  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140031bc4  lea     rcx, [rsp+98h+hKey]
0x140031bcc  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140031bd1  mov     r10, cs:WPP_GLOBAL_Control
0x140031bd8  mov     rax, [rsp+98h+strIn]
0x140031be0  cmp     [rax-10h], ebx
0x140031be3  jnz     short loc_140031C08
0x140031be5  mov     rdx, [rsp+98h+arg_0]
0x140031bed  add     rdx, 130h
0x140031bf4  lea     rcx, [rsp+98h+strIn]
0x140031bfc  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140031c01  mov     r10, cs:WPP_GLOBAL_Control
0x140031c08  cmp     r10, r15
0x140031c0b  jz      short loc_140031C4D
0x140031c0d  test    [r10+1Ch], sil
0x140031c11  jz      short loc_140031C4D
0x140031c13  mov     ecx, edi
0x140031c15  sar     ecx, 1Fh
0x140031c18  and     ecx, 0FFFFFFFDh
0x140031c1b  add     ecx, 5
0x140031c1e  movzx   eax, byte ptr [r10+19h]
0x140031c23  cmp     eax, ecx
0x140031c25  jb      short loc_140031C4D
0x140031c27  mov     edx, 2Bh ; '+'
0x140031c2c  mov     rax, [rsp+98h+strIn]
0x140031c34  mov     [rsp+98h+phkResult], rax
0x140031c39  mov     r9d, edi
0x140031c3c  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031c43  mov     rcx, [r10+10h]
0x140031c47  call    WPP_SF_dS
0x140031c4c  nop
0x140031c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c54  cmp     rcx, r15
0x140031c57  jz      short loc_140031C7A
0x140031c59  test    [rcx+1Ch], sil
0x140031c5d  jz      short loc_140031C7A
0x140031c5f  cmp     byte ptr [rcx+19h], 5
0x140031c63  jb      short loc_140031C7A
0x140031c65  mov     edx, 2Ch ; ','
0x140031c6a  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031c71  mov     rcx, [rcx+10h]
0x140031c75  call    WPP_SF_
0x140031c7a  mov     rcx, [rsp+98h+strIn]; strIn
0x140031c82  lea     rsi, [rcx-18h]
0x140031c86  mov     edx, [rsi+8]; ui
0x140031c89  call    cs:__imp_SysAllocStringLen
0x140031c8f  mov     r12, rax
0x140031c92  mov     [rsp+98h+hKey], rax
0x140031c9a  test    rax, rax
0x140031c9d  jnz     short loc_140031CA5
0x140031c9f  call    ?ThrowMemoryException@?$CSimpleStringT@D$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<char,0>::ThrowMemoryException(void)
0x140031ca5  mov     [rsp+98h+var_60], rsi
0x140031caa  jmp     short loc_140031CD6
0x140031cac  lea     r15, WPP_GLOBAL_Control
0x140031cb3  xor     ebx, ebx
0x140031cb5  mov     r14, [rsp+98h+arg_8]
0x140031cbd  mov     edi, dword ptr [rsp+98h+strIn]
0x140031cc4  mov     r13, [rsp+98h+var_58]
0x140031cc9  mov     r12, [rsp+98h+hKey]
0x140031cd1  mov     rsi, [rsp+98h+var_60]
0x140031cd6  test    r13, r13
0x140031cd9  jz      short loc_140031CE4
0x140031cdb  mov     rcx, r13; hKey
0x140031cde  call    cs:__imp_RegCloseKey
0x140031ce4  mov     rcx, rsi; this
0x140031ce7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140031cec  test    edi, edi
0x140031cee  js      short loc_140031CF3
0x140031cf0  mov     [r14], r12
0x140031cf3  mov     r10, cs:WPP_GLOBAL_Control
0x140031cfa  cmp     r10, r15
0x140031cfd  jz      short loc_140031D4F
0x140031cff  test    byte ptr [r10+1Ch], 1
0x140031d04  jz      short loc_140031D4F
0x140031d06  mov     ecx, edi
0x140031d08  sar     ecx, 1Fh
0x140031d0b  and     ecx, 0FFFFFFFDh
0x140031d0e  add     ecx, 5
0x140031d11  movzx   eax, byte ptr [r10+19h]
0x140031d16  cmp     eax, ecx
0x140031d18  jb      short loc_140031D4F
0x140031d1a  test    edi, edi
0x140031d1c  js      short loc_140031D26
0x140031d1e  mov     rax, [r14]
0x140031d21  mov     rbx, rax
0x140031d24  jmp     short loc_140031D2D
0x140031d26  lea     rax, aUnknown; "Unknown"
0x140031d2d  mov     edx, 2Eh ; '.'
0x140031d32  mov     [rsp+98h+var_70], rax
0x140031d37  mov     [rsp+98h+phkResult], rbx
0x140031d3c  mov     r9d, edi
0x140031d3f  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x140031d46  mov     rcx, [r10+10h]
0x140031d4a  call    WPP_SF_dqS
0x140031d4f  mov     eax, edi
0x140031d51  add     rsp, 60h
0x140031d55  pop     r15
0x140031d57  pop     r14
0x140031d59  pop     r13
0x140031d5b  pop     r12
0x140031d5d  pop     rdi
0x140031d5e  pop     rsi
0x140031d5f  pop     rbx
0x140031d60  retn
```
