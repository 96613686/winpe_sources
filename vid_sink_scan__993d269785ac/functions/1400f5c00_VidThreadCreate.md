# VidThreadCreate

- ea: `0x1400f5c00`
- end: `0x1400f5cea`
- name: `VidThreadCreate`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400742b8`
- `0x1400751c8`
- `0x1400909b4`

## callees

- `0x1400f5c00`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400f5c9d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400f5c9d`
- `ntoskrnl!ZwClose` at `0x1400f5cbd`
- `ntoskrnl!ZwClose` at `0x1400f5cbd`
- `ntoskrnl!PsCreateSystemThread` at `0x1400f5c5b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400f5c5b`
- `ntoskrnl!PsThreadType` at `0x1400f5c6d`

## pseudocode

```c
__int64 __fastcall VidThreadCreate(KSTART_ROUTINE *a1, void *a2, void *a3, PVOID *a4, void **a5)
{
  NTSTATUS v6; // ebx
  void *ThreadHandle; // [rsp+40h] [rbp-40h] BYREF
  PVOID Object; // [rsp+48h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, &ObjectAttributes, a3, 0, a1, a2);
  if ( v6 >= 0 )
  {
    Object = 0;
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
    *a4 = Object;
    if ( a5 )
      *a5 = ThreadHandle;
    else
      ZwClose(ThreadHandle);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400f5c00  mov     r11, rsp
0x1400f5c03  mov     [r11+8], rbx
0x1400f5c07  mov     [r11+10h], rdi
0x1400f5c0b  push    rbp
0x1400f5c0c  mov     rbp, rsp
0x1400f5c0f  sub     rsp, 80h
0x1400f5c16  xor     eax, eax
0x1400f5c18  mov     [r11-58h], rdx
0x1400f5c1c  mov     [r11-60h], rcx
0x1400f5c20  mov     rdi, r9
0x1400f5c23  mov     r9, r8; ProcessHandle
0x1400f5c26  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400f5c2e  xorps   xmm0, xmm0
0x1400f5c31  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x1400f5c39  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400f5c3d  mov     [rbp+ThreadHandle], rax
0x1400f5c41  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400f5c45  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400f5c49  mov     edx, 1FFFFFh; DesiredAccess
0x1400f5c4e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400f5c52  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f5c57  mov     [r11-68h], rax
0x1400f5c5b  call    cs:__imp_PsCreateSystemThread
0x1400f5c62  nop     dword ptr [rax+rax+00h]
0x1400f5c67  mov     ebx, eax
0x1400f5c69  test    eax, eax
0x1400f5c6b  js      short loc_1400F5CC9
0x1400f5c6d  mov     r8, cs:__imp_PsThreadType
0x1400f5c74  lea     rax, [rbp+var_38]
0x1400f5c78  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400f5c7c  xor     r9d, r9d; AccessMode
0x1400f5c7f  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400f5c88  mov     edx, 1FFFFFh; DesiredAccess
0x1400f5c8d  mov     [rbp+var_38], 0
0x1400f5c95  mov     r8, [r8]; ObjectType
0x1400f5c98  mov     [rsp+80h+Object], rax; Object
0x1400f5c9d  call    cs:__imp_ObReferenceObjectByHandle
0x1400f5ca4  nop     dword ptr [rax+rax+00h]
0x1400f5ca9  mov     rcx, [rbp+var_38]
0x1400f5cad  mov     [rdi], rcx
0x1400f5cb0  mov     rcx, [rbp+arg_20]
0x1400f5cb4  test    rcx, rcx
0x1400f5cb7  jnz     short loc_1400F5CE1
0x1400f5cb9  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400f5cbd  call    cs:__imp_ZwClose
0x1400f5cc4  nop     dword ptr [rax+rax+00h]
0x1400f5cc9  lea     r11, [rsp+80h+var_s0]
0x1400f5cd1  mov     eax, ebx
0x1400f5cd3  mov     rbx, [r11+10h]
0x1400f5cd7  mov     rdi, [r11+18h]
0x1400f5cdb  mov     rsp, r11
0x1400f5cde  pop     rbp
0x1400f5cdf  retn
0x1400f5ce1  mov     rax, [rbp+ThreadHandle]
0x1400f5ce5  mov     [rcx], rax
0x1400f5ce8  jmp     short loc_1400F5CC9
```
