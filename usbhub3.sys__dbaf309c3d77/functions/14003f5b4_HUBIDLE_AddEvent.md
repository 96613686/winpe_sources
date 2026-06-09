# HUBIDLE_AddEvent

- ea: `0x14003f5b4`
- end: `0x14003fa57`
- name: `HUBIDLE_AddEvent`
- size: `1187`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140014f80`
- `0x1400153c0`
- `0x140015610`
- `0x140016160`
- `0x1400165c0`
- `0x14003f5b4`
- `0x14003fa60`
- `0x14003faa0`
- `0x14007f118`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x1400067ac`
- `0x1400083b4`
- `0x14000c2bc`
- `0x14002f0b4`
- `0x14003f5b4`
- `0x140045530`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003f730`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f730`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f60f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f60f`
- `ntoskrnl!IofCompleteRequest` at `0x14003fa19`
- `ntoskrnl!IofCompleteRequest` at `0x14003fa19`

## pseudocode

```c
__int64 __fastcall HUBIDLE_AddEvent(__int64 a1, int a2, IRP *a3)
{
  int v3; // ebx
  __int64 v5; // r13
  IRP *v6; // rbp
  unsigned int v9; // edi
  int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rbx
  int v14; // ecx
  int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  __int64 (__fastcall *v26)(__int64, IRP *); // rax
  __int64 v27; // rcx
  KIRQL NewIrql; // [rsp+50h] [rbp-58h]
  int v30; // [rsp+54h] [rbp-54h]
  __int128 v31; // [rsp+58h] [rbp-50h] BYREF

  v3 = *(_DWORD *)(a1 + 160);
  v5 = *(_QWORD *)(a1 + 152);
  v6 = 0;
  v30 = v3;
  v31 = 0;
  v9 = 259;
  v10 = a2;
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 136));
  LOBYTE(v11) = NewIrql;
  if ( v10 != 1000 )
  {
    while ( 1 )
    {
      v12 = 0;
      v13 = *(_QWORD *)(v5 + 8LL * (unsigned int)(*(_DWORD *)(a1 + 144) - v3));
      if ( *(_DWORD *)(v13 + 16) == 1000 )
      {
LABEL_5:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 - 48) + 8LL) + 1432LL),
            v11,
            5,
            11,
            (__int64)WPP_2569be9ff7fd3488897cf7ed99434f3d_Traceguids,
            a2);
        }
        HUBMISC_DbgBreak("Unhandled Event in Idle State Machine", v11);
        if ( (byte_14006ED41 & 0x40) != 0 )
          McTemplateK0ppqqqq_EtwWriteTransfer(
            v14,
            (unsigned int)USBHUB3_ETW_EVENT_UNHANDLED_STATE_MACHINE_EVENT,
            0,
            0,
            0,
            *(_DWORD *)(a1 + 160),
            *(_DWORD *)(a1 + 144),
            a2,
            0);
        goto LABEL_9;
      }
      while ( v10 != *(_DWORD *)(v13 + 8 * v12 + 16) )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( *(_DWORD *)(v13 + 8 * v12 + 16) == 1000 )
          goto LABEL_5;
      }
      v25 = *(_DWORD *)(v13 + 8 * v12 + 20);
      if ( v25 == 1000 )
        break;
      switch ( v25 )
      {
        case 1001:
          goto LABEL_5;
        case 1002:
          v9 = -2147483631;
          goto LABEL_36;
        case 1003:
          v9 = -1073741810;
LABEL_36:
          v6 = a3;
          goto LABEL_9;
      }
      *(_DWORD *)(a1 + 8LL * *(unsigned __int8 *)(a1 + 128) + 4) = v25;
      *(_DWORD *)(a1 + 8LL * *(unsigned __int8 *)(a1 + 128)) = v10;
      *(_BYTE *)(a1 + 128) = (*(_BYTE *)(a1 + 128) + 1) & 0xF;
      if ( byte_14006ED41 < 0 )
        McTemplateK0ppqqqq_EtwWriteTransfer(
          v25 - *(_DWORD *)(a1 + 160),
          (unsigned int)USBHUB3_ETW_EVENT_STATE_MACHINE,
          0,
          *(_QWORD *)(*(_QWORD *)(a1 - 48) + 24LL),
          a1,
          *(_DWORD *)(a1 + 160),
          **(_DWORD **)(*(_QWORD *)(a1 + 152) + 8LL * (unsigned int)(v25 - *(_DWORD *)(a1 + 160))),
          v10,
          0);
      *(_DWORD *)(a1 + 144) = v25;
      v26 = *(__int64 (__fastcall **)(__int64, IRP *))(*(_QWORD *)(v5 + 8LL * (unsigned int)(v25 - v30)) + 8LL);
      if ( !v26 )
        goto LABEL_9;
      v10 = v26(a1, a3);
      if ( v10 == 1000 )
        goto LABEL_9;
      v3 = v30;
    }
    if ( a2 != v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 - 48) + 8LL) + 1432LL),
          v11,
          5,
          10,
          (__int64)WPP_2569be9ff7fd3488897cf7ed99434f3d_Traceguids);
      }
      HUBMISC_DbgBreak("Idle State Machine is ignoring a Sync Event", v11);
    }
