# CUdpPortRange::Initialize(void)

- ea: `0x18001791c`
- end: `0x180017c56`
- name: `?Initialize@CUdpPortRange@@QEAAKXZ`
- size: `826`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002990`
- `0x18000ac40`
- `0x18000cc30`

## callees

- `0x18001791c`
- `0x1800180ec`
- `0x18001c12a`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180017c23`
- `KERNEL32!LeaveCriticalSection` at `0x180017c23`
- `KERNEL32!EnterCriticalSection` at `0x180017936`
- `KERNEL32!EnterCriticalSection` at `0x180017936`
- `ADVAPI32!RegOpenKeyExW` at `0x180017983`
- `ADVAPI32!RegOpenKeyExW` at `0x180017983`
- `ADVAPI32!RegCloseKey` at `0x180017957`
- `ADVAPI32!RegCloseKey` at `0x180017c38`
- `ADVAPI32!RegCloseKey` at `0x180017957`
- `ADVAPI32!RegCloseKey` at `0x180017c38`
- `WS2_32!__imp_closesocket` at `0x180017c07`
- `WS2_32!__imp_closesocket` at `0x180017c07`
- `WS2_32!__imp_socket` at `0x180017b7f`
- `WS2_32!__imp_socket` at `0x180017bd5`
- `WS2_32!__imp_socket` at `0x180017b7f`
- `WS2_32!__imp_socket` at `0x180017bd5`
- `WS2_32!__imp_WSAGetLastError` at `0x180017b91`
- `WS2_32!__imp_WSAGetLastError` at `0x180017be7`
- `WS2_32!__imp_WSAGetLastError` at `0x180017b91`
- `WS2_32!__imp_WSAGetLastError` at `0x180017be7`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017a00`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b03`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b27`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b5e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017bbd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017a00`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b03`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b27`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b5e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017bbd`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x1800179b8`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180017a2f`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180017a67`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x1800179b8`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180017a2f`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180017a67`

## string_xrefs

- `0x180017975`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x180017b18`: `[UDPPorts] Fixed UDP port range policy is incorrectly configured (start=%u end=%u).`
- `0x180017ae9`: `[UDPPorts] Fixed UDP port range policy successfully configured: using ports %u to %u.`
- `0x180017b41`: `[UDPPorts] Winsock dynamic UDP port range policy successfully configured.`

## pseudocode

