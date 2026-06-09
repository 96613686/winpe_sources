# UnBCL::File::Delete(UnBCL::String const *)

- ea: `0x18003b5f0`
- end: `0x18003b731`
- name: `?Delete@File@UnBCL@@SAXPEBVString@2@@Z`
- size: `321`
- prototype: `void __fastcall(const struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180029980`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f90`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011570`
- `0x180025720`
- `0x18002bca0`
- `0x18003b5f0`
- `0x18003b740`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x180064340`

## string_xrefs

- `0x18003b6c6`: `void __cdecl UnBCL::File::Delete(const class UnBCL::String *)`
- `0x18003b70d`: `void __cdecl UnBCL::File::Delete(const class UnBCL::String *)`
- `0x18003b6fd`: `null path to File::Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UnBCL::File::Delete(const struct UnBCL::String *a1)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v3; // rax
  struct UnBCL::String *v4; // rax
  UnBCL::Win32Exception *v5; // rax
  UnBCL::Win32Exception *v6; // rbx
  const struct UnBCL::String *v7; // rax
  UnBCL::ArgumentNullException *v8; // rax
  void **v9; // [rsp+28h] [rbp-28h] BYREF
  struct UnBCL::String *v10; // [rsp+30h] [rbp-20h]
  _QWORD v11[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+60h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v13; // [rsp+68h] [rbp+18h]

  if ( !a1 )
  {
    v8 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v13 = v8;
    if ( v8 )
      v8 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                             v8,
                                             L"null path to File::Delete");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "void __cdecl UnBCL::File::Delete(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  v3 = UnBCL::_::MakeSmartPtr<UnBCL::String>(v11, FullPath);
  v4 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v3 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v9, v4);
  v11[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v11);
  UnBCL::Path::CheckPathTooLong(v10);
  if ( (unsigned int)UnBCL::Directory::Exists(a1) )
  {
    v5 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v6 = v5;
    v13 = v5;
    if ( v5 )
    {
      v7 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v9);
      v5 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v6, 5u, v7);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "void __cdecl UnBCL::File::Delete(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  UnBCL::File::DeleteInternal((LPCWSTR *)v10, 0);
  v9 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v9);
}

```

## disassembly

```asm
0x18003b5f0  push    rbp
0x18003b5f2  mov     rbp, rsp
0x18003b5f5  sub     rsp, 50h
0x18003b5f9  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18003b601  mov     [rsp+50h+arg_10], rbx
0x18003b606  mov     [rsp+50h+arg_18], rdi
0x18003b60b  mov     rbx, rcx
0x18003b60e  test    rcx, rcx
0x18003b611  jz      loc_18003B6EA
0x18003b617  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003b61c  mov     rdx, rax
0x18003b61f  lea     rcx, [rbp+var_18]
0x18003b623  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b628  nop
0x18003b629  mov     edx, 1; int
0x18003b62e  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003b632  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003b637  mov     rdx, rax
0x18003b63a  lea     rcx, [rbp+var_28]
0x18003b63e  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b643  nop
0x18003b644  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003b64b  mov     [rbp+var_18], rdi
0x18003b64f  lea     rcx, [rbp+var_18]
0x18003b653  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b658  mov     rcx, [rbp+var_20]; struct UnBCL::String *
0x18003b65c  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003b661  mov     rcx, rbx; struct UnBCL::String *
0x18003b664  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18003b669  test    eax, eax
0x18003b66b  jnz     short loc_18003B696
0x18003b66d  xor     edx, edx; int
0x18003b66f  mov     rcx, [rbp+var_20]; struct UnBCL::String *
0x18003b673  call    ?DeleteInternal@File@UnBCL@@CAXPEBVString@2@H@Z; UnBCL::File::DeleteInternal(UnBCL::String const *,int)
0x18003b678  nop
0x18003b679  mov     [rbp+var_28], rdi
0x18003b67d  lea     rcx, [rbp+var_28]
0x18003b681  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b686  mov     rbx, [rsp+50h+arg_10]
0x18003b68b  mov     rdi, [rsp+50h+arg_18]
0x18003b690  add     rsp, 50h
0x18003b694  pop     rbp
0x18003b695  retn
0x18003b696  mov     ecx, 40h ; '@'; unsigned __int64
0x18003b69b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b6a0  mov     rbx, rax
0x18003b6a3  mov     [rbp+arg_8], rax
0x18003b6a7  test    rax, rax
0x18003b6aa  jz      short loc_18003B6C6
0x18003b6ac  lea     rcx, [rbp+var_28]
0x18003b6b0  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003b6b5  mov     r8, rax; struct UnBCL::String *
0x18003b6b8  mov     edx, 5; dwMessageId
0x18003b6bd  mov     rcx, rbx; this
0x18003b6c0  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003b6c5  nop
0x18003b6c6  lea     rdx, aVoidCdeclUnbcl_56; "void __cdecl UnBCL::File::Delete(const "...
0x18003b6cd  mov     rcx, rax
0x18003b6d0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003b6d5  mov     [rbp+pExceptionObject], rax
0x18003b6d9  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003b6e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b6e4  call    _CxxThrowException_0
0x18003b6ea  mov     ecx, 38h ; '8'; unsigned __int64
0x18003b6ef  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b6f4  mov     [rbp+arg_8], rax
0x18003b6f8  test    rax, rax
0x18003b6fb  jz      short loc_18003B70D
0x18003b6fd  lea     rdx, aNullPathToFile; "null path to File::Delete"
0x18003b704  mov     rcx, rax; this
0x18003b707  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003b70c  nop
0x18003b70d  lea     rdx, aVoidCdeclUnbcl_56; "void __cdecl UnBCL::File::Delete(const "...
0x18003b714  mov     rcx, rax
0x18003b717  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003b71c  mov     [rbp+pExceptionObject], rax
0x18003b720  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003b727  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b72b  call    _CxxThrowException_0
```