LABEL_9:
    LOBYTE(v11) = NewIrql;
  }
  v15 = *(_DWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 176) = 0;
  if ( v15 == 1 || v15 == 2 || v15 == 3 || v15 == 4 || v15 == 5 || v15 == 8 )
  {
    v6 = *(IRP **)(a1 + 168);
    *(_QWORD *)(a1 + 168) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 136), v11);
  v18 = v15 - 1;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( !v22 )
          {
            v9 = 0;
            LOBYTE(v24) = 0;
            goto LABEL_55;
          }
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 == 1 )
              {
                v9 = -1073741536;
                goto LABEL_55;
              }
            }
            else
            {
              *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                           WdfDriverGlobals,
                           *(_QWORD *)(a1 + 184),
                           off_14006B100) = a1;
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 3040))(
                WdfDriverGlobals,
                *(_QWORD *)(a1 + 184));
            }
          }
          else
          {
            v31 = 0;
            if ( a3 && g_IoGetActivityIdIrp )
              g_IoGetActivityIdIrp(a3, &v31, v17);
            if ( (byte_14006ED41 & 4) != 0 )
              McTemplateK0p_EtwWriteTransfer(
                v16,
                USBHUB3_ETW_EVENT_DEVICE_IDLE_CALLBACK,
                &v31,
                *(_QWORD *)(*(_QWORD *)(a1 - 48) + 24LL));
            v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 168) + 184LL) + 32LL);
            (*(void (__fastcall **)(_QWORD))v27)(*(_QWORD *)(v27 + 8));
            HUBIDLE_AddEvent(a1, 6001, 0);
          }
        }
        else
        {
          v9 = -1073741101;
        }
      }
      else
      {
        v9 = -1073741810;
      }
    }
    else
    {
      v9 = -2147483631;
    }
  }
  else
  {
    v9 = -1073741536;
  }
  LOBYTE(v24) = 0;
LABEL_55:
  if ( v6 )
  {
    v31 = 0;
    if ( g_IoGetActivityIdIrp )
      g_IoGetActivityIdIrp(v6, &v31, v17);
    if ( (byte_14006ED41 & 4) != 0 )
      McTemplateK0pq_EtwWriteTransfer(
        v16,
        USBHUB3_ETW_EVENT_DEVICE_SUBMIT_IDLE_NOTIFICATION_COMPLETE,
        &v31,
        *(_QWORD *)(*(_QWORD *)(a1 - 48) + 24LL),
        v9);
    v6->IoStatus.Status = v9;
    IofCompleteRequest(v6, 0);
  }
  if ( (_BYTE)v24 )
    return 259;
  return v9;
}

