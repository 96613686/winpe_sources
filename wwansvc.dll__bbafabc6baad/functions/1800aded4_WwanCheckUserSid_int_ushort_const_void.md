# WwanCheckUserSid(int *,ushort const *,void *)

- ea: `0x1800aded4`
- end: `0x1800adf78`
- name: `?WwanCheckUserSid@@YAKPEAHPEBGPEAX@Z`
- size: `164`
- prototype: `unsigned int __fastcall(PBOOL IsMember, LPCWSTR StringSid, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023ef0`
- `0x18006a744`

## callees

- `0x1800aded4`
- `0x1800ae9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adf0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adf49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adf0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adf49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adf65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adf65`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800adf3f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800adf3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adf2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adf5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adf2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adf5a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800adf00`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800adf00`

## pseudocode

```c
DWORD __fastcall WwanCheckUserSid(PBOOL IsMember, LPCWSTR StringSid, void *a3)
{
  DWORD RpcClientToken; // ebx
  HANDLE TokenHandle; // [rsp+20h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
    return GetLastError();
  RpcClientToken = getRpcClientToken(&TokenHandle, a3);
  if ( RpcClientToken )
  {
    LocalFree(hMem);
  }
  else
  {
    if ( CheckTokenMembership(TokenHandle, hMem, IsMember) )
      RpcClientToken = 0;
    else
      RpcClientToken = GetLastError();
    LocalFree(hMem);
    CloseHandle(TokenHandle);
  }
  return RpcClientToken;
}

```

## disassembly

```asm
0x1800aded4  mov     r11, rsp
0x1800aded7  mov     [r11+8], rbx
0x1800adedb  push    rdi
0x1800adedc  sub     rsp, 30h
0x1800adee0  mov     rax, rdx
0x1800adee3  mov     qword ptr [r11-18h], 0
0x1800adeeb  mov     rdi, rcx
0x1800adeee  mov     qword ptr [r11+20h], 0
0x1800adef6  mov     rcx, rax; StringSid
0x1800adef9  lea     rdx, [r11+20h]; Sid
0x1800adefd  mov     rbx, r8
0x1800adf00  call    cs:__imp_ConvertStringSidToSidW
0x1800adf06  test    eax, eax
0x1800adf08  jnz     short loc_1800ADF12
0x1800adf0a  call    cs:__imp_GetLastError
0x1800adf10  jmp     short loc_1800ADF6D
0x1800adf12  mov     rdx, rbx
0x1800adf15  lea     rcx, [rsp+38h+TokenHandle]
0x1800adf1a  call    _getRpcClientToken
0x1800adf1f  mov     ebx, eax
0x1800adf21  test    eax, eax
0x1800adf23  jz      short loc_1800ADF32
0x1800adf25  mov     rcx, [rsp+38h+hMem]; hMem
0x1800adf2a  call    cs:__imp_LocalFree
0x1800adf30  jmp     short loc_1800ADF6B
0x1800adf32  mov     rdx, [rsp+38h+hMem]; SidToCheck
0x1800adf37  mov     r8, rdi; IsMember
0x1800adf3a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800adf3f  call    cs:__imp_CheckTokenMembership
0x1800adf45  test    eax, eax
0x1800adf47  jnz     short loc_1800ADF53
0x1800adf49  call    cs:__imp_GetLastError
0x1800adf4f  mov     ebx, eax
0x1800adf51  jmp     short loc_1800ADF55
0x1800adf53  xor     ebx, ebx
0x1800adf55  mov     rcx, [rsp+38h+hMem]; hMem
0x1800adf5a  call    cs:__imp_LocalFree
0x1800adf60  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800adf65  call    cs:__imp_CloseHandle
0x1800adf6b  mov     eax, ebx
0x1800adf6d  mov     rbx, [rsp+38h+arg_0]
0x1800adf72  add     rsp, 30h
0x1800adf76  pop     rdi
0x1800adf77  retn
```
