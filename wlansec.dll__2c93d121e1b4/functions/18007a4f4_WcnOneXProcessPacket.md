# WcnOneXProcessPacket

- ea: `0x18007a4f4`
- end: `0x18007ab73`
- name: `WcnOneXProcessPacket`
- size: `1663`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180074cc8`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x1800198d4`
- `0x180079dac`
- `0x18007a4f4`
- `0x18007b11c`
- `0x18007b1a0`
- `0x18007befc`
- `0x18007c42c`
- `0x18007c968`
- `0x18007d608`
- `0x18007d6c0`
- `0x18007d904`
- `0x18007dc3c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aa4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aa4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa65`
- `MobileNetworking!FreeMemory` at `0x18007a5d1`
- `MobileNetworking!FreeMemory` at `0x18007a5d1`
- `MobileNetworking!ReleaseReadLock` at `0x18007a5ea`
- `MobileNetworking!ReleaseReadLock` at `0x18007ab24`
- `MobileNetworking!ReleaseReadLock` at `0x18007a5ea`
- `MobileNetworking!ReleaseReadLock` at `0x18007ab24`
- `MobileNetworking!AcquireReadLock` at `0x18007aa7f`
- `MobileNetworking!AcquireReadLock` at `0x18007aa7f`

## pseudocode

