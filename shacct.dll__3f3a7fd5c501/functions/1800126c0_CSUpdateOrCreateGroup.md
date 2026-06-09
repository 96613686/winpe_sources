# CSUpdateOrCreateGroup

- ea: `0x1800126c0`
- end: `0x180012ac4`
- name: `CSUpdateOrCreateGroup`
- size: `1028`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int16 **, unsigned int, int, unsigned int, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fe00`
- `0x180014d90`

## callees

- `0x180001e70`
- `0x180003660`
- `0x18000f64c`
- `0x18000f918`
- `0x1800126c0`
- `0x180012f58`
- `0x180013240`
- `0x1800132b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a37`
- `SAMLIB!SamLookupNamesInDomain` at `0x18001278b`
- `SAMLIB!SamLookupNamesInDomain` at `0x18001278b`
- `SAMLIB!SamSetInformationAlias` at `0x180012907`
- `SAMLIB!SamSetInformationAlias` at `0x180012920`
- `SAMLIB!SamSetInformationAlias` at `0x18001298e`
- `SAMLIB!SamSetInformationAlias` at `0x180012907`
- `SAMLIB!SamSetInformationAlias` at `0x180012920`
- `SAMLIB!SamSetInformationAlias` at `0x18001298e`
- `SAMLIB!SamCreateAliasInDomain` at `0x18001286a`
- `SAMLIB!SamCreateAliasInDomain` at `0x18001286a`
- `SAMLIB!SamCloseHandle` at `0x180012a8c`
- `SAMLIB!SamCloseHandle` at `0x180012a96`
- `SAMLIB!SamCloseHandle` at `0x180012aa0`
- `SAMLIB!SamCloseHandle` at `0x180012a8c`
- `SAMLIB!SamCloseHandle` at `0x180012a96`
- `SAMLIB!SamCloseHandle` at `0x180012aa0`
- `SAMLIB!SamOpenAlias` at `0x1800127c4`
- `SAMLIB!SamOpenAlias` at `0x1800127c4`
- `SAMLIB!SamFreeMemory` at `0x18001280a`
- `SAMLIB!SamFreeMemory` at `0x180012814`
- `SAMLIB!SamFreeMemory` at `0x18001280a`
- `SAMLIB!SamFreeMemory` at `0x180012814`

## pseudocode

```c
__int64 __fastcall CSUpdateOrCreateGroup(
        void *a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        char a9)
{
  int v13; // ebx
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // r8d
  int v18; // eax
  _QWORD *v19; // rcx
  int v20; // edx
  __int128 v21; // xmm1
  int v22; // ebx
  int v23; // r8d
  int v24; // ebx
  _QWORD *v25; // rcx
  int v26; // edx
  int v27; // ebx
  int v28; // r8d
  int v29; // eax
  int v30; // r8d
  int v31; // eax
  int v32; // r8d
  void *v34; // [rsp+30h] [rbp-50h] BYREF
  void *v35; // [rsp+38h] [rbp-48h] BYREF
  unsigned int *v36; // [rsp+40h] [rbp-40h] BYREF
  _DWORD *v37; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-30h] BYREF
  void *v39; // [rsp+60h] [rbp-20h] BYREF
  __int128 v40; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v41; // [rsp+B8h] [rbp+38h] BYREF

  if ( !a2 )
    return (unsigned int)-2147467261;
  v39 = 0;
  v35 = 0;
  v13 = SamHandleForDomain(a1, 0xF003Fu, 0x25Eu, &v39, &v35);
  if ( v13 >= 0 || (v13 = SamHandleForDomain(a1, 0xF003Fu, 0x244u, &v39, &v35), v13 >= 0) )
  {
    v34 = 0;
    v41 = 0;
    v36 = 0;
    v37 = 0;
    v14 = SamLookupNamesInDomain(v35, 1, a2, &v36, &v37);
    if ( v14 >= 0 )
    {
      if ( *v37 == 4 )
      {
        v16 = SamOpenAlias(v35, 131095, *v36, &v34);
        if ( v16 >= 0 )
        {
          v41 = *v36;
        }
        else
        {
          v13 = v16 | 0x10000000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, v17, a2, v16);
        }
      }
      else
      {
        v13 = -805306230;
      }
      SamFreeMemory(v37);
      SamFreeMemory(v36);
      goto LABEL_26;
    }
    if ( v14 == -1073741709 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, v15, a2);
      v18 = SamCreateAliasInDomain(v35, a2, 983071, &v34, &v41);
      if ( v18 >= 0
        || (v13 = v18 | 0x10000000, v19 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control)
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_26:
        if ( v13 < 0 || !a3 && !a4 )
          goto LABEL_57;
        if ( (a9 & 8) == 0 )
          goto LABEL_40;
        v21 = *(_OWORD *)((char *)a3 + 24);
        *(_OWORD *)pv = *a3;
        v40 = v21;
        v22 = SamSetInformationAlias(v34, 2, pv);
        if ( v22 < 0 )
        {
          v13 = v22 | 0x10000000;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
LABEL_39:
            if ( v13 >= 0 )
            {
LABEL_40:
              if ( (a9 & 0x10) == 0 )
                goto LABEL_63;
              v27 = SamSetInformationAlias(v34, 5, a4);
              if ( v27 >= 0 )
                goto LABEL_63;
              v13 = v27 | 0x10000000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, v28, a2, v13);
              }
              if ( v13 >= 0 )
              {
LABEL_63:
                if ( (a9 & 1) == 0 )
                  goto LABEL_53;
                pv[0] = 0;
                v13 = CSGetAccountSIDByRID(a1, v41, pv);
                if ( v13 >= 0 )
                {
                  v29 = CSSetAccountRights(pv[0], a8);
                  v13 = v29;
                  if ( v29 < 0
                    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_DZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v30, a8, a2, v29);
                  }
                  CoTaskMemFree(pv[0]);
                  if ( v13 >= 0 )
                  {
LABEL_53:
                    v31 = CSUpdateGroupMembers(v34, (const unsigned __int16 **)a5, a6, a7);
                    v13 = v31;
                    if ( v31 < 0
                      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, v32, a2, v31);
                    }
                  }
                }
              }
            }
