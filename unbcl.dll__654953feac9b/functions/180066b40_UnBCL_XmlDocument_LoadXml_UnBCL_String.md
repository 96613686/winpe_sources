# UnBCL::XmlDocument::LoadXml(UnBCL::String *)

- ea: `0x180066b40`
- end: `0x180066d0c`
- name: `?LoadXml@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z`
- size: `460`
- prototype: `void __fastcall(UnBCL::XmlDocument *__hidden this, struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x1800489c0`
- `0x18005b790`
- `0x180066b40`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180066b65`
- `OLEAUT32!__imp_SysAllocString` at `0x180066b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b96`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b96`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c9a`

## string_xrefs

- `0x180066ca4`: `void __cdecl UnBCL::XmlDocument::LoadXml(class UnBCL::String *)`
- `0x180066ce8`: `void __cdecl UnBCL::XmlDocument::LoadXml(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::XmlDocument::LoadXml(UnBCL::XmlDocument *this, const OLECHAR **a2)
{
  BSTR v3; // rax
  OLECHAR *v4; // rdi
  int v5; // ebx
  UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // rbx
  UnBCL::XmlException *v8; // rax
  __int64 v9; // rdi
  UnBCL::OutOfMemoryException *v10; // rax
  __int64 v11; // rax
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+40h] [rbp-10h] BYREF
  __int16 v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF
  UnBCL::OutOfMemoryException *v17; // [rsp+98h] [rbp+48h] BYREF

  pExceptionObject[1] = -2;
  v15 = 0;
  v3 = SysAllocString(a2[2]);
  v4 = v3;
  if ( !v3 )
  {
    v10 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v17 = v10;
    if ( v10 )
      v11 = UnBCL::OutOfMemoryException::OutOfMemoryException(v10);
    else
      v11 = 0;
    v16 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v11,
            "void __cdecl UnBCL::XmlDocument::LoadXml(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&v16;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int16 *))(**((_QWORD **)this + 3) + 520LL))(
         *((_QWORD *)this + 3),
         v3,
         &v15);
  SysFreeString(v4);
  if ( v5 || !v15 )
  {
    v12 = 0;
    bstrString = 0;
    LODWORD(v17) = 0;
    LODWORD(v16) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 480LL))(*((_QWORD *)this + 3), &v12) >= 0 )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 72LL))(v12, &bstrString);
      (*(void (__fastcall **)(__int64, UnBCL::OutOfMemoryException **))(*(_QWORD *)v12 + 88LL))(v12, &v17);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 96LL))(v12, &v16);
    }
    v6 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    pExceptionObject[0] = v6;
    if ( v6 )
      v7 = (struct UnBCL::String *)UnBCL::String::String(v6, bstrString);
    else
      v7 = 0;
    v8 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    pExceptionObject[0] = v8;
    if ( v8 )
      v9 = UnBCL::XmlException::XmlException(v8, v7, 0, (int)v17, v16, 0);
    else
      v9 = 0;
    if ( v7 )
      (**(void (__fastcall ***)(struct UnBCL::String *, __int64))v7)(v7, 1);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v9,
                            "void __cdecl UnBCL::XmlDocument::LoadXml(class UnBCL::String *)");
    throw (UnBCL::XmlException **)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180066b40  push    rbp
