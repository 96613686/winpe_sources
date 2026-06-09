# RegisterEventLogSource(void)

- ea: `0x18003c86c`
- end: `0x18003ca0c`
- name: `?RegisterEventLogSource@@YAJXZ`
- size: `416`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180039aa4`

## callees

- `0x18003abe4`
- `0x18003c86c`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003c8a7`
- `KERNEL32!lstrlenW` at `0x18003c8a7`
- `ADVAPI32!RegCloseKey` at `0x18003c9da`
- `ADVAPI32!RegCloseKey` at `0x18003c9da`
- `ADVAPI32!RegCreateKeyExW` at `0x18003c8eb`
- `ADVAPI32!RegCreateKeyExW` at `0x18003c8eb`
- `ADVAPI32!RegSetValueExW` at `0x18003c937`
- `ADVAPI32!RegSetValueExW` at `0x18003c95d`
- `ADVAPI32!RegSetValueExW` at `0x18003c996`
- `ADVAPI32!RegSetValueExW` at `0x18003c9c0`
- `ADVAPI32!RegSetValueExW` at `0x18003c937`
- `ADVAPI32!RegSetValueExW` at `0x18003c95d`
- `ADVAPI32!RegSetValueExW` at `0x18003c996`
- `ADVAPI32!RegSetValueExW` at `0x18003c9c0`

## string_xrefs

- `0x18003c8b3`: `SYSTEM\CurrentControlSet\Services\EventLog\Application\ASP.NET 4.0.30319.0`

## pseudocode

```c
__int64 RegisterEventLogSource(void)
{
  DWORD v0; // ebx
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  CSetupLogging::Log(1, "RegisterEventLogSource", 0, "Registering the Asp.Net Event log source", 0);
  v0 = 2 * lstrlenW(&Names::s_wszRcFullPath) + 2;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\EventLog\\Application\\ASP.NET 4.0.30319.0",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v1
    || (Data = 7, (v1 = RegSetValueExW(hKey, L"TypesSupported", 0, 4u, (const BYTE *)&Data, 4u)) != 0)
    || (v1 = RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, (const BYTE *)&Names::s_wszRcFullPath, v0)) != 0
    || (Data = 5, (v1 = RegSetValueExW(hKey, L"CategoryCount", 0, 4u, (const BYTE *)&Data, 4u)) != 0)
    || (v1 = RegSetValueExW(hKey, L"CategoryMessageFile", 0, 2u, (const BYTE *)&Names::s_wszRcFullPath, v0)) != 0 )
  {
    v2 = (unsigned __int16)v1 | 0x80070000;
    if ( v1 <= 0 )
      v2 = v1;
  }
  else
  {
    v2 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  CSetupLogging::Log(v2, "RegisterEventLogSource", 0, "Registering the Asp.Net Event log source", 0);
  return v2;
}

```

## disassembly

