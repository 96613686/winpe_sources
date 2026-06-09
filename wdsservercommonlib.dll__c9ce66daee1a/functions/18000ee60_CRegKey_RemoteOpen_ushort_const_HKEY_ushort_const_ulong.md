# CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)

- ea: `0x18000ee60`
- end: `0x18000f072`
- name: `?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z`
- size: `530`
- prototype: `unsigned int __fastcall(PHKEY phkResult, PCWSTR pNodeName, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fb90`
- `0x18000fff0`
- `0x180024250`
- `0x1800246f0`

## callees

- `0x18000179c`
- `0x180005830`
- `0x1800069c0`
- `0x18000ee60`
- `0x180020400`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x18000efe9`
- `ADVAPI32!RegConnectRegistryW` at `0x18000efe9`
- `ADVAPI32!RegCloseKey` at `0x18000ee9b`
- `ADVAPI32!RegCloseKey` at `0x18000eeb7`
- `ADVAPI32!RegCloseKey` at `0x18000ef38`
- `ADVAPI32!RegCloseKey` at `0x18000f049`
- `ADVAPI32!RegCloseKey` at `0x18000ee9b`
- `ADVAPI32!RegCloseKey` at `0x18000eeb7`
- `ADVAPI32!RegCloseKey` at `0x18000ef38`
- `ADVAPI32!RegCloseKey` at `0x18000f049`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eee1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef62`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f018`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eee1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef62`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f018`

## pseudocode

```c
__int64 __fastcall CRegKey::RemoteOpen(PHKEY phkResult, PCWSTR pNodeName, HKEY hKey, LPCWSTR lpSubKey, unsigned int a5)
{
  HKEY v6; // rcx
  unsigned int HostName; // ebx
  __int64 v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  WCHAR *v15; // r14
  int v16; // eax
  HKEY hKeya; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+70h] [rbp+8h] BYREF
  void *lpMem; // [rsp+78h] [rbp+10h] BYREF

  v6 = *phkResult;
  lpMem = 0;
  v19 = 0;
  hKeya = 0;
  if ( v6 )
  {
    RegCloseKey(v6);
    *phkResult = 0;
  }
  if ( pNodeName )
  {
    HostName = GetHostName(ComputerNameDnsFullyQualified, (unsigned __int16 **)&lpMem);
    if ( !HostName )
    {
      HostName = CNetworkAddress::AreHostsSame((const unsigned __int16 *)lpMem, pNodeName, &v19);
      if ( !HostName )
      {
        if ( v19 )
        {
          if ( *phkResult )
          {
            RegCloseKey(*phkResult);
            *phkResult = 0;
          }
          HostName = RegOpenKeyExW(hKey, lpSubKey, 0, a5 | 0x100, phkResult);
        }
        else
        {
          v11 = -1;
          do
            ++v11;
          while ( pNodeName[v11] );
          v12 = v11 + 3;
          v13 = 2 * v12;
          if ( !is_mul_ok(v12, 2u) )
            v13 = -1;
          v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
          v15 = v14;
          if ( v14 )
          {
            v16 = StringCchPrintfW(v14, v12, L"\\\\%s", pNodeName);
            HostName = v16;
            if ( v16 >= 0 )
            {
              HostName = RegConnectRegistryW(v15, hKey, &hKeya);
              if ( !HostName )
                HostName = RegOpenKeyExW(hKeya, lpSubKey, 0, a5 | 0x100, phkResult);
            }
            else if ( (v16 & 0x1FFF0000) == 0x70000 )
            {
              HostName = (unsigned __int16)v16;
            }
            operator delete(v15);
          }
          else
          {
            HostName = 8;
          }
        }
      }
    }
    if ( lpMem )
      operator delete(lpMem);
  }
  else
  {
    HostName = RegOpenKeyExW(hKey, lpSubKey, 0, a5 | 0x100, phkResult);
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return HostName;
}

