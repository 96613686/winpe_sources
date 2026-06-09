# CRegKey::RemoteCreate(ushort const *,HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000ec80`
- end: `0x18000ee54`
- name: `?RemoteCreate@CRegKey@@QEAAKPEBGPEAUHKEY__@@0KKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `468`
- prototype: `unsigned int __fastcall(PHKEY phkResult, PCWSTR pNodeName, HKEY hKey, LPCWSTR lpSubKey, unsigned int, DWORD, LPSECURITY_ATTRIBUTES, LPDWORD)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000179c`
- `0x1800034c0`
- `0x180005830`
- `0x1800069c0`
- `0x18000ec80`
- `0x180020400`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x18000ed8a`
- `ADVAPI32!RegConnectRegistryW` at `0x18000ed8a`
- `ADVAPI32!RegCloseKey` at `0x18000ecbd`
- `ADVAPI32!RegCloseKey` at `0x18000ee2d`
- `ADVAPI32!RegCloseKey` at `0x18000ecbd`
- `ADVAPI32!RegCloseKey` at `0x18000ee2d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000edd2`
- `ADVAPI32!RegCreateKeyExW` at `0x18000edd2`

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
  void *v13; // rdi
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
  void *lpMem; // [rsp+A8h] [rbp+48h] BYREF

  v9 = *phkResult;
  phkResulta = 0;
  lpMem = 0;
  v24 = 0;
  v13 = 0;
  if ( v9 )
  {
    RegCloseKey(v9);
    *phkResult = 0;
  }
  if ( !pNodeName )
    goto LABEL_19;
  HostName = GetHostName(ComputerNameDnsFullyQualified, (unsigned __int16 **)&lpMem);
  v13 = lpMem;
  Key = HostName;
  if ( HostName )
    goto LABEL_20;
  Key = CNetworkAddress::AreHostsSame((const unsigned __int16 *)lpMem, pNodeName, &v24);
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
0x18000ec80  mov     [rsp-38h+arg_10], rbx
0x18000ec85  push    rbp
0x18000ec86  push    rsi
0x18000ec87  push    rdi
0x18000ec88  push    r12
0x18000ec8a  push    r13
0x18000ec8c  push    r14
0x18000ec8e  push    r15
0x18000ec90  mov     rbp, rsp
0x18000ec93  sub     rsp, 60h
0x18000ec97  xor     r14d, r14d
0x18000ec9a  mov     r15, rcx
0x18000ec9d  mov     rcx, [rcx]; hKey
0x18000eca0  mov     r13, r9
0x18000eca3  mov     [rbp+phkResult], r14
0x18000eca7  mov     r12, r8
0x18000ecaa  mov     [rbp+lpMem], r14
0x18000ecae  mov     rsi, rdx
0x18000ecb1  mov     [rbp+arg_0], r14d
0x18000ecb5  mov     edi, r14d
0x18000ecb8  test    rcx, rcx
0x18000ecbb  jz      short loc_18000ECCC
0x18000ecbd  call    cs:__imp_RegCloseKey
0x18000ecc4  nop     dword ptr [rax+rax+00h]
0x18000ecc9  mov     [r15], r14
0x18000eccc  test    rsi, rsi
0x18000eccf  jz      loc_18000EDEA
0x18000ecd5  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x18000ecd9  mov     ecx, 3; NameType
0x18000ecde  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000ece3  mov     rdi, [rbp+lpMem]
0x18000ece7  mov     ebx, eax
0x18000ece9  test    eax, eax
0x18000eceb  jnz     loc_18000EE17
0x18000ecf1  lea     r8, [rbp+arg_0]; int *
0x18000ecf5  mov     rdx, rsi; pNodeName
0x18000ecf8  mov     rcx, rdi; unsigned __int16 *
0x18000ecfb  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18000ed00  mov     ebx, eax
0x18000ed02  test    eax, eax
0x18000ed04  jnz     loc_18000EE17
0x18000ed0a  cmp     [rbp+arg_0], r14d
0x18000ed0e  jnz     loc_18000EDEA
0x18000ed14  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ed18  mov     rbx, rcx
0x18000ed1b  inc     rbx
0x18000ed1e  cmp     [rsi+rbx*2], r14w
0x18000ed23  jnz     short loc_18000ED1B
0x18000ed25  add     rbx, 3
0x18000ed29  mov     eax, 2
0x18000ed2e  mul     rbx
0x18000ed31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ed38  cmovo   rax, rcx
0x18000ed3c  mov     rcx, rax; unsigned __int64
0x18000ed3f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ed44  mov     r14, rax
0x18000ed47  test    rax, rax
0x18000ed4a  jnz     short loc_18000ED54
0x18000ed4c  lea     ebx, [rax+8]
0x18000ed4f  jmp     loc_18000EE17
0x18000ed54  mov     r9, rsi
0x18000ed57  lea     r8, aS_1; "\\\\%s"
0x18000ed5e  mov     rdx, rbx; unsigned __int64
0x18000ed61  mov     rcx, r14; unsigned __int16 *
0x18000ed64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ed69  mov     ebx, eax
0x18000ed6b  test    eax, eax
0x18000ed6d  jns     short loc_18000ED80
0x18000ed6f  and     eax, 1FFF0000h
0x18000ed74  cmp     eax, 70000h
0x18000ed79  jnz     short loc_18000EDE0
0x18000ed7b  movzx   ebx, bx
0x18000ed7e  jmp     short loc_18000EDE0
0x18000ed80  lea     r8, [rbp+phkResult]; phkResult
0x18000ed84  mov     rdx, r12; hKey
0x18000ed87  mov     rcx, r14; lpMachineName
0x18000ed8a  call    cs:__imp_RegConnectRegistryW
0x18000ed91  nop     dword ptr [rax+rax+00h]
0x18000ed96  mov     ebx, eax
0x18000ed98  test    eax, eax
0x18000ed9a  jnz     short loc_18000EDE0
0x18000ed9c  mov     rax, [rbp+arg_38]
0x18000eda0  xor     r9d, r9d; lpClass
0x18000eda3  mov     ecx, [rbp+arg_20]
0x18000eda6  xor     r8d, r8d; Reserved
0x18000eda9  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000edae  bts     ecx, 8
0x18000edb2  mov     rax, [rbp+arg_30]
0x18000edb6  mov     rdx, r13; lpSubKey
0x18000edb9  mov     [rsp+60h+var_28], r15; phkResult
0x18000edbe  mov     [rsp+60h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000edc3  mov     eax, [rbp+arg_28]
0x18000edc6  mov     [rsp+60h+samDesired], ecx; samDesired
0x18000edca  mov     rcx, [rbp+phkResult]; hKey
0x18000edce  mov     [rsp+60h+dwOptions], eax; dwOptions
0x18000edd2  call    cs:__imp_RegCreateKeyExW
0x18000edd9  nop     dword ptr [rax+rax+00h]
0x18000edde  mov     ebx, eax
0x18000ede0  mov     rcx, r14; lpMem
0x18000ede3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ede8  jmp     short loc_18000EE17
0x18000edea  mov     rax, [rbp+arg_38]
0x18000edee  mov     r8, r13; lpSubKey
0x18000edf1  mov     r9d, [rbp+arg_20]; unsigned int
0x18000edf5  mov     rdx, r12; hKey
0x18000edf8  mov     [rsp+60h+lpSecurityAttributes], rax; unsigned int *
0x18000edfd  mov     rcx, r15; phkResult
0x18000ee00  mov     rax, [rbp+arg_30]
0x18000ee04  mov     qword ptr [rsp+60h+samDesired], rax; LPSECURITY_ATTRIBUTES
0x18000ee09  mov     eax, [rbp+arg_28]
0x18000ee0c  mov     [rsp+60h+dwOptions], eax; DWORD
0x18000ee10  call    ?Create@CRegKey@@QEAAKPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CRegKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000ee15  mov     ebx, eax
0x18000ee17  test    rdi, rdi
0x18000ee1a  jz      short loc_18000EE24
0x18000ee1c  mov     rcx, rdi; lpMem
0x18000ee1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ee24  mov     rcx, [rbp+phkResult]; hKey
0x18000ee28  test    rcx, rcx
0x18000ee2b  jz      short loc_18000EE39
0x18000ee2d  call    cs:__imp_RegCloseKey
0x18000ee34  nop     dword ptr [rax+rax+00h]
0x18000ee39  mov     eax, ebx
0x18000ee3b  mov     rbx, [rsp+60h+arg_10]
0x18000ee43  add     rsp, 60h
0x18000ee47  pop     r15
0x18000ee49  pop     r14
0x18000ee4b  pop     r13
0x18000ee4d  pop     r12
0x18000ee4f  pop     rdi
0x18000ee50  pop     rsi
0x18000ee51  pop     rbp
0x18000ee52  retn
```
