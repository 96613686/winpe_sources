# WriteServiceSettings(SC_HANDLE__ *,ServiceSetupInfo *,ulong,_SERVICE_FAILURE_ACTIONSW *)

- ea: `0x1800400a8`
- end: `0x180040247`
- name: `?WriteServiceSettings@@YAJPEAUSC_HANDLE__@@PEAUServiceSetupInfo@@KPEAU_SERVICE_FAILURE_ACTIONSW@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct ServiceSetupInfo *, unsigned int, struct _SERVICE_FAILURE_ACTIONSW *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x18004086c`

## callees

- `0x18003abe4`
- `0x1800400a8`
- `0x180044be0`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!ChangeServiceConfigW` at `0x180040153`
- `ADVAPI32!ChangeServiceConfigW` at `0x180040153`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800401f8`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800401f8`

## string_xrefs

- `0x1800400d2`: `Writing back various service settings for: `
- `0x18004020d`: `Writing back various service settings for: `
- `0x1800400dc`: `WriteServiceSettings`
- `0x18004021c`: `WriteServiceSettings`
- `0x180040109`: `Changing the service startup type`
- `0x18004016a`: `Changing the service startup type`
- `0x180040113`: `ChangeServiceConfig`
- `0x180040174`: `ChangeServiceConfig`
- `0x18004019f`: `SeShutdownPrivilege`
- `0x1800401a6`: `Adjusting the token privilege to enable: `
- `0x1800401ca`: `Adjusting the token privilege to enable: `
- `0x1800401b2`: `AdjustTokenPrivilege`
- `0x1800401d9`: `AdjustTokenPrivilege`

## pseudocode

```c
__int64 __fastcall WriteServiceSettings(
        SC_HANDLE hService,
        const unsigned __int16 **a2,
        DWORD a3,
        struct _SERVICE_FAILURE_ACTIONSW *a4)
{
  unsigned int LastWin32Error; // ebx
  __int64 v9; // rcx

