# WLGeneric_DwmControl_Enter(_StateMachineCallContext *)

- ea: `0x140084aa0`
- end: `0x140084e0c`
- name: `?WLGeneric_DwmControl_Enter@@YAXPEAU_StateMachineCallContext@@@Z`
- size: `876`
- prototype: `void __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1400057f4`
- `0x14002ba10`
- `0x1400333b0`
- `0x140041c34`
- `0x14004ec2c`
- `0x140050984`
- `0x140056bd8`
- `0x14005b630`
- `0x14005d698`
- `0x140083e20`
- `0x140083ee0`
- `0x140083fa4`
- `0x140084044`
- `0x140084aa0`

## import_xrefs

- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x140084bc0`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x140084d0b`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x140084bc0`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x140084d0b`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x140084b63`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x140084d94`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x140084b63`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x140084d94`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogon` at `0x140084c61`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogon` at `0x140084c7c`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogon` at `0x140084c61`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogon` at `0x140084c7c`

## string_xrefs

- `0x140084cf8`: `DwmpCreateSessionProcess`
- `0x140084d14`: `DwmpCreateSessionProcess`

## pseudocode

```c
void __fastcall WLGeneric_DwmControl_Enter(struct _StateMachineCallContext *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  unsigned int v6; // esi
  __int64 v7; // rdi
  int v8; // ebx
  int v9; // ebx
  int v10; // eax
  int SessionProcess; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  _DWORD v18[8]; // [rsp+20h] [rbp-20h] BYREF
  int v19; // [rsp+70h] [rbp+30h] BYREF
  int v20; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids, a4);
  }
  v5 = *((_DWORD *)a1 + 12);
  v6 = *((_DWORD *)a1 + 13);
  v7 = *((_QWORD *)a1 + 1);
  if ( (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent()
    && (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent()
    && (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent()
    && (unsigned int)CSession::IsDwmRequiredInSession(*(CSession **)(v7 + 16)) )
  {
    if ( !v5 )
    {
      WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Start);
      RecordBlackboxInfo(L"DwmpTerminateSessionProcess", 1, (struct _WLSM_GLOBAL_CONTEXT *)v7);
      v20 = DwmpTerminateSessionProcess(v6);
      v17 = v20;
      RecordBlackboxInfo(L"DwmpTerminateSessionProcess", 0, (struct _WLSM_GLOBAL_CONTEXT *)v7);
      if ( v17 < 0
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids,
          (unsigned int)v17);
      }
      WinlogonProvider::DwmpTerminateSessionProcess<long &>(&v20);
      v12 = &WLEvt_DwmpTerminateSessionProcess_Stop;
      goto LABEL_48;
    }
    v8 = v5 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
      {
        v13 = 0;
        WLEventWrite(&WLEvt_DwmpNotifyUserLogon_Start);
        v14 = *(_QWORD *)(v7 + 32);
        if ( v14 )
          v13 = *(_QWORD *)(v14 + 136);
        RecordBlackboxInfo(L"DwmpNotifyUserLogon", 1, (struct _WLSM_GLOBAL_CONTEXT *)v7);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(v18, 1);
          v15 = DwmpNotifyUserLogon(v13);
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v18);
        }
        else
        {
          v15 = DwmpNotifyUserLogon(v13);
        }
        v20 = v15;
        RecordBlackboxInfo(L"DwmpNotifyUserLogon", 0, (struct _WLSM_GLOBAL_CONTEXT *)v7);
        if ( v15 < 0
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids,
            (unsigned int)v15);
        }
        WinlogonProvider::DwmpNotifyUserLogon<long &>(&v20);
        v12 = (const struct _EVENT_DESCRIPTOR *)WLEvt_DwmpNotifyUserLogon_Stop;
        goto LABEL_48;
      }
      if ( v9 != 1 )
        return;
      WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Start);
      v10 = DwmpTerminateSessionProcess(v6);
      v20 = v10;
      if ( v10 < 0
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids,
          (unsigned int)v10);
      }
      WinlogonProvider::DwmpTerminateSessionProcess<long &>(&v20);
      WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Stop);
      WLEventWrite(&WLEvt_DwmpCreateSessionProcess_Start);
      SessionProcess = DwmpCreateSessionProcess(0);
      v20 = SessionProcess;
      if ( SessionProcess < 0
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids,
          (unsigned int)SessionProcess);
      }
      v19 = 1;
      WinlogonProvider::DwmpCreateSessionProcess<int,long &>(&v19, &v20);
    }
    else
    {
      WLEventWrite(&WLEvt_DwmpCreateSessionProcess_Start);
      RecordBlackboxInfo(L"DwmpCreateSessionProcess", 1, (struct _WLSM_GLOBAL_CONTEXT *)v7);
      v20 = DwmpCreateSessionProcess(v6);
      v16 = v20;
      RecordBlackboxInfo(L"DwmpCreateSessionProcess", 0, (struct _WLSM_GLOBAL_CONTEXT *)v7);
      if ( v16 < 0
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids,
          (unsigned int)v16);
      }
      LOBYTE(v19) = v6 != 0;
      WinlogonProvider::DwmpCreateSessionProcess<bool,long &>(&v19, &v20);
    }
    v12 = &WLEvt_DwmpCreateSessionProcess_Stop;
LABEL_48:
    WLEventWrite(v12);
  }
}

```

