# WanpSetCloseEventIfRequired

- ea: `0x140002ac0`
- end: `0x140002b63`
- name: `WanpSetCloseEventIfRequired`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028b0`
- `0x14000e6f8`
- `0x14000f250`

## callees

- `0x140002ac0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b0c`
- `ntoskrnl!KeSetEvent` at `0x140002af9`
- `ntoskrnl!KeSetEvent` at `0x140002af9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b39`

## pseudocode

```c
char *__fastcall WanpSetCloseEventIfRequired(char a1)
{
  char *result; // rax
  char v3; // cl
  struct _KEVENT *v4; // rcx
  KIRQL v5; // al
  char *v6; // rdx

  result = (char *)(unsigned __int8)byte_140009B4C;
  v3 = byte_140009A2C;
  if ( !a1 )
    v3 = byte_140009B4C;
  if ( v3 )
  {
    v4 = (struct _KEVENT *)qword_140009AB8;
    if ( !a1 )
      v4 = &stru_140009BD8;
    KeSetEvent(v4, 0, 0);
    v5 = KeAcquireSpinLockRaiseToDpc(&g_rlStateLock);
    v6 = &byte_1400099E4;
    if ( !a1 )
      v6 = &byte_140009B04;
    *v6 = 0;
    KeReleaseSpinLock(&g_rlStateLock, v5);
    result = &byte_140009A2C;
    if ( !a1 )
      result = &byte_140009B4C;
    *result = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002ac0  push    rbx
0x140002ac2  sub     rsp, 20h
0x140002ac6  movzx   eax, cs:byte_140009B4C
0x140002acd  movzx   ebx, cl
0x140002ad0  movzx   ecx, cs:byte_140009A2C
0x140002ad7  test    bl, bl
0x140002ad9  cmovz   ecx, eax
0x140002adc  test    cl, cl
0x140002ade  jz      short loc_140002B5C
0x140002ae0  lea     rax, stru_140009BD8
0x140002ae7  test    bl, bl
0x140002ae9  lea     rcx, qword_140009AB8
0x140002af0  cmovz   rcx, rax; Event
0x140002af4  xor     r8d, r8d; Wait
0x140002af7  xor     edx, edx; Increment
0x140002af9  call    cs:__imp_KeSetEvent
0x140002b00  nop     dword ptr [rax+rax+00h]
0x140002b05  lea     rcx, g_rlStateLock; SpinLock
0x140002b0c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b13  nop     dword ptr [rax+rax+00h]
0x140002b18  lea     r8, byte_140009B04
0x140002b1f  test    bl, bl
0x140002b21  lea     rdx, byte_1400099E4
0x140002b28  cmovz   rdx, r8
0x140002b2c  lea     rcx, g_rlStateLock; SpinLock
0x140002b33  mov     byte ptr [rdx], 0
0x140002b36  movzx   edx, al; NewIrql
0x140002b39  call    cs:__imp_KeReleaseSpinLock
0x140002b40  nop     dword ptr [rax+rax+00h]
0x140002b45  test    bl, bl
0x140002b47  lea     rcx, byte_140009B4C
0x140002b4e  lea     rax, byte_140009A2C
0x140002b55  cmovz   rax, rcx
0x140002b59  mov     byte ptr [rax], 0
0x140002b5c  add     rsp, 20h
0x140002b60  pop     rbx
0x140002b61  retn
```
