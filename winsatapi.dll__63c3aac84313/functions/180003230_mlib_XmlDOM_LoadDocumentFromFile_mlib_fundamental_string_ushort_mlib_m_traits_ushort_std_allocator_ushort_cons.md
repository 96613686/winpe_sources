# mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)

- ea: `0x180003230`
- end: `0x180003541`
- name: `?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z`
- size: `785`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001a70`
- `0x18002cfdc`

## callees

- `0x180001a34`
- `0x180003230`
- `0x1800049bc`
- `0x18000782c`
- `0x180013e58`
- `0x180013ec8`
- `0x1800171e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003372`
- `OLEAUT32!__imp_SysAllocString` at `0x180003372`
- `OLEAUT32!__imp_VariantInit` at `0x18000334e`
- `OLEAUT32!__imp_VariantInit` at `0x18000334e`
- `OLEAUT32!__imp_VariantClear` at `0x180003360`
- `OLEAUT32!__imp_VariantClear` at `0x18000340e`
- `OLEAUT32!__imp_VariantClear` at `0x18000347c`
- `OLEAUT32!__imp_VariantClear` at `0x1800034e3`
- `OLEAUT32!__imp_VariantClear` at `0x180003513`
- `OLEAUT32!__imp_VariantClear` at `0x180003360`
- `OLEAUT32!__imp_VariantClear` at `0x18000340e`
- `OLEAUT32!__imp_VariantClear` at `0x18000347c`
- `OLEAUT32!__imp_VariantClear` at `0x1800034e3`
- `OLEAUT32!__imp_VariantClear` at `0x180003513`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000330d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000330d`

## string_xrefs

