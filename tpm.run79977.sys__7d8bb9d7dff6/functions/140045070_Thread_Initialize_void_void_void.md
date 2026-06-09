# Thread::Initialize(void (*)(void *),void *)

- ea: `0x140045070`
- end: `0x140045152`
- name: `?Initialize@Thread@@QEAAJP6AXPEAX@Z0@Z`
- size: `226`
- prototype: `__int64 __fastcall(Thread *__hidden this, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140013da0`
- `0x140045158`
- `0x140045350`

## callees

- `0x140045070`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004512e`
- `ntoskrnl!ZwClose` at `0x14004512e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140045111`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140045111`
- `ntoskrnl!PsCreateSystemThread` at `0x1400450d6`
- `ntoskrnl!PsCreateSystemThread` at `0x1400450d6`

## pseudocode

```c
__int64 __fastcall Thread::Initialize(Thread *this, void (*a2)(void *), void *a3)
{
  NTSTATUS v4; // ebx
  PVOID Object; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+A8h] [rbp+28h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, a2, a3);
  if ( v4 >= 0 )
  {
    Object = 0;
    v4 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    *(_QWORD *)this = Object;
    if ( v4 >= 0 )
      ZwClose(ThreadHandle);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140045070  mov     rax, rsp
0x140045073  mov     [rax+8], rbx
0x140045077  mov     [rax+10h], rdi
0x14004507b  push    rbp
0x14004507c  mov     rbp, rsp
0x14004507f  sub     rsp, 80h
0x140045086  mov     [rax-58h], r8
0x14004508a  mov     rdi, rcx
0x14004508d  mov     [rax-60h], rdx
0x140045091  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140045095  xorps   xmm0, xmm0
0x140045098  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400450a0  xor     edx, edx; DesiredAccess
0x1400450a2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x1400450aa  xor     r9d, r9d; ProcessHandle
0x1400450ad  mov     [rbp+ThreadHandle], 0
0x1400450b5  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400450b9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400450c1  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1400450c9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400450ce  mov     qword ptr [rax-68h], 0
0x1400450d6  call    cs:__imp_PsCreateSystemThread
0x1400450dd  nop     dword ptr [rax+rax+00h]
0x1400450e2  mov     ebx, eax
0x1400450e4  test    eax, eax
0x1400450e6  js      short loc_14004513A
0x1400450e8  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400450ec  lea     rax, [rbp+var_40]
0x1400450f0  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400450f9  xor     r9d, r9d; AccessMode
0x1400450fc  xor     r8d, r8d; ObjectType
0x1400450ff  mov     [rsp+80h+Object], rax; Object
0x140045104  mov     edx, 1FFFFFh; DesiredAccess
0x140045109  mov     [rbp+var_40], 0
0x140045111  call    cs:__imp_ObReferenceObjectByHandle
0x140045118  nop     dword ptr [rax+rax+00h]
0x14004511d  mov     ebx, eax
0x14004511f  mov     rax, [rbp+var_40]
0x140045123  mov     [rdi], rax
0x140045126  test    ebx, ebx
0x140045128  js      short loc_14004513A
0x14004512a  mov     rcx, [rbp+ThreadHandle]; Handle
0x14004512e  call    cs:__imp_ZwClose
0x140045135  nop     dword ptr [rax+rax+00h]
0x14004513a  lea     r11, [rsp+80h+var_s0]
0x140045142  mov     eax, ebx
0x140045144  mov     rbx, [r11+10h]
0x140045148  mov     rdi, [r11+18h]
0x14004514c  mov     rsp, r11
0x14004514f  pop     rbp
0x140045150  retn
```
