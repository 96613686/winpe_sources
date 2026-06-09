# GetAbsoluteSd(void *,void * *)

- ea: `0x140007e80`
- end: `0x140008037`
- name: `?GetAbsoluteSd@@YAKPEAXPEAPEAX@Z`
- size: `439`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008474`

## callees

- `0x140007e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fe5`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007f00`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007fd5`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007f00`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007fd5`
- `ntdll!RtlAllocateHeap` at `0x140007f51`
- `ntdll!RtlAllocateHeap` at `0x140007f51`
- `ntdll!RtlFreeHeap` at `0x140008005`
- `ntdll!RtlFreeHeap` at `0x140008005`

## pseudocode

```c
__int64 __fastcall GetAbsoluteSd(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **a2)
{
  DWORD LastError; // ebx
  char *Heap; // rax
  void *v6; // rdi
  DWORD dwDaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+64h] [rbp-Ch] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwOwnerSize; // [rsp+A0h] [rbp+30h] BYREF
  DWORD dwSaclSize; // [rsp+A8h] [rbp+38h] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( MakeAbsoluteSD(
         pSelfRelativeSecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    return 87;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      LastError = 8;
      Heap = (char *)RtlAllocateHeap(
                       NtCurrentPeb()->ProcessHeap,
                       8u,
                       dwAbsoluteSecurityDescriptorSize + dwDaclSize + dwSaclSize + dwOwnerSize + dwPrimaryGroupSize);
      v6 = Heap;
      if ( Heap )
      {
        if ( MakeAbsoluteSD(
               pSelfRelativeSecurityDescriptor,
               Heap,
               &dwAbsoluteSecurityDescriptorSize,
               (PACL)&Heap[dwAbsoluteSecurityDescriptorSize],
               &dwDaclSize,
               (PACL)&Heap[dwDaclSize + (unsigned __int64)dwAbsoluteSecurityDescriptorSize],
               &dwSaclSize,
               &Heap[dwAbsoluteSecurityDescriptorSize + dwSaclSize + (unsigned __int64)dwDaclSize],
               &dwOwnerSize,
               &Heap[dwAbsoluteSecurityDescriptorSize + dwDaclSize + dwSaclSize + (unsigned __int64)dwOwnerSize],
               &dwPrimaryGroupSize) )
        {
          LastError = 0;
          *a2 = v6;
        }
        else
        {
          LastError = GetLastError();
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x140007e80  mov     r11, rsp
0x140007e83  mov     [r11+8], rbx
0x140007e87  mov     [r11+10h], rsi
0x140007e8b  push    rbp
0x140007e8c  push    rdi
0x140007e8d  push    r14
0x140007e8f  mov     rbp, rsp
0x140007e92  sub     rsp, 70h
0x140007e96  lea     rax, [rbp+dwPrimaryGroupSize]
0x140007e9a  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 0
0x140007ea1  mov     [r11-38h], rax
0x140007ea5  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140007ea9  mov     qword ptr [r11-40h], 0
0x140007eb1  lea     rax, [rbp+dwOwnerSize]
0x140007eb5  mov     [r11-48h], rax
0x140007eb9  mov     rsi, rdx
0x140007ebc  mov     qword ptr [r11-50h], 0
0x140007ec4  lea     rax, [rbp+dwSaclSize]
0x140007ec8  mov     [r11-58h], rax
0x140007ecc  xor     r9d, r9d; pDacl
0x140007ecf  lea     rax, [rbp+dwDaclSize]
0x140007ed3  mov     qword ptr [r11-60h], 0
0x140007edb  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140007edd  mov     [r11-68h], rax
0x140007ee1  mov     r14, rcx
0x140007ee4  mov     [rbp+dwDaclSize], 0
0x140007eeb  mov     [rbp+dwSaclSize], 0
0x140007ef2  mov     [rbp+dwOwnerSize], 0
0x140007ef9  mov     [rbp+dwPrimaryGroupSize], 0
0x140007f00  call    cs:__imp_MakeAbsoluteSD
0x140007f07  nop     dword ptr [rax+rax+00h]
0x140007f0c  test    eax, eax
0x140007f0e  jnz     loc_14000801A
0x140007f14  call    cs:__imp_GetLastError
0x140007f1b  nop     dword ptr [rax+rax+00h]
0x140007f20  mov     ebx, eax
0x140007f22  cmp     eax, 7Ah ; 'z'
0x140007f25  jnz     loc_14000801F
0x140007f2b  mov     r8d, [rbp+dwPrimaryGroupSize]
0x140007f2f  lea     ebx, [rax-72h]
0x140007f32  add     r8d, [rbp+dwOwnerSize]
0x140007f36  mov     edx, ebx; Flags
0x140007f38  add     r8d, [rbp+dwSaclSize]
0x140007f3c  mov     rcx, gs:60h
0x140007f45  add     r8d, [rbp+dwDaclSize]
0x140007f49  add     r8d, [rbp+dwAbsoluteSecurityDescriptorSize]; Size
0x140007f4d  mov     rcx, [rcx+30h]; HeapHandle
0x140007f51  call    cs:__imp_RtlAllocateHeap
0x140007f58  nop     dword ptr [rax+rax+00h]
0x140007f5d  mov     rdi, rax
0x140007f60  test    rax, rax
0x140007f63  jz      loc_14000801F
0x140007f69  mov     r8d, [rbp+dwAbsoluteSecurityDescriptorSize]
0x140007f6d  mov     edx, [rbp+dwDaclSize]
0x140007f70  mov     eax, [rbp+dwSaclSize]
0x140007f73  mov     r10d, [rbp+dwOwnerSize]
0x140007f77  add     r10, rax
0x140007f7a  lea     r9, [r8+rdi]; pDacl
0x140007f7e  add     r10, rdx
0x140007f81  lea     rcx, [rax+rdx]
0x140007f85  add     r10, r8
0x140007f88  lea     rax, [rdx+r8]
0x140007f8c  add     rcx, r8
0x140007f8f  add     rcx, rdi
0x140007f92  lea     rdx, [rbp+dwPrimaryGroupSize]
0x140007f96  mov     [rsp+70h+lpdwPrimaryGroupSize], rdx; lpdwPrimaryGroupSize
0x140007f9b  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140007f9f  add     rax, rdi
0x140007fa2  lea     rdx, [rbp+dwOwnerSize]
0x140007fa6  add     r10, rdi
0x140007fa9  mov     [rsp+70h+pPrimaryGroup], r10; pPrimaryGroup
0x140007fae  mov     [rsp+70h+lpdwOwnerSize], rdx; lpdwOwnerSize
0x140007fb3  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x140007fb6  mov     [rsp+70h+pOwner], rcx; pOwner
0x140007fbb  lea     rcx, [rbp+dwSaclSize]
0x140007fbf  mov     [rsp+70h+lpdwSaclSize], rcx; lpdwSaclSize
0x140007fc4  mov     rcx, r14; pSelfRelativeSecurityDescriptor
0x140007fc7  mov     [rsp+70h+pSacl], rax; pSacl
0x140007fcc  lea     rax, [rbp+dwDaclSize]
0x140007fd0  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x140007fd5  call    cs:__imp_MakeAbsoluteSD
0x140007fdc  nop     dword ptr [rax+rax+00h]
0x140007fe1  test    eax, eax
0x140007fe3  jnz     short loc_140008013
0x140007fe5  call    cs:__imp_GetLastError
0x140007fec  nop     dword ptr [rax+rax+00h]
0x140007ff1  mov     rcx, gs:60h
0x140007ffa  mov     r8, rdi; P
0x140007ffd  xor     edx, edx; Flags
0x140007fff  mov     ebx, eax
0x140008001  mov     rcx, [rcx+30h]; HeapHandle
0x140008005  call    cs:__imp_RtlFreeHeap
0x14000800c  nop     dword ptr [rax+rax+00h]
0x140008011  jmp     short loc_14000801F
0x140008013  xor     ebx, ebx
0x140008015  mov     [rsi], rdi
0x140008018  jmp     short loc_14000801F
0x14000801a  mov     ebx, 57h ; 'W'
0x14000801f  lea     r11, [rsp+70h+var_s0]
0x140008024  mov     eax, ebx
0x140008026  mov     rbx, [r11+20h]
0x14000802a  mov     rsi, [r11+28h]
0x14000802e  mov     rsp, r11
0x140008031  pop     r14
0x140008033  pop     rdi
0x140008034  pop     rbp
0x140008035  retn
```
