# SrvNetRdmaCreateListener

- ea: `0x140046198`
- end: `0x1400465c5`
- name: `SrvNetRdmaCreateListener`
- size: `1069`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x140042864`

## callees

- `0x1400079a0`
- `0x14001389c`
- `0x140014a58`
- `0x140015350`
- `0x140015790`
- `0x140019afc`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x1400460c0`
- `0x140046198`
- `0x140046c1c`

## import_xrefs

- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400462ca`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400462ca`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400463ce`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400463ce`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x14004629d`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x14004629d`

## pseudocode

```c
__int64 __fastcall SrvNetRdmaCreateListener(__int64 a1, __int64 a2)
{
  char v4; // r13
  int v5; // edx
  __int64 v6; // rcx
  int v7; // r8d
  char v8; // r15
  int ListenSocketConfig; // ebx
  int v10; // r9d
  bool v11; // cf
  __int16 v12; // ax
  NTSTATUS v13; // eax
  int AddressInterface; // eax
  int v15; // edx
  int v16; // r8d
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  NTSTATUS v19; // eax
  __int16 *v20; // rax
  unsigned int v21; // r15d
  __int16 v22; // ax
  unsigned int v23; // edi
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  char v27; // [rsp+28h] [rbp-58h]
  unsigned int v28; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR Terminator; // [rsp+40h] [rbp-40h] BYREF
  __int128 v31; // [rsp+48h] [rbp-38h] BYREF
  _QWORD Addr[4]; // [rsp+58h] [rbp-28h] BYREF

  memset(Addr, 0, 28);
  v28 = 0;
  v4 = 0;
  v29 = 0;
  v31 = 0;
  if ( (unsigned __int8)SrvNetAcquireRdmaRundownProtection() )
  {
    v8 = 1;
    *(_QWORD *)(a1 + 32) = 0;
    *(_DWORD *)(a1 + 48) = 0;
    v11 = *(_WORD *)a2 < 0x14u;
    Terminator = 0;
    if ( !v11 )
    {
      v6 = *(_QWORD *)(a2 + 8);
      v12 = *(_WORD *)(v6 + 36);
      if ( v12 == 52 )
      {
        LOWORD(Addr[0]) = 2;
        v13 = RtlIpv4StringToAddressW((PCWSTR)(v6 + 40), 1u, &Terminator, (struct in_addr *)Addr + 1);
        goto LABEL_16;
      }
      if ( v12 == 54 )
      {
        LOWORD(Addr[0]) = 23;
        v13 = RtlIpv6StringToAddressW((PCWSTR)(v6 + 40), &Terminator, (struct in6_addr *)&Addr[1]);
LABEL_16:
        ListenSocketConfig = v13;
        if ( v13 >= 0 )
        {
          AddressInterface = SrvNetFindAddressInterface(Addr, &v28);
          ListenSocketConfig = AddressInterface;
          if ( AddressInterface < 0 )
          {
            if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) != 0 )
              McTemplateK0qqd_EtwWriteTransfer(
                *(_DWORD *)(a1 + 48),
                v15,
                v16,
                1,
                *(_DWORD *)(a1 + 48),
                AddressInterface);
            goto LABEL_61;
          }
          if ( !SrvNetIsSMBDirectSupported )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
              || !BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              goto LABEL_26;
            }
            v18 = 26;
LABEL_25:
            WPP_SF_(v17->AttachedDevice, v18, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids);
LABEL_26:
            if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) != 0 )
              McTemplateK0qqd_EtwWriteTransfer((_DWORD)v17, v15, v16, 2, *(_DWORD *)(a1 + 48), ListenSocketConfig);
            ListenSocketConfig = -1073741637;
            goto LABEL_61;
          }
          if ( !SrvNetEnableRdmaSupport )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
              || !BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              goto LABEL_26;
            }
            v18 = 27;
            goto LABEL_25;
          }
          v19 = RtlRunOnceExecuteOnce(&SrvNetSmbdInitOnce, (PRTL_RUN_ONCE_INIT_FN)SrvNetSmbdRunOnceInitialize, 0, 0);
          ListenSocketConfig = v19;
          if ( v19 < 0 )
          {
            if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) == 0 )
              goto LABEL_61;
            v27 = v19;
            v10 = 3;
            goto LABEL_9;
          }
          v20 = *(__int16 **)(a1 + 368);
          v21 = v28;
          if ( LOWORD(Addr[0]) == 2 )
          {
            if ( v20 )
              v22 = *v20;
            else
              v22 = 445;
            v23 = 16;
          }
          else
          {
            if ( v20 )
              v22 = *v20;
            else
              v22 = 445;
            LODWORD(Addr[3]) = v28;
            v23 = 28;
          }
          WORD1(Addr[0]) = __ROR2__(v22, 8);
          ListenSocketConfig = SrvNetRdmaCreateListenSocketConfig(a1 + 40);
          if ( ListenSocketConfig >= 0 )
          {
            *((_QWORD *)&v31 + 1) = *(_QWORD *)(a1 + 40);
            LODWORD(v31) = 1;
            ListenSocketConfig = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, __int64, _QWORD, __int64 *))(SmbdFastDispatch + 160))(
                                   (unsigned __int64)&v31 & -(__int64)(*((_QWORD *)&v31 + 1) != 0),
                                   v21,
                                   a1,
                                   SrvNetRdmaAcceptEvent,
                                   &v29);
            if ( ListenSocketConfig < 0 )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_53;
              }
              v25 = 28;
LABEL_52:
              WPP_SF_d(
                v24->AttachedDevice,
                v25,
                WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids,
                (unsigned int)ListenSocketConfig);
LABEL_53:
              v4 = 1;
              v8 = 1;
              goto LABEL_61;
            }
            ListenSocketConfig = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(SmbdFastDispatch + 104))(
                                   v29,
                                   Addr,
                                   v23);
            if ( ListenSocketConfig < 0 )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_53;
              }
              v25 = 29;
              goto LABEL_52;
            }
            ListenSocketConfig = 0;
            *(_QWORD *)(a1 + 32) = v29;
            *(_DWORD *)(a1 + 48) = v21;
            v29 = 0;
          }
          v8 = 1;
          goto LABEL_61;
        }
LABEL_70:
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) == 0 )
          goto LABEL_61;
        v10 = 0;
        goto LABEL_8;
      }
    }
    ListenSocketConfig = -1073741811;
    goto LABEL_70;
  }
  v8 = 0;
  LODWORD(v6) = (_DWORD)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids);
  }
  ListenSocketConfig = -1073741267;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) != 0 )
  {
    v10 = 4;
LABEL_8:
    v27 = ListenSocketConfig;
LABEL_9:
    McTemplateK0qqd_EtwWriteTransfer(v6, v5, v7, v10, *(_DWORD *)(a1 + 48), v27);
  }
LABEL_61:
  if ( v29 )
    (*(void (**)(void))(SmbdFastDispatch + 112))();
  if ( ListenSocketConfig < 0 && v8 )
    SrvNetReleaseRdmaRundownProtection();
  if ( v4 )
    SrvNetSendRdmaEndpointNotification(Addr, 0);
  return (unsigned int)ListenSocketConfig;
}

```

