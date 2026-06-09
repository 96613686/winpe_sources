# MSMSecSetRuntimeState

- ea: `0x180030690`
- end: `0x180030af9`
- name: `MSMSecSetRuntimeState`
- size: `1129`
- prototype: `__int64 __fastcall(void *, struct DOT11_MSMSEC_RUNTIME_STATE *)`
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18002bb08`
- `0x180030690`
- `0x180030b00`
- `0x180030c78`
- `0x180030fec`
- `0x1800353d8`
- `0x180038ea8`
- `0x1800558c0`
- `0x180057b18`
- `0x180078be8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800309d7`
- `MobileNetworking!ReleaseWriteLock` at `0x180030a0d`
- `MobileNetworking!ReleaseWriteLock` at `0x1800309d7`
- `MobileNetworking!ReleaseWriteLock` at `0x180030a0d`

## pseudocode

```c
__int64 __fastcall MSMSecSetRuntimeState(void ***a1, struct DOT11_MSMSEC_RUNTIME_STATE *a2)
{
  struct DOT11_MSMSEC_RUNTIME_STATE *v2; // rsi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  PVOID *v9; // rcx
  unsigned int *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r11
  __int64 v20; // r8
  char v21; // r10
  unsigned int v22; // eax
  unsigned int v23; // eax
  struct MSMSEC_PORT_CONTEXT *v24; // rbp
  unsigned int v25; // eax
  struct MSMSEC_PORT_CONTEXT *v27; // [rsp+60h] [rbp-48h] BYREF
  struct DOT11_MSMSEC_RUNTIME_STATE *v28; // [rsp+C0h] [rbp+18h] BYREF
  struct MSMSEC_INTF_CONTEXT *v29; // [rsp+C8h] [rbp+20h] BYREF

  v2 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 248, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v5 = IncThreadCountAndCheckInitializedEx("MSMSecSetRuntimeState", 2178);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v8 = 249;
LABEL_8:
      WPP_SF_d(v7[7], v8, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  if ( !a1 )
  {
    v6 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 250, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_52;
  }
  v5 = SecMgrValidateRefAndLockAdapter(a1, &v29);
  v6 = v5;
  if ( !v5 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = (unsigned int *)v29;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      WPP_SF_LqDDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        252,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v29 + 624),
        a1,
        *((unsigned __int8 *)v29 + 2360),
        *((unsigned __int8 *)v29 + 2361),
        *((unsigned __int8 *)v29 + 2362),
        *((unsigned __int8 *)v29 + 2363),
        *((unsigned __int8 *)v29 + 2364),
        *((unsigned __int8 *)v29 + 2365));
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !a2 )
    {
      SecMgrFreeRTStateIntf((struct MSMSEC_INTF_CONTEXT *)v10);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10[691] == 1 )
    {
      if ( !(unsigned int)IsValidIntfSecStateForAction(v10[681], 14) )
      {
        v6 = 5023;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v15 = IntfActionStr(14, v12, v13, v14);
          v18 = IntfSecStateStr(v16, v17, v15);
          WPP_SF_SLSL(
            *(_QWORD *)(v19 + 56),
            254,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v18,
            v21,
            v20,
            14);
        }
        goto LABEL_44;
      }
      v22 = MSMSecDuplicateRuntimeState(a2, &v28);
      v6 = v22;
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 255, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v22);
        v2 = v28;
        goto LABEL_44;
      }
      SecMgrSetRTStateIntf((struct MSMSEC_INTF_CONTEXT *)v10, v28);
      v23 = SecMgrFindAndRefInfraPort((struct MSMSEC_INTF_CONTEXT *)v10, &v27);
      v6 = v23;
      if ( v23 != 1168 )
      {
        if ( !v23 )
        {
          TraceAdapterId(v10[624], "<<< Unlocking <<<");
          ReleaseWriteLock(v10, v10 + 628, "MSMSecSetRuntimeState", 2257);
          v24 = v27;
          v25 = SecMgrSetRTStatePort(v27, a2);
          v6 = v25;
          if ( v25 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 258, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v25);
          TracePortId(*((_DWORD *)v24 + 78), "<<< Derefing <<<");
          SecMgrDerefPortEx(v24, "MSMSecSetRuntimeState", 2274);
          goto LABEL_50;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 257, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v23);
LABEL_44:
        TraceAdapterId(v10[624], "<<< Unlocking <<<");
        ReleaseWriteLock(v10, v10 + 628, "MSMSecSetRuntimeState", 2270);
LABEL_50:
        TraceAdapterId(v10[624], "<<< Derefing <<<");
        SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v10, "MSMSecSetRuntimeState", 2278);
        if ( v2 )
          MSMSecFreeRuntimeState(v2);
        goto LABEL_52;
      }
      v6 = 0;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
        goto LABEL_44;
      v11 = 256;
    }
    else
    {
      v6 = 1003;
      if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 68) & 1) == 0 )
        goto LABEL_44;
      v11 = 253;
    }
    WPP_SF_(v9[7], v11, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_44;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v8 = 251;
    goto LABEL_8;
  }
