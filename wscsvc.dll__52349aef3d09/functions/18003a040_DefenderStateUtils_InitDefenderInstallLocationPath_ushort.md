# DefenderStateUtils::InitDefenderInstallLocationPath(ushort * *)

- ea: `0x18003a040`
- end: `0x18003a2ae`
- name: `?InitDefenderInstallLocationPath@DefenderStateUtils@@YAJPEAPEAG@Z`
- size: `622`
- prototype: `__int64 __fastcall(DefenderStateUtils *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a2b4`

## callees

- `0x180008e48`
- `0x1800186e0`
- `0x1800202e8`
- `0x180029158`
- `0x180029e74`
- `0x180031a70`
- `0x18003a040`
- `0x18003eca4`
- `0x18003f2a0`
- `0x18003f704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a296`

## pseudocode

```c
__int64 __fastcall DefenderStateUtils::InitDefenderInstallLocationPath(DefenderStateUtils *this, unsigned __int16 **a2)
{
  HKEY *v3; // rdx
  HKEY v4; // r8
  const unsigned __int16 *v5; // r9
  unsigned int v6; // ebx
  int v8; // eax
  HKEY v9; // rdx
  const unsigned __int16 *v10; // r8
  HKEY v11; // rsi
  int ValueAlloc; // edi
  CThirdPartyManager *v13; // rcx
  int v14; // eax
  unsigned __int16 **v15; // rbx
  int v16; // eax
  void *v17; // rdi
  unsigned int v18; // r12d
  __int64 v19; // rcx
  unsigned int v20; // [rsp+20h] [rbp-30h]
  unsigned __int8 **v21; // [rsp+30h] [rbp-20h]
  unsigned __int64 v22; // [rsp+38h] [rbp-18h]
  void *v23; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v24[2]; // [rsp+48h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF
  void *v26; // [rsp+A0h] [rbp+50h] BYREF
  void *Block; // [rsp+A8h] [rbp+58h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::GetImpl'::`2'::impl,
    a2);
  if ( !this )
  {
    v6 = -2147024809;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, 2147942487LL);
    }
    return v6;
  }
  hKey = 0;
  v26 = 0;
  v23 = 0;
  v8 = CommonUtil::UtilRegOpenKey((CommonUtil *)&hKey, v3, v4, v5, v20);
  v11 = hKey;
  if ( v8 < 0 )
    goto LABEL_13;
  LODWORD(hKey) = 0;
  *(_QWORD *)v24 = 0;
  Block = 0;
  ValueAlloc = CommonUtil::UtilRegGetValueAlloc(
                 (CommonUtil *)v11,
                 v9,
                 v10,
                 (unsigned int)&hKey,
                 v24,
                 (unsigned __int64 *)&Block,
                 v21,
                 v22);
  if ( ValueAlloc >= 0 )
  {
    v15 = (unsigned __int16 **)Block;
    goto LABEL_27;
  }
  if ( Block )
    operator delete(Block);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_14:
      if ( v13 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v13 + 2), 12, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids);
      goto LABEL_17;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids,
      (unsigned int)ValueAlloc);
LABEL_13:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_17:
  v14 = CommonUtil::HrDuplicateStringW(
          (CommonUtil *)&v26,
          (unsigned __int16 **)L"%ProgramFiles%\\Windows Defender",
          v10);
  v6 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids,
        (unsigned int)v14);
    }
    if ( v26 )
      operator delete(v26);
    if ( v11 )
      RegCloseKey(v11);
    return v6;
  }
  v15 = (unsigned __int16 **)v26;
LABEL_27:
  v16 = CommonUtil::UtilExpandEnvironmentStrings((CommonUtil *)&v23, v15, v10);
  v17 = v23;
  v18 = v16;
  if ( v16 >= 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v23 + v19) );
    if ( v19 && *((_WORD *)v23 + v19 - 1) == 92 )
      *((_WORD *)v23 + v19 - 1) = 0;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, v17);
    }
    *(_QWORD *)this = v17;
  }
  else
  {
    if ( v23 )
    {
      operator delete(v23);
      v17 = 0;
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, v18);
    }
    if ( v17 )
      operator delete(v17);
  }
  if ( v15 )
    operator delete(v15);
  if ( v11 )
    RegCloseKey(v11);
  return v18;
}