  LastWin32Error = 0;
  CSetupLogging::Log(1, "WriteServiceSettings", 0, "Writing back various service settings for: ", a2[3]);
  if ( a4 )
  {
    if ( a3 != -1 )
    {
      CSetupLogging::Log(1, "ChangeServiceConfig", 0, "Changing the service startup type", 0);
      if ( !ChangeServiceConfigW(hService, 0xFFFFFFFF, a3, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        LastWin32Error = GetLastWin32Error();
      CSetupLogging::Log(LastWin32Error, "ChangeServiceConfig", 0, "Changing the service startup type", 0);
    }
    v9 = 0;
    if ( !a4->cActions )
      goto LABEL_12;
    while ( a4->lpsaActions[v9].Type != SC_ACTION_REBOOT )
    {
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= a4->cActions )
        goto LABEL_12;
    }
    CSetupLogging::Log(
      1,
      "AdjustTokenPrivilege",
      0,
      "Adjusting the token privilege to enable: ",
      L"SeShutdownPrivilege");
    LastWin32Error = AdjustTokenPrivilege(L"SeShutdownPrivilege");
    CSetupLogging::Log(
      LastWin32Error,
      "AdjustTokenPrivilege",
      0,
      "Adjusting the token privilege to enable: ",
      L"SeShutdownPrivilege");
    if ( !LastWin32Error )
    {
LABEL_12:
      if ( !ChangeServiceConfig2W(hService, 2u, a4) )
        LastWin32Error = GetLastWin32Error();
    }
  }
  else
  {
    LastWin32Error = -2147418113;
  }
  CSetupLogging::Log(LastWin32Error, "WriteServiceSettings", 0, "Writing back various service settings for: ", a2[3]);
  return LastWin32Error;
}

```

## disassembly

```asm
0x1800400a8  mov     r11, rsp
0x1800400ab  mov     [r11+8], rbx
0x1800400af  mov     [r11+10h], rbp
0x1800400b3  mov     [r11+18h], rsi
0x1800400b7  mov     [r11+20h], rdi
0x1800400bb  push    r14
0x1800400bd  sub     rsp, 60h
0x1800400c1  mov     rax, [rdx+18h]
0x1800400c5  mov     rdi, r9
0x1800400c8  mov     esi, r8d
0x1800400cb  mov     [r11-48h], rax
0x1800400cf  mov     rbp, rdx
0x1800400d2  lea     r9, aWritingBackVar; "Writing back various service settings f"...
0x1800400d9  mov     r14, rcx
0x1800400dc  lea     rdx, aWriteservicese; "WriteServiceSettings"
0x1800400e3  xor     ebx, ebx
0x1800400e5  xor     r8d, r8d; unsigned int
0x1800400e8  lea     ecx, [rbx+1]; int
0x1800400eb  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800400f0  test    rdi, rdi
0x1800400f3  jnz     short loc_1800400FF
0x1800400f5  mov     ebx, 8000FFFFh
0x1800400fa  jmp     loc_180040209
0x1800400ff  cmp     esi, 0FFFFFFFFh
0x180040102  jz      short loc_180040182
0x180040104  and     [rsp+68h+var_48], rbx
0x180040109  lea     r9, aChangingTheSer; "Changing the service startup type"
0x180040110  xor     r8d, r8d; unsigned int
0x180040113  lea     rdx, aChangeservicec_1; "ChangeServiceConfig"
0x18004011a  lea     ecx, [r8+1]; int
0x18004011e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040123  and     [rsp+68h+var_18], rbx
0x180040128  or      r9d, 0FFFFFFFFh; dwErrorControl
0x18004012c  and     [rsp+68h+var_20], rbx
0x180040131  mov     r8d, esi; dwStartType
0x180040134  and     [rsp+68h+var_28], rbx
0x180040139  or      edx, r9d; dwServiceType
0x18004013c  and     [rsp+68h+var_30], rbx
0x180040141  mov     rcx, r14; hService
0x180040144  and     [rsp+68h+var_38], rbx
0x180040149  and     [rsp+68h+var_40], rbx
0x18004014e  and     [rsp+68h+var_48], rbx
0x180040153  call    cs:__imp_ChangeServiceConfigW
0x180040159  test    eax, eax
0x18004015b  jnz     short loc_180040164
0x18004015d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180040162  mov     ebx, eax
0x180040164  and     [rsp+68h+var_48], 0
0x18004016a  lea     r9, aChangingTheSer; "Changing the service startup type"
0x180040171  xor     r8d, r8d; unsigned int
0x180040174  lea     rdx, aChangeservicec_1; "ChangeServiceConfig"
0x18004017b  mov     ecx, ebx; int
0x18004017d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040182  xor     ecx, ecx
0x180040184  cmp     [rdi+18h], ecx
0x180040187  jbe     short loc_1800401ED
0x180040189  mov     rdx, [rdi+20h]
0x18004018d  cmp     dword ptr [rdx+rcx*8], 2
0x180040191  jz      short loc_18004019C
0x180040193  inc     ecx
0x180040195  cmp     ecx, [rdi+18h]
0x180040198  jb      short loc_18004018D
0x18004019a  jmp     short loc_1800401ED
0x18004019c  xor     r8d, r8d; unsigned int
0x18004019f  lea     rsi, aSeshutdownpriv; "SeShutdownPrivilege"
0x1800401a6  lea     r9, aAdjustingTheTo; "Adjusting the token privilege to enable"...
0x1800401ad  mov     [rsp+68h+var_48], rsi; unsigned __int16 *
0x1800401b2  lea     rdx, aAdjusttokenpri_0; "AdjustTokenPrivilege"
0x1800401b9  lea     ecx, [r8+1]; int
0x1800401bd  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800401c2  mov     rcx, rsi; lpName
0x1800401c5  call    ?AdjustTokenPrivilege@@YAJPEBG@Z; AdjustTokenPrivilege(ushort const *)
0x1800401ca  lea     r9, aAdjustingTheTo; "Adjusting the token privilege to enable"...
0x1800401d1  mov     [rsp+68h+var_48], rsi; unsigned __int16 *
0x1800401d6  xor     r8d, r8d; unsigned int
0x1800401d9  lea     rdx, aAdjusttokenpri_0; "AdjustTokenPrivilege"
0x1800401e0  mov     ecx, eax; int
0x1800401e2  mov     ebx, eax
0x1800401e4  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800401e9  test    ebx, ebx
0x1800401eb  jnz     short loc_180040209
0x1800401ed  mov     r8, rdi; lpInfo
0x1800401f0  mov     edx, 2; dwInfoLevel
0x1800401f5  mov     rcx, r14; hService
0x1800401f8  call    cs:__imp_ChangeServiceConfig2W
0x1800401fe  test    eax, eax
0x180040200  jnz     short loc_180040209
0x180040202  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180040207  mov     ebx, eax
0x180040209  mov     rax, [rbp+18h]
0x18004020d  lea     r9, aWritingBackVar; "Writing back various service settings f"...
0x180040214  xor     r8d, r8d; unsigned int
0x180040217  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18004021c  lea     rdx, aWriteservicese; "WriteServiceSettings"
0x180040223  mov     ecx, ebx; int
0x180040225  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18004022a  lea     r11, [rsp+68h+var_8]
0x18004022f  mov     eax, ebx
0x180040231  mov     rbx, [r11+10h]
0x180040235  mov     rbp, [r11+18h]
0x180040239  mov     rsi, [r11+20h]
0x18004023d  mov     rdi, [r11+28h]
0x180040241  mov     rsp, r11
0x180040244  pop     r14
0x180040246  retn
```
