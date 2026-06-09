# CUser::ApplyLogonHoursRestrictions(void)

- ea: `0x14003fc3c`
- end: `0x1400400dc`
- name: `?ApplyLogonHoursRestrictions@CUser@@QEAAKXZ`
- size: `1184`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047370`
- `0x140072040`

## callees

- `0x1400057f4`
- `0x14000bcb0`
- `0x14002d410`
- `0x14003fc3c`
- `0x14004137c`
- `0x140041c34`
- `0x140082434`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003fdd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140040016`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003fdd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140040016`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003fdf9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14004002c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003fdf9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14004002c`
- `ntdll!TpAllocTimer` at `0x14003feb4`
- `ntdll!TpAllocTimer` at `0x14003ff6d`
- `ntdll!TpAllocTimer` at `0x14003feb4`
- `ntdll!TpAllocTimer` at `0x14003ff6d`
- `ntdll!TpSetTimer` at `0x14003fc82`
- `ntdll!TpSetTimer` at `0x14003fca0`
- `ntdll!TpSetTimer` at `0x14003ff04`
- `ntdll!TpSetTimer` at `0x14003ffdb`
- `ntdll!TpSetTimer` at `0x14003fc82`
- `ntdll!TpSetTimer` at `0x14003fca0`
- `ntdll!TpSetTimer` at `0x14003ff04`
- `ntdll!TpSetTimer` at `0x14003ffdb`
- `ntdll!RtlNtStatusToDosError` at `0x14003ff79`
- `ntdll!RtlNtStatusToDosError` at `0x14003ff79`

## pseudocode

```c
__int64 __fastcall CUser::ApplyLogonHoursRestrictions(CUser *this)
{
  unsigned int v2; // ebx
  _QWORD *v3; // r15
  __int64 v4; // rcx
  _QWORD *v5; // r12
  __int64 v6; // rcx
  CUser *v7; // rcx
  __int64 v8; // rdx
  _DWORD *v9; // r14
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  CUser *v16; // rcx
  __int64 v17; // rdx
  NTSTATUS v18; // eax
  ULONG v19; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+10h] BYREF
  __int64 v22; // [rsp+90h] [rbp+18h] BYREF
  FILETIME FileTime2; // [rsp+98h] [rbp+20h] BYREF

  v2 = 5;
  SystemTimeAsFileTime = 0;
  FileTime2 = 0;
  v3 = (_QWORD *)((char *)this + 280);
  v4 = *((_QWORD *)this + 35);
  if ( v4 )
    TpSetTimer(v4, 0, 0, 0);
  v5 = (_QWORD *)((char *)this + 288);
  v6 = *((_QWORD *)this + 36);
  if ( v6 )
    TpSetTimer(v6, 0, 0, 0);
  WlRemindersTerminate(4);
  if ( *((_DWORD *)this + 38) )
  {
    v2 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = 95;
LABEL_68:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
      goto LABEL_69;
    }
    goto LABEL_69;
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 30) + 16LL) != 0x7FFFFFFFFFFFFFFFLL )
  {
    v9 = (_DWORD *)((char *)this + 296);
    CUser::RegQueryDWORD(
      this,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
      L"LogonHoursAction",
      0,
      (unsigned int *)this + 74);
    v10 = *((_DWORD *)this + 74);
    if ( !v10 )
    {
      v2 = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = 97;
        goto LABEL_68;
      }
      goto LABEL_69;
    }
    v11 = v10 - 1;
    if ( v11 && (unsigned int)(v11 - 1) >= 2 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
          (unsigned int)*v9);
      }
      *v9 = 3;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    FileTime2 = *(FILETIME *)(*((_QWORD *)this + 30) + 16LL);
    if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) >= 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 99;
        goto LABEL_68;
      }
      goto LABEL_69;
    }
    v12 = *((_QWORD *)this + 30);
    v13 = *(_QWORD *)(v12 + 16) - *(_QWORD *)&SystemTimeAsFileTime;
    if ( v13 <= 1200000000 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = 102;
        goto LABEL_47;
      }
    }
    else
    {
      v22 = 0;
      if ( v13 <= 9000000000LL )
      {
        *((_DWORD *)this + 75) = 1;
        v14 = *(_QWORD *)(v12 + 16) - 600000000LL;
      }
      else
      {
        *((_DWORD *)this + 75) = 15;
        v14 = *(_QWORD *)(v12 + 16) - 9000000000LL;
      }
      v22 = v14;
      if ( !*v3 )
      {
        v15 = TpAllocTimer(v3, CUser::LogonHoursWarningCallback, this, 0);
        if ( v15 < 0
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            100,
            WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
            (unsigned int)v15);
        }
      }
      if ( *v3 )
      {
        TpSetTimer(*v3, &v22, 0, 0);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v17 = 101;
LABEL_47:
          WPP_SF_(*((_QWORD *)v16 + 2), v17, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
        }
      }
    }
    if ( *v5 || (v18 = TpAllocTimer((char *)this + 288, CUser::LogonHoursActionCallback, this, 0), v18 >= 0) )
    {
      TpSetTimer(*v5, *((_QWORD *)this + 30) + 16LL, 0, 0);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) < 0 )
      {
        v2 = 0;
        goto LABEL_69;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 105;
        goto LABEL_68;
      }
    }
    else
    {
      v19 = RtlNtStatusToDosError(v18);
      v2 = v19;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v19);
      }
    }
    goto LABEL_69;
  }
  v2 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v8 = 96;
    goto LABEL_68;
  }
LABEL_69:
  if ( v2 )
  {
    if ( *v3 )
      WaitForAndDeleteTimer(v3);
    if ( *v5 )
      WaitForAndDeleteTimer((char *)this + 288);
    if ( *((_DWORD *)this + 74) )
      CUser::LogonHoursTakeAction(this);
  }
  return v2;
}

```

