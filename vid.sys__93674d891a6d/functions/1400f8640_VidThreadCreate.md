# VidThreadCreate

- ea: `0x1400f8640`
- end: `0x1400f872a`
- name: `VidThreadCreate`
- size: `234`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400752a4`
- `0x140076088`
- `0x140091fbc`
- `0x1400cd2bc`

## callees

- `0x1400f8640`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400f86dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400f86dd`
- `ntoskrnl!ZwClose` at `0x1400f86fd`
- `ntoskrnl!ZwClose` at `0x1400f86fd`
- `ntoskrnl!PsCreateSystemThread` at `0x1400f869b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400f869b`
- `ntoskrnl!PsThreadType` at `0x1400f86ad`

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
0x1400f8640  mov     r11, rsp
0x1400f8643  mov     [r11+8], rbx
0x1400f8647  mov     [r11+10h], rdi
0x1400f864b  push    rbp
0x1400f864c  mov     rbp, rsp
0x1400f864f  sub     rsp, 80h
0x1400f8656  xor     eax, eax
0x1400f8658  mov     [r11-58h], rdx
0x1400f865c  mov     [r11-60h], rcx
0x1400f8660  mov     rdi, r9
0x1400f8663  mov     r9, r8; ProcessHandle
0x1400f8666  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400f866e  xorps   xmm0, xmm0
0x1400f8671  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x1400f8679  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400f867d  mov     [rbp+ThreadHandle], rax
0x1400f8681  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400f8685  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400f8689  mov     edx, 1FFFFFh; DesiredAccess
0x1400f868e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400f8692  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f8697  mov     [r11-68h], rax
0x1400f869b  call    cs:__imp_PsCreateSystemThread
0x1400f86a2  nop     dword ptr [rax+rax+00h]
0x1400f86a7  mov     ebx, eax
0x1400f86a9  test    eax, eax
0x1400f86ab  js      short loc_1400F8709
0x1400f86ad  mov     r8, cs:__imp_PsThreadType
0x1400f86b4  lea     rax, [rbp+var_38]
0x1400f86b8  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400f86bc  xor     r9d, r9d; AccessMode
0x1400f86bf  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400f86c8  mov     edx, 1FFFFFh; DesiredAccess
0x1400f86cd  mov     [rbp+var_38], 0
0x1400f86d5  mov     r8, [r8]; ObjectType
0x1400f86d8  mov     [rsp+80h+Object], rax; Object
0x1400f86dd  call    cs:__imp_ObReferenceObjectByHandle
0x1400f86e4  nop     dword ptr [rax+rax+00h]
0x1400f86e9  mov     rcx, [rbp+var_38]
0x1400f86ed  mov     [rdi], rcx
0x1400f86f0  mov     rcx, [rbp+arg_20]
0x1400f86f4  test    rcx, rcx
0x1400f86f7  jnz     short loc_1400F8721
0x1400f86f9  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400f86fd  call    cs:__imp_ZwClose
0x1400f8704  nop     dword ptr [rax+rax+00h]
0x1400f8709  lea     r11, [rsp+80h+var_s0]
0x1400f8711  mov     eax, ebx
0x1400f8713  mov     rbx, [r11+10h]
0x1400f8717  mov     rdi, [r11+18h]
0x1400f871b  mov     rsp, r11
0x1400f871e  pop     rbp
0x1400f871f  retn
0x1400f8721  mov     rax, [rbp+ThreadHandle]
0x1400f8725  mov     [rcx], rax
0x1400f8728  jmp     short loc_1400F8709
```
