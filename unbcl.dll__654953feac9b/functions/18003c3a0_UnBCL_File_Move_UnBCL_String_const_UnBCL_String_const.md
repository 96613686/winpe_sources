# UnBCL::File::Move(UnBCL::String const *,UnBCL::String const *)

- ea: `0x18003c3a0`
- end: `0x18003c672`
- name: `?Move@File@UnBCL@@SAXPEBVString@2@0@Z`
- size: `722`
- prototype: `void __fastcall(const struct UnBCL::String *, const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011570`
- `0x18001a700`
- `0x180025720`
- `0x18003c0a0`
- `0x18003c3a0`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x18005bda0`
- `0x180060150`
- `0x1800641a0`
- `0x180064340`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x18003c49c`
- `KERNEL32!MoveFileExW` at `0x18003c49c`
- `KERNEL32!GetLastError` at `0x18003c5c0`
- `KERNEL32!GetLastError` at `0x18003c5c0`

## string_xrefs

- `0x18003c501`: `void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18003c54c`: `void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18003c59c`: `void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18003c64e`: `void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18003c538`: `null srcpath or destpath to File::Move`
- `0x18003c4ed`: `empty srcpath or destpath to File::Move`
- `0x18003c583`: `source file to File::Move not found`
- `0x18003c5f0`: ` move to `

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall UnBCL::File::Move(const struct UnBCL::String *a1, const struct UnBCL::String *a2)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v4; // rax
  struct UnBCL::String *v5; // rax
  struct UnBCL::String *v6; // rax
  __int64 v7; // rax
  struct UnBCL::String *v8; // rax
  LPCWSTR *v9; // rbx
  struct UnBCL::String *v10; // rdi
  UnBCL::ArgumentException *v11; // rax
  __int64 v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  __int64 v14; // rax
  UnBCL::Win32Exception *v15; // rax
  __int64 v16; // rax
  DWORD LastError; // edi
  __int64 v18; // rax
  const unsigned __int16 *InnerList; // rbx
  __int64 v20; // rax
  const unsigned __int16 *v21; // rax
  struct UnBCL::String *v22; // rax
  UnBCL::Win32Exception *v23; // rbx
  const struct UnBCL::String *v24; // rax
  __int64 v25; // rax
  void **v26; // [rsp+28h] [rbp-48h] BYREF
  struct UnBCL::String *v27; // [rsp+30h] [rbp-40h]
  void **v28; // [rsp+38h] [rbp-38h] BYREF
  struct UnBCL::String *v29; // [rsp+40h] [rbp-30h]
  void **v30; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v31[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+90h] [rbp+20h] BYREF
  UnBCL::ArgumentNullException *v33; // [rsp+A0h] [rbp+30h]

  if ( !a1 || !a2 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v33 = v13;
    if ( v13 )
      v14 = UnBCL::ArgumentNullException::ArgumentNullException(v13, L"null srcpath or destpath to File::Move");
    else
      v14 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) || !**((_WORD **)a2 + 2) )
  {
    v11 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v33 = v11;
    if ( v11 )
      v12 = UnBCL::ArgumentException::ArgumentException(v11, L"empty srcpath or destpath to File::Move");
    else
      v12 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  v4 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v26, FullPath);
  v5 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v4 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v28, v5);
  v26 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v26);
  v6 = UnBCL::Path::GetFullPath(a2);
  v7 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v30, v6);
  v8 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v7 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v26, v8);
  v30 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v30);
  v9 = (LPCWSTR *)v29;
  UnBCL::Path::CheckPathTooLong(v29);
  v10 = v27;
  UnBCL::Path::CheckPathTooLong(v27);
  if ( !(unsigned int)UnBCL::File::Exists((const struct UnBCL::String *)v9) )
  {
    v15 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v33 = v15;
    if ( v15 )
      v16 = UnBCL::Win32Exception::Win32Exception(v15, 2u, L"source file to File::Move not found");
    else
      v16 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !MoveFileExW(v9[2], *((LPCWSTR *)v10 + 2), 0) )
  {
    LastError = GetLastError();
    v18 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v26);
    InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v18);
    v20 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v28);
    v21 = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v20);
    v22 = UnBCL::String::Concat(v21, L" move to ", InnerList);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)&v30, v22);
    v23 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v33 = v23;
    if ( v23 )
    {
      v24 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)v31 + *(int *)(v31[0] + 4LL));
      v25 = UnBCL::Win32Exception::Win32Exception(v23, LastError, v24);
    }
    else
    {
      v25 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v25,
                         "void __cdecl UnBCL::File::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v26 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v26);
  v28 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v28);
}

