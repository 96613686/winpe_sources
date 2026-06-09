# mlib::XmlDOM::GetNodesValues(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<double,std::allocator<double>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140054d0c`
- end: `0x14005504b`
- name: `?GetNodesValues@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@NV?$allocator@N@std@@@std@@PEAV42@@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002e924`

## callees

- `0x140005d78`
- `0x14000712c`
- `0x140016d04`
- `0x1400343e4`
- `0x14003a23c`
- `0x14003a4f8`
- `0x140054d0c`
- `0x1400557f4`
- `0x140056088`
- `0x14011a010`

## import_xrefs

- `msvcrt!_wtof` at `0x140054f61`
- `msvcrt!_wtof` at `0x140054f61`
- `OLEAUT32!__imp_SysFreeString` at `0x140054f39`
- `OLEAUT32!__imp_SysFreeString` at `0x140054fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x140055000`
- `OLEAUT32!__imp_SysFreeString` at `0x140054f39`
- `OLEAUT32!__imp_SysFreeString` at `0x140054fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x140055000`

## string_xrefs

- `0x140054ddb`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054e6c`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054f26`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054fc8`: `base\winsat\mlib\mxmldom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall mlib::XmlDOM::GetNodesValues(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v8; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+40h] [rbp-58h] BYREF
  __int64 v20; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+50h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-40h] BYREF
  double v23[7]; // [rsp+60h] [rbp-38h] BYREF

  v20 = 0;
  v21 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &bstrString,
    &qword_14012B318);
  v8 = mlib::XmlDOM::SelectXml(a1, a2, (__int64)&bstrString, &v20, a4);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&bstrString);
  if ( v8 < 0 )
  {
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    return (unsigned int)v8;
  }
  v19 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v19);
  if ( v10 < 0 )
  {
    v11 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1609,
            v10,
            v20,
            (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
            a4,
            (__int64)L"cannot get the length of list");
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    return v11;
  }
  if ( !v19 )
    goto LABEL_6;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 72LL))(v20, &v21);
  if ( v12 >= 0 )
  {
    v14 = v19;
    if ( (__int64)(a3[2] - *a3) >> 3 > (unsigned __int64)v19 )
      v14 = (__int64)(a3[2] - *a3) >> 3;
    std::vector<double>::reserve(a3, v14);
    while ( v21 )
    {
      bstrString = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 208LL))(v21, &bstrString);
      if ( v15 < 0 )
      {
        v16 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1632,
                v15,
                v20,
                (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                a4,
                (__int64)L"cannot get the text for a node");
        SysFreeString(bstrString);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
        return v16;
      }
      v23[0] = _wtof(bstrString);
      std::vector<_D3DRECT *>::push_back(a3, v23);
      ATL::CComPtrBase<IXMLDOMNode>::Release(&v21);
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 72LL))(v20, &v21);
      if ( v17 < 0 )
      {
        v18 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1641,
                v17,
                v20,
                (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                a4,
                (__int64)L"cannot get the next node in a list");
        SysFreeString(bstrString);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
        return v18;
      }
      SysFreeString(bstrString);
    }
LABEL_6:
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    return 0;
  }
  v13 = mlib::XmlDOM::ReportCOMError_w(
          (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
          1621,
          v12,
          v20,
          (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
          a4,
          (__int64)L"cannot get next node in a list");
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v21);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
  return v13;
}

