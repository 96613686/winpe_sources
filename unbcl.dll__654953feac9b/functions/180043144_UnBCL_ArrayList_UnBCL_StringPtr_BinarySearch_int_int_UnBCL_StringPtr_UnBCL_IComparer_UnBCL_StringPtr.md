# UnBCL::ArrayList<UnBCL::StringPtr>::BinarySearch(int,int,UnBCL::StringPtr,UnBCL::IComparer<UnBCL::StringPtr> *)

- ea: `0x180043144`
- end: `0x1800433cd`
- name: `?BinarySearch@?$ArrayList@VStringPtr@UnBCL@@@UnBCL@@AEAAHHHVStringPtr@2@PEAU?$IComparer@VStringPtr@UnBCL@@@2@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800433e0`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800098b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180043144`
- `0x1800437a0`
- `0x1800477d0`
- `0x1800600d0`
- `0x18006f010`

## string_xrefs

- `0x18004335d`: `int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringPtr,struct UnBCL::IComparer<class UnBCL::StringPtr> *)`
- `0x1800433a7`: `int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringPtr,struct UnBCL::IComparer<class UnBCL::StringPtr> *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UnBCL::ArrayList<UnBCL::StringPtr>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        const struct UnBCL::StringPtr *a4,
        __int64 (__fastcall ***a5)(_QWORD, __int64, __int64))
{
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // esi
  int v10; // r12d
  unsigned int v11; // r15d
  __int64 v12; // rcx
  const struct UnBCL::StringPtr *v13; // rax
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
  __int64 v27; // [rsp+30h] [rbp-118h] BYREF
  __int64 v28; // [rsp+38h] [rbp-110h] BYREF
  __int64 v29; // [rsp+40h] [rbp-108h] BYREF
  __int64 pExceptionObject; // [rsp+48h] [rbp-100h] BYREF
  UnBCL::ArgumentException *v31; // [rsp+50h] [rbp-F8h]
  UnBCL::String *v32; // [rsp+58h] [rbp-F0h]
  _BYTE v33[16]; // [rsp+60h] [rbp-E8h] BYREF
  _QWORD v34[4]; // [rsp+70h] [rbp-D8h] BYREF
  struct UnBCL::Exception *v35; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v36[32]; // [rsp+98h] [rbp-B0h] BYREF
  _BYTE v37[32]; // [rsp+B8h] [rbp-90h] BYREF
  _BYTE v38[32]; // [rsp+D8h] [rbp-70h] BYREF
  _BYTE v39[40]; // [rsp+F8h] [rbp-50h] BYREF

  v34[2] = -2;
  if ( a3 < 0 )
  {
    v21 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v21 )
      v21 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v21,
                                                    L"negative index or count to ArrayList#BinarySearch");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v21,
                         "int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringP"
                         "tr,struct UnBCL::IComparer<class UnBCL::StringPtr> *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v22 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v31 = v22;
    if ( v22 )
      v22 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v22,
                                          L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
    v27 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v22,
            "int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringPtr,struct UnB"
            "CL::IComparer<class UnBCL::StringPtr> *)");
    throw (UnBCL::ArgumentException **)&v27;
  }
  v9 = 0;
  v10 = a3 - 1;
  while ( v9 <= v10 )
  {
    v11 = (v10 + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = (const struct UnBCL::StringPtr *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(
                                             v12,
                                             v11);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v33, v13);
    try
    {
      if ( a5 )
      {
        v14 = **a5;
        v31 = (UnBCL::ArgumentException *)v36;
        v15 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v36, (const struct UnBCL::StringPtr *)v33);
        v34[3] = v37;
        v16 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v37, a4);
        v17 = v14(a5, v16, v15);
      }
      else
      {
        v32 = (UnBCL::String *)v38;
        v18 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v38, (const struct UnBCL::StringPtr *)v33);
        v19 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v39, a4);
        v17 = UnBCL::MP::ObjectSmartPtrCompare<UnBCL::StringPtr>::Compare(v19, v18);
      }
    }
    catch ( UnBCL::Exception *v35 )
    {
      v23 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v24 = v23;
      if ( v23 )
      {
        v25 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v32 = v25;
        if ( v25 )
          v25 = (UnBCL::String *)UnBCL::String::String(v25, L"Compare failed -- bad comparison routines?");
        v23 = (UnBCL::InvalidOperationException *)UnBCL::InvalidOperationException::InvalidOperationException(
                                                    v24,
                                                    v25,
                                                    v35);
      }
      v28 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v23,
              "int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringPtr,struct U"
              "nBCL::IComparer<class UnBCL::StringPtr> *)");
      throw (UnBCL::InvalidOperationException **)&v28;
    }
    catch ( ... )
    {
      v26 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      if ( v26 )
        v26 = (UnBCL::InvalidOperationException *)UnBCL::InvalidOperationException::InvalidOperationException(
                                                    v26,
                                                    L"sort failed -- bad comparison routines?");
      v29 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v26,
              "int __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::BinarySearch(int,int,class UnBCL::StringPtr,struct U"
              "nBCL::IComparer<class UnBCL::StringPtr> *)");
      throw (UnBCL::InvalidOperationException **)&v29;
    }
    if ( !v17 )
    {
      v34[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v34);
      *((_QWORD *)a4 + 2) = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign((char *)a4 + 16);
      return v11;
    }
    if ( v17 >= 0 )
      v9 = v11 + 1;
    else
      v10 = v11 - 1;
    v34[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v34);
  }
  *((_QWORD *)a4 + 2) = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign((char *)a4 + 16);
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x180043144  mov     rax, rsp
0x180043147  mov     [rax+20h], r9
0x18004314b  push    rdi
0x18004314c  push    r12
0x18004314e  push    r13
0x180043150  push    r14
0x180043152  push    r15
0x180043154  sub     rsp, 120h
0x18004315b  mov     qword ptr [rax-0C8h], 0FFFFFFFFFFFFFFFEh
0x180043166  mov     [rax+8], rbx
0x18004316a  mov     [rax+10h], rsi
0x18004316e  mov     r14, r9
0x180043171  mov     ebx, r8d
0x180043174  mov     r13, rcx
0x180043177  test    r8d, r8d
0x18004317a  js      loc_180043339
0x180043180  mov     rax, [rcx+8]
0x180043184  movsxd  rcx, dword ptr [rax+0Ch]
0x180043188  add     rcx, 8
0x18004318c  add     rcx, r13
0x18004318f  mov     rax, [rcx]
0x180043192  mov     rax, [rax]
0x180043195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004319a  cmp     eax, ebx
0x18004319c  jl      loc_180043383
0x1800431a2  xor     esi, esi
0x1800431a4  lea     r12d, [rbx-1]
0x1800431a8  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x1800431af  cmp     esi, r12d
0x1800431b2  jg      loc_180043327
0x1800431b8  lea     eax, [r12+rsi]
0x1800431bc  cdq
0x1800431bd  sub     eax, edx
0x1800431bf  sar     eax, 1
0x1800431c1  mov     r15d, eax
0x1800431c4  mov     rcx, [r13+8]
0x1800431c8  movsxd  rcx, dword ptr [rcx+10h]
0x1800431cc  add     rcx, 8
0x1800431d0  add     rcx, r13
0x1800431d3  mov     rdx, [rcx]
0x1800431d6  mov     rax, [rdx+18h]
0x1800431da  mov     edx, r15d
0x1800431dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431e2  mov     rdx, rax; struct UnBCL::StringPtr *
0x1800431e5  mov     r8d, 1
0x1800431eb  lea     rcx, [rsp+148h+var_E8]; this
0x1800431f0  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x1800431f5  nop
0x1800431f6  mov     rax, [rsp+148h+arg_20]
0x1800431fe  mov     r8d, 1
0x180043204  lea     rdx, [rsp+148h+var_E8]; struct UnBCL::StringPtr *
0x180043209  test    rax, rax
0x18004320c  jz      short loc_180043277
0x18004320e  mov     rax, [rax]
0x180043211  mov     rdi, [rax]
0x180043214  lea     rax, [rsp+148h+var_B0]
0x18004321c  mov     [rsp+148h+var_F8], rax
0x180043221  lea     rcx, [rsp+148h+var_B0]; this
0x180043229  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x18004322e  mov     rbx, rax
0x180043231  lea     rax, [rsp+148h+var_90]
0x180043239  mov     [rsp+148h+var_C0], rax
0x180043241  mov     r8d, 1
0x180043247  mov     rdx, r14; struct UnBCL::StringPtr *
0x18004324a  lea     rcx, [rsp+148h+var_90]; this
0x180043252  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x180043257  nop
0x180043258  mov     r8, rbx
0x18004325b  mov     rdx, rax
0x18004325e  mov     rcx, [rsp+148h+arg_20]
0x180043266  mov     rax, rdi
0x180043269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004326e  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180043275  jmp     short loc_1800432C3
0x180043277  lea     rax, [rsp+148h+var_70]
0x18004327f  mov     [rsp+148h+var_F0], rax
0x180043284  lea     rcx, [rsp+148h+var_70]; this
0x18004328c  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x180043291  mov     rbx, rax
0x180043294  lea     rax, [rsp+148h+var_50]
0x18004329c  mov     [rsp+148h+var_128], rax
0x1800432a1  mov     r8d, 1
0x1800432a7  mov     rdx, r14; struct UnBCL::StringPtr *
0x1800432aa  lea     rcx, [rsp+148h+var_50]; this
0x1800432b2  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x1800432b7  nop
0x1800432b8  mov     rdx, rbx
0x1800432bb  mov     rcx, rax
0x1800432be  call    ?Compare@?$ObjectSmartPtrCompare@VStringPtr@UnBCL@@@MP@UnBCL@@SAHVStringPtr@3@0@Z; UnBCL::MP::ObjectSmartPtrCompare<UnBCL::StringPtr>::Compare(UnBCL::StringPtr,UnBCL::StringPtr)
0x1800432c3  mov     [rsp+148h+var_120], eax
0x1800432c7  test    eax, eax
0x1800432c9  jnz     short loc_180043307
0x1800432cb  mov     [rsp+148h+var_D8], rdi
0x1800432d0  lea     rcx, [rsp+148h+var_D8]
0x1800432d5  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800432da  nop
0x1800432db  lea     rcx, [r14+10h]
0x1800432df  mov     [rcx], rdi
0x1800432e2  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800432e7  mov     eax, r15d
0x1800432ea  lea     r11, [rsp+148h+var_28]
0x1800432f2  mov     rbx, [r11+30h]
0x1800432f6  mov     rsi, [r11+38h]
0x1800432fa  mov     rsp, r11
0x1800432fd  pop     r15
0x1800432ff  pop     r14
0x180043301  pop     r13
0x180043303  pop     r12
0x180043305  pop     rdi
0x180043306  retn
0x180043307  jns     short loc_18004330F
0x180043309  lea     r12d, [r15-1]
0x18004330d  jmp     short loc_180043313
0x18004330f  lea     esi, [r15+1]
0x180043313  mov     [rsp+148h+var_D8], rdi
0x180043318  lea     rcx, [rsp+148h+var_D8]
0x18004331d  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180043322  jmp     loc_1800431AF
0x180043327  not     esi
0x180043329  lea     rcx, [r14+10h]
0x18004332d  mov     [rcx], rdi
0x180043330  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180043335  mov     eax, esi
0x180043337  jmp     short loc_1800432EA
0x180043339  mov     ecx, 38h ; '8'; unsigned __int64
0x18004333e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180043343  mov     [rsp+148h+var_128], rax
0x180043348  test    rax, rax
0x18004334b  jz      short loc_18004335D
0x18004334d  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x180043354  mov     rcx, rax; this
0x180043357  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18004335c  nop
0x18004335d  lea     rdx, aIntCdeclUnbclA_11; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180043364  mov     rcx, rax
0x180043367  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004336c  mov     [rsp+148h+pExceptionObject], rax
0x180043371  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180043378  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18004337d  call    _CxxThrowException_0
0x180043383  mov     ecx, 38h ; '8'; unsigned __int64
0x180043388  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004338d  mov     [rsp+148h+var_F8], rax
0x180043392  test    rax, rax
0x180043395  jz      short loc_1800433A7
0x180043397  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x18004339e  mov     rcx, rax; this
0x1800433a1  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x1800433a6  nop
0x1800433a7  lea     rdx, aIntCdeclUnbclA_11; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x1800433ae  mov     rcx, rax
0x1800433b1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800433b6  mov     [rsp+148h+var_118], rax
0x1800433bb  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800433c2  lea     rcx, [rsp+148h+var_118]; pExceptionObject
0x1800433c7  call    _CxxThrowException_0
```
