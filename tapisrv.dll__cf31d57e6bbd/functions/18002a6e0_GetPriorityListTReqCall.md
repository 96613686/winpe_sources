# GetPriorityListTReqCall

- ea: `0x18002a6e0`
- end: `0x18002a7ad`
- name: `GetPriorityListTReqCall`
- size: `205`
- prototype: `RPC_STATUS()`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006c14`
- `0x18000b990`
- `0x180014710`
- `0x18002fc10`

## callees

- `0x18002a5ac`
- `0x18002a6e0`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a78e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a78e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a737`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a737`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a760`
- `RPCRT4!RpcRevertToSelf` at `0x18002a7a1`
- `RPCRT4!RpcRevertToSelf` at `0x18002a7a1`
- `RPCRT4!RpcImpersonateClient` at `0x18002a6fd`
- `RPCRT4!RpcImpersonateClient` at `0x18002a6fd`
- `KERNEL32!LeaveCriticalSection` at `0x18002a79b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a79b`
- `KERNEL32!EnterCriticalSection` at `0x18002a727`
- `KERNEL32!EnterCriticalSection` at `0x18002a727`

## string_xrefs

- `0x18002a70a`: `GetPriorityListTReqCall: RpcImpersonateClient failed, err=%d`

## pseudocode

```c
RPC_STATUS GetPriorityListTReqCall()
{
  RPC_STATUS v0; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  phkResult = 0;
  hKey = 0;
  v0 = RpcImpersonateClient(0);
  if ( v0 )
    return TRACELogPrint(65538, "GetPriorityListTReqCall: RpcImpersonateClient failed, err=%d", v0);
  EnterCriticalSection(&gPriorityListCritSec);
  if ( !RegOpenCurrentUser(0xF003Fu, &phkResult) )
  {
    if ( !RegOpenKeyExW(
            phkResult,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\HandoffPriorities",
            0,
            0x20019u,
            &hKey) )
    {
      GetPriorityList(hKey, L"RequestMakeCall");
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  LeaveCriticalSection(&gPriorityListCritSec);
  return RpcRevertToSelf();
}

```

## disassembly

```asm
0x18002a6e0  push    rbx
0x18002a6e2  sub     rsp, 30h
0x18002a6e6  mov     rbx, rcx
0x18002a6e9  mov     [rsp+38h+phkResult], 0
0x18002a6f2  xor     ecx, ecx; BindingHandle
0x18002a6f4  mov     [rsp+38h+hKey], 0
0x18002a6fd  call    cs:__imp_RpcImpersonateClient
0x18002a703  test    eax, eax
0x18002a705  jz      short loc_18002A720
0x18002a707  mov     r8d, eax
0x18002a70a  lea     rdx, aGetprioritylis; "GetPriorityListTReqCall: RpcImpersonate"...
0x18002a711  mov     ecx, 10002h
0x18002a716  call    TRACELogPrint
0x18002a71b  jmp     loc_18002A7A7
0x18002a720  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18002a727  call    cs:__imp_EnterCriticalSection
0x18002a72d  lea     rdx, [rsp+38h+phkResult]; phkResult
0x18002a732  mov     ecx, 0F003Fh; samDesired
0x18002a737  call    cs:__imp_RegOpenCurrentUser
0x18002a73d  test    eax, eax
0x18002a73f  jnz     short loc_18002A794
0x18002a741  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002a746  lea     rax, [rsp+38h+hKey]
0x18002a74b  mov     r9d, 20019h; samDesired
0x18002a751  mov     [rsp+38h+var_18], rax; phkResult
0x18002a756  xor     r8d, r8d; ulOptions
0x18002a759  lea     rdx, gszRegKeyHandoffPriorities; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a760  call    cs:__imp_RegOpenKeyExW
0x18002a766  test    eax, eax
0x18002a768  jnz     short loc_18002A789
0x18002a76a  mov     rcx, [rsp+38h+hKey]; hKey
0x18002a76f  lea     rdx, gszRequestMakeCallW; "RequestMakeCall"
0x18002a776  mov     r8, rbx
0x18002a779  call    GetPriorityList
0x18002a77e  mov     rcx, [rsp+38h+hKey]; hKey
0x18002a783  call    cs:__imp_RegCloseKey
0x18002a789  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002a78e  call    cs:__imp_RegCloseKey
0x18002a794  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18002a79b  call    cs:__imp_LeaveCriticalSection
0x18002a7a1  call    cs:__imp_RpcRevertToSelf
0x18002a7a7  add     rsp, 30h
0x18002a7ab  pop     rbx
0x18002a7ac  retn
```
