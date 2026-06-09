# UdfRmwInitQuickGrowFormat

- ea: `0x14003c964`
- end: `0x14003ca72`
- name: `UdfRmwInitQuickGrowFormat`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017c08`

## callees

- `0x14003c964`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ca3f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ca3f`
- `ntoskrnl!KeInitializeEvent` at `0x14003c9b4`
- `ntoskrnl!KeInitializeEvent` at `0x14003c9b4`
- `ntoskrnl!ZwClose` at `0x14003ca51`
- `ntoskrnl!ZwClose` at `0x14003ca51`
- `ntoskrnl!PsCreateSystemThread` at `0x14003ca10`
- `ntoskrnl!PsCreateSystemThread` at `0x14003ca10`

## pseudocode

```c
__int64 __fastcall UdfRmwInitQuickGrowFormat(void *a1, _QWORD *a2)
{
  __int64 v2; // rcx
  __int64 result; // rax
  PVOID *v5; // rdi
  NTSTATUS v6; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+10h] BYREF

  ThreadHandle = a1;
  v2 = a2[13];
  result = 0;
  ThreadHandle = 0;
  v5 = (PVOID *)(v2 + 256);
  memset(&ObjectAttributes, 0, 44);
  if ( !*(_QWORD *)(v2 + 256) )
  {
    KeInitializeEvent((PRKEVENT)(v2 + 232), SynchronizationEvent, 0);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = PsCreateSystemThread(
           &ThreadHandle,
           0x2000000u,
           &ObjectAttributes,
           0,
           0,
           (PKSTART_ROUTINE)UdfRmwBgFormatWorker,
           a2);
    if ( v6 >= 0 )
    {
      v6 = ObReferenceObjectByHandle(ThreadHandle, 0x2000000u, 0, 0, v5, 0);
      ZwClose(ThreadHandle);
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x14003c964  mov     [rsp-8+arg_8], rbx
0x14003c969  mov     [rsp-8+arg_10], rdi
0x14003c96e  mov     [rsp-8+ThreadHandle], rcx
0x14003c973  push    rbp
0x14003c974  mov     rbp, rsp
0x14003c977  sub     rsp, 70h
0x14003c97b  mov     rcx, [rdx+68h]
0x14003c97f  xorps   xmm0, xmm0
0x14003c982  xor     eax, eax
0x14003c984  mov     rbx, rdx
0x14003c987  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003c98b  mov     [rbp+ThreadHandle], rax
0x14003c98f  lea     rdi, [rcx+100h]
0x14003c996  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003c99a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003c99e  cmp     [rdi], rax
0x14003c9a1  jnz     loc_14003CA5F
0x14003c9a7  add     rcx, 0E8h; Event
0x14003c9ae  lea     edx, [rax+1]; Type
0x14003c9b1  xor     r8d, r8d; State
0x14003c9b4  call    cs:__imp_KeInitializeEvent
0x14003c9bb  nop     dword ptr [rax+rax+00h]
0x14003c9c0  lea     rax, UdfRmwBgFormatWorker
0x14003c9c7  mov     [rsp+70h+StartContext], rbx; StartContext
0x14003c9cc  xorps   xmm0, xmm0
0x14003c9cf  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14003c9d4  xor     r9d, r9d; ProcessHandle
0x14003c9d7  mov     [rsp+70h+ClientId], 0; ClientId
0x14003c9e0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003c9e4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003c9eb  mov     edx, 2000000h; DesiredAccess
0x14003c9f0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14003c9f8  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14003c9fc  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14003ca03  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14003ca0b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003ca10  call    cs:__imp_PsCreateSystemThread
0x14003ca17  nop     dword ptr [rax+rax+00h]
0x14003ca1c  mov     ebx, eax
0x14003ca1e  test    eax, eax
0x14003ca20  js      short loc_14003CA5D
0x14003ca22  mov     rcx, [rbp+ThreadHandle]; Handle
0x14003ca26  xor     r9d, r9d; AccessMode
0x14003ca29  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x14003ca32  xor     r8d, r8d; ObjectType
0x14003ca35  mov     edx, 2000000h; DesiredAccess
0x14003ca3a  mov     [rsp+70h+ClientId], rdi; Object
0x14003ca3f  call    cs:__imp_ObReferenceObjectByHandle
0x14003ca46  nop     dword ptr [rax+rax+00h]
0x14003ca4b  mov     rcx, [rbp+ThreadHandle]; Handle
0x14003ca4f  mov     ebx, eax
0x14003ca51  call    cs:__imp_ZwClose
0x14003ca58  nop     dword ptr [rax+rax+00h]
0x14003ca5d  mov     eax, ebx
0x14003ca5f  lea     r11, [rsp+70h+var_s0]
0x14003ca64  mov     rbx, [r11+18h]
0x14003ca68  mov     rdi, [r11+20h]
0x14003ca6c  mov     rsp, r11
0x14003ca6f  pop     rbp
0x14003ca70  retn
```
