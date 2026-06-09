# ClusApi::Facade::StorageMoveGroupLogic::ShouldDeleteResource(std::shared_ptr<ClusApi::IResource> const &,int *)

- ea: `0x1800975c0`
- end: `0x18009772d`
- name: `?ShouldDeleteResource@StorageMoveGroupLogic@Facade@ClusApi@@AEBAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@PEAH@Z`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180096200`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d600`
- `0x18000e14c`
- `0x1800975c0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800976cc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800976cc`

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
0x1800975c0  mov     [rsp-8+arg_18], rbx
0x1800975c5  push    rbp
0x1800975c6  push    rsi
0x1800975c7  push    rdi
0x1800975c8  lea     rbp, [rsp-47h]
0x1800975cd  sub     rsp, 0B0h
0x1800975d4  mov     rax, cs:__security_cookie
0x1800975db  xor     rax, rsp
0x1800975de  mov     [rbp+57h+var_20], rax
0x1800975e2  mov     rsi, r8
0x1800975e5  mov     rdi, rcx
0x1800975e8  lea     rcx, [rbp+57h+var_40]
0x1800975ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800975f1  nop
0x1800975f2  lea     rcx, [rbp+57h+var_60]
0x1800975f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800975fb  nop
0x1800975fc  lea     rcx, [rbp+57h+var_80]
0x180097600  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180097605  nop
0x180097606  xorps   xmm1, xmm1
0x180097609  movdqu  xmmword ptr [rbp+57h+var_90], xmm1
0x18009760e  mov     dword ptr [r8], 0
0x180097615  mov     rcx, [rdx]
0x180097618  mov     rax, [rcx]
0x18009761b  lea     r9, [rbp+57h+var_40]
0x18009761f  xor     r8d, r8d
0x180097622  xor     edx, edx
0x180097624  mov     rax, [rax+78h]
0x180097628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009762d  mov     ebx, eax
0x18009762f  test    eax, eax
0x180097631  js      loc_1800976DF
0x180097637  mov     rcx, [rdi+40h]
0x18009763b  mov     rax, [rcx]
0x18009763e  lea     rdx, [rbp+57h+var_60]
0x180097642  mov     rax, [rax+150h]
0x180097649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009764e  mov     ebx, eax
0x180097650  test    eax, eax
0x180097652  js      loc_1800976DF
0x180097658  mov     r9, [rdi+40h]
0x18009765c  mov     r8, [r9]
0x18009765f  lea     rcx, [rbp+57h+var_40]
0x180097663  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180097668  mov     rdx, rax
0x18009766b  mov     rax, [r8+78h]
0x18009766f  lea     r8, [rbp+57h+var_90]
0x180097673  mov     rcx, r9
0x180097676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009767b  mov     ebx, eax
0x18009767d  test    eax, eax
0x18009767f  js      short loc_1800976DF
0x180097681  mov     rcx, [rbp+57h+var_90]
0x180097685  mov     rax, [rcx]
0x180097688  lea     rdx, [rbp+57h+var_80]
0x18009768c  mov     rax, [rax+60h]
0x180097690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097695  mov     ebx, eax
0x180097697  test    eax, eax
0x180097699  js      short loc_1800976DF
0x18009769b  lea     rcx, [rbp+57h+var_80]
0x18009769f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800976a4  mov     rdx, rax
0x1800976a7  lea     rcx, [rbp+57h+var_60]
0x1800976ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800976b0  mov     r8, rax; lpString1
0x1800976b3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800976b7  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x1800976bc  mov     [rsp+0C0h+lpString2], rdx; lpString2
0x1800976c1  lea     edi, [r9+2]
0x1800976c5  mov     edx, edi; dwCmpFlags
0x1800976c7  mov     ecx, 400h; Locale
0x1800976cc  call    cs:__imp_CompareStringW
0x1800976d3  nop     dword ptr [rax+rax+00h]
0x1800976d8  cmp     eax, 2
0x1800976db  jnz     short loc_1800976DF
0x1800976dd  mov     [rsi], edi
0x1800976df  mov     rcx, [rbp+57h+var_90+8]; this
0x1800976e3  test    rcx, rcx
0x1800976e6  jz      short loc_1800976EE
0x1800976e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800976ed  nop
0x1800976ee  lea     rcx, [rbp+57h+var_80]
0x1800976f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800976f7  nop
0x1800976f8  lea     rcx, [rbp+57h+var_60]
0x1800976fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180097701  nop
0x180097702  lea     rcx, [rbp+57h+var_40]
0x180097706  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009770b  mov     eax, ebx
0x18009770d  mov     rcx, [rbp+57h+var_20]
0x180097711  xor     rcx, rsp; StackCookie
0x180097714  call    __security_check_cookie
0x180097719  mov     rbx, [rsp+0C0h+arg_18]
0x180097721  add     rsp, 0B0h
0x180097728  pop     rdi
0x180097729  pop     rsi
0x18009772a  pop     rbp
0x18009772b  retn
```
