# GetLogonIdFromToken(void *)

- ea: `0x1800b43b8`
- end: `0x1800b4465`
- name: `?GetLogonIdFromToken@@YA_JPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800b44fc`

## callees

- `0x1800b43b8`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800b43f8`
- `KERNELBASE!LocalAlloc` at `0x1800b43f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4445`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4445`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b43e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b4424`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b43e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b4424`

## pseudocode

```c
__int64 __fastcall GetLogonIdFromToken(HANDLE TokenHandle)
{
  __int64 v1; // rbx
  unsigned int *v3; // rdi
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  LODWORD(uBytes) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenStatistics, 0, 0, (PDWORD)&uBytes) )
  {
    v3 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
    if ( v3 )
    {
      if ( GetTokenInformation(TokenHandle, TokenStatistics, v3, uBytes, (PDWORD)&uBytes) )
        v1 = v3[2] + ((__int64)(int)v3[3] << 32);
      LocalFree(v3);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800b43b8  mov     rax, rsp
0x1800b43bb  mov     [rax+8], rbx
0x1800b43bf  mov     [rax+18h], rsi
0x1800b43c3  push    rdi
0x1800b43c4  sub     rsp, 30h
0x1800b43c8  xor     ebx, ebx
0x1800b43ca  xor     r9d, r9d; TokenInformationLength
0x1800b43cd  mov     [rax+10h], ebx
0x1800b43d0  lea     rax, [rax+10h]
0x1800b43d4  xor     r8d, r8d; TokenInformation
0x1800b43d7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800b43dc  mov     rsi, rcx
0x1800b43df  lea     edx, [rbx+0Ah]; TokenInformationClass
0x1800b43e2  call    cs:__imp_GetTokenInformation
0x1800b43e9  nop     dword ptr [rax+rax+00h]
0x1800b43ee  test    eax, eax
0x1800b43f0  jnz     short loc_1800B4451
0x1800b43f2  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x1800b43f6  xor     ecx, ecx; uFlags
0x1800b43f8  call    cs:__imp_LocalAlloc
0x1800b43ff  nop     dword ptr [rax+rax+00h]
0x1800b4404  mov     rdi, rax
0x1800b4407  test    rax, rax
0x1800b440a  jz      short loc_1800B4451
0x1800b440c  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x1800b4411  lea     rax, [rsp+38h+uBytes]
0x1800b4416  mov     r8, rdi; TokenInformation
0x1800b4419  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800b441e  lea     edx, [rbx+0Ah]; TokenInformationClass
0x1800b4421  mov     rcx, rsi; TokenHandle
0x1800b4424  call    cs:__imp_GetTokenInformation
0x1800b442b  nop     dword ptr [rax+rax+00h]
0x1800b4430  test    eax, eax
0x1800b4432  jz      short loc_1800B4442
0x1800b4434  movsxd  rbx, dword ptr [rdi+0Ch]
0x1800b4438  mov     ecx, [rdi+8]
0x1800b443b  shl     rbx, 20h
0x1800b443f  add     rbx, rcx
0x1800b4442  mov     rcx, rdi; hMem
0x1800b4445  call    cs:__imp_LocalFree
0x1800b444c  nop     dword ptr [rax+rax+00h]
0x1800b4451  mov     rsi, [rsp+38h+arg_10]
0x1800b4456  mov     rax, rbx
0x1800b4459  mov     rbx, [rsp+38h+arg_0]
0x1800b445e  add     rsp, 30h
0x1800b4462  pop     rdi
0x1800b4463  retn
```
