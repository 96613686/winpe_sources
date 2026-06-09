# UnBCL::Directory::Move(UnBCL::String const *,UnBCL::String const *)

- ea: `0x18002eb20`
- end: `0x18002efcf`
- name: `?Move@Directory@UnBCL@@SAXPEBVString@2@0@Z`
- size: `1199`
- prototype: `void __fastcall(const struct UnBCL::String *, const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011570`
- `0x18001a700`
- `0x180025720`
- `0x18002bca0`
- `0x18002eb20`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x180049aa0`
- `0x18004a440`
- `0x18005bb40`
- `0x18005be50`
- `0x18005c010`
- `0x18005c180`
- `0x1800641a0`
- `0x180064340`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x18002ed25`
- `KERNEL32!MoveFileExW` at `0x18002ed25`
- `KERNEL32!GetLastError` at `0x18002ef35`
- `KERNEL32!GetLastError` at `0x18002ef35`

## string_xrefs

- `0x18002edd6`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002ee21`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002ee71`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002eec1`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002ef11`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002efab`: `void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)`
- `0x18002ee0d`: `null srcpath or destpath to Directory::Move`
- `0x18002edc2`: `empty srcpath or destpath to Directory::Move`
- `0x18002ee58`: `source and destination for move paths must be different`
- `0x18002eea8`: `source and destination for move must have same root`
- `0x18002eef8`: `root of destination path does not exist`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall UnBCL::Directory::Move(const struct UnBCL::String *a1, const struct UnBCL::String *a2)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v5; // rax
  struct UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // rax
  __int64 v8; // rax
  struct UnBCL::String *v9; // rax
  struct UnBCL::String *v10; // r14
  const unsigned __int16 **v11; // rsi
  struct UnBCL::String *v12; // rax
  struct UnBCL::String *v13; // r14
  struct UnBCL::String *v14; // r15
  struct UnBCL::String *PathRoot; // rax
  struct UnBCL::String *v16; // rax
  struct UnBCL::String *v17; // rax
  UnBCL::ArgumentException *v18; // rax
  __int64 v19; // rax
  UnBCL::ArgumentNullException *v20; // rax
  __int64 v21; // rax
  UnBCL::Win32Exception *v22; // rax
  __int64 v23; // rax
  UnBCL::Win32Exception *v24; // rax
  __int64 v25; // rax
  UnBCL::Win32Exception *v26; // rax
  __int64 v27; // rax
  DWORD LastError; // esi
  __int64 InnerList; // rbx
  __int64 v30; // rax
  struct UnBCL::String *v31; // rax
  UnBCL::Win32Exception *v32; // rbx
  const struct UnBCL::String *v33; // rax
  __int64 v34; // rax
  _QWORD v35[2]; // [rsp+28h] [rbp-69h] BYREF
  void **v36; // [rsp+38h] [rbp-59h] BYREF
  struct UnBCL::String *v37; // [rsp+40h] [rbp-51h]
  void **v38; // [rsp+48h] [rbp-49h] BYREF
  struct UnBCL::String *v39; // [rsp+50h] [rbp-41h]
  void **v40; // [rsp+58h] [rbp-39h] BYREF
  struct UnBCL::String *v41; // [rsp+60h] [rbp-31h]
  _QWORD v42[2]; // [rsp+68h] [rbp-29h] BYREF
  _QWORD v43[2]; // [rsp+78h] [rbp-19h] BYREF
  void **v44; // [rsp+88h] [rbp-9h] BYREF
  struct UnBCL::String *v45; // [rsp+90h] [rbp-1h]
  __int64 v46; // [rsp+98h] [rbp+7h]
  _BYTE v47[72]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 pExceptionObject; // [rsp+F8h] [rbp+67h] BYREF
  UnBCL::ArgumentNullException *v49; // [rsp+108h] [rbp+77h]

  v46 = -2;
  if ( !a1 || !a2 )
  {
    v20 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v49 = v20;
    if ( v20 )
      v21 = UnBCL::ArgumentNullException::ArgumentNullException(v20, L"null srcpath or destpath to Directory::Move");
    else
      v21 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v21,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) || !**((_WORD **)a2 + 2) )
  {
    v18 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v49 = v18;
    if ( v18 )
      v19 = UnBCL::ArgumentException::ArgumentException(v18, L"empty srcpath or destpath to Directory::Move");
    else
      v19 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v19,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  v5 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v36, FullPath);
  v6 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v5 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v44, v6);
  v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
  v7 = UnBCL::Path::GetFullPath(a2);
  v8 = UnBCL::_::MakeSmartPtr<UnBCL::String>(v35, v7);
  v9 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v8 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v36, v9);
  v35[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v35);
  v10 = v45;
  UnBCL::Path::CheckPathTooLong(v45);
  v11 = (const unsigned __int16 **)v37;
  UnBCL::Path::CheckPathTooLong(v37);
  v40 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  v41 = 0;
  if ( !(unsigned int)UnBCL::String::EndsWith(v10, 0x5Cu) )
    v10 = UnBCL::String::Concat(*((const unsigned __int16 **)v10 + 2), L"\\");
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v40, v10);
  v38 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  v39 = 0;
  if ( (unsigned int)UnBCL::String::EndsWith((UnBCL::String *)v11, 0x5Cu) )
    v12 = (struct UnBCL::String *)v11;
  else
    v12 = UnBCL::String::Concat(v11[2], L"\\");
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v38, v12);
  v13 = v39;
  v14 = v41;
  if ( !(unsigned int)UnBCL::String::Compare(
                        *((const unsigned __int16 **)v41 + 2),
                        *((const unsigned __int16 **)v39 + 2),
                        1) )
  {
    v22 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v49 = v22;
    if ( v22 )
      v23 = UnBCL::Win32Exception::Win32Exception(
              v22,
              0x57u,
              L"source and destination for move paths must be different");
    else
      v23 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v23,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  PathRoot = UnBCL::Path::GetPathRoot(v14);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v35, PathRoot);
  v16 = UnBCL::Path::GetPathRoot(v13);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v43, v16);
  if ( (unsigned int)UnBCL::String::Compare(
                       *(const unsigned __int16 **)(v35[1] + 16LL),
                       *(const unsigned __int16 **)(v43[1] + 16LL),
                       1) )
  {
    v24 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v49 = v24;
    if ( v24 )
      v25 = UnBCL::Win32Exception::Win32Exception(v24, 0x57u, L"source and destination for move must have same root");
    else
      v25 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v25,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v17 = UnBCL::Path::GetPathRoot((const struct UnBCL::String *)v11);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v42, v17);
  if ( !(unsigned int)UnBCL::Directory::Exists((const struct UnBCL::String *)v42[1]) )
  {
    v26 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v49 = v26;
    if ( v26 )
      v27 = UnBCL::Win32Exception::Win32Exception(v26, 3u, L"root of destination path does not exist");
    else
      v27 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v27,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !MoveFileExW(*((LPCWSTR *)a1 + 2), *((LPCWSTR *)a2 + 2), 0) )
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      LastError = 3;
    InnerList = UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(a2);
    v30 = UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(a1);
    v31 = UnBCL::String::Format(L"Exception while moving %s to %s", v30, InnerList);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v47, v31);
    v32 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v49 = v32;
    if ( v32 )
    {
      v33 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v47);
      v34 = UnBCL::Win32Exception::Win32Exception(v32, LastError, v33);
    }
    else
    {
      v34 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v34,
                         "void __cdecl UnBCL::Directory::Move(const class UnBCL::String *,const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v42[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v42);
  v43[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v43);
  v35[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v35);
  v38 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v38);
  v40 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v40);
  v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
  v44 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v44);
}

```

