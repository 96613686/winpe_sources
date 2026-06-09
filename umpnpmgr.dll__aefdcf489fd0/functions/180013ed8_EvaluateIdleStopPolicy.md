# EvaluateIdleStopPolicy

- ea: `0x180013ed8`
- end: `0x180013f44`
- name: `EvaluateIdleStopPolicy`
- size: `108`
- prototype: `void()`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180009d70`
- `0x18000cf30`
- `0x180011d38`
- `0x180014340`

## callees

- `0x180013ed8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f31`

## pseudocode

```c
void EvaluateIdleStopPolicy()
{
  struct _FILETIME *p_pftDueTime; // rdx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  p_pftDueTime = 0;
  if ( PnpIdleStopEnabled )
  {
    _m_prefetchw(&PnpServiceControlFlags);
    if ( (_InterlockedOr(&PnpServiceControlFlags, 8u) & 1) == 0 )
    {
      if ( !PnpServiceOutstandingInstalls )
      {
        if ( PnpRpcIdle )
        {
          pftDueTime = (struct _FILETIME)-1200000000LL;
          p_pftDueTime = &pftDueTime;
        }
      }
      SetThreadpoolTimer(PnpIdleStopTimer, p_pftDueTime, 0, 0);
    }
    _InterlockedAnd(&PnpServiceControlFlags, 0xFFFFFFF7);
  }
}

```

## disassembly

```asm
0x180013ed8  sub     rsp, 28h
0x180013edc  xor     edx, edx
0x180013ede  cmp     cs:PnpIdleStopEnabled, edx
0x180013ee4  jz      short loc_180013F3F
0x180013ee6  prefetchw byte ptr cs:PnpServiceControlFlags
0x180013eed  mov     eax, cs:PnpServiceControlFlags
0x180013ef3  mov     ecx, eax
0x180013ef5  or      ecx, 8
0x180013ef8  lock cmpxchg cs:PnpServiceControlFlags, ecx
0x180013f00  jnz     short loc_180013EF3
0x180013f02  test    al, 1
0x180013f04  jnz     short loc_180013F37
0x180013f06  cmp     cs:PnpServiceOutstandingInstalls, edx
0x180013f0c  jnz     short loc_180013F24
0x180013f0e  cmp     cs:PnpRpcIdle, edx
0x180013f14  jz      short loc_180013F24
0x180013f16  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x180013f1f  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180013f24  mov     rcx, cs:PnpIdleStopTimer; pti
0x180013f2b  xor     r9d, r9d; msWindowLength
0x180013f2e  xor     r8d, r8d; msPeriod
0x180013f31  call    cs:__imp_SetThreadpoolTimer
0x180013f37  lock and cs:PnpServiceControlFlags, 0FFFFFFF7h
0x180013f3f  add     rsp, 28h
0x180013f43  retn
```
