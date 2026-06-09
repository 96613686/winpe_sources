# UnBCL::Mutex::Mutex(void)

- ea: `0x180047090`
- end: `0x18004719a`
- name: `??0Mutex@UnBCL@@QEAA@XZ`
- size: `266`
- prototype: `__int64 __fastcall(UnBCL::Mutex *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180047090`
- `0x180063c60`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180047181`
- `KERNEL32!CreateMutexW` at `0x180047181`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
UnBCL::Mutex *__fastcall UnBCL::Mutex::Mutex(UnBCL::Mutex *this, int a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx

  if ( a2 )
  {
    *((_QWORD *)this + 1) = &UnBCL::Mutex::`vbtable';
    *((_QWORD *)this + 6) = &UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'};
    *((_QWORD *)this + 8) = &UnBCL::_::KeyCollection<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::`vbtable'{for `UnBCL::ICollection<UnBCL::SerializationId *>'};
    *((_QWORD *)this + 2) = &UnBCL::Object::`vftable';
    *((_DWORD *)this + 6) = 0;
    *((_DWORD *)this + 7) = _InterlockedIncrement(&dword_1800FFC68);
    UnBCL::WaitHandle::WaitHandle((UnBCL::Mutex *)((char *)this + 56));
  }
  *(_QWORD *)this = &UnBCL::Mutex::`vftable';
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &UnBCL::Mutex::`vftable'{for `UnBCL::Object'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 8LL) + 8) = &UnBCL::Mutex::`vftable'{for `UnBCL::IDisposable'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 12LL) + 8) = &UnBCL::Mutex::`vftable'{for `UnBCL::WaitHandle'};
  v3 = *(int *)(*((_QWORD *)this + 1) + 8LL);
  *(_DWORD *)((char *)this + v3 + 4) = v3 - 32;
  v4 = *(int *)(*((_QWORD *)this + 1) + 12LL);
  *(_QWORD *)((char *)this + v4 + 24) = CreateMutexW(0, 0, 0);
  return this;
}

```

## disassembly

```asm
0x180047090  mov     rax, rsp
0x180047093  mov     [rax+8], rcx
0x180047097  push    rdi
0x180047098  sub     rsp, 30h
0x18004709c  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x1800470a4  mov     [rax+10h], rbx
0x1800470a8  mov     rdi, rcx
0x1800470ab  mov     dword ptr [rax-18h], 0
0x1800470b2  test    edx, edx
0x1800470b4  jz      short loc_18004711D
0x1800470b6  lea     rax, ??_8Mutex@UnBCL@@7B@; const UnBCL::Mutex::`vbtable'
0x1800470bd  mov     [rcx+8], rax
0x1800470c1  lea     rax, ??_8?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@PEAV12@UKeyTraits@42@$1?RetrieveValue@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@7B?$IEnumerator@PEAVString@UnBCL@@@2@@; const UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'}
0x1800470c8  mov     [rcx+30h], rax
0x1800470cc  lea     rax, ??_8?$KeyCollection@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@_@UnBCL@@7B?$ICollection@PEAVSerializationId@UnBCL@@@2@@; const UnBCL::_::KeyCollection<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::`vbtable'{for `UnBCL::ICollection<UnBCL::SerializationId *>'}
0x1800470d3  mov     [rcx+40h], rax
0x1800470d7  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x1800470de  mov     [rcx+10h], rax
0x1800470e2  mov     dword ptr [rcx+18h], 0
0x1800470e9  mov     ecx, 1
0x1800470ee  mov     eax, ecx
0x1800470f0  lock xadd cs:dword_1800FFC68, eax
0x1800470f8  add     eax, ecx
0x1800470fa  mov     [rdi+1Ch], eax
0x1800470fd  mov     [rsp+38h+var_18], ecx
0x180047101  lea     ebx, [rcx+1]
0x180047104  or      ebx, ecx
0x180047106  mov     [rsp+38h+var_18], ebx
0x18004710a  lea     rcx, [rdi+38h]; this
0x18004710e  xor     edx, edx
0x180047110  call    ??0WaitHandle@UnBCL@@IEAA@XZ; UnBCL::WaitHandle::WaitHandle(void)
0x180047115  nop
0x180047116  or      ebx, 4
0x180047119  mov     [rsp+38h+var_18], ebx
0x18004711d  lea     rax, ??_7Mutex@UnBCL@@6B@; const UnBCL::Mutex::`vftable'
0x180047124  mov     [rdi], rax
0x180047127  mov     rax, [rdi+8]
0x18004712b  movsxd  rcx, dword ptr [rax+4]
0x18004712f  lea     rax, ??_7Mutex@UnBCL@@6BObject@1@@; const UnBCL::Mutex::`vftable'{for `UnBCL::Object'}
0x180047136  mov     [rcx+rdi+8], rax
0x18004713b  mov     rax, [rdi+8]
0x18004713f  movsxd  rcx, dword ptr [rax+8]
0x180047143  lea     rax, ??_7Mutex@UnBCL@@6BIDisposable@1@@; const UnBCL::Mutex::`vftable'{for `UnBCL::IDisposable'}
0x18004714a  mov     [rcx+rdi+8], rax
0x18004714f  mov     rax, [rdi+8]
0x180047153  movsxd  rcx, dword ptr [rax+0Ch]
0x180047157  lea     rax, ??_7Mutex@UnBCL@@6BWaitHandle@1@@; const UnBCL::Mutex::`vftable'{for `UnBCL::WaitHandle'}
0x18004715e  mov     [rcx+rdi+8], rax
0x180047163  mov     rax, [rdi+8]
0x180047167  movsxd  rcx, dword ptr [rax+8]
0x18004716b  lea     edx, [rcx-20h]
0x18004716e  mov     [rcx+rdi+4], edx
0x180047172  mov     rax, [rdi+8]
0x180047176  movsxd  rbx, dword ptr [rax+0Ch]
0x18004717a  xor     r8d, r8d; lpName
0x18004717d  xor     edx, edx; bInitialOwner
0x18004717f  xor     ecx, ecx; lpMutexAttributes
0x180047181  call    cs:__imp_CreateMutexW
0x180047187  mov     [rbx+rdi+18h], rax
0x18004718c  mov     rax, rdi
0x18004718f  mov     rbx, [rsp+38h+arg_8]
0x180047194  add     rsp, 30h
0x180047198  pop     rdi
0x180047199  retn
```
