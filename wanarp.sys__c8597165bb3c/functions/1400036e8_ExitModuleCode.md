# ExitModuleCode

- ea: `0x1400036e8`
- end: `0x14000378d`
- name: `ExitModuleCode`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fdc4`
- `0x140010448`
- `0x1400172d0`

## callees

- `0x1400036e8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400036fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400036fb`
- `ntoskrnl!KeSetEvent` at `0x14000375f`
- `ntoskrnl!KeSetEvent` at `0x14000375f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003775`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003775`

## pseudocode

```c
void __fastcall ExitModuleCode(char a1)
{
  KIRQL v2; // al
  int v3; // r8d
  int *v4; // rdx
  KIRQL v5; // di
  int v6; // r8d
  int v7; // edx
  struct _KEVENT *v8; // rcx

  v2 = KeAcquireSpinLockRaiseToDpc(&g_rlStateLock);
  v3 = dword_140009AE8;
  v4 = &dword_140009AE8;
  v5 = v2;
  if ( !a1 )
    v3 = dword_140009C08;
  v6 = v3 - 1;
  if ( !a1 )
    v4 = &dword_140009C08;
  *v4 = v6;
  v7 = dword_140009A80;
  if ( !a1 )
    v7 = Increment;
  if ( !v7 && !v6 )
  {
    v8 = (struct _KEVENT *)qword_140009AA0;
    if ( !a1 )
      v8 = &Object;
    KeSetEvent(v8, 0, 0);
  }
  KeReleaseSpinLock(&g_rlStateLock, v5);
}

```

## disassembly

```asm
0x1400036e8  mov     [rsp+arg_0], rbx
0x1400036ed  push    rdi
0x1400036ee  sub     rsp, 20h
0x1400036f2  mov     bl, cl
0x1400036f4  lea     rcx, g_rlStateLock; SpinLock
0x1400036fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003702  nop     dword ptr [rax+rax+00h]
0x140003707  mov     r8d, cs:dword_140009AE8
0x14000370e  lea     rdx, dword_140009AE8
0x140003715  test    bl, bl
0x140003717  mov     dil, al
0x14000371a  lea     rax, dword_140009C08
0x140003721  cmovz   r8d, cs:dword_140009C08
0x140003729  dec     r8d; Wait
0x14000372c  test    bl, bl
0x14000372e  cmovz   rdx, rax
0x140003732  mov     [rdx], r8d
0x140003735  mov     edx, cs:dword_140009A80
0x14000373b  cmovz   edx, cs:Increment; Increment
0x140003742  test    edx, edx
0x140003744  jnz     short loc_14000376B
0x140003746  test    r8d, r8d
0x140003749  jnz     short loc_14000376B
0x14000374b  test    bl, bl
0x14000374d  lea     rax, Object
0x140003754  lea     rcx, qword_140009AA0
0x14000375b  cmovz   rcx, rax; Event
0x14000375f  call    cs:__imp_KeSetEvent
0x140003766  nop     dword ptr [rax+rax+00h]
0x14000376b  mov     dl, dil; NewIrql
0x14000376e  lea     rcx, g_rlStateLock; SpinLock
0x140003775  call    cs:__imp_KeReleaseSpinLock
0x14000377c  nop     dword ptr [rax+rax+00h]
0x140003781  mov     rbx, [rsp+28h+arg_0]
0x140003786  add     rsp, 20h
0x14000378a  pop     rdi
0x14000378b  retn
```