```

## disassembly

```asm
0x18003a040  push    rbp
0x18003a042  push    rbx
0x18003a043  push    rsi
0x18003a044  push    rdi
0x18003a045  push    r12
0x18003a047  push    r13
0x18003a049  push    r14
0x18003a04b  mov     rbp, rsp
0x18003a04e  sub     rsp, 50h
0x18003a052  mov     r13, rcx
0x18003a055  mov     dl, 1
0x18003a057  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::GetImpl(void)'::`2'::impl
0x18003a05e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003a063  xor     r12d, r12d
0x18003a066  test    r13, r13
0x18003a069  jnz     short loc_18003A0A8
0x18003a06b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a072  lea     r14, WPP_GLOBAL_Control
0x18003a079  mov     ebx, 80070057h
0x18003a07e  cmp     rcx, r14
0x18003a081  jz      short loc_18003A0A1
0x18003a083  test    byte ptr [rcx+1Ch], 1
0x18003a087  jz      short loc_18003A0A1
0x18003a089  mov     rcx, [rcx+10h]
0x18003a08d  lea     edx, [r12+0Ah]
0x18003a092  mov     r9d, ebx
0x18003a095  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a09c  call    WPP_SF_d
0x18003a0a1  mov     eax, ebx
0x18003a0a3  jmp     loc_18003A29F
0x18003a0a8  lea     rcx, [rbp+hKey]; this
0x18003a0ac  mov     [rbp+hKey], r12
0x18003a0b0  mov     [rbp+arg_10], r12
0x18003a0b4  mov     [rbp+var_10], r12
0x18003a0b8  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x18003a0bd  mov     rsi, [rbp+hKey]
0x18003a0c1  lea     r14, WPP_GLOBAL_Control
0x18003a0c8  test    eax, eax
0x18003a0ca  js      short loc_18003A138
0x18003a0cc  lea     rax, [rbp+Block]
0x18003a0d0  mov     dword ptr [rbp+hKey], r12d
0x18003a0d4  mov     [rsp+50h+var_28], rax; unsigned __int64 *
0x18003a0d9  lea     r9, [rbp+hKey]; unsigned int
0x18003a0dd  lea     rax, [rbp+var_8]
0x18003a0e1  mov     qword ptr [rbp+var_8], r12
0x18003a0e5  mov     rcx, rsi; this
0x18003a0e8  mov     [rsp+50h+var_30], rax; unsigned int *
0x18003a0ed  mov     [rbp+Block], r12
0x18003a0f1  call    ?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z; CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)
0x18003a0f6  mov     edi, eax
0x18003a0f8  test    eax, eax
0x18003a0fa  jns     loc_18003A1C4
0x18003a100  mov     rcx, [rbp+Block]; Block
0x18003a104  test    rcx, rcx
0x18003a107  jz      short loc_18003A10E
0x18003a109  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a10e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a115  cmp     rcx, r14
0x18003a118  jz      short loc_18003A15F
0x18003a11a  test    byte ptr [rcx+1Ch], 1
0x18003a11e  jz      short loc_18003A13F
0x18003a120  mov     rcx, [rcx+10h]
0x18003a124  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a12b  mov     edx, 0Bh
0x18003a130  mov     r9d, edi
0x18003a133  call    WPP_SF_d
0x18003a138  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a13f  cmp     rcx, r14
0x18003a142  jz      short loc_18003A15F
0x18003a144  test    byte ptr [rcx+1Ch], 2
0x18003a148  jz      short loc_18003A15F
0x18003a14a  mov     rcx, [rcx+10h]
0x18003a14e  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a155  mov     edx, 0Ch
0x18003a15a  call    WPP_SF_
0x18003a15f  lea     rdx, aProgramfilesWi; "%ProgramFiles%\\Windows Defender"
0x18003a166  lea     rcx, [rbp+arg_10]; this
0x18003a16a  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x18003a16f  mov     ebx, eax
0x18003a171  test    eax, eax
0x18003a173  jns     short loc_18003A1CA
0x18003a175  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a17c  cmp     rcx, r14
0x18003a17f  jz      short loc_18003A19F
0x18003a181  test    byte ptr [rcx+1Ch], 1
0x18003a185  jz      short loc_18003A19F
0x18003a187  mov     rcx, [rcx+10h]
0x18003a18b  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a192  mov     edx, 0Dh
0x18003a197  mov     r9d, eax
0x18003a19a  call    WPP_SF_d
0x18003a19f  mov     rcx, [rbp+arg_10]; Block
0x18003a1a3  test    rcx, rcx
0x18003a1a6  jz      short loc_18003A1AD
0x18003a1a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a1ad  test    rsi, rsi
0x18003a1b0  jz      loc_18003A0A1
0x18003a1b6  mov     rcx, rsi; hKey
0x18003a1b9  call    cs:__imp_RegCloseKey
0x18003a1bf  jmp     loc_18003A0A1
0x18003a1c4  mov     rbx, [rbp+Block]
0x18003a1c8  jmp     short loc_18003A1CE
0x18003a1ca  mov     rbx, [rbp+arg_10]
0x18003a1ce  mov     rdx, rbx; unsigned __int16 **
0x18003a1d1  lea     rcx, [rbp+var_10]; this
0x18003a1d5  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)
0x18003a1da  mov     rdi, [rbp+var_10]
0x18003a1de  mov     r12d, eax
0x18003a1e1  xor     eax, eax
0x18003a1e3  test    r12d, r12d
0x18003a1e6  jns     short loc_18003A234
0x18003a1e8  test    rdi, rdi
0x18003a1eb  jz      short loc_18003A1FB
0x18003a1ed  mov     rcx, rdi; Block
0x18003a1f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a1f5  xor     r13d, r13d
0x18003a1f8  mov     edi, r13d
0x18003a1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a202  cmp     rcx, r14
0x18003a205  jz      short loc_18003A225
0x18003a207  test    byte ptr [rcx+1Ch], 1
0x18003a20b  jz      short loc_18003A225
0x18003a20d  mov     rcx, [rcx+10h]
0x18003a211  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a218  mov     edx, 0Eh
0x18003a21d  mov     r9d, r12d
0x18003a220  call    WPP_SF_d
0x18003a225  test    rdi, rdi
0x18003a228  jz      short loc_18003A281
0x18003a22a  mov     rcx, rdi; Block
0x18003a22d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a232  jmp     short loc_18003A281
0x18003a234  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a238  inc     rcx
0x18003a23b  cmp     [rdi+rcx*2], ax
0x18003a23f  jnz     short loc_18003A238
0x18003a241  test    rcx, rcx
0x18003a244  jz      short loc_18003A253
0x18003a246  cmp     word ptr [rdi+rcx*2-2], 5Ch ; '\'
0x18003a24c  jnz     short loc_18003A253
0x18003a24e  mov     [rdi+rcx*2-2], ax
0x18003a253  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a25a  cmp     rcx, r14
0x18003a25d  jz      short loc_18003A27D
0x18003a25f  test    byte ptr [rcx+1Ch], 4
0x18003a263  jz      short loc_18003A27D
0x18003a265  mov     rcx, [rcx+10h]
0x18003a269  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a270  mov     edx, 0Fh
0x18003a275  mov     r9, rdi
0x18003a278  call    WPP_SF_S
0x18003a27d  mov     [r13+0], rdi
0x18003a281  test    rbx, rbx
0x18003a284  jz      short loc_18003A28E
0x18003a286  mov     rcx, rbx; Block
0x18003a289  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a28e  test    rsi, rsi
0x18003a291  jz      short loc_18003A29C
0x18003a293  mov     rcx, rsi; hKey
0x18003a296  call    cs:__imp_RegCloseKey
0x18003a29c  mov     eax, r12d
0x18003a29f  add     rsp, 50h
0x18003a2a3  pop     r14
0x18003a2a5  pop     r13
0x18003a2a7  pop     r12
0x18003a2a9  pop     rdi
0x18003a2aa  pop     rsi
0x18003a2ab  pop     rbx
0x18003a2ac  pop     rbp
0x18003a2ad  retn
```
