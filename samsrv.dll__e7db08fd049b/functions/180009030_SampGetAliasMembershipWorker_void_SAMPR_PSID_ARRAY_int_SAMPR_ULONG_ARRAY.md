# SampGetAliasMembershipWorker(void *,_SAMPR_PSID_ARRAY *,int,_SAMPR_ULONG_ARRAY *)

- ea: `0x180009030`
- end: `0x180009610`
- name: `?SampGetAliasMembershipWorker@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@HPEAU_SAMPR_ULONG_ARRAY@@@Z`
- size: `1504`
- prototype: `__int64 __fastcall(void *, struct _SAMPR_PSID_ARRAY *, int, struct _SAMPR_ULONG_ARRAY *)`
- caller_count: `4`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180010d00`
- `0x180021550`
- `0x180022370`
- `0x18008b460`

## callees

- `0x1800022a0`
- `0x180007924`
- `0x180007b20`
- `0x180007ba0`
- `0x180009030`
- `0x180009620`
- `0x1800096c0`
- `0x18000ae10`
- `0x180016240`
- `0x180016540`
- `0x18001e130`
- `0x18001f950`
- `0x180021400`
- `0x180021460`
- `0x180021bec`
- `0x180022b30`
- `0x180027e24`
- `0x1800372ac`
- `0x180038f50`
- `0x1800ad5f0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800090c5`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800090c5`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800090a3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800090a3`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800090b5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800090b5`
- `ntdll!RtlValidSid` at `0x180009288`
- `ntdll!RtlValidSid` at `0x180009288`
- `ntdll!RtlEqualSid` at `0x180009380`
- `ntdll!RtlEqualSid` at `0x180009380`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009553`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009553`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009565`

## pseudocode

```c
__int64 __fastcall SampGetAliasMembershipWorker(
        unsigned int *a1,
        struct _SAMPR_PSID_ARRAY *a2,
        int a3,
        struct _SAMPR_ULONG_ARRAY *a4)
{
  unsigned int *v7; // rdi
  unsigned int v8; // r13d
  unsigned int v9; // r15d
  __int64 v10; // r14
  PVOID v11; // rbx
  __int64 v12; // rdx
  PUNICODE_STRING v13; // rcx
  int v14; // ebx
  char v15; // si
  unsigned int v16; // eax
  unsigned __int8 v17; // dl
  __int64 i; // rbx
  bool v19; // bl
  struct _SAMPR_ULONG_ARRAY *v20; // r14
  unsigned int AliasMembership; // eax
  PUNICODE_STRING v22; // rcx
  HLOCAL *v23; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  void **v27; // rcx
  PSID v28; // rsi
  __int64 v29; // rdx
  __int64 j; // rdi
  ULONG v31; // [rsp+30h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-50h] BYREF
  PSID Buffer[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int8 v34; // [rsp+90h] [rbp+8h] BYREF
  int v35; // [rsp+98h] [rbp+10h] BYREF
  struct _SAMPR_ULONG_ARRAY *v36; // [rsp+A8h] [rbp+20h]

  v36 = a4;
  v35 = 0;
  v34 = 0;
  hMem = 0;
  v7 = a1;
  v8 = SampClientRevisionFromHandle(a1);
  SampTraceEvent(1);
  v9 = *(_DWORD *)a2;
  v10 = *((_QWORD *)a2 + 1);
  if ( !SampValidateSIDArray(a2) )
  {
    v14 = -1073741811;
    goto LABEL_33;
  }
  Buffer[0] = v7;
  RtlAcquireSRWLockShared(&SampClientContextLock);
  v11 = RtlLookupElementGenericTableAvl(&SampClientContextTableAVL, Buffer);
  RtlReleaseSRWLockShared(&SampClientContextLock);
  v13 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 51, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v11 != 0);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    v14 = 0;
    if ( v7[6] != -294125688 )
      v14 = -1073741816;
  }
  else
  {
    v14 = -1073545211;
  }
  if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v13[3].Buffer, 15, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, (unsigned int)v14, v14);
  if ( v14 >= 0 )
  {
    if ( !v9 || !v10 )
    {
      *((_QWORD *)a4 + 1) = 0;
      *(_DWORD *)a4 = 0;
      goto LABEL_33;
    }
    if ( (v7[48] & 2) != 0 )
    {
      v26 = 1360LL * v7[50];
      if ( *((_BYTE *)SampDefinedDomains + v26 + 1296) )
      {
        if ( (unsigned __int8)SampDsIsRunning(v26, v12) )
        {
          v27 = (void **)*((_QWORD *)a2 + 1);
          Buffer[0] = 0;
          v14 = SampSplitSid(*v27, Buffer, &v31);
          if ( v14 < 0 )
            goto LABEL_33;
          v28 = Buffer[0];
          if ( RtlEqualSid(Buffer[0], *((PSID *)SampDefinedDomains + 171)) )
            v7 = *(unsigned int **)SampDefinedDomains;
          LocalFree(v28);
        }
        else
        {
          v7 = *(unsigned int **)SampDefinedDomains;
        }
      }
      if ( (v7[48] & 2) != 0 )
      {
        if ( !(unsigned __int8)SampDsIsRunning(v26, v12) )
        {
          v14 = -1073741146;
          goto LABEL_33;
        }
        if ( (v7[48] & 2) != 0 )
          v14 = SampResolveSids(*((void ***)a2 + 1), v9, 8u, (struct _DSNAME ***)&hMem);
      }
    }
    if ( v14 < 0 )
      goto LABEL_33;
    v15 = 0;
    if ( !a3 )
    {
      SampMaybeAcquireReadLock((struct _SAMP_OBJECT *)v7, 1u, &v34);
      v15 = 1;
    }
    v16 = SampLookupContextEx((__int64)v7, 0x80u, 0, 1, &v35);
    v14 = v16;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v16, v16);
    if ( v14 == -1073741790 )
    {
      if ( (unsigned __int8)SampCurrentThreadOwnsLock() && SampTransactionWithinDomainFn() )
        SampSetTransactionWithinDomain(0);
      v14 = SampLookupContext(v7, 512, 1, &v35);
    }
    if ( v14 < 0 )
      goto LABEL_31;
    for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
    {
      v25 = *(void **)(v10 + 8 * i);
      if ( !v25 || !RtlValidSid(v25) )
      {
        v14 = -1073741704;
        goto LABEL_30;
      }
    }
    v19 = *((_BYTE *)SampDefinedDomains + 1360 * (int)v7[50] + 1200) || SampServiceState == 1;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 45, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, v19);
    v20 = v36;
    if ( v19 )
    {
      AliasMembership = SampAlQueryAliasMembership(v7, a2, v36);
      v14 = AliasMembership;
      v22 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      {
        goto LABEL_28;
      }
      v29 = 10;
    }
    else
    {
      AliasMembership = SampAlSlowQueryAliasMembership((struct _DSNAME **)v7, a2, (struct _DSNAME **)hMem, v36);
      v14 = AliasMembership;
      v22 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      {
        goto LABEL_28;
      }
      v29 = 11;
    }
    WPP_SF_d(v22[3].Buffer, v29, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, AliasMembership);
