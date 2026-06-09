# SampEnumerateAccountNamesCommon(void *,_SAMP_OBJECT_TYPE,ulong *,ulong,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *)

- ea: `0x180020f98`
- end: `0x1800213be`
- name: `?SampEnumerateAccountNamesCommon@@YAJPEAXW4_SAMP_OBJECT_TYPE@@PEAKKPEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK2@Z`
- size: `1062`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180058a50`
- `0x180058bb0`

## callees

- `0x180003760`
- `0x180003860`
- `0x180003d40`
- `0x180008590`
- `0x1800096c0`
- `0x180011810`
- `0x180012a28`
- `0x180020f98`
- `0x180027e24`
- `0x1800372ac`
- `0x18005ed6c`
- `0x18005f8ec`
- `0x180076d70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002131d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002132c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002131d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002132c`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUpdateDsPerfStats` at `0x18002102d`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUpdateDsPerfStats` at `0x18002102d`

## pseudocode

```c
__int64 __fastcall SampEnumerateAccountNamesCommon(
        __int64 a1,
        unsigned int a2,
        unsigned int *a3,
        int a4,
        HLOCAL *a5,
        unsigned int a6,
        int a7,
        _DWORD *a8)
{
  HLOCAL v8; // rsi
  unsigned __int8 v13; // bl
  PUNICODE_STRING v14; // rcx
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // eax
  bool v19; // zf
  char v20; // r14
  int inited; // eax
  HLOCAL *v22; // r12
  _DWORD *v23; // rsi
  int v24; // r13d
  struct _PSAMP_DEFINED_DOMAINS *v25; // r8
  int v26; // eax
  int updated; // eax
  char v28; // r12
  int v30; // [rsp+48h] [rbp-28h]
  unsigned __int8 v31; // [rsp+50h] [rbp-20h] BYREF
  char v32; // [rsp+51h] [rbp-1Fh]
  unsigned int v33; // [rsp+54h] [rbp-1Ch] BYREF
  unsigned int v34; // [rsp+58h] [rbp-18h] BYREF
  int v35; // [rsp+5Ch] [rbp-14h] BYREF
  HLOCAL v36; // [rsp+60h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-8h] BYREF
  unsigned __int8 v38; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int *v39; // [rsp+C0h] [rbp+50h]
  int v40; // [rsp+C8h] [rbp+58h]

  v40 = a4;
  v39 = a3;
  v8 = 0;
  v35 = 0;
  if ( !SampUseDsData || (v13 = 1, SampDsStopped) )
    v13 = 0;
  v14 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v13);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    if ( (int)SampShouldCallNtdsaApiSet() >= 0 )
      NtdsaExtUpdateDsPerfStats(7, 1);
    v14 = WPP_GLOBAL_Control;
  }
  if ( a2 - 2 > 2 )
  {
    v15 = -1073741811;
    if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v16 = 10;
      v17 = 3221225485LL;
LABEL_56:
      WPP_SF_Dd(v14[3].Buffer, v16, WPP_35556bb4c1df35c2a329f76602f997a4_Traceguids, v17, v15);
      return (unsigned int)v15;
    }
    return (unsigned int)v15;
  }
  SampAcquireReadLock();
  v18 = SampLookupContextEx(a1, 0x100u, 0, 1, &v35);
  v15 = v18;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v18, v18);
  if ( v15 >= 0 )
  {
    v19 = (*(_BYTE *)(a1 + 192) & 2) == 0;
    v32 = 1;
    if ( !v19 )
    {
      SampReleaseReadLock();
      v32 = 0;
    }
    v20 = (*(_BYTE *)(a1 + 20) & 0x20) != 0;
    v36 = 0;
    v19 = (*(_BYTE *)(a1 + 192) & 2) == 0;
    v31 = 0;
    v38 = 0;
    hMem = 0;
    if ( v19 )
    {
      if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
      {
        v28 = 0;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
      }
      else
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
        SampAcquireReadLock();
        v28 = 1;
        SampSetTransactionDomain(*(unsigned int *)(a1 + 200));
      }
      v15 = SampEnumerateAccountNamesRegistry(a2, a3, v40, a5, a6, a7, a8, v20);
      if ( v28 )
        SampReleaseReadLock();
    }
    else
    {
      v33 = *a3;
      v34 = 0;
      if ( a2 == 4 )
      {
        inited = SampInitSearchParametersFromEnumerationCache(
                   (struct _SAMP_OBJECT *)a1,
                   a3,
                   (struct _SAMP_ENUM_CONTEXT_TABLE_ENTRY **)&hMem,
                   &v38,
                   &v33,
                   &v34,
                   &v36,
                   &v31);
        v8 = v36;
        v15 = inited;
        if ( inited < 0 )
        {
LABEL_44:
          if ( v38 && hMem )
            LocalFree(hMem);
          goto LABEL_47;
        }
      }
      if ( a4 )
      {
        v15 = -1073741811;
        goto LABEL_44;
      }
      v22 = a5;
      v23 = a8;
      v24 = a7;
      do
      {
        v25 = SampDefinedDomains;
        LOBYTE(v30) = v20;
        LOBYTE(v25) = *((_BYTE *)SampDefinedDomains + 1360 * *(unsigned int *)(a1 + 200) + 1296);
        v26 = SampExtEnumerateAccountNamesDs(*(_QWORD *)(a1 + 176), a2, v25, &v33, &v34, v22, a6, v24, v23, v30);
        v15 = v26;
        if ( *v23 )
          break;
        if ( v26 == 261 && *v22 )
        {
          LocalFree(*v22);
          *v22 = 0;
        }
      }
      while ( !*v23 && v15 == 261 );
      v8 = v36;
      if ( a2 == 4 )
      {
        updated = SampUpdateSearchParametersInEnumerationCache(
                    (struct _SAMP_OBJECT *)a1,
                    v39,
                    v15,
                    (struct _SAMP_ENUM_CONTEXT_TABLE_ENTRY **)&hMem,
                    &v33,
                    &v34,
                    v36);
        if ( v15 < 0 )
          goto LABEL_44;
        if ( updated < 0 )
        {
          v15 = updated;
          goto LABEL_44;
        }
LABEL_47:
        if ( v31 )
          LocalFree(v8);
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            13,
            WPP_35556bb4c1df35c2a329f76602f997a4_Traceguids,
            (unsigned int)v15,
            v15);
        if ( !v32 )
          SampAcquireReadLock();
        SampDeReferenceContext(a1, 0);
        goto LABEL_54;
      }
      *v39 = v33;
    }
    if ( v15 < 0 )
      goto LABEL_44;
    goto LABEL_47;
  }
