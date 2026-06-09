# UnBCL::RegistryKey::DeleteSubKey(UnBCL::String const *,int)

- ea: `0x18004d000`
- end: `0x18004d2b2`
- name: `?DeleteSubKey@RegistryKey@UnBCL@@QEAAXPEBVString@2@H@Z`
- size: `690`
- prototype: `void __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x18004cfe0`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800360e0`
- `0x18003f520`
- `0x1800477d0`
- `0x180047d60`
- `0x18004c978`
- `0x18004cbf0`
- `0x18004cf14`
- `0x18004d000`
- `0x18004d760`
- `0x18004e670`
- `0x18004f0f0`
- `0x180060150`
- `0x1800641a0`

## string_xrefs

- `0x18004d1a4`: `method called on closed RegistryKey`
- `0x18004d237`: `null keyname to RegistryKey#DeleteSubKey`
- `0x18004d126`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d16d`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d1b4`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d200`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d247`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d28e`: `void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)`
- `0x18004d15d`: `attempt to delete nonexistent subkey`
- `0x18004d1eb`: `attempt to delete subkey of key opened read-only`
- `0x18004d114`: `unable to delete subkey`
- `0x18004d27e`: `attempt to delete subkey with subkeys`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall UnBCL::RegistryKey::DeleteSubKey(UnBCL::RegistryKey *this, const struct UnBCL::String *a2, int a3)
{
  struct UnBCL::String *v5; // rax
  struct UnBCL::RegistryKey *v6; // rax
  DWORD v7; // ebx
  UnBCL::Win32Exception *v8; // rax
  UnBCL::ArgumentException *v9; // rax
  UnBCL::ObjectDisposedException *v10; // rax
  UnBCL::Win32Exception *v11; // rax
  UnBCL::ArgumentNullException *v12; // rax
  UnBCL::InvalidOperationException *v13; // rax
  void **v14; // [rsp+28h] [rbp-38h] BYREF
  UnBCL::RegistryKey *v15; // [rsp+30h] [rbp-30h]
  _BYTE v16[8]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h]
  struct UnBCL::String *v18[3]; // [rsp+48h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+70h] [rbp+10h] BYREF
  UnBCL::ObjectDisposedException *v20; // [rsp+88h] [rbp+28h]

  if ( *((_DWORD *)this + 2) )
  {
    v10 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v20 = v10;
    if ( v10 )
      v10 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v10,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v11 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v20 = v11;
    if ( v11 )
      v11 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                       v11,
                                       5u,
                                       L"attempt to delete subkey of key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v12 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v20 = v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v12,
                                              L"null keyname to RegistryKey#DeleteSubKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v5 = UnBCL::RegistryKey::FixupName(this, a2);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v16, v5);
  v6 = UnBCL::RegistryKey::OpenSubKey(this, *(struct UnBCL::String **)((char *)v18 + *(int *)(v17 + 4)), 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v14, v6);
  if ( v15 )
  {
    if ( (int)UnBCL::RegistryKey::get_SubKeyCount(v15) > 0 )
    {
      v13 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v20 = v13;
      if ( v13 )
        v13 = (UnBCL::InvalidOperationException *)UnBCL::InvalidOperationException::InvalidOperationException(
                                                    v13,
                                                    L"attempt to delete subkey with subkeys");
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v13,
                           "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
      throw (UnBCL::InvalidOperationException **)&pExceptionObject;
    }
    UnBCL::RegistryKey::Close(v15);
    v7 = ATL::CRegKey::DeleteSubKey(
           *((ATL::CRegKey **)this + 2),
           (*(const unsigned __int16 ***)((char *)v18 + *(int *)(v17 + 4)))[2]);
    if ( v7 )
    {
      v8 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v20 = v8;
      if ( v8 )
        v8 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v8, v7, L"unable to delete subkey");
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v8,
                           "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
  }
  else if ( a3 )
  {
    v9 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v20 = v9;
    if ( v9 )
      v9 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                         v9,
                                         L"attempt to delete nonexistent subkey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v14 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(&v14);
  v18[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v18);
}

```

## disassembly

