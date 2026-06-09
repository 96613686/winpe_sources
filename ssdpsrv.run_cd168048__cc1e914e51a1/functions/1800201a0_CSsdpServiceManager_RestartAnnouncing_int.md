# CSsdpServiceManager::RestartAnnouncing(int)

- ea: `0x1800201a0`
- end: `0x180020210`
- name: `?RestartAnnouncing@CSsdpServiceManager@@QEAAXH@Z`
- size: `112`
- prototype: `void(CSsdpServiceManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011d00`
- `0x18001ca60`

## callees

- `0x180019920`
- `0x1800201a0`
- `0x180031fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201af`

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
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v6) )
        break;
      v4 = v6;
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x1800201a0  mov     [rsp+arg_8], rbx
0x1800201a5  push    rdi
0x1800201a6  sub     rsp, 20h
0x1800201aa  mov     edi, edx
0x1800201ac  mov     rbx, rcx
0x1800201af  call    cs:__imp_EnterCriticalSection
0x1800201b6  nop     dword ptr [rax+rax+00h]
0x1800201bb  lea     rax, [rbx+28h]
0x1800201bf  cmp     qword ptr [rax], 0
0x1800201c3  mov     [rsp+28h+arg_0], rax
0x1800201c8  jz      short loc_1800201F7
0x1800201ca  test    rax, rax
0x1800201cd  jz      short loc_1800201F7
0x1800201cf  mov     rcx, [rax]
0x1800201d2  test    rcx, rcx
0x1800201d5  jz      short loc_1800201F7
0x1800201d7  add     rcx, 8; Parameter
0x1800201db  mov     edx, edi; int
0x1800201dd  call    ?RestartAnnouncing@CSsdpService@@QEAAXH@Z; CSsdpService::RestartAnnouncing(int)
0x1800201e2  lea     rcx, [rsp+28h+arg_0]
0x1800201e7  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800201ec  test    eax, eax
0x1800201ee  jnz     short loc_1800201F7
0x1800201f0  mov     rax, [rsp+28h+arg_0]
0x1800201f5  jmp     short loc_1800201CA
0x1800201f7  mov     rcx, rbx
0x1800201fa  mov     rbx, [rsp+28h+arg_8]
0x1800201ff  add     rsp, 20h
0x180020203  pop     rdi
0x180020204  jmp     cs:__imp_LeaveCriticalSection
```
