# NotificationServiceImpl::FinalConstruct(void)

- ea: `0x18006cff8`
- end: `0x18006d2d6`
- name: `?FinalConstruct@NotificationServiceImpl@@AEAAJXZ`
- size: `734`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18006c720`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18006cff8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d215`
- `ntdll!RtlQueryWnfStateData` at `0x18006d15e`
- `ntdll!RtlQueryWnfStateData` at `0x18006d15e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006d0b3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006d0b3`
- `ntdll!RtlNtStatusToDosError` at `0x18006d0eb`
- `ntdll!RtlNtStatusToDosError` at `0x18006d198`
- `ntdll!RtlNtStatusToDosError` at `0x18006d0eb`
- `ntdll!RtlNtStatusToDosError` at `0x18006d198`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d1ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d1ff`

## string_xrefs

- `0x18006d10c`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d1b9`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d25e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NotificationServiceImpl::FinalConstruct(NotificationServiceImpl *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  NTSTATUS v4; // ebx
  signed int v5; // eax
  PVOID *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  NTSTATUS v9; // ebx
  signed int v10; // eax
  PTP_WORK v11; // rax
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-49h]
  struct _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+40h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v17; // [rsp+D0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  *(_QWORD *)&pcbe.Version = 3;
  v2 = 0;
  *(_QWORD *)&pcbe.Size = 72;
  memset(&pcbe.Pool, 0, 52);
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  if ( *((_DWORD *)this + 24) )
  {
    v17 = 0;
    v3 = RtlSubscribeWnfStateChangeNotification(
           (char *)this + 328,
           WNF_CELL_POSSIBLE_DATA_ACTIVITY_CHANGE_MODEM0,
           0,
           NotificationServiceImpl::CellStatusWnfCallbackThunk);
    v4 = v3;
    if ( v3 >= 0 )
    {
      v2 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v3);
      }
      v5 = RtlNtStatusToDosError(v4);
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
    }
    if ( (v2 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v2,
        (int)this);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v2;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_43;
      v7 = 16;
LABEL_41:
      WPP_SF_d(v6[2], v7, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v2);
LABEL_42:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    v14 = 0;
    v8 = RtlQueryWnfStateData(
           &v17,
           WNF_CELL_POSSIBLE_DATA_ACTIVITY_CHANGE_MODEM0,
           NotificationServiceImpl::CellStatusWnfCallbackThunk,
           this);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v2 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v8);
      }
      v10 = RtlNtStatusToDosError(v9);
      v2 = v10;
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
    }
    if ( (v2 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v2,
        0);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v2;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_43;
      v7 = 18;
      goto LABEL_41;
    }
  }
  v11 = CreateThreadpoolWork((PTP_WORK_CALLBACK)NotificationServiceImpl::RegistrationProcessingCallback, this, &pcbe);
  *((_QWORD *)this + 42) = v11;
  if ( v11 )
    goto LABEL_42;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
    goto LABEL_42;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v2);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xEA,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)v2,
    v14);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    {
LABEL_43:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 21, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v2);
      return v2;
    }
    v7 = 20;
    goto LABEL_41;
  }
  return v2;
}

