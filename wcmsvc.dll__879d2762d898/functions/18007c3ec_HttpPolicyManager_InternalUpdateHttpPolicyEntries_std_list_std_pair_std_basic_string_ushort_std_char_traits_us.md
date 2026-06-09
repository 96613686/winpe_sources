# HttpPolicyManager::InternalUpdateHttpPolicyEntries(std::list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x18007c3ec`
- end: `0x18007c74a`
- name: `?InternalUpdateHttpPolicyEntries@HttpPolicyManager@@AEAAKAEBV?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007c36c`

## callees

- `0x18000dd88`
- `0x1800137a0`
- `0x1800664ec`
- `0x18007c3ec`
- `0x180084f50`
- `0x1800ceb2c`
- `0x1800ced1c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18007c4a2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18007c4a2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c641`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c6e0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c641`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c6e0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007c56f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007c56f`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18007c560`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18007c560`
- `WINHTTP!WinHttpConnectionDeletePolicyEntries` at `0x18007c5e6`
- `WINHTTP!WinHttpConnectionDeletePolicyEntries` at `0x18007c5e6`
- `WINHTTP!WinHttpConnectionSetPolicyEntries` at `0x18007c68d`
- `WINHTTP!WinHttpConnectionSetPolicyEntries` at `0x18007c68d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HttpPolicyManager::InternalUpdateHttpPolicyEntries(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rdi
  _QWORD *i; // rbx
  _QWORD *v8; // rax
  unsigned __int16 *v9; // rcx
  int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rsi
  __int64 j; // rbx
  void *v15; // rcx
  unsigned int v17; // esi
  __int64 v18; // rdi
  __int64 k; // rbx
  void *v20; // rcx
  _QWORD v21[2]; // [rsp+20h] [rbp-98h] BYREF
  char v22; // [rsp+30h] [rbp-88h]
  __int128 v23; // [rsp+38h] [rbp-80h] BYREF
  __int128 v24; // [rsp+48h] [rbp-70h] BYREF
  PSID pSid[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v26; // [rsp+68h] [rbp-50h]
  __int64 v27; // [rsp+78h] [rbp-40h]
  __int128 v28; // [rsp+80h] [rbp-38h] BYREF
  __int64 v29; // [rsp+90h] [rbp-28h]

  v23 = 0;
  DWORD2(v23) = *(_DWORD *)(a2 + 8);
  v28 = 0;
  v29 = 0;
  std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v28);
  v21[1] = &v28;
  v22 = 1;
  if ( DWORD2(v23) )
  {
    v5 = *(_QWORD *)(v4 + 8);
    v21[0] = v5;
    if ( v5 > 0x6DB6DB6DB6DB6DB7LL * ((v29 - (__int64)v28) >> 3) )
    {
      if ( v5 > 0x492492492492492LL )
        std::_Xlength_error("vector too long");
      std::vector<_WINHTTP_CONNECTION_POLICY_ENTRY>::_Reallocate<0>(&v28, v21);
    }
    v6 = *(_QWORD **)a2;
    for ( i = (_QWORD *)*v6; i != v6; i = (_QWORD *)*i )
    {
      HIDWORD(pSid[0]) = 0;
      DWORD1(v26) = 0;
      HIDWORD(v27) = 0;
      v8 = i + 2;
      if ( i[5] > 7u )
        v8 = (_QWORD *)*v8;
      *(_QWORD *)&v24 = v8;
      v9 = (unsigned __int16 *)(i + 6);
      if ( i[9] > 7u )
        v9 = *(unsigned __int16 **)v9;
      *((_QWORD *)&v24 + 1) = v9;
      LODWORD(pSid[0]) = 0;
      pSid[1] = 0;
      LODWORD(v26) = 0;
      *((_QWORD *)&v26 + 1) = 0;
      LODWORD(v27) = 1;
      v10 = *v9 - 42;
      if ( *v9 == 42 )
        v10 = v9[1];
      if ( v10 && (int)DeriveAppContainerSidFromAppContainerName(v9, &pSid[1]) >= 0 )
        LODWORD(pSid[0]) = GetLengthSid(pSid[1]);
      v11 = *((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1) == v29 )
      {
        std::vector<_WINHTTP_CONNECTION_POLICY_ENTRY>::_Emplace_reallocate<_WINHTTP_CONNECTION_POLICY_ENTRY const &>(
          &v28,
          *((_QWORD *)&v28 + 1),
          &v24);
      }
      else
      {
        **((_OWORD **)&v28 + 1) = v24;
        *(_OWORD *)(v11 + 16) = *(_OWORD *)pSid;
        *(_OWORD *)(v11 + 32) = v26;
        *(_QWORD *)(v11 + 48) = v27;
        *((_QWORD *)&v28 + 1) += 56LL;
      }
    }
    *(_QWORD *)&v23 = v28;
  }
  else
  {
    *(_QWORD *)&v23 = 0;
  }
  v12 = WinHttpConnectionDeletePolicyEntries(*a1, 1);
  if ( v12 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids, v12);
    }
    v13 = *((_QWORD *)&v28 + 1);
    for ( j = v28; j != v13; j += 56 )
    {
      v15 = *(void **)(j + 24);
      if ( v15 )
        FreeSid(v15);
    }
    if ( (_QWORD)v28 )
      std::_Deallocate<16>((void *)v28, (struct std::nothrow_t *)(8 * ((v29 - (__int64)v28) >> 3)));
    return v12;
  }
  else
  {
    v17 = WinHttpConnectionSetPolicyEntries(*a1, 1, &v23);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids, v17);
    }
    v18 = *((_QWORD *)&v28 + 1);
    for ( k = v28; k != v18; k += 56 )
    {
      v20 = *(void **)(k + 24);
      if ( v20 )
        FreeSid(v20);
    }
    if ( (_QWORD)v28 )
      std::_Deallocate<16>((void *)v28, (struct std::nothrow_t *)(8 * ((v29 - (__int64)v28) >> 3)));
    return v17;
  }
}

```

