# UnBCL::XmlNode::InsertBefore(UnBCL::XmlNode *,UnBCL::XmlNode *)

- ea: `0x180066690`
- end: `0x18006679a`
- name: `?InsertBefore@XmlNode@UnBCL@@QEAAPEAV12@PEAV12@0@Z`
- size: `266`
- prototype: `struct UnBCL::XmlNode *__fastcall(UnBCL::XmlNode *__hidden this, struct UnBCL::XmlNode *, struct UnBCL::XmlNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180066580`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180066400`
- `0x180066690`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800666cb`
- `OLEAUT32!__imp_VariantInit` at `0x1800666cb`

## string_xrefs

- `0x180066776`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::InsertBefore(class UnBCL::XmlNode *,class UnBCL::XmlNode *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct UnBCL::XmlNode *__fastcall UnBCL::XmlNode::InsertBefore(
        UnBCL::XmlNode *this,
        struct UnBCL::XmlNode *a2,
        struct UnBCL::XmlNode *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  UnBCL::XmlException *v9; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v11; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMNode *v12; // [rsp+90h] [rbp+20h] BYREF
  __int64 pExceptionObject; // [rsp+98h] [rbp+28h] BYREF
  UnBCL::XmlException *v14; // [rsp+A0h] [rbp+30h]

  v12 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 9;
  if ( a3 )
    pvarg.llVal = *((_QWORD *)a3 + 2);
  else
    pvarg.llVal = 0;
  v6 = *((_QWORD *)this + 2);
  v11 = pvarg;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *, struct IXMLDOMNode **))(*(_QWORD *)v6 + 144LL))(
         v6,
         *((_QWORD *)a2 + 2),
         &v11,
         &v12);
  if ( v7 < 0 || !v12 )
  {
    v9 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    v14 = v9;
    if ( v9 )
      v9 = (UnBCL::XmlException *)UnBCL::XmlException::XmlException(v9, 0, 0, 0, 0, v7);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::InsertBefore(class UnBCL::XmlNode *,class UnBCL::XmlNode *)");
    throw (UnBCL::XmlException **)&pExceptionObject;
  }
  return UnBCL::XmlNode::CreateXmlNode(v12);
}

```

## disassembly

```asm
0x180066690  mov     rax, rsp
0x180066693  push    rbp
0x180066694  push    rsi
0x180066695  push    rdi
0x180066696  mov     rbp, rsp
0x180066699  sub     rsp, 70h
0x18006669d  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1800666a5  mov     [rax+20h], rbx
0x1800666a9  mov     rbx, r8
0x1800666ac  mov     rdi, rdx
0x1800666af  mov     rsi, rcx
0x1800666b2  mov     [rbp+arg_0], 0
0x1800666ba  xorps   xmm0, xmm0
0x1800666bd  xor     eax, eax
0x1800666bf  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800666c3  mov     qword ptr [rbp+pvarg+10h], rax
0x1800666c7  lea     rcx, [rbp+pvarg]; pvarg
0x1800666cb  call    cs:__imp_VariantInit
0x1800666d1  mov     eax, 9
0x1800666d6  mov     word ptr [rbp+pvarg], ax
0x1800666da  test    rbx, rbx
0x1800666dd  jz      short loc_1800666E9
0x1800666df  mov     rax, [rbx+10h]
0x1800666e3  mov     qword ptr [rbp+pvarg+8], rax
0x1800666e7  jmp     short loc_1800666F1
0x1800666e9  mov     qword ptr [rbp+pvarg+8], 0
0x1800666f1  mov     rcx, [rsi+10h]
0x1800666f5  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800666f9  movaps  [rbp+var_20], xmm0
0x1800666fd  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180066702  movsd   [rbp+var_10], xmm1
0x180066707  mov     rax, [rcx]
0x18006670a  lea     r9, [rbp+arg_0]
0x18006670e  lea     r8, [rbp+var_20]
0x180066712  mov     rdx, [rdi+10h]
0x180066716  mov     rax, [rax+90h]
0x18006671d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066722  mov     ebx, eax
0x180066724  test    eax, eax
0x180066726  js      short loc_180066746
0x180066728  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x18006672c  test    rcx, rcx
0x18006672f  jz      short loc_180066746
0x180066731  call    ?CreateXmlNode@XmlNode@UnBCL@@SAPEAV12@PEAUIXMLDOMNode@@@Z; UnBCL::XmlNode::CreateXmlNode(IXMLDOMNode *)
0x180066736  mov     rbx, [rsp+70h+arg_18]
0x18006673e  add     rsp, 70h
0x180066742  pop     rdi
0x180066743  pop     rsi
0x180066744  pop     rbp
0x180066745  retn
0x180066746  mov     ecx, 40h ; '@'; unsigned __int64
0x18006674b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066750  mov     [rbp+arg_10], rax
0x180066754  test    rax, rax
0x180066757  jz      short loc_180066776
0x180066759  mov     [rsp+70h+var_48], ebx; int
0x18006675d  mov     [rsp+70h+var_50], 0; int
0x180066765  xor     r9d, r9d; int
0x180066768  xor     r8d, r8d; struct UnBCL::Exception *
0x18006676b  xor     edx, edx; struct UnBCL::String *
0x18006676d  mov     rcx, rax; this
0x180066770  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x180066775  nop
0x180066776  lea     rdx, aClassUnbclXmln_1; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x18006677d  mov     rcx, rax
0x180066780  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066785  mov     [rbp+pExceptionObject], rax
0x180066789  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066790  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066794  call    _CxxThrowException_0
```
