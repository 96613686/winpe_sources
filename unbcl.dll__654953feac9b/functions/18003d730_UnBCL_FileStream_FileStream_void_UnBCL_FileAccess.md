# UnBCL::FileStream::FileStream(void *,UnBCL::FileAccess)

- ea: `0x18003d730`
- end: `0x18003d901`
- name: `??0FileStream@UnBCL@@QEAA@PEAXW4FileAccess@1@@Z`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001574`
- `0x18000225c`
- `0x1800098b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003d730`
- `0x1800477d0`

## string_xrefs

- `0x18003d891`: `__cdecl UnBCL::FileStream::FileStream(void *,enum UnBCL::FileAccess)`
- `0x18003d8db`: `__cdecl UnBCL::FileStream::FileStream(void *,enum UnBCL::FileAccess)`
- `0x18003d8cb`: `invalid access to FileStream constructor`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UnBCL::FileStream::FileStream(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v6; // rcx
  UnBCL::ArgumentOutOfRangeException *v7; // rax
  UnBCL::ArgumentException *v9; // rax
  UnBCL::ArgumentOutOfRangeException *v10; // rax
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-20h] BYREF
  UnBCL::ArgumentOutOfRangeException *v12; // [rsp+38h] [rbp-10h]

  pExceptionObject[1] = -2;
  if ( a4 )
  {
    *(_QWORD *)(a1 + 8) = &UnBCL::FileStream::`vbtable'{for `UnBCL::Stream'};
    *(_QWORD *)(a1 + 72) = &UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'};
    *(_QWORD *)(a1 + 40) = &UnBCL::Object::`vftable';
    *(_DWORD *)(a1 + 48) = 0;
    *(_DWORD *)(a1 + 52) = _InterlockedIncrement(&dword_1800FFC68);
  }
  *(_QWORD *)a1 = &UnBCL::Stream::`vftable'{for `UnBCL::Stream'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &UnBCL::Stream::`vftable'{for `UnBCL::Object'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 8LL) + a1 + 8) = &UnBCL::Stream::`vftable'{for `UnBCL::IDisposable'};
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &UnBCL::FileStream::`vftable'{for `UnBCL::Stream'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &UnBCL::FileStream::`vftable'{for `UnBCL::Object'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 8LL) + a1 + 8) = &UnBCL::FileStream::`vftable'{for `UnBCL::IDisposable'};
  v6 = *(int *)(*(_QWORD *)(a1 + 8) + 8LL);
  *(_DWORD *)(v6 + a1 + 4) = v6 - 56;
  *(_DWORD *)(a1 + 24) = a3 & 1;
  *(_QWORD *)(a1 + 32) = 0;
  if ( (unsigned int)(a3 - 1) > 2 )
  {
    v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v12 = v10;
    if ( v10 )
      v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v10,
                                                    L"invalid access to FileStream constructor");
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v10,
                            "__cdecl UnBCL::FileStream::FileStream(void *,enum UnBCL::FileAccess)");
    throw (UnBCL::ArgumentOutOfRangeException **)pExceptionObject;
  }
  if ( a2 == -1 )
  {
    v9 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v12 = v9;
    if ( v9 )
      v9 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                         v9,
                                         L"invalid handle to FileStream constructor");
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v9,
                            "__cdecl UnBCL::FileStream::FileStream(void *,enum UnBCL::FileAccess)");
    throw (UnBCL::ArgumentException **)pExceptionObject;
  }
  v7 = (UnBCL::ArgumentOutOfRangeException *)operator new(8u);
  v12 = v7;
  if ( v7 )
    *(_QWORD *)v7 = a2;
  *(_QWORD *)(a1 + 32) = v7;
  return a1;
}

```

## disassembly

```asm
0x18003d730  mov     rax, rsp
0x18003d733  mov     [rax+8], rcx
0x18003d737  push    rdi
0x18003d738  sub     rsp, 40h
0x18003d73c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18003d744  mov     [rax+10h], rbx
0x18003d748  mov     rdi, rdx
0x18003d74b  mov     rbx, rcx
0x18003d74e  mov     dword ptr [rax-28h], 0
0x18003d755  mov     r10d, 1
0x18003d75b  test    r9d, r9d
0x18003d75e  jz      short loc_18003D7A9
0x18003d760  lea     rax, ??_8FileStream@UnBCL@@7BStream@1@@; const UnBCL::FileStream::`vbtable'{for `UnBCL::Stream'}
0x18003d767  mov     [rcx+8], rax
0x18003d76b  lea     rax, ??_8?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@PEAV12@UKeyTraits@42@$1?RetrieveValue@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@7B?$IEnumerator@PEAVString@UnBCL@@@2@@; const UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'}
0x18003d772  mov     [rcx+48h], rax
0x18003d776  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18003d77d  mov     [rcx+28h], rax
0x18003d781  mov     dword ptr [rcx+30h], 0
0x18003d788  mov     eax, r10d
0x18003d78b  lock xadd cs:dword_1800FFC68, eax
0x18003d793  add     eax, r10d
0x18003d796  mov     [rcx+34h], eax
0x18003d799  mov     [rsp+48h+var_28], r10d
0x18003d79e  lea     eax, [r10+1]
0x18003d7a2  or      eax, r10d
0x18003d7a5  mov     [rsp+48h+var_28], eax
0x18003d7a9  lea     rax, ??_7Stream@UnBCL@@6B01@@; const UnBCL::Stream::`vftable'{for `UnBCL::Stream'}
0x18003d7b0  mov     [rcx], rax
0x18003d7b3  mov     rax, [rcx+8]
0x18003d7b7  movsxd  rcx, dword ptr [rax+4]
0x18003d7bb  lea     rax, ??_7Stream@UnBCL@@6BObject@1@@; const UnBCL::Stream::`vftable'{for `UnBCL::Object'}
0x18003d7c2  mov     [rcx+rbx+8], rax
0x18003d7c7  mov     rax, [rbx+8]
0x18003d7cb  movsxd  rcx, dword ptr [rax+8]
0x18003d7cf  lea     rax, ??_7Stream@UnBCL@@6BIDisposable@1@@; const UnBCL::Stream::`vftable'{for `UnBCL::IDisposable'}
0x18003d7d6  mov     [rcx+rbx+8], rax
0x18003d7db  mov     qword ptr [rbx+10h], 0
0x18003d7e3  lea     rax, ??_7FileStream@UnBCL@@6BStream@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::Stream'}
0x18003d7ea  mov     [rbx], rax
0x18003d7ed  mov     rax, [rbx+8]
0x18003d7f1  movsxd  rcx, dword ptr [rax+4]
0x18003d7f5  lea     rax, ??_7FileStream@UnBCL@@6BObject@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::Object'}
0x18003d7fc  mov     [rcx+rbx+8], rax
0x18003d801  mov     rax, [rbx+8]
0x18003d805  movsxd  rcx, dword ptr [rax+8]
0x18003d809  lea     rax, ??_7FileStream@UnBCL@@6BIDisposable@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::IDisposable'}
0x18003d810  mov     [rcx+rbx+8], rax
0x18003d815  mov     rax, [rbx+8]
0x18003d819  movsxd  rcx, dword ptr [rax+8]
0x18003d81d  lea     edx, [rcx-38h]
0x18003d820  mov     [rcx+rbx+4], edx
0x18003d824  mov     eax, r8d
0x18003d827  and     eax, r10d
0x18003d82a  mov     [rbx+18h], eax
0x18003d82d  mov     qword ptr [rbx+20h], 0
0x18003d835  lea     eax, [r8-1]
0x18003d839  cmp     eax, 2
0x18003d83c  ja      short loc_18003D8B7
0x18003d83e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003d842  jz      short loc_18003D86D
0x18003d844  mov     ecx, 8; Size
0x18003d849  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d84e  mov     [rsp+48h+var_10], rax
0x18003d853  test    rax, rax
0x18003d856  jz      short loc_18003D85B
0x18003d858  mov     [rax], rdi
0x18003d85b  mov     [rbx+20h], rax
0x18003d85f  mov     rax, rbx
0x18003d862  mov     rbx, [rsp+48h+arg_8]
0x18003d867  add     rsp, 40h
0x18003d86b  pop     rdi
0x18003d86c  retn
0x18003d86d  mov     ecx, 38h ; '8'; unsigned __int64
0x18003d872  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003d877  mov     [rsp+48h+var_10], rax
0x18003d87c  test    rax, rax
0x18003d87f  jz      short loc_18003D891
0x18003d881  lea     rdx, aInvalidHandleT; "invalid handle to FileStream constructo"...
0x18003d888  mov     rcx, rax; this
0x18003d88b  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003d890  nop
0x18003d891  lea     rdx, aCdeclUnbclFile_0; "__cdecl UnBCL::FileStream::FileStream(v"...
0x18003d898  mov     rcx, rax
0x18003d89b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003d8a0  mov     [rsp+48h+pExceptionObject], rax
0x18003d8a5  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003d8ac  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003d8b1  call    _CxxThrowException_0
0x18003d8b7  mov     ecx, 38h ; '8'; unsigned __int64
0x18003d8bc  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003d8c1  mov     [rsp+48h+var_10], rax
0x18003d8c6  test    rax, rax
0x18003d8c9  jz      short loc_18003D8DB
0x18003d8cb  lea     rdx, aInvalidAccessT; "invalid access to FileStream constructo"...
0x18003d8d2  mov     rcx, rax; this
0x18003d8d5  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003d8da  nop
0x18003d8db  lea     rdx, aCdeclUnbclFile_0; "__cdecl UnBCL::FileStream::FileStream(v"...
0x18003d8e2  mov     rcx, rax
0x18003d8e5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003d8ea  mov     [rsp+48h+pExceptionObject], rax
0x18003d8ef  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003d8f6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003d8fb  call    _CxxThrowException_0
```
