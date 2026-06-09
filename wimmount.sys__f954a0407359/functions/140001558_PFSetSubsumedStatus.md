# PFSetSubsumedStatus

- ea: `0x140001558`
- end: `0x14000161f`
- name: `PFSetSubsumedStatus`
- size: `199`
- prototype: `__int64 __fastcall(PFLT_INSTANCE InitiatingInstance)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009aa0`

## callees

- `0x140001558`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400015b0`
- `ntoskrnl!KeSetEvent` at `0x1400015b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400015f2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400015f2`
- `FLTMGR!FltDeleteStreamContext` at `0x1400015c6`
- `FLTMGR!FltDeleteStreamContext` at `0x1400015c6`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140001571`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140001571`
- `FLTMGR!FltReleaseContext` at `0x140001601`
- `FLTMGR!FltReleaseContext` at `0x140001601`
- `FLTMGR!FltReleaseResource` at `0x140001590`
- `FLTMGR!FltReleaseResource` at `0x140001590`
- `FLTMGR!FltUntagFile` at `0x1400015e2`
- `FLTMGR!FltUntagFile` at `0x1400015e2`

## pseudocode

```c
void __fastcall PFSetSubsumedStatus(PFLT_INSTANCE InitiatingInstance, __int64 a2, int a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbx

  FltAcquireResourceExclusive(&Resource);
  v6 = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(a2 + 40) = 0;
  FltReleaseResource(&Resource);
  if ( v6 )
  {
    do
    {
      v7 = *(_QWORD *)(v6 + 40);
      *(_DWORD *)(v6 + 24) = a3;
      KeSetEvent((PRKEVENT)v6, 0, 0);
      FltDeleteStreamContext(InitiatingInstance, *(PFILE_OBJECT *)(v6 + 48), 0);
      FltUntagFile(InitiatingInstance, *(PFILE_OBJECT *)(v6 + 48), 0x80000008, 0);
      ObfDereferenceObject(*(PVOID *)(v6 + 48));
      FltReleaseContext((PFLT_CONTEXT)v6);
      v6 = v7;
    }
    while ( v7 );
  }
}

```

## disassembly

```asm
0x140001558  push    rbx
0x14000155a  push    rbp
0x14000155b  push    rsi
0x14000155c  push    rdi
0x14000155d  sub     rsp, 28h
0x140001561  mov     rsi, rcx
0x140001564  mov     ebp, r8d
0x140001567  lea     rcx, Resource; Resource
0x14000156e  mov     rbx, rdx
0x140001571  call    cs:__imp_FltAcquireResourceExclusive
0x140001578  nop     dword ptr [rax+rax+00h]
0x14000157d  mov     rdi, [rbx+28h]
0x140001581  lea     rcx, Resource; Resource
0x140001588  mov     qword ptr [rbx+28h], 0
0x140001590  call    cs:__imp_FltReleaseResource
0x140001597  nop     dword ptr [rax+rax+00h]
0x14000159c  test    rdi, rdi
0x14000159f  jz      short loc_140001615
0x1400015a1  mov     rbx, [rdi+28h]
0x1400015a5  xor     r8d, r8d; Wait
0x1400015a8  xor     edx, edx; Increment
0x1400015aa  mov     [rdi+18h], ebp
0x1400015ad  mov     rcx, rdi; Event
0x1400015b0  call    cs:__imp_KeSetEvent
0x1400015b7  nop     dword ptr [rax+rax+00h]
0x1400015bc  mov     rdx, [rdi+30h]; FileObject
0x1400015c0  xor     r8d, r8d; OldContext
0x1400015c3  mov     rcx, rsi; Instance
0x1400015c6  call    cs:__imp_FltDeleteStreamContext
0x1400015cd  nop     dword ptr [rax+rax+00h]
0x1400015d2  mov     rdx, [rdi+30h]; FileObject
0x1400015d6  xor     r9d, r9d; Guid
0x1400015d9  mov     r8d, 80000008h; FileTag
0x1400015df  mov     rcx, rsi; InitiatingInstance
0x1400015e2  call    cs:__imp_FltUntagFile
0x1400015e9  nop     dword ptr [rax+rax+00h]
0x1400015ee  mov     rcx, [rdi+30h]; Object
0x1400015f2  call    cs:__imp_ObfDereferenceObject
0x1400015f9  nop     dword ptr [rax+rax+00h]
0x1400015fe  mov     rcx, rdi; Context
0x140001601  call    cs:__imp_FltReleaseContext
0x140001608  nop     dword ptr [rax+rax+00h]
0x14000160d  mov     rdi, rbx
0x140001610  test    rbx, rbx
0x140001613  jnz     short loc_1400015A1
0x140001615  add     rsp, 28h
0x140001619  pop     rdi
0x14000161a  pop     rsi
0x14000161b  pop     rbp
0x14000161c  pop     rbx
0x14000161d  retn
```
