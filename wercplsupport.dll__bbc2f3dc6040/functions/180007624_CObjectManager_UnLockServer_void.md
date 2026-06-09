# CObjectManager::UnLockServer(void)

- ea: `0x180007624`
- end: `0x18000768e`
- name: `?UnLockServer@CObjectManager@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(CObjectManager *__hidden this)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800021ac`
- `0x180002a7c`
- `0x180003e50`
- `0x180003f90`
- `0x180007450`
- `0x18000917c`
- `0x180009244`
- `0x1800092f8`
- `0x180009810`
- `0x180009890`
- `0x180009910`
- `0x180009990`
- `0x180009a10`

## callees

- `0x180007624`
- `0x1800076c8`
- `0x180007c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007643`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007672`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007650`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007650`

## pseudocode

```c
void __fastcall CObjectManager::UnLockServer(CObjectManager *this)
{
  signed __int32 v1; // eax

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( *(_DWORD *)this )
  {
    if ( v1 == *((_DWORD *)this + 1) )
    {
      EnterCriticalSection(&CWerCplSupportService::ms_instance);
      SetEvent(*((HANDLE *)&xmmword_18001C9C0 + 1));
      CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)&CWerCplSupportService::ms_instance, 3u);
      LeaveCriticalSection(&CWerCplSupportService::ms_instance);
    }
    else if ( !v1 )
    {
      CWerCplSupportService::FinalStop((CWerCplSupportService *)&CWerCplSupportService::ms_instance);
    }
  }
}

```

## disassembly

```asm
0x180007624  sub     rsp, 28h
0x180007628  or      eax, 0FFFFFFFFh
0x18000762b  lock xadd [rcx+8], eax
0x180007630  dec     eax
0x180007632  cmp     dword ptr [rcx], 0
0x180007635  jz      short loc_180007689
0x180007637  cmp     eax, [rcx+4]
0x18000763a  jnz     short loc_180007679
0x18000763c  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; lpCriticalSection
0x180007643  call    cs:__imp_EnterCriticalSection
0x180007649  mov     rcx, qword ptr cs:xmmword_18001C9C0+8; hEvent
0x180007650  call    cs:__imp_SetEvent
0x180007656  mov     edx, 3; unsigned int
0x18000765b  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; this
0x180007662  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007667  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; CWerCplSupportService CWerCplSupportService::ms_instance
0x18000766e  add     rsp, 28h
0x180007672  jmp     cs:__imp_LeaveCriticalSection
0x180007679  test    eax, eax
0x18000767b  jnz     short loc_180007689
0x18000767d  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; this
0x180007684  call    ?FinalStop@CWerCplSupportService@@QEAAXXZ; CWerCplSupportService::FinalStop(void)
0x180007689  add     rsp, 28h
0x18000768d  retn
```
