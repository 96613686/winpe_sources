# _WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal_::_1_::catch$4

- ea: `0x18006bd7c`
- end: `0x18006c1ab`
- name: `_WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal_::_1_::catch$4`
- size: `1071`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x180004466`
- `0x180006780`
- `0x1800067d0`
- `0x18002c7b4`
- `0x18002e20c`
- `0x18003a684`
- `0x1800409c8`
- `0x180053b1c`
- `0x180057efc`
- `0x18005c67c`
- `0x18005c708`
- `0x18005c7f4`
- `0x18005c888`
- `0x18005dec4`
- `0x18006bd7c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006be42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006be42`

## string_xrefs

- `0x18006c054`: `WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal_::_1_::catch_4(__int64 a1, __int64 a2)
{
  int Error; // eax
  __int64 v4; // r10
  int v5; // eax
  __int64 v6; // r10
  ULONGLONG TickCount64; // r9
  unsigned int v8; // edi
  WFDSConMgr::CConnectManager **v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // r14d
  ULONGLONG v12; // rsi
  PVOID *v13; // r10
  WFDSConMgr::CException *v14; // rsi
  int v15; // ecx
  int v16; // eax
  __int64 v17; // r10
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r11
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rax
  WFDSConMgr::CWFDConnectHelper *v23; // rax
  bool v24; // al
  __int64 v25; // r9
  __int64 v26; // r11
  __int64 v27; // r10
  __int64 v28; // r8

  if ( *(_BYTE *)(a2 + 83) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      Error = WFDSConMgr::CException::GetError(*(WFDSConMgr::CException **)(a2 + 120));
      WPP_SF_qD(*(_QWORD *)(v4 + 16), 51, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, *(_QWORD *)(a2 + 96), Error);
    }
    throw;
  }
  if ( *(_BYTE *)(a2 + 81) && !*(_BYTE *)(a2 + 80) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = WFDSConMgr::CException::GetError(*(WFDSConMgr::CException **)(a2 + 120));
      WPP_SF_qD(*(_QWORD *)(v6 + 16), 52, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, *(_QWORD *)(a2 + 96), v5);
    }
    throw;
  }
  TickCount64 = GetTickCount64();
  v8 = *(_DWORD *)(a2 + 108) + 1;
  *(_DWORD *)(a2 + 108) = v8;
  v9 = *(WFDSConMgr::CConnectManager ***)(a2 + 96);
  v10 = *((_QWORD *)v9[1] + 13);
  if ( *(_BYTE *)(v10 + 80) && *(_DWORD *)(v10 + 136) == 163852 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids,
        v9,
        **(_DWORD **)(a2 + 120));
    }
