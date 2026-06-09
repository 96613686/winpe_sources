# VmLogError

- ea: `0x140014be0`
- end: `0x140014d66`
- name: `VmLogError`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400049ac`
- `0x140014be0`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x140014d31`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140014d31`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140014c7a`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140014c7a`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140014c33`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140014c33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d48`

## pseudocode

```c
void VmLogError(PVOID *a1, int a2, unsigned __int16 a3, ...)
{
  const wchar_t **v3; // r13
  PVOID *v6; // rax
  PVOID v7; // r15
  char *ErrorLogEntry; // rax
  _WORD *v9; // rsi
  wchar_t *v10; // rdi
  size_t v11; // rbx
  size_t v12; // rbx
  unsigned __int16 i; // r14
  const wchar_t *v14; // r8
  size_t v15; // rbx
  ULONG v16; // [rsp+28h] [rbp-30h]
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+30h] [rbp-28h] BYREF
  size_t pcbRemaining; // [rsp+38h] [rbp-20h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+40h] [rbp-18h] BYREF
  va_list va; // [rsp+B8h] [rbp+60h] BYREF

  va_start(va, a3);
  pcbRemaining = 0;
  va_copy((va_list)v3, va);
  DosName = 0;
  if ( a1 )
    v6 = a1;
  else
    v6 = (PVOID *)((char *)VmRootExtension + 32);
  v7 = *v6;
  ErrorLogEntry = (char *)IoAllocateErrorLogEntry(*v6, 0xF0u);
  v9 = ErrorLogEntry;
  if ( !ErrorLogEntry )
    goto LABEL_17;
  *((_DWORD *)ErrorLogEntry + 3) = a2;
  *(_DWORD *)(ErrorLogEntry + 2) = 0;
  v10 = (wchar_t *)(ErrorLogEntry + 40);
  *((_WORD *)ErrorLogEntry + 3) = 40;
  v11 = 200;
  ppszDestEnd = (NTSTRSAFE_PWSTR)(ErrorLogEntry + 40);
  pcbRemaining = 200;
  if ( a1 )
  {
    if ( IoVolumeDeviceToDosName(v7, &DosName) < 0
      || DosName.Length < 2u
      || RtlStringCbCopyExW(v10, 0xC8u, DosName.Buffer, &ppszDestEnd, &pcbRemaining, v16) < 0 )
    {
      goto LABEL_17;
    }
    v12 = pcbRemaining;
    v10 = ppszDestEnd + 1;
    ++v9[2];
    v11 = v12 - 2;
    ppszDestEnd = v10;
    pcbRemaining = v11;
  }
  for ( i = 0; i < a3 && v11; ++i )
  {
    v14 = *v3++;
    if ( !v14 || RtlStringCbCopyExW(v10, v11, v14, &ppszDestEnd, &pcbRemaining, v16) < 0 )
      goto LABEL_17;
    v15 = pcbRemaining;
    v10 = ppszDestEnd + 1;
    ++v9[2];
    v11 = v15 - 2;
    ppszDestEnd = v10;
    pcbRemaining = v11;
  }
  IoWriteErrorLogEntry(v9);
LABEL_17:
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
}