LABEL_52:
  DecThreadCountEx("MSMSecSetRuntimeState", 2284);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 259, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180030690  mov     rax, rsp
0x180030693  mov     [rax+8], rbx
0x180030697  push    rbp
0x180030698  push    rsi
0x180030699  push    rdi
0x18003069a  push    r12
0x18003069c  push    r13
0x18003069e  push    r14
0x1800306a0  push    r15
0x1800306a2  sub     rsp, 70h
0x1800306a6  xor     esi, esi
0x1800306a8  mov     qword ptr [rax+20h], 0
0x1800306b0  mov     [rax+18h], rsi
0x1800306b4  mov     r14, rdx
0x1800306b7  mov     rbp, rcx
0x1800306ba  mov     qword ptr [rax-48h], 0
0x1800306c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306c9  lea     r15, WPP_GLOBAL_Control
0x1800306d0  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800306d7  cmp     rcx, r15
0x1800306da  jz      short loc_1800306F6
0x1800306dc  test    dword ptr [rcx+44h], 100h
0x1800306e3  jz      short loc_1800306F6
0x1800306e5  mov     rcx, [rcx+38h]
0x1800306e9  mov     edx, 0F8h
0x1800306ee  mov     r8, r12
0x1800306f1  call    WPP_SF_
0x1800306f6  lea     r13, aMsmsecsetrunti_0; "MSMSecSetRuntimeState"
0x1800306fd  mov     edx, 882h; int
0x180030702  mov     rcx, r13; char *
0x180030705  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18003070a  mov     ebx, eax
0x18003070c  test    eax, eax
0x18003070e  jz      short loc_180030743
0x180030710  mov     rcx, cs:WPP_GLOBAL_Control
0x180030717  cmp     rcx, r15
0x18003071a  jz      loc_180030AA8
0x180030720  test    byte ptr [rcx+44h], 1
0x180030724  jz      loc_180030AA8
0x18003072a  mov     edx, 0F9h
0x18003072f  mov     rcx, [rcx+38h]
0x180030733  mov     r9d, eax
0x180030736  mov     r8, r12
0x180030739  call    WPP_SF_d
0x18003073e  jmp     loc_180030AA8
0x180030743  test    rbp, rbp
0x180030746  jnz     short loc_18003077B
0x180030748  lea     ebx, [rbp+57h]
0x18003074b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030752  cmp     rcx, r15
0x180030755  jz      loc_180030AA8
0x18003075b  test    byte ptr [rcx+44h], 1
0x18003075f  jz      loc_180030AA8
0x180030765  mov     rcx, [rcx+38h]
0x180030769  mov     edx, 0FAh
0x18003076e  mov     r8, r12
0x180030771  call    WPP_SF_
0x180030776  jmp     loc_180030AA8
0x18003077b  lea     rdx, [rsp+0A8h+arg_18]; struct MSMSEC_INTF_CONTEXT **
0x180030783  mov     rcx, rbp; void *
0x180030786  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18003078b  mov     ebx, eax
0x18003078d  test    eax, eax
0x18003078f  jz      short loc_1800307B5
0x180030791  mov     rcx, cs:WPP_GLOBAL_Control
0x180030798  cmp     rcx, r15
0x18003079b  jz      loc_180030AA8
0x1800307a1  test    byte ptr [rcx+44h], 1
0x1800307a5  jz      loc_180030AA8
0x1800307ab  mov     edx, 0FBh
0x1800307b0  jmp     loc_18003072F
0x1800307b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307bc  mov     rdi, [rsp+0A8h+arg_18]
0x1800307c4  cmp     rcx, r15
0x1800307c7  jz      short loc_18003083D
0x1800307c9  test    byte ptr [rcx+44h], 20h
0x1800307cd  jz      short loc_18003083D
0x1800307cf  movzx   r8d, byte ptr [rdi+93Ch]
0x1800307d7  mov     edx, 0FCh
0x1800307dc  movzx   r9d, byte ptr [rdi+93Bh]
0x1800307e4  movzx   eax, byte ptr [rdi+93Dh]
0x1800307eb  movzx   r10d, byte ptr [rdi+93Ah]
0x1800307f3  movzx   r11d, byte ptr [rdi+939h]
0x1800307fb  movzx   ebx, byte ptr [rdi+938h]
0x180030802  mov     rcx, [rcx+38h]
0x180030806  mov     [rsp+0A8h+var_58], eax
0x18003080a  mov     [rsp+0A8h+var_60], r8d
0x18003080f  mov     r8, r12
0x180030812  mov     [rsp+0A8h+var_68], r9d
0x180030817  mov     r9d, [rdi+9C0h]
0x18003081e  mov     [rsp+0A8h+var_70], r10d
0x180030823  mov     [rsp+0A8h+var_78], r11d
0x180030828  mov     dword ptr [rsp+0A8h+var_80], ebx
0x18003082c  mov     [rsp+0A8h+var_88], rbp
0x180030831  call    WPP_SF_LqDDDDDD
0x180030836  mov     rcx, cs:WPP_GLOBAL_Control
0x18003083d  test    r14, r14
0x180030840  jnz     short loc_180030851
0x180030842  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180030845  call    ?SecMgrFreeRTStateIntf@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrFreeRTStateIntf(MSMSEC_INTF_CONTEXT *)
0x18003084a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030851  cmp     dword ptr [rdi+0ACCh], 1
0x180030858  jz      short loc_180030888
0x18003085a  mov     ebx, 3EBh
0x18003085f  cmp     rcx, r15
0x180030862  jz      loc_1800309B2
0x180030868  test    byte ptr [rcx+44h], 1
0x18003086c  jz      loc_1800309B2
0x180030872  mov     edx, 0FDh
0x180030877  mov     rcx, [rcx+38h]
0x18003087b  mov     r8, r12
0x18003087e  call    WPP_SF_
0x180030883  jmp     loc_1800309B2
0x180030888  mov     ecx, [rdi+0AA4h]
0x18003088e  mov     ebp, 0Eh
0x180030893  mov     edx, ebp
0x180030895  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18003089a  test    eax, eax
0x18003089c  jnz     short loc_1800308FE
0x18003089e  mov     ebx, 139Fh
0x1800308a3  mov     r11, cs:WPP_GLOBAL_Control
0x1800308aa  cmp     r11, r15
0x1800308ad  jz      loc_1800309B2
0x1800308b3  test    byte ptr [r11+44h], 1
0x1800308b8  jz      loc_1800309B2
0x1800308be  mov     r10d, [rdi+0AA4h]
0x1800308c5  mov     ecx, ebp
0x1800308c7  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800308cc  mov     ecx, r10d
0x1800308cf  mov     r8, rax
0x1800308d2  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800308d7  mov     rcx, [r11+38h]
0x1800308db  mov     r9, rax
0x1800308de  mov     [rsp+0A8h+var_78], ebp
0x1800308e2  mov     edx, 0FEh
0x1800308e7  mov     [rsp+0A8h+var_80], r8
0x1800308ec  mov     r8, r12
0x1800308ef  mov     dword ptr [rsp+0A8h+var_88], r10d
0x1800308f4  call    WPP_SF_SLSL
0x1800308f9  jmp     loc_1800309B2
0x1800308fe  lea     rdx, [rsp+0A8h+arg_10]
0x180030906  mov     rcx, r14
0x180030909  call    MSMSecDuplicateRuntimeState
0x18003090e  mov     ebx, eax
0x180030910  test    eax, eax
0x180030912  jz      short loc_180030944
0x180030914  mov     rcx, cs:WPP_GLOBAL_Control
0x18003091b  cmp     rcx, r15
0x18003091e  jz      short loc_18003093A
0x180030920  test    byte ptr [rcx+44h], 1
0x180030924  jz      short loc_18003093A
0x180030926  mov     rcx, [rcx+38h]
0x18003092a  mov     edx, 0FFh
0x18003092f  mov     r9d, eax
0x180030932  mov     r8, r12
0x180030935  call    WPP_SF_d
0x18003093a  mov     rsi, [rsp+0A8h+arg_10]
0x180030942  jmp     short loc_1800309B2
0x180030944  mov     rdx, [rsp+0A8h+arg_10]; struct DOT11_MSMSEC_RUNTIME_STATE *
0x18003094c  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18003094f  call    ?SecMgrSetRTStateIntf@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z; SecMgrSetRTStateIntf(MSMSEC_INTF_CONTEXT *,DOT11_MSMSEC_RUNTIME_STATE *)
0x180030954  lea     rdx, [rsp+0A8h+var_48]; struct MSMSEC_PORT_CONTEXT **
0x180030959  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18003095c  call    ?SecMgrFindAndRefInfraPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrFindAndRefInfraPort(MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT * *)
0x180030961  mov     ebx, eax
0x180030963  cmp     eax, 490h
0x180030968  jnz     short loc_180030988
0x18003096a  xor     ebx, ebx
0x18003096c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030973  cmp     rcx, r15
0x180030976  jz      short loc_1800309B2
0x180030978  test    byte ptr [rcx+44h], 2
0x18003097c  jz      short loc_1800309B2
0x18003097e  mov     edx, 100h
0x180030983  jmp     loc_180030877
0x180030988  test    eax, eax
0x18003098a  jz      short loc_1800309E8
0x18003098c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030993  cmp     rcx, r15
0x180030996  jz      short loc_1800309B2
0x180030998  test    byte ptr [rcx+44h], 1
0x18003099c  jz      short loc_1800309B2
0x18003099e  mov     rcx, [rcx+38h]
0x1800309a2  mov     edx, 101h
0x1800309a7  mov     r9d, eax
0x1800309aa  mov     r8, r12
0x1800309ad  call    WPP_SF_d
0x1800309b2  mov     ecx, [rdi+9C0h]; unsigned int
0x1800309b8  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800309bf  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800309c4  lea     rdx, [rdi+9D0h]
0x1800309cb  mov     r9d, 8DEh
0x1800309d1  mov     r8, r13
0x1800309d4  mov     rcx, rdi
0x1800309d7  call    cs:__imp_ReleaseWriteLock
0x1800309de  nop     dword ptr [rax+rax+00h]
0x1800309e3  jmp     loc_180030A78
0x1800309e8  mov     ecx, [rdi+9C0h]; unsigned int
0x1800309ee  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800309f5  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800309fa  lea     rdx, [rdi+9D0h]
0x180030a01  mov     r9d, 8D1h
0x180030a07  mov     r8, r13
0x180030a0a  mov     rcx, rdi
0x180030a0d  call    cs:__imp_ReleaseWriteLock
0x180030a14  nop     dword ptr [rax+rax+00h]
0x180030a19  mov     rbp, [rsp+0A8h+var_48]
0x180030a1e  mov     rdx, r14; struct DOT11_MSMSEC_RUNTIME_STATE *
0x180030a21  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180030a24  call    ?SecMgrSetRTStatePort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z; SecMgrSetRTStatePort(MSMSEC_PORT_CONTEXT *,DOT11_MSMSEC_RUNTIME_STATE *)
0x180030a29  mov     ebx, eax
0x180030a2b  test    eax, eax
0x180030a2d  jz      short loc_180030A55
0x180030a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a36  cmp     rcx, r15
0x180030a39  jz      short loc_180030A55
0x180030a3b  test    byte ptr [rcx+44h], 1
0x180030a3f  jz      short loc_180030A55
0x180030a41  mov     rcx, [rcx+38h]
0x180030a45  mov     edx, 102h
0x180030a4a  mov     r9d, eax
0x180030a4d  mov     r8, r12
0x180030a50  call    WPP_SF_d
0x180030a55  mov     ecx, [rbp+138h]; unsigned int
0x180030a5b  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180030a62  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180030a67  mov     r8d, 8E2h; int
0x180030a6d  mov     rdx, r13; char *
0x180030a70  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180030a73  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180030a78  mov     ecx, [rdi+9C0h]; unsigned int
0x180030a7e  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180030a85  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180030a8a  mov     r8d, 8E6h; int
0x180030a90  mov     rdx, r13; char *
0x180030a93  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180030a96  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180030a9b  test    rsi, rsi
0x180030a9e  jz      short loc_180030AA8
0x180030aa0  mov     rcx, rsi
0x180030aa3  call    MSMSecFreeRuntimeState
0x180030aa8  mov     edx, 8ECh; int
0x180030aad  mov     rcx, r13; char *
0x180030ab0  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180030ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030abc  cmp     rcx, r15
0x180030abf  jz      short loc_180030ADE
0x180030ac1  test    dword ptr [rcx+44h], 100h
0x180030ac8  jz      short loc_180030ADE
0x180030aca  mov     rcx, [rcx+38h]
0x180030ace  mov     edx, 103h
0x180030ad3  mov     r9d, ebx
0x180030ad6  mov     r8, r12
0x180030ad9  call    WPP_SF_d
0x180030ade  mov     eax, ebx
0x180030ae0  mov     rbx, [rsp+0A8h+arg_0]
0x180030ae8  add     rsp, 70h
0x180030aec  pop     r15
0x180030aee  pop     r14
0x180030af0  pop     r13
0x180030af2  pop     r12
0x180030af4  pop     rdi
0x180030af5  pop     rsi
0x180030af6  pop     rbp
0x180030af7  retn
```
