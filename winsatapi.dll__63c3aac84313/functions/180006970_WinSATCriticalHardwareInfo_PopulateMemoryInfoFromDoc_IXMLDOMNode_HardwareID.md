# WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(IXMLDOMNode *,HardwareID)

- ea: `0x180006970`
- end: `0x180006c5a`
- name: `?PopulateMemoryInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z`
- size: `746`
- prototype: `int __high(struct IXMLDOMNode *, enum HardwareID)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ad10`

## callees

- `0x180001a34`
- `0x180006970`
- `0x180006c60`
- `0x1800071d0`
- `0x180007220`
- `0x18000739c`
- `0x180007460`
- `0x180013220`
- `0x180013290`
- `0x180013fa3`
- `0x180013fb6`
- `0x180026004`
- `0x18002ce54`
- `0x180031010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006c1b`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006c1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b95`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b95`

## string_xrefs

- `0x180006a8b`: `SystemConfig/Memory/DIMM`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(__int64 a1, __int64 a2, int a3)
{
  wchar_t *XPathForHardwareID; // rdx
  int v6; // r8d
  int NodeValue; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  void *v10; // rax
  __int64 v11; // r8
  __int64 *v12; // rax
  __int64 *v13; // rbx
  __int64 v14; // rcx
  const wchar_t *i; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // rdx
  int v20; // edi
  _QWORD *v21; // rbx
  bool v22; // zf
  void *v23; // rcx
  _QWORD *v24; // rbx
  void *v25; // rcx
  OLECHAR *v27; // [rsp+20h] [rbp-50h]
  unsigned __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v29[3]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v30[4]; // [rsp+50h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+B0h] [rbp+40h] BYREF
  __int64 *v32; // [rsp+B8h] [rbp+48h] BYREF

  pExceptionObject = a3;
  v29[1] = (_QWORD *)-2LL;
  v28 = 0;
  XPathForHardwareID = (wchar_t *)GetXPathForHardwareID(8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v32,
    XPathForHardwareID);
  NodeValue = mlib::XmlDOM::GetNodeValue(a2, (int)&v32, v6, (int)&v28, v27);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v32);
  if ( NodeValue < 0 )
    return (unsigned int)NodeValue;
  *(_QWORD *)(a1 + 40) = RoundTotalPhysMemSize(v28);
  v32 = 0;
  v8 = operator new(0x28u);
  v9 = v8;
  if ( !v8 )
    std::_Xbad_alloc();
  v29[0] = v8;
  v8[2] = 1;
  v8[3] = 0;
  *v8 = 0;
  v8[1] = 0;
  v10 = operator new(2u);
  if ( !v10 )
    std::_Xbad_alloc();
  v9[3] = v10;
  if ( *v9 )
    memcpy_0(v10, 0, 2LL * *v9);
  v11 = v9[3];
  if ( v11 )
    *(_WORD *)(v11 + 2LL * *v9) = 0;
  v29[0] = v9;
  v12 = (__int64 *)operator new(0x28u);
  v13 = v12;
  if ( !v12 )
    std::_Xbad_alloc();
  v29[2] = v12;
  *v12 = 0;
  v12[1] = 0;
  v12[2] = 1;
  v12[3] = 0;
  v14 = 0x10000;
  for ( i = L"SystemConfig/Memory/DIMM"; ; ++i )
  {
    if ( !v14 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v14;
  }
  v16 = i - L"SystemConfig/Memory/DIMM";
  *v13 = v16;
  v13[1] = v16;
  v17 = v16 + 1;
  v18 = 0;
  if ( v17 )
  {
    if ( v17 > 0x7FFFFFFFFFFFFFFFLL || (v18 = operator new(2 * v17)) == 0 )
      std::_Xbad_alloc();
  }
  v13[3] = (__int64)v18;
  if ( !v18 )
  {
    v28 = (unsigned __int64)"bad allocation";
    exception::exception((exception *)v30, (const char *const *)&v28, 1);
    v30[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)v30;
  }
  if ( *v13 )
    memcpy_0(v18, L"SystemConfig/Memory/DIMM", 2 * *v13);
  v19 = v13[3];
  if ( v19 )
    *(_WORD *)(v19 + 2 * *v13) = 0;
  v28 = (unsigned __int64)v13;
  v20 = mlib::XmlDOM::SelectXml(a2, (__int64)&v28, v29, &v32, 0);
  v21 = (_QWORD *)v28;
  v22 = (*(_QWORD *)(v28 + 16))-- == 1;
  if ( v22 && v21 )
  {
    v23 = (void *)v21[3];
    if ( v23 )
      operator delete(v23);
    operator delete(v21);
  }
  v24 = v29[0];
  v22 = v29[0][2]-- == 1;
  if ( v22 && v24 )
  {
    v25 = (void *)v24[3];
    if ( v25 )
      operator delete(v25);
    operator delete(v24);
  }
  if ( v20 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
    return (unsigned int)v20;
  }
  NodeValue = PopulateWinsatMemoryInfoList(v32, a1 + 56);
  if ( NodeValue < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
    return (unsigned int)NodeValue;
  }
  *(_BYTE *)(a1 + 48) = 1;
  if ( v32 )
    (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
  return 0;
}

```

## disassembly

```asm
0x180006970  mov     [rsp-28h+pExceptionObject], r8d
0x180006975  push    rbp
0x180006976  push    rsi
0x180006977  push    rdi
0x180006978  push    r14
0x18000697a  push    r15
0x18000697c  mov     rbp, rsp
0x18000697f  sub     rsp, 70h
0x180006983  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000698b  mov     [rsp+70h+arg_0], rbx
0x180006993  mov     rdi, rdx
0x180006996  mov     rsi, rcx
0x180006999  xor     r14d, r14d
0x18000699c  mov     [rbp+var_40], r14
0x1800069a0  mov     ecx, 8
0x1800069a5  call    ?GetXPathForHardwareID@@YAPEBGW4HardwareID@@@Z; GetXPathForHardwareID(HardwareID)
0x1800069aa  mov     rdx, rax
0x1800069ad  lea     rcx, [rbp+arg_18]
0x1800069b1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1800069b6  nop
0x1800069b7  lea     r9, [rbp+var_40]; int
0x1800069bb  lea     rdx, [rbp+arg_18]; int
0x1800069bf  mov     rcx, rdi; int
0x1800069c2  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_KPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,unsigned __int64 &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1800069c7  mov     ebx, eax
0x1800069c9  lea     rcx, [rbp+arg_18]
0x1800069cd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800069d2  test    ebx, ebx
0x1800069d4  js      loc_180006C53
0x1800069da  mov     rcx, [rbp+var_40]; unsigned __int64
0x1800069de  call    ?RoundTotalPhysMemSize@@YA_K_K@Z; RoundTotalPhysMemSize(unsigned __int64)
0x1800069e3  mov     [rsi+28h], rax
0x1800069e7  mov     [rbp+arg_18], r14
0x1800069eb  mov     ecx, 28h ; '('; Size
0x1800069f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069f5  mov     rbx, rax
0x1800069f8  test    rax, rax
0x1800069fb  jz      loc_180006BEA
0x180006a01  mov     [rbp+var_38], rax
0x180006a05  mov     qword ptr [rax+10h], 1
0x180006a0d  mov     [rax+18h], r14
0x180006a11  mov     [rax], r14
0x180006a14  mov     [rax+8], r14
0x180006a18  mov     ecx, 2; Size
0x180006a1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a22  test    rax, rax
0x180006a25  jz      loc_180006BF0
0x180006a2b  mov     [rbx+18h], rax
0x180006a2f  mov     r8, [rbx]
0x180006a32  test    r8, r8
0x180006a35  jz      short loc_180006A44
0x180006a37  add     r8, r8; Size
0x180006a3a  xor     edx, edx; Src
0x180006a3c  mov     rcx, rax; void *
0x180006a3f  call    memcpy_0
0x180006a44  mov     r8, [rbx+18h]
0x180006a48  test    r8, r8
0x180006a4b  jz      short loc_180006A55
0x180006a4d  mov     rdx, [rbx]
0x180006a50  mov     [r8+rdx*2], r14w
0x180006a55  mov     [rbp+var_38], rbx
0x180006a59  mov     ecx, 28h ; '('; Size
0x180006a5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a63  mov     rbx, rax
0x180006a66  test    rax, rax
0x180006a69  jz      loc_180006BF6
0x180006a6f  mov     [rbp+var_28], rax
0x180006a73  mov     [rax], r14
0x180006a76  mov     [rax+8], r14
0x180006a7a  mov     qword ptr [rax+10h], 1
0x180006a82  mov     [rax+18h], r14
0x180006a86  mov     ecx, 10000h
0x180006a8b  lea     r15, aSystemconfigMe_0; "SystemConfig/Memory/DIMM"
0x180006a92  mov     rax, r15
0x180006a95  test    rcx, rcx
0x180006a98  jz      short loc_180006AA9
0x180006a9a  cmp     word ptr [rax], 0
0x180006a9e  jz      short loc_180006ABA
0x180006aa0  add     rax, 2
0x180006aa4  dec     rcx
0x180006aa7  jmp     short loc_180006A95
0x180006aa9  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180006ab0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006ab4  call    _CxxThrowException_0
0x180006aba  sub     rax, r15
0x180006abd  sar     rax, 1
0x180006ac0  mov     [rbx], rax
0x180006ac3  mov     [rbx+8], rax
0x180006ac7  lea     rcx, [rax+1]
0x180006acb  mov     rax, r14
0x180006ace  test    rcx, rcx
0x180006ad1  jz      short loc_180006AF7
0x180006ad3  mov     rax, 7FFFFFFFFFFFFFFFh
0x180006add  cmp     rcx, rax
0x180006ae0  ja      loc_180006BFC
0x180006ae6  add     rcx, rcx; Size
0x180006ae9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006aee  test    rax, rax
0x180006af1  jz      loc_180006BFC
0x180006af7  mov     [rbx+18h], rax
0x180006afb  test    rax, rax
0x180006afe  jz      loc_180006C02
0x180006b04  mov     r8, [rbx]
0x180006b07  test    r8, r8
0x180006b0a  jz      short loc_180006B1A
0x180006b0c  add     r8, r8; Size
0x180006b0f  mov     rdx, r15; Src
0x180006b12  mov     rcx, rax; void *
0x180006b15  call    memcpy_0
0x180006b1a  mov     rdx, [rbx+18h]
0x180006b1e  test    rdx, rdx
0x180006b21  jz      short loc_180006B2B
0x180006b23  mov     rcx, [rbx]
0x180006b26  mov     [rdx+rcx*2], r14w
0x180006b2b  mov     [rbp+var_40], rbx
0x180006b2f  mov     [rsp+70h+var_50], r14
0x180006b34  lea     r9, [rbp+arg_18]
0x180006b38  lea     r8, [rbp+var_38]
0x180006b3c  lea     rdx, [rbp+var_40]
0x180006b40  mov     rcx, rdi
0x180006b43  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180006b48  mov     edi, eax
0x180006b4a  mov     rbx, [rbp+var_40]
0x180006b4e  sub     qword ptr [rbx+10h], 1
0x180006b53  jnz     short loc_180006B73
0x180006b55  test    rbx, rbx
0x180006b58  jz      short loc_180006B73
0x180006b5a  mov     rcx, [rbx+18h]
0x180006b5e  test    rcx, rcx
0x180006b61  jz      short loc_180006B69
0x180006b63  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b69  mov     rcx, rbx
0x180006b6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b72  nop
0x180006b73  mov     rbx, [rbp+var_38]
0x180006b77  sub     qword ptr [rbx+10h], 1
0x180006b7c  jnz     short loc_180006B9B
0x180006b7e  test    rbx, rbx
0x180006b81  jz      short loc_180006B9B
0x180006b83  mov     rcx, [rbx+18h]
0x180006b87  test    rcx, rcx
0x180006b8a  jz      short loc_180006B92
0x180006b8c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b92  mov     rcx, rbx
0x180006b95  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b9b  test    edi, edi
0x180006b9d  js      loc_180006C3D
0x180006ba3  lea     rdx, [rsi+38h]
0x180006ba7  mov     rcx, [rbp+arg_18]
0x180006bab  call    PopulateWinsatMemoryInfoList
0x180006bb0  mov     ebx, eax
0x180006bb2  test    eax, eax
0x180006bb4  js      loc_180006C4A
0x180006bba  mov     byte ptr [rsi+30h], 1
0x180006bbe  mov     rcx, [rbp+arg_18]
0x180006bc2  test    rcx, rcx
0x180006bc5  jz      short loc_180006BD4
0x180006bc7  mov     rax, [rcx]
0x180006bca  mov     rax, [rax+10h]
0x180006bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd3  nop
0x180006bd4  xor     eax, eax
0x180006bd6  mov     rbx, [rsp+70h+arg_0]
0x180006bde  add     rsp, 70h
0x180006be2  pop     r15
0x180006be4  pop     r14
0x180006be6  pop     rdi
0x180006be7  pop     rsi
0x180006be8  pop     rbp
0x180006be9  retn
0x180006bea  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006bf0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006bf6  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006bfc  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006c02  lea     rax, aBadAllocation; "bad allocation"
0x180006c09  mov     [rbp+var_40], rax
0x180006c0d  mov     r8d, 1
0x180006c13  lea     rdx, [rbp+var_40]
0x180006c17  lea     rcx, [rbp+var_20]
0x180006c1b  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180006c21  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006c28  mov     [rbp+var_20], rax
0x180006c2c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006c33  lea     rcx, [rbp+var_20]; pExceptionObject
0x180006c37  call    _CxxThrowException_0
0x180006c3d  lea     rcx, [rbp+arg_18]
0x180006c41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006c46  mov     eax, edi
0x180006c48  jmp     short loc_180006BD6
0x180006c4a  lea     rcx, [rbp+arg_18]
0x180006c4e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006c53  mov     eax, ebx
0x180006c55  jmp     loc_180006BD6
```
