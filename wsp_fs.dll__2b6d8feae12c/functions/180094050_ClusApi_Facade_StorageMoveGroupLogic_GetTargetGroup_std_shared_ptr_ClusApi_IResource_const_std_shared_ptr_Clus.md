# ClusApi::Facade::StorageMoveGroupLogic::GetTargetGroup(std::shared_ptr<ClusApi::IResource> const &,std::shared_ptr<ClusApi::IGroup> &)

- ea: `0x180094050`
- end: `0x180094142`
- name: `?GetTargetGroup@StorageMoveGroupLogic@Facade@ClusApi@@AEBAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@AEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180094150`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000dd74`
- `0x180094050`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800940ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800940ce`

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
0x180094050  push    rbx
0x180094052  push    rsi
0x180094053  push    rdi
0x180094054  sub     rsp, 60h
0x180094058  mov     rax, cs:__security_cookie
0x18009405f  xor     rax, rsp
0x180094062  mov     [rsp+78h+var_28], rax
0x180094067  mov     rdi, r8
0x18009406a  mov     rsi, rdx
0x18009406d  mov     rbx, rcx
0x180094070  cmp     qword ptr [rcx+8], 0
0x180094075  jz      loc_18009411C
0x18009407b  lea     rcx, [rsp+78h+var_48]
0x180094080  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180094085  nop
0x180094086  mov     rcx, [rdx]
0x180094089  mov     rax, [rcx]
0x18009408c  lea     rdx, [rsp+78h+var_48]
0x180094091  mov     rax, [rax+60h]
0x180094095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009409a  test    eax, eax
0x18009409c  js      short loc_1800940EF
0x18009409e  lea     rcx, [rbx+18h]
0x1800940a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800940a7  mov     r10, rax
0x1800940aa  lea     rcx, [rsp+78h+var_48]
0x1800940af  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800940b4  mov     r8, rax; lpString1
0x1800940b7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800940bb  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x1800940c0  mov     [rsp+78h+lpString2], r10; lpString2
0x1800940c5  lea     edx, [r9+2]; dwCmpFlags
0x1800940c9  mov     ecx, 400h; Locale
0x1800940ce  call    cs:__imp_CompareStringW
0x1800940d4  cmp     eax, 2
0x1800940d7  jnz     short loc_180094112
0x1800940d9  mov     rcx, [rbx+40h]
0x1800940dd  mov     rax, [rcx]
0x1800940e0  mov     rdx, rdi
0x1800940e3  mov     rax, [rax+88h]
0x1800940ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940ef  mov     ebx, eax
0x1800940f1  lea     rcx, [rsp+78h+var_48]
0x1800940f6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800940fb  mov     eax, ebx
0x1800940fd  mov     rcx, [rsp+78h+var_28]
0x180094102  xor     rcx, rsp; StackCookie
0x180094105  call    __security_check_cookie
0x18009410a  add     rsp, 60h
0x18009410e  pop     rdi
0x18009410f  pop     rsi
0x180094110  pop     rbx
0x180094111  retn
0x180094112  lea     rcx, [rsp+78h+var_48]
0x180094117  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009411c  mov     rcx, [rsi]
0x18009411f  mov     rax, [rcx]
0x180094122  mov     rax, [rax+50h]
0x180094126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009412b  mov     rcx, [rax]
0x18009412e  mov     rax, [rcx]
0x180094131  mov     rdx, rdi
0x180094134  mov     rax, [rax+80h]
0x18009413b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094140  jmp     short loc_1800940FD
```
