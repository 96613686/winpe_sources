# UnBCL::XmlDocument::CreateNode(UnBCL::XmlNodeType,UnBCL::String *,UnBCL::String *)

- ea: `0x1800660c0`
- end: `0x1800663f2`
- name: `?CreateNode@XmlDocument@UnBCL@@QEAAPEAVXmlNode@2@W4XmlNodeType@2@PEAVString@2@1@Z`
- size: `818`
- prototype: `struct UnBCL::XmlNode *__fastcall(UnBCL::XmlDocument *__hidden this, enum XmlNodeType, struct UnBCL::String *, struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001ea8`
- `0x18000212c`
- `0x18000219c`
- `0x18000225c`
- `0x180009970`
- `0x180009e7c`
- `0x1800475e0`
- `0x1800477d0`
- `0x1800489c0`
- `0x18005b970`
- `0x1800660c0`
- `0x180066400`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006612c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006614b`
- `OLEAUT32!__imp_SysAllocString` at `0x18006612c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006614b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006625f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006626d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006625f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006626d`
- `OLEAUT32!__imp_VariantClear` at `0x180066277`
- `OLEAUT32!__imp_VariantClear` at `0x180066277`

## string_xrefs

- `0x1800662bb`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class UnBCL::String *,class UnBCL::String *)`
- `0x18006630f`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class UnBCL::String *,class UnBCL::String *)`
- `0x18006638e`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class UnBCL::String *,class UnBCL::String *)`
- `0x1800663ce`: `class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class UnBCL::String *,class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct UnBCL::XmlNode *__fastcall UnBCL::XmlDocument::CreateNode(
        UnBCL::XmlDocument *this,
        int a2,
        struct UnBCL::String *a3,
        struct UnBCL::String *a4)
{
  __int64 *v5; // rdi
  OLECHAR *v8; // r14
  const OLECHAR *v9; // rcx
  OLECHAR *v10; // rdi
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  __int64 v20; // rcx
  int v21; // ebx
  UnBCL::NotSupportedException *v23; // rax
  UnBCL::XmlException *v24; // rax
  UnBCL::ArgumentException *v25; // rax
  UnBCL::OutOfMemoryException *v26; // rax
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-29h] BYREF
  UnBCL::ArgumentException *v28; // [rsp+40h] [rbp-19h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-11h] BYREF
  VARIANTARG v30; // [rsp+60h] [rbp+7h] BYREF
  struct IXMLDOMNode *v31; // [rsp+D0h] [rbp+77h] BYREF

  pExceptionObject[1] = -2;
  v5 = (__int64 *)a3;
  if ( !a3 )
  {
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      v25 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
      v28 = v25;
      if ( v25 )
        v25 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v25);
      pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                              v25,
                              "class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class"
                              " UnBCL::String *,class UnBCL::String *)");
      throw (UnBCL::ArgumentException **)pExceptionObject;
    }
    v5 = qword_1800FFEC0;
    if ( dword_1800FFEBC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_1800FFEBC);
      if ( dword_1800FFEBC == -1 )
      {
        UnBCL::String::String((UnBCL::String *)qword_1800FFEC0);
        atexit(UnBCL::XmlDocument::CreateNode_::_5_::_dynamic_atexit_destructor_for__emptyName__);
        Init_thread_footer(&dword_1800FFEBC);
      }
    }
  }
  v8 = SysAllocString((const OLECHAR *)v5[2]);
  if ( !v8 )
  {
    v26 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v28 = v26;
    if ( v26 )
      v26 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v26);
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v26,
                            "class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class U"
                            "nBCL::String *,class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)pExceptionObject;
  }
  if ( a4 )
    v9 = (const OLECHAR *)*((_QWORD *)a4 + 2);
  else
    v9 = 0;
  v10 = SysAllocString(v9);
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 22;
  if ( a2 > 7 )
  {
    v16 = a2 - 8;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            if ( v19 != 1 )
              goto LABEL_38;
            pvarg.lVal = 12;
          }
          else
          {
            pvarg.lVal = 11;
          }
        }
        else
        {
          pvarg.lVal = 10;
        }
      }
      else
      {
        pvarg.lVal = 9;
      }
    }
    else
    {
      pvarg.lVal = 8;
    }
  }
  else if ( a2 == 7 )
  {
    pvarg.lVal = 7;
  }
  else
  {
    v11 = a2 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 == 1 )
              {
                pvarg.lVal = 6;
                goto LABEL_33;
              }
LABEL_38:
              v23 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
              v28 = v23;
              if ( v23 )
                v23 = (UnBCL::NotSupportedException *)UnBCL::NotSupportedException::NotSupportedException(v23);
              pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                                      v23,
                                      "class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeTy"
                                      "pe,class UnBCL::String *,class UnBCL::String *)");
              throw (UnBCL::NotSupportedException **)pExceptionObject;
            }
            pvarg.lVal = 5;
          }
          else
          {
            pvarg.lVal = 4;
          }
        }
        else
        {
          pvarg.lVal = 3;
        }
      }
      else
      {
        pvarg.lVal = 2;
      }
    }
    else
    {
      pvarg.lVal = 1;
    }
  }
LABEL_33:
  v31 = 0;
  v20 = *((_QWORD *)this + 3);
  v30 = pvarg;
  v21 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, OLECHAR *, OLECHAR *, struct IXMLDOMNode **))(*(_QWORD *)v20 + 448LL))(
          v20,
          &v30,
          v8,
          v10,
          &v31);
  SysFreeString(v8);
  if ( v10 )
    SysFreeString(v10);
  VariantClear(&pvarg);
  if ( v21 < 0 || !v31 )
  {
    v24 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    v28 = v24;
    if ( v24 )
      v24 = (UnBCL::XmlException *)UnBCL::XmlException::XmlException(v24, 0, 0, 0, 0, v21);
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v24,
                            "class UnBCL::XmlNode *__cdecl UnBCL::XmlDocument::CreateNode(enum UnBCL::XmlNodeType,class U"
                            "nBCL::String *,class UnBCL::String *)");
    throw (UnBCL::XmlException **)pExceptionObject;
  }
  return UnBCL::XmlNode::CreateXmlNode(v31);
}

```

