# cxl::Sid::Duplicate(_SID const *)

- ea: `0x180015a0c`
- end: `0x180015b1d`
- name: `?Duplicate@Sid@cxl@@QEAAXPEBU_SID@@@Z`
- size: `273`
- prototype: `void __fastcall(cxl::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c200`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000e91c`
- `0x180010ca4`
- `0x1800112f0`
- `0x180013e14`
- `0x180013e70`
- `0x180015a0c`
- `0x180015d8c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015a51`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015a51`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015a78`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015a78`

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
0x180015a0c  mov     [rsp-8+arg_10], rbx
0x180015a11  mov     [rsp-8+arg_18], rsi
0x180015a16  push    rbp
0x180015a17  push    rdi
0x180015a18  push    r14
0x180015a1a  lea     rbp, [rsp-47h]
0x180015a1f  sub     rsp, 100h
0x180015a26  mov     rax, cs:__security_cookie
0x180015a2d  xor     rax, rsp
0x180015a30  mov     [rbp+57h+var_20], rax
0x180015a34  mov     r14, rdx
0x180015a37  mov     rdi, rcx
0x180015a3a  mov     rax, [rcx]
0x180015a3d  mov     rax, [rax+8]
0x180015a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a46  mov     rcx, r14; struct _SID *
0x180015a49  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180015a4e  mov     rcx, r14; pSid
0x180015a51  call    cs:__imp_GetLengthSid
0x180015a57  mov     esi, eax
0x180015a59  test    al, al
0x180015a5b  jz      short loc_180015AA1
0x180015a5d  movzx   ecx, sil; uBytes
0x180015a61  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180015a66  mov     rbx, rax
0x180015a69  mov     [rsp+110h+var_E0], rax
0x180015a6e  movzx   ecx, sil; nDestinationSidLength
0x180015a72  mov     r8, r14; pSourceSid
0x180015a75  mov     rdx, rax; pDestinationSid
0x180015a78  call    cs:__imp_CopySid
0x180015a7e  test    eax, eax
0x180015a80  jz      short loc_180015AC5
0x180015a82  mov     [rsp+110h+var_E0], 0
0x180015a8b  mov     rdx, rbx; struct _SID *
0x180015a8e  mov     rcx, rdi; this
0x180015a91  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180015a96  nop
0x180015a97  lea     rcx, [rsp+110h+var_E8]
0x180015a9c  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180015aa1  mov     rcx, [rbp+57h+var_20]
0x180015aa5  xor     rcx, rsp; StackCookie
0x180015aa8  call    __security_check_cookie
0x180015aad  lea     r11, [rsp+110h+var_10]
0x180015ab5  mov     rbx, [r11+30h]
0x180015ab9  mov     rsi, [r11+38h]
0x180015abd  mov     rsp, r11
0x180015ac0  pop     r14
0x180015ac2  pop     rdi
0x180015ac3  pop     rbp
0x180015ac4  retn
0x180015ac5  lea     rcx, [rbp+57h+var_B8]
0x180015ac9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015ace  nop
0x180015acf  lea     rdx, [rbp+57h+var_B8]
0x180015ad3  lea     rcx, [rsp+110h+var_D8]
0x180015ad8  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015add  nop
0x180015ade  lea     rcx, [rsp+110h+var_D8]
0x180015ae3  call    ??$Write@$0P@@TextWriter@cxl@@QEAAAEAV01@AEAY0P@$$CBD@Z; cxl::TextWriter::Write<15>(char const (&)[15])
0x180015ae8  call    cs:__imp_GetLastError
0x180015aee  mov     [rsp+110h+var_F0], eax
0x180015af2  mov     [rsp+110h+var_EC], 0
0x180015afa  lea     r8, [rbp+57h+var_B8]
0x180015afe  lea     rdx, [rsp+110h+var_F0]
0x180015b03  lea     rcx, [rbp+57h+pExceptionObject]
0x180015b07  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015b0c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015b13  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180015b17  call    _CxxThrowException_0
```
