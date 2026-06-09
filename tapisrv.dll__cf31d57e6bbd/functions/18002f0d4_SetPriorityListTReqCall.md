# SetPriorityListTReqCall

- ea: `0x18002f0d4`
- end: `0x18002f19e`
- name: `SetPriorityListTReqCall`
- size: `202`
- prototype: `RPC_STATUS __fastcall(LPCWSTR lpString)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014710`

## callees

- `0x18002f06c`
- `0x18002f0d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f18c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f18c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002f111`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002f111`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f15e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f15e`
- `RPCRT4!RpcRevertToSelf` at `0x18002f192`
- `RPCRT4!RpcRevertToSelf` at `0x18002f192`
- `RPCRT4!RpcImpersonateClient` at `0x18002f0f9`
- `RPCRT4!RpcImpersonateClient` at `0x18002f0f9`

## pseudocode

```c
RPC_STATUS __fastcall SetPriorityListTReqCall(LPCWSTR lpString)
{
  RPC_STATUS result; // eax
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    if ( !RegOpenCurrentUser(0xF003Fu, &phkResult) )
    {
      if ( !RegCreateKeyExW(
              phkResult,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\HandoffPriorities",
              0,
              (LPWSTR)&Format,
              0,
              2u,
              0,
              &hKey,
              &dwDisposition) )
      {
        SetPriorityList(hKey, L"RequestMakeCall", lpString);
        RegCloseKey(hKey);
      }
      RegCloseKey(phkResult);
    }
    return RpcRevertToSelf();
  }
  return result;
}

```

## disassembly

```asm
0x18002f0d4  push    rbx
0x18002f0d6  sub     rsp, 50h
0x18002f0da  mov     rbx, rcx
0x18002f0dd  mov     [rsp+58h+hKey], 0
0x18002f0e6  xor     ecx, ecx; BindingHandle
0x18002f0e8  mov     [rsp+58h+phkResult], 0
0x18002f0f1  mov     [rsp+58h+dwDisposition], 0
0x18002f0f9  call    cs:__imp_RpcImpersonateClient
0x18002f0ff  test    eax, eax
0x18002f101  jnz     loc_18002F198
0x18002f107  lea     rdx, [rsp+58h+phkResult]; phkResult
0x18002f10c  mov     ecx, 0F003Fh; samDesired
0x18002f111  call    cs:__imp_RegOpenCurrentUser
0x18002f117  test    eax, eax
0x18002f119  jnz     short loc_18002F192
0x18002f11b  mov     rcx, [rsp+58h+phkResult]; hKey
0x18002f120  lea     rax, [rsp+58h+dwDisposition]
0x18002f125  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18002f12a  lea     r9, Format; lpClass
0x18002f131  lea     rax, [rsp+58h+hKey]
0x18002f136  xor     r8d, r8d; Reserved
0x18002f139  mov     [rsp+58h+var_20], rax; phkResult
0x18002f13e  lea     rdx, gszRegKeyHandoffPriorities; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002f145  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002f14e  mov     [rsp+58h+samDesired], 2; samDesired
0x18002f156  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002f15e  call    cs:__imp_RegCreateKeyExW
0x18002f164  test    eax, eax
0x18002f166  jnz     short loc_18002F187
0x18002f168  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f16d  lea     rdx, gszRequestMakeCallW; "RequestMakeCall"
0x18002f174  mov     r8, rbx; lpString
0x18002f177  call    SetPriorityList
0x18002f17c  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f181  call    cs:__imp_RegCloseKey
0x18002f187  mov     rcx, [rsp+58h+phkResult]; hKey
0x18002f18c  call    cs:__imp_RegCloseKey
0x18002f192  call    cs:__imp_RpcRevertToSelf
0x18002f198  add     rsp, 50h
0x18002f19c  pop     rbx
0x18002f19d  retn
```