LABEL_28:
    if ( v14 >= 0 && SampRODCCacheEnabled && *((_BYTE *)SampDefinedDomains + 1360 * v7[50] + 1296) )
      v14 = SampEvaluateRODCBuiltinRoles(a2, v20);
LABEL_30:
    SampDeReferenceContext2((struct _SAMP_OBJECT *)v7, v17);
LABEL_31:
    if ( v15 )
      SampMaybeReleaseReadLock(v34);
  }
LABEL_33:
  v23 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
    {
      if ( v23[j] )
      {
        LocalFree(v23[j]);
        v23 = (HLOCAL *)hMem;
      }
    }
    LocalFree(v23);
  }
  if ( v8 < 2 )
  {
    switch ( v14 )
    {
      case -1073741100:
        v14 = -1073741811;
        break;
      case -1073741099:
      case -1073741098:
      case -1073741097:
      case -1073741096:
      case -1073741095:
      case -1073741094:
      case -1073741093:
        v14 = -1073741445;
        break;
      case -1073741092:
        v14 = -1073741721;
        break;
      case -1073741081:
        v14 = -1073741756;
        break;
      default:
        break;
    }
  }
  SampTraceEvent(2);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 12, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, (unsigned int)v14, v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180009030  mov     r11, rsp
0x180009033  mov     [r11+18h], rbx
0x180009037  mov     [r11+20h], r9
0x18000903b  push    rbp
0x18000903c  push    rsi
0x18000903d  push    rdi
0x18000903e  push    r12
0x180009040  push    r13
0x180009042  push    r14
0x180009044  push    r15
0x180009046  sub     rsp, 50h
0x18000904a  xor     eax, eax
0x18000904c  mov     rsi, r9
0x18000904f  mov     [r11+10h], eax
0x180009053  mov     ebp, r8d
0x180009056  mov     [r11+8], al
0x18000905a  mov     r12, rdx
0x18000905d  mov     [r11-50h], rax
0x180009061  mov     rdi, rcx
0x180009064  call    ?SampClientRevisionFromHandle@@YAKPEAX@Z; SampClientRevisionFromHandle(void *)
0x180009069  xor     r8d, r8d
0x18000906c  mov     edx, 11h
0x180009071  mov     ecx, 1
0x180009076  mov     r13d, eax
0x180009079  call    SampTraceEvent
0x18000907e  mov     r15d, [r12]
0x180009082  mov     rcx, r12; struct _SAMPR_PSID_ARRAY *
0x180009085  mov     r14, [r12+8]
0x18000908a  call    ?SampValidateSIDArray@@YAEPEAU_SAMPR_PSID_ARRAY@@@Z; SampValidateSIDArray(_SAMPR_PSID_ARRAY *)
0x18000908f  test    al, al
0x180009091  jz      loc_1800092C4
0x180009097  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x18000909e  mov     [rsp+88h+Buffer], rdi
0x1800090a3  call    cs:__imp_RtlAcquireSRWLockShared
0x1800090a9  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800090ae  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x1800090b5  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800090bb  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x1800090c2  mov     rbx, rax
0x1800090c5  call    cs:__imp_RtlReleaseSRWLockShared
0x1800090cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d2  test    dword ptr [rcx+44h], 20000h
0x1800090d9  jnz     loc_1800092CE
0x1800090df  test    rbx, rbx
0x1800090e2  jz      loc_1800092F9
0x1800090e8  xor     ebx, ebx
0x1800090ea  cmp     dword ptr [rdi+18h], 0EE77FF88h
0x1800090f1  jnz     loc_180009303
0x1800090f7  test    dword ptr [rcx+44h], 20000h
0x1800090fe  jnz     loc_1800092A3
0x180009104  test    ebx, ebx
0x180009106  js      loc_180009227
0x18000910c  test    r15d, r15d
0x18000910f  jz      loc_18000952D
0x180009115  test    r14, r14
0x180009118  jz      loc_18000952D
0x18000911e  test    byte ptr [rdi+0C0h], 2
0x180009125  jnz     loc_18000930D
0x18000912b  test    ebx, ebx
0x18000912d  js      loc_180009227
0x180009133  xor     sil, sil
0x180009136  test    ebp, ebp
0x180009138  jz      loc_1800093E9
0x18000913e  lea     rax, [rsp+88h+arg_8]
0x180009146  mov     r9d, 1
0x18000914c  xor     r8d, r8d
0x18000914f  mov     [rsp+88h+var_68], rax
0x180009154  mov     edx, 80h
0x180009159  mov     rcx, rdi
0x18000915c  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x180009161  mov     ebx, eax
0x180009163  mov     rcx, cs:WPP_GLOBAL_Control
0x18000916a  test    dword ptr [rcx+44h], 20000h
0x180009171  jnz     loc_180009406
0x180009177  cmp     ebx, 0C0000022h
0x18000917d  jz      loc_180009427
0x180009183  test    ebx, ebx
0x180009185  js      loc_18000921E
0x18000918b  xor     ebx, ebx
0x18000918d  cmp     ebx, r15d
0x180009190  jb      loc_18000927F
0x180009196  movsxd  rax, dword ptr [rdi+0C8h]
0x18000919d  imul    rcx, rax, 550h
0x1800091a4  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800091ab  cmp     byte ptr [rcx+rax+4B0h], 0
0x1800091b3  jz      loc_180009462
0x1800091b9  mov     bl, 1
0x1800091bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091c2  test    dword ptr [rcx+44h], 20000h
0x1800091c9  jnz     loc_180009476
0x1800091cf  mov     r14, [rsp+88h+arg_18]
0x1800091d7  mov     rdx, r12; struct _SAMPR_PSID_ARRAY *
0x1800091da  mov     rcx, rdi; void *
0x1800091dd  test    bl, bl
0x1800091df  jnz     loc_180009494
0x1800091e5  mov     r8, [rsp+88h+hMem]; struct _DSNAME **
0x1800091ea  mov     r9, r14; struct _SAMPR_ULONG_ARRAY *
0x1800091ed  call    ?SampAlSlowQueryAliasMembership@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@PEAPEAU_DSNAME@@PEAU_SAMPR_ULONG_ARRAY@@@Z; SampAlSlowQueryAliasMembership(void *,_SAMPR_PSID_ARRAY *,_DSNAME * *,_SAMPR_ULONG_ARRAY *)
0x1800091f2  mov     ebx, eax
0x1800091f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091fb  test    byte ptr [rcx+44h], 20h
0x1800091ff  jnz     loc_1800094C0
0x180009205  test    ebx, ebx
0x180009207  js      short loc_180009216
0x180009209  cmp     cs:?SampRODCCacheEnabled@@3EA, 0; uchar SampRODCCacheEnabled
0x180009210  jnz     loc_1800094E7
0x180009216  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180009219  call    ?SampDeReferenceContext2@@YAJPEAU_SAMP_OBJECT@@E@Z; SampDeReferenceContext2(_SAMP_OBJECT *,uchar)
0x18000921e  test    sil, sil
0x180009221  jnz     loc_18000951B
0x180009227  mov     rcx, [rsp+88h+hMem]
0x18000922c  test    rcx, rcx
0x18000922f  jnz     loc_180009540
0x180009235  cmp     r13d, 2
0x180009239  jb      loc_180009570
0x18000923f  mov     r8d, ebx; jumptable 000000018000959A default case, cases -1073741091--1073741082
0x180009242  mov     edx, 11h
0x180009247  mov     ecx, 2
0x18000924c  call    SampTraceEvent
0x180009251  mov     rcx, cs:WPP_GLOBAL_Control
0x180009258  test    dword ptr [rcx+44h], 20000h
0x18000925f  jnz     loc_1800095C4
0x180009265  mov     eax, ebx
0x180009267  mov     rbx, [rsp+88h+arg_10]
0x18000926f  add     rsp, 50h
0x180009273  pop     r15
0x180009275  pop     r14
0x180009277  pop     r13
0x180009279  pop     r12
0x18000927b  pop     rdi
0x18000927c  pop     rsi
0x18000927d  pop     rbp
0x18000927e  retn
0x18000927f  mov     rcx, [r14+rbx*8]; Sid
0x180009283  test    rcx, rcx
0x180009286  jz      short loc_180009299
0x180009288  call    cs:__imp_RtlValidSid
0x18000928e  test    al, al
0x180009290  jz      short loc_180009299
0x180009292  inc     ebx
0x180009294  jmp     loc_18000918D
0x180009299  mov     ebx, 0C0000078h
0x18000929e  jmp     loc_180009216
0x1800092a3  mov     rcx, [rcx+38h]
0x1800092a7  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x1800092ae  mov     edx, 0Fh
0x1800092b3  mov     dword ptr [rsp+88h+var_68], ebx
0x1800092b7  mov     r9d, ebx
0x1800092ba  call    WPP_SF_Dd
0x1800092bf  jmp     loc_180009104
0x1800092c4  mov     ebx, 0C000000Dh
0x1800092c9  jmp     loc_180009227
0x1800092ce  mov     rcx, [rcx+38h]
0x1800092d2  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x1800092d9  xor     r9d, r9d
0x1800092dc  mov     edx, 33h ; '3'
0x1800092e1  test    rbx, rbx
0x1800092e4  setnz   r9b
0x1800092e8  call    WPP_SF_d
0x1800092ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092f4  jmp     loc_1800090DF
0x1800092f9  mov     ebx, 0C0030005h
0x1800092fe  jmp     loc_1800090F7
0x180009303  mov     ebx, 0C0000008h
0x180009308  jmp     loc_1800090F7
0x18000930d  mov     eax, [rdi+0C8h]
0x180009313  imul    rcx, rax, 550h
0x18000931a  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180009321  cmp     byte ptr [rcx+rax+510h], 0
0x180009329  jz      short loc_18000939D
0x18000932b  call    SampDsIsRunning
0x180009330  test    al, al
0x180009332  jnz     short loc_180009340
0x180009334  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18000933b  mov     rdi, [rax]
0x18000933e  jmp     short loc_18000939D
0x180009340  mov     rcx, [r12+8]
0x180009345  lea     r8, [rsp+88h+var_58]
0x18000934a  lea     rdx, [rsp+88h+Buffer]
0x18000934f  mov     [rsp+88h+Buffer], 0
0x180009358  mov     rcx, [rcx]; Src
0x18000935b  call    SampSplitSid
0x180009360  mov     ebx, eax
0x180009362  test    eax, eax
0x180009364  js      loc_180009227
0x18000936a  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180009371  mov     rsi, [rsp+88h+Buffer]
0x180009376  mov     rcx, rsi; Sid1
0x180009379  mov     rdx, [rdx+558h]; Sid2
0x180009380  call    cs:__imp_RtlEqualSid
0x180009386  test    al, al
0x180009388  jz      short loc_180009394
0x18000938a  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180009391  mov     rdi, [rax]
0x180009394  mov     rcx, rsi; hMem
0x180009397  call    cs:__imp_LocalFree
0x18000939d  test    byte ptr [rdi+0C0h], 2
0x1800093a4  jz      loc_18000912B
0x1800093aa  call    SampDsIsRunning
0x1800093af  test    al, al
0x1800093b1  jnz     short loc_1800093BD
0x1800093b3  mov     ebx, 0C00002A6h
0x1800093b8  jmp     loc_180009227
0x1800093bd  test    byte ptr [rdi+0C0h], 2
0x1800093c4  jz      loc_18000912B
0x1800093ca  mov     rcx, [r12+8]; void **
0x1800093cf  lea     r9, [rsp+88h+hMem]; struct _DSNAME ***
0x1800093d4  mov     r8d, 8; unsigned int
0x1800093da  mov     edx, r15d; unsigned int
0x1800093dd  call    ?SampResolveSids@@YAJPEAPEAXKKPEAPEAPEAU_DSNAME@@@Z; SampResolveSids(void * *,ulong,ulong,_DSNAME * * *)
0x1800093e2  mov     ebx, eax
0x1800093e4  jmp     loc_18000912B
0x1800093e9  lea     r8, [rsp+88h+arg_0]; unsigned __int8 *
0x1800093f1  mov     edx, 1; unsigned int
0x1800093f6  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800093f9  call    ?SampMaybeAcquireReadLock@@YAXPEAU_SAMP_OBJECT@@KPEAE@Z; SampMaybeAcquireReadLock(_SAMP_OBJECT *,ulong,uchar *)
0x1800093fe  mov     sil, 1
0x180009401  jmp     loc_18000913E
0x180009406  mov     rcx, [rcx+38h]
0x18000940a  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x180009411  mov     edx, 10h
0x180009416  mov     dword ptr [rsp+88h+var_68], ebx
0x18000941a  mov     r9d, ebx
0x18000941d  call    WPP_SF_Dd
0x180009422  jmp     loc_180009177
0x180009427  call    SampCurrentThreadOwnsLock
0x18000942c  test    al, al
0x18000942e  jz      short loc_180009440
0x180009430  call    ?SampTransactionWithinDomainFn@@YAEXZ; SampTransactionWithinDomainFn(void)
0x180009435  test    al, al
0x180009437  jz      short loc_180009440
0x180009439  xor     ecx, ecx
0x18000943b  call    SampSetTransactionWithinDomain
0x180009440  lea     r9, [rsp+88h+arg_8]
0x180009448  mov     edx, 200h
0x18000944d  mov     r8d, 1
0x180009453  mov     rcx, rdi
0x180009456  call    SampLookupContext
0x18000945b  mov     ebx, eax
0x18000945d  jmp     loc_180009183
0x180009462  cmp     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 1; _SAMP_SERVICE_STATE SampServiceState
0x180009469  jz      loc_1800091B9
0x18000946f  xor     bl, bl
0x180009471  jmp     loc_1800091BB
0x180009476  mov     rcx, [rcx+38h]
0x18000947a  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180009481  movzx   r9d, bl
0x180009485  mov     edx, 2Dh ; '-'
0x18000948a  call    WPP_SF_d
0x18000948f  jmp     loc_1800091CF
0x180009494  mov     r8, r14; struct _SAMPR_ULONG_ARRAY *
0x180009497  call    ?SampAlQueryAliasMembership@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z; SampAlQueryAliasMembership(void *,_SAMPR_PSID_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x18000949c  mov     ebx, eax
0x18000949e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094a5  test    byte ptr [rcx+44h], 20h
0x1800094a9  jz      loc_180009205
0x1800094af  cmp     byte ptr [rcx+41h], 4
0x1800094b3  jb      loc_180009205
0x1800094b9  mov     edx, 0Ah
0x1800094be  jmp     short loc_1800094CF
0x1800094c0  cmp     byte ptr [rcx+41h], 4
0x1800094c4  jb      loc_180009205
0x1800094ca  mov     edx, 0Bh
0x1800094cf  mov     rcx, [rcx+38h]
0x1800094d3  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x1800094da  mov     r9d, eax
0x1800094dd  call    WPP_SF_d
0x1800094e2  jmp     loc_180009205
0x1800094e7  mov     eax, [rdi+0C8h]
0x1800094ed  imul    rcx, rax, 550h
0x1800094f4  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800094fb  cmp     byte ptr [rcx+rax+510h], 0
0x180009503  jz      loc_180009216
0x180009509  mov     rdx, r14; struct _SAMPR_ULONG_ARRAY *
0x18000950c  mov     rcx, r12; struct _SAMPR_PSID_ARRAY *
0x18000950f  call    ?SampEvaluateRODCBuiltinRoles@@YAJPEAU_SAMPR_PSID_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z; SampEvaluateRODCBuiltinRoles(_SAMPR_PSID_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x180009514  mov     ebx, eax
0x180009516  jmp     loc_180009216
0x18000951b  movzx   ecx, [rsp+88h+arg_0]; unsigned __int8
0x180009523  call    ?SampMaybeReleaseReadLock@@YAXE@Z; SampMaybeReleaseReadLock(uchar)
0x180009528  jmp     loc_180009227
0x18000952d  mov     qword ptr [rsi+8], 0
0x180009535  mov     dword ptr [rsi], 0
0x18000953b  jmp     loc_180009227
0x180009540  xor     edi, edi
0x180009542  test    r15d, r15d
0x180009545  jz      short loc_180009565
0x180009547  mov     rdx, [rcx+rdi*8]
0x18000954b  test    rdx, rdx
0x18000954e  jz      short loc_18000955E
0x180009550  mov     rcx, rdx; hMem
0x180009553  call    cs:__imp_LocalFree
0x180009559  mov     rcx, [rsp+88h+hMem]; hMem
0x18000955e  inc     edi
0x180009560  cmp     edi, r15d
0x180009563  jb      short loc_180009547
0x180009565  call    cs:__imp_LocalFree
0x18000956b  jmp     loc_180009235
0x180009570  lea     eax, [rbx+3FFFFD2Ch]; switch 20 cases
0x180009576  cmp     eax, 13h
  ... truncated ...
```
