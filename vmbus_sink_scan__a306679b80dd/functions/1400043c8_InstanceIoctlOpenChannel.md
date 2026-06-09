# InstanceIoctlOpenChannel

- ea: `0x1400043c8`
- end: `0x1400044b0`
- name: `InstanceIoctlOpenChannel`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400041b4`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x1400043c8`
- `0x140004d50`
- `0x140010834`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140004435`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004435`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004417`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004417`

## pseudocode

```c
__int64 __fastcall InstanceIoctlOpenChannel(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // edi
  int v7; // r9d

  InstanceWaitLockAcquire();
  if ( *(_QWORD *)(a1 + 80) )
  {
    v6 = -2147483631;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 4);
    if ( v7 )
    {
      if ( (*(_DWORD *)(a3 + 124) & 1) != 0 )
      {
        ExAcquireFastMutex(&VmbusChannelTargetLock);
        InstancePdoUpdateTargetProcessor(a1, *(unsigned int *)(a3 + 120));
        ExReleaseFastMutex(&VmbusChannelTargetLock);
        v7 = *(_DWORD *)(a1 + 4);
      }
      v6 = ChClientOpenChannel(
             *(_QWORD *)(a1 + 288),
             (unsigned int)InstanceOpenComplete,
             a1,
             v7,
             *(_DWORD *)(a1 + 56),
             a3,
             *(_DWORD *)(a1 + 344),
             (*(_DWORD *)(a3 + 124) & 2) != 0);
      if ( v6 >= 0 )
      {
        *(_QWORD *)(a1 + 80) = a2;
        v6 = 259;
      }
      else
      {
        *(_QWORD *)(a1 + 80) = 0;
      }
    }
    else
    {
      v6 = -1073741661;
    }
  }
  InstanceWaitLockRelease(a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400043c8  mov     [rsp+arg_0], rbx
0x1400043cd  mov     [rsp+arg_8], rsi
0x1400043d2  push    rdi
0x1400043d3  sub     rsp, 40h
0x1400043d7  mov     rdi, r8
0x1400043da  mov     rsi, rdx
0x1400043dd  mov     rbx, rcx
0x1400043e0  call    InstanceWaitLockAcquire
0x1400043e5  cmp     qword ptr [rbx+50h], 0
0x1400043ea  jz      short loc_1400043F6
0x1400043ec  mov     edi, 80000011h
0x1400043f1  jmp     loc_140004495
0x1400043f6  mov     r9d, [rbx+4]
0x1400043fa  test    r9d, r9d
0x1400043fd  jnz     short loc_140004409
0x1400043ff  mov     edi, 0C00000A3h
0x140004404  jmp     loc_140004495
0x140004409  mov     eax, [rdi+7Ch]
0x14000440c  test    al, 1
0x14000440e  jz      short loc_140004445
0x140004410  lea     rcx, VmbusChannelTargetLock; FastMutex
0x140004417  call    cs:__imp_ExAcquireFastMutex
0x14000441e  nop     dword ptr [rax+rax+00h]
0x140004423  mov     edx, [rdi+78h]
0x140004426  mov     rcx, rbx
0x140004429  call    InstancePdoUpdateTargetProcessor
0x14000442e  lea     rcx, VmbusChannelTargetLock; FastMutex
0x140004435  call    cs:__imp_ExReleaseFastMutex
0x14000443c  nop     dword ptr [rax+rax+00h]
0x140004441  mov     r9d, [rbx+4]
0x140004445  mov     eax, [rdi+7Ch]
0x140004448  lea     rdx, InstanceOpenComplete
0x14000444f  mov     rcx, [rbx+120h]
0x140004456  mov     r8, rbx
0x140004459  shr     eax, 1
0x14000445b  and     al, 1
0x14000445d  mov     [rsp+48h+var_10], al
0x140004461  mov     eax, [rbx+158h]
0x140004467  mov     [rsp+48h+var_18], eax
0x14000446b  mov     eax, [rbx+38h]
0x14000446e  mov     [rsp+48h+var_20], rdi
0x140004473  mov     [rsp+48h+var_28], eax
0x140004477  call    ChClientOpenChannel
0x14000447c  mov     edi, eax
0x14000447e  test    eax, eax
0x140004480  jns     short loc_14000448C
0x140004482  mov     qword ptr [rbx+50h], 0
0x14000448a  jmp     short loc_140004495
0x14000448c  mov     [rbx+50h], rsi
0x140004490  mov     edi, 103h
0x140004495  mov     rcx, rbx
0x140004498  call    InstanceWaitLockRelease
0x14000449d  mov     rbx, [rsp+48h+arg_0]
0x1400044a2  mov     eax, edi
0x1400044a4  mov     rsi, [rsp+48h+arg_8]
0x1400044a9  add     rsp, 40h
0x1400044ad  pop     rdi
0x1400044ae  retn
```
