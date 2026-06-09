# Wsp::Facade::FileShareFacade::GetVolumeRelativePath(void)

- ea: `0x180052b44`
- end: `0x180052c55`
- name: `?GetVolumeRelativePath@FileShareFacade@Facade@Wsp@@QEBA?AV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180049b04`

## callees

- `0x180002af4`
- `0x18000e14c`
- `0x180013ea4`
- `0x180014c94`
- `0x180019a00`
- `0x180026588`
- `0x18004905c`
- `0x180052b44`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180052bb3`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180052bb3`

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
        std::wstring::wstring(v9, v12, v6, -1);
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
0x180052b44  mov     [rsp-18h+arg_8], rbx
0x180052b49  mov     [rsp-18h+arg_18], rsi
0x180052b4e  push    rbp
0x180052b4f  push    rdi
0x180052b50  push    r14
0x180052b52  mov     rbp, rsp
0x180052b55  sub     rsp, 50h
0x180052b59  mov     rdi, rdx
0x180052b5c  xor     r14d, r14d
0x180052b5f  mov     rcx, [rcx]
0x180052b62  test    rcx, rcx
0x180052b65  jnz     short loc_180052B6F
0x180052b67  mov     [rdx], r14
0x180052b6a  jmp     loc_180052C3C
0x180052b6f  mov     rax, [rcx]
0x180052b72  lea     rdx, [rbp+arg_0]
0x180052b76  mov     rax, [rax+38h]
0x180052b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b7f  nop
0x180052b80  mov     rax, [rbp+arg_0]
0x180052b84  test    rax, rax
0x180052b87  jnz     short loc_180052B91
0x180052b89  mov     [rdi], r14
0x180052b8c  jmp     loc_180052C33
0x180052b91  mov     ebx, [rax+10h]
0x180052b94  mov     edx, ebx
0x180052b96  lea     rcx, [rbp+lpszVolumePathName]
0x180052b9a  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180052b9f  nop
0x180052ba0  mov     rcx, [rbp+arg_0]
0x180052ba4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180052ba9  mov     r8d, ebx; cchBufferLength
0x180052bac  mov     rdx, [rbp+lpszVolumePathName]; lpszVolumePathName
0x180052bb0  mov     rcx, rax; lpszFileName
0x180052bb3  call    cs:__imp_GetVolumePathNameW
0x180052bba  nop     dword ptr [rax+rax+00h]
0x180052bbf  test    eax, eax
0x180052bc1  jnz     short loc_180052BC8
0x180052bc3  mov     [rdi], r14
0x180052bc6  jmp     short loc_180052C29
0x180052bc8  mov     r9, [rbp+lpszVolumePathName]
0x180052bcc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052bd0  inc     rsi
0x180052bd3  cmp     [r9+rsi*2], r14w
0x180052bd8  jnz     short loc_180052BD0
0x180052bda  mov     rcx, [rbp+arg_0]
0x180052bde  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180052be3  mov     r8, rsi; cchCount2
0x180052be6  mov     rdx, rax; lpString2
0x180052be9  mov     rcx, r9; lpString1
0x180052bec  call    ?ClRtlStrNICmp@@YAHPEB_W0_K@Z; ClRtlStrNICmp(wchar_t const *,wchar_t const *,unsigned __int64)
0x180052bf1  test    eax, eax
0x180052bf3  jnz     short loc_180052BC3
0x180052bf5  lea     ecx, [rax+20h]; Size
0x180052bf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052bfd  mov     rbx, rax
0x180052c00  mov     [rbp+arg_10], rax
0x180052c04  or      r9, 0FFFFFFFFFFFFFFFFh
0x180052c08  mov     r8, rsi
0x180052c0b  mov     rdx, [rbp+arg_0]
0x180052c0f  mov     rcx, rax
0x180052c12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<wchar_t> const &)
0x180052c17  nop
0x180052c18  mov     [rbp+arg_10], r14
0x180052c1c  mov     [rdi], rbx
0x180052c1f  lea     rcx, [rbp+arg_10]
0x180052c23  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052c28  nop
0x180052c29  lea     rcx, [rbp+lpszVolumePathName]
0x180052c2d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180052c32  nop
0x180052c33  lea     rcx, [rbp+arg_0]
0x180052c37  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052c3c  mov     rax, rdi
0x180052c3f  lea     r11, [rsp+50h+var_s0]
0x180052c44  mov     rbx, [r11+28h]
0x180052c48  mov     rsi, [r11+38h]
0x180052c4c  mov     rsp, r11
0x180052c4f  pop     r14
0x180052c51  pop     rdi
0x180052c52  pop     rbp
0x180052c53  retn
```
