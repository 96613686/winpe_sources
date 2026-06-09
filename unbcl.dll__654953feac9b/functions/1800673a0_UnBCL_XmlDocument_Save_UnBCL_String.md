# UnBCL::XmlDocument::Save(UnBCL::String *)

- ea: `0x1800673a0`
- end: `0x1800674c2`
- name: `?Save@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z`
- size: `290`
- prototype: `void __fastcall(UnBCL::XmlDocument *__hidden this, struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x1800489c0`
- `0x1800673a0`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800673d4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800673d4`
- `OLEAUT32!__imp_VariantClear` at `0x180067416`
- `OLEAUT32!__imp_VariantClear` at `0x180067416`

## string_xrefs

- `0x18006745e`: `void __cdecl UnBCL::XmlDocument::Save(class UnBCL::String *)`
- `0x18006749e`: `void __cdecl UnBCL::XmlDocument::Save(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UnBCL::XmlDocument::Save(UnBCL::XmlDocument *this, const OLECHAR **a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  UnBCL::XmlException *v5; // rax
  UnBCL::OutOfMemoryException *v6; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v8; // [rsp+50h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+88h] [rbp+18h] BYREF
  UnBCL::OutOfMemoryException *v10; // [rsp+90h] [rbp+20h]

  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a2[2]);
  if ( !pvarg.llVal )
  {
    v6 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v10 = v6;
    if ( v6 )
      v6 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v6);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "void __cdecl UnBCL::XmlDocument::Save(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&pExceptionObject;
  }
  v3 = *((_QWORD *)this + 3);
  v8 = pvarg;
  v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v3 + 528LL))(v3, &v8);
  VariantClear(&pvarg);
  if ( v4 )
  {
    v5 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    v10 = v5;
    if ( v5 )
      v5 = (UnBCL::XmlException *)UnBCL::XmlException::XmlException(v5, 0, 0, 0, 0, v4);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "void __cdecl UnBCL::XmlDocument::Save(class UnBCL::String *)");
    throw (UnBCL::XmlException **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800673a0  mov     rax, rsp
0x1800673a3  push    rbp
0x1800673a4  mov     rbp, rsp
0x1800673a7  sub     rsp, 70h
0x1800673ab  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1800673b3  mov     [rax+8], rbx
0x1800673b7  mov     rbx, rcx
0x1800673ba  xorps   xmm0, xmm0
0x1800673bd  xor     eax, eax
0x1800673bf  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800673c3  mov     qword ptr [rbp+pvarg+10h], rax
0x1800673c7  mov     eax, 8
0x1800673cc  mov     word ptr [rbp+pvarg], ax
0x1800673d0  mov     rcx, [rdx+10h]; psz
0x1800673d4  call    cs:__imp_SysAllocString
0x1800673da  mov     qword ptr [rbp+pvarg+8], rax
0x1800673de  test    rax, rax
0x1800673e1  jz      loc_180067482
0x1800673e7  mov     rcx, [rbx+18h]
0x1800673eb  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800673ef  movaps  [rbp+var_20], xmm0
0x1800673f3  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800673f8  movsd   [rbp+var_10], xmm1
0x1800673fd  mov     rax, [rcx]
0x180067400  lea     rdx, [rbp+var_20]
0x180067404  mov     rax, [rax+210h]
0x18006740b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067410  mov     ebx, eax
0x180067412  lea     rcx, [rbp+pvarg]; pvarg
0x180067416  call    cs:__imp_VariantClear
0x18006741c  test    ebx, ebx
0x18006741e  jnz     short loc_18006742E
0x180067420  mov     rbx, [rsp+70h+arg_0]
0x180067428  add     rsp, 70h
0x18006742c  pop     rbp
0x18006742d  retn
0x18006742e  mov     ecx, 40h ; '@'; unsigned __int64
0x180067433  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180067438  mov     [rbp+arg_10], rax
0x18006743c  test    rax, rax
0x18006743f  jz      short loc_18006745E
0x180067441  mov     [rsp+70h+var_48], ebx; int
0x180067445  mov     [rsp+70h+var_50], 0; int
0x18006744d  xor     r9d, r9d; int
0x180067450  xor     r8d, r8d; struct UnBCL::Exception *
0x180067453  xor     edx, edx; struct UnBCL::String *
0x180067455  mov     rcx, rax; this
0x180067458  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x18006745d  nop
0x18006745e  lea     rdx, aVoidCdeclUnbcl_8; "void __cdecl UnBCL::XmlDocument::Save(c"...
0x180067465  mov     rcx, rax
0x180067468  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006746d  mov     [rbp+pExceptionObject], rax
0x180067471  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180067478  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006747c  call    _CxxThrowException_0
0x180067482  mov     ecx, 38h ; '8'; unsigned __int64
0x180067487  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18006748c  mov     [rbp+arg_10], rax
0x180067490  test    rax, rax
0x180067493  jz      short loc_18006749E
0x180067495  mov     rcx, rax; this
0x180067498  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x18006749d  nop
0x18006749e  lea     rdx, aVoidCdeclUnbcl_8; "void __cdecl UnBCL::XmlDocument::Save(c"...
0x1800674a5  mov     rcx, rax
0x1800674a8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800674ad  mov     [rbp+pExceptionObject], rax
0x1800674b1  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x1800674b8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800674bc  call    _CxxThrowException_0
```
