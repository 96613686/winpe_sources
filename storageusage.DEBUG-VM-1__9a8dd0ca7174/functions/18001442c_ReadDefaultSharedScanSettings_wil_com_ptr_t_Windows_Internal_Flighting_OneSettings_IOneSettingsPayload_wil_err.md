# ReadDefaultSharedScanSettings(wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,wil::err_exception_policy>,SCAN_SETTINGS &)

- ea: `0x18001442c`
- end: `0x18001454a`
- name: `?ReadDefaultSharedScanSettings@@YAJV?$com_ptr_t@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014550`

## callees

- `0x1800050f0`
- `0x180010330`
- `0x180011438`
- `0x18001442c`
- `0x1800152d4`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadDefaultSharedScanSettings(__int64 *a1, char *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, char *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, int *); // rbx
  int v12[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+28h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v13 = a1;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*a1 + 88LL);
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Default_ScanEnabled", 0x14u, 0x13u);
  v6 = v5(v4, v15, a2 + 5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *(double *)v12 = 0.0;
    v9 = *a1;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)*a1 + 80LL);
    v15 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Default_ScanCooldownHours",
      0x1Au,
      0x19u);
    v6 = v10(v9, v15, v12);
    v7 = v6;
    if ( v6 >= 0 )
    {
      *((_DWORD *)a2 + 2) = (int)*(double *)v12;
      *(_DWORD *)a2 = 19;
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 162;
  }
  else
  {
    v8 = 159;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
    (const char *)(unsigned int)v6,
    v12[0]);
LABEL_7:
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(a1);
  return v7;
}

```

## disassembly

```asm
0x18001442c  mov     r11, rsp
0x18001442f  mov     [r11+18h], rbx
0x180014433  push    rsi
0x180014434  push    rdi
0x180014435  push    r14
0x180014437  sub     rsp, 60h
0x18001443b  mov     rax, cs:__security_cookie
0x180014442  xor     rax, rsp
0x180014445  mov     [rsp+78h+var_28], rax
0x18001444a  mov     rsi, rdx
0x18001444d  mov     r14, rcx
0x180014450  mov     [r11-50h], rcx
0x180014454  mov     rdi, [rcx]
0x180014457  mov     rax, [rdi]
0x18001445a  mov     rbx, [rax+58h]
0x18001445e  mov     qword ptr [r11-30h], 0
0x180014466  mov     r9d, 13h; unsigned int
0x18001446c  lea     r8d, [r9+1]; unsigned int
0x180014470  lea     rdx, sourceString; "Default_ScanEnabled"
0x180014477  lea     rcx, [r11-48h]; hstringHeader
0x18001447b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014480  nop
0x180014481  lea     r8, [rsi+5]
0x180014485  mov     rdx, [rsp+78h+var_30]
0x18001448a  mov     rcx, rdi
0x18001448d  mov     rax, rbx
0x180014490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014495  mov     ebx, eax
0x180014497  test    eax, eax
0x180014499  jns     short loc_1800144A2
0x18001449b  mov     edx, 9Fh
0x1800144a0  jmp     short loc_1800144FA
0x1800144a2  xorps   xmm0, xmm0
0x1800144a5  movsd   qword ptr [rsp+78h+var_58], xmm0; int
0x1800144ab  mov     rdi, [r14]
0x1800144ae  mov     rax, [rdi]
0x1800144b1  mov     rbx, [rax+50h]
0x1800144b5  mov     [rsp+78h+var_30], 0
0x1800144be  mov     r9d, 19h; unsigned int
0x1800144c4  lea     r8d, [r9+1]; unsigned int
0x1800144c8  lea     rdx, aDefaultScancoo; "Default_ScanCooldownHours"
0x1800144cf  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x1800144d4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800144d9  nop
0x1800144da  lea     r8, [rsp+78h+var_58]
0x1800144df  mov     rdx, [rsp+78h+var_30]
0x1800144e4  mov     rcx, rdi
0x1800144e7  mov     rax, rbx
0x1800144ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ef  mov     ebx, eax
0x1800144f1  test    eax, eax
0x1800144f3  jns     short loc_180014510
0x1800144f5  mov     edx, 0A2h; void *
0x1800144fa  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180014501  mov     r9d, eax; char *
0x180014504  mov     rcx, [rsp+78h]; this
0x180014509  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001450e  jmp     short loc_180014522
0x180014510  cvttsd2si rax, qword ptr [rsp+78h+var_58]
0x180014517  mov     [rsi+8], eax
0x18001451a  mov     dword ptr [rsi], 13h
0x180014520  xor     ebx, ebx
0x180014522  mov     rcx, r14
0x180014525  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18001452a  mov     eax, ebx
0x18001452c  mov     rcx, [rsp+78h+var_28]
0x180014531  xor     rcx, rsp; StackCookie
0x180014534  call    __security_check_cookie
0x180014539  mov     rbx, [rsp+78h+arg_10]
0x180014541  add     rsp, 60h
0x180014545  pop     r14
0x180014547  pop     rdi
0x180014548  pop     rsi
0x180014549  retn
```