LABEL_57:
            if ( v34 )
              SamCloseHandle(v34);
            SamCloseHandle(v35);
            SamCloseHandle(v39);
            return (unsigned int)v13;
          }
          v26 = 86;
        }
        else
        {
          v24 = SamSetInformationAlias(v34, 3, &v40);
          if ( v24 >= 0 )
            goto LABEL_40;
          v13 = v24 | 0x10000000;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_39;
          v26 = 85;
        }
        WPP_SF_ZD(v25[2], v26, v23, a2, v13);
        goto LABEL_39;
      }
      v20 = 83;
    }
    else
    {
      v13 = v14 | 0x10000000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_26;
      v20 = 84;
    }
    WPP_SF_ZD(v19[2], v20, v15, a2, v13);
    goto LABEL_26;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800126c0  mov     [rsp-28h+arg_0], rbx
0x1800126c5  mov     [rsp-28h+arg_10], rsi
0x1800126ca  push    rbp
0x1800126cb  push    rdi
0x1800126cc  push    r12
0x1800126ce  push    r13
0x1800126d0  push    r15
0x1800126d2  mov     rbp, rsp
0x1800126d5  sub     rsp, 80h
0x1800126dc  mov     r13, r9
0x1800126df  mov     r15, r8
0x1800126e2  mov     rdi, rdx
0x1800126e5  mov     r12, rcx
0x1800126e8  test    rdx, rdx
0x1800126eb  jnz     short loc_1800126F7
0x1800126ed  mov     ebx, 80004003h
0x1800126f2  jmp     loc_180012AA6
0x1800126f7  lea     rax, [rbp+var_48]
0x1800126fb  mov     [rbp+var_20], 0
0x180012703  mov     esi, 0F003Fh
0x180012708  mov     [rbp+var_48], 0
0x180012710  mov     edx, esi; unsigned int
0x180012712  mov     [rsp+80h+var_60], rax; void **
0x180012717  lea     r9, [rbp+var_20]; void **
0x18001271b  mov     r8d, 25Eh; unsigned int
0x180012721  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180012726  mov     ebx, eax
0x180012728  test    eax, eax
0x18001272a  jns     short loc_180012753
0x18001272c  lea     rax, [rbp+var_48]
0x180012730  mov     r8d, 244h; unsigned int
0x180012736  lea     r9, [rbp+var_20]; void **
0x18001273a  mov     [rsp+80h+var_60], rax; void **
0x18001273f  mov     edx, esi; unsigned int
0x180012741  mov     rcx, r12; void *
0x180012744  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180012749  mov     ebx, eax
0x18001274b  test    eax, eax
0x18001274d  js      loc_180012AA6
0x180012753  mov     rcx, [rbp+var_48]
0x180012757  lea     rax, [rbp+var_38]
0x18001275b  lea     r9, [rbp+var_40]
0x18001275f  mov     [rsp+80h+var_60], rax
0x180012764  mov     r8, rdi
0x180012767  mov     [rbp+var_50], 0
0x18001276f  mov     edx, 1
0x180012774  mov     [rbp+arg_8], 0
0x18001277b  mov     [rbp+var_40], 0
0x180012783  mov     [rbp+var_38], 0
0x18001278b  call    cs:__imp_SamLookupNamesInDomain
0x180012791  test    eax, eax
0x180012793  js      loc_18001281F
0x180012799  mov     rax, [rbp+var_38]
0x18001279d  lea     rsi, WPP_GLOBAL_Control
0x1800127a4  cmp     dword ptr [rax], 4
0x1800127a7  jz      short loc_1800127B0
0x1800127a9  mov     ebx, 0D000008Ah
0x1800127ae  jmp     short loc_180012806
0x1800127b0  mov     r8, [rbp+var_40]
0x1800127b4  lea     r9, [rbp+var_50]
0x1800127b8  mov     rcx, [rbp+var_48]
0x1800127bc  mov     edx, 20017h
0x1800127c1  mov     r8d, [r8]
0x1800127c4  call    cs:__imp_SamOpenAlias
0x1800127ca  test    eax, eax
0x1800127cc  jns     short loc_1800127FD
0x1800127ce  mov     ebx, eax
0x1800127d0  bts     ebx, 1Ch
0x1800127d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127db  cmp     rcx, rsi
0x1800127de  jz      short loc_180012806
0x1800127e0  test    byte ptr [rcx+1Ch], 2
0x1800127e4  jz      short loc_180012806
0x1800127e6  mov     rcx, [rcx+10h]
0x1800127ea  mov     edx, 51h ; 'Q'
0x1800127ef  mov     r9, rdi
0x1800127f2  mov     dword ptr [rsp+80h+var_60], ebx
0x1800127f6  call    WPP_SF_ZD
0x1800127fb  jmp     short loc_180012806
0x1800127fd  mov     rax, [rbp+var_40]
0x180012801  mov     ecx, [rax]
0x180012803  mov     [rbp+arg_8], ecx
0x180012806  mov     rcx, [rbp+var_38]
0x18001280a  call    cs:__imp_SamFreeMemory
0x180012810  mov     rcx, [rbp+var_40]
0x180012814  call    cs:__imp_SamFreeMemory
0x18001281a  jmp     loc_1800128C7
0x18001281f  cmp     eax, 0C0000073h
0x180012824  jnz     short loc_180012893
0x180012826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001282d  lea     rsi, WPP_GLOBAL_Control
0x180012834  cmp     rcx, rsi
0x180012837  jz      short loc_180012850
0x180012839  test    byte ptr [rcx+1Ch], 8
0x18001283d  jz      short loc_180012850
0x18001283f  mov     rcx, [rcx+10h]
0x180012843  mov     edx, 52h ; 'R'
0x180012848  mov     r9, rdi
0x18001284b  call    WPP_SF_Z
0x180012850  mov     rcx, [rbp+var_48]
0x180012854  lea     rax, [rbp+arg_8]
0x180012858  lea     r9, [rbp+var_50]
0x18001285c  mov     [rsp+80h+var_60], rax
0x180012861  mov     r8d, 0F001Fh
0x180012867  mov     rdx, rdi
0x18001286a  call    cs:__imp_SamCreateAliasInDomain
0x180012870  test    eax, eax
0x180012872  jns     short loc_1800128C7
0x180012874  mov     ebx, eax
0x180012876  bts     ebx, 1Ch
0x18001287a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012881  cmp     rcx, rsi
0x180012884  jz      short loc_1800128C7
0x180012886  test    byte ptr [rcx+1Ch], 2
0x18001288a  jz      short loc_1800128C7
0x18001288c  mov     edx, 53h ; 'S'
0x180012891  jmp     short loc_1800128B7
0x180012893  mov     ebx, eax
0x180012895  bts     ebx, 1Ch
0x180012899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128a0  lea     rsi, WPP_GLOBAL_Control
0x1800128a7  cmp     rcx, rsi
0x1800128aa  jz      short loc_1800128C7
0x1800128ac  test    byte ptr [rcx+1Ch], 2
0x1800128b0  jz      short loc_1800128C7
0x1800128b2  mov     edx, 54h ; 'T'
0x1800128b7  mov     rcx, [rcx+10h]
0x1800128bb  mov     r9, rdi
0x1800128be  mov     dword ptr [rsp+80h+var_60], ebx
0x1800128c2  call    WPP_SF_ZD
0x1800128c7  test    ebx, ebx
0x1800128c9  js      loc_180012A83
0x1800128cf  test    r15, r15
0x1800128d2  jnz     short loc_1800128DD
0x1800128d4  test    r13, r13
0x1800128d7  jz      loc_180012A83
0x1800128dd  test    [rbp+arg_40], 8
0x1800128e1  jz      loc_18001297C
0x1800128e7  movups  xmm0, xmmword ptr [r15]
0x1800128eb  mov     rcx, [rbp+var_50]
0x1800128ef  lea     r8, [rbp+pv]
0x1800128f3  movups  xmm1, xmmword ptr [r15+18h]
0x1800128f8  mov     edx, 2
0x1800128fd  movdqu  xmmword ptr [rbp+pv], xmm0
0x180012902  movdqu  [rbp+var_18], xmm1
0x180012907  call    cs:__imp_SamSetInformationAlias
0x18001290d  mov     ebx, eax
0x18001290f  test    eax, eax
0x180012911  js      short loc_180012949
0x180012913  mov     rcx, [rbp+var_50]
0x180012917  lea     r8, [rbp+var_18]
0x18001291b  mov     edx, 3
0x180012920  call    cs:__imp_SamSetInformationAlias
0x180012926  mov     ebx, eax
0x180012928  test    eax, eax
0x18001292a  jns     short loc_18001297C
0x18001292c  bts     ebx, 1Ch
0x180012930  mov     rcx, cs:WPP_GLOBAL_Control
0x180012937  cmp     rcx, rsi
0x18001293a  jz      short loc_180012974
0x18001293c  test    byte ptr [rcx+1Ch], 2
0x180012940  jz      short loc_180012974
0x180012942  mov     edx, 55h ; 'U'
0x180012947  jmp     short loc_180012964
0x180012949  bts     ebx, 1Ch
0x18001294d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012954  cmp     rcx, rsi
0x180012957  jz      short loc_180012974
0x180012959  test    byte ptr [rcx+1Ch], 2
0x18001295d  jz      short loc_180012974
0x18001295f  mov     edx, 56h ; 'V'
0x180012964  mov     rcx, [rcx+10h]
0x180012968  mov     r9, rdi
0x18001296b  mov     dword ptr [rsp+80h+var_60], ebx
0x18001296f  call    WPP_SF_ZD
0x180012974  test    ebx, ebx
0x180012976  js      loc_180012A83
0x18001297c  test    [rbp+arg_40], 10h
0x180012980  jz      short loc_1800129CD
0x180012982  mov     rcx, [rbp+var_50]
0x180012986  mov     r8, r13
0x180012989  mov     edx, 5
0x18001298e  call    cs:__imp_SamSetInformationAlias
0x180012994  mov     ebx, eax
0x180012996  test    eax, eax
0x180012998  jns     short loc_1800129CD
0x18001299a  bts     ebx, 1Ch
0x18001299e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129a5  cmp     rcx, rsi
0x1800129a8  jz      short loc_1800129C5
0x1800129aa  test    byte ptr [rcx+1Ch], 2
0x1800129ae  jz      short loc_1800129C5
0x1800129b0  mov     rcx, [rcx+10h]
0x1800129b4  mov     edx, 57h ; 'W'
0x1800129b9  mov     r9, rdi
0x1800129bc  mov     dword ptr [rsp+80h+var_60], ebx
0x1800129c0  call    WPP_SF_ZD
0x1800129c5  test    ebx, ebx
0x1800129c7  js      loc_180012A83
0x1800129cd  test    [rbp+arg_40], 1
0x1800129d1  jz      short loc_180012A41
0x1800129d3  mov     edx, [rbp+arg_8]
0x1800129d6  lea     r8, [rbp+pv]
0x1800129da  mov     rcx, r12
0x1800129dd  mov     [rbp+pv], 0
0x1800129e5  call    CSGetAccountSIDByRID
0x1800129ea  mov     ebx, eax
0x1800129ec  test    eax, eax
0x1800129ee  js      loc_180012A83
0x1800129f4  mov     edx, [rbp+arg_38]; unsigned int
0x1800129f7  mov     rcx, [rbp+pv]; void *
0x1800129fb  call    ?CSSetAccountRights@@YAJPEAXK@Z; CSSetAccountRights(void *,ulong)
0x180012a00  mov     ebx, eax
0x180012a02  test    eax, eax
0x180012a04  jns     short loc_180012A33
0x180012a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a0d  cmp     rcx, rsi
0x180012a10  jz      short loc_180012A33
0x180012a12  test    byte ptr [rcx+1Ch], 2
0x180012a16  jz      short loc_180012A33
0x180012a18  mov     r9d, [rbp+arg_38]
0x180012a1c  mov     edx, 58h ; 'X'
0x180012a21  mov     rcx, [rcx+10h]
0x180012a25  mov     [rsp+80h+var_58], eax
0x180012a29  mov     [rsp+80h+var_60], rdi
0x180012a2e  call    WPP_SF_DZD
0x180012a33  mov     rcx, [rbp+pv]; pv
0x180012a37  call    cs:__imp_CoTaskMemFree
0x180012a3d  test    ebx, ebx
0x180012a3f  js      short loc_180012A83
0x180012a41  mov     r9d, [rbp+arg_30]; int
0x180012a45  mov     r8d, [rbp+arg_28]; unsigned int
0x180012a49  mov     rdx, [rbp+arg_20]; unsigned __int16 **
0x180012a4d  mov     rcx, [rbp+var_50]; void *
0x180012a51  call    ?CSUpdateGroupMembers@@YAJPEAXPEAPEBGKH@Z; CSUpdateGroupMembers(void *,ushort const * *,ulong,int)
0x180012a56  mov     ebx, eax
0x180012a58  test    eax, eax
0x180012a5a  jns     short loc_180012A83
0x180012a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a63  cmp     rcx, rsi
0x180012a66  jz      short loc_180012A83
0x180012a68  test    byte ptr [rcx+1Ch], 2
0x180012a6c  jz      short loc_180012A83
0x180012a6e  mov     rcx, [rcx+10h]
0x180012a72  mov     edx, 59h ; 'Y'
0x180012a77  mov     r9, rdi
0x180012a7a  mov     dword ptr [rsp+80h+var_60], eax
0x180012a7e  call    WPP_SF_ZD
0x180012a83  mov     rcx, [rbp+var_50]
0x180012a87  test    rcx, rcx
0x180012a8a  jz      short loc_180012A92
0x180012a8c  call    cs:__imp_SamCloseHandle
0x180012a92  mov     rcx, [rbp+var_48]
0x180012a96  call    cs:__imp_SamCloseHandle
0x180012a9c  mov     rcx, [rbp+var_20]
0x180012aa0  call    cs:__imp_SamCloseHandle
0x180012aa6  lea     r11, [rsp+80h+var_s0]
0x180012aae  mov     eax, ebx
0x180012ab0  mov     rbx, [r11+30h]
0x180012ab4  mov     rsi, [r11+40h]
0x180012ab8  mov     rsp, r11
0x180012abb  pop     r15
0x180012abd  pop     r13
0x180012abf  pop     r12
0x180012ac1  pop     rdi
0x180012ac2  pop     rbp
0x180012ac3  retn
```
