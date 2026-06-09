# ConfigBase::WriteRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong)

- ea: `0x180018bd4`
- end: `0x180018cd3`
- name: `?WriteRegEnumValue@ConfigBase@@IEBAXPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z`
- size: `255`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, struct _ENUM_NAMEVALUE_PAIR *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x1800062d4`
- `0x180012b94`
- `0x180018bd4`
- `0x18001f9cc`
- `0x18001fe50`

## pseudocode

```c
void __fastcall ConfigBase::WriteRegEnumValue(
        HKEY *this,
        const unsigned __int16 *a2,
        struct _ENUM_NAMEVALUE_PAIR *a3,
        unsigned int a4)
{
  const unsigned __int16 *v6; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  char v8; // [rsp+28h] [rbp-58h]
  const char *v9; // [rsp+30h] [rbp-50h]
  __int64 v10; // [rsp+38h] [rbp-48h]
  __int64 v11; // [rsp+40h] [rbp-40h]
  int v12; // [rsp+48h] [rbp-38h]
  int v13; // [rsp+4Ch] [rbp-34h]
  int v14; // [rsp+50h] [rbp-30h]
  __int64 v15[4]; // [rsp+58h] [rbp-28h] BYREF

  v6 = EnumValueToName(a3, a4);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 87);
    }
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v10 = 0;
    v11 = 0;
    v12 = 87;
    v13 = -1;
    v14 = 103;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::wstring::wstring((__int64)v15, (__int64)v6);
  RegWriteStringValue(this[2], a2, v15);
  std::wstring::_Tidy(v15, 1, 0);
}

```

## disassembly

```asm
0x180018bd4  push    rbp
0x180018bd6  push    rbx
0x180018bd7  push    rdi
0x180018bd8  mov     rbp, rsp
0x180018bdb  sub     rsp, 80h
0x180018be2  mov     rax, cs:__security_cookie
0x180018be9  xor     rax, rsp
0x180018bec  mov     [rbp+var_8], rax
0x180018bf0  mov     rdi, rdx
0x180018bf3  mov     rbx, rcx
0x180018bf6  mov     edx, r9d; unsigned int
0x180018bf9  mov     rcx, r8; struct _ENUM_NAMEVALUE_PAIR *
0x180018bfc  call    ?EnumValueToName@@YAPEBGPEAU_ENUM_NAMEVALUE_PAIR@@K@Z; EnumValueToName(_ENUM_NAMEVALUE_PAIR *,ulong)
0x180018c01  test    rax, rax
0x180018c04  jnz     loc_180018C90
0x180018c0a  lea     rax, WPP_GLOBAL_Control
0x180018c11  mov     ebx, 57h ; 'W'
0x180018c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c1d  cmp     rcx, rax
0x180018c20  jz      short loc_180018C44
0x180018c22  test    byte ptr [rcx+1Ch], 40h
0x180018c26  jz      short loc_180018C44
0x180018c28  cmp     byte ptr [rcx+19h], 2
0x180018c2c  jb      short loc_180018C44
0x180018c2e  lea     edx, [rbx-48h]
0x180018c31  mov     r9d, ebx
0x180018c34  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180018c3b  mov     rcx, [rcx+10h]
0x180018c3f  call    WPP_SF_D
0x180018c44  mov     [rbp+var_58], 0
0x180018c48  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180018c4f  mov     [rbp+var_50], rax
0x180018c53  mov     [rbp+var_48], 0
0x180018c5b  mov     [rbp+var_40], 0
0x180018c63  mov     [rbp+var_38], ebx
0x180018c66  mov     [rbp+var_34], 0FFFFFFFFh
0x180018c6d  mov     [rbp+var_30], 67h ; 'g'
0x180018c74  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180018c7b  mov     [rbp+pExceptionObject], rax
0x180018c7f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180018c86  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018c8a  call    _CxxThrowException_0
0x180018c90  mov     rdx, rax
0x180018c93  lea     rcx, [rbp+var_28]
0x180018c97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018c9c  nop
0x180018c9d  lea     r8, [rbp+var_28]
0x180018ca1  mov     rdx, rdi
0x180018ca4  mov     rcx, [rbx+10h]
0x180018ca8  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x180018cad  nop
0x180018cae  xor     r8d, r8d
0x180018cb1  mov     dl, 1
0x180018cb3  lea     rcx, [rbp+var_28]
0x180018cb7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018cbc  mov     rcx, [rbp+var_8]
0x180018cc0  xor     rcx, rsp; StackCookie
0x180018cc3  call    __security_check_cookie
0x180018cc8  add     rsp, 80h
0x180018ccf  pop     rdi
0x180018cd0  pop     rbx
0x180018cd1  pop     rbp
0x180018cd2  retn
```
