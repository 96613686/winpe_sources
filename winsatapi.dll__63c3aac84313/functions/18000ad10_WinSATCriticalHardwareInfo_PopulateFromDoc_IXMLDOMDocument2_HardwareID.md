# WinSATCriticalHardwareInfo::PopulateFromDoc(IXMLDOMDocument2 *,HardwareID)

- ea: `0x18000ad10`
- end: `0x18000b115`
- name: `?PopulateFromDoc@WinSATCriticalHardwareInfo@@QEAAJPEAUIXMLDOMDocument2@@W4HardwareID@@@Z`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007930`

## callees

- `0x180001a34`
- `0x180006970`
- `0x1800071d0`
- `0x18000782c`
- `0x18000ad10`
- `0x18000d108`
- `0x1800171e0`
- `0x18002b2e4`
- `0x18002b3e8`
- `0x18002b49c`
- `0x18002b558`
- `0x18002b5f8`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000adef`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000adf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae24`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000adef`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000adf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae24`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ae5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ae7f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aea4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ae5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ae7f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aea4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae4d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae72`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae97`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b046`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b050`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b05a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae4d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae72`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae97`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b046`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b050`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b05a`

## string_xrefs

- `0x18000af26`: `base\winsat\mlib\mxmldom.cpp`
- `0x18000afbd`: `base\winsat\mlib\mxmldom.cpp`
- `0x18000af51`: `cannot get the root node for an XML documentt`
- `0x18000af94`: `cannot select a XML node for from an XPATH expression`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinSATCriticalHardwareInfo::PopulateFromDoc(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 i; // rbx
  __int64 v6; // rsi
  __int64 j; // rbx
  __int64 v8; // rax
  bool v9; // zf
  _QWORD *v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rdi
  void *v14; // rcx
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rdi
  BSTR v17; // rax
  OLECHAR *v18; // rsi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // r14d
  int v25; // ebx
  BSTR v26; // [rsp+48h] [rbp-38h]
  _QWORD v27[4]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD *v28; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+48h] BYREF

  v28 = 0;
  *(_BYTE *)a1 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  for ( i = *(_QWORD *)(a1 + 8); i != v4; i += 24 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(i + 8);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(i);
  }
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 32) = -1;
  *(_QWORD *)(a1 + 40) = -1;
  *(_WORD *)(a1 + 96) = 0;
  *(_WORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = -1;
  *(_DWORD *)(a1 + 84) = -1;
  *(_QWORD *)(a1 + 88) = -1;
  *(_BYTE *)(a1 + 48) = 0;
  *(_WORD *)(a1 + 240) = 0;
  *(_WORD *)(a1 + 368) = 0;
  v6 = *(_QWORD *)(a1 + 64);
  for ( j = *(_QWORD *)(a1 + 56); j != v6; j += 40 )
  {
    v8 = *(_QWORD *)(j + 16);
    v9 = (*(_QWORD *)(v8 + 16))-- == 1;
    if ( v9 )
    {
      v10 = *(_QWORD **)(j + 16);
      if ( v10 )
      {
        v11 = (void *)v10[3];
        if ( v11 )
          operator delete(v11);
        operator delete(v10);
      }
    }
    v12 = *(_QWORD *)(j + 8);
    v9 = (*(_QWORD *)(v12 + 16))-- == 1;
    if ( v9 )
    {
      v13 = *(_QWORD **)(j + 8);
      if ( v13 )
      {
        v14 = (void *)v13[3];
        if ( v14 )
          operator delete(v14);
        operator delete(v13);
      }
    }
  }
  *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 56);
  v29 = 0;
  v28 = 0;
  SysFreeString(0);
  v15 = SysAllocString(L"/WinSAT");
  if ( !v15
    || (SysFreeString(0), (v16 = SysAllocString(L"SelectionNamespaces")) == 0)
    || (SysFreeString(0), v17 = SysAllocString(&String2), v18 = v17, (v26 = v17) == 0) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  v27[0] = 8;
  v27[1] = v17;
  v27[2] = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a2 + 640LL))(a2, v16, v27);
  if ( v19 >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 360LL))(a2, &v29);
    if ( v21 >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD **))(*(_QWORD *)v29 + 296LL))(v29, v15, &v28);
      if ( v22 >= 0 )
      {
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        SysFreeString(v18);
        SysFreeString(v16);
        SysFreeString(v15);
        goto LABEL_31;
      }
      v28 = 0;
      v20 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1130,
              v22,
              v29,
              (__int64)&GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot select a XML node for from an XPATH expression");
    }
    else
    {
      v20 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1123,
              v21,
              a2,
              (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot get the root node for an XML documentt");
    }
  }
  else
  {
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1116,
            v19,
            a2,
            (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
            0,
            (__int64)L"cannot set the %s document propert",
            v16,
            v16,
            v26,
            -2,
            v15);
  }
  v23 = v20;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  SysFreeString(v18);
  SysFreeString(v16);
  SysFreeString(v15);
  if ( v23 < 0 )
  {
    if ( v28 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
    return (unsigned int)v23;
  }
LABEL_31:
  v25 = WinSATCriticalHardwareInfo::PopulateCPUInfoFromDoc(a1, v28);
  if ( v25 < 0
    || (v25 = WinSATCriticalHardwareInfo::PopulateSystemInfoFromDoc(a1, v28), v25 < 0)
    || (v25 = WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(a1, v28), v25 < 0)
    || (v25 = WinSATCriticalHardwareInfo::PopulateDiskInfoFromDoc(a1, v28), v25 < 0)
    || (v25 = WinSATCriticalHardwareInfo::PopulateVideoInfoFromDoc(a1, v28), v25 < 0)
    || (v25 = WinSATCriticalHardwareInfo::PopulateVersionInfoFromDoc(a1, v28), v25 < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    return (unsigned int)v25;
  }
  else if ( (unsigned __int8)WinSATCriticalHardwareInfo::IsPopulated(a1, 4095) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    return 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18000ad10  mov     rax, rsp
0x18000ad13  push    rbp
0x18000ad14  push    rdi
0x18000ad15  push    r12
0x18000ad17  push    r14
0x18000ad19  push    r15
0x18000ad1b  mov     rbp, rsp
0x18000ad1e  sub     rsp, 80h
0x18000ad25  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000ad2d  mov     [rax+10h], rbx
0x18000ad31  mov     [rax+18h], rsi
0x18000ad35  mov     r14, rdx
0x18000ad38  mov     r15, rcx
0x18000ad3b  xor     r12d, r12d
0x18000ad3e  mov     [rbp+arg_0], r12
0x18000ad42  mov     [rcx], r12b
0x18000ad45  mov     rdi, [rcx+10h]
0x18000ad49  mov     rbx, [rcx+8]
0x18000ad4d  cmp     rbx, rdi
0x18000ad50  jz      short loc_18000AD6C
0x18000ad52  lea     rcx, [rbx+8]
0x18000ad56  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000ad5b  mov     rcx, rbx
0x18000ad5e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000ad63  add     rbx, 18h
0x18000ad67  cmp     rbx, rdi
0x18000ad6a  jnz     short loc_18000AD52
0x18000ad6c  mov     rax, [r15+8]
0x18000ad70  mov     [r15+10h], rax
0x18000ad74  mov     qword ptr [r15+20h], 0FFFFFFFFFFFFFFFFh
0x18000ad7c  mov     qword ptr [r15+28h], 0FFFFFFFFFFFFFFFFh
0x18000ad84  mov     [r15+60h], r12w
0x18000ad89  mov     word ptr [r15+0E0h], 0
0x18000ad93  mov     qword ptr [r15+0E8h], 0FFFFFFFFFFFFFFFFh
0x18000ad9e  mov     dword ptr [r15+54h], 0FFFFFFFFh
0x18000ada6  mov     qword ptr [r15+58h], 0FFFFFFFFFFFFFFFFh
0x18000adae  mov     byte ptr [r15+30h], 0
0x18000adb3  mov     [r15+0F0h], r12w
0x18000adbb  mov     word ptr [r15+170h], 0
0x18000adc5  mov     rsi, [r15+40h]
0x18000adc9  mov     rbx, [r15+38h]
0x18000adcd  cmp     rbx, rsi
0x18000add0  jz      short loc_18000AE33
0x18000add2  mov     rax, [rbx+10h]
0x18000add6  sub     qword ptr [rax+10h], 1
0x18000addb  jnz     short loc_18000ADFE
0x18000addd  mov     rdi, [rbx+10h]
0x18000ade1  test    rdi, rdi
0x18000ade4  jz      short loc_18000ADFE
0x18000ade6  mov     rcx, [rdi+18h]
0x18000adea  test    rcx, rcx
0x18000aded  jz      short loc_18000ADF5
0x18000adef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000adf5  mov     rcx, rdi
0x18000adf8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000adfe  mov     rax, [rbx+8]
0x18000ae02  sub     qword ptr [rax+10h], 1
0x18000ae07  jnz     short loc_18000AE2A
0x18000ae09  mov     rdi, [rbx+8]
0x18000ae0d  test    rdi, rdi
0x18000ae10  jz      short loc_18000AE2A
0x18000ae12  mov     rcx, [rdi+18h]
0x18000ae16  test    rcx, rcx
0x18000ae19  jz      short loc_18000AE21
0x18000ae1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae21  mov     rcx, rdi
0x18000ae24  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae2a  add     rbx, 28h ; '('
0x18000ae2e  cmp     rbx, rsi
0x18000ae31  jnz     short loc_18000ADD2
0x18000ae33  mov     rax, [r15+38h]
0x18000ae37  mov     [r15+40h], rax
0x18000ae3b  mov     [rbp+var_40], r12
0x18000ae3f  mov     [rbp+var_38], r12
0x18000ae43  mov     [rbp+arg_18], r12
0x18000ae47  mov     [rbp+arg_0], r12
0x18000ae4b  xor     ecx, ecx; bstrString
0x18000ae4d  call    cs:__imp_SysFreeString
0x18000ae53  lea     rcx, psz; "/WinSAT"
0x18000ae5a  call    cs:__imp_SysAllocString
0x18000ae60  mov     rbx, rax
0x18000ae63  mov     [rbp+var_28], rax
0x18000ae67  test    rax, rax
0x18000ae6a  jz      loc_18000B10A
0x18000ae70  xor     ecx, ecx; bstrString
0x18000ae72  call    cs:__imp_SysFreeString
0x18000ae78  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18000ae7f  call    cs:__imp_SysAllocString
0x18000ae85  mov     rdi, rax
0x18000ae88  mov     [rbp+var_40], rax
0x18000ae8c  test    rax, rax
0x18000ae8f  jz      loc_18000B10A
0x18000ae95  xor     ecx, ecx; bstrString
0x18000ae97  call    cs:__imp_SysFreeString
0x18000ae9d  lea     rcx, String2; psz
0x18000aea4  call    cs:__imp_SysAllocString
0x18000aeaa  mov     rsi, rax
0x18000aead  mov     [rbp+var_38], rax
0x18000aeb1  test    rax, rax
0x18000aeb4  jz      loc_18000B10A
0x18000aeba  xorps   xmm0, xmm0
0x18000aebd  xor     ecx, ecx
0x18000aebf  movups  [rbp+var_20], xmm0
0x18000aec3  mov     eax, 8
0x18000aec8  mov     word ptr [rbp+var_20], ax
0x18000aecc  mov     qword ptr [rbp+var_20+8], rsi
0x18000aed0  movups  xmm0, [rbp+var_20]
0x18000aed4  movaps  [rbp+var_20], xmm0
0x18000aed8  mov     [rbp+var_10], rcx
0x18000aedc  mov     rax, [r14]
0x18000aedf  lea     r8, [rbp+var_20]
0x18000aee3  mov     rdx, rdi
0x18000aee6  mov     rcx, r14
0x18000aee9  mov     rax, [rax+280h]
0x18000aef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef5  test    eax, eax
0x18000aef7  jns     short loc_18000AF37
0x18000aef9  mov     [rsp+80h+var_48], rdi
0x18000aefe  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x18000af05  mov     [rsp+80h+var_50], rcx
0x18000af0a  mov     [rsp+80h+var_58], r12
0x18000af0f  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18000af16  mov     [rsp+80h+var_60], rcx
0x18000af1b  mov     r9, r14
0x18000af1e  mov     r8d, eax
0x18000af21  mov     edx, 45Ch
0x18000af26  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000af2d  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18000af32  jmp     loc_18000AFC9
0x18000af37  mov     rax, [r14]
0x18000af3a  lea     rdx, [rbp+arg_18]
0x18000af3e  mov     rcx, r14
0x18000af41  mov     rax, [rax+168h]
0x18000af48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af4d  test    eax, eax
0x18000af4f  jns     short loc_18000AF6E
0x18000af51  lea     rcx, aCannotGetTheRo; "cannot get the root node for an XML doc"...
0x18000af58  mov     [rsp+80h+var_50], rcx
0x18000af5d  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18000af64  mov     r9, r14
0x18000af67  mov     edx, 463h
0x18000af6c  jmp     short loc_18000AFB0
0x18000af6e  mov     rcx, [rbp+arg_18]
0x18000af72  mov     rax, [rcx]
0x18000af75  lea     r8, [rbp+arg_0]
0x18000af79  mov     rdx, rbx
0x18000af7c  mov     rax, [rax+128h]
0x18000af83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af88  test    eax, eax
0x18000af8a  jns     loc_18000B02D
0x18000af90  mov     [rbp+arg_0], r12
0x18000af94  lea     rcx, aCannotSelectAX; "cannot select a XML node for from an XP"...
0x18000af9b  mov     [rsp+80h+var_50], rcx
0x18000afa0  lea     rcx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18000afa7  mov     r9, [rbp+arg_18]
0x18000afab  mov     edx, 46Ah
0x18000afb0  mov     [rsp+80h+var_58], r12
0x18000afb5  mov     [rsp+80h+var_60], rcx
0x18000afba  mov     r8d, eax
0x18000afbd  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000afc4  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18000afc9  mov     r14d, eax
0x18000afcc  lea     rcx, [rbp+arg_18]
0x18000afd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000afd5  nop
0x18000afd6  mov     rcx, rsi; bstrString
0x18000afd9  call    cs:__imp_SysFreeString
0x18000afdf  nop
0x18000afe0  mov     rcx, rdi; bstrString
0x18000afe3  call    cs:__imp_SysFreeString
0x18000afe9  nop
0x18000afea  mov     rcx, rbx; bstrString
0x18000afed  call    cs:__imp_SysFreeString
0x18000aff3  test    r14d, r14d
0x18000aff6  jns     short loc_18000B060
0x18000aff8  mov     rcx, [rbp+arg_0]
0x18000affc  test    rcx, rcx
0x18000afff  jz      short loc_18000B00E
0x18000b001  mov     rdx, [rcx]
0x18000b004  mov     rax, [rdx+10h]
0x18000b008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00d  nop
0x18000b00e  mov     eax, r14d
0x18000b011  lea     r11, [rsp+80h+var_s0]
0x18000b019  mov     rbx, [r11+38h]
0x18000b01d  mov     rsi, [r11+40h]
0x18000b021  mov     rsp, r11
0x18000b024  pop     r15
0x18000b026  pop     r14
0x18000b028  pop     r12
0x18000b02a  pop     rdi
0x18000b02b  pop     rbp
0x18000b02c  retn
0x18000b02d  mov     rcx, [rbp+arg_18]
0x18000b031  test    rcx, rcx
0x18000b034  jz      short loc_18000B043
0x18000b036  mov     rax, [rcx]
0x18000b039  mov     rax, [rax+10h]
0x18000b03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b042  nop
0x18000b043  mov     rcx, rsi; bstrString
0x18000b046  call    cs:__imp_SysFreeString
0x18000b04c  nop
0x18000b04d  mov     rcx, rdi; bstrString
0x18000b050  call    cs:__imp_SysFreeString
0x18000b056  nop
0x18000b057  mov     rcx, rbx; bstrString
0x18000b05a  call    cs:__imp_SysFreeString
0x18000b060  mov     rdx, [rbp+arg_0]
0x18000b064  mov     rcx, r15
0x18000b067  call    ?PopulateCPUInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateCPUInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b06c  mov     ebx, eax
0x18000b06e  test    eax, eax
0x18000b070  jns     short loc_18000B07F
0x18000b072  lea     rcx, [rbp+arg_0]
0x18000b076  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b07b  mov     eax, ebx
0x18000b07d  jmp     short loc_18000B011
0x18000b07f  mov     rdx, [rbp+arg_0]
0x18000b083  mov     rcx, r15
0x18000b086  call    ?PopulateSystemInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateSystemInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b08b  mov     ebx, eax
0x18000b08d  test    eax, eax
0x18000b08f  js      short loc_18000B072
0x18000b091  mov     rdx, [rbp+arg_0]
0x18000b095  mov     rcx, r15
0x18000b098  call    ?PopulateMemoryInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b09d  mov     ebx, eax
0x18000b09f  test    eax, eax
0x18000b0a1  js      short loc_18000B072
0x18000b0a3  mov     rdx, [rbp+arg_0]
0x18000b0a7  mov     rcx, r15
0x18000b0aa  call    ?PopulateDiskInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateDiskInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b0af  mov     ebx, eax
0x18000b0b1  test    eax, eax
0x18000b0b3  js      short loc_18000B072
0x18000b0b5  mov     rdx, [rbp+arg_0]
0x18000b0b9  mov     rcx, r15
0x18000b0bc  call    ?PopulateVideoInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateVideoInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b0c1  mov     ebx, eax
0x18000b0c3  test    eax, eax
0x18000b0c5  js      short loc_18000B072
0x18000b0c7  mov     rdx, [rbp+arg_0]
0x18000b0cb  mov     rcx, r15
0x18000b0ce  call    ?PopulateVersionInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateVersionInfoFromDoc(IXMLDOMNode *,HardwareID)
0x18000b0d3  mov     ebx, eax
0x18000b0d5  test    eax, eax
0x18000b0d7  js      short loc_18000B072
0x18000b0d9  mov     edx, 0FFFh
0x18000b0de  mov     rcx, r15
0x18000b0e1  call    ?IsPopulated@WinSATCriticalHardwareInfo@@QEBA_NW4HardwareID@@@Z; WinSATCriticalHardwareInfo::IsPopulated(HardwareID)
0x18000b0e6  nop
0x18000b0e7  lea     rcx, [rbp+arg_0]
0x18000b0eb  test    al, al
0x18000b0ed  jnz     short loc_18000B0FE
0x18000b0ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b0f4  mov     eax, 80004005h
0x18000b0f9  jmp     loc_18000B011
0x18000b0fe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b103  xor     eax, eax
0x18000b105  jmp     loc_18000B011
0x18000b10a  mov     ecx, 8007000Eh; int
0x18000b10f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
