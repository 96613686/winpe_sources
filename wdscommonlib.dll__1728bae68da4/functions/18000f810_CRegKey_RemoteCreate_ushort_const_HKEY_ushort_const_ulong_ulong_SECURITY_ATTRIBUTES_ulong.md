# CRegKey::RemoteCreate(ushort const *,HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000f810`
- end: `0x18000f9f2`
- name: `?RemoteCreate@CRegKey@@QEAAKPEBGPEAUHKEY__@@0KKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `482`
- prototype: `unsigned int __fastcall(PHKEY phkResult, PCWSTR pNodeName, HKEY hKey, LPCWSTR lpSubKey, unsigned int, DWORD, LPSECURITY_ATTRIBUTES, LPDWORD)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000214c`
- `0x180003f60`
- `0x180006310`
- `0x1800074d0`
- `0x18000f810`
- `0x180021410`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f973`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f9b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f973`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f9b6`
- `ADVAPI32!RegConnectRegistryW` at `0x18000f91a`
- `ADVAPI32!RegConnectRegistryW` at `0x18000f91a`
- `ADVAPI32!RegCloseKey` at `0x18000f84d`
- `ADVAPI32!RegCloseKey` at `0x18000f9cb`
- `ADVAPI32!RegCloseKey` at `0x18000f84d`
- `ADVAPI32!RegCloseKey` at `0x18000f9cb`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f962`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f962`

## pseudocode

```c
__int64 __fastcall CRegKey::RemoteCreate(
        PHKEY phkResult,
        PCWSTR pNodeName,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned int a5,
        DWORD dwOptions,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        LPDWORD lpdwDisposition)
{
  HKEY v9; // rcx
  unsigned __int16 *v13; // rdi
  unsigned int HostName; // eax
  unsigned int Key; // ebx
  __int64 v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  unsigned __int16 *v19; // rax
  WCHAR *v20; // r14
  int v21; // eax
  HKEY phkResulta; // [rsp+50h] [rbp-10h] BYREF
  int v24; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *v25; // [rsp+A8h] [rbp+48h] BYREF

  v9 = *phkResult;
  phkResulta = 0;
  v25 = 0;
  v24 = 0;
  v13 = 0;
  if ( v9 )
  {
    RegCloseKey(v9);
    *phkResult = 0;
  }
  if ( !pNodeName )
    goto LABEL_19;
  HostName = GetHostName(ComputerNameDnsFullyQualified, &v25);
  v13 = v25;
  Key = HostName;
  if ( HostName )
    goto LABEL_20;
  Key = CNetworkAddress::AreHostsSame(v25, pNodeName, &v24);
  if ( Key )
    goto LABEL_20;
  if ( v24 )
  {
LABEL_19:
    Key = CRegKey::Create(phkResult, hKey, lpSubKey, a5, dwOptions, lpSecurityAttributes, lpdwDisposition);
    goto LABEL_20;
  }
  v16 = -1;
  do
    ++v16;
  while ( pNodeName[v16] );
  v17 = v16 + 3;
  v18 = 2 * v17;
  if ( !is_mul_ok(v17, 2u) )
    v18 = -1;
  v19 = (unsigned __int16 *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v19;
  if ( v19 )
  {
    v21 = StringCchPrintfW(v19, v17, L"\\\\%s", pNodeName);
    Key = v21;
    if ( v21 >= 0 )
    {
      Key = RegConnectRegistryW(v20, hKey, &phkResulta);
      if ( !Key )
        Key = RegCreateKeyExW(
                phkResulta,
                lpSubKey,
                0,
                0,
                dwOptions,
                a5 | 0x100,
                lpSecurityAttributes,
                phkResult,
                lpdwDisposition);
    }
    else if ( (v21 & 0x1FFF0000) == 0x70000 )
    {
      Key = (unsigned __int16)v21;
    }
    operator delete(v20);
  }
  else
  {
    Key = 8;
  }
LABEL_20:
  if ( v13 )
    operator delete(v13);
  if ( phkResulta )
    RegCloseKey(phkResulta);
  return Key;
}

```

## disassembly

