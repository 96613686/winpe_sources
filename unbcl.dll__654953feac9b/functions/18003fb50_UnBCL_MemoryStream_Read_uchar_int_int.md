# UnBCL::MemoryStream::Read(uchar *,int,int)

- ea: `0x18003fb50`
- end: `0x18003fd12`
- name: `?Read@MemoryStream@UnBCL@@UEAAHPEAEHH@Z`
- size: `450`
- prototype: `int(UnBCL::MemoryStream *__hidden this, unsigned __int8 *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000225c`
- `0x180002276`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x18003fb50`
- `0x1800477d0`
- `0x180047d60`
- `0x18006f010`

## string_xrefs

- `0x18003fc97`: `null buf to MemoryStream#Read`
- `0x18003fc19`: `int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)`
- `0x18003fc60`: `int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)`
- `0x18003fca7`: `int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)`
- `0x18003fcee`: `int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)`
- `0x18003fcde`: `Read() on closed MemoryStream`
- `0x18003fc09`: `m_Pos + amt overflowed in MemoryStream#Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UnBCL::MemoryStream::Read(UnBCL::MemoryStream *this, unsigned __int8 *a2, int a3, int a4)
{
  __int64 v4; // r14
  int v7; // esi
  const void *v9; // rax
  unsigned int v10; // ecx
  unsigned int v11; // eax
  UnBCL::ArgumentOutOfRangeException *v12; // rax
  UnBCL::ArgumentOutOfRangeException *v13; // rax
  UnBCL::ArgumentNullException *v14; // rax
  UnBCL::ObjectDisposedException *v15; // rax
  __int64 pExceptionObject; // [rsp+78h] [rbp+40h] BYREF

  v4 = a3;
  if ( !a2 )
  {
    v14 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v14 )
      v14 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v14,
                                              L"null buf to MemoryStream#Read");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 9) )
  {
    v15 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v15 )
      v15 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v15,
                                                L"Read() on closed MemoryStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( a3 < 0 || a4 < 0 )
  {
    v13 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v13 )
      v13 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v13,
                                                    L"negative offset or count");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = *((_DWORD *)this + 12) - *((_DWORD *)this + 13);
  if ( v7 <= 0 )
    return 0;
  if ( v7 > a4 )
    v7 = a4;
  v9 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
  memcpy_0(&a2[v4], v9, (unsigned int)v7);
  v10 = *((_DWORD *)this + 13);
  v11 = v10 + v7;
  if ( v10 + v7 < v10 )
  {
LABEL_13:
    v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v12 )
      v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v12,
                                                    L"m_Pos + amt overflowed in MemoryStream#Read");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "int __cdecl UnBCL::MemoryStream::Read(unsigned char *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    *((_DWORD *)this + 13) = -1;
    goto LABEL_13;
  }
  *((_DWORD *)this + 13) = v11;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003fb50  push    rbp
0x18003fb52  push    rbx
0x18003fb53  push    rsi
0x18003fb54  push    rdi
0x18003fb55  push    r14
0x18003fb57  push    r15
0x18003fb59  mov     rbp, rsp
0x18003fb5c  sub     rsp, 38h
0x18003fb60  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18003fb68  movsxd  r14, r8d
0x18003fb6b  mov     r15, rdx
0x18003fb6e  mov     rdi, rcx
0x18003fb71  test    rdx, rdx
0x18003fb74  jz      loc_18003FC84
0x18003fb7a  cmp     dword ptr [rcx+24h], 0
0x18003fb7e  jnz     loc_18003FCCB
0x18003fb84  test    r8d, r8d
0x18003fb87  js      loc_18003FC3D
0x18003fb8d  test    r9d, r9d
0x18003fb90  js      loc_18003FC3D
0x18003fb96  mov     edx, [rcx+34h]
0x18003fb99  mov     esi, [rcx+30h]
0x18003fb9c  sub     esi, edx
0x18003fb9e  test    esi, esi
0x18003fba0  jg      short loc_18003FBB1
0x18003fba2  xor     eax, eax
0x18003fba4  add     rsp, 38h
0x18003fba8  pop     r15
0x18003fbaa  pop     r14
0x18003fbac  pop     rdi
0x18003fbad  pop     rsi
0x18003fbae  pop     rbx
0x18003fbaf  pop     rbp
0x18003fbb0  retn
0x18003fbb1  cmp     esi, r9d
0x18003fbb4  cmovg   esi, r9d
0x18003fbb8  mov     rcx, [rcx+18h]
0x18003fbbc  mov     rax, [rcx]
0x18003fbbf  mov     rax, [rax+38h]
0x18003fbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbc8  mov     rdx, rax; Src
0x18003fbcb  lea     rcx, [r15+r14]; void *
0x18003fbcf  mov     r8d, esi; Size
0x18003fbd2  call    memcpy_0
0x18003fbd7  mov     ecx, [rdi+34h]
0x18003fbda  lea     eax, [rcx+rsi]
0x18003fbdd  cmp     eax, ecx
0x18003fbdf  jb      short loc_18003FBF6
0x18003fbe1  cmp     eax, 7FFFFFFFh
0x18003fbe6  ja      short loc_18003FBEF
0x18003fbe8  mov     [rdi+34h], eax
0x18003fbeb  mov     eax, esi
0x18003fbed  jmp     short loc_18003FBA4
0x18003fbef  mov     dword ptr [rdi+34h], 0FFFFFFFFh
0x18003fbf6  mov     ecx, 38h ; '8'; unsigned __int64
0x18003fbfb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003fc00  mov     [rbp+var_10], rax
0x18003fc04  test    rax, rax
0x18003fc07  jz      short loc_18003FC19
0x18003fc09  lea     rdx, aMPosAmtOverflo; "m_Pos + amt overflowed in MemoryStream#"...
0x18003fc10  mov     rcx, rax; this
0x18003fc13  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003fc18  nop
0x18003fc19  lea     rdx, aIntCdeclUnbclM_0; "int __cdecl UnBCL::MemoryStream::Read(u"...
0x18003fc20  mov     rcx, rax
0x18003fc23  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003fc28  mov     [rbp+pExceptionObject], rax
0x18003fc2c  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003fc33  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003fc37  call    _CxxThrowException_0
0x18003fc3d  mov     ecx, 38h ; '8'; unsigned __int64
0x18003fc42  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003fc47  mov     [rbp+var_10], rax
0x18003fc4b  test    rax, rax
0x18003fc4e  jz      short loc_18003FC60
0x18003fc50  lea     rdx, aNegativeOffset_0; "negative offset or count"
0x18003fc57  mov     rcx, rax; this
0x18003fc5a  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003fc5f  nop
0x18003fc60  lea     rdx, aIntCdeclUnbclM_0; "int __cdecl UnBCL::MemoryStream::Read(u"...
0x18003fc67  mov     rcx, rax
0x18003fc6a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003fc6f  mov     [rbp+pExceptionObject], rax
0x18003fc73  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003fc7a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003fc7e  call    _CxxThrowException_0
0x18003fc84  mov     ecx, 38h ; '8'; unsigned __int64
0x18003fc89  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003fc8e  mov     [rbp+var_10], rax
0x18003fc92  test    rax, rax
0x18003fc95  jz      short loc_18003FCA7
0x18003fc97  lea     rdx, aNullBufToMemor_0; "null buf to MemoryStream#Read"
0x18003fc9e  mov     rcx, rax; this
0x18003fca1  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003fca6  nop
0x18003fca7  lea     rdx, aIntCdeclUnbclM_0; "int __cdecl UnBCL::MemoryStream::Read(u"...
0x18003fcae  mov     rcx, rax
0x18003fcb1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003fcb6  mov     [rbp+pExceptionObject], rax
0x18003fcba  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003fcc1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003fcc5  call    _CxxThrowException_0
0x18003fccb  mov     ecx, 38h ; '8'; unsigned __int64
0x18003fcd0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003fcd5  mov     [rbp+var_10], rax
0x18003fcd9  test    rax, rax
0x18003fcdc  jz      short loc_18003FCEE
0x18003fcde  lea     rdx, aReadOnClosedMe; "Read() on closed MemoryStream"
0x18003fce5  mov     rcx, rax; this
0x18003fce8  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003fced  nop
0x18003fcee  lea     rdx, aIntCdeclUnbclM_0; "int __cdecl UnBCL::MemoryStream::Read(u"...
0x18003fcf5  mov     rcx, rax
0x18003fcf8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003fcfd  mov     [rbp+pExceptionObject], rax
0x18003fd01  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003fd08  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003fd0c  call    _CxxThrowException_0
```
