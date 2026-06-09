# UnBCL::File::MoveEx(UnBCL::String const *,UnBCL::String const *,ulong)

- ea: `0x18003c680`
- end: `0x18003c958`
- name: `?MoveEx@File@UnBCL@@SAXPEBVString@2@0K@Z`
- size: `728`
- prototype: `static void(const struct UnBCL::String *, const struct UnBCL::String *, unsigned int)`
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
- `0x18003c680`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x18005bda0`
- `0x180060150`
- `0x1800641a0`
- `0x180064340`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x18003c783`
- `KERNEL32!MoveFileExW` at `0x18003c783`
- `KERNEL32!GetLastError` at `0x18003c8a6`
- `KERNEL32!GetLastError` at `0x18003c8a6`

## string_xrefs

- `0x18003c8d6`: ` move to `
- `0x18003c7e7`: `void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)`
- `0x18003c832`: `void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)`
- `0x18003c882`: `void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)`
- `0x18003c934`: `void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)`
- `0x18003c81e`: `null srcpath or destpath to File::MoveEx`
- `0x18003c7d3`: `empty srcpath or destpath to File::MoveEx`
- `0x18003c869`: `source file to File::MoveEx not found`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall UnBCL::File::MoveEx(const struct UnBCL::String *a1, const struct UnBCL::String *a2, DWORD a3)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v6; // rax
  struct UnBCL::String *v7; // rax
  struct UnBCL::String *v8; // rax
  __int64 v9; // rax
  struct UnBCL::String *v10; // rax
  LPCWSTR *v11; // rbx
  struct UnBCL::String *v12; // rsi
  UnBCL::ArgumentException *v13; // rax
  __int64 v14; // rax
  UnBCL::ArgumentNullException *v15; // rax
  __int64 v16; // rax
  UnBCL::Win32Exception *v17; // rax
  __int64 v18; // rax
  DWORD LastError; // edi
  __int64 v20; // rax
  const unsigned __int16 *InnerList; // rbx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  struct UnBCL::String *v24; // rax
  UnBCL::Win32Exception *v25; // rbx
  const struct UnBCL::String *v26; // rax
  __int64 v27; // rax
  void **v28; // [rsp+28h] [rbp-48h] BYREF
  struct UnBCL::String *v29; // [rsp+30h] [rbp-40h]
  void **v30; // [rsp+38h] [rbp-38h] BYREF
  struct UnBCL::String *v31; // [rsp+40h] [rbp-30h]
  void **v32; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v33[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+A0h] [rbp+30h] BYREF
  UnBCL::ArgumentNullException *v35; // [rsp+B8h] [rbp+48h]

  if ( !a1 || !a2 )
  {
    v15 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v35 = v15;
    if ( v15 )
      v16 = UnBCL::ArgumentNullException::ArgumentNullException(v15, L"null srcpath or destpath to File::MoveEx");
    else
      v16 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) || !**((_WORD **)a2 + 2) )
  {
    v13 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v35 = v13;
    if ( v13 )
      v14 = UnBCL::ArgumentException::ArgumentException(v13, L"empty srcpath or destpath to File::MoveEx");
    else
      v14 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  v6 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v28, FullPath);
  v7 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v6 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v30, v7);
  v28 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v28);
  v8 = UnBCL::Path::GetFullPath(a2);
  v9 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v32, v8);
  v10 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v9 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v28, v10);
  v32 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v32);
  v11 = (LPCWSTR *)v31;
  UnBCL::Path::CheckPathTooLong(v31);
  v12 = v29;
  UnBCL::Path::CheckPathTooLong(v29);
  if ( !(unsigned int)UnBCL::File::Exists((const struct UnBCL::String *)v11) )
  {
    v17 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v35 = v17;
    if ( v17 )
      v18 = UnBCL::Win32Exception::Win32Exception(v17, 2u, L"source file to File::MoveEx not found");
    else
      v18 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !MoveFileExW(v11[2], *((LPCWSTR *)v12 + 2), a3) )
  {
    LastError = GetLastError();
    v20 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v28);
    InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v20);
    v22 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v30);
    v23 = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v22);
    v24 = UnBCL::String::Concat(v23, L" move to ", InnerList);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)&v32, v24);
    v25 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v35 = v25;
    if ( v25 )
    {
      v26 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)v33 + *(int *)(v33[0] + 4LL));
      v27 = UnBCL::Win32Exception::Win32Exception(v25, LastError, v26);
    }
    else
    {
      v27 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v27,
                         "void __cdecl UnBCL::File::MoveEx(const class UnBCL::String *,const class UnBCL::String *,unsigned long)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v28 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v28);
  v30 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v30);
}

