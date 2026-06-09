# WldpIsFileWithDetachedSignatureTrusted(void *,void *,_GUID const &,ulong *)

- ea: `0x18002d4e8`
- end: `0x18002d71f`
- name: `?WldpIsFileWithDetachedSignatureTrusted@@YAJPEAX0AEBU_GUID@@PEAK@Z`
- size: `567`
- prototype: `__int64 __fastcall(void *, void *, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ecc0`

## callees

- `0x1800159a0`
- `0x1800159f0`
- `0x180018950`
- `0x18001f038`
- `0x18001f414`
- `0x180021ec0`
- `0x180022a10`
- `0x18002d228`
- `0x18002d4e8`

## import_xrefs

- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d554`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d601`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d6f1`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d554`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d601`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d6f1`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18002d69b`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18002d69b`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18002d6bc`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18002d6bc`

## string_xrefs

- `0x18002d5dc`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WldpIsFileWithDetachedSignatureTrusted(void *a1, void *a2, const struct _GUID *a3, unsigned int *a4)
{
  int IsDetachedSignatureTrusted; // ebx
  const char *v9; // r9
  __int64 result; // rax
  unsigned int v11; // ebx
  _QWORD *v12; // rax
  _QWORD *v13; // r8
  int v14; // [rsp+20h] [rbp-1B8h]
  unsigned int v15; // [rsp+40h] [rbp-198h] BYREF
  int v16; // [rsp+44h] [rbp-194h]
  __int64 v17; // [rsp+48h] [rbp-190h] BYREF
  __int64 *v18; // [rsp+50h] [rbp-188h] BYREF
  __int64 v19; // [rsp+58h] [rbp-180h] BYREF
  char v20; // [rsp+60h] [rbp-178h]
  _QWORD v21[4]; // [rsp+68h] [rbp-170h] BYREF
  _QWORD v22[5]; // [rsp+88h] [rbp-150h] BYREF
  int v23[2]; // [rsp+B0h] [rbp-128h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp-120h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v16 = 0;
  try
  {
    v15 = 0;
    memset_0(v23, 0, 0xE8u);
    v23[0] = 232;
    v17 = 0;
    WTConfigCiFreePrivateData(v23);
    memset_0(v23, 0, 0xE8u);
    v23[0] = 232;
    v18 = &v17;
    v19 = 0;
    v20 = 1;
    v16 = 1;
    IsDetachedSignatureTrusted = WldpIsDetachedSignatureTrusted(
                                   (_DWORD)a1,
                                   (_DWORD)a2,
                                   (unsigned int)&v15,
                                   (unsigned int)&v19,
                                   (__int64)v23);
    v16 = 0;
    wil::details::out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______::_out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______(&v18);
    if ( IsDetachedSignatureTrusted >= 0 )
    {
      v11 = v15;
      v23[1] = v15 != 1 ? 0xD0E90002 : 0;
      v24 = v15;
      GetPathnameFromHandle(v22, a1);
      GetPathnameFromHandle(v21, a2);
      v12 = v21;
      if ( v21[3] > 7u )
        v12 = (_QWORD *)v21[0];
      v13 = v22;
      if ( v22[3] > 7u )
        v13 = (_QWORD *)v22[0];
      WTLogConfigCiScriptEvent2(v17, a1, v13, a2, v12, v23, a3);
      if ( v24 != 1 )
        WTLogConfigCiSignerEvent(v17, a3, 1, 1);
      *a4 = v11;
      std::wstring::~wstring(v21);
      std::wstring::~wstring(v22);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v17);
      WTConfigCiFreePrivateData(v23);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E5,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
        (const char *)(unsigned int)IsDetachedSignatureTrusted,
        v14);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v17);
      WTConfigCiFreePrivateData(v23);
      result = (unsigned int)IsDetachedSignatureTrusted;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x801,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18002d4e8  push    rbx
