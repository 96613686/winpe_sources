# HVSOCKET_BuildAddressVector(NETWORK_ADDRESS_VECTOR * *)

- ea: `0x1800c567c`
- end: `0x1800c57af`
- name: `?HVSOCKET_BuildAddressVector@@YAJPEAPEAUNETWORK_ADDRESS_VECTOR@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct NETWORK_ADDRESS_VECTOR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c5900`

## callees

- `0x1800122f0`
- `0x18002c13c`
- `0x1800c567c`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x1800c5766`
- `ntdll!RtlGUIDFromString` at `0x1800c5766`
- `ntdll!RtlInitUnicodeString` at `0x1800c5758`
- `ntdll!RtlInitUnicodeString` at `0x1800c5758`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5701`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5780`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5739`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5739`

## pseudocode

```c
__int64 __fastcall HVSOCKET_BuildAddressVector(struct NETWORK_ADDRESS_VECTOR **a1)
{
  char *v2; // rax
  struct NETWORK_ADDRESS_VECTOR *v3; // rbx
  __int64 result; // rax
  unsigned __int16 *v5; // rsi
  DWORD Type; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-55h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  GUID Guid; // [rsp+50h] [rbp-39h] BYREF
  WCHAR Data[40]; // [rsp+60h] [rbp-29h] BYREF

  hKey = 0;
  Guid = 0;
  v2 = (char *)I_RpcAllocate(0x5Au);
  v3 = (struct NETWORK_ADDRESS_VECTOR *)v2;
  if ( !v2 )
    return 14;
  v5 = (unsigned __int16 *)(v2 + 16);
  *(_DWORD *)v2 = 1;
  *((_QWORD *)v2 + 1) = v2 + 16;
  Guid = HV_GUID_LOOPBACK;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\HvSocket\\Addresses",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    cbData = 78;
    if ( !RegQueryValueExW(hKey, L"LocalAddress", 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, Data);
      if ( RtlGUIDFromString(&DestinationString, &Guid) < 0 )
        Guid = HV_GUID_LOOPBACK;
    }
    RegCloseKey(hKey);
  }
  RPC_UUID::ConvertToString((RPC_UUID *)&Guid, v5);
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x1800c567c  push    rbp
0x1800c567e  push    rbx
0x1800c567f  push    rsi
0x1800c5680  push    rdi
0x1800c5681  lea     rbp, [rsp-3Fh]
0x1800c5686  sub     rsp, 0C8h
0x1800c568d  mov     rax, cs:__security_cookie
0x1800c5694  xor     rax, rsp
0x1800c5697  mov     [rbp+57h+var_30], rax
0x1800c569b  mov     rdi, rcx
0x1800c569e  mov     [rbp+57h+hKey], 0
0x1800c56a6  xorps   xmm0, xmm0
0x1800c56a9  mov     ecx, 5Ah ; 'Z'; Size
0x1800c56ae  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800c56b2  call    I_RpcAllocate
0x1800c56b7  mov     rbx, rax
0x1800c56ba  test    rax, rax
0x1800c56bd  jnz     short loc_1800C56C7
0x1800c56bf  lea     eax, [rbx+0Eh]
0x1800c56c2  jmp     loc_1800C5797
0x1800c56c7  movups  xmm0, xmmword ptr cs:HV_GUID_LOOPBACK.Data1
0x1800c56ce  lea     rsi, [rax+10h]
0x1800c56d2  mov     dword ptr [rax], 1
0x1800c56d8  mov     [rax+8], rsi
0x1800c56dc  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800c56e3  lea     rax, [rbp+57h+hKey]
0x1800c56e7  mov     r9d, 20019h; samDesired
0x1800c56ed  xor     r8d, r8d; ulOptions
0x1800c56f0  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800c56f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c56fc  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800c5701  call    cs:__imp_RegOpenKeyExW
0x1800c5707  test    eax, eax
0x1800c5709  jnz     short loc_1800C5786
0x1800c570b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c570f  lea     r9, [rbp+57h+Type]; lpType
0x1800c5713  mov     [rbp+57h+Type], eax
0x1800c5716  lea     rdx, aLocaladdress; "LocalAddress"
0x1800c571d  lea     rax, [rbp+57h+cbData]
0x1800c5721  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x1800c5728  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800c572d  xor     r8d, r8d; lpReserved
0x1800c5730  lea     rax, [rbp+57h+Data]
0x1800c5734  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800c5739  call    cs:__imp_RegQueryValueExW
0x1800c573f  test    eax, eax
0x1800c5741  jnz     short loc_1800C577C
0x1800c5743  cmp     [rbp+57h+Type], 1
0x1800c5747  jnz     short loc_1800C577C
0x1800c5749  xorps   xmm0, xmm0
0x1800c574c  lea     rdx, [rbp+57h+Data]; SourceString
0x1800c5750  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c5754  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800c5758  call    cs:__imp_RtlInitUnicodeString
0x1800c575e  lea     rdx, [rbp+57h+Guid]; Guid
0x1800c5762  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x1800c5766  call    cs:__imp_RtlGUIDFromString
0x1800c576c  test    eax, eax
0x1800c576e  jns     short loc_1800C577C
0x1800c5770  movups  xmm0, xmmword ptr cs:HV_GUID_LOOPBACK.Data1
0x1800c5777  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800c577c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c5780  call    cs:__imp_RegCloseKey
0x1800c5786  mov     rdx, rsi; unsigned __int16 *
0x1800c5789  lea     rcx, [rbp+57h+Guid]; this
0x1800c578d  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x1800c5792  xor     eax, eax
0x1800c5794  mov     [rdi], rbx
0x1800c5797  mov     rcx, [rbp+57h+var_30]
0x1800c579b  xor     rcx, rsp; StackCookie
0x1800c579e  call    __security_check_cookie
0x1800c57a3  add     rsp, 0C8h
0x1800c57aa  pop     rdi
0x1800c57ab  pop     rsi
0x1800c57ac  pop     rbx
0x1800c57ad  pop     rbp
0x1800c57ae  retn
```
