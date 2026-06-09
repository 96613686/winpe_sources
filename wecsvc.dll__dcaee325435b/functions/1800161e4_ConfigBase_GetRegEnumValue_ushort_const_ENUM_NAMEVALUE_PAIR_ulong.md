# ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)

- ea: `0x1800161e4`
- end: `0x180016323`
- name: `?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z`
- size: `319`
- prototype: `char __fastcall(ConfigBase *this, const unsigned __int16 *, struct _ENUM_NAMEVALUE_PAIR *, unsigned int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004760`
- `0x1800052cc`
- `0x18001483c`
- `0x180015c30`
- `0x180017b8c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800062d4`
- `0x1800128c0`
- `0x1800161e4`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016271`
- `msvcrt!_wcsicmp` at `0x180016271`

## pseudocode

```c
char __fastcall ConfigBase::GetRegEnumValue(
        ConfigBase *this,
        const unsigned __int16 *a2,
        struct _ENUM_NAMEVALUE_PAIR *a3,
        unsigned int *a4)
{
  const wchar_t *v7; // rdi
  unsigned int v8; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-29h] BYREF
  char v10; // [rsp+28h] [rbp-21h]
  const char *v11; // [rsp+30h] [rbp-19h]
  __int64 v12; // [rsp+38h] [rbp-11h]
  __int64 v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  int v16; // [rsp+50h] [rbp+7h]
  wchar_t *String2[3]; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp+27h]

  v18 = 7;
  String2[2] = 0;
  LOWORD(String2[0]) = 0;
  if ( (unsigned __int8)RegReadStringValue(*((_QWORD *)this + 2), a2, String2) )
  {
    v7 = (const wchar_t *)String2;
    if ( v18 >= 8 )
      v7 = String2[0];
    while ( 1 )
    {
      if ( !*(_QWORD *)a3 )
        goto LABEL_10;
      if ( !_wcsicmp(*(const wchar_t **)a3, v7) )
        break;
      a3 = (struct _ENUM_NAMEVALUE_PAIR *)((char *)a3 + 16);
    }
    v8 = *((_DWORD *)a3 + 2);
    if ( v8 == -1 )
    {
LABEL_10:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 13);
      }
      v10 = 0;
      v11 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v12 = 0;
      v13 = 0;
      v14 = 13;
      v15 = -1;
      v16 = 91;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    *a4 = v8;
    std::wstring::_Tidy(String2, 1, 0);
    return 1;
  }
  else
  {
    std::wstring::_Tidy(String2, 1, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1800161e4  push    rbp
0x1800161e6  push    rbx
0x1800161e7  push    rsi
0x1800161e8  push    rdi
0x1800161e9  lea     rbp, [rsp-3Fh]
0x1800161ee  sub     rsp, 88h
0x1800161f5  mov     rax, cs:__security_cookie
0x1800161fc  xor     rax, rsp
0x1800161ff  mov     [rbp+57h+var_28], rax
0x180016203  mov     rsi, r9
0x180016206  mov     rbx, r8
0x180016209  mov     [rbp+57h+var_30], 7
0x180016211  mov     [rbp+57h+var_38], 0
0x180016219  xor     eax, eax
0x18001621b  mov     word ptr [rbp+57h+String2], ax
0x18001621f  lea     r8, [rbp+57h+String2]
0x180016223  mov     rcx, [rcx+10h]
0x180016227  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001622c  test    al, al
0x18001622e  jnz     short loc_180016258
0x180016230  xor     r8d, r8d
0x180016233  mov     dl, 1
0x180016235  lea     rcx, [rbp+57h+String2]
0x180016239  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001623e  xor     al, al
0x180016240  mov     rcx, [rbp+57h+var_28]
0x180016244  xor     rcx, rsp; StackCookie
0x180016247  call    __security_check_cookie
0x18001624c  add     rsp, 88h
0x180016253  pop     rdi
0x180016254  pop     rsi
0x180016255  pop     rbx
0x180016256  pop     rbp
0x180016257  retn
0x180016258  lea     rdi, [rbp+57h+String2]
0x18001625c  cmp     [rbp+57h+var_30], 8
0x180016261  cmovnb  rdi, [rbp+57h+String2]
0x180016266  mov     rcx, [rbx]; String1
0x180016269  test    rcx, rcx
0x18001626c  jz      short loc_18001629D
0x18001626e  mov     rdx, rdi; String2
0x180016271  call    cs:__imp__wcsicmp
0x180016277  test    eax, eax
0x180016279  jz      short loc_180016281
0x18001627b  add     rbx, 10h
0x18001627f  jmp     short loc_180016266
0x180016281  mov     eax, [rbx+8]
0x180016284  cmp     eax, 0FFFFFFFFh
0x180016287  jz      short loc_18001629D
0x180016289  mov     [rsi], eax
0x18001628b  xor     r8d, r8d
0x18001628e  mov     dl, 1
0x180016290  lea     rcx, [rbp+57h+String2]
0x180016294  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016299  mov     al, 1
0x18001629b  jmp     short loc_180016240
0x18001629d  lea     rax, WPP_GLOBAL_Control
0x1800162a4  mov     ebx, 0Dh
0x1800162a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162b0  cmp     rcx, rax
0x1800162b3  jz      short loc_1800162D7
0x1800162b5  test    byte ptr [rcx+1Ch], 40h
0x1800162b9  jz      short loc_1800162D7
0x1800162bb  cmp     byte ptr [rcx+19h], 2
0x1800162bf  jb      short loc_1800162D7
0x1800162c1  lea     edx, [rbx+1]
0x1800162c4  mov     r9d, ebx
0x1800162c7  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800162ce  mov     rcx, [rcx+10h]
0x1800162d2  call    WPP_SF_D
0x1800162d7  mov     [rbp+57h+var_78], 0
0x1800162db  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800162e2  mov     [rbp+57h+var_70], rax
0x1800162e6  mov     [rbp+57h+var_68], 0
0x1800162ee  mov     [rbp+57h+var_60], 0
0x1800162f6  mov     [rbp+57h+var_58], ebx
0x1800162f9  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180016300  mov     [rbp+57h+var_50], 5Bh ; '['
0x180016307  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001630e  mov     [rbp+57h+pExceptionObject], rax
0x180016312  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180016319  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001631d  call    _CxxThrowException_0
```
