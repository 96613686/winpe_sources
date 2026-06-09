# AddSIDToKernelObjectDacl(void *,ulong,void *,void * *)

- ea: `0x180036994`
- end: `0x180036b75`
- name: `?AddSIDToKernelObjectDacl@@YAJPEAXK0PEAPEAX@Z`
- size: `481`
- prototype: `__int64 __fastcall(PSID pSid, __int64, void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800384f4`

## callees

- `0x18002c8d4`
- `0x180036994`
- `0x18003b2a4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800369e2`
- `KERNEL32!HeapAlloc` at `0x180036a7f`
- `KERNEL32!HeapAlloc` at `0x1800369e2`
- `KERNEL32!HeapAlloc` at `0x180036a7f`
- `KERNEL32!GetLastError` at `0x180036a0d`
- `KERNEL32!GetLastError` at `0x180036a4f`
- `KERNEL32!GetLastError` at `0x180036b14`
- `KERNEL32!GetLastError` at `0x180036a0d`
- `KERNEL32!GetLastError` at `0x180036a4f`
- `KERNEL32!GetLastError` at `0x180036b14`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180036a03`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180036a03`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180036b0a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180036b0a`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180036a45`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180036aa9`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180036a45`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180036aa9`
- `ADVAPI32!SetKernelObjectSecurity` at `0x180036b37`
- `ADVAPI32!SetKernelObjectSecurity` at `0x180036b37`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180036acf`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180036acf`

## pseudocode

```c
__int64 __fastcall AddSIDToKernelObjectDacl(PSID pSid, __int64 a2, void *a3, void **a4)
{
  void *v7; // rdi
  unsigned int v8; // ebx
  signed int LastError; // eax
  bool v10; // cc
  unsigned int v11; // r9d
  int v12; // eax
  PACL v13; // rsi
  signed int v14; // eax
  unsigned __int8 lpnLengthNeeded; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+28h] [rbp-50h]
  BOOL bDaclDefaulted; // [rsp+30h] [rbp-48h] BYREF
  BOOL bDaclPresent; // [rsp+34h] [rbp-44h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-40h] BYREF
  PACL v21; // [rsp+40h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v23; // [rsp+68h] [rbp-10h]
  DWORD nLengthNeeded; // [rsp+B8h] [rbp+40h] BYREF

  v23 = 0;
  nLengthNeeded = 0;
  pDacl = 0;
  v21 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  v7 = HeapAlloc(ghTapisrvHeap, 8u, 0x800u);
  if ( !v7 )
    return (unsigned int)-2147483580;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
