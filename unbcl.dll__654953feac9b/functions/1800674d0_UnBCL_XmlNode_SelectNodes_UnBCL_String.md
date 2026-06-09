# UnBCL::XmlNode::SelectNodes(UnBCL::String *)

- ea: `0x1800674d0`
- end: `0x180067627`
- name: `?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z`
- size: `343`
- prototype: `struct UnBCL::XmlNodeList *(UnBCL::XmlNode *__hidden this, struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180067630`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x1800489c0`
- `0x1800674d0`
- `0x1800684d0`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800674f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800674f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180067526`
- `OLEAUT32!__imp_SysFreeString` at `0x180067526`

## string_xrefs

- `0x1800675be`: `class UnBCL::XmlNodeList *__cdecl UnBCL::XmlNode::SelectNodes(class UnBCL::String *)`
- `0x180067601`: `class UnBCL::XmlNodeList *__cdecl UnBCL::XmlNode::SelectNodes(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::XmlNodeList *__fastcall UnBCL::XmlNode::SelectNodes(UnBCL::XmlNode *this, const OLECHAR **a2)
{
  BSTR v4; // rax
  OLECHAR *v5; // rbx
  int v6; // esi
  _DWORD *v8; // rax
  _DWORD *v9; // rdx
  __int64 v10; // rcx
  UnBCL::XPathException *v11; // rax
  UnBCL::OutOfMemoryException *v12; // rax
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 pExceptionObject; // [rsp+60h] [rbp+18h] BYREF
  UnBCL::OutOfMemoryException *v15; // [rsp+68h] [rbp+20h]

  v13 = 0;
  v4 = SysAllocString(a2[2]);
  v5 = v4;
  if ( !v4 )
  {
    v12 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v15 = v12;
    if ( v12 )
      v12 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(v12);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::XmlNodeList *__cdecl UnBCL::XmlNode::SelectNodes(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**((_QWORD **)this + 2) + 288LL))(
         *((_QWORD *)this + 2),
         v4,
         &v13);
  SysFreeString(v5);
  if ( v6 )
  {
    v11 = (UnBCL::XPathException *)UnBCL::Object::operator new(0x38u);
    v15 = v11;
    if ( v11 )
      v11 = (UnBCL::XPathException *)UnBCL::XPathException::XPathException(v11, (struct UnBCL::String *)a2, 0, v6);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "class UnBCL::XmlNodeList *__cdecl UnBCL::XmlNode::SelectNodes(class UnBCL::String *)");
    throw (UnBCL::XPathException **)&pExceptionObject;
  }
  if ( !v13 )
    return 0;
  v8 = UnBCL::Object::operator new(0x18u);
  v9 = v8;
  pExceptionObject = (__int64)v8;
  if ( !v8 )
    return 0;
  v10 = v13;
  *(_QWORD *)v8 = &UnBCL::Object::`vftable';
  v8[2] = 0;
  v8[3] = _InterlockedIncrement(&dword_1800FFC68);
  *(_QWORD *)v8 = &UnBCL::XmlNodeList::`vftable';
  *((_QWORD *)v8 + 2) = v10;
  return (struct UnBCL::XmlNodeList *)v9;
}

```

## disassembly

```asm
0x1800674d0  push    rbx
0x1800674d2  push    rsi
0x1800674d3  push    rdi
0x1800674d4  sub     rsp, 30h
0x1800674d8  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800674e1  mov     rdi, rdx
0x1800674e4  mov     rsi, rcx
0x1800674e7  mov     [rsp+48h+arg_8], 0
0x1800674f0  mov     rcx, [rdx+10h]; psz
0x1800674f4  call    cs:__imp_SysAllocString
0x1800674fa  mov     rbx, rax
0x1800674fd  test    rax, rax
0x180067500  jz      loc_1800675E4
0x180067506  mov     rcx, [rsi+10h]
0x18006750a  mov     rax, [rcx]
0x18006750d  lea     r8, [rsp+48h+arg_8]
0x180067512  mov     rdx, rbx
0x180067515  mov     rax, [rax+120h]
0x18006751c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067521  mov     esi, eax
0x180067523  mov     rcx, rbx; bstrString
0x180067526  call    cs:__imp_SysFreeString
0x18006752c  test    esi, esi
0x18006752e  jnz     short loc_180067598
0x180067530  cmp     [rsp+48h+arg_8], 0
0x180067536  jnz     short loc_18006753C
0x180067538  xor     eax, eax
0x18006753a  jmp     short loc_180067590
0x18006753c  mov     ecx, 18h; unsigned __int64
0x180067541  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180067546  mov     rdx, rax
0x180067549  mov     [rsp+48h+pExceptionObject], rax
0x18006754e  test    rax, rax
0x180067551  jz      short loc_18006758B
0x180067553  mov     rcx, [rsp+48h+arg_8]
0x180067558  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18006755f  mov     [rdx], rax
0x180067562  mov     dword ptr [rdx+8], 0
0x180067569  mov     eax, 1
0x18006756e  lock xadd cs:dword_1800FFC68, eax
0x180067576  inc     eax
0x180067578  mov     [rdx+0Ch], eax
0x18006757b  lea     rax, ??_7XmlNodeList@UnBCL@@6B@; const UnBCL::XmlNodeList::`vftable'
0x180067582  mov     [rdx], rax
0x180067585  mov     [rdx+10h], rcx
0x180067589  jmp     short loc_18006758D
0x18006758b  xor     edx, edx
0x18006758d  mov     rax, rdx
0x180067590  add     rsp, 30h
0x180067594  pop     rdi
0x180067595  pop     rsi
0x180067596  pop     rbx
0x180067597  retn
0x180067598  mov     ecx, 38h ; '8'; unsigned __int64
0x18006759d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800675a2  mov     [rsp+48h+arg_18], rax
0x1800675a7  test    rax, rax
0x1800675aa  jz      short loc_1800675BE
0x1800675ac  mov     r9d, esi; int
0x1800675af  xor     r8d, r8d; struct UnBCL::Exception *
0x1800675b2  mov     rdx, rdi; struct UnBCL::String *
0x1800675b5  mov     rcx, rax; this
0x1800675b8  call    ??0XPathException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@J@Z; UnBCL::XPathException::XPathException(UnBCL::String *,UnBCL::Exception *,long)
0x1800675bd  nop
0x1800675be  lea     rdx, aClassUnbclXmln_5; "class UnBCL::XmlNodeList *__cdecl UnBCL"...
0x1800675c5  mov     rcx, rax
0x1800675c8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800675cd  mov     [rsp+48h+pExceptionObject], rax
0x1800675d2  lea     rdx, _TI5PEAVXPathException@UnBCL@@; pThrowInfo
0x1800675d9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800675de  call    _CxxThrowException_0
0x1800675e4  mov     ecx, 38h ; '8'; unsigned __int64
0x1800675e9  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800675ee  mov     [rsp+48h+arg_18], rax
0x1800675f3  test    rax, rax
0x1800675f6  jz      short loc_180067601
0x1800675f8  mov     rcx, rax; this
0x1800675fb  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180067600  nop
0x180067601  lea     rdx, aClassUnbclXmln_5; "class UnBCL::XmlNodeList *__cdecl UnBCL"...
0x180067608  mov     rcx, rax
0x18006760b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180067610  mov     [rsp+48h+pExceptionObject], rax
0x180067615  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x18006761c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180067621  call    _CxxThrowException_0
```
