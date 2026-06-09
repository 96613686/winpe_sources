# CMadcapHandler::Initialize(ushort,CInterfaceMonitor *)

- ea: `0x180016948`
- end: `0x180016b00`
- name: `?Initialize@CMadcapHandler@@QEAAKGPEAVCInterfaceMonitor@@@Z`
- size: `440`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int16, struct CInterfaceMonitor *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800174b8`

## callees

- `0x18001687c`
- `0x180016948`
- `0x180016b08`
- `0x1800173ac`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001699a`
- `ADVAPI32!RegOpenKeyExW` at `0x18001699a`
- `ADVAPI32!RegCloseKey` at `0x180016ae4`
- `ADVAPI32!RegCloseKey` at `0x180016ae4`
- `dhcpcsvc!McastApiStartup` at `0x180016a38`
- `dhcpcsvc!McastApiStartup` at `0x180016a38`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180016a24`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180016a24`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016a16`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016aa4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016a16`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016aa4`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180016ace`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180016ace`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x1800169ce`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x1800169ce`

## string_xrefs

- `0x180016972`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall CMadcapHandler::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        struct CInterfaceMonitor *a3)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  LPCRITICAL_SECTION v7; // rdi
  unsigned int ValueSz; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  _WORD *p_Type; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD Version; // [rsp+68h] [rbp+10h] BYREF

  lpCriticalSection[2].OwningThread = a3;
  Version = 1;
  LOWORD(lpCriticalSection[2].DebugInfo) = 2;
  lpCriticalSection[1].LockCount = 4;
  hKey = 0;
  v4 = (unsigned int)RegOpenKeyExW(
                       HKEY_LOCAL_MACHINE,
                       L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                       0,
                       0x20119u,
                       &hKey);
  if ( (unsigned int)ElValidateWin32_8(v4, v5, v6, 85) )
    goto LABEL_12;
  v7 = lpCriticalSection + 1;
  ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"MADCAPScope", (unsigned __int16 **)&lpCriticalSection[1]);
  LODWORD(v4) = ValueSz;
  if ( (ValueSz & 0xFFFFFFFD) == 0 )
  {
    p_Type = &v7->DebugInfo->Type;
    if ( v7->DebugInfo )
    {
      if ( *p_Type )
      {
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[MADCAP] Scope Filter: '%s'", v7->DebugInfo);
      }
      else
      {
        WdsPrivateHpFree(p_Type);
        v7->DebugInfo = 0;
      }
    }
    v4 = McastApiStartup(&Version);
    if ( !(unsigned int)ElValidateWin32_8(v4, v12, v13, 108) )
    {
      v4 = CMadcapHandler::OnNetworkChange(lpCriticalSection);
      if ( !(unsigned int)ElValidateWin32_8(v4, v14, v15, 115) )
      {
        v4 = (unsigned int)CTimer<CMadcapHandler>::Initialize(&lpCriticalSection[2].LockSemaphore);
        if ( !(unsigned int)ElValidateWin32_8(v4, v16, v17, 122) )
          CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[MADCAP] Initialized.");
      }
    }
LABEL_12:
    if ( !(_DWORD)v4 )
      goto LABEL_14;
    goto LABEL_13;
  }
  ElValidateWin32_8(ValueSz, v9, v10, 94);
LABEL_13:
  CEventLog::Log((CEventLog *)qword_180039300, 0xC1010600, 1);
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016948  mov     rax, rsp
0x18001694b  mov     [rax+18h], rbx
0x18001694f  mov     [rax+10h], dx
0x180016953  push    rbp
0x180016954  push    rsi
0x180016955  push    rdi
0x180016956  sub     rsp, 40h
0x18001695a  mov     [rcx+60h], r8
0x18001695e  mov     rsi, rcx
0x180016961  mov     dword ptr [rax+10h], 1
0x180016968  lea     rax, [rax+8]
0x18001696c  mov     word ptr [rcx+50h], 2
0x180016972  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180016979  mov     dword ptr [rcx+30h], 4
0x180016980  xor     ebp, ebp
0x180016982  mov     [rax], rbp
0x180016985  mov     r9d, 20119h; samDesired
0x18001698b  xor     r8d, r8d; ulOptions
0x18001698e  mov     [rsp+58h+phkResult], rax; phkResult
0x180016993  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001699a  call    cs:__imp_RegOpenKeyExW
0x1800169a1  nop     dword ptr [rax+rax+00h]
0x1800169a6  mov     ecx, eax
0x1800169a8  lea     r9d, [rbp+55h]
0x1800169ac  mov     ebx, eax
0x1800169ae  call    ElValidateWin32_8
0x1800169b3  test    eax, eax
0x1800169b5  jnz     loc_180016AB0
0x1800169bb  lea     rdi, [rsi+28h]
0x1800169bf  mov     r8, rdi
0x1800169c2  lea     rdx, aMadcapscope; "MADCAPScope"
0x1800169c9  lea     rcx, [rsp+58h+hKey]
0x1800169ce  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x1800169d5  nop     dword ptr [rax+rax+00h]
0x1800169da  mov     ebx, eax
0x1800169dc  test    eax, 0FFFFFFFDh
0x1800169e1  jz      short loc_1800169F3
0x1800169e3  lea     r9d, [rbp+5Eh]
0x1800169e7  mov     ecx, eax
0x1800169e9  call    ElValidateWin32_8
0x1800169ee  jmp     loc_180016AB4
0x1800169f3  mov     rcx, [rdi]
0x1800169f6  test    rcx, rcx
0x1800169f9  jz      short loc_180016A33
0x1800169fb  cmp     [rcx], bp
0x1800169fe  jz      short loc_180016A24
0x180016a00  mov     r9, rcx
0x180016a03  lea     r8, aMadcapScopeFil; "[MADCAP] Scope Filter: '%s'"
0x180016a0a  lea     rcx, qword_180039310
0x180016a11  mov     edx, 20000h
0x180016a16  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180016a1d  nop     dword ptr [rax+rax+00h]
0x180016a22  jmp     short loc_180016A33
0x180016a24  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180016a2b  nop     dword ptr [rax+rax+00h]
0x180016a30  mov     [rdi], rbp
0x180016a33  lea     rcx, [rsp+58h+Version]; Version
0x180016a38  call    cs:__imp_McastApiStartup
0x180016a3f  nop     dword ptr [rax+rax+00h]
0x180016a44  mov     ecx, eax
0x180016a46  mov     r9d, 6Ch ; 'l'
0x180016a4c  mov     ebx, eax
0x180016a4e  call    ElValidateWin32_8
0x180016a53  test    eax, eax
0x180016a55  jnz     short loc_180016AB0
0x180016a57  mov     rcx, rsi; lpCriticalSection
0x180016a5a  call    ?OnNetworkChange@CMadcapHandler@@QEAAKXZ; CMadcapHandler::OnNetworkChange(void)
0x180016a5f  mov     r9d, 73h ; 's'
0x180016a65  mov     ecx, eax
0x180016a67  mov     ebx, eax
0x180016a69  call    ElValidateWin32_8
0x180016a6e  test    eax, eax
0x180016a70  jnz     short loc_180016AB0
0x180016a72  lea     rcx, [rsi+68h]; Parameter
0x180016a76  mov     rdx, rsi
0x180016a79  call    ?Initialize@?$CTimer@VCMadcapHandler@@@@QEAAKPEAVCMadcapHandler@@PEAXKK1K@Z; CTimer<CMadcapHandler>::Initialize(CMadcapHandler *,void *,ulong,ulong,void *,ulong)
0x180016a7e  mov     r9d, 7Ah ; 'z'
0x180016a84  mov     ecx, eax
0x180016a86  mov     ebx, eax
0x180016a88  call    ElValidateWin32_8
0x180016a8d  test    eax, eax
0x180016a8f  jnz     short loc_180016AB0
0x180016a91  lea     r8, aMadcapInitiali; "[MADCAP] Initialized."
0x180016a98  mov     edx, 20000h
0x180016a9d  lea     rcx, qword_180039310
0x180016aa4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180016aab  nop     dword ptr [rax+rax+00h]
0x180016ab0  test    ebx, ebx
0x180016ab2  jz      short loc_180016ADA
0x180016ab4  mov     r9d, 5
0x180016aba  mov     dword ptr [rsp+58h+phkResult], ebx
0x180016abe  mov     edx, 0C1010600h
0x180016ac3  lea     rcx, qword_180039300
0x180016aca  lea     r8d, [r9-4]
0x180016ace  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180016ad5  nop     dword ptr [rax+rax+00h]
0x180016ada  mov     rcx, [rsp+58h+hKey]; hKey
0x180016adf  test    rcx, rcx
0x180016ae2  jz      short loc_180016AF0
0x180016ae4  call    cs:__imp_RegCloseKey
0x180016aeb  nop     dword ptr [rax+rax+00h]
0x180016af0  mov     eax, ebx
0x180016af2  mov     rbx, [rsp+58h+arg_10]
0x180016af7  add     rsp, 40h
0x180016afb  pop     rdi
0x180016afc  pop     rsi
0x180016afd  pop     rbp
0x180016afe  retn
```
