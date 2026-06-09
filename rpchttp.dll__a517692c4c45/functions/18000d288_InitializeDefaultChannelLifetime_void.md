# InitializeDefaultChannelLifetime(void)

- ea: `0x18000d288`
- end: `0x18000d414`
- name: `?InitializeDefaultChannelLifetime@@YAJXZ`
- size: `396`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x18001b5d0`

## callees

- `0x18000d288`
- `0x18001e4a4`
- `0x18002461d`
- `0x180024640`

## import_xrefs

- `ntdll!_itoa_s` at `0x18000d394`
- `ntdll!_itoa_s` at `0x18000d394`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d2e6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d2e6`
- `ADVAPI32!RegCloseKey` at `0x18000d359`
- `ADVAPI32!RegCloseKey` at `0x18000d407`
- `ADVAPI32!RegCloseKey` at `0x18000d359`
- `ADVAPI32!RegCloseKey` at `0x18000d407`
- `ADVAPI32!RegGetValueW` at `0x18000d343`
- `ADVAPI32!RegGetValueW` at `0x18000d343`
- `RPCRT4!I_RpcAllocate` at `0x18000d3b3`
- `RPCRT4!I_RpcAllocate` at `0x18000d3b3`

## pseudocode

```c
__int64 InitializeDefaultChannelLifetime(void)
{
  LSTATUS v0; // eax
  LSTATUS ValueW; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  int Value; // [rsp+44h] [rbp-2Ch] BYREF
  HKEY hkey; // [rsp+48h] [rbp-28h] BYREF
  char Buffer[24]; // [rsp+50h] [rbp-20h] BYREF

  hkey = 0;
  pcbData = 0;
  Value = 0;
  if ( DefaultChannelLifetimeStringRead )
    return 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 == 2 )
    return 0;
  if ( v0 )
  {
    CompRpcpErrorAddRecord(0xDu, v0, 0xBC2u);
    return 14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"DefaultChannelLifetime", 0x18u, 0, &Value, &pcbData);
  v3 = ValueW;
  if ( ValueW == 2 )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  if ( ValueW )
  {
    CompRpcpErrorAddRecord(0xDu, ValueW, 0xBC3u);
  }
  else
  {
    DefaultChannelLifetime = Value;
    _itoa_s(Value, Buffer, 0x14u, 10);
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
    LODWORD(DefaultChannelLifetimeStringLength) = v4;
    DefaultChannelLifetimeString = I_RpcAllocate((int)v4 + 1);
    if ( DefaultChannelLifetimeString )
    {
      memcpy_0(DefaultChannelLifetimeString, Buffer, (unsigned int)(DefaultChannelLifetimeStringLength + 1));
      DefaultChannelLifetimeStringRead = 1;
    }
    else
    {
      v3 = 14;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v3;
}

```

## disassembly

