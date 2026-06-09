# CfgDupSelection(WLAN_CONFIG_SELECTION *,WLAN_CONFIG_SELECTION * *)

- ea: `0x1800565c0`
- end: `0x180056c66`
- name: `?CfgDupSelection@@YAKPEAUWLAN_CONFIG_SELECTION@@PEAPEAU1@@Z`
- size: `1702`
- prototype: `unsigned int __fastcall(struct WLAN_CONFIG_SELECTION *, struct WLAN_CONFIG_SELECTION **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006508c`
- `0x1800cf6a0`
- `0x180139e20`

## callees

- `0x18000a704`
- `0x18000aa0c`
- `0x180011530`
- `0x180028894`
- `0x18002f450`
- `0x18003fee8`
- `0x1800406cc`
- `0x1800565c0`
- `0x180056c6c`
- `0x180057454`
- `0x180057afc`
- `0x18005aef0`
- `0x1800c6774`
- `0x1800fa048`
- `0x180107318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b8a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180056b61`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180056b61`

## pseudocode

```c
__int64 __fastcall CfgDupSelection(struct WLAN_CONFIG_SELECTION *a1, struct WLAN_CONFIG_SELECTION **a2, __int64 a3)
{
  unsigned int v4; // esi
  PVOID *v6; // rcx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  DWORD v9; // eax
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  struct _PM_PROFILE *v14; // rcx
  _QWORD *v15; // r12
  unsigned int v16; // eax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // kr00_8
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  void *v21; // r9
  DWORD LastError; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r10
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rax
  unsigned int v32; // eax
  void *v33; // rax
  struct _PM_PROFILE *v34; // rcx
  __int64 v35; // rcx
  void *v36; // rcx
  _QWORD *v38; // [rsp+30h] [rbp-68h] BYREF
  struct _PM_PROFILE *v39; // [rsp+38h] [rbp-60h] BYREF
  char v40; // [rsp+40h] [rbp-58h]

  v4 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 80, &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *a2 == a1 )
    goto LABEL_74;
  v7 = (_QWORD *)AllocWLMem(0x320u);
  v8 = v7;
  if ( v7 )
  {
    v7[1] = v7;
    v10 = (_OWORD *)((char *)a1 + 24);
    *v7 = v7;
    v11 = 4;
    v7[2] = *((_QWORD *)a1 + 2);
    v12 = v7 + 3;
    do
    {
      *v12 = *v10;
      v12[1] = v10[1];
      v12[2] = v10[2];
      v12[3] = v10[3];
      v12[4] = v10[4];
      v12[5] = v10[5];
      v12[6] = v10[6];
      v13 = v10[7];
      v10 += 8;
      v12[7] = v13;
      v12 += 8;
      --v11;
    }
    while ( v11 );
    *(_OWORD *)(v8 + 67) = *(_OWORD *)((char *)a1 + 536);
    *(_OWORD *)(v8 + 69) = *(_OWORD *)((char *)a1 + 552);
    *(_OWORD *)((char *)v8 + 564) = *(_OWORD *)((char *)a1 + 564);
    v8[73] = *((_QWORD *)a1 + 73);
    *((_DWORD *)v8 + 148) = *((_DWORD *)a1 + 148);
    v14 = (struct _PM_PROFILE *)v8[75];
    v8[75] = 0;
    if ( v14 )
      PmFreeProfile(v14);
    v8[76] = 0;
    v15 = v8 + 86;
    *((_DWORD *)v8 + 154) = *((_DWORD *)a1 + 154);
    *((_WORD *)v8 + 310) = *((_WORD *)a1 + 310);
    *((_DWORD *)v8 + 156) = *((_DWORD *)a1 + 156);
    v8[79] = 0;
    *((_DWORD *)v8 + 160) = *((_DWORD *)a1 + 160);
    *((_DWORD *)v8 + 161) = *((_DWORD *)a1 + 161);
    *((_DWORD *)v8 + 162) = *((_DWORD *)a1 + 162);
    *((_DWORD *)v8 + 163) = *((_DWORD *)a1 + 163);
    *((_DWORD *)v8 + 164) = *((_DWORD *)a1 + 164);
    *(_OWORD *)(v8 + 83) = 0;
    *((_DWORD *)v8 + 170) = *((_DWORD *)a1 + 170);
    *(_OWORD *)(v8 + 87) = 0;
    v8[89] = 0;
    *((_OWORD *)v8 + 45) = 0;
    v8[92] = 0;
    v8[86] = 0;
    *((_DWORD *)v8 + 186) = *((_DWORD *)a1 + 186);
    *((_DWORD *)v8 + 187) = *((_DWORD *)a1 + 187);
    v8[94] = 0;
    *((_DWORD *)v8 + 190) = *((_DWORD *)a1 + 190);
    *((_DWORD *)v8 + 191) = *((_DWORD *)a1 + 191);
    *((_BYTE *)v8 + 768) = *((_BYTE *)a1 + 768);
    *((_BYTE *)v8 + 769) = *((_BYTE *)a1 + 769);
    *((_DWORD *)v8 + 193) = *((_DWORD *)a1 + 193);
    *((_DWORD *)v8 + 194) = *((_DWORD *)a1 + 194);
    *((_DWORD *)v8 + 195) = *((_DWORD *)a1 + 195);
    *((_DWORD *)v8 + 197) = *((_DWORD *)a1 + 197);
    *((_BYTE *)v8 + 792) = *((_BYTE *)a1 + 792);
    *((_DWORD *)v8 + 199) = *((_DWORD *)a1 + 199);
    v16 = 1;
    if ( *(_DWORD *)(*((_QWORD *)a1 + 76) + 8LL) )
      v16 = *(_DWORD *)(*((_QWORD *)a1 + 76) + 8LL);
    v18 = v16;
    v17 = 36LL * v16;
    if ( !is_mul_ok(v18, 0x24u) || (v19 = v17 + 12, v17 + 12 < v17) || v19 > 0xFFFFFFFF )
      LODWORD(v19) = 0;
    v20 = AllocWLMem((unsigned int)v19);
    v8[76] = v20;
    v21 = (void *)v20;
    if ( !v20 )
    {
      LastError = GetLastError();
      v4 = LastError;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_54;
      }
      v24 = 82;
      goto LABEL_31;
    }
    v25 = *((_QWORD *)a1 + 76);
    v26 = 36LL * *(unsigned int *)(v25 + 8);
    if ( !is_mul_ok(*(unsigned int *)(v25 + 8), 0x24u) || (v27 = v26 + 12, v26 + 12 < v26) || v27 > 0xFFFFFFFF )
      LODWORD(v27) = 0;
    memcpy_0(v21, *((const void **)a1 + 76), (unsigned int)v27);
    v28 = *((_QWORD *)a1 + 79);
    if ( v28 )
    {
      v29 = 1;
      if ( *(_DWORD *)(v28 + 8) )
        v29 = *(unsigned int *)(v28 + 8);
      v30 = SafeVariableListBufferSize(0xCu, v29, 6u);
      v31 = AllocWLMem(v30);
      v8[79] = v31;
      if ( !v31 )
      {
        LastError = GetLastError();
        v4 = LastError;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_54;
        }
        v24 = 83;
        goto LABEL_31;
      }
      v32 = SafeVariableListBufferSize(0xCu, *(unsigned int *)(*((_QWORD *)a1 + 79) + 8LL), 6u);
      memcpy_0((void *)v8[79], *((const void **)a1 + 79), v32);
    }
    v8[84] = 0;
    if ( *((_QWORD *)a1 + 84) )
    {
      v33 = (void *)AllocWLMem(*((unsigned int *)a1 + 166));
      v8[84] = v33;
      if ( !v33 )
      {
        LastError = GetLastError();
        v4 = LastError;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_54;
        }
        v24 = 84;
LABEL_31:
        WPP_SF_d(v23[12], v24, &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids, LastError);
LABEL_54:
        CfgFreeSelection((struct WLAN_CONFIG_SELECTION *)v8);
        goto LABEL_15;
      }
      *((_DWORD *)v8 + 166) = *((_DWORD *)a1 + 166);
      memcpy_0(v33, *((const void **)a1 + 84), *((unsigned int *)a1 + 166));
    }
    if ( *((_DWORD *)a1 + 164) == 1 )
    {
      v4 = CfgDupConfiguration(
             *((const struct wlansvc::RuntimeConfig **)a1 + 73),
             (struct wlansvc::RuntimeConfig **)v8 + 73);
      if ( v4 )
        goto LABEL_54;
    }
    else
    {
      v8[73] = *((_QWORD *)a1 + 73);
    }
    v34 = (struct _PM_PROFILE *)*((_QWORD *)a1 + 75);
    if ( !v34
      || (v38 = v8 + 75,
          v39 = 0,
          v40 = 1,
          v4 = PmCopyProfile(v34, &v39),
          wil::details::out_param_t<wistd::unique_ptr<_PM_PROFILE,wil::function_deleter<void (*)(_PM_PROFILE *),&void PmFreeProfile(_PM_PROFILE *)>>>::~out_param_t<wistd::unique_ptr<_PM_PROFILE,wil::function_deleter<void (*)(_PM_PROFILE *),&void PmFreeProfile(_PM_PROFILE *)>>>(&v38),
          !v4) )
    {
      v35 = *((_QWORD *)a1 + 94);
      if ( !v35 || (v4 = MsmDuplicateRuntimeState(v35, v8 + 94)) == 0 )
      {
        v36 = (void *)*((_QWORD *)a1 + 86);
        if ( v36 )
        {
          if ( DuplicateToken(v36, SecurityImpersonation, (PHANDLE)v8 + 86) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_qq(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                86,
                &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids,
                *((_QWORD *)a1 + 86),
                *v15);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              GetLastError();
              WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 85, &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids);
            }
            *v15 = 0;
          }
        }
        if ( *a2 )
          CfgFreeSelection(*a2);
        *a2 = (struct WLAN_CONFIG_SELECTION *)v8;
        goto LABEL_15;
      }
    }
    goto LABEL_54;
  }
  v9 = GetLastError();
  v4 = v9;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids, v9);
