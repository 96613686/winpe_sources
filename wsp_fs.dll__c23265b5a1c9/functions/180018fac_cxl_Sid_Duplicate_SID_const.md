# cxl::Sid::Duplicate(_SID const *)

- ea: `0x180018fac`
- end: `0x1800190d0`
- name: `?Duplicate@Sid@cxl@@QEAAXPEBU_SID@@@Z`
- size: `292`
- prototype: `void __fastcall(cxl::Sid *__hidden this, const struct _SID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067490`
- `0x1800679e8`
- `0x180073058`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f4b4`
- `0x1800124ac`
- `0x180012b00`
- `0x180015ae4`
- `0x180015bb0`
- `0x180018fac`
- `0x180019740`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019095`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018ff1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018ff1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001901e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001901e`

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
      cxl::TextWriter::Write<15>(v11);
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
0x180018fac  mov     [rsp-8+arg_10], rbx
0x180018fb1  mov     [rsp-8+arg_18], rsi
0x180018fb6  push    rbp
0x180018fb7  push    rdi
0x180018fb8  push    r14
0x180018fba  lea     rbp, [rsp-47h]
0x180018fbf  sub     rsp, 100h
0x180018fc6  mov     rax, cs:__security_cookie
0x180018fcd  xor     rax, rsp
0x180018fd0  mov     [rbp+57h+var_20], rax
0x180018fd4  mov     r14, rdx
0x180018fd7  mov     rdi, rcx
0x180018fda  mov     rax, [rcx]
0x180018fdd  mov     rax, [rax+8]
0x180018fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fe6  mov     rcx, r14; struct _SID *
0x180018fe9  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180018fee  mov     rcx, r14; pSid
0x180018ff1  call    cs:__imp_GetLengthSid
0x180018ff8  nop     dword ptr [rax+rax+00h]
0x180018ffd  mov     esi, eax
0x180018fff  test    al, al
0x180019001  jz      short loc_18001904D
0x180019003  movzx   ecx, sil; uBytes
0x180019007  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18001900c  mov     rbx, rax
0x18001900f  mov     [rsp+110h+var_E0], rax
0x180019014  movzx   ecx, sil; nDestinationSidLength
0x180019018  mov     r8, r14; pSourceSid
0x18001901b  mov     rdx, rax; pDestinationSid
0x18001901e  call    cs:__imp_CopySid
0x180019025  nop     dword ptr [rax+rax+00h]
0x18001902a  test    eax, eax
0x18001902c  jz      short loc_180019072
0x18001902e  mov     [rsp+110h+var_E0], 0
0x180019037  mov     rdx, rbx; struct _SID *
0x18001903a  mov     rcx, rdi; this
0x18001903d  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180019042  nop
0x180019043  lea     rcx, [rsp+110h+var_E8]
0x180019048  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001904d  mov     rcx, [rbp+57h+var_20]
0x180019051  xor     rcx, rsp; StackCookie
0x180019054  call    __security_check_cookie
0x180019059  lea     r11, [rsp+110h+var_10]
0x180019061  mov     rbx, [r11+30h]
0x180019065  mov     rsi, [r11+38h]
0x180019069  mov     rsp, r11
0x18001906c  pop     r14
0x18001906e  pop     rdi
0x18001906f  pop     rbp
0x180019070  retn
0x180019072  lea     rcx, [rbp+57h+var_B8]
0x180019076  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001907b  nop
0x18001907c  lea     rdx, [rbp+57h+var_B8]
0x180019080  lea     rcx, [rsp+110h+var_D8]
0x180019085  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001908a  nop
0x18001908b  lea     rcx, [rsp+110h+var_D8]
0x180019090  call    ??$Write@$0P@@TextWriter@cxl@@QEAAAEAV01@AEAY0P@$$CBD@Z; cxl::TextWriter::Write<15>(char const (&)[15])
0x180019095  call    cs:__imp_GetLastError
0x18001909c  nop     dword ptr [rax+rax+00h]
0x1800190a1  mov     [rsp+110h+var_F0], eax
0x1800190a5  mov     [rsp+110h+var_EC], 0
0x1800190ad  lea     r8, [rbp+57h+var_B8]
0x1800190b1  lea     rdx, [rsp+110h+var_F0]
0x1800190b6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800190ba  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800190bf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800190c6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800190ca  call    _CxxThrowException_0
```