```

## disassembly

```asm
0x18000ee60  mov     rax, rsp
0x18000ee63  mov     [rax+18h], rbx
0x18000ee67  mov     [rax+20h], rsi
0x18000ee6b  push    rdi
0x18000ee6c  push    r12
0x18000ee6e  push    r13
0x18000ee70  push    r14
0x18000ee72  push    r15
0x18000ee74  sub     rsp, 40h
0x18000ee78  xor     r13d, r13d
0x18000ee7b  mov     rdi, rcx
0x18000ee7e  mov     rcx, [rcx]; hKey
0x18000ee81  mov     r12, r9
0x18000ee84  mov     [rax+10h], r13
0x18000ee88  mov     r15, r8
0x18000ee8b  mov     [rax+8], r13d
0x18000ee8f  mov     rsi, rdx
0x18000ee92  mov     [rax-38h], r13
0x18000ee96  test    rcx, rcx
0x18000ee99  jz      short loc_18000EEAD
0x18000ee9b  call    cs:__imp_RegCloseKey
0x18000eea2  nop     dword ptr [rax+rax+00h]
0x18000eea7  mov     ecx, r13d; hKey
0x18000eeaa  mov     [rdi], r13
0x18000eead  test    rsi, rsi
0x18000eeb0  jnz     short loc_18000EEF4
0x18000eeb2  test    rcx, rcx
0x18000eeb5  jz      short loc_18000EEC6
0x18000eeb7  call    cs:__imp_RegCloseKey
0x18000eebe  nop     dword ptr [rax+rax+00h]
0x18000eec3  mov     [rdi], r13
0x18000eec6  mov     r9d, [rsp+68h+arg_20]
0x18000eece  xor     r8d, r8d; ulOptions
0x18000eed1  bts     r9d, 8; samDesired
0x18000eed6  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000eedb  mov     rdx, r12; lpSubKey
0x18000eede  mov     rcx, r15; hKey
0x18000eee1  call    cs:__imp_RegOpenKeyExW
0x18000eee8  nop     dword ptr [rax+rax+00h]
0x18000eeed  mov     ebx, eax
0x18000eeef  jmp     loc_18000F03F
0x18000eef4  lea     rdx, [rsp+68h+lpMem]; unsigned __int16 **
0x18000eef9  mov     ecx, 3; NameType
0x18000eefe  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000ef03  mov     ebx, eax
0x18000ef05  test    eax, eax
0x18000ef07  jnz     loc_18000F02E
0x18000ef0d  mov     rcx, [rsp+68h+lpMem]; unsigned __int16 *
0x18000ef12  lea     r8, [rsp+68h+arg_0]; int *
0x18000ef17  mov     rdx, rsi; pNodeName
0x18000ef1a  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18000ef1f  mov     ebx, eax
0x18000ef21  test    eax, eax
0x18000ef23  jnz     loc_18000F02E
0x18000ef29  cmp     [rsp+68h+arg_0], r13d
0x18000ef2e  jz      short loc_18000EF75
0x18000ef30  mov     rcx, [rdi]; hKey
0x18000ef33  test    rcx, rcx
0x18000ef36  jz      short loc_18000EF47
0x18000ef38  call    cs:__imp_RegCloseKey
0x18000ef3f  nop     dword ptr [rax+rax+00h]
0x18000ef44  mov     [rdi], r13
0x18000ef47  mov     r9d, [rsp+68h+arg_20]
0x18000ef4f  xor     r8d, r8d; ulOptions
0x18000ef52  bts     r9d, 8; samDesired
0x18000ef57  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000ef5c  mov     rdx, r12; lpSubKey
0x18000ef5f  mov     rcx, r15; hKey
0x18000ef62  call    cs:__imp_RegOpenKeyExW
0x18000ef69  nop     dword ptr [rax+rax+00h]
0x18000ef6e  mov     ebx, eax
0x18000ef70  jmp     loc_18000F02E
0x18000ef75  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ef79  mov     rbx, rcx
0x18000ef7c  inc     rbx
0x18000ef7f  cmp     [rsi+rbx*2], r13w
0x18000ef84  jnz     short loc_18000EF7C
0x18000ef86  add     rbx, 3
0x18000ef8a  mov     eax, 2
0x18000ef8f  mul     rbx
0x18000ef92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ef99  cmovo   rax, rcx
0x18000ef9d  mov     rcx, rax; unsigned __int64
0x18000efa0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000efa5  mov     r14, rax
0x18000efa8  test    rax, rax
0x18000efab  jnz     short loc_18000EFB2
0x18000efad  lea     ebx, [rax+8]
0x18000efb0  jmp     short loc_18000F02E
0x18000efb2  mov     r9, rsi
0x18000efb5  lea     r8, aS_1; "\\\\%s"
0x18000efbc  mov     rdx, rbx; unsigned __int64
0x18000efbf  mov     rcx, r14; unsigned __int16 *
0x18000efc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000efc7  mov     ebx, eax
0x18000efc9  test    eax, eax
0x18000efcb  jns     short loc_18000EFDE
0x18000efcd  and     eax, 1FFF0000h
0x18000efd2  cmp     eax, 70000h
0x18000efd7  jnz     short loc_18000F026
0x18000efd9  movzx   ebx, bx
0x18000efdc  jmp     short loc_18000F026
0x18000efde  lea     r8, [rsp+68h+hKey]; phkResult
0x18000efe3  mov     rdx, r15; hKey
0x18000efe6  mov     rcx, r14; lpMachineName
0x18000efe9  call    cs:__imp_RegConnectRegistryW
0x18000eff0  nop     dword ptr [rax+rax+00h]
0x18000eff5  mov     ebx, eax
0x18000eff7  test    eax, eax
0x18000eff9  jnz     short loc_18000F026
0x18000effb  mov     r9d, [rsp+68h+arg_20]
0x18000f003  xor     r8d, r8d; ulOptions
0x18000f006  mov     rcx, [rsp+68h+hKey]; hKey
0x18000f00b  bts     r9d, 8; samDesired
0x18000f010  mov     rdx, r12; lpSubKey
0x18000f013  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000f018  call    cs:__imp_RegOpenKeyExW
0x18000f01f  nop     dword ptr [rax+rax+00h]
0x18000f024  mov     ebx, eax
0x18000f026  mov     rcx, r14; lpMem
0x18000f029  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f02e  cmp     [rsp+68h+lpMem], r13
0x18000f033  jz      short loc_18000F03F
0x18000f035  mov     rcx, [rsp+68h+lpMem]; lpMem
0x18000f03a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f03f  mov     rcx, [rsp+68h+hKey]; hKey
0x18000f044  test    rcx, rcx
0x18000f047  jz      short loc_18000F055
0x18000f049  call    cs:__imp_RegCloseKey
0x18000f050  nop     dword ptr [rax+rax+00h]
0x18000f055  lea     r11, [rsp+68h+var_28]
0x18000f05a  mov     eax, ebx
0x18000f05c  mov     rbx, [r11+40h]
0x18000f060  mov     rsi, [r11+48h]
0x18000f064  mov     rsp, r11
0x18000f067  pop     r15
0x18000f069  pop     r14
0x18000f06b  pop     r13
0x18000f06d  pop     r12
0x18000f06f  pop     rdi
0x18000f070  retn
```