LABEL_4:
    LastError = GetLastError();
    v8 = LastError;
    v10 = LastError <= 0;
    goto LABEL_5;
  }
  if ( GetKernelObjectSecurity(a3, 4u, v7, 0x800u, &nLengthNeeded) )
  {
LABEL_14:
    if ( GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v12 = SetSidOnAcl(pSid, pDacl, &v21, v11, lpnLengthNeeded, v17);
      v13 = v21;
      if ( v12 )
      {
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v21, 0)
          && SetKernelObjectSecurity(a3, 4u, pSecurityDescriptor) )
        {
          v8 = 0;
          *a4 = v7;
        }
        else
        {
          v14 = GetLastError();
          v8 = v14;
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
        }
      }
      else
      {
        v8 = -2147467259;
      }
      if ( v13 )
        ServerFree(v13);
      goto LABEL_24;
    }
    goto LABEL_4;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( nLengthNeeded > 0x800 && LastError == 234 )
  {
    ServerFree(v7);
    v7 = HeapAlloc(ghTapisrvHeap, 8u, nLengthNeeded);
    if ( !v7 )
      return (unsigned int)-2147483580;
    if ( !GetKernelObjectSecurity(a3, 4u, v7, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_4;
    goto LABEL_14;
  }
  v10 = LastError <= 0;
  if ( !LastError )
    goto LABEL_14;
LABEL_5:
  if ( !v10 )
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
  if ( v8 )
  {
    ServerFree(v7);
    *a4 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180036994  mov     [rsp-30h+nLengthNeeded], edx
0x180036998  push    rbp
0x180036999  push    rbx
0x18003699a  push    rsi
0x18003699b  push    rdi
0x18003699c  push    r14
0x18003699e  push    r15
0x1800369a0  mov     rbp, rsp
0x1800369a3  sub     rsp, 78h
0x1800369a7  xor     eax, eax
0x1800369a9  xorps   xmm0, xmm0
0x1800369ac  mov     r14, r8
0x1800369af  mov     [rbp+var_10], rax
0x1800369b3  mov     rsi, rcx
0x1800369b6  mov     [rbp+nLengthNeeded], eax
0x1800369b9  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800369c0  mov     r8d, 800h; dwBytes
0x1800369c6  lea     edx, [rax+8]; dwFlags
0x1800369c9  mov     [rbp+pDacl], rax
0x1800369cd  mov     r15, r9
0x1800369d0  mov     [rbp+var_38], rax
0x1800369d4  movups  [rbp+pSecurityDescriptor], xmm0
0x1800369d8  mov     [rbp+bDaclPresent], eax
0x1800369db  movups  [rbp+var_20], xmm0
0x1800369df  mov     [rbp+bDaclDefaulted], eax
0x1800369e2  call    cs:__imp_HeapAlloc
0x1800369e8  mov     rdi, rax
0x1800369eb  test    rax, rax
0x1800369ee  jnz     short loc_1800369FA
0x1800369f0  mov     ebx, 80000044h
0x1800369f5  jmp     loc_180036B66
0x1800369fa  mov     edx, 1; dwRevision
0x1800369ff  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180036a03  call    cs:__imp_InitializeSecurityDescriptor
0x180036a09  test    eax, eax
0x180036a0b  jnz     short loc_180036A2B
0x180036a0d  call    cs:__imp_GetLastError
0x180036a13  mov     ebx, eax
0x180036a15  test    eax, eax
0x180036a17  jle     loc_180036B53
0x180036a1d  movzx   ebx, ax
0x180036a20  or      ebx, 80070000h
0x180036a26  jmp     loc_180036B53
0x180036a2b  lea     rax, [rbp+nLengthNeeded]
0x180036a2f  mov     r9d, 800h; nLength
0x180036a35  mov     r8, rdi; pSecurityDescriptor
0x180036a38  mov     [rsp+78h+lpnLengthNeeded], rax; unsigned __int8
0x180036a3d  mov     edx, 4; RequestedInformation
0x180036a42  mov     rcx, r14; Handle
0x180036a45  call    cs:__imp_GetKernelObjectSecurity
0x180036a4b  test    eax, eax
0x180036a4d  jnz     short loc_180036AC0
0x180036a4f  call    cs:__imp_GetLastError
0x180036a55  cmp     [rbp+nLengthNeeded], 800h
0x180036a5c  mov     ebx, eax
0x180036a5e  jbe     short loc_180036AB8
0x180036a60  cmp     eax, 0EAh
0x180036a65  jnz     short loc_180036AB8
0x180036a67  mov     rcx, rdi; lpMem
0x180036a6a  call    ServerFree
0x180036a6f  mov     r8d, [rbp+nLengthNeeded]; dwBytes
0x180036a73  mov     edx, 8; dwFlags
0x180036a78  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180036a7f  call    cs:__imp_HeapAlloc
0x180036a85  mov     rdi, rax
0x180036a88  test    rax, rax
0x180036a8b  jz      loc_1800369F0
0x180036a91  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180036a95  lea     rax, [rbp+nLengthNeeded]
0x180036a99  mov     r8, rdi; pSecurityDescriptor
0x180036a9c  mov     [rsp+78h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180036aa1  mov     edx, 4; RequestedInformation
0x180036aa6  mov     rcx, r14; Handle
0x180036aa9  call    cs:__imp_GetKernelObjectSecurity
0x180036aaf  test    eax, eax
0x180036ab1  jnz     short loc_180036AC0
0x180036ab3  jmp     loc_180036A0D
0x180036ab8  test    eax, eax
0x180036aba  jnz     loc_180036A17
0x180036ac0  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180036ac4  mov     rcx, rdi; pSecurityDescriptor
0x180036ac7  lea     r8, [rbp+pDacl]; pDacl
0x180036acb  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180036acf  call    cs:__imp_GetSecurityDescriptorDacl
0x180036ad5  test    eax, eax
0x180036ad7  jz      loc_180036A0D
0x180036add  mov     rdx, [rbp+pDacl]; pAcl
0x180036ae1  lea     r8, [rbp+var_38]; struct _ACL **
0x180036ae5  mov     rcx, rsi; pSid
0x180036ae8  call    ?SetSidOnAcl@@YAJPEAXPEAU_ACL@@PEAPEAU1@KEH@Z; SetSidOnAcl(void *,_ACL *,_ACL * *,ulong,uchar,int)
0x180036aed  mov     rsi, [rbp+var_38]
0x180036af1  test    eax, eax
0x180036af3  jnz     short loc_180036AFC
0x180036af5  mov     ebx, 80004005h
0x180036afa  jmp     short loc_180036B46
0x180036afc  xor     r9d, r9d; bDaclDefaulted
0x180036aff  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180036b03  mov     r8, rsi; pDacl
0x180036b06  lea     edx, [r9+1]; bDaclPresent
0x180036b0a  call    cs:__imp_SetSecurityDescriptorDacl
0x180036b10  test    eax, eax
0x180036b12  jnz     short loc_180036B2B
0x180036b14  call    cs:__imp_GetLastError
0x180036b1a  mov     ebx, eax
0x180036b1c  test    eax, eax
0x180036b1e  jle     short loc_180036B46
0x180036b20  movzx   ebx, ax
0x180036b23  or      ebx, 80070000h
0x180036b29  jmp     short loc_180036B46
0x180036b2b  lea     r8, [rbp+pSecurityDescriptor]; SecurityDescriptor
0x180036b2f  mov     edx, 4; SecurityInformation
0x180036b34  mov     rcx, r14; Handle
0x180036b37  call    cs:__imp_SetKernelObjectSecurity
0x180036b3d  test    eax, eax
0x180036b3f  jz      short loc_180036B14
0x180036b41  xor     ebx, ebx
0x180036b43  mov     [r15], rdi
0x180036b46  test    rsi, rsi
0x180036b49  jz      short loc_180036B53
0x180036b4b  mov     rcx, rsi; lpMem
0x180036b4e  call    ServerFree
0x180036b53  test    ebx, ebx
0x180036b55  jz      short loc_180036B66
0x180036b57  mov     rcx, rdi; lpMem
0x180036b5a  call    ServerFree
0x180036b5f  mov     qword ptr [r15], 0
0x180036b66  mov     eax, ebx
0x180036b68  add     rsp, 78h
0x180036b6c  pop     r15
0x180036b6e  pop     r14
0x180036b70  pop     rdi
0x180036b71  pop     rsi
0x180036b72  pop     rbx
0x180036b73  pop     rbp
0x180036b74  retn
```
