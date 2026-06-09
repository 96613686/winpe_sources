# MSMSecRedoSecurity

- ea: `0x1800540d0`
- end: `0x180054862`
- name: `MSMSecRedoSecurity`
- size: `1938`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct DOT11_MSMSEC_RUNTIME_STATE *)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x180006344`
- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000d5e4`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x180016f04`
- `0x18001d370`
- `0x18002b3f8`
- `0x18002bb08`
- `0x180030b00`
- `0x180030fec`
- `0x1800328b0`
- `0x1800353d8`
- `0x180038ea8`
- `0x18003a5d8`
- `0x1800540d0`
- `0x1800558c0`
- `0x18005c934`
- `0x180078be8`
- `0x180078e80`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180054649`
- `MobileNetworking!ReleaseWriteLock` at `0x180054760`
- `MobileNetworking!ReleaseWriteLock` at `0x1800547a0`
- `MobileNetworking!ReleaseWriteLock` at `0x180054649`
- `MobileNetworking!ReleaseWriteLock` at `0x180054760`
- `MobileNetworking!ReleaseWriteLock` at `0x1800547a0`

## string_xrefs

- `0x180054168`: `MSMSecRedoSecurity`
- `0x18005463f`: `MSMSecRedoSecurity`
- `0x180054746`: `MSMSecRedoSecurity`
- `0x18005476e`: `MSMSecRedoSecurity`

## pseudocode