## disassembly

```asm
0x18002eb20  mov     rax, rsp
0x18002eb23  push    rbp
0x18002eb24  push    rsi
0x18002eb25  push    rdi
0x18002eb26  push    r12
0x18002eb28  push    r13
0x18002eb2a  push    r14
0x18002eb2c  push    r15
0x18002eb2e  lea     rbp, [rax-5Fh]
0x18002eb32  sub     rsp, 0B0h
0x18002eb39  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18002eb41  mov     [rax+10h], rbx
0x18002eb45  mov     rbx, rdx
0x18002eb48  mov     rdi, rcx
0x18002eb4b  xor     r12d, r12d
0x18002eb4e  test    rcx, rcx
0x18002eb51  jz      loc_18002EDFA
0x18002eb57  test    rdx, rdx
0x18002eb5a  jz      loc_18002EDFA
0x18002eb60  mov     rax, [rcx+10h]
0x18002eb64  cmp     [rax], r12w
0x18002eb68  jz      loc_18002EDAF
0x18002eb6e  mov     rax, [rdx+10h]
0x18002eb72  cmp     [rax], r12w
0x18002eb76  jz      loc_18002EDAF
0x18002eb7c  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002eb81  mov     rdx, rax
0x18002eb84  lea     rcx, [rbp+57h+var_B0]
0x18002eb88  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18002eb8d  nop
0x18002eb8e  lea     esi, [r12+1]
0x18002eb93  mov     edx, esi; int
0x18002eb95  mov     rcx, [rax+8]; struct UnBCL::String *
0x18002eb99  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18002eb9e  mov     rdx, rax
0x18002eba1  lea     rcx, [rbp+57h+var_60]
0x18002eba5  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ebaa  nop
0x18002ebab  lea     r13, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002ebb2  mov     [rbp+57h+var_B0], r13
0x18002ebb6  lea     rcx, [rbp+57h+var_B0]
0x18002ebba  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ebbf  mov     rcx, rbx; struct UnBCL::String *
0x18002ebc2  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002ebc7  mov     rdx, rax
0x18002ebca  lea     rcx, [rbp+57h+var_C0]
0x18002ebce  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ebd3  nop
0x18002ebd4  mov     edx, esi; int
0x18002ebd6  mov     rcx, [rax+8]; struct UnBCL::String *
0x18002ebda  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18002ebdf  mov     rdx, rax
0x18002ebe2  lea     rcx, [rbp+57h+var_B0]
0x18002ebe6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ebeb  nop
0x18002ebec  mov     [rbp+57h+var_C0], r13
0x18002ebf0  lea     rcx, [rbp+57h+var_C0]
0x18002ebf4  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ebf9  mov     r14, [rbp+57h+var_58]
0x18002ebfd  mov     rcx, r14; struct UnBCL::String *
0x18002ec00  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18002ec05  mov     rsi, [rbp+57h+var_A8]
0x18002ec09  mov     rcx, rsi; struct UnBCL::String *
0x18002ec0c  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18002ec11  mov     [rbp+57h+var_90], r13
0x18002ec15  mov     [rbp+57h+var_88], r12
0x18002ec19  lea     r15d, [r12+5Ch]
0x18002ec1e  mov     edx, r15d; unsigned __int16
0x18002ec21  mov     rcx, r14; this
0x18002ec24  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x18002ec29  test    eax, eax
0x18002ec2b  jnz     short loc_18002EC40
0x18002ec2d  lea     rdx, asc_180080A2C; "\\"
0x18002ec34  mov     rcx, [r14+10h]; unsigned __int16 *
0x18002ec38  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18002ec3d  mov     r14, rax
0x18002ec40  mov     rdx, r14
0x18002ec43  lea     rcx, [rbp+57h+var_90]
0x18002ec47  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002ec4c  mov     [rbp+57h+var_A0], r13
0x18002ec50  mov     [rbp+57h+var_98], r12
0x18002ec54  mov     edx, r15d; unsigned __int16
0x18002ec57  mov     rcx, rsi; this
0x18002ec5a  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x18002ec5f  test    eax, eax
0x18002ec61  jz      short loc_18002EC68
0x18002ec63  mov     rax, rsi
0x18002ec66  jmp     short loc_18002EC78
0x18002ec68  lea     rdx, asc_180080A2C; "\\"
0x18002ec6f  mov     rcx, [rsi+10h]; unsigned __int16 *
0x18002ec73  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18002ec78  mov     rdx, rax
0x18002ec7b  lea     rcx, [rbp+57h+var_A0]
0x18002ec7f  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002ec84  mov     r14, [rbp+57h+var_98]
0x18002ec88  mov     r15, [rbp+57h+var_88]
0x18002ec8c  mov     r8d, 1; int
0x18002ec92  mov     rdx, [r14+10h]; unsigned __int16 *
0x18002ec96  mov     rcx, [r15+10h]; unsigned __int16 *
0x18002ec9a  call    ?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x18002ec9f  test    eax, eax
0x18002eca1  jz      loc_18002EE45
0x18002eca7  mov     rcx, r15; struct UnBCL::String *
0x18002ecaa  call    ?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetPathRoot(UnBCL::String const *)
0x18002ecaf  mov     rdx, rax
0x18002ecb2  lea     rcx, [rbp+57h+var_C0]
0x18002ecb6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ecbb  nop
0x18002ecbc  mov     rcx, r14; struct UnBCL::String *
0x18002ecbf  call    ?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetPathRoot(UnBCL::String const *)
0x18002ecc4  mov     rdx, rax
0x18002ecc7  lea     rcx, [rbp+57h+var_70]
0x18002eccb  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ecd0  nop
0x18002ecd1  mov     r8d, 1; int
0x18002ecd7  mov     rdx, [rbp+57h+var_68]
0x18002ecdb  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18002ecdf  mov     rcx, [rbp+57h+var_B8]
0x18002ece3  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18002ece7  call    ?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x18002ecec  test    eax, eax
0x18002ecee  jnz     loc_18002EE95
0x18002ecf4  mov     rcx, rsi; struct UnBCL::String *
0x18002ecf7  call    ?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetPathRoot(UnBCL::String const *)
0x18002ecfc  mov     rdx, rax
0x18002ecff  lea     rcx, [rbp+57h+var_80]
0x18002ed03  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ed08  nop
0x18002ed09  mov     rcx, [rbp+57h+var_78]; struct UnBCL::String *
0x18002ed0d  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18002ed12  test    eax, eax
0x18002ed14  jz      loc_18002EEE5
0x18002ed1a  xor     r8d, r8d; dwFlags
0x18002ed1d  mov     rdx, [rbx+10h]; lpNewFileName
0x18002ed21  mov     rcx, [rdi+10h]; lpExistingFileName
0x18002ed25  call    cs:__imp_MoveFileExW
0x18002ed2b  test    eax, eax
0x18002ed2d  jz      loc_18002EF35
0x18002ed33  mov     [rbp+57h+var_80], r13
0x18002ed37  lea     rcx, [rbp+57h+var_80]
0x18002ed3b  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed40  nop
0x18002ed41  mov     [rbp+57h+var_70], r13
0x18002ed45  lea     rcx, [rbp+57h+var_70]
0x18002ed49  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed4e  nop
0x18002ed4f  mov     [rbp+57h+var_C0], r13
0x18002ed53  lea     rcx, [rbp+57h+var_C0]
0x18002ed57  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed5c  nop
0x18002ed5d  mov     [rbp+57h+var_A0], r13
0x18002ed61  lea     rcx, [rbp+57h+var_A0]
0x18002ed65  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed6a  nop
0x18002ed6b  mov     [rbp+57h+var_90], r13
0x18002ed6f  lea     rcx, [rbp+57h+var_90]
0x18002ed73  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed78  nop
0x18002ed79  mov     [rbp+57h+var_B0], r13
0x18002ed7d  lea     rcx, [rbp+57h+var_B0]
0x18002ed81  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed86  nop
0x18002ed87  mov     [rbp+57h+var_60], r13
0x18002ed8b  lea     rcx, [rbp+57h+var_60]
0x18002ed8f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ed94  mov     rbx, [rsp+0E0h+arg_8]
0x18002ed9c  add     rsp, 0B0h
0x18002eda3  pop     r15
0x18002eda5  pop     r14
0x18002eda7  pop     r13
0x18002eda9  pop     r12
0x18002edab  pop     rdi
0x18002edac  pop     rsi
0x18002edad  pop     rbp
0x18002edae  retn
0x18002edaf  mov     ecx, 38h ; '8'; unsigned __int64
0x18002edb4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002edb9  mov     [rbp+57h+arg_10], rax
0x18002edbd  test    rax, rax
0x18002edc0  jz      short loc_18002EDD3
0x18002edc2  lea     rdx, aEmptySrcpathOr_2; "empty srcpath or destpath to Directory:"...
0x18002edc9  mov     rcx, rax; this
0x18002edcc  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18002edd1  jmp     short loc_18002EDD6
0x18002edd3  mov     rax, r12
0x18002edd6  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002eddd  mov     rcx, rax
0x18002ede0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ede5  mov     [rbp+57h+pExceptionObject], rax
0x18002ede9  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18002edf0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002edf4  call    _CxxThrowException_0
0x18002edfa  mov     ecx, 38h ; '8'; unsigned __int64
0x18002edff  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ee04  mov     [rbp+57h+arg_10], rax
0x18002ee08  test    rax, rax
0x18002ee0b  jz      short loc_18002EE1E
0x18002ee0d  lea     rdx, aNullSrcpathOrD_1; "null srcpath or destpath to Directory::"...
0x18002ee14  mov     rcx, rax; this
0x18002ee17  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18002ee1c  jmp     short loc_18002EE21
0x18002ee1e  mov     rax, r12
0x18002ee21  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002ee28  mov     rcx, rax
0x18002ee2b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ee30  mov     [rbp+57h+pExceptionObject], rax
0x18002ee34  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18002ee3b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002ee3f  call    _CxxThrowException_0
0x18002ee45  mov     ecx, 40h ; '@'; unsigned __int64
0x18002ee4a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ee4f  mov     [rbp+57h+arg_10], rax
0x18002ee53  test    rax, rax
0x18002ee56  jz      short loc_18002EE6E
0x18002ee58  lea     r8, aSourceAndDesti_0; "source and destination for move paths m"...
0x18002ee5f  mov     edx, 57h ; 'W'; dwMessageId
0x18002ee64  mov     rcx, rax; this
0x18002ee67  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18002ee6c  jmp     short loc_18002EE71
0x18002ee6e  mov     rax, r12
0x18002ee71  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002ee78  mov     rcx, rax
0x18002ee7b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ee80  mov     [rbp+57h+pExceptionObject], rax
0x18002ee84  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002ee8b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002ee8f  call    _CxxThrowException_0
0x18002ee95  mov     ecx, 40h ; '@'; unsigned __int64
0x18002ee9a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ee9f  mov     [rbp+57h+arg_10], rax
0x18002eea3  test    rax, rax
0x18002eea6  jz      short loc_18002EEBE
0x18002eea8  lea     r8, aSourceAndDesti; "source and destination for move must ha"...
0x18002eeaf  mov     edx, 57h ; 'W'; dwMessageId
0x18002eeb4  mov     rcx, rax; this
0x18002eeb7  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18002eebc  jmp     short loc_18002EEC1
0x18002eebe  mov     rax, r12
0x18002eec1  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002eec8  mov     rcx, rax
0x18002eecb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002eed0  mov     [rbp+57h+pExceptionObject], rax
0x18002eed4  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002eedb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002eedf  call    _CxxThrowException_0
0x18002eee5  mov     ecx, 40h ; '@'; unsigned __int64
0x18002eeea  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002eeef  mov     [rbp+57h+arg_10], rax
0x18002eef3  test    rax, rax
0x18002eef6  jz      short loc_18002EF0E
0x18002eef8  lea     r8, aRootOfDestinat; "root of destination path does not exist"
0x18002eeff  mov     edx, 3; dwMessageId
0x18002ef04  mov     rcx, rax; this
0x18002ef07  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18002ef0c  jmp     short loc_18002EF11
0x18002ef0e  mov     rax, r12
0x18002ef11  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002ef18  mov     rcx, rax
0x18002ef1b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ef20  mov     [rbp+57h+pExceptionObject], rax
0x18002ef24  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002ef2b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002ef2f  call    _CxxThrowException_0
0x18002ef35  call    cs:__imp_GetLastError
0x18002ef3b  mov     esi, eax
0x18002ef3d  mov     ecx, 3
0x18002ef42  cmp     eax, 2
0x18002ef45  cmovz   esi, ecx
0x18002ef48  mov     rcx, rbx
0x18002ef4b  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18002ef50  mov     rbx, rax
0x18002ef53  mov     rcx, rdi
0x18002ef56  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18002ef5b  mov     r8, rbx
0x18002ef5e  mov     rdx, rax
0x18002ef61  lea     rcx, aExceptionWhile; "Exception while moving %s to %s"
0x18002ef68  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18002ef6d  mov     rdx, rax
0x18002ef70  lea     rcx, [rbp+57h+var_48]
0x18002ef74  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ef79  nop
0x18002ef7a  mov     ecx, 40h ; '@'; unsigned __int64
0x18002ef7f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ef84  mov     rbx, rax
0x18002ef87  mov     [rbp+57h+arg_10], rax
0x18002ef8b  test    rax, rax
0x18002ef8e  jz      short loc_18002EFA8
0x18002ef90  lea     rcx, [rbp+57h+var_48]
0x18002ef94  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18002ef99  mov     r8, rax; struct UnBCL::String *
0x18002ef9c  mov     edx, esi; dwMessageId
0x18002ef9e  mov     rcx, rbx; this
0x18002efa1  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18002efa6  jmp     short loc_18002EFAB
0x18002efa8  mov     rax, r12
0x18002efab  lea     rdx, aVoidCdeclUnbcl_0; "void __cdecl UnBCL::Directory::Move(con"...
0x18002efb2  mov     rcx, rax
0x18002efb5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002efba  mov     [rbp+57h+pExceptionObject], rax
0x18002efbe  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
  ... truncated ...
```
