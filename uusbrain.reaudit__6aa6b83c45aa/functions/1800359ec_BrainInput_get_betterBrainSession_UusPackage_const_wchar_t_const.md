# BrainInput::get_betterBrainSession(UusPackage const &,wchar_t const *)

- ea: `0x1800359ec`
- end: `0x180035b28`
- name: `?get_betterBrainSession@BrainInput@@QEBAPEAXAEBVUusPackage@@PEB_W@Z`
- size: `316`
- prototype: `void *(BrainInput *__hidden this, const struct UusPackage *, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180037064`

## callees

- `0x1800089f4`
- `0x180028728`
- `0x180029344`
- `0x180029644`
- `0x1800359ec`
- `0x18003d720`
- `0x18003d7a8`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x180035b07`: `Requesting specific brain when we already did on the previous call.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrainInput::get_betterBrainSession(BrainInput *this, const struct UusPackage *a2, const wchar_t *a3)
{
  int v5; // r9d
  unsigned int v6; // r8d
  const wchar_t *v7; // rdx
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *, __int64, __int64 *); // r14
  __int64 (__fastcall *v10)(_QWORD, _BYTE *, __int64, __int64 *); // r15
  __int64 v11; // rbx
  __int64 v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // [rsp+38h] [rbp-19h] BYREF
  int v15; // [rsp+40h] [rbp-11h]
  int v16; // [rsp+44h] [rbp-Dh]
  __int64 v17; // [rsp+48h] [rbp-9h]
  _QWORD pExceptionObject[3]; // [rsp+50h] [rbp-1h] BYREF
  unsigned __int64 v19; // [rsp+68h] [rbp+17h]
  _BYTE v20[40]; // [rsp+70h] [rbp+1Fh] BYREF

  v5 = *((_DWORD *)this + 14);
  if ( v5 + 1 <= 2 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, __int64, __int64 *))*((_QWORD *)this + 2);
    v10 = **v9;
    if ( v5 < 0 )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "Requesting specific brain when we already did on the previous call.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v17 = 2307;
    v14 = 24;
    v15 = v5 + 1;
    v16 = 0;
    v11 = *((_QWORD *)this + 3);
    std::wstring::wstring(v20, (char *)a2 + 8);
    v12 = v10(v9, v20, v11, &v14);
    std::wstring::_Tidy_deallocate(v20);
    if ( !v12 )
    {
      UusVersion::GetString((char *)a2 + 48, pExceptionObject);
      v13 = (const wchar_t *)pExceptionObject;
      if ( v19 > 7 )
        v13 = (const wchar_t *)pExceptionObject[0];
      uus::UndockedUpdateTelemetry::UusFailedToLoadAnointedPackage(a3, v13);
      std::wstring::_Tidy_deallocate(pExceptionObject);
    }
    return v12;
  }
  else
  {
    UusVersion::GetString((char *)a2 + 48, pExceptionObject);
    v7 = (const wchar_t *)pExceptionObject;
    if ( v19 > 7 )
      v7 = (const wchar_t *)pExceptionObject[0];
    uus::UndockedUpdateTelemetry::UusGetBrainSessionMaxRecursion(a3, v7, v6);
    std::wstring::_Tidy_deallocate(pExceptionObject);
    return 0;
  }
}

