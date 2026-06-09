# MSMSecConnectionHealthCheck

- ea: `0x180052140`
- end: `0x1800524db`
- name: `MSMSecConnectionHealthCheck`
- size: `923`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
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
- `0x180030fec`
- `0x180052140`
- `0x180055744`
- `0x1800558c0`
- `0x18005599c`
- `0x18005892c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180052428`
- `MobileNetworking!ReleaseWriteLock` at `0x180052428`

## pseudocode

```c
__int64 __fastcall MSMSecConnectionHealthCheck(void ***a1, int *a2, int *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int *v10; // rdi
  const wchar_t *v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r11
  __int64 v16; // r8
  char v17; // r10
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // esi
  int v22; // ebp
  int v23; // ecx
  const char *v24; // r9
  int v26; // [rsp+60h] [rbp-38h] BYREF
  struct MSMSEC_INTF_CONTEXT *v27; // [rsp+68h] [rbp-30h] BYREF
  int v28; // [rsp+B8h] [rbp+20h] BYREF

  v27 = 0;
  v28 = 4;
  v26 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 239, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v6 = IncThreadCountAndCheckInitializedEx("MSMSecConnectionHealthCheck", 2088);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 240;
LABEL_8:
      WPP_SF_d(v8[7], v9, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
    }
  }
  else if ( a1 && a2 && a3 )
  {
    v6 = SecMgrValidateRefAndLockAdapter(a1, &v27);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v9 = 242;
        goto LABEL_8;
      }
    }
    else
    {
      v10 = (unsigned int *)v27;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        WPP_SF_LqDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          243,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          *((unsigned int *)v27 + 624),
          a1,
          *((unsigned __int8 *)v27 + 2360),
          *((unsigned __int8 *)v27 + 2361),
          *((unsigned __int8 *)v27 + 2362),
          *((unsigned __int8 *)v27 + 2363),
          *((unsigned __int8 *)v27 + 2364),
          *((unsigned __int8 *)v27 + 2365));
      if ( (unsigned int)IsValidIntfSecStateForAction(v10[681], 12) )
      {
        v18 = SecMgrConnectionHealthCheck(
                (struct MSMSEC_INTF_CONTEXT *)v10,
                (enum MSMSEC_CONNECTION_HEALTH_STATUS *)&v28,
                &v26);
        v7 = v18;
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 245, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v18);
        }
        else
        {
          v21 = v28;
          v22 = v26;
          *a2 = v28;
          *a3 = v22;
          v23 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          {
            v24 = "Healthy";
            if ( v21 != 2 )
              v24 = "Other";
            WPP_SF_sLL(*((_QWORD *)WPP_GLOBAL_Control + 7), v19, v20, (_DWORD)v24, v21, v22);
          }
          if ( (byte_1800AED45 & 1) != 0 )
            McTemplateU0qjtqt_EventWriteTransfer(v23, v19, v10[624], (_DWORD)v10 + 32, v21 == 2, v21, v22);
        }
      }
      else
      {
        v7 = 5023;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v11 = IntfActionStr(12);
          v14 = IntfSecStateStr(v12, v13, v11);
          WPP_SF_SLSL(
            *(_QWORD *)(v15 + 56),
            244,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v14,
            v17,
            v16,
            12);
        }
      }
      TraceAdapterId(v10[624], "<<< Unlocking <<<");
      ReleaseWriteLock(v10, v10 + 628, "MSMSecConnectionHealthCheck", 2154);
      TraceAdapterId(v10[624], "<<< Derefing <<<");
      SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v10, "MSMSecConnectionHealthCheck", 2158);
    }
  }
  else
  {
    v7 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 241, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  }
  DecThreadCountEx("MSMSecConnectionHealthCheck", 2160);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 247, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180052140  mov     rax, rsp
0x180052143  mov     [rax+8], rbx
0x180052147  mov     [rax+10h], rbp
0x18005214b  push    rsi
0x18005214c  push    rdi
0x18005214d  push    r12
0x18005214f  push    r14
0x180052151  push    r15
0x180052153  sub     rsp, 70h
0x180052157  mov     r14, r8
0x18005215a  mov     qword ptr [rax-30h], 0
0x180052162  mov     r15, rdx
0x180052165  mov     dword ptr [rax+20h], 4
0x18005216c  mov     rsi, rcx
0x18005216f  mov     dword ptr [rax-38h], 1
0x180052176  mov     rcx, cs:WPP_GLOBAL_Control
0x18005217d  lea     r12, WPP_GLOBAL_Control
0x180052184  lea     rbp, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18005218b  cmp     rcx, r12
0x18005218e  jz      short loc_1800521AA
0x180052190  test    dword ptr [rcx+44h], 100h
0x180052197  jz      short loc_1800521AA
0x180052199  mov     rcx, [rcx+38h]
0x18005219d  mov     edx, 0EFh
0x1800521a2  mov     r8, rbp
0x1800521a5  call    WPP_SF_
0x1800521aa  mov     edx, 828h; int
0x1800521af  lea     rcx, aMsmsecconnecti_0; "MSMSecConnectionHealthCheck"
0x1800521b6  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x1800521bb  mov     ebx, eax
0x1800521bd  test    eax, eax
0x1800521bf  jz      short loc_1800521F4
0x1800521c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521c8  cmp     rcx, r12
0x1800521cb  jz      loc_180052485
0x1800521d1  test    byte ptr [rcx+44h], 1
0x1800521d5  jz      loc_180052485
0x1800521db  mov     edx, 0F0h
0x1800521e0  mov     rcx, [rcx+38h]
0x1800521e4  mov     r9d, eax
0x1800521e7  mov     r8, rbp
0x1800521ea  call    WPP_SF_d
0x1800521ef  jmp     loc_180052485
0x1800521f4  test    rsi, rsi
0x1800521f7  jz      loc_18005245D
0x1800521fd  test    r15, r15
0x180052200  jz      loc_18005245D
0x180052206  test    r14, r14
0x180052209  jz      loc_18005245D
0x18005220f  lea     rdx, [rsp+98h+var_30]; struct MSMSEC_INTF_CONTEXT **
0x180052214  mov     rcx, rsi; void *
0x180052217  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18005221c  mov     ebx, eax
0x18005221e  test    eax, eax
0x180052220  jz      short loc_180052243
0x180052222  mov     rcx, cs:WPP_GLOBAL_Control
0x180052229  cmp     rcx, r12
0x18005222c  jz      loc_180052485
0x180052232  test    byte ptr [rcx+44h], 1
0x180052236  jz      loc_180052485
0x18005223c  mov     edx, 0F2h
0x180052241  jmp     short loc_1800521E0
0x180052243  mov     rcx, cs:WPP_GLOBAL_Control
0x18005224a  mov     rdi, [rsp+98h+var_30]
0x18005224f  cmp     rcx, r12
0x180052252  jz      short loc_1800522C1
0x180052254  test    byte ptr [rcx+44h], 20h
0x180052258  jz      short loc_1800522C1
0x18005225a  movzx   r8d, byte ptr [rdi+93Ch]
0x180052262  mov     edx, 0F3h
0x180052267  movzx   r9d, byte ptr [rdi+93Bh]
0x18005226f  movzx   eax, byte ptr [rdi+93Dh]
0x180052276  movzx   r10d, byte ptr [rdi+93Ah]
0x18005227e  movzx   r11d, byte ptr [rdi+939h]
0x180052286  movzx   ebx, byte ptr [rdi+938h]
0x18005228d  mov     rcx, [rcx+38h]
0x180052291  mov     [rsp+98h+var_48], eax
0x180052295  mov     [rsp+98h+var_50], r8d
0x18005229a  mov     r8, rbp
0x18005229d  mov     [rsp+98h+var_58], r9d
0x1800522a2  mov     r9d, [rdi+9C0h]
0x1800522a9  mov     [rsp+98h+var_60], r10d
0x1800522ae  mov     [rsp+98h+var_68], r11d
0x1800522b3  mov     dword ptr [rsp+98h+var_70], ebx
0x1800522b7  mov     [rsp+98h+var_78], rsi
0x1800522bc  call    WPP_SF_LqDDDDDD
0x1800522c1  mov     ecx, [rdi+0AA4h]
0x1800522c7  mov     esi, 0Ch
0x1800522cc  mov     edx, esi
0x1800522ce  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x1800522d3  test    eax, eax
0x1800522d5  jnz     short loc_180052337
0x1800522d7  mov     ebx, 139Fh
0x1800522dc  mov     r11, cs:WPP_GLOBAL_Control
0x1800522e3  cmp     r11, r12
0x1800522e6  jz      loc_1800523FF
0x1800522ec  test    byte ptr [r11+44h], 1
0x1800522f1  jz      loc_1800523FF
0x1800522f7  mov     r10d, [rdi+0AA4h]
0x1800522fe  mov     ecx, esi
0x180052300  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180052305  mov     ecx, r10d
0x180052308  mov     r8, rax
0x18005230b  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180052310  mov     rcx, [r11+38h]
0x180052314  mov     r9, rax
0x180052317  mov     [rsp+98h+var_68], esi
0x18005231b  mov     edx, 0F4h
0x180052320  mov     [rsp+98h+var_70], r8
0x180052325  mov     r8, rbp
0x180052328  mov     dword ptr [rsp+98h+var_78], r10d
0x18005232d  call    WPP_SF_SLSL
0x180052332  jmp     loc_1800523FF
0x180052337  lea     r8, [rsp+98h+var_38]; int *
0x18005233c  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18005233f  lea     rdx, [rsp+98h+arg_18]; enum MSMSEC_CONNECTION_HEALTH_STATUS *
0x180052347  call    ?SecMgrConnectionHealthCheck@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAW4MSMSEC_CONNECTION_HEALTH_STATUS@@PEAH@Z; SecMgrConnectionHealthCheck(MSMSEC_INTF_CONTEXT *,MSMSEC_CONNECTION_HEALTH_STATUS *,int *)
0x18005234c  mov     ebx, eax
0x18005234e  test    eax, eax
0x180052350  jz      short loc_180052382
0x180052352  mov     rcx, cs:WPP_GLOBAL_Control
0x180052359  cmp     rcx, r12
0x18005235c  jz      loc_1800523FF
0x180052362  test    byte ptr [rcx+44h], 1
0x180052366  jz      loc_1800523FF
0x18005236c  mov     rcx, [rcx+38h]
0x180052370  mov     edx, 0F5h
0x180052375  mov     r9d, eax
0x180052378  mov     r8, rbp
0x18005237b  call    WPP_SF_d
0x180052380  jmp     short loc_1800523FF
0x180052382  mov     esi, [rsp+98h+arg_18]
0x180052389  mov     ebp, [rsp+98h+var_38]
0x18005238d  mov     [r15], esi
0x180052390  mov     [r14], ebp
0x180052393  mov     rcx, cs:WPP_GLOBAL_Control
0x18005239a  cmp     rcx, r12
0x18005239d  jz      short loc_1800523CB
0x18005239f  test    byte ptr [rcx+44h], 2
0x1800523a3  jz      short loc_1800523CB
0x1800523a5  mov     rcx, [rcx+38h]
0x1800523a9  lea     rax, aOther; "Other"
0x1800523b0  cmp     esi, 2
0x1800523b3  mov     dword ptr [rsp+98h+var_70], ebp
0x1800523b7  lea     r9, aHealthy; "Healthy"
0x1800523be  mov     dword ptr [rsp+98h+var_78], esi
0x1800523c2  cmovnz  r9, rax
0x1800523c6  call    WPP_SF_sLL
0x1800523cb  test    cs:byte_1800AED45, 1
0x1800523d2  jz      short loc_1800523F8
0x1800523d4  mov     r8d, [rdi+9C0h]
0x1800523db  lea     r9, [rdi+20h]
0x1800523df  xor     eax, eax
0x1800523e1  mov     [rsp+98h+var_68], ebp
0x1800523e5  cmp     esi, 2
0x1800523e8  mov     dword ptr [rsp+98h+var_70], esi
0x1800523ec  setz    al
0x1800523ef  mov     dword ptr [rsp+98h+var_78], eax
0x1800523f3  call    McTemplateU0qjtqt_EventWriteTransfer
0x1800523f8  lea     rbp, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800523ff  mov     ecx, [rdi+9C0h]; unsigned int
0x180052405  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18005240c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180052411  lea     rdx, [rdi+9D0h]
0x180052418  mov     r9d, 86Ah
0x18005241e  lea     r8, aMsmsecconnecti_0; "MSMSecConnectionHealthCheck"
0x180052425  mov     rcx, rdi
0x180052428  call    cs:__imp_ReleaseWriteLock
0x18005242f  nop     dword ptr [rax+rax+00h]
0x180052434  mov     ecx, [rdi+9C0h]; unsigned int
0x18005243a  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180052441  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180052446  mov     r8d, 86Eh; int
0x18005244c  lea     rdx, aMsmsecconnecti_0; "MSMSecConnectionHealthCheck"
0x180052453  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180052456  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18005245b  jmp     short loc_180052485
0x18005245d  mov     ebx, 57h ; 'W'
0x180052462  mov     rcx, cs:WPP_GLOBAL_Control
0x180052469  cmp     rcx, r12
0x18005246c  jz      short loc_180052485
0x18005246e  test    byte ptr [rcx+44h], 1
0x180052472  jz      short loc_180052485
0x180052474  mov     rcx, [rcx+38h]
0x180052478  mov     edx, 0F1h
0x18005247d  mov     r8, rbp
0x180052480  call    WPP_SF_
0x180052485  mov     edx, 870h; int
0x18005248a  lea     rcx, aMsmsecconnecti_0; "MSMSecConnectionHealthCheck"
0x180052491  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180052496  mov     rcx, cs:WPP_GLOBAL_Control
0x18005249d  cmp     rcx, r12
0x1800524a0  jz      short loc_1800524BF
0x1800524a2  test    dword ptr [rcx+44h], 100h
0x1800524a9  jz      short loc_1800524BF
0x1800524ab  mov     rcx, [rcx+38h]
0x1800524af  mov     edx, 0F7h
0x1800524b4  mov     r9d, ebx
0x1800524b7  mov     r8, rbp
0x1800524ba  call    WPP_SF_d
0x1800524bf  lea     r11, [rsp+98h+var_28]
0x1800524c4  mov     eax, ebx
0x1800524c6  mov     rbx, [r11+30h]
0x1800524ca  mov     rbp, [r11+38h]
0x1800524ce  mov     rsp, r11
0x1800524d1  pop     r15
0x1800524d3  pop     r14
0x1800524d5  pop     r12
0x1800524d7  pop     rdi
0x1800524d8  pop     rsi
0x1800524d9  retn
```
