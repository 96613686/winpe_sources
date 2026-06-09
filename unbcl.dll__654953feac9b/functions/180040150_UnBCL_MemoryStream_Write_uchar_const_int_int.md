# UnBCL::MemoryStream::Write(uchar const *,int,int)

- ea: `0x180040150`
- end: `0x1800402fd`
- name: `?Write@MemoryStream@UnBCL@@UEAAXPEBEHH@Z`
- size: `429`
- prototype: `void __fastcall(UnBCL::MemoryStream *__hidden this, const unsigned __int8 *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005c230`

## callees

- `0x18000225c`
- `0x180002276`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003fa90`
- `0x180040150`
- `0x180047520`
- `0x1800477d0`
- `0x180047d60`
- `0x18006f010`

## string_xrefs

- `0x180040204`: `void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)`
- `0x18004024b`: `void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)`
- `0x180040292`: `void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)`
- `0x1800402d9`: `void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)`
- `0x1800402c9`: `Write() on read-only MemoryStream`
- `0x180040282`: `null buf to MemoryStream#Write`
- `0x1800401f4`: `Write() on closed MemoryStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UnBCL::MemoryStream::Write(UnBCL::MemoryStream *this, const unsigned __int8 *a2, int a3, int a4)
{
  size_t v4; // r14
  __int64 v5; // rdi
  void *v8; // rax
  UnBCL::ObjectDisposedException *v9; // rax
  UnBCL::ArgumentOutOfRangeException *v10; // rax
  UnBCL::ArgumentNullException *v11; // rax
  UnBCL::NotSupportedException *v12; // rax
  __int64 pExceptionObject; // [rsp+78h] [rbp+40h] BYREF

  v4 = a4;
  v5 = a3;
  if ( !a2 )
  {
    v11 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v11 )
      v11 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v11,
                                              L"null buf to MemoryStream#Write");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 10) )
  {
    v12 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
    if ( v12 )
      v12 = (UnBCL::NotSupportedException *)UnBCL::NotSupportedException::NotSupportedException(
                                              v12,
                                              L"Write() on read-only MemoryStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::NotSupportedException **)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 9) )
  {
    v9 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v9 )
      v9 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v9,
                                               L"Write() on closed MemoryStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v10 )
      v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v10,
                                                    L"negative offset or count");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::MemoryStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  if ( a4 )
  {
    UnBCL::MemoryStream::LengthAtLeast(this, a4 + *((_DWORD *)this + 13));
    v8 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 56LL))(
                   *((_QWORD *)this + 3),
                   *((unsigned int *)this + 13));
    memcpy_0(v8, &a2[v5], v4);
    *((_DWORD *)this + 13) += v4;
  }
}

```

## disassembly

```asm
0x180040150  push    rbp
0x180040152  push    rbx
0x180040153  push    rsi
0x180040154  push    rdi
0x180040155  push    r14
0x180040157  push    r15
0x180040159  mov     rbp, rsp
0x18004015c  sub     rsp, 38h
0x180040160  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180040168  movsxd  r14, r9d
0x18004016b  movsxd  rdi, r8d
0x18004016e  mov     r15, rdx
0x180040171  mov     rsi, rcx
0x180040174  test    rdx, rdx
0x180040177  jz      loc_18004026F
0x18004017d  cmp     dword ptr [rcx+28h], 0
0x180040181  jz      loc_1800402B6
0x180040187  cmp     dword ptr [rcx+24h], 0
0x18004018b  jnz     short loc_1800401E1
0x18004018d  test    r8d, r8d
0x180040190  js      loc_180040228
0x180040196  test    r9d, r9d
0x180040199  js      loc_180040228
0x18004019f  jz      short loc_1800401D4
0x1800401a1  mov     edx, [rcx+34h]
0x1800401a4  add     edx, r14d; int
0x1800401a7  call    ?LengthAtLeast@MemoryStream@UnBCL@@AEAAXH@Z; UnBCL::MemoryStream::LengthAtLeast(int)
0x1800401ac  mov     rcx, [rsi+18h]
0x1800401b0  add     rdi, r15
0x1800401b3  mov     rax, [rcx]
0x1800401b6  mov     edx, [rsi+34h]
0x1800401b9  mov     rax, [rax+38h]
0x1800401bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401c2  mov     rcx, rax; void *
0x1800401c5  mov     r8, r14; Size
0x1800401c8  mov     rdx, rdi; Src
0x1800401cb  call    memcpy_0
0x1800401d0  add     [rsi+34h], r14d
0x1800401d4  add     rsp, 38h
0x1800401d8  pop     r15
0x1800401da  pop     r14
0x1800401dc  pop     rdi
0x1800401dd  pop     rsi
0x1800401de  pop     rbx
0x1800401df  pop     rbp
0x1800401e0  retn
0x1800401e1  mov     ecx, 38h ; '8'; unsigned __int64
0x1800401e6  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800401eb  mov     [rbp+var_10], rax
0x1800401ef  test    rax, rax
0x1800401f2  jz      short loc_180040204
0x1800401f4  lea     rdx, aWriteOnClosedM; "Write() on closed MemoryStream"
0x1800401fb  mov     rcx, rax; this
0x1800401fe  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x180040203  nop
0x180040204  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::MemoryStream::Write"...
0x18004020b  mov     rcx, rax
0x18004020e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180040213  mov     [rbp+pExceptionObject], rax
0x180040217  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004021e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180040222  call    _CxxThrowException_0
0x180040228  mov     ecx, 38h ; '8'; unsigned __int64
0x18004022d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180040232  mov     [rbp+var_10], rax
0x180040236  test    rax, rax
0x180040239  jz      short loc_18004024B
0x18004023b  lea     rdx, aNegativeOffset_0; "negative offset or count"
0x180040242  mov     rcx, rax; this
0x180040245  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18004024a  nop
0x18004024b  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::MemoryStream::Write"...
0x180040252  mov     rcx, rax
0x180040255  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004025a  mov     [rbp+pExceptionObject], rax
0x18004025e  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180040265  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180040269  call    _CxxThrowException_0
0x18004026f  mov     ecx, 38h ; '8'; unsigned __int64
0x180040274  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180040279  mov     [rbp+var_10], rax
0x18004027d  test    rax, rax
0x180040280  jz      short loc_180040292
0x180040282  lea     rdx, aNullBufToMemor; "null buf to MemoryStream#Write"
0x180040289  mov     rcx, rax; this
0x18004028c  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180040291  nop
0x180040292  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::MemoryStream::Write"...
0x180040299  mov     rcx, rax
0x18004029c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800402a1  mov     [rbp+pExceptionObject], rax
0x1800402a5  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800402ac  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800402b0  call    _CxxThrowException_0
0x1800402b6  mov     ecx, 38h ; '8'; unsigned __int64
0x1800402bb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800402c0  mov     [rbp+var_10], rax
0x1800402c4  test    rax, rax
0x1800402c7  jz      short loc_1800402D9
0x1800402c9  lea     rdx, aWriteOnReadOnl; "Write() on read-only MemoryStream"
0x1800402d0  mov     rcx, rax; this
0x1800402d3  call    ??0NotSupportedException@UnBCL@@QEAA@PEBG@Z; UnBCL::NotSupportedException::NotSupportedException(ushort const *)
0x1800402d8  nop
0x1800402d9  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::MemoryStream::Write"...
0x1800402e0  mov     rcx, rax
0x1800402e3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800402e8  mov     [rbp+pExceptionObject], rax
0x1800402ec  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x1800402f3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800402f7  call    _CxxThrowException_0
```