LABEL_15:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_74:
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 105) >= 4u && (*((_BYTE *)v6 + 108) & 1) != 0 )
    WPP_SF_d(v6[12], 87, &WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800565c0  push    rbx
0x1800565c2  push    rbp
0x1800565c3  push    rsi
0x1800565c4  push    rdi
0x1800565c5  push    r12
0x1800565c7  push    r13
0x1800565c9  push    r14
0x1800565cb  push    r15
0x1800565cd  sub     rsp, 58h
0x1800565d1  xor     r13d, r13d
0x1800565d4  mov     r14, rdx
0x1800565d7  mov     esi, r13d
0x1800565da  mov     rbx, rcx
0x1800565dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565e4  lea     rax, WPP_GLOBAL_Control
0x1800565eb  cmp     rcx, rax
0x1800565ee  jz      short loc_180056617
0x1800565f0  cmp     byte ptr [rcx+69h], 4
0x1800565f4  jb      short loc_180056617
0x1800565f6  test    byte ptr [rcx+6Ch], 1
0x1800565fa  jz      short loc_180056617
0x1800565fc  mov     rcx, [rcx+60h]
0x180056600  lea     edx, [r13+50h]
0x180056604  lea     r8, WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids
0x18005660b  call    WPP_SF_
0x180056610  mov     rcx, cs:WPP_GLOBAL_Control
0x180056617  test    rbx, rbx
0x18005661a  jnz     short loc_180056628
0x18005661c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pSrcSelection != nullptr")
0x180056621  mov     rcx, cs:WPP_GLOBAL_Control
0x180056628  test    r14, r14
0x18005662b  jnz     short loc_180056639
0x18005662d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ppDestSelection != nullptr")
0x180056632  mov     rcx, cs:WPP_GLOBAL_Control
0x180056639  cmp     [r14], rbx
0x18005663c  jz      loc_180056C23
0x180056642  mov     ecx, 320h; dwBytes
0x180056647  call    AllocWLMem
0x18005664c  mov     rdi, rax
0x18005664f  test    rax, rax
0x180056652  jnz     short loc_1800566A9
0x180056654  call    cs:__imp_GetLastError
0x18005665a  mov     esi, eax
0x18005665c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056663  lea     rbp, WPP_GLOBAL_Control
0x18005666a  cmp     rcx, rbp
0x18005666d  jz      loc_180056C53
0x180056673  cmp     byte ptr [rcx+69h], 1
0x180056677  jb      loc_180056C2A
0x18005667d  test    byte ptr [rcx+6Ch], 1
0x180056681  jz      loc_180056C2A
0x180056687  mov     rcx, [rcx+60h]
0x18005668b  lea     edx, [rdi+51h]
0x18005668e  mov     r9d, eax
0x180056691  lea     r8, WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids
0x180056698  call    WPP_SF_d
0x18005669d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800566a4  jmp     loc_180056C2A
0x1800566a9  mov     [rax+8], rdi
0x1800566ad  lea     rcx, [rbx+18h]
0x1800566b1  mov     [rax], rdi
0x1800566b4  mov     edx, 4
0x1800566b9  mov     rax, [rbx+10h]
0x1800566bd  mov     [rdi+10h], rax
0x1800566c1  lea     rax, [rdi+18h]
0x1800566c5  lea     r8d, [rdx+7Ch]
0x1800566c9  movups  xmm0, xmmword ptr [rcx]
0x1800566cc  movups  xmmword ptr [rax], xmm0
0x1800566cf  movups  xmm1, xmmword ptr [rcx+10h]
0x1800566d3  movups  xmmword ptr [rax+10h], xmm1
0x1800566d7  movups  xmm0, xmmword ptr [rcx+20h]
0x1800566db  movups  xmmword ptr [rax+20h], xmm0
0x1800566df  movups  xmm1, xmmword ptr [rcx+30h]
0x1800566e3  movups  xmmword ptr [rax+30h], xmm1
0x1800566e7  movups  xmm0, xmmword ptr [rcx+40h]
0x1800566eb  movups  xmmword ptr [rax+40h], xmm0
0x1800566ef  movups  xmm1, xmmword ptr [rcx+50h]
0x1800566f3  movups  xmmword ptr [rax+50h], xmm1
0x1800566f7  movups  xmm0, xmmword ptr [rcx+60h]
0x1800566fb  movups  xmmword ptr [rax+60h], xmm0
0x1800566ff  movups  xmm1, xmmword ptr [rcx+70h]
0x180056703  add     rcx, r8
0x180056706  movups  xmmword ptr [rax+70h], xmm1
0x18005670a  add     rax, r8
0x18005670d  sub     rdx, 1
0x180056711  jnz     short loc_1800566C9
0x180056713  movups  xmm0, xmmword ptr [rbx+218h]
0x18005671a  lea     rbp, [rdi+258h]
0x180056721  lea     r15, [rdi+248h]
0x180056728  movdqu  xmmword ptr [rdi+218h], xmm0
0x180056730  movups  xmm0, xmmword ptr [rbx+228h]
0x180056737  movups  xmmword ptr [rdi+228h], xmm0
0x18005673e  movups  xmm1, xmmword ptr [rbx+234h]
0x180056745  movups  xmmword ptr [rdi+234h], xmm1
0x18005674c  mov     rax, [rbx+248h]
0x180056753  mov     [r15], rax
0x180056756  mov     eax, [rbx+250h]
0x18005675c  mov     [rdi+250h], eax
0x180056762  mov     rcx, [rbp+0]; lpMem
0x180056766  mov     [rbp+0], r13
0x18005676a  test    rcx, rcx
0x18005676d  jz      short loc_180056774
0x18005676f  call    ?PmFreeProfile@@YAXPEAU_PM_PROFILE@@@Z; PmFreeProfile(_PM_PROFILE *)
0x180056774  mov     [rdi+260h], r13
0x18005677b  lea     r12, [rdi+2B0h]
0x180056782  mov     eax, [rbx+268h]
0x180056788  xorps   xmm0, xmm0
0x18005678b  mov     [rdi+268h], eax
0x180056791  xorps   xmm1, xmm1
0x180056794  movzx   eax, word ptr [rbx+26Ch]
0x18005679b  mov     r8d, 0FFFFFFFFh
0x1800567a1  mov     [rdi+26Ch], ax
0x1800567a8  mov     eax, [rbx+270h]
0x1800567ae  mov     [rdi+270h], eax
0x1800567b4  mov     [rdi+278h], r13
0x1800567bb  mov     eax, [rbx+280h]
0x1800567c1  mov     [rdi+280h], eax
0x1800567c7  mov     eax, [rbx+284h]
0x1800567cd  mov     [rdi+284h], eax
0x1800567d3  mov     eax, [rbx+288h]
0x1800567d9  mov     [rdi+288h], eax
0x1800567df  mov     eax, [rbx+28Ch]
0x1800567e5  mov     [rdi+28Ch], eax
0x1800567eb  mov     eax, [rbx+290h]
0x1800567f1  mov     [rdi+290h], eax
0x1800567f7  movdqu  xmmword ptr [rdi+298h], xmm0
0x1800567ff  mov     eax, [rbx+2A8h]
0x180056805  mov     [rdi+2A8h], eax
0x18005680b  xor     eax, eax
0x18005680d  movups  xmmword ptr [rdi+2B8h], xmm0
0x180056814  mov     [rdi+2C8h], rax
0x18005681b  movups  xmmword ptr [rdi+2D0h], xmm1
0x180056822  mov     [rdi+2E0h], rax
0x180056829  mov     [r12], r13
0x18005682d  lea     r13, [rdi+2F0h]
0x180056834  mov     eax, [rbx+2E8h]
0x18005683a  mov     [rdi+2E8h], eax
0x180056840  mov     eax, [rbx+2ECh]
0x180056846  mov     [rdi+2ECh], eax
0x18005684c  mov     [r13+0], rsi
0x180056850  mov     eax, [rbx+2F8h]
0x180056856  mov     [rdi+2F8h], eax
0x18005685c  mov     eax, [rbx+2FCh]
0x180056862  mov     [rdi+2FCh], eax
0x180056868  mov     al, [rbx+300h]
0x18005686e  mov     [rdi+300h], al
0x180056874  mov     al, [rbx+301h]
0x18005687a  mov     [rdi+301h], al
0x180056880  mov     eax, [rbx+304h]
0x180056886  mov     [rdi+304h], eax
0x18005688c  mov     eax, [rbx+308h]
0x180056892  mov     [rdi+308h], eax
0x180056898  mov     eax, [rbx+30Ch]
0x18005689e  mov     [rdi+30Ch], eax
0x1800568a4  mov     eax, [rbx+314h]
0x1800568aa  mov     [rdi+314h], eax
0x1800568b0  mov     al, [rbx+318h]
0x1800568b6  mov     [rdi+318h], al
0x1800568bc  mov     eax, [rbx+31Ch]
0x1800568c2  mov     [rdi+31Ch], eax
0x1800568c8  mov     rax, [rbx+260h]
0x1800568cf  mov     ecx, [rax+8]
0x1800568d2  test    ecx, ecx
0x1800568d4  mov     eax, 1
0x1800568d9  cmovnz  eax, ecx
0x1800568dc  mov     ecx, eax
0x1800568de  mov     eax, 24h ; '$'
0x1800568e3  mul     rcx
0x1800568e6  test    rdx, rdx
0x1800568e9  jnz     short loc_1800568F9
0x1800568eb  lea     rcx, [rax+0Ch]
0x1800568ef  cmp     rcx, rax
0x1800568f2  jb      short loc_1800568F9
0x1800568f4  cmp     rcx, r8
0x1800568f7  jbe     short loc_1800568FB
0x1800568f9  xor     ecx, ecx
0x1800568fb  mov     ecx, ecx; dwBytes
0x1800568fd  call    AllocWLMem
0x180056902  mov     [rdi+260h], rax
0x180056909  mov     r9, rax
0x18005690c  test    rax, rax
0x18005690f  jnz     short loc_180056961
0x180056911  call    cs:__imp_GetLastError
0x180056917  mov     esi, eax
0x180056919  mov     rcx, cs:WPP_GLOBAL_Control
0x180056920  lea     rbp, WPP_GLOBAL_Control
0x180056927  cmp     rcx, rbp
0x18005692a  jz      loc_180056AE6
0x180056930  cmp     byte ptr [rcx+69h], 1
0x180056934  jb      loc_180056AE6
0x18005693a  test    byte ptr [rcx+6Ch], 1
0x18005693e  jz      loc_180056AE6
0x180056944  mov     edx, 52h ; 'R'
0x180056949  mov     rcx, [rcx+60h]
0x18005694d  lea     r8, WPP_6d3dd534f17a3a3c624549005c7eaa95_Traceguids
0x180056954  mov     r9d, eax
0x180056957  call    WPP_SF_d
0x18005695c  jmp     loc_180056AE6
0x180056961  mov     r10, [rbx+260h]
0x180056968  mov     eax, 24h ; '$'
0x18005696d  mov     ecx, [r10+8]
0x180056971  mul     rcx
0x180056974  test    rdx, rdx
0x180056977  jnz     short loc_18005698C
0x180056979  lea     rcx, [rax+0Ch]
0x18005697d  cmp     rcx, rax
0x180056980  jb      short loc_18005698C
0x180056982  mov     eax, 0FFFFFFFFh
0x180056987  cmp     rcx, rax
0x18005698a  jbe     short loc_18005698E
0x18005698c  xor     ecx, ecx
0x18005698e  mov     r8d, ecx; Size
0x180056991  mov     rdx, r10; Src
0x180056994  mov     rcx, r9; void *
0x180056997  call    memcpy_0
0x18005699c  mov     rcx, [rbx+278h]
0x1800569a3  test    rcx, rcx
0x1800569a6  jz      loc_180056A44
0x1800569ac  cmp     [rcx+8], esi
0x1800569af  mov     edx, 1
0x1800569b4  cmova   edx, [rcx+8]; unsigned __int64
0x1800569b8  mov     ecx, 0Ch; unsigned __int64
0x1800569bd  lea     r8d, [rcx-6]; unsigned __int64
0x1800569c1  call    ?SafeVariableListBufferSize@@YAK_K00@Z; SafeVariableListBufferSize(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800569c6  mov     ecx, eax; dwBytes
0x1800569c8  call    AllocWLMem
0x1800569cd  mov     [rdi+278h], rax
0x1800569d4  test    rax, rax
0x1800569d7  jnz     short loc_180056A16
0x1800569d9  call    cs:__imp_GetLastError
0x1800569df  mov     esi, eax
0x1800569e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800569e8  lea     rbp, WPP_GLOBAL_Control
0x1800569ef  cmp     rcx, rbp
0x1800569f2  jz      loc_180056AE6
0x1800569f8  cmp     byte ptr [rcx+69h], 1
0x1800569fc  jb      loc_180056AE6
0x180056a02  test    byte ptr [rcx+6Ch], 1
0x180056a06  jz      loc_180056AE6
0x180056a0c  mov     edx, 53h ; 'S'
0x180056a11  jmp     loc_180056949
0x180056a16  mov     rax, [rbx+278h]
0x180056a1d  mov     ecx, 0Ch; unsigned __int64
0x180056a22  mov     edx, [rax+8]; unsigned __int64
0x180056a25  lea     r8d, [rcx-6]; unsigned __int64
0x180056a29  call    ?SafeVariableListBufferSize@@YAK_K00@Z; SafeVariableListBufferSize(unsigned __int64,unsigned __int64,unsigned __int64)
0x180056a2e  mov     rdx, [rbx+278h]; Src
0x180056a35  mov     rcx, [rdi+278h]; void *
0x180056a3c  mov     r8d, eax; Size
0x180056a3f  call    memcpy_0
0x180056a44  mov     [rdi+2A0h], rsi
0x180056a4b  cmp     [rbx+2A0h], rsi
0x180056a52  jz      short loc_180056ABE
0x180056a54  mov     ecx, [rbx+298h]; dwBytes
0x180056a5a  call    AllocWLMem
0x180056a5f  mov     [rdi+2A0h], rax
0x180056a66  mov     rcx, rax; void *
0x180056a69  test    rax, rax
0x180056a6c  jnz     short loc_180056A9F
0x180056a6e  call    cs:__imp_GetLastError
0x180056a74  mov     esi, eax
0x180056a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a7d  lea     rbp, WPP_GLOBAL_Control
0x180056a84  cmp     rcx, rbp
0x180056a87  jz      short loc_180056AE6
0x180056a89  cmp     byte ptr [rcx+69h], 1
0x180056a8d  jb      short loc_180056AE6
0x180056a8f  test    byte ptr [rcx+6Ch], 1
0x180056a93  jz      short loc_180056AE6
0x180056a95  mov     edx, 54h ; 'T'
0x180056a9a  jmp     loc_180056949
0x180056a9f  mov     eax, [rbx+298h]
0x180056aa5  mov     [rdi+298h], eax
0x180056aab  mov     r8d, [rbx+298h]; Size
0x180056ab2  mov     rdx, [rbx+2A0h]; Src
0x180056ab9  call    memcpy_0
0x180056abe  cmp     dword ptr [rbx+290h], 1
0x180056ac5  mov     rax, [rbx+248h]
0x180056acc  jnz     short loc_180056AF3
0x180056ace  mov     rdx, r15; struct wlansvc::RuntimeConfig **
0x180056ad1  mov     rcx, rax; struct wlansvc::RuntimeConfig *
0x180056ad4  call    ?CfgDupConfiguration@@YAKAEBURuntimeConfig@wlansvc@@PEAPEAU12@@Z; CfgDupConfiguration(wlansvc::RuntimeConfig const &,wlansvc::RuntimeConfig * *)
0x180056ad9  mov     esi, eax
0x180056adb  test    eax, eax
0x180056add  jz      short loc_180056AF6
0x180056adf  lea     rbp, WPP_GLOBAL_Control
0x180056ae6  mov     rcx, rdi; lpMem
0x180056ae9  call    ?CfgFreeSelection@@YAXPEAUWLAN_CONFIG_SELECTION@@@Z; CfgFreeSelection(WLAN_CONFIG_SELECTION *)
0x180056aee  jmp     loc_18005669D
0x180056af3  mov     [r15], rax
0x180056af6  mov     rcx, [rbx+258h]; struct _PM_PROFILE *
0x180056afd  test    rcx, rcx
0x180056b00  jz      short loc_180056B2F
0x180056b02  lea     rdx, [rsp+98h+var_60]; struct _PM_PROFILE **
0x180056b07  mov     [rsp+98h+var_68], rbp
0x180056b0c  mov     [rsp+98h+var_60], 0
0x180056b15  mov     [rsp+98h+var_58], 1
0x180056b1a  call    ?PmCopyProfile@@YAKPEAU_PM_PROFILE@@PEAPEAU1@@Z; PmCopyProfile(_PM_PROFILE *,_PM_PROFILE * *)
0x180056b1f  lea     rcx, [rsp+98h+var_68]
0x180056b24  mov     esi, eax
  ... truncated ...
```