```c
__int64 __fastcall CUdpPortRange::Initialize(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 ValueDwordWithDefault; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // r14d
  LONG v13; // esi
  int v14; // ecx
  unsigned int v15; // r15d
  unsigned int LockSemaphore_high; // eax
  SOCKET v17; // rax
  unsigned int Error; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-10h]
  unsigned int v26; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+80h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  hKey = 0;
  EnterCriticalSection(lpCriticalSection);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( hKey )
    RegCloseKey(hKey);
  LODWORD(ValueDwordWithDefault) = RegOpenKeyExW(
                                     HKEY_LOCAL_MACHINE,
                                     L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                                     0,
                                     0x20119u,
                                     &hKey);
  if ( (unsigned int)ElValidateWin32_10((unsigned int)ValueDwordWithDefault, v3, v4, 110) )
    goto LABEL_27;
  ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"UdpPortPolicy", 0, &v26);
  if ( (unsigned int)ElValidateWin32_10(ValueDwordWithDefault, v5, v6, 117) )
    goto LABEL_27;
  v7 = v26;
  if ( !v26 )
    goto LABEL_8;
  if ( v26 != 1 )
  {
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x40000u,
      L"[UDPPorts] UDP port range policy value %u is invalid, using Winsock dynamic policy.",
      v26);
    v7 = 0;
    v26 = 0;
LABEL_8:
    if ( v7 != 1 )
    {
      HIDWORD(lpCriticalSection[1].DebugInfo) = 0;
      lpCriticalSection[1].LockCount = 0;
      HIDWORD(lpCriticalSection[1639].LockSemaphore) = 0;
      LODWORD(lpCriticalSection[1].DebugInfo) = v7;
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x20000u,
        L"[UDPPorts] Winsock dynamic UDP port range policy successfully configured.");
LABEL_22:
      v17 = socket(lpCriticalSection[1639].SpinCount, 2, 17);
      if ( v17 == -1
        && (WSAGetLastError() != 10047
         || (LODWORD(lpCriticalSection[1639].SpinCount) = 23,
             CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[UDPPorts] No IPv4 support; using IPv6 sockets"),
             v17 = socket(lpCriticalSection[1639].SpinCount, 2, 17),
             v17 == -1)) )
      {
        Error = WSAGetLastError();
        LODWORD(ValueDwordWithDefault) = ElValidateWin32_10(Error, v19, v20, 247);
      }
      else
      {
        v21 = closesocket(v17);
        ElValidateWin32_10(v21, v22, v23, 255);
      }
      goto LABEL_27;
    }
  }
  LODWORD(ValueDwordWithDefault) = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"UdpStartPort", 0xF618u, &v27);
  if ( !(unsigned int)ElValidateWin32_10((unsigned int)ValueDwordWithDefault, v8, v9, 140) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"UdpEndPort", 0xFA00u, &v28);
    if ( !(unsigned int)ElValidateWin32_10(ValueDwordWithDefault, v10, v11, 147) )
    {
      v12 = v27;
      v13 = v28;
      v14 = v27 - 1;
      if ( v27 - 1 <= 0xFFFE && v28 - 1 <= 0xFFFE && v27 <= v28 )
      {
        v15 = v26;
        if ( LODWORD(lpCriticalSection[1].DebugInfo) == v26 )
        {
          LockSemaphore_high = HIDWORD(lpCriticalSection[1639].LockSemaphore);
          if ( v27 > LockSemaphore_high || LockSemaphore_high > v28 )
            HIDWORD(lpCriticalSection[1639].LockSemaphore) = v14;
        }
        else
        {
          HIDWORD(lpCriticalSection[1639].LockSemaphore) = v14;
          memset_0(&lpCriticalSection[1].RecursionCount, 0, 0xFFFFu);
        }
        LODWORD(lpCriticalSection[1].DebugInfo) = v15;
        HIDWORD(lpCriticalSection[1].DebugInfo) = v12;
        lpCriticalSection[1].LockCount = v13;
        LODWORD(phkResult) = v13;
        CTrace::Trace(
          (CTrace *)qword_180039310,
          0x20000u,
          L"[UDPPorts] Fixed UDP port range policy successfully configured: using ports %u to %u.",
          v12,
          phkResult);
        goto LABEL_22;
      }
      LODWORD(phkResult) = v28;
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x80000u,
        L"[UDPPorts] Fixed UDP port range policy is incorrectly configured (start=%u end=%u).",
        v27,
        phkResult);
      LODWORD(ValueDwordWithDefault) = 13;
    }
  }
LABEL_27:
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ValueDwordWithDefault;
}

```

## disassembly

