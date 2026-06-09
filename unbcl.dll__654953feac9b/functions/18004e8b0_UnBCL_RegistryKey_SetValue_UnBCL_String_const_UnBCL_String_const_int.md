# UnBCL::RegistryKey::SetValue(UnBCL::String const *,UnBCL::String const *,int)

- ea: `0x18004e8b0`
- end: `0x18004ea98`
- name: `?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@0H@Z`
- size: `488`
- prototype: `void __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *, const struct UnBCL::String *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004e8b0`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004e93a`
- `ADVAPI32!RegSetValueExW` at `0x18004e93a`

## string_xrefs

- `0x18004e978`: `method called on closed RegistryKey`
- `0x18004e9c3`: `attempt to set value on key opened read-only`
- `0x18004ea13`: `null value to RegistryKey#SetValue`
- `0x18004e98c`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18004e9dc`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18004ea27`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)`
- `0x18004ea74`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UnBCL::RegistryKey::SetValue(
        UnBCL::RegistryKey *this,
        const struct UnBCL::String *a2,
        const struct UnBCL::String *a3,
        int a4)
{
  const BYTE *lpData; // r8
  HKEY *v5; // rcx
  const WCHAR *v6; // rdx
  __int64 v7; // rax
  DWORD v8; // r9d
  LSTATUS v9; // ebx
  UnBCL::ObjectDisposedException *v10; // rax
  __int64 v11; // rax
  UnBCL::Win32Exception *v12; // rax
  __int64 v13; // rax
  UnBCL::ArgumentNullException *v14; // rax
  __int64 v15; // rax
  UnBCL::Win32Exception *v16; // rax
  __int64 v17; // rax
  __int64 pExceptionObject; // [rsp+50h] [rbp+10h] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    v10 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v10 )
      v11 = UnBCL::ObjectDisposedException::ObjectDisposedException(v10, L"method called on closed RegistryKey");
    else
      v11 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    if ( v12 )
      v13 = UnBCL::Win32Exception::Win32Exception(v12, 5u, L"attempt to set value on key opened read-only");
    else
      v13 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a3 )
  {
    v14 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v14 )
      v15 = UnBCL::ArgumentNullException::ArgumentNullException(v14, L"null value to RegistryKey#SetValue");
    else
      v15 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  lpData = (const BYTE *)*((_QWORD *)a3 + 2);
  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v5 = (HKEY *)*((_QWORD *)this + 2);
  v6 = (const WCHAR *)*((_QWORD *)a2 + 2);
  v7 = -1;
  if ( a4 )
  {
    do
      ++v7;
    while ( *(_WORD *)&lpData[2 * v7] );
    v8 = 2;
  }
  else
  {
    do
      ++v7;
    while ( *(_WORD *)&lpData[2 * v7] );
    v8 = 1;
  }
  v9 = RegSetValueExW(*v5, v6, 0, v8, lpData, 2 * v7 + 2);
  if ( v9 )
  {
    v16 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    if ( v16 )
      v17 = UnBCL::Win32Exception::Win32Exception(v16, v9, L"unable to set value on key");
    else
      v17 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18004e8b0  push    rbp
0x18004e8b2  mov     rbp, rsp
0x18004e8b5  sub     rsp, 40h
0x18004e8b9  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18004e8c1  mov     [rsp+40h+arg_8], rbx
0x18004e8c6  mov     [rsp+40h+arg_10], rdi
0x18004e8cb  xor     edi, edi
0x18004e8cd  cmp     [rcx+8], edi
0x18004e8d0  jnz     loc_18004E965
0x18004e8d6  cmp     [rcx+0Ch], edi
0x18004e8d9  jz      loc_18004E9B0
0x18004e8df  test    r8, r8
0x18004e8e2  jz      loc_18004EA00
0x18004e8e8  mov     r8, [r8+10h]
0x18004e8ec  test    r8, r8
0x18004e8ef  jz      short loc_18004E95A
0x18004e8f1  mov     rcx, [rcx+10h]
0x18004e8f5  mov     rdx, [rdx+10h]; lpValueName
0x18004e8f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e8fd  test    r9d, r9d
0x18004e900  jnz     short loc_18004E914
0x18004e902  inc     rax
0x18004e905  cmp     [r8+rax*2], di
0x18004e90a  jnz     short loc_18004E902
0x18004e90c  mov     r9d, 1
0x18004e912  jmp     short loc_18004E924
0x18004e914  inc     rax
0x18004e917  cmp     [r8+rax*2], di
0x18004e91c  jnz     short loc_18004E914
0x18004e91e  mov     r9d, 2; dwType
0x18004e924  lea     eax, ds:2[rax*2]
0x18004e92b  mov     [rsp+40h+cbData], eax; cbData
0x18004e92f  mov     [rsp+40h+lpData], r8; lpData
0x18004e934  xor     r8d, r8d; Reserved
0x18004e937  mov     rcx, [rcx]; hKey
0x18004e93a  call    cs:__imp_RegSetValueExW
0x18004e940  mov     ebx, eax
0x18004e942  test    eax, eax
0x18004e944  jnz     loc_18004EA4B
0x18004e94a  mov     rbx, [rsp+40h+arg_8]
0x18004e94f  mov     rdi, [rsp+40h+arg_10]
0x18004e954  add     rsp, 40h
0x18004e958  pop     rbp
0x18004e959  retn
0x18004e95a  mov     ecx, 80004005h; int
0x18004e95f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004e965  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e96a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e96f  mov     [rbp+var_8], rax
0x18004e973  test    rax, rax
0x18004e976  jz      short loc_18004E989
0x18004e978  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004e97f  mov     rcx, rax; this
0x18004e982  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004e987  jmp     short loc_18004E98C
0x18004e989  mov     rax, rdi
0x18004e98c  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004e993  mov     rcx, rax
0x18004e996  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e99b  mov     [rbp+pExceptionObject], rax
0x18004e99f  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004e9a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e9aa  call    _CxxThrowException_0
0x18004e9b0  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e9b5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e9ba  mov     [rbp+var_8], rax
0x18004e9be  test    rax, rax
0x18004e9c1  jz      short loc_18004E9D9
0x18004e9c3  lea     r8, aAttemptToSetVa; "attempt to set value on key opened read"...
0x18004e9ca  mov     edx, 5; dwMessageId
0x18004e9cf  mov     rcx, rax; this
0x18004e9d2  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004e9d7  jmp     short loc_18004E9DC
0x18004e9d9  mov     rax, rdi
0x18004e9dc  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004e9e3  mov     rcx, rax
0x18004e9e6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e9eb  mov     [rbp+pExceptionObject], rax
0x18004e9ef  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004e9f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e9fa  call    _CxxThrowException_0
0x18004ea00  mov     ecx, 38h ; '8'; unsigned __int64
0x18004ea05  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ea0a  mov     [rbp+var_8], rax
0x18004ea0e  test    rax, rax
0x18004ea11  jz      short loc_18004EA24
0x18004ea13  lea     rdx, aNullValueToReg; "null value to RegistryKey#SetValue"
0x18004ea1a  mov     rcx, rax; this
0x18004ea1d  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004ea22  jmp     short loc_18004EA27
0x18004ea24  mov     rax, rdi
0x18004ea27  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ea2e  mov     rcx, rax
0x18004ea31  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ea36  mov     [rbp+pExceptionObject], rax
0x18004ea3a  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004ea41  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004ea45  call    _CxxThrowException_0
0x18004ea4b  mov     ecx, 40h ; '@'; unsigned __int64
0x18004ea50  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ea55  mov     [rbp+var_8], rax
0x18004ea59  test    rax, rax
0x18004ea5c  jz      short loc_18004EA71
0x18004ea5e  lea     r8, aUnableToSetVal; "unable to set value on key"
0x18004ea65  mov     edx, ebx; dwMessageId
0x18004ea67  mov     rcx, rax; this
0x18004ea6a  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004ea6f  jmp     short loc_18004EA74
0x18004ea71  mov     rax, rdi
0x18004ea74  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ea7b  mov     rcx, rax
0x18004ea7e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ea83  mov     [rbp+pExceptionObject], rax
0x18004ea87  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004ea8e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004ea92  call    _CxxThrowException_0
```
