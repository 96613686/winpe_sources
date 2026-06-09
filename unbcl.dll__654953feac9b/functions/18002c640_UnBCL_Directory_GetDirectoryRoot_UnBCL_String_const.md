# UnBCL::Directory::GetDirectoryRoot(UnBCL::String const *)

- ea: `0x18002c640`
- end: `0x18002c7fd`
- name: `?GetDirectoryRoot@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `445`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180029280`
- `0x18003d910`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x18002c640`
- `0x1800477d0`
- `0x180049500`
- `0x180049ae0`
- `0x18005be50`
- `0x18005de90`
- `0x18005f390`
- `0x180060150`

## string_xrefs

- `0x18002c792`: `class UnBCL::String *__cdecl UnBCL::Directory::GetDirectoryRoot(const class UnBCL::String *)`
- `0x18002c7d9`: `class UnBCL::String *__cdecl UnBCL::Directory::GetDirectoryRoot(const class UnBCL::String *)`
- `0x18002c7c9`: `null path to Directory::GetDirectoryRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::String *__fastcall UnBCL::Directory::GetDirectoryRoot(const struct UnBCL::String *a1)
{
  struct UnBCL::String *FullPath; // rax
  const struct UnBCL::String *v2; // rbx
  int RootLength; // eax
  struct UnBCL::String *v4; // rax
  UnBCL::String *v5; // rcx
  int v6; // edx
  const unsigned __int16 *Chars; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  struct UnBCL::String *v10; // rbx
  UnBCL::ArgumentException *v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  _BYTE v14[8]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  struct UnBCL::String *v16[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h]
  _QWORD v19[3]; // [rsp+58h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+80h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v21; // [rsp+88h] [rbp+18h]

  if ( !a1 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v21 = v13;
    if ( v13 )
      v13 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v13,
                                              L"null path to Directory::GetDirectoryRoot");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "class UnBCL::String *__cdecl UnBCL::Directory::GetDirectoryRoot(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v14, FullPath);
  v2 = *(struct UnBCL::String **)((char *)v16 + *(int *)(v15 + 4));
  RootLength = UnBCL::Path::GetRootLength(v2);
  v4 = UnBCL::String::Substring(v2, 0, RootLength);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v17, v4);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
    (char *)&v16[-1] + *(int *)(v15 + 4),
    *(_QWORD *)((char *)v19 + *(int *)(v18 + 4)));
  v19[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v19);
  v5 = *(struct UnBCL::String **)((char *)v16 + *(int *)(v15 + 4));
  v6 = *(_DWORD *)(*((_QWORD *)v5 + 2) - 16LL);
  if ( !v6 )
  {
    v12 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v21 = v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v12, L"Zero length root");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::String *__cdecl UnBCL::Directory::GetDirectoryRoot(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  Chars = UnBCL::String::get_Chars(v5, v6 - 1);
  v8 = *(int *)(v15 + 4);
  if ( *Chars == 92 )
  {
    v9 = *(__int64 *)((char *)v16 + v8);
    if ( v9 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v9 + 8));
      v10 = *(struct UnBCL::String **)((char *)v16 + v8);
      *(struct UnBCL::String **)((char *)v16 + v8) = 0;
    }
    else
    {
      v10 = 0;
    }
  }
  else
  {
    v10 = UnBCL::String::Concat((*(const unsigned __int16 ***)((char *)v16 + v8))[2], L"\\");
  }
  v16[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
  return v10;
}

