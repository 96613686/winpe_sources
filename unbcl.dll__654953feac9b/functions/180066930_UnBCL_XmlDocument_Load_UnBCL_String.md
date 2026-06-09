# UnBCL::XmlDocument::Load(UnBCL::String *)

- ea: `0x180066930`
- end: `0x180066b2e`
- name: `?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z`
- size: `510`
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
- `0x180066930`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006696e`
- `OLEAUT32!__imp_SysAllocString` at `0x18006696e`
- `OLEAUT32!__imp_SysFreeString` at `0x180066abc`
- `OLEAUT32!__imp_SysFreeString` at `0x180066abc`
- `OLEAUT32!__imp_VariantClear` at `0x1800669b4`
- `OLEAUT32!__imp_VariantClear` at `0x1800669b4`

## string_xrefs

- `0x180066ac6`: `void __cdecl UnBCL::XmlDocument::Load(class UnBCL::String *)`
- `0x180066b0a`: `void __cdecl UnBCL::XmlDocument::Load(class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::XmlDocument::Load(UnBCL::XmlDocument *this, const OLECHAR **a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  UnBCL::String *v5; // rax
  struct UnBCL::String *v6; // rbx
  UnBCL::XmlException *v7; // rax
  __int64 v8; // rdi
  UnBCL::OutOfMemoryException *v9; // rax
  __int64 v10; // rax
  __int64 v11; // [rsp+38h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-11h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+48h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp+7h] BYREF
  VARIANTARG v15; // [rsp+78h] [rbp+27h] BYREF
  __int16 v16; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+C8h] [rbp+77h] BYREF
  UnBCL::OutOfMemoryException *v18; // [rsp+D0h] [rbp+7Fh] BYREF

  pExceptionObject[1] = -2;
  memset(&pvarg, 0, sizeof(pvarg));
  v16 = 0;
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a2[2]);
  if ( !pvarg.llVal )
  {
    v9 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
    v18 = v9;
    if ( v9 )
      v10 = UnBCL::OutOfMemoryException::OutOfMemoryException(v9);
    else
      v10 = 0;
    v17 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v10,
            "void __cdecl UnBCL::XmlDocument::Load(class UnBCL::String *)");
    throw (UnBCL::OutOfMemoryException **)&v17;
  }
  v3 = *((_QWORD *)this + 3);
  v15 = pvarg;
  v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int16 *))(*(_QWORD *)v3 + 464LL))(v3, &v15, &v16);
  VariantClear(&pvarg);
  if ( v4 || !v16 )
  {
    v11 = 0;
    bstrString = 0;
    LODWORD(v18) = 0;
    LODWORD(v17) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 480LL))(*((_QWORD *)this + 3), &v11) >= 0 )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 72LL))(v11, &bstrString);
      (*(void (__fastcall **)(__int64, UnBCL::OutOfMemoryException **))(*(_QWORD *)v11 + 88LL))(v11, &v18);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 96LL))(v11, &v17);
    }
    v5 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    pExceptionObject[0] = v5;
    if ( v5 )
      v6 = (struct UnBCL::String *)UnBCL::String::String(v5, bstrString);
    else
      v6 = 0;
    v7 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    pExceptionObject[0] = v7;
    if ( v7 )
      v8 = UnBCL::XmlException::XmlException(v7, v6, 0, (int)v18, v17, 0);
    else
      v8 = 0;
    if ( v6 )
      (**(void (__fastcall ***)(struct UnBCL::String *, __int64))v6)(v6, 1);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v8,
                            "void __cdecl UnBCL::XmlDocument::Load(class UnBCL::String *)");
    throw (UnBCL::XmlException **)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180066930  mov     rax, rsp
