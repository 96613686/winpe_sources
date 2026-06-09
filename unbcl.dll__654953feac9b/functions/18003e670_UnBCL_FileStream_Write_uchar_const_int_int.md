# UnBCL::FileStream::Write(uchar const *,int,int)

- ea: `0x18003e670`
- end: `0x18003e831`
- name: `?Write@FileStream@UnBCL@@UEAAXPEBEHH@Z`
- size: `449`
- prototype: `void __fastcall(UnBCL::FileStream *__hidden this, const unsigned __int8 *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003de78`
- `0x18003e670`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18003e6d5`
- `KERNEL32!WriteFile` at `0x18003e6d5`
- `KERNEL32!EnterCriticalSection` at `0x18003e6f7`
- `KERNEL32!EnterCriticalSection` at `0x18003e6f7`
- `KERNEL32!LeaveCriticalSection` at `0x18003e704`
- `KERNEL32!LeaveCriticalSection` at `0x18003e704`

## string_xrefs

- `0x18003e76f`: `negative offset or count to FileStream#Read`
- `0x18003e738`: `void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)`
- `0x18003e77f`: `void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)`
- `0x18003e7c6`: `void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)`
- `0x18003e80d`: `void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)`
- `0x18003e7b6`: `null buf to FileStream#Write`
- `0x18003e7fd`: `Write() on closed FileStream`
- `0x18003e726`: `unable to write to FileStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UnBCL::FileStream::Write(UnBCL::FileStream *this, const unsigned __int8 *a2, int a3, signed int a4)
{
  __int64 v4; // rsi
  HANDLE *v6; // rcx
  DWORD Error; // ebx
  __int64 v8; // rdi
  UnBCL::Win32Exception *v9; // rax
  UnBCL::ArgumentOutOfRangeException *v10; // rax
  UnBCL::ArgumentNullException *v11; // rax
  UnBCL::ObjectDisposedException *v12; // rax
  __int64 NumberOfBytesWritten; // [rsp+78h] [rbp+30h] BYREF

  v4 = a4;
  if ( !a2 )
  {
    v11 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v11 )
      v11 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v11,
                                              L"null buf to FileStream#Write");
    NumberOfBytesWritten = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v11,
                             "void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)&NumberOfBytesWritten;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v10 )
      v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v10,
                                                    L"negative offset or count to FileStream#Read");
    NumberOfBytesWritten = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v10,
                             "void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&NumberOfBytesWritten;
  }
  v6 = (HANDLE *)*((_QWORD *)this + 4);
  if ( !v6 )
  {
    v12 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v12 )
      v12 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v12,
                                                L"Write() on closed FileStream");
    NumberOfBytesWritten = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v12,
                             "void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)&NumberOfBytesWritten;
  }
  LODWORD(NumberOfBytesWritten) = 0;
  if ( !WriteFile(*v6, &a2[a3], a4, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error )
    {
      v9 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      if ( v9 )
        v9 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v9, Error, L"unable to write to FileStream");
      NumberOfBytesWritten = AddStackTraceToException<UnBCL::InvalidOperationException>(
                               v9,
                               "void __cdecl UnBCL::FileStream::Write(const unsigned char *,int,int)");
      throw (UnBCL::Win32Exception **)&NumberOfBytesWritten;
    }
  }
  v8 = *((_QWORD *)this + 2);
  if ( v8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    *(_QWORD *)v8 += v4;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  }
}

```

## disassembly

