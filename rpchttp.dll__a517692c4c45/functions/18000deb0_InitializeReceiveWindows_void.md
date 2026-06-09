# InitializeReceiveWindows(void)

- ea: `0x18000deb0`
- end: `0x18000dfdf`
- name: `?InitializeReceiveWindows@@YAJXZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d4fc`
- `0x18001b5d0`

## callees

- `0x18000deb0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000def6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000def6`
- `ADVAPI32!RegCloseKey` at `0x18000dfc6`
- `ADVAPI32!RegCloseKey` at `0x18000dfc6`
- `ADVAPI32!RegGetValueW` at `0x18000dfa0`
- `ADVAPI32!RegGetValueW` at `0x18000dfa0`

## pseudocode

```c
__int64 InitializeReceiveWindows(void)
{
  LSTATUS v0; // eax
  __int64 v2; // rbx
  const WCHAR *v3; // r8
  LPCWSTR lpValue[4]; // [rsp+40h] [rbp-40h]
  _QWORD v5[4]; // [rsp+60h] [rbp-20h]
  DWORD pcbData; // [rsp+90h] [rbp+10h] BYREF
  int pvData; // [rsp+98h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+20h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 != 2 )
  {
    if ( v0 )
      return 14;
    v2 = 0;
    lpValue[0] = L"ClientReceiveWindow";
    lpValue[1] = L"InProxyReceiveWindow";
    lpValue[2] = L"OutProxyReceiveWindow";
    lpValue[3] = L"ServerReceiveWindow";
    v5[0] = &HTTP2ClientReceiveWindow;
    v5[1] = &HTTP2InProxyReceiveWindow;
    v5[2] = &HTTP2OutProxyReceiveWindow;
    v5[3] = &HTTP2ServerReceiveWindow;
    do
    {
      v3 = lpValue[v2];
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, v3, 0x18u, 0, &pvData, &pcbData) )
        *(_DWORD *)v5[v2] = pvData;
      ++v2;
    }
    while ( v2 != 4 );
    if ( hkey )
      RegCloseKey(hkey);
  }
  return 0;
}

```

## disassembly

```asm
0x18000deb0  mov     [rsp-8+arg_18], rbx
0x18000deb5  push    rbp
0x18000deb6  mov     rbp, rsp
0x18000deb9  sub     rsp, 80h
0x18000dec0  lea     rax, [rbp+hkey]
0x18000dec4  mov     [rbp+hkey], 0
0x18000decc  mov     r9d, 20019h; samDesired
0x18000ded2  mov     [rsp+80h+phkResult], rax; phkResult
0x18000ded7  xor     r8d, r8d; ulOptions
0x18000deda  mov     [rbp+arg_0], 0
0x18000dee1  lea     rdx, SubKey; "Software\\Microsoft\\Rpc"
0x18000dee8  mov     [rbp+arg_8], 0
0x18000deef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000def6  call    cs:__imp_RegOpenKeyExW
0x18000defc  cmp     eax, 2
0x18000deff  jz      loc_18000DFCC
0x18000df05  test    eax, eax
0x18000df07  jz      short loc_18000DF13
0x18000df09  mov     eax, 0Eh
0x18000df0e  jmp     loc_18000DFCE
0x18000df13  lea     rax, aClientreceivew; "ClientReceiveWindow"
0x18000df1a  xor     ebx, ebx
0x18000df1c  mov     [rbp+lpValue], rax
0x18000df20  lea     rax, aInproxyreceive; "InProxyReceiveWindow"
0x18000df27  mov     [rbp+var_38], rax
0x18000df2b  lea     rax, aOutproxyreceiv; "OutProxyReceiveWindow"
0x18000df32  mov     [rbp+var_30], rax
0x18000df36  lea     rax, aServerreceivew; "ServerReceiveWindow"
0x18000df3d  mov     [rbp+var_28], rax
0x18000df41  lea     rax, ?HTTP2ClientReceiveWindow@@3KA; ulong HTTP2ClientReceiveWindow
0x18000df48  mov     [rbp+var_20], rax
0x18000df4c  lea     rax, ?HTTP2InProxyReceiveWindow@@3KA; ulong HTTP2InProxyReceiveWindow
0x18000df53  mov     [rbp+var_18], rax
0x18000df57  lea     rax, ?HTTP2OutProxyReceiveWindow@@3KA; ulong HTTP2OutProxyReceiveWindow
0x18000df5e  mov     [rbp+var_10], rax
0x18000df62  lea     rax, ?HTTP2ServerReceiveWindow@@3KA; ulong HTTP2ServerReceiveWindow
0x18000df69  mov     [rbp+var_8], rax
0x18000df6d  mov     r8, [rbp+rbx*8+lpValue]; lpValue
0x18000df72  lea     rax, [rbp+arg_0]
0x18000df76  mov     rcx, [rbp+hkey]; hkey
0x18000df7a  mov     r9d, 18h; dwFlags
0x18000df80  mov     [rsp+80h+pcbData], rax; pcbData
0x18000df85  xor     edx, edx; lpSubKey
0x18000df87  lea     rax, [rbp+arg_8]
0x18000df8b  mov     [rbp+arg_0], 4
0x18000df92  mov     [rsp+80h+pvData], rax; pvData
0x18000df97  mov     [rsp+80h+phkResult], 0; pdwType
0x18000dfa0  call    cs:__imp_RegGetValueW
0x18000dfa6  test    eax, eax
0x18000dfa8  jnz     short loc_18000DFB4
0x18000dfaa  mov     rcx, [rbp+rbx*8+var_20]
0x18000dfaf  mov     eax, [rbp+arg_8]
0x18000dfb2  mov     [rcx], eax
0x18000dfb4  inc     rbx
0x18000dfb7  cmp     rbx, 4
0x18000dfbb  jnz     short loc_18000DF6D
0x18000dfbd  mov     rcx, [rbp+hkey]; hKey
0x18000dfc1  test    rcx, rcx
0x18000dfc4  jz      short loc_18000DFCC
0x18000dfc6  call    cs:__imp_RegCloseKey
0x18000dfcc  xor     eax, eax
0x18000dfce  mov     rbx, [rsp+80h+arg_18]
0x18000dfd6  add     rsp, 80h
0x18000dfdd  pop     rbp
0x18000dfde  retn
```
