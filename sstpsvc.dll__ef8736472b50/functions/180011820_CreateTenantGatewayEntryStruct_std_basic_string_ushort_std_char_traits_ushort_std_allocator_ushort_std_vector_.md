# CreateTenantGatewayEntryStruct(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x180011820`
- end: `0x18001199f`
- name: `?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151e0`

## callees

- `0x180008b90`
- `0x180011820`
- `0x1800134bc`
- `0x180013524`
- `0x18001378c`
- `0x18001cd60`
- `0x18001d210`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001190b`
- `msvcrt!wcscpy_s` at `0x18001194f`
- `msvcrt!wcscpy_s` at `0x18001190b`
- `msvcrt!wcscpy_s` at `0x18001194f`

## string_xrefs

- `0x180011890`: `CreateTenantGatewayEntryStruct: Failed to allocate memory for GATEWAY_CONFIG structure.`
- `0x1800118e7`: `CreateTenantGatewayEntryStruct: Failed to allocate memory for WCHAR.`

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
      if ( (byte_18002E903 & 8) == 0 )
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
    if ( (byte_18002E903 & 8) != 0 )
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
0x180011820  mov     [rsp+arg_18], rbx
0x180011825  push    rbp
0x180011826  push    rsi
0x180011827  push    rdi
0x180011828  push    r14
0x18001182a  push    r15
0x18001182c  sub     rsp, 40h
0x180011830  mov     rax, cs:__security_cookie
0x180011837  xor     rax, rsp
0x18001183a  mov     [rsp+68h+var_30], rax
0x18001183f  mov     rsi, r8
0x180011842  mov     r14, rdx
0x180011845  mov     rdi, rcx
0x180011848  mov     [rsp+68h+var_38], rcx
0x18001184d  mov     [rsp+68h+var_40], rdx
0x180011852  mov     rax, [rdx+8]
0x180011856  sub     rax, [rdx]
0x180011859  sar     rax, 3
0x18001185d  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x180011867  imul    rax, rbx
0x18001186b  imul    rcx, rax, 1FEh; size
0x180011872  call    MIDL_user_allocate
0x180011877  mov     [rsi+18h], rax
0x18001187b  test    rax, rax
0x18001187e  jnz     short loc_1800118AF
0x180011880  lea     ebx, [rax+0Eh]
0x180011883  test    cs:byte_18002E903, 8
0x18001188a  jz      loc_180011965
0x180011890  lea     r8, aCreatetenantga_0; "CreateTenantGatewayEntryStruct: Failed "...
0x180011897  lea     rdx, RasSSTPSvcTraceError
0x18001189e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800118a5  call    McTemplateU0z_EventWriteTransfer
0x1800118aa  jmp     loc_180011965
0x1800118af  mov     rax, [r14+8]
0x1800118b3  sub     rax, [r14]
0x1800118b6  sar     rax, 3
0x1800118ba  imul    rax, rbx
0x1800118be  mov     [rsi+10h], eax
0x1800118c1  mov     rcx, [rdi+10h]
0x1800118c5  lea     rcx, ds:2[rcx*2]; size
0x1800118cd  call    MIDL_user_allocate
0x1800118d2  mov     [rsi+8], rax
0x1800118d6  test    rax, rax
0x1800118d9  jnz     short loc_1800118F0
0x1800118db  lea     ebx, [rax+0Eh]
0x1800118de  test    cs:byte_18002E903, 8
0x1800118e5  jz      short loc_180011965
0x1800118e7  lea     r8, aCreatetenantga; "CreateTenantGatewayEntryStruct: Failed "...
0x1800118ee  jmp     short loc_180011897
0x1800118f0  xor     ebx, ebx
0x1800118f2  cmp     qword ptr [rdi+18h], 8
0x1800118f7  jb      short loc_1800118FE
0x1800118f9  mov     r8, [rdi]
0x1800118fc  jmp     short loc_180011901
0x1800118fe  mov     r8, rdi; Source
0x180011901  mov     rdx, [rdi+10h]
0x180011905  inc     rdx; SizeInWords
0x180011908  mov     rcx, rax; Destination
0x18001190b  call    cs:__imp_wcscpy_s
0x180011912  nop     dword ptr [rax+rax+00h]
0x180011917  mov     eax, [rdi+10h]
0x18001191a  inc     eax
0x18001191c  mov     [rsi], eax
0x18001191e  xor     ebp, ebp
0x180011920  cmp     [rsi+10h], ebx
0x180011923  jbe     short loc_180011962
0x180011925  mov     r15d, ebp
0x180011928  mov     edx, ebp
0x18001192a  mov     rcx, r14
0x18001192d  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x180011932  cmp     qword ptr [rax+18h], 8
0x180011937  jb      short loc_18001193C
0x180011939  mov     rax, [rax]
0x18001193c  imul    rcx, r15, 1FEh
0x180011943  add     rcx, [rsi+18h]; Destination
0x180011947  mov     r8, rax; Source
0x18001194a  mov     edx, 0FFh; SizeInWords
0x18001194f  call    cs:__imp_wcscpy_s
0x180011956  nop     dword ptr [rax+rax+00h]
0x18001195b  inc     ebp
0x18001195d  cmp     ebp, [rsi+10h]
0x180011960  jb      short loc_180011925
0x180011962  mov     [rsi+20h], ebx
0x180011965  xor     r8d, r8d
0x180011968  mov     dl, 1
0x18001196a  mov     rcx, rdi
0x18001196d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011972  nop
0x180011973  mov     rcx, r14
0x180011976  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001197b  mov     eax, ebx
0x18001197d  mov     rcx, [rsp+68h+var_30]
0x180011982  xor     rcx, rsp; StackCookie
0x180011985  call    __security_check_cookie
0x18001198a  mov     rbx, [rsp+68h+arg_18]
0x180011992  add     rsp, 40h
0x180011996  pop     r15
0x180011998  pop     r14
0x18001199a  pop     rdi
0x18001199b  pop     rsi
0x18001199c  pop     rbp
0x18001199d  retn
```
