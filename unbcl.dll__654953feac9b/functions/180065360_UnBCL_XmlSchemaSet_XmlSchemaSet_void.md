# UnBCL::XmlSchemaSet::XmlSchemaSet(void)

- ea: `0x180065360`
- end: `0x180065477`
- name: `??0XmlSchemaSet@UnBCL@@QEAA@XZ`
- size: `279`
- prototype: `__int64 __fastcall(UnBCL::XmlSchemaSet *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800475e0`
- `0x1800477d0`
- `0x180063eb0`
- `0x180065360`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800653ca`
- `ole32!CoCreateInstance` at `0x1800653ca`

## string_xrefs

- `0x180065451`: `struct IXMLDOMSchemaCollection2 *__cdecl UnBCL::MSXmlModule::CreateDOMSchemaCollection(void)`
- `0x18006540b`: `__cdecl UnBCL::XmlSchemaSet::XmlSchemaSet(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
UnBCL::XmlSchemaSet *__fastcall UnBCL::XmlSchemaSet::XmlSchemaSet(UnBCL::XmlSchemaSet *this)
{
  HRESULT Instance; // eax
  unsigned __int16 v3; // di
  __int64 v4; // rax
  UnBCL::NotSupportedException *v6; // rax
  UnBCL::Win32Exception *v7; // rax
  __int64 pExceptionObject; // [rsp+68h] [rbp+10h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF
  UnBCL::Win32Exception *v10; // [rsp+78h] [rbp+20h]

  *(_QWORD *)this = &UnBCL::Object::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = _InterlockedIncrement(&dword_1800FFC68);
  *(_QWORD *)this = &UnBCL::XmlSchemaSet::`vftable';
  pExceptionObject = 0;
  Instance = CoCreateInstance(
               &CLSID_XMLSchemaCache60,
               0,
               1u,
               &IID_IXMLDOMSchemaCollection2,
               (LPVOID *)&pExceptionObject);
  v3 = Instance;
  if ( Instance < 0 )
  {
    v7 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v10 = v7;
    if ( v7 )
      v7 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v7, v3);
    v9 = AddStackTraceToException<UnBCL::InvalidOperationException>(
           v7,
           "struct IXMLDOMSchemaCollection2 *__cdecl UnBCL::MSXmlModule::CreateDOMSchemaCollection(void)");
    throw (UnBCL::Win32Exception **)&v9;
  }
  v4 = pExceptionObject;
  *((_QWORD *)this + 2) = pExceptionObject;
  if ( !v4 )
  {
    v6 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
    v9 = (__int64)v6;
    if ( v6 )
      v6 = (UnBCL::NotSupportedException *)UnBCL::NotSupportedException::NotSupportedException(v6);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "__cdecl UnBCL::XmlSchemaSet::XmlSchemaSet(void)");
    throw (UnBCL::NotSupportedException **)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180065360  mov     r11, rsp
0x180065363  mov     [r11+8], rcx
0x180065367  push    rbx
0x180065368  push    rdi
0x180065369  sub     rsp, 48h
0x18006536d  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180065375  mov     rbx, rcx
0x180065378  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18006537f  mov     [rcx], rax
0x180065382  mov     dword ptr [rcx+8], 0
0x180065389  mov     r8d, 1; dwClsContext
0x18006538f  mov     eax, r8d
0x180065392  lock xadd cs:dword_1800FFC68, eax
0x18006539a  add     eax, r8d
0x18006539d  mov     [rcx+0Ch], eax
0x1800653a0  lea     rax, ??_7XmlSchemaSet@UnBCL@@6B@; const UnBCL::XmlSchemaSet::`vftable'
0x1800653a7  mov     [rcx], rax
0x1800653aa  mov     qword ptr [r11+10h], 0
0x1800653b2  lea     rax, [r11+10h]
0x1800653b6  mov     [r11-38h], rax
0x1800653ba  lea     r9, IID_IXMLDOMSchemaCollection2; riid
0x1800653c1  xor     edx, edx; pUnkOuter
0x1800653c3  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x1800653ca  call    cs:__imp_CoCreateInstance
0x1800653d0  mov     edi, eax
0x1800653d2  test    eax, eax
0x1800653d4  js      short loc_180065431
0x1800653d6  mov     rax, [rsp+58h+pExceptionObject]
0x1800653db  mov     [rbx+10h], rax
0x1800653df  test    rax, rax
0x1800653e2  jz      short loc_1800653EE
0x1800653e4  mov     rax, rbx
0x1800653e7  add     rsp, 48h
0x1800653eb  pop     rdi
0x1800653ec  pop     rbx
0x1800653ed  retn
0x1800653ee  mov     ecx, 38h ; '8'; unsigned __int64
0x1800653f3  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800653f8  mov     [rsp+58h+arg_10], rax
0x1800653fd  test    rax, rax
0x180065400  jz      short loc_18006540B
0x180065402  mov     rcx, rax; this
0x180065405  call    ??0NotSupportedException@UnBCL@@QEAA@XZ; UnBCL::NotSupportedException::NotSupportedException(void)
0x18006540a  nop
0x18006540b  lea     rdx, aCdeclUnbclXmls; "__cdecl UnBCL::XmlSchemaSet::XmlSchemaS"...
0x180065412  mov     rcx, rax
0x180065415  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006541a  mov     [rsp+58h+pExceptionObject], rax
0x18006541f  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x180065426  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18006542b  call    _CxxThrowException_0
0x180065431  mov     ecx, 40h ; '@'; unsigned __int64
0x180065436  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18006543b  mov     [rsp+58h+arg_18], rax
0x180065440  test    rax, rax
0x180065443  jz      short loc_180065451
0x180065445  movzx   edx, di; dwMessageId
0x180065448  mov     rcx, rax; this
0x18006544b  call    ??0Win32Exception@UnBCL@@QEAA@K@Z; UnBCL::Win32Exception::Win32Exception(ulong)
0x180065450  nop
0x180065451  lea     rdx, aStructIxmldoms; "struct IXMLDOMSchemaCollection2 *__cdec"...
0x180065458  mov     rcx, rax
0x18006545b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180065460  mov     [rsp+58h+arg_10], rax
0x180065465  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18006546c  lea     rcx, [rsp+58h+arg_10]; pExceptionObject
0x180065471  call    _CxxThrowException_0
```