```asm
0x18001791c  push    rbp
0x18001791e  push    rbx
0x18001791f  push    rsi
0x180017920  push    rdi
0x180017921  push    r13
0x180017923  push    r14
0x180017925  push    r15
0x180017927  mov     rbp, rsp
0x18001792a  sub     rsp, 30h
0x18001792e  and     [rbp+hKey], 0
0x180017933  mov     rbx, rcx
0x180017936  call    cs:__imp_EnterCriticalSection
0x18001793d  nop     dword ptr [rax+rax+00h]
0x180017942  mov     rcx, [rbp+hKey]; hKey
0x180017946  and     [rbp+arg_0], 0
0x18001794a  and     [rbp+arg_8], 0
0x18001794e  and     [rbp+arg_10], 0
0x180017952  test    rcx, rcx
0x180017955  jz      short loc_180017963
0x180017957  call    cs:__imp_RegCloseKey
0x18001795e  nop     dword ptr [rax+rax+00h]
0x180017963  lea     rax, [rbp+hKey]
0x180017967  mov     r9d, 20119h; samDesired
0x18001796d  xor     r8d, r8d; ulOptions
0x180017970  mov     [rsp+30h+phkResult], rax; phkResult
0x180017975  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18001797c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017983  call    cs:__imp_RegOpenKeyExW
0x18001798a  nop     dword ptr [rax+rax+00h]
0x18001798f  mov     ecx, eax
0x180017991  mov     r9d, 6Eh ; 'n'
0x180017997  mov     edi, eax
0x180017999  call    ElValidateWin32_10
0x18001799e  test    eax, eax
0x1800179a0  jnz     loc_180017C20
0x1800179a6  lea     r9, [rbp+arg_0]
0x1800179aa  xor     r8d, r8d
0x1800179ad  lea     rdx, aUdpportpolicy; "UdpPortPolicy"
0x1800179b4  lea     rcx, [rbp+hKey]
0x1800179b8  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x1800179bf  nop     dword ptr [rax+rax+00h]
0x1800179c4  mov     ecx, eax
0x1800179c6  mov     r9d, 75h ; 'u'
0x1800179cc  mov     edi, eax
0x1800179ce  call    ElValidateWin32_10
0x1800179d3  test    eax, eax
0x1800179d5  jnz     loc_180017C20
0x1800179db  mov     eax, [rbp+arg_0]
0x1800179de  lea     r13, qword_180039310
0x1800179e5  test    eax, eax
0x1800179e7  jz      short loc_180017A11
0x1800179e9  cmp     eax, 1
0x1800179ec  jz      short loc_180017A1A
0x1800179ee  mov     r9d, eax
0x1800179f1  lea     r8, aUdpportsUdpPor; "[UDPPorts] UDP port range policy value "...
0x1800179f8  mov     edx, 40000h
0x1800179fd  mov     rcx, r13
0x180017a00  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017a07  nop     dword ptr [rax+rax+00h]
0x180017a0c  xor     eax, eax
0x180017a0e  mov     [rbp+arg_0], eax
0x180017a11  cmp     eax, 1
0x180017a14  jnz     loc_180017B3D
0x180017a1a  lea     r9, [rbp+arg_8]
0x180017a1e  mov     r8d, 0F618h
0x180017a24  lea     rdx, aUdpstartport; "UdpStartPort"
0x180017a2b  lea     rcx, [rbp+hKey]
0x180017a2f  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180017a36  nop     dword ptr [rax+rax+00h]
0x180017a3b  mov     ecx, eax
0x180017a3d  mov     r9d, 8Ch
0x180017a43  mov     edi, eax
0x180017a45  call    ElValidateWin32_10
0x180017a4a  test    eax, eax
0x180017a4c  jnz     loc_180017C20
0x180017a52  lea     r9, [rbp+arg_10]
0x180017a56  mov     r8d, 0FA00h
0x180017a5c  lea     rdx, aUdpendport; "UdpEndPort"
0x180017a63  lea     rcx, [rbp+hKey]
0x180017a67  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180017a6e  nop     dword ptr [rax+rax+00h]
0x180017a73  mov     ecx, eax
0x180017a75  mov     r9d, 93h
0x180017a7b  mov     edi, eax
0x180017a7d  call    ElValidateWin32_10
0x180017a82  test    eax, eax
0x180017a84  jnz     loc_180017C20
0x180017a8a  mov     r14d, [rbp+arg_8]
0x180017a8e  mov     edx, 0FFFEh
0x180017a93  mov     esi, [rbp+arg_10]
0x180017a96  lea     ecx, [r14-1]
0x180017a9a  cmp     ecx, edx
0x180017a9c  ja      short loc_180017B11
0x180017a9e  lea     eax, [rsi-1]
0x180017aa1  cmp     eax, edx
0x180017aa3  ja      short loc_180017B11
0x180017aa5  cmp     r14d, esi
0x180017aa8  ja      short loc_180017B11
0x180017aaa  mov     r15d, [rbp+arg_0]
0x180017aae  cmp     [rbx+28h], r15d
0x180017ab2  jz      short loc_180017ACD
0x180017ab4  mov     [rbx+10034h], ecx
0x180017aba  xor     edx, edx; Val
0x180017abc  lea     rcx, [rbx+34h]; void *
0x180017ac0  mov     r8d, 0FFFFh; Size
0x180017ac6  call    memset_0
0x180017acb  jmp     short loc_180017AE2
0x180017acd  mov     eax, [rbx+10034h]
0x180017ad3  cmp     r14d, eax
0x180017ad6  ja      short loc_180017ADC
0x180017ad8  cmp     eax, esi
0x180017ada  jbe     short loc_180017AE2
0x180017adc  mov     [rbx+10034h], ecx
0x180017ae2  mov     r9d, r14d
0x180017ae5  mov     [rbx+28h], r15d
0x180017ae9  lea     r8, aUdpportsFixedU_0; "[UDPPorts] Fixed UDP port range policy "...
0x180017af0  mov     [rbx+2Ch], r14d
0x180017af4  mov     edx, 20000h
0x180017af9  mov     [rbx+30h], esi
0x180017afc  mov     rcx, r13
0x180017aff  mov     dword ptr [rsp+30h+phkResult], esi
0x180017b03  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017b0a  nop     dword ptr [rax+rax+00h]
0x180017b0f  jmp     short loc_180017B6A
0x180017b11  mov     r9d, r14d
0x180017b14  mov     dword ptr [rsp+30h+phkResult], esi
0x180017b18  lea     r8, aUdpportsFixedU; "[UDPPorts] Fixed UDP port range policy "...
0x180017b1f  mov     edx, 80000h
0x180017b24  mov     rcx, r13
0x180017b27  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017b2e  nop     dword ptr [rax+rax+00h]
0x180017b33  mov     edi, 0Dh
0x180017b38  jmp     loc_180017C20
0x180017b3d  and     dword ptr [rbx+2Ch], 0
0x180017b41  lea     r8, aUdpportsWinsoc; "[UDPPorts] Winsock dynamic UDP port ran"...
0x180017b48  and     dword ptr [rbx+30h], 0
0x180017b4c  mov     edx, 20000h
0x180017b51  and     dword ptr [rbx+10034h], 0
0x180017b58  mov     rcx, r13
0x180017b5b  mov     [rbx+28h], eax
0x180017b5e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017b65  nop     dword ptr [rax+rax+00h]
0x180017b6a  mov     ecx, [rbx+10038h]; af
0x180017b70  mov     esi, 11h
0x180017b75  mov     r8d, esi; protocol
0x180017b78  lea     r14d, [rsi-0Fh]
0x180017b7c  mov     edx, r14d; type
0x180017b7f  call    cs:__imp_socket
0x180017b86  nop     dword ptr [rax+rax+00h]
0x180017b8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017b8f  jnz     short loc_180017C04
0x180017b91  call    cs:__imp_WSAGetLastError
0x180017b98  nop     dword ptr [rax+rax+00h]
0x180017b9d  cmp     eax, 273Fh
0x180017ba2  jnz     short loc_180017BE7
0x180017ba4  lea     r8, aUdpportsNoIpv4; "[UDPPorts] No IPv4 support; using IPv6 "...
0x180017bab  mov     dword ptr [rbx+10038h], 17h
0x180017bb5  mov     edx, 20000h
0x180017bba  mov     rcx, r13
0x180017bbd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017bc4  nop     dword ptr [rax+rax+00h]
0x180017bc9  mov     ecx, [rbx+10038h]; af
0x180017bcf  mov     r8d, esi; protocol
0x180017bd2  mov     edx, r14d; type
0x180017bd5  call    cs:__imp_socket
0x180017bdc  nop     dword ptr [rax+rax+00h]
0x180017be1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017be5  jnz     short loc_180017C04
0x180017be7  call    cs:__imp_WSAGetLastError
0x180017bee  nop     dword ptr [rax+rax+00h]
0x180017bf3  mov     ecx, eax
0x180017bf5  mov     r9d, 0F7h
0x180017bfb  call    ElValidateWin32_10
0x180017c00  mov     edi, eax
0x180017c02  jmp     short loc_180017C20
0x180017c04  mov     rcx, rax; s
0x180017c07  call    cs:__imp_closesocket
0x180017c0e  nop     dword ptr [rax+rax+00h]
0x180017c13  mov     ecx, eax
0x180017c15  mov     r9d, 0FFh
0x180017c1b  call    ElValidateWin32_10
0x180017c20  mov     rcx, rbx; lpCriticalSection
0x180017c23  call    cs:__imp_LeaveCriticalSection
0x180017c2a  nop     dword ptr [rax+rax+00h]
0x180017c2f  mov     rcx, [rbp+hKey]; hKey
0x180017c33  test    rcx, rcx
0x180017c36  jz      short loc_180017C44
0x180017c38  call    cs:__imp_RegCloseKey
0x180017c3f  nop     dword ptr [rax+rax+00h]
0x180017c44  mov     eax, edi
0x180017c46  add     rsp, 30h
0x180017c4a  pop     r15
0x180017c4c  pop     r14
0x180017c4e  pop     r13
0x180017c50  pop     rdi
0x180017c51  pop     rsi
0x180017c52  pop     rbx
0x180017c53  pop     rbp
0x180017c54  retn
```