```

## disassembly

```asm
0x14003f5b4  mov     [rsp+arg_8], rbx
0x14003f5b9  push    rbp
0x14003f5ba  push    rsi
0x14003f5bb  push    rdi
0x14003f5bc  push    r12
0x14003f5be  push    r13
0x14003f5c0  push    r14
0x14003f5c2  push    r15
0x14003f5c4  sub     rsp, 70h
0x14003f5c8  mov     rax, cs:__security_cookie
0x14003f5cf  xor     rax, rsp
0x14003f5d2  mov     [rsp+0A8h+var_40], rax
0x14003f5d7  mov     ebx, [rcx+0A0h]
0x14003f5dd  mov     rsi, rcx
0x14003f5e0  mov     r13, [rcx+98h]
0x14003f5e7  xorps   xmm0, xmm0
0x14003f5ea  xor     ebp, ebp
0x14003f5ec  mov     [rsp+0A8h+var_54], ebx
0x14003f5f0  add     rcx, 88h; SpinLock
0x14003f5f7  mov     [rsp+0A8h+var_57], bpl
0x14003f5fc  movups  [rsp+0A8h+var_50], xmm0
0x14003f601  mov     r15, r8
0x14003f604  mov     r12d, edx
0x14003f607  mov     edi, 103h
0x14003f60c  mov     r14d, edx
0x14003f60f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003f616  nop     dword ptr [rax+rax+00h]
0x14003f61b  mov     r8d, 3E8h
0x14003f621  mov     [rsp+0A8h+NewIrql], al
0x14003f625  mov     dl, al
0x14003f627  cmp     r14d, r8d
0x14003f62a  jz      loc_14003F6E7
0x14003f630  mov     eax, [rsi+90h]
0x14003f636  xor     ecx, ecx
0x14003f638  sub     eax, ebx
0x14003f63a  mov     rbx, [r13+rax*8+0]
0x14003f63f  cmp     [rbx+10h], r8d
0x14003f643  jz      short loc_14003F659
0x14003f645  cmp     r14d, [rbx+rcx*8+10h]
0x14003f64a  jz      loc_14003F78E
0x14003f650  inc     ecx
0x14003f652  cmp     [rbx+rcx*8+10h], r8d
0x14003f657  jnz     short loc_14003F645
0x14003f659  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f660  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f667  jz      short loc_14003F69A
0x14003f669  mov     rax, [rsi-30h]
0x14003f66d  mov     r9d, 0Bh
0x14003f673  mov     [rsp+0A8h+var_80], r12d
0x14003f678  mov     dl, 2
0x14003f67a  mov     rcx, [rax+8]
0x14003f67e  lea     r8d, [r9-6]
0x14003f682  lea     rax, WPP_2569be9ff7fd3488897cf7ed99434f3d_Traceguids
0x14003f689  mov     [rsp+0A8h+var_88], rax
0x14003f68e  mov     rcx, [rcx+598h]
0x14003f695  call    WPP_RECORDER_SF_d
0x14003f69a  lea     rcx, aUnhandledEvent_0; "Unhandled Event in Idle State Machine"
0x14003f6a1  call    HUBMISC_DbgBreak
0x14003f6a6  test    cs:byte_14006ED41, 40h
0x14003f6ad  jz      short loc_14003F6E3
0x14003f6af  mov     eax, [rsi+90h]
0x14003f6b5  lea     rdx, USBHUB3_ETW_EVENT_UNHANDLED_STATE_MACHINE_EVENT
0x14003f6bc  mov     [rsp+0A8h+var_68], ebp
0x14003f6c0  xor     r9d, r9d
0x14003f6c3  mov     [rsp+0A8h+var_70], r12d
0x14003f6c8  xor     r8d, r8d
0x14003f6cb  mov     [rsp+0A8h+var_78], eax
0x14003f6cf  mov     eax, [rsi+0A0h]
0x14003f6d5  mov     [rsp+0A8h+var_80], eax
0x14003f6d9  mov     [rsp+0A8h+var_88], rbp
0x14003f6de  call    McTemplateK0ppqqqq_EtwWriteTransfer
0x14003f6e3  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14003f6e7  mov     ebx, [rsi+0B0h]
0x14003f6ed  mov     ecx, ebx
0x14003f6ef  mov     dword ptr [rsi+0B0h], 0
0x14003f6f9  sub     ecx, 1
0x14003f6fc  jz      short loc_14003F717
0x14003f6fe  sub     ecx, 1
0x14003f701  jz      short loc_14003F717
0x14003f703  sub     ecx, 1
0x14003f706  jz      short loc_14003F717
0x14003f708  sub     ecx, 1
0x14003f70b  jz      short loc_14003F717
0x14003f70d  sub     ecx, 1
0x14003f710  jz      short loc_14003F717
0x14003f712  cmp     ecx, 3
0x14003f715  jnz     short loc_14003F729
0x14003f717  mov     rbp, [rsi+0A8h]
0x14003f71e  mov     qword ptr [rsi+0A8h], 0
0x14003f729  lea     rcx, [rsi+88h]; SpinLock
0x14003f730  call    cs:__imp_KeReleaseSpinLock
0x14003f737  nop     dword ptr [rax+rax+00h]
0x14003f73c  sub     ebx, 1
0x14003f73f  jz      loc_14003F9BC
0x14003f745  sub     ebx, 1
0x14003f748  jz      loc_14003F9B5
0x14003f74e  sub     ebx, 1
0x14003f751  jz      loc_14003F9AE
0x14003f757  sub     ebx, 1
0x14003f75a  jz      loc_14003F9A7
0x14003f760  sub     ebx, 1
0x14003f763  jz      loc_14003F9A0
0x14003f769  sub     ebx, 1
0x14003f76c  jz      loc_14003F928
0x14003f772  sub     ebx, 1
0x14003f775  jz      loc_14003F8D7
0x14003f77b  cmp     ebx, 1
0x14003f77e  jnz     loc_14003F9C1
0x14003f784  mov     edi, 0C0000120h
0x14003f789  jmp     loc_14003F9C5
0x14003f78e  mov     ebx, [rbx+rcx*8+14h]
0x14003f792  mov     ecx, ebx
0x14003f794  sub     ecx, r8d
0x14003f797  jz      loc_14003F881
0x14003f79d  sub     ecx, 1
0x14003f7a0  jz      loc_14003F659
0x14003f7a6  sub     ecx, 1
0x14003f7a9  jz      loc_14003F87A
0x14003f7af  cmp     ecx, 1
0x14003f7b2  jz      loc_14003F86D
0x14003f7b8  movzx   eax, byte ptr [rsi+80h]
0x14003f7bf  mov     [rsi+rax*8+4], ebx
0x14003f7c3  movzx   eax, byte ptr [rsi+80h]
0x14003f7ca  mov     [rsi+rax*8], r14d
0x14003f7ce  mov     al, [rsi+80h]
0x14003f7d4  inc     al
0x14003f7d6  and     al, 0Fh
0x14003f7d8  mov     [rsi+80h], al
0x14003f7de  cmp     cs:byte_14006ED41, bpl
0x14003f7e5  jge     short loc_14003F82B
0x14003f7e7  mov     edx, [rsi+0A0h]
0x14003f7ed  mov     ecx, ebx
0x14003f7ef  mov     rax, [rsi+98h]
0x14003f7f6  sub     ecx, edx
0x14003f7f8  mov     r9, [rsi-30h]
0x14003f7fc  xor     r8d, r8d
0x14003f7ff  mov     [rsp+0A8h+var_68], ebp
0x14003f803  mov     [rsp+0A8h+var_70], r14d
0x14003f808  mov     rax, [rax+rcx*8]
0x14003f80c  mov     r9, [r9+18h]
0x14003f810  mov     eax, [rax]
0x14003f812  mov     [rsp+0A8h+var_78], eax
0x14003f816  mov     [rsp+0A8h+var_80], edx
0x14003f81a  lea     rdx, USBHUB3_ETW_EVENT_STATE_MACHINE
0x14003f821  mov     [rsp+0A8h+var_88], rsi
0x14003f826  call    McTemplateK0ppqqqq_EtwWriteTransfer
0x14003f82b  mov     [rsi+90h], ebx
0x14003f831  sub     ebx, [rsp+0A8h+var_54]
0x14003f835  mov     rcx, [r13+rbx*8+0]
0x14003f83a  mov     rax, [rcx+8]
0x14003f83e  test    rax, rax
0x14003f841  jz      loc_14003F6E3
0x14003f847  mov     rdx, r15
0x14003f84a  mov     rcx, rsi
0x14003f84d  call    _guard_dispatch_icall
0x14003f852  mov     r8d, 3E8h
0x14003f858  mov     r14d, eax
0x14003f85b  cmp     eax, r8d
0x14003f85e  jz      loc_14003F6E3
0x14003f864  mov     ebx, [rsp+0A8h+var_54]
0x14003f868  jmp     loc_14003F630
0x14003f86d  mov     edi, 0C000000Eh
0x14003f872  mov     rbp, r15
0x14003f875  jmp     loc_14003F6E3
0x14003f87a  mov     edi, 80000011h
0x14003f87f  jmp     short loc_14003F872
0x14003f881  cmp     r12d, r14d
0x14003f884  jz      loc_14003F6E3
0x14003f88a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f891  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f898  jz      short loc_14003F8C6
0x14003f89a  mov     rax, [rsi-30h]
0x14003f89e  mov     r9d, 0Ah
0x14003f8a4  mov     dl, 2
0x14003f8a6  mov     rcx, [rax+8]
0x14003f8aa  lea     r8d, [r9-5]
0x14003f8ae  lea     rax, WPP_2569be9ff7fd3488897cf7ed99434f3d_Traceguids
0x14003f8b5  mov     [rsp+0A8h+var_88], rax
0x14003f8ba  mov     rcx, [rcx+598h]
0x14003f8c1  call    WPP_RECORDER_SF_
0x14003f8c6  lea     rcx, aIdleStateMachi; "Idle State Machine is ignoring a Sync E"...
0x14003f8cd  call    HUBMISC_DbgBreak
0x14003f8d2  jmp     loc_14003F6E3
0x14003f8d7  mov     rax, cs:WdfFunctions_01015
0x14003f8de  mov     r8, cs:off_14006B100
0x14003f8e5  mov     rdx, [rsi+0B8h]
0x14003f8ec  mov     rcx, cs:WdfDriverGlobals
0x14003f8f3  mov     rax, [rax+650h]
0x14003f8fa  call    _guard_dispatch_icall
0x14003f8ff  mov     [rax], rsi
0x14003f902  mov     rax, cs:WdfFunctions_01015
0x14003f909  mov     rdx, [rsi+0B8h]
0x14003f910  mov     rcx, cs:WdfDriverGlobals
0x14003f917  mov     rax, [rax+0BE0h]
0x14003f91e  call    _guard_dispatch_icall
0x14003f923  jmp     loc_14003F9C1
0x14003f928  xorps   xmm0, xmm0
0x14003f92b  movups  [rsp+0A8h+var_50], xmm0
0x14003f930  test    r15, r15
0x14003f933  jz      short loc_14003F94E
0x14003f935  mov     rax, cs:g_IoGetActivityIdIrp
0x14003f93c  test    rax, rax
0x14003f93f  jz      short loc_14003F94E
0x14003f941  lea     rdx, [rsp+0A8h+var_50]
0x14003f946  mov     rcx, r15
0x14003f949  call    _guard_dispatch_icall
0x14003f94e  test    cs:byte_14006ED41, 4
0x14003f955  jz      short loc_14003F970
0x14003f957  mov     r9, [rsi-30h]
0x14003f95b  lea     r8, [rsp+0A8h+var_50]
0x14003f960  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_IDLE_CALLBACK
0x14003f967  mov     r9, [r9+18h]
0x14003f96b  call    McTemplateK0p_EtwWriteTransfer
0x14003f970  mov     rax, [rsi+0A8h]
0x14003f977  mov     rcx, [rax+0B8h]
0x14003f97e  mov     rcx, [rcx+20h]
0x14003f982  mov     rax, [rcx]
0x14003f985  mov     rcx, [rcx+8]
0x14003f989  call    _guard_dispatch_icall
0x14003f98e  xor     r8d, r8d
0x14003f991  mov     edx, 1771h
0x14003f996  mov     rcx, rsi
0x14003f999  call    HUBIDLE_AddEvent
0x14003f99e  jmp     short loc_14003F9C1
0x14003f9a0  xor     edi, edi
0x14003f9a2  mov     bl, dil
0x14003f9a5  jmp     short loc_14003F9C5
0x14003f9a7  mov     edi, 0C00002D3h
0x14003f9ac  jmp     short loc_14003F9C1
0x14003f9ae  mov     edi, 0C000000Eh
0x14003f9b3  jmp     short loc_14003F9C1
0x14003f9b5  mov     edi, 80000011h
0x14003f9ba  jmp     short loc_14003F9C1
0x14003f9bc  mov     edi, 0C0000120h
0x14003f9c1  mov     bl, [rsp+0A8h+var_57]
0x14003f9c5  test    rbp, rbp
0x14003f9c8  jz      short loc_14003FA25
0x14003f9ca  mov     rax, cs:g_IoGetActivityIdIrp
0x14003f9d1  xorps   xmm0, xmm0
0x14003f9d4  movups  [rsp+0A8h+var_50], xmm0
0x14003f9d9  test    rax, rax
0x14003f9dc  jz      short loc_14003F9EB
0x14003f9de  lea     rdx, [rsp+0A8h+var_50]
0x14003f9e3  mov     rcx, rbp
0x14003f9e6  call    _guard_dispatch_icall
0x14003f9eb  test    cs:byte_14006ED41, 4
0x14003f9f2  jz      short loc_14003FA11
0x14003f9f4  mov     r9, [rsi-30h]
0x14003f9f8  lea     r8, [rsp+0A8h+var_50]
0x14003f9fd  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_SUBMIT_IDLE_NOTIFICATION_COMPLETE
0x14003fa04  mov     dword ptr [rsp+0A8h+var_88], edi
0x14003fa08  mov     r9, [r9+18h]
0x14003fa0c  call    McTemplateK0pq_EtwWriteTransfer
0x14003fa11  xor     edx, edx; PriorityBoost
0x14003fa13  mov     [rbp+30h], edi
0x14003fa16  mov     rcx, rbp; Irp
0x14003fa19  call    cs:__imp_IofCompleteRequest
0x14003fa20  nop     dword ptr [rax+rax+00h]
0x14003fa25  mov     eax, 103h
0x14003fa2a  test    bl, bl
0x14003fa2c  cmovnz  edi, eax
0x14003fa2f  mov     eax, edi
0x14003fa31  mov     rcx, [rsp+0A8h+var_40]
0x14003fa36  xor     rcx, rsp; StackCookie
0x14003fa39  call    __security_check_cookie
0x14003fa3e  mov     rbx, [rsp+0A8h+arg_8]
0x14003fa46  add     rsp, 70h
0x14003fa4a  pop     r15
0x14003fa4c  pop     r14
0x14003fa4e  pop     r13
0x14003fa50  pop     r12
0x14003fa52  pop     rdi
0x14003fa53  pop     rsi
0x14003fa54  pop     rbp
0x14003fa55  retn
```
