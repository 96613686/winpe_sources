# UnBCL::Thread::Join(void)

- ea: `0x1800611c0`
- end: `0x18006125d`
- name: `?Join@Thread@UnBCL@@QEAAXXZ`
- size: `157`
- prototype: `void __fastcall(UnBCL::Thread *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18000225c`
- `0x1800477d0`
- `0x180060a54`
- `0x180060a78`
- `0x180060ac0`
- `0x1800611c0`
- `0x180061390`
- `0x1800646f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800611df`
- `KERNEL32!WaitForSingleObject` at `0x1800611df`

## string_xrefs

- `0x180061250`: `base\ntsetup\unbcl\src\thread.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnBCL::Thread::Join(UnBCL::Thread *this)
{
  DWORD v2; // eax
  __int64 v3; // rcx
  UnBCL::ThreadStateException *v4; // rax
  __int64 v5; // rcx
  UnBCL::ThreadStateException *v6; // rbx
  const struct UnBCL::String *v7; // rax
  const struct UnBCL::String *v8; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  UnBCL::ThreadStateException *v10; // [rsp+48h] [rbp+10h]

  if ( !*((_DWORD *)this + 2) )
  {
    v4 = (UnBCL::ThreadStateException *)UnBCL::Object::operator new(0x38u);
    v6 = v4;
    v10 = v4;
    if ( v4 )
    {
      v7 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_1__5(v5);
      v4 = (UnBCL::ThreadStateException *)UnBCL::ThreadStateException::ThreadStateException(v6, v7);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::ThreadStateException>(v4);
    throw (UnBCL::ThreadStateException **)&pExceptionObject;
  }
  do
  {
    v2 = WaitForSingleObject(*((HANDLE *)this + 3), 0xFFFFFFFF);
    if ( v2 == -1 || v2 == 128 )
    {
      v8 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_2__4(v3);
      UnBCL::Win32Exception::ThrowLastError(v8, "base\\ntsetup\\unbcl\\src\\thread.cpp", 62);
    }
  }
  while ( v2 );
}

```

## disassembly

```asm
0x1800611c0  push    rbx
0x1800611c2  sub     rsp, 30h
0x1800611c6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800611cf  mov     rbx, rcx
0x1800611d2  cmp     dword ptr [rcx+8], 0
0x1800611d6  jz      short loc_1800611FB
0x1800611d8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800611db  mov     rcx, [rbx+18h]; hHandle
0x1800611df  call    cs:__imp_WaitForSingleObject
0x1800611e5  cmp     eax, 0FFFFFFFFh
0x1800611e8  jz      short loc_180061242
0x1800611ea  cmp     eax, 80h
0x1800611ef  jz      short loc_180061242
0x1800611f1  test    eax, eax
0x1800611f3  jnz     short loc_1800611D8
0x1800611f5  add     rsp, 30h
0x1800611f9  pop     rbx
0x1800611fa  retn
0x1800611fb  mov     ecx, 38h ; '8'; unsigned __int64
0x180061200  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180061205  mov     rbx, rax
0x180061208  mov     [rsp+38h+arg_8], rax
0x18006120d  test    rax, rax
0x180061210  jz      short loc_180061223
0x180061212  call    UnBCL_____StringLiteral_1__5
0x180061217  mov     rdx, rax; struct UnBCL::String *
0x18006121a  mov     rcx, rbx; this
0x18006121d  call    ??0ThreadStateException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ThreadStateException::ThreadStateException(UnBCL::String const *)
0x180061222  nop
0x180061223  mov     rcx, rax
0x180061226  call    ??$AddStackTraceToException@VThreadStateException@UnBCL@@@@YAPEAVThreadStateException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::ThreadStateException>(UnBCL::ThreadStateException *,char const *)
0x18006122b  mov     [rsp+38h+pExceptionObject], rax
0x180061230  lea     rdx, _TI5PEAVThreadStateException@UnBCL@@; pThrowInfo
0x180061237  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18006123c  call    _CxxThrowException_0
0x180061242  call    UnBCL_____StringLiteral_2__4
0x180061247  mov     rcx, rax; struct UnBCL::String *
0x18006124a  mov     r8d, 3Eh ; '>'; int
0x180061250  lea     rdx, aBaseNtsetupUnb; "base\\ntsetup\\unbcl\\src\\thread.cpp"
0x180061257  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
```
