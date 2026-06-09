# UnBCL::SerializationStream::ReadBytes(uchar *,int)

- ea: `0x180054ff0`
- end: `0x180055142`
- name: `?ReadBytes@SerializationStream@UnBCL@@QEAAXPEAEH@Z`
- size: `338`
- prototype: `void __fastcall(UnBCL::SerializationStream *__hidden this, unsigned __int8 *, int)`
- caller_count: `20`
- callee_count: `10`
- tags: ``

## callers

- `0x180004bc0`
- `0x180004c50`
- `0x180004cd0`
- `0x180004d60`
- `0x180004de0`
- `0x180004e60`
- `0x180004ee0`
- `0x180004f60`
- `0x180004fe0`
- `0x180005060`
- `0x1800050e0`
- `0x18001fc10`
- `0x18001fd40`
- `0x18001fe70`
- `0x1800463c0`
- `0x180050058`
- `0x1800500d8`
- `0x180050158`
- `0x180054f90`
- `0x18005dce0`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x180048a40`
- `0x18004ffe0`
- `0x1800502f8`
- `0x180050340`
- `0x180054ff0`
- `0x18006f010`

## string_xrefs

- `0x18005510c`: `ReadBytes() on closed SerializationStream`
- `0x180055084`: `void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)`
- `0x1800550d2`: `void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)`
- `0x18005511c`: `void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::SerializationStream::ReadBytes(UnBCL::SerializationStream *this, unsigned __int8 *a2, int a3)
{
  int v6; // ebx
  int v7; // eax
  UnBCL::OverflowException *v8; // rax
  UnBCL::OverflowException *v9; // rbx
  const struct UnBCL::String *v10; // rax
  UnBCL::SerializationException *v11; // rax
  UnBCL::SerializationException *v12; // rbx
  const struct UnBCL::String *v13; // rax
  UnBCL::ObjectDisposedException *v14; // rax
  __int64 pExceptionObject; // [rsp+60h] [rbp+8h] BYREF
  UnBCL::ObjectDisposedException *v16; // [rsp+78h] [rbp+20h]

  if ( !*((_QWORD *)this + 6) )
  {
    v14 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v16 = v14;
    if ( v14 )
      v14 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v14,
                                                L"ReadBytes() on closed SerializationStream");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  v6 = 0;
  if ( a3 > 0 )
  {
    while ( 1 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 40LL))(
             *((_QWORD *)this + 6),
             a2,
             (unsigned int)v6,
             (unsigned int)(a3 - v6));
      if ( !v7 )
        break;
      v6 += v7;
      if ( v6 < 0 )
      {
        v8 = (UnBCL::OverflowException *)UnBCL::Object::operator new(0x38u);
        v9 = v8;
        v16 = v8;
        if ( v8 )
        {
          v10 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_5__0();
          v8 = (UnBCL::OverflowException *)UnBCL::OverflowException::OverflowException(v9, v10);
        }
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v8,
                             "void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)");
        throw (UnBCL::OverflowException **)&pExceptionObject;
      }
      if ( v6 >= a3 )
        return;
    }
    if ( v6 < a3 )
    {
      v11 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
      v12 = v11;
      v16 = v11;
      if ( v11 )
      {
        v13 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_6__0();
        v11 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v12, v13);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v11,
                           "void __cdecl UnBCL::SerializationStream::ReadBytes(unsigned char *,int)");
      throw (UnBCL::SerializationException **)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180054ff0  push    rbp
0x180054ff2  push    rsi
0x180054ff3  push    rdi
0x180054ff4  sub     rsp, 40h
0x180054ff8  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x180055001  mov     [rsp+58h+arg_8], rbx
0x180055006  mov     edi, r8d
0x180055009  mov     rbp, rdx
0x18005500c  mov     rsi, rcx
0x18005500f  cmp     qword ptr [rcx+30h], 0
0x180055014  jz      loc_1800550F8
0x18005501a  xor     ebx, ebx
0x18005501c  test    r8d, r8d
0x18005501f  jle     short loc_180055049
0x180055021  mov     rcx, [rsi+30h]
0x180055025  mov     rax, [rcx]
0x180055028  mov     r9d, edi
0x18005502b  sub     r9d, ebx
0x18005502e  mov     r8d, ebx
0x180055031  mov     rdx, rbp
0x180055034  mov     rax, [rax+28h]
0x180055038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005503d  test    eax, eax
0x18005503f  jz      short loc_180055056
0x180055041  add     ebx, eax
0x180055043  js      short loc_18005505C
0x180055045  cmp     ebx, edi
0x180055047  jl      short loc_180055021
0x180055049  mov     rbx, [rsp+58h+arg_8]
0x18005504e  add     rsp, 40h
0x180055052  pop     rdi
0x180055053  pop     rsi
0x180055054  pop     rbp
0x180055055  retn
0x180055056  cmp     ebx, edi
0x180055058  jl      short loc_1800550AA
0x18005505a  jmp     short loc_180055049
0x18005505c  mov     ecx, 38h ; '8'; unsigned __int64
0x180055061  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055066  mov     rbx, rax
0x180055069  mov     [rsp+58h+arg_18], rax
0x18005506e  test    rax, rax
0x180055071  jz      short loc_180055084
0x180055073  call    UnBCL_____StringLiteral_5__0
0x180055078  mov     rdx, rax; struct UnBCL::String *
0x18005507b  mov     rcx, rbx; this
0x18005507e  call    ??0OverflowException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::OverflowException::OverflowException(UnBCL::String const *)
0x180055083  nop
0x180055084  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::SerializationStream"...
0x18005508b  mov     rcx, rax
0x18005508e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055093  mov     [rsp+58h+pExceptionObject], rax
0x180055098  lea     rdx, _TI6PEAVOverflowException@UnBCL@@; pThrowInfo
0x18005509f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800550a4  call    _CxxThrowException_0
0x1800550aa  mov     ecx, 38h ; '8'; unsigned __int64
0x1800550af  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800550b4  mov     rbx, rax
0x1800550b7  mov     [rsp+58h+arg_18], rax
0x1800550bc  test    rax, rax
0x1800550bf  jz      short loc_1800550D2
0x1800550c1  call    UnBCL_____StringLiteral_6__0
0x1800550c6  mov     rdx, rax; struct UnBCL::String *
0x1800550c9  mov     rcx, rbx; this
0x1800550cc  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x1800550d1  nop
0x1800550d2  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::SerializationStream"...
0x1800550d9  mov     rcx, rax
0x1800550dc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800550e1  mov     [rsp+58h+pExceptionObject], rax
0x1800550e6  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x1800550ed  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800550f2  call    _CxxThrowException_0
0x1800550f8  mov     ecx, 38h ; '8'; unsigned __int64
0x1800550fd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055102  mov     [rsp+58h+arg_18], rax
0x180055107  test    rax, rax
0x18005510a  jz      short loc_18005511C
0x18005510c  lea     rdx, aReadbytesOnClo; "ReadBytes() on closed SerializationStre"...
0x180055113  mov     rcx, rax; this
0x180055116  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18005511b  nop
0x18005511c  lea     rdx, aVoidCdeclUnbcl_13; "void __cdecl UnBCL::SerializationStream"...
0x180055123  mov     rcx, rax
0x180055126  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18005512b  mov     [rsp+58h+pExceptionObject], rax
0x180055130  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x180055137  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18005513c  call    _CxxThrowException_0
```
