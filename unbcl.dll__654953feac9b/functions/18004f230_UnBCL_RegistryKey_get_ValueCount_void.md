# UnBCL::RegistryKey::get_ValueCount(void)

- ea: `0x18004f230`
- end: `0x18004f362`
- name: `?get_ValueCount@RegistryKey@UnBCL@@QEBAHXZ`
- size: `306`
- prototype: `__int64 __fastcall(UnBCL::RegistryKey *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004f230`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18004f2a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004f2a1`

## string_xrefs

- `0x18004f326`: `method called on closed RegistryKey`
- `0x18004f2e3`: `int __cdecl UnBCL::RegistryKey::get_ValueCount(void) const`
- `0x18004f336`: `int __cdecl UnBCL::RegistryKey::get_ValueCount(void) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::RegistryKey::get_ValueCount(UnBCL::RegistryKey *this)
{
  LSTATUS v1; // ebx
  UnBCL::Win32Exception *v3; // rax
  UnBCL::ObjectDisposedException *v4; // rax
  DWORD v5; // [rsp+80h] [rbp+8h] BYREF
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
                         "int __cdecl UnBCL::RegistryKey::get_ValueCount(void) const");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  v5 = 0;
  v1 = RegQueryInfoKeyW(**((HKEY **)this + 2), 0, 0, 0, 0, 0, 0, &v5, 0, 0, 0, 0);
  if ( v1 )
  {
    v3 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v7 = v3;
    if ( v3 )
      v3 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v3, v1, L"unable to retrieve value count");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v3,
                         "int __cdecl UnBCL::RegistryKey::get_ValueCount(void) const");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  return v5;
}

```

## disassembly

```asm
0x18004f230  mov     r11, rsp
0x18004f233  push    rbx
0x18004f234  sub     rsp, 70h
0x18004f238  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x18004f240  cmp     dword ptr [rcx+8], 0
0x18004f244  jnz     loc_18004F30F
0x18004f24a  mov     dword ptr [r11+8], 0
0x18004f252  mov     rcx, [rcx+10h]
0x18004f256  mov     qword ptr [r11-20h], 0
0x18004f25e  mov     qword ptr [r11-28h], 0
0x18004f266  mov     qword ptr [r11-30h], 0
0x18004f26e  mov     qword ptr [r11-38h], 0
0x18004f276  lea     rax, [r11+8]
0x18004f27a  mov     [r11-40h], rax
0x18004f27e  mov     qword ptr [r11-48h], 0
0x18004f286  mov     qword ptr [r11-50h], 0
0x18004f28e  mov     qword ptr [r11-58h], 0
0x18004f296  xor     r9d, r9d; lpReserved
0x18004f299  xor     r8d, r8d; lpcchClass
0x18004f29c  xor     edx, edx; lpClass
0x18004f29e  mov     rcx, [rcx]; hKey
0x18004f2a1  call    cs:__imp_RegQueryInfoKeyW
0x18004f2a7  mov     ebx, eax
0x18004f2a9  test    eax, eax
0x18004f2ab  jnz     short loc_18004F2BA
0x18004f2ad  mov     eax, [rsp+78h+arg_0]
0x18004f2b4  add     rsp, 70h
0x18004f2b8  pop     rbx
0x18004f2b9  retn
0x18004f2ba  mov     ecx, 40h ; '@'; unsigned __int64
0x18004f2bf  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f2c4  mov     [rsp+78h+arg_10], rax
0x18004f2cc  test    rax, rax
0x18004f2cf  jz      short loc_18004F2E3
0x18004f2d1  lea     r8, aUnableToRetrie_0; "unable to retrieve value count"
0x18004f2d8  mov     edx, ebx; dwMessageId
0x18004f2da  mov     rcx, rax; this
0x18004f2dd  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004f2e2  nop
0x18004f2e3  lea     rdx, aIntCdeclUnbclR_0; "int __cdecl UnBCL::RegistryKey::get_Val"...
0x18004f2ea  mov     rcx, rax
0x18004f2ed  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f2f2  mov     [rsp+78h+pExceptionObject], rax
0x18004f2fa  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004f301  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004f309  call    _CxxThrowException_0
0x18004f30f  mov     ecx, 38h ; '8'; unsigned __int64
0x18004f314  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f319  mov     [rsp+78h+arg_10], rax
0x18004f321  test    rax, rax
0x18004f324  jz      short loc_18004F336
0x18004f326  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004f32d  mov     rcx, rax; this
0x18004f330  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004f335  nop
0x18004f336  lea     rdx, aIntCdeclUnbclR_0; "int __cdecl UnBCL::RegistryKey::get_Val"...
0x18004f33d  mov     rcx, rax
0x18004f340  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f345  mov     [rsp+78h+pExceptionObject], rax
0x18004f34d  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004f354  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004f35c  call    _CxxThrowException_0
```