LABEL_54:
  SampReleaseReadLock();
  v14 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v16 = 11;
    v17 = (unsigned int)v15;
    goto LABEL_56;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180020f98  mov     [rsp-38h+arg_0], rbx
0x180020f9d  mov     [rsp-38h+arg_18], r9d
0x180020fa2  mov     [rsp-38h+arg_10], r8
0x180020fa7  push    rbp
0x180020fa8  push    rsi
0x180020fa9  push    rdi
0x180020faa  push    r12
0x180020fac  push    r13
0x180020fae  push    r14
0x180020fb0  push    r15
0x180020fb2  mov     rbp, rsp
0x180020fb5  sub     rsp, 70h
0x180020fb9  xor     esi, esi
0x180020fbb  mov     r12d, r9d
0x180020fbe  cmp     cs:?SampUseDsData@@3EA, sil; uchar SampUseDsData
0x180020fc5  mov     r13, r8
0x180020fc8  mov     r15d, edx
0x180020fcb  mov     [rbp+var_14], esi
0x180020fce  mov     rdi, rcx
0x180020fd1  lea     r14d, [rsi+1]
0x180020fd5  jz      short loc_180020FE3
0x180020fd7  cmp     cs:?SampDsStopped@@3EA, sil; uchar SampDsStopped
0x180020fde  mov     bl, r14b
0x180020fe1  jz      short loc_180020FE6
0x180020fe3  mov     bl, sil
0x180020fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fed  test    dword ptr [rcx+44h], 20000h
0x180020ff4  jz      short loc_180021016
0x180020ff6  mov     rcx, [rcx+38h]
0x180020ffa  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180021001  movzx   r9d, bl
0x180021005  mov     edx, 4Ah ; 'J'
0x18002100a  call    WPP_SF_d
0x18002100f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021016  test    bl, bl
0x180021018  jz      short loc_18002103A
0x18002101a  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18002101f  test    eax, eax
0x180021021  js      short loc_180021033
0x180021023  xor     r8d, r8d
0x180021026  mov     edx, r14d
0x180021029  lea     ecx, [r8+7]
0x18002102d  call    cs:__imp_NtdsaExtUpdateDsPerfStats
0x180021033  mov     rcx, cs:WPP_GLOBAL_Control
0x18002103a  lea     eax, [r15-2]
0x18002103e  cmp     eax, 2
0x180021041  jbe     short loc_180021065
0x180021043  test    dword ptr [rcx+44h], 20000h
0x18002104a  mov     ebx, 0C000000Dh
0x18002104f  jz      loc_1800213A4
0x180021055  mov     edx, 0Ah
0x18002105a  mov     r9d, 0C000000Dh
0x180021060  jmp     loc_180021390
0x180021065  call    SampAcquireReadLock
0x18002106a  lea     rax, [rbp+var_14]
0x18002106e  mov     r9d, r14d
0x180021071  xor     r8d, r8d
0x180021074  mov     [rsp+70h+var_50], rax
0x180021079  mov     edx, 100h
0x18002107e  mov     rcx, rdi
0x180021081  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x180021086  mov     ebx, eax
0x180021088  mov     rcx, cs:WPP_GLOBAL_Control
0x18002108f  test    dword ptr [rcx+44h], 20000h
0x180021096  jz      short loc_1800210B4
0x180021098  mov     rcx, [rcx+38h]
0x18002109c  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x1800210a3  mov     edx, 10h
0x1800210a8  mov     dword ptr [rsp+70h+var_50], eax
0x1800210ac  mov     r9d, eax
0x1800210af  call    WPP_SF_Dd
0x1800210b4  test    ebx, ebx
0x1800210b6  js      loc_180021373
0x1800210bc  test    byte ptr [rdi+0C0h], 2
0x1800210c3  mov     [rbp+var_1F], r14b
0x1800210c7  jz      short loc_1800210D2
0x1800210c9  call    SampReleaseReadLock
0x1800210ce  mov     [rbp+var_1F], sil
0x1800210d2  mov     r14b, [rdi+14h]
0x1800210d6  shr     r14b, 5
0x1800210da  and     r14b, 1
0x1800210de  mov     [rbp+var_10], rsi
0x1800210e2  test    byte ptr [rdi+0C0h], 2
0x1800210e9  mov     [rbp+var_20], sil
0x1800210ed  mov     [rbp+arg_8], sil
0x1800210f1  mov     [rbp+hMem], rsi
0x1800210f5  jz      loc_18002124E
0x1800210fb  mov     eax, [r13+0]
0x1800210ff  mov     [rbp+var_1C], eax
0x180021102  mov     [rbp+var_18], esi
0x180021105  cmp     r15d, 4
0x180021109  jnz     short loc_180021150
0x18002110b  lea     rax, [rbp+var_20]
0x18002110f  mov     rdx, r13; unsigned int *
0x180021112  mov     [rsp+70h+var_38], rax; unsigned __int8 *
0x180021117  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x18002111b  lea     rax, [rbp+var_10]
0x18002111f  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180021122  mov     [rsp+70h+var_40], rax; void **
0x180021127  lea     r8, [rbp+hMem]; struct _SAMP_ENUM_CONTEXT_TABLE_ENTRY **
0x18002112b  lea     rax, [rbp+var_18]
0x18002112f  mov     [rsp+70h+var_48], rax; unsigned int *
0x180021134  lea     rax, [rbp+var_1C]
0x180021138  mov     [rsp+70h+var_50], rax; unsigned int *
0x18002113d  call    ?SampInitSearchParametersFromEnumerationCache@@YAJPEAU_SAMP_OBJECT@@PEAKPEAPEAU_SAMP_ENUM_CONTEXT_TABLE_ENTRY@@PEAE11PEAPEAX3@Z; SampInitSearchParametersFromEnumerationCache(_SAMP_OBJECT *,ulong *,_SAMP_ENUM_CONTEXT_TABLE_ENTRY * *,uchar *,ulong *,ulong *,void * *,uchar *)
0x180021142  mov     rsi, [rbp+var_10]
0x180021146  mov     ebx, eax
0x180021148  test    eax, eax
0x18002114a  js      loc_18002130E
0x180021150  test    r12d, r12d
0x180021153  jz      short loc_18002115F
0x180021155  mov     ebx, 0C000000Dh
0x18002115a  jmp     loc_18002130E
0x18002115f  mov     r12, [rbp+arg_20]
0x180021163  mov     rsi, [rbp+arg_38]
0x180021167  mov     r13d, [rbp+arg_30]
0x18002116b  mov     eax, [rdi+0C8h]
0x180021171  lea     r9, [rbp+var_1C]
0x180021175  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18002117c  mov     edx, r15d
0x18002117f  imul    rcx, rax, 550h
0x180021186  mov     eax, [rbp+arg_28]
0x180021189  mov     [rsp+70h+var_28], r14b
0x18002118e  mov     [rsp+70h+var_30], rsi
0x180021193  mov     dword ptr [rsp+70h+var_38], r13d
0x180021198  mov     r8b, [rcx+r8+510h]
0x1800211a0  mov     rcx, [rdi+0B0h]
0x1800211a7  mov     dword ptr [rsp+70h+var_40], eax
0x1800211ab  lea     rax, [rbp+var_18]
0x1800211af  mov     [rsp+70h+var_48], r12
0x1800211b4  mov     [rsp+70h+var_50], rax
0x1800211b9  call    ?SampExtEnumerateAccountNamesDs@@YAJPEAU_DSNAME@@W4_SAMP_OBJECT_TYPE@@EPEAK2PEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK2E@Z; SampExtEnumerateAccountNamesDs(_DSNAME *,_SAMP_OBJECT_TYPE,uchar,ulong *,ulong *,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *,uchar)
0x1800211be  cmp     dword ptr [rsi], 0
0x1800211c1  mov     ebx, eax
0x1800211c3  jnz     short loc_1800211F4
0x1800211c5  cmp     eax, 105h
0x1800211ca  jnz     short loc_1800211E3
0x1800211cc  mov     rcx, [r12]; hMem
0x1800211d0  test    rcx, rcx
0x1800211d3  jz      short loc_1800211E3
0x1800211d5  call    cs:__imp_LocalFree
0x1800211db  mov     qword ptr [r12], 0
0x1800211e3  cmp     dword ptr [rsi], 0
0x1800211e6  jnz     short loc_1800211F4
0x1800211e8  cmp     ebx, 105h
0x1800211ee  jz      loc_18002116B
0x1800211f4  mov     rsi, [rbp+var_10]
0x1800211f8  mov     r13, [rbp+arg_10]
0x1800211fc  cmp     r15d, 4
0x180021200  jnz     short loc_180021242
0x180021202  lea     rax, [rbp+var_18]
0x180021206  mov     [rsp+70h+var_40], rsi; void *
0x18002120b  mov     [rsp+70h+var_48], rax; unsigned int *
0x180021210  lea     r9, [rbp+hMem]; struct _SAMP_ENUM_CONTEXT_TABLE_ENTRY **
0x180021214  lea     rax, [rbp+var_1C]
0x180021218  mov     r8d, ebx; int
0x18002121b  mov     rdx, r13; unsigned int *
0x18002121e  mov     [rsp+70h+var_50], rax; unsigned int *
0x180021223  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180021226  call    ?SampUpdateSearchParametersInEnumerationCache@@YAJPEAU_SAMP_OBJECT@@PEAKJPEAPEAU_SAMP_ENUM_CONTEXT_TABLE_ENTRY@@11PEAX@Z; SampUpdateSearchParametersInEnumerationCache(_SAMP_OBJECT *,ulong *,long,_SAMP_ENUM_CONTEXT_TABLE_ENTRY * *,ulong *,ulong *,void *)
0x18002122b  test    ebx, ebx
0x18002122d  js      loc_18002130E
0x180021233  test    eax, eax
0x180021235  jns     loc_180021323
0x18002123b  mov     ebx, eax
0x18002123d  jmp     loc_18002130E
0x180021242  mov     eax, [rbp+var_1C]
0x180021245  mov     [r13+0], eax
0x180021249  jmp     loc_18002130A
0x18002124e  mov     rax, gs:30h
0x180021257  mov     rcx, [rax+48h]
0x18002125b  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rcx; _RTL_CRITICAL_SECTION SampLock ...
0x180021262  jnz     short loc_180021294
0x180021264  xor     r12b, r12b
0x180021267  mov     rcx, cs:WPP_GLOBAL_Control
0x18002126e  test    dword ptr [rcx+44h], 20000h
0x180021275  jz      short loc_1800212CF
0x180021277  mov     rcx, [rcx+38h]
0x18002127b  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180021282  mov     edx, 0D1h
0x180021287  mov     r9d, 1
0x18002128d  call    WPP_SF_d
0x180021292  jmp     short loc_1800212CF
0x180021294  mov     rcx, cs:WPP_GLOBAL_Control
0x18002129b  test    dword ptr [rcx+44h], 20000h
0x1800212a2  jz      short loc_1800212BC
0x1800212a4  mov     rcx, [rcx+38h]
0x1800212a8  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800212af  mov     edx, 0D2h
0x1800212b4  xor     r9d, r9d
0x1800212b7  call    WPP_SF_d
0x1800212bc  call    SampAcquireReadLock
0x1800212c1  mov     ecx, [rdi+0C8h]
0x1800212c7  mov     r12b, 1
0x1800212ca  call    SampSetTransactionDomain
0x1800212cf  mov     rax, [rbp+arg_38]
0x1800212d3  mov     rdx, r13
0x1800212d6  mov     r9, [rbp+arg_20]
0x1800212da  mov     ecx, r15d
0x1800212dd  mov     r8d, [rbp+arg_18]
0x1800212e1  mov     byte ptr [rsp+70h+var_38], r14b
0x1800212e6  mov     [rsp+70h+var_40], rax
0x1800212eb  mov     eax, [rbp+arg_30]
0x1800212ee  mov     dword ptr [rsp+70h+var_48], eax
0x1800212f2  mov     eax, [rbp+arg_28]
0x1800212f5  mov     dword ptr [rsp+70h+var_50], eax
0x1800212f9  call    ?SampEnumerateAccountNamesRegistry@@YAJW4_SAMP_OBJECT_TYPE@@PEAKKPEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK1E@Z; SampEnumerateAccountNamesRegistry(_SAMP_OBJECT_TYPE,ulong *,ulong,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *,uchar)
0x1800212fe  mov     ebx, eax
0x180021300  test    r12b, r12b
0x180021303  jz      short loc_18002130A
0x180021305  call    SampReleaseReadLock
0x18002130a  test    ebx, ebx
0x18002130c  jns     short loc_180021323
0x18002130e  cmp     [rbp+arg_8], 0
0x180021312  jz      short loc_180021323
0x180021314  mov     rcx, [rbp+hMem]; hMem
0x180021318  test    rcx, rcx
0x18002131b  jz      short loc_180021323
0x18002131d  call    cs:__imp_LocalFree
0x180021323  cmp     [rbp+var_20], 0
0x180021327  jz      short loc_180021332
0x180021329  mov     rcx, rsi; hMem
0x18002132c  call    cs:__imp_LocalFree
0x180021332  mov     rcx, cs:WPP_GLOBAL_Control
0x180021339  test    dword ptr [rcx+44h], 20000h
0x180021340  jz      short loc_18002135E
0x180021342  mov     rcx, [rcx+38h]
0x180021346  lea     r8, WPP_35556bb4c1df35c2a329f76602f997a4_Traceguids
0x18002134d  mov     edx, 0Dh
0x180021352  mov     dword ptr [rsp+70h+var_50], ebx
0x180021356  mov     r9d, ebx
0x180021359  call    WPP_SF_Dd
0x18002135e  cmp     [rbp+var_1F], 0
0x180021362  jnz     short loc_180021369
0x180021364  call    SampAcquireReadLock
0x180021369  xor     edx, edx
0x18002136b  mov     rcx, rdi
0x18002136e  call    SampDeReferenceContext
0x180021373  call    SampReleaseReadLock
0x180021378  mov     rcx, cs:WPP_GLOBAL_Control
0x18002137f  test    dword ptr [rcx+44h], 20000h
0x180021386  jz      short loc_1800213A4
0x180021388  mov     edx, 0Bh
0x18002138d  mov     r9d, ebx
0x180021390  mov     rcx, [rcx+38h]
0x180021394  lea     r8, WPP_35556bb4c1df35c2a329f76602f997a4_Traceguids
0x18002139b  mov     dword ptr [rsp+70h+var_50], ebx
0x18002139f  call    WPP_SF_Dd
0x1800213a4  mov     eax, ebx
0x1800213a6  mov     rbx, [rsp+70h+arg_0]
0x1800213ae  add     rsp, 70h
0x1800213b2  pop     r15
0x1800213b4  pop     r14
0x1800213b6  pop     r13
0x1800213b8  pop     r12
0x1800213ba  pop     rdi
0x1800213bb  pop     rsi
0x1800213bc  pop     rbp
0x1800213bd  retn
```
