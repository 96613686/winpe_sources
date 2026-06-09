# Wsp::Facade::FileShareFacade::DeleteObject(void)

- ea: `0x180051164`
- end: `0x18005129d`
- name: `?DeleteObject@FileShareFacade@Facade@Wsp@@QEAAXXZ`
- size: `313`
- prototype: `void __fastcall(std::_Ref_count_base **this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004ab8c`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000c284`
- `0x18000d33c`
- `0x18000dd74`
- `0x180047e98`
- `0x180051164`
- `0x180052148`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800511f9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800511f9`

## string_xrefs

- `0x18005125d`: `file share already detached`
- `0x180051221`: `Failed to delete file share`

## pseudocode

```c
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
0x180051164  push    rbp
0x180051166  push    rbx
0x180051167  push    rsi
0x180051168  push    rdi
0x180051169  lea     rbp, [rsp-3Fh]
0x18005116e  sub     rsp, 0D8h
0x180051175  mov     rax, cs:__security_cookie
0x18005117c  xor     rax, rsp
0x18005117f  mov     [rbp+57h+var_30], rax
0x180051183  mov     rbx, rcx
0x180051186  mov     rcx, [rcx]
0x180051189  test    rcx, rcx
0x18005118c  jz      loc_18005125D
0x180051192  mov     rax, [rcx]
0x180051195  lea     rdx, [rbp+57h+var_C8]
0x180051199  mov     rax, [rax+38h]
0x18005119d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511a2  nop
0x1800511a3  mov     rcx, rbx; this
0x1800511a6  call    ?ShouldDeleteDirectory@FileShareFacade@Facade@Wsp@@AEAA_NXZ; Wsp::Facade::FileShareFacade::ShouldDeleteDirectory(void)
0x1800511ab  mov     dil, al
0x1800511ae  mov     rcx, [rbx]
0x1800511b1  mov     rdx, [rcx]
0x1800511b4  mov     rax, [rdx+0B0h]
0x1800511bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511c0  mov     esi, eax
0x1800511c2  test    eax, eax
0x1800511c4  js      short loc_180051221
0x1800511c6  mov     qword ptr [rbx], 0
0x1800511cd  mov     rcx, [rbx+8]; this
0x1800511d1  mov     qword ptr [rbx+8], 0
0x1800511d9  test    rcx, rcx
0x1800511dc  jz      short loc_1800511E3
0x1800511de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800511e3  test    dil, dil
0x1800511e6  jz      short loc_180051200
0x1800511e8  mov     rcx, [rbp+57h+var_C8]
0x1800511ec  test    rcx, rcx
0x1800511ef  jz      short loc_180051200
0x1800511f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800511f6  mov     rcx, rax; lpPathName
0x1800511f9  call    cs:__imp_RemoveDirectoryW
0x1800511ff  nop
0x180051200  lea     rcx, [rbp+57h+var_C8]
0x180051204  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180051209  mov     rcx, [rbp+57h+var_30]
0x18005120d  xor     rcx, rsp; StackCookie
0x180051210  call    __security_check_cookie
0x180051215  add     rsp, 0D8h
0x18005121c  pop     rdi
0x18005121d  pop     rsi
0x18005121e  pop     rbx
0x18005121f  pop     rbp
0x180051220  retn
0x180051221  lea     rdx, aFailedToDelete; "Failed to delete file share"
0x180051228  lea     rcx, [rbp+57h+var_C0]
0x18005122c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180051231  nop
0x180051232  mov     [rbp+57h+var_D0], esi
0x180051235  mov     [rbp+57h+var_CC], 2
0x18005123c  mov     r8, rax
0x18005123f  lea     rdx, [rbp+57h+var_D0]
0x180051243  lea     rcx, [rbp+57h+pExceptionObject]
0x180051247  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18005124c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180051253  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180051257  call    _CxxThrowException_0
0x18005125d  lea     rdx, aFileShareAlrea; "file share already detached"
0x180051264  lea     rcx, [rbp+57h+var_C0]
0x180051268  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005126d  nop
0x18005126e  mov     [rbp+57h+var_D0], 2
0x180051275  mov     [rbp+57h+var_CC], 7
0x18005127c  mov     r8, rax
0x18005127f  lea     rdx, [rbp+57h+var_D0]
0x180051283  lea     rcx, [rbp+57h+pExceptionObject]
0x180051287  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18005128c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180051293  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180051297  call    _CxxThrowException_0
```