LABEL_52:
    *(_BYTE *)(a2 + 82) = 1;
    WFDSConMgr::CWFDConnectHelper::Reset(*((WFDSConMgr::CWFDConnectHelper **)v9[1] + 13));
    StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(*((WFDSConMgr::CRemoteDevice **)v9[1] + 16));
    WFDSConMgr::CSessionStateMachine::UpdateWFDState(StateMachine, 2);
    return 1;
  }
  v11 = *(_DWORD *)(a2 + 104);
  if ( v8 >= v11 )
  {
    LODWORD(v12) = *(_DWORD *)(a2 + 112);
LABEL_46:
    if ( !*(_BYTE *)(a2 + 84)
      || WFDSConMgr::CWFDConnectHelper::DeviceNotFound(*((WFDSConMgr::CWFDConnectHelper **)v9[1] + 13)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WFDSConMgr::CException::GetError(*(WFDSConMgr::CException **)(a2 + 120));
        v23 = WFDSConMgr::CConnectManager::WFDHelper(v9[1]);
        v24 = WFDSConMgr::CWFDConnectHelper::DeviceNotFound(v23);
        WPP_SF_qdDDIDl(*(_QWORD *)(v27 + 16), v24, v28, v9, v28, v8, v11, v25 - v26, v12, v24);
      }
      throw;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qdDDID(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        **(unsigned int **)(a2 + 120),
        v19,
        v9,
        **(_DWORD **)(a2 + 120),
        v8,
        v11,
        v20 - v21,
        v12);
    }
    goto LABEL_52;
  }
  v12 = *(unsigned int *)(a2 + 112);
  if ( TickCount64 - *(_QWORD *)(a2 + 152) > v12 )
    goto LABEL_46;
  if ( WFDSConMgr::CWFDConnectHelper::DeviceNotFound(*((WFDSConMgr::CWFDConnectHelper **)v9[1] + 13)) )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v14 = *(WFDSConMgr::CException **)(a2 + 120);
    }
    else
    {
      v14 = *(WFDSConMgr::CException **)(a2 + 120);
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids,
        v9,
        *(_DWORD *)v14);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    *(_BYTE *)(a2 + 81) = 1;
    *(_BYTE *)(a2 + 80) = 0;
  }
  else
  {
    v14 = *(WFDSConMgr::CException **)(a2 + 120);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = *(_DWORD *)v14;
  if ( (*(_DWORD *)v14 & 0x1FFF0000) == 0x70000 )
    v15 = (unsigned __int16)v15;
  if ( v15 == 1223 )
  {
    if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = WFDSConMgr::CException::GetError(v14);
      WPP_SF_qD(*(_QWORD *)(v17 + 16), 57, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v9, v16);
    }
    throw;
  }
  if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 3u && (*((_BYTE *)v13 + 28) & 1) != 0 )
    WPP_SF_qDD(v13[2], 58, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v9, *(_DWORD *)v14, v8);
  WFDSConMgr::CWFDConnectHelper::Reset(*((WFDSConMgr::CWFDConnectHelper **)v9[1] + 13));
  WFDSConMgr::CEventWrapper::WaitAllowTimeout(
    v9 + 12,
    a2 + 160,
    *(_DWORD *)(a2 + 116) + *(_DWORD *)(a2 + 136) * (v8 - 1));
  if ( !*(_DWORD *)(a2 + 164) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
      195,
      L"Connect canceled between reconnect retries",
      v9);
  *(_QWORD *)(a2 + 88) = v9;
  WFDSConMgr::TryCatchTelemetry__lambda_2afaf7eeead46479cc35188dddeb75ee___(a2 + 88);
  return 0;
}

