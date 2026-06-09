# CPxeEndpoints::ReadParameters(void)

- ea: `0x180003924`
- end: `0x180003b6f`
- name: `?ReadParameters@CPxeEndpoints@@AEAAKXZ`
- size: `587`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003eac`

## callees

- `0x180002a30`
- `0x180003924`
- `0x180003f34`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003944`
- `KERNEL32!EnterCriticalSection` at `0x180003944`
- `KERNEL32!LeaveCriticalSection` at `0x180003b43`
- `KERNEL32!LeaveCriticalSection` at `0x180003b43`
- `ADVAPI32!RegCloseKey` at `0x180003959`
- `ADVAPI32!RegCloseKey` at `0x180003b58`
- `ADVAPI32!RegCloseKey` at `0x180003959`
- `ADVAPI32!RegCloseKey` at `0x180003b58`
- `ADVAPI32!RegOpenKeyExW` at `0x180003985`
- `ADVAPI32!RegOpenKeyExW` at `0x180003985`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x1800039c4`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180003a74`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x1800039c4`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180003a74`
- `WdsCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x180003a1d`
- `WdsCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x180003a1d`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180003ac1`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180003ac1`
- `WdsCommonLib!?Initialize@CBindPolicy@@QEAAKW4BindPolicy@1@KPEAPEBG@Z` at `0x180003aef`
- `WdsCommonLib!?Initialize@CBindPolicy@@QEAAKW4BindPolicy@1@KPEAPEBG@Z` at `0x180003aef`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180003b34`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180003b34`

## string_xrefs

- `0x180003977`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`
- `0x1800039e2`: `PXE Bind Policy registry value (%s) not found.  Assuming policy %u.`
- `0x180003a3c`: `PXE Bind List registry value (%s) not found.`
- `0x180003a93`: `PXE DHCP port policy registry value (%s) not found; will not bind on 67-68.`

## pseudocode

```c
__int64 __fastcall CPxeEndpoints::ReadParameters(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 ValueBool; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // edx
  unsigned int v23; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v24; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 **v26; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  v23 = 0;
  v26 = 0;
  v24 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
         0,
         0x20119u,
         &hKey);
  LODWORD(ValueBool) = ElValidateWin32_0(v2, v3, v4, 188);
  if ( !(unsigned int)ElValidateWin32_0((unsigned int)ValueBool, v6, v7, 189) )
  {
    LODWORD(ValueBool) = CRegKey::GetValueDword((CRegKey *)&hKey, L"BindPolicy", &v23);
    if ( (_DWORD)ValueBool == 2 )
    {
      Trace(0x20000u, L"PXE Bind Policy registry value (%s) not found.  Assuming policy %u.", L"BindPolicy", v23);
      LODWORD(ValueBool) = 0;
    }
    if ( !(unsigned int)ElValidateWin32_0((unsigned int)ValueBool, v8, v9, 203) )
    {
      LODWORD(ValueBool) = CRegKey::GetValueMultiSz((CRegKey *)&hKey, L"BindInterfaces", &v26, &v24);
      if ( (_DWORD)ValueBool == 2 )
      {
        Trace(0x20000u, L"PXE Bind List registry value (%s) not found.", L"BindInterfaces");
        LODWORD(ValueBool) = 0;
      }
      if ( !(unsigned int)ElValidateWin32_0((unsigned int)ValueBool, v10, v11, 218) )
      {
        lpCriticalSection[4].LockCount = 0;
        LODWORD(ValueBool) = CRegKey::GetValueDword(
                               (CRegKey *)&hKey,
                               L"UseDhcpPorts",
                               (unsigned int *)&lpCriticalSection[4].LockCount);
        if ( (_DWORD)ValueBool == 2 )
        {
          Trace(
            0x20000u,
            L"PXE DHCP port policy registry value (%s) not found; will not bind on 67-68.",
            L"UseDhcpPorts");
          LODWORD(ValueBool) = 0;
        }
        if ( !(unsigned int)ElValidateWin32_0((unsigned int)ValueBool, v12, v13, 233) )
        {
          ValueBool = CRegKey::GetValueBool(
                        (CRegKey *)&hKey,
                        L"DisableRogueDetection",
                        (int *)&lpCriticalSection[2].SpinCount + 1);
          if ( !(unsigned int)ElValidateWin32_0(ValueBool, v14, v15, 240) )
          {
            v16 = CBindPolicy::Initialize(&lpCriticalSection[1], v23, v24, v26);
            LODWORD(ValueBool) = ElValidateWin32_0(v16, v17, v18, 247);
            ElValidateWin32_0((unsigned int)ValueBool, v19, v20, 248);
          }
        }
      }
    }
  }
  v21 = v24;
  lpCriticalSection[4].RecursionCount = ValueBool != 0;
  if ( v21 && v26 )
    CRegKey::FreeMultiSz(v26, v21);
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ValueBool;
}

