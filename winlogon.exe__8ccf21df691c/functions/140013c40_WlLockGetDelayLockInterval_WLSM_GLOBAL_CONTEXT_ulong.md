# WlLockGetDelayLockInterval(_WLSM_GLOBAL_CONTEXT *,ulong *)

- ea: `0x140013c40`
- end: `0x140013ff9`
- name: `?WlLockGetDelayLockInterval@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@PEAK@Z`
- size: `953`
- prototype: `void __fastcall(struct _WLSM_GLOBAL_CONTEXT *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140061860`
- `0x1400619c0`

## callees

- `0x1400057f4`
- `0x140013100`
- `0x1400132e0`
- `0x140013c40`
- `0x140015260`
- `0x1400155f0`
- `0x1400156c8`
- `0x140065244`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140013e9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140013e9a`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x140013e8d`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x140013e8d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013c9c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013cb0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013cc4`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013c9c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013cb0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140013cc4`

## pseudocode

```c
void __fastcall WlLockGetDelayLockInterval(struct _WLSM_GLOBAL_CONTEXT *a1, unsigned int *a2)
{
  unsigned int v2; // edi
  struct _WLSM_GLOBAL_CONTEXT *v4; // rbx
  int v5; // r12d
  unsigned int v6; // r13d
  int Policies; // eax
  CUser *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // ebx
  struct _tagEASPolicy *v12; // rsi
  CUser *v13; // rcx
  __int64 v14; // rax
  CMachine *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // esi
  __int64 dwTime; // rbx
  ULONGLONG v19; // rcx
  unsigned __int64 v20; // rcx
  int v21; // esi
  unsigned int v22; // r13d
  CMachine *v23; // rcx
  unsigned int v24; // eax
  int v25; // [rsp+48h] [rbp-19h] BYREF
  int v26; // [rsp+4Ch] [rbp-15h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-11h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-Dh] BYREF
  unsigned int v29; // [rsp+58h] [rbp-9h]
  unsigned int v30; // [rsp+5Ch] [rbp-5h] BYREF
  tagLASTINPUTINFO plii; // [rsp+60h] [rbp-1h] BYREF
  struct _tagEASPolicy *v32; // [rsp+68h] [rbp+7h] BYREF
  unsigned int v34; // [rsp+D8h] [rbp+77h] BYREF
  unsigned int pvParam; // [rsp+E0h] [rbp+7Fh] BYREF

  v2 = 0;
  plii = 0;
  v4 = a1;
  v29 = 0;
  pvParam = 0;
  v25 = 0;
  v5 = 0;
  v26 = 0;
  v6 = 0;
  v27 = 0;
  v30 = -1;
  SystemParametersInfoW(0xEu, 0, &pvParam, 0);
  SystemParametersInfoW(0x76u, 0, &v25, 0);
  SystemParametersInfoW(0x10u, 0, &v26, 0);
  v32 = 0;
  v34 = 0;
  v28 = 0;
  Policies = EasEngineGetPolicies(1, 0, 3u, &v28, &v32);
  if ( Policies < 0 )
  {
    if ( Policies == -1073283051 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_12;
      }
      v9 = 14;
      v10 = 3221684245LL;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_12;
      }
      v9 = 15;
      v10 = (unsigned int)Policies;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v10);
LABEL_12:
    CMachine::RegQueryDWORD(
      v8,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
      L"InactivityTimeoutSecs",
      0,
      &v34);
    goto LABEL_28;
  }
  v11 = v28;
  v12 = v32;
  if ( v28 )
  {
    v13 = WPP_GLOBAL_Control;
    do
    {
      v14 = 32LL * v6;
      if ( *(_DWORD *)((char *)v12 + v14) == 7 && *(_WORD *)((char *)v12 + v14 + 8) == 19 )
      {
        v2 = *(_DWORD *)((char *)v12 + v14 + 16);
        if ( v13 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x20000) != 0 && *((_BYTE *)v13 + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)v13 + 2), 16, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v2);
          v13 = WPP_GLOBAL_Control;
        }
      }
      ++v6;
    }
    while ( v6 < v11 );
    v6 = v29;
  }
  _FreePolicies(v11, v12);
  CMachine::RegQueryDWORD(
    v15,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
    L"InactivityTimeoutSecs",
    0,
    &v34);
  v4 = a1;
  if ( !v2 )
  {
    v2 = 0;
LABEL_28:
    v16 = v34;
    if ( !v34 )
      goto LABEL_37;
    goto LABEL_29;
  }
  v16 = v34;
  if ( v34 && v2 > v34 )
  {
LABEL_29:
    v2 = v16;
    if ( v16 )
      goto LABEL_30;
LABEL_37:
    if ( !v25 )
      goto LABEL_45;
    if ( !v26 )
      goto LABEL_45;
    v17 = pvParam;
    if ( !pvParam )
      goto LABEL_45;
LABEL_40:
    if ( !v17 )
      goto LABEL_45;
    goto LABEL_41;
  }
LABEL_30:
  if ( v25 )
  {
    if ( v26 )
    {
      v17 = pvParam;
      if ( pvParam )
      {
        if ( v2 < pvParam )
          v17 = v2;
        goto LABEL_40;
      }
    }
  }
  v17 = v2;
LABEL_41:
  plii.cbSize = 8;
  if ( GetLastInputInfo(&plii) )
  {
    dwTime = plii.dwTime;
    v19 = GetTickCount64() - dwTime;
    v4 = a1;
    v20 = v19 / 0x3E8;
    if ( v17 > (unsigned int)v20 )
    {
      v22 = v17;
      v21 = 1;
      v6 = v22 - v20;
    }
    else
    {
      v21 = 0;
      v5 = 1;
    }
    goto LABEL_46;
  }
LABEL_45:
  v21 = 0;
LABEL_46:
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_lllll(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
      v2,
      v26,
      v25,
      pvParam,
      v6);
  }
  if ( v5 )
    goto LABEL_63;
  WlLockGetDelayLockSettings(v4, &v30);
  v27 = CMachine::IsDomainMember(*((CMachine **)v4 + 1)) == 0;
  CMachine::RegQueryDWORD(v23, L"Software\\Policies\\Microsoft\\Windows\\System", L"AllowDomainDelayLock", v27, &v27);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v27);
  }
  if ( !v27 )
    goto LABEL_63;
  v24 = v30;
  if ( v30 == -1 )
    goto LABEL_60;
  if ( v30 < 0x3C )
  {
LABEL_63:
    v24 = 0;
    goto LABEL_64;
  }
  if ( v30 > 0x384 )
    v24 = 900;
LABEL_60:
  if ( v21 && v24 > v6 )
  {
    *a2 = v6;
    return;
  }
LABEL_64:
  *a2 = v24;
}

```