## disassembly

```asm
0x14003fc3c  mov     rax, rsp
0x14003fc3f  mov     [rax+8], rcx
0x14003fc43  push    rbx
0x14003fc44  push    rsi
0x14003fc45  push    rdi
0x14003fc46  push    r12
0x14003fc48  push    r14
0x14003fc4a  push    r15
0x14003fc4c  sub     rsp, 48h
0x14003fc50  mov     rsi, rcx
0x14003fc53  mov     ebx, 5
0x14003fc58  mov     [rax-48h], ebx
0x14003fc5b  mov     qword ptr [rax+10h], 0
0x14003fc63  mov     qword ptr [rax+20h], 0
0x14003fc6b  lea     r15, [rcx+118h]
0x14003fc72  mov     rcx, [r15]
0x14003fc75  test    rcx, rcx
0x14003fc78  jz      short loc_14003FC88
0x14003fc7a  xor     r9d, r9d
0x14003fc7d  xor     r8d, r8d
0x14003fc80  xor     edx, edx
0x14003fc82  call    cs:__imp_TpSetTimer
0x14003fc88  lea     r12, [rsi+120h]
0x14003fc8f  mov     rcx, [r12]
0x14003fc93  test    rcx, rcx
0x14003fc96  jz      short loc_14003FCA6
0x14003fc98  xor     r9d, r9d
0x14003fc9b  xor     r8d, r8d
0x14003fc9e  xor     edx, edx
0x14003fca0  call    cs:__imp_TpSetTimer
0x14003fca6  mov     ecx, 4
0x14003fcab  call    ?WlRemindersTerminate@@YAKW4WlReminderType@@@Z; WlRemindersTerminate(WlReminderType)
0x14003fcb0  cmp     dword ptr [rsi+98h], 0
0x14003fcb7  jz      short loc_14003FCF2
0x14003fcb9  xor     ebx, ebx
0x14003fcbb  mov     [rsp+78h+var_48], ebx
0x14003fcbf  lea     rdi, WPP_GLOBAL_Control
0x14003fcc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fccd  cmp     rcx, rdi
0x14003fcd0  jz      loc_14004009A
0x14003fcd6  test    byte ptr [rcx+1Ch], 20h
0x14003fcda  jz      loc_14004009A
0x14003fce0  cmp     byte ptr [rcx+19h], 4
0x14003fce4  jb      loc_14004009A
0x14003fcea  lea     edx, [rbx+5Fh]
0x14003fced  jmp     loc_140040089
0x14003fcf2  mov     rax, [rsi+0F0h]
0x14003fcf9  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14003fd03  cmp     [rax+10h], rcx
0x14003fd07  jnz     short loc_14003FD42
0x14003fd09  xor     ebx, ebx
0x14003fd0b  mov     [rsp+78h+var_48], ebx
0x14003fd0f  lea     rdi, WPP_GLOBAL_Control
0x14003fd16  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd1d  cmp     rcx, rdi
0x14003fd20  jz      loc_14004009A
0x14003fd26  test    byte ptr [rcx+1Ch], 20h
0x14003fd2a  jz      loc_14004009A
0x14003fd30  cmp     byte ptr [rcx+19h], 4
0x14003fd34  jb      loc_14004009A
0x14003fd3a  lea     edx, [rbx+60h]
0x14003fd3d  jmp     loc_140040089
0x14003fd42  lea     r14, [rsi+128h]
0x14003fd49  mov     [rsp+78h+var_58], r14; unsigned int *
0x14003fd4e  xor     r9d, r9d; unsigned int
0x14003fd51  lea     r8, aLogonhoursacti; "LogonHoursAction"
0x14003fd58  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14003fd5f  mov     rcx, rsi; this
0x14003fd62  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14003fd67  mov     eax, [r14]
0x14003fd6a  test    eax, eax
0x14003fd6c  jz      loc_140040061
0x14003fd72  sub     eax, 1
0x14003fd75  jz      short loc_14003FDC1
0x14003fd77  sub     eax, 1
0x14003fd7a  jz      short loc_14003FDC1
0x14003fd7c  cmp     eax, 1
0x14003fd7f  jz      short loc_14003FDC1
0x14003fd81  lea     rdi, WPP_GLOBAL_Control
0x14003fd88  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd8f  cmp     rcx, rdi
0x14003fd92  jz      short loc_14003FDB8
0x14003fd94  test    byte ptr [rcx+1Ch], 20h
0x14003fd98  jz      short loc_14003FDB8
0x14003fd9a  cmp     byte ptr [rcx+19h], 2
0x14003fd9e  jb      short loc_14003FDB8
0x14003fda0  mov     edx, 62h ; 'b'
0x14003fda5  mov     r9d, [r14]
0x14003fda8  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003fdaf  mov     rcx, [rcx+10h]
0x14003fdb3  call    WPP_SF_d
0x14003fdb8  mov     dword ptr [r14], 3
0x14003fdbf  jmp     short loc_14003FDC8
0x14003fdc1  lea     rdi, WPP_GLOBAL_Control
0x14003fdc8  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003fdd0  call    cs:__imp_GetSystemTimeAsFileTime
0x14003fdd6  mov     rax, [rsi+0F0h]
0x14003fddd  mov     rcx, [rax+10h]
0x14003fde1  mov     qword ptr [rsp+78h+FileTime2.dwLowDateTime], rcx
0x14003fde9  lea     rdx, [rsp+78h+FileTime2]; lpFileTime2
0x14003fdf1  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime1
0x14003fdf9  call    cs:__imp_CompareFileTime
0x14003fdff  test    eax, eax
0x14003fe01  js      short loc_14003FE35
0x14003fe03  mov     [rsp+78h+var_48], ebx
0x14003fe07  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fe0e  cmp     rcx, rdi
0x14003fe11  jz      loc_14004009A
0x14003fe17  test    byte ptr [rcx+1Ch], 20h
0x14003fe1b  jz      loc_14004009A
0x14003fe21  cmp     byte ptr [rcx+19h], 2
0x14003fe25  jb      loc_14004009A
0x14003fe2b  mov     edx, 63h ; 'c'
0x14003fe30  jmp     loc_140040089
0x14003fe35  mov     rcx, [rsi+0F0h]
0x14003fe3c  mov     rax, [rcx+10h]
0x14003fe40  sub     rax, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x14003fe48  cmp     rax, 47868C00h
0x14003fe4e  jle     loc_14003FF29
0x14003fe54  mov     [rsp+78h+arg_10], 0
0x14003fe60  mov     rdx, 218711A00h
0x14003fe6a  cmp     rax, rdx
0x14003fe6d  jle     short loc_14003FE82
0x14003fe6f  mov     dword ptr [rsi+12Ch], 0Fh
0x14003fe79  mov     rax, [rcx+10h]
0x14003fe7d  sub     rax, rdx
0x14003fe80  jmp     short loc_14003FE96
0x14003fe82  mov     dword ptr [rsi+12Ch], 1
0x14003fe8c  mov     rax, [rcx+10h]
0x14003fe90  sub     rax, 23C34600h
0x14003fe96  mov     [rsp+78h+arg_10], rax
0x14003fe9e  cmp     qword ptr [r15], 0
0x14003fea2  jnz     short loc_14003FEEE
0x14003fea4  xor     r9d, r9d
0x14003fea7  mov     r8, rsi
0x14003feaa  lea     rdx, ?LogonHoursWarningCallback@CUser@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; CUser::LogonHoursWarningCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x14003feb1  mov     rcx, r15
0x14003feb4  call    cs:__imp_TpAllocTimer
0x14003feba  test    eax, eax
0x14003febc  jns     short loc_14003FEEE
0x14003febe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fec5  cmp     rcx, rdi
0x14003fec8  jz      short loc_14003FEEE
0x14003feca  test    byte ptr [rcx+1Ch], 20h
0x14003fece  jz      short loc_14003FEEE
0x14003fed0  cmp     byte ptr [rcx+19h], 2
0x14003fed4  jb      short loc_14003FEEE
0x14003fed6  mov     edx, 64h ; 'd'
0x14003fedb  mov     r9d, eax
0x14003fede  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003fee5  mov     rcx, [rcx+10h]
0x14003fee9  call    WPP_SF_d
0x14003feee  mov     rcx, [r15]
0x14003fef1  test    rcx, rcx
0x14003fef4  jz      short loc_14003FF56
0x14003fef6  xor     r9d, r9d
0x14003fef9  xor     r8d, r8d
0x14003fefc  lea     rdx, [rsp+78h+arg_10]
0x14003ff04  call    cs:__imp_TpSetTimer
0x14003ff0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ff11  cmp     rcx, rdi
0x14003ff14  jz      short loc_14003FF56
0x14003ff16  test    byte ptr [rcx+1Ch], 20h
0x14003ff1a  jz      short loc_14003FF56
0x14003ff1c  cmp     byte ptr [rcx+19h], 4
0x14003ff20  jb      short loc_14003FF56
0x14003ff22  mov     edx, 65h ; 'e'
0x14003ff27  jmp     short loc_14003FF46
0x14003ff29  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ff30  cmp     rcx, rdi
0x14003ff33  jz      short loc_14003FF56
0x14003ff35  test    byte ptr [rcx+1Ch], 20h
0x14003ff39  jz      short loc_14003FF56
0x14003ff3b  cmp     byte ptr [rcx+19h], 4
0x14003ff3f  jb      short loc_14003FF56
0x14003ff41  mov     edx, 66h ; 'f'
0x14003ff46  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003ff4d  mov     rcx, [rcx+10h]
0x14003ff51  call    WPP_SF_
0x14003ff56  cmp     qword ptr [r12], 0
0x14003ff5b  jnz     short loc_14003FFC6
0x14003ff5d  xor     r9d, r9d
0x14003ff60  mov     r8, rsi
0x14003ff63  lea     rdx, ?LogonHoursActionCallback@CUser@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; CUser::LogonHoursActionCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x14003ff6a  mov     rcx, r12
0x14003ff6d  call    cs:__imp_TpAllocTimer
0x14003ff73  test    eax, eax
0x14003ff75  jns     short loc_14003FFC6
0x14003ff77  mov     ecx, eax; Status
0x14003ff79  call    cs:__imp_RtlNtStatusToDosError
0x14003ff7f  mov     ebx, eax
0x14003ff81  mov     [rsp+78h+var_48], eax
0x14003ff85  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ff8c  cmp     rcx, rdi
0x14003ff8f  jz      loc_14004009A
0x14003ff95  test    byte ptr [rcx+1Ch], 20h
0x14003ff99  jz      loc_14004009A
0x14003ff9f  cmp     byte ptr [rcx+19h], 2
0x14003ffa3  jb      loc_14004009A
0x14003ffa9  mov     edx, 67h ; 'g'
0x14003ffae  mov     r9d, eax
0x14003ffb1  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003ffb8  mov     rcx, [rcx+10h]
0x14003ffbc  call    WPP_SF_d
0x14003ffc1  jmp     loc_14004009A
0x14003ffc6  mov     rdx, [rsi+0F0h]
0x14003ffcd  add     rdx, 10h
0x14003ffd1  xor     r9d, r9d
0x14003ffd4  xor     r8d, r8d
0x14003ffd7  mov     rcx, [r12]
0x14003ffdb  call    cs:__imp_TpSetTimer
0x14003ffe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ffe8  cmp     rcx, rdi
0x14003ffeb  jz      short loc_14004000E
0x14003ffed  test    byte ptr [rcx+1Ch], 20h
0x14003fff1  jz      short loc_14004000E
0x14003fff3  cmp     byte ptr [rcx+19h], 4
0x14003fff7  jb      short loc_14004000E
0x14003fff9  mov     edx, 68h ; 'h'
0x14003fffe  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140040005  mov     rcx, [rcx+10h]
0x140040009  call    WPP_SF_
0x14004000e  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140040016  call    cs:__imp_GetSystemTimeAsFileTime
0x14004001c  lea     rdx, [rsp+78h+FileTime2]; lpFileTime2
0x140040024  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime1
0x14004002c  call    cs:__imp_CompareFileTime
0x140040032  test    eax, eax
0x140040034  js      short loc_140040059
0x140040036  mov     [rsp+78h+var_48], ebx
0x14004003a  mov     rcx, cs:WPP_GLOBAL_Control
0x140040041  cmp     rcx, rdi
0x140040044  jz      short loc_14004009A
0x140040046  test    byte ptr [rcx+1Ch], 20h
0x14004004a  jz      short loc_14004009A
0x14004004c  cmp     byte ptr [rcx+19h], 2
0x140040050  jb      short loc_14004009A
0x140040052  mov     edx, 69h ; 'i'
0x140040057  jmp     short loc_140040089
0x140040059  xor     ebx, ebx
0x14004005b  mov     [rsp+78h+var_48], ebx
0x14004005f  jmp     short loc_14004009A
0x140040061  xor     ebx, ebx
0x140040063  mov     [rsp+78h+var_48], ebx
0x140040067  lea     rdi, WPP_GLOBAL_Control
0x14004006e  mov     rcx, cs:WPP_GLOBAL_Control
0x140040075  cmp     rcx, rdi
0x140040078  jz      short loc_14004009A
0x14004007a  test    byte ptr [rcx+1Ch], 20h
0x14004007e  jz      short loc_14004009A
0x140040080  cmp     byte ptr [rcx+19h], 4
0x140040084  jb      short loc_14004009A
0x140040086  lea     edx, [rbx+61h]
0x140040089  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140040090  mov     rcx, [rcx+10h]
0x140040094  call    WPP_SF_
0x140040099  nop
0x14004009a  test    ebx, ebx
0x14004009c  jz      short loc_1400400CC
0x14004009e  cmp     qword ptr [r15], 0
0x1400400a2  jz      short loc_1400400AC
0x1400400a4  mov     rcx, r15
0x1400400a7  call    WaitForAndDeleteTimer
0x1400400ac  cmp     qword ptr [r12], 0
0x1400400b1  jz      short loc_1400400BB
0x1400400b3  mov     rcx, r12
0x1400400b6  call    WaitForAndDeleteTimer
0x1400400bb  cmp     dword ptr [rsi+128h], 0
0x1400400c2  jz      short loc_1400400CC
0x1400400c4  mov     rcx, rsi; this
0x1400400c7  call    ?LogonHoursTakeAction@CUser@@AEAAKXZ; CUser::LogonHoursTakeAction(void)
0x1400400cc  mov     eax, ebx
0x1400400ce  add     rsp, 48h
0x1400400d2  pop     r15
0x1400400d4  pop     r14
0x1400400d6  pop     r12
0x1400400d8  pop     rdi
0x1400400d9  pop     rsi
0x1400400da  pop     rbx
0x1400400db  retn
0x14009e7f0  push    rbx
0x14009e7f2  push    rbp
0x14009e7f3  sub     rsp, 38h
0x14009e7f7  mov     rbp, rdx
0x14009e7fa  cmp     dword ptr [rbp+30h], 0
0x14009e7fe  jz      short loc_14009E847
0x14009e800  mov     rbx, [rbp+80h]
0x14009e807  cmp     qword ptr [rbx+118h], 0
0x14009e80f  jz      short loc_14009E81E
0x14009e811  lea     rcx, [rbx+118h]
0x14009e818  call    WaitForAndDeleteTimer
0x14009e81d  nop
0x14009e81e  cmp     qword ptr [rbx+120h], 0
0x14009e826  jz      short loc_14009E835
0x14009e828  lea     rcx, [rbx+120h]
0x14009e82f  call    WaitForAndDeleteTimer
0x14009e834  nop
0x14009e835  cmp     dword ptr [rbx+128h], 0
0x14009e83c  jz      short loc_14009E847
0x14009e83e  mov     rcx, rbx; this
  ... truncated ...
```