```

## disassembly

```asm
0x18003c680  mov     rax, rsp
0x18003c683  push    rbp
0x18003c684  push    rsi
0x18003c685  push    rdi
0x18003c686  push    r14
0x18003c688  push    r15
0x18003c68a  mov     rbp, rsp
0x18003c68d  sub     rsp, 70h
0x18003c691  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18003c699  mov     [rax+10h], rbx
0x18003c69d  mov     edi, r8d
0x18003c6a0  mov     rbx, rdx
0x18003c6a3  xor     r14d, r14d
0x18003c6a6  test    rcx, rcx
0x18003c6a9  jz      loc_18003C80B
0x18003c6af  test    rdx, rdx
0x18003c6b2  jz      loc_18003C80B
0x18003c6b8  mov     rax, [rcx+10h]
0x18003c6bc  cmp     [rax], r14w
0x18003c6c0  jz      loc_18003C7C0
0x18003c6c6  mov     rax, [rdx+10h]
0x18003c6ca  cmp     [rax], r14w
0x18003c6ce  jz      loc_18003C7C0
0x18003c6d4  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003c6d9  mov     rdx, rax
0x18003c6dc  lea     rcx, [rbp+var_48]
0x18003c6e0  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c6e5  nop
0x18003c6e6  lea     edx, [r14+1]; int
0x18003c6ea  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003c6ee  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003c6f3  mov     rdx, rax
0x18003c6f6  lea     rcx, [rbp+var_38]
0x18003c6fa  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c6ff  nop
0x18003c700  lea     r15, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003c707  mov     [rbp+var_48], r15
0x18003c70b  lea     rcx, [rbp+var_48]
0x18003c70f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c714  mov     rcx, rbx; struct UnBCL::String *
0x18003c717  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003c71c  mov     rdx, rax
0x18003c71f  lea     rcx, [rbp+var_28]
0x18003c723  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c728  nop
0x18003c729  lea     edx, [r14+1]; int
0x18003c72d  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003c731  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003c736  mov     rdx, rax
0x18003c739  lea     rcx, [rbp+var_48]
0x18003c73d  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c742  nop
0x18003c743  mov     [rbp+var_28], r15
0x18003c747  lea     rcx, [rbp+var_28]
0x18003c74b  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c750  mov     rbx, [rbp+var_30]
0x18003c754  mov     rcx, rbx; struct UnBCL::String *
0x18003c757  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003c75c  mov     rsi, [rbp+var_40]
0x18003c760  mov     rcx, rsi; struct UnBCL::String *
0x18003c763  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003c768  mov     rcx, rbx; struct UnBCL::String *
0x18003c76b  call    ?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18003c770  test    eax, eax
0x18003c772  jz      loc_18003C856
0x18003c778  mov     r8d, edi; dwFlags
0x18003c77b  mov     rdx, [rsi+10h]; lpNewFileName
0x18003c77f  mov     rcx, [rbx+10h]; lpExistingFileName
0x18003c783  call    cs:__imp_MoveFileExW
0x18003c789  test    eax, eax
0x18003c78b  jz      loc_18003C8A6
0x18003c791  mov     [rbp+var_48], r15
0x18003c795  lea     rcx, [rbp+var_48]
0x18003c799  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c79e  nop
0x18003c79f  mov     [rbp+var_38], r15
0x18003c7a3  lea     rcx, [rbp+var_38]
0x18003c7a7  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c7ac  mov     rbx, [rsp+70h+arg_8]
0x18003c7b4  add     rsp, 70h
0x18003c7b8  pop     r15
0x18003c7ba  pop     r14
0x18003c7bc  pop     rdi
0x18003c7bd  pop     rsi
0x18003c7be  pop     rbp
0x18003c7bf  retn
0x18003c7c0  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c7c5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c7ca  mov     [rbp+arg_18], rax
0x18003c7ce  test    rax, rax
0x18003c7d1  jz      short loc_18003C7E4
0x18003c7d3  lea     rdx, aEmptySrcpathOr_1; "empty srcpath or destpath to File::Move"...
0x18003c7da  mov     rcx, rax; this
0x18003c7dd  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003c7e2  jmp     short loc_18003C7E7
0x18003c7e4  mov     rax, r14
0x18003c7e7  lea     rdx, aVoidCdeclUnbcl_138; "void __cdecl UnBCL::File::MoveEx(const "...
0x18003c7ee  mov     rcx, rax
0x18003c7f1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c7f6  mov     [rbp+pExceptionObject], rax
0x18003c7fa  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003c801  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c805  call    _CxxThrowException_0
0x18003c80b  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c810  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c815  mov     [rbp+arg_18], rax
0x18003c819  test    rax, rax
0x18003c81c  jz      short loc_18003C82F
0x18003c81e  lea     rdx, aNullSrcpathOrD_0; "null srcpath or destpath to File::MoveE"...
0x18003c825  mov     rcx, rax; this
0x18003c828  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003c82d  jmp     short loc_18003C832
0x18003c82f  mov     rax, r14
0x18003c832  lea     rdx, aVoidCdeclUnbcl_138; "void __cdecl UnBCL::File::MoveEx(const "...
0x18003c839  mov     rcx, rax
0x18003c83c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c841  mov     [rbp+pExceptionObject], rax
0x18003c845  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003c84c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c850  call    _CxxThrowException_0
0x18003c856  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c85b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c860  mov     [rbp+arg_18], rax
0x18003c864  test    rax, rax
0x18003c867  jz      short loc_18003C87F
0x18003c869  lea     r8, aSourceFileToFi_0; "source file to File::MoveEx not found"
0x18003c870  mov     edx, 2; dwMessageId
0x18003c875  mov     rcx, rax; this
0x18003c878  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003c87d  jmp     short loc_18003C882
0x18003c87f  mov     rax, r14
0x18003c882  lea     rdx, aVoidCdeclUnbcl_138; "void __cdecl UnBCL::File::MoveEx(const "...
0x18003c889  mov     rcx, rax
0x18003c88c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c891  mov     [rbp+pExceptionObject], rax
0x18003c895  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003c89c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c8a0  call    _CxxThrowException_0
0x18003c8a6  call    cs:__imp_GetLastError
0x18003c8ac  mov     edi, eax
0x18003c8ae  lea     rcx, [rbp+var_48]
0x18003c8b2  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c8b7  mov     rcx, rax
0x18003c8ba  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003c8bf  mov     rbx, rax
0x18003c8c2  lea     rcx, [rbp+var_38]
0x18003c8c6  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c8cb  mov     rcx, rax
0x18003c8ce  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003c8d3  mov     r8, rbx; unsigned __int16 *
0x18003c8d6  lea     rdx, aMoveTo; " move to "
0x18003c8dd  mov     rcx, rax; unsigned __int16 *
0x18003c8e0  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18003c8e5  mov     rdx, rax; struct UnBCL::String *
0x18003c8e8  mov     r8d, 1
0x18003c8ee  lea     rcx, [rbp+var_28]; this
0x18003c8f2  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18003c8f7  nop
0x18003c8f8  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c8fd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c902  mov     rbx, rax
0x18003c905  mov     [rbp+arg_18], rax
0x18003c909  test    rax, rax
0x18003c90c  jz      short loc_18003C931
0x18003c90e  mov     rcx, [rbp+var_20]
0x18003c912  movsxd  rdx, dword ptr [rcx+4]
0x18003c916  lea     rcx, [rbp+var_20]
0x18003c91a  add     rcx, rdx
0x18003c91d  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c922  mov     r8, rax; struct UnBCL::String *
0x18003c925  mov     edx, edi; dwMessageId
0x18003c927  mov     rcx, rbx; this
0x18003c92a  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003c92f  jmp     short loc_18003C934
0x18003c931  mov     rax, r14
0x18003c934  lea     rdx, aVoidCdeclUnbcl_138; "void __cdecl UnBCL::File::MoveEx(const "...
0x18003c93b  mov     rcx, rax
0x18003c93e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c943  mov     [rbp+pExceptionObject], rax
0x18003c947  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003c94e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c952  call    _CxxThrowException_0
```
