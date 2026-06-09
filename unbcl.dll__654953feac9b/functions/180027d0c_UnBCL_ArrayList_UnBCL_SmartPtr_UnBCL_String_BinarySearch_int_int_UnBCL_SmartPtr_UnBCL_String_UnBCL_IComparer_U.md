# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::BinarySearch(int,int,UnBCL::SmartPtr<UnBCL::String>,UnBCL::IComparer<UnBCL::SmartPtr<UnBCL::String>> *)

- ea: `0x180027d0c`
- end: `0x180027f79`
- name: `?BinarySearch@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@AEAAHHHV?$SmartPtr@VString@UnBCL@@@2@PEAU?$IComparer@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@2@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027f80`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800098b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180011530`
- `0x180027d0c`
- `0x180028294`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180027f09`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`
- `0x180027f53`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        __int64 (__fastcall ***a5)(_QWORD, __int64, __int64))
{
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // r14d
  int v10; // r12d
  unsigned int v11; // r15d
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(_QWORD, __int64, __int64); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  UnBCL::ArgumentOutOfRangeException *v21; // rax
  UnBCL::ArgumentException *v22; // rax
  UnBCL::InvalidOperationException *v23; // rax
  UnBCL::InvalidOperationException *v24; // rbx
  UnBCL::String *v25; // rax
  UnBCL::InvalidOperationException *v26; // rax
  _QWORD v27[2]; // [rsp+28h] [rbp-D0h] BYREF
  int v28; // [rsp+38h] [rbp-C0h]
  __int64 v29; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-A8h] BYREF
  __int64 pExceptionObject; // [rsp+58h] [rbp-A0h] BYREF
  UnBCL::ArgumentException *v33; // [rsp+60h] [rbp-98h]
  UnBCL::String *v34; // [rsp+68h] [rbp-90h]
  __int64 v35; // [rsp+70h] [rbp-88h]
  _BYTE *v36; // [rsp+78h] [rbp-80h]
  struct UnBCL::Exception *v37; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v38[16]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v39[16]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v40[16]; // [rsp+A8h] [rbp-50h] BYREF
  _BYTE v41[24]; // [rsp+B8h] [rbp-40h] BYREF

  v35 = -2;
  if ( a3 < 0 )
  {
    v21 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v21 )
      v21 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v21,
                                                    L"negative index or count to ArrayList#BinarySearch");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v21,
                         "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int"
                         ",class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class"
                         " UnBCL::String> > *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v22 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v33 = v22;
    if ( v22 )
      v22 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v22,
                                          L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
    v29 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v22,
            "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL:"
            ":SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
    throw (UnBCL::ArgumentException **)&v29;
  }
  v9 = 0;
  v10 = a3 - 1;
  while ( v9 <= v10 )
  {
    v11 = (v10 + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v11);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v27, v13);
    try
    {
      if ( a5 )
      {
        v14 = **a5;
        v33 = (UnBCL::ArgumentException *)v38;
        v15 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v38, v27);
        v36 = v39;
        v16 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v39, a4);
        v17 = v14(a5, v16, v15);
      }
      else
      {
        v34 = (UnBCL::String *)v40;
        v18 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v40, v27);
        v19 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v41, a4);
        v17 = UnBCL::MP::ObjectSmartPtrCompare<UnBCL::SmartPtr<UnBCL::String>>::Compare(v19, v18);
      }
      v28 = v17;
    }
    catch ( UnBCL::Exception *v37 )
    {
      v23 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v24 = v23;
      if ( v23 )
      {
        v25 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v34 = v25;
        if ( v25 )
          v25 = (UnBCL::String *)UnBCL::String::String(v25, L"Compare failed -- bad comparison routines?");
        v23 = (UnBCL::InvalidOperationException *)UnBCL::InvalidOperationException::InvalidOperationException(
                                                    v24,
                                                    v25,
                                                    v37);
      }
      v30 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v23,
              "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBC"
              "L::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
      throw (UnBCL::InvalidOperationException **)&v30;
    }
    catch ( ... )
    {
      v26 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      if ( v26 )
        v26 = (UnBCL::InvalidOperationException *)UnBCL::InvalidOperationException::InvalidOperationException(
                                                    v26,
                                                    L"sort failed -- bad comparison routines?");
      v31 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v26,
              "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBC"
              "L::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
      throw (UnBCL::InvalidOperationException **)&v31;
    }
    if ( !v17 )
    {
      v27[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v27);
      *a4 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(a4);
      return v11;
    }
    if ( v17 >= 0 )
      v9 = v11 + 1;
    else
      v10 = v11 - 1;
    v27[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v27);
  }
  *a4 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(a4);
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x180027d0c  mov     rax, rsp
0x180027d0f  mov     [rax+20h], r9
0x180027d13  push    rdi
0x180027d14  push    r12
0x180027d16  push    r13
0x180027d18  push    r14
0x180027d1a  push    r15
0x180027d1c  sub     rsp, 0D0h
0x180027d23  mov     [rsp+0F8h+var_88], 0FFFFFFFFFFFFFFFEh
0x180027d2c  mov     [rax+8], rbx
0x180027d30  mov     [rax+10h], rsi
0x180027d34  mov     rsi, r9
0x180027d37  mov     ebx, r8d
0x180027d3a  mov     r13, rcx
0x180027d3d  test    r8d, r8d
0x180027d40  js      loc_180027EE5
0x180027d46  mov     rax, [rcx+8]
0x180027d4a  movsxd  rcx, dword ptr [rax+0Ch]
0x180027d4e  add     rcx, 8
0x180027d52  add     rcx, r13
0x180027d55  mov     rax, [rcx]
0x180027d58  mov     rax, [rax]
0x180027d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d60  cmp     eax, ebx
0x180027d62  jl      loc_180027F2F
0x180027d68  xor     r14d, r14d
0x180027d6b  lea     r12d, [rbx-1]
0x180027d6f  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180027d76  cmp     r14d, r12d
0x180027d79  jg      loc_180027ED2
0x180027d7f  lea     eax, [r12+r14]
0x180027d83  cdq
0x180027d84  sub     eax, edx
0x180027d86  sar     eax, 1
0x180027d88  mov     r15d, eax
0x180027d8b  mov     rcx, [r13+8]
0x180027d8f  movsxd  rcx, dword ptr [rcx+10h]
0x180027d93  add     rcx, 8
0x180027d97  add     rcx, r13
0x180027d9a  mov     rdx, [rcx]
0x180027d9d  mov     rax, [rdx+18h]
0x180027da1  mov     edx, r15d
0x180027da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da9  mov     rdx, rax
0x180027dac  lea     rcx, [rsp+0F8h+var_D0]
0x180027db1  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180027db6  nop
0x180027db7  mov     rax, [rsp+0F8h+arg_20]
0x180027dbf  lea     rdx, [rsp+0F8h+var_D0]
0x180027dc4  test    rax, rax
0x180027dc7  jz      short loc_180027E29
0x180027dc9  mov     rax, [rax]
0x180027dcc  mov     rdi, [rax]
0x180027dcf  lea     rax, [rsp+0F8h+var_70]
0x180027dd7  mov     [rsp+0F8h+var_98], rax
0x180027ddc  lea     rcx, [rsp+0F8h+var_70]
0x180027de4  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180027de9  mov     rbx, rax
0x180027dec  lea     rax, [rsp+0F8h+var_60]
0x180027df4  mov     [rsp+0F8h+var_80], rax
0x180027df9  mov     rdx, rsi
0x180027dfc  lea     rcx, [rsp+0F8h+var_60]
0x180027e04  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180027e09  nop
0x180027e0a  mov     r8, rbx
0x180027e0d  mov     rdx, rax
0x180027e10  mov     rcx, [rsp+0F8h+arg_20]
0x180027e18  mov     rax, rdi
0x180027e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e20  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180027e27  jmp     short loc_180027E6F
0x180027e29  lea     rax, [rsp+0F8h+var_50]
0x180027e31  mov     [rsp+0F8h+var_90], rax
0x180027e36  lea     rcx, [rsp+0F8h+var_50]
0x180027e3e  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180027e43  mov     rbx, rax
0x180027e46  lea     rax, [rsp+0F8h+var_40]
0x180027e4e  mov     [rsp+0F8h+var_D8], rax
0x180027e53  mov     rdx, rsi
0x180027e56  lea     rcx, [rsp+0F8h+var_40]
0x180027e5e  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180027e63  nop
0x180027e64  mov     rdx, rbx
0x180027e67  mov     rcx, rax
0x180027e6a  call    ?Compare@?$ObjectSmartPtrCompare@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@MP@UnBCL@@SAHV?$SmartPtr@VString@UnBCL@@@3@0@Z; UnBCL::MP::ObjectSmartPtrCompare<UnBCL::SmartPtr<UnBCL::String>>::Compare(UnBCL::SmartPtr<UnBCL::String>,UnBCL::SmartPtr<UnBCL::String>)
0x180027e6f  mov     [rsp+0F8h+var_C0], eax
0x180027e73  test    eax, eax
0x180027e75  jnz     short loc_180027EB2
0x180027e77  mov     [rsp+0F8h+var_D0], rdi
0x180027e7c  lea     rcx, [rsp+0F8h+var_D0]
0x180027e81  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180027e86  nop
0x180027e87  mov     [rsi], rdi
0x180027e8a  mov     rcx, rsi
0x180027e8d  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180027e92  mov     eax, r15d
0x180027e95  lea     r11, [rsp+0F8h+var_28]
0x180027e9d  mov     rbx, [r11+30h]
0x180027ea1  mov     rsi, [r11+38h]
0x180027ea5  mov     rsp, r11
0x180027ea8  pop     r15
0x180027eaa  pop     r14
0x180027eac  pop     r13
0x180027eae  pop     r12
0x180027eb0  pop     rdi
0x180027eb1  retn
0x180027eb2  jns     short loc_180027EBA
0x180027eb4  lea     r12d, [r15-1]
0x180027eb8  jmp     short loc_180027EBE
0x180027eba  lea     r14d, [r15+1]
0x180027ebe  mov     [rsp+0F8h+var_D0], rdi
0x180027ec3  lea     rcx, [rsp+0F8h+var_D0]
0x180027ec8  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180027ecd  jmp     loc_180027D76
0x180027ed2  not     r14d
0x180027ed5  mov     [rsi], rdi
0x180027ed8  mov     rcx, rsi
0x180027edb  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180027ee0  mov     eax, r14d
0x180027ee3  jmp     short loc_180027E95
0x180027ee5  mov     ecx, 38h ; '8'; unsigned __int64
0x180027eea  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027eef  mov     [rsp+0F8h+var_D8], rax
0x180027ef4  test    rax, rax
0x180027ef7  jz      short loc_180027F09
0x180027ef9  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180027f00  mov     rcx, rax; this
0x180027f03  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180027f08  nop
0x180027f09  lea     rdx, aIntCdeclUnbclA_31; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180027f10  mov     rcx, rax
0x180027f13  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027f18  mov     [rsp+0F8h+pExceptionObject], rax
0x180027f1d  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180027f24  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180027f29  call    _CxxThrowException_0
0x180027f2f  mov     ecx, 38h ; '8'; unsigned __int64
0x180027f34  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027f39  mov     [rsp+0F8h+var_98], rax
0x180027f3e  test    rax, rax
0x180027f41  jz      short loc_180027F53
0x180027f43  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x180027f4a  mov     rcx, rax; this
0x180027f4d  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180027f52  nop
0x180027f53  lea     rdx, aIntCdeclUnbclA_31; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180027f5a  mov     rcx, rax
0x180027f5d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027f62  mov     [rsp+0F8h+var_B8], rax
0x180027f67  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180027f6e  lea     rcx, [rsp+0F8h+var_B8]; pExceptionObject
0x180027f73  call    _CxxThrowException_0
```
