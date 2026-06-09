# SpSdCopyHelper(void *,ulong,void * *,ushort *)

- ea: `0x140035254`
- end: `0x14003533b`
- name: `?SpSdCopyHelper@@YAJPEAXKPEAPEAXPEAG@Z`
- size: `231`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptorInput, ULONG SecurityDescriptorLength, void **, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009365c`
- `0x14009c600`
- `0x1400a0278`
- `0x1400a9a34`

## callees

- `0x140035254`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400352f1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400352f1`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400352aa`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400352aa`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400352d7`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400352d7`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035289`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035319`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035289`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140035319`

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
  PSECURITY_DESCRIPTOR v11; // rcx
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
    if ( RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0) )
    {
      LOBYTE(v10) = 1;
      v6 = SeCaptureSecurityDescriptor(SecurityDescriptorInput, 0, 1, v10, &SecurityDescriptor);
      if ( v6 >= 0 )
      {
        v11 = SecurityDescriptor;
        *v8 = SecurityDescriptor;
        *a4 = RtlLengthSecurityDescriptor(v11);
        SecurityDescriptor = 0;
      }
    }
    else
    {
      v6 = -1073741703;
    }
  }
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
0x140035254  mov     [rsp+arg_0], rbx
0x140035259  mov     [rsp+arg_8], rbp
0x14003525e  push    rsi
0x14003525f  push    rdi
0x140035260  push    r14
0x140035262  sub     rsp, 30h
0x140035266  mov     rbp, rcx
0x140035269  mov     [rsp+48h+SecurityDescriptor], 0
0x140035272  mov     rcx, [r8]
0x140035275  xor     ebx, ebx
0x140035277  mov     r14, r9
0x14003527a  mov     rdi, r8
0x14003527d  mov     esi, edx
0x14003527f  test    rcx, rcx
0x140035282  jz      short loc_140035298
0x140035284  mov     r8b, 1
0x140035287  xor     edx, edx
0x140035289  call    cs:__imp_SeReleaseSecurityDescriptor
0x140035290  nop     dword ptr [rax+rax+00h]
0x140035295  mov     [rdi], rbx
0x140035298  xor     eax, eax
0x14003529a  mov     [r14], ax
0x14003529e  test    esi, esi
0x1400352a0  jz      short loc_14003530A
0x1400352a2  xor     r8d, r8d; RequiredInformation
0x1400352a5  mov     edx, esi; SecurityDescriptorLength
0x1400352a7  mov     rcx, rbp; SecurityDescriptorInput
0x1400352aa  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400352b1  nop     dword ptr [rax+rax+00h]
0x1400352b6  test    al, al
0x1400352b8  jnz     short loc_1400352C1
0x1400352ba  mov     ebx, 0C0000079h
0x1400352bf  jmp     short loc_14003530A
0x1400352c1  xor     edx, edx
0x1400352c3  lea     rax, [rsp+48h+SecurityDescriptor]
0x1400352c8  mov     r9b, 1
0x1400352cb  mov     [rsp+48h+var_28], rax
0x1400352d0  mov     rcx, rbp
0x1400352d3  lea     r8d, [rdx+1]
0x1400352d7  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400352de  nop     dword ptr [rax+rax+00h]
0x1400352e3  mov     ebx, eax
0x1400352e5  test    eax, eax
0x1400352e7  js      short loc_14003530A
0x1400352e9  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1400352ee  mov     [rdi], rcx
0x1400352f1  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400352f8  nop     dword ptr [rax+rax+00h]
0x1400352fd  mov     [r14], ax
0x140035301  mov     [rsp+48h+SecurityDescriptor], 0
0x14003530a  mov     rcx, [rsp+48h+SecurityDescriptor]
0x14003530f  test    rcx, rcx
0x140035312  jz      short loc_140035325
0x140035314  mov     r8b, 1
0x140035317  xor     edx, edx
0x140035319  call    cs:__imp_SeReleaseSecurityDescriptor
0x140035320  nop     dword ptr [rax+rax+00h]
0x140035325  mov     rbp, [rsp+48h+arg_8]
0x14003532a  mov     eax, ebx
0x14003532c  mov     rbx, [rsp+48h+arg_0]
0x140035331  add     rsp, 30h
0x140035335  pop     r14
0x140035337  pop     rdi
0x140035338  pop     rsi
0x140035339  retn
```
