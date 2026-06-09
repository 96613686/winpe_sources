# Wsp::Facade::FileShareFacade::DeleteObject(void)

- ea: `0x180052138`
- end: `0x180052278`
- name: `?DeleteObject@FileShareFacade@Facade@Wsp@@QEAAXXZ`
- size: `320`
- prototype: `void __fastcall(Wsp::Facade::FileShareFacade *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004bd4c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000c5c4`
- `0x18000d6a4`
- `0x18000e14c`
- `0x18004905c`
- `0x180052138`
- `0x180053138`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800521cd`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800521cd`

## string_xrefs

- `0x180052238`: `file share already detached`
- `0x1800521fc`: `Failed to delete file share`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Wsp::Facade::FileShareFacade::DeleteObject(std::_Ref_count_base **this)
{
  std::_Ref_count_base *v2; // rcx
  bool v3; // di
  int v4; // esi
  std::_Ref_count_base *v5; // rcx
  const WCHAR *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-79h] BYREF
  int v10; // [rsp+24h] [rbp-75h]
  __int64 v11; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v12[32]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-49h] BYREF

  v2 = *this;
  if ( !v2 )
  {
    v8 = std::wstring::wstring(v12, L"file share already detached");
    v9 = 2;
    v10 = 7;
    cxl::Exception::Exception(pExceptionObject, &v9, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
  (*(void (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v2 + 56LL))(v2, &v11);
  v3 = Wsp::Facade::FileShareFacade::ShouldDeleteDirectory((Wsp::Facade::FileShareFacade *)this);
  v4 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)*this + 176LL))(*this);
  if ( v4 < 0 )
  {
    v7 = std::wstring::wstring(v12, L"Failed to delete file share");
    v9 = v4;
    v10 = 2;
    cxl::Exception::Exception(pExceptionObject, &v9, v7);
    throw (cxl::Exception *)pExceptionObject;
  }
  *this = 0;
  v5 = this[1];
  this[1] = 0;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  if ( v3 && v11 )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
    RemoveDirectoryW(v6);
  }
  std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v11);
}

```

## disassembly

```asm
0x180052138  push    rbp
0x18005213a  push    rbx
0x18005213b  push    rsi
0x18005213c  push    rdi
0x18005213d  lea     rbp, [rsp-3Fh]
0x180052142  sub     rsp, 0D8h
0x180052149  mov     rax, cs:__security_cookie
0x180052150  xor     rax, rsp
0x180052153  mov     [rbp+57h+var_30], rax
0x180052157  mov     rbx, rcx
0x18005215a  mov     rcx, [rcx]
0x18005215d  test    rcx, rcx
0x180052160  jz      loc_180052238
0x180052166  mov     rax, [rcx]
0x180052169  lea     rdx, [rbp+57h+var_C8]
0x18005216d  mov     rax, [rax+38h]
0x180052171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052176  nop
0x180052177  mov     rcx, rbx; this
0x18005217a  call    ?ShouldDeleteDirectory@FileShareFacade@Facade@Wsp@@AEAA_NXZ; Wsp::Facade::FileShareFacade::ShouldDeleteDirectory(void)
0x18005217f  mov     dil, al
0x180052182  mov     rcx, [rbx]
0x180052185  mov     rdx, [rcx]
0x180052188  mov     rax, [rdx+0B0h]
0x18005218f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052194  mov     esi, eax
0x180052196  test    eax, eax
0x180052198  js      short loc_1800521FC
0x18005219a  mov     qword ptr [rbx], 0
0x1800521a1  mov     rcx, [rbx+8]; this
0x1800521a5  mov     qword ptr [rbx+8], 0
0x1800521ad  test    rcx, rcx
0x1800521b0  jz      short loc_1800521B7
0x1800521b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800521b7  test    dil, dil
0x1800521ba  jz      short loc_1800521DA
0x1800521bc  mov     rcx, [rbp+57h+var_C8]
0x1800521c0  test    rcx, rcx
0x1800521c3  jz      short loc_1800521DA
0x1800521c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800521ca  mov     rcx, rax; lpPathName
0x1800521cd  call    cs:__imp_RemoveDirectoryW
0x1800521d4  nop     dword ptr [rax+rax+00h]
0x1800521d9  nop
0x1800521da  lea     rcx, [rbp+57h+var_C8]
0x1800521de  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800521e3  mov     rcx, [rbp+57h+var_30]
0x1800521e7  xor     rcx, rsp; StackCookie
0x1800521ea  call    __security_check_cookie
0x1800521ef  add     rsp, 0D8h
0x1800521f6  pop     rdi
0x1800521f7  pop     rsi
0x1800521f8  pop     rbx
0x1800521f9  pop     rbp
0x1800521fa  retn
0x1800521fc  lea     rdx, aFailedToDelete; "Failed to delete file share"
0x180052203  lea     rcx, [rbp+57h+var_C0]
0x180052207  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005220c  nop
0x18005220d  mov     [rbp+57h+var_D0], esi
0x180052210  mov     [rbp+57h+var_CC], 2
0x180052217  mov     r8, rax
0x18005221a  lea     rdx, [rbp+57h+var_D0]
0x18005221e  lea     rcx, [rbp+57h+pExceptionObject]
0x180052222  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180052227  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005222e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180052232  call    _CxxThrowException_0
0x180052238  lea     rdx, aFileShareAlrea; "file share already detached"
0x18005223f  lea     rcx, [rbp+57h+var_C0]
0x180052243  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180052248  nop
0x180052249  mov     [rbp+57h+var_D0], 2
0x180052250  mov     [rbp+57h+var_CC], 7
0x180052257  mov     r8, rax
0x18005225a  lea     rdx, [rbp+57h+var_D0]
0x18005225e  lea     rcx, [rbp+57h+pExceptionObject]
0x180052262  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180052267  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005226e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180052272  call    _CxxThrowException_0
```
