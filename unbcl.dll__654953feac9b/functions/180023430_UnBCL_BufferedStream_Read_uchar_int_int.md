# UnBCL::BufferedStream::Read(uchar *,int,int)

- ea: `0x180023430`
- end: `0x18002359f`
- name: `?Read@BufferedStream@UnBCL@@UEAAHPEAEHH@Z`
- size: `367`
- prototype: `__int64 __fastcall(UnBCL::BufferedStream *__hidden this, unsigned __int8 *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x1800233f0`
- `0x180023430`
- `0x1800477d0`
- `0x180047d60`
- `0x18006f010`

## string_xrefs

- `0x1800234e5`: `int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)`
- `0x18002352f`: `int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)`
- `0x180023579`: `int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)`
- `0x180023569`: `null buf to BufferedStream#Read`
- `0x18002351f`: `negative offset or count to BufferedStream#Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::BufferedStream::Read(UnBCL::BufferedStream *this, unsigned __int8 *a2, int a3, int a4)
{
  unsigned int v8; // ebx
  UnBCL::ObjectDisposedException *v10; // rax
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  UnBCL::ArgumentNullException *v12; // rax
  __int64 pExceptionObject; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v12 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v12 )
      v12 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v12,
                                              L"null buf to BufferedStream#Read");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v11 )
      v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v11,
                                                    L"negative offset or count to BufferedStream#Read");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    v10 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v10 )
      v10 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v10,
                                                L"Seek() on closed BufferedStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "int __cdecl UnBCL::BufferedStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  UnBCL::BufferedStream::FlushBuffer(this);
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 40LL))(
         *((_QWORD *)this + 4),
         a2,
         (unsigned int)a3,
         (unsigned int)a4);
  *((_QWORD *)this + 7) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
  *((_QWORD *)this + 8) = (***((__int64 (__fastcall ****)(_QWORD))this + 4))(*((_QWORD *)this + 4));
  return v8;
}

```

## disassembly

```asm
0x180023430  push    rbx
0x180023432  push    rbp
0x180023433  push    rsi
0x180023434  push    rdi
0x180023435  sub     rsp, 48h
0x180023439  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x180023442  mov     ebx, r9d
0x180023445  mov     esi, r8d
0x180023448  mov     rbp, rdx
0x18002344b  mov     rdi, rcx
0x18002344e  test    rdx, rdx
0x180023451  jz      loc_180023555
0x180023457  test    r8d, r8d
0x18002345a  js      loc_18002350B
0x180023460  test    ebx, ebx
0x180023462  js      loc_18002350B
0x180023468  cmp     qword ptr [rcx+20h], 0
0x18002346d  jz      short loc_1800234C1
0x18002346f  call    ?FlushBuffer@BufferedStream@UnBCL@@AEAAXXZ; UnBCL::BufferedStream::FlushBuffer(void)
0x180023474  mov     rcx, [rdi+20h]
0x180023478  mov     rax, [rcx]
0x18002347b  mov     r9d, ebx
0x18002347e  mov     r8d, esi
0x180023481  mov     rdx, rbp
0x180023484  mov     rax, [rax+28h]
0x180023488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002348d  mov     ebx, eax
0x18002348f  mov     rcx, [rdi+20h]
0x180023493  mov     rdx, [rcx]
0x180023496  mov     rax, [rdx+8]
0x18002349a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002349f  mov     [rdi+38h], rax
0x1800234a3  mov     rcx, [rdi+20h]
0x1800234a7  mov     rdx, [rcx]
0x1800234aa  mov     rax, [rdx]
0x1800234ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234b2  mov     [rdi+40h], rax
0x1800234b6  mov     eax, ebx
0x1800234b8  add     rsp, 48h
0x1800234bc  pop     rdi
0x1800234bd  pop     rsi
0x1800234be  pop     rbp
0x1800234bf  pop     rbx
0x1800234c0  retn
0x1800234c1  mov     ecx, 38h ; '8'; unsigned __int64
0x1800234c6  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800234cb  mov     [rsp+68h+var_30], rax
0x1800234d0  test    rax, rax
0x1800234d3  jz      short loc_1800234E5
0x1800234d5  lea     rdx, aSeekOnClosedBu; "Seek() on closed BufferedStream"
0x1800234dc  mov     rcx, rax; this
0x1800234df  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x1800234e4  nop
0x1800234e5  lea     rdx, aIntCdeclUnbclB; "int __cdecl UnBCL::BufferedStream::Read"...
0x1800234ec  mov     rcx, rax
0x1800234ef  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800234f4  mov     [rsp+68h+pExceptionObject], rax
0x1800234f9  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x180023500  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180023505  call    _CxxThrowException_0
0x18002350b  mov     ecx, 38h ; '8'; unsigned __int64
0x180023510  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180023515  mov     [rsp+68h+var_30], rax
0x18002351a  test    rax, rax
0x18002351d  jz      short loc_18002352F
0x18002351f  lea     rdx, aNegativeOffset_1; "negative offset or count to BufferedStr"...
0x180023526  mov     rcx, rax; this
0x180023529  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18002352e  nop
0x18002352f  lea     rdx, aIntCdeclUnbclB; "int __cdecl UnBCL::BufferedStream::Read"...
0x180023536  mov     rcx, rax
0x180023539  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002353e  mov     [rsp+68h+pExceptionObject], rax
0x180023543  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18002354a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002354f  call    _CxxThrowException_0
0x180023555  mov     ecx, 38h ; '8'; unsigned __int64
0x18002355a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002355f  mov     [rsp+68h+var_30], rax
0x180023564  test    rax, rax
0x180023567  jz      short loc_180023579
0x180023569  lea     rdx, aNullBufToBuffe; "null buf to BufferedStream#Read"
0x180023570  mov     rcx, rax; this
0x180023573  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180023578  nop
0x180023579  lea     rdx, aIntCdeclUnbclB; "int __cdecl UnBCL::BufferedStream::Read"...
0x180023580  mov     rcx, rax
0x180023583  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180023588  mov     [rsp+68h+pExceptionObject], rax
0x18002358d  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180023594  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180023599  call    _CxxThrowException_0
```
