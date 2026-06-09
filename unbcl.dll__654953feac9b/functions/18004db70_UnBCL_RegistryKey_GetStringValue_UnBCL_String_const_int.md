# UnBCL::RegistryKey::GetStringValue(UnBCL::String const *,int)

- ea: `0x18004db70`
- end: `0x18004de77`
- name: `?GetStringValue@RegistryKey@UnBCL@@QEAAPEAVString@2@PEBV32@H@Z`
- size: `775`
- prototype: `struct UnBCL::String *__fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x18000afd0`
- `0x180011570`
- `0x180011940`
- `0x1800362b0`
- `0x1800477d0`
- `0x180047d60`
- `0x18004db70`
- `0x18005b790`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004dbd9`
- `ADVAPI32!RegQueryValueExW` at `0x18004dc65`
- `ADVAPI32!RegQueryValueExW` at `0x18004dbd9`
- `ADVAPI32!RegQueryValueExW` at `0x18004dc65`

## string_xrefs

- `0x18004ddf2`: `method called on closed RegistryKey`
- `0x18004ddbb`: `class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)`
- `0x18004de06`: `class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)`
- `0x18004de53`: `class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct UnBCL::String *__fastcall UnBCL::RegistryKey::GetStringValue(UnBCL::RegistryKey *this, LPCWSTR *a2, int a3)
{
  LSTATUS Value; // ebx
  __int64 (__fastcall ***v7)(_QWORD); // rcx
  int v8; // ebx
  HKEY *v9; // rdi
  BYTE *lpData; // rsi
  LSTATUS v11; // ebx
  UnBCL::Win32Exception *v12; // rax
  __int64 v13; // rax
  UnBCL::String *v14; // rbx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  struct UnBCL::String *v17; // rax
  struct UnBCL::String *v18; // rbx
  UnBCL::ObjectDisposedException *v20; // rax
  __int64 v21; // rax
  UnBCL::Win32Exception *v22; // rax
  __int64 v23; // rax
  DWORD Type[2]; // [rsp+38h] [rbp-D0h] BYREF
  void **v25; // [rsp+40h] [rbp-C8h] BYREF
  struct UnBCL::String *v26; // [rsp+48h] [rbp-C0h]
  _QWORD v27[3]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v28[16]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp-90h]
  void **v30; // [rsp+88h] [rbp-80h] BYREF
  __int64 pExceptionObject; // [rsp+148h] [rbp+40h] BYREF
  UnBCL::ObjectDisposedException *cbData; // [rsp+160h] [rbp+58h] BYREF

  v27[2] = -2;
  if ( *((_DWORD *)this + 2) )
  {
    v20 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    cbData = v20;
    if ( v20 )
      v21 = UnBCL::ObjectDisposedException::ObjectDisposedException(v20, L"method called on closed RegistryKey");
    else
      v21 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v21,
                         "class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  Type[1] = 0;
  Type[0] = 0;
  Value = RegQueryValueExW(**((HKEY **)this + 2), a2[2], 0, &Type[1], 0, Type);
  if ( Value )
  {
    v22 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    cbData = v22;
    if ( v22 )
      v23 = UnBCL::Win32Exception::Win32Exception(v22, Value, L"unable to query value");
    else
      v23 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v23,
                         "class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  UnBCL::Array<unsigned short>::Array<unsigned short>(v28, (Type[0] >> 1) + 1, 0, 1);
  v7 = (__int64 (__fastcall ***)(_QWORD))((char *)v29 + *(int *)(v29[1] + 12LL) + 8);
  v8 = (**v7)(v7);
  v9 = (HKEY *)*((_QWORD *)this + 2);
  lpData = (BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v29 + 112LL))(v29, 0);
  LODWORD(pExceptionObject) = 0;
  LODWORD(cbData) = 2 * v8;
  v11 = RegQueryValueExW(*v9, a2[2], 0, (LPDWORD)&pExceptionObject, lpData, (LPDWORD)&cbData);
  if ( v11 )
  {
LABEL_10:
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    cbData = v12;
    if ( v12 )
      v13 = UnBCL::Win32Exception::Win32Exception(v12, v11, L"unable to get String value on key");
    else
      v13 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "class UnBCL::String *__cdecl UnBCL::RegistryKey::GetStringValue(const class UnBCL::String *,int)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( (unsigned int)(pExceptionObject - 1) > 1 )
  {
LABEL_9:
    v11 = 13;
    goto LABEL_10;
  }
  if ( lpData )
  {
    if ( (_DWORD)cbData )
    {
      if ( ((unsigned __int8)cbData & 1) != 0
        || *(_WORD *)&lpData[2 * ((unsigned __int64)(unsigned int)cbData >> 1) - 2] )
      {
        goto LABEL_9;
      }
    }
    else
    {
      *(_WORD *)lpData = 0;
    }
  }
  v14 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  pExceptionObject = (__int64)v14;
  if ( v14 )
  {
    v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v29 + 112LL))(v29, 0);
    v16 = UnBCL::String::String(v14, v15);
  }
  else
  {
    v16 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v25, v16);
  if ( a3 && Type[1] == 2 )
  {
    v17 = UnBCL::Environment::ExpandEnvironmentVariables(v26);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v27, v17);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v25, v27[1]);
    v27[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v27);
  }
  v18 = v26;
  if ( v26 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v26 + 2);
    v26 = 0;
  }
  else
  {
    v18 = 0;
  }
  v25 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v25);
  UnBCL::Array<unsigned short>::~Array<unsigned short>(&v30);
  v30 = &UnBCL::Object::`vftable';
  return v18;
}

```

