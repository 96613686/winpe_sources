# IsOwnedBySid

- ea: `0x180027364`
- end: `0x18002745a`
- name: `IsOwnedBySid`
- size: `246`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID pSid2)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180026820`

## callees

- `0x180002a00`
- `0x180002ff0`
- `0x180027364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273a2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180027394`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800273ed`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180027394`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800273ed`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180027415`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180027415`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002742c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002742c`

## pseudocode

```c
__int64 __fastcall IsOwnedBySid(HANDLE Handle, PSID pSid2)
{
  void *v4; // rdi
  unsigned int v5; // ebx
  PSID pOwner; // [rsp+30h] [rbp-18h] BYREF
  DWORD nLengthNeeded; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp+20h] BYREF

  nLengthNeeded = 0;
  if ( !GetKernelObjectSecurity(Handle, 1u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
  {
    if ( nLengthNeeded )
    {
      v4 = operator new(nLengthNeeded, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        if ( GetKernelObjectSecurity(Handle, 1u, v4, nLengthNeeded, &nLengthNeeded) )
        {
          pOwner = 0;
          bOwnerDefaulted = 0;
          if ( GetSecurityDescriptorOwner(v4, &pOwner, &bOwnerDefaulted) )
          {
            if ( pOwner )
            {
              v5 = EqualSid(pOwner, pSid2);
              operator delete(v4);
              return v5;
            }
          }
        }
        operator delete(v4);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027364  mov     rax, rsp
0x180027367  mov     [rax+8], rbx
0x18002736b  mov     [rax+10h], rsi
0x18002736f  push    rdi
0x180027370  sub     rsp, 40h
0x180027374  xor     r9d, r9d; nLength
0x180027377  mov     dword ptr [rax+18h], 0
0x18002737e  mov     rsi, rdx
0x180027381  lea     rax, [rax+18h]
0x180027385  xor     r8d, r8d; pSecurityDescriptor
0x180027388  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002738d  mov     rbx, rcx
0x180027390  lea     edx, [r9+1]; RequestedInformation
0x180027394  call    cs:__imp_GetKernelObjectSecurity
0x18002739a  test    eax, eax
0x18002739c  jnz     loc_180027448
0x1800273a2  call    cs:__imp_GetLastError
0x1800273a8  cmp     eax, 7Ah ; 'z'
0x1800273ab  jnz     loc_180027448
0x1800273b1  mov     eax, [rsp+48h+nLengthNeeded]
0x1800273b5  test    eax, eax
0x1800273b7  jz      loc_180027448
0x1800273bd  mov     ecx, eax; unsigned __int64
0x1800273bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800273c6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800273cb  mov     rdi, rax
0x1800273ce  test    rax, rax
0x1800273d1  jz      short loc_180027448
0x1800273d3  mov     r9d, [rsp+48h+nLengthNeeded]; nLength
0x1800273d8  lea     rax, [rsp+48h+nLengthNeeded]
0x1800273dd  mov     r8, rdi; pSecurityDescriptor
0x1800273e0  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800273e5  mov     edx, 1; RequestedInformation
0x1800273ea  mov     rcx, rbx; Handle
0x1800273ed  call    cs:__imp_GetKernelObjectSecurity
0x1800273f3  test    eax, eax
0x1800273f5  jz      short loc_180027440
0x1800273f7  lea     r8, [rsp+48h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800273fc  mov     [rsp+48h+pOwner], 0
0x180027405  lea     rdx, [rsp+48h+pOwner]; pOwner
0x18002740a  mov     [rsp+48h+bOwnerDefaulted], 0
0x180027412  mov     rcx, rdi; pSecurityDescriptor
0x180027415  call    cs:__imp_GetSecurityDescriptorOwner
0x18002741b  test    eax, eax
0x18002741d  jz      short loc_180027440
0x18002741f  mov     rcx, [rsp+48h+pOwner]; pSid1
0x180027424  test    rcx, rcx
0x180027427  jz      short loc_180027440
0x180027429  mov     rdx, rsi; pSid2
0x18002742c  call    cs:__imp_EqualSid
0x180027432  mov     rcx, rdi; Block
0x180027435  mov     ebx, eax
0x180027437  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002743c  mov     eax, ebx
0x18002743e  jmp     short loc_18002744A
0x180027440  mov     rcx, rdi; Block
0x180027443  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027448  xor     eax, eax
0x18002744a  mov     rbx, [rsp+48h+arg_0]
0x18002744f  mov     rsi, [rsp+48h+arg_8]
0x180027454  add     rsp, 40h
0x180027458  pop     rdi
0x180027459  retn
```
