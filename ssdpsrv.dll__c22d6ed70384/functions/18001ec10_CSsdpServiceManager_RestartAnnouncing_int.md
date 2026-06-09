# CSsdpServiceManager::RestartAnnouncing(int)

- ea: `0x18001ec10`
- end: `0x18001ec75`
- name: `?RestartAnnouncing@CSsdpServiceManager@@QEAAXH@Z`
- size: `101`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010890`
- `0x18001b720`

## callees

- `0x1800186a0`
- `0x18001ec10`
- `0x18002fcb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec1f`

## pseudocode

```c
void __fastcall CSsdpServiceManager::RestartAnnouncing(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rax
  bool v5; // zf
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(this);
  v4 = this + 1;
  v5 = this[1].DebugInfo == 0;
  v6 = this + 1;
  if ( !v5 )
  {
    while ( v4 )
    {
      if ( !v4->DebugInfo )
        break;
      CSsdpService::RestartAnnouncing((char *)&v4->DebugInfo->CriticalSection, a2);
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v6) )
        break;
      v4 = v6;
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001ec10  mov     [rsp+arg_8], rbx
0x18001ec15  push    rdi
0x18001ec16  sub     rsp, 20h
0x18001ec1a  mov     edi, edx
0x18001ec1c  mov     rbx, rcx
0x18001ec1f  call    cs:__imp_EnterCriticalSection
0x18001ec25  lea     rax, [rbx+28h]
0x18001ec29  cmp     qword ptr [rax], 0
0x18001ec2d  mov     [rsp+28h+arg_0], rax
0x18001ec32  jz      short loc_18001EC61
0x18001ec34  test    rax, rax
0x18001ec37  jz      short loc_18001EC61
0x18001ec39  mov     rcx, [rax]
0x18001ec3c  test    rcx, rcx
0x18001ec3f  jz      short loc_18001EC61
0x18001ec41  add     rcx, 8; Parameter
0x18001ec45  mov     edx, edi; int
0x18001ec47  call    ?RestartAnnouncing@CSsdpService@@QEAAXH@Z; CSsdpService::RestartAnnouncing(int)
0x18001ec4c  lea     rcx, [rsp+28h+arg_0]
0x18001ec51  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001ec56  test    eax, eax
0x18001ec58  jnz     short loc_18001EC61
0x18001ec5a  mov     rax, [rsp+28h+arg_0]
0x18001ec5f  jmp     short loc_18001EC34
0x18001ec61  mov     rcx, rbx
0x18001ec64  mov     rbx, [rsp+28h+arg_8]
0x18001ec69  add     rsp, 20h
0x18001ec6d  pop     rdi
0x18001ec6e  jmp     cs:__imp_LeaveCriticalSection
```