## disassembly

```asm
0x140013c40  mov     rax, rsp
0x140013c43  mov     [rax+8], rcx
0x140013c47  push    rbp
0x140013c48  push    rbx
0x140013c49  push    rsi
0x140013c4a  push    r13
0x140013c4c  push    r14
0x140013c4e  push    r15
0x140013c50  lea     rbp, [rax-5Fh]
0x140013c54  sub     rsp, 88h
0x140013c5b  mov     [rax-38h], rdi
0x140013c5f  lea     r8, [rbp+57h+pvParam]; pvParam
0x140013c63  xor     edi, edi
0x140013c65  mov     [rax-40h], r12
0x140013c69  mov     r15, rdx
0x140013c6c  mov     qword ptr [rbp+57h+plii.cbSize], rdi
0x140013c70  mov     rbx, rcx
0x140013c73  mov     [rbp+57h+var_60], edi
0x140013c76  xor     r9d, r9d; fWinIni
0x140013c79  mov     [rbp+57h+arg_8], edi
0x140013c7c  xor     edx, edx; uiParam
0x140013c7e  mov     [rbp+57h+pvParam], edi
0x140013c81  mov     ecx, 0Eh; uiAction
0x140013c86  mov     [rbp+57h+var_70], edi
0x140013c89  mov     r12d, edi
0x140013c8c  mov     [rbp+57h+var_6C], edi
0x140013c8f  mov     r13d, edi
0x140013c92  mov     [rbp+57h+var_68], edi
0x140013c95  mov     [rbp+57h+var_5C], 0FFFFFFFFh
0x140013c9c  call    cs:__imp_SystemParametersInfoW
0x140013ca2  xor     r9d, r9d; fWinIni
0x140013ca5  lea     r8, [rbp+57h+var_70]; pvParam
0x140013ca9  xor     edx, edx; uiParam
0x140013cab  mov     ecx, 76h ; 'v'; uiAction
0x140013cb0  call    cs:__imp_SystemParametersInfoW
0x140013cb6  xor     r9d, r9d; fWinIni
0x140013cb9  lea     r8, [rbp+57h+var_6C]; pvParam
0x140013cbd  xor     edx, edx; uiParam
0x140013cbf  mov     ecx, 10h; uiAction
0x140013cc4  call    cs:__imp_SystemParametersInfoW
0x140013cca  lea     rax, [rbp+57h+var_50]
0x140013cce  mov     [rbp+57h+var_50], rdi
0x140013cd2  lea     r9, [rbp+57h+var_64]; unsigned int *
0x140013cd6  mov     [rsp+0B0h+var_90], rax; struct _tagEASPolicy **
0x140013cdb  xor     edx, edx; void *
0x140013cdd  mov     [rbp+57h+arg_10], edi
0x140013ce0  mov     ecx, 1; int
0x140013ce5  mov     [rbp+57h+var_64], edi
0x140013ce8  mov     r8d, 3; unsigned int
0x140013cee  call    ?EasEngineGetPolicies@@YAJHPEAXKPEAKPEAPEAU_tagEASPolicy@@@Z; EasEngineGetPolicies(int,void *,ulong,ulong *,_tagEASPolicy * *)
0x140013cf3  test    eax, eax
0x140013cf5  jns     loc_140013D8F
0x140013cfb  cmp     eax, 0C0070015h
0x140013d00  jnz     short loc_140013D31
0x140013d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d09  lea     r14, WPP_GLOBAL_Control
0x140013d10  cmp     rcx, r14
0x140013d13  jz      short loc_140013D6B
0x140013d15  test    dword ptr [rcx+1Ch], 20000h
0x140013d1c  jz      short loc_140013D6B
0x140013d1e  cmp     byte ptr [rcx+19h], 3
0x140013d22  jb      short loc_140013D6B
0x140013d24  mov     edx, 0Eh
0x140013d29  mov     r9d, 0C0070015h
0x140013d2f  jmp     short loc_140013D5B
0x140013d31  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d38  lea     r14, WPP_GLOBAL_Control
0x140013d3f  cmp     rcx, r14
0x140013d42  jz      short loc_140013D6B
0x140013d44  test    dword ptr [rcx+1Ch], 20000h
0x140013d4b  jz      short loc_140013D6B
0x140013d4d  cmp     byte ptr [rcx+19h], 3
0x140013d51  jb      short loc_140013D6B
0x140013d53  mov     edx, 0Fh
0x140013d58  mov     r9d, eax
0x140013d5b  mov     rcx, [rcx+10h]
0x140013d5f  lea     r8, WPP_9c18ab671221381626cab8868253e78d_Traceguids
0x140013d66  call    WPP_SF_d
0x140013d6b  lea     rax, [rbp+57h+arg_10]
0x140013d6f  xor     r9d, r9d; unsigned int
0x140013d72  lea     r8, aInactivitytime; "InactivityTimeoutSecs"
0x140013d79  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x140013d7e  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140013d85  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140013d8a  jmp     loc_140013E40
0x140013d8f  mov     ebx, [rbp+57h+var_64]
0x140013d92  lea     r14, WPP_GLOBAL_Control
0x140013d99  mov     rsi, [rbp+57h+var_50]
0x140013d9d  test    ebx, ebx
0x140013d9f  jz      short loc_140013E00
0x140013da1  mov     rcx, cs:WPP_GLOBAL_Control
0x140013da8  mov     eax, r13d
0x140013dab  shl     rax, 5
0x140013daf  cmp     dword ptr [rax+rsi], 7
0x140013db3  jnz     short loc_140013DF4
0x140013db5  cmp     word ptr [rax+rsi+8], 13h
0x140013dbb  jnz     short loc_140013DF4
0x140013dbd  mov     edi, [rax+rsi+10h]
0x140013dc1  cmp     rcx, r14
0x140013dc4  jz      short loc_140013DF4
0x140013dc6  test    dword ptr [rcx+1Ch], 20000h
0x140013dcd  jz      short loc_140013DF4
0x140013dcf  cmp     byte ptr [rcx+19h], 4
0x140013dd3  jb      short loc_140013DF4
0x140013dd5  mov     rcx, [rcx+10h]
0x140013dd9  lea     r8, WPP_9c18ab671221381626cab8868253e78d_Traceguids
0x140013de0  mov     edx, 10h
0x140013de5  mov     r9d, edi
0x140013de8  call    WPP_SF_d
0x140013ded  mov     rcx, cs:WPP_GLOBAL_Control
0x140013df4  inc     r13d
0x140013df7  cmp     r13d, ebx
0x140013dfa  jb      short loc_140013DA8
0x140013dfc  mov     r13d, [rbp+57h+var_60]
0x140013e00  mov     rdx, rsi; struct _tagEASPolicy *
0x140013e03  mov     ecx, ebx; unsigned int
0x140013e05  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x140013e0a  lea     rax, [rbp+57h+arg_10]
0x140013e0e  xor     r9d, r9d; unsigned int
0x140013e11  lea     r8, aInactivitytime; "InactivityTimeoutSecs"
0x140013e18  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x140013e1d  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140013e24  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140013e29  mov     rbx, [rbp+57h+arg_0]
0x140013e2d  test    edi, edi
0x140013e2f  jz      short loc_140013E3E
0x140013e31  mov     eax, [rbp+57h+arg_10]
0x140013e34  test    eax, eax
0x140013e36  jz      short loc_140013E4D
0x140013e38  cmp     edi, eax
0x140013e3a  ja      short loc_140013E47
0x140013e3c  jmp     short loc_140013E4D
0x140013e3e  xor     edi, edi
0x140013e40  mov     eax, [rbp+57h+arg_10]
0x140013e43  test    eax, eax
0x140013e45  jz      short loc_140013E6B
0x140013e47  mov     edi, eax
0x140013e49  test    eax, eax
0x140013e4b  jz      short loc_140013E6B
0x140013e4d  cmp     [rbp+57h+var_70], r12d
0x140013e51  jz      short loc_140013E67
0x140013e53  cmp     [rbp+57h+var_6C], r12d
0x140013e57  jz      short loc_140013E67
0x140013e59  mov     esi, [rbp+57h+pvParam]
0x140013e5c  test    esi, esi
0x140013e5e  jz      short loc_140013E67
0x140013e60  cmp     edi, esi
0x140013e62  cmovb   esi, edi
0x140013e65  jmp     short loc_140013E7E
0x140013e67  mov     esi, edi
0x140013e69  jmp     short loc_140013E82
0x140013e6b  cmp     [rbp+57h+var_70], r12d
0x140013e6f  jz      short loc_140013EE0
0x140013e71  cmp     [rbp+57h+var_6C], r12d
0x140013e75  jz      short loc_140013EE0
0x140013e77  mov     esi, [rbp+57h+pvParam]
0x140013e7a  test    esi, esi
0x140013e7c  jz      short loc_140013EE0
0x140013e7e  test    esi, esi
0x140013e80  jz      short loc_140013EE0
0x140013e82  lea     rcx, [rbp+57h+plii]; plii
0x140013e86  mov     [rbp+57h+plii.cbSize], 8
0x140013e8d  call    cs:__imp_GetLastInputInfo
0x140013e93  test    eax, eax
0x140013e95  jz      short loc_140013EE0
0x140013e97  mov     ebx, [rbp+57h+plii.dwTime]
0x140013e9a  call    cs:__imp_GetTickCount64
0x140013ea0  mov     rcx, rax
0x140013ea3  mov     rax, 624DD2F1A9FBE77h
0x140013ead  sub     rcx, rbx
0x140013eb0  mov     rbx, [rbp+57h+arg_0]
0x140013eb4  mul     rcx
0x140013eb7  sub     rcx, rdx
0x140013eba  shr     rcx, 1
0x140013ebd  add     rcx, rdx
0x140013ec0  shr     rcx, 9
0x140013ec4  cmp     esi, ecx
0x140013ec6  ja      short loc_140013ED3
0x140013ec8  mov     esi, [rbp+57h+arg_8]
0x140013ecb  mov     r12d, 1
0x140013ed1  jmp     short loc_140013EE3
0x140013ed3  mov     r13d, esi
0x140013ed6  mov     esi, 1
0x140013edb  sub     r13d, ecx
0x140013ede  jmp     short loc_140013EE3
0x140013ee0  mov     esi, r12d
0x140013ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x140013eea  cmp     rcx, r14
0x140013eed  jz      short loc_140013F30
0x140013eef  test    dword ptr [rcx+1Ch], 4000h
0x140013ef6  jz      short loc_140013F30
0x140013ef8  cmp     byte ptr [rcx+19h], 4
0x140013efc  jb      short loc_140013F30
0x140013efe  mov     eax, [rbp+57h+pvParam]
0x140013f01  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140013f08  mov     rcx, [rcx+10h]
0x140013f0c  mov     edx, 0Dh
0x140013f11  mov     [rsp+38h], r13d
0x140013f16  mov     r9d, edi
0x140013f19  mov     [rsp+0B0h+var_80], eax
0x140013f1d  mov     eax, [rbp+57h+var_70]
0x140013f20  mov     [rsp+0B0h+var_88], eax
0x140013f24  mov     eax, [rbp+57h+var_6C]
0x140013f27  mov     dword ptr [rsp+0B0h+var_90], eax
0x140013f2b  call    WPP_SF_lllll
0x140013f30  mov     rdi, [rsp+80h]
0x140013f38  test    r12d, r12d
0x140013f3b  mov     r12, [rsp+0B0h+var_38]
0x140013f40  jnz     loc_140013FE3
0x140013f46  lea     rdx, [rbp+57h+var_5C]; unsigned int *
0x140013f4a  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140013f4d  call    ?WlLockGetDelayLockSettings@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@PEAK@Z; WlLockGetDelayLockSettings(_WLSM_GLOBAL_CONTEXT *,ulong *)
0x140013f52  mov     rcx, [rbx+8]; this
0x140013f56  call    ?IsDomainMember@CMachine@@QEAAHXZ; CMachine::IsDomainMember(void)
0x140013f5b  xor     r9d, r9d
0x140013f5e  lea     r8, aAllowdomaindel; "AllowDomainDelayLock"
0x140013f65  test    eax, eax
0x140013f67  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x140013f6e  lea     rax, [rbp+57h+var_68]
0x140013f72  setz    r9b; unsigned int
0x140013f76  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x140013f7b  mov     [rbp+57h+var_68], r9d
0x140013f7f  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140013f84  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f8b  cmp     rcx, r14
0x140013f8e  jz      short loc_140013FB8
0x140013f90  test    dword ptr [rcx+1Ch], 4000h
0x140013f97  jz      short loc_140013FB8
0x140013f99  cmp     byte ptr [rcx+19h], 4
0x140013f9d  jb      short loc_140013FB8
0x140013f9f  mov     r9d, [rbp+57h+var_68]
0x140013fa3  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140013faa  mov     rcx, [rcx+10h]
0x140013fae  mov     edx, 0Eh
0x140013fb3  call    WPP_SF_d
0x140013fb8  cmp     [rbp+57h+var_68], 0
0x140013fbc  jz      short loc_140013FE3
0x140013fbe  mov     eax, [rbp+57h+var_5C]
0x140013fc1  cmp     eax, 0FFFFFFFFh
0x140013fc4  jz      short loc_140013FD5
0x140013fc6  cmp     eax, 3Ch ; '<'
0x140013fc9  jb      short loc_140013FE3
0x140013fcb  mov     ecx, 384h
0x140013fd0  cmp     eax, ecx
0x140013fd2  cmova   eax, ecx
0x140013fd5  test    esi, esi
0x140013fd7  jz      short loc_140013FE5
0x140013fd9  cmp     eax, r13d
0x140013fdc  jbe     short loc_140013FE5
0x140013fde  mov     [r15], r13d
0x140013fe1  jmp     short loc_140013FE8
0x140013fe3  xor     eax, eax
0x140013fe5  mov     [r15], eax
0x140013fe8  add     rsp, 88h
0x140013fef  pop     r15
0x140013ff1  pop     r14
0x140013ff3  pop     r13
0x140013ff5  pop     rsi
0x140013ff6  pop     rbx
0x140013ff7  pop     rbp
0x140013ff8  retn
```
