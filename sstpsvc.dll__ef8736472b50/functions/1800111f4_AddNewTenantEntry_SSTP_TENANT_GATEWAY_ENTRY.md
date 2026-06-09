# AddNewTenantEntry(_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x1800111f4`
- end: `0x180011422`
- name: `?AddNewTenantEntry@@YAKPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `558`
- prototype: `unsigned int __fastcall(struct _SSTP_TENANT_GATEWAY_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014900`

## callees

- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x18001052c`
- `0x180010998`
- `0x180010b08`
- `0x1800111f4`
- `0x1800134bc`
- `0x180013524`
- `0x180013fe0`
- `0x18001cfb4`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800112cb`
- `msvcrt!_wcsicmp` at `0x1800112cb`

## string_xrefs

- `0x1800112f6`: `SstpSvcCreateUpdateTenantGatewayMapping: Duplicate Gateway name %ws`
- `0x180011377`: `SstpSvcCreateUpdateTenantGatewayMapping: Invalid Gateway name %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddNewTenantEntry(struct _SSTP_TENANT_GATEWAY_ENTRY *a1)
{
  unsigned int v2; // r13d
  unsigned int i; // r15d
  __int64 v4; // r12
  __int64 j; // rsi
  unsigned __int64 v6; // rbx
  bool v7; // zf
  const wchar_t *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  struct TenantGatewayMap *Instance; // [rsp+20h] [rbp-E0h]
  __int128 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h]
  _BYTE v16[40]; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v14 = 0;
  v15 = 0;
  v2 = 0;
  Instance = TenantGatewayMap::GetInstance();
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
  {
    v4 = 510LL * i;
    v2 = CheckGatewayName((PCWSTR)(v4 + *((_QWORD *)a1 + 3)));
    if ( v2 )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(
          &v17,
          L"SstpSvcCreateUpdateTenantGatewayMapping: Invalid Gateway name %ws",
          v4 + *((_QWORD *)a1 + 3));
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
      }
    }
    else
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v14 + 1) - v14) >> 3);
        v7 = (unsigned int)j == v6;
        if ( (unsigned int)j >= v6 )
          break;
        v8 = (const wchar_t *)(v14 + 40 * j);
        if ( *((_QWORD *)v8 + 3) >= 8u )
          v8 = *(const wchar_t **)v8;
        if ( !_wcsicmp((const wchar_t *)(v4 + *((_QWORD *)a1 + 3)), v8) )
        {
          if ( (byte_18002E903 & 0x10) != 0 )
          {
            LOWORD(v17) = 0;
            FormatRRASErrorString(
              &v17,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Duplicate Gateway name %ws",
              v4 + *((_QWORD *)a1 + 3));
            if ( (byte_18002E903 & 0x10) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v17);
          }
          v7 = (unsigned int)j == v6;
          break;
        }
      }
      if ( v7 )
      {
        std::wstring::wstring(v16, v4 + *((_QWORD *)a1 + 3));
        std::vector<std::wstring>::push_back(&v14, v16);
        LOBYTE(v9) = 1;
        std::wstring::_Tidy(v16, v9, 0);
      }
    }
  }
  std::wstring::wstring(v16, *((_QWORD *)a1 + 1));
  v10 = std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](
          (char *)Instance + 8,
          v16);
  std::vector<std::wstring>::operator=(v10, &v14);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v16, v11, 0);
  std::vector<std::wstring>::_Tidy(&v14);
  return v2;
}

