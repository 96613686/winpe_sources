# s_wscUpdateProductSubStatus

- ea: `0x180026450`
- end: `0x1800267dc`
- name: `s_wscUpdateProductSubStatus`
- size: `908`
- prototype: `__int64 __fastcall(void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002e30`
- `0x1800070f0`
- `0x180008e48`
- `0x180018b60`
- `0x180019850`
- `0x18001b170`
- `0x18001b870`
- `0x18001c6dc`
- `0x18001fdd8`
- `0x1800202e8`
- `0x1800250c0`
- `0x180026450`
- `0x180031cd0`
- `0x180031efc`
- `0x180035518`
- `0x180042010`

## string_xrefs

- `0x1800264fd`: `s_wscUpdateProductSubStatus`

## pseudocode

```c
__int64 __fastcall s_wscUpdateProductSubStatus(void *a1, unsigned int a2, int a3)
{
  CThirdPartyManager *v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  CThirdPartyManager *v10; // rsi
  unsigned int v11; // r14d
  struct CThirdPartyManager *v12; // r8
  int v13; // edi
  unsigned int v14; // eax
  CThirdPartyManager *v15; // rcx
  int v16; // eax
  const wchar_t *v17; // r9
  void *v18; // r8
  int updated; // eax
  int IsAlerted; // eax
  struct CExternalBase *v22; // [rsp+40h] [rbp-48h] BYREF
  WscServiceUtils *v23; // [rsp+A0h] [rbp+18h] BYREF
  int v24; // [rsp+A8h] [rbp+20h] BYREF

  v22 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 <= 3 )
  {
    switch ( a2 )
    {
      case 0u:
      case 1u:
      case 2u:
        v24 = 0;
        LODWORD(v23) = 0;
        v8 = ValidateCallerAMPPL((int *)&v23, &v24, a1, L"s_wscUpdateProductSubStatus", 0, 0);
        v9 = (unsigned __int16)v8;
        if ( v8 >= 0 )
          v9 = v24;
        if ( v9 )
        {
          WppLogUnregisterNonCompliantProduct(a1);
          s_wscUnregisterSecurityProduct(a1, SECURITY_PRODUCT_TYPE_ANTIVIRUS);
LABEL_34:
          v15 = WPP_GLOBAL_Control;
          goto LABEL_35;
        }
        v10 = WscServiceUtils::g_pAntiVirusManager;
        v11 = 1;
        v12 = WscServiceUtils::g_pAntiVirusVerificationManager;
        v13 = 0;
LABEL_15:
        v14 = WscServiceUtils::CreateExternalBaseFromCaller(a1, v10, v12, &v22);
        v9 = v14;
        if ( v14 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v14);
            goto LABEL_34;
          }
        }
        else
        {
          v16 = CThirdPartyManager::PopulateProductRegistrationInformation(v10, v22);
          if ( v16 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              if ( v13 )
                v17 = L"FW";
              else
                v17 = L"AV";
              WPP_SF_SSDd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                228,
                *((_QWORD *)v22 + 2),
                (_DWORD)v17,
                *((_QWORD *)v22 + 2),
                a3,
                a2);
            }
            CExternalBase::SetSubStatus(v22, a2, (unsigned int)a3);
            WscServiceUtils::CheckAndAddNonCompliantProduct((WscServiceUtils *)(unsigned int)v23, (int)a1, v18);
            updated = CThirdPartyManager::UpdateExternalProduct(v10, v22);
            if ( updated < 0 )
            {
              v9 = (unsigned __int16)updated;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  230,
                  WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                  (unsigned int)updated);
              }
            }
            IsAlerted = CThirdPartyManager::IsAlerted(v10);
            CAlertStatus::SetComponentAlerted(g_pAlertStatus, v11, IsAlerted);
            CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
            goto LABEL_34;
          }
          v9 = 2;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              229,
              WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
              (unsigned int)v16);
            goto LABEL_34;
          }
        }
LABEL_35:
        if ( v22 )
        {
          (**(void (__fastcall ***)(struct CExternalBase *, __int64))v22)(v22, 1);
          v15 = WPP_GLOBAL_Control;
        }
        if ( v15 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)v15 + 2), 231, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v9);
        return v9;
      case 3u:
      case 4u:
      case 5u:
        v10 = WscServiceUtils::g_pFirewallManager;
        v13 = 1;
        v12 = WscServiceUtils::g_pFirewallVerificationManager;
        v11 = 2;
        LODWORD(v23) = 0;
        goto LABEL_15;
      default:
        if ( v6 == (CThirdPartyManager *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 )
          return 87;
        v7 = 225;
        goto LABEL_44;
    }
  }
  if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
  {
    v7 = 224;
LABEL_44:
    WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
  }
  return 87;
}

```