0x180066933  push    rbp
0x180066934  push    rsi
0x180066935  push    rdi
0x180066936  lea     rbp, [rax-5Fh]
0x18006693a  sub     rsp, 90h
0x180066941  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x180066949  mov     [rax+8], rbx
0x18006694d  mov     rdi, rcx
0x180066950  xorps   xmm0, xmm0
0x180066953  xor     eax, eax
0x180066955  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180066959  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18006695d  xor     esi, esi
0x18006695f  mov     [rbp+57h+arg_8], si
0x180066963  lea     eax, [rsi+8]
0x180066966  mov     word ptr [rbp+57h+pvarg], ax
0x18006696a  mov     rcx, [rdx+10h]; psz
0x18006696e  call    cs:__imp_SysAllocString
0x180066974  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180066978  test    rax, rax
0x18006697b  jz      loc_180066AEA
0x180066981  mov     rcx, [rdi+18h]
0x180066985  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180066989  movaps  [rbp+57h+var_30], xmm0
0x18006698d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180066992  movsd   [rbp+57h+var_20], xmm1
0x180066997  mov     rax, [rcx]
0x18006699a  lea     r8, [rbp+57h+arg_8]
0x18006699e  lea     rdx, [rbp+57h+var_30]
0x1800669a2  mov     rax, [rax+1D0h]
0x1800669a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669ae  mov     ebx, eax
0x1800669b0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800669b4  call    cs:__imp_VariantClear
0x1800669ba  test    ebx, ebx
0x1800669bc  jnz     short loc_1800669D7
0x1800669be  cmp     [rbp+57h+arg_8], si
0x1800669c2  jz      short loc_1800669D7
0x1800669c4  mov     rbx, [rsp+0A0h+arg_0]
0x1800669cc  add     rsp, 90h
0x1800669d3  pop     rdi
0x1800669d4  pop     rsi
0x1800669d5  pop     rbp
0x1800669d6  retn
0x1800669d7  mov     [rbp+57h+var_70], rsi
0x1800669db  mov     [rbp+57h+bstrString], rsi
0x1800669df  mov     dword ptr [rbp+57h+arg_18], esi
0x1800669e2  mov     dword ptr [rbp+57h+arg_10], esi
0x1800669e5  mov     rcx, [rdi+18h]
0x1800669e9  mov     rax, [rcx]
0x1800669ec  lea     rdx, [rbp+57h+var_70]
0x1800669f0  mov     rax, [rax+1E0h]
0x1800669f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669fc  test    eax, eax
0x1800669fe  js      short loc_180066A3C
0x180066a00  mov     rcx, [rbp+57h+var_70]
0x180066a04  mov     rax, [rcx]
0x180066a07  lea     rdx, [rbp+57h+bstrString]
0x180066a0b  mov     rax, [rax+48h]
0x180066a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a14  mov     rcx, [rbp+57h+var_70]
0x180066a18  mov     rax, [rcx]
0x180066a1b  lea     rdx, [rbp+57h+arg_18]
0x180066a1f  mov     rax, [rax+58h]
0x180066a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a28  mov     rcx, [rbp+57h+var_70]
0x180066a2c  mov     rax, [rcx]
0x180066a2f  lea     rdx, [rbp+57h+arg_10]
0x180066a33  mov     rax, [rax+60h]
0x180066a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a3c  mov     ecx, 18h; unsigned __int64
0x180066a41  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066a46  mov     [rbp+57h+pExceptionObject], rax
0x180066a4a  test    rax, rax
0x180066a4d  jz      short loc_180066A60
0x180066a4f  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180066a53  mov     rcx, rax; this
0x180066a56  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180066a5b  mov     rbx, rax
0x180066a5e  jmp     short loc_180066A63
0x180066a60  mov     rbx, rsi
0x180066a63  mov     ecx, 40h ; '@'; unsigned __int64
0x180066a68  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066a6d  mov     [rbp+57h+pExceptionObject], rax
0x180066a71  test    rax, rax
0x180066a74  jz      short loc_180066A98
0x180066a76  mov     [rsp+28h], esi; int
0x180066a7a  mov     ecx, dword ptr [rbp+57h+arg_10]
0x180066a7d  mov     [rsp+0A0h+var_80], ecx; int
0x180066a81  mov     r9d, dword ptr [rbp+57h+arg_18]; int
0x180066a85  xor     r8d, r8d; struct UnBCL::Exception *
0x180066a88  mov     rdx, rbx; struct UnBCL::String *
0x180066a8b  mov     rcx, rax; this
0x180066a8e  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x180066a93  mov     rdi, rax
0x180066a96  jmp     short loc_180066A9B
0x180066a98  mov     rdi, rsi
0x180066a9b  test    rbx, rbx
0x180066a9e  jz      short loc_180066AB3
0x180066aa0  mov     rax, [rbx]
0x180066aa3  mov     edx, 1
0x180066aa8  mov     rcx, rbx
0x180066aab  mov     rax, [rax]
0x180066aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ab3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180066ab7  test    rcx, rcx
0x180066aba  jz      short loc_180066AC6
0x180066abc  call    cs:__imp_SysFreeString
0x180066ac2  mov     [rbp+57h+bstrString], rsi
0x180066ac6  lea     rdx, aVoidCdeclUnbcl_88; "void __cdecl UnBCL::XmlDocument::Load(c"...
0x180066acd  mov     rcx, rdi
0x180066ad0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066ad5  mov     [rbp+57h+pExceptionObject], rax
0x180066ad9  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066ae0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180066ae4  call    _CxxThrowException_0
0x180066aea  mov     ecx, 38h ; '8'; unsigned __int64
0x180066aef  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180066af4  mov     [rbp+57h+arg_18], rax
0x180066af8  test    rax, rax
0x180066afb  jz      short loc_180066B07
0x180066afd  mov     rcx, rax; this
0x180066b00  call    ??0OutOfMemoryException@UnBCL@@QEAA@XZ; UnBCL::OutOfMemoryException::OutOfMemoryException(void)
0x180066b05  jmp     short loc_180066B0A
0x180066b07  mov     rax, rsi
0x180066b0a  lea     rdx, aVoidCdeclUnbcl_88; "void __cdecl UnBCL::XmlDocument::Load(c"...
0x180066b11  mov     rcx, rax
0x180066b14  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180066b19  mov     [rbp+57h+arg_10], rax
0x180066b1d  lea     rdx, _TI5PEAVOutOfMemoryException@UnBCL@@; pThrowInfo
0x180066b24  lea     rcx, [rbp+57h+arg_10]; pExceptionObject
0x180066b28  call    _CxxThrowException_0
```
