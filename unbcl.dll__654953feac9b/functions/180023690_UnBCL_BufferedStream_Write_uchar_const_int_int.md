# UnBCL::BufferedStream::Write(uchar const *,int,int)

- ea: `0x180023690`
- end: `0x1800238b5`
- name: `?Write@BufferedStream@UnBCL@@UEAAXPEBEHH@Z`
- size: `549`
- prototype: `void __fastcall(UnBCL::BufferedStream *__hidden this, const unsigned __int8 *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000225c`
- `0x180002276`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x1800233f0`
- `0x180023690`
- `0x1800477d0`
- `0x180047d60`
- `0x18006f010`

## string_xrefs

- `0x180023835`: `negative offset or count to BufferedStream#Read`
- `0x1800237fb`: `void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)`
- `0x180023845`: `void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)`
- `0x18002388f`: `void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)`
- `0x18002387f`: `null buf to BufferedStream#Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::BufferedStream::Write(UnBCL::BufferedStream *this, const unsigned __int8 *a2, int a3, int a4)
{
  int v4; // esi
  int v5; // ebp
  __int64 v8; // rcx
  unsigned int v9; // r9d
  __int64 v10; // r8
  const unsigned __int8 *v11; // rdx
  void *v12; // rcx
  int v13; // ebx
  int v14; // edx
  __int64 v15; // rcx
  UnBCL::ObjectDisposedException *v16; // rax
  UnBCL::ArgumentOutOfRangeException *v17; // rax
  UnBCL::ArgumentNullException *v18; // rax
  __int64 pExceptionObject; // [rsp+68h] [rbp+10h] BYREF

  v4 = a4;
  v5 = a3;
  if ( !a2 )
  {
    v18 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v18 )
      v18 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v18,
                                              L"null buf to BufferedStream#Write");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v17 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v17 )
      v17 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v17,
                                                    L"negative offset or count to BufferedStream#Read");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = *((_QWORD *)this + 4);
  if ( !v8 )
  {
    v16 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v16 )
      v16 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v16,
                                                L"Seek() on closed BufferedStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::BufferedStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( *((_QWORD *)this + 5) )
  {
    if ( a4 > 0 )
    {
      while ( 1 )
      {
        v9 = *((_DWORD *)this + 12);
        v10 = *((unsigned int *)this + 13);
        v11 = &a2[v5];
        v12 = (void *)(v10 + *((_QWORD *)this + 5));
        if ( (int)v10 + v4 <= v9 )
          break;
        v13 = v9 - v10;
        memcpy_0(v12, v11, v9 - (unsigned int)v10);
        v4 -= v13;
        *((_DWORD *)this + 13) = *((_DWORD *)this + 12);
        UnBCL::BufferedStream::FlushBuffer(this);
        *((_QWORD *)this + 7) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
        *((_QWORD *)this + 8) = (***((__int64 (__fastcall ****)(_QWORD))this + 4))(*((_QWORD *)this + 4));
        v5 += v13;
        if ( v4 <= 0 )
          return;
      }
      memcpy_0(v12, v11, (unsigned int)v4);
      v14 = v4 + *((_DWORD *)this + 13);
      *((_DWORD *)this + 13) = v14;
      v15 = (unsigned int)v4 + *((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v15;
      if ( *((_QWORD *)this + 8) < v15 )
        *((_QWORD *)this + 8) = v15;
      if ( v14 == *((_DWORD *)this + 12) )
        UnBCL::BufferedStream::FlushBuffer(this);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
    *((_QWORD *)this + 7) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
    *((_QWORD *)this + 8) = (***((__int64 (__fastcall ****)(_QWORD))this + 4))(*((_QWORD *)this + 4));
  }
}

```

## disassembly

