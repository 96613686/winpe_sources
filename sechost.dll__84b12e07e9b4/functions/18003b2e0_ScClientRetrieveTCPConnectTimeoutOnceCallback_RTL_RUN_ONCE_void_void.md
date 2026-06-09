# ScClientRetrieveTCPConnectTimeoutOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18003b2e0`
- end: `0x18003b39a`
- name: `?ScClientRetrieveTCPConnectTimeoutOnceCallback@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `186`
- prototype: `unsigned int __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003b2e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b326`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b326`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b354`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b36b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b36b`

## pseudocode

```c
__int64 __fastcall ScClientRetrieveTCPConnectTimeoutOnceCallback(union _RTL_RUN_ONCE *a1, void *a2, void **a3)
{
  int v3; // ecx
  __int64 result; // rax
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"SCMApiConnectionParam", 0, &Type, (LPBYTE)&Data, &cbData) && Type != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  v3 = Data;
  dword_18007C5FC = Data >> 31;
  if ( !Data )
    v3 = 21000;
  result = 1;
  LODWORD(optionValue) = v3;
  return result;
}

```

## disassembly

```asm
0x18003b2e0  push    rbp
0x18003b2e2  mov     rbp, rsp
0x18003b2e5  sub     rsp, 40h
0x18003b2e9  lea     rax, [rbp+hKey]
0x18003b2ed  mov     [rbp+hKey], 0
0x18003b2f5  mov     r9d, 20019h; samDesired
0x18003b2fb  mov     [rsp+40h+phkResult], rax; phkResult
0x18003b300  xor     r8d, r8d; ulOptions
0x18003b303  mov     [rbp+Type], 0
0x18003b30a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control"
0x18003b311  mov     [rbp+cbData], 4
0x18003b318  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b31f  mov     [rbp+Data], 0
0x18003b326  call    cs:__imp_RegOpenKeyExW
0x18003b32c  test    eax, eax
0x18003b32e  jnz     short loc_18003B371
0x18003b330  mov     rcx, [rbp+hKey]; hKey
0x18003b334  lea     rax, [rbp+cbData]
0x18003b338  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18003b33d  lea     r9, [rbp+Type]; lpType
0x18003b341  lea     rax, [rbp+Data]
0x18003b345  xor     r8d, r8d; lpReserved
0x18003b348  lea     rdx, aScmapiconnecti; "SCMApiConnectionParam"
0x18003b34f  mov     [rsp+40h+phkResult], rax; lpData
0x18003b354  call    cs:__imp_RegQueryValueExW
0x18003b35a  test    eax, eax
0x18003b35c  jnz     short loc_18003B367
0x18003b35e  cmp     [rbp+Type], 4
0x18003b362  jz      short loc_18003B367
0x18003b364  mov     [rbp+Data], eax
0x18003b367  mov     rcx, [rbp+hKey]; hKey
0x18003b36b  call    cs:__imp_RegCloseKey
0x18003b371  mov     ecx, [rbp+Data]
0x18003b374  mov     eax, ecx
0x18003b376  shr     eax, 1Fh
0x18003b379  mov     cs:dword_18007C5FC, eax
0x18003b37f  test    ecx, ecx
0x18003b381  mov     eax, 5208h
0x18003b386  cmovz   ecx, eax
0x18003b389  mov     eax, 1
0x18003b38e  mov     cs:optionValue, ecx
0x18003b394  add     rsp, 40h
0x18003b398  pop     rbp
0x18003b399  retn
```
