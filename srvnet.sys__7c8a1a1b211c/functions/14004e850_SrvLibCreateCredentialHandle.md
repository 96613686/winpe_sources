# SrvLibCreateCredentialHandle

- ea: `0x14004e850`
- end: `0x14004e8f9`
- name: `SrvLibCreateCredentialHandle`
- size: `169`
- prototype: `__int64 __fastcall(PSECURITY_STRING pPackage, void *pvGetKeyArgument)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x14004e850`

## import_xrefs

- `ksecdd!AcquireCredentialsHandleW` at `0x14004e8be`
- `ksecdd!AcquireCredentialsHandleW` at `0x14004e8be`
- `ksecdd!MapSecurityError` at `0x14004e8d0`
- `ksecdd!MapSecurityError` at `0x14004e8d0`

## pseudocode

```c
__int64 __fastcall SrvLibCreateCredentialHandle(PSECURITY_STRING pPackage, void *pvGetKeyArgument, __int64 *a3)
{
  __int64 phCredential; // rax
  __int64 v7; // rdi
  int v9; // eax
  unsigned int v10; // ebx

  *a3 = 0;
  phCredential = SrvNetAllocatePoolWithTag(256, 24, 1651266380);
  v7 = phCredential;
  if ( !phCredential )
    return 3221225626LL;
  v9 = AcquireCredentialsHandleW(
         0,
         pPackage,
         1u,
         0,
         0,
         0,
         pvGetKeyArgument,
         (PCredHandle)phCredential,
         (PTimeStamp)(phCredential + 16));
  if ( v9 >= 0 )
  {
    *a3 = v7;
    return 0;
  }
  else
  {
    v10 = MapSecurityError(v9);
    SrvNetWskNotifyCleanupProviderContext(v7);
    return v10;
  }
}

```

## disassembly

```asm
0x14004e850  push    rbx
0x14004e852  push    rbp
0x14004e853  push    rsi
0x14004e854  push    rdi
0x14004e855  sub     rsp, 58h
0x14004e859  mov     rbx, r8
0x14004e85c  mov     qword ptr [r8], 0
0x14004e863  mov     rsi, rdx
0x14004e866  mov     rbp, rcx
0x14004e869  mov     edx, 18h
0x14004e86e  mov     ecx, 100h
0x14004e873  mov     r8d, 626C534Ch
0x14004e879  call    SrvNetAllocatePoolWithTag
0x14004e87e  mov     rdi, rax
0x14004e881  test    rax, rax
0x14004e884  jnz     short loc_14004E88D
0x14004e886  mov     eax, 0C000009Ah
0x14004e88b  jmp     short loc_14004E8EF
0x14004e88d  add     rax, 10h
0x14004e891  xor     r9d, r9d; pvLogonId
0x14004e894  mov     [rsp+78h+ptsExpiry], rax; ptsExpiry
0x14004e899  mov     rdx, rbp; pPackage
0x14004e89c  mov     [rsp+78h+phCredential], rdi; phCredential
0x14004e8a1  xor     ecx, ecx; pPrincipal
0x14004e8a3  mov     [rsp+78h+pvGetKeyArgument], rsi; pvGetKeyArgument
0x14004e8a8  mov     [rsp+78h+pGetKeyFn], 0; pGetKeyFn
0x14004e8b1  lea     r8d, [r9+1]; fCredentialUse
0x14004e8b5  mov     [rsp+78h+pAuthData], 0; pAuthData
0x14004e8be  call    cs:__imp_AcquireCredentialsHandleW
0x14004e8c5  nop     dword ptr [rax+rax+00h]
0x14004e8ca  test    eax, eax
0x14004e8cc  jns     short loc_14004E8EA
0x14004e8ce  mov     ecx, eax; SecStatus
0x14004e8d0  call    cs:__imp_MapSecurityError
0x14004e8d7  nop     dword ptr [rax+rax+00h]
0x14004e8dc  mov     rcx, rdi
0x14004e8df  mov     ebx, eax
0x14004e8e1  call    SrvNetWskNotifyCleanupProviderContext
0x14004e8e6  mov     eax, ebx
0x14004e8e8  jmp     short loc_14004E8EF
0x14004e8ea  mov     [rbx], rdi
0x14004e8ed  xor     eax, eax
0x14004e8ef  add     rsp, 58h
0x14004e8f3  pop     rdi
0x14004e8f4  pop     rsi
0x14004e8f5  pop     rbp
0x14004e8f6  pop     rbx
0x14004e8f7  retn
```
