# CWerService::TryReportCrash(ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001ad28`
- end: `0x18001b0ac`
- name: `?TryReportCrash@CWerService@@AEAAJKKPEAX0PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `900`
- prototype: `__int64(__int64, DWORD, DWORD, void *, __int64, __int64, int, int, int, ...)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180016ac0`
- `0x180019d10`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x180015aa8`
- `0x18001ad28`
- `0x180022d54`
- `0x18002dd28`
- `0x18002de2c`
- `0x18002df50`
- `0x18002e034`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001adc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b07f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001adc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b07f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b093`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CWerService::TryReportCrash(
        __int64 a1,
        DWORD a2,
        DWORD a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        ...)
{
  void *v11; // rbx
  void *v12; // r14
  void **v13; // r12
  unsigned int v14; // edi
  int v15; // r13d
  void *v16; // rcx
  int IsCrashFatal; // eax
  int v18; // eax
  int Reservation; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  int v23; // eax
  char *v24; // rax
  __int64 v25; // r8
  int v26; // eax
  void *v27; // rax
  bool v28; // cf
  int v29; // eax
  void *v30; // rcx
  int v32; // [rsp+50h] [rbp-28h] BYREF
  CHandleMonitor *v33; // [rsp+58h] [rbp-20h] BYREF
  void *v34; // [rsp+60h] [rbp-18h] BYREF
  void *v35; // [rsp+68h] [rbp-10h] BYREF
  void **v40; // [rsp+108h] [rbp+90h] BYREF
  va_list va; // [rsp+108h] [rbp+90h]
  va_list va1; // [rsp+110h] [rbp+98h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v40 = va_arg(va1, void **);
  v32 = 0;
  v11 = 0;
  v34 = 0;
  v12 = 0;
  v35 = 0;
  LODWORD(v33) = 0;
  v13 = v40;
  if ( !v40 )
  {
    v14 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    goto LABEL_52;
  }
  v15 = 0;
  v16 = *v40;
  *v40 = 0;
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  IsCrashFatal = CWerService::IsCrashFatal((CWerService *)v16, a4, a2, (int *)&v33);
  if ( IsCrashFatal >= 0 )
  {
    v18 = (int)v33;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)IsCrashFatal);
    v18 = 1;
  }
  LODWORD(v40) = v18;
  v33 = (CHandleMonitor *)(a1 + 80);
  Reservation = CHandleMonitor::GetReservation((CHandleMonitor *)(a1 + 80), &v32);
  v14 = Reservation;
  if ( Reservation < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = 170;
      v22 = (unsigned int)Reservation;
LABEL_17:
      WPP_SF_d(v20[2], v21, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v22);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  if ( v32 )
  {
    v23 = ReportCrash(a2, a3, (__int64)a4, a5, a6, a7, a8, a9, &v34, &v35);
    v14 = v23;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          172,
          WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)v23);
      v11 = v34;
      v12 = v35;
      goto LABEL_49;
    }
    v12 = v35;
    v11 = v34;
    v24 = (char *)v34 + 1;
    if ( (unsigned __int64)v35 + 1 <= 1 )
    {
      if ( (unsigned __int64)v24 > 1 )
      {
        v28 = (_DWORD)v40 != 0;
        LODWORD(v40) = -(int)v40;
        v29 = CHandleMonitor::DupeAndAddHandle(v33, v34, v28 ? a3 : 0);
        if ( v29 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              175,
              WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
              (unsigned int)v29);
        }
        else
        {
          v15 = 1;
        }
      }
      if ( (unsigned __int64)v11 + 1 <= 1 )
        goto LABEL_48;
      v27 = v11;
      v11 = 0;
    }
    else
    {
      if ( (unsigned __int64)v24 <= 1 )
      {
        v14 = -2147418113;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = 173;
          v22 = 2147549183LL;
          goto LABEL_17;
        }
LABEL_49:
        if ( v32 && !v15 )
          CHandleMonitor::CancelReservation(v33);
        goto LABEL_52;
      }
      v25 = (_DWORD)v40 != 0 ? a3 : 0;
      v11 = 0;
      v40 = (void **)v34;
      v26 = CHandleMonitor::AddHandle(v33, (void ***)va, v25);
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            174,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)v26);
      }
      else
      {
        v15 = 1;
      }
      v27 = v12;
      v12 = 0;
    }
    v30 = *v13;
    *v13 = v27;
    if ( (unsigned __int64)v30 + 1 > 1 )
      CloseHandle(v30);
LABEL_48:
    v14 = 0;
    goto LABEL_49;
  }
  v14 = 1769483;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, a3);
LABEL_52:
  if ( (unsigned __int64)v12 + 1 > 1 )
    CloseHandle(v12);
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  return v14;
}

```