0x180066b42  push    rbx
0x180066b43  push    rsi
0x180066b44  push    rdi
0x180066b45  push    r14
0x180066b47  mov     rbp, rsp
0x180066b4a  sub     rsp, 50h
0x180066b4e  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180066b56  mov     rsi, rcx
0x180066b59  xor     r14d, r14d
0x180066b5c  mov     [rbp+arg_8], r14w
0x180066b61  mov     rcx, [rdx+10h]; psz
0x180066b65  call    cs:__imp_SysAllocString
0x180066b6b  mov     rdi, rax
0x180066b6e  test    rax, rax
0x180066b71  jz      loc_180066CC8
0x180066b77  mov     rcx, [rsi+18h]
0x180066b7b  mov     rax, [rcx]
0x180066b7e  lea     r8, [rbp+arg_8]
0x180066b82  mov     rdx, rdi
0x180066b85  mov     rax, [rax+208h]
0x180066b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b91  mov     ebx, eax
0x180066b93  mov     rcx, rdi; bstrString
0x180066b96  call    cs:__imp_SysFreeString
0x180066b9c  test    ebx, ebx
0x180066b9e  jnz     short loc_180066BB2
0x180066ba0  cmp     [rbp+arg_8], r14w
0x180066ba5  jz      short loc_180066BB2
0x180066ba7  add     rsp, 50h
0x180066bab  pop     r14
0x180066bad  pop     rdi
0x180066bae  pop     rsi
0x180066baf  pop     rbx
0x180066bb0  pop     rbp
0x180066bb1  retn
0x180066bb2  mov     [rbp+var_20], r14
0x180066bb6  mov     [rbp+bstrString], r14
0x180066bba  mov     dword ptr [rbp+arg_18], r14d
0x180066bbe  mov     dword ptr [rbp+arg_10], r14d
0x180066bc2  mov     rcx, [rsi+18h]
0x180066bc6  mov     rax, [rcx]
0x180066bc9  lea     rdx, [rbp+var_20]
0x180066bcd  mov     rax, [rax+1E0h]
0x180066bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bd9  test    eax, eax
0x180066bdb  js      short loc_180066C19
0x180066bdd  mov     rcx, [rbp+var_20]
0x180066be1  mov     rax, [rcx]
0x180066be4  lea     rdx, [rbp+bstrString]
0x180066be8  mov     rax, [rax+48h]
0x180066bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bf1  mov     rcx, [rbp+var_20]
0x180066bf5  mov     rax, [rcx]
0x180066bf8  lea     rdx, [rbp+arg_18]
0x180066bfc  mov     rax, [rax+58h]
0x180066c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c05  mov     rcx, [rbp+var_20]
0x180066c09  mov     rax, [rcx]
0x180066c0c  lea     rdx, [rbp+arg_10]
0x180066c10  mov     rax, [rax+60h]
0x180066c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c19  mov     ecx, 18h; unsigned __int64
0x180066c1e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066c23  mov     [rbp+pExceptionObject], rax
0x180066c27  test    rax, rax
0x180066c2a  jz      short loc_180066C3D
0x180066c2c  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180066c30  mov     rcx, rax; this
0x180066c33  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180066c38  mov     rbx, rax
0x180066c3b  jmp     short loc_180066C40
0x180066c3d  mov     rbx, r14
0x180066c40  mov     ecx, 40h ; '@'; unsigned __int64
0x180066c45  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066c4a  mov     [rbp+pExceptionObject], rax
0x180066c4e  test    rax, rax
0x180066c51  jz      short loc_180066C76
0x180066c53  mov     [rsp+50h+var_28], r14d; int
0x180066c58  mov     ecx, dword ptr [rbp+arg_10]
0x180066c5b  mov     [rsp+50h+var_30], ecx; int
0x180066c5f  mov     r9d, dword ptr [rbp+arg_18]; int
0x180066c63  xor     r8d, r8d; struct UnBCL::Exception *
0x180066c66  mov     rdx, rbx; struct UnBCL::String *
0x180066c69  mov     rcx, rax; this
0x180066c6c  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x180066c71  mov     rdi, rax
0x180066c74  jmp     short loc_180066C79
0x180066c76  mov     rdi, r14
0x180066c79  test    rbx, rbx
0x180066c7c  jz      short loc_180066C91
0x180066c7e  mov     rax, [rbx]
0x180066c81  mov     edx, 1
0x180066c86  mov     rcx, rbx
0x180066c89  mov     rax, [rax]
0x180066c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c91  mov     rcx, [rbp+bstrString]; bstrString
0x180066c95  test    rcx, rcx
0x180066c98  jz      short loc_180066CA4
0x180066c9a  call    cs:__imp_SysFreeString
0x180066ca0  mov     [rbp+bstrString], r14
0x180066ca4  lea     rdx, aVoidCdeclUnbcl_96; "void __cdecl UnBCL::XmlDocument::LoadXm"...
0x180066cab  mov     rcx, rdi
0x180066cae  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066cb3  mov     [rbp+pExceptionObject], rax
0x180066cb7  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066cbe  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066cc2  call    _CxxThrowException_0
0x180066cc8  mov     ecx, 38h ; '8'; unsigned __int64
0x180066ccd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066cd2  mov     [rbp+arg_18], rax
0x180066cd6  test    rax, rax
0x180066cd9  jz      short loc_180066CE5
0x180066cdb  mov     rcx, rax; this
0x180066cde  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180066ce3  jmp     short loc_180066CE8
0x180066ce5  mov     rax, r14
0x180066ce8  lea     rdx, aVoidCdeclUnbcl_96; "void __cdecl UnBCL::XmlDocument::LoadXm"...
0x180066cef  mov     rcx, rax
0x180066cf2  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066cf7  mov     [rbp+arg_10], rax
0x180066cfb  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x180066d02  lea     rcx, [rbp+arg_10]; pExceptionObject
0x180066d06  call    _CxxThrowException_0
```
