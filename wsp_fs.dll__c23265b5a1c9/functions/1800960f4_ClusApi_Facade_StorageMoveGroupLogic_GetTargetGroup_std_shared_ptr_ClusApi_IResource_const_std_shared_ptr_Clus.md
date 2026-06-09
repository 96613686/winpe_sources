# ClusApi::Facade::StorageMoveGroupLogic::GetTargetGroup(std::shared_ptr<ClusApi::IResource> const &,std::shared_ptr<ClusApi::IGroup> &)

- ea: `0x1800960f4`
- end: `0x1800961ed`
- name: `?GetTargetGroup@StorageMoveGroupLogic@Facade@ClusApi@@AEBAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@AEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180096200`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000e14c`
- `0x1800960f4`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180096172`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180096172`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClusApi::Facade::StorageMoveGroupLogic::GetTargetGroup(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rdx
  int v7; // eax
  const WCHAR *v8; // rax
  PCNZWCH lpString2; // r10
  unsigned int v10; // ebx
  _QWORD *v12; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-48h] BYREF

  if ( *(_QWORD *)(a1 + 8) )
  {
    std::wstring::wstring(v13);
    v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 96LL))(*v6, v13);
    if ( v7 < 0 )
    {
LABEL_5:
      v10 = v7;
      std::wstring::_Tidy_deallocate(v13);
      return v10;
    }
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 24);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v13);
    if ( CompareStringW(0x400u, 1u, v8, -1, lpString2, -1) == 2 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 64) + 136LL))(*(_QWORD *)(a1 + 64), a3);
      goto LABEL_5;
    }
    std::wstring::_Tidy_deallocate(v13);
  }
  v12 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 80LL))(*a2);
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v12 + 128LL))(*v12, a3);
}

```

## disassembly

```asm
0x1800960f4  push    rbx
0x1800960f6  push    rsi
0x1800960f7  push    rdi
0x1800960f8  sub     rsp, 60h
0x1800960fc  mov     rax, cs:__security_cookie
0x180096103  xor     rax, rsp
0x180096106  mov     [rsp+78h+var_28], rax
0x18009610b  mov     rdi, r8
0x18009610e  mov     rsi, rdx
0x180096111  mov     rbx, rcx
0x180096114  cmp     qword ptr [rcx+8], 0
0x180096119  jz      loc_1800961C7
0x18009611f  lea     rcx, [rsp+78h+var_48]
0x180096124  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180096129  nop
0x18009612a  mov     rcx, [rdx]
0x18009612d  mov     rax, [rcx]
0x180096130  lea     rdx, [rsp+78h+var_48]
0x180096135  mov     rax, [rax+60h]
0x180096139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009613e  test    eax, eax
0x180096140  js      short loc_180096199
0x180096142  lea     rcx, [rbx+18h]
0x180096146  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009614b  mov     r10, rax
0x18009614e  lea     rcx, [rsp+78h+var_48]
0x180096153  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180096158  mov     r8, rax; lpString1
0x18009615b  or      r9d, 0FFFFFFFFh; cchCount1
0x18009615f  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180096164  mov     [rsp+78h+lpString2], r10; lpString2
0x180096169  lea     edx, [r9+2]; dwCmpFlags
0x18009616d  mov     ecx, 400h; Locale
0x180096172  call    cs:__imp_CompareStringW
0x180096179  nop     dword ptr [rax+rax+00h]
0x18009617e  cmp     eax, 2
0x180096181  jnz     short loc_1800961BD
0x180096183  mov     rcx, [rbx+40h]
0x180096187  mov     rax, [rcx]
0x18009618a  mov     rdx, rdi
0x18009618d  mov     rax, [rax+88h]
0x180096194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096199  mov     ebx, eax
0x18009619b  lea     rcx, [rsp+78h+var_48]
0x1800961a0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800961a5  mov     eax, ebx
0x1800961a7  mov     rcx, [rsp+78h+var_28]
0x1800961ac  xor     rcx, rsp; StackCookie
0x1800961af  call    __security_check_cookie
0x1800961b4  add     rsp, 60h
0x1800961b8  pop     rdi
0x1800961b9  pop     rsi
0x1800961ba  pop     rbx
0x1800961bb  retn
0x1800961bd  lea     rcx, [rsp+78h+var_48]
0x1800961c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800961c7  mov     rcx, [rsi]
0x1800961ca  mov     rax, [rcx]
0x1800961cd  mov     rax, [rax+50h]
0x1800961d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800961d6  mov     rcx, [rax]
0x1800961d9  mov     rax, [rcx]
0x1800961dc  mov     rdx, rdi
0x1800961df  mov     rax, [rax+80h]
0x1800961e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800961eb  jmp     short loc_1800961A7
```
