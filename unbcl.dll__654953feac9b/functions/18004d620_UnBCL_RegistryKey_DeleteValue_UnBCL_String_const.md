# UnBCL::RegistryKey::DeleteValue(UnBCL::String const *)

- ea: `0x18004d620`
- end: `0x18004d741`
- name: `?DeleteValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z`
- size: `289`
- prototype: `void __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004d620`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18004d64a`
- `ADVAPI32!RegDeleteValueW` at `0x18004d64a`

## string_xrefs

- `0x18004d6bc`: `method called on closed RegistryKey`
- `0x18004d706`: `attempt to delete value of key opened read-only`
- `0x18004d682`: `void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)`
- `0x18004d6cc`: `void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)`
- `0x18004d71b`: `void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::RegistryKey::DeleteValue(UnBCL::RegistryKey *this, LPCWSTR *a2)
{
  LSTATUS v2; // ebx
  UnBCL::Win32Exception *v3; // rax
  UnBCL::ObjectDisposedException *v4; // rax
  UnBCL::Win32Exception *v5; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  UnBCL::ObjectDisposedException *v7; // [rsp+50h] [rbp+18h]

  if ( *((_DWORD *)this + 2) )
  {
    v4 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v7 = v4;
    if ( v4 )
      v4 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v4,
                                               L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v4,
                         "void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v5 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v7 = v5;
    if ( v5 )
      v5 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                      v5,
                                      5u,
                                      L"attempt to delete value of key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v2 = RegDeleteValueW(**((HKEY **)this + 2), a2[2]);
  if ( v2 )
  {
    v3 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v7 = v3;
    if ( v3 )
      v3 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v3, v2, L"unable to set value on key");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v3,
                         "void __cdecl UnBCL::RegistryKey::DeleteValue(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18004d620  push    rbx
0x18004d622  sub     rsp, 30h
0x18004d626  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004d62f  cmp     dword ptr [rcx+8], 0
0x18004d633  jnz     short loc_18004D6A8
0x18004d635  cmp     dword ptr [rcx+0Ch], 0
0x18004d639  jz      loc_18004D6F2
0x18004d63f  mov     rcx, [rcx+10h]
0x18004d643  mov     rdx, [rdx+10h]; lpValueName
0x18004d647  mov     rcx, [rcx]; hKey
0x18004d64a  call    cs:__imp_RegDeleteValueW
0x18004d650  mov     ebx, eax
0x18004d652  test    eax, eax
0x18004d654  jnz     short loc_18004D65C
0x18004d656  add     rsp, 30h
0x18004d65a  pop     rbx
0x18004d65b  retn
0x18004d65c  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d661  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d666  mov     [rsp+38h+arg_10], rax
0x18004d66b  test    rax, rax
0x18004d66e  jz      short loc_18004D682
0x18004d670  lea     r8, aUnableToSetVal; "unable to set value on key"
0x18004d677  mov     edx, ebx; dwMessageId
0x18004d679  mov     rcx, rax; this
0x18004d67c  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d681  nop
0x18004d682  lea     rdx, aVoidCdeclUnbcl_161; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d689  mov     rcx, rax
0x18004d68c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d691  mov     [rsp+38h+pExceptionObject], rax
0x18004d696  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d69d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18004d6a2  call    _CxxThrowException_0
0x18004d6a8  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d6ad  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d6b2  mov     [rsp+38h+arg_10], rax
0x18004d6b7  test    rax, rax
0x18004d6ba  jz      short loc_18004D6CC
0x18004d6bc  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004d6c3  mov     rcx, rax; this
0x18004d6c6  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004d6cb  nop
0x18004d6cc  lea     rdx, aVoidCdeclUnbcl_161; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d6d3  mov     rcx, rax
0x18004d6d6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d6db  mov     [rsp+38h+pExceptionObject], rax
0x18004d6e0  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004d6e7  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18004d6ec  call    _CxxThrowException_0
0x18004d6f2  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d6f7  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d6fc  mov     [rsp+38h+arg_10], rax
0x18004d701  test    rax, rax
0x18004d704  jz      short loc_18004D71B
0x18004d706  lea     r8, aAttemptToDelet_4; "attempt to delete value of key opened r"...
0x18004d70d  mov     edx, 5; dwMessageId
0x18004d712  mov     rcx, rax; this
0x18004d715  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d71a  nop
0x18004d71b  lea     rdx, aVoidCdeclUnbcl_161; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d722  mov     rcx, rax
0x18004d725  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d72a  mov     [rsp+38h+pExceptionObject], rax
0x18004d72f  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d736  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18004d73b  call    _CxxThrowException_0
```
