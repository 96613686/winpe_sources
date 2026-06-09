# UnBCL::XmlNode::SelectSingleNode(UnBCL::String *)

- ea: `0x180067670`
- end: `0x18006777b`
- name: `?SelectSingleNode@XmlNode@UnBCL@@QEAAPEAV12@PEAVString@2@@Z`
- size: `267`
- prototype: `struct UnBCL::XmlNode *(UnBCL::XmlNode *__hidden this, struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180067790`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x1800489c0`
- `0x180066400`
- `0x180067670`
- `0x1800684d0`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180067694`
- `OLEAUT32!__imp_SysAllocString` at `0x180067694`
- `OLEAUT32!__imp_SysFreeString` at `0x1800676c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800676c6`

## string_xrefs

- `0x180067712`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::SelectSingleNode(class UnBCL::String *)`
- `0x180067755`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::SelectSingleNode(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct UnBCL::XmlNode *__fastcall UnBCL::XmlNode::SelectSingleNode(UnBCL::XmlNode *this, const OLECHAR **a2)
{
  BSTR v4; // rax
  OLECHAR *v5; // rdi
  unsigned int v6; // esi
  UnBCL::XPathException *v8; // rax
  UnBCL::OutOfMemoryException *v9; // rax
  struct IXMLDOMNode *v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 pExceptionObject; // [rsp+60h] [rbp+18h] BYREF
  UnBCL::OutOfMemoryException *v12; // [rsp+68h] [rbp+20h]

  v10 = 0;
  v4 = SysAllocString(a2[2]);
  v5 = v4;
  if ( !v4 )
  {
    v9 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v12 = v9;
    if ( v9 )
      v9 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v9);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::SelectSingleNode(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR, struct IXMLDOMNode **))(**((_QWORD **)this + 2) + 296LL))(
         *((_QWORD *)this + 2),
         v4,
         &v10);
  SysFreeString(v5);
  if ( v6 > 1 )
  {
    v8 = (UnBCL::XPathException *)UnBCL::Object::operator new(0x38u);
    v12 = v8;
    if ( v8 )
      v8 = (UnBCL::XPathException *)UnBCL::XPathException::XPathException(v8, (struct UnBCL::String *)a2, 0, v6);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "class UnBCL::XmlNode *__cdecl UnBCL::XmlNode::SelectSingleNode(class UnBCL::String *)");
    throw (UnBCL::XPathException **)&pExceptionObject;
  }
  if ( v10 )
    return UnBCL::XmlNode::CreateXmlNode(v10);
  else
    return 0;
}

```

## disassembly

```asm
0x180067670  push    rbx
0x180067672  push    rsi
0x180067673  push    rdi
0x180067674  sub     rsp, 30h
0x180067678  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180067681  mov     rbx, rdx
0x180067684  mov     rsi, rcx
0x180067687  mov     [rsp+48h+arg_8], 0
0x180067690  mov     rcx, [rdx+10h]; psz
0x180067694  call    cs:__imp_SysAllocString
0x18006769a  mov     rdi, rax
0x18006769d  test    rax, rax
0x1800676a0  jz      loc_180067738
0x1800676a6  mov     rcx, [rsi+10h]
0x1800676aa  mov     rax, [rcx]
0x1800676ad  lea     r8, [rsp+48h+arg_8]
0x1800676b2  mov     rdx, rdi
0x1800676b5  mov     rax, [rax+128h]
0x1800676bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676c1  mov     esi, eax
0x1800676c3  mov     rcx, rdi; bstrString
0x1800676c6  call    cs:__imp_SysFreeString
0x1800676cc  cmp     esi, 1
0x1800676cf  ja      short loc_1800676EC
0x1800676d1  mov     rcx, [rsp+48h+arg_8]; struct IXMLDOMNode *
0x1800676d6  test    rcx, rcx
0x1800676d9  jnz     short loc_1800676DF
0x1800676db  xor     eax, eax
0x1800676dd  jmp     short loc_1800676E4
0x1800676df  call    ?CreateXmlNode@XmlNode@UnBCL@@SAPEAV12@PEAUIXMLDOMNode@@@Z; UnBCL::XmlNode::CreateXmlNode(IXMLDOMNode *)
0x1800676e4  add     rsp, 30h
0x1800676e8  pop     rdi
0x1800676e9  pop     rsi
0x1800676ea  pop     rbx
0x1800676eb  retn
0x1800676ec  mov     ecx, 38h ; '8'; unsigned __int64
0x1800676f1  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800676f6  mov     [rsp+48h+arg_18], rax
0x1800676fb  test    rax, rax
0x1800676fe  jz      short loc_180067712
0x180067700  mov     r9d, esi; int
0x180067703  xor     r8d, r8d; struct UnBCL::Exception *
0x180067706  mov     rdx, rbx; struct UnBCL::String *
0x180067709  mov     rcx, rax; this
0x18006770c  call    ??0XPathException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@J@Z; UnBCL::XPathException::XPathException(UnBCL::String *,UnBCL::Exception *,long)
0x180067711  nop
0x180067712  lea     rdx, aClassUnbclXmln_4; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x180067719  mov     rcx, rax
0x18006771c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180067721  mov     [rsp+48h+pExceptionObject], rax
0x180067726  lea     rdx, _TI5PEAVXPathException@UnBCL@@; pThrowInfo
0x18006772d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180067732  call    _CxxThrowException_0
0x180067738  mov     ecx, 38h ; '8'; unsigned __int64
0x18006773d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180067742  mov     [rsp+48h+arg_18], rax
0x180067747  test    rax, rax
0x18006774a  jz      short loc_180067755
0x18006774c  mov     rcx, rax; this
0x18006774f  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180067754  nop
0x180067755  lea     rdx, aClassUnbclXmln_4; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x18006775c  mov     rcx, rax
0x18006775f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180067764  mov     [rsp+48h+pExceptionObject], rax
0x180067769  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x180067770  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180067775  call    _CxxThrowException_0
```
