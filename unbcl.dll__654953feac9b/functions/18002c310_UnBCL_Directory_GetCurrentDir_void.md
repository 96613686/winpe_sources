# UnBCL::Directory::GetCurrentDir(void)

- ea: `0x18002c310`
- end: `0x18002c45b`
- name: `?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ`
- size: `331`
- prototype: `struct UnBCL::String *(void)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x1800015ac`
- `0x180002f50`
- `0x180002f90`
- `0x180008160`
- `0x180011570`
- `0x18002c310`
- `0x1800477d0`
- `0x1800498a0`
- `0x18005b790`
- `0x180064680`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002c3fb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002c3fb`
- `KERNEL32!GetCurrentDirectoryW` at `0x18002c32b`
- `KERNEL32!GetCurrentDirectoryW` at `0x18002c36e`
- `KERNEL32!GetCurrentDirectoryW` at `0x18002c32b`
- `KERNEL32!GetCurrentDirectoryW` at `0x18002c36e`

## string_xrefs

- `0x18002c447`: `base\ntsetup\unbcl\src\directory.cpp`
- `0x18002c44e`: `GetCurrentDirectoryW failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct UnBCL::String *UnBCL::Directory::GetCurrentDir(void)
{
  DWORD CurrentDirectoryW; // eax
  DWORD v1; // esi
  struct UnBCL::String *v2; // rbx
  WCHAR *v3; // rax
  unsigned __int16 *v4; // rdi
  UnBCL::String *v5; // rax
  __int64 v6; // rax
  struct UnBCL::String *LongName; // rax
  struct UnBCL::String *v8; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // [rsp+28h] [rbp-40h] BYREF
  void **v11; // [rsp+30h] [rbp-38h] BYREF
  struct UnBCL::String *v12; // [rsp+38h] [rbp-30h]
  _QWORD v13[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp+8h]

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  v1 = CurrentDirectoryW;
  v2 = 0;
  if ( !CurrentDirectoryW )
    UnBCL::Win32Exception::ThrowLastError(
      L"GetCurrentDirectoryW failed",
      "base\\ntsetup\\unbcl\\src\\directory.cpp",
      1700);
  v3 = (WCHAR *)operator new[](saturated_mul(CurrentDirectoryW, 2u));
  v4 = v3;
  v14 = v3;
  if ( !v3 )
    UnBCL::Allocator::MemAllocFailed();
  GetCurrentDirectoryW(v1, v3);
  v5 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  if ( v5 )
    v6 = UnBCL::String::String(v5, v4);
  else
    v6 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v11, v6);
  try
  {
    LongName = UnBCL::Path::GetLongName(v12);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v13, LongName);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v11, v13[1]);
    v13[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v13);
  }
  catch ( UnBCL::Exception *v10 )
  {
    if ( v10 )
      (**v10)(v10, 1);
    v2 = 0;
    v4 = v14;
  }
  operator delete[](v4);
  v8 = v12;
  if ( v12 )
  {
    _InterlockedAdd((volatile signed __int32 *)v12 + 2, 0xFFFFFFFF);
    v12 = 0;
    v2 = v8;
  }
  v11 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v11);
  return v2;
}

```

## disassembly

```asm
0x18002c310  mov     rax, rsp
0x18002c313  push    rsi
0x18002c314  push    rdi
0x18002c315  push    r14
0x18002c317  sub     rsp, 50h
0x18002c31b  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18002c323  mov     [rax+18h], rbx
0x18002c327  xor     edx, edx; lpBuffer
0x18002c329  xor     ecx, ecx; nBufferLength
0x18002c32b  call    cs:__imp_GetCurrentDirectoryW
0x18002c331  mov     esi, eax
0x18002c333  xor     ebx, ebx
0x18002c335  test    eax, eax
0x18002c337  jz      loc_18002C441
0x18002c33d  mov     eax, 2
0x18002c342  mul     rsi
0x18002c345  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002c34c  cmovb   rax, r14
0x18002c350  mov     rcx, rax; unsigned __int64
0x18002c353  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002c358  mov     rdi, rax
0x18002c35b  mov     [rsp+68h+arg_0], rax
0x18002c360  test    rax, rax
0x18002c363  jz      loc_18002C43B
0x18002c369  mov     rdx, rax; lpBuffer
0x18002c36c  mov     ecx, esi; nBufferLength
0x18002c36e  call    cs:__imp_GetCurrentDirectoryW
0x18002c374  lea     ecx, [r14+19h]; unsigned __int64
0x18002c378  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c37d  mov     [rsp+68h+arg_8], rax
0x18002c382  test    rax, rax
0x18002c385  jz      short loc_18002C394
0x18002c387  mov     rdx, rdi; unsigned __int16 *
0x18002c38a  mov     rcx, rax; this
0x18002c38d  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002c392  jmp     short loc_18002C397
0x18002c394  mov     rax, rbx
0x18002c397  mov     rdx, rax
0x18002c39a  lea     rcx, [rsp+68h+var_38]
0x18002c39f  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002c3a4  nop
0x18002c3a5  mov     rcx, [rsp+68h+var_30]; struct UnBCL::String *
0x18002c3aa  call    ?GetLongName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetLongName(UnBCL::String const *)
0x18002c3af  mov     rdx, rax
0x18002c3b2  lea     rcx, [rsp+68h+var_28]
0x18002c3b7  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002c3bc  nop
0x18002c3bd  mov     rdx, [rsp+68h+var_20]
0x18002c3c2  lea     rcx, [rsp+68h+var_38]
0x18002c3c7  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002c3cc  nop
0x18002c3cd  lea     rsi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002c3d4  mov     [rsp+68h+var_28], rsi
0x18002c3d9  lea     rcx, [rsp+68h+var_28]
0x18002c3de  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002c3e3  nop
0x18002c3e4  jmp     short loc_18002C3F8
0x18002c3e6  xor     ebx, ebx
0x18002c3e8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002c3ec  lea     rsi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002c3f3  mov     rdi, [rsp+68h+arg_0]
0x18002c3f8  mov     rcx, rdi
0x18002c3fb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002c401  mov     rax, [rsp+68h+var_30]
0x18002c406  test    rax, rax
0x18002c409  jz      short loc_18002C418
0x18002c40b  lock add [rax+8], r14d
0x18002c410  mov     [rsp+68h+var_30], rbx
0x18002c415  mov     rbx, rax
0x18002c418  mov     [rsp+68h+var_38], rsi
0x18002c41d  lea     rcx, [rsp+68h+var_38]
0x18002c422  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002c427  mov     rax, rbx
0x18002c42a  mov     rbx, [rsp+68h+arg_10]
0x18002c432  add     rsp, 50h
0x18002c436  pop     r14
0x18002c438  pop     rdi
0x18002c439  pop     rsi
0x18002c43a  retn
0x18002c43b  call    ?MemAllocFailed@Allocator@UnBCL@@SAHXZ; UnBCL::Allocator::MemAllocFailed(void)
0x18002c441  mov     r8d, 6A4h; int
0x18002c447  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002c44e  lea     rcx, aGetcurrentdire; "GetCurrentDirectoryW failed"
0x18002c455  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
```
