# SqospInitializeJobDispatcher

- ea: `0x140016078`
- end: `0x1400161e3`
- name: `SqospInitializeJobDispatcher`
- size: `363`
- prototype: `__int64 __fastcall(PVOID *Object)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400161ec`

## callees

- `0x140016078`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400161cb`
- `ntoskrnl!ZwClose` at `0x1400161cb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016121`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016121`
- `ntoskrnl!ExAllocatePool2` at `0x14001615b`
- `ntoskrnl!ExAllocatePool2` at `0x14001615b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400160ee`
- `ntoskrnl!PsCreateSystemThread` at `0x1400160ee`
- `ntoskrnl!KeInitializeQueue` at `0x1400160b4`
- `ntoskrnl!KeInitializeQueue` at `0x1400160b4`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14001613c`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14001613c`

## pseudocode

```c
__int64 __fastcall SqospInitializeJobDispatcher(PVOID *Object)
{
  NTSTATUS v2; // ebx
  __int64 MaximumProcessorCount; // rsi
  void *Pool2; // rax
  unsigned int v5; // r8d
  __int64 v6; // r9
  char *v7; // rcx
  __int64 v8; // rdx
  char *v9; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+A0h] [rbp+28h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeInitializeQueue((PRKQUEUE)(Object + 1), 1u);
  *((_BYTE *)Object + 72) = 1;
  v2 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         &ObjectAttributes,
         0,
         0,
         (PKSTART_ROUTINE)SqosJobDispatcherThreadRoutine,
         Object);
  if ( v2 >= 0 )
  {
    v2 = ObReferenceObjectByHandle(ThreadHandle, 0x100020u, 0, 0, Object, 0);
    if ( v2 >= 0 )
    {
      MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
      Pool2 = (void *)ExAllocatePool2(72, MaximumProcessorCount << 6, 1179865427);
      Object[10] = Pool2;
      if ( Pool2 )
      {
        v5 = 0;
        if ( (_DWORD)MaximumProcessorCount )
        {
          v6 = 0;
          do
          {
            v7 = (char *)Object[10];
            ++v5;
            v8 = v6++ << 6;
            *(_QWORD *)&v7[v8 + 24] = SqosJobDispatcherWorkItemRoutine;
            v9 = &v7[v8 + 8];
            *(_QWORD *)&v7[v8 + 32] = v9;
            *(_QWORD *)v9 = 0;
            *(_QWORD *)((char *)Object[10] + v8) = 0;
          }
          while ( v5 < (unsigned int)MaximumProcessorCount );
        }
      }
      else
      {
        v2 = -1073741670;
      }
    }
  }
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140016078  push    rbp
0x14001607a  push    rbx
0x14001607b  push    rsi
0x14001607c  push    rdi
0x14001607d  mov     rbp, rsp
0x140016080  sub     rsp, 78h
0x140016084  xor     eax, eax
0x140016086  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001608e  mov     rdi, rcx
0x140016091  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x140016099  xorps   xmm0, xmm0
0x14001609c  mov     [rbp+ThreadHandle], rax
0x1400160a0  add     rcx, 8; Queue
0x1400160a4  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400160a8  lea     edx, [rax+1]; Count
0x1400160ab  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400160af  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400160b4  call    cs:__imp_KeInitializeQueue
0x1400160bb  nop     dword ptr [rax+rax+00h]
0x1400160c0  lea     rax, SqosJobDispatcherThreadRoutine
0x1400160c7  mov     [rsp+78h+StartContext], rdi; StartContext
0x1400160cc  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x1400160d1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400160d5  xor     r9d, r9d; ProcessHandle
0x1400160d8  mov     [rsp+78h+ClientId], 0; ClientId
0x1400160e1  mov     edx, 1FFFFFh; DesiredAccess
0x1400160e6  mov     byte ptr [rdi+48h], 1
0x1400160ea  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400160ee  call    cs:__imp_PsCreateSystemThread
0x1400160f5  nop     dword ptr [rax+rax+00h]
0x1400160fa  mov     ebx, eax
0x1400160fc  test    eax, eax
0x1400160fe  js      loc_1400161C2
0x140016104  mov     rcx, [rbp+ThreadHandle]; Handle
0x140016108  xor     r9d, r9d; AccessMode
0x14001610b  mov     [rsp+78h+StartRoutine], 0; HandleInformation
0x140016114  xor     r8d, r8d; ObjectType
0x140016117  mov     edx, 100020h; DesiredAccess
0x14001611c  mov     [rsp+78h+ClientId], rdi; Object
0x140016121  call    cs:__imp_ObReferenceObjectByHandle
0x140016128  nop     dword ptr [rax+rax+00h]
0x14001612d  mov     ebx, eax
0x14001612f  test    eax, eax
0x140016131  js      loc_1400161C2
0x140016137  mov     ecx, 0FFFFh; GroupNumber
0x14001613c  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140016143  nop     dword ptr [rax+rax+00h]
0x140016148  mov     edx, eax
0x14001614a  mov     ecx, 48h ; 'H'
0x14001614f  shl     rdx, 6
0x140016153  mov     r8d, 46535153h
0x140016159  mov     esi, eax
0x14001615b  call    cs:__imp_ExAllocatePool2
0x140016162  nop     dword ptr [rax+rax+00h]
0x140016167  mov     [rdi+50h], rax
0x14001616b  test    rax, rax
0x14001616e  jnz     short loc_140016177
0x140016170  mov     ebx, 0C000009Ah
0x140016175  jmp     short loc_1400161C2
0x140016177  xor     r8d, r8d
0x14001617a  test    esi, esi
0x14001617c  jz      short loc_1400161C2
0x14001617e  xor     r9d, r9d
0x140016181  mov     rcx, [rdi+50h]
0x140016185  lea     rax, SqosJobDispatcherWorkItemRoutine
0x14001618c  mov     rdx, r9
0x14001618f  inc     r8d
0x140016192  shl     rdx, 6
0x140016196  inc     r9
0x140016199  mov     [rcx+rdx+18h], rax
0x14001619e  lea     rax, [rcx+8]
0x1400161a2  add     rax, rdx
0x1400161a5  mov     [rcx+rdx+20h], rax
0x1400161aa  mov     qword ptr [rax], 0
0x1400161b1  mov     rax, [rdi+50h]
0x1400161b5  mov     qword ptr [rdx+rax], 0
0x1400161bd  cmp     r8d, esi
0x1400161c0  jb      short loc_140016181
0x1400161c2  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400161c6  test    rcx, rcx
0x1400161c9  jz      short loc_1400161D7
0x1400161cb  call    cs:__imp_ZwClose
0x1400161d2  nop     dword ptr [rax+rax+00h]
0x1400161d7  mov     eax, ebx
0x1400161d9  add     rsp, 78h
0x1400161dd  pop     rdi
0x1400161de  pop     rsi
0x1400161df  pop     rbx
0x1400161e0  pop     rbp
0x1400161e1  retn
```
