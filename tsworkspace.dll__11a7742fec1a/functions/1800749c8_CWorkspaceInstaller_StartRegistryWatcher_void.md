# CWorkspaceInstaller::StartRegistryWatcher(void)

- ea: `0x1800749c8`
- end: `0x180074b56`
- name: `?StartRegistryWatcher@CWorkspaceInstaller@@QEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(CWorkspaceInstaller *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800743a0`
- `0x180074d30`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800749c8`
- `0x180089a20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180074a78`
- `ADVAPI32!RegCloseKey` at `0x180074a78`
- `ADVAPI32!RegCreateKeyExW` at `0x180074a66`
- `ADVAPI32!RegCreateKeyExW` at `0x180074a66`

## string_xrefs

- `0x180074b15`: `failed to setup listner thread on regkeys`

## pseudocode

```c
__int64 __fastcall CWorkspaceInstaller::StartRegistryWatcher(CWorkspaceInstaller *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HKEY v3; // rdx
  LSTATUS v4; // ebx
  unsigned int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 samDesired; // [rsp+28h] [rbp-30h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v4 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Workspaces\\Events", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      else
        v5 = v4;
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids, v6, v5);
    }
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v4 = CSimpleRegistryWatcher::WatchRegKeyForUpdates(
           (CWorkspaceInstaller *)((char *)this + 8),
           v3,
           L"Software\\Microsoft\\Workspaces\\Events");
    if ( v4 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(samDesired) = v4;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v7,
        (__int64)"failed to setup listner thread on regkeys",
        samDesired);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800749c8  mov     [rsp+arg_0], rbx
0x1800749cd  mov     [rsp+arg_10], rbp
0x1800749d2  push    rdi
0x1800749d3  sub     rsp, 50h
0x1800749d7  mov     rdi, rcx
0x1800749da  mov     [rsp+58h+hKey], 0
0x1800749e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800749ea  lea     rbp, WPP_GLOBAL_Control
0x1800749f1  cmp     rax, rbp
0x1800749f4  jz      short loc_180074A26
0x1800749f6  test    byte ptr [rax+1Ch], 1
0x1800749fa  jz      short loc_180074A26
0x1800749fc  cmp     byte ptr [rax+19h], 4
0x180074a00  jb      short loc_180074A26
0x180074a02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180074a0e  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074a15  mov     edx, 24h ; '$'
0x180074a1a  mov     r9d, eax
0x180074a1d  mov     rcx, [rcx+10h]
0x180074a21  call    WPP_SF_D
0x180074a26  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180074a2f  lea     rax, [rsp+58h+hKey]
0x180074a34  mov     [rsp+58h+phkResult], rax; phkResult
0x180074a39  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Workspaces\\Events"
0x180074a40  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180074a49  xor     r9d, r9d; lpClass
0x180074a4c  mov     dword ptr [rsp+58h+samDesired], 20006h; samDesired
0x180074a54  xor     r8d, r8d; Reserved
0x180074a57  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180074a5e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180074a66  call    cs:__imp_RegCreateKeyExW
0x180074a6c  mov     rcx, [rsp+58h+hKey]; hKey
0x180074a71  mov     ebx, eax
0x180074a73  test    rcx, rcx
0x180074a76  jz      short loc_180074A7E
0x180074a78  call    cs:__imp_RegCloseKey
0x180074a7e  test    ebx, ebx
0x180074a80  jz      short loc_180074AE2
0x180074a82  mov     rax, cs:WPP_GLOBAL_Control
0x180074a89  cmp     rax, rbp
0x180074a8c  jz      short loc_180074AD3
0x180074a8e  test    byte ptr [rax+1Ch], 8
0x180074a92  jz      short loc_180074AD3
0x180074a94  cmp     byte ptr [rax+19h], 2
0x180074a98  jb      short loc_180074AD3
0x180074a9a  test    ebx, ebx
0x180074a9c  jg      short loc_180074AA2
0x180074a9e  mov     edi, ebx
0x180074aa0  jmp     short loc_180074AAB
0x180074aa2  movzx   edi, bx
0x180074aa5  or      edi, 80070000h
0x180074aab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ab7  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074abe  mov     edx, 25h ; '%'
0x180074ac3  mov     [rsp+58h+dwOptions], edi
0x180074ac7  mov     r9d, eax
0x180074aca  mov     rcx, [rcx+10h]
0x180074ace  call    WPP_SF_Dd
0x180074ad3  test    ebx, ebx
0x180074ad5  jle     short loc_180074B44
0x180074ad7  movzx   ebx, bx
0x180074ada  or      ebx, 80070000h
0x180074ae0  jmp     short loc_180074B44
0x180074ae2  lea     rcx, [rdi+8]; this
0x180074ae6  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Workspaces\\Events"
0x180074aed  call    ?WatchRegKeyForUpdates@CSimpleRegistryWatcher@@IEAAJPEAUHKEY__@@PEBG@Z; CSimpleRegistryWatcher::WatchRegKeyForUpdates(HKEY__ *,ushort const *)
0x180074af2  mov     ebx, eax
0x180074af4  test    eax, eax
0x180074af6  jns     short loc_180074B44
0x180074af8  mov     rax, cs:WPP_GLOBAL_Control
0x180074aff  cmp     rax, rbp
0x180074b02  jz      short loc_180074B44
0x180074b04  test    byte ptr [rax+1Ch], 8
0x180074b08  jz      short loc_180074B44
0x180074b0a  cmp     byte ptr [rax+19h], 2
0x180074b0e  jb      short loc_180074B44
0x180074b10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074b15  lea     rcx, aFailedToSetupL; "failed to setup listner thread on regke"...
0x180074b1c  mov     dword ptr [rsp+58h+samDesired], ebx
0x180074b20  mov     qword ptr [rsp+58h+dwOptions], rcx
0x180074b25  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b33  mov     edx, 26h ; '&'
0x180074b38  mov     r9d, eax
0x180074b3b  mov     rcx, [rcx+10h]
0x180074b3f  call    WPP_SF_DsD
0x180074b44  mov     rbp, [rsp+58h+arg_10]
0x180074b49  mov     eax, ebx
0x180074b4b  mov     rbx, [rsp+58h+arg_0]
0x180074b50  add     rsp, 50h
0x180074b54  pop     rdi
0x180074b55  retn
```