## disassembly

```asm
0x18004db70  mov     rax, rsp
0x18004db73  push    rbp
0x18004db74  push    rdi
0x18004db75  push    r12
0x18004db77  push    r14
0x18004db79  push    r15
0x18004db7b  lea     rbp, [rax-38h]
0x18004db7f  sub     rsp, 110h
0x18004db86  mov     qword ptr [rsp+130h+var_D8], 0FFFFFFFFFFFFFFFEh
0x18004db8f  mov     [rax+10h], rbx
0x18004db93  mov     [rax+18h], rsi
0x18004db97  mov     r15d, r8d
0x18004db9a  mov     r14, rdx
0x18004db9d  mov     rdi, rcx
0x18004dba0  xor     r12d, r12d
0x18004dba3  cmp     [rcx+8], r12d
0x18004dba7  jnz     loc_18004DDDF
0x18004dbad  mov     [rsp+130h+Type+4], r12d
0x18004dbb2  mov     [rsp+130h+Type], r12d
0x18004dbb7  mov     rcx, [rcx+10h]
0x18004dbbb  lea     rax, [rsp+130h+Type]
0x18004dbc0  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18004dbc5  mov     [rsp+130h+lpData], r12; lpData
0x18004dbca  lea     r9, [rsp+130h+Type+4]; lpType
0x18004dbcf  xor     r8d, r8d; lpReserved
0x18004dbd2  mov     rdx, [rdx+10h]; lpValueName
0x18004dbd6  mov     rcx, [rcx]; hKey
0x18004dbd9  call    cs:__imp_RegQueryValueExW
0x18004dbdf  mov     ebx, eax
0x18004dbe1  test    eax, eax
0x18004dbe3  jnz     loc_18004DE2A
0x18004dbe9  mov     edx, [rsp+130h+Type]
0x18004dbed  shr     edx, 1
0x18004dbef  inc     edx
0x18004dbf1  lea     r9d, [r12+1]
0x18004dbf6  xor     r8d, r8d
0x18004dbf9  lea     rcx, [rsp+130h+var_D0]
0x18004dbfe  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18004dc03  nop
0x18004dc04  mov     rdx, [rsp+130h+var_C0]
0x18004dc09  mov     rax, [rdx+8]
0x18004dc0d  movsxd  rcx, dword ptr [rax+0Ch]
0x18004dc11  add     rdx, 8
0x18004dc15  add     rcx, rdx
0x18004dc18  mov     rax, [rcx]
0x18004dc1b  mov     rax, [rax]
0x18004dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc23  mov     ebx, eax
0x18004dc25  mov     rdi, [rdi+10h]
0x18004dc29  mov     rcx, [rsp+130h+var_C0]
0x18004dc2e  mov     rdx, [rcx]
0x18004dc31  mov     rax, [rdx+70h]
0x18004dc35  xor     edx, edx
0x18004dc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc3c  mov     rsi, rax
0x18004dc3f  mov     dword ptr [rbp+30h+pExceptionObject], r12d
0x18004dc43  lea     edx, [rbx+rbx]
0x18004dc46  mov     dword ptr [rbp+30h+cbData], edx
0x18004dc49  lea     rax, [rbp+30h+cbData]
0x18004dc4d  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18004dc52  mov     [rsp+130h+lpData], rsi; lpData
0x18004dc57  lea     r9, [rbp+30h+pExceptionObject]; lpType
0x18004dc5b  xor     r8d, r8d; lpReserved
0x18004dc5e  mov     rdx, [r14+10h]; lpValueName
0x18004dc62  mov     rcx, [rdi]; hKey
0x18004dc65  call    cs:__imp_RegQueryValueExW
0x18004dc6b  mov     ebx, eax
0x18004dc6d  test    eax, eax
0x18004dc6f  jnz     short loc_18004DC9B
0x18004dc71  mov     eax, dword ptr [rbp+30h+pExceptionObject]
0x18004dc74  dec     eax
0x18004dc76  cmp     eax, 1
0x18004dc79  ja      short loc_18004DC96
0x18004dc7b  test    rsi, rsi
0x18004dc7e  jz      short loc_18004DCCC
0x18004dc80  mov     eax, dword ptr [rbp+30h+cbData]
0x18004dc83  test    eax, eax
0x18004dc85  jz      short loc_18004DCC8
0x18004dc87  test    al, 1
0x18004dc89  jnz     short loc_18004DC96
0x18004dc8b  shr     rax, 1
0x18004dc8e  cmp     [rsi+rax*2-2], r12w
0x18004dc94  jz      short loc_18004DCCC
0x18004dc96  mov     ebx, 0Dh
0x18004dc9b  mov     ecx, 40h ; '@'; unsigned __int64
0x18004dca0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dca5  mov     [rbp+30h+cbData], rax
0x18004dca9  test    rax, rax
0x18004dcac  jz      loc_18004DDB8
0x18004dcb2  lea     r8, aUnableToGetStr; "unable to get String value on key"
0x18004dcb9  mov     edx, ebx; dwMessageId
0x18004dcbb  mov     rcx, rax; this
0x18004dcbe  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004dcc3  jmp     loc_18004DDBB
0x18004dcc8  mov     [rsi], r12w
0x18004dccc  mov     ecx, 18h; unsigned __int64
0x18004dcd1  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dcd6  mov     rbx, rax
0x18004dcd9  mov     [rbp+30h+pExceptionObject], rax
0x18004dcdd  test    rax, rax
0x18004dce0  jz      short loc_18004DD02
0x18004dce2  mov     rcx, [rsp+130h+var_C0]
0x18004dce7  mov     rdx, [rcx]
0x18004dcea  mov     rax, [rdx+70h]
0x18004dcee  xor     edx, edx
0x18004dcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcf5  mov     rdx, rax; unsigned __int16 *
0x18004dcf8  mov     rcx, rbx; this
0x18004dcfb  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18004dd00  jmp     short loc_18004DD05
0x18004dd02  mov     rax, r12
0x18004dd05  mov     rdx, rax
0x18004dd08  lea     rcx, [rsp+130h+var_F8]
0x18004dd0d  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18004dd12  nop
0x18004dd13  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004dd1a  test    r15d, r15d
0x18004dd1d  jz      short loc_18004DD5D
0x18004dd1f  cmp     [rsp+130h+Type+4], 2
0x18004dd24  jnz     short loc_18004DD5D
0x18004dd26  mov     rcx, [rsp+130h+var_F0]; struct UnBCL::String *
0x18004dd2b  call    ?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x18004dd30  mov     rdx, rax
0x18004dd33  lea     rcx, [rsp+130h+var_E8]
0x18004dd38  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18004dd3d  nop
0x18004dd3e  mov     rdx, [rsp+130h+var_E0]
0x18004dd43  lea     rcx, [rsp+130h+var_F8]
0x18004dd48  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18004dd4d  nop
0x18004dd4e  mov     [rsp+130h+var_E8], rdi
0x18004dd53  lea     rcx, [rsp+130h+var_E8]
0x18004dd58  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004dd5d  mov     rbx, [rsp+130h+var_F0]
0x18004dd62  test    rbx, rbx
0x18004dd65  jnz     short loc_18004DD6C
0x18004dd67  mov     rbx, r12
0x18004dd6a  jmp     short loc_18004DD75
0x18004dd6c  lock dec dword ptr [rbx+8]
0x18004dd70  mov     [rsp+130h+var_F0], r12
0x18004dd75  mov     [rsp+130h+var_F8], rdi
0x18004dd7a  lea     rcx, [rsp+130h+var_F8]
0x18004dd7f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004dd84  nop
0x18004dd85  lea     rcx, [rbp+30h+var_B0]
0x18004dd89  call    ??1?$Array@G@UnBCL@@UEAA@XZ; UnBCL::Array<ushort>::~Array<ushort>(void)
0x18004dd8e  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18004dd95  mov     [rbp+30h+var_B0], rax
0x18004dd99  mov     rax, rbx
0x18004dd9c  lea     r11, [rsp+130h+var_20]
0x18004dda4  mov     rbx, [r11+38h]
0x18004dda8  mov     rsi, [r11+40h]
0x18004ddac  mov     rsp, r11
0x18004ddaf  pop     r15
0x18004ddb1  pop     r14
0x18004ddb3  pop     r12
0x18004ddb5  pop     rdi
0x18004ddb6  pop     rbp
0x18004ddb7  retn
0x18004ddb8  mov     rax, r12
0x18004ddbb  lea     rdx, aClassUnbclStri_32; "class UnBCL::String *__cdecl UnBCL::Reg"...
0x18004ddc2  mov     rcx, rax
0x18004ddc5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ddca  mov     [rbp+30h+pExceptionObject], rax
0x18004ddce  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004ddd5  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18004ddd9  call    _CxxThrowException_0
0x18004dddf  mov     ecx, 38h ; '8'; unsigned __int64
0x18004dde4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dde9  mov     [rbp+30h+cbData], rax
0x18004dded  test    rax, rax
0x18004ddf0  jz      short loc_18004DE03
0x18004ddf2  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004ddf9  mov     rcx, rax; this
0x18004ddfc  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004de01  jmp     short loc_18004DE06
0x18004de03  mov     rax, r12
0x18004de06  lea     rdx, aClassUnbclStri_32; "class UnBCL::String *__cdecl UnBCL::Reg"...
0x18004de0d  mov     rcx, rax
0x18004de10  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004de15  mov     [rbp+30h+pExceptionObject], rax
0x18004de19  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004de20  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18004de24  call    _CxxThrowException_0
0x18004de2a  mov     ecx, 40h ; '@'; unsigned __int64
0x18004de2f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004de34  mov     [rbp+30h+cbData], rax
0x18004de38  test    rax, rax
0x18004de3b  jz      short loc_18004DE50
0x18004de3d  lea     r8, aUnableToQueryV; "unable to query value"
0x18004de44  mov     edx, ebx; dwMessageId
0x18004de46  mov     rcx, rax; this
0x18004de49  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004de4e  jmp     short loc_18004DE53
0x18004de50  mov     rax, r12
0x18004de53  lea     rdx, aClassUnbclStri_32; "class UnBCL::String *__cdecl UnBCL::Reg"...
0x18004de5a  mov     rcx, rax
0x18004de5d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004de62  mov     [rbp+30h+pExceptionObject], rax
0x18004de66  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004de6d  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18004de71  call    _CxxThrowException_0
```