```

## disassembly

```asm
0x18006bd7c  mov     [rsp+arg_8], rdx
0x18006bd81  push    rbx
0x18006bd82  push    rbp
0x18006bd83  push    rsi
0x18006bd84  push    rdi
0x18006bd85  push    r14
0x18006bd87  sub     rsp, 50h
0x18006bd8b  mov     rbp, rdx
0x18006bd8e  cmp     byte ptr [rbp+53h], 0
0x18006bd92  jz      short loc_18006BDE5
0x18006bd94  lea     rax, WPP_GLOBAL_Control
0x18006bd9b  mov     r10, cs:WPP_GLOBAL_Control
0x18006bda2  cmp     r10, rax
0x18006bda5  jz      short loc_18006BDDB
0x18006bda7  cmp     byte ptr [r10+19h], 1
0x18006bdac  jb      short loc_18006BDDB
0x18006bdae  test    byte ptr [r10+1Ch], 1
0x18006bdb3  jz      short loc_18006BDDB
0x18006bdb5  mov     rcx, [rbp+78h]; this
0x18006bdb9  call    ?GetError@CException@WFDSConMgr@@QEBAJXZ; WFDSConMgr::CException::GetError(void)
0x18006bdbe  mov     edx, 33h ; '3'
0x18006bdc3  mov     dword ptr [rsp+78h+var_58], eax
0x18006bdc7  mov     r9, [rbp+60h]
0x18006bdcb  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006bdd2  mov     rcx, [r10+10h]
0x18006bdd6  call    WPP_SF_qD
0x18006bddb  xor     edx, edx; pThrowInfo
0x18006bddd  xor     ecx, ecx; pExceptionObject
0x18006bddf  call    _CxxThrowException_0
0x18006bde5  cmp     byte ptr [rbp+51h], 0
0x18006bde9  jz      short loc_18006BE42
0x18006bdeb  cmp     byte ptr [rbp+50h], 0
0x18006bdef  jnz     short loc_18006BE42
0x18006bdf1  lea     rax, WPP_GLOBAL_Control
0x18006bdf8  mov     r10, cs:WPP_GLOBAL_Control
0x18006bdff  cmp     r10, rax
0x18006be02  jz      short loc_18006BE38
0x18006be04  cmp     byte ptr [r10+19h], 1
0x18006be09  jb      short loc_18006BE38
0x18006be0b  test    byte ptr [r10+1Ch], 1
0x18006be10  jz      short loc_18006BE38
0x18006be12  mov     rcx, [rbp+78h]; this
0x18006be16  call    ?GetError@CException@WFDSConMgr@@QEBAJXZ; WFDSConMgr::CException::GetError(void)
0x18006be1b  mov     edx, 34h ; '4'
0x18006be20  mov     dword ptr [rsp+78h+var_58], eax
0x18006be24  mov     r9, [rbp+60h]
0x18006be28  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006be2f  mov     rcx, [r10+10h]
0x18006be33  call    WPP_SF_qD
0x18006be38  xor     edx, edx; pThrowInfo
0x18006be3a  xor     ecx, ecx; pExceptionObject
0x18006be3c  call    _CxxThrowException_0
0x18006be42  call    cs:__imp_GetTickCount64
0x18006be48  mov     r9, rax
0x18006be4b  mov     edi, [rbp+6Ch]
0x18006be4e  inc     edi
0x18006be50  mov     [rbp+6Ch], edi
0x18006be53  mov     rbx, [rbp+60h]
0x18006be57  mov     rcx, [rbx+8]
0x18006be5b  mov     rax, [rcx+68h]
0x18006be5f  cmp     byte ptr [rax+50h], 0
0x18006be63  jz      short loc_18006BEC5
0x18006be65  cmp     dword ptr [rax+88h], 2800Ch
0x18006be6f  jnz     short loc_18006BEC5
0x18006be71  lea     rax, WPP_GLOBAL_Control
0x18006be78  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be7f  cmp     rcx, rax
0x18006be82  jz      loc_18006C0EF
0x18006be88  cmp     byte ptr [rcx+19h], 3
0x18006be8c  jb      loc_18006C0EF
0x18006be92  test    byte ptr [rcx+1Ch], 1
0x18006be96  jz      loc_18006C0EF
0x18006be9c  mov     edx, 35h ; '5'
0x18006bea1  mov     rax, [rbp+78h]
0x18006bea5  mov     r8d, [rax]
0x18006bea8  mov     dword ptr [rsp+78h+var_58], r8d
0x18006bead  mov     r9, rbx
0x18006beb0  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006beb7  mov     rcx, [rcx+10h]
0x18006bebb  call    WPP_SF_qD
0x18006bec0  jmp     loc_18006C0EF
0x18006bec5  mov     r14d, [rbp+68h]
0x18006bec9  mov     r11, [rbp+98h]
0x18006bed0  cmp     edi, r14d
0x18006bed3  jnb     loc_18006C083
0x18006bed9  mov     rcx, r9
0x18006bedc  sub     rcx, r11
0x18006bedf  mov     esi, [rbp+70h]
0x18006bee2  cmp     rcx, rsi
0x18006bee5  ja      loc_18006C086
0x18006beeb  mov     rcx, [rbx+8]
0x18006beef  mov     rcx, [rcx+68h]; this
0x18006bef3  call    ?DeviceNotFound@CWFDConnectHelper@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CWFDConnectHelper::DeviceNotFound(void)
0x18006bef8  test    al, al
0x18006befa  jz      short loc_18006BF56
0x18006befc  lea     rax, WPP_GLOBAL_Control
0x18006bf03  mov     r10, cs:WPP_GLOBAL_Control
0x18006bf0a  cmp     r10, rax
0x18006bf0d  jz      short loc_18006BF48
0x18006bf0f  cmp     byte ptr [r10+19h], 3
0x18006bf14  jb      short loc_18006BF48
0x18006bf16  test    byte ptr [r10+1Ch], 1
0x18006bf1b  jz      short loc_18006BF48
0x18006bf1d  mov     edx, 38h ; '8'
0x18006bf22  mov     rsi, [rbp+78h]
0x18006bf26  mov     eax, [rsi]
0x18006bf28  mov     dword ptr [rsp+78h+var_58], eax
0x18006bf2c  mov     r9, rbx
0x18006bf2f  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006bf36  mov     rcx, [r10+10h]
0x18006bf3a  call    WPP_SF_qD
0x18006bf3f  mov     r10, cs:WPP_GLOBAL_Control
0x18006bf46  jmp     short loc_18006BF4C
0x18006bf48  mov     rsi, [rbp+78h]
0x18006bf4c  mov     byte ptr [rbp+51h], 1
0x18006bf50  mov     byte ptr [rbp+50h], 0
0x18006bf54  jmp     short loc_18006BF61
0x18006bf56  mov     rsi, [rbp+78h]
0x18006bf5a  mov     r10, cs:WPP_GLOBAL_Control
0x18006bf61  mov     ecx, [rsi]
0x18006bf63  mov     eax, ecx
0x18006bf65  and     eax, 1FFF0000h
0x18006bf6a  cmp     eax, 70000h
0x18006bf6f  jnz     short loc_18006BF74
0x18006bf71  movzx   ecx, cx
0x18006bf74  cmp     ecx, 4C7h
0x18006bf7a  jnz     short loc_18006BFC4
0x18006bf7c  lea     rax, WPP_GLOBAL_Control
0x18006bf83  cmp     r10, rax
0x18006bf86  jz      short loc_18006BFBA
0x18006bf88  cmp     byte ptr [r10+19h], 1
0x18006bf8d  jb      short loc_18006BFBA
0x18006bf8f  test    byte ptr [r10+1Ch], 1
0x18006bf94  jz      short loc_18006BFBA
0x18006bf96  mov     rcx, rsi; this
0x18006bf99  call    ?GetError@CException@WFDSConMgr@@QEBAJXZ; WFDSConMgr::CException::GetError(void)
0x18006bf9e  mov     edx, 39h ; '9'
0x18006bfa3  mov     dword ptr [rsp+78h+var_58], eax
0x18006bfa7  mov     r9, rbx
0x18006bfaa  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006bfb1  mov     rcx, [r10+10h]
0x18006bfb5  call    WPP_SF_qD
0x18006bfba  xor     edx, edx; pThrowInfo
0x18006bfbc  xor     ecx, ecx; pExceptionObject
0x18006bfbe  call    _CxxThrowException_0
0x18006bfc4  lea     rax, WPP_GLOBAL_Control
0x18006bfcb  cmp     r10, rax
0x18006bfce  jz      short loc_18006C000
0x18006bfd0  cmp     byte ptr [r10+19h], 3
0x18006bfd5  jb      short loc_18006C000
0x18006bfd7  test    byte ptr [r10+1Ch], 1
0x18006bfdc  jz      short loc_18006C000
0x18006bfde  mov     edx, 3Ah ; ':'
0x18006bfe3  mov     dword ptr [rsp+78h+var_50], edi
0x18006bfe7  mov     eax, [rsi]
0x18006bfe9  mov     dword ptr [rsp+78h+var_58], eax
0x18006bfed  mov     r9, rbx
0x18006bff0  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18006bff7  mov     rcx, [r10+10h]
0x18006bffb  call    WPP_SF_qDD
0x18006c000  mov     rcx, [rbx+8]
0x18006c004  mov     rcx, [rcx+68h]; this
0x18006c008  call    ?Reset@CWFDConnectHelper@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CWFDConnectHelper::Reset(void)
0x18006c00d  lea     r8d, [rdi-1]
0x18006c011  imul    r8d, [rbp+88h]
0x18006c019  add     r8d, [rbp+74h]
0x18006c01d  lea     rcx, [rbx+60h]
0x18006c021  lea     rdx, [rbp+0A0h]
0x18006c028  call    ?WaitAllowTimeout@CEventWrapper@WFDSConMgr@@QEBA?AVCWaitResult@2@K@Z; WFDSConMgr::CEventWrapper::WaitAllowTimeout(ulong)
0x18006c02d  cmp     dword ptr [rbp+0A4h], 0
0x18006c034  jnz     short loc_18006C066
0x18006c036  mov     [rsp+78h+var_50], rbx; void *
0x18006c03b  lea     rax, aConnectCancele; "Connect canceled between reconnect retr"...
0x18006c042  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18006c047  mov     r9d, 4C3h; char
0x18006c04d  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18006c054  lea     rdx, aWfdsconmgrCcon_12; "WFDSConMgr::CConnectWFDOpenSessionWork:"...
0x18006c05b  mov     ecx, 800704C7h; char
0x18006c060  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18006c066  mov     [rbp+58h], rbx
0x18006c06a  lea     rcx, [rbp+58h]
0x18006c06e  call    WFDSConMgr__TryCatchTelemetry__lambda_2afaf7eeead46479cc35188dddeb75ee___
0x18006c073  nop
0x18006c074  mov     rax, 0
0x18006c07e  jmp     loc_18006C19F
0x18006c083  mov     esi, [rbp+70h]
0x18006c086  cmp     byte ptr [rbp+54h], 0
0x18006c08a  jz      loc_18006C12A
0x18006c090  mov     rcx, [rbx+8]
0x18006c094  mov     rcx, [rcx+68h]; this
0x18006c098  call    ?DeviceNotFound@CWFDConnectHelper@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CWFDConnectHelper::DeviceNotFound(void)
0x18006c09d  test    al, al
0x18006c09f  jnz     loc_18006C12A
0x18006c0a5  lea     rax, WPP_GLOBAL_Control
0x18006c0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0b3  cmp     rcx, rax
0x18006c0b6  jz      short loc_18006C0EF
0x18006c0b8  cmp     byte ptr [rcx+19h], 3
0x18006c0bc  jb      short loc_18006C0EF
0x18006c0be  test    byte ptr [rcx+1Ch], 1
0x18006c0c2  jz      short loc_18006C0EF
0x18006c0c4  sub     r9, r11
0x18006c0c7  mov     [rsp+78h+var_38], esi
0x18006c0cb  mov     [rsp+78h+var_40], r9
0x18006c0d0  mov     [rsp+78h+var_48], r14d
0x18006c0d5  mov     dword ptr [rsp+78h+var_50], edi
0x18006c0d9  mov     rax, [rbp+78h]
0x18006c0dd  mov     edx, [rax]
0x18006c0df  mov     dword ptr [rsp+78h+var_58], edx
0x18006c0e3  mov     r9, rbx
0x18006c0e6  mov     rcx, [rcx+10h]
0x18006c0ea  call    WPP_SF_qdDDID
0x18006c0ef  mov     byte ptr [rbp+52h], 1
0x18006c0f3  mov     rcx, [rbx+8]
0x18006c0f7  mov     rcx, [rcx+68h]; this
0x18006c0fb  call    ?Reset@CWFDConnectHelper@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CWFDConnectHelper::Reset(void)
0x18006c100  mov     rcx, [rbx+8]
0x18006c104  mov     rcx, [rcx+80h]; this
0x18006c10b  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x18006c110  mov     edx, 2
0x18006c115  mov     rcx, rax
0x18006c118  call    ?UpdateWFDState@CSessionStateMachine@WFDSConMgr@@QEAA_NW4_WFDSConMgrWFDStatus@@@Z; WFDSConMgr::CSessionStateMachine::UpdateWFDState(_WFDSConMgrWFDStatus)
0x18006c11d  nop
0x18006c11e  mov     rax, 1
0x18006c128  jmp     short loc_18006C19F
0x18006c12a  lea     rax, WPP_GLOBAL_Control
0x18006c131  mov     r10, cs:WPP_GLOBAL_Control
0x18006c138  cmp     r10, rax
0x18006c13b  jz      short loc_18006C195
0x18006c13d  cmp     byte ptr [r10+19h], 1
0x18006c142  jb      short loc_18006C195
0x18006c144  test    byte ptr [r10+1Ch], 1
0x18006c149  jz      short loc_18006C195
0x18006c14b  mov     rcx, [rbp+78h]; this
0x18006c14f  call    ?GetError@CException@WFDSConMgr@@QEBAJXZ; WFDSConMgr::CException::GetError(void)
0x18006c154  mov     r8d, eax
0x18006c157  mov     rcx, [rbx+8]; this
0x18006c15b  call    ?WFDHelper@CConnectManager@WFDSConMgr@@QEAAAEAVCWFDConnectHelper@2@XZ; WFDSConMgr::CConnectManager::WFDHelper(void)
0x18006c160  mov     rcx, rax; this
0x18006c163  call    ?DeviceNotFound@CWFDConnectHelper@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CWFDConnectHelper::DeviceNotFound(void)
0x18006c168  movzx   edx, al
0x18006c16b  sub     r9, r11
0x18006c16e  mov     [rsp+78h+var_30], edx
0x18006c172  mov     [rsp+78h+var_38], esi
0x18006c176  mov     [rsp+78h+var_40], r9
0x18006c17b  mov     [rsp+78h+var_48], r14d
0x18006c180  mov     dword ptr [rsp+78h+var_50], edi
0x18006c184  mov     dword ptr [rsp+78h+var_58], r8d
0x18006c189  mov     r9, rbx
0x18006c18c  mov     rcx, [r10+10h]
0x18006c190  call    WPP_SF_qdDDIDl
0x18006c195  xor     edx, edx; pThrowInfo
0x18006c197  xor     ecx, ecx; pExceptionObject
0x18006c199  call    _CxxThrowException_0
0x18006c19f  add     rsp, 50h
0x18006c1a3  pop     r14
0x18006c1a5  pop     rdi
0x18006c1a6  pop     rsi
0x18006c1a7  pop     rbp
0x18006c1a8  pop     rbx
0x18006c1a9  retn
```
