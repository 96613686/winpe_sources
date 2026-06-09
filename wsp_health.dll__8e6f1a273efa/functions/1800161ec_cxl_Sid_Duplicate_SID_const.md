# cxl::Sid::Duplicate(_SID const *)

- ea: `0x1800161ec`
- end: `0x180016310`
- name: `?Duplicate@Sid@cxl@@QEAAXPEBU_SID@@@Z`
- size: `292`
- prototype: `void __fastcall(cxl::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d7fc`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000edac`
- `0x180011184`
- `0x180011800`
- `0x180014574`
- `0x1800145d4`
- `0x1800161ec`
- `0x1800165d0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016231`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016231`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001625e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001625e`

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
0x1800161ec  mov     [rsp-8+arg_10], rbx
0x1800161f1  mov     [rsp-8+arg_18], rsi
0x1800161f6  push    rbp
0x1800161f7  push    rdi
0x1800161f8  push    r14
0x1800161fa  lea     rbp, [rsp-47h]
0x1800161ff  sub     rsp, 100h
0x180016206  mov     rax, cs:__security_cookie
0x18001620d  xor     rax, rsp
0x180016210  mov     [rbp+57h+var_20], rax
0x180016214  mov     r14, rdx
0x180016217  mov     rdi, rcx
0x18001621a  mov     rax, [rcx]
0x18001621d  mov     rax, [rax+8]
0x180016221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016226  mov     rcx, r14; struct _SID *
0x180016229  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18001622e  mov     rcx, r14; pSid
0x180016231  call    cs:__imp_GetLengthSid
0x180016238  nop     dword ptr [rax+rax+00h]
0x18001623d  mov     esi, eax
0x18001623f  test    al, al
0x180016241  jz      short loc_18001628D
0x180016243  movzx   ecx, sil; uBytes
0x180016247  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18001624c  mov     rbx, rax
0x18001624f  mov     [rsp+110h+var_E0], rax
0x180016254  movzx   ecx, sil; nDestinationSidLength
0x180016258  mov     r8, r14; pSourceSid
0x18001625b  mov     rdx, rax; pDestinationSid
0x18001625e  call    cs:__imp_CopySid
0x180016265  nop     dword ptr [rax+rax+00h]
0x18001626a  test    eax, eax
0x18001626c  jz      short loc_1800162B2
0x18001626e  mov     [rsp+110h+var_E0], 0
0x180016277  mov     rdx, rbx; struct _SID *
0x18001627a  mov     rcx, rdi; this
0x18001627d  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180016282  nop
0x180016283  lea     rcx, [rsp+110h+var_E8]
0x180016288  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001628d  mov     rcx, [rbp+57h+var_20]
0x180016291  xor     rcx, rsp; StackCookie
0x180016294  call    __security_check_cookie
0x180016299  lea     r11, [rsp+110h+var_10]
0x1800162a1  mov     rbx, [r11+30h]
0x1800162a5  mov     rsi, [r11+38h]
0x1800162a9  mov     rsp, r11
0x1800162ac  pop     r14
0x1800162ae  pop     rdi
0x1800162af  pop     rbp
0x1800162b0  retn
0x1800162b2  lea     rcx, [rbp+57h+var_B8]
0x1800162b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800162bb  nop
0x1800162bc  lea     rdx, [rbp+57h+var_B8]
0x1800162c0  lea     rcx, [rsp+110h+var_D8]
0x1800162c5  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800162ca  nop
0x1800162cb  lea     rcx, [rsp+110h+var_D8]
0x1800162d0  call    ??$Write@$0P@@TextWriter@cxl@@QEAAAEAV01@AEAY0P@$$CBD@Z; cxl::TextWriter::Write<15>(char const (&)[15])
0x1800162d5  call    cs:__imp_GetLastError
0x1800162dc  nop     dword ptr [rax+rax+00h]
0x1800162e1  mov     [rsp+110h+var_F0], eax
0x1800162e5  mov     [rsp+110h+var_EC], 0
0x1800162ed  lea     r8, [rbp+57h+var_B8]
0x1800162f1  lea     rdx, [rsp+110h+var_F0]
0x1800162f6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800162fa  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800162ff  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180016306  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001630a  call    _CxxThrowException_0
```
