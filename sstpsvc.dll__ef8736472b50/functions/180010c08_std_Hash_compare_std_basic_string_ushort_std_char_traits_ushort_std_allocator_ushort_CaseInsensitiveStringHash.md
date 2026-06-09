# std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010c08`
- end: `0x180010ca4`
- name: `??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012dfc`
- `0x180013824`
- `0x180013ed8`

## callees

- `0x1800104f4`
- `0x180010c08`
- `0x1800134bc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010c64`
- `msvcrt!_wcsicmp` at `0x180010c64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rcx
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v14[40]; // [rsp+48h] [rbp-30h] BYREF

  v4 = std::wstring::wstring(&v13, a3);
  v5 = std::wstring::wstring(v14, a2);
  v6 = v5;
  if ( *(_QWORD *)(v4 + 24) < 8u )
    v7 = (const wchar_t *)v4;
  else
    v7 = *(const wchar_t **)v4;
  if ( *(_QWORD *)(v5 + 24) < 8u )
    v8 = (const wchar_t *)v5;
  else
    v8 = *(const wchar_t **)v5;
  v9 = _wcsicmp(v8, v7);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v6, v10, 0);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v4, v11, 0);
  return v9 != 0;
}

```

## disassembly

```asm
0x180010c08  mov     r11, rsp
0x180010c0b  mov     [r11+10h], rbx
0x180010c0f  mov     [r11+18h], rsi
0x180010c13  mov     [r11+8], rcx
0x180010c17  push    rdi
0x180010c18  sub     rsp, 70h
0x180010c1c  mov     rbx, rdx
0x180010c1f  lea     rax, [r11-58h]
0x180010c23  mov     [r11+8], rax
0x180010c27  mov     rdx, r8
0x180010c2a  lea     rcx, [r11-58h]
0x180010c2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010c33  mov     rsi, rax
0x180010c36  mov     rdx, rbx
0x180010c39  lea     rcx, [rsp+78h+var_30]
0x180010c3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010c43  mov     rdi, rax
0x180010c46  cmp     qword ptr [rsi+18h], 8
0x180010c4b  jb      short loc_180010C52
0x180010c4d  mov     rdx, [rsi]
0x180010c50  jmp     short loc_180010C55
0x180010c52  mov     rdx, rsi; String2
0x180010c55  cmp     qword ptr [rax+18h], 8
0x180010c5a  jb      short loc_180010C61
0x180010c5c  mov     rcx, [rax]
0x180010c5f  jmp     short loc_180010C64
0x180010c61  mov     rcx, rdi; String1
0x180010c64  call    cs:__imp__wcsicmp
0x180010c6b  nop     dword ptr [rax+rax+00h]
0x180010c70  mov     ebx, eax
0x180010c72  xor     r8d, r8d
0x180010c75  mov     dl, 1
0x180010c77  mov     rcx, rdi
0x180010c7a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180010c7f  xor     r8d, r8d
0x180010c82  mov     dl, 1
0x180010c84  mov     rcx, rsi
0x180010c87  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180010c8c  test    ebx, ebx
0x180010c8e  setnz   al
0x180010c91  lea     r11, [rsp+78h+var_8]
0x180010c96  mov     rbx, [r11+18h]
0x180010c9a  mov     rsi, [r11+20h]
0x180010c9e  mov     rsp, r11
0x180010ca1  pop     rdi
0x180010ca2  retn
```
