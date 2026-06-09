# UnBCL::File::Copy(UnBCL::String const *,UnBCL::String const *,int)

- ea: `0x18003b2e0`
- end: `0x18003b587`
- name: `?Copy@File@UnBCL@@SAPEAVString@2@PEBV32@0H@Z`
- size: `679`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *, const struct UnBCL::String *, int)`
- caller_count: `0`
- callee_count: `17`
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
- `0x18003b2e0`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x18005bda0`
- `0x180060150`
- `0x180064340`

## import_xrefs

- `KERNEL32!CopyFileExW` at `0x18003b3ea`
- `KERNEL32!CopyFileExW` at `0x18003b3ea`
- `KERNEL32!GetLastError` at `0x18003b4d5`
- `KERNEL32!GetLastError` at `0x18003b4d5`

## string_xrefs

- `0x18003b466`: `class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18003b4b1`: `class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18003b563`: `class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18003b49d`: `null srcpath or destpath to File::Copy`
- `0x18003b452`: `empty srcpath or destpath to File::Copy`
- `0x18003b505`: ` copy to `

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct UnBCL::String *__fastcall UnBCL::File::Copy(
        const struct UnBCL::String *a1,
        const struct UnBCL::String *a2,
        int a3)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v6; // rax
  struct UnBCL::String *v7; // rax
  struct UnBCL::String *v8; // rax
  __int64 v9; // rax
  struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rbx
  struct UnBCL::String *v12; // rdi
  UnBCL::ArgumentException *v14; // rax
  __int64 v15; // rax
  UnBCL::ArgumentNullException *v16; // rax
  __int64 v17; // rax
  DWORD LastError; // edi
  __int64 v19; // rax
  const unsigned __int16 *InnerList; // rbx
  __int64 v21; // rax
  const unsigned __int16 *v22; // rax
  struct UnBCL::String *v23; // rax
  UnBCL::Win32Exception *v24; // rbx
  const struct UnBCL::String *v25; // rax
  __int64 v26; // rax
  void **v27; // [rsp+38h] [rbp-48h] BYREF
  struct UnBCL::String *v28; // [rsp+40h] [rbp-40h]
  void **v29; // [rsp+48h] [rbp-38h] BYREF
  struct UnBCL::String *v30; // [rsp+50h] [rbp-30h]
  void **v31; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v32[4]; // [rsp+60h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+B0h] [rbp+30h] BYREF
  UnBCL::ArgumentNullException *v34; // [rsp+C8h] [rbp+48h]

  if ( !a1 || !a2 )
  {
    v16 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v34 = v16;
    if ( v16 )
      v17 = UnBCL::ArgumentNullException::ArgumentNullException(v16, L"null srcpath or destpath to File::Copy");
    else
      v17 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) || !**((_WORD **)a2 + 2) )
  {
    v14 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v34 = v14;
    if ( v14 )
      v15 = UnBCL::ArgumentException::ArgumentException(v14, L"empty srcpath or destpath to File::Copy");
    else
      v15 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  v6 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v27, FullPath);
  v7 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v6 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v29, v7);
  v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
  v8 = UnBCL::Path::GetFullPath(a2);
  v9 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v31, v8);
  v10 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v9 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v27, v10);
  v31 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v31);
  v11 = v30;
  UnBCL::Path::CheckPathTooLong(v30);
  v12 = v28;
  UnBCL::Path::CheckPathTooLong(v28);
  if ( !CopyFileExW(*((LPCWSTR *)v11 + 2), *((LPCWSTR *)v12 + 2), 0, 0, 0, a3 == 0) )
  {
    LastError = GetLastError();
    v19 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v27);
    InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v19);
    v21 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v29);
    v22 = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v21);
    v23 = UnBCL::String::Concat(v22, L" copy to ", InnerList);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)&v31, v23);
    v24 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v34 = v24;
    if ( v24 )
    {
      v25 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)v32 + *(int *)(v32[0] + 4LL));
      v26 = UnBCL::Win32Exception::Win32Exception(v24, LastError, v25);
    }
    else
    {
      v26 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v26,
                         "class UnBCL::String *__cdecl UnBCL::File::Copy(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( v12 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v12 + 2);
    v28 = 0;
  }
  else
  {
    v12 = 0;
  }
  v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
  v29 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v29);
  return v12;
}

