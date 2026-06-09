# I_StoreClmdOpt(uchar const *,ulong,ushort const *)

- ea: `0x18001f340`
- end: `0x18001f522`
- name: `?I_StoreClmdOpt@@YAKPEBEKPEBG@Z`
- size: `482`
- prototype: `unsigned int __fastcall(BYTE *lpData, DWORD cbData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002e84`

## callees

- `0x180016890`
- `0x18001be10`
- `0x18001f340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4e7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f432`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f472`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f432`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f472`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f3f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f3f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f487`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f487`
- `RPCRT4!UuidToStringW` at `0x18001f4ae`
- `RPCRT4!UuidToStringW` at `0x18001f4ae`
- `RPCRT4!UuidCreate` at `0x18001f498`
- `RPCRT4!UuidCreate` at `0x18001f498`
- `RPCRT4!RpcStringFreeW` at `0x18001f4f9`
- `RPCRT4!RpcStringFreeW` at `0x18001f4f9`

## pseudocode

```c
__int64 __fastcall I_StoreClmdOpt(BYTE *lpData, DWORD cbData, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // edi
  DWORD v8; // edx
  LSTATUS v9; // eax
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR StringUuid; // [rsp+68h] [rbp-98h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[256]; // [rsp+80h] [rbp-80h] BYREF

  cchValueName = 255;
  hKey = 0;
  StringUuid = 0;
  Type = 0;
  v6 = 0;
  Uuid = 0;
  if ( cbData && lpData && a3 )
  {
    if ( I_MatchClmdOpt(lpData, a3) )
    {
      v7 = 0;
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x20007u, 0, &hKey, 0);
      if ( !v6 )
      {
        do
        {
          v8 = v7++;
          v9 = RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, &Type, 0, 0);
          cchValueName = 255;
        }
        while ( !v9 );
        if ( v7 <= 0x64
          || (v6 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, 0, 0)) == 0
          && (v6 = RegDeleteValueW(hKey, ValueName)) == 0 )
        {
          v6 = UuidCreate(&Uuid);
          if ( !v6 )
          {
            v6 = UuidToStringW(&Uuid, &StringUuid);
            if ( !v6 )
              v6 = RegSetValueExW(hKey, StringUuid, 0, 3u, lpData, cbData);
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
  }
  return v6;
}

```

## disassembly

```asm
0x18001f340  push    rbp
0x18001f342  push    rbx
0x18001f343  push    rsi
0x18001f344  push    rdi
0x18001f345  push    r12
0x18001f347  push    r14
0x18001f349  push    r15
0x18001f34b  lea     rbp, [rsp-190h]
0x18001f353  sub     rsp, 290h
0x18001f35a  mov     rax, cs:__security_cookie
0x18001f361  xor     rax, rsp
0x18001f364  mov     [rbp+1C0h+var_40], rax
0x18001f36b  xor     r12d, r12d
0x18001f36e  mov     [rsp+2C0h+cchValueName], 0FFh
0x18001f376  mov     [rsp+2C0h+hKey], r12
0x18001f37b  xorps   xmm0, xmm0
0x18001f37e  mov     [rsp+2C0h+StringUuid], r12
0x18001f383  mov     rsi, r8
0x18001f386  mov     [rsp+2C0h+Type], r12d
0x18001f38b  mov     r15d, edx
0x18001f38e  mov     r14, rcx
0x18001f391  mov     ebx, r12d
0x18001f394  movups  xmmword ptr [rsp+2C0h+Uuid.Data1], xmm0
0x18001f399  test    edx, edx
0x18001f39b  jz      loc_18001F4FF
0x18001f3a1  test    rcx, rcx
0x18001f3a4  jz      loc_18001F4FF
0x18001f3aa  test    r8, r8
0x18001f3ad  jz      loc_18001F4FF
0x18001f3b3  mov     rdx, r8; unsigned __int16 *
0x18001f3b6  call    ?I_MatchClmdOpt@@YAKPEBEPEBG@Z; I_MatchClmdOpt(uchar const *,ushort const *)
0x18001f3bb  test    eax, eax
0x18001f3bd  jz      loc_18001F4DD
0x18001f3c3  mov     [rsp+2C0h+lpdwDisposition], r12; lpdwDisposition
0x18001f3c8  lea     rax, [rsp+2C0h+hKey]
0x18001f3cd  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18001f3d2  xor     r9d, r9d; lpClass
0x18001f3d5  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001f3da  xor     r8d, r8d; Reserved
0x18001f3dd  mov     [rsp+2C0h+samDesired], 20007h; samDesired
0x18001f3e5  mov     rdx, rsi; lpSubKey
0x18001f3e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f3ef  mov     [rsp+2C0h+dwOptions], r12d; dwOptions
0x18001f3f4  mov     edi, r12d
0x18001f3f7  call    cs:__imp_RegCreateKeyExW
0x18001f3fd  mov     ebx, eax
0x18001f3ff  test    eax, eax
0x18001f401  jnz     loc_18001F4DD
0x18001f407  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001f40c  lea     rax, [rsp+2C0h+Type]
0x18001f411  mov     [rsp+2C0h+phkResult], r12; lpcbData
0x18001f416  lea     r9, [rsp+2C0h+cchValueName]; lpcchValueName
0x18001f41b  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpData
0x18001f420  lea     r8, [rbp+1C0h+ValueName]; lpValueName
0x18001f424  mov     qword ptr [rsp+2C0h+samDesired], rax; lpType
0x18001f429  mov     edx, edi; dwIndex
0x18001f42b  mov     qword ptr [rsp+2C0h+dwOptions], r12; lpReserved
0x18001f430  inc     edi
0x18001f432  call    cs:__imp_RegEnumValueW
0x18001f438  mov     [rsp+2C0h+cchValueName], 0FFh
0x18001f440  test    eax, eax
0x18001f442  jz      short loc_18001F407
0x18001f444  cmp     edi, 64h ; 'd'
0x18001f447  jbe     short loc_18001F493
0x18001f449  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001f44e  lea     rax, [rsp+2C0h+Type]
0x18001f453  mov     [rsp+2C0h+phkResult], r12; lpcbData
0x18001f458  lea     r9, [rsp+2C0h+cchValueName]; lpcchValueName
0x18001f45d  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpData
0x18001f462  lea     r8, [rbp+1C0h+ValueName]; lpValueName
0x18001f466  mov     qword ptr [rsp+2C0h+samDesired], rax; lpType
0x18001f46b  xor     edx, edx; dwIndex
0x18001f46d  mov     qword ptr [rsp+2C0h+dwOptions], r12; lpReserved
0x18001f472  call    cs:__imp_RegEnumValueW
0x18001f478  mov     ebx, eax
0x18001f47a  test    eax, eax
0x18001f47c  jnz     short loc_18001F4DD
0x18001f47e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001f483  lea     rdx, [rbp+1C0h+ValueName]; lpValueName
0x18001f487  call    cs:__imp_RegDeleteValueW
0x18001f48d  mov     ebx, eax
0x18001f48f  test    eax, eax
0x18001f491  jnz     short loc_18001F4DD
0x18001f493  lea     rcx, [rsp+2C0h+Uuid]; Uuid
0x18001f498  call    cs:__imp_UuidCreate
0x18001f49e  mov     ebx, eax
0x18001f4a0  test    eax, eax
0x18001f4a2  jnz     short loc_18001F4DD
0x18001f4a4  lea     rdx, [rsp+2C0h+StringUuid]; StringUuid
0x18001f4a9  lea     rcx, [rsp+2C0h+Uuid]; Uuid
0x18001f4ae  call    cs:__imp_UuidToStringW
0x18001f4b4  mov     ebx, eax
0x18001f4b6  test    eax, eax
0x18001f4b8  jnz     short loc_18001F4DD
0x18001f4ba  mov     rdx, [rsp+2C0h+StringUuid]; lpValueName
0x18001f4bf  lea     r9d, [rax+3]; dwType
0x18001f4c3  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001f4c8  xor     r8d, r8d; Reserved
0x18001f4cb  mov     [rsp+2C0h+samDesired], r15d; cbData
0x18001f4d0  mov     qword ptr [rsp+2C0h+dwOptions], r14; lpData
0x18001f4d5  call    cs:__imp_RegSetValueExW
0x18001f4db  mov     ebx, eax
0x18001f4dd  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001f4e2  test    rcx, rcx
0x18001f4e5  jz      short loc_18001F4ED
0x18001f4e7  call    cs:__imp_RegCloseKey
0x18001f4ed  cmp     [rsp+2C0h+StringUuid], r12
0x18001f4f2  jz      short loc_18001F4FF
0x18001f4f4  lea     rcx, [rsp+2C0h+StringUuid]; String
0x18001f4f9  call    cs:__imp_RpcStringFreeW
0x18001f4ff  mov     eax, ebx
0x18001f501  mov     rcx, [rbp+1C0h+var_40]
0x18001f508  xor     rcx, rsp; StackCookie
0x18001f50b  call    __security_check_cookie
0x18001f510  add     rsp, 290h
0x18001f517  pop     r15
0x18001f519  pop     r14
0x18001f51b  pop     r12
0x18001f51d  pop     rdi
0x18001f51e  pop     rsi
0x18001f51f  pop     rbx
0x18001f520  pop     rbp
0x18001f521  retn
```
