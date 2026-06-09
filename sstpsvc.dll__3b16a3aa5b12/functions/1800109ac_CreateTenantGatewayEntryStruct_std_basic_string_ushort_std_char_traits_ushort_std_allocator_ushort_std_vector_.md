# CreateTenantGatewayEntryStruct(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x1800109ac`
- end: `0x180010b1e`
- name: `?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014170`

## callees

- `0x180008360`
- `0x1800109ac`
- `0x1800124fc`
- `0x180012560`
- `0x1800127c0`
- `0x18001b880`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010a97`
- `msvcrt!wcscpy_s` at `0x180010ad5`
- `msvcrt!wcscpy_s` at `0x180010a97`
- `msvcrt!wcscpy_s` at `0x180010ad5`

## string_xrefs

- `0x180010a1c`: `CreateTenantGatewayEntryStruct: Failed to allocate memory for GATEWAY_CONFIG structure.`
- `0x180010a73`: `CreateTenantGatewayEntryStruct: Failed to allocate memory for WCHAR.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateTenantGatewayEntryStruct(wchar_t *Source, _QWORD *a2, __int64 a3)
{
  void *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  const wchar_t *v9; // r8
  wchar_t *v10; // rax
  const wchar_t *v11; // r8
  unsigned int i; // ebp
  __int64 v13; // rax

  v6 = MIDL_user_allocate(102 * ((__int64)(a2[1] - *a2) >> 3));
  *(_QWORD *)(a3 + 24) = v6;
  if ( v6 )
  {
    *(_DWORD *)(a3 + 16) = -858993459 * ((__int64)(a2[1] - *a2) >> 3);
    v10 = (wchar_t *)MIDL_user_allocate(2LL * *((_QWORD *)Source + 2) + 2);
    *(_QWORD *)(a3 + 8) = v10;
    if ( !v10 )
    {
      v8 = 14;
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_16;
      v9 = L"CreateTenantGatewayEntryStruct: Failed to allocate memory for WCHAR.";
      goto LABEL_4;
    }
    v8 = 0;
    if ( *((_QWORD *)Source + 3) < 8u )
      v11 = Source;
    else
      v11 = *(const wchar_t **)Source;
    wcscpy_s(v10, *((_QWORD *)Source + 2) + 1LL, v11);
    *(_DWORD *)a3 = *((_DWORD *)Source + 4) + 1;
    for ( i = 0; i < *(_DWORD *)(a3 + 16); ++i )
    {
      v13 = std::vector<std::wstring>::at(a2, i);
      if ( *(_QWORD *)(v13 + 24) >= 8u )
        v13 = *(_QWORD *)v13;
      wcscpy_s((wchar_t *)(*(_QWORD *)(a3 + 24) + 510LL * i), 0xFFu, (const wchar_t *)v13);
    }
    *(_DWORD *)(a3 + 32) = 0;
  }
  else
  {
    v8 = 14;
    if ( (byte_18002D803 & 8) != 0 )
    {
      v9 = L"CreateTenantGatewayEntryStruct: Failed to allocate memory for GATEWAY_CONFIG structure.";
LABEL_4:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v9);
    }
  }
LABEL_16:
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(Source, v7, 0);
  std::vector<std::wstring>::_Tidy(a2);
  return v8;
}

