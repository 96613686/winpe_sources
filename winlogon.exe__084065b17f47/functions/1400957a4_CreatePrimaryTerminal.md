# CreatePrimaryTerminal

- ea: `0x1400957a4`
- end: `0x140095c9e`
- name: `CreatePrimaryTerminal`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14007b3f4`

## callees

- `0x140005660`
- `0x1400057f4`
- `0x14000f5d0`
- `0x14000f8ec`
- `0x14000fda0`
- `0x140038b60`
- `0x140041c34`
- `0x14004e074`
- `0x1400957a4`
- `0x140095e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095aab`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1400958e2`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1400958e2`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!RegisterLogonProcess` at `0x1400957fa`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!RegisterLogonProcess` at `0x1400957fa`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x140095bd3`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x140095bd3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateWindowStationW` at `0x140095861`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateWindowStationW` at `0x140095861`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetProcessWindowStation` at `0x14009596f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetProcessWindowStation` at `0x14009596f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseWindowStation` at `0x140095c85`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseWindowStation` at `0x1400a08b8`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseWindowStation` at `0x140095c85`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseWindowStation` at `0x1400a08b8`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x140095a32`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x140095a9d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x140095a32`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x140095a9d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140095c63`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140095c74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400a087e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400a089b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140095c63`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140095c74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400a087e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400a089b`

## pseudocode

```c
__int64 __fastcall CreatePrimaryTerminal(
        HWINSTA *a1,
        void **a2,
        HDESK *a3,
        HANDLE *a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned int a8)
{
  DWORD v12; // ebx
  __int64 v13; // r9
  CUser *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  HWINSTA WindowStationW; // rax
  DWORD LastError; // eax
  unsigned int v19; // ebx
  unsigned int v20; // eax
  enum _MANDATORY_LEVEL v21; // edx
  CUser *v22; // rcx
  __int64 v23; // rdx
  HDESK DesktopW; // rax
  HDESK v25; // rax
  __int64 v26; // r9
  enum _MANDATORY_LEVEL v27; // edx
  __int64 v28; // r9
  __int64 v29; // r9
  __int64 v31; // [rsp+88h] [rbp+10h] BYREF
  HDESK *v32; // [rsp+90h] [rbp+18h]
  HANDLE *v33; // [rsp+98h] [rbp+20h]

  v33 = a4;
  v32 = a3;
  v31 = 0;
  v12 = 0;
  *a1 = 0;
  *a2 = 0;
  *a4 = 0;
  *a3 = 0;
  if ( !(unsigned int)RegisterLogonProcess(LODWORD(NtCurrentTeb()->ClientId.UniqueProcess), a5) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v15 = 13;
LABEL_6:
    WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v13);
LABEL_7:
    v16 = 87;
    goto LABEL_76;
  }
  if ( a6 )
  {
    v12 = 2;
  }
  else if ( a7 )
  {
    v19 = a8;
    if ( a8 == -1 || (unsigned int)RtlGetCurrentServiceSessionId() == v19 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v15 = 14;
      goto LABEL_6;
    }
    if ( v19 > 0xFFFF )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v15 = 15;
      goto LABEL_6;
    }
    v12 = ((unsigned __int16)v19 << 16) | 0xC;
  }
  WindowStationW = CreateWindowStationW(L"WinSta0", v12, 0x2000000u, 0);
  *a1 = WindowStationW;
  if ( !WindowStationW )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, LastError);
    }
    if ( !v16 )
      v16 = 8;
    goto LABEL_76;
  }
  SetProcessWindowStation(WindowStationW);
  v20 = SetDefaultWinstaSecurity(*a1, a2);
  v16 = v20;
  if ( v20 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_76;
    }
    v23 = 17;
    goto LABEL_35;
  }
  v20 = SetUserIntegrityLabel(*a1, v21);
  v16 = v20;
  if ( v20 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_76;
    }
    v23 = 18;
    goto LABEL_35;
  }
  DesktopW = CreateDesktopW(L"Winlogon", 0, 0, 0, 0x2000000u, 0);
  *a3 = DesktopW;
  if ( !DesktopW )
  {
    v20 = GetLastError();
    v16 = v20;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_76;
    }
    v23 = 19;
    goto LABEL_35;
  }
  v25 = CreateDesktopW(L"Default", 0, 0, 0, 0x2000000u, 0);
  *a4 = v25;
  if ( !v25 )
  {
    v20 = GetLastError();
    v16 = v20;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_76;
    }
    v23 = 20;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v26);
  }
  v16 = SetWinlogonDesktopSecurity(*a3);
  if ( !v16 )
  {
    v16 = SetUserDesktopSecurity(*a4);
    if ( !v16 )
    {
      v20 = SetUserIntegrityLabel(*a4, v27);
      v16 = v20;
      if ( v20 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_76;
        }
        v23 = 22;
LABEL_35:
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v20);
        goto LABEL_76;
      }
      v16 = ResilientSwitchDesktopWithFade(*a3);
      if ( v16 )
        goto LABEL_76;
      v16 = ResilientSetThreadDesktop(*a3);
      if ( v16 )
        goto LABEL_76;
      if ( !(unsigned int)SetWindowStationUser(*a1, &v31, 0, 0) )
      {
LABEL_75:
        v16 = 14;
        goto LABEL_76;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v28);
      }
      if ( byte_1400D1A5C )
      {
        byte_1400D1A5C = 0;
        if ( !LaunchUmfdHostWithVirtualAccountAsync() )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v29);
          }
          goto LABEL_75;
        }
      }
    }
  }
