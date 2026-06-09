# ReadSharedScanSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &,SCAN_SETTINGS &)

- ea: `0x180014adc`
- end: `0x180014cc3`
- name: `?ReadSharedScanSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@1@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014550`

## callees

- `0x1800050f0`
- `0x180010330`
- `0x180011438`
- `0x180014adc`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReadSharedScanSettings(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, __int64, __int64 *); // rbx
  unsigned int v7; // esi
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, __int64, __int64); // rbx
  _BYTE *v10; // rsi
  int v11; // r12d
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, __int64, __int64); // rbx
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, __int64, double *); // rbx
  int v16; // eax
  __int64 v18; // [rsp+20h] [rbp-50h] BYREF
  double v19; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-40h]
  __int64 *v21; // [rsp+38h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h]

  v20 = a1;
  v21 = a1;
  v18 = 0;
  v5 = *a1;
  v6 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a1 + 64LL);
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SharedSettings", 0xFu, 0xEu);
  if ( v6(v5, v23, &v18) >= 0 )
  {
    v8 = v18;
    v9 = *(int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 96LL);
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UseHardcodedDefaults", 0x15u, 0x14u);
    v10 = (_BYTE *)(a3 + 4);
    if ( v9(v8, v23, a3 + 4) < 0 )
      *v10 = 0;
    if ( *v10 )
    {
      v7 = 0;
    }
    else
    {
      v11 = 0;
      v12 = v18;
      v13 = *(int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 96LL);
      v23 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ScanEnabled", 0xCu, 0xBu);
      if ( v13(v12, v23, a3 + 5) < 0 )
      {
        *(_BYTE *)(a3 + 5) = *(_BYTE *)(a2 + 5);
        v11 = -2147024883;
      }
      v19 = 0.0;
      v14 = v18;
      v15 = *(int (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v18 + 88LL);
      v23 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ScanCooldownHours", 0x12u, 0x11u);
      if ( v15(v14, v23, &v19) >= 0 )
      {
        v16 = (int)v19;
      }
      else
      {
        v11 = -2147024883;
        v16 = *(_DWORD *)(a2 + 8);
      }
      *(_DWORD *)(a3 + 8) = v16;
      v7 = v11;
    }
  }
  else
  {
    *(_BYTE *)(a3 + 5) = *(_BYTE *)(a2 + 5);
    *(_DWORD *)(a3 + 8) = *(_DWORD *)(a2 + 8);
    v7 = -2147024883;
  }
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v18);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(v20);
  return v7;
}

