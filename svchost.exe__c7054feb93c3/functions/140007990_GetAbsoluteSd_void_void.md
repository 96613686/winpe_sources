# GetAbsoluteSd(void *,void * *)

- ea: `0x140007990`
- end: `0x140007b22`
- name: `?GetAbsoluteSd@@YAKPEAXPEAPEAX@Z`
- size: `402`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140007ebc`

## callees

- `0x140007990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007add`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007a10`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007ad3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007a10`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007ad3`
- `ntdll!RtlAllocateHeap` at `0x140007a55`
- `ntdll!RtlAllocateHeap` at `0x140007a55`
- `ntdll!RtlFreeHeap` at `0x140007af7`
- `ntdll!RtlFreeHeap` at `0x140007af7`

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
0x140007990  mov     r11, rsp
0x140007993  mov     [r11+8], rbx
0x140007997  mov     [r11+10h], rsi
0x14000799b  push    rbp
0x14000799c  push    rdi
0x14000799d  push    r14
0x14000799f  mov     rbp, rsp
0x1400079a2  sub     rsp, 70h
0x1400079a6  lea     rax, [rbp+dwPrimaryGroupSize]
0x1400079aa  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 0
0x1400079b1  mov     [r11-38h], rax
0x1400079b5  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1400079b9  mov     qword ptr [r11-40h], 0
0x1400079c1  lea     rax, [rbp+dwOwnerSize]
0x1400079c5  mov     [r11-48h], rax
0x1400079c9  mov     rsi, rdx
0x1400079cc  mov     qword ptr [r11-50h], 0
0x1400079d4  lea     rax, [rbp+dwSaclSize]
0x1400079d8  mov     [r11-58h], rax
0x1400079dc  xor     r9d, r9d; pDacl
0x1400079df  lea     rax, [rbp+dwDaclSize]
0x1400079e3  mov     qword ptr [r11-60h], 0
0x1400079eb  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1400079ed  mov     [r11-68h], rax
0x1400079f1  mov     r14, rcx
0x1400079f4  mov     [rbp+dwDaclSize], 0
0x1400079fb  mov     [rbp+dwSaclSize], 0
0x140007a02  mov     [rbp+dwOwnerSize], 0
0x140007a09  mov     [rbp+dwPrimaryGroupSize], 0
0x140007a10  call    cs:__imp_MakeAbsoluteSD
0x140007a16  test    eax, eax
0x140007a18  jnz     loc_140007B06
0x140007a1e  call    cs:__imp_GetLastError
0x140007a24  mov     ebx, eax
0x140007a26  cmp     eax, 7Ah ; 'z'
0x140007a29  jnz     loc_140007B0B
0x140007a2f  mov     r8d, [rbp+dwPrimaryGroupSize]
0x140007a33  lea     ebx, [rax-72h]
0x140007a36  add     r8d, [rbp+dwOwnerSize]
0x140007a3a  mov     edx, ebx; Flags
0x140007a3c  add     r8d, [rbp+dwSaclSize]
0x140007a40  mov     rcx, gs:60h
0x140007a49  add     r8d, [rbp+dwDaclSize]
0x140007a4d  add     r8d, [rbp+dwAbsoluteSecurityDescriptorSize]; Size
0x140007a51  mov     rcx, [rcx+30h]; HeapHandle
0x140007a55  call    cs:__imp_RtlAllocateHeap
0x140007a5b  mov     rdi, rax
0x140007a5e  test    rax, rax
0x140007a61  jz      loc_140007B0B
0x140007a67  mov     r8d, [rbp+dwAbsoluteSecurityDescriptorSize]
0x140007a6b  mov     edx, [rbp+dwDaclSize]
0x140007a6e  mov     eax, [rbp+dwSaclSize]
0x140007a71  mov     r10d, [rbp+dwOwnerSize]
0x140007a75  add     r10, rax
0x140007a78  lea     r9, [r8+rdi]; pDacl
0x140007a7c  add     r10, rdx
0x140007a7f  lea     rcx, [rax+rdx]
0x140007a83  add     r10, r8
0x140007a86  lea     rax, [rdx+r8]
0x140007a8a  add     rcx, r8
0x140007a8d  add     rcx, rdi
0x140007a90  lea     rdx, [rbp+dwPrimaryGroupSize]
0x140007a94  mov     [rsp+70h+lpdwPrimaryGroupSize], rdx; lpdwPrimaryGroupSize
0x140007a99  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140007a9d  add     rax, rdi
0x140007aa0  lea     rdx, [rbp+dwOwnerSize]
0x140007aa4  add     r10, rdi
0x140007aa7  mov     [rsp+70h+pPrimaryGroup], r10; pPrimaryGroup
0x140007aac  mov     [rsp+70h+lpdwOwnerSize], rdx; lpdwOwnerSize
0x140007ab1  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x140007ab4  mov     [rsp+70h+pOwner], rcx; pOwner
0x140007ab9  lea     rcx, [rbp+dwSaclSize]
0x140007abd  mov     [rsp+70h+lpdwSaclSize], rcx; lpdwSaclSize
0x140007ac2  mov     rcx, r14; pSelfRelativeSecurityDescriptor
0x140007ac5  mov     [rsp+70h+pSacl], rax; pSacl
0x140007aca  lea     rax, [rbp+dwDaclSize]
0x140007ace  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x140007ad3  call    cs:__imp_MakeAbsoluteSD
0x140007ad9  test    eax, eax
0x140007adb  jnz     short loc_140007AFF
0x140007add  call    cs:__imp_GetLastError
0x140007ae3  mov     rcx, gs:60h
0x140007aec  mov     r8, rdi; P
0x140007aef  xor     edx, edx; Flags
0x140007af1  mov     ebx, eax
0x140007af3  mov     rcx, [rcx+30h]; HeapHandle
0x140007af7  call    cs:__imp_RtlFreeHeap
0x140007afd  jmp     short loc_140007B0B
0x140007aff  xor     ebx, ebx
0x140007b01  mov     [rsi], rdi
0x140007b04  jmp     short loc_140007B0B
0x140007b06  mov     ebx, 57h ; 'W'
0x140007b0b  lea     r11, [rsp+70h+var_s0]
0x140007b10  mov     eax, ebx
0x140007b12  mov     rbx, [r11+20h]
0x140007b16  mov     rsi, [r11+28h]
0x140007b1a  mov     rsp, r11
0x140007b1d  pop     r14
0x140007b1f  pop     rdi
0x140007b20  pop     rbp
0x140007b21  retn
```