```asm
0x18000d288  mov     [rsp-8+arg_0], rbx
0x18000d28d  push    rbp
0x18000d28e  mov     rbp, rsp
0x18000d291  sub     rsp, 70h
0x18000d295  mov     rax, cs:__security_cookie
0x18000d29c  xor     rax, rsp
0x18000d29f  mov     [rbp+var_8], rax
0x18000d2a3  cmp     cs:?DefaultChannelLifetimeStringRead@@3HA, 0; int DefaultChannelLifetimeStringRead
0x18000d2aa  mov     [rbp+hkey], 0
0x18000d2b2  mov     [rbp+var_30], 0
0x18000d2b9  mov     [rbp+Value], 0
0x18000d2c0  jnz     loc_18000D35F
0x18000d2c6  lea     rax, [rbp+hkey]
0x18000d2ca  mov     r9d, 20019h; samDesired
0x18000d2d0  xor     r8d, r8d; ulOptions
0x18000d2d3  mov     [rsp+70h+phkResult], rax; phkResult
0x18000d2d8  lea     rdx, SubKey; "Software\\Microsoft\\Rpc"
0x18000d2df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d2e6  call    cs:__imp_RegOpenKeyExW
0x18000d2ec  cmp     eax, 2
0x18000d2ef  jz      short loc_18000D35F
0x18000d2f1  test    eax, eax
0x18000d2f3  jz      short loc_18000D30E
0x18000d2f5  mov     r8d, 0BC2h; unsigned __int16
0x18000d2fb  mov     edx, eax; unsigned int
0x18000d2fd  mov     ecx, 0Dh; unsigned int
0x18000d302  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d307  mov     eax, 0Eh
0x18000d30c  jmp     short loc_18000D361
0x18000d30e  mov     rcx, [rbp+hkey]; hkey
0x18000d312  lea     rax, [rbp+var_30]
0x18000d316  mov     [rsp+70h+pcbData], rax; pcbData
0x18000d31b  lea     r8, aDefaultchannel; "DefaultChannelLifetime"
0x18000d322  lea     rax, [rbp+Value]
0x18000d326  mov     [rbp+var_30], 4
0x18000d32d  mov     [rsp+70h+pvData], rax; pvData
0x18000d332  mov     r9d, 18h; dwFlags
0x18000d338  xor     edx, edx; lpSubKey
0x18000d33a  mov     [rsp+70h+phkResult], 0; pdwType
0x18000d343  call    cs:__imp_RegGetValueW
0x18000d349  mov     ebx, eax
0x18000d34b  cmp     eax, 2
0x18000d34e  jnz     short loc_18000D37B
0x18000d350  mov     rcx, [rbp+hkey]; hKey
0x18000d354  test    rcx, rcx
0x18000d357  jz      short loc_18000D35F
0x18000d359  call    cs:__imp_RegCloseKey
0x18000d35f  xor     eax, eax
0x18000d361  mov     rcx, [rbp+var_8]
0x18000d365  xor     rcx, rsp; StackCookie
0x18000d368  call    __security_check_cookie
0x18000d36d  mov     rbx, [rsp+70h+arg_0]
0x18000d375  add     rsp, 70h
0x18000d379  pop     rbp
0x18000d37a  retn
0x18000d37b  test    eax, eax
0x18000d37d  jnz     short loc_18000D3EC
0x18000d37f  mov     ecx, [rbp+Value]; Value
0x18000d382  lea     r9d, [rax+0Ah]; Radix
0x18000d386  lea     r8d, [rax+14h]; BufferCount
0x18000d38a  mov     cs:?DefaultChannelLifetime@@3KA, ecx; ulong DefaultChannelLifetime
0x18000d390  lea     rdx, [rbp+Buffer]; Buffer
0x18000d394  call    cs:__imp__itoa_s
0x18000d39a  lea     rax, [rbp+Buffer]
0x18000d39e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d3a2  inc     rcx
0x18000d3a5  cmp     byte ptr [rax+rcx], 0
0x18000d3a9  jnz     short loc_18000D3A2
0x18000d3ab  mov     cs:?DefaultChannelLifetimeStringLength@@3KA, ecx; ulong DefaultChannelLifetimeStringLength
0x18000d3b1  inc     ecx; Size
0x18000d3b3  call    cs:__imp_I_RpcAllocate
0x18000d3b9  mov     cs:?DefaultChannelLifetimeString@@3PEADEA, rax; char * DefaultChannelLifetimeString
0x18000d3c0  mov     rcx, rax; void *
0x18000d3c3  test    rax, rax
0x18000d3c6  jnz     short loc_18000D3CD
0x18000d3c8  lea     ebx, [rax+0Eh]
0x18000d3cb  jmp     short loc_18000D3FE
0x18000d3cd  mov     r8d, cs:?DefaultChannelLifetimeStringLength@@3KA; ulong DefaultChannelLifetimeStringLength
0x18000d3d4  lea     rdx, [rbp+Buffer]; Src
0x18000d3d8  inc     r8d; Size
0x18000d3db  call    memcpy_0
0x18000d3e0  mov     cs:?DefaultChannelLifetimeStringRead@@3HA, 1; int DefaultChannelLifetimeStringRead
0x18000d3ea  jmp     short loc_18000D3FE
0x18000d3ec  mov     r8d, 0BC3h; unsigned __int16
0x18000d3f2  mov     edx, eax; unsigned int
0x18000d3f4  mov     ecx, 0Dh; unsigned int
0x18000d3f9  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d3fe  mov     rcx, [rbp+hkey]; hKey
0x18000d402  test    rcx, rcx
0x18000d405  jz      short loc_18000D40D
0x18000d407  call    cs:__imp_RegCloseKey
0x18000d40d  mov     eax, ebx
0x18000d40f  jmp     loc_18000D361
```
