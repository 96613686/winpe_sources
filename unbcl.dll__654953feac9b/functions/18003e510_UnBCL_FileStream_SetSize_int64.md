# UnBCL::FileStream::SetSize(__int64)

- ea: `0x18003e510`
- end: `0x18003e65d`
- name: `?SetSize@FileStream@UnBCL@@UEAAX_J@Z`
- size: `333`
- prototype: `void __fastcall(UnBCL::FileStream *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x180009e7c`
- `0x18003de78`
- `0x18003e510`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18003e569`
- `KERNEL32!SetEndOfFile` at `0x18003e569`
- `KERNEL32!SetFilePointer` at `0x18003e550`
- `KERNEL32!SetFilePointer` at `0x18003e550`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::FileStream::SetSize(UnBCL::FileStream *this, __int64 a2)
{
  HANDLE *v2; // rdi
  signed int Error; // ebx
  UnBCL::Win32Exception *v4; // rax
  UnBCL::ObjectDisposedException *v5; // rax
  UnBCL::ArgumentException *v6; // rax
  __int64 DistanceToMoveHigh; // [rsp+50h] [rbp+20h] BYREF
  __int64 v8; // [rsp+58h] [rbp+28h]
  UnBCL::ObjectDisposedException *v9; // [rsp+60h] [rbp+30h]

  v8 = a2;
  v2 = (HANDLE *)*((_QWORD *)this + 4);
  if ( !v2 )
  {
    v5 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v9 = v5;
    if ( v5 )
      v5 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v5,
                                               L"SetSize() on closed FileStream");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v5,
                           "void __cdecl UnBCL::FileStream::SetSize(__int64)");
    throw (UnBCL::ObjectDisposedException **)&DistanceToMoveHigh;
  }
  if ( a2 < 0 )
  {
    v6 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v9 = v6;
    if ( v6 )
      v6 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v6, L"Can't set a negative size");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v6,
                           "void __cdecl UnBCL::FileStream::SetSize(__int64)");
    throw (UnBCL::ArgumentException **)&DistanceToMoveHigh;
  }
  DistanceToMoveHigh = __PAIR64__(HIDWORD(v8), a2);
  if ( SetFilePointer(*v2, a2, (PLONG)&DistanceToMoveHigh + 1, 0) == -1
    && (Error = ATL::AtlHresultFromLastError(), Error < 0)
    || !SetEndOfFile(*v2) && (Error = ATL::AtlHresultFromLastError(), Error < 0) )
  {
    v4 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v9 = v4;
    if ( v4 )
      v4 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v4, Error, L"unable to SetSize on FileStream");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v4,
                           "void __cdecl UnBCL::FileStream::SetSize(__int64)");
    throw (UnBCL::Win32Exception **)&DistanceToMoveHigh;
  }
}

```

## disassembly

```asm
0x18003e510  mov     [rsp-18h+arg_8], rdx
0x18003e515  push    rbp
0x18003e516  push    rbx
0x18003e517  push    rdi
0x18003e518  mov     rbp, rsp
0x18003e51b  sub     rsp, 30h
0x18003e51f  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18003e527  mov     rdi, [rcx+20h]
0x18003e52b  test    rdi, rdi
0x18003e52e  jz      loc_18003E5CF
0x18003e534  test    rdx, rdx
0x18003e537  js      loc_18003E616
0x18003e53d  mov     dword ptr [rbp+DistanceToMoveHigh], edx
0x18003e540  mov     eax, dword ptr [rbp+arg_8+4]
0x18003e543  mov     dword ptr [rbp+DistanceToMoveHigh+4], eax
0x18003e546  xor     r9d, r9d; dwMoveMethod
0x18003e549  lea     r8, [rbp+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18003e54d  mov     rcx, [rdi]; hFile
0x18003e550  call    cs:__imp_SetFilePointer
0x18003e556  cmp     eax, 0FFFFFFFFh
0x18003e559  jnz     short loc_18003E566
0x18003e55b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e560  mov     ebx, eax
0x18003e562  test    eax, eax
0x18003e564  js      short loc_18003E586
0x18003e566  mov     rcx, [rdi]; hFile
0x18003e569  call    cs:__imp_SetEndOfFile
0x18003e56f  test    eax, eax
0x18003e571  jnz     short loc_18003E57E
0x18003e573  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e578  mov     ebx, eax
0x18003e57a  test    eax, eax
0x18003e57c  js      short loc_18003E586
0x18003e57e  add     rsp, 30h
0x18003e582  pop     rdi
0x18003e583  pop     rbx
0x18003e584  pop     rbp
0x18003e585  retn
0x18003e586  mov     ecx, 40h ; '@'; unsigned __int64
0x18003e58b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e590  mov     [rbp+arg_10], rax
0x18003e594  test    rax, rax
0x18003e597  jz      short loc_18003E5AB
0x18003e599  lea     r8, aUnableToSetsiz; "unable to SetSize on FileStream"
0x18003e5a0  mov     edx, ebx; dwMessageId
0x18003e5a2  mov     rcx, rax; this
0x18003e5a5  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003e5aa  nop
0x18003e5ab  lea     rdx, aVoidCdeclUnbcl_149; "void __cdecl UnBCL::FileStream::SetSize"...
0x18003e5b2  mov     rcx, rax
0x18003e5b5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e5ba  mov     [rbp+DistanceToMoveHigh], rax
0x18003e5be  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003e5c5  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e5c9  call    _CxxThrowException_0
0x18003e5cf  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e5d4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e5d9  mov     [rbp+arg_10], rax
0x18003e5dd  test    rax, rax
0x18003e5e0  jz      short loc_18003E5F2
0x18003e5e2  lea     rdx, aSetsizeOnClose; "SetSize() on closed FileStream"
0x18003e5e9  mov     rcx, rax; this
0x18003e5ec  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003e5f1  nop
0x18003e5f2  lea     rdx, aVoidCdeclUnbcl_149; "void __cdecl UnBCL::FileStream::SetSize"...
0x18003e5f9  mov     rcx, rax
0x18003e5fc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e601  mov     [rbp+DistanceToMoveHigh], rax
0x18003e605  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003e60c  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e610  call    _CxxThrowException_0
0x18003e616  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e61b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003e620  mov     [rbp+arg_10], rax
0x18003e624  test    rax, rax
0x18003e627  jz      short loc_18003E639
0x18003e629  lea     rdx, aCanTSetANegati; "Can't set a negative size"
0x18003e630  mov     rcx, rax; this
0x18003e633  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003e638  nop
0x18003e639  lea     rdx, aVoidCdeclUnbcl_149; "void __cdecl UnBCL::FileStream::SetSize"...
0x18003e640  mov     rcx, rax
0x18003e643  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003e648  mov     [rbp+DistanceToMoveHigh], rax
0x18003e64c  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003e653  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003e657  call    _CxxThrowException_0
```
