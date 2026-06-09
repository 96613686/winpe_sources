# MpRegPreSetKeySecurity

- ea: `0x1400496d8`
- end: `0x140049eb4`
- name: `MpRegPreSetKeySecurity`
- size: `2012`
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
- `0x14000a24c`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x1400496d8`
- `0x14004a758`
- `0x14004b6d0`
- `0x14004c630`
- `0x14004f59c`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`
- `0x14007fce4`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140049a02`
- `ntoskrnl!IoGetCurrentProcess` at `0x140049a02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049e5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049e5b`

## string_xrefs

- `0x140049bb1`: `RegNtPreSetKeySecurity`
- `0x140049be2`: `RegNtPreSetKeySecurity`
- `0x140049c25`: `RegNtPreSetKeySecurity`
- `0x140049c58`: `RegNtPreSetKeySecurity`
- `0x140049a79`: `[Mini-filter] Denied registry key set security of [%wZ] triggered by process [%wZ].`
- `0x140049b5f`: `Due to Tamper Protection, blocked set security [%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreSetKeySecurity(PVOID *a1, int a2, __int64 *a3, _BYTE *a4, _QWORD *a5)
{
  _QWORD *v5; // r12
  _BYTE *v6; // rbx
  int v7; // r14d
  volatile signed __int32 *v8; // rsi
  PVOID *v9; // r13
  int KeyName; // eax
  PVOID v11; // r9
  char v12; // dl
  char v13; // cl
  int matched; // eax
  int v15; // r8d
  PVOID v16; // rdi
  void (__fastcall *v17)(PVOID); // rax
  __int64 v19; // rdx
  char IsRegistryHardeningExemptByContext; // dl
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v22; // rax
  char v23; // al
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // r8
  _BYTE *v28; // rdx
  int v29; // ecx
  char IsTamperProtectedLevelExempt; // al
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 *v35; // rax
  PVOID *v36; // rax
  __int64 v37; // r8
  void *v38; // rcx
  void (__fastcall *v39)(_QWORD *); // rax
  void *v40; // rcx
  int v41; // [rsp+20h] [rbp-71h]
  int v42; // [rsp+20h] [rbp-71h]
  bool v43; // [rsp+40h] [rbp-51h]
  char v44; // [rsp+40h] [rbp-51h]
  _QWORD *v45; // [rsp+48h] [rbp-49h]
  int v46; // [rsp+50h] [rbp-41h]
  __int64 v47; // [rsp+58h] [rbp-39h]
  volatile signed __int32 *v48; // [rsp+60h] [rbp-31h] BYREF
  PVOID P; // [rsp+68h] [rbp-29h] BYREF
  _BYTE *v50; // [rsp+70h] [rbp-21h]
  __int64 *v51; // [rsp+78h] [rbp-19h]
  PVOID *v52; // [rsp+80h] [rbp-11h]
  PVOID Entry; // [rsp+88h] [rbp-9h]

  v5 = a5;
  v6 = 0;
  v7 = 0;
  v50 = a4;
  v8 = 0;
  v52 = a1;
  v45 = a5;
  v9 = 0;
  v51 = a3;
  Entry = 0;
  P = 0;
  v48 = 0;
  v46 = 0;
  if ( !a1 || !a3 )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_21;
    v19 = 139;
    v41 = -1073741811;
    goto LABEL_36;
  }
  *a3 = 0;
  v43 = (*(_DWORD *)(MpData + 868) & 0x40) != 0;
  if ( (a2 & 0x10000) == 0 && ((*(_DWORD *)(MpData + 868) & 0x40) == 0 || (a2 & 0x2000000) == 0) )
    goto LABEL_21;
  if ( a5 )
  {
    v11 = a5;
    Entry = a5;
    v45 = 0;
    goto LABEL_7;
  }
  KeyName = MpRegpGetKeyName(*a1);
  v7 = KeyName;
  if ( KeyName >= 0 )
  {
    v11 = Entry;
LABEL_7:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids, v11);
    v47 = 0x10000;
    v12 = 0;
    v13 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      v13 = 1;
      v12 = 1;
    }
    BYTE4(v47) = v12 | 2;
    BYTE3(v47) = v13 & 0x31 | (2 * (v43 | (2 * (v43 | (2 * (v43 | (8 * (v43 | (2 * v43)))))))));
    matched = MpRegMatchData(Entry, 0, v47, &P);
    v7 = matched;
    if ( matched < 0 )
    {
      if ( matched == -1073741198 )
      {
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          142,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          matched);
      }
      v6 = P;
      goto LABEL_16;
    }
    v6 = P;
    if ( !P )
    {
      v7 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          143,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          -1073741823);
      goto LABEL_16;
    }
    IsRegistryHardeningExemptByContext = 0;
    v44 = 0;
    if ( (*((_BYTE *)P + 27) & 1) != 0 || (*((_BYTE *)P + 28) & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v48);
      v8 = v48;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v48);
      v44 = IsRegistryHardeningExemptByContext;
    }
    if ( (v6[27] & 1) != 0 )
    {
      v46 = 1;
      if ( !v8 || IsRegistryHardeningExemptByContext )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v8 )
            v22 = *((_QWORD *)v8 + 16);
          else
            v22 = 0;
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 145, v15, (_DWORD)Entry, v22);
        }
        v6[27] &= ~1u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 144, v15, (_DWORD)Entry, *((_QWORD *)v8 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry key set security of [%wZ] triggered by process [%wZ].",
          Entry,
          *((_QWORD *)v8 + 16));
        *v50 = 1;
        v6[26] = v6[26] & 0xFC | 1;
      }
    }
    v23 = MpRegTPAllowChange(v6 + 24, Entry, &v48);
    v8 = v48;
    if ( v23 )
    {
      v29 = v46;
      v28 = v50;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v48 )
          v26 = *((_QWORD *)v48 + 16);
        else
          v26 = 0;
        WPP_SF_qZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          146,
          (unsigned int)WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          (__int64)Entry,
          v26);
      }
      if ( v8 )
        v27 = *((_QWORD *)v8 + 16);
      else
        v27 = 0;
      MpLogPrintfW(L"Due to Tamper Protection, blocked set security [%wZ] triggered by process [%wZ].", Entry, v27);
      v28 = v50;
      v29 = 2;
      v46 = 2;
      *v50 = 1;
      v6[26] = v6[26] & 0xFC | 1;
    }
    if ( *v28 == 1 )
      v6[27] |= 1u;
    if ( v29 )
    {
      if ( v29 == 2 && v8 && (v8[15] & 0x200) != 0 )
      {
        LOBYTE(v28) = *v28 == 0;
        MpTraceRegHardeningNotification(
          3,
          (_DWORD)v28,
          (_DWORD)v8,
          (unsigned int)"RegNtPreSetKeySecurity",
          (__int64)Entry,
          0,
          0);
        v28 = v50;
      }
      LOBYTE(v28) = *v28 == 0;
      MpTraceRegHardeningNotification(
        (v46 == 2) + 1,
        (_DWORD)v28,
        (_DWORD)v8,
        (unsigned int)"RegNtPreSetKeySecurity",
        (__int64)Entry,
        0,
        0);
    }
    if ( (char)v6[27] < 0 )
    {
      IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v48, v28, v24, v25);
      v31 = (int)Entry;
      v8 = v48;
      LOBYTE(v31) = IsTamperProtectedLevelExempt;
      MpTraceRegHardeningNotification(4, v31, (_DWORD)v48, (unsigned int)"RegNtPreSetKeySecurity", (__int64)Entry, 0, 0);
    }
    if ( (v6[28] & 1) != 0 )
    {
      LOBYTE(v28) = v44;
      MpTraceRegHardeningNotification(
        5,
        (_DWORD)v28,
        (_DWORD)v8,
        (unsigned int)"RegNtPreSetKeySecurity",
        (__int64)Entry,
        0,
        0);
    }
    if ( *v50 )
    {
      v36 = (PVOID *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
      v9 = v36;
      if ( v36 )
      {
        memset(v36, 0, 0x78u);
        v9[12] = v6;
        v9[1] = Entry;
        *v9 = *v52;
        v9[11] = (PVOID)*((_QWORD *)v6 + 3);
        *((_DWORD *)v9 + 26) = v46;
        v7 = MpRegpSendNotification((__int64)v8, (__int64)v9, v37);
        if ( v7 >= 0
          || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        {
          goto LABEL_16;
        }
        _mm_lfence();
        v34 = 149;
        v42 = v7;
        goto LABEL_91;
      }
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_16;
      v34 = 148;
    }
    else
    {
      v32 = MpRegpAllocSetKeySecurityContext();
      v33 = v32;
      if ( v32 )
      {
        *(_QWORD *)(v32 + 40) = Entry;
        v35 = v51;
        Entry = 0;
        *(_QWORD *)(v33 + 48) = v6;
        v6 = 0;
        *v35 = v33;
        goto LABEL_16;
      }
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_16;
      v34 = 147;
    }
    v42 = -1073741670;
LABEL_91:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v34,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      v42);
LABEL_16:
    v5 = v45;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    _mm_lfence();
    v19 = 140;
    v41 = KeyName;
LABEL_36:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v19,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      v41);
  }
