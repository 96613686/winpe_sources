# UnBCL::FileStream::Read(uchar *,int,int)

- ea: `0x18003e0a0`
- end: `0x18003e266`
- name: `?Read@FileStream@UnBCL@@UEAAHPEAEHH@Z`
- size: `454`
- prototype: `int(UnBCL::FileStream *__hidden this, unsigned __int8 *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003de78`
- `0x18003e0a0`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18003e104`
- `KERNEL32!ReadFile` at `0x18003e104`
- `KERNEL32!EnterCriticalSection` at `0x18003e129`
- `KERNEL32!EnterCriticalSection` at `0x18003e129`
- `KERNEL32!LeaveCriticalSection` at `0x18003e136`
- `KERNEL32!LeaveCriticalSection` at `0x18003e136`

## string_xrefs

- `0x18003e16d`: `int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)`
- `0x18003e1b4`: `int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)`
- `0x18003e1fb`: `int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)`
- `0x18003e242`: `int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)`
- `0x18003e1eb`: `null buf to FileStream#Read`
- `0x18003e1a4`: `negative offset or count to FileStream#Read`
- `0x18003e232`: `Read() on closed FileStream`
- `0x18003e15b`: `unable to read on FileStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UnBCL::FileStream::Read(UnBCL::FileStream *this, unsigned __int8 *a2, int a3, signed int a4)
{
  HANDLE *v5; // rcx
  DWORD Error; // ebx
  __int64 v7; // rsi
  __int64 v8; // rbx
  UnBCL::Win32Exception *v10; // rax
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  UnBCL::ArgumentNullException *v12; // rax
  UnBCL::ObjectDisposedException *v13; // rax
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-28h] BYREF
  UnBCL::ArgumentNullException *v15; // [rsp+40h] [rbp-18h]
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+30h] BYREF

  pExceptionObject[1] = -2;
  if ( !a2 )
  {
    v12 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v15 = v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v12,
                                              L"null buf to FileStream#Read");
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v12,
                            "int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)pExceptionObject;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v15 = v11;
    if ( v11 )
      v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v11,
                                                    L"negative offset or count to FileStream#Read");
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v11,
                            "int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)pExceptionObject;
  }
  v5 = (HANDLE *)*((_QWORD *)this + 4);
  if ( !v5 )
  {
    v13 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v15 = v13;
    if ( v13 )
      v13 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v13,
                                                L"Read() on closed FileStream");
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v13,
                            "int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)pExceptionObject;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(*v5, &a2[a3], a4, &NumberOfBytesRead, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error )
    {
      v10 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v15 = v10;
      if ( v10 )
        v10 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                         v10,
                                         Error,
                                         L"unable to read on FileStream");
      pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                              v10,
                              "int __cdecl UnBCL::FileStream::Read(unsigned char *,int,int)");
      throw (UnBCL::Win32Exception **)pExceptionObject;
    }
  }
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = NumberOfBytesRead;
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
    *(_QWORD *)v7 += v8;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  }
  return NumberOfBytesRead;
}

```

## disassembly