## disassembly

```asm
0x180026450  push    rbp
0x180026452  push    rdi
0x180026453  push    r12
0x180026455  push    r13
0x180026457  push    r15
0x180026459  sub     rsp, 60h
0x18002645d  xor     r13d, r13d
0x180026460  movsxd  r15, edx
0x180026463  mov     [rsp+88h+var_48], r13
0x180026468  mov     r12d, r8d
0x18002646b  mov     rbp, rcx
0x18002646e  mov     r9, cs:WPP_GLOBAL_Control
0x180026475  lea     rdi, WPP_GLOBAL_Control
0x18002647c  cmp     r9, rdi
0x18002647f  jz      short loc_1800264A4
0x180026481  test    byte ptr [r9+1Ch], 8
0x180026486  jz      short loc_1800264A4
0x180026488  mov     rcx, [r9+10h]
0x18002648c  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180026493  mov     edx, 0DFh
0x180026498  call    WPP_SF_
0x18002649d  mov     r9, cs:WPP_GLOBAL_Control
0x1800264a4  mov     [rsp+88h+arg_0], rbx
0x1800264ac  mov     [rsp+88h+var_30], rsi
0x1800264b1  mov     [rsp+88h+var_38], r14
0x1800264b6  cmp     r12d, 3
0x1800264ba  jle     short loc_1800264DA
0x1800264bc  cmp     r9, rdi
0x1800264bf  jz      loc_18002679E
0x1800264c5  test    byte ptr [r9+1Ch], 1
0x1800264ca  jz      loc_18002679E
0x1800264d0  mov     edx, 0E0h
0x1800264d5  jmp     loc_18002678E
0x1800264da  cmp     r15d, 5; switch 6 cases
0x1800264de  ja      def_1800264F6; jumptable 00000001800264F6 default case
0x1800264e4  lea     rdx, __ImageBase
0x1800264eb  mov     ecx, ds:(jpt_1800264F6 - 180000000h)[rdx+r15*4]
0x1800264f3  add     rcx, rdx
0x1800264f6  jmp     rcx; switch jump
0x1800264f8  mov     [rsp+88h+var_60], r13; jumptable 00000001800264F6 cases 0-2
0x1800264fd  lea     r9, aSWscupdateprod; "s_wscUpdateProductSubStatus"
0x180026504  mov     r8, rbp; void *
0x180026507  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x18002650c  lea     rdx, [rsp+88h+arg_18]; int *
0x180026514  mov     [rsp+88h+arg_18], r13d
0x18002651c  lea     rcx, [rsp+88h+arg_10]; int *
0x180026524  mov     dword ptr [rsp+88h+arg_10], r13d
0x18002652c  call    ?ValidateCallerAMPPL@@YAJPEAJ0PEAXPEBG22@Z; ValidateCallerAMPPL(long *,long *,void *,ushort const *,ushort const *,ushort const *)
0x180026531  movzx   ebx, ax
0x180026534  test    eax, eax
0x180026536  js      short loc_18002653F
0x180026538  mov     ebx, [rsp+88h+arg_18]
0x18002653f  test    ebx, ebx
0x180026541  jz      short loc_18002655A
0x180026543  mov     rcx, rbp; void *
0x180026546  call    ?WppLogUnregisterNonCompliantProduct@@YAJPEAX@Z; WppLogUnregisterNonCompliantProduct(void *)
0x18002654b  xor     edx, edx; enum _SECURITY_PRODUCT_TYPE
0x18002654d  mov     rcx, rbp; void *
0x180026550  call    s_wscUnregisterSecurityProduct
0x180026555  jmp     loc_18002672B
0x18002655a  mov     rsi, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180026561  mov     r14d, 1
0x180026567  mov     r8, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; CSecurityVerificationManagerAv * WscServiceUtils::g_pAntiVirusVerificationManager
0x18002656e  mov     edi, r13d
0x180026571  jmp     short loc_180026594
0x180026573  mov     rsi, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; jumptable 00000001800264F6 cases 3-5
0x18002657a  mov     edi, 1
0x18002657f  mov     r8, cs:?g_pFirewallVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerFw@@EA; struct CThirdPartyManager *
0x180026586  mov     r14d, 2
0x18002658c  mov     dword ptr [rsp+88h+arg_10], r13d
0x180026594  lea     r9, [rsp+88h+var_48]; struct CSecurityVerificationManager *
0x180026599  mov     rdx, rsi; void *
0x18002659c  mov     rcx, rbp; ClientBinding
0x18002659f  call    ?CreateExternalBaseFromCaller@WscServiceUtils@@YAJPEAXPEAVCThirdPartyManager@@PEAVCSecurityVerificationManager@@PEAPEAVCExternalBase@@@Z; WscServiceUtils::CreateExternalBaseFromCaller(void *,CThirdPartyManager *,CSecurityVerificationManager *,CExternalBase * *)
0x1800265a4  mov     ebx, eax
0x1800265a6  test    eax, eax
0x1800265a8  jz      short loc_1800265E8
0x1800265aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265b1  lea     rdi, WPP_GLOBAL_Control
0x1800265b8  cmp     rcx, rdi
0x1800265bb  jz      loc_180026732
0x1800265c1  test    byte ptr [rcx+1Ch], 1
0x1800265c5  jz      loc_180026732
0x1800265cb  mov     rcx, [rcx+10h]
0x1800265cf  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800265d6  mov     edx, 0E3h
0x1800265db  mov     r9d, eax
0x1800265de  call    WPP_SF_d
0x1800265e3  jmp     loc_18002672B
0x1800265e8  mov     rdx, [rsp+88h+var_48]; struct CExternalBase *
0x1800265ed  mov     rcx, rsi; this
0x1800265f0  call    ?PopulateProductRegistrationInformation@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::PopulateProductRegistrationInformation(CExternalBase *)
0x1800265f5  test    eax, eax
0x1800265f7  js      loc_1800266F5
0x1800265fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180026604  lea     rax, WPP_GLOBAL_Control
0x18002660b  cmp     rcx, rax
0x18002660e  jz      short loc_18002665E
0x180026610  test    byte ptr [rcx+1Ch], 4
0x180026614  jz      short loc_18002665E
0x180026616  mov     rax, [rsp+88h+var_48]
0x18002661b  mov     r8, [rax+10h]
0x18002661f  test    edi, edi
0x180026621  jnz     short loc_18002662C
0x180026623  lea     r9, aAv; "AV"
0x18002662a  jmp     short loc_180026641
0x18002662c  cmp     edi, 1
0x18002662f  lea     r9, aFw; "FW"
0x180026636  lea     rax, aAs; "AS"
0x18002663d  cmovnz  r9, rax
0x180026641  mov     rcx, [rcx+10h]
0x180026645  mov     edx, 0E4h
0x18002664a  mov     [rsp+88h+var_58], r15d
0x18002664f  mov     dword ptr [rsp+88h+var_60], r12d
0x180026654  mov     [rsp+88h+var_68], r8
0x180026659  call    WPP_SF_SSDd
0x18002665e  mov     rcx, [rsp+88h+var_48]
0x180026663  mov     r8d, r12d
0x180026666  mov     edx, r15d
0x180026669  call    ?SetSubStatus@CExternalBase@@QEAAHW4WSC_SECURITY_SUBSTATUS_TYPE@@W4WSC_SECURITY_PRODUCT_SUBSTATUS@@@Z; CExternalBase::SetSubStatus(WSC_SECURITY_SUBSTATUS_TYPE,WSC_SECURITY_PRODUCT_SUBSTATUS)
0x18002666e  mov     ecx, dword ptr [rsp+88h+arg_10]; this
0x180026675  mov     rdx, rbp; int
0x180026678  call    ?CheckAndAddNonCompliantProduct@WscServiceUtils@@YAJJPEAX@Z; WscServiceUtils::CheckAndAddNonCompliantProduct(long,void *)
0x18002667d  mov     rdx, [rsp+88h+var_48]; struct CExternalBase *
0x180026682  mov     rcx, rsi; this
0x180026685  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x18002668a  test    eax, eax
0x18002668c  jns     short loc_1800266C4
0x18002668e  movzx   ebx, ax
0x180026691  mov     rcx, cs:WPP_GLOBAL_Control
0x180026698  lea     rdi, WPP_GLOBAL_Control
0x18002669f  cmp     rcx, rdi
0x1800266a2  jz      short loc_1800266CB
0x1800266a4  test    byte ptr [rcx+1Ch], 1
0x1800266a8  jz      short loc_1800266CB
0x1800266aa  mov     rcx, [rcx+10h]
0x1800266ae  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800266b5  mov     edx, 0E6h
0x1800266ba  mov     r9d, eax
0x1800266bd  call    WPP_SF_d
0x1800266c2  jmp     short loc_1800266CB
0x1800266c4  lea     rdi, WPP_GLOBAL_Control
0x1800266cb  mov     rcx, rsi; this
0x1800266ce  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x1800266d3  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x1800266da  mov     r8d, eax; int
0x1800266dd  mov     edx, r14d; unsigned int
0x1800266e0  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x1800266e5  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x1800266ec  xor     edx, edx; int
0x1800266ee  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x1800266f3  jmp     short loc_18002672B
0x1800266f5  mov     ebx, 2
0x1800266fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180026701  lea     rdi, WPP_GLOBAL_Control
0x180026708  cmp     rcx, rdi
0x18002670b  jz      short loc_180026732
0x18002670d  test    byte ptr [rcx+1Ch], 1
0x180026711  jz      short loc_180026732
0x180026713  mov     rcx, [rcx+10h]
0x180026717  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18002671e  mov     edx, 0E5h
0x180026723  mov     r9d, eax
0x180026726  call    WPP_SF_d
0x18002672b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026732  mov     r8, [rsp+88h+var_48]
0x180026737  test    r8, r8
0x18002673a  jz      short loc_180026756
0x18002673c  mov     rax, [r8]
0x18002673f  mov     edx, 1
0x180026744  mov     rcx, r8
0x180026747  mov     rax, [rax]
0x18002674a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002674f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026756  cmp     rcx, rdi
0x180026759  jz      short loc_180026779
0x18002675b  test    byte ptr [rcx+1Ch], 8
0x18002675f  jz      short loc_180026779
0x180026761  mov     rcx, [rcx+10h]
0x180026765  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18002676c  mov     edx, 0E7h
0x180026771  mov     r9d, ebx
0x180026774  call    WPP_SF_d
0x180026779  mov     eax, ebx
0x18002677b  jmp     short loc_1800267A3
0x18002677d  cmp     r9, rdi; jumptable 00000001800264F6 default case
0x180026780  jz      short loc_18002679E
0x180026782  test    byte ptr [r9+1Ch], 1
0x180026787  jz      short loc_18002679E
0x180026789  mov     edx, 0E1h
0x18002678e  mov     rcx, [r9+10h]
0x180026792  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180026799  call    WPP_SF_
0x18002679e  mov     eax, 57h ; 'W'
0x1800267a3  mov     r14, [rsp+88h+var_38]
0x1800267a8  mov     rsi, [rsp+88h+var_30]
0x1800267ad  mov     rbx, [rsp+88h+arg_0]
0x1800267b5  add     rsp, 60h
0x1800267b9  pop     r15
0x1800267bb  pop     r13
0x1800267bd  pop     r12
0x1800267bf  pop     rdi
0x1800267c0  pop     rbp
0x1800267c1  retn
```
