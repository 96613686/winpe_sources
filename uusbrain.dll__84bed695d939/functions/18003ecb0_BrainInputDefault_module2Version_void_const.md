# BrainInputDefault::module2Version(void const *)

- ea: `0x18003ecb0`
- end: `0x18003edf7`
- name: `?module2Version@BrainInputDefault@@UEBA?AV?$optional@VUusVersion@@@std@@PEBX@Z`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800295e8`
- `0x180029644`
- `0x1800343b0`
- `0x18003e1bc`
- `0x18003ecb0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed23`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrainInputDefault::module2Version(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  unsigned __int64 ModuleVersion; // rsi
  char v6; // bl
  char v7; // dl
  char v8; // al
  __int64 result; // rax
  const char *pv; // [rsp+20h] [rbp-98h]
  LPVOID pva; // [rsp+20h] [rbp-98h] BYREF
  __int64 v12; // [rsp+28h] [rbp-90h]
  int v13; // [rsp+30h] [rbp-88h]
  _QWORD v14[2]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-68h] BYREF
  char v16; // [rsp+60h] [rbp-58h]
  _QWORD v17[2]; // [rsp+68h] [rbp-50h] BYREF
  char v18; // [rsp+78h] [rbp-40h]
  WCHAR tstrFilename[28]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    v12 = a2;
    v13 = 0;
    if ( a3 )
    {
      pva = 0;
      wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
        (char *)&pva,
        a2,
        a3);
      v4 = -1;
      do
        ++v4;
      while ( *((_WORD *)pva + v4) );
      v14[0] = pva;
      v14[1] = v4;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(tstrFilename, (__int64)v14);
      if ( pva )
        CoTaskMemFree(pva);
      ModuleVersion = ModuleVersion::GetModuleVersion(tstrFilename);
      std::wstring::_Tidy_deallocate((__int64)tstrFilename);
      v15[0] = &UusVersion::`vftable';
      v15[1] = ModuleVersion;
      v16 = 1;
      v6 = 123;
      v7 = 1;
      v8 = v18;
    }
    else
    {
      v8 = 0;
      v18 = 0;
      v6 = 12;
      ModuleVersion = v17[1];
      v7 = 0;
    }
    *(_BYTE *)(a2 + 16) = 0;
    if ( v7 )
    {
      *(_QWORD *)a2 = &UusVersion::`vftable';
      *(_QWORD *)(a2 + 8) = ModuleVersion;
      *(_BYTE *)(a2 + 16) = 1;
    }
    if ( (v6 & 4) != 0 )
    {
      v6 &= ~4u;
      if ( v8 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v17[0])(v17, 0);
    }
    if ( (v6 & 2) != 0 && v16 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v15[0])(v15, 0);
    result = a2;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainInputDefault.cpp",
      "Unable to get the caller's (of the brain session) file version for telemetry!",
      pv);
    *(_BYTE *)(v12 + 16) = 0;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18003ecb0  mov     [rsp+arg_0], rbx
0x18003ecb5  push    rsi
0x18003ecb6  push    rdi
0x18003ecb7  push    r14
0x18003ecb9  sub     rsp, 0A0h
0x18003ecc0  mov     rdi, rdx
0x18003ecc3  mov     [rsp+0B8h+var_90], rdx
0x18003ecc8  xor     r14d, r14d
0x18003eccb  mov     [rsp+0B8h+var_88], r14d
0x18003ecd0  test    r8, r8
0x18003ecd3  jz      loc_18003ED6A
0x18003ecd9  mov     [rsp+0B8h+pv], r14
0x18003ecde  lea     rcx, [rsp+0B8h+pv]
0x18003ece3  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18003ece8  nop
0x18003ece9  mov     rax, [rsp+0B8h+pv]
0x18003ecee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ecf2  inc     rcx
0x18003ecf5  cmp     [rax+rcx*2], r14w
0x18003ecfa  jnz     short loc_18003ECF2
0x18003ecfc  mov     [rsp+0B8h+var_78], rax
0x18003ed01  mov     [rsp+0B8h+var_70], rcx
0x18003ed06  lea     rdx, [rsp+0B8h+var_78]
0x18003ed0b  lea     rcx, [rsp+0B8h+tstrFilename]
0x18003ed13  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003ed18  nop
0x18003ed19  mov     rcx, [rsp+0B8h+pv]; pv
0x18003ed1e  test    rcx, rcx
0x18003ed21  jz      short loc_18003ED2A
0x18003ed23  call    cs:__imp_CoTaskMemFree
0x18003ed29  nop
0x18003ed2a  lea     rcx, [rsp+0B8h+tstrFilename]; lptstrFilename
0x18003ed32  call    ?GetModuleVersion@ModuleVersion@@SA_KAEBVpath@filesystem@std@@@Z; ModuleVersion::GetModuleVersion(std::filesystem::path const &)
0x18003ed37  mov     rsi, rax
0x18003ed3a  lea     rcx, [rsp+0B8h+tstrFilename]
0x18003ed42  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ed47  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003ed4e  mov     [rsp+0B8h+var_68], rcx
0x18003ed53  mov     [rsp+0B8h+var_60], rsi
0x18003ed58  mov     [rsp+0B8h+var_58], 1
0x18003ed5d  mov     ebx, 7Bh ; '{'
0x18003ed62  mov     dl, 1
0x18003ed64  mov     al, [rsp+0B8h+var_40]
0x18003ed68  jmp     short loc_18003ED85
0x18003ed6a  mov     al, r14b
0x18003ed6d  mov     [rsp+0B8h+var_40], al
0x18003ed71  mov     ebx, 0Ch
0x18003ed76  mov     rsi, [rsp+0B8h+var_48]
0x18003ed7b  mov     dl, r14b
0x18003ed7e  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003ed85  mov     [rdi+10h], r14b
0x18003ed89  test    dl, dl
0x18003ed8b  jz      short loc_18003ED98
0x18003ed8d  mov     [rdi], rcx
0x18003ed90  mov     [rdi+8], rsi
0x18003ed94  mov     byte ptr [rdi+10h], 1
0x18003ed98  test    bl, 4
0x18003ed9b  jz      short loc_18003EDB8
0x18003ed9d  and     ebx, 0FFFFFFFBh
0x18003eda0  test    al, al
0x18003eda2  jz      short loc_18003EDB8
0x18003eda4  mov     rax, [rsp+0B8h+var_50]
0x18003eda9  xor     edx, edx
0x18003edab  lea     rcx, [rsp+0B8h+var_50]
0x18003edb0  mov     rax, [rax]
0x18003edb3  call    _guard_dispatch_icall
0x18003edb8  test    bl, 2
0x18003edbb  jz      short loc_18003EDD8
0x18003edbd  cmp     [rsp+0B8h+var_58], r14b
0x18003edc2  jz      short loc_18003EDD8
0x18003edc4  mov     rcx, [rsp+0B8h+var_68]
0x18003edc9  mov     rax, [rcx]
0x18003edcc  xor     edx, edx
0x18003edce  lea     rcx, [rsp+0B8h+var_68]
0x18003edd3  call    _guard_dispatch_icall
0x18003edd8  mov     rax, rdi
0x18003eddb  jmp     short loc_18003EDE2
0x18003eddd  mov     rax, [rsp+0B8h+var_90]
0x18003ede2  mov     rbx, [rsp+0B8h+arg_0]
0x18003edea  add     rsp, 0A0h
0x18003edf1  pop     r14
0x18003edf3  pop     rdi
0x18003edf4  pop     rsi
0x18003edf5  retn
```
