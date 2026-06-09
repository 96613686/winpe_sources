# UnBCL::RegistryKey::get_SubKeyCount(void)

- ea: `0x18004f0f0`
- end: `0x18004f222`
- name: `?get_SubKeyCount@RegistryKey@UnBCL@@QEBAHXZ`
- size: `306`
- prototype: `__int64 __fastcall(UnBCL::RegistryKey *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004d000`
- `0x18004d2c0`
- `0x18004de80`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004f0f0`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18004f161`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004f161`

## string_xrefs

- `0x18004f1a3`: `int __cdecl UnBCL::RegistryKey::get_SubKeyCount(void) const`
- `0x18004f1f6`: `int __cdecl UnBCL::RegistryKey::get_SubKeyCount(void) const`
- `0x18004f1e6`: `method called on closed RegistryKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::RegistryKey::get_SubKeyCount(UnBCL::RegistryKey *this)
{
  LSTATUS v1; // ebx
  UnBCL::Win32Exception *v3; // rax
  UnBCL::ObjectDisposedException *v4; // rax
  DWORD lpcSubKeys; // [rsp+80h] [rbp+8h] BYREF
  __int64 pExceptionObject; // [rsp+88h] [rbp+10h] BYREF
  UnBCL::ObjectDisposedException *v7; // [rsp+90h] [rbp+18h]

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
                         "int __cdecl UnBCL::RegistryKey::get_SubKeyCount(void) const");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  lpcSubKeys = 0;
  v1 = RegQueryInfoKeyW(**((HKEY **)this + 2), 0, 0, 0, &lpcSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v1 )
  {
    v3 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v7 = v3;
    if ( v3 )
      v3 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v3, v1, L"unable to retrieve subkey count");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v3,
                         "int __cdecl UnBCL::RegistryKey::get_SubKeyCount(void) const");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  return lpcSubKeys;
}

```

## disassembly

```asm
0x18004f0f0  mov     rax, rsp
0x18004f0f3  push    rbx
0x18004f0f4  sub     rsp, 70h
0x18004f0f8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18004f100  cmp     dword ptr [rcx+8], 0
0x18004f104  jnz     loc_18004F1CF
0x18004f10a  mov     dword ptr [rax+8], 0
0x18004f111  mov     rcx, [rcx+10h]
0x18004f115  mov     qword ptr [rax-20h], 0
0x18004f11d  mov     qword ptr [rax-28h], 0
0x18004f125  mov     qword ptr [rax-30h], 0
0x18004f12d  mov     qword ptr [rax-38h], 0
0x18004f135  mov     qword ptr [rax-40h], 0
0x18004f13d  mov     qword ptr [rax-48h], 0
0x18004f145  mov     qword ptr [rax-50h], 0
0x18004f14d  lea     rax, [rax+8]
0x18004f151  mov     [rsp+78h+lpcSubKeys], rax; lpcSubKeys
0x18004f156  xor     r9d, r9d; lpReserved
0x18004f159  xor     r8d, r8d; lpcchClass
0x18004f15c  xor     edx, edx; lpClass
0x18004f15e  mov     rcx, [rcx]; hKey
0x18004f161  call    cs:__imp_RegQueryInfoKeyW
0x18004f167  mov     ebx, eax
0x18004f169  test    eax, eax
0x18004f16b  jnz     short loc_18004F17A
0x18004f16d  mov     eax, [rsp+78h+arg_0]
0x18004f174  add     rsp, 70h
0x18004f178  pop     rbx
0x18004f179  retn
0x18004f17a  mov     ecx, 40h ; '@'; unsigned __int64
0x18004f17f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f184  mov     [rsp+78h+arg_10], rax
0x18004f18c  test    rax, rax
0x18004f18f  jz      short loc_18004F1A3
0x18004f191  lea     r8, aUnableToRetrie_3; "unable to retrieve subkey count"
0x18004f198  mov     edx, ebx; dwMessageId
0x18004f19a  mov     rcx, rax; this
0x18004f19d  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004f1a2  nop
0x18004f1a3  lea     rdx, aIntCdeclUnbclR; "int __cdecl UnBCL::RegistryKey::get_Sub"...
0x18004f1aa  mov     rcx, rax
0x18004f1ad  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f1b2  mov     [rsp+78h+pExceptionObject], rax
0x18004f1ba  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004f1c1  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004f1c9  call    _CxxThrowException_0
0x18004f1cf  mov     ecx, 38h ; '8'; unsigned __int64
0x18004f1d4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f1d9  mov     [rsp+78h+arg_10], rax
0x18004f1e1  test    rax, rax
0x18004f1e4  jz      short loc_18004F1F6
0x18004f1e6  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004f1ed  mov     rcx, rax; this
0x18004f1f0  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004f1f5  nop
0x18004f1f6  lea     rdx, aIntCdeclUnbclR; "int __cdecl UnBCL::RegistryKey::get_Sub"...
0x18004f1fd  mov     rcx, rax
0x18004f200  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f205  mov     [rsp+78h+pExceptionObject], rax
0x18004f20d  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004f214  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004f21c  call    _CxxThrowException_0
```
