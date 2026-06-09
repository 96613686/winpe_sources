# mlib::XmlDOM::GetNodesText(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x14005497c`
- end: `0x140054d06`
- name: `?GetNodesText@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAV42@@Z`
- size: `906`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002c7b4`
- `0x14002fb28`
- `0x14002fc4c`
- `0x140032c20`
- `0x140034990`

## callees

- `0x140005d78`
- `0x140005f10`
- `0x14000712c`
- `0x140016300`
- `0x140016588`
- `0x140016d04`
- `0x1400343e4`
- `0x140040afc`
- `0x140042ec0`
- `0x14005497c`
- `0x1400557f4`
- `0x140056088`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140054c75`
- `KERNEL32!GetLastError` at `0x140054c75`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a21`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a98`
- `OLEAUT32!__imp_SysFreeString` at `0x140054abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b3f`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ba6`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c29`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c85`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ce3`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a21`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a98`
- `OLEAUT32!__imp_SysFreeString` at `0x140054abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b3f`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ba6`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c29`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c85`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ce3`
- `OLEAUT32!__imp_SysStringLen` at `0x140054c52`
- `OLEAUT32!__imp_SysStringLen` at `0x140054c52`

## string_xrefs

- `0x140054a0e`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054a85`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054b21`: `base\winsat\mlib\mxmldom.cpp`
- `0x140054c00`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400549e6`: `cannot select XML based on an XPATH expression`
- `0x140054bd6`: `cannot get text for an XML node`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall mlib::XmlDOM::GetNodesText(int a1, int a2, _QWORD *a3, __int64 a4)
{
  int v8; // ebx
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // ebx
  UINT v18; // eax
  unsigned int v19; // ebx
  int v20; // [rsp+40h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-60h] BYREF
  __int64 v22; // [rsp+50h] [rbp-58h] BYREF
  __int64 v23; // [rsp+58h] [rbp-50h] BYREF
  __int64 v24; // [rsp+60h] [rbp-48h] BYREF
  __int64 v25; // [rsp+68h] [rbp-40h] BYREF
  mlib::MSError *v26; // [rsp+70h] [rbp-38h] BYREF

  v22 = 0;
  bstrString = 0;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v25,
      &qword_14012B318);
    v8 = mlib::XmlDOM::SelectXml(a1, a2, (unsigned int)&v25, (unsigned int)&v22, a4);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v25);
    if ( v8 >= 0 )
    {
      v20 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v20);
      if ( v11 >= 0 )
      {
        if ( v20 )
        {
          v23 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, &v23);
          if ( v13 >= 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v24);
            v15 = v20;
            if ( (__int64)(a3[2] - *a3) >> 3 > (unsigned __int64)v20 )
              v15 = (__int64)(a3[2] - *a3) >> 3;
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::reserve(
              a3,
              v15);
            while ( 1 )
            {
              if ( !v23 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
                ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v23);
                SysFreeString(bstrString);
                ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
                return 0;
              }
              v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 208LL))(v23, &bstrString);
              if ( v16 < 0 )
                break;
              if ( bstrString && (v18 = SysStringLen(bstrString)) != 0 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign_from_buf(
                  &v24,
                  bstrString,
                  v18);
                GetLastError();
              }
              else
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)&v24);
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::push_back(
                a3,
                &v24);
              SysFreeString(bstrString);
              bstrString = 0;
              ATL::CComPtrBase<IXMLDOMNode>::Release(&v23);
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, &v23);
            }
            v17 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    1528,
                    v16,
                    v23,
                    (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                    a4,
                    (__int64)L"cannot get text for an XML node");
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v23);
            SysFreeString(bstrString);
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
            result = v17;
          }
          else
          {
            v14 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    1515,
                    v13,
                    v22,
                    (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                    a4,
                    (__int64)L"cannot get next node in a list");
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v23);
            SysFreeString(bstrString);
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
            result = v14;
          }
        }
        else
        {
          SysFreeString(bstrString);
          ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
          result = 0;
        }
      }
      else
      {
        v12 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1503,
                v11,
                v22,
                (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                a4,
                (__int64)L"cannot get the length of list");
        SysFreeString(bstrString);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
        result = v12;
      }
    }
    else
    {
      v9 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             1489,
             v8,
             a1,
             (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
             a4,
             (__int64)L"cannot select XML based on an XPATH expression");
      SysFreeString(bstrString);
      ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
      result = v9;
    }
  }
  catch ( std::bad_alloc )
  {
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1546,
            -2147024882,
            0,
            (__int64)qword_1401C3B08,
            a4,
            (__int64)L"cannot allocate memory");
    goto LABEL_24;
  }
  catch ( mlib::MSError *v26 )
  {
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1551,
            *(_DWORD *)v26,
            0,
            (__int64)qword_1401C3B08,
            0,
            0);
    goto LABEL_24;
  }
  catch ( ... )
  {
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1555,
            -2147467259,
            0,
            (__int64)qword_1401C3B08,
            0,
            0);
LABEL_24:
    v19 = v20;
    SysFreeString(bstrString);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x14005497c  mov     rax, rsp
0x14005497f  mov     [rax+20h], r9
0x140054983  push    rbx
0x140054984  push    rsi
0x140054985  push    rdi
0x140054986  push    r14
0x140054988  sub     rsp, 88h
0x14005498f  mov     rsi, r9
0x140054992  mov     r14, r8
0x140054995  mov     rbx, rdx
0x140054998  mov     rdi, rcx
0x14005499b  mov     qword ptr [rax-58h], 0
0x1400549a3  mov     qword ptr [rax-60h], 0
0x1400549ab  lea     rdx, qword_14012B318
0x1400549b2  lea     rcx, [rax-40h]
0x1400549b6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400549bb  nop
0x1400549bc  mov     [rsp+0A8h+var_88], rsi
0x1400549c1  lea     r9, [rsp+0A8h+var_58]
0x1400549c6  lea     r8, [rsp+0A8h+var_40]
0x1400549cb  mov     rdx, rbx
0x1400549ce  mov     rcx, rdi
0x1400549d1  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1400549d6  mov     ebx, eax
0x1400549d8  lea     rcx, [rsp+0A8h+var_40]
0x1400549dd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400549e2  test    ebx, ebx
0x1400549e4  jns     short loc_140054A39
0x1400549e6  lea     rax, aCannotSelectXm; "cannot select XML based on an XPATH exp"...
0x1400549ed  mov     [rsp+0A8h+var_78], rax
0x1400549f2  mov     [rsp+0A8h+var_80], rsi
0x1400549f7  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1400549fe  mov     [rsp+0A8h+var_88], rcx
0x140054a03  mov     r9, rdi
0x140054a06  mov     r8d, ebx
0x140054a09  mov     edx, 5D1h
0x140054a0e  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054a15  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054a1a  mov     ebx, eax
0x140054a1c  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054a21  call    cs:__imp_SysFreeString
0x140054a27  nop
0x140054a28  lea     rcx, [rsp+0A8h+var_58]
0x140054a2d  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054a32  mov     eax, ebx
0x140054a34  jmp     loc_140054CF6
0x140054a39  mov     [rsp+0A8h+var_68], 0
0x140054a41  mov     rcx, [rsp+0A8h+var_58]
0x140054a46  mov     rax, [rcx]
0x140054a49  lea     rdx, [rsp+0A8h+var_68]
0x140054a4e  mov     rax, [rax+40h]
0x140054a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054a57  test    eax, eax
0x140054a59  jns     short loc_140054AB0
0x140054a5b  lea     rcx, aCannotGetTheLe_0; "cannot get the length of list"
0x140054a62  mov     [rsp+0A8h+var_78], rcx
0x140054a67  mov     [rsp+0A8h+var_80], rsi
0x140054a6c  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054a73  mov     [rsp+0A8h+var_88], rcx
0x140054a78  mov     r9, [rsp+0A8h+var_58]
0x140054a7d  mov     r8d, eax
0x140054a80  mov     edx, 5DFh
0x140054a85  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054a8c  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054a91  mov     ebx, eax
0x140054a93  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054a98  call    cs:__imp_SysFreeString
0x140054a9e  nop
0x140054a9f  lea     rcx, [rsp+0A8h+var_58]
0x140054aa4  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054aa9  mov     eax, ebx
0x140054aab  jmp     loc_140054CF6
0x140054ab0  cmp     [rsp+0A8h+var_68], 0
0x140054ab5  jnz     short loc_140054AD4
0x140054ab7  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054abc  call    cs:__imp_SysFreeString
0x140054ac2  nop
0x140054ac3  lea     rcx, [rsp+0A8h+var_58]
0x140054ac8  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054acd  xor     eax, eax
0x140054acf  jmp     loc_140054CF6
0x140054ad4  mov     [rsp+0A8h+var_50], 0
0x140054add  mov     rcx, [rsp+0A8h+var_58]
0x140054ae2  mov     rax, [rcx]
0x140054ae5  lea     rdx, [rsp+0A8h+var_50]
0x140054aea  mov     rax, [rax+48h]
0x140054aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054af3  test    eax, eax
0x140054af5  jns     short loc_140054B57
0x140054af7  lea     rcx, aCannotGetNextN; "cannot get next node in a list"
0x140054afe  mov     [rsp+0A8h+var_78], rcx
0x140054b03  mov     [rsp+0A8h+var_80], rsi
0x140054b08  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x140054b0f  mov     [rsp+0A8h+var_88], rcx
0x140054b14  mov     r9, [rsp+0A8h+var_58]
0x140054b19  mov     r8d, eax
0x140054b1c  mov     edx, 5EBh
0x140054b21  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054b28  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054b2d  mov     ebx, eax
0x140054b2f  lea     rcx, [rsp+0A8h+var_50]
0x140054b34  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054b39  nop
0x140054b3a  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054b3f  call    cs:__imp_SysFreeString
0x140054b45  nop
0x140054b46  lea     rcx, [rsp+0A8h+var_58]
0x140054b4b  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054b50  mov     eax, ebx
0x140054b52  jmp     loc_140054CF6
0x140054b57  lea     rcx, [rsp+0A8h+var_48]
0x140054b5c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140054b61  nop
0x140054b62  movsxd  rdx, [rsp+0A8h+var_68]
0x140054b67  mov     rax, [r14+10h]
0x140054b6b  sub     rax, [r14]
0x140054b6e  sar     rax, 3
0x140054b72  cmp     rax, rdx
0x140054b75  cmova   rdx, rax
0x140054b79  mov     rcx, r14
0x140054b7c  call    ?reserve@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@QEAAX_K@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::reserve(unsigned __int64)
0x140054b81  mov     rcx, [rsp+0A8h+var_50]
0x140054b86  test    rcx, rcx
0x140054b89  jnz     short loc_140054BBE
0x140054b8b  lea     rcx, [rsp+0A8h+var_48]
0x140054b90  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140054b95  nop
0x140054b96  lea     rcx, [rsp+0A8h+var_50]
0x140054b9b  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054ba0  nop
0x140054ba1  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054ba6  call    cs:__imp_SysFreeString
0x140054bac  nop
0x140054bad  lea     rcx, [rsp+0A8h+var_58]
0x140054bb2  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054bb7  xor     eax, eax
0x140054bb9  jmp     loc_140054CF6
0x140054bbe  mov     rax, [rcx]
0x140054bc1  lea     rdx, [rsp+0A8h+bstrString]
0x140054bc6  mov     rax, [rax+0D0h]
0x140054bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054bd2  test    eax, eax
0x140054bd4  jns     short loc_140054C41
0x140054bd6  lea     rcx, aCannotGetTextF_0; "cannot get text for an XML node"
0x140054bdd  mov     [rsp+0A8h+var_78], rcx
0x140054be2  mov     [rsp+0A8h+var_80], rsi
0x140054be7  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x140054bee  mov     [rsp+0A8h+var_88], rcx
0x140054bf3  mov     r9, [rsp+0A8h+var_50]
0x140054bf8  mov     r8d, eax
0x140054bfb  mov     edx, 5F8h
0x140054c00  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140054c07  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140054c0c  mov     ebx, eax
0x140054c0e  lea     rcx, [rsp+0A8h+var_48]
0x140054c13  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140054c18  nop
0x140054c19  lea     rcx, [rsp+0A8h+var_50]
0x140054c1e  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054c23  nop
0x140054c24  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054c29  call    cs:__imp_SysFreeString
0x140054c2f  nop
0x140054c30  lea     rcx, [rsp+0A8h+var_58]
0x140054c35  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054c3a  mov     eax, ebx
0x140054c3c  jmp     loc_140054CF6
0x140054c41  mov     rcx, [rsp+0A8h+bstrString]; pbstr
0x140054c46  test    rcx, rcx
0x140054c49  jnz     short loc_140054C52
0x140054c4b  lea     rcx, [rsp+0A8h+var_48]
0x140054c50  jmp     short loc_140054C61
0x140054c52  call    cs:__imp_SysStringLen
0x140054c58  lea     rcx, [rsp+0A8h+var_48]
0x140054c5d  test    eax, eax
0x140054c5f  jnz     short loc_140054C68
0x140054c61  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x140054c66  jmp     short loc_140054C7B
0x140054c68  mov     r8d, eax
0x140054c6b  mov     rdx, [rsp+0A8h+bstrString]
0x140054c70  call    ?assign_from_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEBG_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign_from_buf(ushort const *,unsigned __int64)
0x140054c75  call    cs:__imp_GetLastError
0x140054c7b  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054c80  test    rcx, rcx
0x140054c83  jz      short loc_140054C94
0x140054c85  call    cs:__imp_SysFreeString
0x140054c8b  mov     [rsp+0A8h+bstrString], 0
0x140054c94  lea     rdx, [rsp+0A8h+var_48]
0x140054c99  mov     rcx, r14
0x140054c9c  call    ?push_back@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@QEAAX$$QEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::push_back(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &&)
0x140054ca1  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054ca6  call    cs:__imp_SysFreeString
0x140054cac  mov     [rsp+0A8h+bstrString], 0
0x140054cb5  lea     rcx, [rsp+0A8h+var_50]
0x140054cba  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x140054cbf  mov     rcx, [rsp+0A8h+var_58]
0x140054cc4  mov     rax, [rcx]
0x140054cc7  lea     rdx, [rsp+0A8h+var_50]
0x140054ccc  mov     rax, [rax+48h]
0x140054cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054cd5  jmp     loc_140054B81
0x140054cda  mov     ebx, [rsp+0A8h+var_68]
0x140054cde  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140054ce3  call    cs:__imp_SysFreeString
0x140054ce9  nop
0x140054cea  lea     rcx, [rsp+0A8h+var_58]
0x140054cef  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140054cf4  mov     eax, ebx
0x140054cf6  add     rsp, 88h
0x140054cfd  pop     r14
0x140054cff  pop     rdi
0x140054d00  pop     rsi
0x140054d01  pop     rbx
0x140054d02  retn
0x140054d03  jmp     short loc_140054CDA
```
