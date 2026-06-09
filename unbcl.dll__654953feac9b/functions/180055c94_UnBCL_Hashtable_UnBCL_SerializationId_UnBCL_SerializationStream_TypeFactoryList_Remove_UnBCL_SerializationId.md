# UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::Remove(UnBCL::SerializationId *)

- ea: `0x180055c94`
- end: `0x180055db2`
- name: `?Remove@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@UEAAXPEAVSerializationId@2@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180055c80`

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800477d0`
- `0x180051c24`
- `0x18005465c`
- `0x180055c94`
- `0x180055f54`
- `0x18006f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180055d5a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055d5a`

## string_xrefs

- `0x180055d7e`: `null key to Hashtable#Remove`
- `0x180055d8e`: `void __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::Remove(class UnBCL::SerializationId *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::Remove(
        __int64 a1,
        __int64 a2)
{
  __int64 Node; // rax
  void (__fastcall ***v4)(_QWORD, __int64); // r14
  UnBCL::SerializationStream::TypeFactoryList *v5; // rsi
  UnBCL::ArgumentNullException *v6; // rax
  _QWORD v7[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+88h] [rbp+38h] BYREF
  UnBCL::ArgumentNullException *v9; // [rsp+90h] [rbp+40h] BYREF
  char v10; // [rsp+98h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v6 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v9 = v6;
    if ( v6 )
      v6 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                             v6,
                                             L"null key to Hashtable#Remove");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "void __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::"
                         "TypeFactoryList *>::Remove(class UnBCL::SerializationId *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v7[0] = a1 - 128;
  v7[1] = a2;
  if ( *(_DWORD *)(a1 - 112) || *(_DWORD *)(a1 - 108) )
  {
    LODWORD(v9) = 0;
    LODWORD(pExceptionObject) = 0;
    Node = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNode(
             *(_QWORD *)(a1 - 88),
             (unsigned int)v7,
             (unsigned int)&v9,
             (unsigned int)&pExceptionObject,
             (__int64)&v10);
    if ( Node )
    {
      v4 = *(void (__fastcall ****)(_QWORD, __int64))(Node + 8);
      v5 = *(UnBCL::SerializationStream::TypeFactoryList **)(Node + 16);
      ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::RemoveKey(
        *(_QWORD *)(a1 - 88),
        v7);
      if ( *(_DWORD *)(a1 - 112) && v4 )
        (**v4)(v4, 1);
      if ( *(_DWORD *)(a1 - 108) )
      {
        if ( v5 )
        {
          UnBCL::SerializationStream::TypeFactoryList::~TypeFactoryList(v5);
          operator delete(v5);
        }
      }
    }
  }
  else
  {
    ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::RemoveKey(
      *(_QWORD *)(a1 - 88),
      v7);
  }
}

```

## disassembly

```asm
0x180055c94  push    rbp
0x180055c96  push    rbx
0x180055c97  push    rsi
0x180055c98  push    rdi
0x180055c99  push    r14
0x180055c9b  mov     rbp, rsp
0x180055c9e  sub     rsp, 50h
0x180055ca2  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180055caa  mov     rbx, rcx
0x180055cad  test    rdx, rdx
0x180055cb0  jz      loc_180055D6B
0x180055cb6  lea     rax, [rcx-80h]
0x180055cba  mov     [rbp+var_18], rax
0x180055cbe  mov     [rbp+var_10], rdx
0x180055cc2  cmp     dword ptr [rcx-70h], 0
0x180055cc6  jnz     short loc_180055CE0
0x180055cc8  cmp     dword ptr [rcx-6Ch], 0
0x180055ccc  jnz     short loc_180055CE0
0x180055cce  lea     rdx, [rbp+var_18]
0x180055cd2  mov     rcx, [rcx-58h]
0x180055cd6  call    ?RemoveKey@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAA_NAEBUTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::RemoveKey(UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey const &)
0x180055cdb  jmp     loc_180055D60
0x180055ce0  mov     dword ptr [rbp+arg_10], 0
0x180055ce7  mov     dword ptr [rbp+pExceptionObject], 0
0x180055cee  lea     rax, [rbp+arg_18]
0x180055cf2  mov     [rsp+50h+var_30], rax
0x180055cf7  lea     r9, [rbp+pExceptionObject]
0x180055cfb  lea     r8, [rbp+arg_10]
0x180055cff  lea     rdx, [rbp+var_18]
0x180055d03  mov     rcx, [rcx-58h]
0x180055d07  call    ?GetNode@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@AEBAPEAVCNode@12@AEBUTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@AEAI1AEAPEAV312@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNode(UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey const &,uint &,uint &,ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::CNode * &)
0x180055d0c  test    rax, rax
0x180055d0f  jz      short loc_180055D60
0x180055d11  mov     r14, [rax+8]
0x180055d15  mov     rsi, [rax+10h]
0x180055d19  lea     rdx, [rbp+var_18]
0x180055d1d  mov     rcx, [rbx-58h]
0x180055d21  call    ?RemoveKey@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAA_NAEBUTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::RemoveKey(UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey const &)
0x180055d26  cmp     dword ptr [rbx-70h], 0
0x180055d2a  jz      short loc_180055D44
0x180055d2c  test    r14, r14
0x180055d2f  jz      short loc_180055D44
0x180055d31  mov     rax, [r14]
0x180055d34  mov     edx, 1
0x180055d39  mov     rcx, r14
0x180055d3c  mov     rax, [rax]
0x180055d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d44  cmp     dword ptr [rbx-6Ch], 0
0x180055d48  jz      short loc_180055D60
0x180055d4a  test    rsi, rsi
0x180055d4d  jz      short loc_180055D60
0x180055d4f  mov     rcx, rsi; this
0x180055d52  call    ??1TypeFactoryList@SerializationStream@UnBCL@@QEAA@XZ; UnBCL::SerializationStream::TypeFactoryList::~TypeFactoryList(void)
0x180055d57  mov     rcx, rsi
0x180055d5a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180055d60  add     rsp, 50h
0x180055d64  pop     r14
0x180055d66  pop     rdi
0x180055d67  pop     rsi
0x180055d68  pop     rbx
0x180055d69  pop     rbp
0x180055d6a  retn
0x180055d6b  mov     ecx, 38h ; '8'; unsigned __int64
0x180055d70  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055d75  mov     [rbp+arg_10], rax
0x180055d79  test    rax, rax
0x180055d7c  jz      short loc_180055D8E
0x180055d7e  lea     rdx, aNullKeyToHasht_0; "null key to Hashtable#Remove"
0x180055d85  mov     rcx, rax; this
0x180055d88  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180055d8d  nop
0x180055d8e  lea     rdx, aVoidCdeclUnbcl_61; "void __cdecl UnBCL::Hashtable<class UnB"...
0x180055d95  mov     rcx, rax
0x180055d98  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055d9d  mov     [rbp+pExceptionObject], rax
0x180055da1  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180055da8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055dac  call    _CxxThrowException_0
```
