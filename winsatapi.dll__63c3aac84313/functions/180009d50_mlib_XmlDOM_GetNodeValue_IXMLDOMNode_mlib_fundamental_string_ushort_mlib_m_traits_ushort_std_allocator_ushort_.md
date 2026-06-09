# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180009d50`
- end: `0x18000a05e`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z`
- size: `782`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007930`
- `0x180008ce0`
- `0x18000a070`
- `0x18000a310`
- `0x18000a3cc`
- `0x18002ce54`
- `0x18002cf40`

## callees

- `0x180001a34`
- `0x180006c60`
- `0x18000782c`
- `0x180009d50`
- `0x180013220`
- `0x180013290`
- `0x180013fb6`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009e27`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e30`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e27`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e30`

## string_xrefs

- `0x180009f5a`: `base\winsat\mlib\mxmldom.cpp`
- `0x180009fae`: `base\winsat\mlib\mxmldom.cpp`
- `0x18000a002`: `base\winsat\mlib\mxmldom.cpp`
- `0x180009fd8`: `cannot get text for an XML node`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, __int64 a4, int a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v11; // rax
  __int64 v12; // rdx
  int v13; // edi
  _QWORD *v14; // rbx
  bool v15; // zf
  void *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  __int64 v24; // [rsp+40h] [rbp-58h] BYREF
  __int64 v25; // [rsp+48h] [rbp-50h] BYREF
  _QWORD *v26[9]; // [rsp+50h] [rbp-48h] BYREF

  v26[1] = (_QWORD *)-2LL;
  v24 = 0;
  v25 = 0;
  v9 = operator new(0x28u);
  v10 = v9;
  if ( !v9 )
    std::_Xbad_alloc();
  v26[0] = v9;
  v9[2] = 1;
  v9[3] = 0;
  *v9 = 0;
  v9[1] = 0;
  v11 = operator new(2u);
  if ( !v11 )
    std::_Xbad_alloc();
  v10[3] = v11;
  if ( *v10 )
    memcpy_0(v11, 0, 2LL * *v10);
  v12 = v10[3];
  if ( v12 )
    *(_WORD *)(v12 + 2LL * *v10) = 0;
  v26[0] = v10;
  v13 = mlib::XmlDOM::SelectXml(a1, a2, v26, &v24, 0);
  v14 = v26[0];
  v15 = v26[0][2]-- == 1;
  if ( v15 && v14 )
  {
    v16 = (void *)v14[3];
    if ( v16 )
      operator delete(v16);
    operator delete(v14);
  }
  if ( v13 < 0 )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    return (unsigned int)v13;
  }
  else
  {
    a5 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &a5);
    if ( v17 < 0 )
    {
      v21 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1717,
              v17,
              v24,
              (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot get the length of list");
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      return v21;
    }
    if ( a5 <= 0 )
    {
      v19 = -2147467259;
      if ( a3 )
        v19 = 0;
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 72LL))(v24, &v25);
      if ( v18 < 0 )
      {
        v22 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1726,
                v18,
                v24,
                (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                0,
                (__int64)L"cannot get the next node in a list");
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        return v22;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 208LL))(v25, a4);
      if ( v19 < 0 )
      {
        v23 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1734,
                v19,
                v25,
                (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                0,
                (__int64)L"cannot get text for an XML node");
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        return v23;
      }
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x180009d50  push    rbx
0x180009d52  push    rsi
0x180009d53  push    rdi
0x180009d54  push    r12
0x180009d56  push    r14
0x180009d58  push    r15
0x180009d5a  sub     rsp, 68h
0x180009d5e  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFEh
0x180009d67  mov     r14, r9
0x180009d6a  movzx   r15d, r8b
0x180009d6e  mov     rdi, rdx
0x180009d71  mov     rsi, rcx
0x180009d74  xor     r12d, r12d
0x180009d77  mov     [rsp+98h+var_58], r12
0x180009d7c  mov     [rsp+98h+var_50], r12
0x180009d81  mov     ecx, 28h ; '('; Size
0x180009d86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d8b  mov     rbx, rax
0x180009d8e  test    rax, rax
0x180009d91  jz      loc_180009F24
0x180009d97  mov     [rsp+98h+var_48], rax
0x180009d9c  mov     qword ptr [rax+10h], 1
0x180009da4  mov     [rax+18h], r12
0x180009da8  mov     [rax], r12
0x180009dab  mov     [rax+8], r12
0x180009daf  mov     ecx, 2; Size
0x180009db4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009db9  test    rax, rax
0x180009dbc  jz      loc_180009F2A
0x180009dc2  mov     [rbx+18h], rax
0x180009dc6  mov     r8, [rbx]
0x180009dc9  test    r8, r8
0x180009dcc  jz      short loc_180009DDB
0x180009dce  add     r8, r8; Size
0x180009dd1  xor     edx, edx; Src
0x180009dd3  mov     rcx, rax; void *
0x180009dd6  call    memcpy_0
0x180009ddb  mov     rdx, [rbx+18h]
0x180009ddf  test    rdx, rdx
0x180009de2  jz      short loc_180009DEC
0x180009de4  mov     rcx, [rbx]
0x180009de7  mov     [rdx+rcx*2], r12w
0x180009dec  mov     [rsp+98h+var_48], rbx
0x180009df1  mov     [rsp+98h+var_78], r12
0x180009df6  lea     r9, [rsp+98h+var_58]
0x180009dfb  lea     r8, [rsp+98h+var_48]
0x180009e00  mov     rdx, rdi
0x180009e03  mov     rcx, rsi
0x180009e06  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180009e0b  mov     edi, eax
0x180009e0d  mov     rbx, [rsp+98h+var_48]
0x180009e12  sub     qword ptr [rbx+10h], 1
0x180009e17  jnz     short loc_180009E36
0x180009e19  test    rbx, rbx
0x180009e1c  jz      short loc_180009E36
0x180009e1e  mov     rcx, [rbx+18h]
0x180009e22  test    rcx, rcx
0x180009e25  jz      short loc_180009E2D
0x180009e27  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009e2d  mov     rcx, rbx
0x180009e30  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009e36  test    edi, edi
0x180009e38  js      loc_180009EF2
0x180009e3e  mov     [rsp+98h+arg_20], r12d
0x180009e46  mov     rcx, [rsp+98h+var_58]
0x180009e4b  mov     rax, [rcx]
0x180009e4e  lea     rdx, [rsp+98h+arg_20]
0x180009e56  mov     rax, [rax+40h]
0x180009e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e5f  test    eax, eax
0x180009e61  js      loc_180009F30
0x180009e67  cmp     [rsp+98h+arg_20], 0
0x180009e6f  jle     loc_18000A02C
0x180009e75  mov     rcx, [rsp+98h+var_58]
0x180009e7a  mov     rax, [rcx]
0x180009e7d  lea     rdx, [rsp+98h+var_50]
0x180009e82  mov     rax, [rax+48h]
0x180009e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e8b  test    eax, eax
0x180009e8d  js      loc_180009F84
0x180009e93  mov     rcx, [rsp+98h+var_50]
0x180009e98  mov     rax, [rcx]
0x180009e9b  mov     rdx, r14
0x180009e9e  mov     rax, [rax+0D0h]
0x180009ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eaa  mov     ebx, eax
0x180009eac  test    eax, eax
0x180009eae  js      loc_180009FD8
0x180009eb4  mov     rcx, [rsp+98h+var_50]
0x180009eb9  test    rcx, rcx
0x180009ebc  jz      short loc_180009ECB
0x180009ebe  mov     rax, [rcx]
0x180009ec1  mov     rax, [rax+10h]
0x180009ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eca  nop
0x180009ecb  mov     rcx, [rsp+98h+var_58]
0x180009ed0  test    rcx, rcx
0x180009ed3  jz      short loc_180009EE2
0x180009ed5  mov     rdx, [rcx]
0x180009ed8  mov     rax, [rdx+10h]
0x180009edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee1  nop
0x180009ee2  mov     eax, ebx
0x180009ee4  add     rsp, 68h
0x180009ee8  pop     r15
0x180009eea  pop     r14
0x180009eec  pop     r12
0x180009eee  pop     rdi
0x180009eef  pop     rsi
0x180009ef0  pop     rbx
0x180009ef1  retn
0x180009ef2  mov     rcx, [rsp+98h+var_50]
0x180009ef7  test    rcx, rcx
0x180009efa  jz      short loc_180009F09
0x180009efc  mov     rax, [rcx]
0x180009eff  mov     rax, [rax+10h]
0x180009f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f08  nop
0x180009f09  mov     rcx, [rsp+98h+var_58]
0x180009f0e  test    rcx, rcx
0x180009f11  jz      short loc_180009F20
0x180009f13  mov     rax, [rcx]
0x180009f16  mov     rax, [rax+10h]
0x180009f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f1f  nop
0x180009f20  mov     eax, edi
0x180009f22  jmp     short loc_180009EE4
0x180009f24  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009f2a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009f30  lea     rcx, aCannotGetTheLe; "cannot get the length of list"
0x180009f37  mov     [rsp+98h+var_68], rcx
0x180009f3c  mov     [rsp+98h+var_70], r12
0x180009f41  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x180009f48  mov     [rsp+98h+var_78], rcx
0x180009f4d  mov     r9, [rsp+98h+var_58]
0x180009f52  mov     r8d, eax
0x180009f55  mov     edx, 6B5h
0x180009f5a  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180009f61  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180009f66  mov     ebx, eax
0x180009f68  lea     rcx, [rsp+98h+var_50]
0x180009f6d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009f72  nop
0x180009f73  lea     rcx, [rsp+98h+var_58]
0x180009f78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009f7d  mov     eax, ebx
0x180009f7f  jmp     loc_180009EE4
0x180009f84  lea     rcx, aCannotGetTheNe; "cannot get the next node in a list"
0x180009f8b  mov     [rsp+98h+var_68], rcx
0x180009f90  mov     [rsp+98h+var_70], r12
0x180009f95  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x180009f9c  mov     [rsp+98h+var_78], rcx
0x180009fa1  mov     r9, [rsp+98h+var_58]
0x180009fa6  mov     r8d, eax
0x180009fa9  mov     edx, 6BEh
0x180009fae  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180009fb5  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180009fba  mov     ebx, eax
0x180009fbc  lea     rcx, [rsp+98h+var_50]
0x180009fc1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009fc6  nop
0x180009fc7  lea     rcx, [rsp+98h+var_58]
0x180009fcc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009fd1  mov     eax, ebx
0x180009fd3  jmp     loc_180009EE4
0x180009fd8  lea     rax, aCannotGetTextF; "cannot get text for an XML node"
0x180009fdf  mov     [rsp+98h+var_68], rax
0x180009fe4  mov     [rsp+98h+var_70], r12
0x180009fe9  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180009ff0  mov     [rsp+98h+var_78], rax
0x180009ff5  mov     r9, [rsp+98h+var_50]
0x180009ffa  mov     r8d, ebx
0x180009ffd  mov     edx, 6C6h
0x18000a002  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000a009  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18000a00e  mov     ebx, eax
0x18000a010  lea     rcx, [rsp+98h+var_50]
0x18000a015  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a01a  nop
0x18000a01b  lea     rcx, [rsp+98h+var_58]
0x18000a020  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a025  mov     eax, ebx
0x18000a027  jmp     loc_180009EE4
0x18000a02c  mov     ebx, 80004005h
0x18000a031  test    r15b, r15b
0x18000a034  cmovnz  ebx, r12d
0x18000a038  jmp     loc_180009EB4
0x18000a03d  lea     rcx, [rsp+98h+var_50]
0x18000a042  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a047  nop
0x18000a048  lea     rcx, [rsp+98h+var_58]
0x18000a04d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a052  mov     eax, [rsp+98h+arg_20]
0x18000a059  jmp     loc_180009EE4
```
