# UnBCL::FileStream::Seek(__int64,UnBCL::SeekOrigin)

- ea: `0x18003e270`
- end: `0x18003e4fc`
- name: `?Seek@FileStream@UnBCL@@UEAA_J_JW4SeekOrigin@2@@Z`
- size: `652`
- prototype: `__int64 __high(__int64, enum UnBCL::SeekOrigin)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18003d910`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003de78`
- `0x18003e270`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003e2e1`
- `KERNEL32!SetFilePointer` at `0x18003e2e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::FileStream::Seek(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v6; // r14
  __int64 v7; // rax
  DWORD v8; // r9d
  HANDLE *v9; // rcx
  signed int Error; // ebx
  UnBCL::ArgumentException *v12; // rax
  UnBCL::Win32Exception *v13; // rax
  UnBCL::ArgumentException *v14; // rax
  UnBCL::ArgumentException *v15; // rax
  UnBCL::ArgumentOutOfRangeException *v16; // rax
  UnBCL::ObjectDisposedException *v17; // rax
  __int64 DistanceToMoveHigh; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h]
  UnBCL::ObjectDisposedException *v20; // [rsp+78h] [rbp+48h]

  v19 = a2;
  if ( !a1[4] )
  {
    v17 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v20 = v17;
    if ( v17 )
      v17 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v17,
                                                L"Seek() on closed FileStream");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v17,
                           "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
    throw (UnBCL::ObjectDisposedException **)&DistanceToMoveHigh;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD *))*a1)(a1);
  v7 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  if ( a3 )
  {
    v8 = 1;
    if ( a3 == 1 )
    {
      if ( v6 + a2 < 0 )
      {
        v14 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
        v20 = v14;
        if ( v14 )
          v14 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                              v14,
                                              L"Seek() before beginning of FileStream");
        DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                               v14,
                               "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
        throw (UnBCL::ArgumentException **)&DistanceToMoveHigh;
      }
    }
    else
    {
      v8 = 2;
      if ( a3 != 2 )
      {
        v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
        v20 = v16;
        if ( v16 )
          v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                        v16,
                                                        L"bad SeekOrigin to FileStream#Seek");
        DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                               v16,
                               "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
        throw (UnBCL::ArgumentOutOfRangeException **)&DistanceToMoveHigh;
      }
      if ( a2 + v7 < 0 )
      {
        v15 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
        v20 = v15;
        if ( v15 )
          v15 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                              v15,
                                              L"Seek() before beginning of FileStream");
        DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                               v15,
                               "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
        throw (UnBCL::ArgumentException **)&DistanceToMoveHigh;
      }
    }
  }
  else
  {
    if ( a2 < 0 )
    {
      v12 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
      v20 = v12;
      if ( v12 )
        v12 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                            v12,
                                            L"Seek() before beginning of FileStream");
      DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v12,
                             "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
      throw (UnBCL::ArgumentException **)&DistanceToMoveHigh;
    }
    v8 = 0;
  }
  v9 = (HANDLE *)a1[4];
  DistanceToMoveHigh = __PAIR64__(HIDWORD(v19), a2);
  if ( SetFilePointer(*v9, a2, (PLONG)&DistanceToMoveHigh + 1, v8) != -1
    || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
  {
    Error = 0;
  }
  if ( Error )
  {
    v13 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v20 = v13;
    if ( v13 )
      v13 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v13, Error, L"FileStream Seek() failed");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v13,
                           "__int64 __cdecl UnBCL::FileStream::Seek(__int64,enum UnBCL::SeekOrigin)");
    throw (UnBCL::Win32Exception **)&DistanceToMoveHigh;
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18003e270  mov     [rsp-28h+arg_8], rdx
0x18003e275  push    rbp
0x18003e276  push    rbx
0x18003e277  push    rsi
0x18003e278  push    rdi
0x18003e279  push    r14
0x18003e27b  mov     rbp, rsp
0x18003e27e  sub     rsp, 30h
0x18003e282  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18003e28a  mov     esi, r8d
0x18003e28d  mov     rbx, rdx
0x18003e290  mov     rdi, rcx
0x18003e293  cmp     qword ptr [rcx+20h], 0
0x18003e298  jz      loc_18003E4B5
0x18003e29e  mov     rax, [rcx]
0x18003e2a1  mov     rax, [rax]
0x18003e2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2a9  mov     r14, rax
0x18003e2ac  mov     rcx, [rdi]
0x18003e2af  mov     rax, [rcx+8]
0x18003e2b3  mov     rcx, rdi
0x18003e2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2bb  test    esi, esi
0x18003e2bd  jnz     short loc_18003E303
0x18003e2bf  test    rbx, rbx
0x18003e2c2  js      loc_18003E350
0x18003e2c8  xor     r9d, r9d; dwMoveMethod
0x18003e2cb  mov     eax, dword ptr [rbp+arg_8+4]
0x18003e2ce  mov     rcx, [rdi+20h]
0x18003e2d2  mov     dword ptr [rbp+DistanceToMoveHigh], ebx
0x18003e2d5  mov     dword ptr [rbp+DistanceToMoveHigh+4], eax
0x18003e2d8  lea     r8, [rbp+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18003e2dc  mov     edx, ebx; lDistanceToMove
0x18003e2de  mov     rcx, [rcx]; hFile
0x18003e2e1  call    cs:__imp_SetFilePointer
0x18003e2e7  cmp     eax, 0FFFFFFFFh
0x18003e2ea  jnz     short loc_18003E2F7
0x18003e2ec  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e2f1  mov     ebx, eax
0x18003e2f3  test    eax, eax
0x18003e2f5  js      short loc_18003E2F9
0x18003e2f7  xor     ebx, ebx
0x18003e2f9  test    ebx, ebx
0x18003e2fb  jnz     loc_18003E397
0x18003e301  jmp     short loc_18003E337
0x18003e303  mov     r9d, 1
0x18003e309  cmp     esi, r9d
0x18003e30c  jnz     short loc_18003E31D
0x18003e30e  lea     rax, [r14+rbx]
0x18003e312  test    rax, rax
0x18003e315  js      loc_18003E3E0
0x18003e31b  jmp     short loc_18003E2CB
0x18003e31d  mov     r9d, 2
0x18003e323  cmp     esi, r9d
0x18003e326  jnz     loc_18003E46E
0x18003e32c  add     rax, rbx
0x18003e32f  js      loc_18003E427
0x18003e335  jmp     short loc_18003E2CB
0x18003e337  mov     rax, [rdi]
0x18003e33a  mov     rcx, rdi
0x18003e33d  mov     rax, [rax+8]
0x18003e341  add     rsp, 30h
0x18003e345  pop     r14
0x18003e347  pop     rdi
0x18003e348  pop     rsi
0x18003e349  pop     rbx
0x18003e34a  pop     rbp
0x18003e34b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18003e350  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e355  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e35a  mov     [rbp+arg_18], rax
0x18003e35e  test    rax, rax
0x18003e361  jz      short loc_18003E373
0x18003e363  lea     rdx, aSeekBeforeBegi_0; "Seek() before beginning of FileStream"
0x18003e36a  mov     rcx, rax; this
0x18003e36d  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003e372  nop
0x18003e373  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e37a  mov     rcx, rax
0x18003e37d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e382  mov     [rbp+DistanceToMoveHigh], rax
0x18003e386  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003e38d  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e391  call    _CxxThrowException_0
0x18003e397  mov     ecx, 40h ; '@'; unsigned __int64
0x18003e39c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e3a1  mov     [rbp+arg_18], rax
0x18003e3a5  test    rax, rax
0x18003e3a8  jz      short loc_18003E3BC
0x18003e3aa  lea     r8, aFilestreamSeek; "FileStream Seek() failed"
0x18003e3b1  mov     edx, ebx; dwMessageId
0x18003e3b3  mov     rcx, rax; this
0x18003e3b6  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003e3bb  nop
0x18003e3bc  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e3c3  mov     rcx, rax
0x18003e3c6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e3cb  mov     [rbp+DistanceToMoveHigh], rax
0x18003e3cf  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003e3d6  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e3da  call    _CxxThrowException_0
0x18003e3e0  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e3e5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e3ea  mov     [rbp+arg_18], rax
0x18003e3ee  test    rax, rax
0x18003e3f1  jz      short loc_18003E403
0x18003e3f3  lea     rdx, aSeekBeforeBegi_0; "Seek() before beginning of FileStream"
0x18003e3fa  mov     rcx, rax; this
0x18003e3fd  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003e402  nop
0x18003e403  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e40a  mov     rcx, rax
0x18003e40d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e412  mov     [rbp+DistanceToMoveHigh], rax
0x18003e416  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003e41d  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e421  call    _CxxThrowException_0
0x18003e427  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e42c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e431  mov     [rbp+arg_18], rax
0x18003e435  test    rax, rax
0x18003e438  jz      short loc_18003E44A
0x18003e43a  lea     rdx, aSeekBeforeBegi_0; "Seek() before beginning of FileStream"
0x18003e441  mov     rcx, rax; this
0x18003e444  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003e449  nop
0x18003e44a  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e451  mov     rcx, rax
0x18003e454  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e459  mov     [rbp+DistanceToMoveHigh], rax
0x18003e45d  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003e464  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e468  call    _CxxThrowException_0
0x18003e46e  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e473  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e478  mov     [rbp+arg_18], rax
0x18003e47c  test    rax, rax
0x18003e47f  jz      short loc_18003E491
0x18003e481  lea     rdx, aBadSeekoriginT; "bad SeekOrigin to FileStream#Seek"
0x18003e488  mov     rcx, rax; this
0x18003e48b  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003e490  nop
0x18003e491  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e498  mov     rcx, rax
0x18003e49b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e4a0  mov     [rbp+DistanceToMoveHigh], rax
0x18003e4a4  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003e4ab  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e4af  call    _CxxThrowException_0
0x18003e4b5  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e4ba  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e4bf  mov     [rbp+arg_18], rax
0x18003e4c3  test    rax, rax
0x18003e4c6  jz      short loc_18003E4D8
0x18003e4c8  lea     rdx, aSeekOnClosedFi; "Seek() on closed FileStream"
0x18003e4cf  mov     rcx, rax; this
0x18003e4d2  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003e4d7  nop
0x18003e4d8  lea     rdx, aInt64CdeclUnbc_2; "__int64 __cdecl UnBCL::FileStream::Seek"...
0x18003e4df  mov     rcx, rax
0x18003e4e2  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e4e7  mov     [rbp+DistanceToMoveHigh], rax
0x18003e4eb  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003e4f2  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e4f6  call    _CxxThrowException_0
```