```asm
0x18004d000  mov     rax, rsp
0x18004d003  push    rbp
0x18004d004  mov     rbp, rsp
0x18004d007  sub     rsp, 60h
0x18004d00b  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18004d013  mov     [rax+10h], rbx
0x18004d017  mov     [rax+18h], rsi
0x18004d01b  mov     esi, r8d
0x18004d01e  mov     rbx, rcx
0x18004d021  cmp     dword ptr [rcx+8], 0
0x18004d025  jnz     loc_18004D191
0x18004d02b  cmp     dword ptr [rcx+0Ch], 0
0x18004d02f  jz      loc_18004D1D8
0x18004d035  test    rdx, rdx
0x18004d038  jz      loc_18004D224
0x18004d03e  call    ?FixupName@RegistryKey@UnBCL@@AEAAPEAVString@2@AEBV32@@Z; UnBCL::RegistryKey::FixupName(UnBCL::String const &)
0x18004d043  mov     rdx, rax; struct UnBCL::String *
0x18004d046  mov     r8d, 1
0x18004d04c  lea     rcx, [rbp+var_28]; this
0x18004d050  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18004d055  nop
0x18004d056  mov     rax, [rbp+var_20]
0x18004d05a  movsxd  rdx, dword ptr [rax+4]
0x18004d05e  xor     r8d, r8d; int
0x18004d061  mov     rdx, [rbp+rdx+var_18]; struct UnBCL::String *
0x18004d066  mov     rcx, rbx; this
0x18004d069  call    ?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18004d06e  mov     rdx, rax
0x18004d071  lea     rcx, [rbp+var_38]
0x18004d075  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18004d07a  nop
0x18004d07b  cmp     [rbp+var_30], 0
0x18004d080  jnz     short loc_18004D08C
0x18004d082  test    esi, esi
0x18004d084  jnz     loc_18004D14A
0x18004d08a  jmp     short loc_18004D0C6
0x18004d08c  mov     rcx, [rbp+var_30]; this
0x18004d090  call    ?get_SubKeyCount@RegistryKey@UnBCL@@QEBAHXZ; UnBCL::RegistryKey::get_SubKeyCount(void)
0x18004d095  test    eax, eax
0x18004d097  jg      loc_18004D26B
0x18004d09d  mov     rcx, [rbp+var_30]; this
0x18004d0a1  call    ?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x18004d0a6  mov     rax, [rbp+var_20]
0x18004d0aa  movsxd  rcx, dword ptr [rax+4]
0x18004d0ae  mov     rdx, [rbp+rcx+var_18]
0x18004d0b3  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18004d0b7  mov     rcx, [rbx+10h]; this
0x18004d0bb  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18004d0c0  mov     ebx, eax
0x18004d0c2  test    eax, eax
0x18004d0c4  jnz     short loc_18004D101
0x18004d0c6  lea     rax, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18004d0cd  mov     [rbp+var_38], rax
0x18004d0d1  lea     rcx, [rbp+var_38]
0x18004d0d5  call    ?DeAssign@?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(void)
0x18004d0da  nop
0x18004d0db  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004d0e2  mov     [rbp+var_18], rax
0x18004d0e6  lea     rcx, [rbp+var_18]
0x18004d0ea  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004d0ef  lea     r11, [rsp+60h+var_s0]
0x18004d0f4  mov     rbx, [r11+18h]
0x18004d0f8  mov     rsi, [r11+20h]
0x18004d0fc  mov     rsp, r11
0x18004d0ff  pop     rbp
0x18004d100  retn
0x18004d101  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d106  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d10b  mov     [rbp+arg_18], rax
0x18004d10f  test    rax, rax
0x18004d112  jz      short loc_18004D126
0x18004d114  lea     r8, aUnableToDelete; "unable to delete subkey"
0x18004d11b  mov     edx, ebx; dwMessageId
0x18004d11d  mov     rcx, rax; this
0x18004d120  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d125  nop
0x18004d126  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d12d  mov     rcx, rax
0x18004d130  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d135  mov     [rbp+pExceptionObject], rax
0x18004d139  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d140  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d144  call    _CxxThrowException_0
0x18004d14a  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d14f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d154  mov     [rbp+arg_18], rax
0x18004d158  test    rax, rax
0x18004d15b  jz      short loc_18004D16D
0x18004d15d  lea     rdx, aAttemptToDelet_2; "attempt to delete nonexistent subkey"
0x18004d164  mov     rcx, rax; this
0x18004d167  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18004d16c  nop
0x18004d16d  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d174  mov     rcx, rax
0x18004d177  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d17c  mov     [rbp+pExceptionObject], rax
0x18004d180  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18004d187  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d18b  call    _CxxThrowException_0
0x18004d191  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d196  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d19b  mov     [rbp+arg_18], rax
0x18004d19f  test    rax, rax
0x18004d1a2  jz      short loc_18004D1B4
0x18004d1a4  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004d1ab  mov     rcx, rax; this
0x18004d1ae  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004d1b3  nop
0x18004d1b4  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d1bb  mov     rcx, rax
0x18004d1be  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d1c3  mov     [rbp+pExceptionObject], rax
0x18004d1c7  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004d1ce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d1d2  call    _CxxThrowException_0
0x18004d1d8  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d1dd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d1e2  mov     [rbp+arg_18], rax
0x18004d1e6  test    rax, rax
0x18004d1e9  jz      short loc_18004D200
0x18004d1eb  lea     r8, aAttemptToDelet_1; "attempt to delete subkey of key opened "...
0x18004d1f2  mov     edx, 5; dwMessageId
0x18004d1f7  mov     rcx, rax; this
0x18004d1fa  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d1ff  nop
0x18004d200  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d207  mov     rcx, rax
0x18004d20a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d20f  mov     [rbp+pExceptionObject], rax
0x18004d213  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d21a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d21e  call    _CxxThrowException_0
0x18004d224  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d229  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d22e  mov     [rbp+arg_18], rax
0x18004d232  test    rax, rax
0x18004d235  jz      short loc_18004D247
0x18004d237  lea     rdx, aNullKeynameToR_1; "null keyname to RegistryKey#DeleteSubKe"...
0x18004d23e  mov     rcx, rax; this
0x18004d241  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004d246  nop
0x18004d247  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d24e  mov     rcx, rax
0x18004d251  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d256  mov     [rbp+pExceptionObject], rax
0x18004d25a  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004d261  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d265  call    _CxxThrowException_0
0x18004d26b  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d270  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d275  mov     [rbp+arg_18], rax
0x18004d279  test    rax, rax
0x18004d27c  jz      short loc_18004D28E
0x18004d27e  lea     rdx, aAttemptToDelet_3; "attempt to delete subkey with subkeys"
0x18004d285  mov     rcx, rax; this
0x18004d288  call    ??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18004d28d  nop
0x18004d28e  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d295  mov     rcx, rax
0x18004d298  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d29d  mov     [rbp+pExceptionObject], rax
0x18004d2a1  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18004d2a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d2ac  call    _CxxThrowException_0
```
