# RebootIfRequested(void)

- ea: `0x140008ff8`
- end: `0x14000927e`
- name: `?RebootIfRequested@@YAKXZ`
- size: `646`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x140008ff8`
- `0x14000d25c`
- `0x14000e280`
- `0x14001327c`
- `0x1400133f0`
- `0x140013490`

## import_xrefs

- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400090b2`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x14000914f`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x140009192`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400090b2`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x14000914f`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x140009192`
- `KERNEL32!GetCommandLineW` at `0x140009117`
- `KERNEL32!GetCommandLineW` at `0x140009221`
- `KERNEL32!GetCommandLineW` at `0x140009117`
- `KERNEL32!GetCommandLineW` at `0x140009221`
- `KERNEL32!LocalFree` at `0x140009219`
- `KERNEL32!LocalFree` at `0x140009219`
- `KERNEL32!GetLastError` at `0x1400090bc`
- `KERNEL32!GetLastError` at `0x140009159`
- `KERNEL32!GetLastError` at `0x1400091a0`
- `KERNEL32!GetLastError` at `0x1400090bc`
- `KERNEL32!GetLastError` at `0x140009159`
- `KERNEL32!GetLastError` at `0x1400091a0`
- `SHELL32!__imp_RestartDialogEx` at `0x1400090e5`
- `SHELL32!__imp_RestartDialogEx` at `0x1400090e5`

## string_xrefs

- `0x140009250`: `Reboot is not scheduled. IsRunWizardStarted: %u, IsRebootRequired: %u, RestartMode: %u`
- `0x14000904c`: `SeShutdownPrivilege`
- `0x140009063`: `Failed to set privilege SE_SHUTDOWN_NAME`
- `0x1400090f2`: `Succeeded. Reboot was scheduled for update %ls`

## pseudocode

```c
__int64 RebootIfRequested(void)
{
  unsigned int v0; // esi
  int v1; // edi
  signed int v2; // ebx
  int v3; // edi
  int v4; // edi
  signed int v5; // eax
  __int64 v6; // rdx
  LPWSTR CommandLineW; // rax
  signed int v8; // eax
  signed int LastError; // eax
  HLOCAL v10; // rdi
  LPWSTR v11; // rax
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  if ( dword_140020250 )
  {
    v0 = 3017;
    if ( dword_14002024C >= 0 )
      v0 = 3010;
  }
  v1 = dword_140020194;
  if ( dword_14002021C || !dword_140020250 || dword_140020194 == 1 )
  {
    WusaLogDebugEventA(
      L"RebootIfRequested",
      1678,
      "Reboot is not scheduled. IsRunWizardStarted: %u, IsRebootRequired: %u, RestartMode: %u",
      dword_14002021C,
      dword_140020250,
      dword_140020194);
    return v0;
  }
  v2 = EnablePrivilege(L"SeShutdownPrivilege");
  if ( v2 < 0 )
  {
    WusaLogDebugEventA(L"RebootIfRequested", 1683, "Failed to set privilege SE_SHUTDOWN_NAME");
LABEL_32:
    hMem = 0;
    WusaGetErrorMessage(v2, (unsigned __int16 **)&hMem);
    v10 = hMem;
    WusaLogDebugEventA(L"RebootIfRequested", 1767, "Exit with error code 0X%x (%ls)", v2, (const wchar_t *)hMem);
    if ( v10 )
      LocalFree(v10);
    return v0;
  }
  if ( !v1 && !dword_140020188 )
    goto LABEL_18;
  v3 = v1 - 2;
  if ( !v3 )
  {
    if ( !InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0x80020011) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v6 = 1703;
      goto LABEL_29;
    }
    goto LABEL_19;
  }
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
    {
      if ( !InitiateSystemShutdownExW(0, 0, 0, 0, 1, 0x80020011) )
      {
        v5 = GetLastError();
        v2 = v5;
        if ( v5 > 0 )
          v2 = (unsigned __int16)v5 | 0x80070000;
        v6 = 1740;
LABEL_29:
        if ( v2 >= 0 )
          v2 = -2147467259;
        WusaLogDebugEventA(L"RebootIfRequested", v6, "Failed to initiate system shutdown");
        goto LABEL_32;
      }
      goto LABEL_19;
    }
LABEL_18:
    RestartDialogEx(0, 0, 2u, 0x80020011);
    goto LABEL_19;
  }
  if ( !InitiateSystemShutdownExW(0, 0, dwTimeout, 0, 1, 0x80020011) )
  {
    v8 = GetLastError();
    v2 = v8;
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    v6 = 1717;
    goto LABEL_29;
  }