```asm
0x18000f810  mov     [rsp-38h+arg_10], rbx
0x18000f815  push    rbp
0x18000f816  push    rsi
0x18000f817  push    rdi
0x18000f818  push    r12
0x18000f81a  push    r13
0x18000f81c  push    r14
0x18000f81e  push    r15
0x18000f820  mov     rbp, rsp
0x18000f823  sub     rsp, 60h
0x18000f827  xor     r14d, r14d
0x18000f82a  mov     r15, rcx
0x18000f82d  mov     rcx, [rcx]; hKey
0x18000f830  mov     r13, r9
0x18000f833  mov     [rbp+phkResult], r14
0x18000f837  mov     r12, r8
0x18000f83a  mov     [rbp+arg_8], r14
0x18000f83e  mov     rsi, rdx
0x18000f841  mov     [rbp+arg_0], r14d
0x18000f845  mov     edi, r14d
0x18000f848  test    rcx, rcx
0x18000f84b  jz      short loc_18000F85C
0x18000f84d  call    cs:__imp_RegCloseKey
0x18000f854  nop     dword ptr [rax+rax+00h]
0x18000f859  mov     [r15], r14
0x18000f85c  test    rsi, rsi
0x18000f85f  jz      loc_18000F981
0x18000f865  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x18000f869  mov     ecx, 3; NameType
0x18000f86e  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000f873  mov     rdi, [rbp+arg_8]
0x18000f877  mov     ebx, eax
0x18000f879  test    eax, eax
0x18000f87b  jnz     loc_18000F9AE
0x18000f881  lea     r8, [rbp+arg_0]; int *
0x18000f885  mov     rdx, rsi; pNodeName
0x18000f888  mov     rcx, rdi; unsigned __int16 *
0x18000f88b  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18000f890  mov     ebx, eax
0x18000f892  test    eax, eax
0x18000f894  jnz     loc_18000F9AE
0x18000f89a  cmp     [rbp+arg_0], r14d
0x18000f89e  jnz     loc_18000F981
0x18000f8a4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f8a8  mov     rbx, rcx
0x18000f8ab  inc     rbx
0x18000f8ae  cmp     [rsi+rbx*2], r14w
0x18000f8b3  jnz     short loc_18000F8AB
0x18000f8b5  add     rbx, 3
0x18000f8b9  mov     eax, 2
0x18000f8be  mul     rbx
0x18000f8c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f8c8  cmovo   rax, rcx
0x18000f8cc  mov     rcx, rax; unsigned __int64
0x18000f8cf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f8d4  mov     r14, rax
0x18000f8d7  test    rax, rax
0x18000f8da  jnz     short loc_18000F8E4
0x18000f8dc  lea     ebx, [rax+8]
0x18000f8df  jmp     loc_18000F9AE
0x18000f8e4  mov     r9, rsi
0x18000f8e7  lea     r8, aS_1; "\\\\%s"
0x18000f8ee  mov     rdx, rbx; unsigned __int64
0x18000f8f1  mov     rcx, r14; unsigned __int16 *
0x18000f8f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f8f9  mov     ebx, eax
0x18000f8fb  test    eax, eax
0x18000f8fd  jns     short loc_18000F910
0x18000f8ff  and     eax, 1FFF0000h
0x18000f904  cmp     eax, 70000h
0x18000f909  jnz     short loc_18000F970
0x18000f90b  movzx   ebx, bx
0x18000f90e  jmp     short loc_18000F970
0x18000f910  lea     r8, [rbp+phkResult]; phkResult
0x18000f914  mov     rdx, r12; hKey
0x18000f917  mov     rcx, r14; lpMachineName
0x18000f91a  call    cs:__imp_RegConnectRegistryW
0x18000f921  nop     dword ptr [rax+rax+00h]
0x18000f926  mov     ebx, eax
0x18000f928  test    eax, eax
0x18000f92a  jnz     short loc_18000F970
0x18000f92c  mov     rax, [rbp+arg_38]
0x18000f930  xor     r9d, r9d; lpClass
0x18000f933  mov     ecx, [rbp+arg_20]
0x18000f936  xor     r8d, r8d; Reserved
0x18000f939  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000f93e  bts     ecx, 8
0x18000f942  mov     rax, [rbp+arg_30]
0x18000f946  mov     rdx, r13; lpSubKey
0x18000f949  mov     [rsp+60h+var_28], r15; phkResult
0x18000f94e  mov     [rsp+60h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000f953  mov     eax, [rbp+arg_28]
0x18000f956  mov     [rsp+60h+samDesired], ecx; samDesired
0x18000f95a  mov     rcx, [rbp+phkResult]; hKey
0x18000f95e  mov     [rsp+60h+dwOptions], eax; dwOptions
0x18000f962  call    cs:__imp_RegCreateKeyExW
0x18000f969  nop     dword ptr [rax+rax+00h]
0x18000f96e  mov     ebx, eax
0x18000f970  mov     rcx, r14
0x18000f973  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f97a  nop     dword ptr [rax+rax+00h]
0x18000f97f  jmp     short loc_18000F9AE
0x18000f981  mov     rax, [rbp+arg_38]
0x18000f985  mov     r8, r13; lpSubKey
0x18000f988  mov     r9d, [rbp+arg_20]; unsigned int
0x18000f98c  mov     rdx, r12; hKey
0x18000f98f  mov     [rsp+60h+lpSecurityAttributes], rax; unsigned int *
0x18000f994  mov     rcx, r15; phkResult
0x18000f997  mov     rax, [rbp+arg_30]
0x18000f99b  mov     qword ptr [rsp+60h+samDesired], rax; LPSECURITY_ATTRIBUTES
0x18000f9a0  mov     eax, [rbp+arg_28]
0x18000f9a3  mov     [rsp+60h+dwOptions], eax; DWORD
0x18000f9a7  call    ?Create@CRegKey@@QEAAKPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CRegKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000f9ac  mov     ebx, eax
0x18000f9ae  test    rdi, rdi
0x18000f9b1  jz      short loc_18000F9C2
0x18000f9b3  mov     rcx, rdi
0x18000f9b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f9bd  nop     dword ptr [rax+rax+00h]
0x18000f9c2  mov     rcx, [rbp+phkResult]; hKey
0x18000f9c6  test    rcx, rcx
0x18000f9c9  jz      short loc_18000F9D7
0x18000f9cb  call    cs:__imp_RegCloseKey
0x18000f9d2  nop     dword ptr [rax+rax+00h]
0x18000f9d7  mov     eax, ebx
0x18000f9d9  mov     rbx, [rsp+60h+arg_10]
0x18000f9e1  add     rsp, 60h
0x18000f9e5  pop     r15
0x18000f9e7  pop     r14
0x18000f9e9  pop     r13
0x18000f9eb  pop     r12
0x18000f9ed  pop     rdi
0x18000f9ee  pop     rsi
0x18000f9ef  pop     rbp
0x18000f9f0  retn
```
