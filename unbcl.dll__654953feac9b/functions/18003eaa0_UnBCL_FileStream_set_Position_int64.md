# UnBCL::FileStream::set_Position(__int64)

- ea: `0x18003eaa0`
- end: `0x18003ebdb`
- name: `?set_Position@FileStream@UnBCL@@UEAAX_J@Z`
- size: `315`
- prototype: `void __fastcall(UnBCL::FileStream *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x180009b40`
- `0x180009e7c`
- `0x18003de78`
- `0x18003eaa0`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003eae3`
- `KERNEL32!SetFilePointer` at `0x18003eae3`

## string_xrefs

- `0x18003eba7`: `attempt to set negative FileStream position`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::FileStream::set_Position(UnBCL::FileStream *this, __int64 a2)
{
  HANDLE *v2; // rcx
  signed int Error; // ebx
  UnBCL::Win32Exception *v4; // rax
  UnBCL::ObjectDisposedException *v5; // rax
  UnBCL::ArgumentOutOfRangeException *v6; // rax
  __int64 DistanceToMoveHigh; // [rsp+40h] [rbp+10h] BYREF
  __int64 v8; // [rsp+48h] [rbp+18h]
  UnBCL::ObjectDisposedException *v9; // [rsp+50h] [rbp+20h]

  v8 = a2;
  v2 = (HANDLE *)*((_QWORD *)this + 4);
  if ( !v2 )
  {
    v5 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v9 = v5;
    if ( v5 )
      v5 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v5,
                                               L"set_Position() on closed FileStream");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v5,
                           "void __cdecl UnBCL::FileStream::set_Position(__int64)");
    throw (UnBCL::ObjectDisposedException **)&DistanceToMoveHigh;
  }
  if ( a2 < 0 )
  {
    v6 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v9 = v6;
    if ( v6 )
      v6 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                   v6,
                                                   L"attempt to set negative FileStream position");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v6,
                           "void __cdecl UnBCL::FileStream::set_Position(__int64)");
    throw (UnBCL::ArgumentOutOfRangeException **)&DistanceToMoveHigh;
  }
  DistanceToMoveHigh = __PAIR64__(HIDWORD(v8), a2);
  if ( SetFilePointer(*v2, a2, (PLONG)&DistanceToMoveHigh + 1, 0) == -1 )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
    {
      v4 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v9 = v4;
      if ( v4 )
        v4 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                        v4,
                                        Error,
                                        L"unable to set FileStream position");
      DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v4,
                             "void __cdecl UnBCL::FileStream::set_Position(__int64)");
      throw (UnBCL::Win32Exception **)&DistanceToMoveHigh;
    }
  }
}

```

## disassembly

```asm
0x18003eaa0  mov     [rsp-8+arg_8], rdx
0x18003eaa5  push    rbp
0x18003eaa6  mov     rbp, rsp
0x18003eaa9  sub     rsp, 30h
0x18003eaad  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18003eab5  mov     [rsp+30h+arg_18], rbx
0x18003eaba  mov     rcx, [rcx+20h]
0x18003eabe  test    rcx, rcx
0x18003eac1  jz      loc_18003EB4D
0x18003eac7  test    rdx, rdx
0x18003eaca  js      loc_18003EB94
0x18003ead0  mov     dword ptr [rbp+DistanceToMoveHigh], edx
0x18003ead3  mov     eax, dword ptr [rbp+arg_8+4]
0x18003ead6  mov     dword ptr [rbp+DistanceToMoveHigh+4], eax
0x18003ead9  xor     r9d, r9d; dwMoveMethod
0x18003eadc  lea     r8, [rbp+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18003eae0  mov     rcx, [rcx]; hFile
0x18003eae3  call    cs:__imp_SetFilePointer
0x18003eae9  cmp     eax, 0FFFFFFFFh
0x18003eaec  jnz     short loc_18003EAF9
0x18003eaee  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003eaf3  mov     ebx, eax
0x18003eaf5  test    eax, eax
0x18003eaf7  js      short loc_18003EB04
0x18003eaf9  mov     rbx, [rsp+30h+arg_18]
0x18003eafe  add     rsp, 30h
0x18003eb02  pop     rbp
0x18003eb03  retn
0x18003eb04  mov     ecx, 40h ; '@'; unsigned __int64
0x18003eb09  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003eb0e  mov     [rbp+arg_10], rax
0x18003eb12  test    rax, rax
0x18003eb15  jz      short loc_18003EB29
0x18003eb17  lea     r8, aUnableToSetFil; "unable to set FileStream position"
0x18003eb1e  mov     edx, ebx; dwMessageId
0x18003eb20  mov     rcx, rax; this
0x18003eb23  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003eb28  nop
0x18003eb29  lea     rdx, aVoidCdeclUnbcl_104; "void __cdecl UnBCL::FileStream::set_Pos"...
0x18003eb30  mov     rcx, rax
0x18003eb33  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003eb38  mov     [rbp+DistanceToMoveHigh], rax
0x18003eb3c  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003eb43  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003eb47  call    _CxxThrowException_0
0x18003eb4d  mov     ecx, 38h ; '8'; unsigned __int64
0x18003eb52  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003eb57  mov     [rbp+arg_10], rax
0x18003eb5b  test    rax, rax
0x18003eb5e  jz      short loc_18003EB70
0x18003eb60  lea     rdx, aSetPositionOnC; "set_Position() on closed FileStream"
0x18003eb67  mov     rcx, rax; this
0x18003eb6a  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003eb6f  nop
0x18003eb70  lea     rdx, aVoidCdeclUnbcl_104; "void __cdecl UnBCL::FileStream::set_Pos"...
0x18003eb77  mov     rcx, rax
0x18003eb7a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003eb7f  mov     [rbp+DistanceToMoveHigh], rax
0x18003eb83  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003eb8a  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003eb8e  call    _CxxThrowException_0
0x18003eb94  mov     ecx, 38h ; '8'; unsigned __int64
0x18003eb99  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003eb9e  mov     [rbp+arg_10], rax
0x18003eba2  test    rax, rax
0x18003eba5  jz      short loc_18003EBB7
0x18003eba7  lea     rdx, aAttemptToSetNe_0; "attempt to set negative FileStream posi"...
0x18003ebae  mov     rcx, rax; this
0x18003ebb1  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003ebb6  nop
0x18003ebb7  lea     rdx, aVoidCdeclUnbcl_104; "void __cdecl UnBCL::FileStream::set_Pos"...
0x18003ebbe  mov     rcx, rax
0x18003ebc1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003ebc6  mov     [rbp+DistanceToMoveHigh], rax
0x18003ebca  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003ebd1  lea     rcx, [rbp+DistanceToMoveHigh]; pExceptionObject
0x18003ebd5  call    _CxxThrowException_0
```