- `0x1800033fc`: `base\winsat\mlib\mxmldom.cpp`
- `0x18000346a`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800034d1`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800033db`: `cannot create an IXMLDOMDocument2 document`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall mlib::XmlDOM::LoadDocumentFromFile(__int64 a1, char *a2, __int64 a3)
{
  const OLECHAR *v7; // r14
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  LPVOID v13; // rax
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v15; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF
  __int16 v17; // [rsp+C8h] [rbp+48h] BYREF

  ppv = 0;
  v17 = 0;
  if ( dword_18004E6A4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18004E6A4);
    if ( dword_18004E6A4 == -1 )
    {
      byte_18004E6A0 = *a2;
      Init_thread_footer(&dword_18004E6A4);
    }
  }
  *(_QWORD *)a2 = 0;
  if ( mlib::XmlDOM::fInitialized )
    goto LABEL_7;
  mlib::XmlDOM::clsIDDocument = 0;
  mlib::XmlDOM::clsIDSchema = 0;
  if ( mlib::XmlDOM::CheckMSXMLVersion() )
  {
    mlib::XmlDOM::fInitialized = 1;
LABEL_7:
    if ( CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv) >= 0 )
    {
      VariantInit(&pvarg);
      v7 = *(const OLECHAR **)(*(_QWORD *)a1 + 24LL);
      VariantClear(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(v7);
      if ( !pvarg.llVal && v7 )
      {
        pvarg.vt = 10;
        pvarg.lVal = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
      v15 = pvarg;
      v8 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v15, &v17);
      if ( v8 >= 0 )
      {
        if ( v17 )
        {
          v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
          if ( v11 >= 0 )
          {
            v13 = ppv;
            ppv = 0;
            *(_QWORD *)a2 = v13;
            VariantClear(&pvarg);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
            return 0;
          }
          else
          {
            v12 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    246,
                    v11,
                    (_DWORD)ppv,
                    (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                    a3,
                    (__int64)L"cannot set the 'preserve white space' flag");
            VariantClear(&pvarg);
            if ( ppv )
              (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
            return v12;
          }
        }
        else
        {
          v10 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  235,
                  -2147467259,
                  (_DWORD)ppv,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a3,
                  (__int64)L"cannot load document from file '%s'",
                  *(_QWORD *)(*(_QWORD *)a1 + 24LL),
                  -2);
          VariantClear(&pvarg);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
          return v10;
        }
      }
      else
      {
        v9 = mlib::XmlDOM::ReportCOMError_w(
               (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
               230,
               v8,
               0,
               (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               a3,
               (__int64)L"cannot create an IXMLDOMDocument2 document");
        VariantClear(&pvarg);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
        return v9;
      }
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
      return 2147500037LL;
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180003230  mov     rax, rsp
0x180003233  mov     [rax+20h], r9b
0x180003237  push    rbp
0x180003238  push    rdi
0x180003239  push    r12
0x18000323b  push    r14
0x18000323d  push    r15
0x18000323f  mov     rbp, rsp
0x180003242  sub     rsp, 80h
0x180003249  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180003251  mov     [rax+8], rbx
0x180003255  mov     [rax+18h], rsi
0x180003259  mov     rsi, r8
0x18000325c  mov     rbx, rdx
0x18000325f  mov     rdi, rcx
0x180003262  xor     r15d, r15d
0x180003265  mov     [rbp+arg_8], r15
0x180003269  mov     [rbp+arg_18], r15w
0x18000326e  mov     edx, cs:_tls_index
0x180003274  mov     rax, gs:58h
0x18000327d  mov     ecx, 4
0x180003282  mov     rax, [rax+rdx*8]
0x180003286  mov     eax, [rcx+rax]
0x180003289  cmp     cs:dword_18004E6A4, eax
0x18000328f  jle     short loc_1800032BB
0x180003291  lea     rcx, dword_18004E6A4
0x180003298  call    _Init_thread_header
0x18000329d  cmp     cs:dword_18004E6A4, 0FFFFFFFFh
0x1800032a4  jnz     short loc_1800032BB
0x1800032a6  movzx   eax, byte ptr [rbx]
0x1800032a9  mov     cs:byte_18004E6A0, al
0x1800032af  lea     rcx, dword_18004E6A4
0x1800032b6  call    _Init_thread_footer
0x1800032bb  mov     [rbx], r15
0x1800032be  cmp     cs:?fInitialized@XmlDOM@mlib@@0_NA, 0; bool mlib::XmlDOM::fInitialized
0x1800032c5  jnz     short loc_1800032EB
0x1800032c7  xorps   xmm0, xmm0
0x1800032ca  movups  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x1800032d1  xorps   xmm1, xmm1
0x1800032d4  movups  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x1800032db  call    ?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ; mlib::XmlDOM::CheckMSXMLVersion(void)
0x1800032e0  test    al, al
0x1800032e2  jz      short loc_18000332A
0x1800032e4  mov     cs:?fInitialized@XmlDOM@mlib@@0_NA, 1; bool mlib::XmlDOM::fInitialized
0x1800032eb  lea     rax, [rbp+arg_8]
0x1800032ef  mov     [rsp+80h+ppv], rax; ppv
0x1800032f4  lea     r12, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1800032fb  mov     r9, r12; riid
0x1800032fe  xor     edx, edx; pUnkOuter
0x180003300  mov     r8d, 1; dwClsContext
0x180003306  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x18000330d  call    cs:__imp_CoCreateInstance
0x180003313  test    eax, eax
0x180003315  jns     short loc_18000334A
0x180003317  lea     rcx, [rbp+arg_8]
0x18000331b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003320  mov     eax, 80004005h
0x180003325  jmp     loc_180003525
0x18000332a  mov     rcx, [rbp+arg_8]
0x18000332e  test    rcx, rcx
0x180003331  jz      short loc_180003340
0x180003333  mov     rax, [rcx]
0x180003336  mov     rax, [rax+10h]
0x18000333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333f  nop
0x180003340  mov     eax, 80004005h
0x180003345  jmp     loc_180003525
0x18000334a  lea     rcx, [rbp+pvarg]; pvarg
0x18000334e  call    cs:__imp_VariantInit
0x180003354  nop
0x180003355  mov     rax, [rdi]
0x180003358  mov     r14, [rax+18h]
0x18000335c  lea     rcx, [rbp+pvarg]; pvarg
0x180003360  call    cs:__imp_VariantClear
0x180003366  mov     eax, 8
0x18000336b  mov     word ptr [rbp+pvarg], ax
0x18000336f  mov     rcx, r14; psz
0x180003372  call    cs:__imp_SysAllocString
0x180003378  mov     dword ptr [rbp+pvarg+8], eax
0x18000337b  mov     rcx, rax
0x18000337e  sar     rcx, 20h
0x180003382  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x180003385  test    rax, rax
0x180003388  jnz     short loc_1800033AA
0x18000338a  test    r14, r14
0x18000338d  jz      short loc_1800033AA
0x18000338f  mov     eax, 0Ah
0x180003394  mov     word ptr [rbp+pvarg], ax
0x180003398  mov     dword ptr [rbp+pvarg+8], 8007000Eh
0x18000339f  mov     ecx, 8007000Eh; int
0x1800033a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800033aa  mov     rcx, [rbp+arg_8]
0x1800033ae  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800033b2  movaps  [rbp+var_20], xmm0
0x1800033b6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800033bb  movsd   [rbp+var_10], xmm1
0x1800033c0  mov     rax, [rcx]
0x1800033c3  lea     r8, [rbp+arg_18]
0x1800033c7  lea     rdx, [rbp+var_20]
0x1800033cb  mov     rax, [rax+1D0h]
0x1800033d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d7  test    eax, eax
0x1800033d9  jns     short loc_180003432
0x1800033db  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x1800033e2  mov     [rsp+80h+var_50], rcx
0x1800033e7  mov     [rsp+80h+var_58], rsi
0x1800033ec  mov     [rsp+80h+ppv], r12
0x1800033f1  xor     r9d, r9d
0x1800033f4  mov     r8d, eax
0x1800033f7  mov     edx, 0E6h
0x1800033fc  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180003403  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180003408  mov     ebx, eax
0x18000340a  lea     rcx, [rbp+pvarg]; pvarg
0x18000340e  call    cs:__imp_VariantClear
0x180003414  nop
0x180003415  mov     rcx, [rbp+arg_8]
0x180003419  test    rcx, rcx
0x18000341c  jz      short loc_18000342B
0x18000341e  mov     rdx, [rcx]
0x180003421  mov     rax, [rdx+10h]
0x180003425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342a  nop
0x18000342b  mov     eax, ebx
0x18000342d  jmp     loc_180003525
0x180003432  cmp     [rbp+arg_18], 0
0x180003437  jnz     short loc_180003493
0x180003439  mov     rax, [rdi]
0x18000343c  mov     rcx, [rax+18h]
0x180003440  mov     [rsp+80h+var_48], rcx
0x180003445  lea     rax, aCannotLoadDocu; "cannot load document from file '%s'"
0x18000344c  mov     [rsp+80h+var_50], rax
0x180003451  mov     [rsp+80h+var_58], rsi
0x180003456  mov     [rsp+80h+ppv], r12
0x18000345b  mov     r9, [rbp+arg_8]
0x18000345f  mov     edx, 0EBh
0x180003464  mov     r8d, 80004005h
0x18000346a  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180003471  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180003476  mov     ebx, eax
0x180003478  lea     rcx, [rbp+pvarg]; pvarg
0x18000347c  call    cs:__imp_VariantClear
0x180003482  nop
0x180003483  lea     rcx, [rbp+arg_8]
0x180003487  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000348c  mov     eax, ebx
0x18000348e  jmp     loc_180003525
0x180003493  mov     rcx, [rbp+arg_8]
0x180003497  mov     rax, [rcx]
0x18000349a  mov     edx, 0FFFFFFFFh
0x18000349f  mov     rax, [rax+240h]
0x1800034a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ab  test    eax, eax
0x1800034ad  jns     short loc_180003504
0x1800034af  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x1800034b6  mov     [rsp+80h+var_50], rcx
0x1800034bb  mov     [rsp+80h+var_58], rsi
0x1800034c0  mov     [rsp+80h+ppv], r12
0x1800034c5  mov     r9, [rbp+arg_8]
0x1800034c9  mov     r8d, eax
0x1800034cc  mov     edx, 0F6h
0x1800034d1  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1800034d8  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1800034dd  mov     ebx, eax
0x1800034df  lea     rcx, [rbp+pvarg]; pvarg
0x1800034e3  call    cs:__imp_VariantClear
0x1800034e9  nop
0x1800034ea  mov     rcx, [rbp+arg_8]
0x1800034ee  test    rcx, rcx
0x1800034f1  jz      short loc_180003500
0x1800034f3  mov     rdx, [rcx]
0x1800034f6  mov     rax, [rdx+10h]
0x1800034fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ff  nop
0x180003500  mov     eax, ebx
0x180003502  jmp     short loc_180003525
0x180003504  mov     rax, [rbp+arg_8]
0x180003508  mov     [rbp+arg_8], r15
0x18000350c  mov     [rbx], rax
0x18000350f  lea     rcx, [rbp+pvarg]; pvarg
0x180003513  call    cs:__imp_VariantClear
0x180003519  nop
0x18000351a  lea     rcx, [rbp+arg_8]
0x18000351e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003523  xor     eax, eax
0x180003525  lea     r11, [rsp+80h+var_s0]
0x18000352d  mov     rbx, [r11+30h]
0x180003531  mov     rsi, [r11+40h]
0x180003535  mov     rsp, r11
0x180003538  pop     r15
0x18000353a  pop     r14
0x18000353c  pop     r12
0x18000353e  pop     rdi
0x18000353f  pop     rbp
0x180003540  retn
```