```

## disassembly

```asm
0x1800109ac  mov     [rsp+arg_18], rbx
0x1800109b1  push    rbp
0x1800109b2  push    rsi
0x1800109b3  push    rdi
0x1800109b4  push    r14
0x1800109b6  push    r15
0x1800109b8  sub     rsp, 40h
0x1800109bc  mov     rax, cs:__security_cookie
0x1800109c3  xor     rax, rsp
0x1800109c6  mov     [rsp+68h+var_30], rax
0x1800109cb  mov     rsi, r8
0x1800109ce  mov     r14, rdx
0x1800109d1  mov     rdi, rcx
0x1800109d4  mov     [rsp+68h+var_38], rcx
0x1800109d9  mov     [rsp+68h+var_40], rdx
0x1800109de  mov     rax, [rdx+8]
0x1800109e2  sub     rax, [rdx]
0x1800109e5  sar     rax, 3
0x1800109e9  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x1800109f3  imul    rax, rbx
0x1800109f7  imul    rcx, rax, 1FEh; size
0x1800109fe  call    MIDL_user_allocate
0x180010a03  mov     [rsi+18h], rax
0x180010a07  test    rax, rax
0x180010a0a  jnz     short loc_180010A3B
0x180010a0c  lea     ebx, [rax+0Eh]
0x180010a0f  test    cs:byte_18002D803, 8
0x180010a16  jz      loc_180010AE5
0x180010a1c  lea     r8, aCreatetenantga_0; "CreateTenantGatewayEntryStruct: Failed "...
0x180010a23  lea     rdx, RasSSTPSvcTraceError
0x180010a2a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010a31  call    McTemplateU0z_EventWriteTransfer
0x180010a36  jmp     loc_180010AE5
0x180010a3b  mov     rax, [r14+8]
0x180010a3f  sub     rax, [r14]
0x180010a42  sar     rax, 3
0x180010a46  imul    rax, rbx
0x180010a4a  mov     [rsi+10h], eax
0x180010a4d  mov     rcx, [rdi+10h]
0x180010a51  lea     rcx, ds:2[rcx*2]; size
0x180010a59  call    MIDL_user_allocate
0x180010a5e  mov     [rsi+8], rax
0x180010a62  test    rax, rax
0x180010a65  jnz     short loc_180010A7C
0x180010a67  lea     ebx, [rax+0Eh]
0x180010a6a  test    cs:byte_18002D803, 8
0x180010a71  jz      short loc_180010AE5
0x180010a73  lea     r8, aCreatetenantga; "CreateTenantGatewayEntryStruct: Failed "...
0x180010a7a  jmp     short loc_180010A23
0x180010a7c  xor     ebx, ebx
0x180010a7e  cmp     qword ptr [rdi+18h], 8
0x180010a83  jb      short loc_180010A8A
0x180010a85  mov     r8, [rdi]
0x180010a88  jmp     short loc_180010A8D
0x180010a8a  mov     r8, rdi; Source
0x180010a8d  mov     rdx, [rdi+10h]
0x180010a91  inc     rdx; SizeInWords
0x180010a94  mov     rcx, rax; Destination
0x180010a97  call    cs:__imp_wcscpy_s
0x180010a9d  mov     eax, [rdi+10h]
0x180010aa0  inc     eax
0x180010aa2  mov     [rsi], eax
0x180010aa4  xor     ebp, ebp
0x180010aa6  cmp     [rsi+10h], ebx
0x180010aa9  jbe     short loc_180010AE2
0x180010aab  mov     r15d, ebp
0x180010aae  mov     edx, ebp
0x180010ab0  mov     rcx, r14
0x180010ab3  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x180010ab8  cmp     qword ptr [rax+18h], 8
0x180010abd  jb      short loc_180010AC2
0x180010abf  mov     rax, [rax]
0x180010ac2  imul    rcx, r15, 1FEh
0x180010ac9  add     rcx, [rsi+18h]; Destination
0x180010acd  mov     r8, rax; Source
0x180010ad0  mov     edx, 0FFh; SizeInWords
0x180010ad5  call    cs:__imp_wcscpy_s
0x180010adb  inc     ebp
0x180010add  cmp     ebp, [rsi+10h]
0x180010ae0  jb      short loc_180010AAB
0x180010ae2  mov     [rsi+20h], ebx
0x180010ae5  xor     r8d, r8d
0x180010ae8  mov     dl, 1
0x180010aea  mov     rcx, rdi
0x180010aed  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180010af2  nop
0x180010af3  mov     rcx, r14
0x180010af6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180010afb  mov     eax, ebx
0x180010afd  mov     rcx, [rsp+68h+var_30]
0x180010b02  xor     rcx, rsp; StackCookie
0x180010b05  call    __security_check_cookie
0x180010b0a  mov     rbx, [rsp+68h+arg_18]
0x180010b12  add     rsp, 40h
0x180010b16  pop     r15
0x180010b18  pop     r14
0x180010b1a  pop     rdi
0x180010b1b  pop     rsi
0x180010b1c  pop     rbp
0x180010b1d  retn
```