```c
__int64 __fastcall WcnOneXProcessPacket(__int64 a1, unsigned __int16 a2, int a3)
{
  int v4; // r13d
  unsigned int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned int PeerIdentity; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  PVOID *v13; // r10
  unsigned int v14; // ebx
  unsigned int v15; // r15d
  __int64 EapolPktType; // rax
  __int64 v17; // r10
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // r10
  __int64 v22; // r12
  int v23; // r8d
  PVOID *v24; // r10
  int v25; // ebx
  const wchar_t *v26; // rcx
  unsigned int v27; // r14d
  __int64 v28; // rcx
  unsigned int v29; // [rsp+30h] [rbp-20h] BYREF
  int v30; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v31; // [rsp+38h] [rbp-18h] BYREF
  int v32; // [rsp+3Ch] [rbp-14h] BYREF
  __int64 v33; // [rsp+40h] [rbp-10h] BYREF
  __int64 v34; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int8 v35; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 v36; // [rsp+A8h] [rbp+58h] BYREF

  v29 = 5;
  v30 = 9;
  v31 = 0;
  v4 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids);
  v7 = IncThreadCountAndCheckInitialized("WcnOneXProcessPacket", 518);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, v7);
    goto LABEL_8;
  }
  if ( !a1 )
  {
    v8 = 87;
    goto LABEL_8;
  }
  v9 = AuthPortMgrValidateAndRefPort(a1, &v31);
  v8 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, v9);
    goto LABEL_8;
  }
  PeerIdentity = PktParseEapol(*(_DWORD *)(a1 + 132), a2, a3, (unsigned int)&v29, (__int64)&v34, (__int64)&v36);
  v8 = PeerIdentity;
  if ( PeerIdentity )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_8;
    v12 = 50;
    goto LABEL_22;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  v14 = v29;
  v15 = v36;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    EapolPktType = GetEapolPktType(v29);
    WPP_SF_dSd(*(_QWORD *)(v17 + 16), 51, v18, *(_DWORD *)(a1 + 132), EapolPktType, v15);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 )
  {
    if ( v14 != 1 )
    {
      if ( v14 == 2 || v14 - 3 < 2 )
      {
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        {
          v19 = GetEapolPktType(v14);
          WPP_SF_S(*(_QWORD *)(v20 + 16), 63, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, v19);
        }
        goto LABEL_34;
      }
      v8 = 13;
      goto LABEL_8;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_d(v13[2], 61, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, *(unsigned int *)(a1 + 132));
    PeerIdentity = SMInsertTrigger((PVOID)(a1 + 136));
    v8 = PeerIdentity;
    if ( !PeerIdentity )
      goto LABEL_34;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_8;
    v12 = 62;
    goto LABEL_22;
  }
  v22 = v34;
  PeerIdentity = PktParseEap(
                   *(_DWORD *)(a1 + 132),
                   (unsigned __int16)v15,
                   v34,
                   (unsigned int)&v35,
                   (__int64)&v30,
                   (__int64)&v32);
  v8 = PeerIdentity;
  if ( PeerIdentity )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_8;
    v12 = 52;
    goto LABEL_22;
  }
  v24 = (PVOID *)WPP_GLOBAL_Control;
  v25 = v30;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( v30 )
    {
      switch ( v30 )
      {
        case 1:
          v26 = L"EapNotification";
          break;
        case 2:
          v26 = L"EapRequestId";
          break;
        case 3:
          v26 = L"EapSuccess";
          break;
        case 4:
          v26 = L"EapFail";
          break;
        case 5:
          v26 = L"EapRequestOther";
          break;
        case 6:
          v26 = L"EapResponseId";
          break;
        case 7:
          v26 = L"EapResponseNak";
          break;
        case 8:
          v26 = L"EapResponseOther";
          break;
        default:
          v26 = L"EapPacketInvalid";
          break;
      }
    }
    else
    {
      v26 = L"EapPacketNone";
    }
    WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v23, *(_DWORD *)(a1 + 132), (__int64)v26, v15);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v25 == 6 )
  {
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
    {
      WPP_SF_d(v24[2], 54, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, *(unsigned int *)(a1 + 132));
      v24 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *(_BYTE *)(a1 + 296) != v35 )
    {
      if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
        WPP_SF_dd(v24[2], 55, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, *(unsigned __int8 *)(a1 + 296), v35);
      goto LABEL_34;
    }
    PeerIdentity = PktGetPeerIdentity((unsigned __int16)v15, v22, &v33);
    v8 = PeerIdentity;
    if ( PeerIdentity )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_8;
      v12 = 56;
LABEL_22:
      WPP_SF_d(v11[2], v12, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, PeerIdentity);
      goto LABEL_8;
    }
    PeerIdentity = SMInsertTrigger((PVOID)(a1 + 136));
    v8 = PeerIdentity;
    if ( !PeerIdentity )
      goto LABEL_34;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 57;
      goto LABEL_22;
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
    v27 = *(_DWORD *)(a1 + 208);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
    if ( v27 != 5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, v27);
      goto LABEL_34;
    }
    AcquireReadLock(a1 + 24);
    v28 = *(_QWORD *)(a1 + 288);
    v4 = 1;
    if ( v28 )
    {
      PeerIdentity = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(qword_1800BB5A8 + 48))(v28, v22, v15);
      v8 = PeerIdentity;
      if ( !PeerIdentity )
      {
LABEL_11:
        ReleaseReadLock(a1 + 24);
        goto LABEL_34;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_8;
      v12 = 59;
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids);
    v8 = 5023;
  }
LABEL_8:
  if ( v33 )
    FreeMemory(&v33, "WcnOneXProcessPacket", 666);
  if ( v4 )
    goto LABEL_11;
LABEL_34:
  AuthPortMgrDeRefPort(a1, v31);
  DecThreadCount("WcnOneXProcessPacket", 676);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18007a4f4  mov     [rsp-38h+arg_8], rbx
0x18007a4f9  push    rbp
0x18007a4fa  push    rsi
0x18007a4fb  push    rdi
0x18007a4fc  push    r12
0x18007a4fe  push    r13
0x18007a500  push    r14
0x18007a502  push    r15
0x18007a504  mov     rbp, rsp
0x18007a507  sub     rsp, 50h
0x18007a50b  mov     rsi, rcx
0x18007a50e  mov     [rbp+var_20], 5
0x18007a515  xor     ecx, ecx
0x18007a517  mov     [rbp+var_1C], 9
0x18007a51e  mov     [rbp+var_18], ecx
0x18007a521  mov     r13d, ecx
0x18007a524  mov     [rbp+var_8], rcx
0x18007a528  mov     rbx, r8
0x18007a52b  mov     [rbp+arg_18], cx
0x18007a52f  movzx   r14d, dx
0x18007a533  mov     [rbp+arg_0], cl
0x18007a536  mov     [rbp+var_14], ecx
0x18007a539  mov     [rbp+var_10], rcx
0x18007a53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a544  lea     r15, WPP_GLOBAL_Control
0x18007a54b  lea     r12, WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids
0x18007a552  cmp     rcx, r15
0x18007a555  jz      short loc_18007A56E
0x18007a557  test    byte ptr [rcx+1Ch], 1
0x18007a55b  jz      short loc_18007A56E
0x18007a55d  mov     rcx, [rcx+10h]
0x18007a561  mov     edx, 2Fh ; '/'
0x18007a566  mov     r8, r12
0x18007a569  call    WPP_SF_
0x18007a56e  mov     edx, 206h
0x18007a573  lea     rcx, aWcnonexprocess; "WcnOneXProcessPacket"
0x18007a57a  call    IncThreadCountAndCheckInitialized
0x18007a57f  mov     edi, eax
0x18007a581  test    eax, eax
0x18007a583  jz      short loc_18007A5FB
0x18007a585  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a58c  lea     r14, WPP_GLOBAL_Control
0x18007a593  cmp     rcx, r14
0x18007a596  jz      short loc_18007A5B2
0x18007a598  test    byte ptr [rcx+1Ch], 2
0x18007a59c  jz      short loc_18007A5B2
0x18007a59e  mov     rcx, [rcx+10h]
0x18007a5a2  mov     edx, 30h ; '0'
0x18007a5a7  mov     r9d, eax
0x18007a5aa  mov     r8, r12
0x18007a5ad  call    WPP_SF_d
0x18007a5b2  lea     r15, WPP_GLOBAL_Control
0x18007a5b9  cmp     [rbp+var_10], 0
0x18007a5be  jz      short loc_18007A5DD
0x18007a5c0  mov     r8d, 29Ah
0x18007a5c6  lea     rdx, aWcnonexprocess; "WcnOneXProcessPacket"
0x18007a5cd  lea     rcx, [rbp+var_10]
0x18007a5d1  call    cs:__imp_FreeMemory
0x18007a5d8  nop     dword ptr [rax+rax+00h]
0x18007a5dd  test    r13d, r13d
0x18007a5e0  jz      loc_18007A74C
0x18007a5e6  lea     rcx, [rsi+18h]
0x18007a5ea  call    cs:__imp_ReleaseReadLock
0x18007a5f1  nop     dword ptr [rax+rax+00h]
0x18007a5f6  jmp     loc_18007A74C
0x18007a5fb  test    rsi, rsi
0x18007a5fe  jnz     short loc_18007A605
0x18007a600  lea     edi, [rsi+57h]
0x18007a603  jmp     short loc_18007A5B9
0x18007a605  lea     rdx, [rbp+var_18]
0x18007a609  mov     rcx, rsi
0x18007a60c  call    AuthPortMgrValidateAndRefPort
0x18007a611  mov     edi, eax
0x18007a613  test    eax, eax
0x18007a615  jz      short loc_18007A642
0x18007a617  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a61e  cmp     rcx, r15
0x18007a621  jz      short loc_18007A5B9
0x18007a623  test    byte ptr [rcx+1Ch], 2
0x18007a627  jz      short loc_18007A5B9
0x18007a629  mov     rcx, [rcx+10h]
0x18007a62d  mov     edx, 31h ; '1'
0x18007a632  mov     r9d, eax
0x18007a635  mov     r8, r12
0x18007a638  call    WPP_SF_d
0x18007a63d  jmp     loc_18007A5B9
0x18007a642  mov     ecx, [rsi+84h]
0x18007a648  lea     rax, [rbp+arg_18]
0x18007a64c  mov     [rsp+50h+var_28], rax
0x18007a651  lea     r9, [rbp+var_20]
0x18007a655  lea     rax, [rbp+var_8]
0x18007a659  mov     r8, rbx
0x18007a65c  movzx   edx, r14w
0x18007a660  mov     [rsp+50h+var_30], rax
0x18007a665  call    PktParseEapol
0x18007a66a  mov     edi, eax
0x18007a66c  test    eax, eax
0x18007a66e  jz      short loc_18007A6A3
0x18007a670  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a677  cmp     rcx, r15
0x18007a67a  jz      loc_18007A5B9
0x18007a680  test    byte ptr [rcx+1Ch], 2
0x18007a684  jz      loc_18007A5B9
0x18007a68a  mov     edx, 32h ; '2'
0x18007a68f  mov     r8, r12
0x18007a692  mov     rcx, [rcx+10h]
0x18007a696  mov     r9d, eax
0x18007a699  call    WPP_SF_d
0x18007a69e  jmp     loc_18007A5B9
0x18007a6a3  mov     r10, cs:WPP_GLOBAL_Control
0x18007a6aa  lea     r14, WPP_GLOBAL_Control
0x18007a6b1  mov     ebx, [rbp+var_20]
0x18007a6b4  movzx   r15d, [rbp+arg_18]
0x18007a6b9  cmp     r10, r14
0x18007a6bc  jz      short loc_18007A6F2
0x18007a6be  test    byte ptr [r10+1Ch], 1
0x18007a6c3  jz      short loc_18007A6F2
0x18007a6c5  mov     ecx, ebx
0x18007a6c7  call    GetEapolPktType
0x18007a6cc  mov     rcx, [r10+10h]
0x18007a6d0  mov     edx, 33h ; '3'
0x18007a6d5  mov     r9d, [rsi+84h]
0x18007a6dc  mov     dword ptr [rsp+50h+var_28], r15d
0x18007a6e1  mov     [rsp+50h+var_30], rax
0x18007a6e6  call    WPP_SF_dSd
0x18007a6eb  mov     r10, cs:WPP_GLOBAL_Control
0x18007a6f2  mov     ecx, ebx
0x18007a6f4  test    ebx, ebx
0x18007a6f6  jz      loc_18007A824
0x18007a6fc  sub     ecx, 1
0x18007a6ff  jz      loc_18007A7AD
0x18007a705  sub     ecx, 1
0x18007a708  jz      short loc_18007A71E
0x18007a70a  sub     ecx, 1
0x18007a70d  jz      short loc_18007A71E
0x18007a70f  cmp     ecx, 1
0x18007a712  jz      short loc_18007A71E
0x18007a714  mov     edi, 0Dh
0x18007a719  jmp     loc_18007A5B2
0x18007a71e  cmp     r10, r14
0x18007a721  jz      short loc_18007A745
0x18007a723  test    byte ptr [r10+1Ch], 1
0x18007a728  jz      short loc_18007A745
0x18007a72a  mov     ecx, ebx
0x18007a72c  call    GetEapolPktType
0x18007a731  mov     rcx, [r10+10h]
0x18007a735  mov     r9, rax
0x18007a738  mov     edx, 3Fh ; '?'
0x18007a73d  mov     r8, r12
0x18007a740  call    WPP_SF_S
0x18007a745  lea     r15, WPP_GLOBAL_Control
0x18007a74c  mov     edx, [rbp+var_18]
0x18007a74f  mov     rcx, rsi
0x18007a752  call    AuthPortMgrDeRefPort
0x18007a757  mov     edx, 2A4h
0x18007a75c  lea     rcx, aWcnonexprocess; "WcnOneXProcessPacket"
0x18007a763  call    DecThreadCount
0x18007a768  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a76f  cmp     rcx, r15
0x18007a772  jz      short loc_18007A792
0x18007a774  test    byte ptr [rcx+1Ch], 1
0x18007a778  jz      short loc_18007A792
0x18007a77a  mov     rcx, [rcx+10h]
0x18007a77e  lea     r8, WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids
0x18007a785  mov     edx, 40h ; '@'
0x18007a78a  mov     r9d, edi
0x18007a78d  call    WPP_SF_d
0x18007a792  mov     rbx, [rsp+50h+arg_8]
0x18007a79a  mov     eax, edi
0x18007a79c  add     rsp, 50h
0x18007a7a0  pop     r15
0x18007a7a2  pop     r14
0x18007a7a4  pop     r13
0x18007a7a6  pop     r12
0x18007a7a8  pop     rdi
0x18007a7a9  pop     rsi
0x18007a7aa  pop     rbp
0x18007a7ab  retn
0x18007a7ad  cmp     r10, r14
0x18007a7b0  jz      short loc_18007A7D1
0x18007a7b2  test    byte ptr [r10+1Ch], 1
0x18007a7b7  jz      short loc_18007A7D1
0x18007a7b9  mov     r9d, [rsi+84h]
0x18007a7c0  mov     edx, 3Dh ; '='
0x18007a7c5  mov     rcx, [r10+10h]
0x18007a7c9  mov     r8, r12
0x18007a7cc  call    WPP_SF_d
0x18007a7d1  xor     r9d, r9d
0x18007a7d4  lea     rcx, [rsi+88h]; Context
0x18007a7db  xor     r8d, r8d
0x18007a7de  lea     edx, [r9+4]
0x18007a7e2  call    SMInsertTrigger
0x18007a7e7  mov     edi, eax
0x18007a7e9  test    eax, eax
0x18007a7eb  jz      loc_18007A745
0x18007a7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a7f8  cmp     rcx, r14
0x18007a7fb  jz      loc_18007A5B2
0x18007a801  test    byte ptr [rcx+1Ch], 2
0x18007a805  jz      loc_18007A5B2
0x18007a80b  mov     edx, 3Eh ; '>'
0x18007a810  mov     r8, r12
0x18007a813  mov     rcx, [rcx+10h]
0x18007a817  mov     r9d, eax
0x18007a81a  call    WPP_SF_d
0x18007a81f  jmp     loc_18007A5B2
0x18007a824  mov     r12, [rbp+var_8]
0x18007a828  lea     rax, [rbp+var_14]
0x18007a82c  mov     ecx, [rsi+84h]
0x18007a832  lea     r9, [rbp+arg_0]
0x18007a836  mov     [rsp+50h+var_28], rax
0x18007a83b  mov     r8, r12
0x18007a83e  lea     rax, [rbp+var_1C]
0x18007a842  movzx   edx, r15w
0x18007a846  mov     [rsp+50h+var_30], rax
0x18007a84b  call    PktParseEap
0x18007a850  mov     edi, eax
0x18007a852  test    eax, eax
0x18007a854  jz      short loc_18007A87E
0x18007a856  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a85d  cmp     rcx, r14
0x18007a860  jz      loc_18007A5B2
0x18007a866  test    byte ptr [rcx+1Ch], 2
0x18007a86a  jz      loc_18007A5B2
0x18007a870  mov     edx, 34h ; '4'
0x18007a875  lea     r8, WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids
0x18007a87c  jmp     short loc_18007A813
0x18007a87e  mov     r10, cs:WPP_GLOBAL_Control
0x18007a885  mov     ebx, [rbp+var_1C]
0x18007a888  cmp     r10, r14
0x18007a88b  jz      loc_18007A948
0x18007a891  test    byte ptr [r10+1Ch], 1
0x18007a896  jz      loc_18007A948
0x18007a89c  mov     ecx, ebx
0x18007a89e  test    ebx, ebx
0x18007a8a0  jz      short loc_18007A91B
0x18007a8a2  sub     ecx, 1
0x18007a8a5  jz      short loc_18007A912
0x18007a8a7  sub     ecx, 1
0x18007a8aa  jz      short loc_18007A909
0x18007a8ac  sub     ecx, 1
0x18007a8af  jz      short loc_18007A900
0x18007a8b1  sub     ecx, 1
0x18007a8b4  jz      short loc_18007A8F7
0x18007a8b6  sub     ecx, 1
0x18007a8b9  jz      short loc_18007A8EE
0x18007a8bb  sub     ecx, 1
0x18007a8be  jz      short loc_18007A8E5
0x18007a8c0  sub     ecx, 1
0x18007a8c3  jz      short loc_18007A8DC
0x18007a8c5  cmp     ecx, 1
0x18007a8c8  jz      short loc_18007A8D3
0x18007a8ca  lea     rcx, aEappacketinval; "EapPacketInvalid"
0x18007a8d1  jmp     short loc_18007A922
0x18007a8d3  lea     rcx, aEapresponseoth; "EapResponseOther"
0x18007a8da  jmp     short loc_18007A922
0x18007a8dc  lea     rcx, aEapresponsenak; "EapResponseNak"
0x18007a8e3  jmp     short loc_18007A922
0x18007a8e5  lea     rcx, aEapresponseid; "EapResponseId"
0x18007a8ec  jmp     short loc_18007A922
0x18007a8ee  lea     rcx, aEaprequestothe; "EapRequestOther"
0x18007a8f5  jmp     short loc_18007A922
0x18007a8f7  lea     rcx, aEapfail; "EapFail"
0x18007a8fe  jmp     short loc_18007A922
0x18007a900  lea     rcx, aEapsuccess; "EapSuccess"
0x18007a907  jmp     short loc_18007A922
0x18007a909  lea     rcx, aEaprequestid; "EapRequestId"
0x18007a910  jmp     short loc_18007A922
0x18007a912  lea     rcx, aEapnotificatio; "EapNotification"
0x18007a919  jmp     short loc_18007A922
0x18007a91b  lea     rcx, aEappacketnone; "EapPacketNone"
0x18007a922  mov     r9d, [rsi+84h]
0x18007a929  mov     edx, 35h ; '5'
0x18007a92e  mov     dword ptr [rsp+50h+var_28], r15d
0x18007a933  mov     [rsp+50h+var_30], rcx
0x18007a938  mov     rcx, [r10+10h]
0x18007a93c  call    WPP_SF_dSd
0x18007a941  mov     r10, cs:WPP_GLOBAL_Control
0x18007a948  cmp     ebx, 6
0x18007a94b  jnz     loc_18007AA45
0x18007a951  cmp     r10, r14
0x18007a954  jz      short loc_18007A97E
0x18007a956  test    byte ptr [r10+1Ch], 1
0x18007a95b  jz      short loc_18007A97E
0x18007a95d  mov     r9d, [rsi+84h]
0x18007a964  lea     edx, [rbx+30h]
0x18007a967  mov     rcx, [r10+10h]
0x18007a96b  lea     r8, WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids
0x18007a972  call    WPP_SF_d
0x18007a977  mov     r10, cs:WPP_GLOBAL_Control
0x18007a97e  movzx   ecx, byte ptr [rsi+128h]
0x18007a985  cmp     cl, [rbp+arg_0]
0x18007a988  jz      short loc_18007A9C3
0x18007a98a  cmp     r10, r14
0x18007a98d  jz      loc_18007A745
0x18007a993  test    byte ptr [r10+1Ch], 1
0x18007a998  jz      loc_18007A745
0x18007a99e  movzx   eax, [rbp+arg_0]
0x18007a9a2  lea     r8, WPP_88033c3f9901379e0c00184ae6f79aef_Traceguids
0x18007a9a9  mov     r9d, ecx
  ... truncated ...
```
