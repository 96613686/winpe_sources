# CSsdpServiceManager::StopAnnouncing(int)

- ea: `0x18001ba64`
- end: `0x18001bac5`
- name: `?StopAnnouncing@CSsdpServiceManager@@QEAAXH@Z`
- size: `97`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001b720`

## callees

- `0x1800186a0`
- `0x18001ba64`
- `0x180022a80`
- `0x18002fd54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001babe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba6d`

## pseudocode

```c
void __fastcall CSsdpServiceManager::StopAnnouncing(struct _RTL_CRITICAL_SECTION *this)
{
  bool v2; // zf
  CSsdpService *v3; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v4; // [rsp+40h] [rbp+18h] BYREF

  EnterCriticalSection(this);
  v2 = this[1].DebugInfo == 0;
  v4 = this + 1;
  if ( !v2 )
  {
    v3 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v4, &v3) )
        break;
      CSsdpService::StopAnnouncing(v3);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v4) );
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001ba64  push    rbx
0x18001ba66  sub     rsp, 20h
0x18001ba6a  mov     rbx, rcx
0x18001ba6d  call    cs:__imp_EnterCriticalSection
0x18001ba73  lea     rax, [rbx+28h]
0x18001ba77  cmp     qword ptr [rax], 0
0x18001ba7b  mov     [rsp+28h+arg_10], rax
0x18001ba80  jz      short loc_18001BAB6
0x18001ba82  mov     [rsp+28h+arg_0], 0
0x18001ba8b  lea     rdx, [rsp+28h+arg_0]
0x18001ba90  lea     rcx, [rsp+28h+arg_10]
0x18001ba95  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001ba9a  test    eax, eax
0x18001ba9c  jnz     short loc_18001BAB6
0x18001ba9e  mov     rcx, [rsp+28h+arg_0]; this
0x18001baa3  call    ?StopAnnouncing@CSsdpService@@QEAAXH@Z; CSsdpService::StopAnnouncing(int)
0x18001baa8  lea     rcx, [rsp+28h+arg_10]
0x18001baad  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001bab2  test    eax, eax
0x18001bab4  jz      short loc_18001BA8B
0x18001bab6  mov     rcx, rbx
0x18001bab9  add     rsp, 20h
0x18001babd  pop     rbx
0x18001babe  jmp     cs:__imp_LeaveCriticalSection
```