0x18002d4ea  push    rsi
0x18002d4eb  push    rdi
0x18002d4ec  push    r14
0x18002d4ee  push    r15
0x18002d4f0  sub     rsp, 1B0h
0x18002d4f7  mov     rax, cs:__security_cookie
0x18002d4fe  xor     rax, rsp
0x18002d501  mov     [rsp+1D8h+var_38], rax
0x18002d509  mov     r15, r9
0x18002d50c  mov     rdi, r8
0x18002d50f  mov     r14, rdx
0x18002d512  mov     rsi, rcx
0x18002d515  mov     [rsp+1D8h+var_194], 0
0x18002d51d  mov     [rsp+1D8h+var_198], 0
0x18002d525  mov     ebx, 0E8h
0x18002d52a  mov     r8d, ebx; Size
0x18002d52d  xor     edx, edx; Val
0x18002d52f  lea     rcx, [rsp+1D8h+var_128]; void *
0x18002d537  call    memset_0
0x18002d53c  mov     [rsp+1D8h+var_128], ebx
0x18002d543  mov     [rsp+1D8h+var_190], 0
0x18002d54c  lea     rcx, [rsp+1D8h+var_128]
0x18002d554  call    cs:__imp_WTConfigCiFreePrivateData
0x18002d55a  mov     r8d, ebx; Size
0x18002d55d  xor     edx, edx; Val
0x18002d55f  lea     rcx, [rsp+1D8h+var_128]; void *
0x18002d567  call    memset_0
0x18002d56c  mov     [rsp+1D8h+var_128], ebx
0x18002d573  lea     rax, [rsp+1D8h+var_190]
0x18002d578  mov     [rsp+1D8h+var_188], rax
0x18002d57d  mov     [rsp+1D8h+var_180], 0
0x18002d586  mov     [rsp+1D8h+var_178], 1
0x18002d58b  mov     [rsp+1D8h+var_194], 1
0x18002d593  lea     rax, [rsp+1D8h+var_128]
0x18002d59b  mov     qword ptr [rsp+1D8h+var_1B8], rax; int
0x18002d5a0  lea     r9, [rsp+1D8h+var_180]
0x18002d5a5  lea     r8, [rsp+1D8h+var_198]
0x18002d5aa  mov     rdx, r14
0x18002d5ad  mov     rcx, rsi
0x18002d5b0  call    WldpIsDetachedSignatureTrusted
0x18002d5b5  mov     ebx, eax
0x18002d5b7  mov     ecx, 1
0x18002d5bc  and     ecx, 0FFFFFFFEh
0x18002d5bf  mov     [rsp+1D8h+var_194], ecx
0x18002d5c3  lea     rcx, [rsp+1D8h+var_188]
0x18002d5c8  call    wil__details__out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t__________out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_______
0x18002d5cd  test    ebx, ebx
0x18002d5cf  jns     short loc_18002D60E
0x18002d5d1  mov     rcx, [rsp+1D8h]; this
0x18002d5d9  mov     r9d, ebx; char *
0x18002d5dc  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18002d5e3  mov     edx, 7E5h; void *
0x18002d5e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5ed  nop
0x18002d5ee  lea     rcx, [rsp+1D8h+var_190]
0x18002d5f3  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x18002d5f8  nop
0x18002d5f9  lea     rcx, [rsp+1D8h+var_128]
0x18002d601  call    cs:__imp_WTConfigCiFreePrivateData
0x18002d607  mov     eax, ebx
0x18002d609  jmp     loc_18002D6FF
0x18002d60e  mov     ebx, [rsp+1D8h+var_198]
0x18002d612  lea     eax, [rbx-1]
0x18002d615  neg     eax
0x18002d617  sbb     eax, eax
0x18002d619  and     eax, 0D0E90002h
0x18002d61e  mov     [rsp+1D8h+var_124], eax
0x18002d625  mov     [rsp+1D8h+var_120], ebx
0x18002d62c  mov     rdx, rsi
0x18002d62f  lea     rcx, [rsp+1D8h+var_150]
0x18002d637  call    ?GetPathnameFromHandle@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetPathnameFromHandle(void *)
0x18002d63c  nop
0x18002d63d  mov     rdx, r14
0x18002d640  lea     rcx, [rsp+1D8h+var_170]
0x18002d645  call    ?GetPathnameFromHandle@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetPathnameFromHandle(void *)
0x18002d64a  nop
0x18002d64b  lea     rax, [rsp+1D8h+var_170]
0x18002d650  cmp     [rsp+1D8h+var_158], 7
0x18002d659  cmova   rax, [rsp+1D8h+var_170]
0x18002d65f  lea     r8, [rsp+1D8h+var_150]
0x18002d667  cmp     [rsp+1D8h+var_138], 7
0x18002d670  cmova   r8, [rsp+1D8h+var_150]
0x18002d679  mov     [rsp+1D8h+var_1A8], rdi
0x18002d67e  lea     rcx, [rsp+1D8h+var_128]
0x18002d686  mov     [rsp+1D8h+var_1B0], rcx
0x18002d68b  mov     qword ptr [rsp+1D8h+var_1B8], rax
0x18002d690  mov     r9, r14
0x18002d693  mov     rdx, rsi
0x18002d696  mov     rcx, [rsp+1D8h+var_190]
0x18002d69b  call    cs:__imp_WTLogConfigCiScriptEvent2
0x18002d6a1  cmp     [rsp+1D8h+var_120], 1
0x18002d6a9  jz      short loc_18002D6C2
0x18002d6ab  mov     r9d, 1
0x18002d6b1  mov     r8d, r9d
0x18002d6b4  mov     rdx, rdi
0x18002d6b7  mov     rcx, [rsp+1D8h+var_190]
0x18002d6bc  call    cs:__imp_WTLogConfigCiSignerEvent
0x18002d6c2  mov     [r15], ebx
0x18002d6c5  lea     rcx, [rsp+1D8h+var_170]
0x18002d6ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d6cf  nop
0x18002d6d0  lea     rcx, [rsp+1D8h+var_150]
0x18002d6d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d6dd  nop
0x18002d6de  lea     rcx, [rsp+1D8h+var_190]
0x18002d6e3  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x18002d6e8  nop
0x18002d6e9  lea     rcx, [rsp+1D8h+var_128]
0x18002d6f1  call    cs:__imp_WTConfigCiFreePrivateData
0x18002d6f7  xor     eax, eax
0x18002d6f9  jmp     short loc_18002D6FF
0x18002d6fb  mov     eax, [rsp+1D8h+var_198]
0x18002d6ff  mov     rcx, [rsp+1D8h+var_38]
0x18002d707  xor     rcx, rsp; StackCookie
0x18002d70a  call    __security_check_cookie
0x18002d70f  add     rsp, 1B0h
0x18002d716  pop     r15
0x18002d718  pop     r14
0x18002d71a  pop     rdi
0x18002d71b  pop     rsi
0x18002d71c  pop     rbx
0x18002d71d  retn
```
