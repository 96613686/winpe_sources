# UnBCL::RegistryKey::GetValueKind(UnBCL::String const *)

- ea: `0x18004e1e0`
- end: `0x18004e317`
- name: `?GetValueKind@RegistryKey@UnBCL@@QEAA?AW4RegistryValueKind@2@PEBVString@2@@Z`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004e1e0`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004e223`
- `ADVAPI32!RegQueryValueExW` at `0x18004e223`

## string_xrefs

- `0x18004e2e1`: `method called on closed RegistryKey`
- `0x18004e2a7`: `enum UnBCL::RegistryValueKind __cdecl UnBCL::RegistryKey::GetValueKind(const class UnBCL::String *)`
- `0x18004e2f1`: `enum UnBCL::RegistryValueKind __cdecl UnBCL::RegistryKey::GetValueKind(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::RegistryKey::GetValueKind(__int64 a1, __int64 a2)
{
  LSTATUS v2; // ebx
  UnBCL::Win32Exception *v4; // rax
  UnBCL::ObjectDisposedException *v5; // rax
  DWORD v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 pExceptionObject; // [rsp+60h] [rbp+18h] BYREF
  UnBCL::ObjectDisposedException *v8; // [rsp+68h] [rbp+20h]

  if ( *(_DWORD *)(a1 + 8) )
  {
    v5 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v8 = v5;
    if ( v5 )
      v5 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                               v5,
                                               L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "enum UnBCL::RegistryValueKind __cdecl UnBCL::RegistryKey::GetValueKind(const class UnBCL::String *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  v6 = 0;
  v2 = RegQueryValueExW(**(HKEY **)(a1 + 16), *(LPCWSTR *)(a2 + 16), 0, &v6, 0, 0);
  if ( v2 )
  {
    v4 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v8 = v4;
    if ( v4 )
      v4 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v4, v2, L"unable to query value");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v4,
                         "enum UnBCL::RegistryValueKind __cdecl UnBCL::RegistryKey::GetValueKind(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  switch ( v6 )
  {
    case 1u:
      return 0;
    case 2u:
      return 1;
    case 3u:
      return 2;
    case 4u:
      return 3;
    case 7u:
      return 4;
    case 0xBu:
      return 5;
  }
  return 6;
}

```

## disassembly

```asm
0x18004e1e0  mov     rax, rsp
0x18004e1e3  push    rbx
0x18004e1e4  sub     rsp, 40h
0x18004e1e8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18004e1f0  cmp     dword ptr [rcx+8], 0
0x18004e1f4  jnz     loc_18004E2CD
0x18004e1fa  mov     dword ptr [rax+8], 0
0x18004e201  mov     rcx, [rcx+10h]
0x18004e205  mov     qword ptr [rax-20h], 0
0x18004e20d  mov     qword ptr [rax-28h], 0
0x18004e215  lea     r9, [rax+8]; lpType
0x18004e219  xor     r8d, r8d; lpReserved
0x18004e21c  mov     rdx, [rdx+10h]; lpValueName
0x18004e220  mov     rcx, [rcx]; hKey
0x18004e223  call    cs:__imp_RegQueryValueExW
0x18004e229  mov     ebx, eax
0x18004e22b  test    eax, eax
0x18004e22d  jnz     short loc_18004E281
0x18004e22f  mov     eax, [rsp+48h+arg_0]
0x18004e233  sub     eax, 1
0x18004e236  jz      short loc_18004E279
0x18004e238  sub     eax, 1
0x18004e23b  jz      short loc_18004E272
0x18004e23d  sub     eax, 1
0x18004e240  jz      short loc_18004E26B
0x18004e242  sub     eax, 1
0x18004e245  jz      short loc_18004E264
0x18004e247  sub     eax, 3
0x18004e24a  jz      short loc_18004E25D
0x18004e24c  cmp     eax, 4
0x18004e24f  jz      short loc_18004E256
0x18004e251  lea     eax, [rbx+6]
0x18004e254  jmp     short loc_18004E27B
0x18004e256  mov     eax, 5
0x18004e25b  jmp     short loc_18004E27B
0x18004e25d  mov     eax, 4
0x18004e262  jmp     short loc_18004E27B
0x18004e264  mov     eax, 3
0x18004e269  jmp     short loc_18004E27B
0x18004e26b  mov     eax, 2
0x18004e270  jmp     short loc_18004E27B
0x18004e272  mov     eax, 1
0x18004e277  jmp     short loc_18004E27B
0x18004e279  xor     eax, eax
0x18004e27b  add     rsp, 40h
0x18004e27f  pop     rbx
0x18004e280  retn
0x18004e281  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e286  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e28b  mov     [rsp+48h+arg_18], rax
0x18004e290  test    rax, rax
0x18004e293  jz      short loc_18004E2A7
0x18004e295  lea     r8, aUnableToQueryV; "unable to query value"
0x18004e29c  mov     edx, ebx; dwMessageId
0x18004e29e  mov     rcx, rax; this
0x18004e2a1  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004e2a6  nop
0x18004e2a7  lea     rdx, aEnumUnbclRegis; "enum UnBCL::RegistryValueKind __cdecl U"...
0x18004e2ae  mov     rcx, rax
0x18004e2b1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e2b6  mov     [rsp+48h+pExceptionObject], rax
0x18004e2bb  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004e2c2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004e2c7  call    _CxxThrowException_0
0x18004e2cd  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e2d2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e2d7  mov     [rsp+48h+arg_18], rax
0x18004e2dc  test    rax, rax
0x18004e2df  jz      short loc_18004E2F1
0x18004e2e1  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004e2e8  mov     rcx, rax; this
0x18004e2eb  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004e2f0  nop
0x18004e2f1  lea     rdx, aEnumUnbclRegis; "enum UnBCL::RegistryValueKind __cdecl U"...
0x18004e2f8  mov     rcx, rax
0x18004e2fb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e300  mov     [rsp+48h+pExceptionObject], rax
0x18004e305  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004e30c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004e311  call    _CxxThrowException_0
```
