# CPxeRogueDetection::ReadParameters(void)

- ea: `0x18000d13c`
- end: `0x18000d3bd`
- name: `?ReadParameters@CPxeRogueDetection@@AEAAKXZ`
- size: `641`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c494`
- `0x1800104f4`

## callees

- `0x180002a30`
- `0x18000d13c`
- `0x180011068`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d30a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d30a`
- `KERNEL32!EnterCriticalSection` at `0x18000d15d`
- `KERNEL32!EnterCriticalSection` at `0x18000d15d`
- `KERNEL32!LeaveCriticalSection` at `0x18000d386`
- `KERNEL32!LeaveCriticalSection` at `0x18000d386`
- `ADVAPI32!RegCloseKey` at `0x18000d172`
- `ADVAPI32!RegCloseKey` at `0x18000d39b`
- `ADVAPI32!RegCloseKey` at `0x18000d172`
- `ADVAPI32!RegCloseKey` at `0x18000d39b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d19e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d19e`
- `WDSSRV!WdsGetServerInfo` at `0x18000d35e`
- `WDSSRV!WdsGetServerInfo` at `0x18000d35e`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000d328`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000d328`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d1d9`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d222`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d262`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d2ae`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d1d9`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d222`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d262`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000d2ae`

## string_xrefs

- `0x18000d190`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::ReadParameters(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int ValueDword; // edi
  const wchar_t *v6; // r8
  __int64 v7; // r8
  ULONG_PTR *p_SpinCount; // rdi
  void *SpinCount; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  v13 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
         0,
         0x20119u,
         &hKey);
  ValueDword = ElValidateWin32_4(v2, v3, v4, 347);
  if ( !ValueDword )
  {
    LODWORD(lpCriticalSection[1].OwningThread) = 3600;
    ValueDword = CRegKey::GetValueDword(
                   (CRegKey *)&hKey,
                   L"AuthRecheckTime",
                   (unsigned int *)&lpCriticalSection[1].OwningThread);
    if ( (ValueDword & 0xFFFFFFFD) == 0 )
    {
      Trace(0x20000u, L"Rogue Detection: Auth Recheck Time=%u", LODWORD(lpCriticalSection[1].OwningThread));
      HIDWORD(lpCriticalSection[1].OwningThread) = 30;
      ValueDword = CRegKey::GetValueDword(
                     (CRegKey *)&hKey,
                     L"AuthFailureRetryTime",
                     (unsigned int *)&lpCriticalSection[1].OwningThread + 1);
      if ( (ValueDword & 0xFFFFFFFD) == 0 )
      {
        Trace(0x20000u, L"Rogue Detection: Auth Failure Retry Time=%u", HIDWORD(lpCriticalSection[1].OwningThread));
        LODWORD(lpCriticalSection[1].LockSemaphore) = 0;
        ValueDword = CRegKey::GetValueDword(
                       (CRegKey *)&hKey,
                       L"DisableRogueDetection",
                       (unsigned int *)&lpCriticalSection[1].LockSemaphore);
        if ( (ValueDword & 0xFFFFFFFD) == 0 )
        {
          v6 = L"Yes";
          if ( !LODWORD(lpCriticalSection[1].LockSemaphore) )
            v6 = L"No";
          Trace(0x20000u, L"Rogue Detection: Disable Rogue Detection=%s", v6);
          if ( !CRegKey::GetValueDword((CRegKey *)&hKey, L"AssumeRole", (unsigned int *)&v13) )
          {
            if ( (unsigned int)v13 <= 3 )
            {
              v7 = v13;
              HIDWORD(lpCriticalSection[5].LockSemaphore) = v13;
              Trace(0x20000u, L"Rogue Detection: Assume Server Role=%s", (&off_180014C30)[v7]);
            }
            else
            {
              Trace(0x20000u, L"Rogue Detection: Invalid AssumeRole(%u) specified. Ignoring.", (unsigned int)v13);
            }
          }
          p_SpinCount = &lpCriticalSection[5].SpinCount;
          SpinCount = (void *)lpCriticalSection[5].SpinCount;
          if ( SpinCount )
          {
            operator delete[](SpinCount);
            *p_SpinCount = 0;
          }
          if ( !CRegKey::GetValueSz(
                  (CRegKey *)&hKey,
                  L"AssumeDomain",
                  (unsigned __int16 **)&lpCriticalSection[5].SpinCount) )
            Trace(0x20000u, L"Rogue Detection: Assume Domain=%s", *p_SpinCount);
          ValueDword = WdsGetServerInfo(2, &lpCriticalSection[2], 128, &lpCriticalSection[5].LockCount);
          ElValidateWin32_4(ValueDword, v10, v11, 435);
        }
      }
    }
  }
  lpCriticalSection[1].LockCount = ValueDword != 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return ValueDword;
}