## disassembly

```asm
0x1800660c0  push    rbp
0x1800660c2  push    rbx
0x1800660c3  push    rsi
0x1800660c4  push    rdi
0x1800660c5  push    r14
0x1800660c7  push    r15
0x1800660c9  lea     rbp, [rsp-2Fh]
0x1800660ce  sub     rsp, 88h
0x1800660d5  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x1800660dd  mov     rsi, r9
0x1800660e0  mov     rdi, r8
0x1800660e3  mov     ebx, edx
0x1800660e5  mov     r15, rcx
0x1800660e8  test    r8, r8
0x1800660eb  jnz     short loc_180066128
0x1800660ed  lea     eax, [rdx-1]
0x1800660f0  cmp     eax, 1
0x1800660f3  jbe     loc_180066372
0x1800660f9  mov     r8d, cs:_tls_index
0x180066100  mov     rax, gs:58h
0x180066109  mov     ecx, 4
0x18006610e  mov     rax, [rax+r8*8]
0x180066112  lea     rdi, qword_1800FFEC0
0x180066119  mov     eax, [rcx+rax]
0x18006611c  cmp     cs:dword_1800FFEBC, eax
0x180066122  jg      loc_180066333
0x180066128  mov     rcx, [rdi+10h]; psz
0x18006612c  call    cs:__imp_SysAllocString
0x180066132  mov     r14, rax
0x180066135  test    rax, rax
0x180066138  jz      loc_1800663B2
0x18006613e  test    rsi, rsi
0x180066141  jz      short loc_180066149
0x180066143  mov     rcx, [rsi+10h]
0x180066147  jmp     short loc_18006614B
0x180066149  xor     ecx, ecx; psz
0x18006614b  call    cs:__imp_SysAllocString
0x180066151  mov     rdi, rax
0x180066154  xorps   xmm0, xmm0
0x180066157  xor     eax, eax
0x180066159  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18006615d  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180066161  mov     eax, 16h
0x180066166  mov     word ptr [rbp+57h+pvarg], ax
0x18006616a  cmp     ebx, 7
0x18006616d  jg      short loc_1800661D2
0x18006616f  jz      short loc_1800661C9
0x180066171  sub     ebx, 1
0x180066174  jz      short loc_1800661C0
0x180066176  sub     ebx, 1
0x180066179  jz      short loc_1800661B7
0x18006617b  sub     ebx, 1
0x18006617e  jz      short loc_1800661AE
0x180066180  sub     ebx, 1
0x180066183  jz      short loc_1800661A5
0x180066185  sub     ebx, 1
0x180066188  jz      short loc_18006619C
0x18006618a  cmp     ebx, 1
0x18006618d  jnz     loc_18006629F
0x180066193  mov     dword ptr [rbp+57h+pvarg+8], 6
0x18006619a  jmp     short loc_18006621A
0x18006619c  mov     dword ptr [rbp+57h+pvarg+8], 5
0x1800661a3  jmp     short loc_18006621A
0x1800661a5  mov     dword ptr [rbp+57h+pvarg+8], 4
0x1800661ac  jmp     short loc_18006621A
0x1800661ae  mov     dword ptr [rbp+57h+pvarg+8], 3
0x1800661b5  jmp     short loc_18006621A
0x1800661b7  mov     dword ptr [rbp+57h+pvarg+8], 2
0x1800661be  jmp     short loc_18006621A
0x1800661c0  mov     dword ptr [rbp+57h+pvarg+8], 1
0x1800661c7  jmp     short loc_18006621A
0x1800661c9  mov     dword ptr [rbp+57h+pvarg+8], 7
0x1800661d0  jmp     short loc_18006621A
0x1800661d2  sub     ebx, 8
0x1800661d5  jz      short loc_180066213
0x1800661d7  sub     ebx, 1
0x1800661da  jz      short loc_18006620A
0x1800661dc  sub     ebx, 1
0x1800661df  jz      short loc_180066201
0x1800661e1  sub     ebx, 1
0x1800661e4  jz      short loc_1800661F8
0x1800661e6  cmp     ebx, 1
0x1800661e9  jnz     loc_18006629F
0x1800661ef  mov     dword ptr [rbp+57h+pvarg+8], 0Ch
0x1800661f6  jmp     short loc_18006621A
0x1800661f8  mov     dword ptr [rbp+57h+pvarg+8], 0Bh
0x1800661ff  jmp     short loc_18006621A
0x180066201  mov     dword ptr [rbp+57h+pvarg+8], 0Ah
0x180066208  jmp     short loc_18006621A
0x18006620a  mov     dword ptr [rbp+57h+pvarg+8], 9
0x180066211  jmp     short loc_18006621A
0x180066213  mov     dword ptr [rbp+57h+pvarg+8], 8
0x18006621a  mov     [rbp+57h+arg_10], 0
0x180066222  mov     rcx, [r15+18h]
0x180066226  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18006622a  movaps  [rbp+57h+var_50], xmm0
0x18006622e  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180066233  movsd   [rbp+57h+var_40], xmm1
0x180066238  mov     rax, [rcx]
0x18006623b  lea     rdx, [rbp+57h+arg_10]
0x18006623f  mov     qword ptr [rsp+0B0h+var_90], rdx
0x180066244  mov     r9, rdi
0x180066247  mov     r8, r14
0x18006624a  lea     rdx, [rbp+57h+var_50]
0x18006624e  mov     rax, [rax+1C0h]
0x180066255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006625a  mov     ebx, eax
0x18006625c  mov     rcx, r14; bstrString
0x18006625f  call    cs:__imp_SysFreeString
0x180066265  test    rdi, rdi
0x180066268  jz      short loc_180066273
0x18006626a  mov     rcx, rdi; bstrString
0x18006626d  call    cs:__imp_SysFreeString
0x180066273  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180066277  call    cs:__imp_VariantClear
0x18006627d  test    ebx, ebx
0x18006627f  js      short loc_1800662DF
0x180066281  mov     rcx, [rbp+57h+arg_10]; struct IXMLDOMNode *
0x180066285  test    rcx, rcx
0x180066288  jz      short loc_1800662DF
0x18006628a  call    ?CreateXmlNode@XmlNode@UnBCL@@SAPEAV12@PEAUIXMLDOMNode@@@Z; UnBCL::XmlNode::CreateXmlNode(IXMLDOMNode *)
0x18006628f  add     rsp, 88h
0x180066296  pop     r15
0x180066298  pop     r14
0x18006629a  pop     rdi
0x18006629b  pop     rsi
0x18006629c  pop     rbx
0x18006629d  pop     rbp
0x18006629e  retn
0x18006629f  mov     ecx, 38h ; '8'; unsigned __int64
0x1800662a4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800662a9  mov     [rbp+57h+var_70], rax
0x1800662ad  test    rax, rax
0x1800662b0  jz      short loc_1800662BB
0x1800662b2  mov     rcx, rax; this
0x1800662b5  call    ??0NotSupportedException@UnBCL@@QEAA@XZ; UnBCL::NotSupportedException::NotSupportedException(void)
0x1800662ba  nop
0x1800662bb  lea     rdx, aClassUnbclXmln_2; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x1800662c2  mov     rcx, rax
0x1800662c5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800662ca  mov     [rbp+57h+pExceptionObject], rax
0x1800662ce  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x1800662d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800662d9  call    _CxxThrowException_0
0x1800662df  mov     ecx, 40h ; '@'; unsigned __int64
0x1800662e4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800662e9  mov     [rbp+57h+var_70], rax
0x1800662ed  test    rax, rax
0x1800662f0  jz      short loc_18006630F
0x1800662f2  mov     [rsp+0B0h+var_88], ebx; int
0x1800662f6  mov     [rsp+0B0h+var_90], 0; int
0x1800662fe  xor     r9d, r9d; int
0x180066301  xor     r8d, r8d; struct UnBCL::Exception *
0x180066304  xor     edx, edx; struct UnBCL::String *
0x180066306  mov     rcx, rax; this
0x180066309  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x18006630e  nop
0x18006630f  lea     rdx, aClassUnbclXmln_2; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x180066316  mov     rcx, rax
0x180066319  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006631e  mov     [rbp+57h+pExceptionObject], rax
0x180066322  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066329  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006632d  call    _CxxThrowException_0
0x180066333  lea     rcx, dword_1800FFEBC
0x18006633a  call    _Init_thread_header
0x18006633f  cmp     cs:dword_1800FFEBC, 0FFFFFFFFh
0x180066346  jnz     loc_180066128
0x18006634c  mov     rcx, rdi; this
0x18006634f  call    ??0String@UnBCL@@QEAA@XZ; UnBCL::String::String(void)
0x180066354  lea     rcx, _UnBCL__XmlDocument__CreateNode____5____dynamic_atexit_destructor_for__emptyName__; void (__cdecl *)()
0x18006635b  call    atexit
0x180066360  nop
0x180066361  lea     rcx, dword_1800FFEBC
0x180066368  call    _Init_thread_footer
0x18006636d  jmp     loc_180066128
0x180066372  mov     ecx, 38h ; '8'; unsigned __int64
0x180066377  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18006637c  mov     [rbp+57h+var_70], rax
0x180066380  test    rax, rax
0x180066383  jz      short loc_18006638E
0x180066385  mov     rcx, rax; this
0x180066388  call    ??0ArgumentException@UnBCL@@QEAA@XZ; UnBCL::ArgumentException::ArgumentException(void)
0x18006638d  nop
0x18006638e  lea     rdx, aClassUnbclXmln_2; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x180066395  mov     rcx, rax
0x180066398  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006639d  mov     [rbp+57h+pExceptionObject], rax
0x1800663a1  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800663a8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800663ac  call    _CxxThrowException_0
0x1800663b2  mov     ecx, 38h ; '8'; unsigned __int64
0x1800663b7  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800663bc  mov     [rbp+57h+var_70], rax
0x1800663c0  test    rax, rax
0x1800663c3  jz      short loc_1800663CE
0x1800663c5  mov     rcx, rax; this
0x1800663c8  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x1800663cd  nop
0x1800663ce  lea     rdx, aClassUnbclXmln_2; "class UnBCL::XmlNode *__cdecl UnBCL::Xm"...
0x1800663d5  mov     rcx, rax
0x1800663d8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800663dd  mov     [rbp+57h+pExceptionObject], rax
0x1800663e1  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x1800663e8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800663ec  call    _CxxThrowException_0
```
