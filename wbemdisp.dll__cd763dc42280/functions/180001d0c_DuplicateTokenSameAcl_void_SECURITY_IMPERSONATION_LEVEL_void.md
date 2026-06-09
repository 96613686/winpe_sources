# DuplicateTokenSameAcl(void *,_SECURITY_IMPERSONATION_LEVEL,void * *)

- ea: `0x180001d0c`
- end: `0x180001e0e`
- name: `?DuplicateTokenSameAcl@@YAHPEAXW4_SECURITY_IMPERSONATION_LEVEL@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE Handle, enum _SECURITY_IMPERSONATION_LEVEL, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800036e0`
- `0x180006850`
- `0x180008230`
- `0x180008800`

## callees

- `0x180001d0c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001d52`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001d99`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001d52`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DuplicateTokenSameAcl(HANDLE Handle, unsigned int a2, void **a3)
{
  unsigned int KernelObjectSecurity; // ebx
  HLOCAL v7; // rax
  void *v8; // rbx
  unsigned int v9; // edi
  _QWORD v11[3]; // [rsp+48h] [rbp-18h] BYREF
  DWORD nLengthNeeded; // [rsp+98h] [rbp+38h] BYREF

  if ( !s_pfnDuplicateTokenEx )
    return 0;
  nLengthNeeded = 0;
  KernelObjectSecurity = GetKernelObjectSecurity(Handle, 4u, 0, 0, &nLengthNeeded);
  if ( KernelObjectSecurity || GetLastError() != 122 )
    return KernelObjectSecurity;
  v7 = LocalAlloc(0x40u, nLengthNeeded);
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( GetKernelObjectSecurity(Handle, 4u, v7, nLengthNeeded, &nLengthNeeded) )
  {
    v11[0] = 24;
    v11[2] = 0;
    v11[1] = v8;
    v9 = ((__int64 (__fastcall *)(HANDLE, __int64, _QWORD *, _QWORD, int, void **))s_pfnDuplicateTokenEx)(
           Handle,
           44,
           v11,
           a2,
           2,
           a3);
  }
  else
  {
    v9 = 0;
  }
  LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180001d0c  mov     [rsp-18h+arg_0], rbx
0x180001d11  mov     [rsp-18h+arg_8], rsi
0x180001d16  push    rbp
0x180001d17  push    rdi
0x180001d18  push    r14
0x180001d1a  mov     rbp, rsp
0x180001d1d  sub     rsp, 60h
0x180001d21  mov     rsi, r8
0x180001d24  mov     r14d, edx
0x180001d27  mov     rdi, rcx
0x180001d2a  cmp     cs:?s_pfnDuplicateTokenEx@@3P6AHPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@PEAPEAX@ZEA, 0; int (*s_pfnDuplicateTokenEx)(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,void * *)
0x180001d32  jz      loc_180001DC9
0x180001d38  mov     [rbp+nLengthNeeded], 0
0x180001d3f  lea     rax, [rbp+nLengthNeeded]
0x180001d43  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180001d48  xor     r9d, r9d; nLength
0x180001d4b  xor     r8d, r8d; pSecurityDescriptor
0x180001d4e  lea     edx, [r9+4]; RequestedInformation
0x180001d52  call    cs:__imp_GetKernelObjectSecurity
0x180001d58  mov     ebx, eax
0x180001d5a  test    eax, eax
0x180001d5c  jnz     short loc_180001DB2
0x180001d5e  call    cs:__imp_GetLastError
0x180001d64  cmp     eax, 7Ah ; 'z'
0x180001d67  jnz     short loc_180001DB2
0x180001d69  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180001d6c  lea     ecx, [rbx+40h]; uFlags
0x180001d6f  call    cs:__imp_LocalAlloc
0x180001d75  mov     rbx, rax
0x180001d78  test    rax, rax
0x180001d7b  jz      short loc_180001DC9
0x180001d7d  mov     [rbp+var_20], rax
0x180001d81  lea     rax, [rbp+nLengthNeeded]
0x180001d85  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180001d8a  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180001d8e  mov     r8, rbx; pSecurityDescriptor
0x180001d91  mov     edx, 4; RequestedInformation
0x180001d96  mov     rcx, rdi; Handle
0x180001d99  call    cs:__imp_GetKernelObjectSecurity
0x180001d9f  test    eax, eax
0x180001da1  jnz     short loc_180001DCD
0x180001da3  xor     edi, edi
0x180001da5  mov     rcx, rbx; hMem
0x180001da8  call    cs:__imp_LocalFree
0x180001dae  mov     eax, edi
0x180001db0  jmp     short loc_180001DB4
0x180001db2  mov     eax, ebx
0x180001db4  lea     r11, [rsp+60h+var_s0]
0x180001db9  mov     rbx, [r11+20h]
0x180001dbd  mov     rsi, [r11+28h]
0x180001dc1  mov     rsp, r11
0x180001dc4  pop     r14
0x180001dc6  pop     rdi
0x180001dc7  pop     rbp
0x180001dc8  retn
0x180001dc9  xor     eax, eax
0x180001dcb  jmp     short loc_180001DB4
0x180001dcd  mov     [rbp+var_18], 18h
0x180001dd5  mov     [rbp+var_8], 0
0x180001ddd  mov     [rbp+var_10], rbx
0x180001de1  mov     [rsp+60h+var_38], rsi
0x180001de6  mov     dword ptr [rsp+60h+lpnLengthNeeded], 2
0x180001dee  mov     r9d, r14d
0x180001df1  lea     r8, [rbp+var_18]
0x180001df5  mov     edx, 2Ch ; ','
0x180001dfa  mov     rcx, rdi
0x180001dfd  mov     rax, cs:?s_pfnDuplicateTokenEx@@3P6AHPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@PEAPEAX@ZEA; int (*s_pfnDuplicateTokenEx)(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,void * *)
0x180001e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e09  mov     edi, eax
0x180001e0b  jmp     short loc_180001DA5
```
