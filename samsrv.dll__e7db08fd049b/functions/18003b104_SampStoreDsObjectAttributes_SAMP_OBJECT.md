# SampStoreDsObjectAttributes(_SAMP_OBJECT *)

- ea: `0x18003b104`
- end: `0x18003b7ca`
- name: `?SampStoreDsObjectAttributes@@YAJPEAU_SAMP_OBJECT@@@Z`
- size: `1734`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008590`
- `0x180027e70`

## callees

- `0x180012a28`
- `0x180021e80`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x18003b104`
- `0x18003bf70`
- `0x18004f6d8`
- `0x18005d4d8`
- `0x18005d9d8`
- `0x18005db04`
- `0x18005e0c0`
- `0x1800776b4`
- `0x1800a91c0`
- `0x1800a9a04`

## import_xrefs

- `ntdll!RtlClearAllBits` at `0x18003b746`
- `ntdll!RtlClearAllBits` at `0x18003b746`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b35b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b37d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b46b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b499`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b4cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b4e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b537`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b5cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b35b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b37d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b46b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b499`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b4cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b4e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b537`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b5cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b314`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b3d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b728`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b314`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b3d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b728`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b761`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCheckForSiteAffinityUpdate` at `0x18003b446`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCheckForSiteAffinityUpdate` at `0x18003b446`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMapSamAttrIdToDsAttrId` at `0x18003b23f`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMapSamAttrIdToDsAttrId` at `0x18003b23f`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetAttributesEx` at `0x18003b6a1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetAttributesEx` at `0x18003b6a1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUpdateSupplementalCreds` at `0x18003b6f6`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUpdateSupplementalCreds` at `0x18003b6f6`

## pseudocode

```c
__int64 __fastcall SampStoreDsObjectAttributes(struct _SAMP_OBJECT *a1)
{
  char v2; // cl
  struct _ATTRBLOCKSIMPLE *v3; // rbx
  char v4; // al
  char v5; // cl
  int appended; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  _QWORD *v10; // r14
  __int64 v11; // rdx
  _DWORD *v12; // r13
  int v13; // r12d
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // r15d
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // r8d
  __int128 v20; // xmm0
  HLOCAL *v21; // xmm6_8
  HLOCAL *v22; // rcx
  __int64 v23; // r15
  HLOCAL *v24; // r15
  _DWORD *v25; // rax
  __int128 v26; // xmm0
  __int64 v27; // rdi
  _OWORD *v28; // rax
  HLOCAL v29; // rax
  _QWORD *v30; // rdi
  _QWORD *v31; // rax
  _DWORD *v32; // rax
  _QWORD *v33; // rdi
  _QWORD *v34; // rax
  struct _ATTRBLOCKSIMPLE *v35; // rax
  __int64 v36; // rdx
  int v37; // eax
  __int64 i; // rcx
  int v39; // edx
  int v40; // ecx
  int v41; // edx
  unsigned int v42; // r14d
  unsigned int v43; // r14d
  int v44; // eax
  int v45; // eax
  int v46; // eax
  _BYTE *v47; // rax
  char *v48; // r14
  __int64 v49; // rcx
  char v50[8]; // [rsp+38h] [rbp-69h] BYREF
  struct _ATTRBLOCKSIMPLE *v51; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v52; // [rsp+48h] [rbp-59h]
  struct _ATTRBLOCKSIMPLE *v53; // [rsp+50h] [rbp-51h] BYREF
  __int64 v54; // [rsp+58h] [rbp-49h]
  __int128 v55; // [rsp+68h] [rbp-39h] BYREF
  HLOCAL *v56; // [rsp+78h] [rbp-29h]
  __int128 v57; // [rsp+88h] [rbp-19h] BYREF
  HLOCAL *v58; // [rsp+98h] [rbp-9h]

  v2 = *((_BYTE *)a1 + 20);
  v3 = 0;
  v51 = 0;
  v4 = v2 & 5;
  v5 = v2 & 0xA;
  if ( v4 != 5 && v5 != 10 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 14, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
    return 0;
  }
  appended = 0;
  v8 = *((_QWORD *)a1 + 14);
  v9 = *((int *)a1 + 4);
  v10 = 0;
  v11 = *((_QWORD *)a1 + 22);
  v12 = 0;
  v13 = (*((_BYTE *)a1 + 28) & 4) << 16;
  v52 = *((_DWORD *)a1 + 4);
  v54 = v11;
  if ( v8 )
  {
    if ( v4 == 5 )
    {
      v14 = 88 * v9;
      if ( v5 == 10 )
        v15 = SampConvertCombinedAttributesToAttrBlock(
                a1,
                *(_DWORD *)((char *)&SampObjectInformation + v14 + 68),
                *((_DWORD *)a1 + 30) - *(_DWORD *)((char *)&SampObjectInformation + v14 + 72),
                &v51);
      else
        v15 = SampConvertFixedLengthAttributesToAttrBlock(
                (unsigned int)v9,
                v8 + *(unsigned int *)((char *)&SampObjectInformation + v14 + 64),
                &v51);
    }
    else
    {
      if ( v5 != 10 )
        goto LABEL_15;
      v15 = SampConvertVarLengthAttributesToAttrBlock(
              a1,
              (struct _SAMP_VARIABLE_LENGTH_ATTRIBUTE *)(v8 + *((unsigned int *)&SampObjectInformation + 22 * v9 + 19)),
              &v51);
    }
    appended = v15;
    if ( v15 < 0 )
      goto LABEL_28;
    v3 = v51;
  }
LABEL_15:
  v16 = *((_DWORD *)a1 + 4);
  if ( (int)SampShouldCallNtdsaApiSet() >= 0 )
    NtdsaExtMapSamAttrIdToDsAttrId(v16, v3);
  if ( *((_DWORD *)a1 + 4) != 4 )
    goto LABEL_30;
  if ( *((char *)a1 + 20) < 0 || !_bittest64(*((const signed __int64 **)a1 + 13), 5u) )
    goto LABEL_22;
  appended = SampUpgradeUserParms(a1, &v51);
  if ( appended < 0 )
  {
LABEL_28:
    v3 = v51;
    goto LABEL_91;
  }
  v3 = v51;
LABEL_22:
  if ( *((_DWORD *)a1 + 4) != 4 )
    goto LABEL_30;
  v18 = *((_QWORD *)a1 + 38);
  if ( !v18 )
    goto LABEL_30;
  v19 = *((_DWORD *)a1 + 62);
  v58 = 0;
  v57 = 0;
  appended = SampConvertCredentialsToAttr((_DWORD)a1, 0, v19, v18, (__int64)&v57);
  if ( appended >= 0 )
  {
    SampFreeSupplementalCredentialList(*((HLOCAL *)a1 + 38));
    v20 = v57;
    *((_QWORD *)a1 + 38) = 0;
    v21 = v58;
    v55 = v20;
    v56 = v58;
    appended = SampAppendAttrToAttrBlock(&v55, &v51);
    if ( appended < 0 )
    {
      LocalFree(v21[1]);
      v22 = v21;
LABEL_27:
      LocalFree(v22);
      goto LABEL_28;
    }
    v3 = v51;
LABEL_30:
    v23 = 16;
    if ( *((_DWORD *)a1 + 4) == 4 && _bittest64((const signed __int64 *)(*((_QWORD *)a1 + 13) + 16LL), 4u) )
    {
      DWORD1(v57) = 0;
      HIDWORD(v57) = 0;
      v24 = (HLOCAL *)LocalAlloc(0x40u, 0x10u);
      if ( !v24 )
      {
LABEL_33:
        appended = -1073741801;
        goto LABEL_91;
      }
      v25 = LocalAlloc(0x40u, 4u);
      v24[1] = v25;
      if ( !v25 )
      {
        LocalFree(v24);
        goto LABEL_33;
      }
      *v25 = *((_DWORD *)a1 + 141);
      LODWORD(v57) = 591753;
      DWORD2(v57) = 1;
      v26 = v57;
      *(_DWORD *)v24 = 4;
      v56 = v24;
      v55 = v26;
      appended = SampAppendAttrToAttrBlock(&v55, &v51);
      if ( appended < 0 )
      {
        LocalFree(v24[1]);
        v22 = v24;
        goto LABEL_27;
      }
      v3 = v51;
      v13 |= 0x20000000u;
      v23 = 16;
    }
    if ( *((_DWORD *)a1 + 4) != 4 )
      goto LABEL_62;
    if ( !*((_BYTE *)a1 + 384) )
      goto LABEL_62;
    v57 = 0;
    v58 = 0;
    v50[0] = 0;
    if ( (int)SampShouldCallNtdsaApiSet() < 0
      || !(unsigned __int8)NtdsaExtCheckForSiteAffinityUpdate(a1, 0, (char *)a1 + 360, &v57, v50) )
    {
      goto LABEL_62;
    }
    v27 = 1;
    v53 = 0;
    if ( v50[0] )
      v27 = 2;
    v28 = LocalAlloc(0x40u, 0x10u);
    v10 = v28;
    if ( v28 )
    {
      *v28 = 0;
      v29 = LocalAlloc(0x40u, 24 * v27);
      v10[1] = v29;
      if ( v29 )
      {
        memset_0(v29, 0, 24 * v27);
        *(_DWORD *)v10 = v27;
        v51 = 0;
        v23 = 16;
        if ( v50[0] )
        {
          v30 = LocalAlloc(0x40u, 0x10u);
          if ( !v30 )
            goto LABEL_46;
          v31 = LocalAlloc(0x40u, 0x18u);
          if ( !v31 )
            goto LABEL_46;
          *(_OWORD *)v31 = *(_OWORD *)((char *)a1 + 360);
          v31[2] = *((_QWORD *)a1 + 47);
          *(_DWORD *)v30 = 24;
          v30[1] = v31;
          v32 = (_DWORD *)v10[1];
          v51 = (struct _ATTRBLOCKSIMPLE *)1;
          *v32 = 591267;
          *(_DWORD *)(v10[1] + 8LL) = 1;
          *(_QWORD *)(v10[1] + 16LL) = v30;
        }
        v33 = LocalAlloc(0x40u, 0x10u);
        if ( v33 )
        {
          v34 = LocalAlloc(0x40u, 0x18u);
          if ( v34 )
          {
            *(_OWORD *)v34 = v57;
            v34[2] = v58;
            v33[1] = v34;
            v35 = v51;
            *(_DWORD *)v33 = 24;
            v36 = 3LL * (_QWORD)v35;
            *(_DWORD *)(v10[1] + 8 * v36) = 591267;
            *(_DWORD *)(v10[1] + 8 * v36 + 8) = 1;
            *(_QWORD *)(v10[1] + 8 * v36 + 16) = v33;
            appended = SampMergeDsAttrBlocks(v3, v10, &v53);
            if ( appended < 0 )
              goto LABEL_91;
            v3 = v53;
            v12 = LocalAlloc(0x40u, 4LL * *(unsigned int *)v53);
            if ( !v12 )
            {
              appended = -1073741670;
LABEL_90:
              v10 = 0;
              goto LABEL_91;
            }
            v37 = *(_DWORD *)v3;
            for ( i = 0; (unsigned int)i < *(_DWORD *)v3; v37 = *(_DWORD *)v3 )
            {
              v12[i] = 0;
              i = (unsigned int)(i + 1);
            }
            if ( v50[0] )
              v12[v37 - 2] = 4;
            v12[*(_DWORD *)v3 - 1] = 3;
LABEL_62:
            if ( !v3 || !*(_DWORD *)v3 )
            {
LABEL_80:
              v10 = 0;
              if ( *((_DWORD *)a1 + 4) != 4 || !*((_QWORD *)a1 + 89) )
                goto LABEL_91;
              v46 = SampShouldCallNtdsaApiSet();
              appended = v46;
              if ( v46 == -1073741637 )
              {
                appended = 0;
              }
              else if ( v46 >= 0 )
              {
                appended = NtdsaExtUpdateSupplementalCreds(a1);
              }
              v47 = (_BYTE *)*((_QWORD *)a1 + 89);
              v48 = (char *)a1 + 704;
              v49 = *((unsigned __int16 *)a1 + 352);
              if ( *((_WORD *)a1 + 352) )
              {
                do
                {
                  *v47++ = 0;
                  --v49;
                }
                while ( v49 );
              }
              LocalFree(*((HLOCAL *)a1 + 89));
              do
              {
                *v48++ = 0;
                --v23;
              }
              while ( v23 );
              goto LABEL_90;
            }
            LOBYTE(v17) = *((_BYTE *)a1 + 29);
            v39 = v13 | 0x200000;
            if ( (*((_BYTE *)a1 + 28) & 0x20) == 0 )
              v39 = v13;
            v40 = v39 | 0x10000000;
            if ( (v17 & 2) == 0 )
              v40 = v39;
            v41 = v40 | 0x40000000;
            if ( (v17 & 4) == 0 )
              v41 = v40;
            v42 = v41 | 0x80000000;
            if ( (v17 & 8) == 0 )
              v42 = v41;
            v43 = v42 | 1;
            if ( v12 )
            {
              v44 = SampShouldCallNtdsaApiSet();
              appended = v44;
              if ( v44 == -1073741637 )
              {
                appended = 0;
                goto LABEL_79;
              }
              if ( v44 < 0 )
              {
LABEL_79:
                *((_BYTE *)a1 + 28) &= ~0x20u;
                v10 = 0;
                if ( appended < 0 )
                  goto LABEL_91;
                goto LABEL_80;
              }
              v45 = NtdsaExtSetAttributesEx(v54, v43, v12, v52, v3);
            }
            else
            {
              v45 = SampExtSetAttributesDs(v54, v43, v17, v52, v3);
            }
            appended = v45;
            goto LABEL_79;
          }
        }
      }
    }
LABEL_46:
    appended = -1073741670;
  }
LABEL_91:
  *((_BYTE *)a1 + 20) &= 0xF3u;
  RtlClearAllBits((PRTL_BITMAP)a1 + 6);
  if ( v3 )
    SampFreeAttributeBlock(v3);
  if ( v12 )
    LocalFree(v12);
  if ( v10 )
    SampFreeAttributeBlock(v10);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      15,
      WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
      (unsigned int)appended,
      appended);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003b104  mov     rax, rsp