```

## disassembly

```asm
0x18003c3a0  mov     rax, rsp
0x18003c3a3  push    rbp
0x18003c3a4  push    rdi
0x18003c3a5  push    r14
0x18003c3a7  mov     rbp, rsp
0x18003c3aa  sub     rsp, 70h
0x18003c3ae  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18003c3b6  mov     [rax+10h], rbx
0x18003c3ba  mov     [rax+20h], rsi
0x18003c3be  mov     rbx, rdx
0x18003c3c1  xor     esi, esi
0x18003c3c3  test    rcx, rcx
0x18003c3c6  jz      loc_18003C525
0x18003c3cc  test    rdx, rdx
0x18003c3cf  jz      loc_18003C525
0x18003c3d5  mov     rax, [rcx+10h]
0x18003c3d9  cmp     [rax], si
0x18003c3dc  jz      loc_18003C4DA
0x18003c3e2  mov     rax, [rdx+10h]
0x18003c3e6  cmp     [rax], si
0x18003c3e9  jz      loc_18003C4DA
0x18003c3ef  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003c3f4  mov     rdx, rax
0x18003c3f7  lea     rcx, [rbp+var_48]
0x18003c3fb  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c400  nop
0x18003c401  lea     edx, [rsi+1]; int
0x18003c404  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003c408  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003c40d  mov     rdx, rax
0x18003c410  lea     rcx, [rbp+var_38]
0x18003c414  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c419  nop
0x18003c41a  lea     r14, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003c421  mov     [rbp+var_48], r14
0x18003c425  lea     rcx, [rbp+var_48]
0x18003c429  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c42e  mov     rcx, rbx; struct UnBCL::String *
0x18003c431  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003c436  mov     rdx, rax
0x18003c439  lea     rcx, [rbp+var_28]
0x18003c43d  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c442  nop
0x18003c443  lea     edx, [rsi+1]; int
0x18003c446  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003c44a  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003c44f  mov     rdx, rax
0x18003c452  lea     rcx, [rbp+var_48]
0x18003c456  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c45b  nop
0x18003c45c  mov     [rbp+var_28], r14
0x18003c460  lea     rcx, [rbp+var_28]
0x18003c464  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c469  mov     rbx, [rbp+var_30]
0x18003c46d  mov     rcx, rbx; struct UnBCL::String *
0x18003c470  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003c475  mov     rdi, [rbp+var_40]
0x18003c479  mov     rcx, rdi; struct UnBCL::String *
0x18003c47c  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003c481  mov     rcx, rbx; struct UnBCL::String *
0x18003c484  call    ?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18003c489  test    eax, eax
0x18003c48b  jz      loc_18003C570
0x18003c491  xor     r8d, r8d; dwFlags
0x18003c494  mov     rdx, [rdi+10h]; lpNewFileName
0x18003c498  mov     rcx, [rbx+10h]; lpExistingFileName
0x18003c49c  call    cs:__imp_MoveFileExW
0x18003c4a2  test    eax, eax
0x18003c4a4  jz      loc_18003C5C0
0x18003c4aa  mov     [rbp+var_48], r14
0x18003c4ae  lea     rcx, [rbp+var_48]
0x18003c4b2  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c4b7  nop
0x18003c4b8  mov     [rbp+var_38], r14
0x18003c4bc  lea     rcx, [rbp+var_38]
0x18003c4c0  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c4c5  lea     r11, [rsp+70h+var_s0]
0x18003c4ca  mov     rbx, [r11+28h]
0x18003c4ce  mov     rsi, [r11+38h]
0x18003c4d2  mov     rsp, r11
0x18003c4d5  pop     r14
0x18003c4d7  pop     rdi
0x18003c4d8  pop     rbp
0x18003c4d9  retn
0x18003c4da  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c4df  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c4e4  mov     [rbp+arg_10], rax
0x18003c4e8  test    rax, rax
0x18003c4eb  jz      short loc_18003C4FE
0x18003c4ed  lea     rdx, aEmptySrcpathOr; "empty srcpath or destpath to File::Move"
0x18003c4f4  mov     rcx, rax; this
0x18003c4f7  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003c4fc  jmp     short loc_18003C501
0x18003c4fe  mov     rax, rsi
0x18003c501  lea     rdx, aVoidCdeclUnbcl_143; "void __cdecl UnBCL::File::Move(const cl"...
0x18003c508  mov     rcx, rax
0x18003c50b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c510  mov     [rbp+pExceptionObject], rax
0x18003c514  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003c51b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c51f  call    _CxxThrowException_0
0x18003c525  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c52a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c52f  mov     [rbp+arg_10], rax
0x18003c533  test    rax, rax
0x18003c536  jz      short loc_18003C549
0x18003c538  lea     rdx, aNullSrcpathOrD; "null srcpath or destpath to File::Move"
0x18003c53f  mov     rcx, rax; this
0x18003c542  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003c547  jmp     short loc_18003C54C
0x18003c549  mov     rax, rsi
0x18003c54c  lea     rdx, aVoidCdeclUnbcl_143; "void __cdecl UnBCL::File::Move(const cl"...
0x18003c553  mov     rcx, rax
0x18003c556  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c55b  mov     [rbp+pExceptionObject], rax
0x18003c55f  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003c566  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c56a  call    _CxxThrowException_0
0x18003c570  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c575  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c57a  mov     [rbp+arg_10], rax
0x18003c57e  test    rax, rax
0x18003c581  jz      short loc_18003C599
0x18003c583  lea     r8, aSourceFileToFi; "source file to File::Move not found"
0x18003c58a  mov     edx, 2; dwMessageId
0x18003c58f  mov     rcx, rax; this
0x18003c592  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003c597  jmp     short loc_18003C59C
0x18003c599  mov     rax, rsi
0x18003c59c  lea     rdx, aVoidCdeclUnbcl_143; "void __cdecl UnBCL::File::Move(const cl"...
0x18003c5a3  mov     rcx, rax
0x18003c5a6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c5ab  mov     [rbp+pExceptionObject], rax
0x18003c5af  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003c5b6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c5ba  call    _CxxThrowException_0
0x18003c5c0  call    cs:__imp_GetLastError
0x18003c5c6  mov     edi, eax
0x18003c5c8  lea     rcx, [rbp+var_48]
0x18003c5cc  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c5d1  mov     rcx, rax
0x18003c5d4  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003c5d9  mov     rbx, rax
0x18003c5dc  lea     rcx, [rbp+var_38]
0x18003c5e0  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c5e5  mov     rcx, rax
0x18003c5e8  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003c5ed  mov     r8, rbx; unsigned __int16 *
0x18003c5f0  lea     rdx, aMoveTo; " move to "
0x18003c5f7  mov     rcx, rax; unsigned __int16 *
0x18003c5fa  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18003c5ff  mov     rdx, rax; struct UnBCL::String *
0x18003c602  mov     r8d, 1
0x18003c608  lea     rcx, [rbp+var_28]; this
0x18003c60c  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18003c611  nop
0x18003c612  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c617  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c61c  mov     rbx, rax
0x18003c61f  mov     [rbp+arg_10], rax
0x18003c623  test    rax, rax
0x18003c626  jz      short loc_18003C64B
0x18003c628  mov     rcx, [rbp+var_20]
0x18003c62c  movsxd  rdx, dword ptr [rcx+4]
0x18003c630  lea     rcx, [rbp+var_20]
0x18003c634  add     rcx, rdx
0x18003c637  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c63c  mov     r8, rax; struct UnBCL::String *
0x18003c63f  mov     edx, edi; dwMessageId
0x18003c641  mov     rcx, rbx; this
0x18003c644  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003c649  jmp     short loc_18003C64E
0x18003c64b  mov     rax, rsi
0x18003c64e  lea     rdx, aVoidCdeclUnbcl_143; "void __cdecl UnBCL::File::Move(const cl"...
0x18003c655  mov     rcx, rax
0x18003c658  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c65d  mov     [rbp+pExceptionObject], rax
0x18003c661  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003c668  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c66c  call    _CxxThrowException_0
```