## disassembly

```asm
0x140046198  mov     [rsp-28h+arg_10], rbx
0x14004619d  mov     [rsp-28h+arg_18], rdi
0x1400461a2  push    rbp
0x1400461a3  push    r12
0x1400461a5  push    r13
0x1400461a7  push    r14
0x1400461a9  push    r15
0x1400461ab  mov     rbp, rsp
0x1400461ae  sub     rsp, 80h
0x1400461b5  mov     rax, cs:__security_cookie
0x1400461bc  xor     rax, rsp
0x1400461bf  mov     [rbp+var_8], rax
0x1400461c3  xorps   xmm0, xmm0
0x1400461c6  xor     r12d, r12d
0x1400461c9  movups  xmmword ptr [rbp+Addr.S_un], xmm0
0x1400461cd  mov     rbx, rdx
0x1400461d0  mov     r14, rcx
0x1400461d3  movups  xmmword ptr [rbp+Addr.S_un+0Ch], xmm0
0x1400461d7  mov     [rbp+var_4C], r12d
0x1400461db  mov     r13b, r12b
0x1400461de  mov     [rbp+var_48], r12
0x1400461e2  movups  [rbp+var_38], xmm0
0x1400461e6  call    SrvNetAcquireRdmaRundownProtection
0x1400461eb  test    al, al
0x1400461ed  jnz     short loc_14004625A
0x1400461ef  mov     r15b, r12b
0x1400461f2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400461f9  lea     rax, WPP_GLOBAL_Control
0x140046200  cmp     rcx, rax
0x140046203  jz      short loc_140046229
0x140046205  test    dword ptr [rcx+2Ch], 80000h
0x14004620c  jz      short loc_140046229
0x14004620e  cmp     byte ptr [rcx+29h], 1
0x140046212  jb      short loc_140046229
0x140046214  mov     rcx, [rcx+18h]
0x140046218  lea     edx, [r12+19h]
0x14004621d  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x140046224  call    WPP_SF_
0x140046229  mov     edi, 10h
0x14004622e  mov     ebx, 0C000022Dh
0x140046233  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, dil
0x14004623a  jz      loc_140046547
0x140046240  lea     r9d, [rdi-0Ch]
0x140046244  mov     dword ptr [rsp+80h+var_58], ebx
0x140046248  mov     eax, [r14+30h]
0x14004624c  mov     dword ptr [rsp+80h+var_60], eax
0x140046250  call    McTemplateK0qqd_EtwWriteTransfer
0x140046255  jmp     loc_140046547
0x14004625a  mov     r15b, 1
0x14004625d  mov     [r14+20h], r12
0x140046261  mov     [r14+30h], r12d
0x140046265  cmp     word ptr [rbx], 14h
0x140046269  mov     [rbp+var_50], r15b
0x14004626d  mov     [rbp+Terminator], r12
0x140046271  jb      loc_1400465AA
0x140046277  mov     rcx, [rbx+8]
0x14004627b  mov     edi, 2
0x140046280  movzx   eax, word ptr [rcx+24h]
0x140046284  cmp     ax, 34h ; '4'
0x140046288  jnz     short loc_1400462AB
0x14004628a  add     rcx, 28h ; '('; S
0x14004628e  mov     word ptr [rbp+Addr.S_un], di
0x140046292  lea     r9, [rbp+Addr.S_un+4]; Addr
0x140046296  mov     dl, r15b; Strict
0x140046299  lea     r8, [rbp+Terminator]; Terminator
0x14004629d  call    cs:__imp_RtlIpv4StringToAddressW
0x1400462a4  nop     dword ptr [rax+rax+00h]
0x1400462a9  jmp     short loc_1400462D6
0x1400462ab  cmp     ax, 36h ; '6'
0x1400462af  jnz     loc_1400465AA
0x1400462b5  mov     eax, 17h
0x1400462ba  lea     r8, [rbp+Addr.S_un+8]; Addr
0x1400462be  add     rcx, 28h ; '('; S
0x1400462c2  mov     word ptr [rbp+Addr.S_un], ax
0x1400462c6  lea     rdx, [rbp+Terminator]; Terminator
0x1400462ca  call    cs:__imp_RtlIpv6StringToAddressW
0x1400462d1  nop     dword ptr [rax+rax+00h]
0x1400462d6  mov     ebx, eax
0x1400462d8  test    eax, eax
0x1400462da  js      loc_1400465AF
0x1400462e0  lea     rdx, [rbp+var_4C]
0x1400462e4  lea     rcx, [rbp+Addr]
0x1400462e8  call    SrvNetFindAddressInterface
0x1400462ed  mov     ebx, eax
0x1400462ef  test    eax, eax
0x1400462f1  jns     short loc_14004631A
0x1400462f3  mov     edi, 10h
0x1400462f8  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, dil
0x1400462ff  jz      loc_140046547
0x140046305  mov     ecx, [r14+30h]
0x140046309  lea     r9d, [rdi-0Fh]
0x14004630d  mov     dword ptr [rsp+80h+var_58], eax
0x140046311  mov     dword ptr [rsp+80h+var_60], ecx
0x140046315  jmp     loc_140046250
0x14004631a  cmp     cs:SrvNetIsSMBDirectSupported, r12b
0x140046321  jnz     short loc_140046387
0x140046323  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004632a  lea     rax, WPP_GLOBAL_Control
0x140046331  cmp     rcx, rax
0x140046334  jz      short loc_14004635A
0x140046336  test    dword ptr [rcx+2Ch], 80000h
0x14004633d  jz      short loc_14004635A
0x14004633f  cmp     [rcx+29h], r15b
0x140046343  jb      short loc_14004635A
0x140046345  mov     edx, 1Ah
0x14004634a  mov     rcx, [rcx+18h]
0x14004634e  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x140046355  call    WPP_SF_
0x14004635a  mov     edi, 10h
0x14004635f  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, dil
0x140046366  jz      short loc_14004637D
0x140046368  mov     eax, [r14+30h]
0x14004636c  lea     r9d, [rdi-0Eh]
0x140046370  mov     dword ptr [rsp+80h+var_58], ebx
0x140046374  mov     dword ptr [rsp+80h+var_60], eax
0x140046378  call    McTemplateK0qqd_EtwWriteTransfer
0x14004637d  mov     ebx, 0C00000BBh
0x140046382  jmp     loc_140046547
0x140046387  mov     al, cs:SrvNetEnableRdmaSupport
0x14004638d  test    al, al
0x14004638f  jnz     short loc_1400463BA
0x140046391  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046398  lea     rax, WPP_GLOBAL_Control
0x14004639f  cmp     rcx, rax
0x1400463a2  jz      short loc_14004635A
0x1400463a4  test    dword ptr [rcx+2Ch], 80000h
0x1400463ab  jz      short loc_14004635A
0x1400463ad  cmp     [rcx+29h], r15b
0x1400463b1  jb      short loc_14004635A
0x1400463b3  mov     edx, 1Bh
0x1400463b8  jmp     short loc_14004634A
0x1400463ba  xor     r9d, r9d; Context
0x1400463bd  lea     rdx, SrvNetSmbdRunOnceInitialize; InitFn
0x1400463c4  xor     r8d, r8d; Parameter
0x1400463c7  lea     rcx, SrvNetSmbdInitOnce; RunOnce
0x1400463ce  call    cs:__imp_RtlRunOnceExecuteOnce
0x1400463d5  nop     dword ptr [rax+rax+00h]
0x1400463da  mov     ebx, eax
0x1400463dc  test    eax, eax
0x1400463de  jns     short loc_1400463FF
0x1400463e0  mov     edi, 10h
0x1400463e5  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, dil
0x1400463ec  jz      loc_140046547
0x1400463f2  mov     dword ptr [rsp+80h+var_58], eax
0x1400463f6  lea     r9d, [rdi-0Dh]
0x1400463fa  jmp     loc_140046248
0x1400463ff  mov     rax, [r14+170h]
0x140046406  mov     r15d, [rbp+var_4C]
0x14004640a  cmp     word ptr [rbp+Addr.S_un], di
0x14004640e  jnz     short loc_140046426
0x140046410  test    rax, rax
0x140046413  jz      short loc_14004641A
0x140046415  movzx   eax, word ptr [rax]
0x140046418  jmp     short loc_14004641F
0x14004641a  mov     eax, 1BDh
0x14004641f  mov     edi, 10h
0x140046424  jmp     short loc_14004643E
0x140046426  test    rax, rax
0x140046429  jz      short loc_140046430
0x14004642b  movzx   eax, word ptr [rax]
0x14004642e  jmp     short loc_140046435
0x140046430  mov     eax, 1BDh
0x140046435  mov     [rbp+var_10], r15d
0x140046439  mov     edi, 1Ch
0x14004643e  ror     ax, 8
0x140046442  lea     rcx, [r14+28h]
0x140046446  mov     word ptr [rbp+Addr.S_un+2], ax
0x14004644a  call    SrvNetRdmaCreateListenSocketConfig
0x14004644f  mov     ebx, eax
0x140046451  test    eax, eax
0x140046453  js      loc_140046543
0x140046459  mov     rax, [r14+28h]
0x14004645d  lea     rdx, [rbp+var_48]
0x140046461  mov     qword ptr [rbp+var_38+8], rax
0x140046465  lea     r9, SrvNetRdmaAcceptEvent
0x14004646c  neg     rax
0x14004646f  mov     dword ptr [rbp+var_38], 1
0x140046476  lea     rax, [rbp+var_38]
0x14004647a  mov     [rsp+80h+var_60], rdx
0x14004647f  sbb     rcx, rcx
0x140046482  mov     r8, r14
0x140046485  and     rcx, rax
0x140046488  mov     edx, r15d
0x14004648b  mov     rax, cs:SmbdFastDispatch
0x140046492  mov     rax, [rax+0A0h]
0x140046499  call    _guard_dispatch_icall
0x14004649e  mov     ebx, eax
0x1400464a0  test    eax, eax
0x1400464a2  jns     short loc_1400464E6
0x1400464a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400464ab  lea     rax, WPP_GLOBAL_Control
0x1400464b2  cmp     rcx, rax
0x1400464b5  jz      short loc_1400464DE
0x1400464b7  test    dword ptr [rcx+2Ch], 80000h
0x1400464be  jz      short loc_1400464DE
0x1400464c0  cmp     byte ptr [rcx+29h], 1
0x1400464c4  jb      short loc_1400464DE
0x1400464c6  mov     edx, 1Ch
0x1400464cb  mov     rcx, [rcx+18h]
0x1400464cf  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x1400464d6  mov     r9d, ebx
0x1400464d9  call    WPP_SF_d
0x1400464de  mov     r13b, 1
0x1400464e1  mov     r15b, r13b
0x1400464e4  jmp     short loc_140046547
0x1400464e6  mov     rax, cs:SmbdFastDispatch
0x1400464ed  lea     rdx, [rbp+Addr]
0x1400464f1  mov     rcx, [rbp+var_48]
0x1400464f5  mov     r8d, edi
0x1400464f8  mov     rax, [rax+68h]
0x1400464fc  call    _guard_dispatch_icall
0x140046501  mov     ebx, eax
0x140046503  test    eax, eax
0x140046505  jns     short loc_140046530
0x140046507  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004650e  lea     rax, WPP_GLOBAL_Control
0x140046515  cmp     rcx, rax
0x140046518  jz      short loc_1400464DE
0x14004651a  test    dword ptr [rcx+2Ch], 80000h
0x140046521  jz      short loc_1400464DE
0x140046523  cmp     byte ptr [rcx+29h], 1
0x140046527  jb      short loc_1400464DE
0x140046529  mov     edx, 1Dh
0x14004652e  jmp     short loc_1400464CB
0x140046530  mov     rax, [rbp+var_48]
0x140046534  mov     ebx, r12d
0x140046537  mov     [r14+20h], rax
0x14004653b  mov     [r14+30h], r15d
0x14004653f  mov     [rbp+var_48], r12
0x140046543  mov     r15b, [rbp+var_50]
0x140046547  mov     rcx, [rbp+var_48]
0x14004654b  test    rcx, rcx
0x14004654e  jz      short loc_140046560
0x140046550  mov     rax, cs:SmbdFastDispatch
0x140046557  mov     rax, [rax+70h]
0x14004655b  call    _guard_dispatch_icall
0x140046560  test    ebx, ebx
0x140046562  jns     short loc_14004656E
0x140046564  test    r15b, r15b
0x140046567  jz      short loc_14004656E
0x140046569  call    SrvNetReleaseRdmaRundownProtection
0x14004656e  test    r13b, r13b
0x140046571  jz      short loc_14004657E
0x140046573  xor     edx, edx
0x140046575  lea     rcx, [rbp+Addr]
0x140046579  call    SrvNetSendRdmaEndpointNotification
0x14004657e  mov     eax, ebx
0x140046580  mov     rcx, [rbp+var_8]
0x140046584  xor     rcx, rsp; StackCookie
0x140046587  call    __security_check_cookie
0x14004658c  lea     r11, [rsp+80h+var_s0]
0x140046594  mov     rbx, [r11+40h]
0x140046598  mov     rdi, [r11+48h]
0x14004659c  mov     rsp, r11
0x14004659f  pop     r15
0x1400465a1  pop     r14
0x1400465a3  pop     r13
0x1400465a5  pop     r12
0x1400465a7  pop     rbp
0x1400465a8  retn
0x1400465aa  mov     ebx, 0C000000Dh
0x1400465af  mov     edi, 10h
0x1400465b4  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, dil
0x1400465bb  jz      short loc_140046547
0x1400465bd  xor     r9d, r9d
0x1400465c0  jmp     loc_140046244
```