```

## disassembly

```asm
0x18006cff8  push    rbp
0x18006cffa  push    rbx
0x18006cffb  push    rsi
0x18006cffc  push    rdi
0x18006cffd  push    r14
0x18006cfff  push    r15
0x18006d001  lea     rbp, [rsp-2Fh]
0x18006d006  sub     rsp, 98h
0x18006d00d  mov     rdi, rcx
0x18006d010  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d017  lea     r14, WPP_GLOBAL_Control
0x18006d01e  lea     r15, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006d025  cmp     rcx, r14
0x18006d028  jz      short loc_18006D047
0x18006d02a  test    byte ptr [rcx+1Ch], 2
0x18006d02e  jz      short loc_18006D047
0x18006d030  cmp     byte ptr [rcx+19h], 6
0x18006d034  jb      short loc_18006D047
0x18006d036  mov     rcx, [rcx+10h]
0x18006d03a  mov     edx, 0Eh
0x18006d03f  mov     r8, r15
0x18006d042  call    WPP_SF_
0x18006d047  xor     esi, esi
0x18006d049  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x18006d051  xorps   xmm0, xmm0
0x18006d054  mov     ebx, esi
0x18006d056  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x18006d05e  mov     [rbp+57h+pcbe.Pool], rsi
0x18006d062  mov     [rbp+57h+pcbe.CleanupGroup], rsi
0x18006d066  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], rsi
0x18006d06a  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x18006d06f  mov     [rbp+57h+pcbe.FinalizationCallback], rsi
0x18006d073  mov     dword ptr [rbp+57h+pcbe.u], esi
0x18006d076  mov     [rbp+57h+pcbe.CallbackPriority], 1
0x18006d07d  cmp     [rdi+60h], esi
0x18006d080  jz      loc_18006D1F1
0x18006d086  mov     rdx, cs:WNF_CELL_POSSIBLE_DATA_ACTIVITY_CHANGE_MODEM0
0x18006d08d  lea     rcx, [rdi+148h]
0x18006d094  mov     [rsp+0C0h+var_88], esi
0x18006d098  lea     r9, ?CellStatusWnfCallbackThunk@NotificationServiceImpl@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; NotificationServiceImpl::CellStatusWnfCallbackThunk(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18006d09f  mov     [rsp+0C0h+var_90], esi
0x18006d0a3  xor     r8d, r8d
0x18006d0a6  mov     [rsp+0C0h+var_98], rsi
0x18006d0ab  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x18006d0b0  mov     [rbp+57h+arg_0], esi
0x18006d0b3  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18006d0b9  mov     ebx, eax
0x18006d0bb  test    eax, eax
0x18006d0bd  jns     short loc_18006D102
0x18006d0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d0c6  cmp     rcx, r14
0x18006d0c9  jz      short loc_18006D0E9
0x18006d0cb  test    byte ptr [rcx+1Ch], 4
0x18006d0cf  jz      short loc_18006D0E9
0x18006d0d1  cmp     byte ptr [rcx+19h], 2
0x18006d0d5  jb      short loc_18006D0E9
0x18006d0d7  mov     rcx, [rcx+10h]
0x18006d0db  lea     edx, [rsi+0Fh]
0x18006d0de  mov     r9d, eax
0x18006d0e1  mov     r8, r15
0x18006d0e4  call    WPP_SF_d
0x18006d0e9  mov     ecx, ebx; Status
0x18006d0eb  call    cs:__imp_RtlNtStatusToDosError
0x18006d0f1  mov     ebx, eax
0x18006d0f3  test    eax, eax
0x18006d0f5  jle     short loc_18006D104
0x18006d0f7  movzx   ebx, ax
0x18006d0fa  or      ebx, 80070000h
0x18006d100  jmp     short loc_18006D104
0x18006d102  mov     ebx, esi
0x18006d104  test    ebx, ebx
0x18006d106  jns     short loc_18006D144
0x18006d108  mov     rcx, [rbp+5Fh]; this
0x18006d10c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d113  mov     r9d, ebx; char *
0x18006d116  mov     edx, 0D5h; void *
0x18006d11b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d120  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d127  cmp     rcx, r14
0x18006d12a  jz      loc_18006D2C4
0x18006d130  test    byte ptr [rcx+1Ch], 80h
0x18006d134  jz      loc_18006D29F
0x18006d13a  mov     edx, 10h
0x18006d13f  jmp     loc_18006D289
0x18006d144  mov     rdx, cs:WNF_CELL_POSSIBLE_DATA_ACTIVITY_CHANGE_MODEM0
0x18006d14b  lea     r8, ?CellStatusWnfCallbackThunk@NotificationServiceImpl@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; NotificationServiceImpl::CellStatusWnfCallbackThunk(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18006d152  mov     r9, rdi
0x18006d155  mov     qword ptr [rsp+0C0h+var_A0], rsi; int
0x18006d15a  lea     rcx, [rbp+57h+arg_0]
0x18006d15e  call    cs:__imp_RtlQueryWnfStateData
0x18006d164  mov     ebx, eax
0x18006d166  test    eax, eax
0x18006d168  jns     short loc_18006D1AF
0x18006d16a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d171  cmp     rcx, r14
0x18006d174  jz      short loc_18006D196
0x18006d176  test    byte ptr [rcx+1Ch], 4
0x18006d17a  jz      short loc_18006D196
0x18006d17c  cmp     byte ptr [rcx+19h], 2
0x18006d180  jb      short loc_18006D196
0x18006d182  mov     rcx, [rcx+10h]
0x18006d186  mov     edx, 11h
0x18006d18b  mov     r9d, eax
0x18006d18e  mov     r8, r15
0x18006d191  call    WPP_SF_d
0x18006d196  mov     ecx, ebx; Status
0x18006d198  call    cs:__imp_RtlNtStatusToDosError
0x18006d19e  mov     ebx, eax
0x18006d1a0  test    eax, eax
0x18006d1a2  jle     short loc_18006D1B1
0x18006d1a4  movzx   ebx, ax
0x18006d1a7  or      ebx, 80070000h
0x18006d1ad  jmp     short loc_18006D1B1
0x18006d1af  mov     ebx, esi
0x18006d1b1  test    ebx, ebx
0x18006d1b3  jns     short loc_18006D1F1
0x18006d1b5  mov     rcx, [rbp+5Fh]; this
0x18006d1b9  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d1c0  mov     r9d, ebx; char *
0x18006d1c3  mov     edx, 0E2h; void *
0x18006d1c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d1d4  cmp     rcx, r14
0x18006d1d7  jz      loc_18006D2C4
0x18006d1dd  test    byte ptr [rcx+1Ch], 80h
0x18006d1e1  jz      loc_18006D29F
0x18006d1e7  mov     edx, 12h
0x18006d1ec  jmp     loc_18006D289
0x18006d1f1  lea     r8, [rbp+57h+pcbe]; pcbe
0x18006d1f5  mov     rdx, rdi; pv
0x18006d1f8  lea     rcx, ?RegistrationProcessingCallback@NotificationServiceImpl@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006d1ff  call    cs:__imp_CreateThreadpoolWork
0x18006d205  mov     [rdi+150h], rax
0x18006d20c  test    rax, rax
0x18006d20f  jnz     loc_18006D298
0x18006d215  call    cs:__imp_GetLastError
0x18006d21b  mov     ebx, eax
0x18006d21d  test    eax, eax
0x18006d21f  jle     short loc_18006D22A
0x18006d221  movzx   ebx, ax
0x18006d224  or      ebx, 80070000h
0x18006d22a  test    ebx, ebx
0x18006d22c  jns     short loc_18006D298
0x18006d22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d235  cmp     rcx, r14
0x18006d238  jz      short loc_18006D25A
0x18006d23a  test    byte ptr [rcx+1Ch], 8
0x18006d23e  jz      short loc_18006D25A
0x18006d240  cmp     byte ptr [rcx+19h], 2
0x18006d244  jb      short loc_18006D25A
0x18006d246  mov     rcx, [rcx+10h]
0x18006d24a  mov     edx, 13h
0x18006d24f  mov     r9d, ebx
0x18006d252  mov     r8, r15
0x18006d255  call    WPP_SF_d
0x18006d25a  mov     rcx, [rbp+5Fh]; this
0x18006d25e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d265  mov     r9d, ebx; char *
0x18006d268  mov     edx, 0EAh; void *
0x18006d26d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d272  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d279  cmp     rcx, r14
0x18006d27c  jz      short loc_18006D2C4
0x18006d27e  test    byte ptr [rcx+1Ch], 80h
0x18006d282  jz      short loc_18006D29F
0x18006d284  mov     edx, 14h
0x18006d289  mov     rcx, [rcx+10h]
0x18006d28d  mov     r9d, ebx
0x18006d290  mov     r8, r15
0x18006d293  call    WPP_SF_d
0x18006d298  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d29f  cmp     rcx, r14
0x18006d2a2  jz      short loc_18006D2C4
0x18006d2a4  test    byte ptr [rcx+1Ch], 2
0x18006d2a8  jz      short loc_18006D2C4
0x18006d2aa  cmp     byte ptr [rcx+19h], 6
0x18006d2ae  jb      short loc_18006D2C4
0x18006d2b0  mov     rcx, [rcx+10h]
0x18006d2b4  mov     edx, 15h
0x18006d2b9  mov     r9d, ebx
0x18006d2bc  mov     r8, r15
0x18006d2bf  call    WPP_SF_d
0x18006d2c4  mov     eax, ebx
0x18006d2c6  add     rsp, 98h
0x18006d2cd  pop     r15
0x18006d2cf  pop     r14
0x18006d2d1  pop     rdi
0x18006d2d2  pop     rsi
0x18006d2d3  pop     rbx
0x18006d2d4  pop     rbp
0x18006d2d5  retn
```
