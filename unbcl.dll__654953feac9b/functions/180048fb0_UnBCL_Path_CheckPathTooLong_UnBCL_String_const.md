# UnBCL::Path::CheckPathTooLong(UnBCL::String const *)

- ea: `0x180048fb0`
- end: `0x180049136`
- name: `?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z`
- size: `390`
- prototype: `void __fastcall(const struct UnBCL::String *)`
- caller_count: `14`
- callee_count: `10`
- tags: ``

## callers

- `0x180028470`
- `0x180029280`
- `0x180029b30`
- `0x18002a870`
- `0x18002bca0`
- `0x18002eb20`
- `0x1800306a0`
- `0x18003b2e0`
- `0x18003b5f0`
- `0x18003c0a0`
- `0x18003c3a0`
- `0x18003c680`
- `0x18003c960`
- `0x18003d910`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x180036c90`
- `0x1800477d0`
- `0x180048e10`
- `0x180048e58`
- `0x180048ea0`
- `0x180048fb0`
- `0x18004b0e0`
- `0x18005dc40`

## string_xrefs

- `0x18004906e`: `void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)`
- `0x1800490c0`: `void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)`
- `0x180049110`: `void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::Path::CheckPathTooLong(const struct UnBCL::String *a1)
{
  __int64 v2; // rbx
  UnBCL::PathTooLongException *v3; // rdi
  const struct UnBCL::String *v4; // rax
  __int64 v5; // rcx
  UnBCL::PathTooLongException *v6; // rdi
  __int64 v7; // rbx
  const struct UnBCL::String *v8; // rax
  __int64 v9; // rcx
  UnBCL::PathTooLongException *v10; // rdi
  const struct UnBCL::String *v11; // rax
  __int64 pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  UnBCL::PathTooLongException *v13; // [rsp+50h] [rbp+18h]

  if ( *((_DWORD *)UnBCL::Environment::GetOSVersion(0) + 2) == 2 )
  {
    if ( *(int *)(*((_QWORD *)a1 + 2) - 16LL) > 260 )
    {
      v6 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
      v13 = v6;
      v7 = 0;
      if ( v6 )
      {
        v8 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_12__0(v5);
        v7 = UnBCL::PathTooLongException::PathTooLongException(v6, v8);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v7,
                           "void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)");
      throw (UnBCL::PathTooLongException **)&pExceptionObject;
    }
  }
  else
  {
    v2 = 0;
    if ( (unsigned int)UnBCL::String::StartsWith(a1, L"\\\\?\\", 1)
      || (unsigned int)UnBCL::String::StartsWith(a1, L"\\\\?\\UNC\\", 1) )
    {
      if ( *(int *)(*((_QWORD *)a1 + 2) - 16LL) > 0x7FFF )
      {
        v3 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
        v13 = v3;
        if ( v3 )
        {
          v4 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_13__0();
          v2 = UnBCL::PathTooLongException::PathTooLongException(v3, v4);
        }
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v2,
                             "void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)");
        throw (UnBCL::PathTooLongException **)&pExceptionObject;
      }
    }
    else if ( *(int *)(*((_QWORD *)a1 + 2) - 16LL) > 260 )
    {
      v10 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
      v13 = v10;
      if ( v10 )
      {
        v11 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_14_(v9);
        v2 = UnBCL::PathTooLongException::PathTooLongException(v10, v11);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v2,
                           "void __cdecl UnBCL::Path::CheckPathTooLong(const class UnBCL::String *)");
      throw (UnBCL::PathTooLongException **)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180048fb0  push    rdi
0x180048fb2  sub     rsp, 30h
0x180048fb6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180048fbf  mov     [rsp+38h+arg_0], rbx
0x180048fc4  mov     rdi, rcx
0x180048fc7  xor     ecx, ecx; int
0x180048fc9  call    ?GetOSVersion@Environment@UnBCL@@SAPEBVOperatingSystem@2@H@Z; UnBCL::Environment::GetOSVersion(int)
0x180048fce  cmp     dword ptr [rax+8], 2
0x180048fd2  jnz     short loc_180048FE7
0x180048fd4  mov     rax, [rdi+10h]
0x180048fd8  cmp     dword ptr [rax-10h], 104h
0x180048fdf  jg      loc_180049094
0x180048fe5  jmp     short loc_180049039
0x180048fe7  mov     r8d, 1; int
0x180048fed  lea     rdx, asc_1800895A0; "\\\\?\\"
0x180048ff4  mov     rcx, rdi; this
0x180048ff7  call    ?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180048ffc  xor     ebx, ebx
0x180048ffe  test    eax, eax
0x180049000  jnz     short loc_18004902C
0x180049002  lea     r8d, [rbx+1]; int
0x180049006  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18004900d  mov     rcx, rdi; this
0x180049010  call    ?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180049015  test    eax, eax
0x180049017  jnz     short loc_18004902C
0x180049019  mov     rax, [rdi+10h]
0x18004901d  cmp     dword ptr [rax-10h], 104h
0x180049024  jg      loc_1800490E6
0x18004902a  jmp     short loc_180049039
0x18004902c  mov     rax, [rdi+10h]
0x180049030  cmp     dword ptr [rax-10h], 7FFFh
0x180049037  jg      short loc_180049044
0x180049039  mov     rbx, [rsp+38h+arg_0]
0x18004903e  add     rsp, 30h
0x180049042  pop     rdi
0x180049043  retn
0x180049044  mov     ecx, 38h ; '8'; unsigned __int64
0x180049049  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004904e  mov     rdi, rax
0x180049051  mov     [rsp+38h+arg_10], rax
0x180049056  test    rax, rax
0x180049059  jz      short loc_18004906E
0x18004905b  call    UnBCL_____StringLiteral_13__0
0x180049060  mov     rdx, rax; struct UnBCL::String *
0x180049063  mov     rcx, rdi; this
0x180049066  call    ??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x18004906b  mov     rbx, rax
0x18004906e  lea     rdx, aVoidCdeclUnbcl_116; "void __cdecl UnBCL::Path::CheckPathTooL"...
0x180049075  mov     rcx, rbx
0x180049078  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004907d  mov     [rsp+38h+pExceptionObject], rax
0x180049082  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x180049089  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18004908e  call    _CxxThrowException_0
0x180049094  mov     ecx, 38h ; '8'; unsigned __int64
0x180049099  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004909e  mov     rdi, rax
0x1800490a1  mov     [rsp+38h+arg_10], rax
0x1800490a6  xor     ebx, ebx
0x1800490a8  test    rax, rax
0x1800490ab  jz      short loc_1800490C0
0x1800490ad  call    UnBCL_____StringLiteral_12__0
0x1800490b2  mov     rdx, rax; struct UnBCL::String *
0x1800490b5  mov     rcx, rdi; this
0x1800490b8  call    ??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x1800490bd  mov     rbx, rax
0x1800490c0  lea     rdx, aVoidCdeclUnbcl_116; "void __cdecl UnBCL::Path::CheckPathTooL"...
0x1800490c7  mov     rcx, rbx
0x1800490ca  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800490cf  mov     [rsp+38h+pExceptionObject], rax
0x1800490d4  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x1800490db  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800490e0  call    _CxxThrowException_0
0x1800490e6  mov     ecx, 38h ; '8'; unsigned __int64
0x1800490eb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800490f0  mov     rdi, rax
0x1800490f3  mov     [rsp+38h+arg_10], rax
0x1800490f8  test    rax, rax
0x1800490fb  jz      short loc_180049110
0x1800490fd  call    UnBCL_____StringLiteral_14_
0x180049102  mov     rdx, rax; struct UnBCL::String *
0x180049105  mov     rcx, rdi; this
0x180049108  call    ??0PathTooLongException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::PathTooLongException::PathTooLongException(UnBCL::String const *)
0x18004910d  mov     rbx, rax
0x180049110  lea     rdx, aVoidCdeclUnbcl_116; "void __cdecl UnBCL::Path::CheckPathTooL"...
0x180049117  mov     rcx, rbx
0x18004911a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004911f  mov     [rsp+38h+pExceptionObject], rax
0x180049124  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x18004912b  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180049130  call    _CxxThrowException_0
```
