# CBioKeyVault::_OpenVault(void)

- ea: `0x1800382f4`
- end: `0x18003848a`
- name: `?_OpenVault@CBioKeyVault@@AEAAJXZ`
- size: `406`
- prototype: `__int64 __fastcall(CBioKeyVault *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002da38`
- `0x1800985b8`
- `0x180098854`

## callees

- `0x1800382f4`
- `0x180055928`
- `0x180057c8c`
- `0x180068f60`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x180038387`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x180038387`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x180038355`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x180038355`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x180038446`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x180038446`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x180038324`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18003846a`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x180038324`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18003846a`

## pseudocode

```c
__int64 __fastcall CBioKeyVault::_OpenVault(CBioKeyVault *this)
{
  int v3; // eax
  unsigned int v4; // ebx
  signed int ItemType; // eax
  bool v6; // cc
  __int64 v7; // rcx
  __int64 v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v10; // [rsp+30h] [rbp-D0h]
  __int128 v11; // [rsp+50h] [rbp-B0h]
  __int128 v12; // [rsp+60h] [rbp-A0h]
  __int128 v13; // [rsp+70h] [rbp-90h]
  _OWORD v14[4]; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v16; // [rsp+C4h] [rbp-3Ch]
  int v17; // [rsp+CCh] [rbp-34h]
  int v18; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+D4h] [rbp-2Ch]
  int v20; // [rsp+DCh] [rbp-24h]
  int v21; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v22; // [rsp+E4h] [rbp-1Ch]
  int v23; // [rsp+ECh] [rbp-14h]

  v8 = 0;
  if ( *(_QWORD *)this )
  {
    VaultFree(0);
    return 0;
  }
  v10 = 258;
  v9 = *_lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&v15, (__int64)this);
  v3 = VaultOpenVault((char *)this + 8, 0, this);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_14;
  }
  ItemType = VaultGetItemType(*(_QWORD *)this, &CBioKeyVault::_guidSchema, 0, &v8);
  if ( ItemType )
  {
    if ( ItemType != 1168 )
    {
      v6 = ItemType <= 0;
LABEL_9:
      if ( !v6 )
        ItemType = (unsigned __int16)ItemType | 0x80070000;
      v4 = ItemType;
      goto LABEL_14;
    }
    v7 = *(_QWORD *)this;
    *(_QWORD *)&v11 = L"WinBio Key Schema";
    v14[0] = CBioKeyVault::_guidSchema;
    *((_QWORD *)&v11 + 1) = &v15;
    *(_QWORD *)&v12 = &v18;
    *((_QWORD *)&v12 + 1) = &v21;
    v14[1] = v11;
    v13 = 0u;
    v14[2] = v12;
    v15 = 1;
    v16 = 7;
    v17 = 0;
    v18 = 2;
    v19 = 8;
    v20 = 0;
    v21 = 3;
    v22 = 8;
    v23 = 0;
    v14[3] = 0u;
    ItemType = VaultCreateItemType(v7, v14, 0);
    v6 = ItemType <= 0;
    if ( ItemType )
      goto LABEL_9;
  }
  HIBYTE(v10) = 0;
  v4 = 0;
LABEL_14:
  wil::details::ScopeExitFnGuard__lambda_4507a43c5d90d3105f64c9437727e96e___::operator()(&v9);
  VaultFree(v8);
  return v4;
}

```

## disassembly