## disassembly

```asm
0x18007c3ec  mov     r11, rsp
0x18007c3ef  mov     [r11+18h], rbx
0x18007c3f3  mov     [r11+20h], rsi
0x18007c3f7  push    rdi
0x18007c3f8  push    r13
0x18007c3fa  push    r14
0x18007c3fc  sub     rsp, 0A0h
0x18007c403  mov     rax, cs:__security_cookie
0x18007c40a  xor     rax, rsp
0x18007c40d  mov     [rsp+0B8h+var_20], rax
0x18007c415  mov     rdi, rdx
0x18007c418  mov     rsi, rcx
0x18007c41b  xorps   xmm0, xmm0
0x18007c41e  movups  [rsp+0B8h+var_80], xmm0
0x18007c423  mov     eax, [rdx+8]
0x18007c426  mov     dword ptr [rsp+0B8h+var_80+8], eax
0x18007c42a  xor     eax, eax
0x18007c42c  movups  xmmword ptr [r11-38h], xmm0
0x18007c431  mov     [r11-28h], rax
0x18007c435  lea     rcx, [r11-38h]
0x18007c439  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x18007c43e  nop
0x18007c43f  lea     r13, [rsp+0B8h+var_38]
0x18007c447  mov     [rsp+0B8h+var_90], r13
0x18007c44c  mov     [rsp+0B8h+var_88], 1
0x18007c451  mov     r14, 6DB6DB6DB6DB6DB7h
0x18007c45b  cmp     dword ptr [rsp+0B8h+var_80+8], 0
0x18007c460  jbe     loc_18007C5D5
0x18007c466  mov     rcx, [rdx+8]
0x18007c46a  mov     [rsp+0B8h+var_98], rcx
0x18007c46f  mov     rax, [rsp+0B8h+var_28]
0x18007c477  sub     rax, [rsp+0B8h+var_38]
0x18007c47f  sar     rax, 3
0x18007c483  imul    rax, r14
0x18007c487  cmp     rcx, rax
0x18007c48a  jbe     short loc_18007C4BA
0x18007c48c  mov     rax, 492492492492492h
0x18007c496  cmp     rcx, rax
0x18007c499  jbe     short loc_18007C4A8
0x18007c49b  lea     rcx, aVectorTooLong; "vector too long"
0x18007c4a2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18007c4a8  lea     rdx, [rsp+0B8h+var_98]
0x18007c4ad  lea     rcx, [rsp+0B8h+var_38]
0x18007c4b5  call    ??$_Reallocate@$0A@@?$vector@U_WINHTTP_CONNECTION_POLICY_ENTRY@@V?$allocator@U_WINHTTP_CONNECTION_POLICY_ENTRY@@@std@@@std@@AEAAXAEA_K@Z; std::vector<_WINHTTP_CONNECTION_POLICY_ENTRY>::_Reallocate<0>(unsigned __int64 &)
0x18007c4ba  mov     rdi, [rdi]
0x18007c4bd  mov     rbx, [rdi]
0x18007c4c0  cmp     rbx, rdi
0x18007c4c3  jnz     short loc_18007C4D7
0x18007c4c5  mov     rax, [rsp+0B8h+var_38]
0x18007c4cd  mov     qword ptr [rsp+0B8h+var_80], rax
0x18007c4d2  jmp     loc_18007C5DE
0x18007c4d7  mov     dword ptr [rsp+0B8h+pSid+4], 0
0x18007c4df  mov     dword ptr [rsp+0B8h+var_50+4], 0
0x18007c4e7  mov     dword ptr [rsp+0B8h+var_40+4], 0
0x18007c4ef  lea     rax, [rbx+10h]
0x18007c4f3  cmp     qword ptr [rbx+28h], 7
0x18007c4f8  jbe     short loc_18007C4FD
0x18007c4fa  mov     rax, [rax]
0x18007c4fd  mov     qword ptr [rsp+0B8h+var_70], rax
0x18007c502  lea     rcx, [rbx+30h]
0x18007c506  cmp     qword ptr [rbx+48h], 7
0x18007c50b  jbe     short loc_18007C510
0x18007c50d  mov     rcx, [rcx]
0x18007c510  mov     qword ptr [rsp+0B8h+var_70+8], rcx
0x18007c515  mov     dword ptr [rsp+0B8h+pSid], 0
0x18007c51d  mov     [rsp+0B8h+pSid+8], 0
0x18007c526  mov     dword ptr [rsp+0B8h+var_50], 0
0x18007c52e  mov     qword ptr [rsp+0B8h+var_50+8], 0
0x18007c537  mov     dword ptr [rsp+0B8h+var_40], 1
0x18007c53f  movzx   r8d, word ptr [rcx]
0x18007c543  sub     r8d, 2Ah ; '*'
0x18007c547  jnz     short loc_18007C556
0x18007c549  movzx   r8d, word ptr [rcx+2]
0x18007c54e  xor     eax, eax
0x18007c550  movzx   edx, ax
0x18007c553  sub     r8d, edx
0x18007c556  test    r8d, r8d
0x18007c559  jz      short loc_18007C579
0x18007c55b  lea     rdx, [rsp+0B8h+pSid+8]
0x18007c560  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18007c566  test    eax, eax
0x18007c568  js      short loc_18007C579
0x18007c56a  mov     rcx, [rsp+0B8h+pSid+8]; pSid
0x18007c56f  call    cs:__imp_GetLengthSid
0x18007c575  mov     dword ptr [rsp+0B8h+pSid], eax
0x18007c579  mov     rdx, [rsp+0B8h+var_30]
0x18007c581  cmp     rdx, [rsp+0B8h+var_28]
0x18007c589  jz      short loc_18007C5BB
0x18007c58b  movups  xmm0, [rsp+0B8h+var_70]
0x18007c590  movups  xmmword ptr [rdx], xmm0
0x18007c593  movups  xmm1, xmmword ptr [rsp+0B8h+pSid]
0x18007c598  movups  xmmword ptr [rdx+10h], xmm1
0x18007c59c  movups  xmm0, [rsp+0B8h+var_50]
0x18007c5a1  movups  xmmword ptr [rdx+20h], xmm0
0x18007c5a5  movsd   xmm1, [rsp+0B8h+var_40]
0x18007c5ab  movsd   qword ptr [rdx+30h], xmm1
0x18007c5b0  add     [rsp+0B8h+var_30], 38h ; '8'
0x18007c5b9  jmp     short loc_18007C5CD
0x18007c5bb  lea     r8, [rsp+0B8h+var_70]
0x18007c5c0  lea     rcx, [rsp+0B8h+var_38]
0x18007c5c8  call    ??$_Emplace_reallocate@AEBU_WINHTTP_CONNECTION_POLICY_ENTRY@@@?$vector@U_WINHTTP_CONNECTION_POLICY_ENTRY@@V?$allocator@U_WINHTTP_CONNECTION_POLICY_ENTRY@@@std@@@std@@AEAAPEAU_WINHTTP_CONNECTION_POLICY_ENTRY@@QEAU2@AEBU2@@Z; std::vector<_WINHTTP_CONNECTION_POLICY_ENTRY>::_Emplace_reallocate<_WINHTTP_CONNECTION_POLICY_ENTRY const &>(_WINHTTP_CONNECTION_POLICY_ENTRY * const,_WINHTTP_CONNECTION_POLICY_ENTRY const &)
0x18007c5cd  mov     rbx, [rbx]
0x18007c5d0  jmp     loc_18007C4C0
0x18007c5d5  mov     qword ptr [rsp+0B8h+var_80], 0
0x18007c5de  mov     edx, 1
0x18007c5e3  mov     rcx, [rsi]
0x18007c5e6  call    cs:__imp_WinHttpConnectionDeletePolicyEntries
0x18007c5ec  mov     edi, eax
0x18007c5ee  test    eax, eax
0x18007c5f0  jz      loc_18007C680
0x18007c5f6  lea     rax, WPP_GLOBAL_Control
0x18007c5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c604  cmp     rcx, rax
0x18007c607  jz      short loc_18007C62E
0x18007c609  cmp     byte ptr [rcx+19h], 2
0x18007c60d  jb      short loc_18007C62E
0x18007c60f  test    byte ptr [rcx+1Ch], 1
0x18007c613  jz      short loc_18007C62E
0x18007c615  mov     edx, 0Ch
0x18007c61a  mov     r9d, edi
0x18007c61d  lea     r8, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids
0x18007c624  mov     rcx, [rcx+10h]
0x18007c628  call    WPP_SF_d
0x18007c62d  nop
0x18007c62e  mov     rsi, [r13+8]
0x18007c632  mov     rbx, [r13+0]
0x18007c636  jmp     short loc_18007C64B
0x18007c638  mov     rcx, [rbx+18h]; pSid
0x18007c63c  test    rcx, rcx
0x18007c63f  jz      short loc_18007C647
0x18007c641  call    cs:__imp_FreeSid
0x18007c647  add     rbx, 38h ; '8'
0x18007c64b  cmp     rbx, rsi
0x18007c64e  jnz     short loc_18007C638
0x18007c650  mov     rcx, [rsp+0B8h+var_38]
0x18007c658  test    rcx, rcx
0x18007c65b  jz      short loc_18007C679
0x18007c65d  mov     rax, [rsp+0B8h+var_28]
0x18007c665  sub     rax, rcx
0x18007c668  sar     rax, 3
0x18007c66c  imul    rax, r14
0x18007c670  imul    rdx, rax, 38h ; '8'
0x18007c674  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007c679  mov     eax, edi
0x18007c67b  jmp     loc_18007C720
0x18007c680  lea     r8, [rsp+0B8h+var_80]
0x18007c685  mov     edx, 1
0x18007c68a  mov     rcx, [rsi]
0x18007c68d  call    cs:__imp_WinHttpConnectionSetPolicyEntries
0x18007c693  mov     esi, eax
0x18007c695  lea     rax, WPP_GLOBAL_Control
0x18007c69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c6a3  cmp     rcx, rax
0x18007c6a6  jz      short loc_18007C6CD
0x18007c6a8  cmp     byte ptr [rcx+19h], 4
0x18007c6ac  jb      short loc_18007C6CD
0x18007c6ae  test    byte ptr [rcx+1Ch], 1
0x18007c6b2  jz      short loc_18007C6CD
0x18007c6b4  mov     edx, 0Dh
0x18007c6b9  mov     r9d, esi
0x18007c6bc  lea     r8, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids
0x18007c6c3  mov     rcx, [rcx+10h]
0x18007c6c7  call    WPP_SF_d
0x18007c6cc  nop
0x18007c6cd  mov     rdi, [r13+8]
0x18007c6d1  mov     rbx, [r13+0]
0x18007c6d5  jmp     short loc_18007C6EA
0x18007c6d7  mov     rcx, [rbx+18h]; pSid
0x18007c6db  test    rcx, rcx
0x18007c6de  jz      short loc_18007C6E6
0x18007c6e0  call    cs:__imp_FreeSid
0x18007c6e6  add     rbx, 38h ; '8'
0x18007c6ea  cmp     rbx, rdi
0x18007c6ed  jnz     short loc_18007C6D7
0x18007c6ef  mov     rcx, [rsp+0B8h+var_38]
0x18007c6f7  test    rcx, rcx
0x18007c6fa  jz      short loc_18007C718
0x18007c6fc  mov     rax, [rsp+0B8h+var_28]
0x18007c704  sub     rax, rcx
0x18007c707  sar     rax, 3
0x18007c70b  imul    rax, r14
0x18007c70f  imul    rdx, rax, 38h ; '8'
0x18007c713  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007c718  mov     eax, esi
0x18007c71a  jmp     short loc_18007C720
0x18007c71c  mov     eax, dword ptr [rsp+0B8h+var_98]
0x18007c720  mov     rcx, [rsp+0B8h+var_20]
0x18007c728  xor     rcx, rsp; StackCookie
0x18007c72b  call    __security_check_cookie
0x18007c730  lea     r11, [rsp+0B8h+var_18]
0x18007c738  mov     rbx, [r11+30h]
0x18007c73c  mov     rsi, [r11+38h]
0x18007c740  mov     rsp, r11
0x18007c743  pop     r14
0x18007c745  pop     r13
0x18007c747  pop     rdi
0x18007c748  retn
```