```

## disassembly

```asm
0x180014adc  mov     [rsp-38h+arg_8], rbx
0x180014ae1  push    rbp
0x180014ae2  push    rsi
0x180014ae3  push    rdi
0x180014ae4  push    r12
0x180014ae6  push    r13
0x180014ae8  push    r14
0x180014aea  push    r15
0x180014aec  mov     rbp, rsp
0x180014aef  sub     rsp, 70h
0x180014af3  mov     rax, cs:__security_cookie
0x180014afa  xor     rax, rsp
0x180014afd  mov     [rbp+var_10], rax
0x180014b01  mov     r15, r8
0x180014b04  mov     r14, rdx
0x180014b07  mov     [rbp+var_40], rcx
0x180014b0b  mov     [rbp+var_38], rcx
0x180014b0f  xor     r13d, r13d
0x180014b12  mov     [rbp+var_50], r13
0x180014b16  mov     rdi, [rcx]
0x180014b19  mov     rax, [rdi]
0x180014b1c  mov     rbx, [rax+40h]
0x180014b20  mov     [rbp+var_50], r13
0x180014b24  mov     [rbp+var_18], r13
0x180014b28  lea     r9d, [r13+0Eh]; unsigned int
0x180014b2c  lea     r8d, [r13+0Fh]; unsigned int
0x180014b30  lea     rdx, aSharedsettings; "SharedSettings"
0x180014b37  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014b3b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014b40  nop
0x180014b41  lea     r8, [rbp+var_50]
0x180014b45  mov     rdx, [rbp+var_18]
0x180014b49  mov     rcx, rdi
0x180014b4c  mov     rax, rbx
0x180014b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b54  nop
0x180014b55  shr     eax, 1Fh
0x180014b58  test    al, al
0x180014b5a  jz      short loc_180014B73
0x180014b5c  mov     al, [r14+5]
0x180014b60  mov     [r15+5], al
0x180014b64  mov     eax, [r14+8]
0x180014b68  mov     [r15+8], eax
0x180014b6c  mov     esi, 8007000Dh
0x180014b71  jmp     short loc_180014BC6
0x180014b73  mov     rdi, [rbp+var_50]
0x180014b77  mov     rax, [rdi]
0x180014b7a  mov     rbx, [rax+60h]
0x180014b7e  mov     [rbp+var_18], r13
0x180014b82  mov     r9d, 14h; unsigned int
0x180014b88  lea     r8d, [r9+1]; unsigned int
0x180014b8c  lea     rdx, aUsehardcodedde; "UseHardcodedDefaults"
0x180014b93  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014b97  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014b9c  nop
0x180014b9d  lea     rsi, [r15+4]
0x180014ba1  mov     r8, rsi
0x180014ba4  mov     rdx, [rbp+var_18]
0x180014ba8  mov     rcx, rdi
0x180014bab  mov     rax, rbx
0x180014bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb3  nop
0x180014bb4  shr     eax, 1Fh
0x180014bb7  test    al, al
0x180014bb9  jz      short loc_180014BBE
0x180014bbb  mov     [rsi], r13b
0x180014bbe  cmp     [rsi], r13b
0x180014bc1  jz      short loc_180014BCB
0x180014bc3  mov     esi, r13d
0x180014bc6  jmp     loc_180014C8A
0x180014bcb  mov     r12d, r13d
0x180014bce  mov     rdi, [rbp+var_50]
0x180014bd2  mov     rax, [rdi]
0x180014bd5  mov     rbx, [rax+60h]
0x180014bd9  mov     [rbp+var_18], r13
0x180014bdd  mov     r9d, 0Bh; unsigned int
0x180014be3  lea     r8d, [r9+1]; unsigned int
0x180014be7  lea     rdx, aScanenabled; "ScanEnabled"
0x180014bee  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014bf2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014bf7  nop
0x180014bf8  lea     r8, [r15+5]
0x180014bfc  mov     rdx, [rbp+var_18]
0x180014c00  mov     rcx, rdi
0x180014c03  mov     rax, rbx
0x180014c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c0b  nop
0x180014c0c  shr     eax, 1Fh
0x180014c0f  mov     esi, 8007000Dh
0x180014c14  test    al, al
0x180014c16  jz      short loc_180014C23
0x180014c18  mov     al, [r14+5]
0x180014c1c  mov     [r15+5], al
0x180014c20  mov     r12d, esi
0x180014c23  xorps   xmm0, xmm0
0x180014c26  movsd   [rbp+var_48], xmm0
0x180014c2b  mov     rdi, [rbp+var_50]
0x180014c2f  mov     rax, [rdi]
0x180014c32  mov     rbx, [rax+58h]
0x180014c36  mov     [rbp+var_18], 0
0x180014c3e  mov     r9d, 11h; unsigned int
0x180014c44  lea     r8d, [r9+1]; unsigned int
0x180014c48  lea     rdx, aScancooldownho; "ScanCooldownHours"
0x180014c4f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014c53  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014c58  nop
0x180014c59  lea     r8, [rbp+var_48]
0x180014c5d  mov     rdx, [rbp+var_18]
0x180014c61  mov     rcx, rdi
0x180014c64  mov     rax, rbx
0x180014c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c6c  nop
0x180014c6d  shr     eax, 1Fh
0x180014c70  test    al, al
0x180014c72  jz      short loc_180014C7D
0x180014c74  mov     r12d, esi
0x180014c77  mov     eax, [r14+8]
0x180014c7b  jmp     short loc_180014C83
0x180014c7d  cvttsd2si rax, [rbp+var_48]
0x180014c83  mov     [r15+8], eax
0x180014c87  mov     esi, r12d
0x180014c8a  lea     rcx, [rbp+var_50]
0x180014c8e  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014c93  nop
0x180014c94  mov     rcx, [rbp+var_40]
0x180014c98  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014c9d  mov     eax, esi
0x180014c9f  mov     rcx, [rbp+var_10]
0x180014ca3  xor     rcx, rsp; StackCookie
0x180014ca6  call    __security_check_cookie
0x180014cab  mov     rbx, [rsp+70h+arg_8]
0x180014cb3  add     rsp, 70h
0x180014cb7  pop     r15
0x180014cb9  pop     r14
0x180014cbb  pop     r13
0x180014cbd  pop     r12
0x180014cbf  pop     rdi
0x180014cc0  pop     rsi
0x180014cc1  pop     rbp
0x180014cc2  retn
```
