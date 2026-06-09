# MpRegPreCreateKeyEx

- ea: `0x14004dda0`
- end: `0x14004e5b3`
- name: `MpRegPreCreateKeyEx`
- size: `2067`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x140006afc`
- `0x140009bf0`
- `0x14000d2c0`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x14004a758`
- `0x14004c630`
- `0x14004dda0`
- `0x14004e5c0`
- `0x14004f59c`
- `0x14004fefc`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e17a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e17a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004e236`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004e236`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004defa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004defa`

## string_xrefs

- `0x14004e3ca`: `RegNtPreCreateKeyEx`
- `0x14004e3f7`: `RegNtPreCreateKeyEx`
- `0x14004e439`: `RegNtPreCreateKeyEx`
- `0x14004e46c`: `RegNtPreCreateKeyEx`
- `0x14004e0af`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows Defender\Exclusions`
- `0x14004e2b5`: `[Mini-filter] Denied registry key creation of [%wZ] triggered by process [%wZ].`
- `0x14004e379`: `[Mini-filter][TP] Denied registry creation [%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreCreateKeyEx(
        struct _UNICODE_STRING **a1,
        int a2,
        __int64 *a3,
        _BYTE *a4,
        UNICODE_STRING *a5,
        char a6)
{
  __int64 v6; // rdi
  int v7; // r14d
  UNICODE_STRING *v8; // rsi
  _BYTE *v10; // r12
  volatile signed __int32 *v11; // r13
  char v12; // al
  int v13; // ecx
  bool v14; // bl
  char v15; // al
  __int64 v17; // rdx
  char v18; // dl
  char v19; // bl
  int matched; // eax
  int v21; // r8d
  bool v22; // zf
  char v23; // al
  __int64 v24; // r8
  __int64 v25; // r9
  _BYTE *v26; // rcx
  __int64 v27; // rdx
  __int64 KeyContext; // r15
  bool v29; // al
  __int64 *v30; // rax
  struct _KPROCESS *CurrentProcess; // rax
  unsigned __int8 IsRegistryHardeningExemptByContext; // al
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // r8
  unsigned __int8 IsTamperProtectedLevelExempt; // al
  PVOID v37; // rax
  __int64 v38; // r8
  int v39; // [rsp+28h] [rbp-69h]
  unsigned __int8 v40[8]; // [rsp+48h] [rbp-49h] BYREF
  PVOID P; // [rsp+50h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+58h] [rbp-39h]
  _BYTE *v43; // [rsp+60h] [rbp-31h]
  volatile signed __int32 *v44; // [rsp+68h] [rbp-29h] BYREF
  __int64 v45; // [rsp+70h] [rbp-21h] BYREF
  __int64 *v46; // [rsp+78h] [rbp-19h]
  UNICODE_STRING String2; // [rsp+80h] [rbp-11h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v43 = a4;
  v46 = a3;
  v10 = 0;
  *(_QWORD *)&String2.Length = a1;
  P = 0;
  v11 = 0;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  if ( !a1 || !a3 )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_10;
    v17 = 20;
    v39 = -1073741811;
    goto LABEL_22;
  }
  *a3 = 0;
  v12 = a2;
  v13 = *(_DWORD *)(MpData + 868) & 0x40;
  if ( v13 )
    v12 = a2;
  v14 = v13 != 0;
  if ( (v12 & 1) != 0 || v13 && (a2 & 0x2000000) != 0 )
  {
    if ( a5 )
    {
      v15 = a6;
      v8 = a5;
    }
    else
    {
      v40[0] = 0;
      v7 = MpRegpCheckExistingKey(a1, v40, &P);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            v7);
        }
        v8 = (UNICODE_STRING *)P;
        goto LABEL_10;
      }
      v15 = v40[0];
      v8 = (UNICODE_STRING *)P;
    }
    if ( v15 )
      goto LABEL_10;
    P = (PVOID)1;
    v18 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      BYTE2(P) |= 4u;
      v18 = 1;
    }
    BYTE4(P) = v18 | 2;
    BYTE3(P) = BYTE3(P) & 0x31 | (2 * (v14 | (2 * (v14 | (2 * (v14 | (8 * (v14 | (2 * v14)))))))));
    v19 = (char)P;
    matched = MpRegMatchData(v8, 0, P, &v45);
    v7 = matched;
    if ( matched < 0 )
    {
      if ( matched == -1073741198 )
      {
        v10 = (_BYTE *)v45;
        v7 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            matched);
        }
        v10 = (_BYTE *)v45;
      }
      goto LABEL_10;
    }
    v10 = (_BYTE *)v45;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_ZZii(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)&WPP_GLOBAL_Control,
        v21,
        **(_QWORD **)&String2.Length,
        (__int64)v8,
        *(_QWORD *)(v45 + 24),
        v19);
    LOBYTE(v21) = 0;
    v22 = (v10[26] & 4) == 0;
    v40[0] = 0;
    if ( !v22 || (v10[28] & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v44);
      v11 = v44;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v44);
      v21 = IsRegistryHardeningExemptByContext;
      v40[0] = IsRegistryHardeningExemptByContext;
    }
    if ( (v10[26] & 4) != 0 )
    {
      v42 = 1;
      if ( !v11 || (_BYTE)v21 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v11 )
            v33 = *((_QWORD *)v11 + 16);
          else
            v33 = 0;
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 25, v21, (_DWORD)v8, v33);
        }
        v10[26] &= ~4u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 24, v21, (_DWORD)v8, *((_QWORD *)v11 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry key creation of [%wZ] triggered by process [%wZ].",
          v8,
          *((_QWORD *)v11 + 16));
        *v43 = 1;
        v10[24] = v10[24] & 0xFC | 1;
      }
    }
    v23 = MpRegTPAllowChange(v10 + 24, v8, &v44);
    v11 = v44;
    if ( v23 )
    {
      v26 = v43;
      v27 = v42;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v44 )
          v34 = *((_QWORD *)v44 + 16);
        else
          v34 = 0;
        WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 26, v24, (_DWORD)v8, v34);
      }
      if ( v11 )
        v35 = *((_QWORD *)v11 + 16);
      else
        v35 = 0;
      MpLogPrintfW(L"[Mini-filter][TP] Denied registry creation [%wZ] triggered by process [%wZ].", v8, v35);
      v26 = v43;
      v27 = 2;
      v42 = 2;
      *v43 = 1;
      v10[24] = v10[24] & 0xFC | 1;
    }
    if ( *v26 == 1 )
      v10[26] |= 4u;
    if ( (_DWORD)v27 )
    {
      if ( (_DWORD)v27 == 2 && v11 && (v11[15] & 0x200) != 0 )
      {
        LOBYTE(v27) = *v26 == 0;
        MpTraceRegHardeningNotification(3, v27, (_DWORD)v11, (unsigned int)"RegNtPreCreateKeyEx", (__int64)v8, 0, 0);
        v26 = v43;
      }
      LOBYTE(v27) = *v26 == 0;
      MpTraceRegHardeningNotification(
        (v42 == 2) + 1,
        v27,
        (_DWORD)v11,
        (unsigned int)"RegNtPreCreateKeyEx",
        (__int64)v8,
        0,
        0);
      v26 = v43;
    }
    if ( (char)v10[27] < 0 )
    {
      IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v44, v27, v24, v25);
      v11 = v44;
      MpTraceRegHardeningNotification(
        4,
        IsTamperProtectedLevelExempt,
        (_DWORD)v44,
        (unsigned int)"RegNtPreCreateKeyEx",
        (__int64)v8,
        0,
        0);
      v26 = v43;
    }
    if ( (v10[28] & 1) != 0 )
    {
      MpTraceRegHardeningNotification(5, v40[0], (_DWORD)v11, (unsigned int)"RegNtPreCreateKeyEx", (__int64)v8, 0, 0);
      v26 = v43;
    }
    if ( !*v26 )
    {
      *(_QWORD *)&String2.Length = 9699474;
      String2.Buffer = L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows Defender\\Exclusions";
      KeyContext = MpRegpAllocCreateKeyContext();
      if ( KeyContext )
      {
        v29 = *(_BYTE *)(MpData + 4048) && RtlEqualUnicodeString(v8, &String2, 0);
        *(_BYTE *)(KeyContext + 56) = v29;
        v30 = v46;
        *(_QWORD *)(KeyContext + 40) = v8;
        v8 = 0;
        *(_QWORD *)(KeyContext + 48) = v10;
        v10 = 0;
        *v30 = KeyContext;
        goto LABEL_10;
      }
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_10;
      v17 = 27;
      v39 = -1073741670;
LABEL_22:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v17,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        v39);
      goto LABEL_10;
    }
    v37 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
    v6 = (__int64)v37;
    if ( !v37 )
    {
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_10;
      v17 = 28;
      v39 = -1073741670;
      goto LABEL_22;
    }
    memset(v37, 0, 0x78u);
    *(_QWORD *)(v6 + 96) = v10;
    *(_QWORD *)(v6 + 8) = v8;
    *(_QWORD *)(v6 + 88) = *((_QWORD *)v10 + 3);
    *(_DWORD *)(v6 + 104) = v42;
    v7 = MpRegpSendNotification((__int64)v11, v6, v38);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_10;
      _mm_lfence();
      v17 = 29;
      v39 = v7;
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids, v8);
  }
LABEL_10:
  if ( v8 )
    ExFreePoolWithTag(v8, 0x5364504Du);
  if ( v10 )
    MpRegFreeMatchingInfo(v10);
  if ( v6 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), (PVOID)v6);
  if ( v11 )
    MpReleaseProcessContext(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14004dda0  mov     r11, rsp
0x14004dda3  push    rbp
0x14004dda4  push    r13
0x14004dda6  push    r14
0x14004dda8  lea     rbp, [r11-4Fh]
0x14004ddac  sub     rsp, 0C0h
0x14004ddb3  mov     rax, cs:__security_cookie
0x14004ddba  xor     rax, rsp
0x14004ddbd  mov     [rbp+47h+var_48], rax
0x14004ddc1  mov     [r11-20h], rbx
0x14004ddc5  mov     rax, r8
0x14004ddc8  mov     r8, [rbp+47h+arg_20]
0x14004ddcc  mov     [r11-28h], rsi
0x14004ddd0  mov     [r11-30h], rdi
0x14004ddd4  xor     edi, edi
0x14004ddd6  mov     [r11-38h], r12
0x14004ddda  mov     r14d, edi
0x14004dddd  mov     [r11-40h], r15
0x14004dde1  mov     esi, edi
0x14004dde3  mov     [rbp+47h+var_78], r9
0x14004dde7  mov     r9, rcx
0x14004ddea  mov     [rbp+47h+var_60], rax
0x14004ddee  mov     r12d, edi
0x14004ddf1  mov     qword ptr [rbp+47h+String2.Length], rcx
0x14004ddf5  mov     r15d, edi
0x14004ddf8  mov     [rbp+47h+P], rdi
0x14004ddfc  mov     r13d, edi
0x14004ddff  mov     [rbp+47h+var_68], rdi
0x14004de03  mov     [rbp+47h+var_70], rdi
0x14004de07  mov     [rbp+47h+var_80], edi
0x14004de0a  test    rcx, rcx
0x14004de0d  jz      loc_14004DF08
0x14004de13  test    rax, rax
0x14004de16  jz      loc_14004DF08
0x14004de1c  mov     [rax], rdi
0x14004de1f  mov     rax, cs:MpData
0x14004de26  mov     ecx, [rax+364h]
0x14004de2c  mov     rax, rdx
0x14004de2f  and     ecx, 40h
0x14004de32  cmovnz  rax, rdx
0x14004de36  test    ecx, ecx
0x14004de38  setnz   bl
0x14004de3b  test    al, 1
0x14004de3d  jz      loc_14004E18E
0x14004de43  test    r8, r8
0x14004de46  jnz     loc_14004E001
0x14004de4c  lea     r8, [rbp+47h+P]
0x14004de50  mov     [rbp+47h+var_90], sil
0x14004de54  lea     rdx, [rbp+47h+var_90]
0x14004de58  mov     rcx, r9
0x14004de5b  call    MpRegpCheckExistingKey
0x14004de60  mov     r14d, eax
0x14004de63  test    eax, eax
0x14004de65  js      loc_14004DF62
0x14004de6b  movzx   eax, [rbp+47h+var_90]
0x14004de6f  mov     rsi, [rbp+47h+P]
0x14004de73  test    al, al
0x14004de75  jz      loc_14004DF82
0x14004de7b  mov     rbx, [rsp+0B8h]
0x14004de83  test    rsi, rsi
0x14004de86  jnz     short loc_14004DEF2
0x14004de88  mov     rsi, [rsp+0D0h+var_20]
0x14004de90  test    r12, r12
0x14004de93  jnz     loc_14004E581
0x14004de99  mov     r12, [rsp+0D0h+var_30]
0x14004dea1  test    rdi, rdi
0x14004dea4  jnz     loc_14004E58E
0x14004deaa  mov     rdi, [rsp+0D0h+var_28]
0x14004deb2  test    r15, r15
0x14004deb5  jz      short loc_14004DEC4
0x14004deb7  mov     rax, [r15+8]
0x14004debb  mov     rcx, r15
0x14004debe  call    cs:__guard_dispatch_icall_fptr
0x14004dec4  mov     r15, [rsp+0D0h+var_38]
0x14004decc  test    r13, r13
0x14004decf  jnz     loc_14004E5A6
0x14004ded5  mov     eax, r14d
0x14004ded8  mov     rcx, [rbp+47h+var_48]
0x14004dedc  xor     rcx, rsp; StackCookie
0x14004dedf  call    __security_check_cookie
0x14004dee4  add     rsp, 0C0h
0x14004deeb  pop     r14
0x14004deed  pop     r13
0x14004deef  pop     rbp
0x14004def0  retn
0x14004def2  mov     edx, 5364504Dh; Tag
0x14004def7  mov     rcx, rsi; P
0x14004defa  call    cs:__imp_ExFreePoolWithTag
0x14004df01  nop     dword ptr [rax+rax+00h]
0x14004df06  jmp     short loc_14004DE88
0x14004df08  mov     r14d, 0C000000Dh
0x14004df0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df15  lea     rax, WPP_GLOBAL_Control
0x14004df1c  cmp     rcx, rax
0x14004df1f  jz      loc_14004DE7B
0x14004df25  mov     eax, [rcx+2Ch]
0x14004df28  test    al, 1
0x14004df2a  jz      loc_14004DE7B
0x14004df30  mov     edx, 14h
0x14004df35  mov     dword ptr [rsp+0D0h+var_B0], 0C000000Dh
0x14004df3d  mov     r9, gs:188h
0x14004df46  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004df4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df54  mov     rcx, [rcx+18h]
0x14004df58  call    WPP_SF_qD
0x14004df5d  jmp     loc_14004DE7B
0x14004df62  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df69  lea     rax, WPP_GLOBAL_Control
0x14004df70  cmp     rcx, rax
0x14004df73  jnz     loc_14004E1A8
0x14004df79  mov     rsi, [rbp+47h+P]
0x14004df7d  jmp     loc_14004DE7B
0x14004df82  mov     rax, cs:MpData
0x14004df89  mov     [rbp+47h+P], rdi
0x14004df8d  movzx   edx, byte ptr [rbp+47h+P+4]
0x14004df91  mov     byte ptr [rbp+47h+P], 1
0x14004df95  mov     ecx, [rax+364h]
0x14004df9b  test    cl, 8
0x14004df9e  jz      short loc_14004DFA7
0x14004dfa0  or      byte ptr [rbp+47h+P+2], 4
0x14004dfa4  or      dl, 1
0x14004dfa7  movzx   eax, byte ptr [rbp+47h+P+3]
0x14004dfab  lea     r9, [rbp+47h+var_68]
0x14004dfaf  movzx   ecx, bl
0x14004dfb2  or      dl, 2
0x14004dfb5  add     cl, cl
0x14004dfb7  mov     byte ptr [rbp+47h+P+4], dl
0x14004dfba  or      cl, bl
0x14004dfbc  and     al, 31h
0x14004dfbe  shl     cl, 3
0x14004dfc1  xor     edx, edx
0x14004dfc3  or      cl, bl
0x14004dfc5  add     cl, cl
0x14004dfc7  or      cl, bl
0x14004dfc9  add     cl, cl
0x14004dfcb  or      cl, bl
0x14004dfcd  add     cl, cl
0x14004dfcf  or      cl, al
0x14004dfd1  mov     byte ptr [rbp+47h+P+3], cl
0x14004dfd4  mov     rcx, rsi
0x14004dfd7  mov     rbx, [rbp+47h+P]
0x14004dfdb  mov     r8, rbx
0x14004dfde  call    MpRegMatchData
0x14004dfe3  mov     r14d, eax
0x14004dfe6  test    eax, eax
0x14004dfe8  jns     short loc_14004E00D
0x14004dfea  cmp     eax, 0C0000272h
0x14004dfef  jnz     loc_14004E1E6
0x14004dff5  mov     r12, [rbp+47h+var_68]
0x14004dff9  mov     r14d, edi
0x14004dffc  jmp     loc_14004DE7B
0x14004e001  movzx   eax, [rbp+47h+arg_28]
0x14004e005  mov     rsi, r8
0x14004e008  jmp     loc_14004DE73
0x14004e00d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e014  lea     rdx, WPP_GLOBAL_Control
0x14004e01b  mov     r12, [rbp+47h+var_68]
0x14004e01f  cmp     rcx, rdx
0x14004e022  jnz     loc_14004E102
0x14004e028  xor     r8b, r8b
0x14004e02b  test    byte ptr [r12+1Ah], 4
0x14004e031  mov     [rbp+47h+var_90], r8b
0x14004e035  jnz     loc_14004E236
0x14004e03b  test    byte ptr [r12+1Ch], 1
0x14004e041  jnz     loc_14004E236
0x14004e047  test    byte ptr [r12+1Ah], 4
0x14004e04d  jnz     loc_14004E26D
0x14004e053  lea     rcx, [r12+18h]
0x14004e058  mov     rdx, rsi
0x14004e05b  lea     r8, [rbp+47h+var_70]
0x14004e05f  call    MpRegTPAllowChange
0x14004e064  mov     r13, [rbp+47h+var_70]
0x14004e068  test    al, al
0x14004e06a  jz      loc_14004E324
0x14004e070  mov     rcx, [rbp+47h+var_78]
0x14004e074  lea     rbx, WPP_GLOBAL_Control
0x14004e07b  mov     edx, [rbp+47h+var_80]
0x14004e07e  cmp     byte ptr [rcx], 1
0x14004e081  jz      loc_14004E3A8
0x14004e087  test    edx, edx
0x14004e089  jnz     loc_14004E3B3
0x14004e08f  cmp     [r12+1Bh], dil
0x14004e094  jl      loc_14004E42C
0x14004e09a  test    byte ptr [r12+1Ch], 1
0x14004e0a0  jnz     loc_14004E468
0x14004e0a6  cmp     [rcx], dil
0x14004e0a9  jnz     loc_14004E498
0x14004e0af  lea     rax, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x14004e0b6  mov     qword ptr [rbp+47h+String2.Length], 940092h
0x14004e0be  mov     [rbp+47h+String2.Buffer], rax
0x14004e0c2  call    MpRegpAllocCreateKeyContext
0x14004e0c7  mov     r15, rax
0x14004e0ca  test    rax, rax
0x14004e0cd  jnz     short loc_14004E13D
0x14004e0cf  mov     r14d, 0C000009Ah
0x14004e0d5  mov     rax, cs:WPP_GLOBAL_Control
0x14004e0dc  cmp     rax, rbx
0x14004e0df  jz      loc_14004DE7B
0x14004e0e5  mov     eax, [rax+2Ch]
0x14004e0e8  test    al, 1
0x14004e0ea  jz      loc_14004DE7B
0x14004e0f0  mov     edx, 1Bh
0x14004e0f5  mov     dword ptr [rsp+0D0h+var_B0], 0C000009Ah
0x14004e0fd  jmp     loc_14004DF3D
0x14004e102  mov     eax, [rcx+2Ch]
0x14004e105  test    al, 4
0x14004e107  jz      loc_14004E028
0x14004e10d  mov     rax, [r12+18h]
0x14004e112  mov     r9, qword ptr [rbp+47h+String2.Length]
0x14004e116  mov     rcx, [rcx+18h]
0x14004e11a  mov     [rsp+30h], rbx
0x14004e11f  mov     [rsp+0D0h+var_A8], rax
0x14004e124  mov     r9, [r9]
0x14004e127  mov     [rsp+0D0h+var_B0], rsi
0x14004e12c  call    WPP_SF_ZZii
0x14004e131  lea     rdx, WPP_GLOBAL_Control
0x14004e138  jmp     loc_14004E028
0x14004e13d  mov     rax, cs:MpData
0x14004e144  cmp     [rax+0FD0h], dil
0x14004e14b  jnz     short loc_14004E170
0x14004e14d  xor     al, al
0x14004e14f  mov     [r15+38h], al
0x14004e153  mov     rax, [rbp+47h+var_60]
0x14004e157  mov     [r15+28h], rsi
0x14004e15b  mov     rsi, rdi
0x14004e15e  mov     [r15+30h], r12
0x14004e162  mov     r12, rdi
0x14004e165  mov     [rax], r15
0x14004e168  mov     r15, rdi
0x14004e16b  jmp     loc_14004DE7B
0x14004e170  xor     r8d, r8d; CaseInSensitive
0x14004e173  lea     rdx, [rbp+47h+String2]; String2
0x14004e177  mov     rcx, rsi; String1
0x14004e17a  call    cs:__imp_RtlEqualUnicodeString
0x14004e181  nop     dword ptr [rax+rax+00h]
0x14004e186  test    al, al
0x14004e188  jz      short loc_14004E14D
0x14004e18a  mov     al, 1
0x14004e18c  jmp     short loc_14004E14F
0x14004e18e  test    ecx, ecx
0x14004e190  jz      loc_14004DE7B
0x14004e196  shr     rdx, 18h
0x14004e19a  test    dl, 2
0x14004e19d  jz      loc_14004DE7B
0x14004e1a3  jmp     loc_14004DE43
0x14004e1a8  mov     ecx, [rcx+2Ch]
0x14004e1ab  test    cl, 4
0x14004e1ae  jz      loc_14004DF79
0x14004e1b4  lfence
0x14004e1b7  mov     r9, gs:188h
0x14004e1c0  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004e1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e1ce  mov     edx, 15h
0x14004e1d3  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x14004e1d8  mov     rcx, [rcx+18h]
0x14004e1dc  call    WPP_SF_qD
0x14004e1e1  jmp     loc_14004DF79
0x14004e1e6  mov     rax, cs:WPP_GLOBAL_Control
0x14004e1ed  lea     rbx, WPP_GLOBAL_Control
0x14004e1f4  cmp     rax, rbx
0x14004e1f7  jz      short loc_14004E22D
0x14004e1f9  mov     eax, [rax+2Ch]
0x14004e1fc  test    al, 1
0x14004e1fe  jz      short loc_14004E22D
0x14004e200  lfence
0x14004e203  mov     r9, gs:188h
0x14004e20c  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004e213  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e21a  mov     edx, 16h
0x14004e21f  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x14004e224  mov     rcx, [rcx+18h]
0x14004e228  call    WPP_SF_qD
0x14004e22d  mov     r12, [rbp+47h+var_68]
0x14004e231  jmp     loc_14004DE7B
0x14004e236  call    cs:__imp_IoGetCurrentProcess
0x14004e23d  nop     dword ptr [rax+rax+00h]
0x14004e242  mov     rcx, rax; Process
0x14004e245  lea     rdx, [rbp+47h+var_70]
0x14004e249  call    MpGetProcessContextByObject
0x14004e24e  mov     r13, [rbp+47h+var_70]
0x14004e252  mov     rcx, r13
0x14004e255  call    MpIsRegistryHardeningExemptByContext
0x14004e25a  movzx   r8d, al
0x14004e25e  mov     [rbp+47h+var_90], al
0x14004e261  lea     rdx, WPP_GLOBAL_Control
0x14004e268  jmp     loc_14004E047
0x14004e26d  mov     [rbp+47h+var_80], 1
0x14004e274  test    r13, r13
0x14004e277  jz      short loc_14004E2DF
0x14004e279  test    r8b, r8b
0x14004e27c  jnz     short loc_14004E2DF
0x14004e27e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e285  cmp     rcx, rdx
0x14004e288  jz      short loc_14004E2AE
0x14004e28a  mov     eax, [rcx+2Ch]
0x14004e28d  test    al, 2
0x14004e28f  jz      short loc_14004E2AE
0x14004e291  mov     rax, [r13+80h]
0x14004e298  mov     edx, 18h
0x14004e29d  mov     rcx, [rcx+18h]
  ... truncated ...
```
