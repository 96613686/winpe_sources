# MSMSecSetAPSecondaryPSK

- ea: `0x180054f40`
- end: `0x1800552d9`
- name: `MSMSecSetAPSecondaryPSK`
- size: `921`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18001a23c`
- `0x18001c968`
- `0x18001ecb8`
- `0x18001f29c`
- `0x180021fd0`
- `0x18003da94`
- `0x180054f40`
- `0x1800558c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180055221`
- `MobileNetworking!ReleaseWriteLock` at `0x180055221`

## pseudocode

```c
__int64 __fastcall MSMSecSetAPSecondaryPSK(void ***a1, _DWORD *a2)
{
  __int128 v3; // xmm6
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  struct MSMSEC_INTF_CONTEXT *v12; // rdi
  const wchar_t *v13; // rax
  unsigned int v14; // r10d
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // r11
  __int64 v18; // r8
  char v19; // r10
  _QWORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rbp
  __int128 v26; // [rsp+40h] [rbp-48h] BYREF
  struct MSMSEC_INTF_CONTEXT *v27; // [rsp+A0h] [rbp+18h] BYREF

  v3 = 0;
  v27 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 272, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v5 = IncThreadCountAndCheckInitializedEx("MSMSecSetAPSecondaryPSK", 2391);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v8 = 273;
LABEL_8:
      WPP_SF_d(v7[7], v8, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  if ( !a1 || !a2 )
  {
    v6 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_46;
    v10 = 274;
LABEL_45:
    WPP_SF_(v9[7], v10, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_46;
  }
  if ( !(unsigned int)RawDataIsValid(a2 + 2) )
  {
    v6 = 13;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_46;
    v10 = 275;
    goto LABEL_45;
  }
  v5 = SecMgrValidateRefAndLockAdapter(a1, &v27);
  v6 = v5;
  if ( !v5 )
  {
    v12 = v27;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_LqL(*((_QWORD *)WPP_GLOBAL_Control + 7), 277, v11, *((unsigned int *)v27 + 624));
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v12 + 681), 16) )
    {
      v6 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v13 = IntfActionStr(16);
        v16 = IntfSecStateStr(v14, v15, v13);
        WPP_SF_SLSL(
          *(_QWORD *)(v17 + 56),
          278,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v16,
          v19,
          v18,
          16);
      }
      goto LABEL_41;
    }
    if ( !(unsigned int)IntfIsInAPMode(v12) )
    {
      v6 = 5023;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v21 = *((unsigned int *)v12 + 624);
      v22 = 279;
      goto LABEL_30;
    }
    if ( !*((_QWORD *)v12 + 348) )
      goto LABEL_41;
    if ( (unsigned int)RawDataIsNonEmpty(a2 + 2) )
    {
      v23 = CopyKey((*a2 >> 1) & 1, a2 + 2, &v26);
      v6 = v23;
      if ( v23 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_41;
        v22 = 280;
        v21 = v23;
LABEL_30:
        WPP_SF_d(v20[7], v22, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v21);
LABEL_41:
        TraceAdapterId(*((_DWORD *)v12 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(v12, (char *)v12 + 2512, "MSMSecSetAPSecondaryPSK", 2468);
        TraceAdapterId(*((_DWORD *)v12 + 624), "<<< Derefing <<<");
        SecMgrDerefAdapterEx(v12, "MSMSecSetAPSecondaryPSK", 2472);
        goto LABEL_46;
      }
      v3 = v26;
    }
    v24 = *((_QWORD *)v12 + 348);
    if ( *(_QWORD *)(v24 + 96) )
      ScrubAndFreeKeyMaterial(v24 + 96, v24 + 88);
    *(_DWORD *)(v24 + 80) = *(_DWORD *)(v24 + 80) ^ (*a2 ^ *(_DWORD *)(v24 + 80)) & 1 | 2;
    *(_OWORD *)(v24 + 88) = v3;
    goto LABEL_41;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v8 = 276;
    goto LABEL_8;
  }
LABEL_46:
  DecThreadCountEx("MSMSecSetAPSecondaryPSK", 2474);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 281, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180054f40  mov     rax, rsp
0x180054f43  mov     [rax+8], rbx
0x180054f47  mov     [rax+10h], rbp
0x180054f4b  push    rsi
0x180054f4c  push    rdi
0x180054f4d  push    r13
0x180054f4f  push    r14
0x180054f51  push    r15
0x180054f53  sub     rsp, 60h
0x180054f57  movaps  xmmword ptr [rax-38h], xmm6
0x180054f5b  mov     r15, rdx
0x180054f5e  xorps   xmm6, xmm6
0x180054f61  mov     qword ptr [rax+18h], 0
0x180054f69  movups  xmmword ptr [rax-48h], xmm6
0x180054f6d  mov     rsi, rcx
0x180054f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f77  lea     r13, WPP_GLOBAL_Control
0x180054f7e  lea     rbp, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180054f85  cmp     rcx, r13
0x180054f88  jz      short loc_180054FA4
0x180054f8a  test    dword ptr [rcx+44h], 100h
0x180054f91  jz      short loc_180054FA4
0x180054f93  mov     rcx, [rcx+38h]
0x180054f97  mov     edx, 110h
0x180054f9c  mov     r8, rbp
0x180054f9f  call    WPP_SF_
0x180054fa4  mov     edx, 957h; int
0x180054fa9  lea     rcx, aMsmsecsetapsec_0; "MSMSecSetAPSecondaryPSK"
0x180054fb0  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180054fb5  mov     ebx, eax
0x180054fb7  test    eax, eax
0x180054fb9  jz      short loc_180054FEE
0x180054fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fc2  cmp     rcx, r13
0x180054fc5  jz      loc_18005527E
0x180054fcb  test    byte ptr [rcx+44h], 1
0x180054fcf  jz      loc_18005527E
0x180054fd5  mov     edx, 111h
0x180054fda  mov     rcx, [rcx+38h]
0x180054fde  mov     r9d, eax
0x180054fe1  mov     r8, rbp
0x180054fe4  call    WPP_SF_d
0x180054fe9  jmp     loc_18005527E
0x180054fee  test    rsi, rsi
0x180054ff1  jz      loc_180055256
0x180054ff7  test    r15, r15
0x180054ffa  jz      loc_180055256
0x180055000  lea     r14, [r15+8]
0x180055004  mov     rcx, r14
0x180055007  call    RawDataIsValid
0x18005500c  test    eax, eax
0x18005500e  jnz     short loc_180055037
0x180055010  lea     ebx, [rax+0Dh]
0x180055013  mov     rcx, cs:WPP_GLOBAL_Control
0x18005501a  cmp     rcx, r13
0x18005501d  jz      loc_18005527E
0x180055023  test    byte ptr [rcx+44h], 1
0x180055027  jz      loc_18005527E
0x18005502d  mov     edx, 113h
0x180055032  jmp     loc_180055272
0x180055037  lea     rdx, [rsp+88h+arg_10]; struct MSMSEC_INTF_CONTEXT **
0x18005503f  mov     rcx, rsi; void *
0x180055042  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180055047  mov     ebx, eax
0x180055049  test    eax, eax
0x18005504b  jz      short loc_180055071
0x18005504d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055054  cmp     rcx, r13
0x180055057  jz      loc_18005527E
0x18005505d  test    byte ptr [rcx+44h], 1
0x180055061  jz      loc_18005527E
0x180055067  mov     edx, 114h
0x18005506c  jmp     loc_180054FDA
0x180055071  mov     rcx, cs:WPP_GLOBAL_Control
0x180055078  mov     rdi, [rsp+88h+arg_10]
0x180055080  cmp     rcx, r13
0x180055083  jz      short loc_1800550AC
0x180055085  test    byte ptr [rcx+44h], 20h
0x180055089  jz      short loc_1800550AC
0x18005508b  mov     eax, [r14]
0x18005508e  mov     edx, 115h
0x180055093  mov     r9d, [rdi+9C0h]
0x18005509a  mov     rcx, [rcx+38h]
0x18005509e  mov     dword ptr [rsp+88h+var_60], eax
0x1800550a2  mov     [rsp+88h+var_68], rsi
0x1800550a7  call    WPP_SF_LqL
0x1800550ac  mov     ecx, [rdi+0AA4h]
0x1800550b2  mov     esi, 10h
0x1800550b7  mov     edx, esi
0x1800550b9  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x1800550be  test    eax, eax
0x1800550c0  jnz     short loc_180055122
0x1800550c2  mov     ebx, 139Fh
0x1800550c7  mov     r11, cs:WPP_GLOBAL_Control
0x1800550ce  cmp     r11, r13
0x1800550d1  jz      loc_1800551F8
0x1800550d7  test    byte ptr [r11+44h], 1
0x1800550dc  jz      loc_1800551F8
0x1800550e2  mov     r10d, [rdi+0AA4h]
0x1800550e9  mov     ecx, esi
0x1800550eb  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800550f0  mov     ecx, r10d
0x1800550f3  mov     r8, rax
0x1800550f6  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800550fb  mov     rcx, [r11+38h]
0x1800550ff  mov     r9, rax
0x180055102  mov     [rsp+88h+var_58], esi
0x180055106  mov     edx, 116h
0x18005510b  mov     [rsp+88h+var_60], r8
0x180055110  mov     r8, rbp
0x180055113  mov     dword ptr [rsp+88h+var_68], r10d
0x180055118  call    WPP_SF_SLSL
0x18005511d  jmp     loc_1800551F8
0x180055122  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180055125  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x18005512a  test    eax, eax
0x18005512c  jnz     short loc_18005516A
0x18005512e  mov     ebx, 139Fh
0x180055133  mov     rcx, cs:WPP_GLOBAL_Control
0x18005513a  cmp     rcx, r13
0x18005513d  jz      loc_1800551F8
0x180055143  test    byte ptr [rcx+44h], 1
0x180055147  jz      loc_1800551F8
0x18005514d  mov     r9d, [rdi+9C0h]
0x180055154  mov     edx, 117h
0x180055159  mov     rcx, [rcx+38h]
0x18005515d  mov     r8, rbp
0x180055160  call    WPP_SF_d
0x180055165  jmp     loc_1800551F8
0x18005516a  cmp     qword ptr [rdi+0AE0h], 0
0x180055172  jz      loc_1800551F8
0x180055178  mov     rcx, r14
0x18005517b  call    RawDataIsNonEmpty
0x180055180  test    eax, eax
0x180055182  jz      short loc_1800551C0
0x180055184  mov     ecx, [r15]
0x180055187  lea     r8, [rsp+88h+var_48]
0x18005518c  shr     ecx, 1
0x18005518e  mov     rdx, r14
0x180055191  and     ecx, 1
0x180055194  call    CopyKey
0x180055199  mov     ebx, eax
0x18005519b  test    eax, eax
0x18005519d  jz      short loc_1800551BB
0x18005519f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551a6  cmp     rcx, r13
0x1800551a9  jz      short loc_1800551F8
0x1800551ab  test    byte ptr [rcx+44h], 1
0x1800551af  jz      short loc_1800551F8
0x1800551b1  mov     edx, 118h
0x1800551b6  mov     r9d, eax
0x1800551b9  jmp     short loc_180055159
0x1800551bb  movups  xmm6, [rsp+88h+var_48]
0x1800551c0  mov     rbp, [rdi+0AE0h]
0x1800551c7  lea     rcx, [rbp+60h]
0x1800551cb  cmp     qword ptr [rcx], 0
0x1800551cf  jz      short loc_1800551DA
0x1800551d1  lea     rdx, [rbp+58h]
0x1800551d5  call    ScrubAndFreeKeyMaterial
0x1800551da  mov     eax, [rbp+50h]
0x1800551dd  xor     eax, [r15]
0x1800551e0  and     eax, 1
0x1800551e3  xor     eax, [rbp+50h]
0x1800551e6  or      eax, 2
0x1800551e9  mov     [rbp+50h], eax
0x1800551ec  movdqu  xmmword ptr [rbp+58h], xmm6
0x1800551f1  lea     rbp, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800551f8  mov     ecx, [rdi+9C0h]; unsigned int
0x1800551fe  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180055205  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18005520a  lea     rdx, [rdi+9D0h]
0x180055211  mov     r9d, 9A4h
0x180055217  lea     r8, aMsmsecsetapsec_0; "MSMSecSetAPSecondaryPSK"
0x18005521e  mov     rcx, rdi
0x180055221  call    cs:__imp_ReleaseWriteLock
0x180055228  nop     dword ptr [rax+rax+00h]
0x18005522d  mov     ecx, [rdi+9C0h]; unsigned int
0x180055233  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18005523a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18005523f  mov     r8d, 9A8h; int
0x180055245  lea     rdx, aMsmsecsetapsec_0; "MSMSecSetAPSecondaryPSK"
0x18005524c  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18005524f  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180055254  jmp     short loc_18005527E
0x180055256  mov     ebx, 57h ; 'W'
0x18005525b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055262  cmp     rcx, r13
0x180055265  jz      short loc_18005527E
0x180055267  test    byte ptr [rcx+44h], 1
0x18005526b  jz      short loc_18005527E
0x18005526d  mov     edx, 112h
0x180055272  mov     rcx, [rcx+38h]
0x180055276  mov     r8, rbp
0x180055279  call    WPP_SF_
0x18005527e  mov     edx, 9AAh; int
0x180055283  lea     rcx, aMsmsecsetapsec_0; "MSMSecSetAPSecondaryPSK"
0x18005528a  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18005528f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055296  cmp     rcx, r13
0x180055299  jz      short loc_1800552B8
0x18005529b  test    dword ptr [rcx+44h], 100h
0x1800552a2  jz      short loc_1800552B8
0x1800552a4  mov     rcx, [rcx+38h]
0x1800552a8  mov     edx, 119h
0x1800552ad  mov     r9d, ebx
0x1800552b0  mov     r8, rbp
0x1800552b3  call    WPP_SF_d
0x1800552b8  movaps  xmm6, [rsp+88h+var_38]
0x1800552bd  lea     r11, [rsp+88h+var_28]
0x1800552c2  mov     rbp, [r11+38h]
0x1800552c6  mov     eax, ebx
0x1800552c8  mov     rbx, [r11+30h]
0x1800552cc  mov     rsp, r11
0x1800552cf  pop     r15
0x1800552d1  pop     r14
0x1800552d3  pop     r13
0x1800552d5  pop     rdi
0x1800552d6  pop     rsi
0x1800552d7  retn
```