```

## disassembly

```asm
0x1800111f4  push    rbp
0x1800111f6  push    rbx
0x1800111f7  push    rsi
0x1800111f8  push    rdi
0x1800111f9  push    r12
0x1800111fb  push    r13
0x1800111fd  push    r14
0x1800111ff  push    r15
0x180011201  lea     rbp, [rsp-788h]
0x180011209  sub     rsp, 888h
0x180011210  mov     rax, cs:__security_cookie
0x180011217  xor     rax, rsp
0x18001121a  mov     [rbp+7C0h+var_50], rax
0x180011221  mov     rdi, rcx
0x180011224  xorps   xmm0, xmm0
0x180011227  movdqu  [rsp+8C0h+var_898], xmm0
0x18001122d  mov     [rsp+8C0h+var_888], 0
0x180011236  xor     r13d, r13d
0x180011239  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x18001123e  mov     [rsp+8C0h+var_8A0], rax
0x180011243  xor     eax, eax
0x180011245  mov     [rsp+8C0h+var_850], eax
0x180011249  xor     edx, edx; Val
0x18001124b  mov     r8d, 7FCh; Size
0x180011251  lea     rcx, [rsp+8C0h+var_84C]; void *
0x180011256  call    memset_0
0x18001125b  xor     r15d, r15d
0x18001125e  cmp     r15d, [rdi+10h]
0x180011262  jnb     loc_1800113B1
0x180011268  mov     eax, r15d
0x18001126b  imul    r12, rax, 1FEh
0x180011272  mov     rcx, [rdi+18h]
0x180011276  add     rcx, r12; pszName
0x180011279  call    CheckGatewayName
0x18001127e  mov     r13d, eax
0x180011281  test    eax, eax
0x180011283  jnz     loc_180011360
0x180011289  xor     esi, esi
0x18001128b  mov     r14d, esi
0x18001128e  mov     rbx, qword ptr [rsp+8C0h+var_898+8]
0x180011293  mov     rcx, qword ptr [rsp+8C0h+var_898]
0x180011298  sub     rbx, rcx
0x18001129b  sar     rbx, 3
0x18001129f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800112a9  imul    rbx, rax
0x1800112ad  cmp     r14, rbx
0x1800112b0  jnb     short loc_18001132B
0x1800112b2  lea     rax, [rsi+rsi*4]
0x1800112b6  lea     rdx, [rcx+rax*8]
0x1800112ba  cmp     qword ptr [rdx+18h], 8
0x1800112bf  jb      short loc_1800112C4
0x1800112c1  mov     rdx, [rdx]; String2
0x1800112c4  mov     rcx, [rdi+18h]
0x1800112c8  add     rcx, r12; String1
0x1800112cb  call    cs:__imp__wcsicmp
0x1800112d2  nop     dword ptr [rax+rax+00h]
0x1800112d7  test    eax, eax
0x1800112d9  jz      short loc_1800112DF
0x1800112db  inc     esi
0x1800112dd  jmp     short loc_18001128B
0x1800112df  test    cs:byte_18002E903, 10h
0x1800112e6  jz      short loc_180011328
0x1800112e8  xor     eax, eax
0x1800112ea  mov     word ptr [rsp+8C0h+var_850], ax
0x1800112ef  mov     r8, [rdi+18h]
0x1800112f3  add     r8, r12
0x1800112f6  lea     rdx, aSstpsvccreateu_5; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800112fd  lea     rcx, [rsp+8C0h+var_850]
0x180011302  call    FormatRRASErrorString
0x180011307  test    cs:byte_18002E903, 10h
0x18001130e  jz      short loc_180011328
0x180011310  lea     r8, [rsp+8C0h+var_850]
0x180011315  lea     rdx, RasSSTPSvcTraceInfo
0x18001131c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011323  call    McTemplateU0z_EventWriteTransfer
0x180011328  cmp     r14, rbx
0x18001132b  jnz     short loc_1800113A9
0x18001132d  mov     rdx, [rdi+18h]
0x180011331  add     rdx, r12
0x180011334  lea     rcx, [rsp+8C0h+var_878]
0x180011339  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001133e  nop
0x18001133f  lea     rdx, [rsp+8C0h+var_878]
0x180011344  lea     rcx, [rsp+8C0h+var_898]
0x180011349  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18001134e  nop
0x18001134f  xor     r8d, r8d
0x180011352  mov     dl, 1
0x180011354  lea     rcx, [rsp+8C0h+var_878]
0x180011359  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001135e  jmp     short loc_1800113A9
0x180011360  test    cs:byte_18002E903, 8
0x180011367  jz      short loc_1800113A9
0x180011369  xor     eax, eax
0x18001136b  mov     word ptr [rsp+8C0h+var_850], ax
0x180011370  mov     r8, [rdi+18h]
0x180011374  add     r8, r12
0x180011377  lea     rdx, aSstpsvccreateu_3; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x18001137e  lea     rcx, [rsp+8C0h+var_850]
0x180011383  call    FormatRRASErrorString
0x180011388  test    cs:byte_18002E903, 8
0x18001138f  jz      short loc_1800113A9
0x180011391  lea     r8, [rsp+8C0h+var_850]
0x180011396  lea     rdx, RasSSTPSvcTraceError
0x18001139d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800113a4  call    McTemplateU0z_EventWriteTransfer
0x1800113a9  inc     r15d
0x1800113ac  jmp     loc_18001125E
0x1800113b1  mov     rbx, [rsp+8C0h+var_8A0]
0x1800113b6  mov     rdx, [rdi+8]
0x1800113ba  lea     rcx, [rsp+8C0h+var_878]
0x1800113bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800113c4  nop
0x1800113c5  lea     rdx, [rsp+8C0h+var_878]
0x1800113ca  lea     rcx, [rbx+8]
0x1800113ce  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x1800113d3  mov     rcx, rax
0x1800113d6  lea     rdx, [rsp+8C0h+var_898]
0x1800113db  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x1800113e0  nop
0x1800113e1  xor     r8d, r8d
0x1800113e4  mov     dl, 1
0x1800113e6  lea     rcx, [rsp+8C0h+var_878]
0x1800113eb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800113f0  nop
0x1800113f1  lea     rcx, [rsp+8C0h+var_898]
0x1800113f6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800113fb  mov     eax, r13d
0x1800113fe  mov     rcx, [rbp+7C0h+var_50]
0x180011405  xor     rcx, rsp; StackCookie
0x180011408  call    __security_check_cookie
0x18001140d  add     rsp, 888h
0x180011414  pop     r15
0x180011416  pop     r14
0x180011418  pop     r13
0x18001141a  pop     r12
0x18001141c  pop     rdi
0x18001141d  pop     rsi
0x18001141e  pop     rbx
0x18001141f  pop     rbp
0x180011420  retn
```
