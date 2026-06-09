# UnBCL::XmlDocument::RegisterNamespaces(UnBCL::String *)

- ea: `0x180066d50`
- end: `0x180066ef6`
- name: `?RegisterNamespaces@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z`
- size: `422`
- prototype: `void __fastcall(UnBCL::XmlDocument *__hidden this, struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180066f00`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x1800489c0`
- `0x180066d50`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180066d95`
- `OLEAUT32!__imp_SysAllocString` at `0x180066daf`
- `OLEAUT32!__imp_SysAllocString` at `0x180066d95`
- `OLEAUT32!__imp_SysAllocString` at `0x180066daf`
- `OLEAUT32!__imp_SysFreeString` at `0x180066dfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180066dfc`
- `OLEAUT32!__imp_VariantInit` at `0x180066d82`
- `OLEAUT32!__imp_VariantInit` at `0x180066d82`
- `OLEAUT32!__imp_VariantClear` at `0x180066df3`
- `OLEAUT32!__imp_VariantClear` at `0x180066eb0`
- `OLEAUT32!__imp_VariantClear` at `0x180066df3`
- `OLEAUT32!__imp_VariantClear` at `0x180066eb0`

## string_xrefs

- `0x180066e48`: `void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)`
- `0x180066e88`: `void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)`
- `0x180066ed2`: `void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::XmlDocument::RegisterNamespaces(UnBCL::XmlDocument *this, const OLECHAR **a2)
{
  BSTR v4; // rax
  OLECHAR *v5; // rbx
  __int64 v6; // rcx
  int v7; // edi
  UnBCL::XmlException *v8; // rax
  UnBCL::OutOfMemoryException *v9; // rax
  UnBCL::OutOfMemoryException *v10; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v12; // [rsp+50h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+88h] [rbp+18h] BYREF
  UnBCL::OutOfMemoryException *v14; // [rsp+90h] [rbp+20h]

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a2[2]);
  if ( !pvarg.llVal )
  {
    v9 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v14 = v9;
    if ( v9 )
      v9 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v9);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&pExceptionObject;
  }
  v4 = SysAllocString(L"SelectionNamespaces");
  v5 = v4;
  if ( !v4 )
  {
    VariantClear(&pvarg);
    v10 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v14 = v10;
    if ( v10 )
      v10 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v10);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&pExceptionObject;
  }
  v6 = *((_QWORD *)this + 3);
  v12 = pvarg;
  v7 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v6 + 640LL))(v6, v4, &v12);
  VariantClear(&pvarg);
  SysFreeString(v5);
  if ( v7 )
  {
    v8 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    v14 = v8;
    if ( v8 )
      v8 = (UnBCL::XmlException *)UnBCL::XmlException::XmlException(v8, 0, 0, 0, 0, v7);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "void __cdecl UnBCL::XmlDocument::RegisterNamespaces(class UnBCL::String *)");
    throw (UnBCL::XmlException **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180066d50  mov     rax, rsp
0x180066d53  push    rbp
0x180066d54  mov     rbp, rsp
0x180066d57  sub     rsp, 70h
0x180066d5b  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180066d63  mov     [rax+8], rbx
0x180066d67  mov     [rax+20h], rdi
0x180066d6b  mov     rbx, rdx
0x180066d6e  mov     rdi, rcx
0x180066d71  xorps   xmm0, xmm0
0x180066d74  xor     eax, eax
0x180066d76  movups  xmmword ptr [rbp+pvarg], xmm0
0x180066d7a  mov     qword ptr [rbp+pvarg+10h], rax
0x180066d7e  lea     rcx, [rbp+pvarg]; pvarg
0x180066d82  call    cs:__imp_VariantInit
0x180066d88  mov     eax, 8
0x180066d8d  mov     word ptr [rbp+pvarg], ax
0x180066d91  mov     rcx, [rbx+10h]; psz
0x180066d95  call    cs:__imp_SysAllocString
0x180066d9b  mov     qword ptr [rbp+pvarg+8], rax
0x180066d9f  test    rax, rax
0x180066da2  jz      loc_180066E6C
0x180066da8  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x180066daf  call    cs:__imp_SysAllocString
0x180066db5  mov     rbx, rax
0x180066db8  test    rax, rax
0x180066dbb  jz      loc_180066EAC
0x180066dc1  mov     rcx, [rdi+18h]
0x180066dc5  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180066dc9  movaps  [rbp+var_20], xmm0
0x180066dcd  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180066dd2  movsd   [rbp+var_10], xmm1
0x180066dd7  mov     rax, [rcx]
0x180066dda  lea     r8, [rbp+var_20]
0x180066dde  mov     rdx, rbx
0x180066de1  mov     rax, [rax+280h]
0x180066de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ded  mov     edi, eax
0x180066def  lea     rcx, [rbp+pvarg]; pvarg
0x180066df3  call    cs:__imp_VariantClear
0x180066df9  mov     rcx, rbx; bstrString
0x180066dfc  call    cs:__imp_SysFreeString
0x180066e02  test    edi, edi
0x180066e04  jnz     short loc_180066E18
0x180066e06  lea     r11, [rsp+70h+var_s0]
0x180066e0b  mov     rbx, [r11+10h]
0x180066e0f  mov     rdi, [r11+28h]
0x180066e13  mov     rsp, r11
0x180066e16  pop     rbp
0x180066e17  retn
0x180066e18  mov     ecx, 40h ; '@'; unsigned __int64
0x180066e1d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066e22  mov     [rbp+arg_10], rax
0x180066e26  test    rax, rax
0x180066e29  jz      short loc_180066E48
0x180066e2b  mov     [rsp+70h+var_48], edi; int
0x180066e2f  mov     [rsp+70h+var_50], 0; int
0x180066e37  xor     r9d, r9d; int
0x180066e3a  xor     r8d, r8d; struct UnBCL::Exception *
0x180066e3d  xor     edx, edx; struct UnBCL::String *
0x180066e3f  mov     rcx, rax; this
0x180066e42  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x180066e47  nop
0x180066e48  lea     rdx, aVoidCdeclUnbcl_55; "void __cdecl UnBCL::XmlDocument::Regist"...
0x180066e4f  mov     rcx, rax
0x180066e52  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066e57  mov     [rbp+pExceptionObject], rax
0x180066e5b  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066e62  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066e66  call    _CxxThrowException_0
0x180066e6c  mov     ecx, 38h ; '8'; unsigned __int64
0x180066e71  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066e76  mov     [rbp+arg_10], rax
0x180066e7a  test    rax, rax
0x180066e7d  jz      short loc_180066E88
0x180066e7f  mov     rcx, rax; this
0x180066e82  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180066e87  nop
0x180066e88  lea     rdx, aVoidCdeclUnbcl_55; "void __cdecl UnBCL::XmlDocument::Regist"...
0x180066e8f  mov     rcx, rax
0x180066e92  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066e97  mov     [rbp+pExceptionObject], rax
0x180066e9b  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x180066ea2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066ea6  call    _CxxThrowException_0
0x180066eac  lea     rcx, [rbp+pvarg]; pvarg
0x180066eb0  call    cs:__imp_VariantClear
0x180066eb6  mov     ecx, 38h ; '8'; unsigned __int64
0x180066ebb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066ec0  mov     [rbp+arg_10], rax
0x180066ec4  test    rax, rax
0x180066ec7  jz      short loc_180066ED2
0x180066ec9  mov     rcx, rax; this
0x180066ecc  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180066ed1  nop
0x180066ed2  lea     rdx, aVoidCdeclUnbcl_55; "void __cdecl UnBCL::XmlDocument::Regist"...
0x180066ed9  mov     rcx, rax
0x180066edc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066ee1  mov     [rbp+pExceptionObject], rax
0x180066ee5  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x180066eec  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066ef0  call    _CxxThrowException_0
```