```

## disassembly

```asm
0x1800359ec  mov     rax, rsp
0x1800359ef  mov     [rax+10h], rbx
0x1800359f3  mov     [rax+18h], rsi
0x1800359f7  mov     [rax+20h], rdi
0x1800359fb  push    rbp
0x1800359fc  push    r14
0x1800359fe  push    r15
0x180035a00  lea     rbp, [rax-5Fh]
0x180035a04  sub     rsp, 90h
0x180035a0b  mov     rsi, r8
0x180035a0e  mov     rdi, rdx
0x180035a11  mov     r9d, [rcx+38h]
0x180035a15  lea     edx, [r9+1]
0x180035a19  cmp     edx, 2
0x180035a1c  jle     short loc_180035A51
0x180035a1e  lea     rcx, [rdi+30h]
0x180035a22  lea     rdx, [rbp+57h+pExceptionObject]
0x180035a26  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180035a2b  lea     rdx, [rbp+57h+pExceptionObject]
0x180035a2f  cmp     [rbp+57h+var_40], 7
0x180035a34  cmova   rdx, [rbp+57h+pExceptionObject]; wchar_t *
0x180035a39  mov     rcx, rsi; wchar_t *
0x180035a3c  call    ?UusGetBrainSessionMaxRecursion@UndockedUpdateTelemetry@uus@@SAXPEB_W0I@Z; uus::UndockedUpdateTelemetry::UusGetBrainSessionMaxRecursion(wchar_t const *,wchar_t const *,uint)
0x180035a41  lea     rcx, [rbp+57h+pExceptionObject]
0x180035a45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a4a  xor     eax, eax
0x180035a4c  jmp     loc_180035AEA
0x180035a51  mov     r14, [rcx+10h]
0x180035a55  mov     rax, [r14]
0x180035a58  mov     r15, [rax]
0x180035a5b  shr     r9d, 1Fh
0x180035a5f  test    r9b, r9b
0x180035a62  jnz     loc_180035B07
0x180035a68  mov     [rbp+57h+var_60], 903h
0x180035a70  mov     [rbp+57h+var_70], 18h
0x180035a78  mov     [rbp+57h+var_68], edx
0x180035a7b  mov     [rbp+57h+var_64], 0
0x180035a82  mov     rbx, [rcx+18h]
0x180035a86  lea     rdx, [rdi+8]
0x180035a8a  lea     rcx, [rbp+57h+var_38]
0x180035a8e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035a93  nop
0x180035a94  lea     r9, [rbp+57h+var_70]
0x180035a98  mov     r8, rbx
0x180035a9b  lea     rdx, [rbp+57h+var_38]
0x180035a9f  mov     rcx, r14
0x180035aa2  mov     rax, r15
0x180035aa5  call    _guard_dispatch_icall
0x180035aaa  mov     rbx, rax
0x180035aad  lea     rcx, [rbp+57h+var_38]
0x180035ab1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ab6  test    rbx, rbx
0x180035ab9  jnz     short loc_180035AE7
0x180035abb  lea     rcx, [rdi+30h]
0x180035abf  lea     rdx, [rbp+57h+pExceptionObject]
0x180035ac3  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180035ac8  lea     rdx, [rbp+57h+pExceptionObject]
0x180035acc  cmp     [rbp+57h+var_40], 7
0x180035ad1  cmova   rdx, [rbp+57h+pExceptionObject]; wchar_t *
0x180035ad6  mov     rcx, rsi; wchar_t *
0x180035ad9  call    ?UusFailedToLoadAnointedPackage@UndockedUpdateTelemetry@uus@@SAXPEB_W0@Z; uus::UndockedUpdateTelemetry::UusFailedToLoadAnointedPackage(wchar_t const *,wchar_t const *)
0x180035ade  lea     rcx, [rbp+57h+pExceptionObject]
0x180035ae2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ae7  mov     rax, rbx
0x180035aea  lea     r11, [rsp+0A0h+var_10]
0x180035af2  mov     rbx, [r11+28h]
0x180035af6  mov     rsi, [r11+30h]
0x180035afa  mov     rdi, [r11+38h]
0x180035afe  mov     rsp, r11
0x180035b01  pop     r15
0x180035b03  pop     r14
0x180035b05  pop     rbp
0x180035b06  retn
0x180035b07  lea     rdx, aRequestingSpec; "Requesting specific brain when we alrea"...
0x180035b0e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180035b12  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180035b17  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180035b1e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180035b22  call    _CxxThrowException
```