```

## disassembly

```asm
0x18003b2e0  mov     rax, rsp
0x18003b2e3  push    rbp
0x18003b2e4  push    rsi
0x18003b2e5  push    rdi
0x18003b2e6  push    r14
0x18003b2e8  push    r15
0x18003b2ea  mov     rbp, rsp
0x18003b2ed  sub     rsp, 80h
0x18003b2f4  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18003b2fc  mov     [rax+10h], rbx
0x18003b300  mov     esi, r8d
0x18003b303  mov     rbx, rdx
0x18003b306  xor     r14d, r14d
0x18003b309  test    rcx, rcx
0x18003b30c  jz      loc_18003B48A
0x18003b312  test    rdx, rdx
0x18003b315  jz      loc_18003B48A
0x18003b31b  mov     rax, [rcx+10h]
0x18003b31f  cmp     [rax], r14w
0x18003b323  jz      loc_18003B43F
0x18003b329  mov     rax, [rdx+10h]
0x18003b32d  cmp     [rax], r14w
0x18003b331  jz      loc_18003B43F
0x18003b337  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003b33c  mov     rdx, rax
0x18003b33f  lea     rcx, [rbp+var_48]
0x18003b343  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b348  nop
0x18003b349  lea     edx, [r14+1]; int
0x18003b34d  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003b351  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003b356  mov     rdx, rax
0x18003b359  lea     rcx, [rbp+var_38]
0x18003b35d  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b362  nop
0x18003b363  lea     r15, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003b36a  mov     [rbp+var_48], r15
0x18003b36e  lea     rcx, [rbp+var_48]
0x18003b372  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b377  mov     rcx, rbx; struct UnBCL::String *
0x18003b37a  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003b37f  mov     rdx, rax
0x18003b382  lea     rcx, [rbp+var_28]
0x18003b386  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b38b  nop
0x18003b38c  lea     edx, [r14+1]; int
0x18003b390  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003b394  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003b399  mov     rdx, rax
0x18003b39c  lea     rcx, [rbp+var_48]
0x18003b3a0  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b3a5  nop
0x18003b3a6  mov     [rbp+var_28], r15
0x18003b3aa  lea     rcx, [rbp+var_28]
0x18003b3ae  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b3b3  mov     rbx, [rbp+var_30]
0x18003b3b7  mov     rcx, rbx; struct UnBCL::String *
0x18003b3ba  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003b3bf  mov     rdi, [rbp+var_40]
0x18003b3c3  mov     rcx, rdi; struct UnBCL::String *
0x18003b3c6  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003b3cb  mov     eax, r14d
0x18003b3ce  test    esi, esi
0x18003b3d0  setz    al
0x18003b3d3  mov     [rsp+80h+dwCopyFlags], eax; dwCopyFlags
0x18003b3d7  mov     [rsp+80h+pbCancel], r14; pbCancel
0x18003b3dc  xor     r9d, r9d; lpData
0x18003b3df  xor     r8d, r8d; lpProgressRoutine
0x18003b3e2  mov     rdx, [rdi+10h]; lpNewFileName
0x18003b3e6  mov     rcx, [rbx+10h]; lpExistingFileName
0x18003b3ea  call    cs:__imp_CopyFileExW
0x18003b3f0  test    eax, eax
0x18003b3f2  jz      loc_18003B4D5
0x18003b3f8  test    rdi, rdi
0x18003b3fb  jnz     short loc_18003B402
0x18003b3fd  mov     edi, r14d
0x18003b400  jmp     short loc_18003B40A
0x18003b402  lock dec dword ptr [rdi+8]
0x18003b406  mov     [rbp+var_40], r14
0x18003b40a  mov     [rbp+var_48], r15
0x18003b40e  lea     rcx, [rbp+var_48]
0x18003b412  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b417  nop
0x18003b418  mov     [rbp+var_38], r15
0x18003b41c  lea     rcx, [rbp+var_38]
0x18003b420  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003b425  mov     rax, rdi
0x18003b428  mov     rbx, [rsp+80h+arg_8]
0x18003b430  add     rsp, 80h
0x18003b437  pop     r15
0x18003b439  pop     r14
0x18003b43b  pop     rdi
0x18003b43c  pop     rsi
0x18003b43d  pop     rbp
0x18003b43e  retn
0x18003b43f  mov     ecx, 38h ; '8'; unsigned __int64
0x18003b444  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b449  mov     [rbp+arg_18], rax
0x18003b44d  test    rax, rax
0x18003b450  jz      short loc_18003B463
0x18003b452  lea     rdx, aEmptySrcpathOr_0; "empty srcpath or destpath to File::Copy"
0x18003b459  mov     rcx, rax; this
0x18003b45c  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003b461  jmp     short loc_18003B466
0x18003b463  mov     rax, r14
0x18003b466  lea     rdx, aClassUnbclStri_25; "class UnBCL::String *__cdecl UnBCL::Fil"...
0x18003b46d  mov     rcx, rax
0x18003b470  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003b475  mov     [rbp+pExceptionObject], rax
0x18003b479  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003b480  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b484  call    _CxxThrowException_0
0x18003b48a  mov     ecx, 38h ; '8'; unsigned __int64
0x18003b48f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b494  mov     [rbp+arg_18], rax
0x18003b498  test    rax, rax
0x18003b49b  jz      short loc_18003B4AE
0x18003b49d  lea     rdx, aNullSrcpathOrD_2; "null srcpath or destpath to File::Copy"
0x18003b4a4  mov     rcx, rax; this
0x18003b4a7  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003b4ac  jmp     short loc_18003B4B1
0x18003b4ae  mov     rax, r14
0x18003b4b1  lea     rdx, aClassUnbclStri_25; "class UnBCL::String *__cdecl UnBCL::Fil"...
0x18003b4b8  mov     rcx, rax
0x18003b4bb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003b4c0  mov     [rbp+pExceptionObject], rax
0x18003b4c4  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003b4cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b4cf  call    _CxxThrowException_0
0x18003b4d5  call    cs:__imp_GetLastError
0x18003b4db  mov     edi, eax
0x18003b4dd  lea     rcx, [rbp+var_48]
0x18003b4e1  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003b4e6  mov     rcx, rax
0x18003b4e9  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003b4ee  mov     rbx, rax
0x18003b4f1  lea     rcx, [rbp+var_38]
0x18003b4f5  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003b4fa  mov     rcx, rax
0x18003b4fd  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003b502  mov     r8, rbx; unsigned __int16 *
0x18003b505  lea     rdx, aCopyTo; " copy to "
0x18003b50c  mov     rcx, rax; unsigned __int16 *
0x18003b50f  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18003b514  mov     rdx, rax; struct UnBCL::String *
0x18003b517  mov     r8d, 1
0x18003b51d  lea     rcx, [rbp+var_28]; this
0x18003b521  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18003b526  nop
0x18003b527  mov     ecx, 40h ; '@'; unsigned __int64
0x18003b52c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b531  mov     rbx, rax
0x18003b534  mov     [rbp+arg_18], rax
0x18003b538  test    rax, rax
0x18003b53b  jz      short loc_18003B560
0x18003b53d  mov     rcx, [rbp+var_20]
0x18003b541  movsxd  rdx, dword ptr [rcx+4]
0x18003b545  lea     rcx, [rbp+var_20]
0x18003b549  add     rcx, rdx
0x18003b54c  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003b551  mov     r8, rax; struct UnBCL::String *
0x18003b554  mov     edx, edi; dwMessageId
0x18003b556  mov     rcx, rbx; this
0x18003b559  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003b55e  jmp     short loc_18003B563
0x18003b560  mov     rax, r14
0x18003b563  lea     rdx, aClassUnbclStri_25; "class UnBCL::String *__cdecl UnBCL::Fil"...
0x18003b56a  mov     rcx, rax
0x18003b56d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003b572  mov     [rbp+pExceptionObject], rax
0x18003b576  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003b57d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b581  call    _CxxThrowException_0
```
