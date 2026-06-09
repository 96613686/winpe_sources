# MpRegPreRenameKey

- ea: `0x14007e274`
- end: `0x14007ea65`
- name: `MpRegPreRenameKey`
- size: `2033`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x1400064b0`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x14004a758`
- `0x14004b4cc`
- `0x14004b6d0`
- `0x14004c630`
- `0x14004f59c`
- `0x14004f6bc`
- `0x140068d40`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`
- `0x14007e274`
- `0x14007fb14`
- `0x14007fb34`
- `0x14007fc94`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14007e539`
- `ntoskrnl!IoGetCurrentProcess` at `0x14007e539`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e966`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e9c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e966`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e9c2`

## string_xrefs

- `0x14007e6eb`: `RegNtPreRenameKey`
- `0x14007e71c`: `RegNtPreRenameKey`
- `0x14007e75f`: `RegNtPreRenameKey`
- `0x14007e792`: `RegNtPreRenameKey`
- `0x14007e5c0`: `[Mini-filter] Denied registry key rename from [%wZ] to [%wZ] triggered by process [%wZ].`
- `0x14007e696`: `[Mini-filter][TP] Denied registry key rename from [%wZ] to [%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreRenameKey(PVOID *a1, int a2, __int64 *a3, _BYTE *a4, _QWORD *a5)
{
  _QWORD *v5; // r9
  _BYTE *v6; // rbx
  PVOID *v7; // r10
  int KeyDestinationName; // edi
  __int64 v9; // r15
  PVOID *v10; // r12
  _QWORD *v11; // r13
  volatile signed __int32 *v12; // r14
  bool v13; // si
  int KeyName; // eax
  __int64 v15; // rdx
  PVOID v16; // rdx
  char v17; // dl
  int v18; // r8d
  unsigned int i; // ebx
  char IsRegistryHardeningExemptByContext; // dl
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v22; // rax
  char v23; // al
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // r9
  _BYTE *v28; // rdx
  int v29; // ecx
  char IsTamperProtectedLevelExempt; // al
  int v31; // edx
  PVOID *v32; // rax
  PVOID *v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 *v37; // rax
  PVOID v38; // rsi
  void (__fastcall *v39)(PVOID); // rax
  void *v40; // rcx
  void (__fastcall *v41)(_QWORD *); // rax
  void *v42; // rcx
  int v44; // [rsp+20h] [rbp-81h]
  char v45; // [rsp+40h] [rbp-61h]
  int v46; // [rsp+44h] [rbp-5Dh]
  __int64 v47; // [rsp+48h] [rbp-59h]
  volatile signed __int32 *v48; // [rsp+50h] [rbp-51h] BYREF
  __int64 v49; // [rsp+58h] [rbp-49h] BYREF
  _BYTE *v50; // [rsp+60h] [rbp-41h]
  __int64 v51; // [rsp+68h] [rbp-39h] BYREF
  _QWORD *v52; // [rsp+70h] [rbp-31h]
  PVOID P; // [rsp+78h] [rbp-29h] BYREF
  PVOID *v54; // [rsp+80h] [rbp-21h]
  void *v55; // [rsp+88h] [rbp-19h]
  __int64 *v56; // [rsp+90h] [rbp-11h]
  PVOID Entry; // [rsp+98h] [rbp-9h]

  v50 = a4;
  v5 = a5;
  v6 = 0;
  v49 = 0;
  v56 = a3;
  v7 = a1;
  v54 = a1;
  KeyDestinationName = 0;
  v52 = a5;
  v9 = 0;
  Entry = 0;
  v10 = 0;
  v51 = 0;
  v11 = 0;
  v55 = 0;
  v12 = 0;
  P = 0;
  v48 = 0;
  v46 = 0;
  if ( a1 && a3 )
  {
    *a3 = 0;
    v13 = (*(_DWORD *)(MpData + 868) & 0x40) != 0;
    if ( (a2 & 4) != 0 || (*(_DWORD *)(MpData + 868) & 0x40) != 0 && (a2 & 0x2000000) != 0 )
    {
      if ( a5 )
      {
        Entry = a5;
        v52 = 0;
      }
      else
      {
        KeyName = MpRegpGetKeyName(*a1);
        KeyDestinationName = KeyName;
        if ( KeyName < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
            goto LABEL_101;
          }
          _mm_lfence();
          v15 = 98;
          v44 = KeyName;
          goto LABEL_100;
        }
        v7 = v54;
      }
      if ( (*(_DWORD *)(MpData + 864) & 4) != 0 )
        goto LABEL_21;
      KeyDestinationName = MpRegpCopyUnicodeString((PCUNICODE_STRING)v7[1]);
      if ( KeyDestinationName < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_101;
        v15 = 99;
        goto LABEL_18;
      }
      if ( !v55 )
LABEL_21:
        v16 = v54[1];
      else
        v16 = v55;
      KeyDestinationName = MpRegpGetKeyDestinationName(Entry, v16, &v51);
      if ( KeyDestinationName < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            100,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            KeyDestinationName);
        }
        v9 = v51;
        goto LABEL_101;
      }
      v47 = 4;
      v17 = 0;
      if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
      {
        BYTE2(v47) = 8;
        v17 = 1;
      }
      BYTE4(v47) = v17 | 2;
      BYTE3(v47) = 2 * (v13 | (2 * (v13 | (2 * (v13 | (8 * (v13 | (2 * v13))))))));
      MpRegMatchData(Entry, 0, v47, &v49);
      v9 = v51;
      MpRegMatchData(v51, 0, v47, &P);
      v6 = (_BYTE *)v49;
      v11 = P;
      if ( v49 )
      {
        if ( P )
        {
          for ( i = 0; i < *(_DWORD *)v11; ++i )
          {
            KeyDestinationName = MpRegAddMatches(v11[1] + 16LL * i, &v49);
            if ( KeyDestinationName < 0 )
            {
              v6 = (_BYTE *)v49;
              goto LABEL_101;
            }
          }
          v6 = (_BYTE *)v49;
          *(_QWORD *)(v49 + 24) |= v11[3];
        }
        if ( v6 )
        {
LABEL_41:
          IsRegistryHardeningExemptByContext = 0;
          v45 = 0;
          if ( (v6[26] & 8) != 0 || (v6[28] & 1) != 0 )
          {
            CurrentProcess = IoGetCurrentProcess();
            MpGetProcessContextByObject(CurrentProcess, &v48);
            v12 = v48;
            IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v48);
            v45 = IsRegistryHardeningExemptByContext;
          }
          if ( (v6[26] & 8) != 0 )
          {
            v46 = 1;
            if ( !v12 || IsRegistryHardeningExemptByContext )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                if ( v12 )
                  v22 = *((_QWORD *)v12 + 16);
                else
                  v22 = 0;
                WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 102, v18, (_DWORD)Entry, v9, v22);
              }
              v6[26] &= ~8u;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 101, v18, (_DWORD)Entry, v9, *((_QWORD *)v12 + 16));
              }
              MpLogPrintfW(
                L"[Mini-filter] Denied registry key rename from [%wZ] to [%wZ] triggered by process [%wZ].",
                Entry,
                v9,
                *((_QWORD *)v12 + 16));
              *v50 = 1;
              v6[24] = v6[24] & 0xF3 | 4;
            }
          }
          v23 = MpRegTPAllowChange(v6 + 24, Entry, &v48);
          v12 = v48;
          if ( v23 )
          {
            v29 = v46;
            v28 = v50;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              if ( v48 )
                v26 = *((_QWORD *)v48 + 16);
              else
                v26 = 0;
              WPP_SF_ZZZ(WPP_GLOBAL_Control->AttachedDevice, 103, v24, (_DWORD)Entry, v9, v26);
            }
            if ( v12 )
              v27 = *((_QWORD *)v12 + 16);
            else
              v27 = 0;
            MpLogPrintfW(
              L"[Mini-filter][TP] Denied registry key rename from [%wZ] to [%wZ] triggered by process [%wZ].",
              Entry,
              v9,
              v27);
            v28 = v50;
            v29 = 2;
            v46 = 2;
            *v50 = 1;
            v6[24] = v6[24] & 0xF3 | 4;
          }
          if ( *v28 == 1 )
            v6[26] |= 8u;
          if ( v29 )
          {
            if ( v29 == 2 && v12 && (v12[15] & 0x200) != 0 )
            {
              LOBYTE(v28) = *v28 == 0;
              MpTraceRegHardeningNotification(
                3,
                (_DWORD)v28,
                (_DWORD)v12,
                (unsigned int)"RegNtPreRenameKey",
                (__int64)Entry,
                v9,
                0);
              v28 = v50;
            }
            LOBYTE(v28) = *v28 == 0;
            MpTraceRegHardeningNotification(
              (v46 == 2) + 1,
              (_DWORD)v28,
              (_DWORD)v12,
              (unsigned int)"RegNtPreRenameKey",
              (__int64)Entry,
              v9,
              0);
          }
          if ( (char)v6[27] < 0 )
          {
            IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v48, v28, v24, v25);
            v31 = (int)Entry;
            v12 = v48;
            LOBYTE(v31) = IsTamperProtectedLevelExempt;
            MpTraceRegHardeningNotification(
              4,
              v31,
              (_DWORD)v48,
              (unsigned int)"RegNtPreRenameKey",
              (__int64)Entry,
              v9,
              0);
          }
          if ( (v6[28] & 1) != 0 )
          {
            LOBYTE(v28) = v45;
            MpTraceRegHardeningNotification(
              5,
              (_DWORD)v28,
              (_DWORD)v12,
              (unsigned int)"RegNtPreRenameKey",
              (__int64)Entry,
              v9,
              0);
          }
          if ( *v50 == 1 )
          {
            v32 = (PVOID *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
            v10 = v32;
            if ( v32 )
            {
              memset(v32, 0, 0x78u);
              v10[12] = v6;
              v10[1] = Entry;
              v33 = v54;
              v10[3] = (PVOID)v9;
              *v10 = *v33;
              v10[11] = (PVOID)*((_QWORD *)v6 + 3);
              *((_DWORD *)v10 + 26) = v46;
              KeyDestinationName = MpRegpSendNotification((__int64)v12, (__int64)v10, v34);
              if ( KeyDestinationName >= 0
                || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_101;
              }
              v15 = 105;
LABEL_18:
              _mm_lfence();
              v44 = KeyDestinationName;
LABEL_100:
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                v15,
                WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                KeGetCurrentThread(),
                v44);
              goto LABEL_101;
            }
            KeyDestinationName = -1073741670;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_101;
            }
            v15 = 104;
          }
          else
          {
            v35 = MpRegpAllocRenameKeyContext();
            v36 = v35;
            if ( v35 )
            {
              *(_QWORD *)(v35 + 56) = v6;
              v6 = 0;
              *(_QWORD *)(v35 + 40) = Entry;
              v37 = v56;
              *(_QWORD *)(v36 + 48) = v9;
              v9 = 0;
              Entry = 0;
              *v37 = v36;
              goto LABEL_115;
            }
            KeyDestinationName = -1073741670;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_101;
            }
            v15 = 106;
          }
          v44 = -1073741670;
          goto LABEL_100;
        }
      }
      else if ( !P )
      {
        KeyDestinationName = 0;
LABEL_101:
        v38 = Entry;
        if ( Entry )
        {
          v39 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
          if ( v39 )
          {
            v39(Entry);
          }
          else
          {
            v40 = (void *)*((_QWORD *)Entry + 2);
            if ( v40 )
              ExFreePoolWithTag(v40, 0x4B72504Du);
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v38);
          }
          Entry = 0;
        }
        v5 = v52;
        goto LABEL_109;
      }
      v6 = v11;
      v11 = 0;
      goto LABEL_41;
    }
  }
  else
  {
    KeyDestinationName = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v15 = 97;
      v44 = -1073741811;
      goto LABEL_100;
    }
  }
