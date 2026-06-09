# NtCreateSection

- ea: `0x14005c98c`
- end: `0x14005cad2`
- name: `NtCreateSection`
- size: `326`
- prototype: `NTSTATUS __stdcall(PHANDLE SectionHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PLARGE_INTEGER MaximumSize, ULONG SectionPageProtection, ULONG AllocationAttributes, HANDLE FileHandle)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x140002ef0`
- `0x14005c98c`
- `0x140063578`
- `0x1400a0df8`
- `0x1400eff90`
- `0x1400f0140`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
NTSTATUS __stdcall NtCreateSection(
        PHANDLE SectionHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PLARGE_INTEGER MaximumSize,
        ULONG SectionPageProtection,
        ULONG AllocationAttributes,
        HANDLE FileHandle)
{
  void *v11; // rdi
  NTSTATUS result; // eax
  char v13; // si
  __int64 ULong64FromUser; // rax
  __int64 v15; // r8
  NTSTATUS NtSecureImage; // ebx
  __int64 v17; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h] BYREF
  void *v19; // [rsp+58h] [rbp-40h] BYREF

  v17 = 0;
  v11 = 0;
  v19 = 0;
  v18 = 0;
  if ( (AllocationAttributes & 0x1000000) == 0 )
    return -1073741580;
  v13 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  if ( v13 == 1 )
  {
    ULong64FromUser = RtlReadULong64FromUser(SectionHandle);
    RtlWriteULong64ToUser(SectionHandle, ULong64FromUser);
  }
  v17 = 0;
  result = NkCreateSection(
             &v17,
             DesiredAccess,
             ObjectAttributes,
             MaximumSize,
             SectionPageProtection,
             AllocationAttributes,
             FileHandle);
  if ( result >= 0 )
  {
    LOBYTE(v15) = v13;
    NtSecureImage = SkmmGetNtSecureImage(v17, 0, v15, &v18);
    if ( NtSecureImage >= 0 )
    {
      NtSecureImage = SkobCreateHandle(v18, 0, v17, (__int64)&v19);
      v11 = v19;
    }
    if ( !v11 )
      NkClose(v17);
    if ( v13 )
      RtlWriteULong64ToUser(SectionHandle, (__int64)v11);
    else
      *SectionHandle = v11;
    if ( v18 )
      SkobDereferenceObject(v18);
    return NtSecureImage;
  }
  return result;
}

```

## disassembly

```asm
0x14005c98c  push    rbx
0x14005c98e  push    rsi
0x14005c98f  push    rdi
0x14005c990  push    r12
0x14005c992  push    r13
0x14005c994  push    r14
0x14005c996  push    r15
0x14005c998  sub     rsp, 60h
0x14005c99c  mov     r15, r9
0x14005c99f  mov     r12, r8
0x14005c9a2  mov     r13d, edx
0x14005c9a5  mov     r14, rcx
0x14005c9a8  mov     [rsp+98h+var_50], 0
0x14005c9b1  xor     edi, edi
0x14005c9b3  mov     [rsp+98h+var_40], rdi
0x14005c9b8  mov     [rsp+98h+var_48], rdi
0x14005c9bd  mov     ebx, [rsp+98h+AllocationAttributes]
0x14005c9c4  bt      ebx, 18h
0x14005c9c8  jb      short loc_14005C9D4
0x14005c9ca  mov     eax, 0C00000F4h
0x14005c9cf  jmp     loc_14005CAC1
0x14005c9d4  mov     rax, gs:8
0x14005c9dd  mov     sil, [rax+60h]
0x14005c9e1  cmp     sil, 1
0x14005c9e5  jnz     short loc_14005C9FE
0x14005c9e7  call    RtlReadULong64FromUser
0x14005c9ec  mov     rdx, rax
0x14005c9ef  mov     rcx, r14
0x14005c9f2  call    RtlWriteULong64ToUser
0x14005c9f7  jmp     short loc_14005C9FE
0x14005c9f9  jmp     loc_14005CAC1
0x14005c9fe  mov     [rsp+98h+var_50], 0
0x14005ca07  mov     rax, [rsp+98h+FileHandle]
0x14005ca0f  mov     [rsp+98h+var_68], rax
0x14005ca14  mov     [rsp+98h+var_70], ebx
0x14005ca18  mov     eax, [rsp+98h+SectionPageProtection]
0x14005ca1f  mov     [rsp+98h+var_78], eax
0x14005ca23  mov     r9, r15
0x14005ca26  mov     r8, r12
0x14005ca29  mov     edx, r13d
0x14005ca2c  lea     rcx, [rsp+98h+var_50]
0x14005ca31  call    NkCreateSection
0x14005ca36  test    eax, eax
0x14005ca38  js      loc_14005CAC1
0x14005ca3e  mov     byte ptr [rsp+98h+AllocationAttributes], sil
0x14005ca46  lea     r9, [rsp+98h+var_48]
0x14005ca4b  mov     r8b, sil
0x14005ca4e  xor     edx, edx
0x14005ca50  mov     rcx, [rsp+98h+var_50]
0x14005ca55  call    SkmmGetNtSecureImage
0x14005ca5a  mov     ebx, eax
0x14005ca5c  mov     [rsp+98h+var_58], eax
0x14005ca60  test    eax, eax
0x14005ca62  js      short loc_14005CA85
0x14005ca64  lea     r9, [rsp+98h+var_40]
0x14005ca69  mov     r8, [rsp+98h+var_50]
0x14005ca6e  xor     edx, edx
0x14005ca70  mov     rcx, [rsp+98h+var_48]
0x14005ca75  call    SkobCreateHandle
0x14005ca7a  mov     ebx, eax
0x14005ca7c  mov     [rsp+98h+var_58], eax
0x14005ca80  mov     rdi, [rsp+98h+var_40]
0x14005ca85  test    rdi, rdi
0x14005ca88  jnz     short loc_14005CA95
0x14005ca8a  mov     rcx, [rsp+98h+var_50]
0x14005ca8f  call    NkClose
0x14005ca94  nop
0x14005ca95  test    sil, sil
0x14005ca98  jz      short loc_14005CAA7
0x14005ca9a  mov     rdx, rdi
0x14005ca9d  mov     rcx, r14
0x14005caa0  call    RtlWriteULong64ToUser
0x14005caa5  jmp     short loc_14005CAAA
0x14005caa7  mov     [r14], rdi
0x14005caaa  jmp     short loc_14005CAB0
0x14005caac  mov     ebx, [rsp+98h+var_58]
0x14005cab0  mov     rcx, [rsp+98h+var_48]
0x14005cab5  test    rcx, rcx
0x14005cab8  jz      short loc_14005CABF
0x14005caba  call    SkobDereferenceObject
0x14005cabf  mov     eax, ebx
0x14005cac1  add     rsp, 60h
0x14005cac5  pop     r15
0x14005cac7  pop     r14
0x14005cac9  pop     r13
0x14005cacb  pop     r12
0x14005cacd  pop     rdi
0x14005cace  pop     rsi
0x14005cacf  pop     rbx
0x14005cad0  retn
0x1400fa7e8  push    rbp
0x1400fa7ea  sub     rsp, 40h
0x1400fa7ee  mov     rbp, rdx
0x1400fa7f1  xor     eax, eax
0x1400fa7f3  cmp     [rbp+0C8h], al
0x1400fa7f9  setnz   al
0x1400fa7fc  mov     [rbp+44h], eax
0x1400fa7ff  mov     eax, [rbp+44h]
0x1400fa802  add     rsp, 40h
0x1400fa806  pop     rbp
0x1400fa807  retn
```