```

## disassembly

```asm
0x140014be0  mov     [rsp-40h+arg_10], r8w
0x140014be6  mov     [rsp-40h+arg_18], r9
0x140014beb  push    rbp
0x140014bec  push    rbx
0x140014bed  push    rsi
0x140014bee  push    rdi
0x140014bef  push    r12
0x140014bf1  push    r13
0x140014bf3  push    r14
0x140014bf5  push    r15
0x140014bf7  mov     rbp, rsp
0x140014bfa  sub     rsp, 58h
0x140014bfe  mov     [rbp+var_20], 0
0x140014c06  xorps   xmm0, xmm0
0x140014c09  lea     r13, [rbp+arg_18]
0x140014c0d  mov     ebx, edx
0x140014c0f  mov     r14, rcx
0x140014c12  movups  xmmword ptr [rbp+DosName.Length], xmm0
0x140014c16  test    rcx, rcx
0x140014c19  jz      short loc_140014C20
0x140014c1b  mov     rax, rcx
0x140014c1e  jmp     short loc_140014C2B
0x140014c20  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140014c27  add     rax, 20h ; ' '
0x140014c2b  mov     r15, [rax]
0x140014c2e  mov     dl, 0F0h; EntrySize
0x140014c30  mov     rcx, r15; IoObject
0x140014c33  call    cs:__imp_IoAllocateErrorLogEntry
0x140014c3a  nop     dword ptr [rax+rax+00h]
0x140014c3f  mov     rsi, rax
0x140014c42  test    rax, rax
0x140014c45  jz      loc_140014D3D
0x140014c4b  xor     ecx, ecx
0x140014c4d  mov     [rax+0Ch], ebx
0x140014c50  mov     [rax+2], ecx
0x140014c53  lea     rdi, [rax+28h]
0x140014c57  mov     word ptr [rax+6], 28h ; '('
0x140014c5d  mov     ebx, 0C8h
0x140014c62  mov     [rbp+ppszDestEnd], rdi
0x140014c66  mov     [rbp+var_20], rbx
0x140014c6a  lea     r12d, [rcx+2]
0x140014c6e  test    r14, r14
0x140014c71  jz      short loc_140014CD6
0x140014c73  lea     rdx, [rbp+DosName]; DosName
0x140014c77  mov     rcx, r15; VolumeDeviceObject
0x140014c7a  call    cs:__imp_IoVolumeDeviceToDosName
0x140014c81  nop     dword ptr [rax+rax+00h]
0x140014c86  test    eax, eax
0x140014c88  js      loc_140014D3D
0x140014c8e  cmp     [rbp+DosName.Length], r12w
0x140014c93  jb      loc_140014D3D
0x140014c99  mov     r8, [rbp+DosName.Buffer]; pszSrc
0x140014c9d  lea     rax, [rbp+var_20]
0x140014ca1  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x140014ca5  mov     [rsp+58h+pcbRemaining], rax; pcbRemaining
0x140014caa  mov     edx, ebx; cbDest
0x140014cac  mov     rcx, rdi; pszDest
0x140014caf  call    RtlStringCbCopyExW
0x140014cb4  test    eax, eax
0x140014cb6  js      loc_140014D3D
0x140014cbc  mov     rdi, [rbp+ppszDestEnd]
0x140014cc0  mov     rbx, [rbp+var_20]
0x140014cc4  add     rdi, r12
0x140014cc7  inc     word ptr [rsi+4]
0x140014ccb  sub     rbx, r12
0x140014cce  mov     [rbp+ppszDestEnd], rdi
0x140014cd2  mov     [rbp+var_20], rbx
0x140014cd6  xor     r14d, r14d
0x140014cd9  cmp     r14w, [rbp+arg_10]
0x140014cde  jnb     short loc_140014D2E
0x140014ce0  test    rbx, rbx
0x140014ce3  jz      short loc_140014D2E
0x140014ce5  mov     r8, [r13+0]; pszSrc
0x140014ce9  add     r13, 8
0x140014ced  test    r8, r8
0x140014cf0  jz      short loc_140014D3D
0x140014cf2  lea     rax, [rbp+var_20]
0x140014cf6  mov     rdx, rbx; cbDest
0x140014cf9  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x140014cfd  mov     [rsp+58h+pcbRemaining], rax; pcbRemaining
0x140014d02  mov     rcx, rdi; pszDest
0x140014d05  call    RtlStringCbCopyExW
0x140014d0a  test    eax, eax
0x140014d0c  js      short loc_140014D3D
0x140014d0e  mov     rdi, [rbp+ppszDestEnd]
0x140014d12  mov     rbx, [rbp+var_20]
0x140014d16  add     rdi, r12
0x140014d19  inc     word ptr [rsi+4]
0x140014d1d  sub     rbx, r12
0x140014d20  mov     [rbp+ppszDestEnd], rdi
0x140014d24  inc     r14w
0x140014d28  mov     [rbp+var_20], rbx
0x140014d2c  jmp     short loc_140014CD9
0x140014d2e  mov     rcx, rsi; ElEntry
0x140014d31  call    cs:__imp_IoWriteErrorLogEntry
0x140014d38  nop     dword ptr [rax+rax+00h]
0x140014d3d  mov     rcx, [rbp+DosName.Buffer]; P
0x140014d41  test    rcx, rcx
0x140014d44  jz      short loc_140014D54
0x140014d46  xor     edx, edx; Tag
0x140014d48  call    cs:__imp_ExFreePoolWithTag
0x140014d4f  nop     dword ptr [rax+rax+00h]
0x140014d54  add     rsp, 58h
0x140014d58  pop     r15
0x140014d5a  pop     r14
0x140014d5c  pop     r13
0x140014d5e  pop     r12
0x140014d60  pop     rdi
0x140014d61  pop     rsi
0x140014d62  pop     rbx
0x140014d63  pop     rbp
0x140014d64  retn
```