## disassembly

```asm
0x18001ad28  mov     rax, rsp
0x18001ad2b  mov     [rax+20h], r9
0x18001ad2f  mov     [rax+18h], r8d
0x18001ad33  mov     [rax+10h], edx
0x18001ad36  mov     [rax+8], rcx
0x18001ad3a  push    rbp
0x18001ad3b  push    rbx
0x18001ad3c  push    rsi
0x18001ad3d  push    rdi
0x18001ad3e  push    r12
0x18001ad40  push    r13
0x18001ad42  push    r14
0x18001ad44  push    r15
0x18001ad46  mov     rbp, rsp
0x18001ad49  sub     rsp, 78h
0x18001ad4d  mov     rdi, r9
0x18001ad50  mov     esi, edx
0x18001ad52  xor     eax, eax
0x18001ad54  mov     [rbp+var_28], eax
0x18001ad57  mov     ebx, eax
0x18001ad59  mov     [rbp+var_18], rax
0x18001ad5d  mov     r14d, eax
0x18001ad60  mov     [rbp+var_10], rax
0x18001ad64  mov     dword ptr [rbp+var_20], eax
0x18001ad67  mov     r12, [rbp+arg_48]
0x18001ad6e  test    r12, r12
0x18001ad71  jnz     short loc_18001ADB3
0x18001ad73  mov     edi, 80070057h
0x18001ad78  lea     rsi, WPP_GLOBAL_Control
0x18001ad7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad86  cmp     rcx, rsi
0x18001ad89  jz      loc_18001B072
0x18001ad8f  test    byte ptr [rcx+1Ch], 1
0x18001ad93  jz      loc_18001B072
0x18001ad99  mov     edx, 0A8h
0x18001ad9e  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001ada5  mov     rcx, [rcx+10h]
0x18001ada9  call    WPP_SF_
0x18001adae  jmp     loc_18001B072
0x18001adb3  mov     r13d, eax
0x18001adb6  mov     rcx, [r12]; hObject
0x18001adba  mov     [r12], rax
0x18001adbe  lea     rax, [rcx+1]
0x18001adc2  cmp     rax, 1
0x18001adc6  jbe     short loc_18001ADCE
0x18001adc8  call    cs:__imp_CloseHandle
0x18001adce  lea     r9, [rbp+var_20]; int *
0x18001add2  mov     r8d, esi; unsigned int
0x18001add5  mov     rdx, rdi; void *
0x18001add8  call    ?IsCrashFatal@CWerService@@AEAAJPEAXKPEAH@Z; CWerService::IsCrashFatal(void *,ulong,int *)
0x18001addd  lea     rsi, WPP_GLOBAL_Control
0x18001ade4  lea     r15, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001adeb  test    eax, eax
0x18001aded  jns     short loc_18001AE1C
0x18001adef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adf6  cmp     rcx, rsi
0x18001adf9  jz      short loc_18001AE15
0x18001adfb  test    byte ptr [rcx+1Ch], 2
0x18001adff  jz      short loc_18001AE15
0x18001ae01  mov     edx, 0A9h
0x18001ae06  mov     r9d, eax
0x18001ae09  mov     r8, r15
0x18001ae0c  mov     rcx, [rcx+10h]
0x18001ae10  call    WPP_SF_d
0x18001ae15  mov     eax, 1
0x18001ae1a  jmp     short loc_18001AE1F
0x18001ae1c  mov     eax, dword ptr [rbp+var_20]
0x18001ae1f  mov     dword ptr [rbp+arg_48], eax
0x18001ae25  mov     rax, [rbp+arg_0]
0x18001ae29  add     rax, 50h ; 'P'
0x18001ae2d  mov     [rbp+var_20], rax
0x18001ae31  lea     rdx, [rbp+var_28]; int *
0x18001ae35  mov     rcx, rax; this
0x18001ae38  call    ?GetReservation@CHandleMonitor@@QEAAJPEAH@Z; CHandleMonitor::GetReservation(int *)
0x18001ae3d  mov     edi, eax
0x18001ae3f  test    eax, eax
0x18001ae41  jns     short loc_18001AE76
0x18001ae43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae4a  cmp     rcx, rsi
0x18001ae4d  jz      loc_18001B05D
0x18001ae53  test    byte ptr [rcx+1Ch], 1
0x18001ae57  jz      loc_18001B05D
0x18001ae5d  mov     edx, 0AAh
0x18001ae62  mov     r9d, eax
0x18001ae65  mov     r8, r15
0x18001ae68  mov     rcx, [rcx+10h]
0x18001ae6c  call    WPP_SF_d
0x18001ae71  jmp     loc_18001B05D
0x18001ae76  cmp     [rbp+var_28], r13d
0x18001ae7a  jnz     short loc_18001AEB5
0x18001ae7c  mov     edi, 1B000Bh
0x18001ae81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae88  cmp     rcx, rsi
0x18001ae8b  jz      loc_18001B072
0x18001ae91  test    byte ptr [rcx+1Ch], 4
0x18001ae95  jz      loc_18001B072
0x18001ae9b  mov     edx, 0ABh
0x18001aea0  mov     r9d, [rbp+arg_10]
0x18001aea4  mov     r8, r15
0x18001aea7  mov     rcx, [rcx+10h]
0x18001aeab  call    WPP_SF_d
0x18001aeb0  jmp     loc_18001B072
0x18001aeb5  lea     rax, [rbp+var_10]
0x18001aeb9  mov     [rsp+78h+var_30], rax
0x18001aebe  lea     rax, [rbp+var_18]
0x18001aec2  mov     [rsp+78h+var_38], rax
0x18001aec7  mov     eax, [rbp+arg_40]
0x18001aecd  mov     [rsp+78h+var_40], eax
0x18001aed1  mov     eax, [rbp+arg_38]
0x18001aed7  mov     [rsp+78h+var_48], eax
0x18001aedb  mov     eax, [rbp+arg_30]
0x18001aede  mov     [rsp+78h+var_50], eax
0x18001aee2  mov     rax, [rbp+arg_28]
0x18001aee6  mov     [rsp+78h+var_58], rax
0x18001aeeb  mov     r9, [rbp+arg_20]
0x18001aeef  mov     r8, [rbp+arg_18]
0x18001aef3  mov     edx, [rbp+arg_10]
0x18001aef6  mov     ecx, [rbp+arg_8]
0x18001aef9  call    ?ReportCrash@@YAJKKPEAX0PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@2@Z; ReportCrash(ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)
0x18001aefe  mov     edi, eax
0x18001af00  test    eax, eax
0x18001af02  jns     short loc_18001AF37
0x18001af04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af0b  cmp     rcx, rsi
0x18001af0e  jz      short loc_18001AF2A
0x18001af10  test    byte ptr [rcx+1Ch], 1
0x18001af14  jz      short loc_18001AF2A
0x18001af16  mov     edx, 0ACh
0x18001af1b  mov     r9d, eax
0x18001af1e  mov     r8, r15
0x18001af21  mov     rcx, [rcx+10h]
0x18001af25  call    WPP_SF_d
0x18001af2a  mov     rbx, [rbp+var_18]
0x18001af2e  mov     r14, [rbp+var_10]
0x18001af32  jmp     loc_18001B05D
0x18001af37  mov     r14, [rbp+var_10]
0x18001af3b  lea     rax, [r14+1]
0x18001af3f  mov     edi, 1
0x18001af44  mov     rbx, [rbp+var_18]
0x18001af48  cmp     rax, rdi
0x18001af4b  lea     rax, [rbx+1]
0x18001af4f  jbe     loc_18001AFE9
0x18001af55  cmp     rax, rdi
0x18001af58  ja      short loc_18001AF89
0x18001af5a  mov     edi, 8000FFFFh
0x18001af5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af66  cmp     rcx, rsi
0x18001af69  jz      loc_18001B05D
0x18001af6f  test    byte ptr [rcx+1Ch], 1
0x18001af73  jz      loc_18001B05D
0x18001af79  mov     edx, 0ADh
0x18001af7e  mov     r9d, 8000FFFFh
0x18001af84  jmp     loc_18001AE65
0x18001af89  neg     dword ptr [rbp+arg_48]
0x18001af8f  sbb     r8d, r8d
0x18001af92  and     r8d, [rbp+arg_10]
0x18001af96  mov     rax, rbx
0x18001af99  xor     ebx, ebx
0x18001af9b  mov     [rbp+arg_48], rax
0x18001afa2  lea     rdx, [rbp+arg_48]
0x18001afa9  mov     rcx, [rbp+var_20]
0x18001afad  call    ?AddHandle@CHandleMonitor@@QEAAJV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K@Z; CHandleMonitor::AddHandle(tlx::unique_any<tlx::file_handle_traits>,ulong)
0x18001afb2  test    eax, eax
0x18001afb4  js      short loc_18001AFBB
0x18001afb6  mov     r13d, edi
0x18001afb9  jmp     short loc_18001AFE1
0x18001afbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afc2  cmp     rcx, rsi
0x18001afc5  jz      short loc_18001AFE1
0x18001afc7  test    byte ptr [rcx+1Ch], 2
0x18001afcb  jz      short loc_18001AFE1
0x18001afcd  mov     edx, 0AEh
0x18001afd2  mov     r9d, eax
0x18001afd5  mov     r8, r15
0x18001afd8  mov     rcx, [rcx+10h]
0x18001afdc  call    WPP_SF_d
0x18001afe1  mov     rax, r14
0x18001afe4  xor     r14d, r14d
0x18001afe7  jmp     short loc_18001B044
0x18001afe9  cmp     rax, rdi
0x18001afec  jbe     short loc_18001B036
0x18001afee  neg     dword ptr [rbp+arg_48]
0x18001aff4  sbb     r8d, r8d
0x18001aff7  and     r8d, [rbp+arg_10]; unsigned int
0x18001affb  mov     rdx, rbx; void *
0x18001affe  mov     rcx, [rbp+var_20]; this
0x18001b002  call    ?DupeAndAddHandle@CHandleMonitor@@QEAAJPEAXK@Z; CHandleMonitor::DupeAndAddHandle(void *,ulong)
0x18001b007  test    eax, eax
0x18001b009  js      short loc_18001B010
0x18001b00b  mov     r13d, edi
0x18001b00e  jmp     short loc_18001B036
0x18001b010  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b017  cmp     rcx, rsi
0x18001b01a  jz      short loc_18001B036
0x18001b01c  test    byte ptr [rcx+1Ch], 2
0x18001b020  jz      short loc_18001B036
0x18001b022  mov     edx, 0AFh
0x18001b027  mov     r9d, eax
0x18001b02a  mov     r8, r15
0x18001b02d  mov     rcx, [rcx+10h]
0x18001b031  call    WPP_SF_d
0x18001b036  lea     rax, [rbx+1]
0x18001b03a  cmp     rax, rdi
0x18001b03d  jbe     short loc_18001B05B
0x18001b03f  mov     rax, rbx
0x18001b042  xor     ebx, ebx
0x18001b044  mov     rcx, [r12]; hObject
0x18001b048  mov     [r12], rax
0x18001b04c  lea     rax, [rcx+1]
0x18001b050  cmp     rax, rdi
0x18001b053  jbe     short loc_18001B05B
0x18001b055  call    cs:__imp_CloseHandle
0x18001b05b  xor     edi, edi
0x18001b05d  cmp     [rbp+var_28], 0
0x18001b061  jz      short loc_18001B072
0x18001b063  test    r13d, r13d
0x18001b066  jnz     short loc_18001B072
0x18001b068  mov     rcx, [rbp+var_20]; this
0x18001b06c  call    ?CancelReservation@CHandleMonitor@@QEAAJXZ; CHandleMonitor::CancelReservation(void)
0x18001b071  nop
0x18001b072  lea     rax, [r14+1]
0x18001b076  cmp     rax, 1
0x18001b07a  jbe     short loc_18001B086
0x18001b07c  mov     rcx, r14; hObject
0x18001b07f  call    cs:__imp_CloseHandle
0x18001b085  nop
0x18001b086  lea     rax, [rbx+1]
0x18001b08a  cmp     rax, 1
0x18001b08e  jbe     short loc_18001B099
0x18001b090  mov     rcx, rbx; hObject
0x18001b093  call    cs:__imp_CloseHandle
0x18001b099  mov     eax, edi
0x18001b09b  add     rsp, 78h
0x18001b09f  pop     r15
0x18001b0a1  pop     r14
0x18001b0a3  pop     r13
0x18001b0a5  pop     r12
0x18001b0a7  pop     rdi
0x18001b0a8  pop     rsi
0x18001b0a9  pop     rbx
0x18001b0aa  pop     rbp
0x18001b0ab  retn
```
