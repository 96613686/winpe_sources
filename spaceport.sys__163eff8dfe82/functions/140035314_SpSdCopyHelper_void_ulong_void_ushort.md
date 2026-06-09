# SpSdCopyHelper(void *,ulong,void * *,ushort *)

- ea: `0x140035314`
- end: `0x140035409`
- name: `?SpSdCopyHelper@@YAJPEAXKPEAPEAXPEAG@Z`
- size: `245`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptorInput, ULONG SecurityDescriptorLength, void **, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009365c`
- `0x14009c600`
- `0x1400a0274`
- `0x1400a9bc4`

## callees

- `0x140035314`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400353ae`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400353ae`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14003536a`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14003536a`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140035397`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140035397`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035349`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400353e7`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035349`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1400353e7`

## pseudocode

```c
__int64 __fastcall SpSdCopyHelper(
        PSECURITY_DESCRIPTOR SecurityDescriptorInput,
        ULONG SecurityDescriptorLength,
        void **a3,
        unsigned __int16 *a4)
{
  void *v5; // rcx
  int v6; // ebx
  void **v8; // rdi
  __int64 v10; // r9
  ULONG v11; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  v5 = *a3;
  v6 = 0;
  v8 = a3;
  if ( *a3 )
  {
    LOBYTE(a3) = 1;
    SeReleaseSecurityDescriptor(v5, 0, a3);
    *v8 = 0;
  }
  *a4 = 0;
  if ( SecurityDescriptorLength )
  {
    if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0) )
    {
LABEL_5:
      v6 = -1073741703;
      goto LABEL_9;
    }
    LOBYTE(v10) = 1;
    v6 = SeCaptureSecurityDescriptor(SecurityDescriptorInput, 0, 1, v10, &SecurityDescriptor);
    if ( v6 >= 0 )
    {
      v11 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      if ( v11 > 0xFFFF )
        goto LABEL_5;
      *v8 = SecurityDescriptor;
      *a4 = v11;
      SecurityDescriptor = 0;
    }
  }
LABEL_9:
  if ( SecurityDescriptor )
  {
    LOBYTE(a3) = 1;
    SeReleaseSecurityDescriptor(SecurityDescriptor, 0, a3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140035314  mov     [rsp+arg_0], rbx
0x140035319  mov     [rsp+arg_8], rbp
0x14003531e  push    rsi
0x14003531f  push    rdi
0x140035320  push    r14
0x140035322  sub     rsp, 30h
0x140035326  mov     rbp, rcx
0x140035329  mov     [rsp+48h+SecurityDescriptor], 0
0x140035332  mov     rcx, [r8]
0x140035335  xor     ebx, ebx
0x140035337  mov     r14, r9
0x14003533a  mov     rdi, r8
0x14003533d  mov     esi, edx
0x14003533f  test    rcx, rcx
0x140035342  jz      short loc_140035358
0x140035344  mov     r8b, 1
0x140035347  xor     edx, edx
0x140035349  call    cs:__imp_SeReleaseSecurityDescriptor
0x140035350  nop     dword ptr [rax+rax+00h]
0x140035355  mov     [rdi], rbx
0x140035358  xor     eax, eax
0x14003535a  mov     [r14], ax
0x14003535e  test    esi, esi
0x140035360  jz      short loc_1400353D8
0x140035362  xor     r8d, r8d; RequiredInformation
0x140035365  mov     edx, esi; SecurityDescriptorLength
0x140035367  mov     rcx, rbp; SecurityDescriptorInput
0x14003536a  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140035371  nop     dword ptr [rax+rax+00h]
0x140035376  test    al, al
0x140035378  jnz     short loc_140035381
0x14003537a  mov     ebx, 0C0000079h
0x14003537f  jmp     short loc_1400353D8
0x140035381  xor     edx, edx
0x140035383  lea     rax, [rsp+48h+SecurityDescriptor]
0x140035388  mov     r9b, 1
0x14003538b  mov     [rsp+48h+var_28], rax
0x140035390  mov     rcx, rbp
0x140035393  lea     r8d, [rdx+1]
0x140035397  call    cs:__imp_SeCaptureSecurityDescriptor
0x14003539e  nop     dword ptr [rax+rax+00h]
0x1400353a3  mov     ebx, eax
0x1400353a5  test    eax, eax
0x1400353a7  js      short loc_1400353D8
0x1400353a9  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400353ae  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400353b5  nop     dword ptr [rax+rax+00h]
0x1400353ba  mov     ecx, eax
0x1400353bc  cmp     eax, 0FFFFh
0x1400353c1  ja      short loc_14003537A
0x1400353c3  mov     rax, [rsp+48h+SecurityDescriptor]
0x1400353c8  mov     [rdi], rax
0x1400353cb  mov     [r14], cx
0x1400353cf  mov     [rsp+48h+SecurityDescriptor], 0
0x1400353d8  mov     rcx, [rsp+48h+SecurityDescriptor]
0x1400353dd  test    rcx, rcx
0x1400353e0  jz      short loc_1400353F3
0x1400353e2  mov     r8b, 1
0x1400353e5  xor     edx, edx
0x1400353e7  call    cs:__imp_SeReleaseSecurityDescriptor
0x1400353ee  nop     dword ptr [rax+rax+00h]
0x1400353f3  mov     rbp, [rsp+48h+arg_8]
0x1400353f8  mov     eax, ebx
0x1400353fa  mov     rbx, [rsp+48h+arg_0]
0x1400353ff  add     rsp, 30h
0x140035403  pop     r14
0x140035405  pop     rdi
0x140035406  pop     rsi
0x140035407  retn
```
