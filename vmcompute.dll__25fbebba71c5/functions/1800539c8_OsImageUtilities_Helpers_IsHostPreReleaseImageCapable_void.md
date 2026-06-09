# OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(void)

- ea: `0x1800539c8`
- end: `0x180053be6`
- name: `?IsHostPreReleaseImageCapable@Helpers@OsImageUtilities@@YA_NXZ`
- size: `542`
- prototype: `bool __fastcall(OsImageUtilities::Helpers *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800542e4`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x18000d108`
- `0x1800539c8`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053a1c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053a1c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180053afc`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180053b7e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180053afc`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180053b7e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800539ed`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800539ed`

## string_xrefs

- `0x180053bbf`: `onecore\vm\common\mgmt\inc\VirtualizationSettings.h`
- `0x180053ba7`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180053bd4`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
bool __fastcall OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(OsImageUtilities::Helpers *this)
{
  bool v1; // bl
  _QWORD *v2; // rdi
  bool v3; // si
  LPVOID v4; // rcx
  int v6; // eax
  int v7; // eax
  LPVOID v8; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  __int16 v10[2]; // [rsp+50h] [rbp-20h] BYREF
  __int16 v11; // [rsp+54h] [rbp-1Ch] BYREF
  LPVOID v12; // [rsp+58h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v1 = 1;
  RoInitialize(1);
  v12 = 0;
  if ( CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v12) >= 0 )
  {
    v10[0] = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 24LL))(v12, v10);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 112LL))(v12, &v11);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    if ( v10[0] != -1 )
      v1 = v11 == 0;
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
    RoUninitialize();
    return v1;
  }
  else
  {
    v2 = operator new(0x30u);
    *v2 = &Vml::VmMachineLocalSettingsStore::`vftable';
    v2[1] = 0;
    *((_OWORD *)v2 + 1) = 0;
    v2[4] = 0;
    v2[5] = 7;
    *((_WORD *)v2 + 8) = 0;
    v13 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, __int64))(*v2 + 8LL))(v2, 0, 131097) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\vm\\common\\mgmt\\inc\\VirtualizationSettings.h",
        (const char *)0x8000FFFFLL,
        ppv);
    LODWORD(v13) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, const unsigned __int16 *, __int64 *))(*v2 + 56LL))(
           v2,
           L"AzureFeatureSet",
           &v13) )
    {
      v3 = (_DWORD)v13 != 0;
    }
    else
    {
      v3 = 0;
    }
    (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
    v4 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    RoUninitialize();
    return v3;
  }
}

```

## disassembly

```asm
0x1800539c8  push    rbp
0x1800539ca  push    rbx
0x1800539cb  push    rsi
0x1800539cc  push    rdi
0x1800539cd  push    r14
0x1800539cf  mov     rbp, rsp
0x1800539d2  sub     rsp, 70h
0x1800539d6  mov     rax, cs:__security_cookie
0x1800539dd  xor     rax, rsp
0x1800539e0  mov     [rbp+var_8], rax
0x1800539e4  xor     r14d, r14d
0x1800539e7  lea     ebx, [r14+1]
0x1800539eb  mov     ecx, ebx
0x1800539ed  call    cs:__imp_RoInitialize
0x1800539f4  nop     dword ptr [rax+rax+00h]
0x1800539f9  mov     [rbp+var_3F], bl
0x1800539fc  mov     [rbp+var_18], r14
0x180053a00  lea     rax, [rbp+var_18]
0x180053a04  mov     qword ptr [rsp+70h+ppv], rax; int
0x180053a09  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180053a10  mov     r8d, ebx; dwClsContext
0x180053a13  xor     edx, edx; pUnkOuter
0x180053a15  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180053a1c  call    cs:__imp_CoCreateInstance
0x180053a23  nop     dword ptr [rax+rax+00h]
0x180053a28  test    eax, eax
0x180053a2a  jns     loc_180053B0D
0x180053a30  xorps   xmm0, xmm0
0x180053a33  movups  [rbp+var_38], xmm0
0x180053a37  lea     ecx, [rbx+2Fh]; Size
0x180053a3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053a3f  mov     rdi, rax
0x180053a42  lea     rax, ??_7VmMachineLocalSettingsStore@Vml@@6B@; const Vml::VmMachineLocalSettingsStore::`vftable'
0x180053a49  mov     [rdi], rax
0x180053a4c  mov     [rdi+8], r14
0x180053a50  xorps   xmm0, xmm0
0x180053a53  movups  xmmword ptr [rdi+10h], xmm0
0x180053a57  mov     [rdi+20h], r14
0x180053a5b  mov     qword ptr [rdi+28h], 7
0x180053a63  mov     [rdi+10h], r14w
0x180053a68  mov     [rbp+var_10], r14
0x180053a6c  lea     rax, ??_7VirtualizationSettings@@6B@; const VirtualizationSettings::`vftable'
0x180053a73  mov     qword ptr [rbp+var_38], rax
0x180053a77  mov     [rbp+var_28], r14
0x180053a7b  mov     qword ptr [rbp+var_38+8], rdi
0x180053a7f  mov     rax, [rdi]
0x180053a82  xor     edx, edx
0x180053a84  mov     r8d, 20019h
0x180053a8a  mov     rcx, rdi
0x180053a8d  mov     rax, [rax+8]
0x180053a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a96  mov     rcx, [rbp+28h]; this
0x180053a9a  test    al, al
0x180053a9c  jz      loc_180053BB9
0x180053aa2  mov     dword ptr [rbp+var_10], r14d
0x180053aa6  mov     rax, [rdi]
0x180053aa9  lea     r8, [rbp+var_10]
0x180053aad  lea     rdx, ?AzureFeatureSetEnabled@VirtualizationSettings@@2QBGB; "AzureFeatureSet"
0x180053ab4  mov     rcx, rdi
0x180053ab7  mov     rax, [rax+38h]
0x180053abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ac0  test    al, al
0x180053ac2  jz      short loc_180053ACE
0x180053ac4  cmp     dword ptr [rbp+var_10], r14d
0x180053ac8  setnz   sil
0x180053acc  jmp     short loc_180053AD1
0x180053ace  mov     sil, r14b
0x180053ad1  mov     rax, [rdi]
0x180053ad4  mov     edx, ebx
0x180053ad6  mov     rcx, rdi
0x180053ad9  mov     rax, [rax]
0x180053adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ae1  nop
0x180053ae2  mov     rcx, [rbp+var_18]
0x180053ae6  test    rcx, rcx
0x180053ae9  jz      short loc_180053AFC
0x180053aeb  mov     [rbp+var_18], r14
0x180053aef  mov     rdx, [rcx]
0x180053af2  mov     rax, [rdx+10h]
0x180053af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053afb  nop
0x180053afc  call    cs:__imp_RoUninitialize
0x180053b03  nop     dword ptr [rax+rax+00h]
0x180053b08  mov     al, sil
0x180053b0b  jmp     short loc_180053B8C
0x180053b0d  mov     [rbp+var_20], r14w
0x180053b12  mov     rcx, [rbp+var_18]
0x180053b16  mov     rax, [rcx]
0x180053b19  lea     rdx, [rbp+var_20]
0x180053b1d  mov     rax, [rax+18h]
0x180053b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b26  mov     rcx, [rbp+28h]; this
0x180053b2a  test    eax, eax
0x180053b2c  js      loc_180053BD1
0x180053b32  mov     [rbp+var_1C], r14w
0x180053b37  mov     rcx, [rbp+var_18]
0x180053b3b  mov     rax, [rcx]
0x180053b3e  lea     rdx, [rbp+var_1C]
0x180053b42  mov     rax, [rax+70h]
0x180053b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b4b  mov     rcx, [rbp+28h]; this
0x180053b4f  test    eax, eax
0x180053b51  js      short loc_180053BA4
0x180053b53  cmp     [rbp+var_20], 0FFFFh
0x180053b58  jz      short loc_180053B64
0x180053b5a  cmp     [rbp+var_1C], r14w
0x180053b5f  jz      short loc_180053B64
0x180053b61  mov     bl, r14b
0x180053b64  mov     rcx, [rbp+var_18]
0x180053b68  test    rcx, rcx
0x180053b6b  jz      short loc_180053B7E
0x180053b6d  mov     [rbp+var_18], r14
0x180053b71  mov     rax, [rcx]
0x180053b74  mov     rax, [rax+10h]
0x180053b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b7d  nop
0x180053b7e  call    cs:__imp_RoUninitialize
0x180053b85  nop     dword ptr [rax+rax+00h]
0x180053b8a  mov     al, bl
0x180053b8c  mov     rcx, [rbp+var_8]
0x180053b90  xor     rcx, rsp; StackCookie
0x180053b93  call    __security_check_cookie
0x180053b98  add     rsp, 70h
0x180053b9c  pop     r14
0x180053b9e  pop     rdi
0x180053b9f  pop     rsi
0x180053ba0  pop     rbx
0x180053ba1  pop     rbp
0x180053ba2  retn
0x180053ba4  mov     r9d, eax; char *
0x180053ba7  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053bae  mov     edx, 171h; void *
0x180053bb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053bb9  mov     r9d, 8000FFFFh; char *
0x180053bbf  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\mgmt\\inc\\Virtual"...
0x180053bc6  mov     edx, 0ABh; void *
0x180053bcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053bd1  mov     r9d, eax; char *
0x180053bd4  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053bdb  mov     edx, 16Eh; void *
0x180053be0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
