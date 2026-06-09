# cxl::Sid::Duplicate(_SID const *)

- ea: `0x18001873c`
- end: `0x18001884d`
- name: `?Duplicate@Sid@cxl@@QEAAXPEBU_SID@@@Z`
- size: `273`
- prototype: `void __fastcall(cxl::Sid *__hidden this, const struct _SID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800661a8`
- `0x180066718`
- `0x1800714f8`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000f074`
- `0x180012028`
- `0x180012660`
- `0x1800153e4`
- `0x1800154ac`
- `0x18001873c`
- `0x180018e0c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018818`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018781`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018781`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800187a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800187a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::Sid::Duplicate(cxl::Sid *this, struct _SID *a2)
{
  unsigned __int8 LengthSid; // al
  unsigned int v5; // edx
  unsigned __int8 v6; // si
  struct _SID *v7; // rbx
  _DWORD v8[2]; // [rsp+20h] [rbp-99h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-91h] BYREF
  struct _SID *v10; // [rsp+30h] [rbp-89h]
  _BYTE v11[32]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v12[40]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-39h] BYREF

  (*(void (__fastcall **)(cxl::Sid *))(*(_QWORD *)this + 8LL))(this);
  cxl::SidBase::VerifySid(a2);
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid;
  if ( LengthSid )
  {
    v7 = (struct _SID *)cxl::LocalHeap::Alloc(LengthSid, v5);
    v10 = v7;
    if ( !CopySid(v6, v7, a2) )
    {
      std::wstring::wstring(v12);
      cxl::StringWriter::StringWriter(v11, v12);
      cxl::TextWriter::Write<15>((__int64)v11);
      v8[0] = GetLastError();
      v8[1] = 0;
      cxl::Exception::Exception(pExceptionObject, v8, v12);
      throw (cxl::Exception *)pExceptionObject;
    }
    v10 = 0;
    cxl::SidBase::Attach(this, v7);
    cxl::LocalHeapPtr<unsigned char>::Clear(v9);
  }
}

```

## disassembly

```asm
0x18001873c  mov     [rsp-8+arg_10], rbx
0x180018741  mov     [rsp-8+arg_18], rsi
0x180018746  push    rbp
0x180018747  push    rdi
0x180018748  push    r14
0x18001874a  lea     rbp, [rsp-47h]
0x18001874f  sub     rsp, 100h
0x180018756  mov     rax, cs:__security_cookie
0x18001875d  xor     rax, rsp
0x180018760  mov     [rbp+57h+var_20], rax
0x180018764  mov     r14, rdx
0x180018767  mov     rdi, rcx
0x18001876a  mov     rax, [rcx]
0x18001876d  mov     rax, [rax+8]
0x180018771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018776  mov     rcx, r14; struct _SID *
0x180018779  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18001877e  mov     rcx, r14; pSid
0x180018781  call    cs:__imp_GetLengthSid
0x180018787  mov     esi, eax
0x180018789  test    al, al
0x18001878b  jz      short loc_1800187D1
0x18001878d  movzx   ecx, sil; uBytes
0x180018791  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180018796  mov     rbx, rax
0x180018799  mov     [rsp+110h+var_E0], rax
0x18001879e  movzx   ecx, sil; nDestinationSidLength
0x1800187a2  mov     r8, r14; pSourceSid
0x1800187a5  mov     rdx, rax; pDestinationSid
0x1800187a8  call    cs:__imp_CopySid
0x1800187ae  test    eax, eax
0x1800187b0  jz      short loc_1800187F5
0x1800187b2  mov     [rsp+110h+var_E0], 0
0x1800187bb  mov     rdx, rbx; struct _SID *
0x1800187be  mov     rcx, rdi; this
0x1800187c1  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x1800187c6  nop
0x1800187c7  lea     rcx, [rsp+110h+var_E8]
0x1800187cc  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x1800187d1  mov     rcx, [rbp+57h+var_20]
0x1800187d5  xor     rcx, rsp; StackCookie
0x1800187d8  call    __security_check_cookie
0x1800187dd  lea     r11, [rsp+110h+var_10]
0x1800187e5  mov     rbx, [r11+30h]
0x1800187e9  mov     rsi, [r11+38h]
0x1800187ed  mov     rsp, r11
0x1800187f0  pop     r14
0x1800187f2  pop     rdi
0x1800187f3  pop     rbp
0x1800187f4  retn
0x1800187f5  lea     rcx, [rbp+57h+var_B8]
0x1800187f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800187fe  nop
0x1800187ff  lea     rdx, [rbp+57h+var_B8]
0x180018803  lea     rcx, [rsp+110h+var_D8]
0x180018808  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001880d  nop
0x18001880e  lea     rcx, [rsp+110h+var_D8]
0x180018813  call    ??$Write@$0P@@TextWriter@cxl@@QEAAAEAV01@AEAY0P@$$CBD@Z; cxl::TextWriter::Write<15>(char const (&)[15])
0x180018818  call    cs:__imp_GetLastError
0x18001881e  mov     [rsp+110h+var_F0], eax
0x180018822  mov     [rsp+110h+var_EC], 0
0x18001882a  lea     r8, [rbp+57h+var_B8]
0x18001882e  lea     rdx, [rsp+110h+var_F0]
0x180018833  lea     rcx, [rbp+57h+pExceptionObject]
0x180018837  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001883c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018843  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018847  call    _CxxThrowException_0
```
