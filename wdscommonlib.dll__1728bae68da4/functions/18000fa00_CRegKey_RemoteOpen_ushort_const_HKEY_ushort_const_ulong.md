# CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)

- ea: `0x18000fa00`
- end: `0x18000fc23`
- name: `?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z`
- size: `547`
- prototype: `unsigned int __fastcall(PHKEY phkResult, PCWSTR pNodeName, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010750`
- `0x180010bb0`
- `0x180025320`
- `0x1800257c0`

## callees

- `0x18000214c`
- `0x180006310`
- `0x1800074d0`
- `0x18000fa00`
- `0x180021410`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbe4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbe4`
- `ADVAPI32!RegConnectRegistryW` at `0x18000fb8c`
- `ADVAPI32!RegConnectRegistryW` at `0x18000fb8c`
- `ADVAPI32!RegCloseKey` at `0x18000fa3b`
- `ADVAPI32!RegCloseKey` at `0x18000fa57`
- `ADVAPI32!RegCloseKey` at `0x18000fad8`
- `ADVAPI32!RegCloseKey` at `0x18000fbfa`
- `ADVAPI32!RegCloseKey` at `0x18000fa3b`
- `ADVAPI32!RegCloseKey` at `0x18000fa57`
- `ADVAPI32!RegCloseKey` at `0x18000fad8`
- `ADVAPI32!RegCloseKey` at `0x18000fbfa`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa81`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fb02`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fbbb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa81`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fb02`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fbbb`

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
  unsigned __int16 *v20; // [rsp+78h] [rbp+10h] BYREF

  v6 = *phkResult;
  v20 = 0;
  v19 = 0;
  hKeya = 0;
  if ( v6 )
  {
    RegCloseKey(v6);
    *phkResult = 0;
  }
  if ( pNodeName )
  {
    HostName = GetHostName(ComputerNameDnsFullyQualified, &v20);
    if ( !HostName )
    {
      HostName = CNetworkAddress::AreHostsSame(v20, pNodeName, &v19);
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
    if ( v20 )
      operator delete(v20);
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
0x18000fa00  mov     rax, rsp
0x18000fa03  mov     [rax+18h], rbx
0x18000fa07  mov     [rax+20h], rsi
0x18000fa0b  push    rdi
0x18000fa0c  push    r12
0x18000fa0e  push    r13
0x18000fa10  push    r14
0x18000fa12  push    r15
0x18000fa14  sub     rsp, 40h
0x18000fa18  xor     r13d, r13d
0x18000fa1b  mov     rdi, rcx
0x18000fa1e  mov     rcx, [rcx]; hKey
0x18000fa21  mov     r12, r9
0x18000fa24  mov     [rax+10h], r13
0x18000fa28  mov     r15, r8
0x18000fa2b  mov     [rax+8], r13d
0x18000fa2f  mov     rsi, rdx
0x18000fa32  mov     [rax-38h], r13
0x18000fa36  test    rcx, rcx
0x18000fa39  jz      short loc_18000FA4D
0x18000fa3b  call    cs:__imp_RegCloseKey
0x18000fa42  nop     dword ptr [rax+rax+00h]
0x18000fa47  mov     ecx, r13d; hKey
0x18000fa4a  mov     [rdi], r13
0x18000fa4d  test    rsi, rsi
0x18000fa50  jnz     short loc_18000FA94
0x18000fa52  test    rcx, rcx
0x18000fa55  jz      short loc_18000FA66
0x18000fa57  call    cs:__imp_RegCloseKey
0x18000fa5e  nop     dword ptr [rax+rax+00h]
0x18000fa63  mov     [rdi], r13
0x18000fa66  mov     r9d, [rsp+68h+arg_20]
0x18000fa6e  xor     r8d, r8d; ulOptions
0x18000fa71  bts     r9d, 8; samDesired
0x18000fa76  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000fa7b  mov     rdx, r12; lpSubKey
0x18000fa7e  mov     rcx, r15; hKey
0x18000fa81  call    cs:__imp_RegOpenKeyExW
0x18000fa88  nop     dword ptr [rax+rax+00h]
0x18000fa8d  mov     ebx, eax
0x18000fa8f  jmp     loc_18000FBF0
0x18000fa94  lea     rdx, [rsp+68h+arg_8]; unsigned __int16 **
0x18000fa99  mov     ecx, 3; NameType
0x18000fa9e  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000faa3  mov     ebx, eax
0x18000faa5  test    eax, eax
0x18000faa7  jnz     loc_18000FBD8
0x18000faad  mov     rcx, [rsp+68h+arg_8]; unsigned __int16 *
0x18000fab2  lea     r8, [rsp+68h+arg_0]; int *
0x18000fab7  mov     rdx, rsi; pNodeName
0x18000faba  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18000fabf  mov     ebx, eax
0x18000fac1  test    eax, eax
0x18000fac3  jnz     loc_18000FBD8
0x18000fac9  cmp     [rsp+68h+arg_0], r13d
0x18000face  jz      short loc_18000FB15
0x18000fad0  mov     rcx, [rdi]; hKey
0x18000fad3  test    rcx, rcx
0x18000fad6  jz      short loc_18000FAE7
0x18000fad8  call    cs:__imp_RegCloseKey
0x18000fadf  nop     dword ptr [rax+rax+00h]
0x18000fae4  mov     [rdi], r13
0x18000fae7  mov     r9d, [rsp+68h+arg_20]
0x18000faef  xor     r8d, r8d; ulOptions
0x18000faf2  bts     r9d, 8; samDesired
0x18000faf7  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000fafc  mov     rdx, r12; lpSubKey
0x18000faff  mov     rcx, r15; hKey
0x18000fb02  call    cs:__imp_RegOpenKeyExW
0x18000fb09  nop     dword ptr [rax+rax+00h]
0x18000fb0e  mov     ebx, eax
0x18000fb10  jmp     loc_18000FBD8
0x18000fb15  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fb19  mov     rbx, rcx
0x18000fb1c  inc     rbx
0x18000fb1f  cmp     [rsi+rbx*2], r13w
0x18000fb24  jnz     short loc_18000FB1C
0x18000fb26  add     rbx, 3
0x18000fb2a  mov     eax, 2
0x18000fb2f  mul     rbx
0x18000fb32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fb39  cmovo   rax, rcx
0x18000fb3d  mov     rcx, rax; unsigned __int64
0x18000fb40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fb45  mov     r14, rax
0x18000fb48  test    rax, rax
0x18000fb4b  jnz     short loc_18000FB55
0x18000fb4d  lea     ebx, [rax+8]
0x18000fb50  jmp     loc_18000FBD8
0x18000fb55  mov     r9, rsi
0x18000fb58  lea     r8, aS_1; "\\\\%s"
0x18000fb5f  mov     rdx, rbx; unsigned __int64
0x18000fb62  mov     rcx, r14; unsigned __int16 *
0x18000fb65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fb6a  mov     ebx, eax
0x18000fb6c  test    eax, eax
0x18000fb6e  jns     short loc_18000FB81
0x18000fb70  and     eax, 1FFF0000h
0x18000fb75  cmp     eax, 70000h
0x18000fb7a  jnz     short loc_18000FBC9
0x18000fb7c  movzx   ebx, bx
0x18000fb7f  jmp     short loc_18000FBC9
0x18000fb81  lea     r8, [rsp+68h+hKey]; phkResult
0x18000fb86  mov     rdx, r15; hKey
0x18000fb89  mov     rcx, r14; lpMachineName
0x18000fb8c  call    cs:__imp_RegConnectRegistryW
0x18000fb93  nop     dword ptr [rax+rax+00h]
0x18000fb98  mov     ebx, eax
0x18000fb9a  test    eax, eax
0x18000fb9c  jnz     short loc_18000FBC9
0x18000fb9e  mov     r9d, [rsp+68h+arg_20]
0x18000fba6  xor     r8d, r8d; ulOptions
0x18000fba9  mov     rcx, [rsp+68h+hKey]; hKey
0x18000fbae  bts     r9d, 8; samDesired
0x18000fbb3  mov     rdx, r12; lpSubKey
0x18000fbb6  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000fbbb  call    cs:__imp_RegOpenKeyExW
0x18000fbc2  nop     dword ptr [rax+rax+00h]
0x18000fbc7  mov     ebx, eax
0x18000fbc9  mov     rcx, r14
0x18000fbcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fbd3  nop     dword ptr [rax+rax+00h]
0x18000fbd8  cmp     [rsp+68h+arg_8], r13
0x18000fbdd  jz      short loc_18000FBF0
0x18000fbdf  mov     rcx, [rsp+68h+arg_8]
0x18000fbe4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fbeb  nop     dword ptr [rax+rax+00h]
0x18000fbf0  mov     rcx, [rsp+68h+hKey]; hKey
0x18000fbf5  test    rcx, rcx
0x18000fbf8  jz      short loc_18000FC06
0x18000fbfa  call    cs:__imp_RegCloseKey
0x18000fc01  nop     dword ptr [rax+rax+00h]
0x18000fc06  lea     r11, [rsp+68h+var_28]
0x18000fc0b  mov     eax, ebx
0x18000fc0d  mov     rbx, [r11+40h]
0x18000fc11  mov     rsi, [r11+48h]
0x18000fc15  mov     rsp, r11
0x18000fc18  pop     r15
0x18000fc1a  pop     r14
0x18000fc1c  pop     r13
0x18000fc1e  pop     r12
0x18000fc20  pop     rdi
0x18000fc21  retn
```
