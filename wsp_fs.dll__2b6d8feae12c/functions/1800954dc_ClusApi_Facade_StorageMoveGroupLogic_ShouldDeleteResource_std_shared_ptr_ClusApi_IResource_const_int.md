# ClusApi::Facade::StorageMoveGroupLogic::ShouldDeleteResource(std::shared_ptr<ClusApi::IResource> const &,int *)

- ea: `0x1800954dc`
- end: `0x180095642`
- name: `?ShouldDeleteResource@StorageMoveGroupLogic@Facade@ClusApi@@AEBAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@PEAH@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180094150`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000d298`
- `0x18000dd74`
- `0x1800954dc`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800955e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800955e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClusApi::Facade::StorageMoveGroupLogic::ShouldDeleteResource(__int64 a1, __int64 a2, _DWORD *a3)
{
  _DWORD *v5; // r8
  _QWORD *v6; // rdx
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rax
  PCNZWCH lpString2; // rdx
  std::_Ref_count_base *v14[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp+17h] BYREF

  std::wstring::wstring(v17);
  std::wstring::wstring(v16);
  std::wstring::wstring(v15);
  *(_OWORD *)v14 = 0;
  *v5 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)*v6 + 120LL))(*v6, 0, 0, v17);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 64) + 336LL))(*(_QWORD *)(a1 + 64), v16);
    if ( v7 >= 0 )
    {
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, std::_Ref_count_base **))(v9 + 120))(v10, v8, v14);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v14[0] + 96LL))(v14[0], v15);
        if ( v7 >= 0 )
        {
          std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v15);
          v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v16);
          if ( CompareStringW(0x400u, 1u, v11, -1, lpString2, -1) == 2 )
            *a3 = 1;
        }
      }
    }
  }
  if ( v14[1] )
    std::_Ref_count_base::_Decref(v14[1]);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v16);
  std::wstring::_Tidy_deallocate(v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800954dc  mov     [rsp-8+arg_18], rbx
0x1800954e1  push    rbp
0x1800954e2  push    rsi
0x1800954e3  push    rdi
0x1800954e4  lea     rbp, [rsp-47h]
0x1800954e9  sub     rsp, 0B0h
0x1800954f0  mov     rax, cs:__security_cookie
0x1800954f7  xor     rax, rsp
0x1800954fa  mov     [rbp+57h+var_20], rax
0x1800954fe  mov     rsi, r8
0x180095501  mov     rdi, rcx
0x180095504  lea     rcx, [rbp+57h+var_40]
0x180095508  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009550d  nop
0x18009550e  lea     rcx, [rbp+57h+var_60]
0x180095512  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180095517  nop
0x180095518  lea     rcx, [rbp+57h+var_80]
0x18009551c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180095521  nop
0x180095522  xorps   xmm1, xmm1
0x180095525  movdqu  xmmword ptr [rbp+57h+var_90], xmm1
0x18009552a  mov     dword ptr [r8], 0
0x180095531  mov     rcx, [rdx]
0x180095534  mov     rax, [rcx]
0x180095537  lea     r9, [rbp+57h+var_40]
0x18009553b  xor     r8d, r8d
0x18009553e  xor     edx, edx
0x180095540  mov     rax, [rax+78h]
0x180095544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095549  mov     ebx, eax
0x18009554b  test    eax, eax
0x18009554d  js      loc_1800955F5
0x180095553  mov     rcx, [rdi+40h]
0x180095557  mov     rax, [rcx]
0x18009555a  lea     rdx, [rbp+57h+var_60]
0x18009555e  mov     rax, [rax+150h]
0x180095565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009556a  mov     ebx, eax
0x18009556c  test    eax, eax
0x18009556e  js      loc_1800955F5
0x180095574  mov     r9, [rdi+40h]
0x180095578  mov     r8, [r9]
0x18009557b  lea     rcx, [rbp+57h+var_40]
0x18009557f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180095584  mov     rdx, rax
0x180095587  mov     rax, [r8+78h]
0x18009558b  lea     r8, [rbp+57h+var_90]
0x18009558f  mov     rcx, r9
0x180095592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095597  mov     ebx, eax
0x180095599  test    eax, eax
0x18009559b  js      short loc_1800955F5
0x18009559d  mov     rcx, [rbp+57h+var_90]
0x1800955a1  mov     rax, [rcx]
0x1800955a4  lea     rdx, [rbp+57h+var_80]
0x1800955a8  mov     rax, [rax+60h]
0x1800955ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955b1  mov     ebx, eax
0x1800955b3  test    eax, eax
0x1800955b5  js      short loc_1800955F5
0x1800955b7  lea     rcx, [rbp+57h+var_80]
0x1800955bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800955c0  mov     rdx, rax
0x1800955c3  lea     rcx, [rbp+57h+var_60]
0x1800955c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800955cc  mov     r8, rax; lpString1
0x1800955cf  or      r9d, 0FFFFFFFFh; cchCount1
0x1800955d3  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x1800955d8  mov     [rsp+0C0h+lpString2], rdx; lpString2
0x1800955dd  lea     edi, [r9+2]
0x1800955e1  mov     edx, edi; dwCmpFlags
0x1800955e3  mov     ecx, 400h; Locale
0x1800955e8  call    cs:__imp_CompareStringW
0x1800955ee  cmp     eax, 2
0x1800955f1  jnz     short loc_1800955F5
0x1800955f3  mov     [rsi], edi
0x1800955f5  mov     rcx, [rbp+57h+var_90+8]; this
0x1800955f9  test    rcx, rcx
0x1800955fc  jz      short loc_180095604
0x1800955fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180095603  nop
0x180095604  lea     rcx, [rbp+57h+var_80]
0x180095608  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009560d  nop
0x18009560e  lea     rcx, [rbp+57h+var_60]
0x180095612  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095617  nop
0x180095618  lea     rcx, [rbp+57h+var_40]
0x18009561c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095621  mov     eax, ebx
0x180095623  mov     rcx, [rbp+57h+var_20]
0x180095627  xor     rcx, rsp; StackCookie
0x18009562a  call    __security_check_cookie
0x18009562f  mov     rbx, [rsp+0C0h+arg_18]
0x180095637  add     rsp, 0B0h
0x18009563e  pop     rdi
0x18009563f  pop     rsi
0x180095640  pop     rbp
0x180095641  retn
```