```

## disassembly

```asm
0x18002c640  mov     rax, rsp
0x18002c643  push    rbp
0x18002c644  mov     rbp, rsp
0x18002c647  sub     rsp, 70h
0x18002c64b  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18002c653  mov     [rax+18h], rbx
0x18002c657  mov     [rax+20h], rdi
0x18002c65b  test    rcx, rcx
0x18002c65e  jz      loc_18002C7B6
0x18002c664  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002c669  mov     rdx, rax; struct UnBCL::String *
0x18002c66c  mov     edi, 1
0x18002c671  mov     r8d, edi
0x18002c674  lea     rcx, [rbp+var_48]; this
0x18002c678  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18002c67d  nop
0x18002c67e  mov     rax, [rbp+var_40]
0x18002c682  movsxd  rcx, dword ptr [rax+4]
0x18002c686  mov     rbx, [rbp+rcx+var_38]
0x18002c68b  mov     rcx, rbx; struct UnBCL::String *
0x18002c68e  call    ?GetRootLength@Path@UnBCL@@KAHPEBVString@2@@Z; UnBCL::Path::GetRootLength(UnBCL::String const *)
0x18002c693  mov     r8d, eax; int
0x18002c696  xor     edx, edx; int
0x18002c698  mov     rcx, rbx; this
0x18002c69b  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x18002c6a0  mov     rdx, rax; struct UnBCL::String *
0x18002c6a3  mov     r8d, edi
0x18002c6a6  lea     rcx, [rbp+var_28]; this
0x18002c6aa  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18002c6af  nop
0x18002c6b0  mov     rax, [rbp+var_20]
0x18002c6b4  movsxd  rdx, dword ptr [rax+4]
0x18002c6b8  mov     rax, [rbp+var_40]
0x18002c6bc  movsxd  rcx, dword ptr [rax+4]
0x18002c6c0  lea     rax, [rbp+var_40]
0x18002c6c4  add     rcx, rax
0x18002c6c7  mov     rdx, [rbp+rdx+var_18]
0x18002c6cc  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002c6d1  nop
0x18002c6d2  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002c6d9  mov     [rbp+var_18], rdi
0x18002c6dd  lea     rcx, [rbp+var_18]
0x18002c6e1  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002c6e6  mov     rax, [rbp+var_40]
0x18002c6ea  movsxd  rcx, dword ptr [rax+4]
0x18002c6ee  mov     rcx, [rbp+rcx+var_38]; this
0x18002c6f3  mov     rax, [rcx+10h]
0x18002c6f7  mov     edx, [rax-10h]
0x18002c6fa  test    edx, edx
0x18002c6fc  jz      short loc_18002C76F
0x18002c6fe  dec     edx; int
0x18002c700  call    ?get_Chars@String@UnBCL@@QEBAAEBGH@Z; UnBCL::String::get_Chars(int)
0x18002c705  cmp     word ptr [rax], 5Ch ; '\'
0x18002c709  mov     rax, [rbp+var_40]
0x18002c70d  movsxd  rcx, dword ptr [rax+4]
0x18002c711  jnz     short loc_18002C735
0x18002c713  mov     rax, [rbp+rcx+var_38]
0x18002c718  test    rax, rax
0x18002c71b  jnz     short loc_18002C721
0x18002c71d  xor     ebx, ebx
0x18002c71f  jmp     short loc_18002C74D
0x18002c721  lock dec dword ptr [rax+8]
0x18002c725  mov     rbx, [rbp+rcx+var_38]
0x18002c72a  mov     [rbp+rcx+var_38], 0
0x18002c733  jmp     short loc_18002C74D
0x18002c735  mov     rcx, [rbp+rcx+var_38]
0x18002c73a  lea     rdx, asc_180080A2C; "\\"
0x18002c741  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18002c745  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18002c74a  mov     rbx, rax
0x18002c74d  mov     [rbp+var_38], rdi
0x18002c751  lea     rcx, [rbp+var_38]
0x18002c755  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002c75a  mov     rax, rbx
0x18002c75d  lea     r11, [rsp+70h+var_s0]
0x18002c762  mov     rbx, [r11+20h]
0x18002c766  mov     rdi, [r11+28h]
0x18002c76a  mov     rsp, r11
0x18002c76d  pop     rbp
0x18002c76e  retn
0x18002c76f  mov     ecx, 38h ; '8'; unsigned __int64
0x18002c774  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c779  mov     [rbp+arg_8], rax
0x18002c77d  test    rax, rax
0x18002c780  jz      short loc_18002C792
0x18002c782  lea     rdx, aZeroLengthRoot; "Zero length root"
0x18002c789  mov     rcx, rax; this
0x18002c78c  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18002c791  nop
0x18002c792  lea     rdx, aClassUnbclStri_31; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002c799  mov     rcx, rax
0x18002c79c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002c7a1  mov     [rbp+pExceptionObject], rax
0x18002c7a5  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18002c7ac  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002c7b0  call    _CxxThrowException_0
0x18002c7b6  mov     ecx, 38h ; '8'; unsigned __int64
0x18002c7bb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c7c0  mov     [rbp+arg_8], rax
0x18002c7c4  test    rax, rax
0x18002c7c7  jz      short loc_18002C7D9
0x18002c7c9  lea     rdx, aNullPathToDire_0; "null path to Directory::GetDirectoryRoo"...
0x18002c7d0  mov     rcx, rax; this
0x18002c7d3  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18002c7d8  nop
0x18002c7d9  lea     rdx, aClassUnbclStri_31; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002c7e0  mov     rcx, rax
0x18002c7e3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002c7e8  mov     [rbp+pExceptionObject], rax
0x18002c7ec  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18002c7f3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002c7f7  call    _CxxThrowException_0
```
