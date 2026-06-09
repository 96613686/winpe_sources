# _lambda_8d831eddfe3752f93790a35eaa4aecc3_::operator()(std::filesystem::path const &,char const *)

- ea: `0x18000cdfc`
- end: `0x18000cf10`
- name: `??R_lambda_8d831eddfe3752f93790a35eaa4aecc3_@@QEBAXAEBVpath@filesystem@std@@PEBD@Z`
- size: `276`
- prototype: `void __fastcall(__int64, const wchar_t *, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18001ac80`

## callees

- `0x180008f3c`
- `0x18000cdfc`
- `0x18000dc04`
- `0x1800252e0`
- `0x1800266b0`
- `0x180028728`
- `0x1800295e8`
- `0x180029644`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _lambda_8d831eddfe3752f93790a35eaa4aecc3_::operator()(__int64 a1, const wchar_t *a2, const char *a3)
{
  const char *v3; // rdi
  const wchar_t *v4; // rbx
  __int64 v6; // rdx
  char v7; // si
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  const struct std::filesystem::path *v10; // rdx
  const char *v11; // rax
  const wchar_t *v12; // rcx
  const std::exception *v13; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v14[2]; // [rsp+30h] [rbp-88h] BYREF
  char v15; // [rsp+40h] [rbp-78h]
  _QWORD v16[4]; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v17[9]; // [rsp+70h] [rbp-48h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = (__int64)std::filesystem::path::filename((std::filesystem *)a2, v17);
  std::wstring::wstring((__int64)v16, v6);
  UusVersion::TryStrToVer<wchar_t>(v14, v16);
  v7 = v15;
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v14[0])(v14, 0);
  std::wstring::_Tidy_deallocate((__int64)v16);
  std::wstring::_Tidy_deallocate((__int64)v17);
  if ( v7 )
  {
    ++**(_QWORD **)a1;
    v8 = v4;
    if ( *((_QWORD *)v4 + 3) > 7u )
      v8 = *(const wchar_t **)v4;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v14[0] = v8;
      v14[1] = v9;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v16, (__int64)v14);
      std::filesystem::remove_all((std::filesystem *)v16, v10);
      std::wstring::_Tidy_deallocate((__int64)v16);
      ++*(_QWORD *)(*(_QWORD *)a1 + 8LL);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v13) )
      {
        v11 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v13 + 8LL))(v13);
        v12 = a2;
        if ( *((_QWORD *)a2 + 3) > 7u )
          v12 = *(const wchar_t **)a2;
        uus::UndockedUpdateTelemetry::UusFailedToRemoveInvalidPackage(v12, v11);
        v3 = a3;
        v4 = a2;
        __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18000CEDD);
      }
    }
  }
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  uus::UndockedUpdateTelemetry::UusScavengeIgnoringInvalidPackage(v4, v3);
}

```

## disassembly

```asm
0x18000cdfc  mov     [rsp+arg_10], r8
0x18000ce01  mov     [rsp+arg_8], rdx
0x18000ce06  push    rbx
0x18000ce07  push    rsi
0x18000ce08  push    rdi
0x18000ce09  push    r14
0x18000ce0b  push    r15
0x18000ce0d  sub     rsp, 90h
0x18000ce14  mov     rdi, r8
0x18000ce17  mov     rbx, rdx
0x18000ce1a  mov     r14, rcx
0x18000ce1d  xor     r15d, r15d
0x18000ce20  lea     rdx, [rsp+0B8h+var_48]
0x18000ce25  mov     rcx, rbx
0x18000ce28  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x18000ce2d  nop
0x18000ce2e  mov     rdx, rax
0x18000ce31  lea     rcx, [rsp+0B8h+var_68]
0x18000ce36  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ce3b  nop
0x18000ce3c  lea     rdx, [rsp+0B8h+var_68]
0x18000ce41  lea     rcx, [rsp+0B8h+var_88]
0x18000ce46  call    ??$TryStrToVer@_W@UusVersion@@SA?AV?$optional@VUusVersion@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; UusVersion::TryStrToVer<wchar_t>(std::wstring const &)
0x18000ce4b  mov     sil, [rsp+0B8h+var_78]
0x18000ce50  test    sil, sil
0x18000ce53  jz      short loc_18000CE6A
0x18000ce55  mov     rax, [rsp+0B8h+var_88]
0x18000ce5a  xor     edx, edx
0x18000ce5c  lea     rcx, [rsp+0B8h+var_88]
0x18000ce61  mov     rax, [rax]
0x18000ce64  call    _guard_dispatch_icall
0x18000ce69  nop
0x18000ce6a  lea     rcx, [rsp+0B8h+var_68]
0x18000ce6f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ce74  nop
0x18000ce75  lea     rcx, [rsp+0B8h+var_48]
0x18000ce7a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ce7f  test    sil, sil
0x18000ce82  jz      short loc_18000CEED
0x18000ce84  mov     rax, [r14]
0x18000ce87  inc     qword ptr [rax]
0x18000ce8a  mov     rcx, rbx
0x18000ce8d  cmp     qword ptr [rbx+18h], 7
0x18000ce92  jbe     short loc_18000CE97
0x18000ce94  mov     rcx, [rbx]
0x18000ce97  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ce9b  inc     rax
0x18000ce9e  cmp     [rcx+rax*2], r15w
0x18000cea3  jnz     short loc_18000CE9B
0x18000cea5  mov     [rsp+0B8h+var_88], rcx
0x18000ceaa  mov     [rsp+0B8h+var_80], rax
0x18000ceaf  lea     rdx, [rsp+0B8h+var_88]
0x18000ceb4  lea     rcx, [rsp+0B8h+var_68]
0x18000ceb9  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000cebe  nop
0x18000cebf  lea     rcx, [rsp+0B8h+var_68]; this
0x18000cec4  call    ?remove_all@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::remove_all(std::filesystem::path const &)
0x18000cec9  nop
0x18000ceca  lea     rcx, [rsp+0B8h+var_68]
0x18000cecf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ced4  mov     rax, [r14]
0x18000ced7  inc     qword ptr [rax+8]
0x18000cedb  jmp     short loc_18000CEED
0x18000cedd  mov     rdi, [rsp+0B8h+arg_10]
0x18000cee5  mov     rbx, [rsp+0B8h+arg_8]
0x18000ceed  cmp     qword ptr [rbx+18h], 7
0x18000cef2  jbe     short loc_18000CEF7
0x18000cef4  mov     rbx, [rbx]
0x18000cef7  mov     rdx, rdi; char *
0x18000cefa  mov     rcx, rbx; wchar_t *
0x18000cefd  add     rsp, 90h
0x18000cf04  pop     r15
0x18000cf06  pop     r14
0x18000cf08  pop     rdi
0x18000cf09  pop     rsi
0x18000cf0a  pop     rbx
0x18000cf0b  jmp     ?UusScavengeIgnoringInvalidPackage@UndockedUpdateTelemetry@uus@@SAXPEB_WPEBD@Z; uus::UndockedUpdateTelemetry::UusScavengeIgnoringInvalidPackage(wchar_t const *,char const *)
```
