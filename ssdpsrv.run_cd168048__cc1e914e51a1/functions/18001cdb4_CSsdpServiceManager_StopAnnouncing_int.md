# CSsdpServiceManager::StopAnnouncing(int)

- ea: `0x18001cdb4`
- end: `0x18001ce20`
- name: `?StopAnnouncing@CSsdpServiceManager@@QEAAXH@Z`
- size: `108`
- prototype: `void __fastcall(CSsdpServiceManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001ca60`

## callees

- `0x180019920`
- `0x18001cdb4`
- `0x180024490`
- `0x180032068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cdbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cdbd`

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
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v4, &v3) )
        break;
      CSsdpService::StopAnnouncing(v3);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v4) );
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001cdb4  push    rbx
0x18001cdb6  sub     rsp, 20h
0x18001cdba  mov     rbx, rcx
0x18001cdbd  call    cs:__imp_EnterCriticalSection
0x18001cdc4  nop     dword ptr [rax+rax+00h]
0x18001cdc9  lea     rax, [rbx+28h]
0x18001cdcd  cmp     qword ptr [rax], 0
0x18001cdd1  mov     [rsp+28h+arg_10], rax
0x18001cdd6  jz      short loc_18001CE0C
0x18001cdd8  mov     [rsp+28h+arg_0], 0
0x18001cde1  lea     rdx, [rsp+28h+arg_0]
0x18001cde6  lea     rcx, [rsp+28h+arg_10]
0x18001cdeb  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18001cdf0  test    eax, eax
0x18001cdf2  jnz     short loc_18001CE0C
0x18001cdf4  mov     rcx, [rsp+28h+arg_0]; this
0x18001cdf9  call    ?StopAnnouncing@CSsdpService@@QEAAXH@Z; CSsdpService::StopAnnouncing(int)
0x18001cdfe  lea     rcx, [rsp+28h+arg_10]
0x18001ce03  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001ce08  test    eax, eax
0x18001ce0a  jz      short loc_18001CDE1
0x18001ce0c  mov     rcx, rbx
0x18001ce0f  add     rsp, 20h
0x18001ce13  pop     rbx
0x18001ce14  jmp     cs:__imp_LeaveCriticalSection
```