```asm
0x18003e0a0  push    rbp
0x18003e0a2  push    rbx
0x18003e0a3  push    rsi
0x18003e0a4  push    rdi
0x18003e0a5  mov     rbp, rsp
0x18003e0a8  sub     rsp, 58h
0x18003e0ac  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x18003e0b4  mov     eax, r9d
0x18003e0b7  mov     r9, rdx
0x18003e0ba  mov     rsi, rcx
0x18003e0bd  test    rdx, rdx
0x18003e0c0  jz      loc_18003E1D8
0x18003e0c6  test    r8d, r8d
0x18003e0c9  js      loc_18003E191
0x18003e0cf  test    eax, eax
0x18003e0d1  js      loc_18003E191
0x18003e0d7  mov     rcx, [rcx+20h]
0x18003e0db  test    rcx, rcx
0x18003e0de  jz      loc_18003E21F
0x18003e0e4  mov     [rbp+NumberOfBytesRead], 0
0x18003e0eb  movsxd  rdx, r8d
0x18003e0ee  add     rdx, r9; lpBuffer
0x18003e0f1  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18003e0fa  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003e0fe  mov     r8d, eax; nNumberOfBytesToRead
0x18003e101  mov     rcx, [rcx]; hFile
0x18003e104  call    cs:__imp_ReadFile
0x18003e10a  test    eax, eax
0x18003e10c  jnz     short loc_18003E119
0x18003e10e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e113  mov     ebx, eax
0x18003e115  test    eax, eax
0x18003e117  jnz     short loc_18003E148
0x18003e119  mov     rsi, [rsi+10h]
0x18003e11d  test    rsi, rsi
0x18003e120  jz      short loc_18003E13C
0x18003e122  mov     ebx, [rbp+NumberOfBytesRead]
0x18003e125  lea     rcx, [rsi+8]; lpCriticalSection
0x18003e129  call    cs:__imp_EnterCriticalSection
0x18003e12f  add     [rsi], rbx
0x18003e132  lea     rcx, [rsi+8]; lpCriticalSection
0x18003e136  call    cs:__imp_LeaveCriticalSection
0x18003e13c  mov     eax, [rbp+NumberOfBytesRead]
0x18003e13f  add     rsp, 58h
0x18003e143  pop     rdi
0x18003e144  pop     rsi
0x18003e145  pop     rbx
0x18003e146  pop     rbp
0x18003e147  retn
0x18003e148  mov     ecx, 40h ; '@'; unsigned __int64
0x18003e14d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e152  mov     [rbp+var_18], rax
0x18003e156  test    rax, rax
0x18003e159  jz      short loc_18003E16D
0x18003e15b  lea     r8, aUnableToReadOn; "unable to read on FileStream"
0x18003e162  mov     edx, ebx; dwMessageId
0x18003e164  mov     rcx, rax; this
0x18003e167  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003e16c  nop
0x18003e16d  lea     rdx, aIntCdeclUnbclF_0; "int __cdecl UnBCL::FileStream::Read(uns"...
0x18003e174  mov     rcx, rax
0x18003e177  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e17c  mov     [rbp+pExceptionObject], rax
0x18003e180  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003e187  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e18b  call    _CxxThrowException_0
0x18003e191  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e196  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e19b  mov     [rbp+var_18], rax
0x18003e19f  test    rax, rax
0x18003e1a2  jz      short loc_18003E1B4
0x18003e1a4  lea     rdx, aNegativeOffset; "negative offset or count to FileStream#"...
0x18003e1ab  mov     rcx, rax; this
0x18003e1ae  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003e1b3  nop
0x18003e1b4  lea     rdx, aIntCdeclUnbclF_0; "int __cdecl UnBCL::FileStream::Read(uns"...
0x18003e1bb  mov     rcx, rax
0x18003e1be  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e1c3  mov     [rbp+pExceptionObject], rax
0x18003e1c7  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003e1ce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e1d2  call    _CxxThrowException_0
0x18003e1d8  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e1dd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e1e2  mov     [rbp+var_18], rax
0x18003e1e6  test    rax, rax
0x18003e1e9  jz      short loc_18003E1FB
0x18003e1eb  lea     rdx, aNullBufToFiles_0; "null buf to FileStream#Read"
0x18003e1f2  mov     rcx, rax; this
0x18003e1f5  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003e1fa  nop
0x18003e1fb  lea     rdx, aIntCdeclUnbclF_0; "int __cdecl UnBCL::FileStream::Read(uns"...
0x18003e202  mov     rcx, rax
0x18003e205  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e20a  mov     [rbp+pExceptionObject], rax
0x18003e20e  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003e215  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e219  call    _CxxThrowException_0
0x18003e21f  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e224  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e229  mov     [rbp+var_18], rax
0x18003e22d  test    rax, rax
0x18003e230  jz      short loc_18003E242
0x18003e232  lea     rdx, aReadOnClosedFi; "Read() on closed FileStream"
0x18003e239  mov     rcx, rax; this
0x18003e23c  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003e241  nop
0x18003e242  lea     rdx, aIntCdeclUnbclF_0; "int __cdecl UnBCL::FileStream::Read(uns"...
0x18003e249  mov     rcx, rax
0x18003e24c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e251  mov     [rbp+pExceptionObject], rax
0x18003e255  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003e25c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e260  call    _CxxThrowException_0
```