```asm
0x18003c86c  mov     [rsp+arg_10], rbx
0x18003c871  push    r14
0x18003c873  sub     rsp, 50h
0x18003c877  and     [rsp+58h+hKey], 0
0x18003c87d  lea     r9, aRegisteringThe; "Registering the Asp.Net Event log sourc"...
0x18003c884  and     [rsp+58h+lpData], 0
0x18003c88a  lea     rdx, aRegistereventl; "RegisterEventLogSource"
0x18003c891  xor     r8d, r8d; unsigned int
0x18003c894  lea     ecx, [r8+1]; int
0x18003c898  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003c89d  lea     r14, ?s_wszRcFullPath@Names@@0PAGA; ushort near * Names::s_wszRcFullPath
0x18003c8a4  mov     rcx, r14; lpString
0x18003c8a7  call    cs:__imp_lstrlenW
0x18003c8ad  and     [rsp+58h+var_18], 0
0x18003c8b3  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18003c8ba  xor     r9d, r9d; lpClass
0x18003c8bd  xor     r8d, r8d; Reserved
0x18003c8c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c8c7  lea     ebx, ds:2[rax*2]
0x18003c8ce  lea     rax, [rsp+58h+hKey]
0x18003c8d3  mov     [rsp+58h+phkResult], rax; phkResult
0x18003c8d8  and     [rsp+58h+var_28], 0
0x18003c8de  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18003c8e6  and     dword ptr [rsp+58h+lpData], 0
0x18003c8eb  call    cs:__imp_RegCreateKeyExW
0x18003c8f1  test    eax, eax
0x18003c8f3  jz      short loc_18003C908
0x18003c8f5  movzx   ebx, ax
0x18003c8f8  or      ebx, 80070000h
0x18003c8fe  test    eax, eax
0x18003c900  cmovle  ebx, eax
0x18003c903  jmp     loc_18003C9D0
0x18003c908  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c90d  lea     rax, [rsp+58h+Data]
0x18003c912  mov     [rsp+58h+samDesired], 4; cbData
0x18003c91a  lea     rdx, aTypessupported; "TypesSupported"
0x18003c921  mov     r9d, 4; dwType
0x18003c927  mov     [rsp+58h+lpData], rax; lpData
0x18003c92c  xor     r8d, r8d; Reserved
0x18003c92f  mov     [rsp+58h+Data], 7
0x18003c937  call    cs:__imp_RegSetValueExW
0x18003c93d  test    eax, eax
0x18003c93f  jnz     short loc_18003C8F5
0x18003c941  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c946  lea     r9d, [rax+2]; dwType
0x18003c94a  mov     [rsp+58h+samDesired], ebx; cbData
0x18003c94e  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18003c955  xor     r8d, r8d; Reserved
0x18003c958  mov     [rsp+58h+lpData], r14; lpData
0x18003c95d  call    cs:__imp_RegSetValueExW
0x18003c963  test    eax, eax
0x18003c965  jnz     short loc_18003C8F5
0x18003c967  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c96c  lea     rax, [rsp+58h+Data]
0x18003c971  mov     [rsp+58h+samDesired], 4; cbData
0x18003c979  lea     rdx, aCategorycount; "CategoryCount"
0x18003c980  mov     r9d, 4; dwType
0x18003c986  mov     [rsp+58h+lpData], rax; lpData
0x18003c98b  xor     r8d, r8d; Reserved
0x18003c98e  mov     [rsp+58h+Data], 5
0x18003c996  call    cs:__imp_RegSetValueExW
0x18003c99c  test    eax, eax
0x18003c99e  jnz     loc_18003C8F5
0x18003c9a4  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c9a9  lea     r9d, [rax+2]; dwType
0x18003c9ad  mov     [rsp+58h+samDesired], ebx; cbData
0x18003c9b1  lea     rdx, aCategorymessag; "CategoryMessageFile"
0x18003c9b8  xor     r8d, r8d; Reserved
0x18003c9bb  mov     [rsp+58h+lpData], r14; unsigned __int16 *
0x18003c9c0  call    cs:__imp_RegSetValueExW
0x18003c9c6  test    eax, eax
0x18003c9c8  jnz     loc_18003C8F5
0x18003c9ce  xor     ebx, ebx
0x18003c9d0  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c9d5  test    rcx, rcx
0x18003c9d8  jz      short loc_18003C9E0
0x18003c9da  call    cs:__imp_RegCloseKey
0x18003c9e0  and     [rsp+58h+lpData], 0
0x18003c9e6  lea     r9, aRegisteringThe; "Registering the Asp.Net Event log sourc"...
0x18003c9ed  xor     r8d, r8d; unsigned int
0x18003c9f0  lea     rdx, aRegistereventl; "RegisterEventLogSource"
0x18003c9f7  mov     ecx, ebx; int
0x18003c9f9  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003c9fe  mov     eax, ebx
0x18003ca00  mov     rbx, [rsp+58h+arg_10]
0x18003ca05  add     rsp, 50h
0x18003ca09  pop     r14
0x18003ca0b  retn
```