0x18003b107  push    rbp
0x18003b108  push    rbx
0x18003b109  push    rsi
0x18003b10a  push    rdi
0x18003b10b  push    r12
0x18003b10d  push    r13
0x18003b10f  push    r14
0x18003b111  push    r15
0x18003b113  lea     rbp, [rax-5Fh]
0x18003b117  sub     rsp, 0B8h
0x18003b11e  movaps  xmmword ptr [rax-58h], xmm6
0x18003b122  mov     rax, cs:__security_cookie
0x18003b129  xor     rax, rsp
0x18003b12c  mov     qword ptr [rbp+57h+var_58], rax
0x18003b130  mov     rsi, rcx
0x18003b133  mov     r11b, 5
0x18003b136  mov     cl, [rcx+14h]
0x18003b139  xor     ebx, ebx
0x18003b13b  mov     al, cl
0x18003b13d  mov     [rbp+57h+var_B8], rbx
0x18003b141  mov     r10b, 0Ah
0x18003b144  and     al, r11b
0x18003b147  and     cl, r10b
0x18003b14a  cmp     al, r11b
0x18003b14d  jz      short loc_18003B185
0x18003b14f  cmp     cl, r10b
0x18003b152  jz      short loc_18003B185
0x18003b154  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b15b  test    dword ptr [rcx+44h], 20000h
0x18003b162  jz      short loc_18003B17E
0x18003b164  mov     rcx, [rcx+38h]
0x18003b168  lea     edx, [rbx+0Eh]
0x18003b16b  xor     r9d, r9d
0x18003b16e  mov     [rsp+20h], ebx
0x18003b172  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x18003b179  call    WPP_SF_Dd
0x18003b17e  xor     eax, eax
0x18003b180  jmp     loc_18003B7A2
0x18003b185  movzx   r12d, byte ptr [rsi+1Ch]
0x18003b18a  xor     edi, edi
0x18003b18c  mov     r8, [rsi+70h]
0x18003b190  and     r12d, 4
0x18003b194  movsxd  r9, dword ptr [rsi+10h]
0x18003b198  xor     r14d, r14d
0x18003b19b  mov     rdx, [rsi+0B0h]
0x18003b1a2  xor     r13d, r13d
0x18003b1a5  shl     r12d, 10h
0x18003b1a9  mov     [rbp+57h+var_B0], r9d
0x18003b1ad  mov     [rbp+57h+var_A0], rdx
0x18003b1b1  test    r8, r8
0x18003b1b4  jz      short loc_18003B22C
0x18003b1b6  cmp     al, r11b
0x18003b1b9  jnz     short loc_18003B1FB
0x18003b1bb  imul    rdx, r9, 58h ; 'X'
0x18003b1bf  lea     rax, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x18003b1c6  cmp     cl, r10b
0x18003b1c9  jnz     short loc_18003B1E6
0x18003b1cb  mov     r8d, [rsi+78h]
0x18003b1cf  lea     r9, [rbp+57h+var_B8]; struct _ATTRBLOCKSIMPLE **
0x18003b1d3  sub     r8d, [rdx+rax+48h]; unsigned int
0x18003b1d8  mov     rcx, rsi; struct _SAMP_OBJECT *
0x18003b1db  mov     edx, [rdx+rax+44h]; unsigned int
0x18003b1df  call    ?SampConvertCombinedAttributesToAttrBlock@@YAJPEAU_SAMP_OBJECT@@KKPEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampConvertCombinedAttributesToAttrBlock(_SAMP_OBJECT *,ulong,ulong,_ATTRBLOCKSIMPLE * *)
0x18003b1e4  jmp     short loc_18003B21E
0x18003b1e6  mov     edx, [rdx+rax+40h]
0x18003b1ea  mov     ecx, r9d
0x18003b1ed  add     rdx, r8
0x18003b1f0  lea     r8, [rbp+57h+var_B8]
0x18003b1f4  call    ?SampConvertFixedLengthAttributesToAttrBlock@@YAJW4_SAMP_OBJECT_TYPE@@PEAXPEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampConvertFixedLengthAttributesToAttrBlock(_SAMP_OBJECT_TYPE,void *,_ATTRBLOCKSIMPLE * *)
0x18003b1f9  jmp     short loc_18003B21E
0x18003b1fb  cmp     cl, r10b
0x18003b1fe  jnz     short loc_18003B22C
0x18003b200  imul    rcx, r9, 58h ; 'X'
0x18003b204  lea     rax, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x18003b20b  mov     edx, [rcx+rax+4Ch]
0x18003b20f  mov     rcx, rsi; struct _SAMP_OBJECT *
0x18003b212  add     rdx, r8; struct _SAMP_VARIABLE_LENGTH_ATTRIBUTE *
0x18003b215  lea     r8, [rbp+57h+var_B8]; struct _ATTRBLOCKSIMPLE **
0x18003b219  call    ?SampConvertVarLengthAttributesToAttrBlock@@YAJPEAU_SAMP_OBJECT@@PEAU_SAMP_VARIABLE_LENGTH_ATTRIBUTE@@PEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampConvertVarLengthAttributesToAttrBlock(_SAMP_OBJECT *,_SAMP_VARIABLE_LENGTH_ATTRIBUTE *,_ATTRBLOCKSIMPLE * *)
0x18003b21e  mov     edi, eax
0x18003b220  test    eax, eax
0x18003b222  js      loc_18003B31A
0x18003b228  mov     rbx, [rbp+57h+var_B8]
0x18003b22c  mov     r15d, [rsi+10h]
0x18003b230  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18003b235  test    eax, eax
0x18003b237  js      short loc_18003B245
0x18003b239  mov     rdx, rbx
0x18003b23c  mov     ecx, r15d
0x18003b23f  call    cs:__imp_NtdsaExtMapSamAttrIdToDsAttrId
0x18003b245  cmp     dword ptr [rsi+10h], 4
0x18003b249  jnz     loc_18003B327
0x18003b24f  cmp     [rsi+14h], r13b
0x18003b253  jl      short loc_18003B27F
0x18003b255  mov     rax, [rsi+68h]
0x18003b259  bt      qword ptr [rax], 5
0x18003b25e  setb    al
0x18003b261  test    al, al
0x18003b263  jz      short loc_18003B27F
0x18003b265  lea     rdx, [rbp+57h+var_B8]; struct _ATTRBLOCKSIMPLE **
0x18003b269  mov     rcx, rsi; struct _SAMP_OBJECT *
0x18003b26c  call    ?SampUpgradeUserParms@@YAJPEAU_SAMP_OBJECT@@PEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampUpgradeUserParms(_SAMP_OBJECT *,_ATTRBLOCKSIMPLE * *)
0x18003b271  mov     edi, eax
0x18003b273  test    eax, eax
0x18003b275  js      loc_18003B31A
0x18003b27b  mov     rbx, [rbp+57h+var_B8]
0x18003b27f  cmp     dword ptr [rsi+10h], 4
0x18003b283  jnz     loc_18003B327
0x18003b289  mov     r9, [rsi+130h]
0x18003b290  test    r9, r9
0x18003b293  jz      loc_18003B327
0x18003b299  mov     r8d, [rsi+0F8h]
0x18003b2a0  xor     eax, eax
0x18003b2a2  mov     [rbp+57h+var_60], rax
0x18003b2a6  xorps   xmm0, xmm0
0x18003b2a9  lea     rax, [rbp+57h+var_70]
0x18003b2ad  xor     edx, edx
0x18003b2af  mov     rcx, rsi
0x18003b2b2  mov     [rsp+20h], rax
0x18003b2b7  movups  [rbp+57h+var_70], xmm0
0x18003b2bb  call    SampConvertCredentialsToAttr
0x18003b2c0  mov     edi, eax
0x18003b2c2  test    eax, eax
0x18003b2c4  js      loc_18003B73E
0x18003b2ca  mov     rcx, [rsi+130h]; hMem
0x18003b2d1  call    ?SampFreeSupplementalCredentialList@@YAXPEAU_SAMP_SUPPLEMENTAL_CRED@@@Z; SampFreeSupplementalCredentialList(_SAMP_SUPPLEMENTAL_CRED *)
0x18003b2d6  movups  xmm0, [rbp+57h+var_70]
0x18003b2da  lea     rdx, [rbp+57h+var_B8]
0x18003b2de  mov     [rsi+130h], r13
0x18003b2e5  movsd   xmm6, [rbp+57h+var_60]
0x18003b2ea  lea     rcx, [rbp+57h+var_90]
0x18003b2ee  movaps  [rbp+57h+var_90], xmm0
0x18003b2f2  movsd   [rbp+57h+var_80], xmm6
0x18003b2f7  call    ?SampAppendAttrToAttrBlock@@YAJU_ATTRSIMPLE@@PEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampAppendAttrToAttrBlock(_ATTRSIMPLE,_ATTRBLOCKSIMPLE * *)
0x18003b2fc  mov     edi, eax
0x18003b2fe  test    eax, eax
0x18003b300  jns     short loc_18003B323
0x18003b302  movq    rbx, xmm6
0x18003b307  mov     rcx, [rbx+8]; hMem
0x18003b30b  call    cs:__imp_LocalFree
0x18003b311  mov     rcx, rbx; hMem
0x18003b314  call    cs:__imp_LocalFree
0x18003b31a  mov     rbx, [rbp+57h+var_B8]
0x18003b31e  jmp     loc_18003B73E
0x18003b323  mov     rbx, [rbp+57h+var_B8]
0x18003b327  cmp     dword ptr [rsi+10h], 4
0x18003b32b  mov     r15d, 10h
0x18003b331  jnz     loc_18003B3F3
0x18003b337  mov     rax, [rsi+68h]
0x18003b33b  bt      qword ptr [rax+10h], 4
0x18003b341  setb    al
0x18003b344  test    al, al
0x18003b346  jz      loc_18003B3F3
0x18003b34c  mov     edx, r15d; uBytes
0x18003b34f  mov     dword ptr [rbp+57h+var_70+4], r13d
0x18003b353  lea     ecx, [r15+30h]; uFlags
0x18003b357  mov     dword ptr [rbp+57h+var_70+0Ch], r13d
0x18003b35b  call    cs:__imp_LocalAlloc
0x18003b361  mov     r15, rax
0x18003b364  test    rax, rax
0x18003b367  jnz     short loc_18003B373
0x18003b369  mov     edi, 0C0000017h
0x18003b36e  jmp     loc_18003B73E
0x18003b373  mov     edi, 4
0x18003b378  mov     edx, edi; uBytes
0x18003b37a  lea     ecx, [rdi+3Ch]; uFlags
0x18003b37d  call    cs:__imp_LocalAlloc
0x18003b383  mov     [r15+8], rax
0x18003b387  mov     rcx, rax
0x18003b38a  test    rax, rax
0x18003b38d  jnz     short loc_18003B39A
0x18003b38f  mov     rcx, r15; hMem
0x18003b392  call    cs:__imp_LocalFree
0x18003b398  jmp     short loc_18003B369
0x18003b39a  mov     eax, [rsi+234h]
0x18003b3a0  lea     rdx, [rbp+57h+var_B8]
0x18003b3a4  mov     [rcx], eax
0x18003b3a6  lea     rcx, [rbp+57h+var_90]
0x18003b3aa  mov     dword ptr [rbp+57h+var_70], 90789h
0x18003b3b1  mov     dword ptr [rbp+57h+var_70+8], 1
0x18003b3b8  movups  xmm0, [rbp+57h+var_70]
0x18003b3bc  mov     [r15], edi
0x18003b3bf  mov     [rbp+57h+var_80], r15
0x18003b3c3  movaps  [rbp+57h+var_90], xmm0
0x18003b3c7  call    ?SampAppendAttrToAttrBlock@@YAJU_ATTRSIMPLE@@PEAPEAU_ATTRBLOCKSIMPLE@@@Z; SampAppendAttrToAttrBlock(_ATTRSIMPLE,_ATTRBLOCKSIMPLE * *)
0x18003b3cc  mov     edi, eax
0x18003b3ce  test    eax, eax
0x18003b3d0  jns     short loc_18003B3E4
0x18003b3d2  mov     rcx, [r15+8]; hMem
0x18003b3d6  call    cs:__imp_LocalFree
0x18003b3dc  mov     rcx, r15
0x18003b3df  jmp     loc_18003B314
0x18003b3e4  mov     rbx, [rbp+57h+var_B8]
0x18003b3e8  bts     r12d, 1Dh
0x18003b3ed  mov     r15d, 10h
0x18003b3f3  cmp     dword ptr [rsi+10h], 4
0x18003b3f7  mov     r14d, 2
0x18003b3fd  jnz     loc_18003B621
0x18003b403  cmp     [rsi+180h], r13b
0x18003b40a  jz      loc_18003B621
0x18003b410  xor     eax, eax
0x18003b412  xorps   xmm0, xmm0
0x18003b415  movups  [rbp+57h+var_70], xmm0
0x18003b419  mov     [rbp+57h+var_60], rax
0x18003b41d  mov     [rbp+57h+var_C0], al
0x18003b420  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18003b425  test    eax, eax
0x18003b427  js      loc_18003B621
0x18003b42d  lea     rcx, [rbp+57h+var_C0]
0x18003b431  xor     edx, edx
0x18003b433  mov     [rsp+20h], rcx
0x18003b438  lea     r8, [rsi+168h]
0x18003b43f  mov     rcx, rsi
0x18003b442  lea     r9, [rbp+57h+var_70]
0x18003b446  call    cs:__imp_NtdsaExtCheckForSiteAffinityUpdate
0x18003b44c  test    al, al
0x18003b44e  jz      loc_18003B621
0x18003b454  cmp     [rbp+57h+var_C0], r13b
0x18003b458  lea     edi, [r14-1]
0x18003b45c  mov     rdx, r15; uBytes
0x18003b45f  mov     [rbp+57h+var_A8], r13
0x18003b463  lea     ecx, [r14+3Eh]; uFlags
0x18003b467  cmovnz  edi, r14d
0x18003b46b  call    cs:__imp_LocalAlloc
0x18003b471  mov     r14, rax
0x18003b474  test    rax, rax
0x18003b477  jnz     short loc_18003B483
0x18003b479  mov     edi, 0C000009Ah
0x18003b47e  jmp     loc_18003B73E
0x18003b483  xorps   xmm0, xmm0
0x18003b486  lea     r15, [rdi+rdi*2]
0x18003b48a  shl     r15, 3
0x18003b48e  mov     ecx, 40h ; '@'; uFlags
0x18003b493  mov     rdx, r15; uBytes
0x18003b496  movups  xmmword ptr [rax], xmm0
0x18003b499  call    cs:__imp_LocalAlloc
0x18003b49f  mov     [r14+8], rax
0x18003b4a3  test    rax, rax
0x18003b4a6  jz      short loc_18003B479
0x18003b4a8  mov     r8, r15; Size
0x18003b4ab  xor     edx, edx; Val
0x18003b4ad  mov     rcx, rax; void *
0x18003b4b0  call    memset_0
0x18003b4b5  xor     eax, eax
0x18003b4b7  mov     [r14], edi
0x18003b4ba  mov     [rbp+57h+var_B8], rax
0x18003b4be  lea     r15d, [rax+10h]
0x18003b4c2  cmp     [rbp+57h+var_C0], al
0x18003b4c5  jz      short loc_18003B52F
0x18003b4c7  mov     edx, r15d; uBytes
0x18003b4ca  lea     ecx, [rax+40h]; uFlags
0x18003b4cd  call    cs:__imp_LocalAlloc
0x18003b4d3  mov     rdi, rax
0x18003b4d6  test    rax, rax
0x18003b4d9  jz      short loc_18003B479
0x18003b4db  lea     edx, [r15+8]; uBytes
0x18003b4df  lea     ecx, [rdx+28h]; uFlags
0x18003b4e2  call    cs:__imp_LocalAlloc
0x18003b4e8  test    rax, rax
0x18003b4eb  jz      short loc_18003B479
0x18003b4ed  lea     rcx, [rsi+168h]
0x18003b4f4  movups  xmm0, xmmword ptr [rcx]
0x18003b4f7  movups  xmmword ptr [rax], xmm0
0x18003b4fa  movsd   xmm1, qword ptr [rcx+10h]
0x18003b4ff  lea     ecx, [r15-0Fh]
0x18003b503  movsd   qword ptr [rax+10h], xmm1
0x18003b508  mov     dword ptr [rdi], 18h
0x18003b50e  mov     [rdi+8], rax
0x18003b512  mov     rax, [r14+8]
0x18003b516  mov     [rbp+57h+var_B8], rcx
0x18003b51a  mov     dword ptr [rax], 905A3h
0x18003b520  mov     rax, [r14+8]
0x18003b524  mov     [rax+8], ecx
0x18003b527  mov     rax, [r14+8]
0x18003b52b  mov     [rax+10h], rdi
0x18003b52f  mov     rdx, r15; uBytes
0x18003b532  mov     ecx, 40h ; '@'; uFlags
0x18003b537  call    cs:__imp_LocalAlloc
0x18003b53d  mov     rdi, rax
0x18003b540  test    rax, rax
0x18003b543  jz      loc_18003B479
0x18003b549  mov     edx, 18h; uBytes
0x18003b54e  lea     ecx, [rdx+28h]; uFlags
0x18003b551  call    cs:__imp_LocalAlloc
0x18003b557  test    rax, rax
0x18003b55a  jz      loc_18003B479
0x18003b560  movups  xmm0, [rbp+57h+var_70]
0x18003b564  lea     r8, [rbp+57h+var_A8]; struct _ATTRBLOCKSIMPLE **
0x18003b568  mov     rcx, rbx; hMem
0x18003b56b  movups  xmmword ptr [rax], xmm0
0x18003b56e  movsd   xmm1, [rbp+57h+var_60]
0x18003b573  movsd   qword ptr [rax+10h], xmm1
0x18003b578  mov     [rdi+8], rax
0x18003b57c  mov     rax, [rbp+57h+var_B8]
0x18003b580  mov     dword ptr [rdi], 18h
0x18003b586  lea     rdx, [rax+rax*2]
0x18003b58a  mov     rax, [r14+8]
0x18003b58e  mov     dword ptr [rax+rdx*8], 905A3h
0x18003b595  mov     rax, [r14+8]
  ... truncated ...
```
