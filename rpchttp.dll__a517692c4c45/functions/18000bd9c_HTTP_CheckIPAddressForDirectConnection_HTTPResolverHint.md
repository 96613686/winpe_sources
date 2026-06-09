# HTTP_CheckIPAddressForDirectConnection(HTTPResolverHint *)

- ea: `0x18000bd9c`
- end: `0x18000bebd`
- name: `?HTTP_CheckIPAddressForDirectConnection@@YAJPEAVHTTPResolverHint@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct HTTPResolverHint *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c1a0`

## callees

- `0x18000bd9c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000be62`
- `ADVAPI32!RegCloseKey` at `0x18000be62`
- `ADVAPI32!RegOpenKeyW` at `0x18000be13`
- `ADVAPI32!RegOpenKeyW` at `0x18000be13`
- `ADVAPI32!RegGetValueW` at `0x18000be56`
- `ADVAPI32!RegGetValueW` at `0x18000be56`
- `WS2_32!freeaddrinfo` at `0x18000bead`
- `WS2_32!freeaddrinfo` at `0x18000bead`
- `WS2_32!getnameinfo` at `0x18000be98`
- `WS2_32!getnameinfo` at `0x18000be98`
- `WS2_32!getaddrinfo` at `0x18000bdec`
- `WS2_32!getaddrinfo` at `0x18000bdec`

## pseudocode

```c
__int64 __fastcall HTTP_CheckIPAddressForDirectConnection(struct HTTPResolverHint *a1)
{
  const CHAR *v2; // rcx
  LSTATUS ValueW; // ebx
  ADDRINFOA pHints; // [rsp+40h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+20h] BYREF
  int pvData; // [rsp+98h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+30h] BYREF
  PADDRINFOA ppResult; // [rsp+A8h] [rbp+38h] BYREF

  phkResult = 0;
  pvData = 0;
  v2 = (const CHAR *)*((_QWORD *)a1 + 12);
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_flags = 4;
  pcbData = 0;
  ppResult = 0;
  if ( !getaddrinfo(v2, 0, &pHints, &ppResult) )
  {
    *((_DWORD *)a1 + 8) = 1;
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", &phkResult) )
    {
      pcbData = 4;
      ValueW = RegGetValueW(phkResult, 0, L"UseProxyForIPAddrIfRDNSFails", 0x18u, 0, &pvData, &pcbData);
      RegCloseKey(phkResult);
      if ( !ValueW && pvData == 1 && getnameinfo(ppResult->ai_addr, ppResult->ai_addrlen, 0, 0, 0, 0, 4) )
        *((_DWORD *)a1 + 8) = 2;
    }
    freeaddrinfo(ppResult);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bd9c  push    rbp
0x18000bd9e  push    rbx
0x18000bd9f  push    rdi
0x18000bda0  mov     rbp, rsp
0x18000bda3  sub     rsp, 70h
0x18000bda7  xorps   xmm0, xmm0
0x18000bdaa  mov     [rbp+phkResult], 0
0x18000bdb2  mov     rdi, rcx
0x18000bdb5  mov     [rbp+arg_8], 0
0x18000bdbc  mov     rcx, [rcx+60h]; pNodeName
0x18000bdc0  lea     r9, [rbp+ppResult]; ppResult
0x18000bdc4  movups  xmmword ptr [rbp+pHints.ai_flags], xmm0
0x18000bdc8  lea     r8, [rbp+pHints]; pHints
0x18000bdcc  mov     [rbp+pHints.ai_flags], 4
0x18000bdd3  xor     edx, edx; pServiceName
0x18000bdd5  mov     [rbp+arg_0], 0
0x18000bddc  mov     [rbp+ppResult], 0
0x18000bde4  movups  xmmword ptr [rbp+pHints.ai_addrlen], xmm0
0x18000bde8  movups  xmmword ptr [rbp+pHints.ai_addr], xmm0
0x18000bdec  call    cs:__imp_getaddrinfo
0x18000bdf2  test    eax, eax
0x18000bdf4  jnz     loc_18000BEB3
0x18000bdfa  lea     r8, [rbp+phkResult]; phkResult
0x18000bdfe  mov     dword ptr [rdi+20h], 1
0x18000be05  lea     rdx, SubKey; "Software\\Microsoft\\Rpc"
0x18000be0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000be13  call    cs:__imp_RegOpenKeyW
0x18000be19  test    eax, eax
0x18000be1b  jnz     loc_18000BEA9
0x18000be21  mov     rcx, [rbp+phkResult]; hkey
0x18000be25  lea     rax, [rbp+arg_0]
0x18000be29  mov     [rsp+70h+pcbData], rax; pcbData
0x18000be2e  lea     r8, Value; "UseProxyForIPAddrIfRDNSFails"
0x18000be35  lea     rax, [rbp+arg_8]
0x18000be39  mov     [rbp+arg_0], 4
0x18000be40  mov     [rsp+70h+pvData], rax; pvData
0x18000be45  mov     r9d, 18h; dwFlags
0x18000be4b  xor     edx, edx; lpSubKey
0x18000be4d  mov     [rsp+70h+pdwType], 0; pdwType
0x18000be56  call    cs:__imp_RegGetValueW
0x18000be5c  mov     rcx, [rbp+phkResult]; hKey
0x18000be60  mov     ebx, eax
0x18000be62  call    cs:__imp_RegCloseKey
0x18000be68  test    ebx, ebx
0x18000be6a  jnz     short loc_18000BEA9
0x18000be6c  cmp     [rbp+arg_8], 1
0x18000be70  jnz     short loc_18000BEA9
0x18000be72  mov     rcx, [rbp+ppResult]
0x18000be76  xor     r9d, r9d; NodeBufferSize
0x18000be79  mov     dword ptr [rsp+70h+pcbData], 4; Flags
0x18000be81  xor     r8d, r8d; pNodeBuffer
0x18000be84  mov     dword ptr [rsp+70h+pvData], ebx; ServiceBufferSize
0x18000be88  mov     [rsp+70h+pdwType], 0; pServiceBuffer
0x18000be91  mov     edx, [rcx+10h]; SockaddrLength
0x18000be94  mov     rcx, [rcx+20h]; pSockaddr
0x18000be98  call    cs:__imp_getnameinfo
0x18000be9e  test    eax, eax
0x18000bea0  jz      short loc_18000BEA9
0x18000bea2  mov     dword ptr [rdi+20h], 2
0x18000bea9  mov     rcx, [rbp+ppResult]; pAddrInfo
0x18000bead  call    cs:__imp_freeaddrinfo
0x18000beb3  xor     eax, eax
0x18000beb5  add     rsp, 70h
0x18000beb9  pop     rdi
0x18000beba  pop     rbx
0x18000bebb  pop     rbp
0x18000bebc  retn
```
