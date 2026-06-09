# UnBCL::FileSystemEnumerator::FileSystemEnumerator(ushort const *,ushort const *)

- ea: `0x18003ccb0`
- end: `0x18003cfb9`
- name: `??0FileSystemEnumerator@UnBCL@@QEAA@PEBG0@Z`
- size: `777`
- prototype: `_QWORD(UnBCL::FileSystemEnumerator *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x1800015ac`
- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011570`
- `0x18002bca0`
- `0x18003ccb0`
- `0x1800477d0`
- `0x18005b790`
- `0x18005c180`
- `0x180060150`
- `0x1800601c0`
- `0x1800602f0`
- `0x1800646f0`
- `0x180069020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003ce92`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003cf2e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003ce92`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003cf2e`
- `KERNEL32!GetFullPathNameW` at `0x18003cdd1`
- `KERNEL32!GetFullPathNameW` at `0x18003cdfe`
- `KERNEL32!GetFullPathNameW` at `0x18003cdd1`
- `KERNEL32!GetFullPathNameW` at `0x18003cdfe`

## string_xrefs

- `0x18003cf37`: `unable to get full path for %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
UnBCL::FileSystemEnumerator *__fastcall UnBCL::FileSystemEnumerator::FileSystemEnumerator(
        UnBCL::FileSystemEnumerator *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  char *v7; // r15
  DWORD FullPathNameW; // eax
  DWORD v9; // esi
  WCHAR *v10; // rdi
  UnBCL::String *v11; // rax
  UnBCL::ArgumentException *v13; // rax
  struct UnBCL::String *v14; // rax
  __int64 v15; // rax
  const struct UnBCL::String *v16; // rax
  UnBCL::ArgumentNullException *v17; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp-D8h] BYREF
  UnBCL::ArgumentNullException *v19; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v21[4]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+78h] [rbp-90h] BYREF

  v21[2] = -2;
  v21[3] = this;
  if ( a4 )
  {
    *((_QWORD *)this + 1) = &UnBCL::FileSystemEnumerator::`vbtable';
    *((_QWORD *)this + 93) = &UnBCL::Object::`vftable';
    *((_DWORD *)this + 188) = 0;
    *((_DWORD *)this + 189) = _InterlockedIncrement(&dword_1800FFC68);
  }
  *(_QWORD *)this = &UnBCL::FileSystemEnumerator::`vftable'{for `UnBCL::IEnumerator<UnBCL::String *>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &UnBCL::FileSystemEnumerator::`vftable'{for `UnBCL::Object'};
  v7 = (char *)this + 608;
  UnBCL::StringPtr::StringPtr((UnBCL::FileSystemEnumerator *)((char *)this + 608));
  UnBCL::StringPtr::StringPtr((UnBCL::FileSystemEnumerator *)((char *)this + 640), a3);
  *((_QWORD *)this + 84) = -1;
  UnBCL::StringPtr::StringPtr((UnBCL::FileSystemEnumerator *)((char *)this + 680));
  UnBCL::StringPtr::StringPtr((UnBCL::FileSystemEnumerator *)((char *)this + 712));
  if ( !a2 )
  {
    v17 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v19 = v17;
    if ( v17 )
      v17 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(v17, L"RootDir");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "__cdecl UnBCL::FileSystemEnumerator::FileSystemEnumerator(const unsigned short *,const unsigned"
                         " short *) noexcept(false)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, 0);
  v9 = FullPathNameW;
  if ( FullPathNameW <= 0x104 )
  {
    if ( FullPathNameW )
    {
      v10 = Buffer;
      goto LABEL_9;
    }
LABEL_19:
    v14 = UnBCL::String::Format(L"unable to get full path for %s", a2);
    v15 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v19, v14);
    v16 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v15);
    UnBCL::Win32Exception::ThrowLastError(v16, "base\\ntsetup\\unbcl\\src\\fileenum.cpp", 55);
  }
  v10 = (WCHAR *)operator new[](saturated_mul(FullPathNameW, 2u));
  if ( !GetFullPathNameW(a2, v9, v10, 0) )
  {
    operator delete[](v10);
    goto LABEL_19;
  }
