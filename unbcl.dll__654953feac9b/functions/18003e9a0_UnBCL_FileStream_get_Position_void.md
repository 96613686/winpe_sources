# UnBCL::FileStream::get_Position(void)

- ea: `0x18003e9a0`
- end: `0x18003ea90`
- name: `?get_Position@FileStream@UnBCL@@UEBA_JXZ`
- size: `240`
- prototype: `__int64 __fastcall(UnBCL::FileStream *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x18003de78`
- `0x18003e9a0`
- `0x1800477d0`
- `0x180047d60`
- `0x1800641a0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003e9d5`
- `KERNEL32!SetFilePointer` at `0x18003e9d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::FileStream::get_Position(UnBCL::FileStream *this)
{
  HANDLE *v1; // rcx
  signed int Error; // ebx
  UnBCL::Win32Exception *v4; // rax
  UnBCL::ObjectDisposedException *v5; // rax
  __int64 DistanceToMoveHigh; // [rsp+40h] [rbp+8h] BYREF
  UnBCL::ObjectDisposedException *v7; // [rsp+48h] [rbp+10h]

  v1 = (HANDLE *)*((_QWORD *)this + 4);
  if ( !v1 )
  {
    v5 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v7 = v5;
    if ( v5 )
      v5 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v5,
                                               L"get_Position() on closed FileStream");
    DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v5,
                           "__int64 __cdecl UnBCL::FileStream::get_Position(void) const");
    throw (UnBCL::ObjectDisposedException **)&DistanceToMoveHigh;
  }
  DistanceToMoveHigh = 0;
  LODWORD(DistanceToMoveHigh) = SetFilePointer(*v1, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
  if ( (_DWORD)DistanceToMoveHigh == -1 )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
    {
      v4 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v7 = v4;
      if ( v4 )
        v4 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v4, Error, L"unable to get file position");
      DistanceToMoveHigh = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v4,
                             "__int64 __cdecl UnBCL::FileStream::get_Position(void) const");
      throw (UnBCL::Win32Exception **)&DistanceToMoveHigh;
    }
  }
  return DistanceToMoveHigh;
}

```

## disassembly

```asm
0x18003e9a0  push    rbx
0x18003e9a2  sub     rsp, 30h
0x18003e9a6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18003e9af  mov     rcx, [rcx+20h]
0x18003e9b3  test    rcx, rcx
0x18003e9b6  jz      loc_18003EA46
0x18003e9bc  mov     [rsp+38h+DistanceToMoveHigh], 0
0x18003e9c5  mov     r9d, 1; dwMoveMethod
0x18003e9cb  lea     r8, [rsp+38h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18003e9d0  xor     edx, edx; lDistanceToMove
0x18003e9d2  mov     rcx, [rcx]; hFile
0x18003e9d5  call    cs:__imp_SetFilePointer
0x18003e9db  mov     dword ptr [rsp+38h+DistanceToMoveHigh], eax
0x18003e9df  cmp     eax, 0FFFFFFFFh
0x18003e9e2  jnz     short loc_18003E9EF
0x18003e9e4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003e9e9  mov     ebx, eax
0x18003e9eb  test    eax, eax
0x18003e9ed  js      short loc_18003E9FA
0x18003e9ef  mov     rax, [rsp+38h+DistanceToMoveHigh]
0x18003e9f4  add     rsp, 30h
0x18003e9f8  pop     rbx
0x18003e9f9  retn
0x18003e9fa  mov     ecx, 40h ; '@'; unsigned __int64
0x18003e9ff  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003ea04  mov     [rsp+38h+arg_8], rax
0x18003ea09  test    rax, rax
0x18003ea0c  jz      short loc_18003EA20
0x18003ea0e  lea     r8, aUnableToGetFil; "unable to get file position"
0x18003ea15  mov     edx, ebx; dwMessageId
0x18003ea17  mov     rcx, rax; this
0x18003ea1a  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18003ea1f  nop
0x18003ea20  lea     rdx, aInt64CdeclUnbc; "__int64 __cdecl UnBCL::FileStream::get_"...
0x18003ea27  mov     rcx, rax
0x18003ea2a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003ea2f  mov     [rsp+38h+DistanceToMoveHigh], rax
0x18003ea34  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003ea3b  lea     rcx, [rsp+38h+DistanceToMoveHigh]; pExceptionObject
0x18003ea40  call    _CxxThrowException_0
0x18003ea46  mov     ecx, 38h ; '8'; unsigned __int64
0x18003ea4b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003ea50  mov     [rsp+38h+arg_8], rax
0x18003ea55  test    rax, rax
0x18003ea58  jz      short loc_18003EA6A
0x18003ea5a  lea     rdx, aGetPositionOnC_1; "get_Position() on closed FileStream"
0x18003ea61  mov     rcx, rax; this
0x18003ea64  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18003ea69  nop
0x18003ea6a  lea     rdx, aInt64CdeclUnbc; "__int64 __cdecl UnBCL::FileStream::get_"...
0x18003ea71  mov     rcx, rax
0x18003ea74  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003ea79  mov     [rsp+38h+DistanceToMoveHigh], rax
0x18003ea7e  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18003ea85  lea     rcx, [rsp+38h+DistanceToMoveHigh]; pExceptionObject
0x18003ea8a  call    _CxxThrowException_0
```