LABEL_109:
  if ( v5 )
  {
    v41 = (void (__fastcall *)(_QWORD *))*((_QWORD *)MpRegData + 5);
    if ( v41 )
    {
      v41(v5);
    }
    else
    {
      v42 = (void *)v5[2];
      if ( v42 )
      {
        ExFreePoolWithTag(v42, 0x4B72504Du);
        v5 = v52;
      }
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v5);
    }
  }
LABEL_115:
  if ( v55 )
    MpRegpFreeUnicodeString();
  if ( v9 )
    MpRegpFreeDestinationKeyName(v9);
  if ( v6 )
    MpRegFreeMatchingInfo(v6);
  if ( v11 )
    MpRegFreeMatchingInfo(v11);
  if ( v10 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v10);
  if ( v12 )
    MpReleaseProcessContext(v12);
  return (unsigned int)KeyDestinationName;
}

```

## disassembly

```asm
0x14007e274  push    rbp
0x14007e276  push    rbx
0x14007e277  push    rsi
0x14007e278  push    rdi
0x14007e279  push    r12
0x14007e27b  push    r13
0x14007e27d  push    r14
0x14007e27f  push    r15
0x14007e281  lea     rbp, [rsp-17h]
0x14007e286  sub     rsp, 0B8h
0x14007e28d  mov     rax, cs:__security_cookie
0x14007e294  xor     rax, rsp
0x14007e297  mov     [rbp+4Fh+var_50], rax
0x14007e29b  xor     esi, esi
0x14007e29d  mov     [rbp+4Fh+var_90], r9
0x14007e2a1  mov     r9, [rbp+4Fh+arg_20]
0x14007e2a5  mov     ebx, esi
0x14007e2a7  mov     [rbp+4Fh+var_98], rbx
0x14007e2ab  mov     rax, r8
0x14007e2ae  mov     [rbp+4Fh+var_60], rax
0x14007e2b2  mov     r10, rcx
0x14007e2b5  mov     [rbp+4Fh+var_70], rcx
0x14007e2b9  mov     edi, esi
0x14007e2bb  mov     [rbp+4Fh+var_80], r9
0x14007e2bf  mov     r15d, esi
0x14007e2c2  mov     [rbp+4Fh+Entry], rsi
0x14007e2c6  mov     r12d, esi
0x14007e2c9  mov     [rbp+4Fh+var_88], rsi
0x14007e2cd  mov     r13d, esi
0x14007e2d0  mov     [rbp+4Fh+var_68], rsi
0x14007e2d4  mov     r14d, esi
0x14007e2d7  mov     [rbp+4Fh+P], rsi
0x14007e2db  mov     [rbp+4Fh+var_A0], rsi
0x14007e2df  mov     [rbp+4Fh+var_AC], esi
0x14007e2e2  test    rcx, rcx
0x14007e2e5  jz      loc_14007E8E0
0x14007e2eb  test    rax, rax
0x14007e2ee  jz      loc_14007E8E0
0x14007e2f4  mov     [r8], rsi
0x14007e2f7  mov     rax, cs:MpData
0x14007e2fe  mov     ecx, [rax+364h]
0x14007e304  and     ecx, 40h
0x14007e307  setnz   sil
0x14007e30b  test    dl, 4
0x14007e30e  jnz     short loc_14007E325
0x14007e310  test    ecx, ecx
0x14007e312  jz      loc_14007E994
0x14007e318  shr     rdx, 18h
0x14007e31c  test    dl, 2
0x14007e31f  jz      loc_14007E994
0x14007e325  test    r9, r9
0x14007e328  jnz     short loc_14007E376
0x14007e32a  mov     rcx, [r10]; Object
0x14007e32d  lea     rdx, [rbp+4Fh+Entry]
0x14007e331  call    MpRegpGetKeyName
0x14007e336  mov     edi, eax
0x14007e338  test    eax, eax
0x14007e33a  jns     short loc_14007E370
0x14007e33c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e343  lea     rsi, WPP_GLOBAL_Control
0x14007e34a  cmp     rcx, rsi
0x14007e34d  jz      loc_14007E934
0x14007e353  mov     ecx, [rcx+2Ch]
0x14007e356  test    cl, 4
0x14007e359  jz      loc_14007E934
0x14007e35f  lfence
0x14007e362  mov     edx, 62h ; 'b'
0x14007e367  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14007e36b  jmp     loc_14007E914
0x14007e370  mov     r10, [rbp+4Fh+var_70]
0x14007e374  jmp     short loc_14007E37E
0x14007e376  mov     [rbp+4Fh+Entry], r9
0x14007e37a  mov     [rbp+4Fh+var_80], rbx
0x14007e37e  mov     rax, cs:MpData
0x14007e385  mov     ecx, [rax+360h]
0x14007e38b  test    cl, 4
0x14007e38e  jnz     short loc_14007E3E4
0x14007e390  mov     rcx, [r10+8]; SourceString
0x14007e394  lea     rdx, [rbp+4Fh+var_68]
0x14007e398  call    MpRegpCopyUnicodeString
0x14007e39d  mov     edi, eax
0x14007e39f  test    eax, eax
0x14007e3a1  jns     short loc_14007E3D6
0x14007e3a3  mov     rax, cs:WPP_GLOBAL_Control
0x14007e3aa  lea     rsi, WPP_GLOBAL_Control
0x14007e3b1  cmp     rax, rsi
0x14007e3b4  jz      loc_14007E934
0x14007e3ba  mov     eax, [rax+2Ch]
0x14007e3bd  test    al, 1
0x14007e3bf  jz      loc_14007E934
0x14007e3c5  mov     edx, 63h ; 'c'
0x14007e3ca  lfence
0x14007e3cd  mov     dword ptr [rsp+0F0h+var_D0], edi
0x14007e3d1  jmp     loc_14007E914
0x14007e3d6  mov     r8, [rbp+4Fh+var_68]
0x14007e3da  test    r8, r8
0x14007e3dd  jz      short loc_14007E3E4
0x14007e3df  mov     rdx, r8
0x14007e3e2  jmp     short loc_14007E3EC
0x14007e3e4  mov     rdx, [rbp+4Fh+var_70]
0x14007e3e8  mov     rdx, [rdx+8]
0x14007e3ec  mov     rcx, [rbp+4Fh+Entry]
0x14007e3f0  lea     r8, [rbp+4Fh+var_88]
0x14007e3f4  call    MpRegpGetKeyDestinationName
0x14007e3f9  mov     edi, eax
0x14007e3fb  test    eax, eax
0x14007e3fd  jns     short loc_14007E44E
0x14007e3ff  mov     rax, cs:WPP_GLOBAL_Control
0x14007e406  lea     rsi, WPP_GLOBAL_Control
0x14007e40d  cmp     rax, rsi
0x14007e410  jz      short loc_14007E445
0x14007e412  mov     eax, [rax+2Ch]
0x14007e415  test    al, 1
0x14007e417  jz      short loc_14007E445
0x14007e419  lfence
0x14007e41c  mov     r9, gs:188h
0x14007e425  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007e42c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e433  mov     edx, 64h ; 'd'
0x14007e438  mov     dword ptr [rsp+0F0h+var_D0], edi
0x14007e43c  mov     rcx, [rcx+18h]
0x14007e440  call    WPP_SF_qD
0x14007e445  mov     r15, [rbp+4Fh+var_88]
0x14007e449  jmp     loc_14007E934
0x14007e44e  mov     rax, cs:MpData
0x14007e455  mov     [rbp+4Fh+var_A8], rbx
0x14007e459  mov     dl, byte ptr [rbp+4Fh+var_A8+4]
0x14007e45c  mov     byte ptr [rbp+4Fh+var_A8], 4
0x14007e460  mov     ecx, [rax+364h]
0x14007e466  test    cl, 8
0x14007e469  jz      short loc_14007E472
0x14007e46b  or      byte ptr [rbp+4Fh+var_A8+2], 8
0x14007e46f  or      dl, 1
0x14007e472  mov     al, byte ptr [rbp+4Fh+var_A8+3]
0x14007e475  lea     r9, [rbp+4Fh+var_98]
0x14007e479  or      dl, 2
0x14007e47c  mov     cl, sil
0x14007e47f  add     cl, cl
0x14007e481  mov     byte ptr [rbp+4Fh+var_A8+4], dl
0x14007e484  or      cl, sil
0x14007e487  and     al, 31h
0x14007e489  shl     cl, 3
0x14007e48c  xor     edx, edx
0x14007e48e  or      cl, sil
0x14007e491  add     cl, cl
0x14007e493  or      cl, sil
0x14007e496  add     cl, cl
0x14007e498  or      cl, sil
0x14007e49b  add     cl, cl
0x14007e49d  or      cl, al
0x14007e49f  mov     byte ptr [rbp+4Fh+var_A8+3], cl
0x14007e4a2  mov     r8, [rbp+4Fh+var_A8]
0x14007e4a6  mov     rcx, [rbp+4Fh+Entry]
0x14007e4aa  call    MpRegMatchData
0x14007e4af  mov     r15, [rbp+4Fh+var_88]
0x14007e4b3  lea     r9, [rbp+4Fh+P]
0x14007e4b7  mov     r8, [rbp+4Fh+var_A8]
0x14007e4bb  mov     rcx, r15
0x14007e4be  xor     edx, edx
0x14007e4c0  call    MpRegMatchData
0x14007e4c5  mov     rbx, [rbp+4Fh+var_98]
0x14007e4c9  mov     r13, [rbp+4Fh+P]
0x14007e4cd  test    rbx, rbx
0x14007e4d0  jnz     short loc_14007E4DE
0x14007e4d2  test    r13, r13
0x14007e4d5  jnz     short loc_14007E522
0x14007e4d7  xor     edi, edi
0x14007e4d9  jmp     loc_14007E934
0x14007e4de  test    r13, r13
0x14007e4e1  jz      short loc_14007E51D
0x14007e4e3  xor     ebx, ebx
0x14007e4e5  cmp     ebx, [r13+0]
0x14007e4e9  jnb     short loc_14007E511
0x14007e4eb  mov     ecx, ebx
0x14007e4ed  lea     rdx, [rbp+4Fh+var_98]
0x14007e4f1  shl     rcx, 4
0x14007e4f5  add     rcx, [r13+8]
0x14007e4f9  call    MpRegAddMatches
0x14007e4fe  mov     edi, eax
0x14007e500  test    eax, eax
0x14007e502  js      short loc_14007E508
0x14007e504  inc     ebx
0x14007e506  jmp     short loc_14007E4E5
0x14007e508  mov     rbx, [rbp+4Fh+var_98]
0x14007e50c  jmp     loc_14007E934
0x14007e511  mov     rbx, [rbp+4Fh+var_98]
0x14007e515  mov     rax, [r13+18h]
0x14007e519  or      [rbx+18h], rax
0x14007e51d  test    rbx, rbx
0x14007e520  jnz     short loc_14007E528
0x14007e522  mov     rbx, r13
0x14007e525  xor     r13d, r13d
0x14007e528  xor     dl, dl
0x14007e52a  test    byte ptr [rbx+1Ah], 8
0x14007e52e  mov     [rbp+4Fh+var_B0], dl
0x14007e531  jnz     short loc_14007E539
0x14007e533  test    byte ptr [rbx+1Ch], 1
0x14007e537  jz      short loc_14007E562
0x14007e539  call    cs:__imp_IoGetCurrentProcess
0x14007e540  nop     dword ptr [rax+rax+00h]
0x14007e545  mov     rcx, rax; Process
0x14007e548  lea     rdx, [rbp+4Fh+var_A0]
0x14007e54c  call    MpGetProcessContextByObject
0x14007e551  mov     r14, [rbp+4Fh+var_A0]
0x14007e555  mov     rcx, r14
0x14007e558  call    MpIsRegistryHardeningExemptByContext
0x14007e55d  mov     dl, al
0x14007e55f  mov     [rbp+4Fh+var_B0], al
0x14007e562  test    byte ptr [rbx+1Ah], 8
0x14007e566  lea     rsi, WPP_GLOBAL_Control
0x14007e56d  jz      loc_14007E629
0x14007e573  mov     [rbp+4Fh+var_AC], 1
0x14007e57a  test    r14, r14
0x14007e57d  jz      short loc_14007E5E6
0x14007e57f  test    dl, dl
0x14007e581  jnz     short loc_14007E5E6
0x14007e583  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e58a  cmp     rcx, rsi
0x14007e58d  jz      short loc_14007E5B9
0x14007e58f  mov     eax, [rcx+2Ch]
0x14007e592  test    al, 2
0x14007e594  jz      short loc_14007E5B9
0x14007e596  mov     rax, [r14+80h]
0x14007e59d  mov     edx, 65h ; 'e'
0x14007e5a2  mov     r9, [rbp+4Fh+Entry]
0x14007e5a6  mov     rcx, [rcx+18h]
0x14007e5aa  mov     [rsp+0F0h+var_C8], rax
0x14007e5af  mov     [rsp+0F0h+var_D0], r15
0x14007e5b4  call    WPP_SF_ZZZ
0x14007e5b9  mov     r9, [r14+80h]
0x14007e5c0  lea     rcx, aMiniFilterDeni_0; "[Mini-filter] Denied registry key renam"...
0x14007e5c7  mov     rdx, [rbp+4Fh+Entry]
0x14007e5cb  mov     r8, r15
0x14007e5ce  call    MpLogPrintfW
0x14007e5d3  mov     rax, [rbp+4Fh+var_90]
0x14007e5d7  mov     byte ptr [rax], 1
0x14007e5da  mov     al, [rbx+18h]
0x14007e5dd  and     al, 0F7h
0x14007e5df  or      al, 4
0x14007e5e1  mov     [rbx+18h], al
0x14007e5e4  jmp     short loc_14007E629
0x14007e5e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5ed  cmp     rcx, rsi
0x14007e5f0  jz      short loc_14007E625
0x14007e5f2  mov     eax, [rcx+2Ch]
0x14007e5f5  test    al, 4
0x14007e5f7  jz      short loc_14007E625
0x14007e5f9  test    r14, r14
0x14007e5fc  jz      short loc_14007E607
0x14007e5fe  mov     rax, [r14+80h]
0x14007e605  jmp     short loc_14007E609
0x14007e607  xor     eax, eax
0x14007e609  mov     r9, [rbp+4Fh+Entry]
0x14007e60d  mov     edx, 66h ; 'f'
0x14007e612  mov     rcx, [rcx+18h]
0x14007e616  mov     [rsp+0F0h+var_C8], rax
0x14007e61b  mov     [rsp+0F0h+var_D0], r15
0x14007e620  call    WPP_SF_ZZZ
0x14007e625  and     byte ptr [rbx+1Ah], 0F7h
0x14007e629  mov     rdx, [rbp+4Fh+Entry]
0x14007e62d  lea     rcx, [rbx+18h]
0x14007e631  lea     r8, [rbp+4Fh+var_A0]
0x14007e635  call    MpRegTPAllowChange
0x14007e63a  mov     r14, [rbp+4Fh+var_A0]
0x14007e63e  test    al, al
0x14007e640  jnz     short loc_14007E6C0
0x14007e642  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e649  cmp     rcx, rsi
0x14007e64c  jz      short loc_14007E681
0x14007e64e  mov     eax, [rcx+2Ch]
0x14007e651  test    al, 2
0x14007e653  jz      short loc_14007E681
0x14007e655  test    r14, r14
0x14007e658  jz      short loc_14007E663
0x14007e65a  mov     rax, [r14+80h]
0x14007e661  jmp     short loc_14007E665
0x14007e663  xor     eax, eax
0x14007e665  mov     r9, [rbp+4Fh+Entry]
0x14007e669  mov     edx, 67h ; 'g'
0x14007e66e  mov     rcx, [rcx+18h]
0x14007e672  mov     [rsp+0F0h+var_C8], rax
0x14007e677  mov     [rsp+0F0h+var_D0], r15
0x14007e67c  call    WPP_SF_ZZZ
0x14007e681  test    r14, r14
0x14007e684  jz      short loc_14007E68F
0x14007e686  mov     r9, [r14+80h]
0x14007e68d  jmp     short loc_14007E692
0x14007e68f  xor     r9d, r9d
0x14007e692  mov     rdx, [rbp+4Fh+Entry]
0x14007e696  lea     rcx, aMiniFilterTpDe; "[Mini-filter][TP] Denied registry key r"...
0x14007e69d  mov     r8, r15
0x14007e6a0  call    MpLogPrintfW
0x14007e6a5  mov     rdx, [rbp+4Fh+var_90]
0x14007e6a9  mov     ecx, 2
0x14007e6ae  mov     [rbp+4Fh+var_AC], ecx
0x14007e6b1  mov     byte ptr [rdx], 1
0x14007e6b4  mov     al, [rbx+18h]
0x14007e6b7  and     al, 0F7h
0x14007e6b9  or      al, 4
0x14007e6bb  mov     [rbx+18h], al
  ... truncated ...
```
