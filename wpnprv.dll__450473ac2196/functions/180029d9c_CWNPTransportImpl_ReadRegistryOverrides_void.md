# CWNPTransportImpl::ReadRegistryOverrides(void)

- ea: `0x180029d9c`
- end: `0x180029ef6`
- name: `?ReadRegistryOverrides@CWNPTransportImpl@@AEAAXXZ`
- size: `346`
- prototype: `void __fastcall(CWNPTransportImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800209a0`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x180029d9c`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029e75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029e75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180029e0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180029e0f`

## pseudocode

```c
void __fastcall CWNPTransportImpl::ReadRegistryOverrides(CWNPTransportImpl *this)
{
  int v2; // eax
  PVOID *v3; // rcx
  unsigned int v4; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids);
  }
  hKey = 0;
  v4 = 0;
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( !v2 )
  {
    if ( (int)WpnRegLoadDWord(hKey, L"EnableInterfaceSelection", &v4) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids);
      }
    }
    else
    {
      *((_BYTE *)this + 352) = v4 != 0;
    }
    RegCloseKey(hKey);
LABEL_19:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
      (unsigned int)v2);
    goto LABEL_19;
  }
LABEL_20:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 && *((_BYTE *)v3 + 25) >= 6u )
    WPP_SF_d(v3[2], 19, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids, v4);
}

```

## disassembly

```asm
0x180029d9c  mov     [rsp+arg_0], rbx
0x180029da1  push    rbp
0x180029da2  sub     rsp, 30h
0x180029da6  mov     rbx, rcx
0x180029da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029db0  lea     rbp, WPP_GLOBAL_Control
0x180029db7  cmp     rcx, rbp
0x180029dba  jz      short loc_180029DDD
0x180029dbc  test    byte ptr [rcx+1Ch], 4
0x180029dc0  jz      short loc_180029DDD
0x180029dc2  cmp     byte ptr [rcx+19h], 6
0x180029dc6  jb      short loc_180029DDD
0x180029dc8  mov     rcx, [rcx+10h]
0x180029dcc  lea     r8, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x180029dd3  mov     edx, 10h
0x180029dd8  call    WPP_SF_
0x180029ddd  lea     rax, [rsp+38h+hKey]
0x180029de2  mov     [rsp+38h+hKey], 0
0x180029deb  mov     r9d, 1; samDesired
0x180029df1  mov     [rsp+38h+phkResult], rax; phkResult
0x180029df6  xor     r8d, r8d; ulOptions
0x180029df9  mov     [rsp+38h+arg_8], 0
0x180029e01  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180029e08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029e0f  call    cs:__imp_RegOpenKeyExA
0x180029e15  test    eax, eax
0x180029e17  jnz     short loc_180029E7D
0x180029e19  mov     rcx, [rsp+38h+hKey]; hKey
0x180029e1e  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180029e23  lea     rdx, ?g_cszEnableInterfaceSelection@@3QBGB; "EnableInterfaceSelection"
0x180029e2a  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x180029e2f  test    eax, eax
0x180029e31  js      short loc_180029E43
0x180029e33  cmp     [rsp+38h+arg_8], 0
0x180029e38  setnz   al
0x180029e3b  mov     [rbx+160h], al
0x180029e41  jmp     short loc_180029E70
0x180029e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e4a  cmp     rcx, rbp
0x180029e4d  jz      short loc_180029E70
0x180029e4f  test    byte ptr [rcx+1Ch], 4
0x180029e53  jz      short loc_180029E70
0x180029e55  cmp     byte ptr [rcx+19h], 3
0x180029e59  jb      short loc_180029E70
0x180029e5b  mov     rcx, [rcx+10h]
0x180029e5f  lea     r8, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x180029e66  mov     edx, 11h
0x180029e6b  call    WPP_SF_
0x180029e70  mov     rcx, [rsp+38h+hKey]; hKey
0x180029e75  call    cs:__imp_RegCloseKey
0x180029e7b  jmp     short loc_180029EB9
0x180029e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e84  cmp     rcx, rbp
0x180029e87  jz      short loc_180029EEB
0x180029e89  test    byte ptr [rcx+1Ch], 4
0x180029e8d  jz      short loc_180029EC0
0x180029e8f  cmp     byte ptr [rcx+19h], 2
0x180029e93  jb      short loc_180029EC0
0x180029e95  test    eax, eax
0x180029e97  jle     short loc_180029EA1
0x180029e99  movzx   eax, ax
0x180029e9c  or      eax, 80070000h
0x180029ea1  mov     rcx, [rcx+10h]
0x180029ea5  lea     r8, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x180029eac  mov     edx, 12h
0x180029eb1  mov     r9d, eax
0x180029eb4  call    WPP_SF_d
0x180029eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ec0  cmp     rcx, rbp
0x180029ec3  jz      short loc_180029EEB
0x180029ec5  test    byte ptr [rcx+1Ch], 4
0x180029ec9  jz      short loc_180029EEB
0x180029ecb  cmp     byte ptr [rcx+19h], 6
0x180029ecf  jb      short loc_180029EEB
0x180029ed1  mov     r9d, [rsp+38h+arg_8]
0x180029ed6  lea     r8, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x180029edd  mov     rcx, [rcx+10h]
0x180029ee1  mov     edx, 13h
0x180029ee6  call    WPP_SF_d
0x180029eeb  mov     rbx, [rsp+38h+arg_0]
0x180029ef0  add     rsp, 30h
0x180029ef4  pop     rbp
0x180029ef5  retn
```