```

## disassembly

```asm
0x18000d13c  mov     [rsp-18h+arg_10], rbx
0x18000d141  mov     [rsp-18h+arg_18], rsi
0x18000d146  push    rbp
0x18000d147  push    rdi
0x18000d148  push    r15
0x18000d14a  mov     rbp, rsp
0x18000d14d  sub     rsp, 30h
0x18000d151  and     [rbp+hKey], 0
0x18000d156  mov     rbx, rcx
0x18000d159  and     [rbp+arg_0], 0
0x18000d15d  call    cs:__imp_EnterCriticalSection
0x18000d164  nop     dword ptr [rax+rax+00h]
0x18000d169  mov     rcx, [rbp+hKey]; hKey
0x18000d16d  test    rcx, rcx
0x18000d170  jz      short loc_18000D17E
0x18000d172  call    cs:__imp_RegCloseKey
0x18000d179  nop     dword ptr [rax+rax+00h]
0x18000d17e  lea     rax, [rbp+hKey]
0x18000d182  mov     r9d, 20119h; samDesired
0x18000d188  xor     r8d, r8d; ulOptions
0x18000d18b  mov     [rsp+30h+phkResult], rax; phkResult
0x18000d190  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000d197  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d19e  call    cs:__imp_RegOpenKeyExW
0x18000d1a5  nop     dword ptr [rax+rax+00h]
0x18000d1aa  mov     ecx, eax
0x18000d1ac  mov     r9d, 15Bh
0x18000d1b2  call    ElValidateWin32_4
0x18000d1b7  mov     edi, eax
0x18000d1b9  test    eax, eax
0x18000d1bb  jnz     loc_18000D379
0x18000d1c1  lea     rsi, [rbx+38h]
0x18000d1c5  mov     r8, rsi
0x18000d1c8  mov     dword ptr [rsi], 0E10h
0x18000d1ce  lea     rdx, aAuthrechecktim; "AuthRecheckTime"
0x18000d1d5  lea     rcx, [rbp+hKey]
0x18000d1d9  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000d1e0  nop     dword ptr [rax+rax+00h]
0x18000d1e5  mov     edi, eax
0x18000d1e7  test    eax, 0FFFFFFFDh
0x18000d1ec  jnz     loc_18000D379
0x18000d1f2  mov     r8d, [rsi]
0x18000d1f5  lea     rdx, aRogueDetection_4; "Rogue Detection: Auth Recheck Time=%u"
0x18000d1fc  mov     r15d, 20000h
0x18000d202  mov     ecx, r15d; unsigned int
0x18000d205  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d20a  lea     rsi, [rbx+3Ch]
0x18000d20e  mov     r8, rsi
0x18000d211  mov     dword ptr [rsi], 1Eh
0x18000d217  lea     rdx, aAuthfailureret; "AuthFailureRetryTime"
0x18000d21e  lea     rcx, [rbp+hKey]
0x18000d222  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000d229  nop     dword ptr [rax+rax+00h]
0x18000d22e  mov     edi, eax
0x18000d230  test    eax, 0FFFFFFFDh
0x18000d235  jnz     loc_18000D379
0x18000d23b  mov     r8d, [rsi]
0x18000d23e  lea     rdx, aRogueDetection_12; "Rogue Detection: Auth Failure Retry Tim"...
0x18000d245  mov     ecx, r15d; unsigned int
0x18000d248  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d24d  lea     rsi, [rbx+40h]
0x18000d251  and     dword ptr [rsi], 0
0x18000d254  lea     rdx, aDisableroguede; "DisableRogueDetection"
0x18000d25b  mov     r8, rsi
0x18000d25e  lea     rcx, [rbp+hKey]
0x18000d262  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000d269  nop     dword ptr [rax+rax+00h]
0x18000d26e  mov     edi, eax
0x18000d270  test    eax, 0FFFFFFFDh
0x18000d275  jnz     loc_18000D379
0x18000d27b  cmp     dword ptr [rsi], 0
0x18000d27e  lea     rax, aNo; "No"
0x18000d285  lea     r8, aYes; "Yes"
0x18000d28c  mov     ecx, r15d; unsigned int
0x18000d28f  cmovz   r8, rax
0x18000d293  lea     rdx, aRogueDetection_13; "Rogue Detection: Disable Rogue Detectio"...
0x18000d29a  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d29f  lea     r8, [rbp+arg_0]
0x18000d2a3  lea     rdx, aAssumerole; "AssumeRole"
0x18000d2aa  lea     rcx, [rbp+hKey]
0x18000d2ae  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000d2b5  nop     dword ptr [rax+rax+00h]
0x18000d2ba  test    eax, eax
0x18000d2bc  jnz     short loc_18000D2FB
0x18000d2be  movsxd  rax, [rbp+arg_0]
0x18000d2c2  mov     ecx, r15d; unsigned int
0x18000d2c5  cmp     eax, 3
0x18000d2c8  jbe     short loc_18000D2DB
0x18000d2ca  mov     r8d, eax
0x18000d2cd  lea     rdx, aRogueDetection_6; "Rogue Detection: Invalid AssumeRole(%u)"...
0x18000d2d4  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d2d9  jmp     short loc_18000D2FB
0x18000d2db  mov     r8, rax
0x18000d2de  mov     [rbx+0E4h], eax
0x18000d2e4  lea     rax, off_180014C30; "NT5 Domain"
0x18000d2eb  lea     rdx, aRogueDetection_8; "Rogue Detection: Assume Server Role=%s"
0x18000d2f2  mov     r8, [rax+r8*8]
0x18000d2f6  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d2fb  lea     rdi, [rbx+0E8h]
0x18000d302  mov     rcx, [rdi]
0x18000d305  test    rcx, rcx
0x18000d308  jz      short loc_18000D31A
0x18000d30a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d311  nop     dword ptr [rax+rax+00h]
0x18000d316  and     qword ptr [rdi], 0
0x18000d31a  mov     r8, rdi
0x18000d31d  lea     rdx, aAssumedomain; "AssumeDomain"
0x18000d324  lea     rcx, [rbp+hKey]
0x18000d328  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18000d32f  nop     dword ptr [rax+rax+00h]
0x18000d334  test    eax, eax
0x18000d336  jnz     short loc_18000D34A
0x18000d338  mov     r8, [rdi]
0x18000d33b  lea     rdx, aRogueDetection_7; "Rogue Detection: Assume Domain=%s"
0x18000d342  mov     ecx, r15d; unsigned int
0x18000d345  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000d34a  mov     ecx, 2
0x18000d34f  lea     r9, [rbx+0D0h]
0x18000d356  lea     rdx, [rbx+50h]
0x18000d35a  lea     r8d, [rcx+7Eh]
0x18000d35e  call    cs:__imp_WdsGetServerInfo
0x18000d365  nop     dword ptr [rax+rax+00h]
0x18000d36a  mov     ecx, eax
0x18000d36c  mov     r9d, 1B3h
0x18000d372  mov     edi, eax
0x18000d374  call    ElValidateWin32_4
0x18000d379  xor     eax, eax
0x18000d37b  mov     rcx, rbx; lpCriticalSection
0x18000d37e  test    edi, edi
0x18000d380  setnz   al
0x18000d383  mov     [rbx+30h], eax
0x18000d386  call    cs:__imp_LeaveCriticalSection
0x18000d38d  nop     dword ptr [rax+rax+00h]
0x18000d392  mov     rcx, [rbp+hKey]; hKey
0x18000d396  test    rcx, rcx
0x18000d399  jz      short loc_18000D3A7
0x18000d39b  call    cs:__imp_RegCloseKey
0x18000d3a2  nop     dword ptr [rax+rax+00h]
0x18000d3a7  mov     rbx, [rsp+30h+arg_10]
0x18000d3ac  mov     eax, edi
0x18000d3ae  mov     rsi, [rsp+30h+arg_18]
0x18000d3b3  add     rsp, 30h
0x18000d3b7  pop     r15
0x18000d3b9  pop     rdi
0x18000d3ba  pop     rbp
0x18000d3bb  retn
```