```asm
0x180023690  push    rsi
0x180023692  push    rdi
0x180023693  push    r14
0x180023695  sub     rsp, 40h
0x180023699  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800236a2  mov     [rsp+58h+arg_0], rbx
0x1800236a7  mov     [rsp+58h+arg_10], rbp
0x1800236ac  mov     esi, r9d
0x1800236af  mov     ebp, r8d
0x1800236b2  mov     r14, rdx
0x1800236b5  mov     rdi, rcx
0x1800236b8  test    rdx, rdx
0x1800236bb  jz      loc_18002386B
0x1800236c1  test    r8d, r8d
0x1800236c4  js      loc_180023821
0x1800236ca  test    r9d, r9d
0x1800236cd  js      loc_180023821
0x1800236d3  mov     rcx, [rcx+20h]
0x1800236d7  test    rcx, rcx
0x1800236da  jz      loc_1800237D7
0x1800236e0  cmp     qword ptr [rdi+28h], 0
0x1800236e5  jz      loc_1800237A2
0x1800236eb  test    r9d, r9d
0x1800236ee  jle     short loc_180023759
0x1800236f0  mov     r9d, [rdi+30h]
0x1800236f4  mov     r8d, [rdi+34h]
0x1800236f8  movsxd  rdx, ebp
0x1800236fb  add     rdx, r14; Src
0x1800236fe  mov     rcx, [rdi+28h]
0x180023702  add     rcx, r8; void *
0x180023705  lea     eax, [r8+rsi]
0x180023709  cmp     eax, r9d
0x18002370c  jbe     short loc_18002376C
0x18002370e  sub     r9d, r8d
0x180023711  mov     ebx, r9d
0x180023714  mov     r8d, r9d; Size
0x180023717  call    memcpy_0
0x18002371c  sub     esi, ebx
0x18002371e  mov     eax, [rdi+30h]
0x180023721  mov     [rdi+34h], eax
0x180023724  mov     rcx, rdi; this
0x180023727  call    ?FlushBuffer@BufferedStream@UnBCL@@AEAAXXZ; UnBCL::BufferedStream::FlushBuffer(void)
0x18002372c  mov     rcx, [rdi+20h]
0x180023730  mov     rax, [rcx]
0x180023733  mov     rax, [rax+8]
0x180023737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002373c  mov     [rdi+38h], rax
0x180023740  mov     rcx, [rdi+20h]
0x180023744  mov     rax, [rcx]
0x180023747  mov     rax, [rax]
0x18002374a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002374f  mov     [rdi+40h], rax
0x180023753  add     ebp, ebx
0x180023755  test    esi, esi
0x180023757  jg      short loc_1800236F0
0x180023759  mov     rbx, [rsp+58h+arg_0]
0x18002375e  mov     rbp, [rsp+58h+arg_10]
0x180023763  add     rsp, 40h
0x180023767  pop     r14
0x180023769  pop     rdi
0x18002376a  pop     rsi
0x18002376b  retn
0x18002376c  mov     ebx, esi
0x18002376e  mov     r8d, esi; Size
0x180023771  call    memcpy_0
0x180023776  mov     edx, [rdi+34h]
0x180023779  add     edx, esi
0x18002377b  mov     [rdi+34h], edx
0x18002377e  mov     rcx, [rdi+38h]
0x180023782  add     rcx, rbx
0x180023785  mov     [rdi+38h], rcx
0x180023789  cmp     [rdi+40h], rcx
0x18002378d  jge     short loc_180023793
0x18002378f  mov     [rdi+40h], rcx
0x180023793  cmp     edx, [rdi+30h]
0x180023796  jnz     short loc_180023759
0x180023798  mov     rcx, rdi; this
0x18002379b  call    ?FlushBuffer@BufferedStream@UnBCL@@AEAAXXZ; UnBCL::BufferedStream::FlushBuffer(void)
0x1800237a0  jmp     short loc_180023759
0x1800237a2  mov     rax, [rcx]
0x1800237a5  mov     rax, [rax+30h]
0x1800237a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237ae  mov     rcx, [rdi+20h]
0x1800237b2  mov     rax, [rcx]
0x1800237b5  mov     rax, [rax+8]
0x1800237b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237be  mov     [rdi+38h], rax
0x1800237c2  mov     rcx, [rdi+20h]
0x1800237c6  mov     rax, [rcx]
0x1800237c9  mov     rax, [rax]
0x1800237cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237d1  mov     [rdi+40h], rax
0x1800237d5  jmp     short loc_180023759
0x1800237d7  mov     ecx, 38h ; '8'; unsigned __int64
0x1800237dc  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800237e1  mov     [rsp+58h+var_20], rax
0x1800237e6  test    rax, rax
0x1800237e9  jz      short loc_1800237FB
0x1800237eb  lea     rdx, aSeekOnClosedBu; "Seek() on closed BufferedStream"
0x1800237f2  mov     rcx, rax; this
0x1800237f5  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x1800237fa  nop
0x1800237fb  lea     rdx, aVoidCdeclUnbcl_139; "void __cdecl UnBCL::BufferedStream::Wri"...
0x180023802  mov     rcx, rax
0x180023805  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002380a  mov     [rsp+58h+pExceptionObject], rax
0x18002380f  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x180023816  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002381b  call    _CxxThrowException_0
0x180023821  mov     ecx, 38h ; '8'; unsigned __int64
0x180023826  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002382b  mov     [rsp+58h+var_20], rax
0x180023830  test    rax, rax
0x180023833  jz      short loc_180023845
0x180023835  lea     rdx, aNegativeOffset_1; "negative offset or count to BufferedStr"...
0x18002383c  mov     rcx, rax; this
0x18002383f  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180023844  nop
0x180023845  lea     rdx, aVoidCdeclUnbcl_139; "void __cdecl UnBCL::BufferedStream::Wri"...
0x18002384c  mov     rcx, rax
0x18002384f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180023854  mov     [rsp+58h+pExceptionObject], rax
0x180023859  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180023860  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180023865  call    _CxxThrowException_0
0x18002386b  mov     ecx, 38h ; '8'; unsigned __int64
0x180023870  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180023875  mov     [rsp+58h+var_20], rax
0x18002387a  test    rax, rax
0x18002387d  jz      short loc_18002388F
0x18002387f  lea     rdx, aNullBufToBuffe_0; "null buf to BufferedStream#Write"
0x180023886  mov     rcx, rax; this
0x180023889  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18002388e  nop
0x18002388f  lea     rdx, aVoidCdeclUnbcl_139; "void __cdecl UnBCL::BufferedStream::Wri"...
0x180023896  mov     rcx, rax
0x180023899  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002389e  mov     [rsp+58h+pExceptionObject], rax
0x1800238a3  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800238aa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800238af  call    _CxxThrowException_0
```
