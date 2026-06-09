# PFReleaseContextAndUntagFile

- ea: `0x14000a0d0`
- end: `0x14000a21c`
- name: `PFReleaseContextAndUntagFile`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140009aa0`

## callees

- `0x1400098a8`
- `0x14000a0d0`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a13a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a13a`
- `ntoskrnl!KeSetEvent` at `0x14000a186`
- `ntoskrnl!KeSetEvent` at `0x14000a1c0`
- `ntoskrnl!KeSetEvent` at `0x14000a186`
- `ntoskrnl!KeSetEvent` at `0x14000a1c0`
- `ntoskrnl!IoFileObjectType` at `0x14000a115`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1fd`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1fd`
- `FLTMGR!FltDeleteStreamContext` at `0x14000a19e`
- `FLTMGR!FltDeleteStreamContext` at `0x14000a19e`
- `FLTMGR!FltReleaseContext` at `0x14000a1cf`
- `FLTMGR!FltReleaseContext` at `0x14000a1e5`
- `FLTMGR!FltReleaseContext` at `0x14000a1cf`
- `FLTMGR!FltReleaseContext` at `0x14000a1e5`
- `FLTMGR!FltUntagFile` at `0x14000a165`
- `FLTMGR!FltUntagFile` at `0x14000a165`

## pseudocode

```c
__int64 __fastcall PFReleaseContextAndUntagFile(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        struct _KEVENT *a3,
        char a4,
        HANDLE Handle,
        char a6)
{
  int v8; // eax
  NTSTATUS v9; // ebx
  PVOID Object[3]; // [rsp+30h] [rbp-18h] BYREF

  Object[0] = 0;
  if ( !a4 )
    goto LABEL_12;
  v8 = Handle
     ? ObReferenceObjectByHandle(Handle, 0xF0000u, (POBJECT_TYPE)IoFileObjectType, 0, Object, 0)
     : PFOpenReparseTarget(a1, a2, 0, Object);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_11;
  if ( a6 )
  {
    v9 = FltUntagFile(*(PFLT_INSTANCE *)(a2 + 24), (PFILE_OBJECT)Object[0], 0x80000008, 0);
    if ( v9 == -1073741195 )
      v9 = 0;
  }
  KeSetEvent(a3, 0, 0);
  FltDeleteStreamContext(*(PFLT_INSTANCE *)(a2 + 24), (PFILE_OBJECT)Object[0], 0);
  if ( a6 && v9 < 0 )
  {
LABEL_11:
    a3[1].Header.LockNV = v9;
    KeSetEvent(a3, 0, 0);
    FltReleaseContext(a3);
  }
  else
  {
LABEL_12:
    if ( a3 )
      FltReleaseContext(a3);
    v9 = 0;
  }
  if ( Object[0] )
    ObfDereferenceObject(Object[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000a0d0  mov     r11, rsp
0x14000a0d3  mov     [r11+8], rbx
0x14000a0d7  mov     [r11+10h], rbp
0x14000a0db  push    rdi
0x14000a0dc  sub     rsp, 40h
0x14000a0e0  mov     qword ptr [r11-18h], 0
0x14000a0e8  mov     rdi, r8
0x14000a0eb  mov     rbp, rdx
0x14000a0ee  mov     rax, rcx
0x14000a0f1  test    r9b, r9b
0x14000a0f4  jz      loc_14000A1DD
0x14000a0fa  mov     rcx, [rsp+48h+Handle]; Handle
0x14000a0ff  test    rcx, rcx
0x14000a102  jnz     short loc_14000A115
0x14000a104  lea     r9, [r11-18h]
0x14000a108  xor     r8d, r8d
0x14000a10b  mov     rcx, rax
0x14000a10e  call    PFOpenReparseTarget
0x14000a113  jmp     short loc_14000A146
0x14000a115  mov     r8, cs:__imp_IoFileObjectType
0x14000a11c  lea     rax, [rsp+48h+var_18]
0x14000a121  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x14000a12a  xor     r9d, r9d; AccessMode
0x14000a12d  mov     edx, 0F0000h; DesiredAccess
0x14000a132  mov     [rsp+48h+Object], rax; Object
0x14000a137  mov     r8, [r8]; ObjectType
0x14000a13a  call    cs:__imp_ObReferenceObjectByHandle
0x14000a141  nop     dword ptr [rax+rax+00h]
0x14000a146  mov     ebx, eax
0x14000a148  test    eax, eax
0x14000a14a  js      short loc_14000A1B5
0x14000a14c  cmp     [rsp+48h+arg_28], 0
0x14000a151  jz      short loc_14000A17E
0x14000a153  mov     rdx, [rsp+48h+var_18]; FileObject
0x14000a158  xor     r9d, r9d; Guid
0x14000a15b  mov     rcx, [rbp+18h]; InitiatingInstance
0x14000a15f  mov     r8d, 80000008h; FileTag
0x14000a165  call    cs:__imp_FltUntagFile
0x14000a16c  nop     dword ptr [rax+rax+00h]
0x14000a171  mov     ebx, eax
0x14000a173  xor     eax, eax
0x14000a175  cmp     ebx, 0C0000275h
0x14000a17b  cmovz   ebx, eax
0x14000a17e  xor     r8d, r8d; Wait
0x14000a181  xor     edx, edx; Increment
0x14000a183  mov     rcx, rdi; Event
0x14000a186  call    cs:__imp_KeSetEvent
0x14000a18d  nop     dword ptr [rax+rax+00h]
0x14000a192  mov     rdx, [rsp+48h+var_18]; FileObject
0x14000a197  xor     r8d, r8d; OldContext
0x14000a19a  mov     rcx, [rbp+18h]; Instance
0x14000a19e  call    cs:__imp_FltDeleteStreamContext
0x14000a1a5  nop     dword ptr [rax+rax+00h]
0x14000a1aa  cmp     [rsp+48h+arg_28], 0
0x14000a1af  jz      short loc_14000A1DD
0x14000a1b1  test    ebx, ebx
0x14000a1b3  jns     short loc_14000A1DD
0x14000a1b5  xor     r8d, r8d; Wait
0x14000a1b8  mov     [rdi+18h], ebx
0x14000a1bb  xor     edx, edx; Increment
0x14000a1bd  mov     rcx, rdi; Event
0x14000a1c0  call    cs:__imp_KeSetEvent
0x14000a1c7  nop     dword ptr [rax+rax+00h]
0x14000a1cc  mov     rcx, rdi; Context
0x14000a1cf  call    cs:__imp_FltReleaseContext
0x14000a1d6  nop     dword ptr [rax+rax+00h]
0x14000a1db  jmp     short loc_14000A1F3
0x14000a1dd  test    rdi, rdi
0x14000a1e0  jz      short loc_14000A1F1
0x14000a1e2  mov     rcx, rdi; Context
0x14000a1e5  call    cs:__imp_FltReleaseContext
0x14000a1ec  nop     dword ptr [rax+rax+00h]
0x14000a1f1  xor     ebx, ebx
0x14000a1f3  mov     rcx, [rsp+48h+var_18]; Object
0x14000a1f8  test    rcx, rcx
0x14000a1fb  jz      short loc_14000A209
0x14000a1fd  call    cs:__imp_ObfDereferenceObject
0x14000a204  nop     dword ptr [rax+rax+00h]
0x14000a209  mov     rbp, [rsp+48h+arg_8]
0x14000a20e  mov     eax, ebx
0x14000a210  mov     rbx, [rsp+48h+arg_0]
0x14000a215  add     rsp, 40h
0x14000a219  pop     rdi
0x14000a21a  retn
```
