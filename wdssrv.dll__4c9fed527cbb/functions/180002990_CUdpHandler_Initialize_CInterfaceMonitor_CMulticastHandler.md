# CUdpHandler::Initialize(CInterfaceMonitor *,CMulticastHandler *)

- ea: `0x180002990`
- end: `0x180002a99`
- name: `?Initialize@CUdpHandler@@UEAAKPEAVCInterfaceMonitor@@PEAVCMulticastHandler@@@Z`
- size: `265`
- prototype: `unsigned int __fastcall(CUdpHandler *__hidden this, struct CInterfaceMonitor *, struct CMulticastHandler *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002990`
- `0x180003944`
- `0x18001791c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800029d0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800029d0`
- `ADVAPI32!RegCloseKey` at `0x180002a48`
- `ADVAPI32!RegCloseKey` at `0x180002a48`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180002a0a`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180002a0a`

## string_xrefs

- `0x1800029ba`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall CUdpHandler::Initialize(
        CUdpHandler *this,
        struct CInterfaceMonitor *a2,
        struct CMulticastHandler *a3)
{
  unsigned int ValueDwordWithDefault; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  hKey = 0;
  *((_QWORD *)this + 11) = a2;
  *((_QWORD *)this + 12) = a3;
  ValueDwordWithDefault = RegOpenKeyExW(
                            HKEY_LOCAL_MACHINE,
                            L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                            0,
                            0x20119u,
                            &hKey);
  if ( !(unsigned int)ElValidateWin32(
                        ValueDwordWithDefault,
                        v5,
                        "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp",
                        255) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"SharedPorts", 0, &v10);
    if ( !(unsigned int)ElValidateWin32(
                          ValueDwordWithDefault,
                          v7,
                          "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp",
                          259) )
      *((_DWORD *)this + 16426) = v10 == 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !(unsigned int)ElValidateWin32(
                        ValueDwordWithDefault,
                        v6,
                        "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp",
                        107) )
  {
    ValueDwordWithDefault = CUdpPortRange::Initialize((LPCRITICAL_SECTION)((char *)this + 104));
    ElValidateWin32(ValueDwordWithDefault, v8, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 114);
  }
  return ValueDwordWithDefault;
}

```

## disassembly

```asm
0x180002990  mov     rax, rsp
0x180002993  mov     [rax+18h], rbx
0x180002997  push    rdi
0x180002998  sub     rsp, 30h
0x18000299c  and     dword ptr [rax+8], 0
0x1800029a0  mov     rdi, rcx
0x1800029a3  and     qword ptr [rax+10h], 0
0x1800029a8  lea     rax, [rax+10h]
0x1800029ac  mov     [rcx+58h], rdx
0x1800029b0  mov     r9d, 20119h; samDesired
0x1800029b6  mov     [rcx+60h], r8
0x1800029ba  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800029c1  xor     r8d, r8d; ulOptions
0x1800029c4  mov     [rsp+38h+phkResult], rax; phkResult
0x1800029c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800029d0  call    cs:__imp_RegOpenKeyExW
0x1800029d7  nop     dword ptr [rax+rax+00h]
0x1800029dc  mov     r9d, 0FFh
0x1800029e2  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x1800029e9  mov     ecx, eax
0x1800029eb  mov     ebx, eax
0x1800029ed  call    ElValidateWin32
0x1800029f2  test    eax, eax
0x1800029f4  jnz     short loc_180002A3E
0x1800029f6  lea     r9, [rsp+38h+arg_0]
0x1800029fb  xor     r8d, r8d
0x1800029fe  lea     rdx, aSharedports; "SharedPorts"
0x180002a05  lea     rcx, [rsp+38h+hKey]
0x180002a0a  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180002a11  nop     dword ptr [rax+rax+00h]
0x180002a16  mov     r9d, 103h
0x180002a1c  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180002a23  mov     ecx, eax
0x180002a25  mov     ebx, eax
0x180002a27  call    ElValidateWin32
0x180002a2c  test    eax, eax
0x180002a2e  jnz     short loc_180002A3E
0x180002a30  cmp     [rsp+38h+arg_0], 1
0x180002a35  setz    al
0x180002a38  mov     [rdi+100A8h], eax
0x180002a3e  mov     rcx, [rsp+38h+hKey]; hKey
0x180002a43  test    rcx, rcx
0x180002a46  jz      short loc_180002A54
0x180002a48  call    cs:__imp_RegCloseKey
0x180002a4f  nop     dword ptr [rax+rax+00h]
0x180002a54  mov     r9d, 6Bh ; 'k'
0x180002a5a  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180002a61  mov     ecx, ebx
0x180002a63  call    ElValidateWin32
0x180002a68  test    eax, eax
0x180002a6a  jnz     short loc_180002A8B
0x180002a6c  lea     rcx, [rdi+68h]; lpCriticalSection
0x180002a70  call    ?Initialize@CUdpPortRange@@QEAAKXZ; CUdpPortRange::Initialize(void)
0x180002a75  mov     r9d, 72h ; 'r'
0x180002a7b  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180002a82  mov     ecx, eax
0x180002a84  mov     ebx, eax
0x180002a86  call    ElValidateWin32
0x180002a8b  mov     eax, ebx
0x180002a8d  mov     rbx, [rsp+38h+arg_10]
0x180002a92  add     rsp, 30h
0x180002a96  pop     rdi
0x180002a97  retn
```
