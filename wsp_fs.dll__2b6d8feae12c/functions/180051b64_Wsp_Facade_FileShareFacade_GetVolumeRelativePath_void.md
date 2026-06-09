# Wsp::Facade::FileShareFacade::GetVolumeRelativePath(void)

- ea: `0x180051b64`
- end: `0x180051c6e`
- name: `?GetVolumeRelativePath@FileShareFacade@Facade@Wsp@@QEBA?AV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180048938`

## callees

- `0x180002a94`
- `0x18000dd74`
- `0x180013940`
- `0x180014630`
- `0x1800190b4`
- `0x180025888`
- `0x180047e98`
- `0x180051b64`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180051bd3`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180051bd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Wsp::Facade::FileShareFacade::GetVolumeRelativePath(__int64 *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  DWORD v4; // ebx
  const WCHAR *v5; // rax
  unsigned __int64 v6; // rsi
  const WCHAR *v7; // rax
  PCNZWCH v8; // r9
  void *v9; // rbx
  LPWSTR lpszVolumePathName[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF
  void *v13; // [rsp+80h] [rbp+30h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL))(v3, &v12);
    if ( v12 )
    {
      v4 = *(_DWORD *)(v12 + 16);
      std::vector<wchar_t>::vector<wchar_t>(lpszVolumePathName, v4);
      v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
      if ( !GetVolumePathNameW(v5, lpszVolumePathName[0], v4) )
        goto LABEL_6;
      v6 = -1;
      do
        ++v6;
      while ( lpszVolumePathName[0][v6] );
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
      if ( (unsigned int)ClRtlStrNICmp(v8, v7, v6) )
      {
LABEL_6:
        *a2 = 0;
      }
      else
      {
        v9 = operator new(0x20u);
        v13 = v9;
        std::wstring::wstring(v9, v12, v6);
        v13 = 0;
        *a2 = v9;
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v13);
      }
      std::vector<unsigned short>::_Tidy(lpszVolumePathName);
    }
    else
    {
      *a2 = 0;
    }
    std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v12);
  }
  else
  {
    *a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180051b64  mov     [rsp-18h+arg_8], rbx
0x180051b69  mov     [rsp-18h+arg_18], rsi
0x180051b6e  push    rbp
0x180051b6f  push    rdi
0x180051b70  push    r14
0x180051b72  mov     rbp, rsp
0x180051b75  sub     rsp, 50h
0x180051b79  mov     rdi, rdx
0x180051b7c  xor     r14d, r14d
0x180051b7f  mov     rcx, [rcx]
0x180051b82  test    rcx, rcx
0x180051b85  jnz     short loc_180051B8F
0x180051b87  mov     [rdx], r14
0x180051b8a  jmp     loc_180051C56
0x180051b8f  mov     rax, [rcx]
0x180051b92  lea     rdx, [rbp+arg_0]
0x180051b96  mov     rax, [rax+38h]
0x180051b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b9f  nop
0x180051ba0  mov     rax, [rbp+arg_0]
0x180051ba4  test    rax, rax
0x180051ba7  jnz     short loc_180051BB1
0x180051ba9  mov     [rdi], r14
0x180051bac  jmp     loc_180051C4D
0x180051bb1  mov     ebx, [rax+10h]
0x180051bb4  mov     edx, ebx
0x180051bb6  lea     rcx, [rbp+lpszVolumePathName]
0x180051bba  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180051bbf  nop
0x180051bc0  mov     rcx, [rbp+arg_0]
0x180051bc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180051bc9  mov     r8d, ebx; cchBufferLength
0x180051bcc  mov     rdx, [rbp+lpszVolumePathName]; lpszVolumePathName
0x180051bd0  mov     rcx, rax; lpszFileName
0x180051bd3  call    cs:__imp_GetVolumePathNameW
0x180051bd9  test    eax, eax
0x180051bdb  jnz     short loc_180051BE2
0x180051bdd  mov     [rdi], r14
0x180051be0  jmp     short loc_180051C43
0x180051be2  mov     r9, [rbp+lpszVolumePathName]
0x180051be6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180051bea  inc     rsi
0x180051bed  cmp     [r9+rsi*2], r14w
0x180051bf2  jnz     short loc_180051BEA
0x180051bf4  mov     rcx, [rbp+arg_0]
0x180051bf8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180051bfd  mov     r8, rsi; cchCount2
0x180051c00  mov     rdx, rax; lpString2
0x180051c03  mov     rcx, r9; lpString1
0x180051c06  call    ?ClRtlStrNICmp@@YAHPEB_W0_K@Z; ClRtlStrNICmp(wchar_t const *,wchar_t const *,unsigned __int64)
0x180051c0b  test    eax, eax
0x180051c0d  jnz     short loc_180051BDD
0x180051c0f  lea     ecx, [rax+20h]; Size
0x180051c12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051c17  mov     rbx, rax
0x180051c1a  mov     [rbp+arg_10], rax
0x180051c1e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180051c22  mov     r8, rsi
0x180051c25  mov     rdx, [rbp+arg_0]
0x180051c29  mov     rcx, rax
0x180051c2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<wchar_t> const &)
0x180051c31  nop
0x180051c32  mov     [rbp+arg_10], r14
0x180051c36  mov     [rdi], rbx
0x180051c39  lea     rcx, [rbp+arg_10]
0x180051c3d  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180051c42  nop
0x180051c43  lea     rcx, [rbp+lpszVolumePathName]
0x180051c47  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180051c4c  nop
0x180051c4d  lea     rcx, [rbp+arg_0]
0x180051c51  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180051c56  mov     rax, rdi
0x180051c59  lea     r11, [rsp+50h+var_s0]
0x180051c5e  mov     rbx, [r11+28h]
0x180051c62  mov     rsi, [r11+38h]
0x180051c66  mov     rsp, r11
0x180051c69  pop     r14
0x180051c6b  pop     rdi
0x180051c6c  pop     rbp
0x180051c6d  retn
```
