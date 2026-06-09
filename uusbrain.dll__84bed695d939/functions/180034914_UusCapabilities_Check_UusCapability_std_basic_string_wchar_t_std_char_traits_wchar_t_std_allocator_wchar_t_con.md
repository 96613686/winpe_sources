# UusCapabilities::Check(UusCapability,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180034914`
- end: `0x180034b77`
- name: `?Check@UusCapabilities@@QEAA_NW4UusCapability@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@1@Z`
- size: `611`
- prototype: `bool __fastcall(UusCapabilities *, int, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180035160`
- `0x180035610`

## callees

- `0x180028728`
- `0x180029644`
- `0x180034914`
- `0x180034b80`
- `0x18003da28`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UusCapabilities::Check(UusCapabilities *a1, int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v7; // r12d
  unsigned __int64 v8; // r14
  const char *v9; // r14
  bool result; // al
  bool v11; // r15
  const char *v12; // r14
  wil *v13; // rcx
  int v14; // edi
  const char *v15; // rbx
  _BYTE v16[32]; // [rsp+0h] [rbp-F8h] BYREF
  void **v17; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B0h]
  char v19; // [rsp+50h] [rbp-A8h]
  void ***v20; // [rsp+58h] [rbp-A0h]
  void ***v21; // [rsp+60h] [rbp-98h]
  _BYTE v22[32]; // [rsp+68h] [rbp-90h] BYREF
  char v23; // [rsp+88h] [rbp-70h]
  __int64 v24; // [rsp+90h] [rbp-68h]
  __int64 v25; // [rsp+98h] [rbp-60h]
  __int64 v26; // [rsp+A0h] [rbp-58h]
  __int64 v27; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    v7 = a3;
    v8 = a2;
    v25 = a3;
    v26 = a4;
    v27 = a5;
    v24 = a6;
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        if ( (unsigned __int64)a2 >= 2 )
          v9 = "UusCapability::****UNKNOWN_MAPPING****";
        else
          v9 = (const char *)UusCapabilityConvert::_enum2str[2 * a2 + 1];
        v20 = &v17;
        v19 = 0;
        if ( *(_BYTE *)(a5 + 16) )
        {
          v17 = &UusVersion::`vftable';
          v18 = *(_QWORD *)(a5 + 8);
          v19 = 1;
        }
        v21 = (void ***)v22;
        v23 = 0;
        if ( *(_BYTE *)(a4 + 32) )
        {
          std::wstring::wstring((__int64)v22, a4);
          v23 = 1;
        }
        uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(
          v7,
          (unsigned int)v22,
          (unsigned int)&v17,
          a6,
          (__int64)v9,
          0,
          0);
        if ( *(_BYTE *)(a4 + 32) )
          std::wstring::_Tidy_deallocate(a4);
        if ( *(_BYTE *)(a5 + 16) )
          (**(void (__fastcall ***)(__int64, _QWORD))a5)(a5, 0);
        return 0;
      }
      v11 = UusCapabilities::Check_WUSystemInterfaceDependency(a1);
    }
    else
    {
      v11 = 1;
    }
    if ( !v11 )
    {
      if ( v8 >= 2 )
        v12 = "UusCapability::****UNKNOWN_MAPPING****";
      else
        v12 = (const char *)UusCapabilityConvert::_enum2str[2 * v8 + 1];
      v21 = &v17;
      v19 = 0;
      if ( *(_BYTE *)(a5 + 16) )
      {
        v17 = &UusVersion::`vftable';
        v18 = *(_QWORD *)(a5 + 8);
        v19 = 1;
      }
      v20 = (void ***)v22;
      v23 = 0;
      if ( *(_BYTE *)(a4 + 32) )
      {
        std::wstring::wstring((__int64)v22, a4);
        v23 = 1;
      }
      uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(
        v7,
        (unsigned int)v22,
        (unsigned int)&v17,
        a6,
        (__int64)v12,
        1,
        0);
    }
    if ( *(_BYTE *)(a4 + 32) )
      std::wstring::_Tidy_deallocate(a4);
    if ( *(_BYTE *)(a5 + 16) )
      (**(void (__fastcall ***)(__int64, _QWORD))a5)(a5, 0);
    result = v11;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x62,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\UusCapabilities.hpp",
      (const char *)a4);
    v14 = wil::ResultFromCaughtException(v13);
    if ( (unsigned __int64)a2 >= 2 )
      v15 = "UusCapability::****UNKNOWN_MAPPING****";
    else
      v15 = (const char *)UusCapabilityConvert::_enum2str[2 * a2 + 1];
    v21 = &v17;
    v19 = 0;
    if ( *(_BYTE *)(v27 + 16) )
    {
      v17 = &UusVersion::`vftable';
      v18 = *(_QWORD *)(v27 + 8);
      v19 = 1;
    }
    v20 = (void ***)v22;
    v23 = 0;
    if ( *(_BYTE *)(v26 + 32) )
    {
      std::wstring::wstring((__int64)v22, v26);
      v23 = 1;
    }
    uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(
      v25,
      (unsigned int)v16 + 104,
      (unsigned int)v16 + 64,
      v24,
      (__int64)v15,
      0,
      v14);
    if ( *(_BYTE *)(v26 + 32) )
      std::wstring::_Tidy_deallocate(v26);
    if ( *(_BYTE *)(v27 + 16) )
      (**(void (__fastcall ***)(__int64, _QWORD))v27)(v27, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180034914  mov     [rsp+arg_8], edx
0x180034918  mov     r11, rsp
0x18003491b  push    rbx
0x18003491c  push    rsi
0x18003491d  push    rdi
0x18003491e  push    r12
0x180034920  push    r13
0x180034922  push    r14
0x180034924  push    r15
0x180034926  sub     rsp, 0C0h
0x18003492d  mov     rax, cs:__security_cookie
0x180034934  xor     rax, rsp
0x180034937  mov     [rsp+0F8h+var_48], rax
0x18003493f  mov     rsi, r9
0x180034942  mov     r12, r8
0x180034945  movsxd  r14, edx
0x180034948  mov     [rsp+0F8h+var_60], r8
0x180034950  mov     [r11-58h], r9
0x180034954  mov     rdi, [rsp+0F8h+arg_20]
0x18003495c  mov     [r11-50h], rdi
0x180034960  mov     r13, [rsp+0F8h+arg_28]
0x180034968  mov     [rsp+0F8h+var_68], r13
0x180034970  xor     ebx, ebx
0x180034972  test    edx, edx
0x180034974  jz      loc_180034A55
0x18003497a  cmp     r14d, 1
0x18003497e  jz      loc_180034A4B
0x180034984  mov     rax, r14
0x180034987  cmp     r14, 2
0x18003498b  jnb     short loc_18003499E
0x18003498d  add     rax, rax
0x180034990  lea     rcx, ?_enum2str@UusCapabilityConvert@@0QBU?$pair@W4UusCapability@@PEAD@std@@B; std::pair<UusCapability,char *> const near * const UusCapabilityConvert::_enum2str
0x180034997  mov     r14, [rcx+rax*8+8]
0x18003499c  jmp     short loc_1800349A5
0x18003499e  lea     r14, aUuscapabilityU; "UusCapability::****UNKNOWN_MAPPING****"
0x1800349a5  lea     rax, [rsp+0F8h+var_B8]
0x1800349aa  mov     [rsp+0F8h+var_A0], rax
0x1800349af  mov     [rsp+0F8h+var_A8], bl
0x1800349b3  cmp     [rdi+10h], bl
0x1800349b6  jz      short loc_1800349D2
0x1800349b8  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x1800349bf  mov     [rsp+0F8h+var_B8], rax
0x1800349c4  mov     rax, [rdi+8]
0x1800349c8  mov     [rsp+0F8h+var_B0], rax
0x1800349cd  mov     [rsp+0F8h+var_A8], 1
0x1800349d2  lea     rax, [rsp+0F8h+var_90]
0x1800349d7  mov     [rsp+0F8h+var_98], rax
0x1800349dc  mov     [rsp+0F8h+var_70], bl
0x1800349e3  cmp     [r9+20h], bl
0x1800349e7  jz      short loc_1800349FE
0x1800349e9  mov     rdx, rsi
0x1800349ec  lea     rcx, [rsp+0F8h+var_90]
0x1800349f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800349f6  mov     [rsp+0F8h+var_70], 1
0x1800349fe  mov     [rsp+0F8h+var_C8], ebx
0x180034a02  mov     [rsp+0F8h+var_D0], bl
0x180034a06  mov     [rsp+0F8h+var_D8], r14
0x180034a0b  mov     r9, r13
0x180034a0e  lea     r8, [rsp+0F8h+var_B8]
0x180034a13  lea     rdx, [rsp+0F8h+var_90]
0x180034a18  mov     rcx, r12
0x180034a1b  call    ?UusComponentDisabledByCapability@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0PEBD_NJ@Z; uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &,char const *,bool,long)
0x180034a20  nop
0x180034a21  cmp     [rsi+20h], bl
0x180034a24  jz      short loc_180034A2F
0x180034a26  mov     rcx, rsi
0x180034a29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034a2e  nop
0x180034a2f  cmp     [rdi+10h], bl
0x180034a32  jz      short loc_180034A44
0x180034a34  mov     rax, [rdi]
0x180034a37  xor     edx, edx
0x180034a39  mov     rcx, rdi
0x180034a3c  mov     rax, [rax]
0x180034a3f  call    _guard_dispatch_icall
0x180034a44  xor     al, al
0x180034a46  jmp     loc_180034B54
0x180034a4b  call    ?Check_WUSystemInterfaceDependency@UusCapabilities@@AEAA_NXZ; UusCapabilities::Check_WUSystemInterfaceDependency(void)
0x180034a50  mov     r15b, al
0x180034a53  jmp     short loc_180034A58
0x180034a55  mov     r15b, 1
0x180034a58  test    r15b, r15b
0x180034a5b  jnz     loc_180034AFB
0x180034a61  cmp     r14, 2
0x180034a65  jnb     short loc_180034A78
0x180034a67  add     r14, r14
0x180034a6a  lea     rcx, ?_enum2str@UusCapabilityConvert@@0QBU?$pair@W4UusCapability@@PEAD@std@@B; std::pair<UusCapability,char *> const near * const UusCapabilityConvert::_enum2str
0x180034a71  mov     r14, [rcx+r14*8+8]
0x180034a76  jmp     short loc_180034A7F
0x180034a78  lea     r14, aUuscapabilityU; "UusCapability::****UNKNOWN_MAPPING****"
0x180034a7f  lea     rax, [rsp+0F8h+var_B8]
0x180034a84  mov     [rsp+0F8h+var_98], rax
0x180034a89  mov     [rsp+0F8h+var_A8], bl
0x180034a8d  cmp     [rdi+10h], bl
0x180034a90  jz      short loc_180034AAC
0x180034a92  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180034a99  mov     [rsp+0F8h+var_B8], rax
0x180034a9e  mov     rax, [rdi+8]
0x180034aa2  mov     [rsp+0F8h+var_B0], rax
0x180034aa7  mov     [rsp+0F8h+var_A8], 1
0x180034aac  lea     rax, [rsp+0F8h+var_90]
0x180034ab1  mov     [rsp+0F8h+var_A0], rax
0x180034ab6  mov     [rsp+0F8h+var_70], bl
0x180034abd  cmp     [rsi+20h], bl
0x180034ac0  jz      short loc_180034AD7
0x180034ac2  mov     rdx, rsi
0x180034ac5  lea     rcx, [rsp+0F8h+var_90]
0x180034aca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034acf  mov     [rsp+0F8h+var_70], 1
0x180034ad7  mov     [rsp+0F8h+var_C8], ebx
0x180034adb  mov     [rsp+0F8h+var_D0], 1
0x180034ae0  mov     [rsp+0F8h+var_D8], r14
0x180034ae5  mov     r9, r13
0x180034ae8  lea     r8, [rsp+0F8h+var_B8]
0x180034aed  lea     rdx, [rsp+0F8h+var_90]
0x180034af2  mov     rcx, r12
0x180034af5  call    ?UusComponentDisabledByCapability@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0PEBD_NJ@Z; uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &,char const *,bool,long)
0x180034afa  nop
0x180034afb  cmp     [rsi+20h], bl
0x180034afe  jz      short loc_180034B09
0x180034b00  mov     rcx, rsi
0x180034b03  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034b08  nop
0x180034b09  cmp     [rdi+10h], bl
0x180034b0c  jz      short loc_180034B1E
0x180034b0e  mov     rcx, [rdi]
0x180034b11  mov     rax, [rcx]
0x180034b14  xor     edx, edx
0x180034b16  mov     rcx, rdi
0x180034b19  call    _guard_dispatch_icall
0x180034b1e  mov     al, r15b
0x180034b21  jmp     short loc_180034B54
0x180034b23  xor     ebx, ebx
0x180034b25  mov     rcx, [rsp+0F8h+var_58]
0x180034b2d  cmp     [rcx+20h], bl
0x180034b30  jz      short loc_180034B38
0x180034b32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034b37  nop
0x180034b38  mov     rcx, [rsp+0F8h+var_50]
0x180034b40  cmp     [rcx+10h], bl
0x180034b43  jz      short loc_180034B52
0x180034b45  mov     rax, [rcx]
0x180034b48  xor     edx, edx
0x180034b4a  mov     rax, [rax]
0x180034b4d  call    _guard_dispatch_icall
0x180034b52  xor     al, al
0x180034b54  mov     rcx, [rsp+0F8h+var_48]
0x180034b5c  xor     rcx, rsp; StackCookie
0x180034b5f  call    __security_check_cookie
0x180034b64  add     rsp, 0C0h
0x180034b6b  pop     r15
0x180034b6d  pop     r14
0x180034b6f  pop     r13
0x180034b71  pop     r12
0x180034b73  pop     rdi
0x180034b74  pop     rsi
0x180034b75  pop     rbx
0x180034b76  retn
```