LABEL_9:
  v11 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v19 = v11;
  if ( v11 )
    v11 = (UnBCL::String *)UnBCL::String::String(v11, v10);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v20, v11);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
    &v7[*(int *)(*((_QWORD *)this + 77) + 4LL) + 8],
    *(_QWORD *)((char *)v21 + *(int *)(v20[1] + 4LL)));
  v21[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v21);
  if ( v10 != Buffer )
    operator delete[](v10);
  if ( !(unsigned int)UnBCL::Directory::Exists(*(const struct UnBCL::String **)((char *)this
                                                                              + *(int *)(*((_QWORD *)this + 77) + 4LL)
                                                                              + 624)) )
  {
    v13 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v19 = v13;
    if ( v13 )
      v13 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v13, L"RootDir");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "__cdecl UnBCL::FileSystemEnumerator::FileSystemEnumerator(const unsigned short *,const unsigned"
                         " short *) noexcept(false)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18003ccb0  mov     rax, rsp
0x18003ccb3  push    rbp
0x18003ccb4  push    rsi
0x18003ccb5  push    rdi
0x18003ccb6  push    r12
0x18003ccb8  push    r13
0x18003ccba  push    r14
0x18003ccbc  push    r15
0x18003ccbe  lea     rbp, [rax-1C8h]
0x18003ccc5  sub     rsp, 290h
0x18003cccc  mov     [rsp+2C0h+var_260], 0FFFFFFFFFFFFFFFEh
0x18003ccd5  mov     [rax+20h], rbx
0x18003ccd9  mov     rax, cs:__security_cookie
0x18003cce0  xor     rax, rsp
0x18003cce3  mov     [rbp+1C0h+var_40], rax
0x18003ccea  mov     rdi, r8
0x18003cced  mov     r14, rdx
0x18003ccf0  mov     rbx, rcx
0x18003ccf3  mov     qword ptr [rsp+2C0h+var_258], rcx
0x18003ccf8  mov     dword ptr [rsp+2C0h+var_2A0], 0
0x18003cd00  mov     r12d, 1
0x18003cd06  test    r9d, r9d
0x18003cd09  jz      short loc_18003CD47
0x18003cd0b  lea     rax, ??_8FileSystemEnumerator@UnBCL@@7B@; const UnBCL::FileSystemEnumerator::`vbtable'
0x18003cd12  mov     [rcx+8], rax
0x18003cd16  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18003cd1d  mov     [rcx+2E8h], rax
0x18003cd24  mov     dword ptr [rcx+2F0h], 0
0x18003cd2e  mov     eax, r12d
0x18003cd31  lock xadd cs:dword_1800FFC68, eax
0x18003cd39  add     eax, r12d
0x18003cd3c  mov     [rcx+2F4h], eax
0x18003cd42  mov     dword ptr [rsp+2C0h+var_2A0], r12d
0x18003cd47  lea     rax, ??_7FileSystemEnumerator@UnBCL@@6B?$IEnumerator@PEAVString@UnBCL@@@1@@; const UnBCL::FileSystemEnumerator::`vftable'{for `UnBCL::IEnumerator<UnBCL::String *>'}
0x18003cd4e  mov     [rcx], rax
0x18003cd51  mov     rax, [rcx+8]
0x18003cd55  movsxd  rcx, dword ptr [rax+4]
0x18003cd59  lea     rax, ??_7FileSystemEnumerator@UnBCL@@6BObject@1@@; const UnBCL::FileSystemEnumerator::`vftable'{for `UnBCL::Object'}
0x18003cd60  mov     [rcx+rbx+8], rax
0x18003cd65  lea     r15, [rbx+260h]
0x18003cd6c  mov     edx, r12d
0x18003cd6f  mov     rcx, r15; this
0x18003cd72  call    ??0StringPtr@UnBCL@@QEAA@XZ; UnBCL::StringPtr::StringPtr(void)
0x18003cd77  nop
0x18003cd78  lea     rcx, [rbx+280h]; this
0x18003cd7f  mov     r8d, r12d
0x18003cd82  mov     rdx, rdi; unsigned __int16 *
0x18003cd85  call    ??0StringPtr@UnBCL@@QEAA@PEBG@Z; UnBCL::StringPtr::StringPtr(ushort const *)
0x18003cd8a  nop
0x18003cd8b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003cd8f  mov     [rbx+2A0h], r13
0x18003cd96  lea     rcx, [rbx+2A8h]; this
0x18003cd9d  mov     edx, r12d
0x18003cda0  call    ??0StringPtr@UnBCL@@QEAA@XZ; UnBCL::StringPtr::StringPtr(void)
0x18003cda5  nop
0x18003cda6  lea     rcx, [rbx+2C8h]; this
0x18003cdad  mov     edx, r12d
0x18003cdb0  call    ??0StringPtr@UnBCL@@QEAA@XZ; UnBCL::StringPtr::StringPtr(void)
0x18003cdb5  nop
0x18003cdb6  test    r14, r14
0x18003cdb9  jz      loc_18003CF6F
0x18003cdbf  xor     r9d, r9d; lpFilePart
0x18003cdc2  lea     r8, [rsp+2C0h+Buffer]; lpBuffer
0x18003cdc7  mov     edi, 104h
0x18003cdcc  mov     edx, edi; nBufferLength
0x18003cdce  mov     rcx, r14; lpFileName
0x18003cdd1  call    cs:__imp_GetFullPathNameW
0x18003cdd7  mov     esi, eax
0x18003cdd9  cmp     eax, edi
0x18003cddb  jbe     short loc_18003CE0E
0x18003cddd  lea     eax, [r13+3]
0x18003cde1  mul     rsi
0x18003cde4  cmovb   rax, r13
0x18003cde8  mov     rcx, rax; unsigned __int64
0x18003cdeb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003cdf0  mov     rdi, rax
0x18003cdf3  xor     r9d, r9d; lpFilePart
0x18003cdf6  mov     r8, rax; lpBuffer
0x18003cdf9  mov     edx, esi; nBufferLength
0x18003cdfb  mov     rcx, r14; lpFileName
0x18003cdfe  call    cs:__imp_GetFullPathNameW
0x18003ce04  test    eax, eax
0x18003ce06  jz      loc_18003CF2B
0x18003ce0c  jmp     short loc_18003CE1B
0x18003ce0e  test    eax, eax
0x18003ce10  jz      loc_18003CF34
0x18003ce16  lea     rdi, [rsp+2C0h+Buffer]
0x18003ce1b  mov     ecx, 18h; unsigned __int64
0x18003ce20  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003ce25  mov     [rsp+2C0h+var_290], rax
0x18003ce2a  test    rax, rax
0x18003ce2d  jz      short loc_18003CE3B
0x18003ce2f  mov     rdx, rdi; unsigned __int16 *
0x18003ce32  mov     rcx, rax; this
0x18003ce35  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003ce3a  nop
0x18003ce3b  mov     r8d, r12d
0x18003ce3e  mov     rdx, rax; struct UnBCL::String *
0x18003ce41  lea     rcx, [rsp+2C0h+var_280]; this
0x18003ce46  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18003ce4b  nop
0x18003ce4c  mov     rax, [rsp+2C0h+var_278]
0x18003ce51  movsxd  rdx, dword ptr [rax+4]
0x18003ce55  mov     rax, [r15+8]
0x18003ce59  movsxd  rcx, dword ptr [rax+4]
0x18003ce5d  add     rcx, 8
0x18003ce61  add     rcx, r15
0x18003ce64  mov     rdx, [rsp+rdx+50h]
0x18003ce69  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003ce6e  nop
0x18003ce6f  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003ce76  mov     [rsp+50h], rax
0x18003ce7b  lea     rcx, [rsp+50h]
0x18003ce80  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003ce85  lea     rax, [rsp+2C0h+Buffer]
0x18003ce8a  cmp     rdi, rax
0x18003ce8d  jz      short loc_18003CE98
0x18003ce8f  mov     rcx, rdi
0x18003ce92  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003ce98  mov     rax, [rbx+268h]
0x18003ce9f  movsxd  rcx, dword ptr [rax+4]
0x18003cea3  mov     rcx, [rcx+rbx+270h]; struct UnBCL::String *
0x18003ceab  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18003ceb0  test    eax, eax
0x18003ceb2  jz      short loc_18003CEE1
0x18003ceb4  mov     rax, rbx
0x18003ceb7  mov     rcx, [rbp+1C0h+var_40]
0x18003cebe  xor     rcx, rsp; StackCookie
0x18003cec1  call    __security_check_cookie
0x18003cec6  mov     rbx, [rsp+2C0h+arg_18]
0x18003cece  add     rsp, 290h
0x18003ced5  pop     r15
0x18003ced7  pop     r14
0x18003ced9  pop     r13
0x18003cedb  pop     r12
0x18003cedd  pop     rdi
0x18003cede  pop     rsi
0x18003cedf  pop     rbp
0x18003cee0  retn
0x18003cee1  mov     ecx, 38h ; '8'; unsigned __int64
0x18003cee6  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003ceeb  mov     [rsp+2C0h+var_290], rax
0x18003cef0  test    rax, rax
0x18003cef3  jz      short loc_18003CF05
0x18003cef5  lea     rdx, aRootdir; "RootDir"
0x18003cefc  mov     rcx, rax; this
0x18003ceff  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003cf04  nop
0x18003cf05  lea     rdx, aCdeclUnbclFile; "__cdecl UnBCL::FileSystemEnumerator::Fi"...
0x18003cf0c  mov     rcx, rax
0x18003cf0f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003cf14  mov     [rsp+2C0h+pExceptionObject], rax
0x18003cf19  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003cf20  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x18003cf25  call    _CxxThrowException_0
0x18003cf2b  mov     rcx, rdi
0x18003cf2e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003cf34  mov     rdx, r14
0x18003cf37  lea     rcx, aUnableToGetFul; "unable to get full path for %s"
0x18003cf3e  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18003cf43  mov     rdx, rax
0x18003cf46  lea     rcx, [rsp+2C0h+var_290]
0x18003cf4b  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003cf50  nop
0x18003cf51  mov     rcx, rax
0x18003cf54  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003cf59  mov     rcx, rax; struct UnBCL::String *
0x18003cf5c  mov     r8d, 37h ; '7'; int
0x18003cf62  lea     rdx, aBaseNtsetupUnb_8; "base\\ntsetup\\unbcl\\src\\fileenum.cpp"
0x18003cf69  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
0x18003cf6f  mov     ecx, 38h ; '8'; unsigned __int64
0x18003cf74  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003cf79  mov     [rsp+2C0h+var_290], rax
0x18003cf7e  test    rax, rax
0x18003cf81  jz      short loc_18003CF93
0x18003cf83  lea     rdx, aRootdir; "RootDir"
0x18003cf8a  mov     rcx, rax; this
0x18003cf8d  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003cf92  nop
0x18003cf93  lea     rdx, aCdeclUnbclFile; "__cdecl UnBCL::FileSystemEnumerator::Fi"...
0x18003cf9a  mov     rcx, rax
0x18003cf9d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003cfa2  mov     [rsp+2C0h+pExceptionObject], rax
0x18003cfa7  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003cfae  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x18003cfb3  call    _CxxThrowException_0
```