LABEL_17:
  v16 = Entry;
  if ( Entry )
  {
    v17 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
    if ( v17 )
    {
      v17(Entry);
    }
    else
    {
      v38 = (void *)*((_QWORD *)Entry + 2);
      if ( v38 )
        ExFreePoolWithTag(v38, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v16);
    }
    Entry = 0;
  }
LABEL_21:
  if ( v5 )
  {
    v39 = (void (__fastcall *)(_QWORD *))*((_QWORD *)MpRegData + 5);
    if ( v39 )
    {
      v39(v5);
    }
    else
    {
      v40 = (void *)v5[2];
      if ( v40 )
        ExFreePoolWithTag(v40, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v5);
    }
  }
  if ( v6 )
    MpRegFreeMatchingInfo(v6);
  if ( v9 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v9);
  if ( v8 )
    MpReleaseProcessContext(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400496d8  push    rbp
0x1400496da  push    rbx
0x1400496db  push    rsi
0x1400496dc  push    rdi
0x1400496dd  push    r12
0x1400496df  push    r13
0x1400496e1  push    r14
0x1400496e3  push    r15
0x1400496e5  lea     rbp, [rsp-17h]
0x1400496ea  sub     rsp, 0A8h
0x1400496f1  mov     rax, cs:__security_cookie
0x1400496f8  xor     rax, rsp
0x1400496fb  mov     [rbp+4Fh+var_50], rax
0x1400496ff  mov     r12, [rbp+4Fh+arg_20]
0x140049703  xor     ebx, ebx
0x140049705  xor     r14d, r14d
0x140049708  mov     [rbp+4Fh+var_70], r9
0x14004970c  xor     esi, esi
0x14004970e  mov     [rbp+4Fh+var_60], rcx
0x140049712  mov     rax, r8
0x140049715  mov     [rbp+4Fh+var_98], r12
0x140049719  xor     r13d, r13d
0x14004971c  mov     [rbp+4Fh+var_68], rax
0x140049720  mov     [rbp+4Fh+Entry], r14
0x140049724  mov     r8, rcx
0x140049727  mov     [rbp+4Fh+P], rbx
0x14004972b  mov     [rbp+4Fh+var_80], rsi
0x14004972f  mov     [rbp+4Fh+var_90], ebx
0x140049732  test    rcx, rcx
0x140049735  jz      loc_140049DC6
0x14004973b  test    rax, rax
0x14004973e  jz      loc_140049DC6
0x140049744  mov     [rax], rbx
0x140049747  lea     edi, [rbx+1]
0x14004974a  mov     rax, cs:MpData
0x140049751  mov     ecx, [rax+364h]
0x140049757  mov     rax, rdx
0x14004975a  and     ecx, 40h
0x14004975d  setnz   [rbp+4Fh+var_A0]
0x140049761  shr     rax, 10h
0x140049765  test    dil, al
0x140049768  jz      loc_1400498C3
0x14004976e  test    r12, r12
0x140049771  jnz     loc_1400498B3
0x140049777  mov     rcx, [r8]; Object
0x14004977a  lea     rdx, [rbp+4Fh+Entry]
0x14004977e  call    MpRegpGetKeyName
0x140049783  mov     r14d, eax
0x140049786  test    eax, eax
0x140049788  js      loc_1400498D5
0x14004978e  mov     r9, [rbp+4Fh+Entry]
0x140049792  mov     rcx, cs:WPP_GLOBAL_Control
0x140049799  lea     r15, WPP_GLOBAL_Control
0x1400497a0  lea     r12, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400497a7  cmp     rcx, r15
0x1400497aa  jz      short loc_1400497B7
0x1400497ac  mov     eax, [rcx+2Ch]
0x1400497af  test    al, 4
0x1400497b1  jnz     loc_140049938
0x1400497b7  mov     rax, cs:MpData
0x1400497be  mov     [rbp+4Fh+var_88], rbx
0x1400497c2  mov     dl, byte ptr [rbp+4Fh+var_88+4]
0x1400497c5  mov     byte ptr [rbp+4Fh+var_88+2], dil
0x1400497c9  mov     ecx, [rax+364h]
0x1400497cf  test    cl, 8
0x1400497d2  mov     cl, byte ptr [rbp+4Fh+var_88+3]
0x1400497d5  jz      short loc_1400497DD
0x1400497d7  or      cl, dil
0x1400497da  or      dl, dil
0x1400497dd  mov     r8b, [rbp+4Fh+var_A0]
0x1400497e1  lea     r9, [rbp+4Fh+P]
0x1400497e5  mov     al, r8b
0x1400497e8  and     cl, 31h
0x1400497eb  add     al, al
0x1400497ed  or      dl, 2
0x1400497f0  or      al, r8b
0x1400497f3  mov     byte ptr [rbp+4Fh+var_88+4], dl
0x1400497f6  shl     al, 3
0x1400497f9  xor     edx, edx
0x1400497fb  or      al, r8b
0x1400497fe  add     al, al
0x140049800  or      al, r8b
0x140049803  add     al, al
0x140049805  or      al, r8b
0x140049808  add     al, al
0x14004980a  or      al, cl
0x14004980c  mov     rcx, [rbp+4Fh+Entry]
0x140049810  mov     byte ptr [rbp+4Fh+var_88+3], al
0x140049813  mov     r8, [rbp+4Fh+var_88]
0x140049817  call    MpRegMatchData
0x14004981c  mov     r14d, eax
0x14004981f  test    eax, eax
0x140049821  jns     loc_140049998
0x140049827  cmp     eax, 0C0000272h
0x14004982c  jnz     loc_14004994E
0x140049832  xor     r14d, r14d
0x140049835  mov     rbx, [rbp+4Fh+P]
0x140049839  mov     r12, [rbp+4Fh+var_98]
0x14004983d  mov     rdi, [rbp+4Fh+Entry]
0x140049841  test    rdi, rdi
0x140049844  jz      short loc_14004986B
0x140049846  mov     rax, cs:MpRegData
0x14004984d  mov     rax, [rax+28h]
0x140049851  test    rax, rax
0x140049854  jz      loc_140049DF9
0x14004985a  mov     rcx, rdi
0x14004985d  call    cs:__guard_dispatch_icall_fptr
0x140049863  mov     [rbp+4Fh+Entry], 0
0x14004986b  test    r12, r12
0x14004986e  jnz     loc_140049E2E
0x140049874  test    rbx, rbx
0x140049877  jnz     loc_140049E82
0x14004987d  test    r13, r13
0x140049880  jnz     loc_140049E8F
0x140049886  test    rsi, rsi
0x140049889  jnz     loc_140049EA7
0x14004988f  mov     eax, r14d
0x140049892  mov     rcx, [rbp+4Fh+var_50]
0x140049896  xor     rcx, rsp; StackCookie
0x140049899  call    __security_check_cookie
0x14004989e  add     rsp, 0A8h
0x1400498a5  pop     r15
0x1400498a7  pop     r14
0x1400498a9  pop     r13
0x1400498ab  pop     r12
0x1400498ad  pop     rdi
0x1400498ae  pop     rsi
0x1400498af  pop     rbx
0x1400498b0  pop     rbp
0x1400498b1  retn
0x1400498b3  mov     r9, r12
0x1400498b6  mov     [rbp+4Fh+Entry], r12
0x1400498ba  mov     [rbp+4Fh+var_98], rbx
0x1400498be  jmp     loc_140049792
0x1400498c3  test    ecx, ecx
0x1400498c5  jz      short loc_14004986B
0x1400498c7  shr     rdx, 18h
0x1400498cb  test    dl, 2
0x1400498ce  jz      short loc_14004986B
0x1400498d0  jmp     loc_14004976E
0x1400498d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498dc  lea     r15, WPP_GLOBAL_Control
0x1400498e3  cmp     rcx, r15
0x1400498e6  jz      loc_14004983D
0x1400498ec  mov     ecx, [rcx+2Ch]
0x1400498ef  test    cl, 4
0x1400498f2  jz      loc_14004983D
0x1400498f8  lfence
0x1400498fb  mov     edx, 8Ch
0x140049900  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140049904  jmp     short loc_140049913
0x140049906  mov     edx, 8Bh
0x14004990b  mov     dword ptr [rsp+0E0h+var_C0], 0C000000Dh
0x140049913  mov     r9, gs:188h
0x14004991c  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x140049923  mov     rcx, cs:WPP_GLOBAL_Control
0x14004992a  mov     rcx, [rcx+18h]
0x14004992e  call    WPP_SF_qD
0x140049933  jmp     loc_14004983D
0x140049938  mov     rcx, [rcx+18h]
0x14004993c  mov     edx, 8Dh
0x140049941  mov     r8, r12
0x140049944  call    WPP_SF_Z
0x140049949  jmp     loc_1400497B7
0x14004994e  mov     rax, cs:WPP_GLOBAL_Control
0x140049955  cmp     rax, r15
0x140049958  jz      loc_140049835
0x14004995e  mov     eax, [rax+2Ch]
0x140049961  test    dil, al
0x140049964  jz      loc_140049835
0x14004996a  lfence
0x14004996d  mov     r9, gs:188h
0x140049976  mov     edx, 8Eh
0x14004997b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049982  mov     r8, r12
0x140049985  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x14004998a  mov     rcx, [rcx+18h]
0x14004998e  call    WPP_SF_qD
0x140049993  jmp     loc_140049835
0x140049998  mov     rbx, [rbp+4Fh+P]
0x14004999c  test    rbx, rbx
0x14004999f  jnz     short loc_1400499F1
0x1400499a1  mov     r14d, 0C0000001h
0x1400499a7  mov     rax, cs:WPP_GLOBAL_Control
0x1400499ae  cmp     rax, r15
0x1400499b1  jz      loc_140049839
0x1400499b7  mov     eax, [rax+2Ch]
0x1400499ba  test    dil, al
0x1400499bd  jz      loc_140049839
0x1400499c3  mov     r9, gs:188h
0x1400499cc  mov     edx, 8Fh
0x1400499d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499d8  mov     r8, r12
0x1400499db  mov     dword ptr [rsp+0E0h+var_C0], 0C0000001h
0x1400499e3  mov     rcx, [rcx+18h]
0x1400499e7  call    WPP_SF_qD
0x1400499ec  jmp     loc_140049839
0x1400499f1  xor     dl, dl
0x1400499f3  mov     [rbp+4Fh+var_A0], dl
0x1400499f6  test    [rbx+1Bh], dil
0x1400499fa  jnz     short loc_140049A02
0x1400499fc  test    [rbx+1Ch], dil
0x140049a00  jz      short loc_140049A2B
0x140049a02  call    cs:__imp_IoGetCurrentProcess
0x140049a09  nop     dword ptr [rax+rax+00h]
0x140049a0e  mov     rcx, rax; Process
0x140049a11  lea     rdx, [rbp+4Fh+var_80]
0x140049a15  call    MpGetProcessContextByObject
0x140049a1a  mov     rsi, [rbp+4Fh+var_80]
0x140049a1e  mov     rcx, rsi
0x140049a21  call    MpIsRegistryHardeningExemptByContext
0x140049a26  mov     dl, al
0x140049a28  mov     [rbp+4Fh+var_A0], al
0x140049a2b  test    [rbx+1Bh], dil
0x140049a2f  jz      loc_140049ADB
0x140049a35  mov     [rbp+4Fh+var_90], edi
0x140049a38  test    rsi, rsi
0x140049a3b  jz      short loc_140049A9D
0x140049a3d  test    dl, dl
0x140049a3f  jnz     short loc_140049A9D
0x140049a41  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a48  cmp     rcx, r15
0x140049a4b  jz      short loc_140049A72
0x140049a4d  mov     eax, [rcx+2Ch]
0x140049a50  test    al, 2
0x140049a52  jz      short loc_140049A72
0x140049a54  mov     rax, [rsi+80h]
0x140049a5b  mov     edx, 90h
0x140049a60  mov     r9, [rbp+4Fh+Entry]
0x140049a64  mov     rcx, [rcx+18h]
0x140049a68  mov     [rsp+0E0h+var_C0], rax
0x140049a6d  call    WPP_SF_ZZ
0x140049a72  mov     r8, [rsi+80h]
0x140049a79  lea     rcx, aMiniFilterDeni_8; "[Mini-filter] Denied registry key set s"...
0x140049a80  mov     rdx, [rbp+4Fh+Entry]
0x140049a84  call    MpLogPrintfW
0x140049a89  mov     rax, [rbp+4Fh+var_70]
0x140049a8d  mov     [rax], dil
0x140049a90  mov     al, [rbx+1Ah]
0x140049a93  and     al, 0FDh
0x140049a95  or      al, dil
0x140049a98  mov     [rbx+1Ah], al
0x140049a9b  jmp     short loc_140049ADB
0x140049a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140049aa4  cmp     rcx, r15
0x140049aa7  jz      short loc_140049AD7
0x140049aa9  mov     eax, [rcx+2Ch]
0x140049aac  test    al, 4
0x140049aae  jz      short loc_140049AD7
0x140049ab0  test    rsi, rsi
0x140049ab3  jz      short loc_140049ABE
0x140049ab5  mov     rax, [rsi+80h]
0x140049abc  jmp     short loc_140049AC0
0x140049abe  xor     eax, eax
0x140049ac0  mov     r9, [rbp+4Fh+Entry]
0x140049ac4  mov     edx, 91h
0x140049ac9  mov     rcx, [rcx+18h]
0x140049acd  mov     [rsp+0E0h+var_C0], rax
0x140049ad2  call    WPP_SF_ZZ
0x140049ad7  and     byte ptr [rbx+1Bh], 0FEh
0x140049adb  mov     rdx, [rbp+4Fh+Entry]
0x140049adf  lea     rcx, [rbx+18h]
0x140049ae3  lea     r8, [rbp+4Fh+var_80]
0x140049ae7  call    MpRegTPAllowChange
0x140049aec  mov     rsi, [rbp+4Fh+var_80]
0x140049af0  test    al, al
0x140049af2  jnz     loc_140049B87
0x140049af8  mov     rax, cs:WPP_GLOBAL_Control
0x140049aff  cmp     rax, r15
0x140049b02  jz      short loc_140049B4A
0x140049b04  mov     eax, [rax+2Ch]
0x140049b07  test    al, 2
0x140049b09  jz      short loc_140049B4A
0x140049b0b  test    rsi, rsi
0x140049b0e  jz      short loc_140049B19
0x140049b10  mov     rax, [rsi+80h]
0x140049b17  jmp     short loc_140049B1B
0x140049b19  xor     eax, eax
0x140049b1b  mov     r9, gs:188h
0x140049b24  mov     edx, 92h
0x140049b29  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b30  mov     r8, r12
0x140049b33  mov     [rsp+0E0h+var_B8], rax
0x140049b38  mov     rax, [rbp+4Fh+Entry]
0x140049b3c  mov     [rsp+0E0h+var_C0], rax
0x140049b41  mov     rcx, [rcx+18h]
0x140049b45  call    WPP_SF_qZZ
0x140049b4a  test    rsi, rsi
0x140049b4d  jz      short loc_140049B58
0x140049b4f  mov     r8, [rsi+80h]
0x140049b56  jmp     short loc_140049B5B
0x140049b58  xor     r8d, r8d
0x140049b5b  mov     rdx, [rbp+4Fh+Entry]
0x140049b5f  lea     rcx, aDueToTamperPro; "Due to Tamper Protection, blocked set s"...
0x140049b66  call    MpLogPrintfW
0x140049b6b  mov     rdx, [rbp+4Fh+var_70]
0x140049b6f  mov     ecx, 2
0x140049b74  mov     [rbp+4Fh+var_90], ecx
0x140049b77  mov     [rdx], dil
0x140049b7a  mov     al, [rbx+1Ah]
  ... truncated ...
```
