# WdsProviderServiceControl(void *,ulong)

- ea: `0x180003050`
- end: `0x180003148`
- name: `?WdsProviderServiceControl@@YAXPEAXK@Z`
- size: `248`
- prototype: `void(void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180002a30`
- `0x180003050`
- `0x180003eac`
- `0x180004c58`
- `0x1800069c4`
- `0x180006f24`
- `0x1800104f4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800030a9`
- `KERNEL32!EnterCriticalSection` at `0x1800030a9`
- `KERNEL32!LeaveCriticalSection` at `0x18000311b`
- `KERNEL32!LeaveCriticalSection` at `0x18000311b`

## pseudocode

```c
void __fastcall WdsProviderServiceControl(void *a1, unsigned int a2)
{
  const wchar_t *v3; // r8
  const wchar_t *v4; // rdx
  const wchar_t *v5; // r9

  if ( dword_18001C060 )
  {
    if ( a2 == 128 )
    {
      CPxeEndpoints::UpdateSettings(&CriticalSection);
      CPxeRogueDetection::UpdateSettings(&stru_18001CD10);
      CPxeProviderHandler::UpdateSettings((CPxeProviderHandler *)&off_18001C020);
    }
    else if ( a2 == 130 )
    {
      EnterCriticalSection(&stru_18001CD10);
      v3 = L"Yes";
      v4 = L"Yes";
      v5 = L"Yes";
      if ( !dword_18001CD50 )
        v4 = L"No";
      if ( !dword_18001CD44 )
        v5 = L"No";
      if ( !dword_18001CD40 )
        v3 = L"No";
      Trace(
        0x20000u,
        L"PXE Rogue Detection\n"
         "-------------------\n"
         "In Error State: %s\n"
         "Authorized: %s\n"
         "Rogue Detection Disabled: %s\n"
         "Retry Time: %u Seconds\n"
         "Recheck Time: %u Seconds\n",
        v3,
        v5,
        v4,
        dword_18001CD4C,
        dword_18001CD48);
      LeaveCriticalSection(&stru_18001CD10);
      CPxeProviderHandler::DumpState((CPxeProviderHandler *)&off_18001C020);
    }
    CPxeProviderHandler::ServiceControl((CPxeProviderHandler *)&off_18001C020, a2);
  }
}

```

## disassembly

```asm
0x180003050  push    rbx
0x180003052  sub     rsp, 40h
0x180003056  cmp     cs:dword_18001C060, 0
0x18000305d  mov     ebx, edx
0x18000305f  jz      loc_180003141
0x180003065  cmp     edx, 80h
0x18000306b  jnz     short loc_180003096
0x18000306d  lea     rcx, CriticalSection; lpCriticalSection
0x180003074  call    ?UpdateSettings@CPxeEndpoints@@QEAAKXZ; CPxeEndpoints::UpdateSettings(void)
0x180003079  lea     rcx, stru_18001CD10; lpCriticalSection
0x180003080  call    ?UpdateSettings@CPxeRogueDetection@@QEAAKXZ; CPxeRogueDetection::UpdateSettings(void)
0x180003085  lea     rcx, off_18001C020; this
0x18000308c  call    ?UpdateSettings@CPxeProviderHandler@@QEAAKXZ; CPxeProviderHandler::UpdateSettings(void)
0x180003091  jmp     loc_180003133
0x180003096  cmp     ebx, 82h
0x18000309c  jnz     loc_180003133
0x1800030a2  lea     rcx, stru_18001CD10; lpCriticalSection
0x1800030a9  call    cs:__imp_EnterCriticalSection
0x1800030b0  nop     dword ptr [rax+rax+00h]
0x1800030b5  cmp     cs:dword_18001CD50, 0
0x1800030bc  lea     rax, aNo; "No"
0x1800030c3  lea     r8, aYes; "Yes"
0x1800030ca  mov     ecx, 20000h; unsigned int
0x1800030cf  mov     rdx, r8
0x1800030d2  mov     r9, r8
0x1800030d5  cmovz   rdx, rax
0x1800030d9  cmp     cs:dword_18001CD44, 0
0x1800030e0  cmovz   r9, rax
0x1800030e4  cmp     cs:dword_18001CD40, 0
0x1800030eb  cmovz   r8, rax
0x1800030ef  mov     eax, cs:dword_18001CD48
0x1800030f5  mov     [rsp+48h+var_18], eax
0x1800030f9  mov     eax, cs:dword_18001CD4C
0x1800030ff  mov     [rsp+48h+var_20], eax
0x180003103  mov     [rsp+48h+var_28], rdx
0x180003108  lea     rdx, aPxeRogueDetect; "PXE Rogue Detection\n------------------"...
0x18000310f  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180003114  lea     rcx, stru_18001CD10; lpCriticalSection
0x18000311b  call    cs:__imp_LeaveCriticalSection
0x180003122  nop     dword ptr [rax+rax+00h]
0x180003127  lea     rcx, off_18001C020; this
0x18000312e  call    ?DumpState@CPxeProviderHandler@@QEAAXXZ; CPxeProviderHandler::DumpState(void)
0x180003133  mov     edx, ebx; unsigned int
0x180003135  lea     rcx, off_18001C020; this
0x18000313c  call    ?ServiceControl@CPxeProviderHandler@@QEAAXK@Z; CPxeProviderHandler::ServiceControl(ulong)
0x180003141  add     rsp, 40h
0x180003145  pop     rbx
0x180003146  retn
```