```

## disassembly

```asm
0x140054d0c  mov     rax, rsp
0x140054d0f  mov     [rax+20h], r9
0x140054d13  push    rbx
0x140054d14  push    rsi
0x140054d15  push    rdi
0x140054d16  push    r14
0x140054d18  sub     rsp, 78h
0x140054d1c  mov     rdi, r9
0x140054d1f  mov     r14, r8
0x140054d22  mov     rbx, rdx
0x140054d25  mov     rsi, rcx
0x140054d28  mov     qword ptr [rax-50h], 0
0x140054d30  mov     qword ptr [rax-48h], 0
0x140054d38  lea     rdx, qword_14012B318
0x140054d3f  lea     rcx, [rax-40h]
0x140054d43  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140054d48  nop
0x140054d49  mov     [rsp+98h+var_78], rdi
0x140054d4e  lea     r9, [rsp+98h+var_50]
0x140054d53  lea     r8, [rsp+98h+bstrString]
0x140054d58  mov     rdx, rbx
0x140054d5b  mov     rcx, rsi
0x140054d5e  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140054d63  mov     ebx, eax
0x140054d65  lea     rcx, [rsp+98h+bstrString]
0x140054d6a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140054d6f  test    ebx, ebx
0x140054d71  jns     short loc_140054D8F
0x140054d73  lea     rcx, [rsp+98h+var_48]
0x140054d78  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054d7d  nop
0x140054d7e  lea     rcx, [rsp+98h+var_50]
0x140054d83  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054d88  mov     eax, ebx
0x140054d8a  jmp     loc_140055041
0x140054d8f  mov     [rsp+98h+var_58], 0
0x140054d97  mov     rcx, [rsp+98h+var_50]
0x140054d9c  mov     rax, [rcx]
0x140054d9f  lea     rdx, [rsp+98h+var_58]
0x140054da4  mov     rax, [rax+40h]
0x140054da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054dad  test    eax, eax
0x140054daf  jns     short loc_140054E05
0x140054db1  lea     rcx, aCannotGetTheLe_0; "cannot get the length of list"
0x140054db8  mov     [rsp+98h+var_68], rcx
0x140054dbd  mov     [rsp+98h+var_70], rdi
0x140054dc2  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054dc9  mov     [rsp+98h+var_78], rcx
0x140054dce  mov     r9, [rsp+98h+var_50]
0x140054dd3  mov     r8d, eax
0x140054dd6  mov     edx, 649h
0x140054ddb  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054de2  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054de7  mov     ebx, eax
0x140054de9  lea     rcx, [rsp+98h+var_48]
0x140054dee  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054df3  nop
0x140054df4  lea     rcx, [rsp+98h+var_50]
0x140054df9  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054dfe  mov     eax, ebx
0x140054e00  jmp     loc_140055041
0x140054e05  cmp     [rsp+98h+var_58], 0
0x140054e0a  jnz     short loc_140054E28
0x140054e0c  lea     rcx, [rsp+98h+var_48]
0x140054e11  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054e16  nop
0x140054e17  lea     rcx, [rsp+98h+var_50]
0x140054e1c  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054e21  xor     eax, eax
0x140054e23  jmp     loc_140055041
0x140054e28  mov     rcx, [rsp+98h+var_50]
0x140054e2d  mov     rax, [rcx]
0x140054e30  lea     rdx, [rsp+98h+var_48]
0x140054e35  mov     rax, [rax+48h]
0x140054e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054e3e  test    eax, eax
0x140054e40  jns     short loc_140054E96
0x140054e42  lea     rcx, aCannotGetNextN; "cannot get next node in a list"
0x140054e49  mov     [rsp+98h+var_68], rcx
0x140054e4e  mov     [rsp+98h+var_70], rdi
0x140054e53  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054e5a  mov     [rsp+98h+var_78], rcx
0x140054e5f  mov     r9, [rsp+98h+var_50]
0x140054e64  mov     r8d, eax
0x140054e67  mov     edx, 655h
0x140054e6c  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054e73  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054e78  mov     ebx, eax
0x140054e7a  lea     rcx, [rsp+98h+var_48]
0x140054e7f  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054e84  nop
0x140054e85  lea     rcx, [rsp+98h+var_50]
0x140054e8a  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054e8f  mov     eax, ebx
0x140054e91  jmp     loc_140055041
0x140054e96  movsxd  rdx, [rsp+98h+var_58]
0x140054e9b  mov     rax, [r14+10h]
0x140054e9f  sub     rax, [r14]
0x140054ea2  sar     rax, 3
0x140054ea6  cmp     rax, rdx
0x140054ea9  cmova   rdx, rax
0x140054ead  mov     rcx, r14
0x140054eb0  call    ?reserve@?$vector@NV?$allocator@N@std@@@std@@QEAAX_K@Z; std::vector<double>::reserve(unsigned __int64)
0x140054eb5  mov     rcx, [rsp+98h+var_48]
0x140054eba  test    rcx, rcx
0x140054ebd  jnz     short loc_140054EDB
0x140054ebf  lea     rcx, [rsp+98h+var_48]
0x140054ec4  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054ec9  nop
0x140054eca  lea     rcx, [rsp+98h+var_50]
0x140054ecf  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054ed4  xor     eax, eax
0x140054ed6  jmp     loc_140055041
0x140054edb  mov     [rsp+98h+bstrString], 0
0x140054ee4  mov     rax, [rcx]
0x140054ee7  lea     rdx, [rsp+98h+bstrString]
0x140054eec  mov     rax, [rax+0D0h]
0x140054ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054ef8  test    eax, eax
0x140054efa  jns     short loc_140054F5C
0x140054efc  lea     rcx, aCannotGetTheTe; "cannot get the text for a node"
0x140054f03  mov     [rsp+98h+var_68], rcx
0x140054f08  mov     [rsp+98h+var_70], rdi
0x140054f0d  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054f14  mov     [rsp+98h+var_78], rcx
0x140054f19  mov     r9, [rsp+98h+var_50]
0x140054f1e  mov     r8d, eax
0x140054f21  mov     edx, 660h
0x140054f26  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054f2d  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054f32  mov     ebx, eax
0x140054f34  mov     rcx, [rsp+98h+bstrString]; bstrString
0x140054f39  call    cs:__imp_SysFreeString
0x140054f3f  nop
0x140054f40  lea     rcx, [rsp+98h+var_48]
0x140054f45  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054f4a  nop
0x140054f4b  lea     rcx, [rsp+98h+var_50]
0x140054f50  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054f55  mov     eax, ebx
0x140054f57  jmp     loc_140055041
0x140054f5c  mov     rcx, [rsp+98h+bstrString]; String
0x140054f61  call    cs:__imp__wtof
0x140054f67  movsd   [rsp+98h+var_38], xmm0
0x140054f6d  lea     rdx, [rsp+98h+var_38]
0x140054f72  mov     rcx, r14
0x140054f75  call    ?push_back@?$vector@PEAU_D3DRECT@@V?$allocator@PEAU_D3DRECT@@@std@@@std@@QEAAXAEBQEAU_D3DRECT@@@Z; std::vector<_D3DRECT *>::push_back(_D3DRECT * const &)
0x140054f7a  lea     rcx, [rsp+98h+var_48]
0x140054f7f  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x140054f84  mov     rcx, [rsp+98h+var_50]
0x140054f89  mov     rax, [rcx]
0x140054f8c  lea     rdx, [rsp+98h+var_48]
0x140054f91  mov     rax, [rax+48h]
0x140054f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054f9a  test    eax, eax
0x140054f9c  jns     short loc_140054FFB
0x140054f9e  lea     rcx, aCannotGetTheNe; "cannot get the next node in a list"
0x140054fa5  mov     [rsp+98h+var_68], rcx
0x140054faa  mov     [rsp+98h+var_70], rdi
0x140054faf  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054fb6  mov     [rsp+98h+var_78], rcx
0x140054fbb  mov     r9, [rsp+98h+var_50]
0x140054fc0  mov     r8d, eax
0x140054fc3  mov     edx, 669h
0x140054fc8  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054fcf  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054fd4  mov     ebx, eax
0x140054fd6  mov     rcx, [rsp+98h+bstrString]; bstrString
0x140054fdb  call    cs:__imp_SysFreeString
0x140054fe1  nop
0x140054fe2  lea     rcx, [rsp+98h+var_48]
0x140054fe7  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054fec  nop
0x140054fed  lea     rcx, [rsp+98h+var_50]
0x140054ff2  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054ff7  mov     eax, ebx
0x140054ff9  jmp     short loc_140055041
0x140054ffb  mov     rcx, [rsp+98h+bstrString]; bstrString
0x140055000  call    cs:__imp_SysFreeString
0x140055006  jmp     loc_140054EB5
0x14005500b  mov     ebx, [rsp+98h+var_58]
0x14005500f  lea     rcx, [rsp+98h+var_48]
0x140055014  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055019  nop
0x14005501a  lea     rcx, [rsp+98h+var_50]
0x14005501f  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055024  mov     eax, ebx
0x140055026  jmp     short loc_140055041
0x140055028  lea     rcx, [rsp+98h+var_48]
0x14005502d  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055032  nop
0x140055033  lea     rcx, [rsp+98h+var_50]
0x140055038  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x14005503d  mov     eax, [rsp+98h+var_58]
0x140055041  add     rsp, 78h
0x140055045  pop     r14
0x140055047  pop     rdi
0x140055048  pop     rsi
0x140055049  pop     rbx
0x14005504a  retn
```