```c
__int64 __fastcall MSMSecRedoSecurity(
        void *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        struct DOT11_MSMSEC_RUNTIME_STATE *a5)
{
  struct MSMSEC_INTF_CONTEXT *v5; // rsi
  struct MSMSEC_PORT_CONTEXT *v6; // r14
  struct DOT11_MSMSEC_RUNTIME_STATE *v7; // r12
  unsigned int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  PVOID *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  unsigned int v22; // r10d
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // r11
  __int64 v26; // r8
  char v27; // r10
  unsigned int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  struct DOT11_MSMSEC_RUNTIME_STATE *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned int v38; // ecx
  int v40; // [rsp+68h] [rbp-31h]
  int v41; // [rsp+6Ch] [rbp-2Dh] BYREF
  int v42; // [rsp+70h] [rbp-29h]
  int v43; // [rsp+74h] [rbp-25h]
  int v44; // [rsp+78h] [rbp-21h]
  struct MSMSEC_INTF_CONTEXT *v45; // [rsp+80h] [rbp-19h] BYREF
  struct DOT11_MSMSEC_RUNTIME_STATE *v46; // [rsp+88h] [rbp-11h] BYREF
  struct MSMSEC_PORT_CONTEXT *v47; // [rsp+90h] [rbp-9h] BYREF
  __int128 v48; // [rsp+98h] [rbp-1h] BYREF
  _OWORD v49[4]; // [rsp+A8h] [rbp+Fh] BYREF

  v41 = 2;
  v45 = 0;
  v47 = 0;
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v40 = 0;
  v43 = 0;
  v7 = 0;
  v42 = 0;
  v48 = 0;
  v46 = 0;
  v49[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 220, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v10 = IncThreadCountAndCheckInitializedEx("MSMSecRedoSecurity", 1911);
  v11 = v10;
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v13 = 221;
LABEL_75:
      WPP_SF_d(v12[7], v13, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v10);
      goto LABEL_76;
    }
    goto LABEL_76;
  }
  if ( !a1 )
  {
    v11 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_76;
    v15 = 222;
    goto LABEL_58;
  }
  v16 = SecMgrValidateRefAndLockAdapter(a1, &v45);
  v11 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 223, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v16);
    v5 = v45;
    goto LABEL_76;
  }
  v44 = 1;
  v40 = 1;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  v5 = v45;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
  {
    WPP_SF_LqDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      224,
      &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
      *((unsigned int *)v45 + 624),
      a1,
      *((unsigned __int8 *)v45 + 2360),
      *((unsigned __int8 *)v45 + 2361),
      *((unsigned __int8 *)v45 + 2362),
      *((unsigned __int8 *)v45 + 2363),
      *((unsigned __int8 *)v45 + 2364),
      *((unsigned __int8 *)v45 + 2365));
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AED45 & 1) != 0 )
  {
    McTemplateU0qj_EventWriteTransfer(v17, MsmSecRedoSecurity, *((unsigned int *)v5 + 624), (char *)v5 + 32);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 68) & 2) != 0 )
    WPP_SF_qq(v17[7], 225, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v5 + 681), 11) )
  {
    v11 = 5023;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v21 = IntfActionStr(11, v18, v19, v20);
      v24 = IntfSecStateStr(v22, v23, v21);
      WPP_SF_SLSL(
        *(_QWORD *)(v25 + 56),
        226,
        (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        v24,
        v27,
        v26,
        11);
    }
    goto LABEL_76;
  }
  v10 = MSMSecCompareProfilesHelper(*((_QWORD *)v5 + 349), a4, v19, v20, (__int64)&v41);
  v11 = v10;
  if ( !v10 )
  {
    if ( v41 )
    {
      v11 = 50;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_76;
      v15 = 228;
    }
    else
    {
      v10 = CheckProfileValidForReauth((struct DOT11_MSMSEC_CONNECTION_PROFILE *)a4);
      v11 = v10;
      if ( v10 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v13 = 229;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
      v10 = CopyRawData(a4 + 40, &v48);
      v11 = v10;
      if ( v10 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v13 = 230;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
      v10 = CopyRawData(a4 + 40, v49);
      v11 = v10;
      if ( v10 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v13 = 231;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
      v28 = MSMSecDuplicateRuntimeState(a5, &v46);
      v11 = v28;
      if ( v28 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 232, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v28);
        v7 = v46;
        goto LABEL_76;
      }
      FreeRawData(*((_QWORD *)v5 + 348) + 40LL);
      FreeRawData(*((_QWORD *)v5 + 349) + 40LL);
      v29 = *((_QWORD *)v5 + 349);
      v30 = *(_DWORD *)(a4 + 40);
      v31 = v46;
      LODWORD(v48) = 0;
      *(_DWORD *)(v29 + 40) = v30;
      v32 = *((_QWORD *)v5 + 349);
      v33 = *((_QWORD *)v5 + 348);
      LODWORD(v49[0]) = 0;
      *(_DWORD *)(v33 + 40) = *(_DWORD *)(v32 + 40);
      v34 = *((_QWORD *)v5 + 348);
      v35 = *((_QWORD *)&v48 + 1);
      *((_QWORD *)&v48 + 1) = 0;
      *(_QWORD *)(v34 + 48) = v35;
      v36 = *((_QWORD *)v5 + 349);
      v37 = *((_QWORD *)&v49[0] + 1);
      *((_QWORD *)&v49[0] + 1) = 0;
      *(_QWORD *)(v36 + 48) = v37;
      *((_QWORD *)v5 + 328) = a2;
      SecMgrSetRTStateIntf(v5, v31);
      v10 = SecMgrFindAndRefInfraPort(v5, &v47);
      v6 = v47;
      v11 = v10;
      if ( v10 == 1168 )
      {
        v11 = 0;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
          goto LABEL_76;
        v15 = 233;
      }
      else
      {
        if ( v10 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v13 = 234;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        v38 = *((_DWORD *)v5 + 624);
        v43 = 1;
        TraceAdapterId(v38, "<<< Unlocking <<<");
        ReleaseWriteLock(v5, (char *)v5 + 2512, "MSMSecRedoSecurity", 2026);
        v40 = 0;
        v10 = SecMgrLockAndCheckPortActive(v6);
        v11 = v10;
        if ( v10 != 6 )
        {
          if ( v10 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              v13 = 236;
              goto LABEL_75;
            }
          }
          else
          {
            v42 = 1;
            SecMgrSetMSMPortHandle(v6, a3);
            v10 = AuthMgrRedoSecurity(
                    (struct MSMSEC_PORT_CONTEXT *)((char *)v6 + 920),
                    (struct DOT11_MSMSEC_CONNECTION_PROFILE *)a4,
                    a5);
            v11 = v10;
            if ( v10 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                v13 = 237;
                goto LABEL_75;
              }
            }
          }
          goto LABEL_76;
        }
        v11 = 0;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
          goto LABEL_76;
        v15 = 235;
      }
    }
LABEL_58:
    WPP_SF_(v14[7], v15, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_76;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v13 = 227;
    goto LABEL_75;
  }
LABEL_76:
  FreeRawData(&v48);
  FreeRawData(v49);
  if ( v40 )
  {
    TraceAdapterId(*((_DWORD *)v5 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v5, (char *)v5 + 2512, "MSMSecRedoSecurity", 2053);
  }
  if ( v42 )
  {
    TracePortId(*((_DWORD *)v6 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(v6, (char *)v6 + 320, "MSMSecRedoSecurity", 2057);
  }
  if ( v43 )
  {
    TracePortId(*((_DWORD *)v6 + 78), "<<< Derefing <<<");
    SecMgrDerefPortEx(v6, "MSMSecRedoSecurity", 2061);
  }
  if ( v44 )
  {
    TraceAdapterId(*((_DWORD *)v5 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v5, "MSMSecRedoSecurity", 2065);
  }
  if ( v7 )
    MSMSecFreeRuntimeState(v7);
  DecThreadCountEx("MSMSecRedoSecurity", 2071);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 238, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800540d0  mov     rax, rsp
0x1800540d3  mov     [rax+8], rbx
0x1800540d7  mov     [rax+18h], r8
0x1800540db  mov     [rax+10h], rdx
0x1800540df  push    rbp
0x1800540e0  push    rsi
0x1800540e1  push    rdi
0x1800540e2  push    r12
0x1800540e4  push    r13
0x1800540e6  push    r14
0x1800540e8  push    r15
0x1800540ea  lea     rbp, [rax-57h]
0x1800540ee  sub     rsp, 0B0h
0x1800540f5  xor     edi, edi
0x1800540f7  mov     [rbp+4Fh+var_7C], 2
0x1800540fe  xorps   xmm0, xmm0
0x180054101  mov     [rbp+4Fh+var_68], rdi
0x180054105  xorps   xmm1, xmm1
0x180054108  mov     [rbp+4Fh+var_58], rdi
0x18005410c  mov     esi, edi
0x18005410e  mov     [rbp+4Fh+var_70], edi
0x180054111  mov     r14d, edi
0x180054114  mov     [rbp+4Fh+var_80], edi
0x180054117  mov     [rbp+4Fh+var_74], edi
0x18005411a  mov     r12d, edi
0x18005411d  mov     [rbp+4Fh+var_78], edi
0x180054120  mov     r13, r9
0x180054123  movups  [rbp+4Fh+var_50], xmm0
0x180054127  mov     [rbp+4Fh+var_60], rdi
0x18005412b  mov     r15, rcx
0x18005412e  movups  [rbp+4Fh+var_40], xmm1
0x180054132  mov     rcx, cs:WPP_GLOBAL_Control
0x180054139  lea     rax, WPP_GLOBAL_Control
0x180054140  cmp     rcx, rax
0x180054143  jz      short loc_180054163
0x180054145  test    dword ptr [rcx+44h], 100h
0x18005414c  jz      short loc_180054163
0x18005414e  mov     rcx, [rcx+38h]
0x180054152  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180054159  mov     edx, 0DCh
0x18005415e  call    WPP_SF_
0x180054163  mov     edx, 777h; int
0x180054168  lea     rcx, aMsmsecredosecu_0; "MSMSecRedoSecurity"
0x18005416f  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180054174  mov     ebx, eax
0x180054176  test    eax, eax
0x180054178  jz      short loc_1800541AA
0x18005417a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054181  lea     r15, WPP_GLOBAL_Control
0x180054188  cmp     rcx, r15
0x18005418b  jz      loc_18005471B
0x180054191  mov     edi, 1
0x180054196  test    [rcx+44h], dil
0x18005419a  jz      loc_18005471B
0x1800541a0  mov     edx, 0DDh
0x1800541a5  jmp     loc_1800546FF
0x1800541aa  test    r15, r15
0x1800541ad  jnz     short loc_1800541E1
0x1800541af  lea     ebx, [r15+57h]
0x1800541b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541ba  lea     r15, WPP_GLOBAL_Control
0x1800541c1  cmp     rcx, r15
0x1800541c4  jz      loc_18005471B
0x1800541ca  lea     edi, [rbx-56h]
0x1800541cd  test    [rcx+44h], dil
0x1800541d1  jz      loc_18005471B
0x1800541d7  mov     edx, 0DEh
0x1800541dc  jmp     loc_1800545D9
0x1800541e1  lea     rdx, [rbp+4Fh+var_68]; struct MSMSEC_INTF_CONTEXT **
0x1800541e5  mov     rcx, r15; void *
0x1800541e8  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x1800541ed  mov     ebx, eax
0x1800541ef  test    eax, eax
0x1800541f1  jz      short loc_180054232
0x1800541f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541fa  lea     r15, WPP_GLOBAL_Control
0x180054201  cmp     rcx, r15
0x180054204  jz      short loc_180054229
0x180054206  mov     edi, 1
0x18005420b  test    [rcx+44h], dil
0x18005420f  jz      short loc_180054229
0x180054211  mov     rcx, [rcx+38h]
0x180054215  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18005421c  mov     edx, 0DFh
0x180054221  mov     r9d, eax
0x180054224  call    WPP_SF_d
0x180054229  mov     rsi, [rbp+4Fh+var_68]
0x18005422d  jmp     loc_18005471B
0x180054232  mov     edi, 1
0x180054237  mov     [rbp+4Fh+var_70], edi
0x18005423a  mov     [rbp+4Fh+var_80], edi
0x18005423d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054244  lea     rax, WPP_GLOBAL_Control
0x18005424b  mov     rsi, [rbp+4Fh+var_68]
0x18005424f  cmp     rcx, rax
0x180054252  jz      short loc_1800542CC
0x180054254  test    byte ptr [rcx+44h], 20h
0x180054258  jz      short loc_1800542CC
0x18005425a  movzx   r8d, byte ptr [rsi+93Ch]
0x180054262  mov     edx, 0E0h
0x180054267  movzx   r9d, byte ptr [rsi+93Bh]
0x18005426f  movzx   eax, byte ptr [rsi+93Dh]
0x180054276  movzx   r10d, byte ptr [rsi+93Ah]
0x18005427e  movzx   r11d, byte ptr [rsi+939h]
0x180054286  movzx   ebx, byte ptr [rsi+938h]
0x18005428d  mov     rcx, [rcx+38h]
0x180054291  mov     [rsp+50h], eax
0x180054295  mov     [rsp+0E0h+var_98], r8d
0x18005429a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800542a1  mov     [rsp+0E0h+var_A0], r9d
0x1800542a6  mov     r9d, [rsi+9C0h]
0x1800542ad  mov     [rsp+0E0h+var_A8], r10d
0x1800542b2  mov     [rsp+0E0h+var_B0], r11d
0x1800542b7  mov     [rsp+0E0h+var_B8], ebx
0x1800542bb  mov     [rsp+0E0h+var_C0], r15
0x1800542c0  call    WPP_SF_LqDDDDDD
0x1800542c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542cc  test    cs:byte_1800AED45, dil
0x1800542d3  jz      short loc_1800542F3
0x1800542d5  mov     r8d, [rsi+9C0h]
0x1800542dc  lea     r9, [rsi+20h]
0x1800542e0  lea     rdx, MsmSecRedoSecurity
0x1800542e7  call    McTemplateU0qj_EventWriteTransfer
0x1800542ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542f3  lea     r15, WPP_GLOBAL_Control
0x1800542fa  cmp     rcx, r15
0x1800542fd  jz      short loc_18005432A
0x1800542ff  test    byte ptr [rcx+44h], 2
0x180054303  jz      short loc_18005432A
0x180054305  mov     rax, [rbp+4Fh+arg_8]
0x180054309  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180054310  mov     r9, [rsi+0A40h]
0x180054317  mov     edx, 0E1h
0x18005431c  mov     rcx, [rcx+38h]
0x180054320  mov     [rsp+0E0h+var_C0], rax
0x180054325  call    WPP_SF_qq
0x18005432a  mov     ecx, [rsi+0AA4h]
0x180054330  mov     edx, 0Bh
0x180054335  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18005433a  test    eax, eax
0x18005433c  jnz     short loc_1800543A4
0x18005433e  mov     ebx, 139Fh
0x180054343  mov     r11, cs:WPP_GLOBAL_Control
0x18005434a  cmp     r11, r15
0x18005434d  jz      loc_18005471B
0x180054353  test    [r11+44h], dil
0x180054357  jz      loc_18005471B
0x18005435d  mov     r10d, [rsi+0AA4h]
0x180054364  lea     edi, [rax+0Bh]
0x180054367  mov     ecx, edi
0x180054369  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x18005436e  mov     ecx, r10d
0x180054371  mov     r8, rax
0x180054374  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180054379  mov     rcx, [r11+38h]
0x18005437d  mov     r9, rax
0x180054380  mov     [rsp+0E0h+var_B0], edi
0x180054384  mov     edx, 0E2h
0x180054389  mov     qword ptr [rsp+0E0h+var_B8], r8
0x18005438e  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180054395  mov     dword ptr [rsp+0E0h+var_C0], r10d
0x18005439a  call    WPP_SF_SLSL
0x18005439f  jmp     loc_18005471B
0x1800543a4  mov     rcx, [rsi+0AE8h]
0x1800543ab  lea     rax, [rbp+4Fh+var_7C]
0x1800543af  mov     rdx, r13
0x1800543b2  mov     [rsp+0E0h+var_C0], rax
0x1800543b7  call    MSMSecCompareProfilesHelper
0x1800543bc  mov     ebx, eax
0x1800543be  test    eax, eax
0x1800543c0  jz      short loc_1800543E6
0x1800543c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543c9  cmp     rcx, r15
0x1800543cc  jz      loc_18005471B
0x1800543d2  test    [rcx+44h], dil
0x1800543d6  jz      loc_18005471B
0x1800543dc  mov     edx, 0E3h
0x1800543e1  jmp     loc_1800546FF
0x1800543e6  cmp     [rbp+4Fh+var_7C], r12d
0x1800543ea  jz      short loc_180054415
0x1800543ec  mov     ebx, 32h ; '2'
0x1800543f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543f8  cmp     rcx, r15
0x1800543fb  jz      loc_18005471B
0x180054401  test    [rcx+44h], dil
0x180054405  jz      loc_18005471B
0x18005440b  mov     edx, 0E4h
0x180054410  jmp     loc_1800545D9
0x180054415  mov     rcx, r13; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180054418  call    ?CheckProfileValidForReauth@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z; CheckProfileValidForReauth(DOT11_MSMSEC_CONNECTION_PROFILE *)
0x18005441d  mov     ebx, eax
0x18005441f  test    eax, eax
0x180054421  jz      short loc_180054447
0x180054423  mov     rcx, cs:WPP_GLOBAL_Control
0x18005442a  cmp     rcx, r15
0x18005442d  jz      loc_18005471B
0x180054433  test    [rcx+44h], dil
0x180054437  jz      loc_18005471B
0x18005443d  mov     edx, 0E5h
0x180054442  jmp     loc_1800546FF
0x180054447  lea     r15, [r13+28h]
0x18005444b  mov     rcx, r15
0x18005444e  lea     rdx, [rbp+4Fh+var_50]
0x180054452  call    CopyRawData
0x180054457  mov     ebx, eax
0x180054459  test    eax, eax
0x18005445b  jz      short loc_180054488
0x18005445d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054464  lea     r15, WPP_GLOBAL_Control
0x18005446b  cmp     rcx, r15
0x18005446e  jz      loc_18005471B
0x180054474  test    [rcx+44h], dil
0x180054478  jz      loc_18005471B
0x18005447e  mov     edx, 0E6h
0x180054483  jmp     loc_1800546FF
0x180054488  lea     rdx, [rbp+4Fh+var_40]
0x18005448c  mov     rcx, r15
0x18005448f  call    CopyRawData
0x180054494  mov     ebx, eax
0x180054496  test    eax, eax
0x180054498  jz      short loc_1800544C5
0x18005449a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544a1  lea     r15, WPP_GLOBAL_Control
0x1800544a8  cmp     rcx, r15
0x1800544ab  jz      loc_18005471B
0x1800544b1  test    [rcx+44h], dil
0x1800544b5  jz      loc_18005471B
0x1800544bb  mov     edx, 0E7h
0x1800544c0  jmp     loc_1800546FF
0x1800544c5  mov     rcx, [rbp+4Fh+arg_20]
0x1800544c9  lea     rdx, [rbp+4Fh+var_60]
0x1800544cd  call    MSMSecDuplicateRuntimeState
0x1800544d2  mov     ebx, eax
0x1800544d4  test    eax, eax
0x1800544d6  jz      short loc_180054512
0x1800544d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544df  lea     r15, WPP_GLOBAL_Control
0x1800544e6  cmp     rcx, r15
0x1800544e9  jz      short loc_180054509
0x1800544eb  test    [rcx+44h], dil
0x1800544ef  jz      short loc_180054509
0x1800544f1  mov     rcx, [rcx+38h]
0x1800544f5  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800544fc  mov     edx, 0E8h
0x180054501  mov     r9d, eax
0x180054504  call    WPP_SF_d
0x180054509  mov     r12, [rbp+4Fh+var_60]
0x18005450d  jmp     loc_18005471B
0x180054512  mov     rcx, [rsi+0AE0h]
0x180054519  add     rcx, 28h ; '('
0x18005451d  call    FreeRawData
0x180054522  mov     rcx, [rsi+0AE8h]
0x180054529  add     rcx, 28h ; '('
0x18005452d  call    FreeRawData
0x180054532  mov     rcx, [rsi+0AE8h]
0x180054539  mov     eax, [r15]
0x18005453c  mov     rdx, [rbp+4Fh+var_60]; struct DOT11_MSMSEC_RUNTIME_STATE *
0x180054540  mov     dword ptr [rbp+4Fh+var_50], r12d
0x180054544  mov     [rcx+28h], eax
0x180054547  mov     rax, [rsi+0AE8h]
0x18005454e  mov     rcx, [rsi+0AE0h]
0x180054555  mov     dword ptr [rbp+4Fh+var_40], r12d
0x180054559  mov     eax, [rax+28h]
0x18005455c  mov     [rcx+28h], eax
0x18005455f  mov     rcx, [rsi+0AE0h]
0x180054566  mov     rax, qword ptr [rbp+4Fh+var_50+8]
0x18005456a  mov     qword ptr [rbp+4Fh+var_50+8], r12
0x18005456e  mov     [rcx+30h], rax
0x180054572  mov     rcx, [rsi+0AE8h]
0x180054579  mov     rax, qword ptr [rbp+4Fh+var_40+8]
0x18005457d  mov     qword ptr [rbp+4Fh+var_40+8], r12
0x180054581  mov     [rcx+30h], rax
0x180054585  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180054588  mov     rax, [rbp+4Fh+arg_8]
0x18005458c  mov     [rsi+0A40h], rax
0x180054593  call    ?SecMgrSetRTStateIntf@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z; SecMgrSetRTStateIntf(MSMSEC_INTF_CONTEXT *,DOT11_MSMSEC_RUNTIME_STATE *)
0x180054598  lea     rdx, [rbp+4Fh+var_58]; struct MSMSEC_PORT_CONTEXT **
0x18005459c  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18005459f  call    ?SecMgrFindAndRefInfraPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrFindAndRefInfraPort(MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT * *)
0x1800545a4  mov     r14, [rbp+4Fh+var_58]
0x1800545a8  mov     ebx, eax
0x1800545aa  cmp     eax, 490h
0x1800545af  jnz     short loc_1800545EE
0x1800545b1  xor     ebx, ebx
0x1800545b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800545ba  lea     r15, WPP_GLOBAL_Control
0x1800545c1  cmp     rcx, r15
0x1800545c4  jz      loc_18005471B
0x1800545ca  test    byte ptr [rcx+44h], 2
0x1800545ce  jz      loc_18005471B
0x1800545d4  mov     edx, 0E9h
0x1800545d9  mov     rcx, [rcx+38h]
0x1800545dd  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800545e4  call    WPP_SF_
0x1800545e9  jmp     loc_18005471B
0x1800545ee  test    eax, eax
0x1800545f0  jz      short loc_18005461D
0x1800545f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800545f9  lea     r15, WPP_GLOBAL_Control
0x180054600  cmp     rcx, r15
  ... truncated ...
```
