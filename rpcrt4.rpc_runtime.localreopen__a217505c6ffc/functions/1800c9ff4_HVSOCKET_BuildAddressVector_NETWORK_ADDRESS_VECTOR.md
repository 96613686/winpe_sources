# HVSOCKET_BuildAddressVector(NETWORK_ADDRESS_VECTOR * *)

- ea: `0x1800c9ff4`
- end: `0x1800ca14a`
- name: `?HVSOCKET_BuildAddressVector@@YAJPEAPEAUNETWORK_ADDRESS_VECTOR@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(struct NETWORK_ADDRESS_VECTOR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ca2a0`

## callees

- `0x18002d45c`
- `0x180044870`
- `0x1800c9ff4`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x1800ca0f4`
- `ntdll!RtlGUIDFromString` at `0x1800ca0f4`
- `ntdll!RtlInitUnicodeString` at `0x1800ca0e0`
- `ntdll!RtlInitUnicodeString` at `0x1800ca0e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca079`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca114`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca0bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca0bb`

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
0x1800c9ff4  push    rbp
0x1800c9ff6  push    rbx
0x1800c9ff7  push    rsi
0x1800c9ff8  push    rdi
0x1800c9ff9  lea     rbp, [rsp-3Fh]
0x1800c9ffe  sub     rsp, 0C8h
0x1800ca005  mov     rax, cs:__security_cookie
0x1800ca00c  xor     rax, rsp
0x1800ca00f  mov     [rbp+57h+var_30], rax
0x1800ca013  mov     rdi, rcx
0x1800ca016  mov     [rbp+57h+hKey], 0
0x1800ca01e  xorps   xmm0, xmm0
0x1800ca021  mov     ecx, 5Ah ; 'Z'; Size
0x1800ca026  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800ca02a  call    I_RpcAllocate
0x1800ca02f  mov     rbx, rax
0x1800ca032  test    rax, rax
0x1800ca035  jnz     short loc_1800CA03F
0x1800ca037  lea     eax, [rbx+0Eh]
0x1800ca03a  jmp     loc_1800CA131
0x1800ca03f  movups  xmm0, xmmword ptr cs:HV_GUID_LOOPBACK.Data1
0x1800ca046  lea     rsi, [rax+10h]
0x1800ca04a  mov     dword ptr [rax], 1
0x1800ca050  mov     [rax+8], rsi
0x1800ca054  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ca05b  lea     rax, [rbp+57h+hKey]
0x1800ca05f  mov     r9d, 20019h; samDesired
0x1800ca065  xor     r8d, r8d; ulOptions
0x1800ca068  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800ca06d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ca074  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800ca079  call    cs:__imp_RegOpenKeyExW
0x1800ca080  nop     dword ptr [rax+rax+00h]
0x1800ca085  test    eax, eax
0x1800ca087  jnz     loc_1800CA120
0x1800ca08d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ca091  lea     r9, [rbp+57h+Type]; lpType
0x1800ca095  mov     [rbp+57h+Type], eax
0x1800ca098  lea     rdx, aLocaladdress; "LocalAddress"
0x1800ca09f  lea     rax, [rbp+57h+cbData]
0x1800ca0a3  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x1800ca0aa  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800ca0af  xor     r8d, r8d; lpReserved
0x1800ca0b2  lea     rax, [rbp+57h+Data]
0x1800ca0b6  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800ca0bb  call    cs:__imp_RegQueryValueExW
0x1800ca0c2  nop     dword ptr [rax+rax+00h]
0x1800ca0c7  test    eax, eax
0x1800ca0c9  jnz     short loc_1800CA110
0x1800ca0cb  cmp     [rbp+57h+Type], 1
0x1800ca0cf  jnz     short loc_1800CA110
0x1800ca0d1  xorps   xmm0, xmm0
0x1800ca0d4  lea     rdx, [rbp+57h+Data]; SourceString
0x1800ca0d8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800ca0dc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800ca0e0  call    cs:__imp_RtlInitUnicodeString
0x1800ca0e7  nop     dword ptr [rax+rax+00h]
0x1800ca0ec  lea     rdx, [rbp+57h+Guid]; Guid
0x1800ca0f0  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x1800ca0f4  call    cs:__imp_RtlGUIDFromString
0x1800ca0fb  nop     dword ptr [rax+rax+00h]
0x1800ca100  test    eax, eax
0x1800ca102  jns     short loc_1800CA110
0x1800ca104  movups  xmm0, xmmword ptr cs:HV_GUID_LOOPBACK.Data1
0x1800ca10b  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1800ca110  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ca114  call    cs:__imp_RegCloseKey
0x1800ca11b  nop     dword ptr [rax+rax+00h]
0x1800ca120  mov     rdx, rsi; unsigned __int16 *
0x1800ca123  lea     rcx, [rbp+57h+Guid]; this
0x1800ca127  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x1800ca12c  xor     eax, eax
0x1800ca12e  mov     [rdi], rbx
0x1800ca131  mov     rcx, [rbp+57h+var_30]
0x1800ca135  xor     rcx, rsp; StackCookie
0x1800ca138  call    __security_check_cookie
0x1800ca13d  add     rsp, 0C8h
0x1800ca144  pop     rdi
0x1800ca145  pop     rsi
0x1800ca146  pop     rbx
0x1800ca147  pop     rbp
0x1800ca148  retn
```