LABEL_76:
  if ( v16 )
  {
    if ( *a4 )
    {
      CloseDesktop((HDESK)*a4);
      *a4 = 0;
    }
    if ( *a3 )
    {
      CloseDesktop(*a3);
      *a3 = 0;
    }
    if ( *a1 )
    {
      CloseWindowStation(*a1);
      *a1 = 0;
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1400957a4  mov     rax, rsp
0x1400957a7  mov     [rax+20h], r9
0x1400957ab  mov     [rax+18h], r8
0x1400957af  mov     [rax+8], rcx
0x1400957b3  push    rbx
0x1400957b4  push    rsi
0x1400957b5  push    rdi
0x1400957b6  push    r12
0x1400957b8  push    r14
0x1400957ba  push    r15
0x1400957bc  sub     rsp, 48h
0x1400957c0  mov     r15, r9
0x1400957c3  mov     rsi, r8
0x1400957c6  mov     rdi, rdx
0x1400957c9  mov     r14, rcx
0x1400957cc  xor     r12d, r12d
0x1400957cf  mov     [rax-48h], r12d
0x1400957d3  mov     [rax+10h], r12
0x1400957d7  mov     ebx, r12d
0x1400957da  mov     [rcx], r12
0x1400957dd  mov     [rdx], r12
0x1400957e0  mov     [r9], r12
0x1400957e3  mov     [r8], r12
0x1400957e6  mov     rcx, gs:30h
0x1400957ef  mov     rdx, [rsp+78h+arg_20]
0x1400957f7  mov     ecx, [rcx+40h]
0x1400957fa  call    cs:__imp_RegisterLogonProcess
0x140095800  test    eax, eax
0x140095802  jnz     short loc_140095840
0x140095804  lea     rdi, WPP_GLOBAL_Control
0x14009580b  mov     rcx, cs:WPP_GLOBAL_Control
0x140095812  cmp     rcx, rdi
0x140095815  jz      short loc_140095836
0x140095817  test    byte ptr [rcx+1Ch], 4
0x14009581b  jz      short loc_140095836
0x14009581d  cmp     byte ptr [rcx+19h], 2
0x140095821  jb      short loc_140095836
0x140095823  lea     edx, [rax+0Dh]
0x140095826  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x14009582d  mov     rcx, [rcx+10h]
0x140095831  call    WPP_SF_
0x140095836  mov     ebx, 57h ; 'W'
0x14009583b  jmp     loc_140095C53
0x140095840  cmp     [rsp+78h+arg_28], r12d
0x140095848  jz      short loc_1400958C8
0x14009584a  mov     ebx, 2
0x14009584f  xor     r9d, r9d; lpsa
0x140095852  mov     r8d, 2000000h; dwDesiredAccess
0x140095858  mov     edx, ebx; dwFlags
0x14009585a  lea     rcx, aWinsta0; "WinSta0"
0x140095861  call    cs:__imp_CreateWindowStationW
0x140095867  mov     [r14], rax
0x14009586a  test    rax, rax
0x14009586d  jnz     loc_14009596C
0x140095873  call    cs:__imp_GetLastError
0x140095879  mov     ebx, eax
0x14009587b  mov     [rsp+78h+var_48], eax
0x14009587f  lea     rdi, WPP_GLOBAL_Control
0x140095886  mov     rcx, cs:WPP_GLOBAL_Control
0x14009588d  cmp     rcx, rdi
0x140095890  jz      short loc_1400958B6
0x140095892  test    byte ptr [rcx+1Ch], 4
0x140095896  jz      short loc_1400958B6
0x140095898  cmp     byte ptr [rcx+19h], 2
0x14009589c  jb      short loc_1400958B6
0x14009589e  mov     edx, 10h
0x1400958a3  mov     r9d, eax
0x1400958a6  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x1400958ad  mov     rcx, [rcx+10h]
0x1400958b1  call    WPP_SF_d
0x1400958b6  test    ebx, ebx
0x1400958b8  jnz     loc_140095C57
0x1400958be  mov     ebx, 8
0x1400958c3  jmp     loc_140095C53
0x1400958c8  cmp     [rsp+78h+arg_30], r12d
0x1400958d0  jz      loc_14009584F
0x1400958d6  mov     ebx, [rsp+78h+arg_38]
0x1400958dd  cmp     ebx, 0FFFFFFFFh
0x1400958e0  jz      short loc_140095937
0x1400958e2  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1400958e8  cmp     eax, ebx
0x1400958ea  jz      short loc_140095937
0x1400958ec  cmp     ebx, 0FFFFh
0x1400958f2  jbe     short loc_140095929
0x1400958f4  lea     rdi, WPP_GLOBAL_Control
0x1400958fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140095902  cmp     rcx, rdi
0x140095905  jz      loc_140095836
0x14009590b  test    byte ptr [rcx+1Ch], 4
0x14009590f  jz      loc_140095836
0x140095915  cmp     byte ptr [rcx+19h], 2
0x140095919  jb      loc_140095836
0x14009591f  mov     edx, 0Fh
0x140095924  jmp     loc_140095826
0x140095929  movzx   ebx, bx
0x14009592c  shl     ebx, 10h
0x14009592f  or      ebx, 0Ch
0x140095932  jmp     loc_14009584F
0x140095937  lea     rdi, WPP_GLOBAL_Control
0x14009593e  mov     rcx, cs:WPP_GLOBAL_Control
0x140095945  cmp     rcx, rdi
0x140095948  jz      loc_140095836
0x14009594e  test    byte ptr [rcx+1Ch], 4
0x140095952  jz      loc_140095836
0x140095958  cmp     byte ptr [rcx+19h], 2
0x14009595c  jb      loc_140095836
0x140095962  mov     edx, 0Eh
0x140095967  jmp     loc_140095826
0x14009596c  mov     rcx, rax; hWinSta
0x14009596f  call    cs:__imp_SetProcessWindowStation
0x140095975  mov     rdx, rdi; void **
0x140095978  mov     rcx, [r14]; hObj
0x14009597b  call    ?SetDefaultWinstaSecurity@@YAKPEAUHWINSTA__@@PEAPEAX@Z; SetDefaultWinstaSecurity(HWINSTA__ *,void * *)
0x140095980  mov     ebx, eax
0x140095982  mov     [rsp+78h+var_48], eax
0x140095986  test    eax, eax
0x140095988  jz      short loc_1400959D2
0x14009598a  lea     rdi, WPP_GLOBAL_Control
0x140095991  mov     rcx, cs:WPP_GLOBAL_Control
0x140095998  cmp     rcx, rdi
0x14009599b  jz      loc_140095C57
0x1400959a1  test    byte ptr [rcx+1Ch], 4
0x1400959a5  jz      loc_140095C57
0x1400959ab  cmp     byte ptr [rcx+19h], 2
0x1400959af  jb      loc_140095C57
0x1400959b5  mov     edx, 11h
0x1400959ba  mov     r9d, eax
0x1400959bd  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x1400959c4  mov     rcx, [rcx+10h]
0x1400959c8  call    WPP_SF_d
0x1400959cd  jmp     loc_140095C57
0x1400959d2  mov     rcx, [r14]; hObj
0x1400959d5  call    ?SetUserIntegrityLabel@@YAKPEAXW4_MANDATORY_LEVEL@@@Z; SetUserIntegrityLabel(void *,_MANDATORY_LEVEL)
0x1400959da  mov     ebx, eax
0x1400959dc  mov     [rsp+78h+var_48], eax
0x1400959e0  test    eax, eax
0x1400959e2  jz      short loc_140095A16
0x1400959e4  lea     rdi, WPP_GLOBAL_Control
0x1400959eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400959f2  cmp     rcx, rdi
0x1400959f5  jz      loc_140095C57
0x1400959fb  test    byte ptr [rcx+1Ch], 4
0x1400959ff  jz      loc_140095C57
0x140095a05  cmp     byte ptr [rcx+19h], 2
0x140095a09  jb      loc_140095C57
0x140095a0f  mov     edx, 12h
0x140095a14  jmp     short loc_1400959BA
0x140095a16  mov     [rsp+78h+lpsa], r12; lpsa
0x140095a1b  mov     [rsp+78h+dwDesiredAccess], 2000000h; dwDesiredAccess
0x140095a23  xor     r9d, r9d; dwFlags
0x140095a26  xor     r8d, r8d; pDevmode
0x140095a29  xor     edx, edx; lpszDevice
0x140095a2b  lea     rcx, aWinlogon_1; "Winlogon"
0x140095a32  call    cs:__imp_CreateDesktopW
0x140095a38  mov     [rsi], rax
0x140095a3b  test    rax, rax
0x140095a3e  jnz     short loc_140095A81
0x140095a40  call    cs:__imp_GetLastError
0x140095a46  mov     ebx, eax
0x140095a48  mov     [rsp+78h+var_48], eax
0x140095a4c  lea     rdi, WPP_GLOBAL_Control
0x140095a53  mov     rcx, cs:WPP_GLOBAL_Control
0x140095a5a  cmp     rcx, rdi
0x140095a5d  jz      loc_140095C57
0x140095a63  test    byte ptr [rcx+1Ch], 4
0x140095a67  jz      loc_140095C57
0x140095a6d  cmp     byte ptr [rcx+19h], 2
0x140095a71  jb      loc_140095C57
0x140095a77  mov     edx, 13h
0x140095a7c  jmp     loc_1400959BA
0x140095a81  mov     [rsp+78h+lpsa], r12; lpsa
0x140095a86  mov     [rsp+78h+dwDesiredAccess], 2000000h; dwDesiredAccess
0x140095a8e  xor     r9d, r9d; dwFlags
0x140095a91  xor     r8d, r8d; pDevmode
0x140095a94  xor     edx, edx; lpszDevice
0x140095a96  lea     rcx, aDefault_0; "Default"
0x140095a9d  call    cs:__imp_CreateDesktopW
0x140095aa3  mov     [r15], rax
0x140095aa6  test    rax, rax
0x140095aa9  jnz     short loc_140095AEC
0x140095aab  call    cs:__imp_GetLastError
0x140095ab1  mov     ebx, eax
0x140095ab3  mov     [rsp+78h+var_48], eax
0x140095ab7  lea     rdi, WPP_GLOBAL_Control
0x140095abe  mov     rcx, cs:WPP_GLOBAL_Control
0x140095ac5  cmp     rcx, rdi
0x140095ac8  jz      loc_140095C57
0x140095ace  test    byte ptr [rcx+1Ch], 4
0x140095ad2  jz      loc_140095C57
0x140095ad8  cmp     byte ptr [rcx+19h], 2
0x140095adc  jb      loc_140095C57
0x140095ae2  mov     edx, 14h
0x140095ae7  jmp     loc_1400959BA
0x140095aec  lea     rdi, WPP_GLOBAL_Control
0x140095af3  mov     rcx, cs:WPP_GLOBAL_Control
0x140095afa  cmp     rcx, rdi
0x140095afd  jz      short loc_140095B20
0x140095aff  test    byte ptr [rcx+1Ch], 4
0x140095b03  jz      short loc_140095B20
0x140095b05  cmp     byte ptr [rcx+19h], 5
0x140095b09  jb      short loc_140095B20
0x140095b0b  mov     edx, 15h
0x140095b10  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140095b17  mov     rcx, [rcx+10h]
0x140095b1b  call    WPP_SF_
0x140095b20  mov     rcx, [rsi]; hObj
0x140095b23  call    ?SetWinlogonDesktopSecurity@@YAKPEAUHDESK__@@@Z; SetWinlogonDesktopSecurity(HDESK__ *)
0x140095b28  mov     ebx, eax
0x140095b2a  mov     [rsp+78h+var_48], eax
0x140095b2e  test    eax, eax
0x140095b30  jnz     loc_140095C57
0x140095b36  xor     edx, edx
0x140095b38  mov     rcx, [r15]; hObj
0x140095b3b  call    SetUserDesktopSecurity
0x140095b40  mov     ebx, eax
0x140095b42  mov     [rsp+78h+var_48], eax
0x140095b46  test    eax, eax
0x140095b48  jnz     loc_140095C57
0x140095b4e  mov     rcx, [r15]; hObj
0x140095b51  call    ?SetUserIntegrityLabel@@YAKPEAXW4_MANDATORY_LEVEL@@@Z; SetUserIntegrityLabel(void *,_MANDATORY_LEVEL)
0x140095b56  mov     ebx, eax
0x140095b58  mov     [rsp+78h+var_48], eax
0x140095b5c  test    eax, eax
0x140095b5e  jz      short loc_140095B8E
0x140095b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140095b67  cmp     rcx, rdi
0x140095b6a  jz      loc_140095C57
0x140095b70  test    byte ptr [rcx+1Ch], 4
0x140095b74  jz      loc_140095C57
0x140095b7a  cmp     byte ptr [rcx+19h], 2
0x140095b7e  jb      loc_140095C57
0x140095b84  mov     edx, 16h
0x140095b89  jmp     loc_1400959BA
0x140095b8e  xor     r9d, r9d
0x140095b91  xor     r8d, r8d
0x140095b94  xor     edx, edx
0x140095b96  mov     rcx, [rsi]; hDesktop
0x140095b99  call    ResilientSwitchDesktopWithFade
0x140095b9e  mov     ebx, eax
0x140095ba0  mov     [rsp+78h+var_48], eax
0x140095ba4  test    eax, eax
0x140095ba6  jnz     loc_140095C57
0x140095bac  mov     rcx, [rsi]; hDesktop
0x140095baf  call    ResilientSetThreadDesktop
0x140095bb4  mov     ebx, eax
0x140095bb6  mov     [rsp+78h+var_48], eax
0x140095bba  test    eax, eax
0x140095bbc  jnz     loc_140095C57
0x140095bc2  xor     r9d, r9d
0x140095bc5  xor     r8d, r8d
0x140095bc8  lea     rdx, [rsp+78h+arg_8]
0x140095bd0  mov     rcx, [r14]
0x140095bd3  call    cs:__imp_SetWindowStationUser
0x140095bd9  test    eax, eax
0x140095bdb  jz      short loc_140095C4E
0x140095bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140095be4  cmp     rcx, rdi
0x140095be7  jz      short loc_140095C08
0x140095be9  test    byte ptr [rcx+1Ch], 4
0x140095bed  jz      short loc_140095C08
0x140095bef  cmp     byte ptr [rcx+19h], 4
0x140095bf3  jb      short loc_140095C08
0x140095bf5  lea     edx, [rbx+17h]
0x140095bf8  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140095bff  mov     rcx, [rcx+10h]
0x140095c03  call    WPP_SF_
0x140095c08  cmp     cs:byte_1400D1A5C, r12b
0x140095c0f  jz      short loc_140095C57
0x140095c11  mov     cs:byte_1400D1A5C, r12b
0x140095c18  call    ?LaunchUmfdHostWithVirtualAccountAsync@@YA_NXZ; LaunchUmfdHostWithVirtualAccountAsync(void)
0x140095c1d  test    al, al
0x140095c1f  jnz     short loc_140095C57
0x140095c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140095c28  cmp     rcx, rdi
0x140095c2b  jz      short loc_140095C4E
0x140095c2d  test    byte ptr [rcx+1Ch], 4
0x140095c31  jz      short loc_140095C4E
0x140095c33  cmp     byte ptr [rcx+19h], 2
0x140095c37  jb      short loc_140095C4E
0x140095c39  mov     edx, 18h
0x140095c3e  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140095c45  mov     rcx, [rcx+10h]
0x140095c49  call    WPP_SF_
0x140095c4e  mov     ebx, 0Eh
0x140095c53  mov     [rsp+78h+var_48], ebx
0x140095c57  test    ebx, ebx
0x140095c59  jz      short loc_140095C8E
0x140095c5b  mov     rcx, [r15]; hDesktop
0x140095c5e  test    rcx, rcx
0x140095c61  jz      short loc_140095C6C
0x140095c63  call    cs:__imp_CloseDesktop
0x140095c69  mov     [r15], r12
0x140095c6c  mov     rcx, [rsi]; hDesktop
0x140095c6f  test    rcx, rcx
0x140095c72  jz      short loc_140095C7D
0x140095c74  call    cs:__imp_CloseDesktop
0x140095c7a  mov     [rsi], r12
0x140095c7d  mov     rcx, [r14]; hWinSta
0x140095c80  test    rcx, rcx
0x140095c83  jz      short loc_140095C8E
  ... truncated ...
```