```

## disassembly

```asm
0x180003924  push    rbp
0x180003926  push    rbx
0x180003927  push    rdi
0x180003928  mov     rbp, rsp
0x18000392b  sub     rsp, 30h
0x18000392f  and     [rbp+hKey], 0
0x180003934  mov     rdi, rcx
0x180003937  and     [rbp+arg_0], 0
0x18000393b  and     [rbp+arg_18], 0
0x180003940  and     [rbp+arg_8], 0
0x180003944  call    cs:__imp_EnterCriticalSection
0x18000394b  nop     dword ptr [rax+rax+00h]
0x180003950  mov     rcx, [rbp+hKey]; hKey
0x180003954  test    rcx, rcx
0x180003957  jz      short loc_180003965
0x180003959  call    cs:__imp_RegCloseKey
0x180003960  nop     dword ptr [rax+rax+00h]
0x180003965  lea     rax, [rbp+hKey]
0x180003969  mov     r9d, 20119h; samDesired
0x18000396f  xor     r8d, r8d; ulOptions
0x180003972  mov     [rsp+30h+phkResult], rax; phkResult
0x180003977  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000397e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003985  call    cs:__imp_RegOpenKeyExW
0x18000398c  nop     dword ptr [rax+rax+00h]
0x180003991  mov     ecx, eax
0x180003993  mov     r9d, 0BCh
0x180003999  call    ElValidateWin32_0
0x18000399e  mov     r9d, 0BDh
0x1800039a4  mov     ecx, eax
0x1800039a6  mov     ebx, eax
0x1800039a8  call    ElValidateWin32_0
0x1800039ad  test    eax, eax
0x1800039af  jnz     loc_180003B17
0x1800039b5  lea     r8, [rbp+arg_0]
0x1800039b9  lea     rdx, aBindpolicy; "BindPolicy"
0x1800039c0  lea     rcx, [rbp+hKey]
0x1800039c4  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x1800039cb  nop     dword ptr [rax+rax+00h]
0x1800039d0  mov     ebx, eax
0x1800039d2  cmp     eax, 2
0x1800039d5  jnz     short loc_1800039F5
0x1800039d7  mov     r9d, [rbp+arg_0]
0x1800039db  lea     r8, aBindpolicy; "BindPolicy"
0x1800039e2  lea     rdx, aPxeBindPolicyR; "PXE Bind Policy registry value (%s) not"...
0x1800039e9  mov     ecx, 20000h; unsigned int
0x1800039ee  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x1800039f3  xor     ebx, ebx
0x1800039f5  mov     r9d, 0CBh
0x1800039fb  mov     ecx, ebx
0x1800039fd  call    ElValidateWin32_0
0x180003a02  test    eax, eax
0x180003a04  jnz     loc_180003B17
0x180003a0a  lea     r9, [rbp+arg_8]
0x180003a0e  lea     r8, [rbp+arg_18]
0x180003a12  lea     rdx, aBindinterfaces; "BindInterfaces"
0x180003a19  lea     rcx, [rbp+hKey]
0x180003a1d  call    cs:__imp_?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z; CRegKey::GetValueMultiSz(ushort const *,ushort * * *,ulong *)
0x180003a24  nop     dword ptr [rax+rax+00h]
0x180003a29  mov     ebx, eax
0x180003a2b  cmp     eax, 2
0x180003a2e  jnz     short loc_180003A4A
0x180003a30  lea     r8, aBindinterfaces; "BindInterfaces"
0x180003a37  mov     ecx, 20000h; unsigned int
0x180003a3c  lea     rdx, aPxeBindListReg; "PXE Bind List registry value (%s) not f"...
0x180003a43  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180003a48  xor     ebx, ebx
0x180003a4a  mov     r9d, 0DAh
0x180003a50  mov     ecx, ebx
0x180003a52  call    ElValidateWin32_0
0x180003a57  test    eax, eax
0x180003a59  jnz     loc_180003B17
0x180003a5f  lea     r8, [rdi+0A8h]
0x180003a66  and     [r8], eax
0x180003a69  lea     rdx, aUsedhcpports; "UseDhcpPorts"
0x180003a70  lea     rcx, [rbp+hKey]
0x180003a74  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180003a7b  nop     dword ptr [rax+rax+00h]
0x180003a80  mov     ebx, eax
0x180003a82  cmp     eax, 2
0x180003a85  jnz     short loc_180003AA1
0x180003a87  lea     r8, aUsedhcpports; "UseDhcpPorts"
0x180003a8e  mov     ecx, 20000h; unsigned int
0x180003a93  lea     rdx, aPxeDhcpPortPol; "PXE DHCP port policy registry value (%s"...
0x180003a9a  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180003a9f  xor     ebx, ebx
0x180003aa1  mov     r9d, 0E9h
0x180003aa7  mov     ecx, ebx
0x180003aa9  call    ElValidateWin32_0
0x180003aae  test    eax, eax
0x180003ab0  jnz     short loc_180003B17
0x180003ab2  lea     r8, [rdi+74h]
0x180003ab6  lea     rdx, aDisableroguede; "DisableRogueDetection"
0x180003abd  lea     rcx, [rbp+hKey]
0x180003ac1  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x180003ac8  nop     dword ptr [rax+rax+00h]
0x180003acd  mov     ecx, eax
0x180003acf  mov     r9d, 0F0h
0x180003ad5  mov     ebx, eax
0x180003ad7  call    ElValidateWin32_0
0x180003adc  test    eax, eax
0x180003ade  jnz     short loc_180003B17
0x180003ae0  mov     r9, [rbp+arg_18]
0x180003ae4  lea     rcx, [rdi+28h]
0x180003ae8  mov     r8d, [rbp+arg_8]
0x180003aec  mov     edx, [rbp+arg_0]
0x180003aef  call    cs:__imp_?Initialize@CBindPolicy@@QEAAKW4BindPolicy@1@KPEAPEBG@Z; CBindPolicy::Initialize(CBindPolicy::BindPolicy,ulong,ushort const * *)
0x180003af6  nop     dword ptr [rax+rax+00h]
0x180003afb  mov     ecx, eax
0x180003afd  mov     r9d, 0F7h
0x180003b03  call    ElValidateWin32_0
0x180003b08  mov     r9d, 0F8h
0x180003b0e  mov     ecx, eax
0x180003b10  mov     ebx, eax
0x180003b12  call    ElValidateWin32_0
0x180003b17  mov     edx, [rbp+arg_8]
0x180003b1a  xor     eax, eax
0x180003b1c  test    ebx, ebx
0x180003b1e  setnz   al
0x180003b21  mov     [rdi+0ACh], eax
0x180003b27  test    edx, edx
0x180003b29  jz      short loc_180003B40
0x180003b2b  mov     rcx, [rbp+arg_18]
0x180003b2f  test    rcx, rcx
0x180003b32  jz      short loc_180003B40
0x180003b34  call    cs:__imp_?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x180003b3b  nop     dword ptr [rax+rax+00h]
0x180003b40  mov     rcx, rdi; lpCriticalSection
0x180003b43  call    cs:__imp_LeaveCriticalSection
0x180003b4a  nop     dword ptr [rax+rax+00h]
0x180003b4f  mov     rcx, [rbp+hKey]; hKey
0x180003b53  test    rcx, rcx
0x180003b56  jz      short loc_180003B64
0x180003b58  call    cs:__imp_RegCloseKey
0x180003b5f  nop     dword ptr [rax+rax+00h]
0x180003b64  mov     eax, ebx
0x180003b66  add     rsp, 30h
0x180003b6a  pop     rdi
0x180003b6b  pop     rbx
0x180003b6c  pop     rbp
0x180003b6d  retn
```