## disassembly

```asm
0x140084aa0  mov     [rsp-28h+arg_10], rbx
0x140084aa5  push    rbp
0x140084aa6  push    rsi
0x140084aa7  push    rdi
0x140084aa8  push    r14
0x140084aaa  push    r15
0x140084aac  mov     rbp, rsp
0x140084aaf  sub     rsp, 40h
0x140084ab3  mov     rdi, rcx
0x140084ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140084abd  lea     r14, WPP_GLOBAL_Control
0x140084ac4  lea     r15, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140084acb  cmp     rcx, r14
0x140084ace  jz      short loc_140084AF0
0x140084ad0  test    dword ptr [rcx+1Ch], 100h
0x140084ad7  jz      short loc_140084AF0
0x140084ad9  cmp     byte ptr [rcx+19h], 4
0x140084add  jb      short loc_140084AF0
0x140084adf  mov     rcx, [rcx+10h]
0x140084ae3  mov     edx, 3Eh ; '>'
0x140084ae8  mov     r8, r15
0x140084aeb  call    WPP_SF_
0x140084af0  mov     ebx, [rdi+30h]
0x140084af3  mov     esi, [rdi+34h]
0x140084af6  mov     rdi, [rdi+8]
0x140084afa  call    IsDwmpStartWinlogonMouseThreadPresent
0x140084aff  test    al, al
0x140084b01  jz      loc_140084DF8
0x140084b07  call    IsDwmpStartWinlogonMouseThreadPresent
0x140084b0c  test    al, al
0x140084b0e  jz      loc_140084DF8
0x140084b14  call    IsDwmpStartWinlogonMouseThreadPresent
0x140084b19  test    al, al
0x140084b1b  jz      loc_140084DF8
0x140084b21  mov     rcx, [rdi+10h]; this
0x140084b25  call    ?IsDwmRequiredInSession@CSession@@QEAAHXZ; CSession::IsDwmRequiredInSession(void)
0x140084b2a  test    eax, eax
0x140084b2c  jz      loc_140084DF8
0x140084b32  test    ebx, ebx
0x140084b34  jz      loc_140084D72
0x140084b3a  sub     ebx, 1
0x140084b3d  jz      loc_140084CE9
0x140084b43  sub     ebx, 1
0x140084b46  jz      loc_140084C1C
0x140084b4c  cmp     ebx, 1
0x140084b4f  jnz     loc_140084DF8
0x140084b55  lea     rcx, WLEvt_DwmpTerminateSessionProcess_Start; struct _EVENT_DESCRIPTOR *
0x140084b5c  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084b61  mov     ecx, esi
0x140084b63  call    cs:__imp_DwmpTerminateSessionProcess
0x140084b69  mov     [rbp+arg_8], eax
0x140084b6c  test    eax, eax
0x140084b6e  jns     short loc_140084B9D
0x140084b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140084b77  cmp     rcx, r14
0x140084b7a  jz      short loc_140084B9D
0x140084b7c  test    dword ptr [rcx+1Ch], 100000h
0x140084b83  jz      short loc_140084B9D
0x140084b85  cmp     byte ptr [rcx+19h], 2
0x140084b89  jb      short loc_140084B9D
0x140084b8b  mov     rcx, [rcx+10h]
0x140084b8f  lea     edx, [rbx+41h]
0x140084b92  mov     r9d, eax
0x140084b95  mov     r8, r15
0x140084b98  call    WPP_SF_d
0x140084b9d  lea     rcx, [rbp+arg_8]
0x140084ba1  call    ??$DwmpTerminateSessionProcess@AEAJ@WinlogonProvider@@SAXAEAJ@Z; WinlogonProvider::DwmpTerminateSessionProcess<long &>(long &)
0x140084ba6  lea     rcx, WLEvt_DwmpTerminateSessionProcess_Stop; struct _EVENT_DESCRIPTOR *
0x140084bad  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084bb2  lea     rcx, WLEvt_DwmpCreateSessionProcess_Start; struct _EVENT_DESCRIPTOR *
0x140084bb9  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084bbe  xor     ecx, ecx
0x140084bc0  call    cs:__imp_DwmpCreateSessionProcess
0x140084bc6  mov     [rbp+arg_8], eax
0x140084bc9  test    eax, eax
0x140084bcb  jns     short loc_140084BFC
0x140084bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140084bd4  cmp     rcx, r14
0x140084bd7  jz      short loc_140084BFC
0x140084bd9  test    dword ptr [rcx+1Ch], 100000h
0x140084be0  jz      short loc_140084BFC
0x140084be2  cmp     byte ptr [rcx+19h], 2
0x140084be6  jb      short loc_140084BFC
0x140084be8  mov     rcx, [rcx+10h]
0x140084bec  mov     edx, 43h ; 'C'
0x140084bf1  mov     r9d, eax
0x140084bf4  mov     r8, r15
0x140084bf7  call    WPP_SF_d
0x140084bfc  lea     rdx, [rbp+arg_8]
0x140084c00  mov     [rbp+arg_0], 1
0x140084c07  lea     rcx, [rbp+arg_0]
0x140084c0b  call    ??$DwmpCreateSessionProcess@HAEAJ@WinlogonProvider@@SAX$$QEAHAEAJ@Z; WinlogonProvider::DwmpCreateSessionProcess<int,long &>(int &&,long &)
0x140084c10  lea     rcx, WLEvt_DwmpCreateSessionProcess_Stop
0x140084c17  jmp     loc_140084DF3
0x140084c1c  lea     rcx, WLEvt_DwmpNotifyUserLogon_Start; struct _EVENT_DESCRIPTOR *
0x140084c23  xor     ebx, ebx
0x140084c25  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084c2a  mov     rax, [rdi+20h]
0x140084c2e  test    rax, rax
0x140084c31  jz      short loc_140084C3A
0x140084c33  mov     rbx, [rax+88h]
0x140084c3a  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084c3d  lea     rcx, aDwmpnotifyuser_1; "DwmpNotifyUserLogon"
0x140084c44  mov     edx, 1; int
0x140084c49  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084c4e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl(void)'::`2'::impl
0x140084c55  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(void)
0x140084c5a  test    al, al
0x140084c5c  jnz     short loc_140084C6B
0x140084c5e  mov     rcx, rbx
0x140084c61  call    cs:__imp_DwmpNotifyUserLogon
0x140084c67  mov     ebx, eax
0x140084c69  jmp     short loc_140084C8D
0x140084c6b  mov     edx, 1
0x140084c70  lea     rcx, [rbp+var_20]
0x140084c74  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140084c79  mov     rcx, rbx
0x140084c7c  call    cs:__imp_DwmpNotifyUserLogon
0x140084c82  lea     rcx, [rbp+var_20]; this
0x140084c86  mov     ebx, eax
0x140084c88  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x140084c8d  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084c90  mov     [rbp+arg_8], ebx
0x140084c93  xor     edx, edx; int
0x140084c95  lea     rcx, aDwmpnotifyuser_1; "DwmpNotifyUserLogon"
0x140084c9c  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084ca1  test    ebx, ebx
0x140084ca3  jns     short loc_140084CD4
0x140084ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x140084cac  cmp     rcx, r14
0x140084caf  jz      short loc_140084CD4
0x140084cb1  test    dword ptr [rcx+1Ch], 100000h
0x140084cb8  jz      short loc_140084CD4
0x140084cba  cmp     byte ptr [rcx+19h], 2
0x140084cbe  jb      short loc_140084CD4
0x140084cc0  mov     rcx, [rcx+10h]
0x140084cc4  mov     edx, 41h ; 'A'
0x140084cc9  mov     r9d, ebx
0x140084ccc  mov     r8, r15
0x140084ccf  call    WPP_SF_d
0x140084cd4  lea     rcx, [rbp+arg_8]
0x140084cd8  call    ??$DwmpNotifyUserLogon@AEAJ@WinlogonProvider@@SAXAEAJ@Z; WinlogonProvider::DwmpNotifyUserLogon<long &>(long &)
0x140084cdd  lea     rcx, WLEvt_DwmpNotifyUserLogon_Stop
0x140084ce4  jmp     loc_140084DF3
0x140084ce9  lea     rcx, WLEvt_DwmpCreateSessionProcess_Start; struct _EVENT_DESCRIPTOR *
0x140084cf0  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084cf5  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084cf8  lea     rcx, aDwmpcreatesess_0; "DwmpCreateSessionProcess"
0x140084cff  mov     edx, 1; int
0x140084d04  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084d09  mov     ecx, esi
0x140084d0b  call    cs:__imp_DwmpCreateSessionProcess
0x140084d11  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084d14  lea     rcx, aDwmpcreatesess_0; "DwmpCreateSessionProcess"
0x140084d1b  xor     edx, edx; int
0x140084d1d  mov     [rbp+arg_8], eax
0x140084d20  mov     ebx, eax
0x140084d22  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084d27  test    ebx, ebx
0x140084d29  jns     short loc_140084D5A
0x140084d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140084d32  cmp     rcx, r14
0x140084d35  jz      short loc_140084D5A
0x140084d37  test    dword ptr [rcx+1Ch], 100000h
0x140084d3e  jz      short loc_140084D5A
0x140084d40  cmp     byte ptr [rcx+19h], 2
0x140084d44  jb      short loc_140084D5A
0x140084d46  mov     rcx, [rcx+10h]
0x140084d4a  mov     edx, 3Fh ; '?'
0x140084d4f  mov     r9d, ebx
0x140084d52  mov     r8, r15
0x140084d55  call    WPP_SF_d
0x140084d5a  test    esi, esi
0x140084d5c  lea     rdx, [rbp+arg_8]
0x140084d60  lea     rcx, [rbp+arg_0]
0x140084d64  setnz   byte ptr [rbp+arg_0]
0x140084d68  call    ??$DwmpCreateSessionProcess@_NAEAJ@WinlogonProvider@@SAX$$QEA_NAEAJ@Z; WinlogonProvider::DwmpCreateSessionProcess<bool,long &>(bool &&,long &)
0x140084d6d  jmp     loc_140084C10
0x140084d72  lea     rcx, WLEvt_DwmpTerminateSessionProcess_Start; struct _EVENT_DESCRIPTOR *
0x140084d79  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084d7e  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084d81  lea     rcx, aDwmpterminates_0; "DwmpTerminateSessionProcess"
0x140084d88  mov     edx, 1; int
0x140084d8d  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084d92  mov     ecx, esi
0x140084d94  call    cs:__imp_DwmpTerminateSessionProcess
0x140084d9a  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140084d9d  lea     rcx, aDwmpterminates_0; "DwmpTerminateSessionProcess"
0x140084da4  xor     edx, edx; int
0x140084da6  mov     [rbp+arg_8], eax
0x140084da9  mov     ebx, eax
0x140084dab  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140084db0  test    ebx, ebx
0x140084db2  jns     short loc_140084DE3
0x140084db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140084dbb  cmp     rcx, r14
0x140084dbe  jz      short loc_140084DE3
0x140084dc0  test    dword ptr [rcx+1Ch], 100000h
0x140084dc7  jz      short loc_140084DE3
0x140084dc9  cmp     byte ptr [rcx+19h], 2
0x140084dcd  jb      short loc_140084DE3
0x140084dcf  mov     rcx, [rcx+10h]
0x140084dd3  mov     edx, 40h ; '@'
0x140084dd8  mov     r9d, ebx
0x140084ddb  mov     r8, r15
0x140084dde  call    WPP_SF_d
0x140084de3  lea     rcx, [rbp+arg_8]
0x140084de7  call    ??$DwmpTerminateSessionProcess@AEAJ@WinlogonProvider@@SAXAEAJ@Z; WinlogonProvider::DwmpTerminateSessionProcess<long &>(long &)
0x140084dec  lea     rcx, WLEvt_DwmpTerminateSessionProcess_Stop; struct _EVENT_DESCRIPTOR *
0x140084df3  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140084df8  mov     rbx, [rsp+40h+arg_10]
0x140084e00  add     rsp, 40h
0x140084e04  pop     r15
0x140084e06  pop     r14
0x140084e08  pop     rdi
0x140084e09  pop     rsi
0x140084e0a  pop     rbp
0x140084e0b  retn
```