LABEL_19:
  WusaLogDebugEventA(
    L"RebootIfRequested",
    1745,
    "Succeeded. Reboot was scheduled for update %ls",
    (const wchar_t *)off_1400201D8);
  if ( dword_14002017C )
  {
    CommandLineW = GetCommandLineW();
    WusaEventUninstallRebootInitiated(off_1400201D8, CommandLineW);
  }
  else
  {
    v11 = GetCommandLineW();
    WusaEventInstallRebootInitiated(off_1400201D8, v11);
  }
  v0 = 3018;
  if ( dword_14002024C >= 0 )
    return 1641;
  return v0;
}

```

## disassembly

```asm
0x140008ff8  mov     [rsp+arg_8], rbx
0x140008ffd  mov     [rsp+arg_10], rsi
0x140009002  push    rdi
0x140009003  sub     rsp, 30h
0x140009007  mov     eax, cs:dword_140020250
0x14000900d  xor     esi, esi
0x14000900f  test    eax, eax
0x140009011  jz      short loc_140009025
0x140009013  cmp     cs:dword_14002024C, 0
0x14000901a  mov     esi, 0BC9h
0x14000901f  lea     ecx, [rsi-7]
0x140009022  cmovge  esi, ecx
0x140009025  mov     r9d, cs:dword_14002021C
0x14000902c  mov     edi, cs:dword_140020194
0x140009032  test    r9d, r9d
0x140009035  jnz     loc_14000924C
0x14000903b  test    eax, eax
0x14000903d  jz      loc_14000924C
0x140009043  cmp     edi, 1
0x140009046  jz      loc_14000924C
0x14000904c  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x140009053  call    ?EnablePrivilege@@YAJPEBG@Z; EnablePrivilege(ushort const *)
0x140009058  mov     ebx, eax
0x14000905a  test    eax, eax
0x14000905c  jns     short loc_14000906F
0x14000905e  mov     edx, 693h
0x140009063  lea     r8, aFailedToSetPri_0; "Failed to set privilege SE_SHUTDOWN_NAM"...
0x14000906a  jmp     loc_1400091CB
0x14000906f  mov     r8d, 2; dwReturn
0x140009075  test    edi, edi
0x140009077  jnz     short loc_140009081
0x140009079  cmp     cs:dword_140020188, edi
0x14000907f  jz      short loc_1400090DB
0x140009081  sub     edi, r8d
0x140009084  jz      loc_140009175
0x14000908a  sub     edi, 1
0x14000908d  jz      loc_140009131
0x140009093  cmp     edi, 1
0x140009096  jz      short loc_1400090DB
0x140009098  mov     [rsp+38h+dwReason], 80020011h; dwReason
0x1400090a0  xor     r9d, r9d; bForceAppsClosed
0x1400090a3  xor     r8d, r8d; dwTimeout
0x1400090a6  mov     [rsp+38h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x1400090ae  xor     edx, edx; lpMessage
0x1400090b0  xor     ecx, ecx; lpMachineName
0x1400090b2  call    cs:__imp_InitiateSystemShutdownExW
0x1400090b8  test    eax, eax
0x1400090ba  jnz     short loc_1400090EB
0x1400090bc  call    cs:__imp_GetLastError
0x1400090c2  mov     ebx, eax
0x1400090c4  test    eax, eax
0x1400090c6  jle     short loc_1400090D1
0x1400090c8  movzx   ebx, ax
0x1400090cb  or      ebx, 80070000h
0x1400090d1  mov     edx, 6CCh
0x1400090d6  jmp     loc_1400091BA
0x1400090db  xor     edx, edx; pszPrompt
0x1400090dd  xor     ecx, ecx; hwnd
0x1400090df  mov     r9d, 80020011h; dwReasonCode
0x1400090e5  call    cs:__imp_RestartDialogEx
0x1400090eb  mov     r9, cs:off_1400201D8
0x1400090f2  lea     r8, aSucceededReboo; "Succeeded. Reboot was scheduled for upd"...
0x1400090f9  mov     edx, 6D1h
0x1400090fe  lea     rcx, aRebootifreques; "RebootIfRequested"
0x140009105  call    WusaLogDebugEventA
0x14000910a  cmp     cs:dword_14002017C, 0
0x140009111  jz      loc_140009221
0x140009117  call    cs:__imp_GetCommandLineW
0x14000911d  mov     rcx, cs:off_1400201D8
0x140009124  mov     rdx, rax
0x140009127  call    WusaEventUninstallRebootInitiated
0x14000912c  jmp     loc_140009236
0x140009131  mov     r8d, cs:dwTimeout; dwTimeout
0x140009138  xor     r9d, r9d; bForceAppsClosed
0x14000913b  mov     [rsp+38h+dwReason], 80020011h; dwReason
0x140009143  xor     edx, edx; lpMessage
0x140009145  xor     ecx, ecx; lpMachineName
0x140009147  mov     [rsp+38h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x14000914f  call    cs:__imp_InitiateSystemShutdownExW
0x140009155  test    eax, eax
0x140009157  jnz     short loc_1400090EB
0x140009159  call    cs:__imp_GetLastError
0x14000915f  mov     ebx, eax
0x140009161  test    eax, eax
0x140009163  jle     short loc_14000916E
0x140009165  movzx   ebx, ax
0x140009168  or      ebx, 80070000h
0x14000916e  mov     edx, 6B5h
0x140009173  jmp     short loc_1400091BA
0x140009175  mov     [rsp+38h+dwReason], 80020011h; dwReason
0x14000917d  mov     r9d, 1; bForceAppsClosed
0x140009183  xor     r8d, r8d; dwTimeout
0x140009186  mov     [rsp+38h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x14000918e  xor     edx, edx; lpMessage
0x140009190  xor     ecx, ecx; lpMachineName
0x140009192  call    cs:__imp_InitiateSystemShutdownExW
0x140009198  test    eax, eax
0x14000919a  jnz     loc_1400090EB
0x1400091a0  call    cs:__imp_GetLastError
0x1400091a6  mov     ebx, eax
0x1400091a8  test    eax, eax
0x1400091aa  jle     short loc_1400091B5
0x1400091ac  movzx   ebx, ax
0x1400091af  or      ebx, 80070000h
0x1400091b5  mov     edx, 6A7h
0x1400091ba  test    ebx, ebx
0x1400091bc  lea     r8, aFailedToInitia_0; "Failed to initiate system shutdown"
0x1400091c3  mov     eax, 80004005h
0x1400091c8  cmovns  ebx, eax
0x1400091cb  lea     rcx, aRebootifreques; "RebootIfRequested"
0x1400091d2  call    WusaLogDebugEventA
0x1400091d7  lea     rdx, [rsp+38h+hMem]; unsigned __int16 **
0x1400091dc  mov     [rsp+38h+hMem], 0
0x1400091e5  mov     ecx, ebx; dwMessageId
0x1400091e7  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x1400091ec  mov     rdi, [rsp+38h+hMem]
0x1400091f1  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x1400091f8  mov     r9d, ebx
0x1400091fb  mov     qword ptr [rsp+38h+bRebootAfterShutdown], rdi
0x140009200  mov     edx, 6E7h
0x140009205  lea     rcx, aRebootifreques; "RebootIfRequested"
0x14000920c  call    WusaLogDebugEventA
0x140009211  test    rdi, rdi
0x140009214  jz      short loc_14000926C
0x140009216  mov     rcx, rdi; hMem
0x140009219  call    cs:__imp_LocalFree
0x14000921f  jmp     short loc_14000926C
0x140009221  call    cs:__imp_GetCommandLineW
0x140009227  mov     rcx, cs:off_1400201D8
0x14000922e  mov     rdx, rax
0x140009231  call    WusaEventInstallRebootInitiated
0x140009236  cmp     cs:dword_14002024C, 0
0x14000923d  mov     esi, 0BCAh
0x140009242  mov     eax, 669h
0x140009247  cmovge  esi, eax
0x14000924a  jmp     short loc_14000926C
0x14000924c  mov     [rsp+38h+dwReason], edi
0x140009250  lea     r8, aRebootIsNotSch; "Reboot is not scheduled. IsRunWizardSta"...
0x140009257  mov     edx, 68Eh
0x14000925c  mov     [rsp+38h+bRebootAfterShutdown], eax
0x140009260  lea     rcx, aRebootifreques; "RebootIfRequested"
0x140009267  call    WusaLogDebugEventA
0x14000926c  mov     rbx, [rsp+38h+arg_8]
0x140009271  mov     eax, esi
0x140009273  mov     rsi, [rsp+38h+arg_10]
0x140009278  add     rsp, 30h
0x14000927c  pop     rdi
0x14000927d  retn
```