```asm
0x18003e670  push    rbp
0x18003e672  push    rbx
0x18003e673  push    rsi
0x18003e674  push    rdi
0x18003e675  mov     rbp, rsp
0x18003e678  sub     rsp, 48h
0x18003e67c  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18003e684  movsxd  rsi, r9d
0x18003e687  mov     rax, rdx
0x18003e68a  mov     rdi, rcx
0x18003e68d  test    rdx, rdx
0x18003e690  jz      loc_18003E7A3
0x18003e696  test    r8d, r8d
0x18003e699  js      loc_18003E75C
0x18003e69f  test    r9d, r9d
0x18003e6a2  js      loc_18003E75C
0x18003e6a8  mov     rcx, [rcx+20h]
0x18003e6ac  test    rcx, rcx
0x18003e6af  jz      loc_18003E7EA
0x18003e6b5  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x18003e6bc  movsxd  rdx, r8d
0x18003e6bf  add     rdx, rax; lpBuffer
0x18003e6c2  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18003e6cb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e6cf  mov     r8d, esi; nNumberOfBytesToWrite
0x18003e6d2  mov     rcx, [rcx]; hFile
0x18003e6d5  call    cs:__imp_WriteFile
0x18003e6db  test    eax, eax
0x18003e6dd  jnz     short loc_18003E6EA
0x18003e6df  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e6e4  mov     ebx, eax
0x18003e6e6  test    eax, eax
0x18003e6e8  jnz     short loc_18003E713
0x18003e6ea  mov     rdi, [rdi+10h]
0x18003e6ee  test    rdi, rdi
0x18003e6f1  jz      short loc_18003E70A
0x18003e6f3  lea     rcx, [rdi+8]; lpCriticalSection
0x18003e6f7  call    cs:__imp_EnterCriticalSection
0x18003e6fd  add     [rdi], rsi
0x18003e700  lea     rcx, [rdi+8]; lpCriticalSection
0x18003e704  call    cs:__imp_LeaveCriticalSection
0x18003e70a  add     rsp, 48h
0x18003e70e  pop     rdi
0x18003e70f  pop     rsi
0x18003e710  pop     rbx
0x18003e711  pop     rbp
0x18003e712  retn
0x18003e713  mov     ecx, 40h ; '@'; unsigned __int64
0x18003e718  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e71d  mov     [rbp+var_10], rax
0x18003e721  test    rax, rax
0x18003e724  jz      short loc_18003E738
0x18003e726  lea     r8, aUnableToWriteT; "unable to write to FileStream"
0x18003e72d  mov     edx, ebx; dwMessageId
0x18003e72f  mov     rcx, rax; this
0x18003e732  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003e737  nop
0x18003e738  lea     rdx, aVoidCdeclUnbcl_33; "void __cdecl UnBCL::FileStream::Write(c"...
0x18003e73f  mov     rcx, rax
0x18003e742  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e747  mov     [rbp+NumberOfBytesWritten], rax
0x18003e74b  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003e752  lea     rcx, [rbp+NumberOfBytesWritten]; pExceptionObject
0x18003e756  call    _CxxThrowException_0
0x18003e75c  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e761  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e766  mov     [rbp+var_10], rax
0x18003e76a  test    rax, rax
0x18003e76d  jz      short loc_18003E77F
0x18003e76f  lea     rdx, aNegativeOffset; "negative offset or count to FileStream#"...
0x18003e776  mov     rcx, rax; this
0x18003e779  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003e77e  nop
0x18003e77f  lea     rdx, aVoidCdeclUnbcl_33; "void __cdecl UnBCL::FileStream::Write(c"...
0x18003e786  mov     rcx, rax
0x18003e789  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e78e  mov     [rbp+NumberOfBytesWritten], rax
0x18003e792  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003e799  lea     rcx, [rbp+NumberOfBytesWritten]; pExceptionObject
0x18003e79d  call    _CxxThrowException_0
0x18003e7a3  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e7a8  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e7ad  mov     [rbp+var_10], rax
0x18003e7b1  test    rax, rax
0x18003e7b4  jz      short loc_18003E7C6
0x18003e7b6  lea     rdx, aNullBufToFiles; "null buf to FileStream#Write"
0x18003e7bd  mov     rcx, rax; this
0x18003e7c0  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003e7c5  nop
0x18003e7c6  lea     rdx, aVoidCdeclUnbcl_33; "void __cdecl UnBCL::FileStream::Write(c"...
0x18003e7cd  mov     rcx, rax
0x18003e7d0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e7d5  mov     [rbp+NumberOfBytesWritten], rax
0x18003e7d9  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003e7e0  lea     rcx, [rbp+NumberOfBytesWritten]; pExceptionObject
0x18003e7e4  call    _CxxThrowException_0
0x18003e7ea  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e7ef  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e7f4  mov     [rbp+var_10], rax
0x18003e7f8  test    rax, rax
0x18003e7fb  jz      short loc_18003E80D
0x18003e7fd  lea     rdx, aWriteOnClosedF; "Write() on closed FileStream"
0x18003e804  mov     rcx, rax; this
0x18003e807  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003e80c  nop
0x18003e80d  lea     rdx, aVoidCdeclUnbcl_33; "void __cdecl UnBCL::FileStream::Write(c"...
0x18003e814  mov     rcx, rax
0x18003e817  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e81c  mov     [rbp+NumberOfBytesWritten], rax
0x18003e820  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003e827  lea     rcx, [rbp+NumberOfBytesWritten]; pExceptionObject
0x18003e82b  call    _CxxThrowException_0
```
