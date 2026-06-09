# UnBCL::RegistryKey::SetValue(UnBCL::String const *,int)

- ea: `0x18004eaa0`
- end: `0x18004ebdf`
- name: `?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@H@Z`
- size: `319`
- prototype: `void __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004eaa0`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004eae8`
- `ADVAPI32!RegSetValueExW` at `0x18004eae8`

## string_xrefs

- `0x18004eb5a`: `method called on closed RegistryKey`
- `0x18004eb20`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)`
- `0x18004eb6a`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)`
- `0x18004ebb9`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)`
- `0x18004eba4`: `attempt to set value on key opened read-only`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::RegistryKey::SetValue(UnBCL::RegistryKey *this, LPCWSTR *a2, int a3)
{
  LSTATUS v3; // ebx
  UnBCL::Win32Exception *v4; // rax
  UnBCL::ObjectDisposedException *v5; // rax
  UnBCL::Win32Exception *v6; // rax
  __int64 pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF
  UnBCL::ObjectDisposedException *v9; // [rsp+68h] [rbp+20h]

  v8 = a3;
  if ( *((_DWORD *)this + 2) )
  {
    v5 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v9 = v5;
    if ( v5 )
      v5 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v5,
                                               L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v6 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v9 = v6;
    if ( v6 )
      v6 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                      v6,
                                      5u,
                                      L"attempt to set value on key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v3 = RegSetValueExW(**((HKEY **)this + 2), a2[2], 0, 4u, (const BYTE *)&v8, 4u);
  if ( v3 )
  {
    v4 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v9 = v4;
    if ( v4 )
      v4 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v4, v3, L"unable to set value on key");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v4,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18004eaa0  mov     r11, rsp
0x18004eaa3  mov     [r11+18h], r8d
0x18004eaa7  push    rbx
0x18004eaa8  sub     rsp, 40h
0x18004eaac  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x18004eab4  cmp     dword ptr [rcx+8], 0
0x18004eab8  jnz     loc_18004EB46
0x18004eabe  cmp     dword ptr [rcx+0Ch], 0
0x18004eac2  jz      loc_18004EB90
0x18004eac8  mov     rcx, [rcx+10h]
0x18004eacc  mov     r9d, 4; dwType
0x18004ead2  mov     [r11-20h], r9d
0x18004ead6  lea     rax, [r11+18h]
0x18004eada  mov     [r11-28h], rax
0x18004eade  xor     r8d, r8d; Reserved
0x18004eae1  mov     rdx, [rdx+10h]; lpValueName
0x18004eae5  mov     rcx, [rcx]; hKey
0x18004eae8  call    cs:__imp_RegSetValueExW
0x18004eaee  mov     ebx, eax
0x18004eaf0  test    eax, eax
0x18004eaf2  jnz     short loc_18004EAFA
0x18004eaf4  add     rsp, 40h
0x18004eaf8  pop     rbx
0x18004eaf9  retn
0x18004eafa  mov     ecx, 40h ; '@'; unsigned __int64
0x18004eaff  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004eb04  mov     [rsp+48h+arg_18], rax
0x18004eb09  test    rax, rax
0x18004eb0c  jz      short loc_18004EB20
0x18004eb0e  lea     r8, aUnableToSetVal; "unable to set value on key"
0x18004eb15  mov     edx, ebx; dwMessageId
0x18004eb17  mov     rcx, rax; this
0x18004eb1a  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004eb1f  nop
0x18004eb20  lea     rdx, aVoidCdeclUnbcl_103; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004eb27  mov     rcx, rax
0x18004eb2a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004eb2f  mov     [rsp+48h+pExceptionObject], rax
0x18004eb34  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004eb3b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004eb40  call    _CxxThrowException_0
0x18004eb46  mov     ecx, 38h ; '8'; unsigned __int64
0x18004eb4b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004eb50  mov     [rsp+48h+arg_18], rax
0x18004eb55  test    rax, rax
0x18004eb58  jz      short loc_18004EB6A
0x18004eb5a  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004eb61  mov     rcx, rax; this
0x18004eb64  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004eb69  nop
0x18004eb6a  lea     rdx, aVoidCdeclUnbcl_103; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004eb71  mov     rcx, rax
0x18004eb74  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004eb79  mov     [rsp+48h+pExceptionObject], rax
0x18004eb7e  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004eb85  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004eb8a  call    _CxxThrowException_0
0x18004eb90  mov     ecx, 40h ; '@'; unsigned __int64
0x18004eb95  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004eb9a  mov     [rsp+48h+arg_18], rax
0x18004eb9f  test    rax, rax
0x18004eba2  jz      short loc_18004EBB9
0x18004eba4  lea     r8, aAttemptToSetVa; "attempt to set value on key opened read"...
0x18004ebab  mov     edx, 5; dwMessageId
0x18004ebb0  mov     rcx, rax; this
0x18004ebb3  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004ebb8  nop
0x18004ebb9  lea     rdx, aVoidCdeclUnbcl_103; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ebc0  mov     rcx, rax
0x18004ebc3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ebc8  mov     [rsp+48h+pExceptionObject], rax
0x18004ebcd  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004ebd4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004ebd9  call    _CxxThrowException_0
```