```asm
0x1800382f4  push    rbp
0x1800382f6  push    rbx
0x1800382f7  push    rsi
0x1800382f8  push    rdi
0x1800382f9  lea     rbp, [rsp-8]
0x1800382fe  sub     rsp, 108h
0x180038305  mov     rax, cs:__security_cookie
0x18003830c  xor     rax, rsp
0x18003830f  mov     [rbp+20h+var_30], rax
0x180038313  xor     esi, esi
0x180038315  mov     rdi, rcx
0x180038318  mov     [rsp+120h+var_100], rsi
0x18003831d  cmp     [rcx], rsi
0x180038320  jz      short loc_180038331
0x180038322  xor     ecx, ecx
0x180038324  call    cs:__imp_VaultFree
0x18003832a  xor     eax, eax
0x18003832c  jmp     loc_180038472
0x180038331  mov     rdx, rdi
0x180038334  lea     rcx, [rbp+20h+var_60]
0x180038338  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18003833d  mov     r8, rdi
0x180038340  mov     [rsp+120h+var_F0], 102h
0x180038347  xor     edx, edx
0x180038349  mov     rcx, [rax]
0x18003834c  mov     [rsp+120h+var_F8], rcx
0x180038351  lea     rcx, [rdi+8]
0x180038355  call    cs:__imp_VaultOpenVault
0x18003835b  mov     ebx, eax
0x18003835d  test    eax, eax
0x18003835f  jz      short loc_180038375
0x180038361  jle     loc_18003845B
0x180038367  movzx   ebx, ax
0x18003836a  or      ebx, 80070000h
0x180038370  jmp     loc_18003845B
0x180038375  mov     rcx, [rdi]
0x180038378  lea     r9, [rsp+120h+var_100]
0x18003837d  xor     r8d, r8d
0x180038380  lea     rdx, ?_guidSchema@CBioKeyVault@@0U_GUID@@A; _GUID CBioKeyVault::_guidSchema
0x180038387  call    cs:__imp_VaultGetItemType
0x18003838d  test    eax, eax
0x18003838f  jz      loc_180038454
0x180038395  cmp     eax, 490h
0x18003839a  jz      short loc_1800383AF
0x18003839c  test    eax, eax
0x18003839e  jle     short loc_1800383A8
0x1800383a0  movzx   eax, ax
0x1800383a3  or      eax, 80070000h
0x1800383a8  mov     ebx, eax
0x1800383aa  jmp     loc_18003845B
0x1800383af  movups  xmm0, xmmword ptr cs:?_guidSchema@CBioKeyVault@@0U_GUID@@A.Data1; _GUID CBioKeyVault::_guidSchema ...
0x1800383b6  mov     rcx, [rdi]
0x1800383b9  lea     rax, aWinbioKeySchem; "WinBio Key Schema"
0x1800383c0  mov     qword ptr [rsp+120h+var_D0], rax
0x1800383c5  lea     rdx, [rbp+20h+var_A0]
0x1800383c9  movaps  [rbp+20h+var_A0], xmm0
0x1800383cd  lea     rax, [rbp+20h+var_60]
0x1800383d1  mov     qword ptr [rsp+120h+var_D0+8], rax
0x1800383d6  xor     r8d, r8d
0x1800383d9  movaps  xmm0, [rsp+120h+var_D0]
0x1800383de  lea     rax, [rbp+20h+var_50]
0x1800383e2  mov     qword ptr [rsp+120h+var_C0], rax
0x1800383e7  lea     rax, [rbp+20h+var_40]
0x1800383eb  mov     qword ptr [rsp+120h+var_C0+8], rax
0x1800383f0  movaps  xmm1, [rsp+120h+var_C0]
0x1800383f5  movaps  [rbp+20h+var_90], xmm0
0x1800383f9  mov     qword ptr [rsp+120h+var_B0], rsi
0x1800383fe  mov     qword ptr [rsp+120h+var_B0+8], rsi
0x180038403  movaps  xmm0, [rsp+120h+var_B0]
0x180038408  movaps  [rbp+20h+var_80], xmm1
0x18003840c  mov     [rbp+20h+var_60], 1
0x180038413  mov     [rbp+20h+var_5C], 7
0x18003841b  mov     [rbp+20h+var_54], esi
0x18003841e  mov     [rbp+20h+var_50], 2
0x180038425  mov     [rbp+20h+var_4C], 8
0x18003842d  mov     [rbp+20h+var_44], esi
0x180038430  mov     [rbp+20h+var_40], 3
0x180038437  mov     [rbp+20h+var_3C], 8
0x18003843f  mov     [rbp+20h+var_34], esi
0x180038442  movaps  [rbp+20h+var_70], xmm0
0x180038446  call    cs:__imp_VaultCreateItemType
0x18003844c  test    eax, eax
0x18003844e  jnz     loc_18003839E
0x180038454  mov     byte ptr [rsp+120h+var_F0+1], sil
0x180038459  mov     ebx, esi
0x18003845b  lea     rcx, [rsp+120h+var_F8]
0x180038460  call    wil__details__ScopeExitFnGuard__lambda_4507a43c5d90d3105f64c9437727e96e_____operator__
0x180038465  mov     rcx, [rsp+120h+var_100]
0x18003846a  call    cs:__imp_VaultFree
0x180038470  mov     eax, ebx
0x180038472  mov     rcx, [rbp+20h+var_30]
0x180038476  xor     rcx, rsp; StackCookie
0x180038479  call    __security_check_cookie
0x18003847e  add     rsp, 108h
0x180038485  pop     rdi
0x180038486  pop     rsi
0x180038487  pop     rbx
0x180038488  pop     rbp
0x180038489  retn
```
